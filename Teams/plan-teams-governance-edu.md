---
title: 관리자용 Microsoft 교육 거버넌스 FAQ
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Microsoft Education 그룹을 사용하는 관리자로부터 자주 묻는 질문에 대한 Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ada92509adc0f066bf957ddaa8f5de8dd0c47653
ms.sourcegitcommit: 8906fc384cd13255972df53d2a07d12589154d42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2021
ms.locfileid: "52085850"
---
# <a name="microsoft-education-governance-faq-for-admins"></a><span data-ttu-id="02435-103">관리자용 Microsoft 교육 거버넌스 FAQ</span><span class="sxs-lookup"><span data-stu-id="02435-103">Microsoft Education governance FAQ for admins</span></span>

> [!Tip]
> <span data-ttu-id="02435-104">다음 세션에서 관리에 대한 자세한 Microsoft Teams: 거버넌스, 관리 및 [수명 주기에 Microsoft Teams](https://aka.ms/teams-governance)</span><span class="sxs-lookup"><span data-stu-id="02435-104">Watch the following session to learn about more about management in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a><span data-ttu-id="02435-105">팀 만들기를 제어하는 방법</span><span class="sxs-lookup"><span data-stu-id="02435-105">How do I control team creation?</span></span> <span data-ttu-id="02435-106">학생들이 부적절한 팀을 만들지 걱정됩니다.</span><span class="sxs-lookup"><span data-stu-id="02435-106">I'm worried students are going to create inappropriate teams.</span></span>

<span data-ttu-id="02435-107">부적절하거나 잘못된 이름을 방지하거나 팀 이름을 지정하는 방법에 대한 더 많은 구조를 제공하기 위해 Microsoft 365 그룹 명명 정책(현재 미리 보기)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-107">To avoid inappropriate or misleading names, or just to provide more structure for how teams are named, you can use the Microsoft 365 Groups naming policy (currently in preview):</span></span>

-   <span data-ttu-id="02435-108">**접두사-접미사 이름 이름 정책** 접두사 또는 접미사를 사용하여 팀(그룹)의 이름 **규칙을 정의할 수 GRP_US_My Group_Engineering.**</span><span class="sxs-lookup"><span data-stu-id="02435-108">**Prefix-Suffix naming policy** You can use prefixes or suffixes to define the naming convention of teams (groups), for example, **GRP_US_My Group_Engineering**.</span></span> <span data-ttu-id="02435-109">접두사 및 접미사는 팀을 만드는 사용자를 기반으로 이름에 추가되는 문자열 또는 사용자 특성(예: **[부서])일** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-109">The prefixes and suffixes can be fixed strings or user attributes (such as **[Department]**) that are added to the name based on the user who's creating the team.</span></span>
-   <span data-ttu-id="02435-110">**사용자 지정 차단된 단어** 특정 조직의 사용자가 만든 팀의 이름으로 사용이 차단된 단어 집합을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-110">**Custom Blocked Words** You can upload a set of words that users in a specific organization are blocked from using in names of teams they create.</span></span> <span data-ttu-id="02435-111">예를 들어 **CEO,** **급여** 및 **HR** 용어가 적용되지 않는 그룹의 팀 이름에서 사용되는 것을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-111">For example, you can block the terms **CEO**, **Payroll**, and **HR** from being used in team names for groups they don't apply to.</span></span>
-   <span data-ttu-id="02435-112">**분류** 조직에서 사용자가 그룹 그룹을 만들 때 설정할 수 있는 분류를 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-112">**Classification** You can create classifications that the users in your organization can set when they create a Microsoft 365 Group.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="02435-113">그룹 Microsoft 365 정책을 사용하려면 하나 Azure Active Directory Premium 그룹의 구성원인 각 고유 사용자에 대해 P1 Azure Active Directory Premium Azure AD Basic EDU 라이선스를 Microsoft 365 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-113">Using the Microsoft 365 Groups Naming Policy requires Azure Active Directory Premium P1 licenses or Azure AD Basic EDU licenses for each unique user that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="02435-114">자세한 지침은 그룹 [Office 정책 을 참조하세요.](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)</span><span class="sxs-lookup"><span data-stu-id="02435-114">For detailed instructions, see [Office groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

> [!Note]
> <span data-ttu-id="02435-115">다른 시스템의 입력을 사용하여 팀을 자동으로 만든 경우(예: 학교 데이터 동기화) 입력 데이터가 구성한 이름 정책을 준수하는지 확인해야 합니다. 그렇지 않은 경우 팀 만들기가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-115">If teams are created automatically by using the input from another system (for example, School Data Sync), verify that the input data complies with the naming policy you've configured; if it doesn't, team creation will fail.</span></span>

## <a name="can-i-see-who-created-a-team"></a><span data-ttu-id="02435-116">팀을 만든 사람도 볼 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="02435-116">Can I see who created a team?</span></span>

<span data-ttu-id="02435-117">특정 팀을 만든 사용자에 대해 확인하려면 의 이벤트에 대한 감사 [로그 검색을 Microsoft Teams.](audit-log-events.md)</span><span class="sxs-lookup"><span data-stu-id="02435-117">To find out who created a specific team, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="can-i-control-who-can-create-teams"></a><span data-ttu-id="02435-118">팀을 만들 수 있는 사용자도 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="02435-118">Can I control who can create teams?</span></span>

<span data-ttu-id="02435-119">일반적으로 모든 사용자가 팀을 만드는 것을 방지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-119">In general, we recommend against preventing anyone from creating teams.</span></span> <span data-ttu-id="02435-120">모든 사용자가 팀을 만들 수 Teams 널리 채택될 가능성이 더 습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-120">If everyone can create teams, Teams is more likely to be widely adopted.</span></span> <span data-ttu-id="02435-121">교직원, 교사 또는 학생은 학습 그룹을 Teams 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-121">Faculty, teachers, or students can  use Teams to create study groups or special interest groups.</span></span> <span data-ttu-id="02435-122">이렇게 하면 교실 Teams 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-122">This will help Teams be accepted inside and outside of the classroom.</span></span>

<span data-ttu-id="02435-123">사용자 교육을 통해 책임감 있는 사용 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-123">In our experience, user education helps ensure responsible Teams usage.</span></span> <span data-ttu-id="02435-124">사용자가 팀을 만드는 것이 익명이 아니라는 것을 이해하면 부적절하게 팀을 만드는 의미를 이해하고 도구를 오용하지 않는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-124">As soon as users understand that creating teams isn't anonymous, they understand the implications of carelessly creating them and tend to shy away from misusing the tool.</span></span>

<span data-ttu-id="02435-125">팀을 만들 수 있는 사용자에 대해 제어하려는 경우 그룹 그룹을 만들 수 있는 Microsoft 365 [참조합니다.](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)</span><span class="sxs-lookup"><span data-stu-id="02435-125">If you're sure you want to control who can create teams, see [Manage who can create Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a><span data-ttu-id="02435-126">학기 또는 분기 초에 각 과정에 대한 팀을 자동으로 만들 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="02435-126">How do I automatically create a team for each course at the beginning of the semester or quarter?</span></span>

<span data-ttu-id="02435-127">각학기 또는 분기가 시작될 때 새 팀이 여러 개 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-127">At the start of each semester or quarter, you'll need a number of new teams.</span></span> <span data-ttu-id="02435-128">이러한 팀을 자동으로 만들고, 올바른 사용자로 채우고, 올바른 권한을 설정하는 자동화된 접근 방식을 취하는 것이 맞을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-128">It might make sense to take an automated approach to create these teams automatically, populate them with the right users, and set the right permissions:</span></span>

-   <span data-ttu-id="02435-129">학교 데이터 동기화 다른 많은 타사 애플리케이션에 대한 Microsoft 365 및 Exchange Online SharePoint, Microsoft Teams 및 OneNote 수업용 수업 팀, Intune for Education의 학교 그룹, 등록 및 SSO(Single Sign-On) 통합을 위한 그룹 및 온라인 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-129">School Data Sync can create Microsoft 365 Groups for Exchange Online and SharePoint Online, class teams for Microsoft Teams and OneNote Class notebooks, school groups for Intune for Education, and rostering and single sign-on (SSO) integration for many other third-party applications.</span></span> <span data-ttu-id="02435-130">자세한 내용은 의 개요 [에서 학교 데이터 동기화.](/schooldatasync/overview-of-school-data-sync)</span><span class="sxs-lookup"><span data-stu-id="02435-130">Learn more at [Overview of School Data Sync](/schooldatasync/overview-of-school-data-sync).</span></span>
-   <span data-ttu-id="02435-131">PowerShell을 사용하면 팀 및 채널을 만들고 설정을 자동으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-131">With PowerShell, you can create teams and channels, and configure settings automatically.</span></span> <span data-ttu-id="02435-132">자세한 [Microsoft Teams PowerShell을](/powershell/module/teams/?view=teams-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02435-132">See [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
-   <span data-ttu-id="02435-133">Microsoft Graph API(현재 베타)를 사용하여 팀을 만들고, 구성하고, 복제하고, 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-133">You can use the Microsoft Graph API (currently in beta) to create, configure, clone, and archive teams.</span></span> <span data-ttu-id="02435-134">자세한 [내용은 Microsoft Graph API를 사용하여](/graph/api/resources/teams-api-overview) Microsoft Teams 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02435-134">See [Use the Microsoft Graph API to work with Microsoft Teams](/graph/api/resources/teams-api-overview) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="02435-135">학교 데이터 동기화 동기화된 각 Microsoft 365 그룹을 만들고 숨겨진 그룹 [](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) 멤버 자격을 사용할 수 있으므로 수업 내의 교사와 학생만 해당 수업의 구성원을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-135">School Data Sync creates a Microsoft 365 Group for each class synced and [enables hidden group membership](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) so only teachers and students within the class can see the members of that class.</span></span> <span data-ttu-id="02435-136">다른 프로세스를 사용하여 클래스 그룹을 만드는 경우 동일한 개인 정보 New-UnifiedGroup cmdlet의 HiddenGroupMembershipEnabled 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-136">If using a different process to create class groups use the HiddenGroupMembershipEnabled parameter of the New-UnifiedGroup cmdlet to meet the same privacy requirements.</span></span>

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a><span data-ttu-id="02435-137">한학기 또는 분기가 끝나면 팀을 어떻게 처리하나요?</span><span class="sxs-lookup"><span data-stu-id="02435-137">How do I deal with teams when the semester or quarter ends?</span></span>

<span data-ttu-id="02435-138">학교 학기 또는 분기가 Teams 데이터를 처리하려는 방법에 대해 먼저 생각해 보는 것이 좋습니다. 수업을 완료한 후에도 해당 데이터를 삭제하거나 학생이 사용할 수 있도록 유지할지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="02435-138">We recommend that you first think about how you want to handle Teams data when the school semester or quarter is over: whether to delete it or keep it available for students even after they've completed the course.</span></span> <span data-ttu-id="02435-139">설정한 정책이 공휴일과 충돌하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-139">You'll want to keep the school calendar in mind so any policies you set don't conflict with holidays.</span></span> <span data-ttu-id="02435-140">다음 도구를 사용하여 전략을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-140">You can use the following tools to implement your strategy:</span></span>

-   <span data-ttu-id="02435-141">**보존 정책:** 이 옵션을 사용하여 지정한 연령보다 오래된 모든 데이터를 삭제하여 채팅(전체 또는 일부 사용자의 경우) 및 채널에서 이전 데이터가 제거되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="02435-141">**Retention policy:** Use this to delete all data older than an age you specify to make sure that old data is removed from chats (for all or some users) and channels.</span></span> <span data-ttu-id="02435-142">콘텐츠를 삭제할 수 Teams 유지하도록 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-142">You can also configure Teams to retain content so it can't be deleted.</span></span> <span data-ttu-id="02435-143">자세한 내용은 에 대한 [보존 정책을 Microsoft Teams.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)</span><span class="sxs-lookup"><span data-stu-id="02435-143">For more information, see [Retention policies for Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).</span></span>
-   <span data-ttu-id="02435-144">**만료 정책:** 특정 일 수 후에 만료하도록 팀을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-144">**Expiry policy:** Configure teams to expire after a certain number of days.</span></span> <span data-ttu-id="02435-145">만료 30일 전에 팀의 모든 소유자에게 팀을 갱신해야 하다가 삭제됩니다(관리자가 삭제된 팀을 추가로 30일 동안 복구할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="02435-145">Thirty days before expiration, all owners of a team are notified that their team needs to be renewed, otherwise it will be deleted (though an administrator can recover deleted teams for an additional 30 days).</span></span> <span data-ttu-id="02435-146">이 설정은 사용되지 않는 팀이 일몰된지 확인하는 데 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-146">This setting is very useful for making sure unused teams are sunsetted.</span></span> <span data-ttu-id="02435-147">자세한 내용은 Microsoft 365 [만료 정책 에서 자세히 알아보고](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)</span><span class="sxs-lookup"><span data-stu-id="02435-147">Learn more at [Microsoft 365 group Expiration Policy](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).</span></span>

-   <span data-ttu-id="02435-148">**보관 팀:** 이 설정은 팀을 읽기 전용 모드로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-148">**Archive team:** This setting puts teams into read-only mode.</span></span> <span data-ttu-id="02435-149">검색 및 검색할 수 있지만 새 게시물을 추가할 수 있는 사람은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-149">They can still be browsed and searched, but no one can add any new posts.</span></span> <span data-ttu-id="02435-150">[팀의](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) 보관 또는 복원은 팀 소유자가 팀을 보관할 수 있는 방법을 설명합니다. 팀 소유자는 팀의 Graph [API(베타)를](/graph/api/resources/teams-api-overview) 사용하여 팀을 보관하거나 복원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-150">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describes how team owners can archive a team; Team owners can also use the [Graph API (beta)](/graph/api/resources/teams-api-overview) to archive or restore a team.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="02435-151">그룹 Microsoft 365 만료 정책을 사용하려면 하나 Azure Active Directory Premium 그룹의 구성원인 각 고유 사용자에 대해 P1 라이선스를 Microsoft 365 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-151">Using the Microsoft 365 Groups Expiration Policy requires Azure Active Directory Premium P1 licenses for each unique user that is a member of one or more Microsoft 365 groups.</span></span>

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a><span data-ttu-id="02435-152">팀을 만들 때 사용할 교직원용 팀 템플릿이 있나요?</span><span class="sxs-lookup"><span data-stu-id="02435-152">Are there team templates for my faculty members to use when creating a team?</span></span>

<span data-ttu-id="02435-153">예.</span><span class="sxs-lookup"><span data-stu-id="02435-153">Yes.</span></span> <span data-ttu-id="02435-154">사용자는 **새** 팀을 만들 때 기존 템플릿에서 팀 만들기를 선택할 수 Teams 소유자는 Graph [API(베타)를](/graph/api/resources/teams-api-overview) 사용하여 사용 가능한 템플릿에서 새 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-154">Users can select **Create Team from existing template** when creating a new team, and Teams owners can also use the [Graph API (beta)](/graph/api/resources/teams-api-overview) to create a new team from the available templates.</span></span>

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a><span data-ttu-id="02435-155">PowerShell을 통해 자동화할 수 있는 작업은 Graph?</span><span class="sxs-lookup"><span data-stu-id="02435-155">What tasks can I automate via PowerShell or Graph?</span></span>

<span data-ttu-id="02435-156">[Microsoft Graph API(베타)는](/graph/api/resources/teams-api-overview) 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-156">The [Microsoft Graph API (beta)](/graph/api/resources/teams-api-overview) can do the following:</span></span>

-   <span data-ttu-id="02435-157">팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-157">Create a team.</span></span>
-   <span data-ttu-id="02435-158">구성원 및 소유자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-158">Add members and owners.</span></span>
-   <span data-ttu-id="02435-159">채널을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-159">Add channels.</span></span>
-   <span data-ttu-id="02435-160">앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-160">Add apps.</span></span>
-   <span data-ttu-id="02435-161">기존 팀을 복제하여 해당 단계를 바로 가기하고 탭도 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-161">Shortcut those steps by cloning an existing team, and get its tabs too.</span></span>
-   <span data-ttu-id="02435-162">방금 만든 팀에 대한 링크를 사용자에게 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-162">Give the user a link to the team you just created.</span></span>
-   <span data-ttu-id="02435-163">더 이상 필요하지 않습니다. 멤버, 소유자, 채널 및 앱을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-163">Remove members, owners, channels, and apps when you no longer need them.</span></span>
-   <span data-ttu-id="02435-164">더 이상 활성 상태일 때 팀을 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-164">Archive the team when it's no longer active.</span></span> 
-   <span data-ttu-id="02435-165">팀을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-165">Delete the team.</span></span>
-   <span data-ttu-id="02435-166">채널 스레드 만들기</span><span class="sxs-lookup"><span data-stu-id="02435-166">Create a channel thread</span></span>

<span data-ttu-id="02435-167">[PowerShell은](/powershell/module/teams/?view=teams-ps) 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-167">[PowerShell](/powershell/module/teams/?view=teams-ps) can do the following:</span></span>

-   <span data-ttu-id="02435-168">팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-168">Create a team.</span></span>
-   <span data-ttu-id="02435-169">구성원 및 소유자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-169">Add members and owners.</span></span>
-   <span data-ttu-id="02435-170">채널을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-170">Add channels.</span></span>
-   <span data-ttu-id="02435-171">더 이상 필요하지 않습니다. 멤버, 소유자 및 채널을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-171">Remove members, owners, and channels when you no longer need them.</span></span>
-   <span data-ttu-id="02435-172">팀을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-172">Delete the team.</span></span>

> [!TIP]
> <span data-ttu-id="02435-173">Graph API 및 PowerShell cmdlet은 지속적으로 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-173">The Graph API and PowerShell cmdlets are constantly adding functionality.</span></span> <span data-ttu-id="02435-174">기능 향상을 위해 Microsoft Graph [API(베타)](/graph/api/resources/teams-api-overview) 및 [PowerShell](/powershell/module/teams/?view=teams-ps) 문서를 자주 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-174">Make sure to check the [Microsoft Graph API (beta)](/graph/api/resources/teams-api-overview) and [PowerShell](/powershell/module/teams/?view=teams-ps) articles often for feature enhancements.</span></span>  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a><span data-ttu-id="02435-175">교직원 및 Teams 액세스할 수 있는 기능을 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="02435-175">Can I control what Teams features my faculty and students have access to?</span></span>

<span data-ttu-id="02435-176">예.</span><span class="sxs-lookup"><span data-stu-id="02435-176">Yes.</span></span> <span data-ttu-id="02435-177">정책을 사용하여 사용자가 액세스할 수 있는 특정 메시징, 모임, 통화 및 라이브 이벤트 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-177">You can use policies to control specific messaging, meeting, calling, and live event features your users have access to.</span></span> <span data-ttu-id="02435-178">테넌트 전체 설정을 사용하여 모두에 동일한 설정을 적용하거나 필요한 경우 사용자 수준 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-178">You can use tenant-wide settings to apply the same settings to all, or apply user-level policies if required.</span></span> 

<span data-ttu-id="02435-179">정책에 대한 Teams 자세한 내용은 조직의 Microsoft Teams [설정 관리를 참조하세요.](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="02435-179">For more details about Teams policies, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a><span data-ttu-id="02435-180">교직원 및 학생들이 공동 작업하는 외부 당사자를 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="02435-180">Can I control what external parties my faculty and students collaborate with?</span></span>

<span data-ttu-id="02435-181">게스트 액세스를 사용하여 테넌트 외부의 사용자를 초대할 수 있습니다. 이는 연구 공동 작업 또는 게스트 강의에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-181">You can use guest access to invite users from outside of your tenant, which can be useful for research collaboration or guest lectures:</span></span>

-   <span data-ttu-id="02435-182">도메인 허용 목록을 사용하여 도메인에 따라 게스트를 허용하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-182">Use a domain allowlist to allow or block guests based on their domain.</span></span>
-   <span data-ttu-id="02435-183">특정 그룹 및 Microsoft 365 게스트 액세스를 켜고 끄고 게스트를 초대할 수 있는 팀을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-183">Turn guest access on and off for particular Microsoft 365 Groups and teams, to control which teams can (and can't) invite guests.</span></span>
-   <span data-ttu-id="02435-184">감사 로그를 사용하여 초대된 게스트에게 전송된 경고를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-184">Use the audit log to see which alerts were sent to invited guests.</span></span>

<span data-ttu-id="02435-185">자세한 내용은 그룹 의 [게스트 Microsoft 365 참조하세요.](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)</span><span class="sxs-lookup"><span data-stu-id="02435-185">For more information, see [Guest access in Microsoft 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).</span></span>

## <a name="what-information-can-i-review-about-existing-teams"></a><span data-ttu-id="02435-186">기존 팀에 대해 어떤 정보를 검토할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="02435-186">What information can I review about existing teams?</span></span>

<span data-ttu-id="02435-187">감사 로그를 확인하여 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-187">You can check the audit logs to see:</span></span>

-   <span data-ttu-id="02435-188">Who 게스트로 초대된 팀입니다.</span><span class="sxs-lookup"><span data-stu-id="02435-188">Who was invited as a guest to which team.</span></span>
-   <span data-ttu-id="02435-189">Who 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02435-189">Who created which team.</span></span>

<span data-ttu-id="02435-190">자세한 내용은 의 이벤트에 대한 감사 [로그 검색을 Microsoft Teams.](audit-log-events.md)</span><span class="sxs-lookup"><span data-stu-id="02435-190">For more information, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a><span data-ttu-id="02435-191">Teams 빠르게 진화합니다.</span><span class="sxs-lookup"><span data-stu-id="02435-191">Teams evolves so quickly.</span></span> <span data-ttu-id="02435-192">최신을 유지 어떻게 할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="02435-192">How can I stay up-to-date?</span></span>

<span data-ttu-id="02435-193">다음 리소스를 통해 최신 업데이트를 Teams.</span><span class="sxs-lookup"><span data-stu-id="02435-193">We recommend the following resources to get the latest updates on Teams:</span></span>

-   [<span data-ttu-id="02435-194">새로운 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="02435-194">What's new in Microsoft Teams</span></span>](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [<span data-ttu-id="02435-195">Microsoft Teams 블로그</span><span class="sxs-lookup"><span data-stu-id="02435-195">Microsoft Teams blog</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)