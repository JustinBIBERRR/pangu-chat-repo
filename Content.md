## 📄 文件内容


### `pangu-chat-client/__mocks__/axios.ts`
```ts
import mockAxios from 'jest-mock-axios';

export default {
  ...mockAxios,
  ...{
    create: jest.fn(() => ({
      ...mockAxios,
    })),
  },
};

```

### `pangu-chat-client/.build_config/build-npm.sh`
```sh
#!/bin/bash
# NPM_TAG 构建参数 npm包发布tag
if [ "$NPM_Tag" != "" ]
then
  echo 'NPM_TAG is exits';
else
  echo 'set NPM_TAG latest';
  # 默认发布beta版本
  NPM_TAG='beta';
fi
echo "NPM_TAG is ${NPM_TAG}";
# VERSION 构建参数 npm包发布版本
if [ "" != "$VERSION" ]
then
 # 应用自定义版本号
 sed  -i "s/\"version\":.*$/\"version\":\"${VERSION}\",/" packages/toolkit/package.json
else
echo 'set version 0.0.1';
 VERSION='0.0.1';  
fi
echo "version is ${VERSION}";
# npm config set registry=http://szg1.artifactory.inhuawei.com/artifactory/api/npm/cbu-npm-public/
# npm config set @cloud:registry=https://maven.cloudartifact.lfg.dragon.tools.huawei.com/artifactory/api/npm/npm-cbu-common

npm config list

npm install --force && npm run build:types


# tar -cvf "aio-toolkit-deep-cli-$VERSION.tar.gz" --exclude=node_modules --exclude=.git  .

```

### `pangu-chat-client/.build_config/build.sh`
```sh
#!/bin/bash
 
sed -i "s|#{VITE_CARD_STATIC_PATH}|${VITE_CARD_STATIC_PATH}|" ./.env.client-prod
sed -i "s|#{VITE_IS_ULANQAB_ENV}|${VITE_IS_ULANQAB_ENV}|" ./.env.client-prod
 
staticReleaseVersion=$staticReleaseVersion
# 伏羲没有提供对应的环境变量，通过查看版本号有几个 . 来判断是类生产还是生产环境
dot_count=$(echo "$staticReleaseVersion" | awk -F'.' '{print NF-1}')
 
client_relative_path="js/pangu-chat-client.js"
 
VITE_CLIENT_ASSET_PATH=""
# 根据 '.' 的数量确定 VITE_CLIENT_PATH 的值
if [ "$dot_count" -eq 3 ]; then
    VITE_CLIENT_ASSET_PATH="https://portal-hc-cdn.ulanqab.huawei.com/pangu-chat-client/${staticReleaseVersion}/client/"
elif [ "$dot_count" -eq 2 ]; then
    VITE_CLIENT_ASSET_PATH="https://portal.hc-cdn.com/pangu-chat-client/${staticReleaseVersion}/client/"
else
    echo "staticReleaseVersion 中 '.' 的数量不符合要求，无法进行替换操作。"
    exit 1  # 退出脚本
fi
 
VITE_CLIENT_PATH="${VITE_CLIENT_ASSET_PATH}${client_relative_path}"
 
sed -i "s|#{VITE_CLIENT_ASSET_PATH}|${VITE_CLIENT_ASSET_PATH}|" ./.env
sed -i "s|#{VITE_CLIENT_PATH}|${VITE_CLIENT_PATH}|" ./.env.loader-prod
 
echo "VITE_CLIENT_ASSET_PATH is ${VITE_CLIENT_ASSET_PATH}"
echo "VITE_CLIENT_PATH is ${VITE_CLIENT_PATH}"
echo "VITE_CARD_STATIC_PATH is ${VITE_CARD_STATIC_PATH}"
echo "VITE_IS_ULANQAB_ENV is ${VITE_IS_ULANQAB_ENV}"
 
export NODE_OPTIONS=--max_old_space_size=8192
 
npm config set registry=https://maven.cloudartifact.lfg.dragon.tools.huawei.com/artifactory/api/npm/cbu-npm-public/
npm install --force 
npm run build-client
npm run build-loader
npm run build-panel
 
```

