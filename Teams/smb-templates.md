---
title: Microsoft Graph로 작성 된 중소 기업에 대 한 팀 서식 파일
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Microsoft Graph에서 기본 제공 되는 Microsoft 팀 미리 정의 된 서식 파일을 사용 하 여 중소기업을 위한 쉽고 빠르게 팀을 만들 수 있습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7196dd93fc1245102a333c150715c4b4570986c7
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294554"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>중소 기업에 맞게 Microsoft Graph로 작성 된 팀 서식 파일

Microsoft 팀 서식 파일을 사용 하면 미리 정의 된 서식 파일 (설정, 채널 및 사전 설치 된 앱)을 제공 하 여 빠르고 쉽게 팀을 만들 수 있습니다.

중소기업의 경우 관리자가 조직에 신속 하 게 팀을 배포 하는 데 도움을 주는 대신 서식 파일을 사용 하는 것이 특히 유용 합니다. 또한 서식 파일을 사용 하 여 팀을 효과적으로 사용할 수 있도록 도와 드립니다. 이 문서는 조직에서 여러 팀을 계획, 배포 및 관리 해야 하는 경우에 유용 합니다.

현재 다양 한 상황에 활용할 수 있는 제 3 자 SMB 서식 파일을 제공 합니다. 모든 서식 파일은 *비공개* 팀을 만듭니다. 팀을 만들었고 조직에 롤아웃 할 준비가 되 면 개인 정보를 적절 하 게 *조직 전체* 또는 *공개*로 설정할 수 있습니다. 팀 서식 파일에 대 한 일반적인 내용은 [팀 서식 파일 시작](get-started-with-teams-templates.md)을 참조 하세요.

## <a name="company-wide-template"></a>회사 전체 서식 파일
회사 전체의 서식 파일은 전체 회사와 관련 된 커뮤니케이션 및 공동 작업을 위한 것입니다. 회사 차원의 공지 사항, 업계 뉴스 또는 임원 게시물에 대 한 일반 채널을 사용할 수 있습니다. 인적 자원 채널은 작업 게시물, 새로운 직원 온 보 딩, 교육, 개발 등의 모든 HR 관련 활동을 통합 하기에 좋은 장소입니다. 재미 있는 채널은 모든 임의 및 재미 있는 게시물에 대 한 소셜 플랫폼을 제공 합니다.

| 기본 서식 파일 형식  | baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| 중소기업 <br>회사 전체 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| 채널 <ul><li>일반\*</li><li>인적 자원\*</li><li>재미 있는 내용\*</li></ul><br> 앱<ul><li>회사 포털 ( **인적 자원** 채널에 고정 된 웹 사이트) </li> </UL><br>팀 속성 <ul><li>팀 표시 유형을 비공개로 설정</li></ul> |

* 자동 즐겨찾기에 채널 

미리 정의 된 템플릿에서 기본값을 가져와 회사 차원의 팀을 만들려면 요청 본문에 팀 개체의 JSON 표현을 제공 합니다. 팀 템플릿을 배포 하는 방법에 대해 자세히 알아보려면 [팀 만들기에 대](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)한 Microsoft Graph 문서를 참조 하세요.

#### <a name="request"></a>요청당 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a>임원 팀 서식 파일

임원 팀 서식 파일은 회사 경영진이 연간 우선 순위, 회계 예산, 전략적 이니셔티브, 상위 클라이언트와 같은 회사 이니셔티브에 대해 의사 소통 하 고 공동 작업을 수행 하는 팀을 만드는 데 적합 합니다. 이 서식 파일에는 특정 항목에 대 한 사용자 선택을 초대 하는 *개인* 채널이 제공 됩니다.

| 기본 서식 파일 형식  | baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| 중소기업 <br>임원 팀 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | 채널 <ul><li>일반\*</li><li>개인용 \*</li></ul> 앱<ul><li>OneNote ( **개인** 채널로 고정)</li> <li>Planner ( **개인** 채널에 고정 됨) </li></ul><br>팀 속성 <ul><li>팀 표시 유형을 비공개로 설정</li></ul> | 

* 자동 즐겨찾기에 채널<br>

미리 정의 된 템플릿에서 기본값을 가져와 임원 팀을 만들려면 요청 본문에 팀 개체의 JSON 표현을 제공 합니다. 팀 템플릿을 배포 하는 방법에 대해 자세히 알아보려면 [팀 만들기에 대](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)한 Microsoft Graph 문서를 참조 하세요.

#### <a name="request"></a>요청당 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>부서별 팀 서식 파일

부서별 팀 템플릿을 사용 하 여 개별 부서나 프로젝트에 대 한 팀을 만들 수 있습니다. 재무 팀 서식 파일은 재무 팀 구성원 및 경영진 팀 구성원 내의 모든 게시물, 공지 사항, 일일 공동 작업 및 의사 소통에 적합 합니다. 이 서식 파일에는 특정 항목에 대 한 사용자 선택을 초대 하는 *개인* 채널이 제공 됩니다. 또한 원하는 대로 추가, 삭제 또는 편집 하 여 서식 파일을 추가 부서나 특정 프로젝트로 확장 하는 데 사용할 수 있는 재무 팀에 대 한 아래 스크립트도 제공 합니다. 예를 들어 *마케팅* 부서가 있는 경우 팀의 이름을 *재무* 에서 *마케팅* 으로 변경 하 여 새 마케팅 팀을 만들기 위해 스크립트를 적용할 수 있습니다.

| 기본 서식 파일 형식 | baseTemplateId | 이 기본 서식 파일에 포함 된 속성 |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| 중소기업 <br>재무  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| 채널 <ul><li>일반\*</li><li>개인용 \*</li></ul><br> 앱<ul><li>OneNote ( **개인** 채널로 고정)</li> <li>Planner ( **개인** 채널에 고정 됨) </li> </ul><br>팀 속성 <ul><li>팀 표시 유형을 비공개로 설정</li></ul> | 

* 자동 즐겨찾기에 채널

미리 정의 된 템플릿에서 기본값을 가져와 재무 팀을 만들려면 요청 본문에 팀 개체의 JSON 표현을 제공 합니다. 팀 템플릿을 배포 하는 방법에 대해 자세히 알아보려면 [팀 만들기에 대](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)한 Microsoft Graph 문서를 참조 하세요.

#### <a name="request"></a>요청당 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a>예: 재무 팀 서식 파일 확장 스크립트

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a>관련 항목

- [관리 콘솔에서 팀 서식 파일 시작](get-started-with-teams-templates-in-the-admin-console.md)
- [Teams 서식 파일 시작](get-started-with-teams-templates.md)
- [팀 만들기](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (미리 보기)

