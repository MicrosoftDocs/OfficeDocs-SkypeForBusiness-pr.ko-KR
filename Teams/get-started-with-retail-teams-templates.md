---
title: 소매에서 Teams 서식 파일 시작
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 미리 정의한 설정, 채널 및 미리 설치된 앱을 제공하여 소매점 요구를 위해 설계된 팀 구조를 만들기 위해 Teams 서식 파일을 사용하는 방법을 배워 하세요.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424638"
---
# <a name="get-started-with-teams-templates-in-retail"></a>소매에서 Teams 서식 파일 시작

Teams 서식 파일을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 서식 파일을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.

Teams 템플릿에는 소매점 요구 사항을 중심으로 설계된 팀 구조에 대한 미리 작성된 정의가 있습니다. Teams 서식 파일을 사용하여 소매점에 잘 작동하고 조직 전체에 배포하는 팀 유형을 빠르게 만들 수 있습니다. Teams 서식 파일을 확장하여 특정 조직 요구에 맞는 팀을 만들 수도 있습니다.

이 문서에서는 각 Teams 서식 파일을 소개하고 이를 사용하는 방법을 권장합니다.

이 문서는 소매 조직 전체에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다. 조직에 Teams 서비스를 이미 배포했습니다. 아직 Teams를 출시하지 않은 경우 먼저 Microsoft Teams를 롤아웃하는 [방법을 읽어 읽습니다.](How-to-roll-out-teams.md)

일반적으로 팀 서식 파일에 대한 자세한 내용은 Teams 서식 파일 [시작을 참조합니다.](get-started-with-teams-templates.md)

## <a name="store-template"></a>스토어 템플릿

스토어 템플릿은 개별 소매점 위치를 나타내는 팀을 만드는 데 이상적입니다. 스토어 템플릿을 사용하여 조직의 각 소매점 위치에 대한 팀을 만들 수 있습니다.

| 기본 템플릿 형식 | baseTemplateId | 이 기본 템플릿과 함께 사용할 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 소매 - <br>스토어 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| 채널 <ul><li>교대 근무 유인\*</li><li>학습\*</li></ul>\*자동 즐겨찾기 채널<br><br>팀 속성 <ul><li>팀 가시성을 공개로 설정</li></ul> <br>멤버 권한 <ul><li>채널을 만들/업데이트/삭제할 수 없습니다. </li><li>앱을 추가/제거할 수 없습니다. </li><li>탭을 만들/업데이트/제거할 수 없습니다.</li><li>커넥터를 만들/업데이트/제거할 수 없습니다.</li><ul>|
||||

조직의 스토어 템플릿을 사용자 지정하는 권장 방법:

- 조직에 각 저장소 내에 부서가 있는 경우 각 부서에 대한 채널을 추가합니다. 채널을 추가하면 부서 내에서 통신 및 공동 작업을 용이하게 할 수 있습니다.

- 조직에 내부 웹 사이트(예: SharePoint 사이트)가 있는 경우 관련 팀 채널의 탭으로 고정하는 것이 좋습니다. 지침은 Teams 서식 파일 [시작을](get-started-with-teams-templates.md) 참조하세요.

## <a name="manager-collaboration-template"></a>관리자 공동 작업 템플릿

관리자 공동 작업 템플릿은 소매점 요구 사항을 중심으로 디자인된 Teams 템플릿 중 하나입니다. 관리자 공동 작업 템플릿은 매장/지역 등에서 공동 작업할 관리자 집합에 대한 팀을 만드는 데 이상적입니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대한 관리자 공동 작업 팀을 만들고 해당 지역의 모든 스토어 관리자와 해당 지역의 지역 관리자를 포함할 수 있습니다.

| 기본 템플릿 형식 | baseTemplateId | 이 기본 템플릿과 함께 사용할 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 소매 - <br>스토어 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| 채널 <ul><li>운영\*</li><li>학습\*</li></ul>\*자동 즐겨찾기 채널<br><br>팀 속성 <ul><li>팀 가시성을 비공개로 설정</li></ul> <br>멤버 권한 <ul><li>채널을 만들/업데이트/삭제할 수 있습니다. </li><li>앱을 추가/제거할 수 있습니다. </li><li>탭을 만들/업데이트/제거할 수 있습니다.</li><li>커넥터를 만들/업데이트/제거할 수 있습니다.</li><ul>|
||||

조직의 관리자 공동 작업 템플릿을 사용자 지정하는 권장 방법:

- 조직에 관리자와 관련된 SharePoint 사이트와 같은 내부 웹 사이트가 있는 경우 관련 팀 채널의 탭으로 고정하는 것이 좋습니다. 지침은 Microsoft Teams 서식 파일 [설명서를 참조하세요.](get-started-with-teams-templates.md)

## <a name="how-to-use-first-party-templates"></a>첫 번째 파티 서식 파일을 사용하는 방법

이러한 템플릿을 사용 설정하기 위해 요청 본문의 'template@odata.bind' 속성을 'standard'에서 위의 TemplateID로 변경합니다.  Teams 템플릿을 배포하는 방법에 대한 자세한 내용은 팀을 만드는 방법에 대한 Microsoft Graph [문서를 참조하세요.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> 템플릿의 채널은 일반 탭 아래에 자동으로 만들어집니다.

### <a name="example-store-template-extension-script"></a>예: 템플릿 확장 스크립트 저장

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
## <a name="relate-topic"></a>관련 항목

[관리 센터에서 Teams 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)
