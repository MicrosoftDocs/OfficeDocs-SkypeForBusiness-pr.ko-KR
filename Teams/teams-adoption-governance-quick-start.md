---
title: Microsoft Teams에 대한 거버넌스 빠른 시작
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams 채택 계획의 2단계에서 결정해야 하는 주요 결정을 다루는 빠른 시작입니다.
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd54902e00e984de740b7bbf6d0fd96e37e88aa9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424558"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Microsoft Teams에 대한 거버넌스 빠른 시작

다음 활동은 동시에 발생하며 주요 팀 전체 또는 일부가 관련될 수 있습니다. Teams의 초기 실험을 완료한 후 대규모 거버넌스 및 보안 대화를 연기하는 것이 가장 좋은 모범 사례입니다. 거버넌스 결정이 최종 사용자 환경에 어떤 영향을 줄 수 있으며 나중에 결정해야 하는 결정을 간소화하는 것이 중요합니다. 이 단계에서는 몇 가지 결정을 내릴 필요가 있습니다. 성공적으로 만들기 위해 먼저 다음 질문에 답변해야 합니다.

- 이전 평가의 이해 관계자는 이 제한된 비즈니스 온보더링에 참여하기에 좋은 후보인가요?
- 이 단계에 좋은 사용 사례를 제안한 개별(또는 개인 그룹)이 있나요?  
- 조직의 직원에게서 조기 채택자이자 의미 있고 정기적인 피드백을 제공해야 하나요? 

자세한 내용은 Teams의 거버넌스 계획 및 [Teams의](plan-teams-governance.md) 수명 주기 관리 계획을 [읽어보는 것이 더 많은 경우](plan-teams-lifecycle.md)

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![의사 결정 지점을 보여 주는 아이콘](media/teams-adoption-decision-icon.png)의사 결정

다음 결정을 내릴 수 있습니다(이 시점에서 이러한 결정은 2단계에만 적용됨).

### <a name="decision-1-who-can-create-teams"></a>결정 1: 팀을 만들 수 있는 사용자 

이 단계의 목적을 위해 핵심 프로젝트 팀 외에도 초기 채택자 인구로 팀을 만들 수 있는 사용자로 제한할 수 있습니다. 이렇게 하면 초기 채택자는 필요한 경우 추가 팀을 만들 수 있습니다. 이 동작을 모니터링하면 광범위한 배포에 대한 주요 정보를 제공합니다.

### <a name="decision-2-teams-naming-conventions"></a>의사 결정 2: 팀 이름 규칙 

Teams의 광범위한 배포에 대한 몇 가지 명명 규칙을 구현하고 중복된 이름을 확인하려는 경우일 수 있습니다. 2단계에서는 초기 프로젝트에 대한 수동 이름 규칙만 구현하는 것이 권장됩니다. 이를 위한 모범 사례는 초기 채택자 프로젝트 팀과 대화형 온보드를 수행하고 자신의 이름을 선택할 수 있도록 하는 것입니다. 이렇게 하면 직원이 업무에 대해 어떻게 생각하는지 파악할 수 있으며 나중에 더 큰 규모 이름명 규칙을 만드는 데 필수적입니다. (대화형 온보더의 요소에 대한 추가 정보는 이 가이드의 후반부에 표시됩니다.)

### <a name="decision-3-guest-access"></a>결정 3: 게스트 액세스

프로젝트의 범위 및 유형과 산업 특성에 따라 파트너 또는 공급업체와의 보안 공동 작업을 사용하도록 설정하는 것이 테스트하려는 필수 기능일 수 있습니다. 적절한 테넌트 컨트롤을 사용하여 게스트를 팀에 추가할 수 있는 사용자 수를 제한하고 민감도 레이블을 사용하여 게스트에 열려 있는 팀을 제한할 수 있습니다. 또한 게스트가 MFA(Multi-Factor Authentication) 사용과 같은 조직의 보안 요구 사항을 준수하도록 할 수 있습니다.

