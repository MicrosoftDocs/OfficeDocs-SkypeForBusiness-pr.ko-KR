---
title: Microsoft와 함께 구축된 중소기업용 팀 Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Microsoft Microsoft Teams 미리 정의된 템플릿을 사용하여 중소 Graph 팀을 빠르고 쉽게 만들 수 있습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0855e7a61b52582b283a5c1f7c4c4f966045d743
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991217"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>중소기업을 위해 Microsoft Graph 기본 제공된 팀 템플릿

팀 템플릿을 Microsoft Teams 설정, 채널 및 미리 설치된 앱의 미리 정의된 팀 구조를 제공하여 빠르고 쉽게 팀을 만들 수 있습니다.

중소기업의 경우 템플릿이 조직 전체에 빠르게 배포할 수 있도록 도와주기 때문에 특히 Teams 수 있습니다. 템플릿을 사용하면 사용자가 템플릿을 효과적으로 사용하는 방법을 알 수 Teams. 이 문서는 조직 전체에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다.

현재 다양한 상황에 사용할 수 있는 중소기업에 미리 작성된 3가지 템플릿을 제공합니다. 모든 템플릿은 개인 *팀을* 만듭니다. 팀을 만들고 조직에 롤아웃할 준비가 된 후 개인 정보를 *조직* 전체 또는 공용으로 적절하게 설정할 수 있습니다.

일반적으로 팀 템플릿에 대한 자세한 내용은 [Microsoft](get-started-with-teams-templates.md)Graph.

## <a name="company-wide-template"></a>Company-Wide 템플릿

이 Company-Wide 템플릿은 전체 회사에 대한 통신 및 공동 작업을 위한 것입니다. 회사 전체 공지, 업계 뉴스 또는 임원 게시물에 일반 채널을 사용할 수 있습니다. 인사 채널은 작업 게시물, 신입 직원 온보더링, 교육 및 개발과 같은 모든 HR 관련 활동을 통합할 수 있는 좋은 장소입니다. Fun Stuff 채널은 모든 임의 및 재미있는 게시물에 대한 소셜 플랫폼을 제공합니다.

| 템플릿 유형  | TemplateId | 이 템플릿과 함께 있는 속성 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>회사 전체 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| 채널 <ul><li>일반\*</li><li>인적 리소스\*</li><li>재미있는 물건\*</li></ul><br> 앱<ul><li>회사 포털(인사 채널에 고정된 **웹** 사이트) </li> </UL><br>팀 속성 <ul><li>비공개로 설정된 팀 표시 유형</li></ul> |

*자동 즐겨찾기 채널 

미리 정의된 Company-Wide 기본 설정을 사용하여 팀 팀을 만들하려면 요청 본문에 팀 개체의 JSON 표현을 제공합니다. 팀 템플릿을 배포하는 방법에 대한 자세한 내용은 팀 만들기에 대한 Microsoft Graph [문서를 참조하세요.](/graph/api/team-post?view=graph-rest-beta)

#### <a name="request"></a>요청 
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

## <a name="executive-team-template"></a>Executive Team 템플릿

Executive Team 템플릿은 회사 경영진이 연간 우선 순위, 회계 예산, 전략적 이니셔티브 및 상위 클라이언트와 같은 회사 이니셔티브에 대해 의사소통하고 공동 작업할 수 있는 팀을 만드는 데 이상적입니다. 이 템플릿에는 특정 *토픽에* 대한 선택 사용자를 초대하는 개인 채널이 함께 있습니다.

| 템플릿 유형  | TemplateId | 이 템플릿과 함께 있는 속성 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>임원 팀 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | 채널 <ul><li>일반\*</li><li>비공개 \*</li></ul> 앱<ul><li>OneNote(개인 채널에 고정) </li> <li>Planner(개인 채널에 **고정)** </li></ul><br>팀 속성 <ul><li>비공개로 설정된 팀 표시 유형</li></ul> | 

*자동 즐겨찾기 채널<br>

미리 정의된 템플릿에서 기본 설정을 사용하여 Executives 팀을 만들하려면 요청 본문에 팀 개체의 JSON 표현을 제공합니다. 팀 템플릿을 배포하는 방법에 대한 자세한 내용은 팀 만들기에 대한 Microsoft Graph [문서를 참조하세요.](/graph/api/team-post?view=graph-rest-beta)

#### <a name="request"></a>요청 
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

## <a name="departmental-team-template"></a>부서 팀 템플릿

부서 팀 템플릿은 개별 부서 또는 프로젝트에 대한 팀을 만드는 데 사용할 수 있습니다. 재무 팀 템플릿은 재무 팀 구성원 및 임원 팀 구성원 내의 모든 게시물, 공지사항 및 일일 공동 작업 및 커뮤니케이션에 적합합니다. 템플릿에는 특정 *토픽에* 대한 선택 사용자를 초대할 수 있는 개인 채널이 함께 있습니다.

또한 템플릿을 추가, 삭제 또는 편집하여 추가 부서 또는 특정 프로젝트로 템플릿을 확장하는 데 사용할 수 있는 재무 팀에 대한 아래 스크립트를 제공합니다. 예를 들어 마케팅 부서가 있는 경우 재무에서 마케팅으로 팀 이름을 조정하여  새 마케팅 팀을 만들 수 있습니다.  

| 템플릿 유형 | TemplateId | 이 템플릿과 함께 있는 속성 |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>재무  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| 채널 <ul><li>일반\*</li><li>비공개 \*</li></ul><br> 앱<ul><li>OneNote(개인 채널에 고정) </li> <li>Planner(개인 채널에 **고정)** </li> </ul><br>팀 속성 <ul><li>비공개로 설정된 팀 표시 유형</li></ul> | 

*자동 즐겨찾기 채널

미리 정의된 템플릿에서 기본 설정을 사용하여 재무 팀을 만들하려면 요청 본문에 팀 개체의 JSON 표현을 제공합니다. 팀 템플릿을 배포하는 방법에 대한 자세한 내용은 팀 만들기에 대한 Microsoft Graph [문서를 참조하세요.](/graph/api/team-post?view=graph-rest-beta)

#### <a name="request"></a>요청 
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

### <a name="example-finance-team-template-extension-script"></a>예: Finance Team 템플릿 확장 스크립트

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

## <a name="related-topics"></a>관련 주제

- [관리 콘솔에서 Teams 템플릿 시작](get-started-with-teams-templates-in-the-admin-console.md)
- [Teams 서식 파일 시작](get-started-with-teams-templates.md)
- [팀 만들기(미리](/graph/api/team-post?view=graph-rest-beta) 보기)