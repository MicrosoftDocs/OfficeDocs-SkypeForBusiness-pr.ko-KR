---
title: Teams에서 일선 작업자에 대한 교대 근무 기반 액세스 관리
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 일선 작업자용 Teams에서 교대 근무 기반 액세스를 관리하는 방법을 배워야 합니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b73fe9b3c4b39e7d3fa7b31427f563c47e5a737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823018"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a><span data-ttu-id="36895-103">Teams에서 일선 작업자에 대한 교대 근무 기반 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="36895-103">Manage shift-based access for Firstline Workers in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36895-104">2020년 6월 30일부로 Microsoft StaffHub가 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="36895-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="36895-105">Microsoft Teams에 StaffHub 기능을 구축하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="36895-106">현재 Teams에는 일정 관리를 위한 Shifts 앱이 포함되어 있으며 시간이 지날 때 추가 기능이 출시됩니다.</span><span class="sxs-lookup"><span data-stu-id="36895-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="36895-107">StaffHub는 2020년 6월 30일 모든 사용자에 대한 작업을 중지했습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="36895-108">StaffHub를 열려고 하는 모든 사람이 Teams를 다운로드할 수 있는 메시지를 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36895-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="36895-109">자세한 내용은 [Microsoft StaffHub가](microsoft-staffhub-to-be-retired.md)사용 중지된 것을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="36895-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview"></a><span data-ttu-id="36895-110">개요</span><span class="sxs-lookup"><span data-stu-id="36895-110">Overview</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="36895-111">Microsoft Teams의 현재 상태는 사용자의 현재 상태와 다른 사용자에게 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36895-111">Presence in Microsoft Teams indicates a user's current availability and status to other users.</span></span> <span data-ttu-id="36895-112">일선 직원의 존재는 일반적으로 매일 동일하지 않은 다른 직원보다 예측하기가 더 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-112">The presence of Firstline Workers is often less predictable than other staff as their working hours are typically not the same each day.</span></span> <span data-ttu-id="36895-113">관리자는 조직의 일선 직원에 대한 교대 근무 기반 현재 상태 집합을 표시하도록 Teams를 구성하여 교대 근무 중 및 벗어날 때를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-113">As an admin, you can configure Teams to show a set of shift-based presence states for the Firstline Workers in your organization to indicate when they are on and off shift.</span></span>

