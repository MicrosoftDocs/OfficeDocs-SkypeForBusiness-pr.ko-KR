---
title: Microsoft Teams에서 라이브 이벤트 설정 구성
author: cichur
ms.author: v-cichur
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
- m365initiative-meetings-enabler
- enabler-strategic
description: 조직에서 개최된 Teams 라이브 이벤트에 대한 설정을 관리하는 방법에 대해 자세히 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bcb5edea00066c861b2288791f3ff3e0ee58431
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461018"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>Microsoft Teams에서 라이브 이벤트 설정 구성

Teams 라이브 이벤트 설정을 사용하여 조직에서 개최된 라이브 이벤트에 대한 설정을 구성합니다. 지원 URL을 설정하고 타사 비디오 배포 공급자를 구성할 수 있습니다. 이러한 설정은 조직에서 생성된 모든 라이브 이벤트에 적용됩니다.

Microsoft Teams 관리 센터에서 이러한 설정을 쉽게 관리할 수 있습니다. 왼쪽 탐색에서 모임   >  **라이브 이벤트 설정으로 이동합니다.**

![Teams 라이브 이벤트 설정의 스크린샷](../media/teams-live-events-settings.png "Microsoft Teams 관리 센터에서 구성할 수 있는 Teams 라이브 이벤트 설정 스크린샷")

## <a name="set-up-event-support-url"></a>이벤트 지원 URL 설정

이 URL은 라이브 이벤트 참석자에 표시됩니다. 조직에 대한 지원 URL을 추가하여 참석자들에게 라이브 이벤트 중에 지원에 문의할 수 있는 방법을 제공합니다.

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams 로고를 보여주는 아이콘](../media/teams-logo-30x30.png) Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색에서 모임   >  **라이브 이벤트 설정으로 이동합니다.**
2. 지원 **URL 아래에서** 조직의 지원 URL을 입력합니다.

    ![관리 센터의 라이브 이벤트에 대한 지원 URL 설정](../media/teams-live-events-settings-supporturl.png "Teams 라이브 이벤트에 대한 지원 URL 설정 스크린샷")

### <a name="using-windows-powershell"></a>Using Windows PowerShell

다음을 실행합니다.

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
자세한 내용은 [Set-CsTeamsMeetingBroadcastConfiguration 을 참조하세요.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)
## <a name="configure-a-third-party-video-distribution-provider"></a>타사 비디오 배포 공급자 구성 

Microsoft 비디오 배달 파트너를 통해 SDN(소프트웨어 정의 네트워크) 솔루션 또는 eCDN(엔터프라이즈 콘텐츠 배달 네트워크) 솔루션을 구입하고 설정한 경우 Teams에서 라이브 이벤트에 대한 공급자를 구성합니다. 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Microsoft Teams 로고를 보여주는 아이콘](../media/teams-logo-30x30.png) Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색에서 모임   >  **라이브 이벤트 설정으로 이동합니다.**
2. 타사 **비디오** 배포 공급자에서 다음을 완료합니다. 

    ![관리 센터의 타사 비디오 배포 공급자 설정](../media/teams-live-events-settings-distribution-provider.png "라이브 이벤트에 대한 타사 비디오 배포 공급자 설정의 스크린샷")

    - **타사 배포 공급자 사용** 타사 비디오 배포 공급자를 사용하도록 설정하려면 이 기능을 켜야 합니다.
    - **SDN 공급자 이름** 사용 중이신 공급자를 선택하세요.
    - **공급자 라이선스 키** 공급자 연락처에서 받은 라이선스 ID를 입력합니다.
    - **SDN API 템플릿 URL** 공급자 연락처에서 제공한 API 템플릿 URL을 입력합니다.

### <a name="using-windows-powershell"></a>Using Windows PowerShell
공급자 연락처에서 라이선스 ID 또는 API 토큰 및 API 템플릿을 받은 다음 사용 중 공급자에 따라 다음 중 하나를 실행합니다.

**Hive** 
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

자세한 내용은 [Set-CsTeamsMeetingBroadcastConfiguration 을 참조하세요.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)

> [!NOTE]
> 외부 앱 또는 디바이스를 사용하여 라이브 이벤트를 만들 계획인 경우 Microsoft Stream을 사용하여 [eCDN 공급자를 구성해야 합니다.](https://docs.microsoft.com/stream/network-caching) 

>[!Note]
> Microsoft Stream의 사용에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](../tmr-meeting-recording-change.md)로의 변경은 단계별 접근 방식을 사용합니다. 출시하면 이 환경에 대해 옵트인할 수 있고 11월에는 Stream을 계속 사용하려는 경우, 옵트아웃해야 합니다. 2021년 초에는 모든 고객이 모임 녹음/녹화를 위해 비즈니스용 OneDrive와 SharePoint를 사용해야 합니다.

### <a name="related-topics"></a>관련 항목
- [Teams 라이브 이벤트란?](what-are-teams-live-events.md)
- [Teams 라이브 이벤트 계획](plan-for-teams-live-events.md)
- [Teams 라이브 이벤트 설정](set-up-for-teams-live-events.md)
