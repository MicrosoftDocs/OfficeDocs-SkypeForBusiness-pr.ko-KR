---
title: Microsoft 팀에서 실시간 이벤트 설정 구성
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 조직에 보유 된 팀의 live 이벤트에 대 한 설정을 관리 하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: afbcd90db9a17f509076bae1271bf541dfb93fd4
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030894"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Microsoft 팀에서 실시간 이벤트 설정 구성

팀 라이브 이벤트 설정을 사용 하 여 조직에 보유 된 라이브 이벤트에 대 한 설정을 구성할 수 있습니다. 지원 URL을 설정 하 고 타사 영상 배포 공급자를 구성할 수 있습니다. 이러한 설정은 조직에서 만든 모든 라이브 이벤트에 적용 됩니다.

Microsoft 팀 관리 센터에서 이러한 설정을 쉽게 관리할 수 있습니다. 왼쪽 탐색 창에서 **모임**  >  **라이브 이벤트 설정** 으로 이동 합니다.

![팀의 라이브 이벤트 설정 스크린샷](../media/teams-live-events-settings.png "Microsoft 팀 관리 센터에서 구성할 수 있는 팀 live 이벤트 설정 스크린샷")

## <a name="set-up-event-support-url"></a>이벤트 지원 URL 설정

이 URL은 live 이벤트 참석자에 게 표시 됩니다. 라이브 이벤트 중에 참석자에 게 고객 지원에 연락할 수 있는 방법을 제공 하는 조직의 지원 URL을 추가 합니다.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams 로고를 보여주는 아이콘](../media/teams-logo-30x30.png) Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 창에서 **모임**  >  **라이브 이벤트 설정** 으로 이동 합니다.
2. **지원 url** 에서 조직의 지원 url을 입력 합니다.

    ![관리 센터에서 라이브 이벤트에 대 한 URL 설정 지원](../media/teams-live-events-settings-supporturl.png "팀 라이브 이벤트에 대 한 지원 URL 설정 스크린샷")

### <a name="using-windows-powershell"></a>Windows PowerShell 사용

다음을 실행 합니다.

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
자세한 내용은 [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)을 참조 하세요.
## <a name="configure-a-third-party-video-distribution-provider"></a>타사 영상 배포 공급자 구성 

Microsoft 비디오 배달 파트너를 통해 SDN (소프트웨어 정의 네트워크) 솔루션 또는 eCDN (enterprise content delivery network) 솔루션을 구입한 경우 팀에서 실시간 이벤트에 대 한 공급자를 구성 합니다. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams 로고를 보여주는 아이콘](../media/teams-logo-30x30.png) Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 창에서 **모임**  >  **라이브 이벤트 설정** 으로 이동 합니다.
2. **타사 비디오 배포 공급자** 아래에서 다음을 수행 합니다. 

    ![관리 센터의 타사 영상 배포 공급자 설정](../media/teams-live-events-settings-distribution-provider.png "라이브 이벤트의 타사 비디오 배포 공급자 설정 스크린샷")

    - **타사 배포 공급자 사용** 타사 비디오 배포 공급자를 사용 하도록 설정 합니다.
    - **SDN 공급자 이름** 사용 중인 공급자를 선택 합니다.
    - **공급자 라이선스 키** 공급자 연락처에서 받은 라이선스 ID를 입력 합니다.
    - **SDN API 서식 파일 URL** 공급자 연락처에서 받은 API 서식 파일 URL을 입력 합니다.

### <a name="using-windows-powershell"></a>Windows PowerShell 사용
공급자 연락처에서 라이선스 ID 또는 API 토큰과 API 서식 파일을 가져온 후 사용 중인 공급자에 따라 다음 중 하나를 실행 합니다.

**벌** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Riverbed** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```

자세한 내용은 [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)을 참조 하세요.

> [!NOTE]
> 외부 앱 또는 장치를 사용 하 여 라이브 이벤트를 만들려는 경우 Microsoft Stream을 사용 하 여 [eCDN 공급자도 구성](https://docs.microsoft.com/stream/network-caching)해야 합니다. 

>[!Note]
> Microsoft Stream에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](../tmr-meeting-recording-change.md)로의 변경은 단계별로 접근합니다. 출시하면 이 환경에 대해 옵트인할 수 있고 11월에는 Stream을 계속 사용하려는 경우 옵트아웃해야 합니다. 2021년 초에는 모든 고객이 새 모임 녹음/녹화를 위해 비즈니스용 OneDrive와 SharePoint를 사용해야 합니다.

### <a name="related-topics"></a>관련 항목
- [Teams 라이브 이벤트란?](what-are-teams-live-events.md)
- [Teams 라이브 이벤트 계획](plan-for-teams-live-events.md)
- [Teams 라이브 이벤트 설정](set-up-for-teams-live-events.md)
