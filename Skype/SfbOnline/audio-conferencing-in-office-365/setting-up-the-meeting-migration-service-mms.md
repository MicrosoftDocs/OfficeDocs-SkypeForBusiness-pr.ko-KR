---
title: MMS (모임 마이그레이션 서비스) 사용
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: MMS (모임 마이그레이션 서비스)는 백그라운드에서 실행 되며 사용자를 위해 비즈니스용 Skype 및 Microsoft 팀 모임을 자동으로 업데이트 하는 서비스입니다. MMS는 사용자가 모임 마이그레이션 도구를 실행 하 여 비즈니스용 Skype 및 Microsoft 팀 모임을 업데이트 하지 않아도 되도록 설계 되었습니다.
ms.openlocfilehash: 3f643f20937fd13b0d9576640487da30f17dd7bf
ms.sourcegitcommit: 8db50c46992dccf54c1d4be58d8a0d21ec64ddd0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772282"
---
# <a name="using-the-meeting-migration-service-mms"></a><span data-ttu-id="11731-104">MMS (모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="11731-104">Using the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="11731-105">이 MMS (모임 마이그레이션 서비스)는 다음과 같은 시나리오에서 사용자의 기존 모임을 업데이트 하는 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="11731-105">The Meeting Migration Service (MMS) is service that updates a user’s existing meetings in the following scenarios:</span></span>

- <span data-ttu-id="11731-106">사용자가 온-프레미스에서 클라우드로 마이그레이션 (비즈니스용 Skype Online 또는 팀 전용 등)</span><span class="sxs-lookup"><span data-stu-id="11731-106">When a user is migrated from on-premises to the cloud (whether to Skype for Business Online or to TeamsOnly).</span></span>
- <span data-ttu-id="11731-107">관리자가 사용자의 오디오 회의 설정을 변경 하는 경우</span><span class="sxs-lookup"><span data-stu-id="11731-107">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="11731-108">온라인 사용자가 팀 으로만 업그레이드 되거나 TeamsUpgradePolicy의 사용자 모드가 SfBwithTeamsCollabAndMeetings로 설정 된 경우</span><span class="sxs-lookup"><span data-stu-id="11731-108">When an online user is upgraded to Teams only, or when a user's mode in TeamsUpgradePolicy is set to SfBwithTeamsCollabAndMeetings</span></span>
- <span data-ttu-id="11731-109">PowerShell을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="11731-109">When you use PowerShell</span></span> 


<span data-ttu-id="11731-110">기본적으로 MMS는 이러한 각 경우에 자동으로 트리거 되지만, 관리자는 테 넌 트 수준에서 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-110">By default, MMS is automatically triggered in each of these cases, although admins can disable it at the tenant level.</span></span> <span data-ttu-id="11731-111">또한 관리자는 PowerShell cmdlet을 사용 하 여 지정 된 사용자에 대 한 모임 마이그레이션을 수동으로 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-111">In addition, admins can use a PowerShell cmdlet to manually trigger meeting migration for a given user.</span></span>


<span data-ttu-id="11731-112">**제한 사항**: 다음 중 하나라도 적용 되 면 모임 마이그레이션 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-112">**Limitations**: The meeting migration service can't be used if any of the following apply:</span></span>

- <span data-ttu-id="11731-113">사용자의 사서함이 Exchange 온-프레미스에 호스팅 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-113">The user’s mailbox is hosted in Exchange on-premises.</span></span>
- <span data-ttu-id="11731-114">사용자가 클라우드에서 비즈니스용 Skype Server 온-프레미스로 마이그레이션 중입니다.</span><span class="sxs-lookup"><span data-stu-id="11731-114">The user is being migrated from the cloud to Skype for Business Server on-premises.</span></span>

