---
title: Microsoft Teams에서 조직의 작업 앱 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
audience: admin
description: 조직의 사용자에 대한 작업 앱을 관리하는 방법을 배워야 합니다.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2cc477b9589aeebb8dcd486e7f85ca04daf6ff4d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909402"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>Microsoft Teams에서 조직의 작업 앱 관리

## <a name="overview-of-tasks"></a>작업 개요

작업 앱은 Microsoft Teams에 통합된 작업 관리 환경을 [제공하며, Microsoft To Do에서](https://todo.microsoft.com/tasks/) 제공한 개별 작업과 Planner가 제공한 팀 작업을 한 곳으로 통합합니다. 사용자는 Teams의 왼쪽에 있는 앱으로, 개별 팀 내의 채널에서 탭으로 작업에 액세스할 수 있습니다. **작업의 내 작업** 및 **공유 계획을** 통해 사용자는 모든 개별 및 팀 작업을 보고 관리하고 작업의 우선 순위를 지정할 수 있습니다. 작업은 Teams 데스크톱, 웹 및 모바일 클라이언트에서 사용할 수 있습니다. 

> [!NOTE]
> Teams 데스크톱 클라이언트에서 작업 환경을 롤아웃하면 앱 이름이 처음에 **Planner로** 사용자에게 표시됩니다. 그러면 이름이 Planner 및 **To Do에** 의해 작업으로 일시적으로 변경된 후 나중에 작업으로 이름이 **변경됩니다.** Teams 모바일 클라이언트에서 사용자는 항상 앱 이름을 작업으로 **볼 수 있습니다.** 데스크톱 환경을 사용할 수 있는 후에 모바일 환경의 가용성이 잠시 지연될 수 있습니다.

   ![Teams 목록의 작업 목록 보기 스크린샷](media/manage-tasks-app-tasks.png)

일선 작업자에 대한 작업 관리를 간소화하려는 조직의 경우 작업에는 Frontline Workforce 전체에서 대규모 작업을 대상으로 지정, 게시 및 추적할 수 있는 기능도 포함됩니다. 예를 들어 기업 및 지역 리더십은 특정 소매점과 같은 관련 위치를 대상으로 하는 작업 목록을 만들고 게시하고 실시간 보고서를 통해 진행률을 추적할 수 있습니다. 관리자는 직원에게 작업을 할당하고 해당 위치 내에서 직접 작업을 할당할 수 있으며, 일선 직원은 모바일 또는 데스크톱에서 할당된 작업의 우선 순위 목록을 제공합니다. 작업 [게시를](#task-publishing)사용하려면 먼저 계층 구조의 모든 팀이 서로 관련되는 방법을 정의하는 조직에 대한 팀 대상 계층 구조를 설정해야 합니다.

## <a name="what-you-need-to-know-about-tasks"></a>작업에 대해 알아야 할 작업

작업은 앱 및 채널의 탭으로 사용할 수 있습니다. 앱은 To Do의 개별 작업과 Planner의 팀 작업으로 구성되는 반면 탭에는 팀 작업만 표시됩니다.

작업을 통해 사용자는 데스크톱, 웹 및 모바일 환경을 얻을 수 있습니다. Teams 데스크톱 클라이언트에 작업이 설치된 경우 사용자는 Teams 웹 및 모바일 클라이언트에서도 해당 작업을 볼 수 있습니다. 게스트 사용자만 예외입니다. 게스트가 Teams 모바일 클라이언트에서 앱으로 작업만 액세스할 수 있습니다. 게스트는 Teams 데스크톱 및 웹 클라이언트 모두에 작업 탭을 볼 수 있습니다.

**내 작업에는** 사용자의 개별 작업이 표시됩니다. **공유 계획은** 전체 팀이 작업하는 작업을 표시하고 채널에 작업 탭으로 추가된 모든 작업 목록을 포함합니다. 다음에 유의합니다.

- 작업 앱에서 사용자가 만든 작업 목록은 해당 사용자의 To Do 클라이언트에도 표시됩니다. 마찬가지로, 할 일에서 사용자가 만든 작업 목록은 해당 사용자의 작업에서 **내** 작업에 표시됩니다. 개별 작업에도 마찬가지입니다.

- 채널에 추가된 모든 작업 탭은 Planner 클라이언트에도 표시됩니다. 사용자가 Planner에서 계획을 만드는 경우 계획이 채널에 탭으로 추가되지 않는 한 작업 또는 Planner 앱에 계획이 표시되지 않습니다. 사용자가 새 작업 탭을 추가하면 새 목록을 만들거나 계획을 세우거나 기존 작업 탭을 선택할 수 있습니다.

## <a name="set-up-tasks"></a>작업 설정

> [!IMPORTANT]
> Planner에 대해 구성한 설정 및 정책도 작업에 적용됩니다.

### <a name="enable-or-disable-tasks-in-your-organization"></a>조직에서 작업 사용 또는 사용 안 하도록 설정

작업은 조직의 모든 Teams 사용자에 대해 기본적으로 사용하도록 설정됩니다. Microsoft Teams 관리 센터의 앱 관리 페이지에서 구성 [](manage-apps.md) 수준에서 앱을 끄거나 끄면 됩니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Teams 앱 **관리**  >  **앱으로 이동하세요.**
2. 앱 목록에서 다음 중 하나를 실행합니다.

    - 조직의 작업을 해제하려면 작업 앱을 검색하고 선택한 다음 차단을 **클릭합니다.**
    - 조직에 대한 작업을 켜려면 작업 앱을 검색하고 선택한 다음 허용을 **클릭합니다.**

> [!NOTE]
> 작업 앱을 찾을 수 없는 경우 이 문서의 첫 번째 메모에서 이름을 검색합니다. 앱이 여전히 이름을 다시 정하는 중일 수 있습니다.

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>조직의 특정 사용자에 대한 작업 사용 또는 사용 안 하도록 설정

조직의 특정 사용자가 작업을 사용할 수 있도록 허용하거나 차단하려면 앱 관리 [](manage-apps.md) 페이지에서 조직에 대해 작업이 켜져 있는지 확인한 다음 사용자 지정 앱 사용 권한 정책을 만들고 해당 사용자에게 할당합니다. 자세한 내용은 [Teams에서 앱 사용 권한 정책 관리를 참조하세요.](teams-app-permission-policies.md)

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>앱 설정 정책을 사용하여 Teams에 작업 고정

앱 설정 정책을 사용하면 Teams를 사용자 지정하여 조직의 사용자에게 가장 중요한 앱을 강조할 수 있습니다. 정책에서 설정한 앱은 Teams 데스크톱 클라이언트의 측면 및 사용자가 빠르고 쉽게 액세스할 수 있는 Teams 모바일 클라이언트의 아래쪽에 있는 앱 표시줄에 &mdash; &mdash; 고정됩니다.

사용자에 대한 작업 앱을 고정하려면 전역(전체 기본) 정책을 편집하거나 사용자 지정 앱 설정 정책을 만들고 할당할 수 있습니다. 자세한 내용은 [Teams에서 앱 설정 정책 관리를 참조하세요.](teams-app-setup-policies.md)

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>사용자가 Exchange Online에 대한 라이선스를 받은 경우 사용자의 내 작업이 표시됩니다.

사용자가 내 작업을 보지 못하게 하려는 경우 숨길 수 있습니다.  이렇게하려면 [사용자의 Exchange Online 라이선스를 제거합니다.](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) Exchange Online 라이선스를 제거한 후 사용자는 더 이상 사서함에 액세스할 수 없음을 알아야 합니다.  사서함 데이터는 30일 동안 유지되고, 그 이후에는 데이터가 제거되고 사서함이 원본 위치 유지 또는 소송 보류에 배치되지 않는 한 복구할 [수 없습니다.](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

정보 근로자는 이를 권장하지 않지만 전자 메일에 의존하지 않는 일선 작업자의 경우와 같이 일부 시나리오가 적용될 수 있습니다.

## <a name="task-publishing"></a>작업 게시

작업 게시를 통해 조직은 조직 전체의 특정 위치(팀)를 대상으로 하는 작업 목록을 게시하여 해당 위치에서 완료할 작업 계획을 정의하고 공유할 수 있습니다.

- 회사 또는 지역 리더와 같은 게시 팀의 사람들은 작업 목록을 만들고 특정 팀에 게시할 수 있습니다.<br>
    ![작업 게시 스크린샷](media/manage-tasks-app-publish.png)
- 받는 사람 팀의 관리자는 게시된 작업 목록을 검토하고 팀 구성원에게 개별 작업을 할당할 수 있습니다.<br>
    ![작업 할당 스크린샷](media/manage-tasks-app-assign.png)
- 일선 작업자는 작업에 배정된 작업을 볼 수 있는 간단한 모바일 환경을 제공합니다. 사진을 첨부하여 적절한 경우 작업을 표시하고 작업을 완료로 표시하면 됩니다.
- 게시자와 관리자는 보고서를 보고 위치(팀), 작업 목록 및 개별 작업을 포함하여 각 수준에서 작업의 할당 및 완료 상태를 볼 수 있습니다.<br>
    ![모바일에서 할당된 작업의 스크린샷](media/manage-tasks-app-reporting.png)

사용자는 작업 앱의 게시된 목록  탭에서 작업 목록을 만들고 관리하고 게시합니다. 이 탭은 조직에서 계층 [](#set-up-your-team-targeting-hierarchy) 구조를 대상으로 하는 팀을 설정하고 사용자가 계층 구조에 포함된 팀에 있는 경우 사용자에게만 표시됩니다. 계층 구조는 사용자가 작업 목록을 게시하거나 받을 수 있는지 여부를 결정하고 수신된 목록에 대한 보고를 볼 수 있습니다.

### <a name="example-scenario"></a>예제 시나리오

작업 게시의 작동 방식에 대한 예제는 다음과 같습니다.

Contoso는 새로운 음식 인출 및 배달 프로모션을 출시하고 있습니다. 일관된 브랜드 환경을 유지하려면 300개 이상의 저장소 위치에서 일관된 롤아웃 실행을 조정해야 합니다.

마케팅 팀은 프로모션 세부 정보 및 해당 작업 목록을 Retail Communications Manager와 공유합니다. 매장에 대한 게이트키퍼 역할을 하는 Retail Communications Manager는 정보를 검토하고, 프로모션을 위한 작업 목록을 만든 다음, 영향을 받는 각 매장에서 수행해야 하는 작업 단위에 대한 작업을 만듭니다. 작업 목록이 완료되면 작업을 완료해야 하는 저장소를 선택해야 합니다. 이 경우 프로모션은 매장 내 식당이 있는 미국 내 매장에만 적용됩니다. 작업에서 매장 내 식당 특성을 기준으로 스토어 목록을 필터하고, 계층 구조에서 일치하는 미국 위치를 선택한 다음, 해당 매장에 작업 목록을 게시합니다.

각 위치에 있는 저장소 관리자는 게시된 작업의 복사본을 받고 해당 작업을 팀 구성원에게 할당합니다. 관리자는 작업 환경을 사용하여 스토어에서 필요한 모든 작업을 이해할 수 있습니다. 또한 사용 가능한 필터를 사용하여 기한이 오늘인 작업이나 특정 지역에서 작업하는 등 특정 작업 집합에 집중할 수도 있습니다.

이제 각 매장 위치의 일선 작업자가 모바일 장치의 작업에서 작업의 우선 순위 목록이 지정됩니다. 작업을 마치면 완료로 표시됩니다. 작업의 작업을 표시하기 위해 사진을 업로드하고 작업에 첨부할 수도 있습니다.

Contoso 본사 및 중간 관리자는 보고를 보고하여 각 매장 및 매장에서 작업의 배정 및 완료 상태를 확인할 수 있습니다. 또한 특정 작업으로 드릴다운하여 다른 저장소 내의 상태를 볼 수도 있습니다. 출시 날짜가 가까워질수록 모든 이상을 확인하고 필요한 경우 팀에 체크 인할 수 있습니다. 이러한 가시성을 통해 Contoso는 롤아웃의 효율성을 개선하고 매장에서 보다 일관된 환경을 제공할 수 있습니다.

### <a name="set-up-your-team-targeting-hierarchy"></a>팀 대상 계층 구조 설정

조직에서 작업 게시를 사용하도록 설정하려면 먼저 에서 팀 대상을 지정하는 팀을 설정해야 합니다. CSV 파일. 이마트는 계층 구조의 모든 팀이 서로 관련되는 방식과 팀을 필터링하고 선택하는 데 사용되는 특성을 정의합니다. 스마마를 만든 후 Teams에 업로드하여 조직에 적용합니다. 그런 다음 예제 시나리오의 Retail Communications Manager와 같은 게시 팀의 구성원은 계층 구조, 특성 또는 둘의 조합을 통해 팀을 필터링하여 작업 목록을 수신해야 하는 관련 팀을 선택한 다음 해당 팀에 작업 목록을 게시할 수 있습니다.

팀 대상 계층 구조를 설정하는 방법에 대한 단계는 팀 대상 계층 구조 [설정을 참조하세요.](set-up-your-team-hierarchy.md)

## <a name="power-automate-and-graph-api"></a>Power Automate 및 Graph API

작업은 Planner용 Power Automate for To Do 및 Graph API를 지원합니다. 자세한 내용은 다음을 참조하세요.

- [Planner 작업 및 계획 API 개요](https://docs.microsoft.com/graph/planner-concept-overview)
- [Power Automate에서 Microsoft To Do 사용](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
