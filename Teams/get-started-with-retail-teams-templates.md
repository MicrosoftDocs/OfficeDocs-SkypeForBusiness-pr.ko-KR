---
title: 정품에서 팀 서식 파일 시작
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
description: 팀 서식 파일을 사용 하 여 미리 정의 된 설정, 채널 및 사전 설치 앱을 제공 하 여 소매업 자의 요구 사항에 맞게 설계한 팀 구조를 만드는 방법을 알아봅니다.
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
# <a name="get-started-with-teams-templates-in-retail"></a>정품에서 팀 서식 파일 시작

팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.

팀 템플릿에는 소매점의 요구 사항에 따라 디자인 된 팀 구조의 정의가 미리 작성 되어 있습니다. 팀 서식 파일을 사용 하 여 소매 업체에 잘 맞는 팀 유형을 신속 하 게 만들고 조직 내에서 배포할 수 있습니다. 팀 템플릿을 확장 하 여 특정 조직의 요구 사항에 맞게 조정 된 팀을 만들 수도 있습니다.

이 문서에서는 각 팀 템플릿을 소개 하 고 사용 방법을 추천 합니다.

본 문서는 소매점에서 여러 팀을 계획, 배포 및 관리 해야 하는 경우에 적합 합니다. 조직에 이미 팀 서비스를 배포 했습니다. 아직 팀을 롤아웃하기 않은 경우 먼저 [Microsoft 팀을 배포 하는 방법을](How-to-roll-out-teams.md)읽어 보세요.

일반적으로 팀 서식 파일에 대 한 자세한 내용은 [팀 서식 파일 시작](get-started-with-teams-templates.md)을 참조 하세요.

## <a name="store-template"></a>스토어 서식 파일

스토어 서식 파일은 개별 소매 상점 위치를 나타내는 팀을 만드는 데 적합 합니다. 스토어 서식 파일을 사용 하 여 조직의 각 소매점 위치에 대 한 팀을 만들 수 있습니다.

| 기본 서식 파일 형식 | baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail <br>스토어 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| 채널 <ul><li>이송 이동\*</li><li>배웁니다\*</li></ul>\*자동 즐겨찾기에 채널<br><br>팀 속성 <ul><li>팀 가시성을 공개로 설정</li></ul> <br>회원 사용 권한 <ul><li>채널을 만들거나 업데이트 하거나 삭제할 수 없습니다. </li><li>앱을 추가/제거할 수 없음 </li><li>탭을 만들거나 업데이트 하거나 삭제할 수 없습니다.</li><li>커넥터를 만들거나 업데이트 하거나 제거할 수 없습니다.</li><ul>|
||||

조직의 스토어 서식 파일을 사용자 지정 하는 권장 방법:

- 조직의 부서가 각 매장 내에 있는 경우 각 부서에 대 한 채널을 추가 합니다. 채널을 추가 하면 부서 내의 의사 소통 및 공동 작업이 용이해 집니다.

- 조직에 내부 웹 사이트 (예: SharePoint 사이트)가 있는 경우 관련 팀 채널에서 탭으로 고정 하는 것이 좋습니다. 자세한 내용은 [팀 템플릿 시작](get-started-with-teams-templates.md) 을 참조 하세요.

## <a name="manager-collaboration-template"></a>관리자 공동 작업 서식 파일

관리자 공동 작업 서식 파일은 소매점 필요에 따라 디자인 된 팀 템플릿 중 하나입니다. 관리자 공동 작업 서식 파일은 관리자 집합을 대상으로 팀을 만들어 저장소/지역에서 공동 작업 하는 데 적합 합니다. 예를 들어 조직에 지역이 있는 경우 캘리포니아 지역에 대 한 관리자 공동 작업 팀을 만들고 해당 지역의 모든 스토어 관리자와 해당 지역의 지역 관리자를 함께 포함할 수 있습니다.

| 기본 서식 파일 형식 | baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| ------------------ | -------------- | ----------------------------------------------------- |
| Retail <br>스토어 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| 채널 <ul><li>운영\*</li><li>배웁니다\*</li></ul>\*자동 즐겨찾기에 채널<br><br>팀 속성 <ul><li>팀 표시 유형을 비공개로 설정</li></ul> <br>회원 사용 권한 <ul><li>채널을 만들거나 업데이트 하거나 삭제할 수 있습니다. </li><li>앱을 추가/제거할 수 있습니다. </li><li>탭을 만들거나 업데이트/제거할 수 있습니다.</li><li>커넥터를 만들거나 업데이트 하거나 제거할 수 있습니다.</li><ul>|
||||

조직의 관리자 공동 작업 서식 파일을 사용자 지정 하는 권장 방법:

- 조직에 SharePoint 사이트와 같이 관리자와 관련 된 내부 웹 사이트가 있는 경우이를 관련 팀 채널에서 탭으로 고정 하는 것이 좋습니다. 자세한 내용은 [Microsoft 팀 서식 파일 설명서](get-started-with-teams-templates.md) 를 참조 하세요.

## <a name="how-to-use-first-party-templates"></a>자사 서식 파일을 사용 하는 방법

이 템플릿을 사용 하려면 요청 본문의 ' template@odata. ' 속성을 ' standard '에서 위의 TemplateIDs로 변경 합니다.  팀 템플릿을 배포 하는 방법에 대 한 자세한 내용은 [팀을 만드는](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)방법에 대 한 Microsoft Graph 문서를 참조 하세요.

> [!NOTE]
> 서식 파일의 채널이 일반 탭 아래에 자동으로 생성 됩니다.

### <a name="example-store-template-extension-script"></a>예: Store template extension 스크립트

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
## <a name="relate-topic"></a>관계 주제

[관리 센터에서 팀 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)
