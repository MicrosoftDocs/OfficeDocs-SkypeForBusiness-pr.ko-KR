---
title: 작업의 프런트라인 작업자에 대한 교대 근무 Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 Frontline 작업자에 대한 Teams 교대 근무 기반 액세스를 관리하는 방법에 대해 자세히 알아보습니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c69f5678b2a3884f52dd3dc676fce21e2ee67f4f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092546"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a><span data-ttu-id="f17d6-103">작업의 프런트라인 작업자에 대한 교대 근무 Teams</span><span class="sxs-lookup"><span data-stu-id="f17d6-103">Manage shift-based access for Frontline Workers in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f17d6-104">2020년 6월 30일부터 Microsoft StaffHub는 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="f17d6-105">StaffHub 기능을 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f17d6-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="f17d6-106">현재 Teams에는 일정 관리를 위한 교대 근무 앱이 포함되어 있으며 시간이 지날 때 추가 기능이 배포될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="f17d6-107">2020년 6월 30일 StaffHub에서 모든 사용자에 대해 작동이 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="f17d6-108">StaffHub를 여는 모든 사용자에게 Teams를 다운로드하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="f17d6-109">자세한 내용은 [Microsoft StaffHub는 사용 중지됨](microsoft-staffhub-to-be-retired.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f17d6-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview"></a><span data-ttu-id="f17d6-110">개요</span><span class="sxs-lookup"><span data-stu-id="f17d6-110">Overview</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="f17d6-111">Microsoft Teams 상태는 사용자의 현재 가용성 및 다른 사용자에게 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-111">Presence in Microsoft Teams indicates a user's current availability and status to other users.</span></span> <span data-ttu-id="f17d6-112">프런트라인 작업자의 근무 시간은 일반적으로 매일 동일하지기 때문에 다른 직원보다 예측할 수 없는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-112">The presence of Frontline Workers is often less predictable than other staff as their working hours are typically not the same each day.</span></span> <span data-ttu-id="f17d6-113">관리자는 조직에서 Teams 근무 중일 때를 표시하도록 교대 근무 기반 상태 집합을 표시하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-113">As an admin, you can configure Teams to show a set of shift-based presence states for the Frontline Workers in your organization to indicate when they are on and off shift.</span></span>

<span data-ttu-id="f17d6-114">이러한 교대 근무 기반 현재 상태 단색 확인 표시, Shift On Shift, x가 있는 회색 원, Off &mdash; ![ Shift Off ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png) **Shift,** ![ 단색 ](../../media/flw-presence-busy.png)  &mdash; [](../../presence-admins.md) 빨간색 원을 나타내며, 사용 중이 현재 상태의 기본 집합과 별개인 경우를 Teams.</span><span class="sxs-lookup"><span data-stu-id="f17d6-114">These shift-based presence states&mdash;![Solid green check mark, indicates On shift](../../media/flw-presence-on-shift.png) **On shift**, ![Gray circle with x, indicates Off shift](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams.</span></span> <span data-ttu-id="f17d6-115">이 두 가지 현재 상태 집합을 사용하면 해당 역할에 따라 조직의 사용자에 대해 서로 다른 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-115">With these two sets of presence states, you can configure different experiences for people in your organization based on their role.</span></span>

<span data-ttu-id="f17d6-116">Shift 기반 액세스를 사용하면 Frontline 작업자가 교대 근무를 Teams 경우 액세스 권한을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-116">With shift-based access, you can manage access to Teams when Frontline Workers are off shift.</span></span> <span data-ttu-id="f17d6-117">예를 들어, Teams 근무자가 예약된 교대 근무에 있지 않은 경우 Teams 전에 프런트라인 작업자가 인정해야 하는 메시지를 표시하려면 이 메시지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-117">For example, you can set Teams to display a message that Frontline Workers must acknowledge before they can use Teams when they're not on a scheduled shift.</span></span>  

## <a name="scenario"></a><span data-ttu-id="f17d6-118">시나리오</span><span class="sxs-lookup"><span data-stu-id="f17d6-118">Scenario</span></span>

<span data-ttu-id="f17d6-119">조직에서 교대 근무 기반 액세스를 관리하는 방법에 대한 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-119">Here's an example of how your organization can manage shift-based access.</span></span>

<span data-ttu-id="f17d6-120">조직에는 관리자가 예약하고 승인한 교대 근무 시간 동안만 지불해야 하는 프런트라인 작업자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-120">You have Frontline Workers in your organization that should only be paid for hours they work on a shift that their manager scheduled and approved.</span></span> <span data-ttu-id="f17d6-121">예약된 교대 근무 외부에서 작업하는 데 소요되는 시간(앱 사용 포함)에 대한 Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-121">They shouldn't be paid for time spent working outside a scheduled shift, which includes using the Teams app.</span></span> <span data-ttu-id="f17d6-122">"근무 중일 때 Teams 지급 가능 시간으로 계산되지 않습니다"라는 사용자 지정 메시지를 설정했습니다. 이 메시지는 Frontline 작업자가 교대 근무를 벗어날 때 Teams 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-122">You set up a custom message that says "Your time on Teams when on off shift won't count toward payable hours", which is displayed when Frontline Workers try to access Teams when off shift.</span></span> <span data-ttu-id="f17d6-123">해당 사용자가 Teams 경우 이 시간  동안 지급되지 않습니다는 것을 이해하여 동의를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-123">If they choose to use Teams, they click **I accept** with the understanding that they won't be paid for this time.</span></span>

<span data-ttu-id="f17d6-124">또한 조직에 급여를 받는 정보 근로자가 있으며 교대 근무를 하지 않는 사용자도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-124">You also have information workers in your organization who are salaried and who don't work shifts.</span></span> <span data-ttu-id="f17d6-125">Frontline Workers 교대 근무 기반 Teams 상태의 기본 상태 사용을 위해 정보 작업자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-125">You configure your information workers to use the default presence states in Teams while giving your Frontline Workers shift-based presence.</span></span>

## <a name="shift-based-presence-states"></a><span data-ttu-id="f17d6-126">Shift 기반 현재 상태</span><span class="sxs-lookup"><span data-stu-id="f17d6-126">Shift-based presence states</span></span>

<span data-ttu-id="f17d6-127">교대 근무 기반 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-127">Here are the shift-based presence states.</span></span>

|<span data-ttu-id="f17d6-128">앱이 구성함</span><span class="sxs-lookup"><span data-stu-id="f17d6-128">App configured</span></span> |<span data-ttu-id="f17d6-129">사용자가 구성함</span><span class="sxs-lookup"><span data-stu-id="f17d6-129">User configured</span></span>  |<span data-ttu-id="f17d6-130">추가 정보</span><span class="sxs-lookup"><span data-stu-id="f17d6-130">More information</span></span>  |
|---------|---------|---------|
|![단색 녹색 확인 표시, 이동 중을 나타냅니다.](../../media/flw-presence-on-shift.png) <span data-ttu-id="f17d6-132">교대 근무 중</span><span class="sxs-lookup"><span data-stu-id="f17d6-132">On shift</span></span>     |         |<span data-ttu-id="f17d6-133">교대 근무 시작 시 자동으로 설정</span><span class="sxs-lookup"><span data-stu-id="f17d6-133">Automatically set at the start of a shift</span></span>         |
|![x가 있는 회색 원은 이동 해제를 나타냅니다.](../../media/flw-presence-off-shift.png) <span data-ttu-id="f17d6-135">교대 근무 해제</span><span class="sxs-lookup"><span data-stu-id="f17d6-135">Off shift</span></span>     |         |<span data-ttu-id="f17d6-136">교대 근무가 끝날 때 자동으로 설정</span><span class="sxs-lookup"><span data-stu-id="f17d6-136">Automatically set at the end of a shift</span></span>         |
|![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) <span data-ttu-id="f17d6-138">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="f17d6-138">Busy</span></span>      | ![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) <span data-ttu-id="f17d6-140">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="f17d6-140">Busy</span></span>         |<span data-ttu-id="f17d6-141">자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-141">Automatically set.</span></span> <span data-ttu-id="f17d6-142">Frontline Worker가 교대 근무 중일 때 수동으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-142">Can also be manually set when the Frontline Worker is on shift.</span></span>|

## <a name="off-shift-access-to-teams"></a><span data-ttu-id="f17d6-143">다른 사용자에 대한 교대 근무 Teams</span><span class="sxs-lookup"><span data-stu-id="f17d6-143">Off shift access to Teams</span></span>

<span data-ttu-id="f17d6-144">이 기능을 사용하면 Frontline 작업자가 교대 근무를 Teams 경우 액세스 권한을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-144">This feature lets you manage access to Teams when Frontline Workers are off shift.</span></span> <span data-ttu-id="f17d6-145">교대 근무 Teams 액세스하는 경우 프런트라인 작업자에게 메시지를 표시하는 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-145">You can set Teams to display a message to Frontline Workers if they access Teams when off shift.</span></span> <span data-ttu-id="f17d6-146">프런트라인 작업자가  메시지를 사용하기 전에 동의를 클릭하여 메시지를 Teams.</span><span class="sxs-lookup"><span data-stu-id="f17d6-146">Frontline Workers must click **I accept** to acknowledge the message before they can use Teams.</span></span>

<span data-ttu-id="f17d6-147">기본 메시지를 사용하거나 미리 정의된 메시지 집합에서 선택하거나 메시지를 사용자 지정하여 원하는 텍스트를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-147">You can use the default message, choose from a set of pre-defined messages, or customize the message to display any text that you want.</span></span> <span data-ttu-id="f17d6-148">기본 메시지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-148">Here's the default message:</span></span>

![기본 메시지 스크린샷](../../media/shifts-presence-message.png)

<span data-ttu-id="f17d6-150">또한 메시지가 표시될 때 빈도를 설정하고 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료될 때와 교대 근무에 대한 액세스가 제한되는 Teams 유예 기간을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-150">You can also set the frequency when the message is displayed and set a grace period between when the first shift starts or last shift ends and when access to Teams is restricted.</span></span>

## <a name="manage-shift-based-access"></a><span data-ttu-id="f17d6-151">교대 근무 기반 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="f17d6-151">Manage shift-based access</span></span>

<span data-ttu-id="f17d6-152">관리자는 정책을 사용하여 조직의 Frontline Workers에 대한 교대 근무 기반 현재 상태 제어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-152">As an admin, you use policies to control shift-based presence for Frontline Workers in your organization.</span></span> <span data-ttu-id="f17d6-153">다음 PowerShell cmdlet을 사용하여 이러한 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-153">You manage these policies by using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="f17d6-154">New-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="f17d6-154">New-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/new-csteamsshiftspolicy)
- [<span data-ttu-id="f17d6-155">Get-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="f17d6-155">Get-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/get-csteamsshiftspolicy)
- [<span data-ttu-id="f17d6-156">Set-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="f17d6-156">Set-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/set-csteamsshiftspolicy)
- [<span data-ttu-id="f17d6-157">Grant-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="f17d6-157">Grant-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/grant-csteamsshiftspolicy)
- [<span data-ttu-id="f17d6-158">Remove-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="f17d6-158">Remove-CsTeamsShiftsPolicy</span></span>](/powershell/module/teams/remove-csteamsshiftspolicy)

<span data-ttu-id="f17d6-159">New-CsTeamsShiftsPolicy cmdlet을 사용하여 새 정책을 만들고, 원하는 정책 설정을 설정한 다음, Grant-CsTeamsShiftsPolicy cmdlet을 사용하여 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-159">Use the New-CsTeamsShiftsPolicy cmdlet to create a new policy, set the policy settings that you want, and then use the Grant-CsTeamsShiftsPolicy cmdlet to assign the policy to users.</span></span>

<span data-ttu-id="f17d6-160">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-160">Here's some examples.</span></span> <span data-ttu-id="f17d6-161">선택할 수 있는 미리 정의된 교대 근무 메시지 목록을 비롯한 각 정책 설정 및 매개 변수에 대한 자세한 내용은 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f17d6-161">For detailed information about each policy setting and parameter, including the list of predefined off shift messages that you can choose from, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-1"></a><span data-ttu-id="f17d6-162">예제 1</span><span class="sxs-lookup"><span data-stu-id="f17d6-162">Example 1</span></span>

<span data-ttu-id="f17d6-163">이 예제에서는 Access 기본 메시지에 대해 Shift Teams 새 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-163">In this example, we create a new policy named Off Shift Teams Access Default Message.</span></span> <span data-ttu-id="f17d6-164">이 정책에서는 교대 근무 기반 현재 상태가 켜져 있으며, 이 정책에 할당된 사용자가 교대 근무를 벗어날 때 Teams 때마다 기본 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-164">In this policy, shift-based presence is turned on and the default message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="f17d6-165">사용자가 메시지를 Teams 경우 교대 근무를 해제할 때 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한된 경우의 유예 기간은 10분입니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-165">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 10 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> <span data-ttu-id="f17d6-166">**ShiftNoticeMessageType 매개** 변수를 사용하여 표시할 메시지를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-166">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="f17d6-167">이 매개 변수에서 선택할 수 있는 미리 정의된 메시지 목록을 확인한 경우 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f17d6-167">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-2"></a><span data-ttu-id="f17d6-168">예제 2</span><span class="sxs-lookup"><span data-stu-id="f17d6-168">Example 2</span></span> 

<span data-ttu-id="f17d6-169">이 예제에서는 Access Custom Message에서 Off Shift라는 Teams 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-169">In this example, we create a new policy named Off Shift Teams Access Custom Message.</span></span> <span data-ttu-id="f17d6-170">이 정책에서는 교대 근무 기반 존재가 켜져 있으며, 이 정책에 할당된 사용자가 교대 근무를 벗어날 때 사용자 지정 Teams 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-170">In this policy, shift-based presence is turned on and a custom message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="f17d6-171">사용자가 메시지를 Teams 경우 교대 근무를 해제할 때 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한된 경우의 유예 기간은 15분입니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-171">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 15 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> <span data-ttu-id="f17d6-172">**ShiftNoticeMessageType 매개** 변수를 사용하여 표시할 메시지를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-172">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="f17d6-173">자세한 내용은 [New-CsTeamsShiftsPolicy 를 참조합니다.](/powershell/module/teams/new-csteamsshiftspolicy)</span><span class="sxs-lookup"><span data-stu-id="f17d6-173">To learn more, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-3"></a><span data-ttu-id="f17d6-174">예제 3</span><span class="sxs-lookup"><span data-stu-id="f17d6-174">Example 3</span></span>

<span data-ttu-id="f17d6-175">이 예제에서는 Access Message1에서 Off Shift라는 새 정책을 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-175">In this example, we create a new policy named Off Shift Teams Access Message1.</span></span> <span data-ttu-id="f17d6-176">이 정책에서는 교대 근무 기반 현재 상태가 켜져 있으며, 이 정책에 할당된 사용자가 교대 근무를 벗어날 때 이 정책에 액세스할 때마다 다음과 같은 미리 Teams 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-176">In this policy, shift-based presence is turned on and the following predefined message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span>

  <span data-ttu-id="f17d6-177">"고용주는 비영업 시간 동안 비면제 또는 시간당 직원의 네트워크, 애플리케이션, 시스템 또는 도구 사용을 승인하거나 승인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-177">"Your employer does not authorize or approve of the use of its network, applications, systems, or tools by non-exempt or hourly employees during their non-working hours.</span></span> <span data-ttu-id="f17d6-178">수락을 통해 교대 근무하는 동안 Teams 사용이 승인되지 않은 것을 인정하며 보상되지 않습니다."</span><span class="sxs-lookup"><span data-stu-id="f17d6-178">By accepting, you acknowledge that your use of Teams while off shift is not authorized and you will not be compensated."</span></span> 

<span data-ttu-id="f17d6-179">사용자가 메시지를 Teams 경우 교대 근무를 해제할 때 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한된 경우의 유예 기간은 3분입니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-179">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is three minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> <span data-ttu-id="f17d6-180">**ShiftNoticeMessageType 매개** 변수를 사용하여 표시할 메시지를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f17d6-180">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="f17d6-181">이 매개 변수에서 선택할 수 있는 미리 정의된 메시지 목록을 확인한 경우 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f17d6-181">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-4"></a><span data-ttu-id="f17d6-182">예제 4</span><span class="sxs-lookup"><span data-stu-id="f17d6-182">Example 4</span></span>

<span data-ttu-id="f17d6-183">이 예제에서는 Off Shift라는 정책을 Teams 사용자 지정 메시지에 액세스 사용자 지정 메시지를 remy@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f17d6-183">In this example, we assign a policy named Off Shift Teams Access Custom Message to a user named remy@contoso.com.</span></span>

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a><span data-ttu-id="f17d6-184">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f17d6-184">Related topics</span></span>

- [<span data-ttu-id="f17d6-185">Teams에서 조직의 교대 근무 앱 관리</span><span class="sxs-lookup"><span data-stu-id="f17d6-185">Manage the Shifts app for your organization in Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="f17d6-186">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="f17d6-186">Teams PowerShell overview</span></span>](../../teams-powershell-overview.md)