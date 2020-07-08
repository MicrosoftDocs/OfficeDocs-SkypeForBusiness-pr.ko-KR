---
title: 발신 통화 제한-오디오 회의 & PSTN 통화
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
description: 관리자는 오디오 회의의 종류와 사용자가 설정할 수 있는 최종 사용자 PSTN 통화를 제어할 수 있습니다.
ms.openlocfilehash: fd7c30a7561c06dd237bb72b405c8fc5b7b68dcd
ms.sourcegitcommit: c8b5d4dd70d183f7ca480fb735a19290a3457b30
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45077673"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a><span data-ttu-id="77bb4-103">오디오 회의 및 사용자 PSTN 통화의 아웃바운드 전화 제한 정책</span><span class="sxs-lookup"><span data-stu-id="77bb4-103">Outbound calling restriction policies for Audio Conferencing and user PSTN calls</span></span>

<span data-ttu-id="77bb4-104">관리자는 아웃바운드 호출 제어를 사용하여 조직의 사용자가 만들 수 있는 오디오 회의 및 최종 사용자 PSTN 통화 유형을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-104">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span> 

<span data-ttu-id="77bb4-105">아웃 바운드 통화 컨트롤은 사용자별로 적용할 수 있으며 다음 두 가지 컨트롤을 제공 하 여 각 유형의 아웃 바운드 호출을 독립적으로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-105">Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls.</span></span> <span data-ttu-id="77bb4-106">기본적으로 두 컨트롤 모두 국제 및 국내 아웃 바운드 통화를 허용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-106">By default, both controls are set to allow international and domestic outbound calls.</span></span> 

|<span data-ttu-id="77bb4-107">Ctrl</span><span class="sxs-lookup"><span data-stu-id="77bb4-107">Control</span></span>|<span data-ttu-id="77bb4-108">설명</span><span class="sxs-lookup"><span data-stu-id="77bb4-108">Description</span></span>|<span data-ttu-id="77bb4-109">제어 옵션</span><span class="sxs-lookup"><span data-stu-id="77bb4-109">Control options</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="77bb4-110">오디오 회의 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="77bb4-110">Audio Conferencing PSTN calls</span></span>|<span data-ttu-id="77bb4-111">아웃 바운드 유형을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-111">Restricts the type of outbound</span></span> </br><span data-ttu-id="77bb4-112">내에서 허용 되는 통화</span><span class="sxs-lookup"><span data-stu-id="77bb4-112">calls that are allowed from within</span></span> </br><span data-ttu-id="77bb4-113">사용자가 구성한 모임</span><span class="sxs-lookup"><span data-stu-id="77bb4-113">meetings organized by a user.</span></span>|<span data-ttu-id="77bb4-114">모든 대상 (기본값)</span><span class="sxs-lookup"><span data-stu-id="77bb4-114">Any destination (default)</span></span></br><span data-ttu-id="77bb4-115">Organizor와 동일한 국가 또는 지역에서</span><span class="sxs-lookup"><span data-stu-id="77bb4-115">In the same country or region as the organizor</span></span> </br> </br><span data-ttu-id="77bb4-116">국가 또는 지역만 영역</span><span class="sxs-lookup"><span data-stu-id="77bb4-116">Zone A countries or regions only</span></span> </br><span data-ttu-id="77bb4-117">허용 안 함</span><span class="sxs-lookup"><span data-stu-id="77bb4-117">Don't allow</span></span>|
|<span data-ttu-id="77bb4-118">최종 사용자 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="77bb4-118">End user PSTN calls</span></span>|<span data-ttu-id="77bb4-119">통화 유형을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-119">Restricts the type of calls</span></span> </br><span data-ttu-id="77bb4-120">사용자가 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-120">that can be made by a user.</span></span>|<span data-ttu-id="77bb4-121">국제 및 국내 (기본값)</span><span class="sxs-lookup"><span data-stu-id="77bb4-121">International and Domestic (default)</span></span></br><span data-ttu-id="77bb4-122">국내</span><span class="sxs-lookup"><span data-stu-id="77bb4-122">Domestic</span></span></br><span data-ttu-id="77bb4-123">없음</span><span class="sxs-lookup"><span data-stu-id="77bb4-123">None</span></span>|

