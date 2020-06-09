---
title: 새 팀 관리 센터로 팀 전환
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: Microsoft 365 관리 센터의 팀에서 새 팀 관리 센터로 전환 하는 동안 팀의 테 넌 트 전체 및 사용자 설정을 관리 하는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- ms.teamsadmincenter.dashboard.helparticle.manageteamsnewadmincenter
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
- Skype for Business Online
ms.openlocfilehash: f30db1425c61e8cb5f916345c0b751bc81c90a0f
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637427"
---
<a name="manage-teams-during-the-transition-to-the-new-microsoft-teams-admin-center"></a>새 Microsoft Teams 관리 센터로 전환하는 동안 팀 관리
======================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

## <a name="what-is-the-new-microsoft-teams-admin-center"></a>새로운 Microsoft 팀 관리 센터는 무엇 인가요?  

새로운 관리 센터 환경은 팀과 비즈니스용 Skype를 모두 관리할 수 있는 통일 된 환경을 제공 합니다. 추가 기능, 종단 간 insights, 사용자 수준에서 팀 설정을 관리 하는 기능을 제공 하는 것입니다. 의 관리 센터에 액세스할 수 있습니다 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

![Microsoft 팀 관리 센터의 스크린샷.](media/manage-teams-skype-for-business-admin-center-portal.png)

## <a name="settings-migrated-to-the-new-microsoft-teams-admin-center"></a>새 Microsoft 팀 관리 센터로 마이그레이션된 설정

다음 표에서는 마이그레이션된 팀 환경의 섹션을 식별 하 고 새 관리 포털의 현재 설정과 정책 간의 관계를 보여 줍니다.

|Microsoft 365 관리 센터의 팀 섹션  |설정 이름 (테 넌 트 수준)  |Microsoft 팀 관리 센터 정책   |수준: 테 넌 트 또는 사용자   |
|---------|---------|---------|---------|
|일반     |개인 프로필에 조직도 표시        |  [TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)       |  테 넌 트       |
|일반     |팀이 없는 받는 사람에 게 비즈니스용 Skype 사용         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |테 넌 트         |
|전자 메일 통합     |사용자가 채널에 전자 메일을 보낼 수 있도록 허용         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |테 넌 트         |
|전자 메일 통합     |보낸 사람 목록 허용         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)        |테 넌 트         |
|사용자 지정 클라우드 저장소     |확인란이         |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |테 넌 트         |
|사용자 지정 클라우드 저장소     |상자        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |테 넌 트         |
|사용자 지정 클라우드 저장소     |Egnyte (출시 예정)        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |테 넌 트         |
|사용자 지정 클라우드 저장소     |Google Drive        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |테 넌 트         |
|사용자 지정 클라우드 저장소     |ShareFile        |[TeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)         |테 넌 트         |
|사용자/라이선스 유형별 설정     |모든 사용자에 대해 Microsoft 팀 설정 또는 해제          |사용 되지 않음<sup>1</sup>        |         |
|팀 및 채널     |         |Azure Active Directory 그룹 관리로 리디렉션합니다 (현재 환경과 동일).              |사용자         |
|팀 및 채널     |         |AAD 그룹 관리로 리디렉션합니다 (현재 환경과 동일).             |사용자          |
|앱|기본적으로 새 외부 앱 사용|조직 전체 앱 설정|테 넌 트|
|앱|외부 앱 허용|조직 전체 앱 설정|테 넌 트|
|앱|외부 앱의 테스트용 로드 허용<sup>2</sup>|[TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)|사용자|
|앱|기본 앱<sup>3</sup>|TeamsAppPermissionPolicy|사용자|
|앱|외부 앱<sup>3</sup>|TeamsAppPermissionPolicy|사용자|
|통화 및 모임     |비공개 모임에 대 한 예약 허용         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |사용자          |
|통화 및 모임     |Ad hoc 채널 잔 허용         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |사용자          |
|통화 및 모임     |채널 모임 예약 허용         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |사용자          |
|통화 및 모임     |모임에서 비디오 허용         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |사용자          |
|통화 및 모임     |모임에서 화면 공유 허용         |[TeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)         |사용자          |
|통화 및 모임     |개인 통화 허용         |[TeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)        |사용자          |
|메시징     |사용자가 대화에 Gif를 추가할 수 있도록 Giphy 설정         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |사용자         |
|메시징     |콘텐츠 등급         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |사용자         |
|메시징     |사용자가 편집 하 고 대화에 추가할 수 있는 밈         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |사용자         |
|메시징     |사용자가 편집 하 고 대화에 추가할 수 있는 스티커 사용         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |사용자         |
|메시징     |소유자가 모든 메시지를 삭제할 수 있도록 허용         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |사용자         |
|메시징     |사용자가 자신의 메시지를 편집할 수 있도록 허용         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |사용자         |
|메시징     |사용자가 자신의 메시지를 삭제할 수 있도록 허용         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |사용자         |
|메시징     |사용자가 개인적으로 채팅 하도록 허용 합니다.         |[TeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)         |사용자         |

