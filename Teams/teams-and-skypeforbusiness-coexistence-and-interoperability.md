---
title: Microsoft 팀 | 업그레이드, 군도 모드, Interop 정책
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 비즈니스용 Skype 및 Microsoft 팀의 공존 옵션 및 비즈니스용 Skype 간 상호 운용성에 대해 자세히 설명 합니다.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ba7ae0613bbab87f09a6c290d191d711d583c24
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237531"
---
![프로젝트 정의 단계를 강조 하 여 여행 다이어그램 업그레이드] (media/upgrade-banner-project-definition.png "프로젝트 정의 단계에 대 한 강조를 사용 하 여 업그레이드 여행 단계")

이 문서는 coalition 및 프로젝트 팀을 만들고 프로젝트에 대 한 범위, 목표, 비전을 정의 하는 과정을 완료 한 후 업그레이드를 위한 프로젝트 정의 단계의 일부입니다. 계속 하기 전에 다음 활동을 완료 했는지 확인 합니다.

- [프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해

조직에서 현재 비즈니스용 Skype를 사용 하 고 있거나 팀으로 업그레이드 하기 시작 하는 경우, 두 응용 프로그램이 공존 하는 방법, 상호 운용 되는 경우 및 방법, 관리 방법에 대해 이해 하는 것이 중요 합니다. 사용자의 마이그레이션-비즈니스용 Skype에서 팀으로의 최종 업그레이드에 대 한 모든 방법입니다.

> [!Tip]
> [공존 및 상호 운용성](https://aka.ms/teams-upgrade-coexistence-interop)에 대해 알아보려면 다음 세션을 시청 하세요.
>
> 또한 업그레이드 계획 및 구현을 시작 하도록 설계 된 지침, 모범 사례 및 리소스를 공유 하는 실시간 대화형 워크샵에 대해 저희에 게 참가할 수 있습니다.
>
> 먼저 [업그레이드 세션 계획](https://aka.ms/SkypeToTeamsPlanning) 에 참가 하 여 시작 하세요.

## <a name="coexistence-of-teams-and-skype-for-business"></a>팀과 비즈니스용 Skype의 공존

공동 작업 기능 외에도 팀은 채팅, 통화 및 모임 기능을 제공 합니다. 팀 배포를 선택 하는 방법에 따라 이러한 접근 권한 값이 지정 된 사용자에 대해 비즈니스용 Skype에서 제공 하는 기능과 중복 될 수 있습니다. 기본 모드는 기능이 겹치는 비즈니스용 Skype와 함께 팀을 실행 하는 것입니다. 그러나 사용자는 해당 사용자에 대해 이러한 기능이 중복 되지 않도록 설계 된 여러 공존 모드 중 하나를 할당할 수 있습니다 (예를 들어, 팀과 비즈니스용 Skype의 상호 운용성을 사용할 수 있는 경우).

조직에 적합 한 경로를 결정 하는 데 도움이 되도록 아래에서 설명 하는 공존 모드를 검토 하는 것이 좋습니다.

> [!Important]
> 새로운 비즈니스 혜택을 제공 하는 한편, 사용자에 게 방해가 될 수 있는 기존 비즈니스용 Skype 환경에 대 한 새 기술 소개 또는 변경 하기 이 문서에 설명 된 변경 내용을 구현 하기 전에 사용자의 준비를 평가 하 고 커뮤니케이션 및 교육 계획을 구현 하는 시간을 찍습니다. 또한 조직에서이를 구현 하기 전에 선택한 사용자 그룹을 사용 하 여 계획을 파일럿 하도록 권장 합니다.

### <a name="islands-mode"></a>아일랜드 모드

기본적으로 사용자는 현재 상태, 채팅, 통화, 모임 등 유사 하 고 겹치는 기능을 제공 하는 두 개의 별도 솔루션으로 팀을 비즈니스용 Skype와 함께 실행할 수 있습니다. 팀 사용자는 또한 팀과 채널, Office 365의 파일에 대 한 액세스, 응용 프로그램 등의 새로운 공동 작업 기능을 활용할 수 있습니다.

**아일랜드**라는이 공존 모드에서는 각 클라이언트 응용 프로그램이 별도의 아일랜드로 작동 합니다. 비즈니스용 skype는 비즈니스용 Skype와 통신 하 고 팀에 게 통신 합니다. 사용자는 항상 두 클라이언트를 모두 실행 하 고 통신이 시작 된 클라이언트에서 기본적으로 통신할 수 있습니다. 따라서 **아일랜드** 모드에서는 상호 운영성이 필요 하지 않습니다.

비즈니스용 Skype 환경, 외부 (연합) 통신, PSTN 음성 서비스 및 음성 응용 프로그램, 사무실 통합, 기타 여러 통합이 비즈니스용 Skype에서 계속 해 서 처리 되는 것을 방지 합니다.

> [!Important]
> **아일랜드** 모드에서는 페더레이션 사용자 (조직 외부의 사용자)가 비즈니스용 Skype로 배달 됩니다. **팀 전용** 모드로 전환한 후에는 조직 외부의 모든 메시지가 팀에 게 전달 됩니다.

> [!Tip]
> 비즈니스용 Skype Online 고객 추천 경로는 기본 **제도** 모드를 시작 하 여 조직의 팀에서 채도를 채택 하 고 **팀 전용** 모드로 빠르게 전환 하는 것입니다. 온-프레미스 및 하이브리드 고객은 **팀 공동 작업** 모드를 사용 하는 비즈니스를 아일랜드이 아닌 시작 점으로 배포 하 고 **팀 공동 작업 및 모임 모드를 통해 비즈니스용 skype** 에 이르기까지 진행 하는 데 도움이 될 수 있습니다. 해당 하는 경우 조직에서 팀을 채택할 준비가 되 면 **팀 전용** 모드로 전환 합니다.

### <a name="skype-for-business-only"></a>비즈니스용 Skype 전용

이 공존 모드에서는 사용자가 비즈니스용 Skype (예, 채팅, 모임, 통화 기능)를 유지 하 고 팀과 채널에 팀을 사용 하지 않습니다. 이 모드는 오늘 사용할 수 있습니다. 그러나 현재 구현에서 팀과 채널은 사용자에 대해 자동으로 해제 되지 않습니다. 이는 팀과 채널을 숨기기 위해 앱 사용 권한 정책을 사용 하 여 달성할 수 있습니다.

### <a name="teams-only"></a>팀만

**팀 전용** 사용자 ( *업그레이드* 된 사용자 라고도 함)는 팀의 모든 기능에 액세스할 수 있습니다. 업그레이드 되지 않은 사용자나 외부 사용자가 구성한 비즈니스용 Skype에서 비즈니스용 skype 클라이언트를 유지 하 여 모임에 참가할 수 있습니다. 업그레이드 된 사용자는 팀과 비즈니스용 Skype 간의 상호 운용성 기능을 사용 하 여 비즈니스용 Skype를 계속 사용 중인 조직의 다른 사용자와 통신할 수 있습니다 (비즈니스용 Skype 사용자가 아일랜드 모드에 있지 않은 경우). ; 그러나 업그레이드 된 사용자는 비즈니스용 Skype 채팅, 통화 또는 모임을 시작할 수 없습니다.

조직에서 일부 또는 모든 사용자가 팀을 유일한 통신 및 공동 작업 도구로 사용할 준비가 되는 즉시 해당 사용자를 **팀 전용** 모드로 업그레이드할 수 있습니다. 아일랜드 모드에서 업그레이드 하는 경우 업그레이드 프로세스를 시작 하기 전에 조직 전체에서 팀을 처음부터 다시 채택 하는 것이 좋습니다. 이렇게 하면 상호 운용성을 제공 하지 않는 아일랜드 모드 때문에 통신 시나리오가 중단 되지 않습니다.

팀 전용 모드로 전환 하는 방법에 대 한 추가 고려 사항은 [팀 전용 모드 고려 사항](teams-only-mode-considerations.md)을 참조 하세요.

![팀 확인 메시지 스크린샷] (media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "사용자가 팀 전용 사용자로 업그레이드 한 후 특별 한 모드로 실행 되는 비즈니스용 Skype 클라이언트")

### <a name="skype-for-business-with-teams-collaboration"></a>팀 공동 작업을 통한 비즈니스용 Skype

이 모드를 사용 하 여 비즈니스용 Skype에서 기존 투자를 계속 활용 하면서 팀을 환경에 도입할 수 있습니다. 이 모드에서는 채팅, 통화 및 모임 기능을 위해 비즈니스용 Skype를 변경 하지 않고 팀 공동 작업 기능 (팀 및 채널, Office 365의 파일에 대 한 액세스 및 응용 프로그램)을 추가할 수 있습니다. 팀 통신 기능-비공개 채팅, 통화, 모임 예약 등은이 모드에서 기본적으로 해제 되어 있습니다. 온-프레미스 또는 하이브리드 비즈니스 서버의 비즈니스용 Skype를 사용 하는 조직은 사용자의 통신에 대 한 상호 운용성 및 예측 가능성을 제공 하려는 경우이 모드를 아일랜드 모드의 대 안으로 고려해 야 합니다.

### <a name="skype-for-business-with-teams-collaboration-and-meetings"></a>팀 공동 작업 및 모임이 있는 비즈니스용 Skype

이 공존 모드를 사용 하 여 공동 작업 기능 외에도 사용자가 상위 팀 모임 경험을 활용할 수 있도록 하는 조직의 팀 모임 접근 권한 값을 높일 수 있습니다. 이동이 잦은 장치 및 브라우저를 포함 하 여 모든 플랫폼에서의 고급 사용자 환경과 기록, 번역 또는 배경 흐림 등 혁신적인 기능.

이 모드에서 팀과 채널 기반 대화에 팀을 사용 하는 것과 함께 사용자는 팀을 사용 하 여 모임을 예약 하 고 수행 합니다. 개인 채팅 및 통화는 비즈니스용 Skype에 남아 있습니다. 팀과 비즈니스용 Skype는 현재 상태 조정, 자동 보존/유지 중단, 두 응용 프로그램 간의 HID 장치 지원과 같은 "더 나은" 기능 범위에서 혜택을 누릴 수 있습니다. 

이 공존 모드는 enterprise voice를 사용 하는 비즈니스용 Skype 온-프레미스 배포의 사용자에 게 특히, 팀으로 업그레이드 하는 데 시간이 오래 걸리거나 상위 팀 모임에서 가능한 한 빨리 혜택을 받을 수 있도록 하는 데 유용 합니다.

> [!Note]
> 특정 공존 모드로 배포 하는 경우, 팀과 비즈니스용 Skype를 [](#interoperability-of-teams-and-skype-for-business)함께 사용 하 여 다른 사용자 들과 채팅 하 고 동시에 통화할 수 있으며, 팀에 대 한 업그레이드를 여행 하는 동안 조직 내에서 의사 소통을 지속적으로 유지 합니다. 공존 모드는 상호 운용성을 제어 합니다. 수신기의 공존 모드는 상호 운용성을 사용할 수 있는지 여부를 결정 합니다. 예를 들어, 수신기가 한 대의 클라이언트 (예: 팀) 에서만 사용할 수 있는 모드인 경우 개시자가 다른 클라이언트 (이 경우 비즈니스용 Skype)를 사용 하 여 채팅을 시작 하는 경우에는 일반적으로 채팅 상호 운용성을 사용할 수 있습니다. 반면, 수신기가 두 클라이언트 (섬 모드)에서 채팅을 사용할 수 있는 모드인 경우에는 채팅에 상호 운용성을 제공 하지 않습니다. 초기자가 채팅을 시작한 클라이언트의 받는 사람에 게 메시지가 수신 됩니다. 따라서 아일랜드 모드의 적절 한 의사 소통에는 팀 채택을 포화 해야 합니다. 즉, 모든 사용자가 두 클라이언트를 활발 하 게 사용 하 고 모니터링 합니다.

> [!TIP]
> 비즈니스용 Skype를 사용 하는 동안 팀에서 사용 하려는 기능을 기반으로 권장 되는 업그레이드 모드를 식별 하는 데 도움이 되도록 [skype To 팀 업그레이드 마법사](https://aka.ms/SkypeToTeamsWizard)를 이용해 보세요.

공존 모드, 필수 구성 요소 및 관리에 대 한 자세한 내용은 [비즈니스용 Skype로 팀을 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](https://aka.ms/SkypeToTeams-Interop) 을 참조 하 고 [공존 및 업그레이드 설정을 설정](https://aka.ms/SkypeToTeams-SetCoexistence)합니다.

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|판단 요점|<ul><li>조직의 요구 사항에 가장 적합 한 공존 모드 (들)</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|다음 단계|<ul><li>업그레이드 여행에 가장 적합 한 방법을 선택 합니다.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>팀 및 비즈니스용 Skype의 상호 운용성

상호 운용성은 팀과 비즈니스용 Skype를 통해 같은 조직에 있는 비즈니스용 Skype 사용자가 통신 하는 기능입니다.

### <a name="native-interop-and-interop-escalation"></a>네이티브 interop 및 interop 에스컬레이션

Interop 환경에는 네이티브 및 interop 에스컬레이션 이라는 두 가지 유형이 있습니다.

- _기본 interop_ 환경은 사용자가 현재 사용 중인 클라이언트에서 발생 합니다. 한 명의 사용자가 비즈니스용 Skype 클라이언트, 그리고 팀에서 진행 됩니다. 기본 interop 환경은 다른 클라이언트에 게 통신 하는 것이 아니라 사용자가 현재 사용 중인 클라이언트에서 대화를 수행할 수 있습니다. 기본 interop 환경은 일대일 채팅 및 통화입니다.
- _Interop 에스컬레이션_ 환경은 사용자가 고급 작업 (예: 데스크톱 공유)을 수행 하는 데 도움이 되는 것을 의미 하는 것으로, 클라이언트는 사용자가 참가 하 여 해당 모임에서 계속 진행 되는 모임을 만들 수 있습니다. 작업의 개시자 플랫폼에서 모임이 만들어집니다. 해당 플랫폼을 사용 하지 않는 사용자는 모임 참가 링크를 받습니다. 이 링크를 클릭 하면 호환 되는 클라이언트 (브라우저, 웹 앱 또는 전체 클라이언트)의 모임에 참가 합니다. 비즈니스용 Skype에서의 Interop 에스컬레이션에는 최신 클라이언트가 필요 합니다. 팀에서의 Interop 에스컬레이션이 곧 제공 될 예정입니다.

### <a name="native-interop-experiences"></a>기본 interop 환경

위에서 설명한 대로 사용자에 게 할당 된 공존 모드에 따라 다음과 같은 기본 interop 환경을 사용할 수 있습니다.

- 비즈니스용 Skype 사용자는 팀 사용자와 일대일 채팅을 할 수 있으며 그 반대의 경우도 마찬가지입니다. Interop 채팅은 팀 클라우드 서비스의 일부인 interop 게이트웨이를 통과 해야 하며 온라인 으로만 존재 하는 경우에만 가능 합니다. Interop 채팅은 서식 있는 텍스트와 이모티콘을 지원 하지 않는 일반 텍스트입니다. 팀과 비즈니스용 Skype의 사용자에 게 대화가 interop 대화 인지에 대 한 알림이 표시 됩니다.

    ![팀의 Interop 채팅 경험 스크린샷] (media/Interop_chat_experience_from_Teams.png "팀의 Interop 채팅 환경")

- 비즈니스용 Skype 사용자는 팀 사용자에 게 일대일 음성 및 영상 통화를 할 수 있으며 그 반대의 경우도 마찬가지입니다.

    ![팀의 Interop 호출 경험 스크린샷] (media/Interop_calling_experience_from_Teams.png "팀의 Interop 호출 환경")

> [!Important]
> 비즈니스용 Skype 배포의 Interop 환경은 Office 365 비즈니스용 Skype를 사용 하 여 온-프레미스 환경이 하이브리드 모드에 있어야 합니다. 자세한 내용은 [마이그레이션 및 상호 운용성 지침](https://aka.ms/SkypeToTeams-Interop)을 참조 하세요.

이러한 interop 환경은 다음 공존 모드 중 하나를 지정 하는 사용자와 함께 사용할 수 있습니다. **팀 공동 작업**, **팀 공동 작업 및 모임이 있는**비즈니스용 skype, **skype 비즈니스만**또는 **팀만**. 아일랜드 모드에서는 사용자와의 상호 운영성이 없습니다.

### <a name="native-interop-experience-limitations"></a>기본 interop 환경 제한 사항

일부 기능은 업무용 및 비즈니스용 Skype 간의 interop 채팅 및 interop 호출 환경에서 사용할 수 없습니다.

- 마크 다운, 서식 있는 텍스트, 전체 이모티콘 집합은 팀 또는 비즈니스용 Skype에서 지원 되지 않습니다. 팀 대화방의 작성 상자에 있는 기타 기본 기능은 지원 되지 않습니다.
- 팀과 비즈니스용 Skype 간의 화면 공유 (데스크톱 또는 앱 공유)는 지원 되지 않습니다.
- 팀의 그룹 채팅 (복수 파티 대화)은 팀을 사용 하는 참가자만 포함할 수 있습니다.
- 비즈니스용 Skype의 여러 파티 메신저 대화 (그룹 채팅)는 비즈니스용 Skype를 사용 하는 참가자만 포함할 수 있습니다.
- 진행 중인 피어 투 피어 음성 또는 영상 통화를 팀과 비즈니스용 Skype 사용자가 모두 포함 된 여러 사람에 게 에스컬레이션 하는 것은 지원 되지 않습니다.
- 2 자리 채팅에 대 한 파일 전송 또는 그룹 채팅의 파일 첨부, 팀에서 비즈니스용 Skype로 또는 그 반대의 경우는 지원 되지 않습니다.
- 비즈니스용 Skype 영구 채팅에는 상호 운영성이 없습니다.

영구 채팅을 제외한 이러한 모든 제한 사항에 대 한 해결 방법 중 하나는 한 명의 사용자가 모임을 시작 하 고 다른 사용자를 참가 하도록 초대 하는 것입니다. 이 해결 방법은 interop 에스컬레이션의 기반입니다.

이 문서를 검토 한 후에는 [업그레이드 여행 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [마이그레이션 및 상호 운용성 가이드](https://aka.ms/SkypeToTeams-Interop), 비즈니스용 [Skype와 함께 공존](coexistence-chat-calls-presence.md), 구현에 대 한 [공존 및 업그레이드 설정 설정](https://aka.ms/SkypeToTeams-SetCoexistence) 등을 참조 하세요. 세부적인.

## <a name="related-links"></a>관련 링크

[비디오: SfB 및 팀 간의 공존 및 상호 운용성 관리](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