<span data-ttu-id="77bb4-124">영역 A로 간주 되는 국가/지역에 [대해 알아보려면 국가/지역 영역을](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="77bb4-124">To find out which countries/regions are considered Zone A, see [Zone A countries/regions](https://docs.microsoft.com/microsoftteams/calling-plans-for-office-365).</span></span>

   > [!NOTE]
   > <span data-ttu-id="77bb4-125">전화를 거는 번호가 모임 이끌이 (오디오 회의의 경우) 또는 최종 사용자 (최종 사용자 PSTN 통화의 경우)에 대해 설정 된 같은 국가에 365 365 거주 하는 경우에는 통화가 국내으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-125">A call is considered domestic if the number dialed is in the same country where Microsoft 365 or Office 365 has been set up for the organizer of the meeting (in the case of audio conferencing), or the end user (in the case of end user PSTN calls).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a><span data-ttu-id="77bb4-126">오디오 회의 발신 전화 제한</span><span class="sxs-lookup"><span data-stu-id="77bb4-126">Restrict audio conferencing outbound calls</span></span> 

<span data-ttu-id="77bb4-127">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="77bb4-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="77bb4-128">왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-128">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="77bb4-129">페이지 맨 위에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-129">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="77bb4-130">**오디오 회의**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-130">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="77bb4-131">**모임에서 전화 걸기 사용 권한**에서 원하는 전화 걸기 제한 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-131">Under **Dial-out permission from meetings**, select the dial-out restriction option you want.</span></span>

5. <span data-ttu-id="77bb4-132">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-132">Click **Save**.</span></span> 

<span data-ttu-id="77bb4-133">![비즈니스용 skype 로고를 나타내는 아이콘](media/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="77bb4-133">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1.    <span data-ttu-id="77bb4-134">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의**  >  **사용자**로 이동한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then select the user from the list of available users.</span></span>

2.    <span data-ttu-id="77bb4-135">작업 창에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-135">In the Action pane, click **Edit**.</span></span>

3.    <span data-ttu-id="77bb4-136">**이 사용자의 모임에서 전화를 걸 수 있는 제한**에서 원하는 전화 걸기 제한 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-136">Under **Restrictions to dial-outs from meetings of this user**, select the dial-out restriction option you want.</span></span>

    ![전화 걸기 옵션에 대 한 제한 사항](/Skype/SfbOnline/images/restrictions-to-dial-outs.png)

5. <span data-ttu-id="77bb4-138">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-138">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="77bb4-139">**PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="77bb4-139">**Using PowerShell**</span></span>

<span data-ttu-id="77bb4-140">아웃 바운드 통화 제한은 각에 대 한 제한 특성이 있는 OnlineDialOutPolicy 이라는 단일 정책에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-140">Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each.</span></span> <span data-ttu-id="77bb4-141">정책은 사용자 지정할 수 없으며, 설정의 각 조합에 대해 미리 정의 된 정책 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-141">The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings.</span></span> 

<span data-ttu-id="77bb4-142">CSOnlineDialOutPolicy cmdlet을 사용 하 여 아웃 바운드 호출 정책을 보고 CSDialOutPolicy cmdlet을 사용 하 여 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-142">You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet.</span></span> <span data-ttu-id="77bb4-143">(Get cmdlet을 사용할 때 Grant cmdlet에 "Online" 이라는 단어가 포함 되지 않는다는 점에 유의 하세요.)</span><span class="sxs-lookup"><span data-stu-id="77bb4-143">(Please note that the Grant cmdlet doesn't contain the word "Online" as the Get cmdlet does.)</span></span> 

<span data-ttu-id="77bb4-144">다음 표에서는 각 정책에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-144">The following table provides an overview of each policy.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="77bb4-145">Id = ' tag: DialoutCPCandPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="77bb4-145">Identity='tag:DialoutCPCandPSTNInternational'</span></span>    |    <span data-ttu-id="77bb4-146">전화 회의에 참가 한 사용자는 국제 및 국내 번호로 통화할 수 있으며,이 사용자는 국제/국내 번호로 아웃 바운드 통화를 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-146">User in the conference can dial out to   international and domestic numbers, and this user can also make outbound calls to international and domestic numbers.</span></span>    |
|<span data-ttu-id="77bb4-147">Id = ' tag: DialoutCPCDomesticPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="77bb4-147">Identity='tag:DialoutCPCDomesticPSTNInternational'</span></span>  |    <span data-ttu-id="77bb4-148">회의 사용자는 국내 번호로만 전화를 걸 수 있으며,이 사용자는 국제 및 국내 번호로 아웃 바운드 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-148">User in the conference can only dial out to   domestic numbers, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="77bb4-149">Id = ' tag: DialoutCPCDisabledPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="77bb4-149">Identity='tag:DialoutCPCDisabledPSTNInternational'</span></span>    |    <span data-ttu-id="77bb4-150">회의 사용자가 전화를 걸 수 없습니다. 이 사용자는 국제 및 국내 번호로 아웃 바운드 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-150">User in the conference cannot make any dial out. This user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="77bb4-151">Id = ' tag: DialoutCPCInternationalPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="77bb4-151">Identity='tag:DialoutCPCInternationalPSTNDomestic'</span></span>    |    <span data-ttu-id="77bb4-152">전화 회의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며,이 사용자는 국내 PSTN 번호로만 아웃 바운드 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-152">User in the conference can dial out to   international and domestic numbers, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="77bb4-153">Id = ' tag: DialoutCPCInternationalPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="77bb4-153">Identity='tag:DialoutCPCInternationalPSTNDisabled'</span></span>    |    <span data-ttu-id="77bb4-154">전화 회의 사용자는 국제 및 국내 번호로 전화를 걸 수 있으며,이 사용자는 비상 번호로 PSTN 번호로의 아웃 바운드 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-154">User in the conference can dial out to   international and domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="77bb4-155">Id = ' tag: DialoutCPCandPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="77bb4-155">Identity='tag:DialoutCPCandPSTNDomestic'</span></span>    |    <span data-ttu-id="77bb4-156">회의 사용자는 국내 번호로만 전화를 걸 수 있으며,이 사용자는 국내 PSTN 번호로만 아웃 바운드 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-156">User in the conference can only dial out to   domestic numbers, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="77bb4-157">Id = ' tag: DialoutCPCDomesticPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="77bb4-157">Identity='tag:DialoutCPCDomesticPSTNDisabled'</span></span>    |    <span data-ttu-id="77bb4-158">회의 사용자는 국내 번호로만 전화를 걸 수 있으며,이 사용자는 비상 번호 이외의 PSTN 번호로의 아웃 바운드 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-158">User in the conference can only dial out to   domestic numbers, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="77bb4-159">Id = ' tag: DialoutCPCDisabledPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="77bb4-159">Identity='tag:DialoutCPCDisabledPSTNDomestic'</span></span>    |    <span data-ttu-id="77bb4-160">회의 중인 사용자는 전화를 걸 수 없으며,이 사용자는 국내 PSTN 번호로만 아웃 바운드 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-160">User in the conference cannot make any dial   out, and this user can only make outbound call to domestic PSTN numbers.</span></span>    |
|    <span data-ttu-id="77bb4-161">Id = ' tag: DialoutCPCandPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="77bb4-161">Identity='tag:DialoutCPCandPSTNDisabled'</span></span>    |    <span data-ttu-id="77bb4-162">회의 중 사용자는 전화를 걸 수 없으며,이 사용자는 비상 번호 이외의 PSTN 번호로의 아웃 바운드 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-162">User in the conference cannot make any dial   out, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
|    <span data-ttu-id="77bb4-163">Id = ' tag: DialoutCPCZoneAPSTNInternational '</span><span class="sxs-lookup"><span data-stu-id="77bb4-163">Identity='tag:DialoutCPCZoneAPSTNInternational'</span></span>    |    <span data-ttu-id="77bb4-164">전화 회의 사용자는 국가 및 지역 영역에만 전화를 걸 수 있으며,이 사용자는 국제 및 국내 번호로 아웃 바운드 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-164">User in the conference can only dial out to Zone A countries and regions, and this user can make outbound calls to international and domestic numbers.</span></span>    |
|    <span data-ttu-id="77bb4-165">Id = ' tag: DialoutCPCZoneAPSTNDomestic '</span><span class="sxs-lookup"><span data-stu-id="77bb4-165">Identity='tag:DialoutCPCZoneAPSTNDomestic'</span></span>    |    <span data-ttu-id="77bb4-166">전화 회의 사용자는 국가 및 지역 영역에만 전화를 걸 수 있으며,이 사용자는 국내 PSTN 번호로만 아웃 바운드 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-166">User in the conference can only dial out to Zone A countries and regions, and this user can only make outbound calls to domestic PSTN number.</span></span>    |
|    <span data-ttu-id="77bb4-167">Id = ' tag: DialoutCPCZoneAPSTNDisabled '</span><span class="sxs-lookup"><span data-stu-id="77bb4-167">Identity='tag:DialoutCPCZoneAPSTNDisabled'</span></span>    |    <span data-ttu-id="77bb4-168">전화 회의 사용자는 국가 및 지역 영역에만 전화를 걸 수 있으며,이 사용자는 비상 번호 이외의 PSTN 번호로의 아웃 바운드 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77bb4-168">User in the conference can only dial out to Zone A countries and regions, and this user cannot make any outbound calls to PSTN number besides emergency numbers.</span></span>    |
