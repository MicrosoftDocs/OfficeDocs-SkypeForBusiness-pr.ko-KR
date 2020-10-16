---
title: 팀의 Firstline Worker에 대 한 shift 기반 액세스 관리
author: LanaChin
ms.author: v-lanac
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 Firstline Worker에 대 한 팀에서 교대 근무 액세스를 관리 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01180f95766412b82d9df7986c3667298f24d5b4
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48486878"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a><span data-ttu-id="7fbeb-103">팀의 Firstline Worker에 대 한 shift 기반 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="7fbeb-103">Manage shift-based access for Firstline Workers in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7fbeb-104">유효 2020 년 6 월 30 일에 Microsoft StaffHub 사용이 중지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-104">Effective June 30, 2020, Microsoft StaffHub has been retired.</span></span> <span data-ttu-id="7fbeb-105">Microsoft 팀에 StaffHub 접근 권한 값을 구축 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="7fbeb-106">현재 팀에는 일정 관리를 위해 교대 근무 앱이 포함 되어 있으며 추가 기능이 시간에 따라 롤아웃 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="7fbeb-107">StaffHub에서 2020 년 6 월 30 일에 모든 사용자의 작동이 중지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-107">StaffHub stopped working for all users on June 30, 2020.</span></span> <span data-ttu-id="7fbeb-108">StaffHub를 열려고 하는 모든 사용자에 게 팀을 다운로드 하도록 지시 하는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-108">Anyone who tries to open StaffHub is shown a message directing them to download Teams.</span></span> <span data-ttu-id="7fbeb-109">자세한 내용은 [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)을 사용 중지 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-109">To learn more, see [Microsoft StaffHub has been retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview"></a><span data-ttu-id="7fbeb-110">개요</span><span class="sxs-lookup"><span data-stu-id="7fbeb-110">Overview</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="7fbeb-111">Microsoft 팀에는 사용자의 현재 사용 가능 시간 및 다른 사용자에 대 한 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-111">Presence in Microsoft Teams indicates a user's current availability and status to other users.</span></span> <span data-ttu-id="7fbeb-112">다른 직원이 근무 시간이 매번 동일 하지 않기 때문에 Firstline Worker의 현재 상태는 예측 하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-112">The presence of Firstline Workers is often less predictable than other staff as their working hours are typically not the same each day.</span></span> <span data-ttu-id="7fbeb-113">관리자는 조직의 Firstline Worker에 대 한 교대 근무 상태의 현재 상태 집합을 표시 하도록 팀을 구성 하 여 shift 키를 사용 하거나 사용 하지 않을 시점을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-113">As an admin, you can configure Teams to show a set of shift-based presence states for the Firstline Workers in your organization to indicate when they are on and off shift.</span></span>

<span data-ttu-id="7fbeb-114">이러한 교대 근무 현재 상태에 &mdash; ![ 는 녹색 체크 표시, ](../../media/flw-presence-on-shift.png) **shift**키, ![ x가 있는 회색 원 ](../../media/flw-presence-off-shift.png) **Off shift**, ![ ](../../media/flw-presence-busy.png) **Busy** &mdash; [default set of presence states](../../presence-admins.md) shift 키를 사용 하 여 교대 근무 시간 표시, 빨간색 실선이 있는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-114">These shift-based presence states&mdash;![Solid green check mark, indicates On shift](../../media/flw-presence-on-shift.png) **On shift**, ![Gray circle with x, indicates Off shift](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams.</span></span> <span data-ttu-id="7fbeb-115">이러한 두 가지 현재 상태 집합을 사용 하 여 조직 내 사용자의 역할에 따라 다른 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-115">With these two sets of presence states, you can configure different experiences for people in your organization based on their role.</span></span>

<span data-ttu-id="7fbeb-116">Shift 기반 액세스를 사용 하면 Firstline Worker가 교대 근무 중일 때 팀에 대 한 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-116">With shift-based access, you can manage access to Teams when Firstline Workers are off shift.</span></span> <span data-ttu-id="7fbeb-117">예를 들어 팀에서 예정 된 교대 근무에 있지 않은 팀을 사용할 수 있도록 하기 전에 Firstline Worker가 승인 해야 하는 메시지를 표시 하도록 팀을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-117">For example, you can set Teams to display a message that Firstline Workers must acknowledge before they can use Teams when they're not on a scheduled shift.</span></span>  

## <a name="scenario"></a><span data-ttu-id="7fbeb-118">시나리오</span><span class="sxs-lookup"><span data-stu-id="7fbeb-118">Scenario</span></span>

<span data-ttu-id="7fbeb-119">다음은 조직에서 shift 기반 액세스를 관리 하는 방법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-119">Here's an example of how your organization can manage shift-based access.</span></span>

<span data-ttu-id="7fbeb-120">조직의 Firstline Worker를 보유 하 고 있으며, 관리자가 작업을 예약 하 고 승인 하는 시간 동안만 지불 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-120">You have Firstline Workers in your organization that should only be paid for hours they work on a shift that their manager scheduled and approved.</span></span> <span data-ttu-id="7fbeb-121">팀 앱을 사용 하는 것을 포함 하 여 예정 된 교대 근무 범위를 벗어나는 시간에 대해 지급 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-121">They shouldn't be paid for time spent working outside a scheduled shift, which includes using the Teams app.</span></span> <span data-ttu-id="7fbeb-122">"교대 근무 시간이 지난 후에는 팀에 시간을 초과 하지 않습니다." 라는 사용자 지정 메시지를 설정 하 여 Firstline Worker가 shift 키를 끄면 팀에 액세스 하려고 할 때 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-122">You set up a custom message that says "Your time on Teams when on off shift won't count toward payable hours", which is displayed when Firstline Workers try to access Teams when off shift.</span></span> <span data-ttu-id="7fbeb-123">팀을 사용 하기로 선택 하는 경우에는 해당 시간에 지불 되지 않는다는 것을 이해 하는 것으로 **승인** 됨을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-123">If they choose to use Teams, they click **I accept** with the understanding that they won't be paid for this time.</span></span>

<span data-ttu-id="7fbeb-124">또한 조직의 정보 근로자와 함께 salaried 작업을 수행 하지 않는 사람을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-124">You also have information workers in your organization who are salaried and who don't work shifts.</span></span> <span data-ttu-id="7fbeb-125">팀에서 Firstline Worker를 이동 하는 동안 기본 현재 상태를 사용 하도록 정보 근로자를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-125">You configure your information workers to use the default presence states in Teams while giving your Firstline Workers shift-based presence.</span></span>

## <a name="shift-based-presence-states"></a><span data-ttu-id="7fbeb-126">Shift 기반 현재 상태</span><span class="sxs-lookup"><span data-stu-id="7fbeb-126">Shift-based presence states</span></span>

<span data-ttu-id="7fbeb-127">다음은 shift 기반 현재 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-127">Here are the shift-based presence states.</span></span>

|<span data-ttu-id="7fbeb-128">앱이 구성함</span><span class="sxs-lookup"><span data-stu-id="7fbeb-128">App configured</span></span> |<span data-ttu-id="7fbeb-129">사용자가 구성함</span><span class="sxs-lookup"><span data-stu-id="7fbeb-129">User configured</span></span>  |<span data-ttu-id="7fbeb-130">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7fbeb-130">More information</span></span>  |
|---------|---------|---------|
|![녹색 확인 표시가 있고 shift 키를 나타냄](../../media/flw-presence-on-shift.png) <span data-ttu-id="7fbeb-132">Shift 키</span><span class="sxs-lookup"><span data-stu-id="7fbeb-132">On shift</span></span>     |         |<span data-ttu-id="7fbeb-133">교대 근무 시작 시 자동으로 설정</span><span class="sxs-lookup"><span data-stu-id="7fbeb-133">Automatically set at the start of a shift</span></span>         |
|![X가 있는 회색 원은 shift 키를 표시 합니다.](../../media/flw-presence-off-shift.png) <span data-ttu-id="7fbeb-135">Shift 키 해제</span><span class="sxs-lookup"><span data-stu-id="7fbeb-135">Off shift</span></span>     |         |<span data-ttu-id="7fbeb-136">자동으로 교대 근무의 끝에 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-136">Automatically set at the end of a shift</span></span>         |
|![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) <span data-ttu-id="7fbeb-138">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="7fbeb-138">Busy</span></span>      | ![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) <span data-ttu-id="7fbeb-140">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="7fbeb-140">Busy</span></span>         |<span data-ttu-id="7fbeb-141">자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-141">Automatically set.</span></span> <span data-ttu-id="7fbeb-142">Firstline Worker가 shift에 있는 경우 수동으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-142">Can also be manually set when the Firstline Worker is on shift.</span></span>|

## <a name="off-shift-access-to-teams"></a><span data-ttu-id="7fbeb-143">팀에 대 한 shift 액세스 해제</span><span class="sxs-lookup"><span data-stu-id="7fbeb-143">Off shift access to Teams</span></span>

<span data-ttu-id="7fbeb-144">이 기능을 사용 하면 Firstline Worker가 교대 근무 중일 때 팀에 대 한 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-144">This feature lets you manage access to Teams when Firstline Workers are off shift.</span></span> <span data-ttu-id="7fbeb-145">Shift 키를 사용 하지 않을 때 팀에 액세스 하는 경우 Firstline Worker에 게 메시지를 표시 하도록 팀을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-145">You can set Teams to display a message to Firstline Workers if they access Teams when off shift.</span></span> <span data-ttu-id="7fbeb-146">Firstline Worker는 팀을 사용할 수 있도록 메시지를 승인 하기 위해 **수락** 을 클릭 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-146">Firstline Workers must click **I accept** to acknowledge the message before they can use Teams.</span></span>

<span data-ttu-id="7fbeb-147">기본 메시지를 사용 하거나, 미리 정의 된 메시지 집합에서 선택 하거나, 메시지를 사용자 지정 하 여 원하는 텍스트를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-147">You can use the default message, choose from a set of pre-defined messages, or customize the message to display any text that you want.</span></span> <span data-ttu-id="7fbeb-148">기본 메시지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-148">Here's the default message:</span></span>

![기본 메시지 스크린샷](../../media/shifts-presence-message.png)

<span data-ttu-id="7fbeb-150">메시지가 표시 되는 빈도를 설정 하 고 첫 번째 교대조가 시작 되는 동안 또는 마지막으로 이동 하는 경우와 팀에 대 한 액세스가 제한 되는 경우의 유예 기간을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-150">You can also set the frequency when the message is displayed and set a grace period between when the first shift starts or last shift ends and when access to Teams is restricted.</span></span>

## <a name="manage-shift-based-access"></a><span data-ttu-id="7fbeb-151">Shift 기반 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="7fbeb-151">Manage shift-based access</span></span>

<span data-ttu-id="7fbeb-152">관리자는 정책을 사용 하 여 조직의 Firstline Worker에 대 한 shift 기반 현재 상태를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-152">As an admin, you use policies to control shift-based presence for Firstline Workers in your organization.</span></span> <span data-ttu-id="7fbeb-153">다음 PowerShell cmdlet을 사용 하 여 이러한 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-153">You manage these policies by using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="7fbeb-154">새로운 CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="7fbeb-154">New-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [<span data-ttu-id="7fbeb-155">Get-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="7fbeb-155">Get-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [<span data-ttu-id="7fbeb-156">Set-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="7fbeb-156">Set-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [<span data-ttu-id="7fbeb-157">부여-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="7fbeb-157">Grant-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [<span data-ttu-id="7fbeb-158">제거-CsTeamsShiftsPolicy</span><span class="sxs-lookup"><span data-stu-id="7fbeb-158">Remove-CsTeamsShiftsPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

<span data-ttu-id="7fbeb-159">New-CsTeamsShiftsPolicy cmdlet을 사용 하 여 새 정책을 만들고 원하는 정책 설정을 설정한 다음 Grant-CsTeamsShiftsPolicy cmdlet을 사용 하 여 정책을 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-159">Use the New-CsTeamsShiftsPolicy cmdlet to create a new policy, set the policy settings that you want, and then use the Grant-CsTeamsShiftsPolicy cmdlet to assign the policy to users.</span></span>

<span data-ttu-id="7fbeb-160">몇 가지 예를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-160">Here's some examples.</span></span> <span data-ttu-id="7fbeb-161">선택할 수 있는 미리 정의 된 오프 라인 이동 메시지 목록을 비롯 한 각 정책 설정 및 매개 변수에 대 한 자세한 내용은 [CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-161">For detailed information about each policy setting and parameter, including the list of predefined off shift messages that you can choose from, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-1"></a><span data-ttu-id="7fbeb-162">예제 1</span><span class="sxs-lookup"><span data-stu-id="7fbeb-162">Example 1</span></span>

<span data-ttu-id="7fbeb-163">이 예제에서는 Off Shift 팀 이라는 새 정책을 만들어 기본 메시지에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-163">In this example, we create a new policy named Off Shift Teams Access Default Message.</span></span> <span data-ttu-id="7fbeb-164">이 정책에서 shift 기반 현재 상태는 설정 되어 있으며,이 정책이 할당 된 사용자가 shift 키를 끄면 팀에 액세스할 때마다 기본 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-164">In this policy, shift-based presence is turned on and the default message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="7fbeb-165">사용자가 메시지를 수락 하는 경우에는 팀을 사용할 수 있으며, 첫 번째 교대조가 시작 되는 동안 또는 마지막으로 이동 하는 동안 유예 기간이 10 분으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-165">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 10 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> <span data-ttu-id="7fbeb-166">**ShiftNoticeMessageType** 매개 변수를 사용 하 여 표시 하려는 메시지를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-166">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="7fbeb-167">이 매개 변수에 대해 선택할 수 있는 미리 정의 된 메시지의 목록을 보려면 [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-167">To see a list of the pre-defined messages that you can choose from for this parameter, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-2"></a><span data-ttu-id="7fbeb-168">예제 2</span><span class="sxs-lookup"><span data-stu-id="7fbeb-168">Example 2</span></span> 

<span data-ttu-id="7fbeb-169">이 예제에서는 사용자 지정 메시지에 대 한 외부 전환 팀 이라는 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-169">In this example, we create a new policy named Off Shift Teams Access Custom Message.</span></span> <span data-ttu-id="7fbeb-170">이 정책에서 shift 기반 현재 상태는 설정 되어 있으며,이 정책이 할당 된 사용자가 shift 키를 끄면 팀에 액세스할 때마다 사용자 지정 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-170">In this policy, shift-based presence is turned on and a custom message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span> <span data-ttu-id="7fbeb-171">사용자가 메시지를 수락 하는 경우에는 팀을 사용할 수 있고, 첫 번째 교대조가 시작 되는 동안 또는 마지막으로 이동 하는 경우와 access가 제한 되는 경우에는 15 분 간의 유예 기간이 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-171">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is 15 minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> <span data-ttu-id="7fbeb-172">**ShiftNoticeMessageType** 매개 변수를 사용 하 여 표시 하려는 메시지를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-172">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="7fbeb-173">자세한 내용은 [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-173">To learn more, see [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).</span></span>

### <a name="example-3"></a><span data-ttu-id="7fbeb-174">예제 3</span><span class="sxs-lookup"><span data-stu-id="7fbeb-174">Example 3</span></span>

<span data-ttu-id="7fbeb-175">이 예제에서는 Off Shift 팀에 게 Message1 액세스 라는 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-175">In this example, we create a new policy named Off Shift Teams Access Message1.</span></span> <span data-ttu-id="7fbeb-176">이 정책에서 shift 기반 현재 상태는 설정 되어 있으며,이 정책이 할당 된 사용자가 shift 키를 끄면 팀에 액세스할 때마다 미리 정의 된 다음 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-176">In this policy, shift-based presence is turned on and the following predefined message is displayed every time a user who is assigned this policy accesses Teams when off shift.</span></span>

  <span data-ttu-id="7fbeb-177">"고용주는 근무 시간 중 비 면제 또는 시간당 직원에의 한 네트워크, 응용 프로그램, 시스템 또는 도구 사용을 허가 하거나 승인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-177">"Your employer does not authorize or approve of the use of its network, applications, systems, or tools by non-exempt or hourly employees during their non-working hours.</span></span> <span data-ttu-id="7fbeb-178">수락 하면 교대 근무를 해제 하는 동안 팀을 사용 하는 것이 승인 되지 않았으므로 사용자는 보정 되지 않습니다. "</span><span class="sxs-lookup"><span data-stu-id="7fbeb-178">By accepting, you acknowledge that your use of Teams while off shift is not authorized and you will not be compensated."</span></span> 

<span data-ttu-id="7fbeb-179">사용자가 메시지를 수락 하는 경우에는 팀을 사용할 수 있고, 첫 번째 교대조가 시작 되는 동안 또는 마지막으로 이동 하는 경우와 access가 제한 되는 시간 사이에 유예 기간이 3 분입니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-179">The user can use Teams when off shift if they accept the message, and the grace period between when the first shift starts or last shift ends and when access is restricted is three minutes.</span></span>  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> <span data-ttu-id="7fbeb-180">**ShiftNoticeMessageType** 매개 변수를 사용 하 여 표시 하려는 메시지를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-180">Use the **ShiftNoticeMessageType** parameter to set the message that you want to display.</span></span> <span data-ttu-id="7fbeb-181">이 매개 변수에 대해 선택할 수 있는 미리 정의 된 메시지의 목록을 보려면 New-TeamsShiftPolicy을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-181">To see a list of the pre-defined messages that you can choose from for this parameter, see New-TeamsShiftPolicy.</span></span>

### <a name="example-4"></a><span data-ttu-id="7fbeb-182">예제 4</span><span class="sxs-lookup"><span data-stu-id="7fbeb-182">Example 4</span></span>

<span data-ttu-id="7fbeb-183">이 예제에서는 remy@contoso.com 라는 사용자에 게 사용자 지정 메시지에 대 한 외부 교대 팀의 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fbeb-183">In this example, we assign a policy named Off Shift Teams Access Custom Message to a user named remy@contoso.com.</span></span>

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a><span data-ttu-id="7fbeb-184">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7fbeb-184">Related topics</span></span>

- [<span data-ttu-id="7fbeb-185">Teams에서 조직의 교대 근무 앱 관리</span><span class="sxs-lookup"><span data-stu-id="7fbeb-185">Manage the Shifts app for your organization in Teams</span></span>](manage-the-shifts-app-for-your-organization-in-teams.md)
- [<span data-ttu-id="7fbeb-186">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="7fbeb-186">Teams PowerShell overview</span></span>](../../teams-powershell-overview.md)
