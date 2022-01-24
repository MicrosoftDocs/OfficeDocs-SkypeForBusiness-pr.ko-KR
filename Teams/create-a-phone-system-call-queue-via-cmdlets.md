---
title: cmdlet을 통해 호출 큐 만들기
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: cmdlet을 통해 호출 큐를 구성하는 방법 자세히 알아보기
ms.openlocfilehash: a8f24f11cb19f448fc897043c7cb046a08c32341
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2022
ms.locfileid: "62181111"
---
# <a name="create-a-call-queue-via-cmdlets"></a>cmdlet을 통해 호출 큐 만들기

## <a name="assumptions"></a>가정
1)  컴퓨터에 PowerShell이 설치되어 있습니다.
- 컴퓨터를 설정하여 [](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) Windows PowerShell
- MSTeams 모듈 설치 ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- MSOnline 모듈이 설치되어 있습니다. ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  테넌트 관리 권한
3)  구입한 Microsoft Teams 전화
4)  에이전트, 메일 목록 및 Teams 채널이 이미 만들어졌습니다.

참고: Teams 채널 cmdlet은 PowerShell 모듈의 공용 미리 보기 Teams 일부입니다.  자세한 내용은 [PowerShell](teams-powershell-install.md) Teams 미리 보기 설치를 참조하고 [PowerShell 릴리스 Microsoft Teams 참조하세요.](teams-powershell-release-notes.md)

이미 MicrosoftTeams 모듈을 설치한 사용자는 최신 버전을 설치해야 ````Update-Module MicrosoftTeams```` 합니다.


## <a name="scenario"></a>시나리오

다음 세 개의 호출 큐가 만들어집니다.

판매 통화 큐 정보:
- 앞에서 자동 전화 교환: 예
- PSTN에서 직접 호출: 아니요
- 언어: 미국 영어
- 인사말: 없음
- 음악 보류 중: 오디오 파일 재생
- - 파일 이름: sales-hold-in-queue-music.wav
- 통화 응답: 사용자
- - Bill@contoso.com
- - Mary@contoso.com
- 회의 모드: 설정
- 라우팅 방법: 참석자
- 현재 상태 기반 라우팅: 끄기
- 통화 에이전트는 통화를 수신 거부할 수 있습니다. 예
- 전화 에이전트 경고 시간: 15
- 통화 오버플로 처리: 200
- - 리디렉션: Adele@contoso.com
- 통화 시간 제한 처리: 120초
- - 리디렉션: Adele@contoso.com

통화 큐 정보 지원:
- 앞에서 자동 전화 교환: 예
- PSTN에서 직접 호출: 아니요
-   언어: 영어 영국
-   인사말: 오디오 파일 재생
-   - Filename: support-greeting.wav
-   음악 보류 중: 오디오 파일 재생
-   - 파일 이름: support-hold-in-queue-music.wav
-   전화 응답: 지원 메일 목록
-   - Support@contoso.com
-   회의 모드: 설정
-   라우팅 방법: 가장 긴 유휴
-   현재 상태 기반 라우팅: N/A – 기본적으로 가장 긴 유휴으로 인하여 설정
-   통화 에이전트가 통화를 수신 거부할 수 있습니다. 아니요
-   전화 에이전트 경고 시간: 15
-   통화 오버플로 처리: 200
-   - 리디렉션: 공유 음성 파일 지원
- - -   오디오 파일 재생(support-shared-voicemail-greeting.wav)
- - -   전사 사용
-   통화 시간 제한 처리: 45분
-   - 리디렉션: 공유 음성 파일 지원
- - - TTS: "기다려주신 것을 죄송합니다. 이제 음성사서로 통화를 전송하고 있습니다."
- - - 전사 사용


시설 공동 호출 큐 정보:
- 앞에서 자동 전화 교환: 아니요
- PSTN에서 직접 호출: 아니요(내부 호출만 해당)
-   언어: 프랑스어 FR
-   인사말: 없음
-   음악 보류 중: 기본값
-   전화 응답: Team: 시설
-   전화 응답 채널: 지원 센터
-   - 채널 소유자: Fred@contoso.com
-   회의 모드: 설정
-   라우팅 방법: 라운드 로빈
-   현재 상태 기반 라우팅: On
-   통화 에이전트가 통화를 수신 거부할 수 있습니다. 아니요
-   전화 에이전트 경고 시간: 15
-   통화 오버플로 처리: 200
-   - 연결 끊기
-   통화 시간 제한 처리: 45분
-   - 연결 끊기


