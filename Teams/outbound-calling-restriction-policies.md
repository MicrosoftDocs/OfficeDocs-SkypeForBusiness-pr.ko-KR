---
title: 아웃바운드 호출 제한 - 오디오 회의 & PSTN 호출
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 관리자는 사용자가 만들 수 있는 오디오 회의 및 최종 사용자 PSTN 호출 유형을 제어할 수 있습니다.
ms.openlocfilehash: 86622b493fbb8d31f98f600acb7158afc82e15e5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526731"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="02d4c-103">오디오 회의 및 사용자 PSTN 통화의 아웃바운드 전화 제한 정책</span><span class="sxs-lookup"><span data-stu-id="02d4c-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="02d4c-104">관리자는 아웃바운드 호출 컨트롤을 사용하여 조직의 사용자가 만들 수 있는 오디오 회의 및 PSTN(최종 사용자 공용 전환 전화 네트워크) 호출 유형을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end-user Public Switched Telephone Network (PSTN) calls that can be made by users in your organization.</span></span>

<span data-ttu-id="02d4c-105">아웃바운드 호출 컨트롤은 사용자별로 또는 테넌트별로 적용될 수 있으며, 각 아웃바운드 호출 유형을 독립적으로 제한하기 위해 다음 두 컨트롤을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-105">Outbound call controls can be applied on a per-user basis or on a tenant basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="02d4c-106">기본적으로 두 컨트롤은 국제 및 국내 아웃바운드 호출을 허용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-106">By default, both controls are set to allow international and domestic outbound calls.</span></span>

