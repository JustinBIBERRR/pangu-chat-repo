# 项目概览：pangu_11.6.2


## 📁 目录结构


```
pangu_11.6.2/
└── pangu-chat-client/
    └── __mocks__/
        ├── axios.ts
    └── .build_config/
        ├── build-npm.sh
        ├── build.sh
    └── .cloudbuild/
        ├── pangu-chat-client-npm.yml
        ├── pangu-chat-client.yml
    └── .codecheck/
        ├── check.yml
    └── src/
        ├── application/
        │   ├── core/
        │   │   ├── conversation/
        │   │   │   ├── __tests__/
        │   │   │   │   ├── ConversationUseCase.updateBotContent.test.ts
        │   │   │   ├── business-card/
        │   │   │   │   ├── BusinessCardUseCase.ts
        │   │   │   ├── config/
        │   │   │   │   ├── ConversationConfigUseCase.ts
        │   │   │   │   ├── DefaultBotMessage.ts
        │   │   │   ├── credit/
        │   │   │   │   ├── CreditManagementUseCase.ts
        │   │   │   ├── decision/
        │   │   │   │   ├── __tests__/
        │   │   │   │   │   ├── MessageUpdateDecisionMaker.test.ts
        │   │   │   │   ├── MessageUpdateDecision.ts
        │   │   │   ├── deepThink/
        │   │   │   │   ├── converter/
        │   │   │   │   │   ├── DeepThinkConverter.ts
        │   │   │   │   ├── DeepThinkUseCase.ts
        │   │   │   ├── files/
        │   │   │   │   ├── ConversationImagesUseCase.ts
        │   │   │   ├── history/
        │   │   │   │   ├── converter/
        │   │   │   │   │   ├── HistoryDtoConverter.ts
        │   │   │   │   ├── dto/
        │   │   │   │   │   ├── ConversationHistoryDTO.ts
        │   │   │   │   ├── ConversationHistoryUseCase.ts
        │   │   │   ├── manual/
        │   │   │   │   ├── ManualServiceUseCase.ts
        │   │   │   ├── polling/
        │   │   │   │   ├── PollingUseCase.ts
        │   │   │   ├── strategy/
        │   │   │   │   ├── __tests__/
        │   │   │   │   │   ├── MessageContentStrategy.test.ts
        │   │   │   │   ├── MessageContentStrategy.ts
        │   │   │   ├── ConversationUseCase.ts
        │   │   ├── userDistributary/
        │   │   │   └── UserDistributaryUseCase.ts
        │   ├── shared/
        │   │   ├── auth/
        │   │   │   ├── AuthUseCase.ts
        │   │   ├── context/
        │   │   │   └── WebContextUseCase.ts
        │   ├── support/
        │   │   └── card/
        │   │       ├── CardDelegate.ts
        │   │       ├── CardUseCase.ts
        │   │       ├── RemoteCardConfig.ts
        │   │   └── console-login/
        │   │       ├── ConsoleLoginUseCase.ts
        │   │   └── feedback/
        │   │       ├── FeedbackUseCase.ts
        │   │   └── pager/
        │   │       ├── pagerUseCase.ts
        │   │   └── recommendation/
        │   │       ├── RecommendationUseCase.ts
        │   │   └── refer/
        │   │       ├── ReferUseCase.ts
        │   │   └── suggested-prompt/
        │   │       ├── SuggestedPromptUseCase.ts
        │   │   └── user-collect/
        │   │       └── UserCollectionUseCase.ts
        ├── domain/
        │   ├── common/
        │   │   ├── VO/
        │   │   │   └── CommonResponseVO.ts
        │   ├── core/
        │   │   ├── conversation/
        │   │   │   ├── business-card/
        │   │   │   │   ├── delegate/
        │   │   │   │   │   ├── BusinessCardDelegate.ts
        │   │   │   │   ├── models/
        │   │   │   │   │   └── BusinessCardCriteria.ts
        │   │   │   ├── config/
        │   │   │   │   ├── delegate/
        │   │   │   │   │   ├── ConversationConfigDelegate.ts
        │   │   │   │   ├── models/
        │   │   │   │   │   └── ConversationConfigVO.ts
        │   │   │   ├── credit/
        │   │   │   │   ├── delegate/
        │   │   │   │   │   └── CreditManagementDelegate.ts
        │   │   │   ├── files/
        │   │   │   │   ├── delegate/
        │   │   │   │   │   ├── ConversationImagesDelegate.ts
        │   │   │   │   ├── models/
        │   │   │   │   │   └── ConversationImagesVO.ts
        │   │   │   ├── history/
        │   │   │   │   ├── delegate/
        │   │   │   │   │   ├── ConversationHistoryDelegate.ts
        │   │   │   │   ├── models/
        │   │   │   │   │   ├── ConversationHistoryCriteria.ts
        │   │   │   │   │   ├── ConversationHistoryVO.ts
        │   │   │   │   ├── PO/
        │   │   │   │   │   └── ConversationHistoryPO.ts
        │   │   │   ├── manual/
        │   │   │   │   ├── delegate/
        │   │   │   │   │   ├── ManualServiceDelegate.ts
        │   │   │   │   ├── models/
        │   │   │   │   │   └── ManualServiceVO.ts
        │   │   │   ├── message/
        │   │   │   │   ├── delegate/
        │   │   │   │   │   ├── MessageDelegate.ts
        │   │   │   │   ├── Message.ts
        │   │   │   │   ├── ThinkMessage.ts
        │   │   │   ├── polling/
        │   │   │   │   ├── delegate/
        │   │   │   │   │   ├── PollingServiceDelegate.ts
        │   │   │   │   ├── models/
        │   │   │   │   │   └── PollingCriteria.ts
        │   │   │   │   │   └── PollingVO.ts
        │   │   │   ├── repository/
        │   │   │   │   ├── ConversationRepository.ts
        │   │   │   ├── Conversation.ts
        │   │   │   ├── ConversationVO.ts
        │   │   ├── userDistributary/
        │   │   │   └── delegate/
        │   │   │       ├── BrandDistributaryDelegate.ts
        │   │   │       ├── UserDistributary.ts
        │   │   │   └── PO/
        │   │   │       ├── useDistributaryPO.ts
        │   │   │   └── UserDIstributary.ts
        │   ├── recommendation/
        │   │   ├── delegate/
        │   │   │   ├── SupportDelegate.ts
        │   │   ├── models/
        │   │   │   └── PromptVO.ts
        │   │   │   └── SupportCriteria.ts
        │   │   │   └── SupportVO.ts
        │   ├── shared/
        │   │   ├── auth/
        │   │   │   ├── delegate/
        │   │   │   │   ├── AuthDelegate.ts
        │   │   │   ├── valueobject/
        │   │   │   │   └── User.type.ts
        │   │   │   │   └── UserVO.ts
        │   │   ├── context/
        │   │   │   ├── delegate/
        │   │   │   │   └── WebContextDelegate.ts
        │   │   ├── criteria/
        │   │   │   └── ListCriteria.ts
        │   │   │   └── QueryCriteria.ts
        │   ├── suggested-prompt/
        │   │   ├── delegate/
        │   │   │   ├── SuggestedPromptDelegate.ts
        │   │   ├── models/
        │   │   │   └── SuggestedPromptCriteria.ts
        │   │   │   └── SuggestedPromptVO.ts
        │   ├── support/
        │   │   ├── console-login/
        │   │   │   ├── delegate/
        │   │   │   │   └── ConsoleLoginDelegate.ts
        │   │   ├── feedback/
        │   │   │   ├── delegate/
        │   │   │   │   ├── FeedbackDelegate.ts
        │   │   │   ├── Feedback.ts
        │   │   ├── Pager/
        │   │   │   ├── delegate/
        │   │   │   │   ├── PagerDelegate.ts
        │   │   │   ├── Pager.ts
        │   │   ├── refer/
        │   │   │   ├── delegate/
        │   │   │   │   └── ServiceNameDelegate.ts
        │   │   ├── user-collect/
        │   │   │   └── delegate/
        │   │   │       ├── UserCollectionDelegate.ts
        │   │   │   └── UserCollection.ts
        │   ├── window/
        │   │   └── global.d.ts
        ├── infrastructure/
        │   ├── adapter/
        │   │   ├── common/
        │   │   │   ├── decorators.ts
        │   │   ├── inbound/
        │   │   │   ├── model/
        │   │   │   │   ├── Feedback.ts
        │   │   │   │   ├── History.ts
        │   │   │   ├── AdapterIntegrator.ts
        │   │   │   ├── AdapterIntegratorProvider.ts
        │   │   │   ├── AuthAdapter.ts
        │   │   │   ├── ContextAdapter.ts
        │   │   │   ├── CustomConversationStart.ts
        │   │   │   ├── CustomFeedbackResponse.ts
        │   │   │   ├── CustomHistoryResponse.ts
        │   │   │   ├── CustomHotSpotSuggest.ts
        │   │   │   ├── CustomOnMessageEvent.ts
        │   │   │   ├── CustomOpenUrl.ts
        │   │   │   ├── CustomRefreshPrompts.ts
        │   │   │   ├── CustomRelatedSuggest.ts
        │   │   │   ├── CustomRemoteCard.ts
        │   │   │   ├── CustomSearchHint.ts
        │   │   │   ├── CustomSendMessageRequest.ts
        │   │   │   ├── CustomSendResponseJson.ts
        │   │   │   ├── CustomSuggestPrompts.ts
        │   │   ├── outbound/
        │   │   │   ├── delegate/
        │   │   │   │   ├── auth/
        │   │   │   │   │   ├── PO/
        │   │   │   │   │   │   ├── W3UserPO.ts
        │   │   │   │   │   ├── user/
        │   │   │   │   │   │   ├── LoginIns.ts
        │   │   │   │   │   │   ├── UserContext.ts
        │   │   │   │   │   ├── AuthDelegateImpl.ts
        │   │   │   │   ├── card/
        │   │   │   │   │   ├── CardDelegateImpl.ts
        │   │   │   │   ├── console-login/
        │   │   │   │   │   ├── ConsoleLoginDelegateImpl.ts
        │   │   │   │   ├── conversation-config/
        │   │   │   │   │   ├── ConversationConfigDelegateImpl.ts
        │   │   │   │   ├── core/
        │   │   │   │   │   ├── conversation/
        │   │   │   │   │   │   ├── business-card/
        │   │   │   │   │   │   │   ├── BusinessCardDelegateImpl.ts
        │   │   │   │   │   │   ├── credit/
        │   │   │   │   │   │   │   ├── CreditManagementDelegateImpl.ts
        │   │   │   │   │   │   ├── history/
        │   │   │   │   │   │   │   ├── converter/
        │   │   │   │   │   │   │   │   ├── HistoryAdditionalInfoHandler.ts
        │   │   │   │   │   │   │   │   ├── HistoryBotContentConverter.ts
        │   │   │   │   │   │   │   │   ├── HistoryPoConverter.ts
        │   │   │   │   │   │   │   │   ├── HistorySeatContentConverter.ts
        │   │   │   │   │   │   │   │   ├── HistoryThinkContentConverter.ts
        │   │   │   │   │   │   │   ├── ConversationHistoryDelegateImpl.ts
        │   │   │   │   │   │   ├── manual/
        │   │   │   │   │   │   │   ├── converter/
        │   │   │   │   │   │   │   │   ├── ManualServiceConverter.ts
        │   │   │   │   │   │   │   ├── PO/
        │   │   │   │   │   │   │   │   ├── ManualServicePO.ts
        │   │   │   │   │   │   │   ├── ManualServiceDelegateImpl.ts
        │   │   │   │   │   │   ├── messagedelegate/
        │   │   │   │   │   │   │   ├── EventSource.js
        │   │   │   │   │   │   │   ├── MessageDelegateImpl.ts
        │   │   │   │   │   │   │   ├── MessageDelegateSymbol.ts
        │   │   │   │   │   │   │   ├── MessagePollingDelegateImpl.ts
        │   │   │   │   │   │   ├── PO/
        │   │   │   │   │   │   │   ├── ConversationResponsePO.ts
        │   │   │   │   │   │   ├── polling/
        │   │   │   │   │   │   │   ├── PollingDelegateImpl.ts
        │   │   │   │   │   │   ├── CustomEventSource.ts
        │   │   │   │   │   │   ├── useReturnMessage.ts
        │   │   │   │   │   ├── type/
        │   │   │   │   │   │   ├── cutsomEventSourceType.ts
        │   │   │   │   │   ├── userDistributary/
        │   │   │   │   │   │   └── converter/
        │   │   │   │   │   │       ├── BrandDistributaryPoConverter.ts
        │   │   │   │   │   │       ├── UserDistributaryPoConverter.ts
        │   │   │   │   │   │   └── BrandDisrtibutaryDelegateImpl.ts
        │   │   │   │   │   │   └── UserDisrtibutaryDelegateImpl.ts
        │   │   │   │   ├── feedback/
        │   │   │   │   │   ├── FeedbackDelegateImpl.ts
        │   │   │   │   ├── files/
        │   │   │   │   │   ├── ConversationImagesDelegateImpl.ts
        │   │   │   │   ├── pager/
        │   │   │   │   │   ├── PagerDelegateImpl.ts
        │   │   │   │   ├── refer/
        │   │   │   │   │   ├── ServiceNameDelegateImpl.ts
        │   │   │   │   ├── suggested-prompt/
        │   │   │   │   │   ├── converter/
        │   │   │   │   │   │   ├── consts.ts
        │   │   │   │   │   │   ├── SuggestPromptConverter.ts
        │   │   │   │   │   ├── PO/
        │   │   │   │   │   │   ├── SuggestPromptPO.ts
        │   │   │   │   │   ├── SuggestedPromptDelegateImpl.ts
        │   │   │   │   ├── user-collect/
        │   │   │   │   │   └── UserCollectionDelegateImpl.ts
        │   │   │   ├── repository/
        │   │   │   │   └── core/
        │   │   │   │       └── conversation/
        │   │   │   │           └── stop/
        │   │   │   │               ├── ConversationStopHandler.ts
        │   │   │   │           └── ConversationRepositoryImpl.ts
        │   │   ├── recommendation/
        │   │   │   └── SupportImpl.ts
        │   ├── cache/
        │   │   ├── indexedDB/
        │   │   │   ├── requestResponseIndexDBStorage.ts
        │   │   ├── localStorage/
        │   │   │   ├── requestResponseLocalStorage.ts
        │   │   ├── BotMessagePagerCache.ts
        │   │   ├── ConfigCache.ts
        │   │   ├── KnowledgeCache.ts
        │   │   ├── WindowCache.ts
        │   ├── context/
        │   │   ├── botMessage/
        │   │   │   ├── botCardInfo.ts
        │   │   ├── cookie/
        │   │   │   ├── cookie.ts
        │   │   │   ├── CookieContext.ts
        │   │   ├── dom/
        │   │   │   ├── DomContext.ts
        │   │   ├── env/
        │   │   │   ├── converter/
        │   │   │   │   ├── optionPresetConverter.ts
        │   │   │   ├── types/
        │   │   │   │   ├── Types.ts
        │   │   │   ├── ClientContext.ts
        │   │   │   ├── ConversationStatusContext.ts
        │   │   │   ├── CoreResourceContext.ts
        │   │   │   ├── EnvContext.ts
        │   │   │   ├── MessageContext.ts
        │   │   │   ├── PanguChatOptionContext.ts
        │   │   │   ├── PanguOptionContext.ts
        │   │   │   ├── ProxyWindowContext.ts
        │   │   │   ├── RequestStopContext.ts
        │   │   │   ├── StreamStopContext.ts
        │   │   ├── messages/
        │   │   │   ├── conversationCacheContext.ts
        │   │   ├── url/
        │   │   │   ├── helpers/
        │   │   │   │   ├── removeURLParam.ts
        │   │   │   ├── UrlContext.ts
        │   │   ├── WebContextService.ts
        │   │   ├── WebContextServiceImpl.ts
        │   ├── dependencies/
        │   │   ├── pubsub/
        │   │   │   └── index.ts
        │   ├── http/
        │   │   ├── cloudclient/
        │   │   │   ├── adapter/
        │   │   │   │   ├── RequestOptionAdapter.ts
        │   │   │   ├── constant/
        │   │   │   │   ├── constant.ts
        │   │   │   ├── converter/
        │   │   │   │   ├── ParamConverter.ts
        │   │   │   │   ├── ResponseUnifiedConverter.ts
        │   │   │   │   ├── UrlConverter.ts
        │   │   │   ├── locator/
        │   │   │   │   ├── ServiceLocator.ts
        │   │   │   ├── type/
        │   │   │   │   ├── CloudClientOption.ts
        │   │   │   │   ├── Request.ts
        │   │   │   │   ├── Response.ts
        │   │   │   ├── validator/
        │   │   │   │   ├── ParamValidator.ts
        │   │   │   ├── CloudClient.ts
        │   │   ├── common/
        │   │   │   ├── Header.ts
        │   │   ├── service/
        │   │   │   ├── cloudservice/
        │   │   │   │   ├── BusinessCard.ts
        │   │   │   │   ├── Conversation.ts
        │   │   │   │   ├── ConversationConfig.ts
        │   │   │   │   ├── ConversationHistory.ts
        │   │   │   │   ├── ConversationImage.ts
        │   │   │   │   ├── CreditManagement.ts
        │   │   │   │   ├── Feedback.ts
        │   │   │   │   ├── Knowledge.ts
        │   │   │   │   ├── ManualService.ts
        │   │   │   │   ├── PagerService.ts
        │   │   │   │   ├── Recommendation.ts
        │   │   │   │   ├── Refer.ts
        │   │   │   │   ├── SmartSuggestion.ts
        │   │   │   │   ├── User.ts
        │   │   │   │   ├── UserCollection.ts
        │   │   │   │   ├── UserDistributary.ts
        │   │   │   ├── CommonOperation.ts
        │   │   │   ├── Module.ts
        │   │   │   ├── Service.ts
        │   │   ├── validator/
        │   │   │   ├── RequestValidator.ts
        │   │   │   ├── SuccessCodes.ts
        │   │   ├── ErrorCode.ts
        │   │   ├── Http.ts
        │   │   ├── Jsonp.ts
        │   ├── shared/
        │   │   ├── context/
        │   │   │   ├── constant/
        │   │   │   │   ├── InnerPresetConfig.ts
        │   │   │   ├── ApplicationContext.ts
        │   │   │   ├── ConversationContext.ts
        │   │   │   ├── ManualServiceContext.ts
        │   │   │   ├── Types.ts
        │   │   │   ├── UserContext.ts
        │   │   ├── i18n/
        │   │   │   ├── common/
        │   │   │   │   ├── BIName/
        │   │   │   │   │   ├── en-us.ts
        │   │   │   │   │   ├── zh-cn.ts
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── conversation-history/
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── errormessage/
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── eventtracking/
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── feedback/
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── file-upload/
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── home/
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── manual/
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── message/
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── reference/
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── sendbox/
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── setting/
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── user/
        │   │   │   │   ├── en-us.ts
        │   │   │   │   ├── zh-cn.ts
        │   │   │   ├── en-us.ts
        │   │   │   ├── i18n.ts
        │   │   │   ├── types.ts
        │   │   │   ├── zh-cn.ts
        │   │   ├── instance/
        │   │   │   ├── InstanceGetter.ts
        │   │   ├── logger/
        │   │   │   ├── plugin/
        │   │   │   │   ├── console-logger/
        │   │   │   │   │   └── index.ts
        │   │   │   ├── shared/
        │   │   │   │   ├── Logger.ts
        │   │   │   ├── index.ts
        │   │   ├── ploc/
        │   │   │   ├── Observable.ts
        │   │   ├── pubsub/
        │   │   │   ├── event/
        │   │   │   │   ├── param/
        │   │   │   │   │   ├── MessageParam.ts
        │   │   │   │   ├── Event.ts
        │   │   │   ├── PubSub.ts
        │   │   ├── reporter/
        │   │   │   ├── PerformanceReporter.ts
        │   │   │   ├── UbaReporter.ts
        │   │   ├── type/
        │   │   │   ├── EventSourceWithType.ts
        │   │   ├── util/
        │   │   │   └── copy/
        │   │   │       ├── copyText.ts
        │   │   │   └── domOperation/
        │   │   │       ├── createElement.ts
        │   │   │       ├── getSiblingElement.ts
        │   │   │   └── layout/
        │   │   │       ├── feedbackIconLayout/
        │   │   │       │   └── spaceAnalyzer.ts
        │   │   │       │   └── statusUpdater.ts
        │   │   │       │   └── types.ts
        │   │   │       │   └── widthCalculator.ts
        │   │   │   └── md/
        │   │   │       ├── parseMd.ts
        │   │   │   └── object/
        │   │   │       ├── cloneDeep.ts
        │   │   │       ├── get.ts
        │   │   │       ├── isEmpty.ts
        │   │   │       ├── transformKeysToCamel.ts
        │   │   │   └── safe/
        │   │   │       ├── filterXssFn.ts
        │   │   │   └── skill/
        │   │   │       ├── skillParse.ts
        │   │   │   └── stream/
        │   │   │       ├── parse.ts
        │   │   │   └── string/
        │   │   │       ├── languages.ts
        │   │   │       ├── parse.ts
        │   │   │       ├── templateReplace.ts
        │   │   │   └── upload/
        │   │   │       ├── getFileInfo.ts
        │   │   │   └── url/
        │   │   │       ├── formatUrl.ts
        │   │   │       ├── getRemoteAssetUrlByTheme.ts
        │   │   │       ├── Urlparams.ts
        │   │   │   └── validator/
        │   │   │       ├── isLenientValidURL.ts
        │   │   │       ├── isStrictValidURL.ts
        │   │   │       ├── isUndefined.ts
        │   │   │   └── Util.ts
        │   ├── theme/
        │   │   ├── dark-theme.ts
        │   ├── type/
        │   │   └── PO/
        │   │       ├── responsePO.ts
        │   │   └── util/
        │   │       └── upload.type.ts
        ├── view/
        │   ├── asset/
        │   │   ├── icon/
        │   │   │   ├── arrow-down.svg
        │   │   │   ├── arrow-right.svg
        │   │   │   ├── arrow-up.svg
        │   │   │   ├── arrow.svg
        │   │   │   ├── auto-completion-icon.svg
        │   │   │   ├── check-mark.svg
        │   │   │   ├── close.svg
        │   │   │   ├── complain.svg
        │   │   │   ├── complete.svg
        │   │   │   ├── concept-explanation.svg
        │   │   │   ├── copy.svg
        │   │   │   ├── costs.svg
        │   │   │   ├── create.svg
        │   │   │   ├── deep-thinking.svg
        │   │   │   ├── delete.svg
        │   │   │   ├── dislike-active.svg
        │   │   │   ├── dislike.svg
        │   │   │   ├── edit.svg
        │   │   │   ├── fault-diagnosis.svg
        │   │   │   ├── float.svg
        │   │   │   ├── fullScreen.svg
        │   │   │   ├── history.svg
        │   │   │   ├── home-warn-up.svg
        │   │   │   ├── like-active.svg
        │   │   │   ├── like.svg
        │   │   │   ├── locate.svg
        │   │   │   ├── manual-suffix.svg
        │   │   │   ├── manual-tip.svg
        │   │   │   ├── microphone.svg
        │   │   │   ├── miniScreen.svg
        │   │   │   ├── more.svg
        │   │   │   ├── new-release.svg
        │   │   │   ├── phone.svg
        │   │   │   ├── pin.svg
        │   │   │   ├── purchase-Inquiry.svg
        │   │   │   ├── question-consultation.svg
        │   │   │   ├── questionnaire.svg
        │   │   │   ├── quickAccess.svg
        │   │   │   ├── quotation.svg
        │   │   │   ├── refresh.svg
        │   │   │   ├── resize-point.svg
        │   │   │   ├── resources.svg
        │   │   │   ├── search.svg
        │   │   │   ├── setting.svg
        │   │   │   ├── shutdown.svg
        │   │   │   ├── side-hide.svg
        │   │   │   ├── side.svg
        │   │   │   ├── starshining.svg
        │   │   │   ├── stop-bot-answering.svg
        │   │   │   ├── use-consultation.svg
        │   │   │   ├── user-message-collect.svg
        │   │   │   ├── user-message-collected.svg
        │   │   │   ├── user-message-copy.svg
        │   │   │   ├── zoomIn.svg
        │   │   │   ├── zoomOut.svg
        │   │   ├── image/
        │   │   │   └── conversation/
        │   │   │       ├── botMessage/
        │   │   │       │   ├── corner-tag-clicked.png
        │   │   │       │   ├── corner-tag-unclicked.png
        │   │   │       ├── history/
        │   │   │       │   └── check-mark.svg
        │   │   │       │   └── cross-mark.svg
        │   │   │       │   └── delete.svg
        │   │   │       │   └── edit.svg
        │   │   │       │   └── empty.svg
        │   │   │       │   └── locate.svg
        │   │   │       │   └── pin.svg
        │   │   │       │   └── pinned.svg
        │   │   │       │   └── search.svg
        │   │   │       │   └── warning.svg
        │   │   │   └── dark/
        │   │   │       ├── ai-send-button-hover.svg
        │   │   │       ├── ai-send-button.svg
        │   │   │       ├── complain.svg
        │   │   │       ├── concept-explanation.svg
        │   │   │       ├── helpDoc.svg
        │   │   │       ├── hot-questions-no-data.svg
        │   │   │       ├── hot-questions-star-icon.svg
        │   │   │       ├── info.svg
        │   │   │       ├── no-search-results.svg
        │   │   │       ├── panguLogo.svg
        │   │   │       ├── prompt-background-logo.svg
        │   │   │       ├── purchase-Inquiry.svg
        │   │   │       ├── quick-entrances.svg
        │   │   │       ├── selfHelp.svg
        │   │   │       ├── skill-intent.svg
        │   │   │       ├── use-consultation.svg
        │   │   │       ├── warning.svg
        │   │   │   └── deep-think/
        │   │   │       ├── arrow-down.svg
        │   │   │       ├── arrow-up.svg
        │   │   │       ├── complete.svg
        │   │   │       ├── down.svg
        │   │   │       ├── search.webp
        │   │   │       ├── up.svg
        │   │   │   └── default/
        │   │   │       ├── ai-send-button-hover.svg
        │   │   │       ├── ai-send-button.svg
        │   │   │       ├── complain.svg
        │   │   │       ├── concept-explanation.svg
        │   │   │       ├── helpDoc.svg
        │   │   │       ├── hot-questions-no-data.svg
        │   │   │       ├── hot-questions-star-icon.svg
        │   │   │       ├── info.svg
        │   │   │       ├── no-search-results.svg
        │   │   │       ├── panguLogo.svg
        │   │   │       ├── prompt-background-logo.svg
        │   │   │       ├── purchase-Inquiry.svg
        │   │   │       ├── quick-entrances.svg
        │   │   │       ├── selfHelp.svg
        │   │   │       ├── skill-intent.svg
        │   │   │       ├── use-consultation.svg
        │   │   │       ├── warning.svg
        │   │   │   └── empty/
        │   │   │       ├── no-data.svg
        │   │   │   └── feedback/
        │   │   │       ├── complain.svg
        │   │   │       ├── dislike-active.svg
        │   │   │       ├── dislike-old.svg
        │   │   │       ├── dislike.svg
        │   │   │       ├── like-active-webp.webp
        │   │   │       ├── like-active.svg
        │   │   │       ├── like.svg
        │   │   │       ├── refresh.svg
        │   │   │   └── header/
        │   │   │       ├── create.svg
        │   │   │       ├── float.svg
        │   │   │       ├── fullScreen.svg
        │   │   │       ├── history.svg
        │   │   │       ├── home-warn-tip.svg
        │   │   │       ├── info.svg
        │   │   │       ├── miniScreen.svg
        │   │   │       ├── more.svg
        │   │   │       ├── quickAccess.svg
        │   │   │       ├── side.svg
        │   │   │   └── manual/
        │   │   │       ├── close.svg
        │   │   │       ├── manual-service.svg
        │   │   │       ├── manual-suffix.svg
        │   │   │       ├── manual-tip.svg
        │   │   │   └── sendbox/
        │   │   │       ├── auto-completion-icon.svg
        │   │   │       ├── costs.svg
        │   │   │       ├── deep-think-active.svg
        │   │   │       ├── deep-think.svg
        │   │   │       ├── fault-diagnosis.svg
        │   │   │       ├── hot-questions-no-data.svg
        │   │   │       ├── hot-questions-star-icon.svg
        │   │   │       ├── microphone.png
        │   │   │       ├── question-consultation.svg
        │   │   │       ├── resources.svg
        │   │   │       ├── send-button-hover.svg
        │   │   │       ├── send-button.svg
        │   │   │       ├── starShining.svg
        │   │   │       ├── stop-bot-answering.svg
        │   │   │   └── shared/
        │   │   │       ├── loading-colorful-dot.webp
        │   │   │   └── ai-assistant.svg
        │   │   │   └── arrow-down.svg
        │   │   │   └── arrow-right.svg
        │   │   │   └── arrow-up.svg
        │   │   │   └── arrow.png
        │   │   │   └── close.svg
        │   │   │   └── copy.svg
        │   │   │   └── dialog-close-hover.svg
        │   │   │   └── dialog-close.svg
        │   │   │   └── full-screen.svg
        │   │   │   └── helpDoc.svg
        │   │   │   └── huawei-logo.png
        │   │   │   └── info.svg
        │   │   │   └── logo.png
        │   │   │   └── new-tag-dark.svg
        │   │   │   └── new-tag-default.svg
        │   │   │   └── PanguLogo.svg
        │   │   │   └── phone.svg
        │   │   │   └── quick-entrances.svg
        │   │   │   └── refresh.svg
        │   │   │   └── resize-point.svg
        │   │   │   └── selfHelp.svg
        │   │   │   └── show-all.svg
        │   │   │   └── warning.svg
        │   │   │   └── zoomClose.svg
        │   │   │   └── zoomCloseHover.svg
        │   ├── component/
        │   │   ├── avatar/
        │   │   │   ├── Avatar.vue
        │   │   ├── card/
        │   │   │   ├── adaptiveexperience/
        │   │   │   │   ├── ButtonGroupCard/
        │   │   │   │   │   ├── ButtonGroupCard.vue
        │   │   │   │   │   ├── ButtonGroupCardType.ts
        │   │   │   │   ├── composables/
        │   │   │   │   │   ├── types.ts
        │   │   │   │   │   ├── useTriggerEvents.ts
        │   │   │   │   ├── DownloadCard/
        │   │   │   │   │   ├── DownloadCard.vue
        │   │   │   │   ├── EntranceCard/
        │   │   │   │   │   ├── EntranceCard.vue
        │   │   │   │   │   ├── EntranceCardType.ts
        │   │   │   │   │   ├── EntranceContent.vue
        │   │   │   │   ├── EvaluationCard/
        │   │   │   │   │   ├── EvaluationCard.vue
        │   │   │   │   │   ├── useEvaluation.ts
        │   │   │   │   ├── FormCard/
        │   │   │   │   │   ├── Collapse.vue
        │   │   │   │   │   ├── CopyText.vue
        │   │   │   │   │   ├── FormCard.vue
        │   │   │   │   ├── GUICard/
        │   │   │   │   │   ├── GUICard.vue
        │   │   │   │   ├── ImageCard/
        │   │   │   │   │   ├── ImageCard.vue
        │   │   │   │   ├── markdown/
        │   │   │   │   │   ├── AdaptiveMDCard/
        │   │   │   │   │   │   ├── AdaptiveMarkdownCard.vue
        │   │   │   │   │   ├── MarkdownDslRender/
        │   │   │   │   │   │   └── customComponents/
        │   │   │   │   │   │       ├── shared/
        │   │   │   │   │   │       │   ├── ZoomInButton.vue
        │   │   │   │   │   │       ├── knowledgeIndexesConverter.ts
        │   │   │   │   │   │       ├── PanguBotCard.vue
        │   │   │   │   │   │       ├── PanguMdCodeBlock.vue
        │   │   │   │   │   │       ├── PanguMdCollapse.vue
        │   │   │   │   │   │       ├── PanguMdCornerTag.vue
        │   │   │   │   │   │       ├── PanguMdHeader.vue
        │   │   │   │   │   │       ├── PanguMdImage.vue
        │   │   │   │   │   │       ├── PanguMdLink.vue
        │   │   │   │   │   │       ├── PanguMdTable.vue
        │   │   │   │   │   │       ├── PanguStop.vue
        │   │   │   │   │   │       ├── useZoomCustomComponent.ts
        │   │   │   │   │   │       ├── ZoomContainer.vue
        │   │   │   │   │   │   └── renderer/
        │   │   │   │   │   │       └── core/
        │   │   │   │   │   │           ├── converter/
        │   │   │   │   │   │           │   ├── increment.ts
        │   │   │   │   │   │           │   ├── linearSuffix.ts
        │   │   │   │   │   │           │   ├── mdToDslConverter.ts
        │   │   │   │   │   │           ├── Constants.ts
        │   │   │   │   │   │           ├── Renderer.vue
        │   │   │   │   │   │       └── processDSL/
        │   │   │   │   │   │           ├── processCustomComponents/
        │   │   │   │   │   │           │   ├── cornerTag.ts
        │   │   │   │   │   │           │   ├── panguBotCard.ts
        │   │   │   │   │   │           │   ├── panguCollapse.ts
        │   │   │   │   │   │           │   ├── panguStop.ts
        │   │   │   │   │   │           ├── processCustomComponents.ts
        │   │   │   │   │   │           ├── processInlineComponents.ts
        │   │   │   │   │   │           ├── processList.ts
        │   │   │   │   │   │           ├── processTable.ts
        │   │   │   │   │   │       └── types.ts
        │   │   │   │   │   │       └── useDslMdRenderer.ts
        │   │   │   │   ├── operationCard/
        │   │   │   │   │   ├── LinkCard.vue
        │   │   │   │   │   ├── OperationCard.vue
        │   │   │   │   │   ├── ProductToolCard.vue
        │   │   │   │   │   ├── TextCard.vue
        │   │   │   │   ├── SelectCard/
        │   │   │   │   │   ├── SelectCard.vue
        │   │   │   │   ├── AdaptiveExperienceCard.vue
        │   │   │   │   ├── useAdaptiveexperienceCard.ts
        │   │   │   ├── bot/
        │   │   │   │   ├── type/
        │   │   │   │   │   ├── PanguConfig.ts
        │   │   │   │   ├── BotCard.vue
        │   │   │   ├── remote/
        │   │   │   │   ├── RemoteCard.vue
        │   │   │   │   ├── RemoteData.ts
        │   │   │   │   ├── useRemoteCard.ts
        │   │   │   ├── type/
        │   │   │   │   └── commonCard.ts
        │   │   ├── highlight/
        │   │   │   ├── highlightWords/
        │   │   │   │   └── highlightWords.ts
        │   │   ├── message/
        │   │   │   ├── bot/
        │   │   │   │   ├── bot-collapse/
        │   │   │   │   │   ├── useBotContentCollapse.ts
        │   │   │   │   ├── bot-think/
        │   │   │   │   │   ├── deep-think/
        │   │   │   │   │   │   ├── DeepThink.vue
        │   │   │   │   │   │   ├── DeepThinkAnalyze.vue
        │   │   │   │   │   │   ├── DeepThinkSearch.vue
        │   │   │   │   │   │   ├── DeepThinkSearchComplete.vue
        │   │   │   │   │   │   ├── DeepThinkSubEventTitle.vue
        │   │   │   │   │   │   ├── useDeepThink.ts
        │   │   │   │   │   ├── task-think/
        │   │   │   │   │   │   ├── TaskThink.vue
        │   │   │   │   │   │   ├── TaskThinkAnalyze.vue
        │   │   │   │   │   │   ├── TaskThinkEventContent.vue
        │   │   │   │   │   ├── BotThink.vue
        │   │   │   │   ├── botError/
        │   │   │   │   │   ├── BotErrorMessage.vue
        │   │   │   │   ├── built-in-bot-message/
        │   │   │   │   │   ├── scenario/
        │   │   │   │   │   │   ├── ScenarioSuggestion.vue
        │   │   │   │   │   │   ├── useScenarioSuggestion.ts
        │   │   │   │   │   │   ├── useSuggestion.ts
        │   │   │   │   │   ├── BuiltInBotComponent.vue
        │   │   │   │   ├── credit/
        │   │   │   │   │   ├── RemoveCreditLimit.vue
        │   │   │   │   │   ├── useCreditManagement.ts
        │   │   │   │   ├── streamMessage/
        │   │   │   │   │   ├── render-message.less
        │   │   │   │   │   ├── StreamMessage.vue
        │   │   │   │   ├── BotAnswerProcess.vue
        │   │   │   │   ├── BotMessage.vue
        │   │   │   │   ├── ManualSuffixMessage.vue
        │   │   │   │   ├── RiskAlarm.vue
        │   │   │   ├── printAnimation/
        │   │   │   │   ├── printAnimation.ts
        │   │   │   ├── shared/
        │   │   │   │   ├── style.less
        │   │   │   ├── user/
        │   │   │   │   └── tool/
        │   │   │   │       ├── mobile/
        │   │   │   │       │   ├── useMenuMobile.ts
        │   │   │   │       │   ├── UserMessageMenuMobile.vue
        │   │   │   │       ├── pc/
        │   │   │   │       │   ├── BallAnimation.vue
        │   │   │   │       │   ├── useQuestionEdit.ts
        │   │   │   │       │   ├── UserMessageMenuPC.vue
        │   │   │   │       ├── UserMessageMenu.vue
        │   │   │   │   └── UserMessage.vue
        │   │   ├── messagefeedback/
        │   │   │   ├── component/
        │   │   │   │   ├── Pager.vue
        │   │   │   ├── content/
        │   │   │   │   ├── complain/
        │   │   │   │   │   ├── FeedbackComplain.vue
        │   │   │   │   ├── composables/
        │   │   │   │   │   ├── useFoldStatusCalculator.ts
        │   │   │   │   │   ├── useFoldWidthCalculator.ts
        │   │   │   │   ├── copy/
        │   │   │   │   │   ├── FeedbackCopy.vue
        │   │   │   │   ├── dislike/
        │   │   │   │   │   ├── FeedbackDialog.vue
        │   │   │   │   │   ├── FeedbackDislike.vue
        │   │   │   │   ├── like/
        │   │   │   │   │   ├── feedbackLike.ts
        │   │   │   │   │   ├── FeedbackLike.vue
        │   │   │   │   ├── refresh/
        │   │   │   │   │   ├── FeedbackRefresh.vue
        │   │   │   │   │   ├── useRefreshBotMessage.ts
        │   │   │   │   ├── shared/
        │   │   │   │   │   ├── feedbackIcon.less
        │   │   │   │   ├── ticketManualService/
        │   │   │   │   │   ├── FeedbackTicketManualService.vue
        │   │   │   │   ├── Feedback.vue
        │   │   │   │   ├── types.ts
        │   │   │   │   ├── useMessageFeedback.ts
        │   │   │   │   ├── useMessagePager.ts
        │   │   │   ├── MessageFeedback.vue
        │   │   │   ├── SuggestQuestion.vue
        │   │   ├── panguComponents.ts
        │   ├── hook/
        │   │   ├── customHook/
        │   │   │   └── onConversationStarted.ts
        │   ├── outbound/
        │   │   ├── auth/
        │   │   │   ├── isLogin.ts
        │   │   │   ├── isPanguAvailable.ts
        │   │   │   ├── isPanguBrand.ts
        │   │   ├── config/
        │   │   │   ├── panguAsk.ts
        │   │   │   ├── panguConfig.ts
        │   │   │   ├── panguRequest.ts
        │   │   │   ├── panguStopMsg.ts
        │   │   │   ├── panguTheme.ts
        │   │   │   ├── panguToggleHistoryPanel.ts
        │   │   ├── consoleadapter/
        │   │   │   ├── getConsoleOption.ts
        │   │   │   ├── setDraggableZone.ts
        │   │   │   ├── useConsoleAdapter.ts
        │   │   ├── zoneAdapter/
        │   │   │   ├── ignoreError.ts
        │   │   ├── displayChat.ts
        │   │   ├── LoadPangu.ts
        │   │   ├── loadShadowDom.ts
        │   ├── page/
        │   │   ├── content/
        │   │   │   ├── component/
        │   │   │   │   ├── agreement/
        │   │   │   │   │   ├── composable/
        │   │   │   │   │   │   ├── useAgreement.ts
        │   │   │   │   │   ├── Agreement.vue
        │   │   │   │   ├── common/
        │   │   │   │   │   ├── zoomImageViewer.vue
        │   │   │   │   ├── conversation-helpCenter/
        │   │   │   │   │   ├── ConversationHelpCenter.vue
        │   │   │   │   ├── conversation-history/
        │   │   │   │   │   ├── history/
        │   │   │   │   │   │   ├── ConversationHistoryList.vue
        │   │   │   │   │   │   ├── EditTitleInput.vue
        │   │   │   │   │   │   ├── HistoryDeleteTip.vue
        │   │   │   │   │   │   ├── HistoryItem.vue
        │   │   │   │   │   │   ├── MobileHistoryItem.vue
        │   │   │   │   │   ├── search/
        │   │   │   │   │   │   ├── SearchInput.vue
        │   │   │   │   │   │   ├── SearchResult.vue
        │   │   │   │   │   │   ├── useHistorySearch.ts
        │   │   │   │   │   ├── type/
        │   │   │   │   │   │   ├── type.ts
        │   │   │   │   │   ├── ConversationHistory.vue
        │   │   │   │   ├── deepthink/
        │   │   │   │   │   ├── DeepthinkController.vue
        │   │   │   │   ├── leaveToolTip/
        │   │   │   │   │   ├── composable/
        │   │   │   │   │   │   ├── useLeaveToolTip.ts
        │   │   │   │   │   ├── LeaveToolTip.vue
        │   │   │   │   ├── manual/
        │   │   │   │   │   ├── CloseManualService.vue
        │   │   │   │   │   ├── SplitLine.vue
        │   │   │   │   ├── re-edit/
        │   │   │   │   │   ├── ReEdit.vue
        │   │   │   │   ├── reference/
        │   │   │   │   │   ├── composable/
        │   │   │   │   │   │   ├── useReference.ts
        │   │   │   │   │   ├── content/
        │   │   │   │   │   │   ├── ReferenceContent.vue
        │   │   │   │   │   ├── Reference.vue
        │   │   │   │   ├── sendbox/
        │   │   │   │   │   ├── components/
        │   │   │   │   │   │   ├── files-upload/
        │   │   │   │   │   │   │   ├── composable/
        │   │   │   │   │   │   │   │   ├── useBase64Converter.ts
        │   │   │   │   │   │   │   │   ├── useImageCheck.ts
        │   │   │   │   │   │   │   │   ├── useImageItem.ts
        │   │   │   │   │   │   │   │   ├── useImagesUpload.ts
        │   │   │   │   │   │   │   ├── FilesUpload.vue
        │   │   │   │   │   │   │   ├── FileView.vue
        │   │   │   │   │   │   ├── hot-popover/
        │   │   │   │   │   │   │   ├── body/
        │   │   │   │   │   │   │   │   ├── user-collection/
        │   │   │   │   │   │   │   │   │   ├── UserCollectionToolbarMobile.vue
        │   │   │   │   │   │   │   │   │   ├── UserCollectionToolbarPC.vue
        │   │   │   │   │   │   │   │   │   ├── useUserCollection.ts
        │   │   │   │   │   │   │   │   ├── PopoverBody.vue
        │   │   │   │   │   │   │   │   ├── PopoverContent.vue
        │   │   │   │   │   │   │   ├── header/
        │   │   │   │   │   │   │   │   ├── PopoverHeader.vue
        │   │   │   │   │   │   │   │   ├── useHotQuestionTab.ts
        │   │   │   │   │   │   │   │   ├── useMyCollectionTab.ts
        │   │   │   │   │   │   │   │   ├── usePopoverTab.ts
        │   │   │   │   │   │   │   ├── type/
        │   │   │   │   │   │   │   │   ├── type.ts
        │   │   │   │   │   │   │   ├── useHotPopover.ts
        │   │   │   │   │   │   ├── image-viewer/
        │   │   │   │   │   │   │   ├── ImageViewer.vue
        │   │   │   │   │   │   │   ├── usaImageViewerStatus.ts
        │   │   │   │   │   │   │   ├── useImageViewer.ts
        │   │   │   │   │   │   ├── skill-intent/
        │   │   │   │   │   │   │   ├── SkillIntent.vue
        │   │   │   │   │   │   │   ├── SkillIntentItem.vue
        │   │   │   │   │   │   ├── AutoCompletion.vue
        │   │   │   │   │   │   ├── HotQuestions.vue
        │   │   │   │   │   │   ├── RecommendPromptWords.vue
        │   │   │   │   │   │   ├── RecommendTools.vue
        │   │   │   │   │   │   ├── SendBoxDeepThinkButton.vue
        │   │   │   │   │   │   ├── SendBoxInput.vue
        │   │   │   │   │   │   ├── SendBoxInputOld.vue
        │   │   │   │   │   │   ├── SendBoxInputTools.vue
        │   │   │   │   │   │   ├── SvgIcon.ts
        │   │   │   │   │   │   ├── TinyRobotSendBoxInput.vue
        │   │   │   │   │   ├── composable/
        │   │   │   │   │   │   ├── MockAutoCompletions.ts
        │   │   │   │   │   │   ├── MockHotQuestions.ts
        │   │   │   │   │   │   ├── useAutoCompletions.ts
        │   │   │   │   │   │   ├── useHotQuestions.ts
        │   │   │   │   │   │   ├── useRecommendPromptWords.ts
        │   │   │   │   │   │   ├── useSendBoxStyle.ts
        │   │   │   │   │   ├── type/
        │   │   │   │   │   │   ├── type.ts
        │   │   │   │   │   ├── SendBox.vue
        │   │   │   │   ├── setting/
        │   │   │   │   │   ├── PanguSetting.vue
        │   │   │   │   │   ├── usePanguSetting.ts
        │   │   │   │   ├── sideBar/
        │   │   │   │   │   ├── type/
        │   │   │   │   │   │   ├── type.ts
        │   │   │   │   │   ├── OperationalLayer.vue
        │   │   │   │   │   ├── Sidebar.vue
        │   │   │   │   ├── skeleton/
        │   │   │   │   │   ├── Skeleton.vue
        │   │   │   │   ├── suggested-prompt/
        │   │   │   │   │   ├── PromptContent.vue
        │   │   │   │   │   ├── Tag.vue
        │   │   │   │   ├── LogoContent.vue
        │   │   │   │   ├── MessageContent.vue
        │   │   │   │   ├── ToBottom.vue
        │   │   │   ├── composable/
        │   │   │   │   ├── useRecommendTools.ts
        │   │   │   │   ├── useReEdit.ts
        │   │   │   │   ├── useSendBoxDisabled.ts
        │   │   │   │   ├── useSendBoxInput.ts
        │   │   │   │   ├── useSendBoxStatus.ts
        │   │   │   │   ├── useSetOpenUrl.ts
        │   │   │   │   ├── useSkillIntent.ts
        │   │   │   │   ├── useSkillIntentStatus.ts
        │   │   │   ├── Content.vue
        │   │   ├── data-empty/
        │   │   │   ├── DataEmpty.vue
        │   │   ├── footer/
        │   │   │   ├── Footer.vue
        │   │   │   ├── useFooter.ts
        │   │   ├── header/
        │   │   │   ├── Header.vue
        │   │   │   ├── HeaderOpenButtonTip.vue
        │   │   │   ├── serviceTicket.vue
        │   │   │   ├── useHeader.ts
        │   │   │   ├── usePanguDisplay.ts
        │   │   │   ├── useQuickAccess.ts
        │   │   ├── home-loading-mask/
        │   │   │   ├── HomeLoadingMask.vue
        │   │   │   ├── useHomeLoadingMask.ts
        │   │   ├── layout/
        │   │   │   ├── composable/
        │   │   │   │   ├── usePanguLayout.ts
        │   │   │   ├── PanguLayout.vue
        │   │   ├── panel/
        │   │   │   ├── buildPanel.ts
        │   │   │   ├── Panel.vue
        │   │   │   ├── usePanel.ts
        │   │   ├── recommendation/
        │   │   │   └── Recommendation.vue
        │   │   │   └── RecommendationModal.vue
        │   │   │   └── SupportItem.vue
        │   │   │   └── useSupport.ts
        │   ├── shared/
        │   │   ├── app/
        │   │   │   ├── init/
        │   │   │   │   ├── useInitAction.ts
        │   │   │   │   ├── useInitActionCompute.ts
        │   │   │   ├── integratorAdapter/
        │   │   │   │   ├── useScroll.ts
        │   │   │   ├── useApp.ts
        │   │   │   ├── useDraggable.ts
        │   │   │   ├── usePolling.ts
        │   │   │   ├── useWindowPanguEvents.ts
        │   │   ├── component/
        │   │   │   ├── messageTip/
        │   │   │   │   ├── MessageTip.ts
        │   │   │   │   ├── MessageTip.vue
        │   │   │   │   ├── useMessageTip.ts
        │   │   │   ├── subscribers/
        │   │   │   │   ├── components/
        │   │   │   │   │   ├── Index.ts
        │   │   │   │   ├── SubscriberComponentService.ts
        │   │   │   │   ├── Subscribers.ts
        │   │   │   ├── svgIcon/
        │   │   │   │   ├── svgIcon.vue
        │   │   │   ├── themeImage/
        │   │   │   │   ├── themeImage.vue
        │   │   │   ├── toolTip/
        │   │   │   │   └── ToolTip.vue
        │   │   │   │   └── types.ts
        │   │   ├── composable/
        │   │   │   ├── common/
        │   │   │   │   ├── useClickOutsideContainer.ts
        │   │   │   │   ├── useDispatchPanguCommonEvents.ts
        │   │   │   │   ├── useDispatchPanguEvents.ts
        │   │   │   │   ├── useGetPanguLogo.ts
        │   │   │   │   ├── useHelpCenter.ts
        │   │   │   │   ├── useKeepWebsiteSession.ts
        │   │   │   │   ├── useOpenUrl.ts
        │   │   │   │   ├── useScrollBarVisibility.ts
        │   │   │   │   ├── useSubscribePanguEvents.ts
        │   │   │   │   ├── useTooltip.ts
        │   │   │   │   ├── useUserDistributary.ts
        │   │   │   ├── conversation/
        │   │   │   │   ├── deepthink/
        │   │   │   │   │   ├── useDeepThinkEvent.ts
        │   │   │   │   ├── history/
        │   │   │   │   │   ├── useConversationHistory.ts
        │   │   │   │   │   ├── useHistoricalConversations.ts
        │   │   │   │   ├── manual/
        │   │   │   │   │   ├── useManualBusinessCard.ts
        │   │   │   │   │   ├── useManualListener.ts
        │   │   │   │   │   ├── useManualPrompt.ts
        │   │   │   │   │   ├── useManualService.ts
        │   │   │   │   │   ├── useManualSuggestMessage.ts
        │   │   │   │   ├── sideBar/
        │   │   │   │   │   ├── useSideBar.ts
        │   │   │   │   ├── utils/
        │   │   │   │   │   ├── businesscard/
        │   │   │   │   │   │   ├── updateCardLayout.ts
        │   │   │   │   │   │   ├── useBusinessCard.ts
        │   │   │   │   │   ├── markdown/
        │   │   │   │   │   │   ├── marked/
        │   │   │   │   │   │   │   └── codeblockValidation.ts
        │   │   │   │   │   ├── galaxyUtils.ts
        │   │   │   │   │   ├── getTextNodes.ts
        │   │   │   │   │   ├── utils.ts
        │   │   │   │   ├── onCustomMessageEvent.ts
        │   │   │   │   ├── useConversation.ts
        │   │   │   │   ├── useConversationMessage.ts
        │   │   │   │   ├── useMessageEvent.ts
        │   │   │   │   ├── useOpenConversation.ts
        │   │   │   │   ├── useScrollEvent.ts
        │   │   │   ├── integrator/
        │   │   │   │   ├── PanguChatOption.ts
        │   │   │   │   ├── usePanguChatOption.ts
        │   │   │   │   ├── useQuery.ts
        │   │   │   ├── mode/
        │   │   │   │   ├── useMode.ts
        │   │   │   ├── reporter/
        │   │   │   │   ├── useReportEvent.ts
        │   │   │   │   ├── useUbaReporter.ts
        │   │   │   ├── sendBox/
        │   │   │   │   ├── useCursorPositionChange.ts
        │   │   │   │   ├── useTabKeyboardEvent.ts
        │   │   │   │   ├── useUpDownKeyboardChange.ts
        │   │   │   ├── user/
        │   │   │   │   ├── useLogin.ts
        │   │   │   │   ├── useResetLogin.ts
        │   │   │   ├── UseCaseProvider.ts
        │   │   ├── style/
        │   │   │   └── highlight/
        │   │   │       ├── highlight.less
        │   │   │   └── token/
        │   │   │       ├── common.less
        │   │   │       ├── dark.less
        │   │   │       ├── default.less
        │   │   │   └── consoleFramework.less
        │   │   │   └── global.less
        │   │   │   └── injection.less
        │   │   │   └── integrator.less
        │   ├── App.ts
        │   ├── App.vue
        │   ├── env.d.ts
        │   ├── Home.vue
        │   ├── prototypeStorage.ts
        ├── auto-imports.d.ts
    └── test/
        ├── arch/
        │   ├── Arch.spec.ts
        ├── assets/
        │   ├── long-icon-shark.jpg
        ├── mocks/
        │   ├── mock/
        │   │   ├── window/
        │   │   │   └── EventSource.js
        │   │   │   └── EventSourceForTest.js
        │   ├── stub/
        │   │   └── message/
        │   │       └── adaptiveCard/
        │   │           ├── ButtonGroupCard.json
        │   │           ├── EntranceCard.json
        │   │           ├── FormCard.json
        │   │           ├── GUICard.json
        │   │           ├── operationCard.json
        │   │           ├── PanguMarkdown.json
        │   │           ├── SelectCard.json
        │   │       └── history/
        │   │           ├── HistoryBotMessageStub.ts
        │   │           ├── HistoryDeepThinkMessageStub.ts
        │   │           ├── HistoryManualMessageStub.ts
        │   │           ├── HistoryUserMessageStub.ts
        │   │       └── markdown/
        │   │           ├── MdBasicTestStub.ts
        │   │           ├── MdCustomComponentTestStub.ts
        │   │           ├── MdRealDataTestStub.ts
        │   │       └── AdaptiveCardMessage.ts
        │   │       └── AdaptiveCardSchema.ts
        │   │       └── CardMessage.ts
        │   │       └── cce-pod.json
        │   │       └── cce.json
        │   │       └── ComponentSchema.ts
        │   │       └── console-card.json
        │   │       └── knowledgeJson.json
        │   │       └── ManualBotMessage.ts
        │   │       └── pangu-entrance.json
        │   │       └── res.json
        │   │       └── TextMessage.ts
        ├── unit/
        │   ├── application/
        │   │   ├── usecase/
        │   │   │   └── ContextUseCase.spec.ts
        │   │   │   └── ConversationUseCase.spec.ts
        │   ├── infrastructure/
        │   │   ├── adaptivecard/
        │   │   │   ├── parseMd.spec.ts
        │   │   ├── chatOptionPreset/
        │   │   │   ├── InnerPreset.spec.ts
        │   │   ├── cloudclient/
        │   │   │   ├── CloudClient.spec.ts
        │   │   │   ├── RequestValidator.spec.ts
        │   │   ├── history/
        │   │   │   ├── spec/
        │   │   │   │   ├── HistoryConvertBotMessage.spec.ts
        │   │   │   │   ├── HistoryConvertDeepThinkMessage.spec.ts
        │   │   │   │   ├── HistoryConvertManualMessage.spec.ts
        │   │   │   │   ├── HistoryConvertUserMessage.spec.ts
        │   │   │   ├── utls/
        │   │   │   │   └── HistoryConvertUtils.spec.ts
        │   │   ├── http/
        │   │   │   ├── cloudclient/
        │   │   │   │   └── CloudClient.spec.ts
        │   │   │   │   └── RequestOptionAdapter.spec.ts
        │   │   ├── markdown/
        │   │   │   ├── converter/
        │   │   │   │   ├── collapsePositionConverter.spec.ts
        │   │   │   ├── DSL/
        │   │   │   │   ├── basicTest/
        │   │   │   │   │   ├── dsl_base_cases.spec.ts
        │   │   │   │   │   ├── dsl_codeblock_cases.spec.ts
        │   │   │   │   │   ├── dsl_link_cases.spec.ts
        │   │   │   │   │   ├── dsl_list_cases.spec.ts
        │   │   │   │   │   ├── dsl_table_cases.spec.ts
        │   │   │   │   ├── cutsomComponentTest/
        │   │   │   │   │   └── dsl_collapse_cases.spec.ts
        │   │   │   │   │   └── dsl_collapse_nested.spec.ts
        │   │   │   │   │   └── dsl_corner_tag_cases.spec.ts
        │   │   │   │   │   └── dsl_corner_tag_converter.spec.ts
        │   │   │   ├── marked/
        │   │   │   │   └── codeblock.spec.ts
        │   │   ├── openUrl/
        │   │   │   ├── defaultOpenUrl.spec.ts
        │   │   ├── shared/
        │   │   │   └── util/
        │   │   │       ├── layout/
        │   │   │       │   └── spaceAnalyzer.spec.ts
        │   │   │       │   └── types.spec.ts
        │   │   │       │   └── widthCalculator.spec.ts
        │   │   │   └── utils/
        │   │   │       └── languages/
        │   │   │           ├── isChinese.spec.ts
        │   │   │       └── object/
        │   │   │           ├── transformKeysToCamel.spec.ts
        │   │   │       └── validator/
        │   │   │           ├── isLenientValidateURL.spec.ts
        │   │   │           ├── isStrictValidateURL.spec.ts
        │   │   │       └── ConvertUtils.spec.ts
        │   ├── view/
        │   │   └── component/
        │   │       └── card/
        │   │           ├── adaptiveexperience/
        │   │           │   └── composables/
        │   │           │       └── useTriggerEvents.spec.ts
        │   │       └── messagefeedback/
        │   │           └── content/
        │   │               └── composables/
        │   │                   └── useFoldStatusCalculator.spec.ts
        ├── setupTestFramework.js
    └── .env
    └── .env.client
    └── .env.client-prod
    └── .env.loader
    └── .env.loader-prod
    └── .eslintrc.cjs
    └── .gitattributes
    └── .prettierrc.cjs
    └── .roomodes
    └── babel.config.json
    └── cui.config.js
    └── index_independency.html
    └── index.html
    └── jest.config.json
    └── jest.setup.js
    └── package-lock.json
    └── package.json
    └── pangu.html
    └── tsconfig.json
    └── vite.config.ts
```