### <a name="decision-4-approved-apps"></a>결정 4: 승인된 앱

Teams를 사용하는 가장 좋은 사례에는 다른 앱의 환경 통합이 포함됩니다. 최소한 기술 팀은 Teams 경험에서 첫 번째 파티 및 추천 앱을 사용하도록 설정해야 합니다. 사용 사례 및 조직에서 사용되는 기타 앱에 따라 제어된 실험의 일부로 추가 앱을 포함하기로 선택할 수 있습니다. 타사 앱이 조직의 보안 및 규정 준수 요구 사항을 준수하는지 확인합니다.

### <a name="decision-5-are-meetings-included-in-your-test"></a>결정 5: 테스트에 모임이 포함되어 있나요? 

Teams 모임 환경은 고품질로 지원하고, 비디오 채팅을 지원하며, 직원을 더 효과적으로 모을 수 있도록 합니다. 사용자 환경에 간단한 VoIP 모임을 포함할 준비가 됐는지 기술 팀에 문의합니다. 오디오 회의 또는 음성 서비스를 사용하도록 설정하는 것이 일반적으로 실험의 이 단계에서 제외됩니다. 그러나 이는 핵심 프로젝트 팀, 기술 준비 상태 및 조직의 다른 음성/모임 서비스의 상태에 따라 다를 수 있습니다. 기술 준비에는 회의실 장비, 최종 사용자 장치 및 액세서리 및 네트워크와 같은 것이 포함되어야 합니다. Teams 구현에서 더 많은 가치를 얻기 위해 실험에 비디오 채팅 및 VoIP 모임을 포함하는 것이 좋습니다. 

### <a name="decision-6-content-management-and-structure"></a>의사 결정 6: 콘텐츠 관리 및 구조
Teams는 사용자가 계속해서 레거시 시스템 및 서비스로 다시 전환하도록 요구하는 대신 플랫폼 내에서 종단식으로 작업할 때 가장 잘 작동하며, 사용자가 익숙한 방식과 다른 새로운 작업 방법을 제공합니다. 실험의 일환으로 참가자와 협력하여 Teams 내에서 공동 작업하는 여러 모달 방법을 수용하는 팀 구조와 채널을 고려하고 기존 폴더 및 저장소 구조를 복제하지 않도록 합니다. 또한 레코드 관리 또는 백업 시스템과 같이 지원되는 기존 시스템 외부에 저장된 콘텐츠에 대한 규정 준수 요구 사항을 고려합니다.

### <a name="decision-7--data-security"></a>의사 결정 7: 데이터 보안

광범위한 배포를 준비하기 위해 보안 레이블을 사용하여 사용자 환경에서 팀 유형을 분류할 수 있습니다. 이 실험에서는 [Teams의](plan-teams-governance.md) 거버넌스 계획을 참조하고 Microsoft 365의 Teams 데이터에 대해 기본 보존 정책을 설정하는 것이 좋습니다. 이 작업을 완료하려면 Microsoft 365 관리자 권한이 필요하기 때문에 기술 팀과 이 작업을 조정해야 할 수 있습니다.

### <a name="decision-8-length-of-your-experiment"></a>결정 8: 실험의 길이

성공적인 Teams 구현은 적절한 모멘텀, 포커스 및 학습을 보장하기 위해 정상 속도로 진행됩니다. 초기 채택자들이 충분한 비즈니스 주기를 완료할 수 있도록 프로젝트의 이 단계를 60일로 설정하는 것이 좋습니다. 실험을 너무 길게 확장하면 프로그램이 실패할 위험이 증가합니다. 그러나 이 시간은 모든 조직에 따라 달라집니다.  

![다음 단계를 나타내는 ](media/teams-adoption-next-icon.png) 아이콘: [사용](teams-adoption-define-usage-scenarios.md) 시나리오 정의