<span data-ttu-id="36895-114">이러한 교대 근무 기반 현재 상태는 단색 녹색 확인 표시로, Shift 시 시프트 시 회색 원, Shift를 끄는 회색 원, 단색 빨간색 원, 다른 사용 중이 Teams의 기본 현재 상태 집합과 별개인 경우를 &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; 나타냅니다. [](../../presence-admins.md)</span><span class="sxs-lookup"><span data-stu-id="36895-114">These shift-based presence states&mdash;![Solid green check mark, indicates On shift](../../media/flw-presence-on-shift.png) **On shift**, ![Gray circle with x, indicates Off shift](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams.</span></span> <span data-ttu-id="36895-115">이러한 두 현재 상태 집합을 사용하면 해당 역할에 따라 조직의 사용자에 대해 서로 다른 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-115">With these two sets of presence states, you can configure different experiences for people in your organization based on their role.</span></span>

<span data-ttu-id="36895-116">교대 근무 기반 액세스를 사용하면 일선 작업자가 교대 근무 중일 때 Teams에 대한 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-116">With shift-based access, you can manage access to Teams when Firstline Workers are off shift.</span></span> <span data-ttu-id="36895-117">예를 들어 일선 작업자가 예약된 교대 근무에 있지 않을 때 Teams를 사용하기 전에 먼저 일선 작업자가 인정해야 하는 메시지를 표시하는 Teams를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-117">For example, you can set Teams to display a message that Firstline Workers must acknowledge before they can use Teams when they're not on a scheduled shift.</span></span>  

## <a name="scenario"></a><span data-ttu-id="36895-118">시나리오</span><span class="sxs-lookup"><span data-stu-id="36895-118">Scenario</span></span>

<span data-ttu-id="36895-119">다음은 조직에서 교대 근무 기반 액세스를 관리하는 방법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="36895-119">Here's an example of how your organization can manage shift-based access.</span></span>

<span data-ttu-id="36895-120">조직의 일선 작업자는 관리자가 예약하고 승인한 교대 근무 시간에 한해 지급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36895-120">You have Firstline Workers in your organization that should only be paid for hours they work on a shift that their manager scheduled and approved.</span></span> <span data-ttu-id="36895-121">Teams 앱 사용을 포함하는 예약된 교대 근무 외부에서 작업하는 데 소요된 시간으로는 지불하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36895-121">They shouldn't be paid for time spent working outside a scheduled shift, which includes using the Teams app.</span></span> <span data-ttu-id="36895-122">일선 작업자가 교대 근무 중일 때 Teams에 액세스하려고 할 때 표시되는 사용자 지정 메시지를 설정하면 "근무 시간에는 지불할 수 있는 시간에 계산되지 않습니다."라는 사용자 지정 메시지를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-122">You set up a custom message that says "Your time on Teams when on off shift won't count toward payable hours", which is displayed when Firstline Workers try to access Teams when off shift.</span></span> <span data-ttu-id="36895-123">Teams를 사용하기로 선택한 경우  이 시간 동안 지불되지 않는 것으로 이해하면 동의를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="36895-123">If they choose to use Teams, they click **I accept** with the understanding that they won't be paid for this time.</span></span>

<span data-ttu-id="36895-124">또한 급여를 받는 정보 근로자가 있으며 근무하지 않는 정보 근로자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-124">You also have information workers in your organization who are salaried and who don't work shifts.</span></span> <span data-ttu-id="36895-125">일선 작업자의 교대 근무 기반 현재 상태는 제공하면서 Teams의 기본 현재 상태 사용을 정보 근로자가 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="36895-125">You configure your information workers to use the default presence states in Teams while giving your Firstline Workers shift-based presence.</span></span>

## <a name="shift-based-presence-states"></a><span data-ttu-id="36895-126">Shift 기반 현재 상태</span><span class="sxs-lookup"><span data-stu-id="36895-126">Shift-based presence states</span></span>

<span data-ttu-id="36895-127">교대 기반 현재 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-127">Here are the shift-based presence states.</span></span>

|<span data-ttu-id="36895-128">앱이 구성함</span><span class="sxs-lookup"><span data-stu-id="36895-128">App configured</span></span> |<span data-ttu-id="36895-129">사용자가 구성함</span><span class="sxs-lookup"><span data-stu-id="36895-129">User configured</span></span>  |<span data-ttu-id="36895-130">추가 정보</span><span class="sxs-lookup"><span data-stu-id="36895-130">More information</span></span>  |
|---------|---------|---------|
|![단색 녹색 확인 표시, 시프트 표시](../../media/flw-presence-on-shift.png) <span data-ttu-id="36895-132">교대 근무 중</span><span class="sxs-lookup"><span data-stu-id="36895-132">On shift</span></span>     |         |<span data-ttu-id="36895-133">교대 근무 시작 시 자동으로 설정</span><span class="sxs-lookup"><span data-stu-id="36895-133">Automatically set at the start of a shift</span></span>         |
|![회색 원(x, 끄기 이동 표시)](../../media/flw-presence-off-shift.png) <span data-ttu-id="36895-135">끄기 교대 근무</span><span class="sxs-lookup"><span data-stu-id="36895-135">Off shift</span></span>     |         |<span data-ttu-id="36895-136">교대 근무 끝에 자동으로 설정</span><span class="sxs-lookup"><span data-stu-id="36895-136">Automatically set at the end of a shift</span></span>         |
|![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) <span data-ttu-id="36895-138">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="36895-138">Busy</span></span>      | ![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) <span data-ttu-id="36895-140">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="36895-140">Busy</span></span>         |<span data-ttu-id="36895-141">자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="36895-141">Automatically set.</span></span> <span data-ttu-id="36895-142">일선 근무가 교대 근무 중일 때 수동으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-142">Can also be manually set when the Firstline Worker is on shift.</span></span>|

## <a name="off-shift-access-to-teams"></a><span data-ttu-id="36895-143">Teams에 대한 교대 근무 액세스 해제</span><span class="sxs-lookup"><span data-stu-id="36895-143">Off shift access to Teams</span></span>

<span data-ttu-id="36895-144">이 기능을 사용하면 일선 작업자가 교대 근무 중일 때 Teams에 대한 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-144">This feature lets you manage access to Teams when Firstline Workers are off shift.</span></span> <span data-ttu-id="36895-145">근무 중일 때 Teams에 액세스하는 경우 일선 작업자에게 메시지를 표시하는 Teams를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-145">You can set Teams to display a message to Firstline Workers if they access Teams when off shift.</span></span> <span data-ttu-id="36895-146">일선 작업자가  Teams를 사용하려면 먼저 메시지를 승인하려면 동의를 클릭해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36895-146">Firstline Workers must click **I accept** to acknowledge the message before they can use Teams.</span></span>

<span data-ttu-id="36895-147">기본 메시지를 사용하거나 미리 정의된 메시지 집합에서 선택하거나 원하는 텍스트를 표시하는 메시지를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-147">You can use the default message, choose from a set of pre-defined messages, or customize the message to display any text that you want.</span></span> <span data-ttu-id="36895-148">기본 메시지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-148">Here's the default message:</span></span>

![기본 메시지 스크린샷](../../media/shifts-presence-message.png)

<span data-ttu-id="36895-150">메시지가 표시될 때 빈도를 설정하고 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 Teams에 대한 액세스가 제한되는 시기 사이의 유예 기간을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-150">You can also set the frequency when the message is displayed and set a grace period between when the first shift starts or last shift ends and when access to Teams is restricted.</span></span>

## <a name="manage-shift-based-access"></a><span data-ttu-id="36895-151">교대 근무 기반 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="36895-151">Manage shift-based access</span></span>

<span data-ttu-id="36895-152">관리자는 정책을 사용하여 조직의 일선 직원에 대한 교대 근무 기반 현재 상태 제어</span><span class="sxs-lookup"><span data-stu-id="36895-152">As an admin, you use policies to control shift-based presence for Firstline Workers in your organization.</span></span> <span data-ttu-id="36895-153">다음 PowerShell cmdlet을 사용하여 이러한 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="36895-153">You manage these policies by using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="36895-154">New-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="36895-154">New-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [<span data-ttu-id="36895-155">Get-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="36895-155">Get-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [<span data-ttu-id="36895-156">Set-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="36895-156">Set-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [<span data-ttu-id="36895-157">Grant-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="36895-157">Grant-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [<span data-ttu-id="36895-158">Remove-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="36895-158">Remove-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

<span data-ttu-id="36895-159">New-CsTeamsShiftsPolicy cmdlet을 사용하여 새 정책을 만들고, 원하는 정책 설정을 설정한 다음, Grant-CsTeamsShiftsPolicy cmdlet을 사용하여 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="36895-159">Use the New-CsTeamsShiftsPolicy cmdlet to create a new policy, set the policy settings that you want, and then use the Grant-CsTeamsShiftsPolicy cmdlet to assign the policy to users.</span></span>

<span data-ttu-id="36895-160">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="36895-160">Here's some examples.</span></span> <span data-ttu-id="36895-161">선택할 수 있는 미리 정의한 교대 근무 메시지 목록을 포함하여 각 정책 설정 및 매개 변수에 대한 자세한 내용은 [New-CsTeamsShiftsPolicy를](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36895-161">For detailed information about each policy setting and parameter, including the list of predefined off shift messages that you can choose from, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-1"></a><span data-ttu-id="36895-162">예제 1</span><span class="sxs-lookup"><span data-stu-id="36895-162">Example 1</span></span>

<span data-ttu-id="36895-163">이 예제에서는 Shift Teams 액세스 기본 메시지 해제라는 새 정책을 만들겠습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-163">In this example, we create a new policy named Off Shift Teams Access Default Message.</span></span> <span data-ttu-id="36895-164">이 정책에서는 교대 근무 기반 현재 상태가 켜져 있으며 이 정책이 할당된 사용자가 교대 근무 중일 때 Teams에 액세스할 때마다 기본 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="36895-164">In this policy, shift-based presence is turned on and the default message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="36895-165">사용자는 메시지를 수락하는 경우 교대 근무를 해제할 때 Teams를 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한되는 시기 사이의 유예 기간은 10분입니다.</span><span class="sxs-lookup"><span data-stu-id="36895-165">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 10 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> <span data-ttu-id="36895-166">**ShiftNoticeMessageType** 매개 변수를 사용하여 표시할 메시지를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-166">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="36895-167">이 매개 변수에 대해 선택할 수 있는 미리 정의된 메시지 목록을 확인한 다음 [New-CsTeamsShiftsPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)</span><span class="sxs-lookup"><span data-stu-id="36895-167">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-2"></a><span data-ttu-id="36895-168">예제 2</span><span class="sxs-lookup"><span data-stu-id="36895-168">Example 2</span></span> 

<span data-ttu-id="36895-169">이 예제에서는 Shift Teams 액세스 사용자 지정 메시지 해제라는 새 정책을 만들겠습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-169">In this example, we create a new policy named Off Shift Teams Access Custom Message.</span></span> <span data-ttu-id="36895-170">이 정책에서는 교대 근무 기반 현재 상태가 켜져 있으며 이 정책이 할당된 사용자가 교대 근무 중일 때 Teams에 액세스할 때마다 사용자 지정 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="36895-170">In this policy, shift-based presence is turned on and a custom message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="36895-171">사용자는 메시지를 수락하는 경우 교대 근무를 해제할 때 Teams를 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한되는 시기 사이의 유예 기간은 15분입니다.</span><span class="sxs-lookup"><span data-stu-id="36895-171">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 15 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> <span data-ttu-id="36895-172">**ShiftNoticeMessageType** 매개 변수를 사용하여 표시할 메시지를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-172">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="36895-173">자세한 내용은 [New-CsTeamsShiftsPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)</span><span class="sxs-lookup"><span data-stu-id="36895-173">To learn more, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-3"></a><span data-ttu-id="36895-174">예제 3</span><span class="sxs-lookup"><span data-stu-id="36895-174">Example 3</span></span>

<span data-ttu-id="36895-175">이 예제에서는 Shift Teams Access Message1이라는 새 정책을 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-175">In this example, we create a new policy named Off Shift Teams Access Message1.</span></span> <span data-ttu-id="36895-176">이 정책에서는 교대 근무 기반 현재 상태가 켜져 있으며 이 정책이 할당된 사용자가 교대 근무 중일 때 Teams에 액세스할 때마다 다음과 같은 미리 정의된 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="36895-176">In this policy, shift-based presence is turned on and the following predefined message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span>

  <span data-ttu-id="36895-177">"고용주가 비면제 또는 시간당 직원이 근무하지 않는 시간 동안 네트워크, 애플리케이션, 시스템 또는 도구의 사용을 승인하거나 승인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-177">"Your employer does not authorize or approve of the use of its network, applications, systems, or tools by non-exempt or hourly employees during their non-working hours.</span></span> <span data-ttu-id="36895-178">수락하면 교대 근무 중 Teams를 사용할 수 있는 권한이 부여되지 않은 것을 인정하고 보상을 하지 않습니다."</span><span class="sxs-lookup"><span data-stu-id="36895-178">By accepting, you acknowledge that your use of Teams while off shift is not authorized and you will not be compensated."</span></span> 

<span data-ttu-id="36895-179">사용자는 메시지를 수락하는 경우 교대 근무를 해제할 때 Teams를 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한되는 시기 사이의 유예 기간은 3분입니다.</span><span class="sxs-lookup"><span data-stu-id="36895-179">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is three minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> <span data-ttu-id="36895-180">**ShiftNoticeMessageType** 매개 변수를 사용하여 표시할 메시지를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36895-180">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="36895-181">이 매개 변수에 대해 선택할 수 있는 미리 정의된 메시지 목록을 확인한 다음 [New-CsTeamsShiftsPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)</span><span class="sxs-lookup"><span data-stu-id="36895-181">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-4"></a><span data-ttu-id="36895-182">예제 4</span><span class="sxs-lookup"><span data-stu-id="36895-182">Example 4</span></span>

<span data-ttu-id="36895-183">이 예제에서는 Shift Teams Access 사용자 지정 메시지 해제라는 정책을 사용자 지정 remy@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="36895-183">In this example, we assign a policy named Off Shift Teams Access Custom Message to a user named remy@contoso.com.</span></span>

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a><span data-ttu-id="36895-184">관련 항목</span><span class="sxs-lookup"><span data-stu-id="36895-184">Related topics</span></span>

- [<span data-ttu-id="36895-185">Teams에서 조직의 교대 근무 앱 관리</span><span class="sxs-lookup"><span data-stu-id="36895-185">Manage the Shifts app for your organization in Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="36895-186">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="36895-186">Teams PowerShell overview</span></span>](../../teams-powershell-overview.md)
