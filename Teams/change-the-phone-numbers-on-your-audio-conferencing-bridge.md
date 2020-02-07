---
title: 오디오 회의 브리지에서 전화 번호 변경
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 오디오 회의 라이선스를 구입 하는 경우 Microsoft는 조직에 대 한 오디오 회의 브리지를 호스팅 하 고 있습니다. 오디오 회의 브리지는 다른 위치에서 전화 접속 전화 번호를 제공 하므로 모임 이끌이 및 참가자가 휴대폰을 사용 하 여 비즈니스용 Skype 또는 Microsoft 팀 모임에 참가 하는 데 사용할 수 있습니다.
ms.openlocfilehash: 54662b34f5b8b1f56aceffb2294801a485bc26ae
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825206"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="3748c-104">오디오 회의 브리지에서 전화 번호 변경</span><span class="sxs-lookup"><span data-stu-id="3748c-104">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="3748c-105">**오디오 회의** 라이선스를 구입 하는 경우 Microsoft는 조직에 대 한 오디오 회의 브리지를 호스팅 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-105">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="3748c-106">오디오 회의 브리지는 다른 위치에서 전화 접속 전화 번호를 제공 하 여 모임 이끌이 및 참가자가 휴대폰을 사용 하 여 비즈니스용 Skype 또는 Microsoft 팀 모임에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-106">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="3748c-107">이미 회의 브리지에 지정 된 전화번호 외에도 다른 위치에서 [추가 서비스 번호](/microsoftteams/getting-service-phone-numbers) (오디오 회의에 사용 되는 유료 및 수신자 부담 번호)를 가져온 다음 사용자를 위한 적용 범위를 확장할 수 있도록이를 회의 브리지에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-107">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3748c-108">회의 브리지의 전화 번호를 할당/할당 취소 하려면 전화 번호가 '*서비스*' 번호 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-108">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="3748c-109">이전 포털에서 **음성** > **전화 번호로** 이동 하 여 **번호 형식** 열을 보면 번호 형식을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-109">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the legacy portal and looking in the **Number Type** column.</span></span> <span data-ttu-id="3748c-110">사용자가 유료 번호를 사용 하 여 bridge로 전화를 걸려면 먼저 Office 365 통신 크레딧을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-110">Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="3748c-111">회의 브리지에 새 서비스 전화 번호를 할당 하는 단계</span><span class="sxs-lookup"><span data-stu-id="3748c-111">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="3748c-112">1 단계-오디오 회의 브리지에 새 전화 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-112">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

1. <span data-ttu-id="3748c-113">회사 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-113">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="3748c-114">**Microsoft 365 관리 센터** > **관리자** > **팀** > 으로 이동 하 여 Skype**레거시 포털** > **음성** > **전화 번호**를 &.</span><span class="sxs-lookup"><span data-stu-id="3748c-114">Go to **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="3748c-115">목록에서 전화 번호를 선택 하 고 작업 창에서 **할당**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-115">Select the phone number from the list, and in the Action pane, click **Assign**.</span></span>

4. <span data-ttu-id="3748c-116">**배정** 페이지에서 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-116">On the **Assign** page, click **Save**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="3748c-117">2 단계-회의 브리지의 기본 전화 번호 변경 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="3748c-117">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="3748c-118">전화 회의 브리지의 기본 전화 번호는 모임 내에서 참가자 또는 이끌이를 통해 아웃 바운드 통화를 할 때 사용 되는 발신자 ID를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-118">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="3748c-119">회의 브리지의 기본 번호로 서비스 유료 번호를 설정할 수 있습니다. **서비스 무료 번호는 회의 브리지의 기본 번호로 설정할 수 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="3748c-119">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="3748c-120">서비스 유료 전화 번호를 할당 하는 경우 오디오 회의 브리지에 대 한 새로운 기본 번호로 설정 하려면 다음 단계를 수행 하세요.</span><span class="sxs-lookup"><span data-stu-id="3748c-120">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

1. <span data-ttu-id="3748c-121">회사 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-121">Sign in to Office 365 with your work account.</span></span>

2. <span data-ttu-id="3748c-122">**Microsoft 365 관리 센터** > \*\*\*\* > **팀** > 으로 이동 하 여 Skype**모임** > **회의 브리지**를 & 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-122">Go to **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="3748c-123">기본값으로 구성 하려는 서비스 유료 전화 번호를 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-123">Highlight the service toll number that you want to configure as the default.</span></span>