|<span data-ttu-id="02d4c-107">제어</span><span class="sxs-lookup"><span data-stu-id="02d4c-107">Control</span></span>|<span data-ttu-id="02d4c-108">설명</span><span class="sxs-lookup"><span data-stu-id="02d4c-108">Description</span></span>|<span data-ttu-id="02d4c-109">제어 옵션</span><span class="sxs-lookup"><span data-stu-id="02d4c-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="02d4c-110">오디오 회의 PSTN 호출</span><span class="sxs-lookup"><span data-stu-id="02d4c-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="02d4c-111">아웃바운드 형식 제한</span><span class="sxs-lookup"><span data-stu-id="02d4c-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="02d4c-112">내에서 허용되는 호출</span><span class="sxs-lookup"><span data-stu-id="02d4c-112">calls that are allowed from within</span></span> </br><span data-ttu-id="02d4c-113">사용자가 구성한 모임입니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-113">meetings organized by a user.</span></span>|<span data-ttu-id="02d4c-114">모든 대상(기본값)</span><span class="sxs-lookup"><span data-stu-id="02d4c-114">Any destination (default)</span></span></br><span data-ttu-id="02d4c-115">이끌이와 동일한 국가 또는 지역에서</span><span class="sxs-lookup"><span data-stu-id="02d4c-115">In the same country or region as the organizer</span></span> </br> <span data-ttu-id="02d4c-116">[영역 A 국가 또는 지역만](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="02d4c-116">[Zone A countries or regions](audio-conferencing-zones.md) only</span></span> </br><span data-ttu-id="02d4c-117">허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-117">Don't allow</span></span>|
|<span data-ttu-id="02d4c-118">최종 사용자 PSTN 호출</span><span class="sxs-lookup"><span data-stu-id="02d4c-118">End-user PSTN calls</span></span>|<span data-ttu-id="02d4c-119">호출 유형을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-119">Restricts the type of calls</span></span> </br><span data-ttu-id="02d4c-120">사용자가 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-120">that can be made by a user.</span></span>|<span data-ttu-id="02d4c-121">국제 및 국내(기본값)</span><span class="sxs-lookup"><span data-stu-id="02d4c-121">International and Domestic (default)</span></span></br><span data-ttu-id="02d4c-122">국내선</span><span class="sxs-lookup"><span data-stu-id="02d4c-122">Domestic</span></span></br><span data-ttu-id="02d4c-123">없음</span><span class="sxs-lookup"><span data-stu-id="02d4c-123">None</span></span>|

<span data-ttu-id="02d4c-124">영역 A로 간주되는 국가 및 지역을 찾으면 오디오 회의의 국가 및 지역을 [참조합니다.](audio-conferencing-zones.md)</span><span class="sxs-lookup"><span data-stu-id="02d4c-124">To find out which countries and regions are considered Zone A, see [Country and region zones for Audio Conferencing](audio-conferencing-zones.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="02d4c-125">전화 걸기 번호가 모임의 이끌이(오디오 회의의 경우) 또는 최종 사용자(최종 사용자 PSTN 호출의 경우)에 대해 설정된 Microsoft 365 Office 365 국가에 있는 경우 통화가 국내로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="02d4c-126">오디오 회의 아웃바운드 호출 제한</span><span class="sxs-lookup"><span data-stu-id="02d4c-126">Restrict audio conferencing outbound calls</span></span>

<span data-ttu-id="02d4c-127">![Microsoft Teams ](media/teams-logo-30x30.png) **관리 센터를 사용하여 Microsoft Teams 로고**</span><span class="sxs-lookup"><span data-stu-id="02d4c-127">![the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="02d4c-128">왼쪽 탐색에서 **사용자** 를 선택한 다음 사용 가능한 사용자 목록에서 사용자의 표시 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-128">In the left navigation, select **Users**, and then select the display name of the user from the list of available users.</span></span>

3. <span data-ttu-id="02d4c-129">오디오 **회의** 옆에 있는 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="02d4c-129">Next to **Audio Conferencing**, select **Edit**.</span></span>

4. <span data-ttu-id="02d4c-130">모임에서 **전화** 접속에서 원하는 전화 접속 제한 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-130">Under **Dial-out from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="02d4c-131">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-131">Select **Save**.</span></span>

<span data-ttu-id="02d4c-132">![비즈니스용 skype 로고를 나타내는 아이콘](media/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="02d4c-132">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="02d4c-133">관리 **비즈니스용 Skype** 왼쪽 탐색에서 **오디오** 회의 사용자로 이동한 다음 사용 가능한 사용자 목록에서 사용자를  >  선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-133">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="02d4c-134">작업 창에서 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="02d4c-134">In the Action pane, select **Edit**.</span></span>

3.  <span data-ttu-id="02d4c-135">이 **사용자의 모임에서** 전화 접속 제한에서 원하는 전화 접속 제한 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-135">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

      ![전화 접속 옵션에 대한 제한 사항](media/restrictions-to-dial-outs.png)

4. <span data-ttu-id="02d4c-137">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-137">Select **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="02d4c-138">**PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="02d4c-138">**Using PowerShell**</span></span>

<span data-ttu-id="02d4c-139">아웃바운드 호출 제한은 각각에 대한 제한 특성이 있는 OnlineDialOutPolicy라는 단일 정책에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-139">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy, which has a restriction attribute for each.</span></span> <span data-ttu-id="02d4c-140">정책을 사용자 지정할 수 없습니다. 설정의 각 조합에 대해 미리 정의된 정책 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-140">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span>

<span data-ttu-id="02d4c-141">Get-CSOnlineDialOutPolicy cmdlet을 사용하여 아웃바운드 호출 정책을 보고 설정에 다음 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-141">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and use the following command for the setup.</span></span>

<span data-ttu-id="02d4c-142">**다음 cmdlet을** 통해 사용자당 수준으로 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-142">**Set the policy on a per-user level with the following cmdlet**.</span></span> <span data-ttu-id="02d4c-143">(권한 부여 cmdlet에는 Get cmdlet에서처럼 "Online"이라는 단어가 포함되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="02d4c-143">(The Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span>

```
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

<span data-ttu-id="02d4c-144">**다음 cmdlet을** 통해 테넌트 수준에서 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-144">**Set the policy on the tenant level with the following cmdlet**.</span></span>

```
Grant-CsDialoutPolicy  -Tenant <guid> -PolicyName <policy name>  -Global 
```

<span data-ttu-id="02d4c-145">전화 접속 정책이 할당되지 않은 테넌트의 모든 사용자에게 이 정책이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-145">All users of the tenant who don't have any dialout policy assigned will get this policy.</span></span> <span data-ttu-id="02d4c-146">다른 사용자는 현재 정책으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-146">Other users remain with their current policy.</span></span>

<span data-ttu-id="02d4c-147">다음 표에서는 각 정책에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-147">The following table provides an overview of each policy.</span></span>

|<span data-ttu-id="02d4c-148">PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="02d4c-148">PowerShell cmdlet</span></span>|<span data-ttu-id="02d4c-149">설명</span><span class="sxs-lookup"><span data-stu-id="02d4c-149">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="02d4c-150">Identity='tag:DialoutCPCandPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="02d4c-150">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="02d4c-151">회의의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며, 이 사용자는 국제 및 국내 번호로 아웃바운드 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-151">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="02d4c-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="02d4c-152">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="02d4c-153">회의의 사용자는 국내 번호로만 전화를 걸 수 있으며, 이 사용자는 국제 및 국내 번호로 아웃바운드 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-153">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="02d4c-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="02d4c-154">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="02d4c-155">회의에 참석한 사용자는 전화를 걸 수 없습니다. 이 사용자는 국제 및 국내 번호로 아웃바운드 호출을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-155">User in the conference can't dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="02d4c-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="02d4c-156">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="02d4c-157">회의의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며, 이 사용자는 국내 PSTN 번호로 아웃바운드 호출만 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-157">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="02d4c-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="02d4c-158">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="02d4c-159">회의의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며, 이 사용자는 긴급 번호 외에 PSTN 번호로 아웃바운드 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-159">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="02d4c-160">Identity='tag:DialoutCPCandPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="02d4c-160">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="02d4c-161">회의의 사용자는 국내 번호로만 전화를 걸 수 있으며, 이 사용자는 국내 PSTN 번호로 아웃바운드 호출만 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-161">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="02d4c-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="02d4c-162">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="02d4c-163">회의의 사용자는 국내 번호로만 전화를 걸 수 있으며, 이 사용자는 긴급 번호 외에 PSTN 번호로 아웃바운드 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-163">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="02d4c-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="02d4c-164">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="02d4c-165">회의의 사용자는 전화를 걸 수 없습니다. 이 사용자는 국내 PSTN 번호로 아웃바운드 호출만 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-165">User in the conference can't dial out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="02d4c-166">Identity='tag:DialoutCPCandPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="02d4c-166">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="02d4c-167">회의의 사용자는 전화를 걸 수 없습니다. 이 사용자는 긴급 번호 외에 PSTN 번호로 아웃바운드 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-167">User in the conference can't dial out, and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="02d4c-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span><span class="sxs-lookup"><span data-stu-id="02d4c-168">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="02d4c-169">회의의 사용자는 Zone [A](audio-conferencing-zones.md)국가 및 지역으로만 전화를 걸 수 있으며, 이 사용자는 국제 및 국내 번호로 아웃바운드 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-169">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="02d4c-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span><span class="sxs-lookup"><span data-stu-id="02d4c-170">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="02d4c-171">회의의 사용자는 Zone [A](audio-conferencing-zones.md)국가 및 지역으로만 전화를 걸 수 있으며, 이 사용자는 국내 PSTN 번호로 아웃바운드 호출만 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-171">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="02d4c-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span><span class="sxs-lookup"><span data-stu-id="02d4c-172">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="02d4c-173">회의의 사용자는 영역 [A](audio-conferencing-zones.md)국가 및 지역으로만 전화를 걸 수 있으며, 이 사용자는 긴급 번호 외에 PSTN 번호로 아웃바운드 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02d4c-173">User in the conference can only dial out to [Zone A countries and regions](audio-conferencing-zones.md), and this user can't make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
