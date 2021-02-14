---
title: MMS(모임 마이그레이션 서비스) 사용
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: MMS(Meeting Migration Service)는 백그라운드에서 실행되고 사용자를 위해 비즈니스용 Skype 및 Microsoft Teams 모임을 자동으로 업데이트하는 서비스입니다. MMS는 사용자가 모임 마이그레이션 도구를 실행하여 비즈니스용 Skype 및 Microsoft Teams 모임을 업데이트할 필요가 없습니다.
ms.openlocfilehash: 9223102ef9c264fdafdb9f52ec74d6edb383f987
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47765350"
---
# <a name="using-the-meeting-migration-service-mms"></a><span data-ttu-id="e5c2a-104">MMS(모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="e5c2a-104">Using the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="e5c2a-105">MMS(Meeting Migration Service)는 다음과 같은 시나리오에서 사용자의 기존 모임을 업데이트하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-105">The Meeting Migration Service (MMS) is a service that updates a user’s existing meetings in the following scenarios:</span></span>

- <span data-ttu-id="e5c2a-106">사용자가 비즈니스용 Skype Online 또는 TeamsOnly로 마이그레이션된 경우</span><span class="sxs-lookup"><span data-stu-id="e5c2a-106">When a user is migrated from on-premises to the cloud (whether to Skype for Business Online or to TeamsOnly).</span></span>
- <span data-ttu-id="e5c2a-107">관리자가 사용자의 오디오 회의 설정을 변경하는 경우</span><span class="sxs-lookup"><span data-stu-id="e5c2a-107">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="e5c2a-108">온라인 사용자가 Teams로만 업그레이드되거나 TeamsUpgradePolicy의 사용자 모드가 SfBwithTeamsCollabAndMeetings로 설정된 경우</span><span class="sxs-lookup"><span data-stu-id="e5c2a-108">When an online user is upgraded to Teams only, or when a user's mode in TeamsUpgradePolicy is set to SfBwithTeamsCollabAndMeetings</span></span>
- <span data-ttu-id="e5c2a-109">PowerShell을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="e5c2a-109">When you use PowerShell</span></span> 


<span data-ttu-id="e5c2a-110">관리자가 테넌트 수준에서 사용하지 않도록 설정할 수 있는 경우도 기본적으로 MMS는 이러한 각 경우에 자동으로 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-110">By default, MMS is automatically triggered in each of these cases, although admins can disable it at the tenant level.</span></span> <span data-ttu-id="e5c2a-111">또한 관리자는 PowerShell cmdlet을 사용하여 특정 사용자에 대한 모임 마이그레이션을 수동으로 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-111">In addition, admins can use a PowerShell cmdlet to manually trigger meeting migration for a given user.</span></span>


<span data-ttu-id="e5c2a-112">**제한 사항:** 다음 중 한 가지가 적용되는 경우 모임 마이그레이션 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-112">**Limitations**: The meeting migration service can't be used if any of the following apply:</span></span>

- <span data-ttu-id="e5c2a-113">사용자의 사서함은 Exchange On-프레미스에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-113">The user’s mailbox is hosted in Exchange on-premises.</span></span>
- <span data-ttu-id="e5c2a-114">사용자가 클라우드에서 비즈니스용 Skype 서버온-프레미스로 마이그레이션되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-114">The user is being migrated from the cloud to Skype for Business Server on-premises.</span></span>

