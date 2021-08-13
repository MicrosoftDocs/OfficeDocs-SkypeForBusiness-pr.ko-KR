---
title: 2016년 8월에 Mac 클라이언트 환경 비즈니스용 Skype
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: 이 문서에서는 Mac 클라이언트의 클라이언트에서 사용할 수 있는 클라이언트 기본 비즈니스용 Skype 및 앱 외부에서 편집하는 방법에 대해 설명하고 있습니다.
ms.openlocfilehash: bf93b08686ed245fab38364cf9aff4fee0526a8bd496231865640aeb2c6e67f0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54325495"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a>2016년 8월에 Mac 클라이언트 환경 비즈니스용 Skype
 
이 문서에서는 Mac 클라이언트의 클라이언트에서 사용할 수 있는 클라이언트 기본 비즈니스용 Skype 및 앱 외부에서 편집하는 방법에 대해 설명하고 있습니다.
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a>비즈니스용 Skype 설정에 대한 정보

Mac 클라이언트에서 사용할 수 있는 특정 비즈니스용 Skype 및 동작은 클라이언트의 기본 설정에 따라 결정됩니다. Mac 비즈니스용 Skype 기본 설정에 대한 설정은 다음 경로에 있는 비즈니스용 Skype 클라이언트를 설치한 Mac에 있는 파일에서 찾을 수 있습니다. 
  
 **~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**
  
이러한 기본 설정을 설정하려면 클라이언트의 Mac에서 터미널 프롬프트로 이동하고 필요한 경우 다음 표에 설명된 기본 설정 키를 사용하여 com.microsoft.SkypeForBusiness 키 명령을 기본값으로 입력합니다.
  
**클라이언트 기본 설정 키**


| 키 | 타이핑 | 값 | 설명 |
|:-----|:-----|:-----|:-----|
|autoDetectAutoDicoveryURLs    |Bool    |0 = 수동 서버 구성  <br/> 1 = 자동 서버 검색(기본값)    |로그인 비즈니스용 Skype 전송 및 서버를 식별하는 방법을 지정합니다. 이 정책 설정을 사용하면 **internalAutoDiscoveryURL** 및 **externalAutoDiscoveryURL** 을 지정해야 합니다.   |
|internalAutoDiscoveryURL    |String    |전체 자동검사 URL    |내부 자동검사 URL    |
|externalAutoDiscoveryURL    |String    |전체 자동검사 URL    |외부 자동검사 URL    |
|httpProxyDomain    |String    ||HTTP 프록시 도메인    |
|httpProxyUserName    |String    ||HTTP 프록시 사용자 이름    |
|httpProxyPassword    |String    ||HTTP 프록시 암호    |
|trustedDomainList    |배열    ||HTTP 리디렉션을 위한 신뢰할 수 있는 도메인 목록입니다.    |
|autoAcceptTimeout    |숫자    |300(기본값)    |서버 쪽 대화 기록이 없는 사용자에 대한 자동 수락 시간 제한입니다.    |
|warnWhenUnknownLocationForE911    |Bool    |0 = 사용 안 하게  <br/> 1 = 사용    |알 수 없는 위치에서 긴급 번호로 전화를 걸 때 사용자에게 경고합니다.    |
|sipAddress    |String    ||로그인하는 데 사용되는 SIP 주소(전자 메일)비즈니스용 Skype.    |
|userName    |String    ||사용자 이름에 로그인하는 데 사용되는 UPN(UserName)비즈니스용 Skype.    |
|userNameInAdvancedOnly    |Bool    |0 = 기본 로그인 화면 및 고급 속성 대화 상자에 사용자 이름 필드 표시  <br/> 1 = 고급 속성 대화 상자에서만 사용자 이름 필드 표시(기본값)    |로그인하는 동안 사용자 이름 필드가 표시되는 위치를 지정합니다.    |
   
### <a name="usage-examples"></a>사용 예제

신뢰할 수 있는 도메인 목록에 단일 도메인(Contoso.com)을 추가하려면 다음과 같이 trustedDomainList 키를 사용하게 됩니다.
  
기본값은 com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"
  
신뢰할 수 있는 도메인 목록에 여러 도메인을 추가하려면 다음과 같이 trustedDomainList 키를 사용하게 됩니다.
  
기본값은 com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"
  
### <a name="sample-unedited-settings"></a>샘플의 선택되지 않은 설정

참조를 위해 다음은 기본 설정만 사용하는 샘플 설정 파일입니다. 
  
```console
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}
```
