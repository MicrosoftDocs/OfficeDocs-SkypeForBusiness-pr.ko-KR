---
title: Microsoft 팀을 위한 관리 빠른 시작
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/29/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
localization_priority: Normal
search.appverid: MET150
description: 채택 계획의 2 단계에 대 한 주요 결정 사항 만들기
f1.keywords:
- CSH
ms.custom: Adopt
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8c154a0e3f1366327b37b22531541fde288db2
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780487"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Microsoft 팀을 위한 관리 빠른 시작

다음 활동이 동시에 수행 되며, 주요 팀의 전부 또는 일부를 포함할 수 있습니다. 가장 좋은 방법은 팀의 초기 실험을 완료 한 후 대규모 관리 및 보안 대화를 연기 하는 것입니다. 이렇게 하면 나중에 변경 해야 하는 사항을 단순화할 수 있습니다. 이 단계에서는 몇 가지 결정 해야 할 사항이 있습니다. 이를 성공적으로 수행 하려면 먼저 다음 질문에 답해 보아야 합니다.

- 이전 평가의 관계자가이 제한 된 비즈니스 보 딩에 참여 하는 데 좋은 후보자가 있나요?
- 이 단계의 좋은 사용 사례를 제안 하는 개인 (또는 개인 그룹)이 있나요?  
- 조직의 직원 들이 초기에 대 한 평가를 할 수 있을 만큼의 관심이 있고, 의미 있고 정기적인 피드백이 있으신가요? 

자세한 내용은 팀의 관리 [팀 및](plan-teams-governance.md) [수명 주기 관리 계획](plan-teams-lifecycle.md)을 참고 하세요.

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![결정 지점을 나타내는 아이콘](media/teams-adoption-decision-icon.png)사항이

다음과 같은 결정을 내릴 수 있습니다 (이 단계에서는 이러한 결정 사항은 2 단계에만 적용).

### <a name="decision-1-who-can-create-teams"></a>의사 결정 1: 팀을 만들 수 있는 사람 

이 단계의 목적으로, 핵심 프로젝트 팀 외에도 초기 도입자에 팀을 만들 수 있는 사용자를 제한할 수 있습니다. 이렇게 하면 필요한 경우 초기 사용자가 추가 팀을 만들 수 있습니다. 이 동작을 모니터링 하면 광범위 한 배포에 대 한 주요 정보가 제공 됩니다.

### <a name="decision-2-teams-naming-conventions"></a>의사 결정 2: 팀 명명 규칙 

광범위 한 팀 배포에 대해 몇 가지 명명 규칙을 구현 하 고 중복 이름이 있는지 확인 하는 것이 일반적입니다. 2 단계에서는 초기 프로젝트에 대해서만 수동 명명 규칙을 구현 하는 것이 좋습니다. 이 작업을 수행 하는 가장 좋은 방법은 초기 프로젝트 팀과의 대화형 온 보 딩을 진행 하 고 사용자가 자신의 이름을 선택 하도록 하는 것입니다. 이렇게 하면 직원 들이 자신의 업무에 대해 생각 하는 방법을 알 수 있으며 나중에 더 많은 배율 명명 규칙을 만들 때 매우 중요 합니다. (대화형 온 보 딩의 요소에 대 한 추가 정보는이 가이드의 뒷부분에 표시 됩니다.)

### <a name="decision-3-guest-access"></a>의사 결정 3: 게스트 액세스

프로젝트의 범위 및 유형 및 업계의 특성에 따라 파트너 또는 공급 업체와의 보안 공동 작업을 가능 하 게 하는 것이 테스트 하려는 필수 기능 일 수 있습니다. 적절 한 테 넌 트 컨트롤을 사용 하 여 팀 구현에 게스트를 추가할 수 있는 사용자를 제한할 수 있습니다. 

### <a name="decision-4-approved-apps"></a>의사 결정 4: 승인 된 앱

팀의 가장 좋은 사례는 다른 앱의 통합을 환경에 포함 하는 것입니다. 적어도 기술 팀은 팀 환경에서 첫 번째 파티 및 추천 앱을 사용 하도록 설정 해야 합니다. 조직에서 사용 하는 사용 사례 및 기타 앱에 따라 제어 실험의 일부로 추가 앱을 포함 하도록 선택할 수 있습니다. 

### <a name="decision-5-are-meetings-included-in-your-test"></a>의사 결정 5: 테스트에 모임이 포함 되어 있습니까? 

팀 모임 환경은 고품질 이며, 영상 채팅을 지원 하며, 직원 들을 서로 더 효과적으로 사용할 수 있도록 만듭니다. 기술 팀에 문의 하 여 환경이 간단한 VoIP 모임을 포함할 준비가 되었는지 확인 하세요. 오디오 회의 또는 음성 서비스를 사용 하도록 설정 하는 것은 일반적으로 실험의이 단계에서 제외 됩니다. 그러나이는 주요 프로젝트 팀, 기술 준비, 조직의 다른 음성/모임 서비스 상태에 따라 달라 집니다. 팀 구현에서 더 많은 가치를 얻을 수 있도록 영상 채팅 및 VoIP 모임을 실험에 포함 하는 것이 좋습니다. 

### <a name="decision-6--data-security"></a>의사 결정 6: 데이터 보안

광범위 한 배포를 준비 하기 위해 보안 레이블을 사용 하 여 환경에서 팀 유형을 분류 하도록 선택할 수 있습니다. 이 실험의 목적을 위해 [팀에서 관리 계획](plan-teams-governance.md) 을 참조 하 고 Microsoft 365 또는 Office 365의 팀 데이터에 대 한 기본 보존 정책이 설정 되어 있는지 확인 하는 것이 좋습니다. 이 작업을 완료 하는 데 Office 365 관리자 권한이 필요 하기 때문에이 작업을 기술 팀과 조정 해야 할 수 있습니다.

### <a name="decision-7-length-of-your-experiment"></a>의사 결정 7: 실험의 길이

성공적인 팀 구현은 적절 한 통해 계속 앞서, 초점 및 학습이을 보장 하기 위해 정상 속도로 진행 됩니다. 초기에 충분 한 비즈니스 주기가 완료 되도록 프로젝트의이 단계를 60 days로 설정 하는 것이 좋습니다. 시간이 너무 오래 걸리는 실험을 확장 하면 실패 한 변경 프로그램이 발생할 위험이 높아집니다. 그러나이 시간은 모든 조직에 따라 달라 집니다.  

![다음 단계](media/teams-adoption-next-icon.png) 를 나타내는 아이콘 (다음: [사용 시나리오 정의](teams-adoption-define-usage-scenarios.md) )