<span data-ttu-id="11731-115">이러한 상황에서는 최종 사용자가 [모임 마이그레이션 도구](https://www.microsoft.com/en-us/download/details.aspx?id=51659) 를 사용 하 여 자신의 모임을 대신 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-115">In these situations, end users can use the [Meeting Migration Tool](https://www.microsoft.com/en-us/download/details.aspx?id=51659) to migrate their own meetings instead.</span></span>

## <a name="how-mms-works"></a><span data-ttu-id="11731-116">MMS 작동 방식</span><span class="sxs-lookup"><span data-stu-id="11731-116">How MMS works</span></span>

<span data-ttu-id="11731-117">지정 된 사용자에 대해 MMS를 트리거한 경우 해당 사용자에 대 한 마이그레이션 요청이 큐에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11731-117">When MMS is triggered for a given user, a migration request for that user is placed in a queue.</span></span> <span data-ttu-id="11731-118">경합 상태를 방지 하기 위해 최소 90 분이 없어질 때까지 대기 요청이 처리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-118">To avoid any race conditions, the queued request is deliberately not processed until at least 90 minutes have gone by.</span></span> <span data-ttu-id="11731-119">MMS는 요청을 처리 하 고 나면 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-119">Once MMS processes the request, it performs the following tasks:</span></span>

1. <span data-ttu-id="11731-120">해당 사용자가 구성한 모든 기존 모임에 대해 해당 사용자의 사서함을 검색 하 고 나중에 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-120">It searches that user’s mailbox for all existing meetings organized by that user and scheduled in the future.</span></span>
2. <span data-ttu-id="11731-121">사용자의 사서함에 있는 정보에 따라 정확한 시나리오에 따라 팀 또는 비즈니스용 Skype Online에서 해당 사용자의 새 모임을 업데이트 하거나 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-121">Based on the information found in the user’s mailbox, it either updates or schedules new meetings in either Teams or Skype for Business Online for that user, depending on the exact scenario.</span></span>
3. <span data-ttu-id="11731-122">전자 메일 메시지에서 모임 세부 정보에서 온라인 모임 블록을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="11731-122">In the email message, it replaces the online meeting block in the meeting details.</span></span>
4. <span data-ttu-id="11731-123">모임 이끌이를 대신 하 여 모든 모임 받는 사람에 게 해당 모임의 업데이트 된 버전을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="11731-123">It sends the updated version of that meeting to all meeting recipients on behalf of the meeting organizer.</span></span> <span data-ttu-id="11731-124">모임 초대 대 상자는 전자 메일에 업데이트 된 모임 좌표가 있는 모임 업데이트를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-124">Meeting invitees will receive a meeting update with updated meeting coordinates in their email.</span></span> 

    ![MMS를 통해 업데이트 되는 모임 블록](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)

<span data-ttu-id="11731-126">MMS를 트리거하는 시점부터, 일반적으로 사용자의 모임이 마이그레이션될 때까지 약 2 시간이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11731-126">From the time MMS is triggered, it typically takes about 2 hours until the user’s meetings are migrated.</span></span> <span data-ttu-id="11731-127">그러나 사용자에 게 많은 모임이 있는 경우에는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-127">However, if the user has a large number of meetings, it might take longer.</span></span> <span data-ttu-id="11731-128">MMS에서 사용자에 대 한 하나 이상의 모임을 마이그레이션하는 동안 오류가 발생 하면 24 시간 범위 동안 최대 9 번까지 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-128">If MMS encounters an error migrating one or more meetings for the user, it will periodically retry up to 9 times over the span of 24 hours.</span></span>

<span data-ttu-id="11731-129">**참고**사항:</span><span class="sxs-lookup"><span data-stu-id="11731-129">**Notes**:</span></span>

- <span data-ttu-id="11731-130">모임이 마이그레이션될 때 온라인 모임 정보 블록의 모든 내용을 MMS로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="11731-130">MMS replaces everything in the online meeting information block when a meeting is migrated.</span></span> <span data-ttu-id="11731-131">따라서 사용자가 해당 블록을 편집 하면 해당 변경 내용을 덮어쓰게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11731-131">Therefore, if a user has edited that block, their changes will be overwritten.</span></span> <span data-ttu-id="11731-132">온라인 모임 정보 블록 외부의 모임 세부 정보에 있는 모든 콘텐츠는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-132">Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
- <span data-ttu-id="11731-133">웹용 Outlook에서 또는 Outlook 용 Skype 모임 추가 기능을 사용 하 여 **skype 모임 추가** 단추를 클릭 하 여 예약 된 비즈니스용 Skype 또는 Microsoft 팀 모임만 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="11731-133">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated.</span></span> <span data-ttu-id="11731-134">사용자가 한 모임에서 Skype online 모임 정보를 복사 하 여 새 모임에 붙여 넣으면 원래 서비스에 모임이 없기 때문에 새 모임이 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-134">If a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated since there is no meeting in the original service.</span></span>
- <span data-ttu-id="11731-135">MMS를 실행 한 후에는 모임에 만들었거나 연결 된 모임 콘텐츠 (화이트 보드, 설문 등)가 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-135">Meeting content that was created or attached to the meeting (whiteboards, polls, and so on) won't be retained after MMS runs.</span></span> <span data-ttu-id="11731-136">모임 이끌이가 미리 모임에 콘텐츠를 첨부 한 경우 MMS를 실행 한 후 콘텐츠를 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-136">If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
- <span data-ttu-id="11731-137">또한 Skype 모임 내에서 일정 항목의 공유 모임 메모에 대 한 링크도 덮어쓰게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11731-137">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten.</span></span> <span data-ttu-id="11731-138">OneNote에 저장 된 실제 모임 메모는 그대로 유지 됩니다. 이는 덮어쓴 공유 메모에 대 한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="11731-138">Note that the actual meeting notes stored in OneNote will still be there; it is only the link to the shared notes that is overwritten.</span></span>
- <span data-ttu-id="11731-139">250 개 이상의 참석자 (이끌이 포함)가 포함 된 모임은 마이그레이션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-139">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
- <span data-ttu-id="11731-140">초대 본문의 일부 유니코드 문자가 ï, ¿, 1/2, 특수 문자 중 하나로 잘못 업데이트 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-140">Some UNICODE characters in the body of the invite might be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>

## <a name="triggering-mms-for-a-user"></a><span data-ttu-id="11731-141">사용자의 MMS 트리거</span><span class="sxs-lookup"><span data-stu-id="11731-141">Triggering MMS for a user</span></span>

<span data-ttu-id="11731-142">이 섹션에서는 다음과 같은 각 경우에 MMS를 트리거할 때 수행 되는 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-142">This section describes what happens when MMS is triggered in each of the following cases:</span></span>

- <span data-ttu-id="11731-143">사용자가 온-프레미스에서 클라우드로 마이그레이션 되는 경우</span><span class="sxs-lookup"><span data-stu-id="11731-143">When a user is migrated from on-premises to the cloud</span></span>
- <span data-ttu-id="11731-144">관리자가 사용자의 오디오 회의 설정을 변경 하는 경우</span><span class="sxs-lookup"><span data-stu-id="11731-144">When an admin makes a change to the user’s audio conferencing settings</span></span> 
- <span data-ttu-id="11731-145">TeamsUpgradePolicy의 사용자 모드가 TeamsOnly 또는 SfBWithTeamsCollabAndMeetings로 설정 된 경우 (Powershell 또는 팀 관리 포털 사용)</span><span class="sxs-lookup"><span data-stu-id="11731-145">When the user's mode in TeamsUpgradePolicy is set to either TeamsOnly or SfBWithTeamsCollabAndMeetings (using either Powershell or the Teams Admin Portal)</span></span>
- <span data-ttu-id="11731-146">PowerShell cmdlet을 사용 하는 경우 시작-CsExMeetingMigration</span><span class="sxs-lookup"><span data-stu-id="11731-146">When you use the PowerShell cmdlet, Start-CsExMeetingMigration</span></span>

### <a name="updating-meetings-when-you-move-an-on-premises-user-to-the-cloud"></a><span data-ttu-id="11731-147">온-프레미스 사용자를 클라우드로 이동할 때 모임 업데이트</span><span class="sxs-lookup"><span data-stu-id="11731-147">Updating meetings when you move an on-premises user to the cloud</span></span>

<span data-ttu-id="11731-148">이는 MMS에서 사용자에 게 원활한 전환을 만들기 위해 사용 하는 가장 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="11731-148">This is the most common scenario where MMS helps create a smoother transition for your users.</span></span> <span data-ttu-id="11731-149">모임 마이그레이션이 없으면 사용자가 온라인으로 이동 하면 비즈니스용 Skype Server 온-프레미스의 사용자가 구성한 기존 모임이 더 이상 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-149">Without meeting migration, existing meetings organized by a user in Skype for Business Server on-premises would no longer work once the user is moved online.</span></span> <span data-ttu-id="11731-150">따라서 사용자를 클라우드로 이동 하기 위해 온-프레미스 관리 도구 `Move-CsUser` (또는 관리 제어판)를 사용 하는 경우 다음과 같이 기존 모임이 클라우드로 자동으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11731-150">Therefore, when you use the on-premises admin tools (either `Move-CsUser` or the Admin Control Panel) to move a user to the cloud, existing meetings are automatically moved to the cloud as follows:</span></span>

- <span data-ttu-id="11731-151">If `MoveToTeams` 스위치 `Move-CsUser` 를 지정 하면 모임이 팀으로 직접 마이그레이션되고 사용자는 teamsonly 모드에 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11731-151">If the `MoveToTeams` switch in `Move-CsUser` is specified, meetings are migrated directly to Teams and the user will be in TeamsOnly mode.</span></span> <span data-ttu-id="11731-152">이 스위치를 사용 하려면 비즈니스용 Skype 서버 2015 (CU8 이상)이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-152">Use of this switch requires Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="11731-153">이러한 사용자는 비즈니스용 skype 클라이언트 또는 Skype 모임 앱을 사용 하 여 초대를 받을 수 있는 비즈니스용 Skype 모임에 계속 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-153">These users can still join any Skype for Business meeting they may be invited to, using either the Skype for Business client or the Skype Meeting App.</span></span>
- <span data-ttu-id="11731-154">그렇지 않으면 모임이 비즈니스용 Skype Online으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="11731-154">Otherwise meetings are migrated to Skype for Business Online.</span></span>

<span data-ttu-id="11731-155">두 경우 모두 사용자에 게 클라우드로 이동 하기 전에 오디오 회의 라이선스가 할당 되 면 전화 접속 좌표를 사용 하 여 모임이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11731-155">In either case, if the user has been assigned an Audio Conferencing license before being moved to the cloud, the meetings will be created with dial-in coordinates.</span></span> <span data-ttu-id="11731-156">사용자를 온-프레미스에서 클라우드로 이동 하 고 해당 사용자가 오디오 회의를 사용 하려는 경우에는 먼저 오디오 회의를 할당 한 후 1 회의 마이그레이션과만 트리거 되도록 사용자를 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-156">If you move a user from on-premises to the cloud and you intend for that user to use Audio Conferencing, we recommend that you first assign the audio conference before you move the user so that only 1 meeting migration is triggered.</span></span>


### <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="11731-157">사용자의 오디오 회의 설정이 변경 될 때 모임 업데이트</span><span class="sxs-lookup"><span data-stu-id="11731-157">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="11731-158">다음 경우에 MMS는 전화 접속 좌표를 추가, 제거 또는 수정 하기 위해 기존 비즈니스용 Skype 및 Microsoft 팀 모임을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-158">In the following cases, MMS will update existing Skype for Business and Microsoft Teams meetings to add, remove, or modify dial-in coordinates:</span></span>

- <span data-ttu-id="11731-159">사용자에 게 Microsoft 오디오 회의 서비스 라이선스를 할당 하거나 제거 하는 경우 해당 사용자는 타사 오디오 회의 공급자에 대해 사용 하도록 설정 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11731-159">When you assign or remove a Microsoft Audio Conferencing service license to a user, and that user is not enabled for a third-party audio conferencing provider.</span></span>
- <span data-ttu-id="11731-160">사용자가 Microsoft 오디오 회의 라이선스를 할당 받은 경우 다른 공급자에서 Microsoft로 사용자의 오디오 회의 공급자를 변경 하는 경우</span><span class="sxs-lookup"><span data-stu-id="11731-160">When you change the audio conferencing provider of a user from any other provider to Microsoft, provided the user is assigned a Microsoft Audio Conferencing license.</span></span> <span data-ttu-id="11731-161">자세한 내용은 [Microsoft를 오디오 회의 공급자로 지정](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="11731-161">For more information, see [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span> <span data-ttu-id="11731-162">또한 [이전에 발표](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers)된 것 처럼 2019 년 4 월 1 일에는 제 3 자 오디오 회의 공급자에 대 한 지원이 예약 되어 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="11731-162">Also note that support for third party audio conferencing providers [ACP] is scheduled for end of life on April 1, 2019, as [previously announced](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/end-of-integration-with-3rd-party-providers).</span></span>
- <span data-ttu-id="11731-163">사용자에 대해 오디오 회의를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-163">When you enable or disable audio conferencing for a user.</span></span>
- <span data-ttu-id="11731-164">공용 모임을 사용 하도록 구성 된 사용자의 전화 회의 ID를 변경 하거나 다시 설정 하는 경우</span><span class="sxs-lookup"><span data-stu-id="11731-164">When you change or reset the conference ID for a user configured to use public meetings.</span></span>
- <span data-ttu-id="11731-165">사용자를 새 오디오 회의 브리지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-165">When you move the user to a new audio conferencing bridge.</span></span>
- <span data-ttu-id="11731-166">오디오 회의 브리지의 전화 번호를 할당 하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="11731-166">When a phone number from a audio conferencing bridge is unassigned.</span></span> <span data-ttu-id="11731-167">이는 추가 단계가 필요한 복잡 한 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="11731-167">This is a complex scenario that requires additional steps.</span></span> <span data-ttu-id="11731-168">자세한 내용은 [오디오 회의 브리지에서 전화 번호 변경을](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="11731-168">For more information, see [Change the phone numbers on your audio conferencing bridge](https://docs.microsoft.com/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

<span data-ttu-id="11731-169">사용자의 오디오 회의 설정에 대 한 모든 변경 내용이 MMS를 트리거하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-169">Not all changes to a user's audio conferencing settings trigger MMS.</span></span> <span data-ttu-id="11731-170">특히 다음 두 가지 변경 사항으로 인해 MMS 업데이트는 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-170">Specifically, the following two changes won't result in MMS updating meetings:</span></span>

- <span data-ttu-id="11731-171">모임 이끌이의 SIP 주소 (SIP 사용자 이름 또는 SIP 도메인)를 변경 하는 경우</span><span class="sxs-lookup"><span data-stu-id="11731-171">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
- <span data-ttu-id="11731-172">`Update-CsTenantMeetingUrl` 명령을 사용 하 여 조직의 모임 URL을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-172">When you change your organization's meeting URL using the `Update-CsTenantMeetingUrl` command.</span></span>


### <a name="updating-meetings-when-assigning-teamsupgradepolicy"></a><span data-ttu-id="11731-173">TeamsUpgradePolicy 배정 시 모임 업데이트</span><span class="sxs-lookup"><span data-stu-id="11731-173">Updating meetings when assigning TeamsUpgradePolicy</span></span>

<span data-ttu-id="11731-174">기본적으로 모임 마이그레이션은 사용자에 게 `TeamsUpgradePolicy` `mode=TeamsOnly` 또는 `mode= SfBWithTeamsCollabAndMeetings`의 인스턴스가 부여 될 때 자동으로 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="11731-174">By default, meeting migration is automatically triggered when a user is granted an instance of `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode= SfBWithTeamsCollabAndMeetings`.</span></span> <span data-ttu-id="11731-175">이러한 모드 중 하나를 허용할 때 모임을 마이그레이션하지 않으려는 경우 (PowerShell을 사용 하는 `MigrateMeetingsToTeams $false` 경우 `Grant-CsTeamsUpgradePolicy` )에서 지정 하거나 확인란을 선택 취소 하 여 사용자의 공존 모드 (팀 관리 포털을 사용 하는 경우)를 설정할 때 모임 마이그레이션을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-175">If you do not want to migrate meetings when granting either of these modes, then specify `MigrateMeetingsToTeams $false` in `Grant-CsTeamsUpgradePolicy` (if using PowerShell) or uncheck the box to migrate meetings when setting a user's coexistence mode (if using the Teams admin portal).</span></span>

<span data-ttu-id="11731-176">또한 다음을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="11731-176">Also note the following:</span></span>

- <span data-ttu-id="11731-177">모임 마이그레이션은 특정 사용자에 게 부여 `TeamsUpgradePolicy` 하는 경우에만 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11731-177">Meeting migration is only invoked when you grant `TeamsUpgradePolicy` for a specific user.</span></span> <span data-ttu-id="11731-178">`TeamsUpgradePolicy` `mode=TeamsOnly` 또는 `mode=SfBWithTeamsCollabAndMeetings` *테 넌 트 전체* 를 사용 하 여 부여 하는 경우에는 모임 마이그레이션이 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-178">If you grant `TeamsUpgradePolicy` with `mode=TeamsOnly` or `mode=SfBWithTeamsCollabAndMeetings` on a *tenant-wide* basis, meeting migration is not invoked.</span></span>
- <span data-ttu-id="11731-179">사용자에 게 온라인 상태를 유지 하는 경우에만 팀 전용 모드를 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-179">A user can only be granted TeamsOnly mode if the user is homed online.</span></span> <span data-ttu-id="11731-180">온-프레미스 사용자는 앞에서 설명한 대로 사용 하 `Move-CsUser` 여 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-180">Users that are homed on-premises must be moved using `Move-CsUser` as previously described.</span></span>
- <span data-ttu-id="11731-181">TeamsOnly 또는 SfBWithTeamsCollabAndMeetings 이외의 모드를 허용 하면 기존 팀 모임이 비즈니스용 Skype 모임으로 전환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-181">Granting a mode other than TeamsOnly or SfBWithTeamsCollabAndMeetings does not convert existing Teams meetings to Skype for Business meetings.</span></span>

### <a name="trigger-meeting-migration-manually-via-powershell-cmdlet"></a><span data-ttu-id="11731-182">PowerShell cmdlet을 통해 수동으로 모임 마이그레이션 트리거</span><span class="sxs-lookup"><span data-stu-id="11731-182">Trigger Meeting Migration manually via PowerShell cmdlet</span></span>

<span data-ttu-id="11731-183">자동 모임 마이그레이션 외에도 관리자는 cmdlet `Start-CsExMeetingMigration`을 실행 하 여 사용자에 대 한 모임 마이그레이션을 수동으로 트리거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-183">In addition to automatic meeting migrations, admins can manually trigger meeting migration for a user by running the cmdlet `Start-CsExMeetingMigration`.</span></span> <span data-ttu-id="11731-184">이 cmdlet은 지정 된 사용자에 대 한 마이그레이션 요청을 큐에 대기 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="11731-184">This cmdlet queues a migration request for the specified user.</span></span>  <span data-ttu-id="11731-185">필수 `Identity` 매개 변수 외에도 다음과 같은 두 개의 선택적 매개 변수 `SourceMeetingType` `TargetMeetingType`를 사용 하 여 모임을 마이그레이션하는 방법을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-185">In addition to the required `Identity` parameter, it takes two optional parameters, `SourceMeetingType` and `TargetMeetingType`, which allow you to specify how to migrate meetings:</span></span>

<span data-ttu-id="11731-186">**TargetMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="11731-186">**TargetMeetingType:**</span></span>

- <span data-ttu-id="11731-187">을 `TargetMeetingType Current` 사용 하 여 비즈니스용 skype 모임이 비즈니스용 skype 모임 및 팀 모임으로 유지 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-187">Using `TargetMeetingType Current` specifies that Skype for Business meetings remain Skype for Business meetings and Teams meetings remain Teams meetings.</span></span> <span data-ttu-id="11731-188">그러나 오디오 회의 좌표는 변경 될 수 있으며, 온-프레미스 비즈니스용 Skype 모임은 비즈니스용 Skype Online으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="11731-188">However audio conferencing coordinates might be changed, and any on-premises Skype for Business meetings would be migrated to Skype for Business Online.</span></span> <span data-ttu-id="11731-189">이 값이 TargetMeetingType의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="11731-189">This is the default value for TargetMeetingType.</span></span>
- <span data-ttu-id="11731-190">사용 `TargetMeetingType Teams` 은 모임이 비즈니스용 Skype online 또는 온-프레미스에 호스팅 되었는지 여부와 오디오 회의 업데이트가 필요한 지 여부에 관계 없이 모든 기존 모임을 팀으로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-190">Using `TargetMeetingType Teams` specifies that any existing meeting must be migrated to Teams, regardless of whether the meeting is hosted in Skype for Business online or on-premises, and regardless of whether any audio conferencing updates are required.</span></span> 

<span data-ttu-id="11731-191">**SourceMeetingType:**</span><span class="sxs-lookup"><span data-stu-id="11731-191">**SourceMeetingType:**</span></span>
- <span data-ttu-id="11731-192">을 `SourceMeetingType SfB` 사용 하면 Skype for Business 모임만 (온-프레미스 또는 온라인)으로 업데이트 해야 한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11731-192">Using `SourceMeetingType SfB` indicates that only Skype for Business meetings (whether on-premises or online) should be updated.</span></span>
- <span data-ttu-id="11731-193">사용 `SourceMeetingType Teams` 은 팀 모임만 업데이트 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11731-193">Using `SourceMeetingType Teams` indicates that only Teams meetings should be updated.</span></span>
- <span data-ttu-id="11731-194">을 `SourceMeetingType All` 사용 하 여 Skyep 비즈니스 모임 및 팀 모임 모두를 업데이트 해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11731-194">Using `SourceMeetingType All` indicates that both Skyep for Business meetings and Teams meetings should be updated.</span></span> <span data-ttu-id="11731-195">이 값이 SourceMeetingType의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="11731-195">This is the default value for SourceMeetingType.</span></span>
    

<span data-ttu-id="11731-196">아래 예제에서는 모든 모임이 팀으로 마이그레이션될 수 있도록 사용자 ashaw@contoso.com에 대 한 모임 마이그레이션을 시작 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11731-196">The example below shows how to initiate meeting migration for user ashaw@contoso.com so that all meetings are migrated to Teams:</span></span>

```
Start-CsExMeetingMigration -Identity ashaw@contoso.com -TargetMeetingType Teams
```



## <a name="managing-mms"></a><span data-ttu-id="11731-197">MMS 관리</span><span class="sxs-lookup"><span data-stu-id="11731-197">Managing MMS</span></span>

<span data-ttu-id="11731-198">Windows PowerShell을 사용 하 여 진행 중인 마이그레이션 상태를 확인 하 고, 수동으로 모임 마이그레이션을 시작 하 고, 마이그레이션을 모두 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-198">Using Windows PowerShell, you can check the status of ongoing migrations, manually trigger meeting migration, and disable migration altogether.</span></span> 

### <a name="check-the-status-of-meeting-migrations"></a><span data-ttu-id="11731-199">모임 마이그레이션 상태 확인</span><span class="sxs-lookup"><span data-stu-id="11731-199">Check the status of meeting migrations</span></span>

<span data-ttu-id="11731-200">`Get-CsMeetingMigrationStatus` Cmdlet을 사용 하 여 모임 마이그레이션 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-200">You use the `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations.</span></span> <span data-ttu-id="11731-201">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="11731-201">Below are some examples.</span></span>

- <span data-ttu-id="11731-202">모든 MMS 마이그레이션에 대 한 요약 상태를 얻으려면 모든 마이그레이션 상태의 표 형식 보기를 제공 하는 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-202">To get a summary status of all MMS migrations, run the following command which provides a tabular view of all migration states:</span></span>

    ```
    Get-CsMeetingMigrationStatus -SummaryOnly

    State      UserCount
    ------     ---------
    Pending      21
    InProgress    6
    Failed            2 
    Succeeded   131
    ```
- <span data-ttu-id="11731-203">특정 기간 내의 모든 마이그레이션에 대 한 세부 정보를 모두 보려면 `StartTime` 및 `EndTime` 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-203">To get full details of all migrations within a specific time period, use the `StartTime` and `EndTime` parameters.</span></span> <span data-ttu-id="11731-204">예를 들어 다음 명령은 2018 년 10 월 1 일부 터 2018 년 10 월 8 일 까지의 모든 마이그레이션에 대해 전체 세부 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-204">For example, the following command will return full details on all migrations that occurred from October 1, 2018 to October 8, 2018.</span></span>

    ```
    Get-CsMeetingMigrationStatus -StartTime "10/1/2018" -EndTime "10/8/2018"
    ```
- <span data-ttu-id="11731-205">특정 사용자에 대 한 마이그레이션 상태를 확인 하려면 `Identity` 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-205">To check the status of migration for a specific user, use the `Identity` parameter.</span></span> <span data-ttu-id="11731-206">예를 들어 다음 명령을 실행 하면 사용자 ashaw@contoso.com의 상태가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11731-206">For example, the following command will return the status for the user ashaw@contoso.com:</span></span>

    ```
    Get-CsMeetingMigrationStatus -Identity ashaw@contoso.com
    ```
<span data-ttu-id="11731-207">실패 한 마이그레이션이 표시 되는 경우 이러한 문제를 해결할 때까지 해당 사용자가 구성한 모임에 대 한 전화 접속을 할 수 없기 때문에, 가능한 한 빨리 해결 하기 위해 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-207">If you see any migrations that have failed, take action to resolve these issues as soon as possible, since people won't be able to dial-in to the meetings organized by those users until you resolve them.</span></span> <span data-ttu-id="11731-208">에서 `Get-CsMeetingMigrationStatus` 실패 상태의 마이그레이션이 표시 되는 경우 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-208">If `Get-CsMeetingMigrationStatus` shows any migrations in a failed state, perform these steps:</span></span>
 
1. <span data-ttu-id="11731-209">어떤 사용자에 게 영향을 미치는지 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-209">Determine which users are affected.</span></span> <span data-ttu-id="11731-210">다음 명령을 실행 하 여 영향을 받는 사용자 목록과 보고 된 특정 오류를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="11731-210">Run the following command to get the list of affected users, and the specific error that was reported:</span></span>

    ```
    Get-CsMeetingMigrationStatus| Where {$_.State -eq "Failed"}| Format-Table UserPrincipalName, LastMessage
    ```
2. <span data-ttu-id="11731-211">영향을 받는 각 사용자에 대해 모임 마이그레이션 도구를 실행 하 여 모임을 수동으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-211">For each affected user, run the Meeting Migration Tool to manually migrate their meetings.</span></span>

3. <span data-ttu-id="11731-212">여전히 마이그레이션이 모임 마이그레이션 도구에서 작동 하지 않으면 다음 두 가지 옵션 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-212">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>

    - <span data-ttu-id="11731-213">사용자가 새 Skype 모임을 만들도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-213">Have the users create new Skype meetings.</span></span>
    - <span data-ttu-id="11731-214">[고객 지원에 문의 하세요](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span><span class="sxs-lookup"><span data-stu-id="11731-214">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>


### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="11731-215">MMS 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="11731-215">Enabling and disabling MMS</span></span>

<span data-ttu-id="11731-216">MMS는 모든 조직에 대해 기본적으로 사용 하도록 설정 되지만 다음과 같이 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-216">MMS is enabled by default for all organizations, but it can be disabled as follows:</span></span>

- <span data-ttu-id="11731-217">테 넌 트에 대해 완전히 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-217">Disable entirely for the tenant.</span></span> 
- <span data-ttu-id="11731-218">오디오 회의 관련 변경 내용에 대해서만 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-218">Disable only for changes related to audio conferencing.</span></span> <span data-ttu-id="11731-219">이 경우 사용자를 온-프레미스에서 클라우드로 마이그레이션하거나 TeamsOnly 모드 또는 SfBWithTeamsCollabAndMeetings 모드를 사용 하도록 허용할 때 MMS는 계속 실행 됩니다 `TeamsUpgradePolicy`.</span><span class="sxs-lookup"><span data-stu-id="11731-219">In this case, MMS will still run when a user is migrated from on-premises to the cloud or when you grant TeamsOnly mode or SfBWithTeamsCollabAndMeetings mode in `TeamsUpgradePolicy`.</span></span>

<span data-ttu-id="11731-220">예를 들어 조직의 오디오 회의 설정을 대폭 변경 하면서 모든 모임을 수동으로 마이그레이션하거나 MMS를 일시적으로 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-220">For example, you may want to manually migrate all meetings or temporarily disable MMS while making substantial changes to the audio conferencing settings for your organization</span></span>

<span data-ttu-id="11731-221">조직에 MMS를 사용할 수 있는지 확인 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-221">To see if MMS is enabled for your organization, run the following command.</span></span> <span data-ttu-id="11731-222">매개 변수가 있는 `MeetingMigrationEnabled` 경우 MMS를 사용할 `$true`수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11731-222">MMS is enabled if the `MeetingMigrationEnabled` parameter is `$true`.</span></span>
```
Get-CsTenantMigrationConfiguration
```
<span data-ttu-id="11731-223">MMS를 완전히 사용 하거나 사용 하지 않도록 설정 `Set-CsTenantMigrationConfiguration` 하려면 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-223">To enable or disable MMS entirely, use the `Set-CsTenantMigrationConfiguration` command.</span></span> <span data-ttu-id="11731-224">예를 들어 MMS를 사용 하지 않도록 설정 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-224">For example, to disable MMS, run the following command:</span></span>

```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```
<span data-ttu-id="11731-225">조직에서 MMS를 사용 하도록 설정 하 고 오디오 회의 업데이트를 사용 하도록 설정 되어 있는지 확인 하려면 출력에서 `AutomaticallyMigrateUserMeetings` 매개 변수 값을 확인 `Get-CsOnlineDialInConferencingTenantSettings`합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-225">If MMS is enabled in the organization and you want to check if it is enabled for audio conferencing updates, check the value of the `AutomaticallyMigrateUserMeetings` parameter in the output from `Get-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="11731-226">오디오 회의에 대 한 MMS를 사용 하거나 사용 `Set-CsOnlineDialInConferencingTenantSettings`하지 않도록 설정 하려면을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-226">To enable or disable MMS for audio conferencing, use `Set-CsOnlineDialInConferencingTenantSettings`.</span></span> <span data-ttu-id="11731-227">예를 들어 오디오 회의에 대 한 MMS를 사용 하지 않도록 설정 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="11731-227">For example, to disable MMS for audio conferencing, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $false
```

## <a name="related-topics"></a><span data-ttu-id="11731-228">관련 주제</span><span class="sxs-lookup"><span data-stu-id="11731-228">Related topics</span></span>

[<span data-ttu-id="11731-229">Office 365에서 오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="11731-229">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

[<span data-ttu-id="11731-230">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="11731-230">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)
