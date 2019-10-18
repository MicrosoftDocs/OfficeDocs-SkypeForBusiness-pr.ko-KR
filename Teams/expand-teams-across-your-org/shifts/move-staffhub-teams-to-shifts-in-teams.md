---
title: Microsoft 팀에서 StaffHub 팀을 교대으로 이동
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft 팀에서 Microsoft StaffHub 팀 및 일정 데이터를 이동 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03131bd9a89ae5f54fc8318b004385de3e32e26e
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569685"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a><span data-ttu-id="22341-103">Microsoft 팀에서 Microsoft StaffHub 팀을 교대으로 옮기기</span><span class="sxs-lookup"><span data-stu-id="22341-103">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22341-104">2019 년 12 월 31 일에 효력을 StaffHub Microsoft는 곧 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="22341-105">Microsoft 팀에 StaffHub 접근 권한 값을 구축 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="22341-106">현재 팀에는 일정 관리를 위해 교대 근무 앱이 포함 되어 있으며 추가 기능이 시간에 따라 롤아웃 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="22341-107">StaffHub는 2019 년 12 월 31 일에 모든 사용자의 작동이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="22341-108">StaffHub를 열려고 하는 모든 사용자에 게 팀을 다운로드 하도록 지시 하는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="22341-109">자세한 내용은 [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)을 사용 중지 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>

<span data-ttu-id="22341-110">팀에서 교대 근무 앱은 일정을 관리 하는 간단한 방법과 매일 수행 되는 교대 전환 및 취소의 일정 한 흐름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-110">The Shifts app in Teams provides a simple approach to managing schedules and the constant flow of shift swaps and cancellations that occur on a daily basis.</span></span> <span data-ttu-id="22341-111">팀 구성원은 일정에 액세스 하 고, 앱 및 장치에서 직접 정보를 이동 하 여 기본 설정을 지정 하 고, 일정을 관리 하 고, 휴가를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-111">Team members can access their schedule and shift information directly in the app and across their devices to set their preferences, manage their schedules, and request time off.</span></span>

<span data-ttu-id="22341-112">이 문서에서는 팀에서 조직의 StaffHub 팀 및 일정 데이터를 이동 하는 방법을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-112">This article walks you through how to move your organization’s StaffHub teams and schedule data to Shifts in Teams.</span></span> <span data-ttu-id="22341-113">설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-113">It covers:</span></span>