4. <span data-ttu-id="3748c-124">**기본값으로 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-124">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="3748c-125">3 단계-사용자의 모임 초대에 포함 된 기본 전화 번호 변경 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="3748c-125">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="3748c-126">사용자의 기본 전화 번호는 모임 일정을 정할 때 모임 초대에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-126">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="3748c-127">Defaul 전화 번호가 새 사용자에 게 할당 되는 방식을 비롯 한 자세한 내용은 [Microsoft 팀의 초대에 포함 된 전화 번호 설정](set-the-phone-numbers-included-on-invites-in-teams.md) 또는 비즈니스용 [Skype Online의 초대에 포함 된 전화 번호](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)설정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3748c-127">For more information, including how the defaul phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>
  
1. <span data-ttu-id="3748c-128">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-128">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="3748c-129">**Microsoft 365 관리 센터** > **관리** > 센터**팀** > 으로 이동 하 여 Skype**레거시 포털** > **오디오 회의** > **사용자**를 & 하 고 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-129">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Audio conferencing** > **Users**, and select the users on the list.</span></span>

3. <span data-ttu-id="3748c-130">작업 창에서 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-130">Click **Edit** in the action pane.</span></span>

4. <span data-ttu-id="3748c-131">**기본 유료 전화 번호** 또는 **기본 무료 유료 번호**에서 목록에 있는 번호를 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-131">Under **Default toll number** or **Default toll-free number**, select the number in the list and click **Save**.</span></span>

