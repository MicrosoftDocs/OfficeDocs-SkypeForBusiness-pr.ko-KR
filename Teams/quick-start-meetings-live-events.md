---
title: 관리자 빠른 시작 - Microsoft Teams의 모임 및 라이브 이벤트
ms.reviewer: ''
description: Microsoft Teams에서 온라인 모임 및 라이브 이벤트에 대한 라이선스를 받고, 배포 및 구성할 수 있는 관리자를 위한 빠른 시작 가이드입니다.
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ca2c048b28d82c7c41a7f98712264c739bce210
ms.sourcegitcommit: d5e77f8a3b8084ed92f0a77888a555626309591b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/18/2021
ms.locfileid: "52517741"
---
# <a name="admin-quick-start---meetings-and-live-events-in-microsoft-teams"></a>관리자 빠른 시작 - Microsoft Teams의 모임 및 라이브 이벤트

Microsoft Teams에서는 2개의 방법(모임 및 라이브 이벤트)을 통해 모임을 가질 수 있습니다. 이 문서를 사용하여 조직의 모임 및 라이브 이벤트를 빠르게 배포하고 구성할 수 있습니다.

> [!Note]
> 여러 플랫폼에서 Teams 모임 및 이벤트를 신속하게 구성에 대한 자세한 내용은 [플랫폼별 Teams 기능을 참조](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)하세요.

 - Teams의 **모임** 에는 최대 1000명의 사용자를 위한 음성, 영상 및 화면 공유 기능이 포함됩니다. 이러한 기능은 Teams에서 공동 작업하는 주요 방법 중 하나입니다. 조직의 구성원이 아니거나(심지어 Teams 계정이 없어도) Teams 모임에 참여할 수 있습니다. 전화 걸기에 대한 지침은 초대를 참조하세요.

 - **라이브 이벤트** 는 대규모 온라인 사용자(최대 10,000명)에게 스트리밍되는 이벤트를 예약하고 생성할 수 있도록 해주는 Teams 모임의 확장입니다. 1000명 이상의 사용자를 위한 모임을 필요로 하는 경우에는 라이브 이벤트를 사용합니다.

## <a name="get-licenses-for-meetings-and-live-events"></a>모임 및 라이브 이벤트에 대한 라이선스 받기

모든 사용자는 Teams 모임 또는 공개 라이브 이벤트에 무료로 참석할 수 있습니다. 이 때 라이선스는 필요하지 않습니다. 참석자는 Teams 또는 모임 초대에서 **참가** 단추를 클릭하여 Teams 모임이나 라이브 이벤트에 참가합니다. 모임 오디오는 Teams 모임의 일부이지만 사용자가 전화를 통해 모임에 전화를 걸 수 있게 하려면 전화 접속 번호를 제공해야 합니다.

모임 또는 라이브 이벤트를 구성, 예약 및 호스트하는 사용자의 경우, 아래 표에 나열된 Microsoft 365 또는 Office 365 라이선스 중 하나가 필요합니다. 이미 Teams를 사용하고 있는 경우, 모임 및 라이브 이벤트를 구성하고 호스트하는 데 필요한 라이선스가 아마도 있을 것입니다.

:::image type="content" source="media/quick-start-meetings-live-events-image1.png" alt-text="Teams 모임이나 라이브 이벤트에 필요한 라이선스가 포함된 표":::

> <sup>1</sup> 모임 이끌이는 전화 접속 회의를 포함하는 초대를 보내려면 [오디오 회의 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)가 있어야 합니다.
>
> <sup>2</sup> [**번호** 로 전화 걸기](set-up-the-call-me-feature-for-your-users.md)에 대한 모임 전화 걸기는 모임 이끌이가 E5 또는 [오디오 회의 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 보유하고 있어야 합니다. [다이얼 플랜](what-are-dial-plans.md) 또한 필요할 수도 있습니다.

라이선싱에 대한 자세한 내용은 [Microsoft Teams 서비스 설명](/office365/servicedescriptions/teams-service-description)을 읽어보세요.

## <a name="make-sure-your-networks-ready"></a>네트워크가 준비가 되었는지 확인합니다.

Microsoft 365 또는 Office 365를 배포할 때 네트워크가 이미 준비된 경우, 모두 설정되었을 수 있습니다. 경우에 따라, 특히 **원격 작업자** 를 지원하기 위해 첫 Office 365 워크로드로서 Teams를 빠르게 배포하는 경우, [Teams에 대해 조직 네트워크 준비](prepare-network.md)를 참조하여 준비가 되었는지 확인합니다.

## <a name="meetings-and-conferencing"></a>모임 및 회의

- 관리자는 모든 사용자에 대해 [모임 설정](meeting-settings-in-teams.md)을 구성할 수 있습니다. 그런 다음 [모임 정책](meeting-policies-in-teams.md)을 사용하여 사용자가 사용할 수 있는(없는) 모임 기능을 제어합니다.

- 모임 녹음/녹화를 관리하는 방법에 대해 알아보려면 [Teams 클라우드 모임 녹음/녹화](cloud-recording.md)를 참조하세요.

- Teams 모임을 처음 사용하는 사용자인 경우, [모임 관리](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) 교육을 공유하세요. 당사의 강사 주도 온라인 수업, [Teams로 모임을 효과적으로 진행](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings)을 확인하세요.

- 모임 옵션 관리에 대한 자세한 내용은 [Teams 모임에 대한 참가자 설정 변경](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)을 참조하세요.

- 휴대폰, 헤드셋, 카메라 등의 [사용자 장치 관리](./devices/device-management.md)에 대해 잊지마세요. Teams 인증 장치에 대한 최신 정보를 얻으려면 [Teams 장치](https://office.com/teamsdevices)로 이동합니다.

## <a name="live-events"></a>라이브 이벤트

- 모임과 마찬가지로, 관리자는 모든 사용자에 대해 [라이브 이벤트를 구성](teams-live-events/configure-teams-live-events.md)할 수 있습니다. 그런 다음 [라이브 이벤트 정책](teams-live-events/set-up-for-teams-live-events.md)을 설정(할당)하고 사용자가 수행할 수 있는(그리고 없는) 작업을 제어합니다.

- 라이브 이벤트 제작자 및 주최자가 교육을 받은 상태인지 확인하고 [라이브 이벤트 시작하기](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a)로 보냅니다.

- 라이브 이벤트를 처음 사용한 경우 [Teams 라이브 이벤트가 무엇인가요?](teams-live-events/what-are-teams-live-events.md) 및 [Teams 라이브 이벤트에 대한 계획](teams-live-events/plan-for-teams-live-events.md)을 확인하세요.

## <a name="related-topics"></a>관련 항목

[Teams의 모임 및 모임](deploy-meetings-microsoft-teams-landing-page.md)

[Teams의 오디오 모임](deploy-audio-conferencing-teams-landing-page.md)

[Teams의 라이브 이벤트](teams-live-events/what-are-teams-live-events.md)

[Teams의 제한과 사양](limits-specifications-teams.md)

[Microsoft 기술 커뮤니티: Microsoft 365의 라이브 이벤트](https://resources.techcommunity.microsoft.com/live-events/)