### `pangu-chat-client/.cloudbuild/pangu-chat-client-npm.yml`
```yml
version: 1.0
name: pangu-chat-client-npm
language: nodejs

dependencies:
  base:
    nodejs: 16.15.0

machine:
  standard:
    x86_euler2.10:
      - default

scripts:
  - sh ./.build_config/build-npm.sh

artifacts:
  static:
    - output: dist
      include:
        - '*'
      exclude:
        - '*.java'
        - '*.kotlin'
        - '*.class'
        - '*.jar'
        - '*.war'
        - '*.c'
        - '*.cpp'
        - '*.h'
        - '*.o'
        - '*.so'
        - '*.dll'
        - '*.out'
        - '*.py'
        - '*.whl'
        - '*.go'

```

### `pangu-chat-client/.cloudbuild/pangu-chat-client.yml`
```yml
version: '2.0'
env:
  label: Fuxi-Build-x86-euler2.10-vpc-nat
  build_box:
    fuxi_os: x86_euler2.10
    dependencies:
      nodejs: 18.14.1

#构建参数
params:
  - name: product
    value: cloudbuild2.0
  - name: CID_credible_repo
    value: true

#构建步骤
steps:
  PRE_BUILD:
    - checkout
  BUILD:
    - build_execute:
        command: sh .build_config/build.sh
  POST_BUILD:
    - hwcloud_artifact:
        version: '1.0'
        static:
          - output: dist
            include:
              - '*'
            exclude:
              - '*.java'
              - '*.kotlin'
              - '*.class'
              - '*.jar'
              - '*.war'
              - '*.c'
              - '*.cpp'
              - '*.h'
              - '*.o'
              - '*.so'
              - '*.dll'
              - '*.out'
              - '*.py'
              - '*.whl'
              - '*.go'

```

### `pangu-chat-client/.codecheck/check.yml`
```yml
version: 2.0

steps:
  pre_codecheck:
    - checkout

tool_params:
  secsolar:
    source_dir: ./

```