## <a name="login"></a>로그인
관리자 자격 증명을 입력하라는 Teams 메시지가 표시됩니다.
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="sales-queue"></a>판매 큐
### <a name="create-audio-files"></a>오디오 파일 만들기
"d: " 를 wav 파일이 컴퓨터에 저장되는 \\ 경로로 바 대체합니다.

````
$content = Get-Content “d:\sales-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
````

### <a name="get-users-id"></a>사용자 ID를 얻게 됩니다.
````
$userAdeleID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).ObjectID
$userSalesBillID = (Get-CsOnlineUser -Identity “sip:bill@contoso.com”).ObectID
$userSalesMaryID = (Get-CsOnlineUser -Identity “sip:mary@contoso.com”).ObjectID
````

### <a name="get-list-of-supported-languages"></a>지원되는 언어 목록 얻습니다.
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>통화 큐 만들기
````
New-CsCallQueue -Name “Sales” -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID “en-US”
````

### <a name="get-license-types"></a>라이선스 유형 얻기
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>리소스 계정 만들기 및 할당
참고: 전화 큐가 프런트 엔드로 끝나기 때문에 여기에 필요하지 않은 자동 전화 교환
- ApplicationID
- - 자동 전화 교환: ce933385-9390-45d1-9512-c8d228074e07
- - 통화 큐: 11cd3e2e-fccb-42ad-ad00-878b93575e07

참고: 아래에 표시된 라이선스 유형(PHONESYSTEM_VIRTUALUSER)은 위의 cmdlet에 Get-MsolAccountSku 있어야 합니다.

````
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Sales-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="support-queue"></a>지원 큐
### <a name="create-audio-files"></a>오디오 파일 만들기
"d: " 를 wav 파일이 컴퓨터에 저장되는 \\ 경로로 바 대체합니다.

````
$content = Get-Content “d:\support-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content “d:\support-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content “d:\support-shared-voicemail-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
````

### <a name="get-support-team-group-id"></a>지원 팀 그룹 ID를 구합니다.
````
$teamSupportID = (Get-Team -displayname "Support").GroupID
````

### <a name="get-list-of-supported-languages"></a>지원되는 언어 목록 얻습니다.
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>통화 큐 만들기
````
New-CsCallQueue -Name “Support” -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID “en-US”
````

### <a name="get-license-types"></a>라이선스 유형 얻기
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>리소스 계정 만들기 및 할당
참고: 전화 큐가 프런트 엔드로 설정되어 있는 경우 여기에 필요하지 않은 자동 전화 교환
- ApplicationID
- - 자동 전화 교환: ce933385-9390-45d1-9512-c8d228074e07
- - 통화 큐: 11cd3e2e-fccb-42ad-ad00-878b93575e07

참고: 아래에 표시된 라이선스 유형(PHONESYSTEM_VIRTUALUSER)은 위의 cmdlet에 Get-MsolAccountSku 있어야 합니다.

````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Support-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="facilities-collaborative-calling-queue"></a>시설 공동 호출 큐
### <a name="get-facilities-team-group-id"></a>시설 팀 그룹 ID를 얻습니다.
````
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
````

### <a name="get-facilities-help-desk-team-channel-id"></a>시설 지원 센터 팀 채널 ID를 얻습니다.
````
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
````

### <a name="get-facilities-help-desk-channel-ower-user-id"></a>시설 도움말 데스크 채널 ower 사용자 ID를 얻습니다.
````
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
````

### <a name="get-on-behalf-of-calling-resource-account-id"></a>리소스 계정 ID 호출을 대신하여 Get
````
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").ObjectID
````

### <a name="get-list-of-supported-languages"></a>지원되는 언어 목록 얻습니다.
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>통화 큐 만들기
````
New-CsCallQueue -Name “Facilities” -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID “fr-FR” -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
````

### <a name="get-license-types"></a>라이선스 유형 얻기
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>리소스 계정 만들기 및 할당
참고: 전화 큐가 프런트 엔드로 설정되어 있는 경우 여기에 필요하지 않은 자동 전화 교환
- ApplicationID
- - 자동 전화 교환: ce933385-9390-45d1-9512-c8d228074e07
- - 통화 큐: 11cd3e2e-fccb-42ad-ad00-878b93575e07

참고: 아래에 표시된 라이선스 유형(PHONESYSTEM_VIRTUALUSER)은 위의 cmdlet에 Get-MsolAccountSku 있어야 합니다.

````
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Facilities-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````
