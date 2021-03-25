---
title: Microsoft Graph를 사용하여 구축된 중소기업용 Teams 템플릿
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
description: Microsoft Graph에 기본 제공된 Microsoft Teams 미리 정의된 템플릿을 사용하여 중소기업에 대한 팀을 빠르고 쉽게 만들 수 있습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116996"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="65266-103">중소기업용 Microsoft Graph에서 기본 제공된 팀 템플릿</span><span class="sxs-lookup"><span data-stu-id="65266-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="65266-104">Microsoft Teams 서식 파일을 사용하면 미리 정의된 설정, 채널 및 미리 설치된 앱 서식 파일을 제공하여 팀을 쉽고 빠르게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65266-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="65266-105">중소기업의 경우 관리자가 조직 전체에 Teams를 빠르게 배포할 수 있도록 도와주기 위해 템플릿이 특히 강력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65266-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="65266-106">템플릿은 사용자를 지향하고 Teams를 효과적으로 사용하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65266-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="65266-107">이 문서는 조직 전체에서 여러 팀을 계획, 배포 및 관리할 책임이 있는 경우를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65266-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="65266-108">현재 다양한 상황에 활용할 수 있는 3개의 파티 SMB 템플릿을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65266-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="65266-109">모든 템플릿은 *개인 팀을* 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65266-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="65266-110">Teams를 만들어 조직에 롤아웃할 준비가되면 개인 정보를 *조직* 전체 또는 공용으로 적절하게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65266-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="65266-111">일반적인 팀 서식 파일에 대한 자세한 내용은 [Teams 서식 파일 시작하기](get-started-with-teams-templates.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="65266-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="65266-112">Company-Wide 템플릿</span><span class="sxs-lookup"><span data-stu-id="65266-112">Company-Wide template</span></span>
<span data-ttu-id="65266-113">이 Company-Wide 템플릿은 회사 전체에 관련된 통신 및 공동 작업을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65266-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="65266-114">회사 전체 공지, 업계 뉴스 또는 임원 게시물에 일반 채널을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65266-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="65266-115">인사 채널은 작업 게시물, 신입 직원 온보더링, 교육 및 개발과 같은 모든 HR 관련 활동을 통합할 수 있는 좋은 장소입니다.</span><span class="sxs-lookup"><span data-stu-id="65266-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="65266-116">Fun Stuff 채널은 모든 임의 및 재미있는 게시물에 대한 소셜 플랫폼을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65266-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="65266-117">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="65266-117">Base template type</span></span>  | <span data-ttu-id="65266-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="65266-118">baseTemplateId</span></span> | <span data-ttu-id="65266-119">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="65266-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="65266-120">SMB -</span><span class="sxs-lookup"><span data-stu-id="65266-120">SMB -</span></span> <br><span data-ttu-id="65266-121">회사 전체</span><span class="sxs-lookup"><span data-stu-id="65266-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="65266-122">채널</span><span class="sxs-lookup"><span data-stu-id="65266-122">Channels</span></span> <ul><li><span data-ttu-id="65266-123">일반\*</span><span class="sxs-lookup"><span data-stu-id="65266-123">General\*</span></span></li><li><span data-ttu-id="65266-124">인적 리소스\*</span><span class="sxs-lookup"><span data-stu-id="65266-124">Human Resources\*</span></span></li><li><span data-ttu-id="65266-125">재미있는 물건\*</span><span class="sxs-lookup"><span data-stu-id="65266-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="65266-126">앱</span><span class="sxs-lookup"><span data-stu-id="65266-126">Apps</span></span><ul><li><span data-ttu-id="65266-127">회사 포털(인사 채널에 고정된 **웹 사이트)**</span><span class="sxs-lookup"><span data-stu-id="65266-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="65266-128">팀 속성</span><span class="sxs-lookup"><span data-stu-id="65266-128">Team properties</span></span> <ul><li><span data-ttu-id="65266-129">비공개로 설정된 팀 표시 유형</span><span class="sxs-lookup"><span data-stu-id="65266-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="65266-130">\*자동 즐겨찾기 채널</span><span class="sxs-lookup"><span data-stu-id="65266-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="65266-131">미리 Company-Wide 템플릿에서 기본값을 사용하여 팀 팀을 만들 경우 요청 본문에 팀 개체의 JSON 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65266-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="65266-132">Teams 템플릿을 배포하는 방법에 대한 자세한 내용은 팀 만들기에 대한 Microsoft Graph [문서를 참조하세요.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="65266-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="65266-133">요청</span><span class="sxs-lookup"><span data-stu-id="65266-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="65266-134">Executive Team 템플릿</span><span class="sxs-lookup"><span data-stu-id="65266-134">Executive Team template</span></span>

<span data-ttu-id="65266-135">Executive Team 템플릿은 회사 경영진이 연간 우선 순위, 회계 예산, 전략적 이니셔티브 및 상위 클라이언트와 같은 회사 이니셔티브에 대해 의사소통하고 공동 작업할 수 있는 팀을 만드는 데 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="65266-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="65266-136">이 템플릿에는 특정 *토픽에* 대한 선택 사용자를 초대하는 개인 채널이 함께 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65266-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="65266-137">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="65266-137">Base template type</span></span>  | <span data-ttu-id="65266-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="65266-138">baseTemplateId</span></span> | <span data-ttu-id="65266-139">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="65266-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="65266-140">SMB -</span><span class="sxs-lookup"><span data-stu-id="65266-140">SMB -</span></span> <br><span data-ttu-id="65266-141">임원 팀</span><span class="sxs-lookup"><span data-stu-id="65266-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="65266-142">채널</span><span class="sxs-lookup"><span data-stu-id="65266-142">Channels</span></span> <ul><li><span data-ttu-id="65266-143">일반\*</span><span class="sxs-lookup"><span data-stu-id="65266-143">General\*</span></span></li><li><span data-ttu-id="65266-144">비공개 \*</span><span class="sxs-lookup"><span data-stu-id="65266-144">Private \*</span></span></li></ul> <span data-ttu-id="65266-145">앱</span><span class="sxs-lookup"><span data-stu-id="65266-145">Apps</span></span><ul><li><span data-ttu-id="65266-146">OneNote(개인 채널에 **고정)**</span><span class="sxs-lookup"><span data-stu-id="65266-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="65266-147">Planner(개인 채널에 **고정)**</span><span class="sxs-lookup"><span data-stu-id="65266-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="65266-148">팀 속성</span><span class="sxs-lookup"><span data-stu-id="65266-148">Team properties</span></span> <ul><li><span data-ttu-id="65266-149">비공개로 설정된 팀 표시 유형</span><span class="sxs-lookup"><span data-stu-id="65266-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="65266-150">\*자동 즐겨찾기 채널</span><span class="sxs-lookup"><span data-stu-id="65266-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="65266-151">미리 정의된 템플릿에서 기본값을 사용하여 Executives 팀을 만들 경우 요청 본문에 팀 개체의 JSON 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65266-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="65266-152">Teams 템플릿을 배포하는 방법에 대한 자세한 내용은 팀 만들기에 대한 Microsoft Graph [문서를 참조하세요.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="65266-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="65266-153">요청</span><span class="sxs-lookup"><span data-stu-id="65266-153">Request</span></span> 
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

## <a name="departmental-team-template"></a><span data-ttu-id="65266-154">부서 팀 템플릿</span><span class="sxs-lookup"><span data-stu-id="65266-154">Departmental Team template</span></span>

<span data-ttu-id="65266-155">부서 팀 템플릿은 개별 부서 또는 프로젝트에 대한 팀을 만드는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65266-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="65266-156">재무 팀 템플릿은 재무 팀 구성원 및 임원 팀 구성원 내의 모든 게시물, 공지사항 및 일일 공동 작업 및 커뮤니케이션에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="65266-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="65266-157">템플릿에는 특정 *토픽에* 대한 선택 사용자를 초대하는 개인 채널이 함께 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65266-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="65266-158">또한 템플릿을 추가, 삭제 또는 편집하여 추가 부서 또는 특정 프로젝트로 템플릿을 확장하는 데 사용할 수 있는 재무 팀에 대한 아래 스크립트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65266-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="65266-159">예를 들어 마케팅 부서가 있는 경우 재무에서 마케팅으로 팀 이름을 조정하여  새 마케팅 팀을 만들 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="65266-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="65266-160">기본 서식 파일 형식</span><span class="sxs-lookup"><span data-stu-id="65266-160">Base template type</span></span> | <span data-ttu-id="65266-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="65266-161">baseTemplateId</span></span> | <span data-ttu-id="65266-162">이 기본 서식 파일과 함께 사용할 수 있는 속성</span><span class="sxs-lookup"><span data-stu-id="65266-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="65266-163">SMB -</span><span class="sxs-lookup"><span data-stu-id="65266-163">SMB -</span></span> <br><span data-ttu-id="65266-164">재무</span><span class="sxs-lookup"><span data-stu-id="65266-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="65266-165">채널</span><span class="sxs-lookup"><span data-stu-id="65266-165">Channels</span></span> <ul><li><span data-ttu-id="65266-166">일반\*</span><span class="sxs-lookup"><span data-stu-id="65266-166">General\*</span></span></li><li><span data-ttu-id="65266-167">비공개 \*</span><span class="sxs-lookup"><span data-stu-id="65266-167">Private \*</span></span></li></ul><br> <span data-ttu-id="65266-168">앱</span><span class="sxs-lookup"><span data-stu-id="65266-168">Apps</span></span><ul><li><span data-ttu-id="65266-169">OneNote(개인 채널에 **고정)**</span><span class="sxs-lookup"><span data-stu-id="65266-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="65266-170">Planner(개인 채널에 **고정)**</span><span class="sxs-lookup"><span data-stu-id="65266-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="65266-171">팀 속성</span><span class="sxs-lookup"><span data-stu-id="65266-171">Team properties</span></span> <ul><li><span data-ttu-id="65266-172">비공개로 설정된 팀 표시 유형</span><span class="sxs-lookup"><span data-stu-id="65266-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="65266-173">\*자동 즐겨찾기 채널</span><span class="sxs-lookup"><span data-stu-id="65266-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="65266-174">미리 정의된 템플릿에서 기본값을 사용하여 재무 팀을 만들 경우 요청 본문에 팀 개체의 JSON 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65266-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="65266-175">Teams 템플릿을 배포하는 방법에 대한 자세한 내용은 팀 만들기에 대한 Microsoft Graph [문서를 참조하세요.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="65266-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="65266-176">요청</span><span class="sxs-lookup"><span data-stu-id="65266-176">Request</span></span> 
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

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="65266-177">예: Finance Team 템플릿 확장 스크립트</span><span class="sxs-lookup"><span data-stu-id="65266-177">Example: Finance Team template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="65266-178">관련 항목</span><span class="sxs-lookup"><span data-stu-id="65266-178">Related topics</span></span>

- [<span data-ttu-id="65266-179">관리 콘솔에서 Teams 템플릿 시작</span><span class="sxs-lookup"><span data-stu-id="65266-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="65266-180">Teams 서식 파일 시작</span><span class="sxs-lookup"><span data-stu-id="65266-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="65266-181">[팀 만들기(미리](/graph/api/team-post?view=graph-rest-beta) 보기)</span><span class="sxs-lookup"><span data-stu-id="65266-181">[Create team](/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>