---
title: EDU 관리자용 Microsoft Teams 정책 패키지
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1.keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 정책 패키지를 사용 하 고 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 922481747e83b8885641185b8a7e4fa65bb2a1bd
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708664"
---
# <a name="microsoft-teams-policy-packages-for-edu-admins"></a>EDU 관리자용 Microsoft Teams 정책 패키지

Microsoft 팀의 정책 패키지는 기관에서 유사한 역할을 갖는 사용자에 게 할당할 수 있는 미리 정의 된 정책 및 정책 설정을 수집 합니다. 정책 패키지는 정책을 관리할 때 일관성을 단순화 하 고 효율적으로 지원 합니다. 일반적인 연습에서는 각 사용자에 게 정책 패키지를 할당 하 고 필요에 따라 각 패키지의 정책을 다시 정의 하 여 해당 사용자 그룹의 요구에 맞게 만듭니다. 패키지의 설정을 업데이트 하면 해당 패키지에 할당 된 모든 사용자가 대량 업데이트로 변경 됩니다.

일반적으로 교육 기관에는 학생의 연령 및 성숙도에 따라 고유한 요구 사항으로 많은 사용자 유형이 있습니다. 예를 들어 강사와 직원에 게 Microsoft 팀에 대 한 전체 액세스 권한을 부여할 수 있지만, 학생을 위해 Microsoft 팀의 기능을 제한 하 여 안전 하 고 중요 한 학습 환경을 장려 하는 것이 좋습니다. 정책 패키지를 사용 하 여 학교 커뮤니티에서 다른 cohorts의 요구 사항에 따라 설정을 조정할 수 있습니다.

## <a name="what-is-a-policy-package"></a>정책 패키지 란?

정책 패키지를 통해 Microsoft 팀이 조직의 특정 사용자 집합에 대해 사용 하도록 허용 하거나 제한할 수 있는 Microsoft 팀 기능을 제어할 수 있습니다. 각 정책 패키지는 사용자 역할을 중심으로 설계 되며, 해당 역할에 대 한 일반적인 활동을 지 원하는 미리 정의 된 정책 및 정책 설정이 포함 되어 있습니다.

정책 패키지 미리 정의할 정책:
- 메시징
- 모임
- 앱 설정
- 전화
- 라이브 이벤트

Microsoft 팀에는 현재 다음 정책 패키지가 포함 되어 있습니다.

|Microsoft 팀 관리 센터에 나열 된 패키지 이름 |사용 용도  |설명 |
|:--- |:--- |:--- |
|Education_Teacher| 교사 및 스태프| 이 정책 및 정책 설정 집합을 사용 하 여 조직 내 강사와 직원에 게 Microsoft 팀을 통해 채팅, 통화, 모임에 대 한 모든 액세스 권한을 부여 합니다. |
|Education_PrimaryStudent | 기본 학교 오래 된 학생  | 귀하의 기관 내에 있는 기본 학교 오래 된 학생이 Microsoft 팀 내에서 더 많은 제한을 필요로 할 수 있습니다. 이 정책 및 정책 설정 집합을 사용 하 여 모임 만들기 및 관리, 채팅 관리, 비공개 통화와 같은 기능을 제한할 수 있습니다. |
|Education_SecondaryStudent| 보조 학교 오래 된 학생 | 귀하의 기관 내에 있는 2 차 학교 오래 된 학생이 Microsoft 팀 내에서 더 많은 제한을 필요로 할 수 있습니다. 이 정책 및 정책 설정 집합을 사용 하 여 모임 만들기 및 관리, 채팅 관리, 비공개 통화와 같은 기능을 제한할 수 있습니다. |
|Education_HigherEducationStudent | 높은 교육 학생 | Intuition 내에서 교육 학생 수가 높을수록 더 적은 수의 학생이 필요 하지 않지만 몇 가지 제한 사항이 있을 수 있습니다. 이 정책 및 정책 설정 집합을 사용 하 여 조직 내에서 채팅, 통화, 모임에 대 한 액세스 권한을 부여할 수 있지만 학생 들이 외부 참가자와 Microsoft 팀을 사용 하는 방법은 제한 합니다. |
|||

정책 패키지에 연결 된 정책을 쉽게 식별할 수 있도록 각 개별 정책에 정책 패키지의 이름이 지정 됩니다. 예를 들어 학교에 Education_Teacher 정책 패키지를 할당 하면 패키지의 각 정책에 대해 Education_Teacher 이라는 정책이 만들어집니다.

![Education_Teacher 정책 패키지 스크린샷](media/policy-packages-education_teacher.png)

> [!NOTE]
> 교사와 관리 지원 담당자에 게 다른 정책이 필요 하다 고 판단 되는 경우 기존 패키지를 사용할 수 있습니다. 현재 사용 하지 않는 패키지를 식별 하 고 해당 그룹에 맞게 설정을 변경 합니다. 어떤 그룹에 어떤 패키지가 있는지 자신에 게 기록해 야 할 수 있지만,이는 패키지를 재활용 하는 유일한 장애입니다.

## <a name="why-use-policy-packages"></a>정책 패키지를 사용 하는 이유

기관에 수백 개 또는 수천 명의 사용자가 있는 경우 "특정 패키지를 할당 하는 이유는 무엇 인가요? 그리고 모든 사용자에 게 다른 권한이 있는 경우" 라는 메시지가 표시 될 수 있습니다.

수백 명의 사용자에 게 패키지를 할당 하는 것은 관리 시간에 아무런 문제 없이 투자 하는 것입니다. 투자에 대 한 중요 한 점은 시간이 지남에 따라 즉각적이 지는 것이 아니라 시간을 지불 하는 것입니다.

교육 환경에는 같은 역할이 나 비슷한 역할을 갖는 사용자가 많습니다. 사용자 환경을 관리 하는 것과 동일한 방식으로 시간에 따른 노력을 줄일 수 있습니다. 패키지 그룹은 기관에 있는 다양 한 역할과 관련 된 정책 집합을 그룹화 합니다. 동일한 라이선스가 있지만 역할이 서로 다른 사용자는 해당 역할을 기준으로 하는 관련 정책을 할당할 수 있으며,이는 개별 사용자의 조정 정책 보다 더 효율적입니다.

기관에 있는 모든 사용자를 그룹으로 정렬 하 고 패키지를 적용 한 후에는 패키지에 할당 된 모든 사용자에 대해 패키지 설정을 한 번만 변경 하면 됩니다. 패키지에 사용자를 할당 하기 전이나 후에 패키지 내에서 정책을 미세 조정 하도록 선택할 수 있습니다.

단일 사용자 지정 패키지, 최대 20 명의 사용자에 게 패키지 할당, 각 패키지에 연결 된 정책 관리 및 업데이트에 대 한 단계별 지침은 [Microsoft 팀에서 정책 패키지 관리](manage-policy-packages.md) 를 참조 하세요.
