---
title: 소매 팀 템플릿 사용
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.localizationpriority: high
search.appverid: MET150
description: Teams 관리 센터와 Microsoft Graph에서 소매 팀 템플릿을 관리하고 사용하여 소매 조직을 위한 팀을 빠르고 쉽게 만드는 방법을 알아보세요.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e32430990450fbe72cf80efd5eb960a28e3315a1
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131327"
---
# <a name="use-retail-team-templates"></a>소매 팀 템플릿 사용

## <a name="overview"></a>개요

Microsoft Teams의 팀 템플릿을 사용하면 설정, 채널 및 사전 설치된 앱의 미리 정의된 팀 구조를 제공하여 팀을 빠르고 쉽게 만들 수 있습니다.

소매점의 경우 팀 템플릿은 조직 전체에 일관된 팀을 신속하게 배포하는 데 도움이 되므로 특히 강력할 수 있습니다. 템플릿은 또한 직원이 Teams를 효과적으로 사용하는 방법에 대해 방향을 잡는 데 도움이 됩니다.

Teams에는 소매점 요구 사항에 맞게 특별히 설계된 템플릿이 포함되어 있습니다. 이러한 미리 빌드된 서식 파일을 사용하여 직원들이 커뮤니케이션하고 공동 작업할 수 있는 팀을 빠르게 만들 수 있습니다. 이 게시물에서는 이러한 각 템플릿을 소개하고 사용 방법을 권장합니다.

팀 템플릿을 관리하고 사용하는 방법은 관리자인지 개발자인지에 따라 다릅니다.

