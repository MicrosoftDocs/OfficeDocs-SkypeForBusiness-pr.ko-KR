---
title: Microsoft 팀에서 StaffHub 팀을 교대으로 이동
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Microsoft 팀에서 Microsoft StaffHub 팀 및 일정 데이터를 이동 하는 방법에 대해 알아봅니다.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56f1501f0b9947ea009c6ebbf697a211dd1118ae
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2019
ms.locfileid: "36184571"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="c9e61-103">Microsoft 팀에서 Microsoft StaffHub 팀을 교대으로 옮기기</span><span class="sxs-lookup"><span data-stu-id="c9e61-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9e61-104">2019 년 10 월 1 일에 유효 합니다. Microsoft StaffHub는 곧 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="c9e61-105">Microsoft 팀에 StaffHub 접근 권한 값을 구축 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="c9e61-106">현재 팀에는 일정 관리를 위해 교대 근무 앱이 포함 되어 있으며 추가 기능이 시간에 따라 롤아웃 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="c9e61-107">StaffHub는 2019 년 10 월 1 일에 모든 사용자의 작동이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="c9e61-108">StaffHub를 열려고 하는 모든 사용자에 게 팀을 다운로드 하도록 지시 하는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="c9e61-109">자세한 내용은 [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)을 사용 중지 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="c9e61-110">팀에서 교대 근무 앱은 일정을 관리 하는 간단한 방법과 매일 수행 되는 교대 전환 및 취소의 일정 한 흐름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="c9e61-111">팀 구성원은 일정에 액세스 하 고, 앱 및 장치에서 직접 정보를 이동 하 여 기본 설정을 지정 하 고, 일정을 관리 하 고, 휴가를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="c9e61-112">이 문서에서는 팀에서 조직의 StaffHub 팀 및 일정 데이터를 이동 하는 방법을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="c9e61-113">설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-113">It covers:</span></span>

