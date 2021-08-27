---
title: 중소 기업 Microsoft Teams 설정
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 중소 기업에서 Teams를 설정하면 사용자가 채팅 및 파일 공유를 사용하여 공동 작업하고 소규모, 대규모 모임을 설정 및 참가하고 영상 및 음성으로 대화할 수 있습니다.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7e15a8a327d40ea11412229205fca6e856e9f7b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596322"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a>중소 기업 Microsoft Teams 설정

Teams를 사용자 지정하는 방법에는 여러 가지가 있습니다. 다음 섹션에서는 각 Teams 워크로드(**채팅, 팀 및 채널**, **모임 및 회의** 및 **Cloud Voice**)를 설정하는 방법을 보여 줍니다. 각 워크로드를 설정하는 순서는 사용자가 결정합니다. 먼저 채팅, 팀 및 채널 워크로드를 먼저 설정하는 것이 좋지만, 모임 및 회의나 Cloud Voice으로 설정할 수 있습니다. 선택은 자유입니다.

> [!NOTE]
> 아직 완료하지 않은 경우, Teams 배포 파일럿을 시작하는 것이 좋습니다. 파일럿을 통해 사용자와 일부 얼리어답터는 계획 및 최종 배포 전에 Teams와 Teams의 기능에 익숙해질 수 있습니다. 파일럿을 시작하는 방법에 대한 자세한 내용은 [Microsoft Teams 시작](get-started-with-teams-quick-start.md)을 참조하세요.