|다음과 같은 경우: | 그렇다면 귀하는: |
| ---- | --------- |
| 관리자 또는 IT 전문가 |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| 개발자 | [Microsoft Graph를 사용](#use-team-templates-with-microsoft-graph)하여 팀 템플릿에서 팀을 만듭니다. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 관리 센터에서 팀 템플릿 관리

관리자는 Microsoft Teams 관리 센터에서 팀 템플릿을 관리할 수 있습니다. 여기에서 각 템플릿에 대한 세부 정보를 볼 수 있습니다. 또한 [템플릿 정책을 만들고 할당](templates-policies.md)하여 직원이 [팀 만들기](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)를 위해 Teams에서 보게 될 템플릿을 제어할 수 있습니다.

일반적인 팀 템플릿에 대한 자세한 내용은 [Teams 관리 센터에서 팀 템플릿 시작하기](get-started-with-teams-templates-in-the-admin-console.md)를 참조하세요.

현재 다음과 같은 미리 빌드된 소매 팀 템플릿을 제공합니다. 이를 보려면 Teams 관리 센터의 왼쪽 탐색 메뉴에서 **팀** > **팀 템플릿** 으로 이동하세요.

> [!NOTE]
> 별표(*)는 템플릿이 *Microsoft 365 연결된 템플릿* 임을 나타냅니다. 사용자가 템플릿을 사용하여 팀을 만들면 연결된 SharePoint 템플릿이 사이트 및 팀에 적용됩니다. 페이지, 목록 및 Power Platform 통합과 같은 SharePoint 구성 요소는 자동으로 추가되고 팀의 일반 채널에 탭으로 고정됩니다. 사용자는 Teams 내에서 바로 이러한 페이지와 목록을 편집할 수 있습니다.
>
> SharePoint 템플릿에 대한 자세한 내용은 [SharePoint 사이트 템플릿 적용 및 사용자 지정을 참조하세요](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### <a name="manage-a-store"></a>스토어 관리*

하나의 중앙 집중식 경험을 통해 판매점 직원들을 하나로 묶어 작업을 관리하고, 문서를 공유하며, 고객 문제를 해결합니다. 추가 애플리케이션을 통합하여 시프트 시작 및 종료 프로세스를 간소화합니다.

> [!div class="mx-tdBreakAll"]
>| 서식 파일 유형 |TemplateId | 이 템플릿과 함께 제공되는 속성 |
>| ------------------|-- |----------------------------------------------------- |
>| 스토어 관리| `retailStore` |채널 <ul><li>일반<li>Shift Handoff</li><li>스토어 준비 상태</li><li>학습</li></ul> 앱: <ul><li>승인</li><li>검사</li><li>목록<ul><li>인벤토리 목록</li></ul></li><li>SharePoint Pages<ul><li>Microsoft Store</li></ul></li><li>교대 근무</li><li>Planner 및 할 일별 작업</li><li>Wiki</li></ul>|

### <a name="retail-for-managers"></a>관리자용 소매*

매장 또는 지역에서 공동 작업할 관리자 집합을 위한 팀을 만듭니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대한 팀을 만들고 해당 지역의 모든 매장 관리자와 해당 지역의 지역 관리자를 포함할 수 있습니다.

> [!div class="mx-tdBreakAll"]
>| 서식 파일 유형| TemplateId | 이 템플릿과 함께 제공되는 속성 |
>| ------------------|- |----------------------------------------------------- |
>| 관리자를 위한 소매| `retailManagerCollaboration` |채널 <ul><li>일반<li>작업</li><li>학습</li></ul> 앱: <ul><li>승인</li><li>검사</li><li>SharePoint Pages<ul><li>Microsoft Store</li></ul></li><li>Planner 및 할 일별 작업</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Microsoft Graph에서 팀 템플릿 사용

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

다음은 미리 빌드된 소매 팀 템플릿입니다.

> [!NOTE]
> 별표(*)는 템플릿이 *Microsoft 365 연결된 템플릿* 임을 나타냅니다. 사용자가 템플릿을 사용하여 팀을 만들면 연결된 SharePoint 템플릿이 사이트 및 팀에 적용됩니다. 페이지, 목록 및 Power Platform 통합과 같은 SharePoint 구성 요소는 자동으로 추가되고 팀의 일반 채널에 탭으로 고정됩니다. 사용자는 Teams 내에서 바로 이러한 페이지와 목록을 편집할 수 있습니다.
>
> SharePoint 템플릿에 대한 자세한 내용은 [SharePoint 사이트 템플릿 적용 및 사용자 지정을 참조하세요](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### <a name="manage-a-store"></a>스토어 관리*

이 템플릿을 사용하여 조직의 각 소매점 위치에 대한 팀을 만듭니다.

> [!div class="mx-tdBreakAll"]
>| 서식 파일 유형 | TemplateId | 템플릿 채널 |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| 소매 - <br>Microsoft Store | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| 채널 <ul><li>일반</li><li>Shift Handoff</li><li>스토어 준비 상태</li><li>학습</li></ul>팀 속성 <ul><li>팀 표시 유형이 공개로 설정됨</li></ul> <br>구성원 권한 <ul><li>채널을 만들거나 업데이트하거나 삭제할 수 없습니다. </li><li>앱을 추가하거나 제거할 수 없습니다. </li><li>탭을 만들거나 업데이트하거나 제거할 수 없습니다.</li><li>커넥터를 만들거나 업데이트하거나 제거할 수 없습니다.</li><ul>|

조직에 맞게 Store 서식 파일을 사용자 지정하기 위한 권장 방법:

- 조직의 각 매장 내에 부서가 있는 경우 각 부서에 대해 채널을 추가합니다. 채널을 추가하면 부서 내에서 의사소통과 공동 작업을 용이하게 할 수 있습니다.

- 조직에 내부 웹 사이트(예: SharePoint 사이트)가 있는 경우 해당 웹 사이트를 관련 팀 채널의 탭으로 고정해 보세요.

### <a name="retail-for-managers"></a>관리자용 소매*

이 템플릿을 사용하여 일련의 관리자가 매장 또는 지역에서 공동 작업할 팀을 만듭니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대한 팀을 만들고 해당 지역의 모든 매장 관리자와 해당 지역의 지역 관리자를 포함할 수 있습니다.

> [!div class="mx-tdBreakAll"]
>| 서식 파일 유형 | TemplateId | 템플릿 채널 |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| 소매 - <br>관리자 공동 작업 | `https://graph.microsoft.com/beta/teamsTemplates('retailManagerCollaboration')`| 채널 <ul><li>일반</li><li>작업</li><li>학습</li></ul>팀 속성 <ul><li>비공개로 설정된 팀 표시 유형</li></ul> <br>구성원 권한 <ul><li>채널을 만들고, 업데이트하고, 삭제할 수 있습니다. </li><li>앱을 추가 및 제거할 수 있습니다. </li><li>탭을 만들고, 업데이트하고, 제거할 수 있습니다.</li><li>커넥터를 만들고, 업데이트하고, 제거할 수 있습니다.</li><ul>|

조직에 맞게 관리자 공동 작업 서식 파일을 사용자 지정하기 위한 권장 방법:

- 조직에 관리자와 관련된 SharePoint 사이트와 같은 내부 웹 사이트가 있는 경우 해당 웹 사이트를 관련 팀 채널의 탭으로 고정하는 것이 좋습니다.

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Microsoft Graph에서 팀 템플릿을 사용하는 방법

이러한 템플릿을 사용하려면 요청 본문의 'template@odata.bind' 속성을 'standard'에서 위의 TemplateIds로 변경하세요.  팀 템플릿을 배포하는 방법에 대한 자세한 내용은 [팀 만들기](/graph/api/team-post?view=graph-rest-beta) 방법에 대한 Microsoft Graph 문서를 참조하세요.

> [!NOTE]
> 서식 파일에서 채널은 **일반** 탭 아래에 자동으로 만들어집니다.

### <a name="example-store-template-extension-script"></a>예: Store 서식 파일 확장 스크립트

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```

> [!NOTE]
> Microsoft Graph를 사용하여 Microsoft 365 연결된 템플릿을 사용하여 기존 Microsoft 365 그룹 또는 팀에서 팀을 만드는 경우 연결된 SharePoint 템플릿이 사이트 또는 팀에 자동으로 적용되지 않습니다. 팀을 만든 후 SharePoint 사이트 템플릿을 수동으로 적용해야 합니다. Teams에서 팀으로 이동하여 오른쪽 위 모서리에 있는 **추가 옵션** > **SharePoint에서 열기를** 선택합니다. 그런 다음 **설정** > **사이트 서식 파일 적용을** 선택하고 해당 사이트 템플릿을 선택합니다.

## <a name="related-articles"></a>관련 기사

- [Teams 관리 센터에서 팀 템플릿 시작하기](get-started-with-teams-templates-in-the-admin-console.md)
- [템플릿으로 팀 만들기](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Microsoft Graph를 사용하여 팀 템플릿 시작하기](get-started-with-teams-templates.md)