- [<span data-ttu-id="c9e61-114">팀으로 이동 하는 방법에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="c9e61-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="c9e61-115">대비</span><span class="sxs-lookup"><span data-stu-id="c9e61-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="c9e61-116">파일럿 실시</span><span class="sxs-lookup"><span data-stu-id="c9e61-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="c9e61-117">파일럿을 넘어서 모든 StaffHub 팀을 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="c9e61-118">팀 사용량 모니터링</span><span class="sxs-lookup"><span data-stu-id="c9e61-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="c9e61-119">해결사</span><span class="sxs-lookup"><span data-stu-id="c9e61-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="c9e61-120">하나 또는 두 개의 StaffHub 팀이 있는 중소기업이 고 수백 StaffHub 팀이 있는 대기업에 있든 관계 없이, 팀으로 전환 하는 데 도움이 되는 관리자 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="c9e61-121">이 문서에 나와 있는 단계를 수행 하려면 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="c9e61-122">아직 수행 하지 않은 경우 [StaffHub 만료 FAQ](microsoft-staffhub-to-be-retired.md) 를 참조 하 여 질문에 대 한 답을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="c9e61-123">팀으로 이동 하는 방법에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="c9e61-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="c9e61-124">팀으로 이동 하는 경우</span><span class="sxs-lookup"><span data-stu-id="c9e61-124">When to move to Teams</span></span>

<span data-ttu-id="c9e61-125">2019 년 10 월 1 일에 유효 하며, StaffHub가 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-125">Effective October 1, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="c9e61-126">지금 팀 사용을 시작 하 고 조직의 팀과 사용자를 StaffHub에서 전환 하기 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="c9e61-127">StaffHub에서 가장 일반적으로 사용 되는 기능으로 일정 관리를 사용 하는 경우 팀에서 이동 앱을 진행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="c9e61-128">팀으로 이동 하는 항목</span><span class="sxs-lookup"><span data-stu-id="c9e61-128">What is moved to Teams</span></span>

<span data-ttu-id="c9e61-129">StaffHub 팀을 이동 하면 팀 구성원, 사용자 세부 정보, 팀 일정 및 채팅 데이터가 팀으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="c9e61-130">StaffHub 팀을 이동할 때 파일이 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="c9e61-131">StaffHub 팀에 팀으로 이동 하려는 파일이 포함 되어 있는 경우 별도의 단계로 파일을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="c9e61-132">모든 StaffHub 팀에는 해당 하는 Office 365 그룹이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="c9e61-133">StaffHub 팀에 Office 365 그룹이 연결 되어 있지 않으면 전환을 지원할 수 있도록 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-133">If a StaffHub team doesn't have an Office 365 Group associated with it, one is automatically created for you to support the transition.</span></span> <span data-ttu-id="c9e61-134">팀과 StaffHub 간의 팀 및 그룹 명명 차이로 인해 팀에 다른 팀 이름이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-134">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span>

<span data-ttu-id="c9e61-135">StaffHub에서 팀으로 전환 하는 동안 사용자는 더 이상 StaffHub에서 해당 일정에 액세스할 수 없으며 팀에서 이동 하도록 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-135">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="c9e61-136">중단을 최소화 하 고 사용자가 팀을 채택 하 고 탐색 하도록 하는 것을 권장 하기 위해 조직에서이 변경 내용을 알릴 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-136">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="c9e61-137">Azure AD Premium을 사용 하는 경우 [보고서를 실행](run-report-to-show-staffhub-usage.md) 하 여 조직의 StaffHub 사용자 중 해당 변경 사항에 대해 알고 있어야 하는 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-137">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="c9e61-138">StaffHub 팀을 팀으로 이동한 후에는 롤백 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-138">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="c9e61-139">팀을 이동할 때의 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="c9e61-139">User experience when you move a team</span></span>

<span data-ttu-id="c9e61-140">팀이 StaffHub에서 전환 되는 경우 사용자에 대 한 가동 중지 (가능한 경우 두 번째이 하)는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-140">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="c9e61-141">사용자는 팀으로 이동이 완료 될 때까지 StaffHub를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-141">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="c9e61-142">이동이 완료 되 면 팀 구성원은 팀 일정에 액세스 하기 위해 팀의 교대 근무를 사용 해야 한다는 것을 알리는 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-142">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="c9e61-143">다음은 StaffHub 팀이 팀으로 이동한 후 사용자에 게 StaffHub에 표시 되는 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-143">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="c9e61-144">![사용자에 게 표시 되는 메시지의 예입니다.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "StaffHub 팀이 팀으로 이동한 후 사용자가 StaffHub에 표시 하는 메시지의 예")</span><span class="sxs-lookup"><span data-stu-id="c9e61-144">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="c9e61-145">대비</span><span class="sxs-lookup"><span data-stu-id="c9e61-145">Prepare</span></span>

<span data-ttu-id="c9e61-146">팀으로 이동 하기 위해 준비 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-146">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="c9e61-147">전제 조건이 충족 되는지 확인</span><span class="sxs-lookup"><span data-stu-id="c9e61-147">Check that prerequisites are met</span></span>

<span data-ttu-id="c9e61-148">StaffHub 팀을 팀으로 이동 하기 전에 다음을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-148">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="c9e61-149">로그인 한 사용자는 전역 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-149">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="c9e61-150">팀은 테 넌 트의 모든 사용자에 대해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-150">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="c9e61-151">테 넌 트에서 Office 365 그룹 만들기를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-151">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="c9e61-152">StaffHub teamId가 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-152">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="c9e61-153">StaffHub 팀은 구성원을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-153">The StaffHub team contains members.</span></span>
- <span data-ttu-id="c9e61-154">모든 StaffHub 팀 구성원은 Azure AD 계정에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-154">All StaffHub team members are linked to an Azure AD account.</span></span>

<span data-ttu-id="c9e61-155">이러한 선행 조건이 충족 되지 않으면 이동 요청이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-155">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="c9e61-156">팀 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="c9e61-156">Assign Teams licenses</span></span>

<span data-ttu-id="c9e61-157">각 사용자는 [적격 요금제](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) 에서 활성 Microsoft 365 또는 Office 365 라이선스를 보유 하 고 있어야 하며 팀 라이선스를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-157">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="c9e61-158">사용자에 게 팀 라이선스를 할당 하면 팀에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-158">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="c9e61-159">Microsoft 365 관리 센터에서 팀 라이선스를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-159">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c9e61-160">자세히 알아보려면 [팀에 대 한 사용자 액세스 관리](../../user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-160">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c9e61-161">조직에서 비즈니스용 Skype를 사용 하는 경우 모든 사용자를 팀으로 이동할 준비가 되지 않은 경우, 팀을 비즈니스용 Skype와 함께 실행할 수 있는 Firstline Worker에 대 한 팀을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-161">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="c9e61-162">*아일랜드*라는이 공존 모드에서는 각 클라이언트 앱이 별도의 솔루션으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-162">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="c9e61-163">자세한 내용은 [비즈니스용 Skype 공존 및 상호 운용성에 대해 팀 이해](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-163">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-staffhub-powershell-module"></a><span data-ttu-id="c9e61-164">StaffHub PowerShell 모듈 설치</span><span class="sxs-lookup"><span data-stu-id="c9e61-164">Install the StaffHub PowerShell module</span></span>

<span data-ttu-id="c9e61-165">아직 없는 경우 [StaffHub PowerShell 모듈을 설치](install-the-staffhub-powershell-module.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-165">If you haven't already, [install the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span> 

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="c9e61-166">StaffHub 팀 구성원에 대 한 Azure AD 계정 연결</span><span class="sxs-lookup"><span data-stu-id="c9e61-166">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="c9e61-167">각 StaffHub 팀 구성원은 Azure AD (Azure Active Directory) 계정에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-167">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="c9e61-168">다음 시나리오 중 하나가 적용 되는 경우 조직의 사용자는 Azure AD 계정에 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-168">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="c9e61-169">팀 소유자가 Azure AD 계정이 없는 사용자를 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-169">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="c9e61-170">팀 소유자가 사용자를 StaffHub 팀에 초대 했으며 해당 사용자가 초대를 수락 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-170">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="c9e61-171">이러한 사용자에 대 한 Azure AD 계정을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-171">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="c9e61-172">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-172">Here's how.</span></span>

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-linked-to-an-azure-ad-account"></a><span data-ttu-id="c9e61-173">Azure AD 계정에 연결 되지 않은 팀 구성원이 있는 StaffHub 팀의 모든 사용자 목록 가져오기</span><span class="sxs-lookup"><span data-stu-id="c9e61-173">Get a list of all users on StaffHub teams that have team members that aren't linked to an Azure AD account</span></span>

<span data-ttu-id="c9e61-174">다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-174">Run the following:</span></span>
```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="link-the-account"></a><span data-ttu-id="c9e61-175">계정 연결</span><span class="sxs-lookup"><span data-stu-id="c9e61-175">Link the account</span></span>

<span data-ttu-id="c9e61-176">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-176">Do one of the following:</span></span>

- <span data-ttu-id="c9e61-177">계정을 변환 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-177">Convert and link the account.</span></span>

  <span data-ttu-id="c9e61-178">StaffHub 팀 소유자 및 관리자는 사용자의 전자 메일 주소를 StaffHub 팀 설정 페이지에서 유효한 UPN으로 변경 하 여 비활성 계정을 변환 하 고 StaffHub의 Azure AD 계정에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-178">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="c9e61-179">연결 되지 않은 계정을 제거한 다음 UPN을 사용 하 여 계정을 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-179">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="c9e61-180">[StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet을 실행 하 여 StaffHub 팀에서 프로 비전 되지 않은 계정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-180">Run the [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="c9e61-181">[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet을 실행 하 여 UPN을 사용 하 여 StaffHub 팀에 계정을 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-181">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="c9e61-182">연결이 연결 되지 않은 사용자 계정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-182">Remove the unlinked user account.</span></span> <span data-ttu-id="c9e61-183">사용자 계정이 더 이상 필요 하지 않은 경우이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-183">Use this option the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="c9e61-184">사용자에 게 FirstlineWorker 앱 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c9e61-184">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="c9e61-185">팀에는 조직의 Firstline 작업자에 게 가장 중요 한 앱을 강조 표시 하도록 팀을 사용자 지정 하는 데 사용할 수 있는 기본 제공 FirstlineWorker 앱 설정 정책이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-185">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="c9e61-186">이 정책을 사용자에 게 할당 하면, 정책의 앱이 팀의 앱 표시줄에 고정 되므로 빠르고 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-186">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="c9e61-187">팀에 추가 된 다른 앱은 앱 표시줄에서 다음을 클릭 하 여 찾을 수 있습니다. \*\* \*\*팀 데스크톱 및 웹 클라이언트의 앱이 더 있고 팀 모바일 클라이언트에서 위로 살짝 밀어 보세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-187">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="c9e61-188">기본적으로 FirstlineWorker 앱 설정 정책에는 활동, 교대, 채팅 및 통화 앱이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-188">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="c9e61-189">FirstlineWorker 앱 설치 정책을 사용자에 게 할당 하는 방법에 대 한 단계는 [FirstlineWorker 앱 설정 정책을 사용 하 여 팀에 고정](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-189">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="c9e61-190">정책을 할당 하면 적용 되는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-190">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="c9e61-191">StaffHub 팀 이나 사용자를 팀으로 이동 하기 전에 적어도 일주일에이 단계를 완료 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-191">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="c9e61-192">팀에 속한 사용자는 교대 근무 앱을 보고 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-192">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="c9e61-193">사용자 지정 앱 설정 정책을 만들고 전역 앱 설정 정책에서 설정을 편집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-193">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="c9e61-194">자세한 내용은 [팀에서 앱 설치 정책 관리](../../teams-app-setup-policies.md)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-194">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="c9e61-195">팀에 대 한 온보드 사용자</span><span class="sxs-lookup"><span data-stu-id="c9e61-195">Onboard users to Teams</span></span>

<span data-ttu-id="c9e61-196">온 보 딩 전략의 일부로 팀에 익숙해질 수 있도록 사용자에 게 교육 및 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-196">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="c9e61-197">팀 클라이언트, 교육 및 지원을 받을 위치를 알 수 있도록 다음 리소스를 사용자와 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-197">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="c9e61-198">팀 웹 클라이언트</span><span class="sxs-lookup"><span data-stu-id="c9e61-198">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="c9e61-199">데스크톱 및 모바일 클라이언트 다운로드 링크</span><span class="sxs-lookup"><span data-stu-id="c9e61-199">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="c9e61-200">팀 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="c9e61-200">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="c9e61-201">팀 도움말 문서</span><span class="sxs-lookup"><span data-stu-id="c9e61-201">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="c9e61-202">팀 및 운전 팀 채택을 배포 하는 방법에 대 한 지침은 팀을 롤 포워드 하 고 [팀을 채택](../../adopt-microsoft-teams-landing-page.md)하 [는 방법을](../../How-to-roll-out-teams.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-202">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="c9e61-203">파일럿 실시</span><span class="sxs-lookup"><span data-stu-id="c9e61-203">Conduct a pilot</span></span>

<span data-ttu-id="c9e61-204">최초 사용자의 선택 그룹을 위해 2 개 또는 3 개의 StaffHub 팀부터 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-204">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="c9e61-205">파일럿을 실행 하면 전환 계획을 개선 하 고 조직의 모든 StaffHub 팀을 팀으로 이동할 준비가 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-205">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="c9e61-206">또한 조직에서 채택을 간편 하 게 할 수 있는 챔피언 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-206">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="c9e61-207">단계별 접근 방법이 필요 하지 않은 중소 기업 이라면이 섹션의 단계를 StaffHub에서 팀으로 전환 하는 것이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-207">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="c9e61-208">파일럿 팀 식별</span><span class="sxs-lookup"><span data-stu-id="c9e61-208">Identify pilot teams</span></span>

<span data-ttu-id="c9e61-209">2 명 또는 세 명의 파일럿 팀을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-209">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="c9e61-210">모든 팀 구성원은 팀의 교대 근무를 사용 하 여 일정을 관리 하 고 서로와 통신 하 고 공동 작업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-210">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="c9e61-211">팀 챔피언 확인</span><span class="sxs-lookup"><span data-stu-id="c9e61-211">Identify team champions</span></span>

<span data-ttu-id="c9e61-212">파일럿 팀에서 챔피언를 식별 하 고 참여 하 여 evangelize 교대 근무를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-212">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="c9e61-213">팀 챔피언 자신의 학습이을 공유 하 여 팀 구성원에 게 지원 및 지침을 제공 하는 것에 대해 열정.</span><span class="sxs-lookup"><span data-stu-id="c9e61-213">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="c9e61-214">팀 챔피언 팀 소유자 또는 관리자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-214">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="c9e61-215">팀 챔피언 모든 사람이 [팀 클라이언트를 확보](../../get-clients.md)하 고, 팀에 로그인 하 고, 일정을 교대에서 확인 하 고, 서로 채팅을 시작 하도록 시간을 설정 하는 것을 보장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-215">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="c9e61-216">이미 StaffHub에 익숙한 사용자는 이동 중에 빠르게 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-216">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="c9e61-217">또한 [도움말](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) 을 가리키면 추가 도움말을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-217">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="c9e61-218">StaffHub 팀 이동</span><span class="sxs-lookup"><span data-stu-id="c9e61-218">Move a StaffHub team</span></span>

<span data-ttu-id="c9e61-219">이 단계를 사용 하 여 한 번에 한 StaffHub 팀을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-219">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="c9e61-220">파일럿 팀에이 접근 방법을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-220">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="c9e61-221">나중에 조직의 모든 StaffHub 팀을 이동할 준비가 되 면 여러 팀을 한 번에 이동 하는 방법에 대 한 단계에 대해 [StaffHub 팀 이동을](#move-your-staffhub-teams) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-221">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="c9e61-222">다음을 실행 하 여 StaffHub 팀을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-222">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="c9e61-223">예</span><span class="sxs-lookup"><span data-stu-id="c9e61-223">Example:</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="c9e61-224">다음은 StaffHub 팀을 팀으로 이동 하는 요청을 제출할 때 표시 되는 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-224">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="c9e61-225">이동 요청의 상태를 확인 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-225">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="c9e61-226">예</span><span class="sxs-lookup"><span data-stu-id="c9e61-226">Example:</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="c9e61-227">다음은 이동을 진행 하는 동안 받은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-227">Here's an example of the response you get when a move is in progress.</span></span>

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="c9e61-228">StaffHub 팀에서 팀으로 파일 이동</span><span class="sxs-lookup"><span data-stu-id="c9e61-228">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="c9e61-229">이 단계는 팀으로 이동한 StaffHub 팀에 게 팀으로 이동 하려는 파일이 있는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-229">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="c9e61-230">SharePoint Online 또는 PowerShell을 사용 하 여 파일을 직접 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-230">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="c9e61-231">SharePoint Online에서</span><span class="sxs-lookup"><span data-stu-id="c9e61-231">In SharePoint Online</span></span>

<span data-ttu-id="c9e61-232">[SharePoint Online에서 파일을 이동 하는 방법](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-232">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="c9e61-233">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="c9e61-233">Using PowerShell</span></span>

<span data-ttu-id="c9e61-234">아직 없는 경우 [SharePoint Online 관리 셸을](https://www.microsoft.com/download/details.aspx?id=35588)다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-234">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="c9e61-235">파일을 이동 하는 데 필요한 cmdlet이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-235">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="c9e61-236">SharePoint Online 팀 사이트에 연결 하려면 [PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-236">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="c9e61-237">StaffHub에서 팀으로 이동 하려는 각 파일에 대해 [move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet을 사용 하 여 파일을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-237">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="c9e61-238">여러 파일을 이동 하려면 파일을 순환 하면서 루프에서 두 번째 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-238">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="c9e61-239">세션이 활성 상태를 유지 하는 경우 첫 번째 명령을 반복할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-239">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="c9e61-240">파일럿을 넘어서 모든 StaffHub 팀을 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-240">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="c9e61-241">인식 발생</span><span class="sxs-lookup"><span data-stu-id="c9e61-241">Raise awareness</span></span>

<span data-ttu-id="c9e61-242">파일럿 팀으로 이동 하 고 조직의 StaffHub 팀을 팀으로 이동할 준비가 되 면 먼저 조직 전반에 변경 내용을 전달 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-242">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="c9e61-243">이동 및 팀으로 전환에 대 한 단어를 분산 하 여 인식, 흥미로운 생성, 드라이브 채택을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-243">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="c9e61-244">StaffHub 팀 이동</span><span class="sxs-lookup"><span data-stu-id="c9e61-244">Move your StaffHub teams</span></span>

<span data-ttu-id="c9e61-245">StaffHub 팀을 대량으로 이동 하려면 다음 단계를 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-245">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="c9e61-246">조직의 StaffHub 팀을 모두 이동 하거나 특정 StaffHub 팀을 이동 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-246">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="c9e61-247">StaffHub 팀을 한 번에 하나씩 이동 하려면 [StaffHub 팀 이동을](#move-a-staffhub-team)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-247">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="c9e61-248">모든 StaffHub 팀 이동</span><span class="sxs-lookup"><span data-stu-id="c9e61-248">Move all StaffHub teams</span></span>

<span data-ttu-id="c9e61-249">다음을 실행 하 여 조직의 모든 StaffHub 팀 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-249">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

<span data-ttu-id="c9e61-250">모든 팀을 이동 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-250">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="c9e61-251">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-251">Here's an example of the response.</span></span>

<span data-ttu-id="c9e61-252">이미 팀으로 이동 하거나 팀에 이미 있는 팀의 경우, 해당 팀을 이동 하기 위해 작업을 제출할 필요가 없으므로 jobId는 "null"이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-252">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="c9e61-253">특정 StaffHub 팀 이동</span><span class="sxs-lookup"><span data-stu-id="c9e61-253">Move specific StaffHub teams</span></span>

<span data-ttu-id="c9e61-254">조직의 모든 StaffHub 팀 Id 목록을 가져오려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-254">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="c9e61-255">이전에 실행 한 `Get-StaffHubteamsForTenant` cmdlet에서 반환 된 결과에서 이동 하려는 팀 id를 선택한 다음 CSV (쉼표로 구분 된 값) 파일에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-255">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="c9e61-256">다음은 CSV 파일의 서식을 지정 하는 방법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-256">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="c9e61-257">I</span><span class="sxs-lookup"><span data-stu-id="c9e61-257">Id</span></span>  |
|---------|
|<span data-ttu-id="c9e61-258">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="c9e61-258">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="c9e61-259">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="c9e61-259">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="c9e61-260">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="c9e61-260">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="c9e61-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="c9e61-261">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="c9e61-262">CSV 파일을 만든 후 다음을 실행 하 여 CSV 파일에서 지정한 팀을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-262">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="c9e61-263">StaffHub 팀이 팀으로 이동 했는지 확인</span><span class="sxs-lookup"><span data-stu-id="c9e61-263">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="c9e61-264">다음을 실행 하 여 조직에서 모든 팀의 변화에 대 한 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-264">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="c9e61-265">StaffHub 팀에서 팀으로 파일 이동</span><span class="sxs-lookup"><span data-stu-id="c9e61-265">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="c9e61-266">이동한 StaffHub 팀에 팀으로 이동 하려는 파일이 포함 되어 있는 경우 [StaffHub 팀에서 팀으로 파일 이동을](#move-files-from-a-staffhub-team-to-teams)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-266">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="c9e61-267">팀 사용량 모니터링</span><span class="sxs-lookup"><span data-stu-id="c9e61-267">Monitor Teams usage</span></span>

<span data-ttu-id="c9e61-268">사용 현황 보고서를 통해 사용 패턴을 보다 잘 이해 하 고 조직의 교육 및 통신 작업에 대 한 우선 순위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-268">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="c9e61-269">전체 팀 사용, 팀에서 사용자가 수행 하는 작업 유형, 사용자가 팀에 연결 하는 방법 등에 대 한 보고서를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-269">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="c9e61-270">자세한 내용은 [microsoft 365 관리 센터의](../../teams-activity-reports.md) [microsoft 팀 관리 센터](../../teams-analytics-and-reports/teams-reporting-reference.md) 및 팀 활동 보고서에서 팀 보고를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9e61-270">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c9e61-271">해결사</span><span class="sxs-lookup"><span data-stu-id="c9e61-271">Troubleshooting</span></span>

<span data-ttu-id="c9e61-272">**파일을 StaffHub에서 팀으로 이동 하려고 하면 "사용 권한 거부 됨" 오류 메시지가 표시 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="c9e61-272">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="c9e61-273">구성원이 아닌 개인 Office 365 그룹의 파일을 이동 하려는 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-273">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="c9e61-274">이 경우 [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet을 사용 하 여 자신을 StaffHub 팀에 추가한 다음 파일을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-274">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="c9e61-275">파일을 이동한 후 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet을 사용 하 여 팀에서 자신을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-275">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="c9e61-276">**파일을 StaffHub에서 팀으로 이동 하려고 하면 일반 폴더가 없다는 오류 메시지가 나타납니다.**</span><span class="sxs-lookup"><span data-stu-id="c9e61-276">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="c9e61-277">다음 명령을 실행 하 여 SharePoint에 일반 폴더를 추가한 다음 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9e61-277">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="c9e61-278">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c9e61-278">Related topics</span></span>
- [<span data-ttu-id="c9e61-279">Microsoft 팀을 배포 하는 방법</span><span class="sxs-lookup"><span data-stu-id="c9e61-279">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="c9e61-280">Microsoft StaffHub 사용 중지</span><span class="sxs-lookup"><span data-stu-id="c9e61-280">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="c9e61-281">Microsoft 팀에서 조직의 교대 근무 앱 관리</span><span class="sxs-lookup"><span data-stu-id="c9e61-281">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="c9e61-282">StaffHub PowerShell 참조</span><span class="sxs-lookup"><span data-stu-id="c9e61-282">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
