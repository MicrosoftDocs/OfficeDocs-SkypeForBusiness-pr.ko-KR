---
title: 비즈니스용 Skype 서버에서 통화 속도 평가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: '요약: 비즈니스용 Skype 서버의 통화 속도 기능에 대해 알아봅니다.'
ms.openlocfilehash: 15f2bcbcf75690baaa350541f5f1da134fb32025
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902222"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 통화 속도 평가

**요약:** 비즈니스용 Skype 서버의 통화 속도 기능에 대해 알아봅니다.

Rate 사용자가 최종 사용자 로부터 피드백을 얻을 수 있는 방법을 제공 하는 Windows의 비즈니스용 Skype 2015 및 2016 클라이언트의 새로운 기능입니다.

통화 속도 창에는 음성 및 화상 통화에 대 한 "별" 등급 시스템과 미리 정의 된 토큰이 제공 됩니다. 또한 관리자는 사용자 지정 필드를 사용 하 여 피드백을 제공할 수 있습니다.

수집 된 속도 내 통화 데이터가 기존 모니터링 보고서에 현재 포함 되어 있지는 않지만 별도의 모니터링 보고서가 있습니다. Sql 쿼리를 실행 하 여 액세스할 수 있는 SQL 테이블에서 데이터를 수집 합니다.

## <a name="rate-my-call-prerequisites"></a>내 통화 필수 구성 요소 평가

비즈니스용 Skype 서버 배포의 사용자가 통화 속도에 액세스 하기 전에 다음 구성 요소 집합을 배포 및 구성 해야 합니다.

-  비즈니스용 Skype 서버 (버전 9160 이상)가 설치 되어 있어야 합니다.

- 사용자에 게 비즈니스용 Skype의 최신 버전을 설치 하 고 업데이트 하 여 비즈니스용 Skype UI를 사용 하도록 요청 합니다.

- 사용자는 비즈니스용 Skype 서버 프런트 엔드 풀에 속해 있어야 합니다.

- 비즈니스용 skype 서버 모니터링 데이터베이스를 배포 하 고 비즈니스용 Skype 서버 풀에 연결 해야 합니다.

- CQD (통화 품질 대시보드)를 배포 하는 것이 좋습니다.

## <a name="configure-rate-my-call"></a>통화 속도 구성

다음 설정을 사용 하 여 클라이언트 정책에서 내 통화 기능 속도를 기본적으로 사용 하도록 설정 합니다.

- 통화 표시 비율-10%

- 통화 속도 사용자 지정 사용자 의견 허용-사용 안 함

기본 기능을 사용 하도록 설정 하는 데 필요한 작업은 없지만 사용자 지정 피드백을 원하는 경우에는 별도로 사용 하도록 설정 해야 합니다. 다음 Windows PowerShell cmdlet은 사용자 지정 최종 사용자 의견을 사용 하도록 설정 하 고 간격을 10%에서 80%로 변경 하는 예제입니다.

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>통화 속도 데이터 액세스

사용자의 데이터는 모니터링 데이터베이스의 두 테이블에 수집 됩니다.

 **[QoeMetrics]. [dbo] [CallQualityFeedbackToken]** -이 테이블에는 최종 사용자의 토큰 폴링 결과가 포함 되어 있습니다.

 **[QoeMetrics]. [dbo] [CallQualityFeedbackTokenDef]** -이 테이블에는 토큰 정의가 포함 되어 있습니다.

토큰 정의는 다음과 같이 코딩 됩니다.

|||
|:-----|:-----|
|1   <br/> |DistortedSpeech  <br/> |
|2   <br/> | ElectronicFeedback <br/> |
|3   <br/> | BackgroundNoise <br/> |
|4   <br/> |MuffledSpeech  <br/> |
|5   <br/> |에코  <br/> |
| 21  <br/> | FrozenVideo <br/> |
|22  <br/> | PixelatedVideo <br/> |
|불가능  <br/> | BlurryImage <br/> |
|mb  <br/> | PoorColor <br/> |
|25@@  <br/> | DarkVideo <br/> |
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

 **[QoeMetrics]. [dbo] [CallQualityFeedback]** 이 테이블은 사용 하도록 설정 된 경우 "별모양" 투표 및 고객 피드백의 폴링 결과를 포함 합니다.

**Select \* from [Table.Name]** QUERY 또는 Microsoft SQL Server Management Studio를 사용 하 여 테이블의 데이터를 호출할 수 있습니다.

다음 SQL 쿼리를 사용할 수 있습니다.

 **오디오만**

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

최신 비즈니스용 Skype 클라이언트가 \> [QoeMetrics]에 표시 되지 않을 수 있는 새 문제 토큰 id (100)를 보고 합니다. [ dbo]입니다. [CallQualityFeedbackTokenDef] 테이블입니다. 최신 토큰 정의로 데이터베이스 테이블을 업데이트 하려면 아래의 SQL 명령을 Microsoft SQL Server Management Studio를 사용 하 여 모니터링 데이터베이스에서 실행할 수 있습니다. 이 명령은 [QoeMetrics]의 모든 항목을 대체 합니다. [dbo] [CallQualityFeedbackTokenDef] 테이블입니다.

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


