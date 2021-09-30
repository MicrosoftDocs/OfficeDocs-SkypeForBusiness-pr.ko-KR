---
title: 내 통화에 대한 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: '요약: 내 통화 요금제 기능에 대해 비즈니스용 Skype 서버.'
ms.openlocfilehash: 73a08b0acb32651c42de4ddda9fe12c7ae9f9655
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014142"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>내 통화에 대한 비즈니스용 Skype 서버

**요약:** 내 통화 요금제 기능에 대해 비즈니스용 Skype 서버.

비즈니스용 Skype 내 통화 평가는 기업이 최종 사용자로부터 피드백을 받을 수 있는 방법을 제공하는 Windows 2015 및 2016 클라이언트의 새로운 기능입니다.

내 통화 속도 창은 오디오 및 비디오 통화에 대해 "별" 등급 시스템 및 미리 정의한 토큰을 제공합니다. 또한 관리자는 사용자 정의 필드를 사용하여 피드백을 제공할 수 있습니다.

수집된 통화율 내 통화 데이터는 현재 기존 모니터링 보고서에 포함되지 않지만 별도의 모니터링 보고서가 있습니다. 데이터는 SQL 쿼리를 실행하여 액세스할 수 있는 SQL 수집됩니다.

## <a name="rate-my-call-prerequisites"></a>통화 선행 조율

내 통화 비즈니스용 Skype 서버 배포의 사용자가 속도 내 통화 기능에 액세스하려면 다음 구성 요소 집합을 배포하고 구성해야 합니다.

-  설치한 버전(비즈니스용 Skype 서버 버전 9160 이상)이 있어야 합니다.

- 사용자가 최신 버전의 비즈니스용 Skype 설치하고 업데이트하도록 요청하고 비즈니스용 Skype UI를 비즈니스용 Skype.

- 사용자는 프런트 엔드 풀에 비즈니스용 Skype 서버 있어야 합니다.

- 모니터링 데이터베이스를 배포하고 비즈니스용 Skype 서버 풀에 연결해야 비즈니스용 Skype 서버 있습니다.

- CQD(통화 품질 대시보드)를 배포하는 것이 좋습니다.

## <a name="configure-rate-my-call"></a>내 통화 속도 구성

클라이언트 정책에서 내 통화 속도 기능은 기본적으로 사용하도록 설정되어 있습니다. 설정은 다음과 같습니다.

- Rate My Call Display Percentage - 10%

- 내 통화 허용 사용자 지정 사용자 피드백 평가 - 사용 안 하도록 설정

기본 기능을 사용하도록 설정하는 데 필요한 작업은 없지만 사용자 지정 피드백을 원할 경우 별도로 사용하도록 설정해야 합니다. 다음 Windows PowerShell cmdlet은 사용자 지정 최종 사용자 피드백을 사용하도록 설정하고 간격을 10%에서 80%로 변경하는 예제입니다.

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>통화 속도 내 통화 데이터 액세스

사용자의 데이터는 모니터링 데이터베이스의 두 테이블에 수집됩니다.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** - 이 표에는 최종 사용자의 토큰 폴링 결과가 포함되어 있습니다.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** - 이 표에는 토큰 정의가 포함되어 있습니다.

토큰 정의는 다음과 같이 코딩됩니다.

|#|정의|
|:-----|:-----|
|1  <br/> |DistortedSpeech  <br/> |
|2  <br/> | ElectronicFeedback <br/> |
|3   <br/> | BackgroundNoise <br/> |
|4   <br/> |MuffledSpeech  <br/> |
|5  <br/> |에코  <br/> |
| 21  <br/> | FrozenVideo <br/> |
|22  <br/> | PixelatedVideo <br/> |
|23  <br/> | BlurryImage <br/> |
|24  <br/> | PoorColor <br/> |
|25  <br/> | DarkVideo <br/> |
|101  <br/> |Audio_SilentLocal  <br/> |
|102  <br/> |Audio_SilentRemote  <br/> |
|103  <br/> |Audio_Echo  <br/> |
|104  <br/> |Audio_BackgroundNoise  <br/> |
|105  <br/> |Audio_LowSound  <br/> |
|106  <br/> |Audio_Dropped  <br/> |
|107  <br/> |Audio_DistortedSpeech  <br/> |
|108  <br/> |Audio_Interrupted  <br/> |
|109  <br/> |Audio_Other  <br/> |
|201  <br/> |Video_NoLocalVideo  <br/> |
|202  <br/> |Video_NoRemoteVideo  <br/> |
|203  <br/> |Video_LowQuality  <br/> |
|204  <br/> |Video_FrozenVideo  <br/> |
|205  <br/> |Video_StoppedUnexpectedly  <br/> |
|206  <br/> |Video_DarkVideo  <br/> |
|207  <br/> |Video_NoAudioSync  <br/> |
|208  <br/> |Video_Other  <br/> |
|301  <br/> |Pstn_DialPad  <br/> |
|401  <br/> |SS_NoContentLocal  <br/> |
|402  <br/> |SS_NoContentRemote  <br/> |
|403  <br/> |SS_CantPresent  <br/> |
|404  <br/> |SS_LowQuality  <br/> |
|405  <br/> |SS_Freezing  <br/> |
|406  <br/> |SS_StoppedUnexpectedly  <br/> |
|407  <br/> |SS_LargeDelay  <br/> |
|408  <br/> |SS_Other  <br/> |
|501  <br/> |Reliabilty_Join  <br/> |
|502  <br/> |Reliabilty_Invite  <br/> |

 **[QoeMetrics]. [dbo]. [CallQualityFeedback]** 이 표에는 "Star" 투표의 폴링 결과 및 사용하도록 설정된 경우 고객 피드백이 포함되어 있습니다.

테이블의 데이터는 **\* [Table.Name]** 쿼리에서 선택하거나 쿼리를 사용하여 호출할 수 Microsoft SQL Server Management Studio.

다음 SQL 쿼리를 사용할 수 있습니다.

 **오디오**

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 **비디오**

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a>토큰 정의 업데이트

최신 비즈니스용 Skype 클라이언트는 [QoeMetrics]에 존재하지 않을 수 있는 새 문제 \> 토큰(100)을 보고합니다.[ dbo]. [CallQualityFeedbackTokenDef] 테이블 데이터베이스 테이블을 최신 토큰 정의로 업데이트하려면 SQL 데이터베이스에서 데이터베이스 테이블을 사용하여 실행할 수 Microsoft SQL Server Management Studio. 이 명령은 [QoeMetrics]의 모든 항목을 대체합니다. [dbo]. [CallQualityFeedbackTokenDef] 테이블

```SQL
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


