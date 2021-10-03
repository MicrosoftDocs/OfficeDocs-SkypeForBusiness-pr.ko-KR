---
title: 소매 팀 템플릿 사용
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
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
ms.openlocfilehash: f3cf6d2e7eb23517477572775e7d18571463957b
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046344"
---
# <a name="use-retail-team-templates"></a>소매 팀 템플릿 사용

Microsoft Teams의 팀 템플릿을 사용하면 설정, 채널 및 사전 설치된 앱의 미리 정의된 팀 구조를 제공하여 팀을 빠르고 쉽게 만들 수 있습니다.

소매점의 경우 팀 템플릿은 조직 전체에 일관된 팀을 신속하게 배포하는 데 도움이 되므로 특히 강력할 수 있습니다. 템플릿은 또한 직원이 Teams를 효과적으로 사용하는 방법에 대해 방향을 잡는 데 도움이 됩니다.

Teams에는 소매점 요구 사항에 맞게 특별히 설계된 템플릿이 포함되어 있습니다. 이러한 미리 빌드된 서식 파일을 사용하여 직원들이 커뮤니케이션하고 공동 작업할 수 있는 팀을 빠르게 만들 수 있습니다. 이 게시물에서는 이러한 각 템플릿을 소개하고 사용 방법을 권장합니다.

팀 템플릿을 관리하고 사용하는 방법은 관리자인지 개발자인지에 따라 다릅니다.

