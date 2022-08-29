---
title: Microsoft Graph를 사용하여 빌드된 중소기업을 위한 팀 템플릿
author: LanaChin
ms.author: v-lanachin
manager: samanro
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
description: Microsoft Graph에서 빌드된 Microsoft Teams 미리 정의된 템플릿을 사용하여 중소기업용 팀을 빠르고 쉽게 만들 수 있습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 644d45660fba729991796f33e7210222832e0c0f
ms.sourcegitcommit: 903abff4ce79c10bf1fb936b8ad71f6315a43c18
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2022
ms.locfileid: "67278482"
---
# <a name="team-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>중소기업용 Microsoft Graph에서 빌드된 팀 템플릿

Microsoft Teams의 팀 템플릿을 사용하면 설정, 채널 및 사전 설치된 앱의 미리 정의된 팀 구조를 제공하여 팀을 빠르고 쉽게 만들 수 있습니다.

중소기업의 경우 템플릿은 조직 전체에 Teams를 신속하게 배포하는 데 도움이 되므로 특히 강력할 수 있습니다. 템플릿을 사용하면 사용자가 Teams를 효과적으로 사용하는 방법을 파악할 수 있습니다. 이 문서는 조직 전체에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우에 적합합니다.

현재 다양한 상황에 사용할 수 있는 중소 기업용으로 미리 빌드된 3가지 템플릿을 제공합니다. 모든 템플릿은 *프라이빗* 팀을 만듭니다. 팀을 만들고 조직에 배포할 준비가 되면 개인 정보를 *조직 전체* 또는 *공용* 으로 적절하게 설정할 수 있습니다.

> [!NOTE]
> Microsoft Graph를 사용하여 사용자 지정 템플릿을 만들 수도 있습니다. 자세한 내용은 [teamTemplate 리소스 종류를](/graph/api/resources/teamtemplate) 참조하세요.

일반적으로 팀 템플릿에 대한 자세한 내용은 [Microsoft Graph를 사용하여 팀 템플릿 시작](get-started-with-teams-templates.md)을 참조하세요.

## <a name="company-wide-template"></a>Company-Wide 템플릿

Company-Wide 템플릿은 회사 전체의 커뮤니케이션 및 협업을 위한 것입니다. 회사 전체 공지, 업계 뉴스 또는 임원 게시물에 일반 채널을 사용할 수 있습니다. 인사 채널은 직무 게시물, 신입 직원 온보딩, 교육 및 개발과 같은 모든 HR 관련 활동을 통합하기에 좋은 장소입니다. Fun Stuff 채널은 모든 임의 및 재미있는 게시물에 대한 소셜 플랫폼을 제공합니다.

| 서식 파일 유형  | TemplateId | 이 템플릿과 함께 제공되는 속성 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>회사 전체 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| 채널 <ul><li>일반\*</li><li>인적 리소스\*</li><li>재미있는 물건\*</li></ul><br> 앱<ul><li>회사 포털(**인사** 채널에 고정된 웹 사이트) </li> </UL><br>팀 속성 <ul><li>비공개로 설정된 팀 표시 유형</li></ul> |

*자동 즐겨찾기 채널 

미리 정의된 템플릿에서 기본 설정을 가져와 Company-Wide 팀을 만들려면 요청 본문에 팀 개체의 JSON 표현을 제공합니다. 팀 템플릿을 배포하는 방법에 대한 자세한 내용은 [팀 만들기에 대한](/graph/api/team-post?view=graph-rest-beta) Microsoft Graph 문서를 참조하세요.

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

## <a name="executive-team-template"></a>이그제큐티브 팀 템플릿

경영진 템플릿은 회사 임원이 연간 우선 순위, 재정 예산, 전략적 이니셔티브 및 최고 고객과 같은 회사 이니셔티브에 대해 의사 소통하고 협업할 수 있는 팀을 만드는 데 이상적입니다. 이 템플릿에는 특정 토픽에 대한 선택 사용자를 초대하는 *비공개* 채널이 함께 제공됩니다.

| 서식 파일 유형  | TemplateId | 이 템플릿과 함께 제공되는 속성 |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>임원 팀 | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | 채널 <ul><li>일반\*</li><li>개인 \*</li></ul> 앱<ul><li>OneNote( **비공개** 채널에 고정됨)</li> <li>Planner( **프라이빗** 채널에 고정됨) </li></ul><br>팀 속성 <ul><li>비공개로 설정된 팀 표시 유형</li></ul> | 

*자동 즐겨찾기 채널<br>

미리 정의된 템플릿에서 기본 설정을 가져와서 임원 팀을 만들려면 요청 본문에 팀 개체의 JSON 표현을 제공합니다. 팀 템플릿을 배포하는 방법에 대한 자세한 내용은 [팀 만들기에 대한](/graph/api/team-post?view=graph-rest-beta) Microsoft Graph 문서를 참조하세요.

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

## <a name="departmental-team-template"></a>부서별 팀 템플릿

부서 팀 템플릿은 개별 부서 또는 프로젝트에 대한 팀을 만드는 데 사용할 수 있습니다. 재무 팀 템플릿은 재무 팀 구성원 및 경영진 팀 구성원 내에서 모든 게시물, 공지 사항 및 일상적인 공동 작업 및 커뮤니케이션에 적합합니다. 템플릿에는 특정 토픽에 대한 선택 사용자를 초대하는 *비공개* 채널이 함께 제공됩니다.

또한 원하는 대로 추가, 삭제 또는 편집하여 템플릿을 추가 부서 또는 특정 프로젝트로 확장하는 데 사용할 수 있는 Finance 팀에 대한 아래 스크립트를 제공합니다. 예를 들어 *마케팅* 부서가 있는 경우 팀의 이름을 *Finance* 에서 *Marketing* 으로 변경하여 새 마케팅 팀을 만들어 스크립트를 조정할 수 있습니다.

| 서식 파일 유형 | TemplateId | 이 템플릿과 함께 제공되는 속성 |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB - <br>재무  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| 채널 <ul><li>일반\*</li><li>개인 \*</li></ul><br> 앱<ul><li>OneNote( **비공개** 채널에 고정됨)</li> <li>Planner( **프라이빗** 채널에 고정됨) </li> </ul><br>팀 속성 <ul><li>비공개로 설정된 팀 표시 유형</li></ul> | 

*자동 즐겨찾기 채널

미리 정의된 템플릿에서 기본 설정을 가져와 재무 팀을 만들려면 요청 본문에 팀 개체의 JSON 표현을 제공합니다. 팀 템플릿을 배포하는 방법에 대한 자세한 내용은 [팀 만들기에 대한](/graph/api/team-post?view=graph-rest-beta) Microsoft Graph 문서를 참조하세요.

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

- [Teams 관리 센터에서 팀 템플릿 시작하기](get-started-with-teams-templates-in-the-admin-console.md)
- [Microsoft Graph를 사용하여 팀 템플릿 시작하기](get-started-with-teams-templates.md)
- [팀 만들기](/graph/api/team-post?view=graph-rest-beta) (미리 보기)