<sup>1</sup> 게스트에 사용 되지 않습니다. 이제 게스트를 사용 하거나 사용 하지 않도록 설정 하면 Microsoft 팀 관리 센터에서 관리할 수 있습니다. 비즈니스 Enterprise, .Edu Student, .Edu 교직원 용 팀을 활성화/비활성화 하는 것은 곧 더 이상 사용 되지 않습니다. 이는 Microsoft 365 관리 센터에서 라이선스를 할당 하 여 관리 해야 합니다. [Microsoft 팀에 대 한 사용자 액세스 관리를](user-access.md)참조 하세요.
<br><br>
<sup>2</sup> 테스트용 로드는 다음과 같이 나누어집니다.

- 사용자가 [TeamsAppSetupPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsappsetuppolicy?view=skype-ps)의 사용자 수준에서 관리할 수 있는 앱을 테스트용으로 로드 수 있도록 허용 합니다.
- 테 넌 트에서 사용자가 조직 전체 앱 설정의 테 넌 트 수준에서 관리할 수 있는 사용자 지정 앱과 상호 작용할 수 있도록 허용 합니다.
 
<sup>3</sup> TeamsAppPermissionPolicy의 사용자 수준에서 기본 앱 및 외부 앱을 사용 하도록 설정 하거나 사용 하지 않도록 설정할 수 있습니다. 또한 사용자 및 테 넌 트 수준 설정을 재정의 하는 조직 전체 앱 설정에서 테 넌 트 수준에서 앱을 차단할 수 있습니다. 

> [!NOTE]
> 팀 및 채널과 관련 된 구성의 경우 Microsoft 365 관리 센터에서 그룹 대시보드를 계속 사용 합니다. 앱에 대 한 설정은 Microsoft 365 관리 센터의 팀 영역에 유지 되 고 나중에 마이그레이션됩니다. 

## <a name="manage-settings-during-the-migration"></a>마이그레이션 중 설정 관리

테 넌 트에 대해 섹션의 마이그레이션이 완료 될 때까지 Microsoft 365 관리 센터 및 비즈니스용 Skype 관리 센터에서 설정을 계속 수정할 수 있습니다. 

다음 표에서는 마이그레이션 중에 기능을 관리할 수 있는 위치를 보여 줍니다.

|기능  |Microsoft 팀 관리 센터                      |비즈니스용 Skype 관리 센터 (레거시)  |Microsoft 365 관리 센터  |
|---------|:---------:|:---------:|:---------:|
|팀 메시징, 모임 및 라이브 이벤트 정책     |     X    |         |         |
|팀 업그레이드 정책     |    X     |         |         |
|메시징, 모임, 음성에 대 한 게스트 설정     |   X      |         |         |
|팀 수명 주기 관리   |    X    |      |       |
|팀 설정   |    X    |      |       |
|외부 액세스 설정     |    X    |      |       |
|사용자 관리    |         |         |    X     |    
|오디오 회의     |    X     |    X     |         |
|통화 요금제     |    X    |    X     |         |
|전화 시스템    |    X    |     X    |         |
|전화 번호 관리     |    X    |   X      |         |
|클라우드 음성 기능 라이선스     |         |         |    X     |
|자동 전화 교환     |    X    |          |         |
|통화 큐     |    X    |          |         |

## <a name="manage-settings-after-the-migration"></a>마이그레이션 후 설정 관리

이러한 설정의 마이그레이션이 완료 되 면 Microsoft 365 관리 센터 및 비즈니스용 Skype 관리 센터에서이 설정을 사용 하지 않도록 설정 하 고 새 Microsoft 팀 관리 센터에서 관리할 수 있습니다.