- [<span data-ttu-id="22341-114">팀으로 이동 하는 방법에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="22341-114">What you need to know about the move to Teams</span></span>](#what-you-need-to-know-about-the-move-to-teams)
- [<span data-ttu-id="22341-115">대비</span><span class="sxs-lookup"><span data-stu-id="22341-115">Prepare</span></span>](#prepare)
- [<span data-ttu-id="22341-116">파일럿 실시</span><span class="sxs-lookup"><span data-stu-id="22341-116">Conduct a pilot</span></span>](#conduct-a-pilot) 
- [<span data-ttu-id="22341-117">파일럿을 넘어서 모든 StaffHub 팀을 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-117">Go beyond your pilot and move all StaffHub teams</span></span>](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [<span data-ttu-id="22341-118">팀 사용량 모니터링</span><span class="sxs-lookup"><span data-stu-id="22341-118">Monitor Teams usage</span></span>](#monitor-teams-usage)
- [<span data-ttu-id="22341-119">해결사</span><span class="sxs-lookup"><span data-stu-id="22341-119">Troubleshooting</span></span>](#troubleshooting)

<span data-ttu-id="22341-120">하나 또는 두 개의 StaffHub 팀이 있는 중소기업이 고 수백 StaffHub 팀이 있는 대기업에 있든 관계 없이, 팀으로 전환 하는 데 도움이 되는 관리자 지침을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-120">Whether you’re a small business with one or two StaffHub teams or a large enterprise with hundreds of StaffHub teams, here you’ll find the admin guidance you need to help make your transition to Teams successful.</span></span>

<span data-ttu-id="22341-121">이 문서에 나와 있는 단계를 수행 하려면 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-121">You must be a global admin to perform the steps in this article.</span></span> <span data-ttu-id="22341-122">아직 수행 하지 않은 경우 [StaffHub 만료 FAQ](microsoft-staffhub-to-be-retired.md) 를 참조 하 여 질문에 대 한 답을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-122">If you haven't already done so, have a look through the [StaffHub retirement FAQ](microsoft-staffhub-to-be-retired.md) to get answers to any questions you may have.</span></span>

## <a name="what-you-need-to-know-about-the-move-to-teams"></a><span data-ttu-id="22341-123">팀으로 이동 하는 방법에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="22341-123">What you need to know about the move to Teams</span></span>

### <a name="when-to-move-to-teams"></a><span data-ttu-id="22341-124">팀으로 이동 하는 경우</span><span class="sxs-lookup"><span data-stu-id="22341-124">When to move to Teams</span></span>

<span data-ttu-id="22341-125">2019 년 12 월 31 일에 효력을 StaffHub 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-125">Effective December 31, 2019, StaffHub will be retired.</span></span> <span data-ttu-id="22341-126">지금 팀 사용을 시작 하 고 조직의 팀과 사용자를 StaffHub에서 전환 하기 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-126">We encourage you to start using Teams today and begin to transition your organization's teams and users from StaffHub.</span></span> <span data-ttu-id="22341-127">StaffHub에서 가장 일반적으로 사용 되는 기능으로 일정 관리를 사용 하는 경우 팀에서 이동 앱을 진행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-127">With schedule management being the most commonly-used feature in StaffHub, we recommend you use the Shifts app in Teams moving forward.</span></span>

### <a name="what-is-moved-to-teams"></a><span data-ttu-id="22341-128">팀으로 이동 하는 항목</span><span class="sxs-lookup"><span data-stu-id="22341-128">What is moved to Teams</span></span>

<span data-ttu-id="22341-129">StaffHub 팀을 이동 하면 팀 구성원, 사용자 세부 정보, 팀 일정 및 채팅 데이터가 팀으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-129">When you move a StaffHub team, team membership, user details, team schedules, and chat data are moved to Teams.</span></span> <span data-ttu-id="22341-130">StaffHub 팀을 이동할 때 파일이 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-130">Files aren't moved when you move a StaffHub team.</span></span> <span data-ttu-id="22341-131">StaffHub 팀에 팀으로 이동 하려는 파일이 포함 되어 있는 경우 별도의 단계로 파일을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-131">If a StaffHub team contains files that you also want to move to teams, you move the files in a separate step.</span></span>

<span data-ttu-id="22341-132">모든 StaffHub 팀에는 해당 하는 Office 365 그룹이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-132">Every StaffHub team needs a corresponding Office 365 Group.</span></span> <span data-ttu-id="22341-133">StaffHub 팀이 Office 365 그룹과 연결 된 경우 팀을 이동할 때 그룹의 개인 정보 설정이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-133">If a StaffHub team is associated with an Office 365 Group, the privacy setting of the group is retained when you move the team.</span></span> <span data-ttu-id="22341-134">StaffHub 팀에 Office 365 그룹이 연결 되어 있지 않은 경우 개인 정보 보호 설정이 있는 그룹이 전환을 지원할 수 있도록 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="22341-134">If a StaffHub team doesn't have an Office 365 Group associated with it, a group with a privacy setting of Private is automatically created for you to support the transition.</span></span>  <span data-ttu-id="22341-135">팀과 StaffHub 간의 팀 및 그룹 명명 차이로 인해 팀에 다른 팀 이름이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-135">Given the difference in team and group naming between Teams and StaffHub, you may see a different team name in Teams.</span></span> 

<span data-ttu-id="22341-136">StaffHub에서 팀으로 전환 하는 동안 사용자는 더 이상 StaffHub에서 해당 일정에 액세스할 수 없으며 팀에서 이동 하도록 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-136">As you transition teams from StaffHub to Teams, users will no longer have access to their schedules in StaffHub and are redirected to Shifts in Teams.</span></span> <span data-ttu-id="22341-137">중단을 최소화 하 고 사용자가 팀을 채택 하 고 탐색 하도록 하는 것을 권장 하기 위해 조직에서이 변경 내용을 알릴 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-137">We recommend you communicate this change across your organization to minimize disruption and to encourage users to adopt and explore Teams.</span></span> <span data-ttu-id="22341-138">Azure AD Premium을 사용 하는 경우 [보고서를 실행](run-report-to-show-staffhub-usage.md) 하 여 조직의 StaffHub 사용자 중 해당 변경 사항에 대해 알고 있어야 하는 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-138">If you have Azure AD Premium, you can [run a report](run-report-to-show-staffhub-usage.md) to get a list of StaffHub users in your organization who need to know about this change.</span></span>  

<span data-ttu-id="22341-139">StaffHub 팀을 팀으로 이동한 후에는 롤백 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-139">There's no rollback option after you move a StaffHub team to Teams.</span></span>

### <a name="user-experience-when-you-move-a-team"></a><span data-ttu-id="22341-140">팀을 이동할 때의 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="22341-140">User experience when you move a team</span></span>

<span data-ttu-id="22341-141">팀이 StaffHub에서 전환 되는 경우 사용자에 대 한 가동 중지 (가능한 경우 두 번째이 하)는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-141">There's minimal downtime (less than a second, if any at all) for users when their team is switched from StaffHub to Shifts in Teams.</span></span> <span data-ttu-id="22341-142">사용자는 팀으로 이동이 완료 될 때까지 StaffHub를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-142">Users can continue using StaffHub until the move to Teams is completed.</span></span> <span data-ttu-id="22341-143">이동이 완료 되 면 팀 구성원은 팀 일정에 액세스 하기 위해 팀의 교대 근무를 사용 해야 한다는 것을 알리는 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-143">When the move is completed, team members will see a message to let them know that they need to start using Shifts in Teams to access their team schedule.</span></span> <span data-ttu-id="22341-144">다음은 StaffHub 팀이 팀으로 이동한 후 사용자에 게 StaffHub에 표시 되는 메시지의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="22341-144">Here's an example of the message that users see in StaffHub after the StaffHub team is moved to Teams.</span></span>

<span data-ttu-id="22341-145">![사용자에 게 표시 되는 메시지의 예입니다.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "StaffHub 팀이 팀으로 이동한 후 사용자가 StaffHub에 표시 하는 메시지의 예")</span><span class="sxs-lookup"><span data-stu-id="22341-145">![Example of the message that users see.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Example of the message that users see in StaffHub after the StaffHub team is moved to Teams")</span></span>

## <a name="prepare"></a><span data-ttu-id="22341-146">대비</span><span class="sxs-lookup"><span data-stu-id="22341-146">Prepare</span></span>

<span data-ttu-id="22341-147">팀으로 이동 하기 위해 준비 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-147">Here's how to prepare for the move to Teams.</span></span>

### <a name="check-that-prerequisites-are-met"></a><span data-ttu-id="22341-148">전제 조건이 충족 되는지 확인</span><span class="sxs-lookup"><span data-stu-id="22341-148">Check that prerequisites are met</span></span>

<span data-ttu-id="22341-149">StaffHub 팀을 팀으로 이동 하기 전에 다음을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-149">Before you move a StaffHub team to Teams, make sure that:</span></span>

- <span data-ttu-id="22341-150">로그인 한 사용자는 전역 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="22341-150">The signed-in user is a global admin.</span></span>
- <span data-ttu-id="22341-151">팀은 테 넌 트의 모든 사용자에 대해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-151">Teams is enabled for all users in the tenant.</span></span>
- <span data-ttu-id="22341-152">테 넌 트에서 Office 365 그룹 만들기를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-152">Office 365 Groups creation is enabled in the tenant.</span></span>
- <span data-ttu-id="22341-153">StaffHub teamId가 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-153">The StaffHub teamId is valid.</span></span>
- <span data-ttu-id="22341-154">StaffHub 팀에 팀 소유자가 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-154">The StaffHub team has at least one team owner.</span></span>
- <span data-ttu-id="22341-155">StaffHub 팀은 구성원을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-155">The StaffHub team contains members.</span></span>
- <span data-ttu-id="22341-156">모든 StaffHub 팀 구성원은 Azure AD 계정에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-156">All StaffHub team members are linked to an Azure AD account.</span></span>
- <span data-ttu-id="22341-157">모든 StaffHub 팀 구성원에 게 팀 라이선스가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-157">All StaffHub team members are assigned a Teams license.</span></span>  

<span data-ttu-id="22341-158">이러한 선행 조건이 충족 되지 않으면 이동 요청이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-158">If these prerequisites aren't met, the move request will fail.</span></span>

### <a name="assign-teams-licenses"></a><span data-ttu-id="22341-159">팀 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="22341-159">Assign Teams licenses</span></span>

<span data-ttu-id="22341-160">각 사용자는 [적격 요금제](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) 에서 활성 Microsoft 365 또는 Office 365 라이선스를 보유 하 고 있어야 하며 팀 라이선스를 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-160">Each user must have an active Microsoft 365 or Office 365 license from [an eligible plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) and must be assigned a Teams license.</span></span> <span data-ttu-id="22341-161">사용자에 게 팀 라이선스를 할당 하면 팀에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-161">Assigning a Teams license to users gives them access to Teams.</span></span>

<span data-ttu-id="22341-162">Microsoft 365 관리 센터에서 팀 라이선스를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-162">You manage Teams licenses in the Microsoft 365 admin center.</span></span> <span data-ttu-id="22341-163">자세히 알아보려면 [팀에 대 한 사용자 액세스 관리](../../user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-163">To learn more, see [Manage user access to Teams](../../user-access.md).</span></span>

> [!NOTE]
> <span data-ttu-id="22341-164">조직에서 비즈니스용 Skype를 사용 하는 경우 모든 사용자를 팀으로 이동할 준비가 되지 않은 경우, 팀을 비즈니스용 Skype와 함께 실행할 수 있는 Firstline Worker에 대 한 팀을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-164">If your organization uses Skype for Business and you’re not ready to move all your users to Teams, you can enable Teams for your Firstline Workers who can then run Teams alongside Skype for Business.</span></span> <span data-ttu-id="22341-165">*아일랜드*라는이 공존 모드에서는 각 클라이언트 앱이 별도의 솔루션으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-165">In this coexistence mode, called *Islands*, each client app operates as a separate solution.</span></span> <span data-ttu-id="22341-166">자세한 내용은 [비즈니스용 Skype 공존 및 상호 운용성에 대해 팀 이해](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-166">To learn more, see [Understand Teams and Skype for Business coexistence and interoperability](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a><span data-ttu-id="22341-167">StaffHub PowerShell 모듈의 시험판 버전을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-167">Install the prerelease version of the StaffHub PowerShell module</span></span>

<span data-ttu-id="22341-168">아직 설치 하지 않은 경우 [StaffHub PowerShell 모듈의 시험판 버전을 설치](install-the-staffhub-powershell-module.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-168">If you haven't already, [install the prerelease version of the StaffHub PowerShell module](install-the-staffhub-powershell-module.md).</span></span>

<span data-ttu-id="22341-169">StaffHub 팀을 팀으로 이동 하려면 시험판 버전의 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-169">You must have the prerelease version of the module installed to move your StaffHub teams to Teams.</span></span>

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a><span data-ttu-id="22341-170">StaffHub 팀 구성원에 대 한 Azure AD 계정 연결</span><span class="sxs-lookup"><span data-stu-id="22341-170">Link an Azure AD account for StaffHub team members who don't have one</span></span>

<span data-ttu-id="22341-171">각 StaffHub 팀 구성원은 Azure AD (Azure Active Directory) 계정에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-171">Each StaffHub team member must be linked to an Azure Active Directory (Azure AD) account.</span></span> <span data-ttu-id="22341-172">다음 시나리오 중 하나가 적용 되는 경우 조직의 사용자는 Azure AD 계정에 연결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-172">Users in your organization won't be linked to an Azure AD account if any of the following scenarios apply:</span></span>

- <span data-ttu-id="22341-173">팀 소유자가 Azure AD 계정이 없는 사용자를 추가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-173">A team owner added a user who doesn't have an Azure AD account.</span></span>
- <span data-ttu-id="22341-174">팀 소유자가 사용자를 StaffHub 팀에 초대 했으며 해당 사용자가 초대를 수락 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-174">A team owner invited a user to a StaffHub team and that user didn't accept the invitation.</span></span>

<span data-ttu-id="22341-175">이러한 사용자는 비활성 계정이 있으며 알 수 없음, 초대 또는 InviteRejected 사용자 상태를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-175">These users have inactive accounts and show a user state of Unknown, Invited, or InviteRejected.</span></span> <span data-ttu-id="22341-176">이러한 사용자에 대 한 Azure AD 계정을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-176">You can link an Azure AD account for these users.</span></span>  <span data-ttu-id="22341-177">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-177">Here's how.</span></span>

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a><span data-ttu-id="22341-178">StaffHub 팀의 모든 비활성 계정 목록 가져오기</span><span class="sxs-lookup"><span data-stu-id="22341-178">Get a list of all inactive accounts on StaffHub teams</span></span>

<span data-ttu-id="22341-179">다음을 실행 하 여 StaffHub 팀의 모든 비활성 계정 목록을 가져오고 목록을 CSV 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="22341-179">Run the following to get a list of all inactive accounts on StaffHub teams and export the list to a CSV file.</span></span>

```
$InvitedUsersObject = @()
$StaffHubTeams = Get-StaffHubTeamsForTenant $StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
foreach($team in $StaffHubTeams[0]) { write-host $team.name $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{         "TeamID"="$($team.Id)"         "TeamName"="$($team.name)"         "MemberID"="$($StaffHubUser.Id)" }
}
}
$InvitedUsersObject | SELECT * $InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a><span data-ttu-id="22341-180">계정 연결</span><span class="sxs-lookup"><span data-stu-id="22341-180">Link the account</span></span>

<span data-ttu-id="22341-181">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-181">Do one of the following:</span></span>

- <span data-ttu-id="22341-182">계정을 변환 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-182">Convert and link the account.</span></span>

  <span data-ttu-id="22341-183">StaffHub 팀 소유자 및 관리자는 사용자의 전자 메일 주소를 StaffHub 팀 설정 페이지에서 유효한 UPN으로 변경 하 여 비활성 계정을 변환 하 고 StaffHub의 Azure AD 계정에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-183">StaffHub team owners and managers can convert an inactive account and link it to an Azure AD account in StaffHub by changing the user's email address to a valid UPN on the StaffHub team settings page.</span></span>

- <span data-ttu-id="22341-184">연결 되지 않은 계정을 제거한 다음 UPN을 사용 하 여 계정을 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-184">Remove the unlinked account and then re-add the account by using the UPN.</span></span>
    1. <span data-ttu-id="22341-185">[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet을 실행 하 여 StaffHub 팀에서 프로 비전 되지 않은 계정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-185">Run the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet to remove the non-provisioned account from the StaffHub team.</span></span>
    2. <span data-ttu-id="22341-186">[StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet을 실행 하 여 UPN을 사용 하 여 StaffHub 팀에 계정을 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-186">Run the [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet to add the account back to the StaffHub team by using the UPN.</span></span>

- <span data-ttu-id="22341-187">비활성 계정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-187">Remove the inactive account.</span></span> <span data-ttu-id="22341-188">사용자 계정이 더 이상 필요 하지 않은 경우이 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-188">Use this option if the user account is no longer needed.</span></span>

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a><span data-ttu-id="22341-189">사용자에 게 FirstlineWorker 앱 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="22341-189">Assign the FirstlineWorker app setup policy to users</span></span>

<span data-ttu-id="22341-190">팀에는 조직의 Firstline 작업자에 게 가장 중요 한 앱을 강조 표시 하도록 팀을 사용자 지정 하는 데 사용할 수 있는 기본 제공 FirstlineWorker 앱 설정 정책이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-190">Teams includes a built-in FirstlineWorker app setup policy that you can use to customize Teams to highlight the apps that are most important for the Firstline Workers in your organization.</span></span> <span data-ttu-id="22341-191">이 정책을 사용자에 게 할당 하면, 정책의 앱이 팀의 앱 표시줄에 고정 되므로 빠르고 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-191">When you assign this policy to users, the apps in the policy are pinned to the app bar in Teams for quick and easy access.</span></span> <span data-ttu-id="22341-192">팀에 추가 된 다른 앱은 앱 표시줄에서 다음을 클릭 하 여 찾을 수 \*\*있습니다. \*\*팀 데스크톱 및 웹 클라이언트의 앱이 더 있고 팀 모바일 클라이언트에서 위로 살짝 밀어 보세요.</span><span class="sxs-lookup"><span data-stu-id="22341-192">Other apps added to Teams can be found in the app bar by clicking **... More apps** in the Teams desktop and web clients and by swiping up in the Teams mobile client.</span></span> <span data-ttu-id="22341-193">기본적으로 FirstlineWorker 앱 설정 정책에는 활동, 교대, 채팅 및 통화 앱이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-193">By default, the FirstlineWorker app setup policy includes the Activity, Shifts, Chat, and Calling apps.</span></span>

<span data-ttu-id="22341-194">FirstlineWorker 앱 설치 정책을 사용자에 게 할당 하는 방법에 대 한 단계는 [FirstlineWorker 앱 설정 정책을 사용 하 여 팀에 고정](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-194">For steps on how to assign the FirstlineWorker app setup policy to users, see [Use the FirstlineWorker app setup policy to pin Shifts to Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams).</span></span> <span data-ttu-id="22341-195">정책을 할당 하면 적용 되는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-195">After you assign a policy, it can take up to 24 hours to take effect.</span></span>

<span data-ttu-id="22341-196">StaffHub 팀 이나 사용자를 팀으로 이동 하기 전에 적어도 일주일에이 단계를 완료 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-196">We recommend you complete this step at least a week before you move your StaffHub teams and users to Teams.</span></span> <span data-ttu-id="22341-197">팀에 속한 사용자는 교대 근무 앱을 보고 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-197">When users are on Teams, confirm that they can see and access the Shifts app.</span></span>

<span data-ttu-id="22341-198">사용자 지정 앱 설정 정책을 만들고 전역 앱 설정 정책에서 설정을 편집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-198">You can also create custom app setup policies and edit the settings in the global app setup policy.</span></span> <span data-ttu-id="22341-199">자세한 내용은 [팀에서 앱 설치 정책 관리](../../teams-app-setup-policies.md)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-199">To learn more, check out [Manage app setup policies in Teams](../../teams-app-setup-policies.md).</span></span>

### <a name="onboard-users-to-teams"></a><span data-ttu-id="22341-200">팀에 대 한 온보드 사용자</span><span class="sxs-lookup"><span data-stu-id="22341-200">Onboard users to Teams</span></span>

<span data-ttu-id="22341-201">온 보 딩 전략의 일부로 팀에 익숙해질 수 있도록 사용자에 게 교육 및 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-201">As part of your onboarding strategy, provide training and guidance for users to help them get familiar with Teams.</span></span> <span data-ttu-id="22341-202">팀 클라이언트, 교육 및 지원을 받을 위치를 알 수 있도록 다음 리소스를 사용자와 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-202">Share the following resources with users so they know where to get Teams clients, training, and support:</span></span>

- [<span data-ttu-id="22341-203">팀 웹 클라이언트</span><span class="sxs-lookup"><span data-stu-id="22341-203">Teams web client</span></span>](https://teams.microsoft.com)
- [<span data-ttu-id="22341-204">데스크톱 및 모바일 클라이언트 다운로드 링크</span><span class="sxs-lookup"><span data-stu-id="22341-204">Desktop and mobile client download links</span></span>](https://teams.microsoft.com/downloads)
- [<span data-ttu-id="22341-205">팀 교육 비디오</span><span class="sxs-lookup"><span data-stu-id="22341-205">Teams training videos</span></span>](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [<span data-ttu-id="22341-206">팀 도움말 문서</span><span class="sxs-lookup"><span data-stu-id="22341-206">Teams Help documentation</span></span>](https://support.office.com/teams)

<span data-ttu-id="22341-207">팀 및 운전 팀 채택을 배포 하는 방법에 대 한 지침은 팀을 롤 포워드 하 고 [팀을 채택](../../adopt-microsoft-teams-landing-page.md)하 [는 방법을](../../How-to-roll-out-teams.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-207">For guidance on deploying Teams and driving Teams adoption, see [How to roll out Teams](../../How-to-roll-out-teams.md) and [Adopt Teams](../../adopt-microsoft-teams-landing-page.md).</span></span>

## <a name="conduct-a-pilot"></a><span data-ttu-id="22341-208">파일럿 실시</span><span class="sxs-lookup"><span data-stu-id="22341-208">Conduct a pilot</span></span>

<span data-ttu-id="22341-209">최초 사용자의 선택 그룹을 위해 2 개 또는 3 개의 StaffHub 팀부터 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-209">We recommend you start by moving two or three StaffHub teams for a select group of early adopters.</span></span> <span data-ttu-id="22341-210">파일럿을 실행 하면 전환 계획을 개선 하 고 조직의 모든 StaffHub 팀을 팀으로 이동할 준비가 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-210">Running a pilot helps you refine your transition plan and ensure you're ready to move all your organization's StaffHub teams to Teams.</span></span> <span data-ttu-id="22341-211">또한 조직에서 채택을 간편 하 게 할 수 있는 챔피언 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-211">It also identifies champions who can help drive adoption across your organization.</span></span> <span data-ttu-id="22341-212">단계별 접근 방법이 필요 하지 않은 중소 기업 이라면이 섹션의 단계를 StaffHub에서 팀으로 전환 하는 것이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-212">If you're a small business who doesn't need a phased approach, the steps in this section may be all you need to make the switch from StaffHub to Teams.</span></span>

### <a name="identify-pilot-teams"></a><span data-ttu-id="22341-213">파일럿 팀 식별</span><span class="sxs-lookup"><span data-stu-id="22341-213">Identify pilot teams</span></span>

<span data-ttu-id="22341-214">2 명 또는 세 명의 파일럿 팀을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-214">Reach out to identify two or three pilot teams.</span></span> <span data-ttu-id="22341-215">모든 팀 구성원은 팀의 교대 근무를 사용 하 여 일정을 관리 하 고 서로와 통신 하 고 공동 작업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-215">All team members should commit to using Shifts in Teams to manage their schedules and communicate and collaborate with each other.</span></span>

### <a name="identify-team-champions"></a><span data-ttu-id="22341-216">팀 챔피언 확인</span><span class="sxs-lookup"><span data-stu-id="22341-216">Identify team champions</span></span>

<span data-ttu-id="22341-217">파일럿 팀에서 챔피언를 식별 하 고 참여 하 여 evangelize 교대 근무를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-217">Identify champions across pilot teams and enlist them to help evangelize Shifts.</span></span> <span data-ttu-id="22341-218">팀 챔피언 자신의 학습이을 공유 하 여 팀 구성원에 게 지원 및 지침을 제공 하는 것에 대해 열정.</span><span class="sxs-lookup"><span data-stu-id="22341-218">Team champions are passionate about what they do, sharing their own learnings to offer support and guidance to team members.</span></span> <span data-ttu-id="22341-219">팀 챔피언 팀 소유자 또는 관리자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-219">Team champions can be team owners or managers.</span></span>

<span data-ttu-id="22341-220">팀 챔피언 모든 사람이 [팀 클라이언트를 확보](../../get-clients.md)하 고, 팀에 로그인 하 고, 일정을 교대에서 확인 하 고, 서로 채팅을 시작 하도록 시간을 설정 하는 것을 보장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-220">Team champions should ensure team members are set up by dedicating time for everyone to [get Teams clients](../../get-clients.md), sign in to Teams and check out their schedules in Shifts, and start chatting with each other.</span></span> <span data-ttu-id="22341-221">이미 StaffHub에 익숙한 사용자는 이동 중에 빠르게 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-221">Users who are already familiar with StaffHub will be up and running quickly in Shifts.</span></span> <span data-ttu-id="22341-222">또한 [도움말](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) 을 가리키면 추가 도움말을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-222">You can also point them to [Shifts Help](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) for additional help.</span></span>

### <a name="move-a-staffhub-team"></a><span data-ttu-id="22341-223">StaffHub 팀 이동</span><span class="sxs-lookup"><span data-stu-id="22341-223">Move a StaffHub team</span></span>

<span data-ttu-id="22341-224">이 단계를 사용 하 여 한 번에 한 StaffHub 팀을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-224">Use these steps to move one StaffHub team at a time.</span></span> <span data-ttu-id="22341-225">파일럿 팀에이 접근 방법을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-225">We recommend this approach for your pilot teams.</span></span> <span data-ttu-id="22341-226">나중에 조직의 모든 StaffHub 팀을 이동할 준비가 되 면 여러 팀을 한 번에 이동 하는 방법에 대 한 단계에 대해 [StaffHub 팀 이동을](#move-your-staffhub-teams) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-226">Later, when you're ready to move all your organization's StaffHub teams, see [Move your StaffHub teams](#move-your-staffhub-teams) for steps on how move multiple teams at a time.</span></span>

<span data-ttu-id="22341-227">다음을 실행 하 여 StaffHub 팀을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-227">Run the following to move a StaffHub team.</span></span>

```
Move-StaffHubTeam -TeamId <String>
```
<span data-ttu-id="22341-228">예</span><span class="sxs-lookup"><span data-stu-id="22341-228">Example:</span></span>

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

<span data-ttu-id="22341-229">다음은 StaffHub 팀을 팀으로 이동 하는 요청을 제출할 때 표시 되는 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="22341-229">Here's an example of the response you get when you submit a request to move a StaffHub team to Teams.</span></span>

```
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

<span data-ttu-id="22341-230">이동 요청의 상태를 확인 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-230">To check the status of a move request, run the following.</span></span>

```
Get-TeamMigrationJobStatus <String>
```
<span data-ttu-id="22341-231">예</span><span class="sxs-lookup"><span data-stu-id="22341-231">Example:</span></span>

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

<span data-ttu-id="22341-232">다음은 이동을 진행 하는 동안 받은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="22341-232">Here's an example of the response you get when a move is in progress.</span></span>

```
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a><span data-ttu-id="22341-233">StaffHub 팀에서 팀으로 파일 이동</span><span class="sxs-lookup"><span data-stu-id="22341-233">Move files from a StaffHub team to Teams</span></span>

<span data-ttu-id="22341-234">이 단계는 팀으로 이동한 StaffHub 팀에 게 팀으로 이동 하려는 파일이 있는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-234">This step only applies if the StaffHub team that you moved to Teams has files that you want to also move to Teams.</span></span> <span data-ttu-id="22341-235">SharePoint Online 또는 PowerShell을 사용 하 여 파일을 직접 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-235">You can move files directly in SharePoint Online or by using PowerShell.</span></span>

#### <a name="in-sharepoint-online"></a><span data-ttu-id="22341-236">SharePoint Online에서</span><span class="sxs-lookup"><span data-stu-id="22341-236">In SharePoint Online</span></span>

<span data-ttu-id="22341-237">[SharePoint Online에서 파일을 이동 하는 방법](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="22341-237">See [How to move files in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="22341-238">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="22341-238">Using PowerShell</span></span>

<span data-ttu-id="22341-239">아직 없는 경우 [SharePoint Online 관리 셸을](https://www.microsoft.com/download/details.aspx?id=35588)다운로드 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-239">Download and install the [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588), if you haven't already.</span></span> <span data-ttu-id="22341-240">파일을 이동 하는 데 필요한 cmdlet이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-240">It contains the cmdlets you need to move files.</span></span>  

<span data-ttu-id="22341-241">SharePoint Online 팀 사이트에 연결 하려면 [PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-241">Use the [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet to connect to the SharePoint Online team site.</span></span>

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

<span data-ttu-id="22341-242">StaffHub에서 팀으로 이동 하려는 각 파일에 대해 [move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet을 사용 하 여 파일을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-242">For each file that you want to move from StaffHub to Teams, use the [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet to move the file.</span></span>

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

<span data-ttu-id="22341-243">여러 파일을 이동 하려면 파일을 순환 하면서 루프에서 두 번째 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-243">To move multiple files, loop over the files and run the second command on the loop.</span></span> <span data-ttu-id="22341-244">세션이 활성 상태를 유지 하는 경우 첫 번째 명령을 반복할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-244">You don't need to repeat the first command if the session remains active.</span></span>

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a><span data-ttu-id="22341-245">파일럿을 넘어서 모든 StaffHub 팀을 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-245">Go beyond your pilot and move all StaffHub teams</span></span>

### <a name="raise-awareness"></a><span data-ttu-id="22341-246">인식 발생</span><span class="sxs-lookup"><span data-stu-id="22341-246">Raise awareness</span></span>

<span data-ttu-id="22341-247">파일럿 팀으로 이동 하 고 조직의 StaffHub 팀을 팀으로 이동할 준비가 되 면 먼저 조직 전반에 변경 내용을 전달 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-247">When you're ready to go beyond your pilot teams and move your organization's StaffHub teams to Teams, it's important to first communicate the change across your organization.</span></span> <span data-ttu-id="22341-248">이동 및 팀으로 전환에 대 한 단어를 분산 하 여 인식, 흥미로운 생성, 드라이브 채택을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="22341-248">Spread the word about Shifts and the transition to Teams to raise awareness, generate excitement, and drive adoption.</span></span>

### <a name="move-your-staffhub-teams"></a><span data-ttu-id="22341-249">StaffHub 팀 이동</span><span class="sxs-lookup"><span data-stu-id="22341-249">Move your StaffHub teams</span></span>

<span data-ttu-id="22341-250">StaffHub 팀을 대량으로 이동 하려면 다음 단계를 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-250">Use these steps to move StaffHub teams in bulk.</span></span> <span data-ttu-id="22341-251">조직의 StaffHub 팀을 모두 이동 하거나 특정 StaffHub 팀을 이동 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-251">You can choose to move all your organization's StaffHub teams or move specific StaffHub teams.</span></span> <span data-ttu-id="22341-252">StaffHub 팀을 한 번에 하나씩 이동 하려면 [StaffHub 팀 이동을](#move-a-staffhub-team)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-252">If you want to move StaffHub teams one at a time, see [Move a StaffHub team](#move-a-staffhub-team).</span></span>

#### <a name="move-all-staffhub-teams"></a><span data-ttu-id="22341-253">모든 StaffHub 팀 이동</span><span class="sxs-lookup"><span data-stu-id="22341-253">Move all StaffHub teams</span></span>

<span data-ttu-id="22341-254">다음을 실행 하 여 조직의 모든 StaffHub 팀 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="22341-254">Run the following to get a list of all StaffHub teams in your organization.</span></span>

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

<span data-ttu-id="22341-255">모든 팀을 이동 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-255">Then, run the following to move all teams.</span></span>

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

<span data-ttu-id="22341-256">다음은 응답의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="22341-256">Here's an example of the response.</span></span>

<span data-ttu-id="22341-257">이미 팀으로 이동 하거나 팀에 이미 있는 팀의 경우, 해당 팀을 이동 하기 위해 작업을 제출할 필요가 없으므로 jobId는 "null"이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-257">For any team that was already moved to Teams or already exists in Teams, the jobId will be "null" as a job doesn't need to be submitted to move that team.</span></span>

```
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a><span data-ttu-id="22341-258">특정 StaffHub 팀 이동</span><span class="sxs-lookup"><span data-stu-id="22341-258">Move specific StaffHub teams</span></span>

<span data-ttu-id="22341-259">조직의 모든 StaffHub 팀 Id 목록을 가져오려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-259">Run the following to get a list of all StaffHub team Ids in your organization.</span></span>

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

<span data-ttu-id="22341-260">이전에 실행 한 `Get-StaffHubteamsForTenant` cmdlet에서 반환 된 결과에서 이동 하려는 팀 id를 선택한 다음 CSV (쉼표로 구분 된 값) 파일에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-260">In the results returned by the `Get-StaffHubteamsForTenant` cmdlet you ran earlier, select the Team Ids you want to move, and then add them to a comma-separated values (CSV) file.</span></span>

<span data-ttu-id="22341-261">다음은 CSV 파일의 서식을 지정 하는 방법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="22341-261">Here's an example of how the CSV file should be formatted.</span></span>

|<span data-ttu-id="22341-262">I</span><span class="sxs-lookup"><span data-stu-id="22341-262">Id</span></span>  |
|---------|
|<span data-ttu-id="22341-263">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span><span class="sxs-lookup"><span data-stu-id="22341-263">TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f</span></span><br><span data-ttu-id="22341-264">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span><span class="sxs-lookup"><span data-stu-id="22341-264">TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000</span></span><br><span data-ttu-id="22341-265">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="22341-265">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span><br><span data-ttu-id="22341-266">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span><span class="sxs-lookup"><span data-stu-id="22341-266">TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000</span></span>|

<span data-ttu-id="22341-267">CSV 파일을 만든 후 다음을 실행 하 여 CSV 파일에서 지정한 팀을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-267">After you create the CSV file, run the following to move the teams you specified in the CSV file.</span></span>

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a><span data-ttu-id="22341-268">StaffHub 팀이 팀으로 이동 했는지 확인</span><span class="sxs-lookup"><span data-stu-id="22341-268">Confirm that your StaffHub teams have moved to Teams</span></span>

<span data-ttu-id="22341-269">다음을 실행 하 여 조직에서 모든 팀의 변화에 대 한 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="22341-269">Run the following to get a list of all teams in Shifts in your organization.</span></span> 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a><span data-ttu-id="22341-270">StaffHub 팀에서 팀으로 파일 이동</span><span class="sxs-lookup"><span data-stu-id="22341-270">Move files from your StaffHub teams to Teams</span></span>

<span data-ttu-id="22341-271">이동한 StaffHub 팀에 팀으로 이동 하려는 파일이 포함 되어 있는 경우 [StaffHub 팀에서 팀으로 파일 이동을](#move-files-from-a-staffhub-team-to-teams)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-271">If the StaffHub teams that you moved contain files that you also want to move to Teams, see [Move files from a StaffHub team to Teams](#move-files-from-a-staffhub-team-to-teams).</span></span>

## <a name="monitor-teams-usage"></a><span data-ttu-id="22341-272">팀 사용량 모니터링</span><span class="sxs-lookup"><span data-stu-id="22341-272">Monitor Teams usage</span></span>

<span data-ttu-id="22341-273">사용 현황 보고서를 통해 사용 패턴을 보다 잘 이해 하 고 조직의 교육 및 통신 작업에 대 한 우선 순위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-273">Usage reports can help you better understand usage patterns and give you insights on where to prioritize training and communication efforts across your organization.</span></span> <span data-ttu-id="22341-274">전체 팀 사용, 팀에서 사용자가 수행 하는 작업 유형, 사용자가 팀에 연결 하는 방법 등에 대 한 보고서를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-274">You can run reports that show you overall Teams usage, the types of activities that users perform in Teams, how users connect to Teams, and more.</span></span> <span data-ttu-id="22341-275">자세한 내용은 [microsoft 365 관리 센터의](../../teams-activity-reports.md) [microsoft 팀 관리 센터](../../teams-analytics-and-reports/teams-reporting-reference.md) 및 팀 활동 보고서에서 팀 보고를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22341-275">For more information, see [Teams reporting in the Microsoft Teams admin center](../../teams-analytics-and-reports/teams-reporting-reference.md) and [Teams activity reports in the Microsoft 365 admin center](../../teams-activity-reports.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="22341-276">해결사</span><span class="sxs-lookup"><span data-stu-id="22341-276">Troubleshooting</span></span>

<span data-ttu-id="22341-277">**실패 오류에 대 한 자세한 정보를 얻는 방법**</span><span class="sxs-lookup"><span data-stu-id="22341-277">**How to get more information about failure errors**</span></span>

<span data-ttu-id="22341-278">팀을 이동 하려고 할 때 발생 하는 "실패" 오류에 대 한 자세한 내용을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-278">Run the following to get more information about "Failure" errors that occur when you try to move a team:</span></span>

```
Move-StaffHubTeam -TeamId <TeamId>
$res = Get-TeamMigrationJobStatus -JobId <JobId>
$res.Status
```

<span data-ttu-id="22341-279">성공, 실패, InProgress, 대기열에 반환 된 상태 중 하나가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22341-279">You'll see one of the following statuses returned: Success, Failure, InProgress, Queued.</span></span>

<span data-ttu-id="22341-280">"실패"가 반환 되는 경우 다음을 실행 하 여 오류에 대 한 자세한 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-280">If "Failure" is returned, run the following to get more information about the error:</span></span>

```
$res.Result.Error.Innererror
```

<span data-ttu-id="22341-281">**StaffHub 팀을 이동 하려고 하면 상태가 "실패"로 표시 되 고 "사용자에 대해 해당 SKU 범주를 검색 하지 못했습니다." 오류 메시지가 표시 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="22341-281">**When you try to move a StaffHub team, the status shows as "Failure" and you receive a "Failed to retrieve applicable SKU categories for the user" error message**</span></span>

<span data-ttu-id="22341-282">하나 이상의 팀 구성원에 게 팀 라이선스가 없는 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-282">This can occur if one or more team members don't have a Teams license.</span></span> <span data-ttu-id="22341-283">Portal.office.com로 이동 하 여 그룹을 찾은 다음 그룹 구성원에 게 팀 라이선스가 할당 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-283">Go to portal.office.com, find the group, and then confirm that group members are assigned a Teams license.</span></span>

<span data-ttu-id="22341-284">**StaffHub 팀을 이동 하려고 하면 상태가 "실패"로 표시 되 고 "팀 소유자가 없습니다." 오류 메시지가 표시 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="22341-284">**When you try to move a StaffHub team, the status shows as "Failure" and you receive a "Team owner not found" error message**</span></span>

<span data-ttu-id="22341-285">StaffHub 팀과 연결 된 그룹에 팀 소유자가 없는 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-285">This can occur if the group that's associated with the StaffHub team doesn't have a team owner.</span></span> <span data-ttu-id="22341-286">Portal.office.com로 이동 하 여 그룹을 찾은 다음 하나 이상의 소유자를 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-286">Go to portal.office.com, find the group, and then add one or more owners to the group.</span></span>

<span data-ttu-id="22341-287">**파일을 StaffHub에서 팀으로 이동 하려고 하면 "사용 권한 거부 됨" 오류 메시지가 표시 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="22341-287">**When you try to move files from StaffHub to Teams, you get a "Permission denied" error message.**</span></span>

<span data-ttu-id="22341-288">구성원이 아닌 개인 Office 365 그룹의 파일을 이동 하려는 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22341-288">This may occur if you're trying to move files in a private Office 365 group that you're not a member of.</span></span> <span data-ttu-id="22341-289">이 경우 [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet을 사용 하 여 자신을 StaffHub 팀에 추가한 다음 파일을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-289">If this is the case, use the [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet to add yourself to the StaffHub team, and then move the files.</span></span> <span data-ttu-id="22341-290">파일을 이동한 후 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet을 사용 하 여 팀에서 자신을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-290">After you move the files, use the [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet to remove yourself from the team.</span></span> 

<span data-ttu-id="22341-291">**파일을 StaffHub에서 팀으로 이동 하려고 하면 일반 폴더가 없다는 오류 메시지가 나타납니다.**</span><span class="sxs-lookup"><span data-stu-id="22341-291">**When you try to move files from StaffHub to Teams, you get an error that says the General folder doesn't exist.**</span></span>

<span data-ttu-id="22341-292">다음 명령을 실행 하 여 SharePoint에 일반 폴더를 추가한 다음 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="22341-292">Run the following command to add the General folder to SharePoint, and then try again:</span></span>

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a><span data-ttu-id="22341-293">관련 항목</span><span class="sxs-lookup"><span data-stu-id="22341-293">Related topics</span></span>
- [<span data-ttu-id="22341-294">Microsoft 팀을 배포 하는 방법</span><span class="sxs-lookup"><span data-stu-id="22341-294">How to roll out Microsoft Teams</span></span>](../../How-to-roll-out-teams.md)
- [<span data-ttu-id="22341-295">Microsoft StaffHub 사용 중지</span><span class="sxs-lookup"><span data-stu-id="22341-295">Microsoft StaffHub to be retired</span></span>](microsoft-staffhub-to-be-retired.md)
- [<span data-ttu-id="22341-296">Microsoft 팀에서 조직의 교대 근무 앱 관리</span><span class="sxs-lookup"><span data-stu-id="22341-296">Manage the Shifts app for your organization in Microsoft Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="22341-297">StaffHub PowerShell 참조</span><span class="sxs-lookup"><span data-stu-id="22341-297">StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
