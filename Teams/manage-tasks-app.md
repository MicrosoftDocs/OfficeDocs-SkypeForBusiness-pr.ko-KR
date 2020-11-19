---
title: Microsoft 팀에서 조직의 작업 앱 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
audience: admin
description: 조직의 사용자에 대 한 작업 앱을 관리 하는 방법을 알아봅니다.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.openlocfilehash: 18af74a2a62f8282ee9b39c998db803235cc4ff0
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130499"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>Microsoft 팀에서 조직의 작업 앱 관리

## <a name="overview-of-tasks"></a>작업 개요

Tasks 앱은 microsoft 팀에 게 긴밀 한 작업 관리 경험을 제공 하 여 Microsoft가 제공 하는 개별 작업과 Planner에서 제공 [하](https://todo.microsoft.com/tasks/) 는 팀 작업을 한 곳에 통합 합니다. 사용자는 팀의 왼쪽에 있는 앱으로 작업에 액세스 하 고 개별 팀 내에서 채널의 탭으로 액세스할 수 있습니다. 작업의 **내 작업** 및 **공유 계획** 을 통해 사용자가 모든 개인 및 팀 작업을 보고 관리 하 고 작업의 우선 순위를 정할 수 있습니다. 작업은 팀 데스크톱, 웹, 모바일 클라이언트에서 사용할 수 있습니다. 

> [!NOTE]
> 팀 데스크톱 클라이언트에 작업 환경을 배포 하면 앱 이름이 처음에는 사용자에 게 **Planner** 로 표시 됩니다. 그러면 이름이 **Planner에 의해 작업** 으로 일시적으로 변경 되 고, 나중에 **는 작업으로 이름이 바뀝니다.** 팀 모바일 클라이언트에서는 사용자가 항상 앱 이름을 **작업** 으로 보게 됩니다. 데스크톱 경험을 사용할 수 있게 되 면 모바일 환경의 가용성에 약간의 시간이 걸릴 수 있습니다.

   ![팀 목록에 있는 작업 목록 보기 스크린샷](media/manage-tasks-app-tasks.png)

Firstline Worker에 대 한 작업 관리를 합리화 하려는 조직의 경우 작업에는 Firstline 인적 자원에 걸친 작업을 대상으로 하 고, 게시 하 고, 추적할 수 있는 접근 권한 값도 포함 되어 있습니다. 예를 들어 회사 및 지역 리더십은 특정 소매점과 같은 관련 위치를 대상으로 하는 작업 목록을 만들고 게시 하 고 실시간 보고서를 통해 진행 상황을 추적할 수 있습니다. 관리자는 직원에 게 작업을 할당 하 고 해당 위치 내에서 활동을 직접 수행할 수 있으며, Firstline Worker에는 할당 된 작업에 대 한 우선 순위가 높은 목록이 휴대폰 또는 데스크톱에 표시 됩니다. [작업 게시](#task-publishing)기능을 사용 하도록 설정 하려면 먼저 조직의 팀 대상 계층을 설정 하 여 계층 구조의 모든 팀이 서로 어떻게 관련 되는지 정의 해야 합니다.

## <a name="what-you-need-to-know-about-tasks"></a>작업에 대해 알아야 할 사항

작업은 앱 이나 채널의 탭으로 사용할 수 있습니다. 앱은 Planner에서 할 일 및 팀 작업의 개별 작업을 구성 하는 반면, 탭에는 팀 작업만 표시 됩니다.

작업을 통해 사용자는 데스크톱, 웹, 모바일 환경을 이용할 수 있습니다. 팀 데스크톱 클라이언트에 작업을 설치 하는 경우 사용자는 팀 웹 및 모바일 클라이언트 에서도이를 볼 수 있습니다. 게스트 사용자는 예외입니다. 게스트는 팀 모바일 클라이언트의 앱 으로만 작업에 액세스할 수 있다는 것을 알아야 합니다. 게스트에는 팀 데스크톱 및 웹 클라이언트의 작업 탭이 표시 됩니다.

**내 작업** 에는 사용자의 개별 작업이 표시 됩니다. **공유 계획** 은 팀 전체가 작업 중인 작업을 표시 하 고, 채널에 작업 탭으로 추가 된 모든 작업 목록을 포함 합니다. 다음 사항에 유의 하세요.

- 사용자가 작업에서 만든 작업 목록도 해당 사용자를 위해 클라이언트에 게 표시 됩니다. 마찬가지로 사용자가 수행 하기 위해 만드는 작업 목록이 해당 사용자의 작업에서 **내 작업** 에 표시 됩니다. 개별 작업의 경우에도 마찬가지입니다.

- 채널에 추가 된 모든 작업 탭이 Planner 클라이언트에도 표시 됩니다. 사용자가 Planner에서 계획을 만들 때 해당 계획이 작업 또는 Planner 앱에 표시 되지 않는 경우 채널에 탭으로 추가 됩니다. 사용자가 새 작업 탭을 추가 하면 새 목록 또는 계획을 만들거나 기존 항목을 선택할 수 있습니다.

## <a name="set-up-tasks"></a>작업 설정

> [!IMPORTANT]
> Planner에 대해 구성한 설정 및 정책이 작업에도 적용 됩니다.

### <a name="enable-or-disable-tasks-in-your-organization"></a>조직의 작업 설정 또는 해제

작업은 조직의 모든 팀 사용자에 대해 기본적으로 사용 하도록 설정 됩니다. Microsoft 팀 관리 센터에서 [앱 관리](manage-apps.md) 페이지의 조직 수준에서 앱을 끄거나 켤 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** 으로  >  **앱 관리** 로 이동 합니다.
2. 앱 목록에서 다음 중 하나를 수행 합니다.

    - 조직에 대 한 작업을 해제 하려면 작업 앱을 검색 하 고 선택한 다음 **차단을** 클릭 합니다.
    - 조직에 대 한 작업을 설정 하려면 작업 앱을 검색 하 여 선택한 다음 **허용** 을 클릭 합니다.

> [!NOTE]
> 작업 앱을 찾을 수 없는 경우이 문서의 첫 번째 노트에서 이름을 검색 합니다. 이 앱은 여전히 이름을 바꾸는 동안에도 발생할 수 있습니다.

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>조직의 특정 사용자에 대 한 작업 사용 또는 사용 안 함

조직의 특정 사용자가 작업을 사용 하지 못하도록 허용 하거나 차단 하려면 [앱 관리](manage-apps.md) 페이지에서 조직에 대 한 작업이 설정 되어 있는지 확인 한 다음 사용자 지정 앱 사용 권한 정책을 만들어 해당 사용자에 게 할당 합니다. 자세히 알아보려면 [팀에서 앱 권한 정책 관리](teams-app-permission-policies.md)를 참조 하세요.

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>앱 설치 정책을 사용 하 여 팀에 작업 고정

앱 설정 정책은 팀을 사용자 지정 하 여 조직의 사용자에 게 가장 중요 한 앱을 강조 표시할 수 있습니다. 정책에서 설정한 앱은 &mdash; 팀 데스크톱 클라이언트의 측면에 있는 표시줄과 팀 모바일 클라이언트의 맨 아래에 &mdash; 사용자가 빠르고 쉽게 액세스할 수 있습니다.

사용자를 위해 작업 앱을 고정 하려면 전역 (조직 차원의 기본) 정책을 편집 하거나 사용자 지정 앱 설정 정책을 만들고 할당할 수 있습니다. 자세히 알아보려면 [팀에서 앱 설정 정책 관리](teams-app-setup-policies.md)를 참조 하세요.

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>사용자가 Exchange Online에 대 한 사용이 허가 된 경우 사용자의 내 작업이 표시 됨

사용자에 게 **내 작업** 을 표시 하지 않으려면 숨길 수 있습니다. 이렇게 하려면 [사용자의 Exchange Online 라이선스를 제거](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)합니다. Exchange Online 라이선스를 제거한 후에는 사용자가 더 이상 해당 사서함에 액세스할 수 없다는 것을 알아야 합니다.  사서함 데이터는 30 일간 보유 되며, 그 이후에는 사서함이 원본 [위치 유지 또는 소송 유지](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)에 배치 되지 않은 경우에는 데이터를 제거 하 고 복구할 수 없게 됩니다.

정보 근로자에 게는이 방법을 권장 하지 않지만, 전자 메일을 이용 하지 않는 Firstline Worker 등의 몇 가지 시나리오가 적용 될 수 있습니다.

## <a name="task-publishing"></a>작업 게시

조직에서는 작업 게시를 사용 하 여 조직에서 특정 위치 (팀)를 대상으로 하는 작업 목록을 게시 하 여 작업 계획을 정의 및 공유 하 고 해당 위치에서 완료할 수 있습니다.

- 회사나 지역 리더십 등의 게시 팀 구성원은 작업 목록을 만들어 특정 팀에 게 게시할 수 있습니다.<br>
    ![작업 게시 스크린샷](media/manage-tasks-app-publish.png)
- 받는 사람 팀의 관리자는 게시 된 작업 목록을 검토 하 고 개별 작업을 팀 구성원에 게 할당할 수 있습니다.<br>
    ![작업 지정 스크린샷](media/manage-tasks-app-assign.png)
- Firstline Worker는 자신에 게 할당 된 작업을 볼 수 있는 간단한 모바일 환경을 제공 합니다. 사진을 첨부 하 여 적절 한 작업을 표시 하 고 작업을 완료로 표시할 수 있습니다.
- 게시자 및 관리자가 보고서를 보고 각 수준에서 위치 (팀), 작업 목록, 개별 작업 등의 작업에 대 한 과제 및 완료 상태를 확인할 수 있습니다.<br>
    ![모바일에서 할당 된 작업 스크린샷](media/manage-tasks-app-reporting.png)

사용자는 작업 앱의 **게시 된 목록** 탭에서 작업 목록을 만들고, 관리 하 고, 게시할 수 있습니다. 이 탭은 조직에서 [팀 대상 계층 구조를 설정](#set-up-your-team-targeting-hierarchy) 하 고 사용자가 계층 구조에 포함 된 팀을 사용 하는 경우에만 사용자에 게 표시 됩니다. 계층 구조는 사용자가 작업 목록을 게시 하거나 수신 하 고 받은 목록에 대 한 보고를 볼 수 있는지 여부를 결정 합니다.

### <a name="example-scenario"></a>예제 시나리오

다음은 작업 게시가 작동 하는 방식에 대 한 예입니다.

Contoso는 새로운 음식 takeout 배달 상태 올리기를 진행 중입니다. 일관 된 브랜드 환경을 유지 하기 위해서는 300 스토어 위치에서 출시의 일관성 있는 실행을 조정 해야 합니다.

마케팅 팀은 소매 통신 관리자를 사용 하 여 홍보 정보 및 해당 작업 목록을 공유 합니다. 매장 용 게이트 키퍼 역할을 하는 소매 통신 관리자는 정보를 검토 하 고, 홍보에 대 한 작업 목록을 만든 다음, 영향을 받는 각 상점에서 수행 해야 하는 각 작업 단위에 대해 작업을 만듭니다. 작업 목록이 완성 되 면 작업을 완료 해야 하는 상점을 선택 해야 합니다. 이 경우 홍보는 매장 내 식당의 미국에 있는 매장에만 적용 됩니다. 작업에서 매장 내 식당 특성을 기준으로 스토어 목록을 필터링 하 고 계층 구조에서 일치 하는 미국 위치를 선택한 다음 해당 저장소에 작업 목록을 게시 합니다.

각 위치의 저장소 관리자는 게시 된 작업의 복사본을 받고 해당 작업을 팀 구성원에 게 할당 합니다. 관리자는 작업 환경을 사용 하 여 스토어에서 필요한 모든 작업을 이해할 수 있습니다. 또한 사용 가능한 필터를 사용 하 여 특정 작업 집합 (예: 오늘 작업 기한 또는 특정 영역에서 작업)에 집중할 수 있습니다.

이제 각 매장 위치의 firstline 근로자는 해당 모바일 장치에서 작업에 대 한 우선 순위가 지정 된 목록을 표시 합니다. 작업이 완료 되 면 완료 된 것으로 표시 됩니다. 일부 경우에는 작업에 사진을 업로드 하 고 첨부 하 여 작업을 표시할 수도 있습니다.

Contoso 본부와 중급 관리자는 보고를 보고 각 저장소와 상점에서 작업의 과제 및 완료 상태를 확인할 수 있습니다. 또한 특정 작업을 드릴 다운 하 여 다른 저장소 내의 상태를 확인할 수도 있습니다. 시작 날짜가 가까이 있으면 모든 abnormalities을 검색 하 고 필요에 따라 팀을 확인할 수 있습니다. 이러한 가시성으로 Contoso는 출시의 효율성을 개선 하 고 스토어에서 보다 일관 된 환경을 제공할 수 있습니다.

### <a name="set-up-your-team-targeting-hierarchy"></a>팀 대상 지정 계층 구조 설정

조직에서 작업 게시를 사용 하도록 설정 하려면 먼저에서 팀 대상 지정 스키마를 설정 해야 합니다. CSV 파일 스키마는 계층의 모든 팀과 팀을 필터링 하 고 선택 하는 데 사용 되는 특성을 서로 연결 하는 방법을 정의 합니다. 스키마를 만든 후에는 팀에 업로드 하 여 조직에 적용 합니다. 예제 시나리오의 소매 통신 관리자와 같은 게시 팀의 구성원은 계층, 특성 또는 둘 다의 조합 별로 팀을 필터링 하 여 작업 목록을 받을 관련 팀을 선택한 다음 해당 팀에 작업 목록을 게시할 수 있습니다.

팀 대상 지정 계층을 설정 하는 방법에 대 한 단계는 [팀 대상 지정 계층 설정을](set-up-your-team-hierarchy.md)참조 하세요.

## <a name="power-automate-and-graph-api"></a>파워 자동화 및 그래프 API

작업은 Planner 용 Api를 수행 하 고 그래프에 대 한 고급 자동화를 지원 합니다. 자세히 알아보려면 다음을 참조 하세요.

- [Planner 작업 및 계획 API 개요](https://docs.microsoft.com/graph/planner-concept-overview)
- [Microsoft를 사용 하 여 파워 자동화로 작업](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
