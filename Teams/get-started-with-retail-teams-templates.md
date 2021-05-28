---
title: 소매에서 팀 템플릿 시작
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
description: 팀 템플릿을 사용하여 미리 정의된 설정, 채널 및 미리 설치된 앱을 제공하여 소매업체 요구에 따라 디자인된 팀 구조를 만드는 방법을 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edc3b646af4577199b13a5803837625b8a9ea354
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684556"
---
# <a name="create-a-team-using-retail-team-templates"></a>소매 팀 템플릿을 사용하여 팀 만들기

Microsoft 팀 템플릿을 사용하면 설정, 채널 및 미리 설치된 앱의 미리 정의된 템플릿을 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.

팀 템플릿에는 소매업체 요구 사항을 중심으로 디자인된 팀 구조에 대한 미리 작성된 정의가 있습니다. 팀 템플릿을 사용하여 소매업체에 잘 작동하고 조직 전체에 배포하는 팀 유형을 빠르게 만들 수 있습니다. 팀 템플릿을 확장하여 특정 조직 요구에 맞게 팀을 만들 수도 있습니다.

이 문서에서는 각 팀 템플릿을 소개하고 이를 사용하는 방법을 권장합니다.

이 문서는 판매점 조직 전체에 걸쳐 여러 Teams를 계획, 배포 및 관리하는 업무를 담당하는 사용자를 위한 것입니다. 귀사는 이미 Teams 서비스를 구축했습니다. Teams를 아직 배포하지 않은 경우 먼저 [Microsoft Teams를 배포하는 방법](./deploy-overview.md)을 읽어보세요.

일반적으로 팀 템플릿에 대한 자세한 내용은 팀 템플릿 시작 을 [참조합니다.](get-started-with-teams-templates.md)

| Who | 사용 방법: |
| ---- | --------- |
| 관리자 및 IT 전문가 | [관리 Teams](#use-the-team-templates-in-the-teams-admin-center) 관리 센터를 사용하여 소매 팀 템플릿을 기반으로 팀을 만듭니다.|
| 개발자 및 시스템 통합자 | [Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) 팀 템플릿을 기반으로 팀을 만듭니다. |

## <a name="use-the-team-templates-in-the-teams-admin-center"></a>관리 센터에서 팀 Teams 사용

### <a name="organize-a-store"></a>스토어 구성

하나의 중앙 집중식 경험을 통해 판매점 직원들을 하나로 묶어 작업을 관리하고, 문서를 공유하며, 고객 문제를 해결합니다. 추가 애플리케이션을 통합하여 교대 근무 시작 및 종료 프로세스를 효율화할 수 있습니다.

| 기본 서식 파일 형식 |baseTemplateId | 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------|-- |----------------------------------------------------- |
|스토어 구성|`retailStore`|채널 <ul><li>일반<li>교대 근무 전달</li><li>학습</li></ul> 앱: <ul><li>Wiki</li></ul>|
||||

### <a name="manager-collaboration"></a>관리자 공동 작업

관리자 공동 작업 템플릿은 관리자 집합이 상점/지역 등에서 공동 작업할 수 있는 팀을 만드는 데 이상적입니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대한 관리자 공동 작업 팀을 만들고 해당 지역에 대한 지역 관리자와 함께 해당 지역에 있는 모든 저장소 관리자를 포함할 수 있습니다.

| 기본 서식 파일 형식| baseTemplateId | 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------|- |----------------------------------------------------- |
|소매 - 관리자 공동 작업|`retailManagerCollaboration` |채널 <ul><li>일반<li>작업</li><li>학습</li></ul> 앱: <ul><li>Wiki</li></ul>|
||||

## <a name="use-the-team-templates-with-the-microsoft-graph"></a>Microsoft 사용자와 함께 팀 템플릿을 Graph

### <a name="store-template"></a>Store 서식 파일

Store 서식 파일은 개별 판매점 위치를 대표하기 위해 팀을 만드는 경우에 이상적입니다. Store 서식 파일을 사용하여 조직의 각 판매점 위치별로 팀을 만들 수 있습니다.

| 기본 서식 파일 형식 | baseTemplateId | 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 소매 - <br>Microsoft Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| 채널 <ul><li>교대 근무 전달\*</li><li>Learning\*</li></ul>\*자동 즐겨찾기 채널<br><br>팀 속성 <ul><li>팀 표시 유형이 공개로 설정됨</li></ul> <br>구성원 권한 <ul><li>채널을 생성/업데이트/삭제할 수 없음 </li><li>앱을 추가/제거할 수 없음 </li><li>탭을 생성/업데이트/제거할 수 없음</li><li>커넥터를 생성/업데이트/제거할 수 없음</li><ul>|
||||

조직에 맞게 Store 서식 파일을 사용자 지정하기 위한 권장 방법:

- 조직의 각 매장 내에 부서가 있는 경우 각 부서에 대해 채널을 추가합니다. 채널을 추가하면 부서 내에서 의사소통과 공동 작업을 용이하게 할 수 있습니다.

- 조직에 내부 웹 사이트(예: SharePoint 사이트)가 있는 경우 해당 웹 사이트를 관련 팀 채널의 탭으로 고정해 보세요. 지침은 팀 [템플릿](get-started-with-teams-templates.md) 시작을 참조하세요.

### <a name="manager-collaboration-template"></a>관리자 공동 작업 서식 파일

Manager 공동 작업 템플릿은 소매업체 요구 사항을 중심으로 디자인된 팀 템플릿 중 하나입니다. 관리자 공동 작업 서식 파일은 매장/지역 등에서 공동 작업할 관리자 집합을 위한 팀을 만드는 데 이상적입니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대한 관리자 공동 작업 팀을 생성하고 해당 지역의 모든 스토어 매니저와 해당 지역의 지역 관리자를 포함할 수 있습니다.

| 기본 서식 파일 형식 | baseTemplateId | 이 기본 서식 파일과 함께 사용할 수 있는 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| 소매 - <br>Microsoft Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| 채널 <ul><li>작업\*</li><li>Learning\*</li></ul>\*자동 즐겨찾기 채널<br><br>팀 속성 <ul><li>비공개로 설정된 팀 표시 유형</li></ul> <br>구성원 권한 <ul><li>채널을 생성/업데이트/삭제할 수 없음 </li><li>앱을 추가/제거할 수 있음 </li><li>탭을 생성/업데이트/제거</li><li>커넥터 생성/업데이트/제거</li><ul>|
||||

조직에 맞게 관리자 공동 작업 서식 파일을 사용자 지정하기 위한 권장 방법:

- 조직에 관리자와 관련된 SharePoint 사이트와 같은 내부 웹 사이트가 있는 경우 해당 웹 사이트를 관련 팀 채널의 탭으로 고정하는 것이 좋습니다. 지침은 Microsoft 팀 템플릿 설명서를 [살펴](get-started-with-teams-templates.md) 볼 수 있습니다.

## <a name="how-to-use-first-party-templates"></a>기본 서식 파일을 사용하는 방법

이러한 서식 파일을 사용하려면 요청 본문의 'template@odata.bind' 속성을 '표준'에서 위의 TemplateID로 변경하세요.  팀 템플릿을 배포하는 방법에 대한 자세한 내용은 팀을 만드는 Graph Microsoft Graph [문서를 참조하세요.](/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> 서식 파일에서 채널은 일반 탭 아래에 자동으로 만들어집니다.

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