<span data-ttu-id="e5c2a-115">이러한 상황에서 최종 사용자는 모임 [](https://www.microsoft.com/download/details.aspx?id=51659) 마이그레이션 도구를 사용하여 자신의 모임을 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-115">In these situations, end users can use the [Meeting Migration Tool](https://www.microsoft.com/download/details.aspx?id=51659) to migrate their own meetings instead.</span></span>

## <a name="how-mms-works"></a><span data-ttu-id="e5c2a-116">MMS 작동 방식</span><span class="sxs-lookup"><span data-stu-id="e5c2a-116">How MMS works</span></span>

<span data-ttu-id="e5c2a-117">특정 사용자에 대해 MMS가 트리거되면 해당 사용자에 대한 마이그레이션 요청이 큐에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-117">When MMS is triggered for a given user, a migration request for that user is placed in a queue.</span></span> <span data-ttu-id="e5c2a-118">경마 조건을 방지하기 위해 대기 중인 요청은 90분 이상이 지날 때까지 고의로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-118">To avoid any race conditions, the queued request is deliberately not processed until at least 90 minutes have gone by.</span></span> <span data-ttu-id="e5c2a-119">MMS가 요청을 처리하면 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-119">Once MMS processes the request, it performs the following tasks:</span></span>

1. <span data-ttu-id="e5c2a-120">해당 사용자의 사서함에서 해당 사용자가 구성하고 향후에 예약된 모든 기존 모임을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-120">It searches that user’s mailbox for all existing meetings organized by that user and scheduled in the future.</span></span>
2. <span data-ttu-id="e5c2a-121">사용자의 사서함에 있는 정보에 따라 정확한 시나리오에 따라 해당 사용자의 Teams 또는 비즈니스용 Skype Online에서 새 모임을 업데이트하거나 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-121">Based on the information found in the user’s mailbox, it either updates or schedules new meetings in either Teams or Skype for Business Online for that user, depending on the exact scenario.</span></span>
3. <span data-ttu-id="e5c2a-122">전자 메일 메시지에서 모임 세부 정보의 온라인 모임 블록을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-122">In the email message, it replaces the online meeting block in the meeting details.</span></span>
4. <span data-ttu-id="e5c2a-123">모임 이끌이를 대신하여 모든 모임 받는 사람에게 해당 모임의 업데이트된 버전을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-123">It sends the updated version of that meeting to all meeting recipients on behalf of the meeting organizer.</span></span> <span data-ttu-id="e5c2a-124">모임 초대 받은 이가 전자 메일에 업데이트된 모임 좌표가 있는 모임 업데이트를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-124">Meeting invitees will receive a meeting update with updated meeting coordinates in their email.</span></span> 

    ![MMS에 의해 업데이트되는 모임 블록](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

<span data-ttu-id="e5c2a-126">MMS가 트리거되는 시간부터 사용자의 모임이 마이그레이션될 때까지 일반적으로 약 2시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-126">From the time MMS is triggered, it typically takes about 2 hours until the user’s meetings are migrated.</span></span> <span data-ttu-id="e5c2a-127">그러나 사용자가 많은 수의 모임을 가지는 경우 시간이 더 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-127">However, if the user has a large number of meetings, it might take longer.</span></span> <span data-ttu-id="e5c2a-128">MMS에서 사용자에 대해 하나 이상의 모임을 마이그레이션하는 오류가 발생하면 24시간 동안 주기적으로 최대 9회까지 재시도합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-128">If MMS encounters an error migrating one or more meetings for the user, it will periodically retry up to 9 times over the span of 24 hours.</span></span>

<span data-ttu-id="e5c2a-129">**참고:**</span><span class="sxs-lookup"><span data-stu-id="e5c2a-129">**Notes**:</span></span>

- <span data-ttu-id="e5c2a-130">MMS는 모임이 마이그레이션된 경우 온라인 모임 정보 블록의 모든 것을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-130">MMS replaces everything in the online meeting information block when a meeting is migrated.</span></span> <span data-ttu-id="e5c2a-131">따라서 사용자가 해당 차단을 편집한 경우 해당 변경 내용을 덮어습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-131">Therefore, if a user has edited that block, their changes will be overwritten.</span></span> <span data-ttu-id="e5c2a-132">온라인 모임 정보 블록 외부의 모임 세부 정보에 있는 콘텐츠는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-132">Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span> <span data-ttu-id="e5c2a-133">즉, 모임 초대에 첨부된 모든 파일이 계속 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-133">This means any files attached to the meeting invite will still be included.</span></span> 
- <span data-ttu-id="e5c2a-134">웹용 Outlook에서 Skype 모임 추가 단추를 클릭하거나  Outlook용 Skype 모임 추가 기능을 사용하여 예약된 비즈니스용 Skype 또는 Microsoft Teams 모임만 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-134">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="e5c2a-135">사용자가 Skype 온라인 모임 정보를 한 모임에서 새 모임으로 복사하여 붙여 넣는 경우 원래 서비스에 모임이 아니기 때문에 새 모임이 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-135">If a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated since there is no meeting in the original service.</span></span>
- <span data-ttu-id="e5c2a-136">모임에서 만들거나 모임에 첨부된 모임 콘텐츠(화이트보드, 설문 조사 등)는 MMS가 실행된 후에 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-136">Meeting content that was created or attached to the meeting (whiteboards, polls, and so on) won't be retained after MMS runs.</span></span> <span data-ttu-id="e5c2a-137">모임 이끌이가 모임에 콘텐츠를 미리 첨부한 경우 MMS가 실행된 후 콘텐츠를 다시 만드셔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-137">If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
- <span data-ttu-id="e5c2a-138">일정 항목 및 Skype 모임 내에서 공유 모임 메모에 대한 링크도 덮어 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-138">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten.</span></span> <span data-ttu-id="e5c2a-139">OneNote에 저장된 실제 모임 메모는 여전히 있습니다. 덮어 작성된 공유 노트에 대한 링크일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-139">Note that the actual meeting notes stored in OneNote will still be there; it is only the link to the shared notes that is overwritten.</span></span>
- <span data-ttu-id="e5c2a-140">250명 이상의 참석자가 있는 모임(이끌이 포함)은 마이그레이션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-140">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
- <span data-ttu-id="e5c2a-141">초대 본문에 있는 일부 유니코드 문자가 다음과 같은 특수 문자 중 하나에 잘못 업데이트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-141">Some UNICODE characters in the body of the invite might be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>

## <a name="triggering-mms-for-a-user"></a><span data-ttu-id="e5c2a-142">사용자에 대한 MMS 트리거</span><span class="sxs-lookup"><span data-stu-id="e5c2a-142">Triggering MMS for a user</span></span>

<span data-ttu-id="e5c2a-143">이 섹션에서는 다음과 같은 각 경우에 MMS가 트리거될 때 발생하는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-143">This section describes what happens when MMS is triggered in each of the following cases:</span></span>

- <span data-ttu-id="e5c2a-144">사용자가 프레미스에서 클라우드로 마이그레이션된 경우</span><span class="sxs-lookup"><span data-stu-id="e5c2a-144">When a user is migrated from on-premises to the cloud</span></span>
- <span data-ttu-id="e5c2a-145">관리자가 사용자의 오디오 회의 설정을 변경하는 경우</span><span class="sxs-lookup"><span data-stu-id="e5c2a-145">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="e5c2a-146">TeamsUpgradePolicy의 사용자 모드가 TeamsOnly 또는 SfBWithTeamsCollabAndMeetings로 설정된 경우(Powershell 또는 Teams 관리 포털 사용)</span><span class="sxs-lookup"><span data-stu-id="e5c2a-146">When the user's mode in TeamsUpgradePolicy is set to either TeamsOnly or SfBWithTeamsCollabAndMeetings (using either Powershell or the Teams Admin Portal)</span></span>
- <span data-ttu-id="e5c2a-147">PowerShell cmdlet을 사용하는 경우 Start-CsExMeetingMigration</span><span class="sxs-lookup"><span data-stu-id="e5c2a-147">When you use the PowerShell cmdlet, Start-CsExMeetingMigration</span></span>

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a><span data-ttu-id="e5c2a-148">클라우드로의 프레미스 사용자를 이동할 때 모임 업데이트</span><span class="sxs-lookup"><span data-stu-id="e5c2a-148">Updating meetings when you move an on-premises user to the cloud</span></span>

<span data-ttu-id="e5c2a-149">MMS가 사용자에게 더 원활한 전환을 만드는 데 도움이 되는 가장 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-149">This is the most common scenario where MMS helps create a smoother transition for your users.</span></span> <span data-ttu-id="e5c2a-150">모임 마이그레이션이 없는 경우 사용자가 온라인으로 이동하면 비즈니스용 Skype Server의 사용자가 구성한 기존 모임이 더 이상 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-150">Without meeting migration, existing meetings organized by a user in Skype for Business Server on-premises would no longer work once the user is moved online.</span></span> <span data-ttu-id="e5c2a-151">따라서 사용자를 클라우드로 이동하기 위해 사용자 또는 관리 제어판을 사용하는 경우 기존 모임은 다음과 같이 자동으로 클라우드로 `Move-CsUser` 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-151">Therefore, when you use the on-premises admin tools (either `Move-CsUser` or the Admin Control Panel) to move a user to the cloud, existing meetings are automatically moved to the cloud as follows:</span></span>

- <span data-ttu-id="e5c2a-152">전환을 지정하면 모임이 Teams로 직접 마이그레이션되어 사용자가 `MoveToTeams` `Move-CsUser` TeamsOnly 모드로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-152">If the `MoveToTeams` switch in `Move-CsUser` is specified, meetings are migrated directly to Teams and the user will be in TeamsOnly mode.</span></span> <span data-ttu-id="e5c2a-153">이 스위치를 사용하려면 CU8 이상을 사용하는 비즈니스용 Skype Server 2015가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-153">Use of this switch requires Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="e5c2a-154">이러한 사용자는 비즈니스용 Skype 클라이언트 또는 Skype 모임 앱을 사용하여 초대될 수 있는 비즈니스용 Skype 모임에 계속 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-154">These users can still join any Skype for Business meeting they may be invited to, using either the Skype for Business client or the Skype Meeting App.</span></span>
- <span data-ttu-id="e5c2a-155">그렇지 않으면 모임이 비즈니스용 Skype Online으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-155">Otherwise meetings are migrated to Skype for Business Online.</span></span>

<span data-ttu-id="e5c2a-156">두 경우 모두 사용자가 클라우드로 이동하기 전에 오디오 회의 라이선스가 할당된 경우 전화 접속 좌표를 사용하여 모임이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-156">In either case, if the user has been assigned an Audio Conferencing license before being moved to the cloud, the meetings will be created with dial-in coordinates.</span></span> <span data-ttu-id="e5c2a-157">사용자를 프레미스에서 클라우드로 이동하고 해당 사용자가 오디오 회의를 사용하려는 경우 모임 마이그레이션이 한 개만 트리거될 수 있도록 사용자를 이동하기 전에 먼저 오디오 회의를 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-157">If you move a user from on-premises to the cloud and you intend for that user to use Audio Conferencing, we recommend that you first assign the audio conference before you move the user so that only 1 meeting migration is triggered.</span></span>


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="e5c2a-158">사용자의 오디오 회의 설정이 변경될 때 모임 업데이트</span><span class="sxs-lookup"><span data-stu-id="e5c2a-158">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="e5c2a-159">다음과 같은 경우 MMS는 기존 비즈니스용 Skype 및 Microsoft Teams 모임을 업데이트하여 전화 접속 좌표를 추가, 제거 또는 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-159">In the following cases, MMS will update existing Skype for Business and Microsoft Teams meetings to add, remove, or modify dial-in coordinates:</span></span>

- <span data-ttu-id="e5c2a-160">사용자에게 Microsoft 오디오 회의 서비스 라이선스를 할당하거나 제거하는 경우 해당 사용자가 타사 오디오 회의 공급자에 대해 사용하도록 설정되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-160">When you assign or remove a Microsoft Audio Conferencing service license to a user, and that user is not enabled for a third-party audio conferencing provider.</span></span>
- <span data-ttu-id="e5c2a-161">사용자의 오디오 회의 공급자를 다른 공급자에서 Microsoft로 변경하는 경우 사용자에게 Microsoft 오디오 회의 라이선스가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-161">When you change the audio conferencing provider of a user from any other provider to Microsoft, provided the user is assigned a Microsoft Audio Conferencing license.</span></span> <span data-ttu-id="e5c2a-162">자세한 내용은 Microsoft를 오디오 회의 공급자로 [할당을 참조하세요.](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)</span><span class="sxs-lookup"><span data-stu-id="e5c2a-162">For more information, see [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span> <span data-ttu-id="e5c2a-163">또한 앞서 발표한 2019년 4월 1일부터 타사 오디오 회의 공급자 [ACP]에 [](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)대한 지원이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-163">Also note that support for third party audio conferencing providers [ACP] is scheduled for end of life on April 1, 2019, as [previously announced](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).</span></span>
- <span data-ttu-id="e5c2a-164">사용자에 대한 오디오 회의를 설정하거나 사용하지 않도록 설정하는 경우.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-164">When you enable or disable audio conferencing for a user.</span></span>
- <span data-ttu-id="e5c2a-165">공용 모임을 사용하도록 구성된 사용자의 회의 ID를 변경하거나 다시 설정할 때</span><span class="sxs-lookup"><span data-stu-id="e5c2a-165">When you change or reset the conference ID for a user configured to use public meetings.</span></span>
- <span data-ttu-id="e5c2a-166">사용자를 새 오디오 회의 브리지로 이동하는 경우</span><span class="sxs-lookup"><span data-stu-id="e5c2a-166">When you move the user to a new audio conferencing bridge.</span></span>
- <span data-ttu-id="e5c2a-167">오디오 회의 브리지의 전화 번호가 부재 중이면</span><span class="sxs-lookup"><span data-stu-id="e5c2a-167">When a phone number from a audio conferencing bridge is unassigned.</span></span> <span data-ttu-id="e5c2a-168">이는 추가 단계가 필요한 복잡한 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-168">This is a complex scenario that requires additional steps.</span></span> <span data-ttu-id="e5c2a-169">자세한 내용은 오디오 회의 브리지의 전화 번호 변경을 [참조하세요.](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="e5c2a-169">For more information, see [Change the phone numbers on your audio conferencing bridge](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

<span data-ttu-id="e5c2a-170">사용자의 오디오 회의 설정에 대한 모든 변경 내용이 MMS를 트리거하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-170">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="e5c2a-171">특히 다음 두 가지 변경으로 인해 MMS가 모임을 업데이트하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-171">Specifically, the following two changes won't result in MMS updating meetings:</span></span>

- <span data-ttu-id="e5c2a-172">모임 이끌이의 SIP 주소(해당 SIP 사용자 이름 또는 해당 SIP 도메인)를 변경하는 경우</span><span class="sxs-lookup"><span data-stu-id="e5c2a-172">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
- <span data-ttu-id="e5c2a-173">이 명령을 사용하여 조직의 모임 URL을 `Update-CsTenantMeetingUrl` 변경하는 경우</span><span class="sxs-lookup"><span data-stu-id="e5c2a-173">When you change your organization's meeting URL using the `Update-CsTenantMeetingUrl` command.</span></span>


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a><span data-ttu-id="e5c2a-174">TeamsUpgradePolicy를 할당할 때 모임 업데이트</span><span class="sxs-lookup"><span data-stu-id="e5c2a-174">Updating meetings when assigning TeamsUpgradePolicy</span></span>

<span data-ttu-id="e5c2a-175">기본적으로 모임 마이그레이션은 사용자에게 with 또는 .의 인스턴스가 부여될 때 자동으로 `TeamsUpgradePolicy` `mode=TeamsOnly` `mode= SfBWithTeamsCollabAndMeetings` 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-175">By default, meeting migration is automatically triggered when a user is granted an instance of `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode= SfBWithTeamsCollabAndMeetings`.</span></span> <span data-ttu-id="e5c2a-176">이러한 모드 중 하나를 부여할 때 모임을 마이그레이션하지 않도록 하려는 경우(PowerShell을 사용하는 경우) 사용자의 공존 모드(Teams 관리 포털을 사용하는 경우)를 설정할 때 모임 마이그레이션 확인란을 선택하지 `MigrateMeetingsToTeams $false` `Grant-CsTeamsUpgradePolicy` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-176">If you do not want to migrate meetings when granting either of these modes, then specify `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` (if using PowerShell) or uncheck the box to migrate meetings when setting a user's coexistence mode (if using the Teams admin portal).</span></span>

<span data-ttu-id="e5c2a-177">또한 다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-177">Also note the following:</span></span>

- <span data-ttu-id="e5c2a-178">모임 마이그레이션은 특정 사용자에게 부여할 `TeamsUpgradePolicy` 때만 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-178">Meeting migration is only invoked when you grant `TeamsUpgradePolicy` for a specific user.</span></span> <span data-ttu-id="e5c2a-179">테넌트 전체에 부여하거나 부여하는 경우 모임 `TeamsUpgradePolicy` `mode=TeamsOnly` `mode=SfBWithTeamsCollabAndMeetings` 마이그레이션이 호출되지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="e5c2a-179">If you grant `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode=SfBWithTeamsCollabAndMeetings` on a *tenant-wide* basis, meeting migration is not invoked.</span></span>
- <span data-ttu-id="e5c2a-180">사용자가 온라인에 있는 경우 사용자에게 TeamsOnly 모드만 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-180">A user can only be granted TeamsOnly mode if the user is homed online.</span></span> <span data-ttu-id="e5c2a-181">홈에 있는 사용자는 앞서 설명한 바와 같이 `Move-CsUser` 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-181">Users that are homed on-premises must be moved using `Move-CsUser` as previously described.</span></span>
- <span data-ttu-id="e5c2a-182">TeamsOnly 또는 SfBWithTeamsCollabAndMeetings가 아닌 모드를 부여하는 것은 기존 Teams 모임을 비즈니스용 Skype 모임으로 변환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-182">Granting a mode other than TeamsOnly or SfBWithTeamsCollabAndMeetings does not convert existing Teams meetings to Skype for Business meetings.</span></span>

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a><span data-ttu-id="e5c2a-183">PowerShell cmdlet을 통해 수동으로 모임 마이그레이션 트리거</span><span class="sxs-lookup"><span data-stu-id="e5c2a-183">Trigger Meeting Migration manually via PowerShell cmdlet</span></span>

<span data-ttu-id="e5c2a-184">관리자는 자동 모임 마이그레이션 외에도 cmdlet을 실행하여 사용자에 대한 모임 마이그레이션을 수동으로 트리거할 수 `Start-CsExMeetingMigration` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-184">In addition to automatic meeting migrations, admins can manually trigger meeting migration for a user by running the cmdlet `Start-CsExMeetingMigration`.</span></span> <span data-ttu-id="e5c2a-185">이 cmdlet은 지정된 사용자에 대한 마이그레이션 요청을 큐에 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-185">This cmdlet queues a migration request for the specified user.</span></span>  <span data-ttu-id="e5c2a-186">필수 매개 변수 외에도 두 개의 선택적 매개 변수를 사용하며, 이를 통해 모임을 마이그레이션하는 방법을 지정할 `Identity` `SourceMeetingType` 수 `TargetMeetingType` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-186">In addition to the required `Identity` parameter, it takes two optional parameters, `SourceMeetingType` and `TargetMeetingType`, which allow you to specify how to migrate meetings:</span></span>

<span data-ttu-id="e5c2a-187">**TargetMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="e5c2a-187">**TargetMeetingType:**</span></span>

- <span data-ttu-id="e5c2a-188">비즈니스용 Skype 모임을 비즈니스용 Skype 모임으로 유지하고 Teams 모임은 Teams 모임으로 `TargetMeetingType Current` 유지된다고 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-188">Using `TargetMeetingType Current` specifies that Skype for Business meetings remain Skype for Business meetings and Teams meetings remain Teams meetings.</span></span> <span data-ttu-id="e5c2a-189">그러나 오디오 회의 좌표가 변경될 수 있으며 모든 비즈니스용 Skype 모임은 비즈니스용 Skype Online으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-189">However audio conferencing coordinates might be changed, and any on-premises Skype for Business meetings would be migrated to Skype for Business Online.</span></span> <span data-ttu-id="e5c2a-190">TargetMeetingType의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-190">This is the default value for TargetMeetingType.</span></span>
- <span data-ttu-id="e5c2a-191">모임이 온라인 또는 비즈니스용 Skype에서 호스팅되는지 여부와 오디오 회의 업데이트가 필요한지 여부에 관계없이 기존 모임을 Teams로 마이그레이션해야 하게 `TargetMeetingType Teams` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-191">Using `TargetMeetingType Teams` specifies that any existing meeting must be migrated to Teams, regardless of whether the meeting is hosted in Skype for Business online or on-premises, and regardless of whether any audio conferencing updates are required.</span></span> 

<span data-ttu-id="e5c2a-192">**SourceMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="e5c2a-192">**SourceMeetingType:**</span></span>
- <span data-ttu-id="e5c2a-193">사용은 비즈니스용 Skype 모임(온라인 또는 온라인)만 업데이트해야 한다고 `SourceMeetingType SfB` 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-193">Using `SourceMeetingType SfB` indicates that only Skype for Business meetings (whether on-premises or online) should be updated.</span></span>
- <span data-ttu-id="e5c2a-194">사용은 `SourceMeetingType Teams` Teams 모임만 업데이트해야 한다고 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-194">Using `SourceMeetingType Teams` indicates that only Teams meetings should be updated.</span></span>
- <span data-ttu-id="e5c2a-195">사용 시 비즈니스용 Skype 모임과 Teams 모임을 모두 `SourceMeetingType All` 업데이트해야 한다고 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-195">Using `SourceMeetingType All` indicates that both Skype for Business meetings and Teams meetings should be updated.</span></span> <span data-ttu-id="e5c2a-196">SourceMeetingType의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-196">This is the default value for SourceMeetingType.</span></span>
    

<span data-ttu-id="e5c2a-197">아래 예제에서는 모든 모임이 Teams로 마이그레이션하도록 ashaw@contoso.com 사용자에 대한 모임 마이그레이션을 시작하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-197">The example below shows how to initiate meeting migration for user ashaw@contoso.com so that all meetings are migrated to Teams:</span></span>

```PowerShell
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a><span data-ttu-id="e5c2a-198">MMS 관리</span><span class="sxs-lookup"><span data-stu-id="e5c2a-198">Managing MMS</span></span>

<span data-ttu-id="e5c2a-199">이 Windows PowerShell 사용하여 진행되는 마이그레이션의 상태를 확인하고, 수동으로 모임 마이그레이션을 트리거하고, 마이그레이션을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-199">Using Windows PowerShell, you can check the status of ongoing migrations, manually trigger meeting migration, and disable migration altogether.</span></span> 

### <a name="check-the-status-of-meeting-migrations"></a><span data-ttu-id="e5c2a-200">모임 마이그레이션 상태 확인</span><span class="sxs-lookup"><span data-stu-id="e5c2a-200">Check the status of meeting migrations</span></span>

<span data-ttu-id="e5c2a-201">`Get-CsMeetingMigrationStatus`cmdlet을 사용하여 모임 마이그레이션의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-201">You use the `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations.</span></span> <span data-ttu-id="e5c2a-202">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-202">Below are some examples.</span></span>

- <span data-ttu-id="e5c2a-203">모든 MMS 마이그레이션의 요약 상태를 확인하려는 경우 모든 마이그레이션 상태의 테이블형 보기를 제공하는 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-203">To get a summary status of all MMS migrations, run the following command which provides a tabular view of all migration states:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- <span data-ttu-id="e5c2a-204">특정 기간 내에 모든 마이그레이션에 대한 전체 세부 정보를 얻은 다음 매개 `StartTime` 변수를 `EndTime` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-204">To get full details of all migrations within a specific time period, use the `StartTime` and `EndTime` parameters.</span></span> <span data-ttu-id="e5c2a-205">예를 들어 다음 명령은 2018년 10월 1일에서 2018년 10월 8일까지 발생한 모든 마이그레이션에 대한 전체 세부 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-205">For example, the following command will return full details on all migrations that occurred from October 1, 2018 to October 8, 2018.</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- <span data-ttu-id="e5c2a-206">특정 사용자에 대한 마이그레이션 상태를 확인하려는 경우 매개 변수를 `Identity` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-206">To check the status of migration for a specific user, use the `Identity` parameter.</span></span> <span data-ttu-id="e5c2a-207">예를 들어 다음 명령은 사용자에 대한 상태를 ashaw@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-207">For example, the following command will return the status for the user ashaw@contoso.com:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
<span data-ttu-id="e5c2a-208">마이그레이션에 실패한 경우 사용자가 해결할 때까지 해당 사용자가 구성한 모임에 전화 접속할 수 없습니다. 가능한 한 빨리 이러한 문제를 해결하기 위해 조치를 취하세요.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-208">If you see any migrations that have failed, take action to resolve these issues as soon as possible, since people won't be able to dial-in to the meetings organized by those users until you resolve them.</span></span> <span data-ttu-id="e5c2a-209">실패한 상태의 마이그레이션을 표시하는 경우 `Get-CsMeetingMigrationStatus` 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-209">If `Get-CsMeetingMigrationStatus` shows any migrations in a failed state, perform these steps:</span></span>
 
1. <span data-ttu-id="e5c2a-210">영향을 받는 사용자를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-210">Determine which users are affected.</span></span> <span data-ttu-id="e5c2a-211">다음 명령을 실행하여 영향을 받는 사용자 목록 및 보고된 특정 오류를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-211">Run the following command to get the list of affected users, and the specific error that was reported:</span></span>

    ```PowerShell
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. <span data-ttu-id="e5c2a-212">영향을 받는 각 사용자에 대해 모임 마이그레이션 도구를 실행하여 모임을 수동으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-212">For each affected user, run the Meeting Migration Tool to manually migrate their meetings.</span></span>

3. <span data-ttu-id="e5c2a-213">마이그레이션이 모임 마이그레이션 도구에서 여전히 작동하지 않는 경우 다음 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-213">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>

    - <span data-ttu-id="e5c2a-214">사용자가 새 Skype 모임을 만들게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-214">Have the users create new Skype meetings.</span></span>
    - <span data-ttu-id="e5c2a-215">[고객 지원에 문의합니다.](https://go.microsoft.com/fwlink/p/?LinkID=518322)</span><span class="sxs-lookup"><span data-stu-id="e5c2a-215">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>


### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="e5c2a-216">MMS 사용 및 사용 안 림</span><span class="sxs-lookup"><span data-stu-id="e5c2a-216">Enabling and disabling MMS</span></span>

<span data-ttu-id="e5c2a-217">MMS는 기본적으로 모든 조직에 대해 사용하도록 설정되지만 다음과 같이 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-217">MMS is enabled by default for all organizations, but it can be disabled as follows:</span></span>

- <span data-ttu-id="e5c2a-218">테넌트에 대해 완전히 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="e5c2a-218">Disable entirely for the tenant.</span></span> 
- <span data-ttu-id="e5c2a-219">오디오 회의와 관련된 변경 내용에 한해 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-219">Disable only for changes related to audio conferencing.</span></span> <span data-ttu-id="e5c2a-220">이 경우 사용자가 클라우드로 마이그레이션되거나 TeamsOnly 모드 또는 SfBWithTeamsCollabAndMeetings 모드를 부여할 때 MMS가 계속 `TeamsUpgradePolicy` 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-220">In this case, MMS will still run when a user is migrated from on-premises to the cloud or when you grant TeamsOnly mode or SfBWithTeamsCollabAndMeetings mode in `TeamsUpgradePolicy`.</span></span>

<span data-ttu-id="e5c2a-221">예를 들어 조직의 오디오 회의 설정을 대폭 변경하는 동안 수동으로 모든 모임을 마이그레이션하거나 MMS를 일시적으로 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-221">For example, you may want to manually migrate all meetings or temporarily disable MMS while making substantial changes to the audio conferencing settings for your organization</span></span>

<span data-ttu-id="e5c2a-222">조직에 대해 MMS를 사용할 수 있도록 설정되어 있는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-222">To see if MMS is enabled for your organization, run the following command.</span></span> <span data-ttu-id="e5c2a-223">매개 변수가 .인 경우 `MeetingMigrationEnabled` MMS가 `$true` 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-223">MMS is enabled if the `MeetingMigrationEnabled` parameter is `$true`.</span></span>
```PowerShell
Get-CsTenantMigrationConfiguration
```
<span data-ttu-id="e5c2a-224">MMS를 완전히 사용 또는 사용하지 않도록 설정하려면 명령을 `Set-CsTenantMigrationConfiguration` 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-224">To enable or disable MMS entirely, use the `Set-CsTenantMigrationConfiguration` command.</span></span> <span data-ttu-id="e5c2a-225">예를 들어 MMS를 사용하지 않도록 설정하는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-225">For example, to disable MMS, run the following command:</span></span>

```PowerShell
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
<span data-ttu-id="e5c2a-226">조직에서 MMS를 사용하도록 설정하고 오디오 회의 업데이트에 대해 사용하도록 설정되어 있는지 확인하려는 경우 출력의 매개 변수 값을 `AutomaticallyMigrateUserMeetings` `Get-CsOnlineDialInConferencingTenantSettings` 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-226">If MMS is enabled in the organization and you want to check if it is enabled for audio conferencing updates, check the value of the `AutomaticallyMigrateUserMeetings` parameter in the output from `Get-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="e5c2a-227">오디오 회의에 MMS를 사용 또는 사용하지 않도록 설정하려면 `Set-CsOnlineDialInConferencingTenantSettings` .</span><span class="sxs-lookup"><span data-stu-id="e5c2a-227">To enable or disable MMS for audio conferencing, use `Set-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="e5c2a-228">예를 들어 오디오 회의에 MMS를 사용하지 않도록 설정하는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2a-228">For example, to disable MMS for audio conferencing, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a><span data-ttu-id="e5c2a-229">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e5c2a-229">Related topics</span></span>

[<span data-ttu-id="e5c2a-230">Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매</span><span class="sxs-lookup"><span data-stu-id="e5c2a-230">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[<span data-ttu-id="e5c2a-231">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="e5c2a-231">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
