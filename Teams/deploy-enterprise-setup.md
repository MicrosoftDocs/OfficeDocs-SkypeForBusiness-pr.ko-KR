---
title: 엔터프라이즈에서 Microsoft Teams 설정
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 엔터프라이즈에서 Teams를 설정하면 사용자가 채팅 및 파일 공유를 사용하여 공동 작엔터프라이즈하고 소규모, 대규모 모임을 설정 및 참가하고 영상 및 음성으로 대화할 수 있습니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4614bc88ba65803ea5a8696af9e55a104912855
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101304"
---
# <a name="set-up-microsoft-teams-in-your-enterprise"></a>엔터프라이즈에서 Microsoft Teams 설정

이 문서의 정보를 사용하여 조직에서 Teams 배포를 안내합니다.

> [!NOTE]
> 아직 완료하지 않은 경우, Teams 배포 파일럿을 시작하는 것이 좋습니다. 파일럿을 통해 사용자와 일부 얼리어답터는 계획 및 최종 배포 전에 Teams와 Teams의 기능에 익숙해질 수 있습니다. 파일럿을 시작하는 방법에 대한 자세한 내용은 [Microsoft Teams 시작](get-started-with-teams-quick-start.md)을 참조하세요.

Teams를 광범위하게 배포하기 전에 [준비되었는지 확인](get-started-with-teams-quick-start.md#make-sure-youre-ready)에서 항목을 검토하여 조직이 준비되었는지 확인해야 합니다.

## <a name="plan-your-deployment"></a>배포 계획

Teams 배포를 시작하기 전에 계획 프로세스를 완료해야 합니다. 계획 프로세스에는 다음이 포함되어야 합니다.

- Teams 아키텍처 이해
- Teams 워크로드 및 Microsoft 365에서의 사용법 검토 및 이해
- 네트워크 요구 사항을 계산하고 네트워크 및 인터넷 연결이 실시간 통신과 같은 중요한 요구 사항을 지원하는 데 필요한 하드웨어와 용량을 갖추도록 합니다.
- Teams 및 기타 Microsoft 365 서비스에 저장된 정보에 대한 규정 및 규정 준수 요구 사항 이해
- 사용자가 Teams 사용의 이점을 이해하는 데 도움이 되는 채택 계획 만들기

배포에 도움이 되는 [Teams용 어드바이저](https://admin.teams.microsoft.com/teams-deployment) 사용을 적극 권장합니다. Teams 어드바이저의 작동 방법에 대한 자세한 내용은 [Teams용 어드바이저를 사용하여 Microsoft Teams 배포](use-advisor-teams-roll-out.md)를 참조하세요.

> [!TIP]
> Microsoft Learn에서 [Teams용 Advisor를 사용하여 원격 설치](/learn/modules/m365-teams-rollout-using-advisor/) 모듈을 완료하여 Teams용 어드바이저를 사용하여 Teams 배포를 계획하는 방법을 참조하세요.

Teams 계획 수립에 대한 자세한 내용은 [Teams 엔터프라이즈 배포 개요](deploy-enterprise-overview.md)를 참조하세요.

## <a name="workloads"></a>워크로드

Teams를 사용자 지정하는 방법에는 여러 가지가 있습니다. 다음 섹션에서는 각 Teams 워크로드(**채팅, 팀 및 채널**, **모임 및 회의** 및 **전화 시스템**)를 설정하는 방법을 보여 줍니다. 각 워크로드를 설정하는 순서는 사용자가 결정합니다. 먼저 채팅, 팀 및 채널 워크로드를 먼저 설정하는 것이 좋지만, 모임 및 회의나 전화 시스템으로 설정할 수 있습니다.

#### <a name="chat-teams-and-channels"></a>[채팅, 팀 및 채널](#tab/ChatTeamsChannels)

채팅, 팀 및 채널은 Teams의 기본입니다. **채팅** 에서는 한 명 이상의 사용자가 서로 대화하고 파일을 공유하고 개인적으로 만날 수 있습니다. **팀** 에서는 조직 내의 모든 사람이 또는 팀 구성원만 볼 수 있어 장기간 실행되는 프로젝트나 생일 파티를 계획하는 작업이나 상황에 관계없이 적합한 사람이 공동 작업할 수 있도록 합니다. **채널** 에서는 팀 내에서 주제, 프로젝트, 부서 또는 다른 항목을 분할할 수 있습니다. 채팅, 팀 및 채널에 대한 자세한 내용은 [팀 및 채널 개요](teams-channels-overview.md)를 확인하세요.

> [!TIP]
> 팀 역할, 액세스 및 메시지 정책을 관리하는 방법은 Microsoft Learn에서 [Microsoft Teams 관리](/learn/modules/m365-teams-collab-manage-teams/) 모듈을 완료하여 알아보세요.

### <a name="administration-and-team-ownership"></a>관리 및 팀 소유권

| 판단 | 설명 |
|--|--|
| Teams 관리자는 누구인가요? | 관리자 역할은 Teams를 관리하려는 사용자에게 특정 사용 권한을 부여하는 데 사용할 수 있습니다. 중소 기업의 경우, 같은 사람이 Teams의 모든 측면을 담당할 수 있기 때문에 이러한 추가 역할이 필요하지 않을 수 있습니다. 나중에 언제든지 관리자를 추가하거나 제거할 수 있습니다.<p>[Microsoft Teams 관리자 역할을 사용하여 Teams 관리](using-admin-roles.md) |
| 팀 소유자와 구성원은 누구인가요? | 팀 소유자는 팀 및 해당 채널에 액세스할 수 있는 권한을 제어합니다. 팀 또는 채널이 공개(조직에)인지 아니면 비공개인지를 결정하고 채널의 중재 여부와 같은 정책을 설정할 수 있습니다. 구성원은 팀과 해당 채널에 액세스할 수 있으며(채널이 비공개로 설정되어 있으며 해당 채널의 구성원이 아닌 경우) 중재자로 지정될 수 있습니다.<p>[Microsoft Teams에서 팀 소유자 및 구성원 할당](assign-roles-permissions.md) |

### <a name="default-settings-and-lifecycle-policies"></a>기본 설정 및 수명 주기 정책

| 판단 | 설명 |
|--|--|
| 어떤 메시지 정책을 적용해야 하나요? | 메시지 정책은 Teams에서 어떤 채팅 및 채널 메시징 기능(예: 채팅을 사용할 수 있는 사용자, 보낸 메시지를 편집하고 삭제할 수 있는 사용자 등)을 사용자가 사용할 수 있는지 제어합니다. Teams에는 모든 사용자에게 적용되는 전역 정책이 있습니다. 전역 정책의 모든 기능은 기본적으로 **켜져있습니다**.<p>모든 사용자에 대해 동일한 정책을 적용하려면 이 전역 정책을 변경하기만하면 됩니다(예: 대화에서 밈 지원 해제).<p>다른 그룹의 사용자들에게 서로 다른 정책(예: 사무실 근로자를 위한 정책 하나 및 공장 근로자용 정책 하나)을 사용하려는 경우 정책을 만들고 할당할 수 있습니다. 사용자에게 정책을 할당하는 경우 전역 정책은 더 이상 해당 사용자에게 적용되지 않습니다.<p>[Teams에서 메시지 정책 관리](messaging-policies-in-teams.md) |
| 어떤 Teams 설정을 적용해야 하나요? | Teams 설정을 사용하여 팀에 전자 메일의 통합, 클라우드 저장소 옵션, 조직 탭, 회의실 장치 설정 및 검색 범위와 같은 기능을 설정할 수 있습니다. 이러한 설정을 변경하면 변경 사항은 조직의 모든 팀에 적용됩니다. <p>[Teams 설정](enable-features-office-365.md#teams-settings)  |

### <a name="external-and-guest-access"></a>외부 및 게스트 액세스

| 판단 | 설명 |
|--|--|
| 외부 액세스를 사용하도록 설정해야 하나요? | 외부 액세스를 사용하면 다른 조직의 모든 사용자가 조직의 사용자와 대화할 수 있습니다. 이는 공급업체와 같은 다른 조직과 긴밀한 관계를 맺고 두 조직의 사용자가 서로 채팅하고 모임을 잡는 등의 작업을 용이하게 하려는 경우 유용합니다. <p>외부 액세스는 게스트 액세스와 다릅니다. 외부 액세스를 사용하면 다른 조직의 모든 사용자가 조직의 사용자와 상호 작용할 수 있습니다. 게스트 액세스는 조직 내 사용자와 상호 작용하기 위해 특정 개인 액세스를 초대합니다.<p>외부 액세스 기능은 기본적으로 **꺼져있습니다**.<p>[Microsoft Teams에서 외부 액세스 관리](manage-external-access.md)  |
| 게스트 액세스를 사용하도록 설정해야 하나요? |게스트 액세스를 통해 조직 내부의 사용자가 조직 외부의 사용자를 팀 및 채널에 액세스할 수 있도록 초대할 수 있습니다. 게스트 액세스는 조직 외부 사용자와 공식적인 관계가 없는 사용자와 공동 작업하는 데 주로 사용됩니다. 예를 들어 프로젝트에서 일시적으로 작업할 프로젝트 플래너를 초대할 수 있습니다.<p>게스트 액세스는 외부 액세스와 다릅니다. 게스트 액세스는 조직 내 사용자와 상호 작용하기 위해 특정 개인 액세스를 초대합니다. 외부 액세스를 사용하면 다른 조직의 모든 사용자가 조직의 사용자와 상호 작용할 수 있습니다. <p>게스트 액세스 기능은 기본적으로 **꺼져있습니다**. <p>[Microsoft Teams에 대한 게스트 액세스 켜기 또는 끄기](set-up-guests.md)  |

#### <a name="meetings-and-audio-conferencing"></a>[모임 및 오디오 회의](#tab/MeetingsAudioConferencing)

모임 및 회의를 통해 조직 내 사용자가 서로 만나고 조직 외부 사용자와도 만날 수 있습니다. Teams 또는 비즈니스용 Skype 클라이언트가 있는 모든 사용자는 초대된 **모임** 에 참가할 수 있습니다. 장치의 마이크, 카메라 및 화면을 사용하여 참가자는 휴대폰 없이도 대화에 참여할 수 있습니다. 참가자는 PC 또는 모바일 장치를 사용하여 채팅하고, 음성 통화를 걸고, 비디오 및 앱을 다른 참가자와 공유할 수 있습니다.

**오디오 회의** 를 통해 회의 전화 번호로 전화를 걸고 모임 ID를 입력하여 일반 전화로 모임에 참가할 수 있습니다. 오디오 회의는 참가자가 인터넷에 연결되어 있지 않거나, 모임이 음성 전용이거나, Teams 클라이언트를 통해 참가할 수 없는 다른 상황에서 유용합니다.

> [!TIP]
> 모임 및 이벤트는 Microsoft Learn에서 [Microsoft Teams 모임, 화의 및 이벤트 관리](/learn/modules/m365-teams-collab-manage-meetings) 모듈을 완료하여 더 익숙해질 수 있습니다.

### <a name="meetings"></a>모임

| 판단 | 설명 |
|--|--|
| 어떠한 조직 전체 모임 설정을 적용해야 하나요?| 모임 정책은 모임 이끌이 및 모임 참가자가 사용할 수 있는 모임 기능을 제어합니다. 익명 참가자가 모임에 참가할 수 있는지 여부, 모임 초대 사용자 지정, 실시간 미디어 처리 방법 등 다양한 작업을 제어할 수 있습니다. 이러한 설정을 변경하면 변경 사항은 조직의 모든 모임에 적용됩니다. <p>[Microsoft Teams에서 모임 설정 관리](meeting-settings-in-teams.md)|
| 어떤 모임 정책을 적용해야 하나요? | 모임 정책은 조직에서 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다. 사용자가 비공개 모임을 예약할 수 있는지, 지금 모임 시작 옵션을 사용할 수 있는지, 모임을 레코딩할 수 있는지 여부를 제어할 수 있습니다. Teams에는 모든 사용자에게 적용되는 전역 정책이 있습니다.<p> 모든 사용자에 대해 동일한 정책을 적용하려면 이 전역 정책을 변경하기만하면 됩니다(예: 모임 레코딩 끄기). <p>다른 그룹의 사용자들에게 서로 다른 정책(예: 사무실 근로자를 위한 정책 하나 및 임원진용 정책 하나)을 사용하려는 경우 정책을 만들고 할당할 수 있습니다. 사용자에게 정책을 할당하는 경우 전역 정책은 더 이상 해당 사용자에게 적용되지 않습니다.<p> [Teams에서의 모임 정책 관리](meeting-policies-in-teams.md)|
| 모임 레코딩 및 보관을 허용하고 싶나요?| 모임 이끌이는 클라우드에서 모임을 레코딩 및 보관할 수 있습니다. 모임 정책을 사용하여 모임 레코딩 및 보관을 설정하거나 해제할 수 있습니다.<p> [Teams 클라우드 모임 녹음/녹화](cloud-recording.md) |

### <a name="audio-conferencing"></a>오디오 회의

| 판단 | 설명 |
|--|--|
| 타사 솔루션과의 비디오 상호 운용성을 설정하고 싶나요?| 클라우드 비디오 상호 운용성을 통해 타사 원거리 영상 회의 및 개인 비디오 장치를 이용하여 Teams 모임에 참가할 수 있습니다. 화상 회의 및 개인 비디오 장치에 이미 투자한 경우 비디오 상호 운용성을 사용하여 해당 장치를 Teams와 통합할 수 있습니다.<p> [Microsoft Teams용 클라우드 비디오 Interop](cloud-video-interop.md)|
| 어떤 조직 전체 오디오 회의 설정을 적용해야 하나요?| 오디오 회의 설정을 통해 모임 참가자가 전화를 사용하여 모임에 전화를 거는 방법을 제어할 수 있습니다. 모임에 참가하고, 회의 ID를 다시 설정하고, 참가자에게 오디오 회의 정보 전송을 사용하거나 사용하지 않도록 하는 등에 필요한 PIN의 길이를 설정할 수 있습니다. 오디오 회의 설정에 대한 변경 내용은 조직의 모든 사용자에 적용됩니다.<p>[Microsoft Teams에서 조직의 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) |
| 모임 이끌이가 대상에 전화를 걸 필요가 있나요?| 통신 크레딧은 오디오 회의 모임에서 조직 외부의 전화번호로 전화를 걸 때 사용됩니다. 오디오 회의 중에 크레딧이 부족하지 않도록 충분한 통신 크레딧을 구입해야 합니다.<p>일부 오디오 회의 구독에는 아웃바운드 통화가 포함될 수 있습니다. 자세한 내용은 구독 정보를 확인하세요.<p> [조직에 사용할 통신 크레딧 설정](set-up-communications-credits-for-your-organization.md)|
| 어떤 아웃바운드 통화 제한을 적용해야 하나요?| 아웃바운드 호출 제어를 사용하여 조직의 사용자가 만들 수 있는 오디오 회의 통화 유형을 제한할 수 있습니다. 예를 들어 모임에서 국제 전화 번호를 걸고, 아웃바운드 전화를 걸고, 특정 국가 또는 지역으로만 전화를 걸 수 있는지 여부를 제어할 수 있습니다.<p>[오디오 회의 및 사용자 PSTN 통화의 아웃바운드 전화 제한 정책](outbound-calling-restriction-policies.md) |
| Teams에서 전화번호를 변환하는 방식을 변경하고 싶나요? | 전화번호가 다이얼 플랜을 사용하여 변환되는 방식을 제어할 수 있습니다. 예를 들어, 외부 전화 회선에 전화를 걸 전화번호를 설정하고, 전화 내선번호 처리 방식을 제어하고, 전화 내선번호가 전체 전화번호로 변환되도록 하는 프리픽스를 설정할 수 있습니다.<p> [다이얼 플랜 만들기 및 관리](create-and-manage-dial-plans.md) |
| 라이브 이벤트를 사용하도록 설정하고 싶나요? | 라이브 이벤트를 통해 대규모 청중에게 비디오 및 모임 콘텐츠를 브로드캐스트할 수 있습니다. 라이브 이벤트를 사용하도록 설정한 경우 사용 방법을 제어하기 위한 정책을 설정할 수 있습니다. 예를 들어 참가자가 지원에 사용할 URL을 구성하고, 타사 비디오 배포 공급자가 있는 경우 이를 구성하는 등의 작업을 수행할 수 있습니다. Teams에는 모든 사용자에게 적용되는 전역 정책이 있습니다.<p>모든 사용자에 대해 동일한 정책을 적용하려면 이 전역 정책을 변경하기만하면 됩니다. <p>다른 그룹의 사용자들에게 서로 다른 정책(예: 사무실 근로자를 위한 정책 하나 및 임원진용 정책 하나)을 사용하려는 경우 정책을 만들고 할당할 수 있습니다. 사용자에게 정책을 할당하는 경우 전역 정책은 더 이상 해당 사용자에게 적용되지 않습니다.<p> [Microsoft Teams에서 실시간 이벤트 설정](teams-live-events/set-up-for-teams-live-events.md) |

#### <a name="phone-system-and-pstn-connectivity"></a>[전화 시스템 및 공중 전화망(PSTN) 연결](#tab/PhoneSystem)

전화 시스템을 사용하면 기존 온-프레미스 전화 시스템을 클라우드 환경과 밀접하게 통합된 Microsoft 365에서 제공하는 기능 집합으로 대체할 수 있습니다.

| 판단 | 설명 |
|--|--|
| 모든 온-프레미스 전화 시스템을 교체해 보시겠어요? | 전화 시스템을 설정하고 자동 전화 교환, 통화 플랜, 통화 대기열 등을 구성할 수 있습니다. <p> [조직에서 전화 시스템 설정](setting-up-your-phone-system.md)|
| 클라우드 음성 사서함 정책을 설정하고 싶나요?| 사용자가 사용할 수 있는 클라우드 음성 사서함 기능과 해당 기능의 작동 방법을 제어할 수 있습니다. 예를 들어 전체 조직에 대해 음성 사서함 전사 기능을 사용하거나 사용하지 않도록 설정하고 특정 사용자에 대해 욕설 필터링을 사용하거나 사용하지 않도록 설정할 수 있습니다.<p> [클라우드 음성 사서함 설정](set-up-phone-system-voicemail.md) |
| 동적 긴급 통화를 사용하도록 설정하고 싶나요?| 동적 긴급 통화를 사용하면 네트워크 설정 및 기타 메타데이터에 따라 위치 맵을 구성하여 사용자가 긴급 통화를 발신할 경우 비상 인력을 보낼 위치를 결정할 수 있습니다. 네트워크 설정을 구성하고, 위치에 긴급 주소를 할당하는 등 다양한 작업을 수행할 수 있습니다.<p>[동적인 긴급 전화 계획 및 구성](configure-dynamic-emergency-calling.md) |
| 발신자 ID 동작을 사용자 지정하고 싶나요? | 기본적으로 Teams 사용자가 전화를 걸 때 표시되는 전화번호는 사용자의 전화번호입니다. 이를 회사의 주 번호로 변경하거나, 전화번호를 차단하거나, 번호를 익명으로 만들거나, 다른 서비스 번호로 변경할 수 있습니다. Teams에는 모든 사용자에게 적용되는 전역 정책이 있습니다.<p>모든 사용자에 대해 동일한 정책을 적용하려면 이 전역 정책을 변경하기만하면 됩니다. <p>다른 그룹의 사용자들에게 서로 다른 정책(예: 사무실 근로자를 위한 정책 하나 및 임원진용 정책 하나)을 사용하려는 경우 정책을 만들고 할당할 수 있습니다. 사용자에게 정책을 할당하는 경우 전역 정책은 더 이상 해당 사용자에게 적용되지 않습니다.<p> [Microsoft Teams에서 발신자 ID 정책 관리](caller-id-policies.md) |

---

## <a name="security"></a>보안

Teams는 [Microsoft 신뢰할 수 있는 컴퓨팅 SDL(보안 개발 수명 주기)](https://www.microsoft.com/sdl/default.aspx)에 따라 설계 및 개발되었습니다. SDL을 준수하기 위해, Teams는 업계 표준 보안 기술을 아키텍처의 기본적인 부분으로 통합하며, 다음을 포함합니다.

- 이후 테스트되는 위협 모델 및 기능 설계
- 보안 관련 개선 사항을 코딩 프로세스 및 사례에 통합
- 제품에 코드가 체크인되기 전에 버퍼 오버런 및 기타 잠재적 보안 위협을 감지하는 빌드 시간 도구 만들기

Teams는 "Trustworthy by Design"(디자인을 통한 신뢰 구축) 방법을 따르지만 알 수 없는 모든 보안 위협에 대해 디자인하는 것은 불가능합니다. 따라서 Teams가 어떻게 작동하고 다른 시스템과 어떻게 상호 작용하는지 이해하는 것이 중요합니다. 또한 IP 주소 스푸핑, 서비스 거부 공격, 중간자(man-in-the-middle) 공격 등과 같은 일반적인 위협이 얼마나 자주 일어나는지 파악하여 이러한 공격이 발생할 가능성을 줄일 수 있도록 네트워크 및 Teams 구성을 디자인하는 것도 중요합니다.

Teams에서 디자인에 보안 기본을 통합하는 방법을 이해하고 일반적인 위협에 대해 자세히 알아보려면 [보안 및 Microsoft Teams](teams-security-guide.md)를 참조하세요.

## <a name="compliance"></a>규정 준수

Teams 및 Microsoft 365는 회사 및 사용자가 위치한 곳의 규정 요구 사항을 준수하는 데 도움이 되는 많은 도구를 제공합니다. Teams에서 각 규정 준수 기능을 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

| 기능 | 설명|
|-|-|
| [정보 장벽](information-barriers-in-teams.md)| 개인 또는 그룹이 서로 의사소통하거나 사용자 선택기에서 찾지 못하도록 합니다.|
| [보존 정책](retention-policies.md)| Teams에서 데이터를 보관하는 기간이나 특정 기간 후에 데이터를 제거해야 하는지 여부를 제어할 수 있습니다.|
| [커뮤니케이션 규정 준수](communication-compliance.md)| 불쾌감, 욕설 및 괴롭힘이 포함된 언어, 선정적 이미지, 잔인한 이미지, 중요한 정보 공유를 식별하고 조치를 취하여 의사 소통 위험을 줄이는 데 도움이 됩니다. |
| [통화 및 모임에 대한 정책 기반 레코딩](teams-recording-policy.md)| 나중에 처리, 보존 또는 분석을 위해 통화 및 모임을 자동으로 기록하고 저장해야 하는지 여부를 제어할 수 있습니다.|
| [민감도 레이블](sensitivity-labels.md)| 선택한 개인 정보 옵션을 적용하는 레이블을 만들어 중요한 정보에 대한 액세스를 보호하고 제어하는 데 도움이 됩니다.|
| [데이터 손실 방지](/microsoft-365/compliance/dlp-microsoft-teams?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json&view=o365-worldwide)| 주민등급번호, 신용 카드 번호 등의 특정 정보를 처리하는 방법을 결정하는 규칙을 만들 수 있습니다. 특정 정보가 전송되는 것을 방지하고 조직을 외부로 나가지 못하도록 할 수 있습니다.|
| [eDiscovery](eDiscovery-investigation.md)| 조직이 법적 절차에 의해 수색 요구를 받았을 때 조직의 콘텐츠를 검색하는 데 도움이 됩니다. |
| [법적 보존](legal-hold.md)| 사용자가 삭제한 경우를 포함하여 eDiscovery 조사 중에 정보를 검색할 수 있도록 법적 절차 중에 필요한 경우 조직에서 정보를 보존할 수 있습니다. |
| [콘텐츠 검색](content-search.md)| Exchange, SharePoint Online 및 비즈니스용 OneDrive에 걸쳐 Teams 정보를 쿼리하는 방법을 제공합니다.|
| [Auditing](audit-log-events.md)| 작업을 수행한 사용자, 작업이 수행된 시간, 사용된 IP 주소 등 지정된 작업에 대한 정보를 볼 수 있습니다. 이러한 작업에는 팀 생성 또는 삭제, 채널 생성, Teams에서 설정 변경 등이 포함됩니다.|
| [고객 키](/microsoft-365/compliance/customer-key-tenant-level?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json&view=o365-worldwide)| 제공한 암호화 키를 사용하여 데이터 암호화 정책을 만들 수 있습니다.|

## <a name="clients"></a>클라이언트

Teams를 사용할 준비가 되면 Windows, Mac, Linux PC나Android, iOS 장치에 Teams 클라이언트를 설치할 수 있습니다. <https://teams.microsoft.com/downloads>에서 Teams 클라이언트를 직집 다운로드할 수 있습니다.

Teams를 사용할 모든 사용자는 Teams 라이선스가 있는지 확인하세요. Teams 라이선스 할당에 대한 자세한 내용은 [Teams에 대한 사용자 액세스 관리](user-access.md#using-the-microsoft-365-admin-center)를 참조하세요.

> [!TIP]
> Microsoft Learn에서 [Microsoft Teams 클라이언트 배포](/learn/modules/m365-teams-collab-deploy-clients/) 모듈을 완료하여 Teams 클라이언트 배포를 계획하는 방법에 대한 권장 사항을 확인하세요.

조직에서 Microsoft Endpoint Configuration Manager, 그룹 정책 또는 타사 배포 메커니즘을 사용하여 사용자의 컴퓨터에 소프트웨어를 배포하는 경우 [Microsoft Endpoint Configuration Manager를 사용하여 Microsoft Teams 설치](msi-deployment.md)를 참조하세요.

Teams 클라이언트 배포에 대한 자세한 내용은 [Microsoft Teams 클라이언트 다운로드](get-clients.md)를 참조하세요.

## <a name="training"></a>교육

사용자 및 관리자가 Teams를 사용하도록 교육하는 방법에 대한 자세한 내용은 [Microsoft Teams 교육](training-microsoft-teams-landing-page.md)을 참조하세요.