|다음과 같은 경우: | 그렇다면 귀하는: |
| ---- | --------- |
| 관리자 또는 IT 전문가 |[Teams 관리자 센터에서 팀 템플릿을 관리합니다](#manage-team-templates-in-the-teams-admin-center). 팀 템플릿을 보고 템플릿 정책을 적용하여 직원이 팀을 만들기 위해 Teams에서 사용할 수 있는 템플릿을 제어합니다. |
| 개발자 | [Microsoft Graph를 사용](#use-team-templates-with-microsoft-graph)하여 팀 템플릿에서 팀을 만듭니다. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 관리 센터에서 팀 템플릿 관리

관리자는 Microsoft Teams 관리 센터에서 팀 템플릿을 관리할 수 있습니다. 여기에서 각 템플릿에 대한 세부 정보를 볼 수 있습니다. 또한 [템플릿 정책을 만들고 할당](templates-policies.md)하여 직원이 [팀 만들기](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)를 위해 Teams에서 보게 될 템플릿을 제어할 수 있습니다.

일반적인 팀 템플릿에 대한 자세한 내용은 [Teams 관리 센터에서 팀 템플릿 시작하기](get-started-with-teams-templates-in-the-admin-console.md)를 참조하세요.

현재 다음과 같은 미리 빌드된 소매 팀 템플릿을 제공합니다. 이를 보려면 Teams 관리 센터의 왼쪽 탐색 메뉴에서 **팀** > **팀 템플릿** 으로 이동하세요.

### <a name="organize-a-store"></a>매장 구성

하나의 중앙 집중식 경험을 통해 판매점 직원들을 하나로 묶어 작업을 관리하고, 문서를 공유하며, 고객 문제를 해결합니다. 추가 앱을 통합하여 교대 근무 시작 및 종료 프로세스를 간소화합니다.

| 서식 파일 유형 |TemplateId | 이 템플릿과 함께 제공되는 속성 |
| ------------------|-- |----------------------------------------------------- |
|스토어 구성| `retailStore` |채널 <ul><li>일반<li>교대 근무 전달</li><li>매장 준비 상태<ul><li>검사&sup1;</li></ul></li><li>학습</li></ul> 앱: <ul><li>Wiki</li><li>작업</li><li>교대 근무</li><li>검사</li></ul>|

&sup1;앱이 탭으로 채널에 추가되었습니다.

### <a name="manager-collaboration"></a>관리자 공동 작업

관리자 공동 작업 서식 파일은 관리자 집합이 여러 매장/지역 등에서 협업할 팀을 만드는 데 이상적입니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대한 관리자 공동 작업 팀을 생성하고 해당 지역의 모든 스토어 매니저와 해당 지역의 지역 관리자를 포함할 수 있습니다.

| 서식 파일 유형| TemplateId | 이 템플릿과 함께 제공되는 속성 |
| ------------------|- |----------------------------------------------------- |
|관리자용 소매|`retailManagerCollaboration` |채널 <ul><li>일반<li>작업<ul><li>작업(운영 작업)&sup1;</li><li>검사&sup1;</li></ul></li><li>학습<ul><li>작업(학습 작업)&sup1;</li></ul></li></ul> 앱: <ul><li>Wiki</li><li>작업</li><li>검사</li></ul>|
||||

&sup1;앱이 탭으로 채널에 추가되었습니다.

## <a name="use-team-templates-with-microsoft-graph"></a>Microsoft Graph에서 팀 템플릿 사용

개발자는 Microsoft Graph를 사용해 미리 작성된 팀 템플릿을 사용해 팀을 만들 수 있습니다. Microsoft Graph에서 팀 템플릿을 사용하는 방법에 관한 자세한 내용은 [Microsoft Graph를 사용하여 팀 템플릿 시작하기](get-started-with-teams-templates.md), [Microsoft Teams API 개요](/graph/teams-concept-overview?view=graph-rest-1.0) 및 [teamsTemplate 리소스 유형](/graph/api/resources/teamstemplate?view=graph-rest-1.0)을 참조하세요.

다음은 미리 빌드된 소매 팀 템플릿입니다.

### <a name="store"></a>스토어

Store 서식 파일은 개별 판매점 위치를 대표하기 위해 팀을 만드는 경우에 이상적입니다. Store 서식 파일을 사용하여 조직의 각 판매점 위치별로 팀을 만들 수 있습니다.

| 서식 파일 유형 | TemplateId | 템플릿 채널 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 소매 - <br>Microsoft Store | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| 채널 <ul><li>일반</li><li>교대 근무 핸드오프&sup2;</li><li>매장 준비 상태</li><li>학습&sup2;</li></ul>팀 속성 <ul><li>팀 표시 유형이 공개로 설정됨</li></ul> <br>구성원 권한 <ul><li>채널을 만들거나 업데이트하거나 삭제할 수 없습니다. </li><li>앱을 추가하거나 제거할 수 없습니다. </li><li>탭을 만들거나 업데이트하거나 제거할 수 없습니다.</li><li>커넥터를 만들거나 업데이트하거나 제거할 수 없습니다.</li><ul>|
||||

&sup2;자동 즐겨찾기 채널

조직에 맞게 Store 서식 파일을 사용자 지정하기 위한 권장 방법:

- 조직의 각 매장 내에 부서가 있는 경우 각 부서에 대해 채널을 추가합니다. 채널을 추가하면 부서 내에서 의사소통과 공동 작업을 용이하게 할 수 있습니다.

- 조직에 내부 웹 사이트(예: SharePoint 사이트)가 있는 경우 해당 웹 사이트를 관련 팀 채널의 탭으로 고정해 보세요.

### <a name="manager-collaboration"></a>관리자 공동 작업

관리자 공동 작업 서식 파일은 관리자 집합이 여러 매장/지역 등에서 협업할 팀을 만드는 데 이상적입니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대한 관리자 공동 작업 팀을 생성하고 해당 지역의 모든 스토어 매니저와 해당 지역의 지역 관리자를 포함할 수 있습니다.

| 서식 파일 유형 | TemplateId | 템플릿 채널 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 소매 - <br>Microsoft Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| 채널 <ul><li>일반</li><li>작업&sup2;</li><li>학습&sup2;</li></ul>팀 속성 <ul><li>비공개로 설정된 팀 표시 유형</li></ul> <br>구성원 권한 <ul><li>채널을 만들고, 업데이트하고, 삭제할 수 있습니다. </li><li>앱을 추가 및 제거할 수 있습니다. </li><li>탭을 만들고, 업데이트하고, 제거할 수 있습니다.</li><li>커넥터를 만들고, 업데이트하고, 제거할 수 있습니다.</li><ul>|
||||

&sup2;자동 즐겨찾기 채널

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

## <a name="related-articles"></a>관련 기사

- [Teams 관리 센터에서 팀 템플릿 시작하기](get-started-with-teams-templates-in-the-admin-console.md)
- [템플릿으로 팀 만들기](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Microsoft Graph를 사용하여 팀 템플릿 시작하기](get-started-with-teams-templates.md)