### `pangu-chat-client/src/application/core/conversation/__tests__/ConversationUseCase.updateBotContent.test.ts`
```ts
import ConversationUseCase from '../ConversationUseCase';
import { BotMessageDTO, Status, BotMessageType } from '@/domain/core/conversation/message/Message';

describe('ConversationUseCase.updateBotContent', () => {
  let useCase: ConversationUseCase;
  let mockRepository: any;

  beforeEach(() => {
    // Mock repository
    mockRepository = {
      getLatestMessage: jest.fn(),
      appendContentToLatestAnswer: jest.fn(),
      updateLastContent: jest.fn(),
      updateAnswerStatus: jest.fn(),
      addAnswerToLatestMessage: jest.fn(),
      addMessage: jest.fn(),
    };

    // Create use case with mocked repository
    useCase = new ConversationUseCase();
    (useCase as any).conversationRepository = mockRepository;
  });

  describe('场景1: 连续追加text内容', () => {
    test('应该正确追加text内容', () => {
      // Arrange
      const lastMessage = {
        role: 'bot',
        answers: [
          {
            answerId: 'ans-1',
            status: Status.Bot_Sending,
            contents: [
              { type: 'text' as BotMessageType, content: 'Hello ' },
            ],
          },
        ],
      };

      const botContent: BotMessageDTO = {
        messageId: 'msg-1',
        requestId: 'req-1',
        answerId: 'ans-1',
        role: 'bot',
        status: Status.Bot_Sending,
        type: 'text',
        content: 'World',
      };

      mockRepository.getLatestMessage.mockReturnValue(lastMessage);

      // Act
      useCase.updateBotContent(botContent);

      // Assert
      expect(mockRepository.updateLastContent).toHaveBeenCalledWith({
        type: 'text',
        content: 'Hello World',
      });
      expect(mockRepository.updateAnswerStatus).toHaveBeenCalledWith('ans-1', Status.Bot_Sending);
    });
  });

  describe('场景2: 连续追加rag内容', () => {
    test('应该正确追加rag内容', () => {
      // Arrange
      const lastMessage = {
        role: 'bot',
        answers: [
          {
            answerId: 'ans-1',
            status: Status.Bot_Sending,
            contents: [
              { type: 'rag' as BotMessageType, content: 'RAG part 1 ' },
            ],
          },
        ],
      };

      const botContent: BotMessageDTO = {
        messageId: 'msg-1',
        requestId: 'req-1',
        answerId: 'ans-1',
        role: 'bot',
        status: Status.Bot_Sending,
        type: 'rag',
        content: 'RAG part 2',
      };

      mockRepository.getLatestMessage.mockReturnValue(lastMessage);

      // Act
      useCase.updateBotContent(botContent);

      // Assert
      expect(mockRepository.updateLastContent).toHaveBeenCalledWith({
        type: 'rag',
        content: 'RAG part 1 RAG part 2',
      });
    });
  });

  describe('场景3: 不同类型内容，新增content', () => {
    test('应该新增content而不是合并（text -> card）', () => {
      // Arrange
      const lastMessage = {
        role: 'bot',
        answers: [
          {
            answerId: 'ans-1',
            status: Status.Bot_Sending,
            contents: [
              { type: 'text' as BotMessageType, content: 'Hello' },
            ],
          },
        ],
      };

      const botContent: BotMessageDTO = {
        messageId: 'msg-1',
        requestId: 'req-1',
        answerId: 'ans-1',
        role: 'bot',
        status: Status.Bot_Sending,
        type: 'card',
        content: '{"type": "card"}',
        cardRenderId: 'card-1',
      };

      mockRepository.getLatestMessage.mockReturnValue(lastMessage);

      // Act
      useCase.updateBotContent(botContent);

      // Assert
      expect(mockRepository.appendContentToLatestAnswer).toHaveBeenCalledWith({
        type: 'card',
        content: '{"type": "card"}',
        cardRenderId: 'card-1',
      });
      expect(mockRepository.updateLastContent).not.toHaveBeenCalled();
    });

    test('应该新增content而不是合并（card -> text）', () => {
      // Arrange
      const lastMessage = {
        role: 'bot',
        answers: [
          {
            answerId: 'ans-1',
            status: Status.Bot_Sending,
            contents: [
              { type: 'card' as BotMessageType, content: '{"type": "card"}', cardRenderId: 'card-1' },
            ],
          },
        ],
      };

      const botContent: BotMessageDTO = {
        messageId: 'msg-1',
        requestId: 'req-1',
        answerId: 'ans-1',
        role: 'bot',
        status: Status.Bot_Sending,
        type: 'text',
        content: 'Hello',
      };

      mockRepository.getLatestMessage.mockReturnValue(lastMessage);

      // Act
      useCase.updateBotContent(botContent);

      // Assert
      expect(mockRepository.appendContentToLatestAnswer).toHaveBeenCalledWith({
        type: 'text',
        content: 'Hello',
        cardRenderId: undefined,
      });
      expect(mockRepository.updateLastContent).not.toHaveBeenCalled();
    });

    test('应该新增content而不是合并（rag -> card）', () => {
      // Arrange
      const lastMessage = {
        role: 'bot',
        answers: [
          {
            answerId: 'ans-1',
            status: Status.Bot_Sending,
            contents: [
              { type: 'rag' as BotMessageType, content: 'RAG content' },
            ],
          },
        ],
      };

      const botContent: BotMessageDTO = {
        messageId: 'msg-1',
        requestId: 'req-1',
        answerId: 'ans-1',
        role: 'bot',
        status: Status.Bot_Sending,
        type: 'card',
        content: '{"type": "card"}',
        cardRenderId: 'card-1',
      };

      mockRepository.getLatestMessage.mockReturnValue(lastMessage);

      // Act
      useCase.updateBotContent(botContent);

      // Assert
      expect(mockRepository.appendContentToLatestAnswer).toHaveBeenCalledWith({
        type: 'card',
        content: '{"type": "card"}',
        cardRenderId: 'card-1',
      });
      expect(mockRepository.updateLastContent).not.toHaveBeenCalled();
    });
  });

  describe('场景4: 新增answer', () => {
    test('应该新增answer到message', () => {
      // Arrange
      const lastMessage = {
        role: 'bot',
        requestId: 'req-1',
        answers: [
          {
            answerId: 'ans-1',
            status: Status.Bot_Sent,
            contents: [
              { type: 'text', content: 'Hello' },
            ],
          },
        ],
      };

      const botContent: BotMessageDTO = {
        messageId: 'msg-1',
        requestId: 'req-1',
        answerId: 'ans-2',
        role: 'bot',
        status: Status.Bot_Sending,
        type: 'text',
        content: 'World',
      };

      mockRepository.getLatestMessage.mockReturnValue(lastMessage);

      // Act
      useCase.updateBotContent(botContent);

      // Assert
      expect(mockRepository.addAnswerToLatestMessage).toHaveBeenCalledWith({
        answerId: 'ans-2',
        status: Status.Bot_Sending,
        type: 'text',
        refer: [],
        contents: [
          {
            type: 'text',
            content: 'World',
          },
        ],
        feedback: undefined,
        manualSuggestAction: undefined,
      });
    });
  });

  describe('场景5: 新增message', () => {
    test('应该新增message到conversation', () => {
      // Arrange
      mockRepository.getLatestMessage.mockReturnValue(undefined);

      const botContent: BotMessageDTO = {
        messageId: 'msg-1',
        requestId: 'req-1',
        answerId: 'ans-1',
        role: 'bot',
        status: Status.Bot_Sending,
        type: 'text',
        content: 'Hello',
      };

      // Act
      useCase.updateBotContent(botContent);

      // Assert
      expect(mockRepository.addMessage).toHaveBeenCalledWith({
        messageId: 'msg-1',
        role: 'bot',
        requestId: 'req-1',
        suggests: undefined,
        thinkContents: undefined,
        answers: [
          {
            answerId: 'ans-1',
            status: Status.Bot_Sending,
            type: 'text',
            refer: [],
            contents: [
              {
                type: 'text',
                content: 'Hello',
              },
            ],
            feedback: undefined,
            manualSuggestAction: undefined,
          },
        ],
      });
    });
  });

  describe('边界条件测试', () => {
    test('应该处理空content', () => {
      // Arrange
      const lastMessage = {
        role: 'bot',
        answers: [
          {
            answerId: 'ans-1',
            status: Status.Bot_Sending,
            contents: [],
          },
        ],
      };

      const botContent: BotMessageDTO = {
        messageId: 'msg-1',
        requestId: 'req-1',
        answerId: 'ans-1',
        role: 'bot',
        status: Status.Bot_Sending,
        type: 'text',
        content: 'Hello',
      };

      mockRepository.getLatestMessage.mockReturnValue(lastMessage);

      // Act
      useCase.updateBotContent(botContent);

      // Assert
      expect(mockRepository.appendContentToLatestAnswer).toHaveBeenCalled();
    });

    test('应该处理空answer', () => {
      // Arrange
      const lastMessage = {
        role: 'bot',
        answers: [],
      };

      const botContent: BotMessageDTO = {
        messageId: 'msg-1',
        requestId: 'req-1',
        answerId: 'ans-1',
        role: 'bot',
        status: Status.Bot_Sending,
        type: 'text',
        content: 'Hello',
      };

      mockRepository.getLatestMessage.mockReturnValue(lastMessage);

      // Act
      useCase.updateBotContent(botContent);

      // Assert
      expect(mockRepository.addAnswerToLatestMessage).toHaveBeenCalled();
    });
  });
});
```
