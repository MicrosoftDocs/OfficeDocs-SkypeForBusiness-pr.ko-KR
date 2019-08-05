---
title: IT 전문가를 위한 microsoft 교육 관리 FAQ-Microsoft 팀
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 팀을 사용 하는 Microsoft 교육 그룹의 관리자가 자주 묻는 질문에 대 한 답변입니다.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0faa5f24ea64ae0fcfc967281126a4852dd139cf
ms.sourcegitcommit: 8ec1aa8f953206a08a488efdb59691824e26056a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2019
ms.locfileid: "36184967"
---
# <a name="microsoft-education-governance-faq-for-admins"></a><span data-ttu-id="5e108-103">관리자를 위한 Microsoft 교육 관리 FAQ</span><span class="sxs-lookup"><span data-stu-id="5e108-103">Microsoft Education governance FAQ for admins</span></span>

> [!Tip]
> <span data-ttu-id="5e108-104">Microsoft 팀의 관리 [, 관리 및 수명 주기](https://aka.ms/teams-governance) 에 대 한 자세한 내용을 보려면 다음 세션을 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-104">Watch the following session to learn about more about management in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="how-do-i-control-team-creation-im-worried-students-are-going-to-create-inappropriate-teams"></a><span data-ttu-id="5e108-105">팀 만들기를 제어 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="5e108-105">How do I control team creation?</span></span> <span data-ttu-id="5e108-106">걱정 하는 학생 들이 부적절 한 팀을 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-106">I'm worried students are going to create inappropriate teams.</span></span>

<span data-ttu-id="5e108-107">부적절 하거나 잘못 된 이름을 피하고, 팀의 이름을 지정 하는 방법에 대 한 추가 구조를 제공 하기 위해 Office 365 Groups name policy (현재 미리 보기 상태)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-107">To avoid inappropriate or misleading names, or just to provide more structure for how teams are named, you can use the Office 365 Groups naming policy (currently in preview):</span></span>

-   <span data-ttu-id="5e108-108">**접두사 접미사 이름 지정 정책** 접두 번호 또는 접미사를 사용 하 여 팀 (그룹)의 명명 규칙 (예: **GRP_US_My Group_Engineering**을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-108">**Prefix-Suffix naming policy** You can use prefixes or suffixes to define the naming convention of teams (groups), for example, **GRP_US_My Group_Engineering**.</span></span> <span data-ttu-id="5e108-109">접두 번호와 접미사는 팀을 만드는 사용자에 따라 이름에 추가 되는 고정 문자열 또는 사용자 특성 (예: **[부서]**) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-109">The prefixes and suffixes can be fixed strings or user attributes (such as **[Department]**) that are added to the name based on the user who’s creating the team.</span></span>
-   <span data-ttu-id="5e108-110">**사용자 지정 차단 된 단어** 특정 조직의 사용자가 자신이 만든 팀의 이름에서 사용을 차단 하는 단어 집합을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-110">**Custom Blocked Words** You can upload a set of words that users in a specific organization are blocked from using in names of teams they create.</span></span> <span data-ttu-id="5e108-111">예를 들어 팀 이름에 적용 되지 않는 그룹의 경우 **CEO**, **급여**, **HR** 의 사용 조건을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-111">For example, you can block the terms **CEO**, **Payroll**, and **HR** from being used in team names for groups they don’t apply to.</span></span>
-   <span data-ttu-id="5e108-112">**분류** 조직의 사용자가 Office 365 그룹을 만들 때 설정할 수 있는 분류를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-112">**Classification** You can create classifications that the users in your organization can set when they create an Office 365 group.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5e108-113">Office 365 Groups 명명 정책을 사용 하 여 하나 이상의 Office 365 그룹의 구성원 인 각 고유 사용자에 대 한 Azure Active Directory Premium P1 라이선스 또는 Azure AD 기본 .EDU 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-113">Using the Office 365 Groups Naming Policy requires Azure Active Directory Premium P1 licenses or Azure AD Basic EDU licenses for each unique user that is a member of one or more Office 365 groups.</span></span>

<span data-ttu-id="5e108-114">자세한 지침은 [Office 그룹 이름 지정 정책을](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-114">For detailed instructions, see [Office groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

> [!Note]
> <span data-ttu-id="5e108-115">다른 시스템의 입력을 사용 하 여 (예: School 데이터 동기화) 팀이 자동으로 생성 되는 경우 입력 데이터가 구성 된 이름 지정 정책에 부합 하는지 확인 합니다. 그렇지 않으면 팀 만들기가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-115">If teams are created automatically by using the input from another system (for example, School Data Sync), verify that the input data complies with the naming policy you’ve configured; if it doesn’t, team creation will fail.</span></span>

## <a name="can-i-see-who-created-a-team"></a><span data-ttu-id="5e108-116">누가 팀을 만들었는지 확인할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="5e108-116">Can I see who created a team?</span></span>

<span data-ttu-id="5e108-117">특정 팀을 만든 사용자를 확인 하려면 [Microsoft 팀에서 감사 로그에서 이벤트 검색](audit-log-events.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-117">To find out who created a specific team, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="can-i-control-who-can-create-teams"></a><span data-ttu-id="5e108-118">팀을 만들 수 있는 사용자를 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="5e108-118">Can I control who can create teams?</span></span>

<span data-ttu-id="5e108-119">일반적으로 모든 사용자가 팀을 만들지 못하도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-119">In general, we recommend against preventing anyone from creating teams.</span></span> <span data-ttu-id="5e108-120">모든 사용자가 팀을 만들 수 있는 경우 팀이 광범위 하 게 채택 될 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-120">If everyone can create teams, Teams is more likely to be widely adopted.</span></span> <span data-ttu-id="5e108-121">교직원, 교사 또는 학생이 팀을 사용 하 여 연구 그룹 또는 특별 이자 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-121">Faculty, teachers, or students can  use Teams to create study groups or special interest groups.</span></span> <span data-ttu-id="5e108-122">이렇게 하면 강의실 내부 및 외부에서 팀을 수락 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-122">This will help Teams be accepted inside and outside of the classroom.</span></span>

<span data-ttu-id="5e108-123">우리의 경험으로, 사용자 교육을 통해 책임이 있는 팀의 사용량을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-123">In our experience, user education helps ensure responsible Teams usage.</span></span> <span data-ttu-id="5e108-124">사용자가 익명이 아닌 것을 이해 하는 즉시, 팀을 만드는 carelessly의 의미를 이해 하 게 되 면이 도구를 잘못 된 방식으로 오용 하는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-124">As soon as users understand that creating teams isn’t anonymous, they understand the implications of carelessly creating them and tend to shy away from misusing the tool.</span></span>

<span data-ttu-id="5e108-125">팀을 만들 수 있는 사용자를 제어 하려면 [Office 365 그룹을 만들 수 있는 사용자 관리](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-125">If you’re sure you want to control who can create teams, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

## <a name="how-do-i-automatically-create-a-team-for-each-course-at-the-beginning-of-the-semester-or-quarter"></a><span data-ttu-id="5e108-126">반기 또는 분기 시작 시 각 과정에 대 한 팀을 자동으로 만들려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="5e108-126">How do I automatically create a team for each course at the beginning of the semester or quarter?</span></span>

<span data-ttu-id="5e108-127">각 반기 또는 분기의 시작 부분에는 여러 개의 새로운 팀이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-127">At the start of each semester or quarter, you’ll need a number of new teams.</span></span> <span data-ttu-id="5e108-128">자동으로 이러한 팀을 만들고 적절 한 사용자로 채운 다음 적절 한 사용 권한을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-128">It might make sense to take an automated approach to create these teams automatically, populate them with the right users, and set the right permissions:</span></span>

-   <span data-ttu-id="5e108-129">School Data Sync에서는 Exchange Online 및 SharePoint Online 용 Office 365 그룹, Microsoft 팀 및 OneNote 수업용 전자 필기장의 수업 팀, 교육용 Intune 용 학교 그룹, rostering 및 기타 다양 한 SSO (single sign-on) 통합을 만들 수 있습니다. 타사 응용 프로그램.</span><span class="sxs-lookup"><span data-stu-id="5e108-129">School Data Sync can create Office 365 Groups for Exchange Online and SharePoint Online, class teams for Microsoft Teams and OneNote Class notebooks, school groups for Intune for Education, and rostering and single sign-on (SSO) integration for many other third-party applications.</span></span> <span data-ttu-id="5e108-130">[School Data Sync 개요](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-130">Learn more at [Overview of School Data Sync](https://docs.microsoft.com/schooldatasync/overview-of-school-data-sync).</span></span>
-   <span data-ttu-id="5e108-131">PowerShell을 사용 하 여 팀과 채널을 만들고 설정을 자동으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-131">With PowerShell, you can create teams and channels, and configure settings automatically.</span></span> <span data-ttu-id="5e108-132">자세한 내용은 [Microsoft 팀 PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-132">See [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
-   <span data-ttu-id="5e108-133">Microsoft Graph API (현재 베타 버전)를 사용 하 여 팀을 만들고, 구성 하 고, 복제 하 고, 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-133">You can use the Microsoft Graph API (currently in beta) to create, configure, clone, and archive teams.</span></span> <span data-ttu-id="5e108-134">자세한 내용은 [Microsoft GRAPH API를 사용 하 여 Microsoft 팀 작업을](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-134">See [Use the Microsoft Graph API to work with Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="5e108-135">School Data Sync에서는 각 수업에 대해 Office 365 그룹을 만들어 동기화 하 고 [숨겨진 그룹 구성원을 사용 하도록 설정](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) 하 여 수업 내에서 교사와 학생이 해당 클래스의 구성원을 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-135">School Data Sync creates an Office 365 group for each class synced and [enables hidden group membership](https://techcommunity.microsoft.com/t5/School-Data-Sync/HiddenGroupMembershipEnabled-SDS-setting/td-p/159945) so only teachers and students within the class can see the members of that class.</span></span> <span data-ttu-id="5e108-136">다른 프로세스를 사용 하 여 클래스 그룹을 만드는 경우 새로운 UnifiedGroup cmdlet의 HiddenGroupMembershipEnabled 매개 변수를 사용 하 여 동일한 개인 정보 요구 사항을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-136">If using a different process to create class groups use the HiddenGroupMembershipEnabled parameter of the New-UnifiedGroup cmdlet to meet the same privacy requirements.</span></span>

## <a name="how-do-i-deal-with-teams-when-the-semester-or-quarter-ends"></a><span data-ttu-id="5e108-137">반기 또는 분기가 종료 되는 경우 팀을 처리 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="5e108-137">How do I deal with teams when the semester or quarter ends?</span></span>

<span data-ttu-id="5e108-138">이 과정을 완료 한 후에도 학교 반기 또는 분기가 종료 되 면 팀 데이터 처리 방법을 고려 하는 것이 좋습니다. 삭제 하거나 학생에 게 제공 된 상태를 유지 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-138">We recommend that you first think about how you want to handle Teams data when the school semester or quarter is over: whether to delete it or keep it available for students even after they’ve completed the course.</span></span> <span data-ttu-id="5e108-139">설정한 정책이 공휴일과 충돌 하지 않도록 학교 일정을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-139">You’ll want to keep the school calendar in mind so any policies you set don’t conflict with holidays.</span></span> <span data-ttu-id="5e108-140">다음 도구를 사용 하 여 전략을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-140">You can use the following tools to implement your strategy:</span></span>

-   <span data-ttu-id="5e108-141">**보존 정책:** 지정한 기간 보다 오래 된 모든 데이터를 삭제 하 여 이전 데이터가 채팅 (전체 또는 일부 사용자의 경우) 및 채널에서 제거 되었는지 확인 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-141">**Retention policy:** Use this to delete all data older than an age you specify to make sure that old data is removed from chats (for all or some users) and channels.</span></span> <span data-ttu-id="5e108-142">콘텐츠를 삭제 하지 못하도록 보존 하도록 팀을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-142">You can also configure Teams to retain content so it can’t be deleted.</span></span> <span data-ttu-id="5e108-143">자세한 내용은 [Microsoft 팀의 보존 정책을](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-143">For more information, see [Retention policies for Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Retention-policies-for-Microsoft-Teams/ba-p/178011).</span></span>
-   <span data-ttu-id="5e108-144">**만료 정책:** 특정 일 수가 지난 후에 만료 되도록 팀을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-144">**Expiry policy:** Configure teams to expire after a certain number of days.</span></span> <span data-ttu-id="5e108-145">만료 되기 30 일 전 팀의 모든 소유자에 게 팀을 갱신 해야 한다는 알림이 표시 되 고, 그렇지 않으면 관리자가 삭제 된 팀을 30 일간 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-145">Thirty days before expiration, all owners of a team are notified that their team needs to be renewed, otherwise it will be deleted (though an administrator can recover deleted teams for an additional 30 days).</span></span> <span data-ttu-id="5e108-146">이 설정은 사용 되지 않은 팀이 sunsetted 인지 확인 하는 데 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-146">This setting is very useful for making sure unused teams are sunsetted.</span></span> <span data-ttu-id="5e108-147">자세한 내용은 [Office 365 그룹 만료 정책](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-147">Learn more at [Office 365 Group Expiration Policy](https://support.office.com/article/office-365-group-expiration-policy-8d253fe5-0e09-4b3c-8b5e-f48def064733).</span></span>

-   <span data-ttu-id="5e108-148">**팀 보관:** 이 설정은 팀을 읽기 전용 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-148">**Archive team:** This setting puts teams into read-only mode.</span></span> <span data-ttu-id="5e108-149">계속 해 서 검색 하 고 검색할 수 있지만, 새 게시물을 추가할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-149">They can still be browsed and searched, but no one can add any new posts.</span></span> <span data-ttu-id="5e108-150">팀 소유자가 팀을 보관 하는 방법에 대해 설명 하는 [팀 보관 또는 복원](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) 팀 소유자는 [그래프 API (베타)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) 를 사용 하 여 팀을 보관 하거나 복원할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-150">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) describes how team owners can archive a team; Team owners can also use the [Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) to archive or restore a team.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="5e108-151">Office 365 그룹 만료 정책을 사용 하 여 하나 이상의 Office 365 그룹의 구성원 인 각 고유 사용자에 대 한 Azure Active Directory Premium P1 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-151">Using the Office 365 Groups Expiration Policy requires Azure Active Directory Premium P1 licenses for each unique user that is a member of one or more Office 365 groups.</span></span>

## <a name="are-there-team-templates-for-my-faculty-members-to-use-when-creating-a-team"></a><span data-ttu-id="5e108-152">팀을 만들 때 교직원 구성원을 위해 팀 서식 파일을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="5e108-152">Are there team templates for my faculty members to use when creating a team?</span></span>

<span data-ttu-id="5e108-153">'.</span><span class="sxs-lookup"><span data-stu-id="5e108-153">Yes.</span></span> <span data-ttu-id="5e108-154">사용자는 새 팀을 만들 때 **기존 서식 파일에서 팀 만들기** 를 선택할 수 있으며, 팀 소유자는 [Graph API (베타)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) 를 사용 하 여 사용 가능한 서식 파일에서 새 팀을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-154">Users can select **Create Team from existing template** when creating a new team, and Teams owners can also use the [Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) to create a new team from the available templates.</span></span>

## <a name="what-tasks-can-i-automate-via-powershell-or-graph"></a><span data-ttu-id="5e108-155">PowerShell 또는 그래프를 통해 자동화할 수 있는 작업은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="5e108-155">What tasks can I automate via PowerShell or Graph?</span></span>

<span data-ttu-id="5e108-156">[Microsoft GRAPH API (베타)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) 는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-156">The [Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) can do the following:</span></span>

-   <span data-ttu-id="5e108-157">팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-157">Create a team.</span></span>
-   <span data-ttu-id="5e108-158">회원 및 소유자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-158">Add members and owners.</span></span>
-   <span data-ttu-id="5e108-159">채널을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-159">Add channels.</span></span>
-   <span data-ttu-id="5e108-160">앱을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-160">Add apps.</span></span>
-   <span data-ttu-id="5e108-161">기존 팀을 복제 하 고 해당 탭을 가져오는 방법으로 바로 가기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-161">Shortcut those steps by cloning an existing team, and get its tabs too.</span></span>
-   <span data-ttu-id="5e108-162">방금 만든 팀에 대 한 링크를 사용자에 게 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-162">Give the user a link to the team you just created.</span></span>
-   <span data-ttu-id="5e108-163">구성원, 소유자, 채널, 앱을 더 이상 필요 하지 않은 경우 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-163">Remove members, owners, channels, and apps when you no longer need them.</span></span>
-   <span data-ttu-id="5e108-164">팀이 더 이상 활성화 되어 있지 않으면 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-164">Archive the team when it's no longer active.</span></span> 
-   <span data-ttu-id="5e108-165">팀을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-165">Delete the team.</span></span>
-   <span data-ttu-id="5e108-166">채널 스레드 만들기</span><span class="sxs-lookup"><span data-stu-id="5e108-166">Create a channel thread</span></span>

<span data-ttu-id="5e108-167">[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 은 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-167">[PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) can do the following:</span></span>

-   <span data-ttu-id="5e108-168">팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-168">Create a team.</span></span>
-   <span data-ttu-id="5e108-169">회원 및 소유자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-169">Add members and owners.</span></span>
-   <span data-ttu-id="5e108-170">채널을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-170">Add channels.</span></span>
-   <span data-ttu-id="5e108-171">더 이상 필요 하지 않은 구성원, 소유자, 채널을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-171">Remove members, owners, and channels when you no longer need them.</span></span>
-   <span data-ttu-id="5e108-172">팀을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-172">Delete the team.</span></span>

> [!TIP]
> <span data-ttu-id="5e108-173">그래프 API와 PowerShell cmdlet은 항상 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-173">The Graph API and PowerShell cmdlets are constantly adding functionality.</span></span> <span data-ttu-id="5e108-174">기능 향상을 위해 [Microsoft GRAPH API (베타)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) 및 [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 문서를 자주 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-174">Make sure to check the [Microsoft Graph API (beta)](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview) and [PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) articles often for feature enhancements.</span></span>  


## <a name="can-i-control-what-teams-features-my-faculty-and-students-have-access-to"></a><span data-ttu-id="5e108-175">내 교사와 학생이 액세스할 수 있는 팀의 기능을 제어 하나요?</span><span class="sxs-lookup"><span data-stu-id="5e108-175">Can I control what Teams features my faculty and students have access to?</span></span>

<span data-ttu-id="5e108-176">'.</span><span class="sxs-lookup"><span data-stu-id="5e108-176">Yes.</span></span> <span data-ttu-id="5e108-177">정책을 사용 하 여 사용자가 액세스할 수 있는 특정 메시징, 모임, 통화, 라이브 이벤트 기능을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-177">You can use policies to control specific messaging, meeting, calling, and live event features your users have access to.</span></span> <span data-ttu-id="5e108-178">테 넌 트 전체 설정을 사용 하 여 동일한 설정을 all에 적용 하거나 필요한 경우 사용자 수준 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-178">You can use tenant-wide settings to apply the same settings to all, or apply user-level policies if required.</span></span> 

<span data-ttu-id="5e108-179">팀 정책에 대 한 자세한 내용은 [조직의 Microsoft 팀 설정 관리](enable-features-office-365.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-179">For more details about Teams policies, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>
 
## <a name="can-i-control-what-external-parties-my-faculty-and-students-collaborate-with"></a><span data-ttu-id="5e108-180">교사와 학생이 공동 작업할 외부 당사자를 제어할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="5e108-180">Can I control what external parties my faculty and students collaborate with?</span></span>

<span data-ttu-id="5e108-181">게스트 액세스를 사용 하 여 테 넌 트 외부에서 사용자를 초대할 수 있으며,이를 통해 리서치 공동 작업 또는 게스트 강의에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-181">You can use guest access to invite users from outside of your tenant, which can be useful for research collaboration or guest lectures:</span></span>

-   <span data-ttu-id="5e108-182">도메인 whitelisting를 사용 하 여 도메인에 따라 게스트를 허용 하거나 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-182">Use domain whitelisting to allow or block guests based on their domain.</span></span>
-   <span data-ttu-id="5e108-183">특정 Office 365 그룹 및 팀에 대해 게스트 액세스를 설정 하거나 해제 하 여 게스트 초대를 수행할 수 있는 팀을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-183">Turn guest access on and off for particular Office 365 Groups and teams, to control which teams can (and can’t) invite guests.</span></span>
-   <span data-ttu-id="5e108-184">감사 로그를 사용 하 여 초대한 게스트에 게 전송 된 알림을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-184">Use the audit log to see which alerts were sent to invited guests.</span></span>

<span data-ttu-id="5e108-185">자세한 내용은 [Office 365 그룹의 게스트 액세스](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-185">For more information, see [Guest access in Office 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6#PickTab=Manage).</span></span>

## <a name="what-information-can-i-review-about-existing-teams"></a><span data-ttu-id="5e108-186">기존 팀에 대해 검토할 수 있는 정보</span><span class="sxs-lookup"><span data-stu-id="5e108-186">What information can I review about existing teams?</span></span>

<span data-ttu-id="5e108-187">감사 로그를 확인 하 여 다음을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-187">You can check the audit logs to see:</span></span>

-   <span data-ttu-id="5e108-188">누가 팀에 게 게스트로 초대를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-188">Who was invited as a guest to which team.</span></span>
-   <span data-ttu-id="5e108-189">누가 팀을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-189">Who created which team.</span></span>

<span data-ttu-id="5e108-190">자세한 내용은 [Microsoft 팀의 이벤트 감사 로그 검색](audit-log-events.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e108-190">For more information, see [Search the audit log for events in Microsoft Teams](audit-log-events.md).</span></span>

## <a name="teams-evolves-so-quickly-how-can-i-stay-up-to-date"></a><span data-ttu-id="5e108-191">팀이 빠르게 발전 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-191">Teams evolves so quickly.</span></span> <span data-ttu-id="5e108-192">최신 상태를 유지 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="5e108-192">How can I stay up-to-date?</span></span>

<span data-ttu-id="5e108-193">팀에 최신 업데이트를 받으려면 다음 리소스를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e108-193">We recommend the following resources to get the latest updates on Teams:</span></span>

-   [<span data-ttu-id="5e108-194">Microsoft 팀의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="5e108-194">What's new in Microsoft Teams</span></span>](https://support.office.com/article/What-s-new-in-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
-   [<span data-ttu-id="5e108-195">Microsoft 팀 블로그</span><span class="sxs-lookup"><span data-stu-id="5e108-195">Microsoft Teams blog</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)