Teams를 광범위하게 배포하기 전에 [준비되었는지 확인](get-started-with-teams-quick-start.md#make-sure-youre-ready)에서 항목을 검토하여 조직이 준비되었는지 확인해야 합니다.

관심 있는 섹션으로 이동:

- [워크로드](#workloads)
  - [채팅, 팀 및 채널](#chat-teams-and-channels)
  - [모임 및 회의](#meetings-and-conferencing)
  - [Business Voice](#business-voice)
- [클라이언트 배포](#deploy-clients)
- [교육](#training)

## <a name="workloads"></a>워크로드
### <a name="chat-teams-and-channels"></a>채팅, 팀 및 채널

채팅, 팀 및 채널은 Teams의 기본입니다. **채팅** 에서는 한 명 이상의 사용자가 서로 대화하고 파일을 공유하고 개인적으로 만날 수 있습니다. **팀** 에서는 조직 내의 모든 사람이 또는 팀 구성원만 볼 수 있어 장기간 실행되는 프로젝트나 생일 파티를 계획하는 작업이나 상황에 관계없이 적합한 사람이 공동 작업할 수 있도록 합니다. **채널** 에서는 팀 내에서 주제, 프로젝트, 부서 또는 다른 항목을 분할할 수 있습니다. 채팅, 팀 및 채널에 대한 자세한 내용은 [팀 및 채널 개요](teams-channels-overview.md)를 확인하세요.

> [!TIP]
> 팀 역할, 액세스 및 메시지 정책을 관리하는 방법은 Microsoft Learn에서 [Microsoft Teams 관리](/learn/modules/m365-teams-collab-manage-teams/) 모듈을 완료하여 알아보세요.

팀과 채널을 배포하려면 팀과 채널을 만들 수 있는 사용자와 조직 외부 게스트가 팀과 채널에 액세스할 수 있는지 여부 등을 결정해야 합니다. [Microsoft Teams의 채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md) 문서에는 채팅, 팀 및 채널 계획에 대한 많은 정보가 있지만, 다음에 이 문서에서 고려해야할 몇 가지 주요 사항이 있습니다. 더 많은 정보를 원하면 결정을 선택하세요.

| 판단 | 설명 |
|--|--|
| [Teams 관리자는 누구인가요?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-administrators) | 관리자 역할은 Teams를 관리하려는 사용자에게 특정 사용 권한을 부여하는 데 사용할 수 있습니다. 중소 기업의 경우, 같은 사람이 Teams의 모든 측면을 담당할 수 있기 때문에 이러한 추가 역할이 필요하지 않을 수 있습니다. 나중에 언제든지 관리자를 추가하거나 제거할 수 있습니다.<br><br>[Microsoft Teams 관리자 역할을 사용하여 Teams 관리](using-admin-roles.md) |
| [팀 소유자와 구성원은 누구인가요?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-owners-and-members) | 팀 소유자는 팀 및 해당 채널에 액세스할 수 있는 권한을 제어합니다. 팀 또는 채널이 공개(조직에)인지 아니면 비공개인지를 결정하고 채널의 중재 여부와 같은 정책을 설정할 수 있습니다. 구성원은 팀과 해당 채널에 액세스할 수 있으며(채널이 비공개로 설정되어 있으며 해당 채널의 구성원이 아닌 경우) 중재자로 지정될 수 있습니다.<br><br>[Microsoft Teams에서 팀 소유자 및 구성원 할당](assign-roles-permissions.md) |
| [게스트 액세스를 사용하도록 설정해야 하나요?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#guest-access) |게스트 액세스를 통해 조직 내부의 사용자가 조직 외부의 사용자를 팀 및 채널에 액세스할 수 있도록 초대할 수 있습니다. 게스트 액세스는 조직 외부 사용자와 공식적인 관계가 없는 사용자와 공동 작업하는 데 주로 사용됩니다. 예를 들어 프로젝트에서 일시적으로 작업할 프로젝트 플래너를 초대할 수 있습니다.<br>게스트 액세스는 외부 액세스와 다릅니다. 게스트 액세스는 조직 내 사용자와 상호 작용하기 위해 특정 개인 액세스를 초대합니다.  <br>게스트 액세스 기능은 기본적으로 **꺼져있습니다**. <br><br>[Microsoft Teams에 대한 게스트 액세스 켜기 또는 끄기](set-up-guests.md)  |

사용자가 채팅, 팀 및 채널 사용을 시작하기 위해 다른 작업을 할 필요가 없습니다. 그러나 Teams 사용 방법을 제어하기 위한 옵션은 많이 있습니다. 지금 변경하거나 사람들이 Teams를 사용하는 방법을 지켜보고 나중에 변경할 수 있습니다. 자세한 내용에 대해서는 다음 문서를 확인하세요.

- [Teams에서 메시징 정책 관리](messaging-policies-in-teams.md)
- [Teams 설정](enable-features-office-365.md#teams-settings)

### <a name="meetings-and-conferencing"></a>모임 및 회의

모임 및 회의를 통해 조직 내 사용자가 서로 만나고 조직 외부 사용자와도 만날 수 있습니다. Teams 또는 비즈니스용 Skype 클라이언트가 있는 모든 사용자는 초대된 **모임** 에 참가할 수 있습니다. 장치의 마이크, 카메라 및 화면을 사용하여 참가자는 휴대폰 없이도 대화에 참여할 수 있습니다. 참가자는 PC 또는 모바일 장치를 사용하여 채팅하고, 음성 통화를 걸고, 비디오 및 앱을 다른 참가자와 공유할 수 있습니다.

**오디오 회의** 를 통해 회의 전화 번호로 전화를 걸고 모임 ID를 입력하여 일반 전화로 모임에 참가할 수 있습니다. 오디오 회의는 참가자가 인터넷에 연결되어 있지 않거나, 모임이 음성 전용이거나, Teams 클라이언트를 통해 참가할 수 없는 다른 상황에서 유용합니다.

> [!TIP]
> 모임 및 이벤트는 Microsoft Learn에서 [Microsoft Teams 모임, 화의 및 이벤트 관리](/learn/modules/m365-teams-collab-manage-meetings) 모듈을 완료하여 더 익숙해질 수 있습니다.

Teams에서는 모임이 기본적으로 활성화되어 있지만, 이끌이 및 참가자의 모임 환경을 제어할 수 있습니다. 또한 모임 전이나 모임 중에 허용된 사람과 허용되지 않는 사람에 대한 정책을 설정할 수 있습니다. 자세한 내용에 대해서는 다음 문서를 확인하세요.

- [관리자 빠른 시작 - Microsoft Teams의 모임 및 라이브 이벤트](quick-start-meetings-live-events.md)
- [중소 기업을 위한 오디오 회의 설정](audio-conferencing-smb.md)

### <a name="business-voice"></a>Business Voice

[Microsoft 365 Business Voice](business-voice/whats-business-voice.md)는 사무실 전화 시스템의 모든 기능을 제공하는 300명 미만의 사용자를 보유한 기업에 적합한 솔루션입니다. Business Voice에는 복잡하고 비용이 많이 드는 사내 전화 시스템을 관리할 필요 없이 음성 메일, 발신자 ID, 전화 시스템 메뉴, 무료 전화 번호 등이 포함되어 있습니다.

Microsoft 365 전화 시스템을 기반으로 하는 Business Voice는 전화 시스템 기능과 추가 기능을 결합하고 전화 시스템을 설정하는 데 도움이 되는 간편한 마법사를 제공하여 조직에 음성을 간편하게 추가할 수 있도록 지원합니다. 조직이 [Business Voice를 지원하는 국가나 지역](business-voice/country-region-availability.md)에 있는 경우, 전화 번호를 Microsoft 365로 전송하여 전화 시스템을 관리할 수 있습니다.

Microsoft 365를 전화 시스템으로 사용하는 경우 Teams 클라이언트를 설치하여 장치를 전화로 전환할 수 있습니다. 또는 기존의 업무 전화나 전화 회의를 원하는 경우 여러 Teams 인증 장치를 선택하여 사용할 수 있습니다. 어느 쪽이든 통화는 항상 현재 위치로 라우팅됩니다. 전화를 걸면 항상 사무실 전화 번호가 뜹니다.

Business Voice를 사용햐보고 싶은 경우 [Microsoft 365 Business Voice를 사용하려면 무엇을 구입해야 하나요?](business-voice/what-to-buy.md)를 참조하세요.

## <a name="deploy-clients"></a>클라이언트 배포

Teams를 사용할 준비가 되면 Windows, Mac, Linux PC나Android, iOS 장치에 Teams 클라이언트를 설치할 수 있습니다. <https://teams.microsoft.com/downloads>에서 Teams 클라이언트를 직집 다운로드할 수 있습니다.

Teams를 사용할 모든 사람에게 Teams 라이선스가 있는지 확인 Teams 라이선스 할당에 대한 자세한 내용은 [Teams에 대한 사용자 액세스 관리](user-access.md#using-the-microsoft-365-admin-center)를 참조하세요.

> [!TIP]
> Microsoft Learn에서 [Microsoft Teams 클라이언트 배포](/learn/modules/m365-teams-collab-deploy-clients/) 모듈을 완료하여 Teams 클라이언트 배포를 계획하는 방법에 대한 권장 사항을 확인하세요.

조직에서 Microsoft Endpoint Configuration Manager, 그룹 정책 또는 타사 배포 메커니즘을 사용하여 사용자의 컴퓨터에 소프트웨어를 배포하는 경우 [Microsoft Endpoint Configuration Manager를 사용하여 Microsoft Teams 설치](msi-deployment.md)를 참조하세요.

Teams 클라이언트 배포에 대한 자세한 내용은 [Microsoft Teams 클라이언트 다운로드](get-clients.md)를 참조하세요.

## <a name="training"></a>교육

사용자가 Teams를 사용하도록 교육하는 방법에 대한 자세한 내용은 [Microsoft Teams 교육](training-microsoft-teams-landing-page.md)을 참조하세요.