<span data-ttu-id="3748c-132">변경 내용이 저장 되 면 다음에 새 모임을 예약할 때 새 기본 전화 번호가 이끌이의 모임 초대에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-132">After the changes have been saved, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="3748c-133">4 단계-모임 마이그레이션 서비스를 사용 하 여 사용자의 기존 모임 초대 업데이트 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="3748c-133">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="3748c-134">다음 두 단계는 Windows PowerShell을 시작 해야 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-134">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="3748c-135">일부 또는 모든 사용자에 대 한 모임 초대에 사용 되는 기본 전화 번호를 업데이트 한 경우에는 조직의 사용자에 게 이미 보낸 모임 초대를 선택적으로 업데이트할 수 있으며,이 경우 해당 기본 전화 번호를 사용 하 여 변경 되었습니다. 모임 마이그레이션 서비스.</span><span class="sxs-lookup"><span data-stu-id="3748c-135">If you updated the default phone numbers that are inlcuded in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="3748c-136">자세한 내용은 [MMS (모임 마이그레이션 서비스) 설정을](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3748c-136">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="3748c-137">2 단계에서 기본 전화 번호를 변경한 사용자를 위해 MMS (모임 마이그레이션 서비스)를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-137">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="3748c-138">이렇게 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-138">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="3748c-139">모임 마이그레이션 상태를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-139">You can also view the meeting migration status.</span></span> <span data-ttu-id="3748c-140">*보류* 중이거나 *진행* 중 상태인 작업이 없는 경우 모든 모임의 일정이 다시 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-140">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="3748c-141">회의 브리지에 대 한 서비스 전화 번호의 할당을 취소 하는 단계</span><span class="sxs-lookup"><span data-stu-id="3748c-141">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="3748c-142">회의 브리지에서 전화 번호를 할당 취소 하면 사용자는 해당 전화 번호를 사용 하 여 모임에 더 이상 참가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-142">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="3748c-143">전화 번호가 변경 되므로 전화 번호를 기본 번호 (있는 경우)로 사용 하는 모든 사용자를 업데이트 하 고 기존 모임 초대를 업데이트 하 여 전화 번호가 오디오 회의 브리지에서 할당 되지 않도록 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-143">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="3748c-144">사용자 및 해당 모임을 업데이트 하지 않고 전화 번호가 제거 되는 경우 기존 모임 초대에는 모임 참가에 사용할 수 없는 전화 번호가 포함 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-144">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="3748c-145">처음 세 단계는 Windows PowerShell을 시작 해야 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-145">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="3748c-146">이 작업을 수행 하는 방법을 알아보려면 [Windows PowerShell을 사용 하 여 관리 하는 방법을 알아보려면 원하는](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell) 을 클릭 하세요.</span><span class="sxs-lookup"><span data-stu-id="3748c-146">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="3748c-147">1 단계-전화 번호를 할당 하지 않은 사용자를 기본 번호 중 하나로 업데이트</span><span class="sxs-lookup"><span data-stu-id="3748c-147">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="3748c-148">기본 유료 또는 수신자 부담 전화 번호를 기본 번호로 지정할 수 없는 번호를 사용 하는 모든 사용자를 대체 하 고 모임의 일정을 재조정 하는 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-148">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="3748c-149">이렇게 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-149">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="3748c-150">비즈니스용 Skype 관리 센터에서 기본 유료 또는 무료 사용자 수를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-150">You can also change the default toll or toll-free number of users in the Skype for Business admin center.</span></span> <span data-ttu-id="3748c-151">그러나 모임 일정이 자동으로 재조정 되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-151">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="3748c-152">자세한 내용은 [Microsoft 팀의 초대에 포함 된 전화 번호 설정](set-the-phone-numbers-included-on-invites-in-teams.md) 또는 비즈니스용 [Skype Online의 초대에 포함 된 전화 번호](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)설정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3748c-152">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="3748c-153">조직의 규모에 따라 완료 하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-153">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="3748c-154">2 단계-Windows PowerShell을 사용 하 여 모임 마이그레이션 상태 보기</span><span class="sxs-lookup"><span data-stu-id="3748c-154">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="3748c-155">*보류* 중이거나 *진행* 중 상태인 작업이 없는 경우 모든 모임의 일정이 다시 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-155">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="3748c-156">모임 마이그레이션 서비스에 대 한 자세한 내용은 [MMS (모임 마이그레이션 서비스) 설정을](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3748c-156">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="3748c-157">3 단계-오디오 회의 브리지에서 이전 전화 번호 할당 취소</span><span class="sxs-lookup"><span data-stu-id="3748c-157">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

1. <span data-ttu-id="3748c-158">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-158">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="3748c-159">**Microsoft 365 관리 센터** > **관리** > **팀**으로 이동 하 여 Skype > **레거시 포털** > **음성** > **전화 번호**를 &.</span><span class="sxs-lookup"><span data-stu-id="3748c-159">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams & Skype** > **Legacy portal** > **Voice** > **Phone numbers**.</span></span>

3. <span data-ttu-id="3748c-160">전화 번호가 무료 번호 이면 목록에서 전화 번호를 선택 하 고 작업 창에서 **할당**취소를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-160">If the phone number is a toll-free number, select the phone number from the list, and in the Action pane, click **Unassign**.</span></span> <span data-ttu-id="3748c-161">전화 번호가 유료 이면 [Microsoft 지원](https://go.microsoft.com/fwlink/?linkid=2091806) 에 문의 하 여 전화 번호를 지정 하지 않은 것으로 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="3748c-161">If the phone number is a toll-number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

4. <span data-ttu-id="3748c-162">전화 번호가 유료-fre 번호 이면 확인 창에서 **예** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-162">If the phone number is a toll-fre number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="3748c-163">오디오 회의 브리지에서 전화 번호를 할당 하지 않은 후에는 더 이상 사용자가 전화 번호를 사용 하 여 새 모임이 나 기존 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-163">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3748c-164">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="3748c-164">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="3748c-165"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="3748c-165"><a name="bkPowerShell"> </a></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="3748c-166">Windows PowerShell을 사용할 준비가 되었는지 확인 하려면 다음을 실행 하세요.</span><span class="sxs-lookup"><span data-stu-id="3748c-166">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="3748c-167">이 단계에서는 Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-167">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="3748c-168">**시작 메뉴** > **Windows PowerShell**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-168">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="3748c-169">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-169">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="3748c-170">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-170">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="3748c-171">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-171">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span>
<span data-ttu-id="3748c-172">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-172">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="3748c-173">비즈니스용 Skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-173">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="3748c-174">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-174">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="3748c-175">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-175">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="3748c-176">자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3748c-176">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="3748c-177">Windows PowerShell을 시작 하려면</span><span class="sxs-lookup"><span data-stu-id="3748c-177">To start Windows PowerShell</span></span>

 <span data-ttu-id="3748c-178">**Windows PowerShell 세션 시작**</span><span class="sxs-lookup"><span data-stu-id="3748c-178">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="3748c-179">**시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-179">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="3748c-180">**Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-180">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>

>
  ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> <span data-ttu-id="3748c-181">비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-181">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
<span data-ttu-id="3748c-182">Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online에](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)연결을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3748c-182">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="3748c-183">시간 절약 및 자동화</span><span class="sxs-lookup"><span data-stu-id="3748c-183">Save time and automate</span></span>

<span data-ttu-id="3748c-184">이 프로세스를 자동화 하 여 시간을 절약 하기 위해 [set-get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688) 또는 **CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-184">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="3748c-185">[Get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet을 사용 하 여 특정 사용자의 기본 유료 또는 무료 전화 번호를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-185">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="3748c-186">사용자의 기본 무료 전화 번호를 변경 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-186">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="3748c-187">**CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용 하 여 기본 유료 또는 수신자의 사용자 수를 원래의 기본 숫자나 해당 위치에 따라 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-187">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3748c-188">BridgeID를 찾으려면 **CsOnlineDialInConferencingBridge**를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-188">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="3748c-189">1 ~ 8005551234 없는 모든 사용자의 기본 무료 전화 번호를 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-189">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="3748c-190">8005551234을 기본 무료 번호로 사용 하는 모든 사용자의 기본 무료 (수신자 부담 번호)를 8005551239로 변경 하 고 자동으로 모임 일정을 조정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-190">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="3748c-191">미국에 거주 하는 모든 사용자의 기본 무료 무료 번호를 8005551234로 설정 하 고 자동으로 모임 일정을 재조정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-191">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="3748c-192">위에서 사용 되는 위치는 Microsoft 365 관리 센터에서 설정한 사용자의 연락처 정보와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-192">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="3748c-193">해결사</span><span class="sxs-lookup"><span data-stu-id="3748c-193">Troubleshooting</span></span>

<span data-ttu-id="3748c-194">**할당 취소 단추가 회색으로 표시 됨**</span><span class="sxs-lookup"><span data-stu-id="3748c-194">**Unassign button is greyed-out**</span></span>

<span data-ttu-id="3748c-195">숫자의 할당을 취소 했지만 단추가 회색으로 표시 되는 동안에는 다음 메시지가 표시 되 면 _"기본 또는 공유 번호를 브리지에서 할당 해제할 수 없었습니다" 라는 메시지와 함께 연락처에 대 한 지원이 리디렉션됩니다. 전용 유료 전화 번호를 할당 취소 하려면 고객 지원에 문의 하세요._"</span><span class="sxs-lookup"><span data-stu-id="3748c-195">You want to Unassign a number but the button is greyed-out and if while hoovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="3748c-196">브리지에 대 한 자세한 정보를 얻으려면 다음 Powershell을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-196">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="3748c-197">그 결과, Id, 이름, 지역 등의 다른 정보는 함께 DefaultServiceNumber를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-197">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="3748c-198">**예**를 들어, DefaultServiceNumber "8005551234"을 할당 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="3748c-198">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName “Conference Bridge” -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="3748c-199">Windows PowerShell 정보</span><span class="sxs-lookup"><span data-stu-id="3748c-199">About Windows PowerShell</span></span>

<span data-ttu-id="3748c-200">Windows PowerShell을 사용 하 여 사용자를 관리 하 고, 수행할 수 있는 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-200">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="3748c-201">Windows PowerShell을 사용 하면 작업을 수행 하는 데 많은 작업을 수행할 수 있는 단일 관리 지점을 통해 Office 365 및 비즈니스용 Skype Online을 손쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-201">Windows PowerShell  can help you manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="3748c-202">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3748c-202">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="3748c-203">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="3748c-203">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="3748c-204">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="3748c-204">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="3748c-205">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3748c-205">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="3748c-206">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3748c-206">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="3748c-207">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="3748c-207">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="3748c-208">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="3748c-208">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="3748c-209">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="3748c-209">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="3748c-210">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3748c-210">Related topics</span></span>
[<span data-ttu-id="3748c-211">오디오 회의 브리지의 설정 변경</span><span class="sxs-lookup"><span data-stu-id="3748c-211">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
