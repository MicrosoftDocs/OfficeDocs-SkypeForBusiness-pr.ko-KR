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
- seo-marvel-mar2020
description: 사용자의 범위를 확장하기 위해 전화 회의 브리지에 새 서비스 전화 번호를 할당하는 데 필요한 단계를 알아보십시오.
ms.openlocfilehash: 7f9efd4289f24b4248cddd732773d7c96e728f0c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918754"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="66e28-103">오디오 회의 브리지에서 전화 번호 변경</span><span class="sxs-lookup"><span data-stu-id="66e28-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="66e28-104">오디오 **회의** 라이선스를 구입하면 Microsoft에서 조직의 오디오 회의 브리지를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="66e28-105">오디오 회의 브리지는 모임 이끌이와 참가자가 전화기를 사용하여 비즈니스용 Skype 또는 Microsoft Teams 모임에 참가할 수 있도록 여러 위치에서 전화 접속 전화 번호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="66e28-106">회의 브리지에 이미 할당된 전화 번호 외에도 다른 [](/microsoftteams/getting-service-phone-numbers) 위치에서 추가 서비스 번호(오디오 회의에 사용되는 무료 번호)를 확인한 다음 회의 브리지에 할당하여 사용자에 대한 적용 범위를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="66e28-107">회의 브리지의 전화 번호를 할당/할당을 해지하려면 전화 번호가 *'서비스'* 번호가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="66e28-108">Microsoft Teams 관리 센터에서 음성 전화 번호로 찾아 번호 유형 열을 보고 번호 유형을 볼  >   **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="66e28-109">사용자가 무료 번호로 브리지에 전화를 걸 수 있도록 Microsoft 365 또는 Office 365 통신 크레딧을 먼저 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="66e28-110">전화 회의 브리지에 새 서비스 전화 번호를 할당하는 단계</span><span class="sxs-lookup"><span data-stu-id="66e28-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="66e28-111">1단계 - 오디오 회의 브리지에 새 전화 번호 할당</span><span class="sxs-lookup"><span data-stu-id="66e28-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="66e28-112">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="66e28-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="66e28-113">왼쪽 탐색 창에서 **음성** 전화  >  **번호로 이동**</span><span class="sxs-lookup"><span data-stu-id="66e28-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="66e28-114">목록에서 전화 번호를 선택하고 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="66e28-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="66e28-115">편집 페이지의 **[할당]** 아래에서 드롭다운을 확장한 다음 회의 브리지    >  **적용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="66e28-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="66e28-116">2단계 - 전화 회의 브리지의 기본 전화 번호 변경(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="66e28-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="66e28-117">전화 회의 브리지의 기본 전화 번호는 모임 내에서 참가자 또는 이끌이가 아웃바운드 통화를 걸 때 사용할 발신자 ID를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="66e28-118">서비스 에일리 번호만 회의 브리지의 기본 번호로 설정할 수 있습니다. **서비스 무료 번호는** 회의 브리지의 기본 번호로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="66e28-119">서비스 LL 번호를 할당하고 오디오 회의 브리지의 새 기본 번호로 설정하는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="66e28-120">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="66e28-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="66e28-121">왼쪽 탐색 창에서 모임 회의  >  **브리지로 이동**</span><span class="sxs-lookup"><span data-stu-id="66e28-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="66e28-122">기본값으로 구성하려는 서비스 에지 번호를 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="66e28-123">기본값으로 **설정 선택**</span><span class="sxs-lookup"><span data-stu-id="66e28-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="66e28-124">3단계 - 사용자의 모임 초대에 포함된 기본 전화 번호 변경(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="66e28-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="66e28-125">사용자의 기본 전화 번호는 모임을 예약할 때 모임 초대에 포함된 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="66e28-126">새 사용자에 대해 기본 전화 번호가 할당되는 방법을 비롯한 자세한 내용은 [Microsoft Teams의](set-the-phone-numbers-included-on-invites-in-teams.md) 초대에 포함된 전화 번호 설정 또는 비즈니스용 [Skype Online의](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)초대에 포함된 전화 번호 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66e28-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="66e28-127">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="66e28-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="66e28-128">왼쪽 탐색 창에서 사용자로  이동하고 목록에서 원하는 사용자의 표시 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="66e28-129">오디오 회의 옆에 **있는** 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="66e28-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="66e28-130">무료 **전화** 번호 또는 무료 번호 아래의 드롭다운에서 번호를 선택하고 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="66e28-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="66e28-131">변경 내용이 적용된 후 다음에 새 모임을 예약할 때 이끌이의 모임 초대에 새 기본 전화 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="66e28-132">4단계 - 모임 마이그레이션 서비스를 사용하여 사용자의 기존 모임 초대 업데이트(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="66e28-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="66e28-133">다음 두 단계의 경우 다음 단계를 시작해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66e28-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="66e28-134">일부 또는 전체 사용자의 모임 초대에 포함된 기본 전화 번호를 업데이트한 경우 모임 마이그레이션 서비스를 사용하여 기본 전화 번호가 변경되기 전에 조직의 사용자에게 이미 전송된 모임 초대를 선택적으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="66e28-135">자세한 내용은 [MMS(모임 마이그레이션 서비스) 설정을 참조하세요.](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="66e28-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="66e28-136">2단계에서 기본 전화 번호가 변경된 사용자에 대해 MMS(모임 마이그레이션 서비스)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="66e28-137">이를 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="66e28-138">모임 마이그레이션 상태를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="66e28-139">보류 중 또는 진행 중 상태인 작업이 없는  경우 모든 모임이 다시 *예약됩니다.*</span><span class="sxs-lookup"><span data-stu-id="66e28-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="66e28-140">회의 브리지에 대한 서비스 전화 번호를 부재 중일 때의 단계</span><span class="sxs-lookup"><span data-stu-id="66e28-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="66e28-141">회의 브리지에서 전화 번호를 재할당을 해지하면 사용자는 더 이상 해당 전화 번호를 사용하여 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="66e28-142">전화 번호가 변경되기 때문에 전화 번호를 기본 번호(있는 경우)로 사용할 수 있는 모든 사용자를 업데이트하고 오디오 회의 브리지에서 전화 번호가 지정되지 않은 경우 기존 모임 초대를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="66e28-143">사용자 및 해당 모임을 업데이트하지 않고 전화 번호가 제거되면 기존 모임 초대에 모임에 참가할 수 없는 전화 번호가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="66e28-144">처음 세 단계의 경우 다음 단계를 시작해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66e28-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="66e28-145">이 작업을 하는 방법을 보려면 다음을 사용하여 관리 방법을 알고 [Windows PowerShell.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span><span class="sxs-lookup"><span data-stu-id="66e28-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="66e28-146">1단계 - 전화 번호를 지정하지 않은 사용자를 기본 번호 중 하나로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="66e28-147">번호가 지정되지 않은 모든 사용자의 기본 통행료 또는 무료 번호를 기본 번호로 바꾸고 모임을 다시 진행하는 프로세스를 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="66e28-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="66e28-148">이를 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="66e28-149">Microsoft Teams 관리 센터에서 기본 무료 사용자 수를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="66e28-150">그러나 모임을 자동으로 다시 조정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="66e28-151">자세한 내용은 [Microsoft Teams의](set-the-phone-numbers-included-on-invites-in-teams.md) 초대에 포함된 전화 번호 설정 또는 비즈니스용 Skype Online의 초대에 포함된 전화 번호 [설정을 참조하세요.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="66e28-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="66e28-152">조직의 크기에 따라 완료하는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="66e28-153">2단계 - 다음을 사용하여 모임 마이그레이션 상태 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="66e28-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="66e28-154">보류 중 또는 진행 중 상태인 작업이 없는  경우 모든 모임이 다시 *예약됩니다.*</span><span class="sxs-lookup"><span data-stu-id="66e28-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="66e28-155">모임 마이그레이션 서비스에 대한 자세한 내용은 [MMS(모임](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)마이그레이션 서비스) 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66e28-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="66e28-156">3단계 - 오디오 회의 브리지에서 이전 전화 번호의 이전 전화 번호의 재할당을 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="66e28-157">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="66e28-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="66e28-158">왼쪽 탐색 모음에서 **음성** 전화  >  **번호로 이동**</span><span class="sxs-lookup"><span data-stu-id="66e28-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="66e28-159">전화 번호가 무료 번호인 경우 목록에서 전화 번호를 선택하고 릴리스를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="66e28-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="66e28-160">전화 번호가 통행료 번호인 경우 [Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) 지원에 문의하여 전화 번호를 미지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-160">If the phone number is a toll number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="66e28-161">전화 번호가 무료 번호인 경우 확인 창에서 **예를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="66e28-162">오디오 회의 브리지에서 전화 번호가 부재 중이면 사용자가 새 모임이나 기존 모임에 참가할 수 없는 전화 번호가 더 이상 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="66e28-163">사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="66e28-163">Want to know how to manage with Windows PowerShell?</span></span>
<span data-ttu-id="66e28-164"><a name="bkPowerShell"> </a></span><span class="sxs-lookup"><span data-stu-id="66e28-164"><a name="bkPowerShell"> </a></span></span>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a><span data-ttu-id="66e28-165">다음을 Windows PowerShell 준비가 됐는지 확인</span><span class="sxs-lookup"><span data-stu-id="66e28-165">To verify that Windows PowerShell is ready to go</span></span>

 <span data-ttu-id="66e28-166">다음 단계에서는 버전 3.0 Windows PowerShell 실행 중인지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-166">These steps check that you are running Windows PowerShell version 3.0 or higher.</span></span>

1. <span data-ttu-id="66e28-167">시작 **메뉴를**  >  **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="66e28-167">Type **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="66e28-168">버전 확인을 위해  Windows PowerShell _Get-Host를_ 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-168">Type _Get-Host_ in the **Windows PowerShell** window to check the version.</span></span>

3. <span data-ttu-id="66e28-169">버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66e28-169">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="66e28-170">버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-170">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span>
<span data-ttu-id="66e28-171">메시지가 표시될 때 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-171">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="66e28-172">또한 비즈니스용 Skype Online에 Windows PowerShell 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online용 Windows PowerShell 모듈을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-172">You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="66e28-173">이 모듈은 64비트 컴퓨터에서만 지원하며 비즈니스용 Skype Online용 Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 [다운로드할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="66e28-173">This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span>
<span data-ttu-id="66e28-174">메시지가 표시될 경우 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-174">Restart your computer if you are prompted.</span></span>

<span data-ttu-id="66e28-175">자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)</span><span class="sxs-lookup"><span data-stu-id="66e28-175">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

### <a name="to-start-windows-powershell"></a><span data-ttu-id="66e28-176">시작 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="66e28-176">To start Windows PowerShell</span></span>

 <span data-ttu-id="66e28-177">**세션 Windows PowerShell 시작**</span><span class="sxs-lookup"><span data-stu-id="66e28-177">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="66e28-178">시작 **메뉴에서**  >  **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="66e28-178">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="66e28-179">다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-179">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>

> [!NOTE]
> <span data-ttu-id="66e28-180">비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-180">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="66e28-181">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-181">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> <span data-ttu-id="66e28-182">비즈니스용 Skype Online  모듈을 처음 사용하는 경우 모듈 가져오기 명령을 Windows PowerShell 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-182">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
<span data-ttu-id="66e28-183">Windows PowerShell 시작하는 데 대한 자세한 내용은 단일 Windows PowerShell 창에서 모든 [Microsoft 365 또는 Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결하거나 [Windows PowerShell.](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="66e28-183">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="66e28-184">시간 절약 및 자동화</span><span class="sxs-lookup"><span data-stu-id="66e28-184">Save time and automate</span></span>

<span data-ttu-id="66e28-185">이 프로세스를 자동화하여 시간을 절약하기 위해 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) 또는 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-185">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="66e28-186">[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet을 사용하여 특정 사용자의 기본 무료 또는 무료 번호를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-186">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="66e28-187">사용자의 기본 무료 번호를 변경하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-187">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="66e28-188">**Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용하여 원래 기본 번호 또는 해당 위치에 따라 기본 무료 사용자 수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-188">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="66e28-189">BridgeID를 찾으면 **Get-CsOnlineDialInConferencingBridge를 사용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="66e28-189">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="66e28-190">8005551234로 설정하지 않은 모든 사용자의 기본 무료 번호를 설정하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-190">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="66e28-191">기본 무료 번호로 8005551234가 있는 모든 사용자의 기본 무료 번호를 8005551239로 변경하고 모임을 자동으로 다시 조정하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-191">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="66e28-192">미국에 있는 모든 사용자의 기본 무료 수를 8005551234로 설정하고 모임을 자동으로 다시 조정하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-192">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="66e28-193">위에서 사용된 위치는 Microsoft 365 관리 센터에 설정된 사용자의 연락처 정보와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-193">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="66e28-194">문제 해결</span><span class="sxs-lookup"><span data-stu-id="66e28-194">Troubleshooting</span></span>

<span data-ttu-id="66e28-195">**선택 안 하여 단추를 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="66e28-195">**Unassign button isn't available**</span></span>

<span data-ttu-id="66e28-196">번호의 배정을 해지하고 단추를 사용할 수 없습니다. 단추를 마우스로 이동하는 동안 지원에 "기본 또는 공유 번호는 브리지에서 지정을 해지할 수 _없습니다. 전용 통행료_ 번호를 부과하지 않는 경우 고객 지원에 문의하시기 바랍니다. ".</span><span class="sxs-lookup"><span data-stu-id="66e28-196">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="66e28-197">브리지에 대한 자세한 정보를 얻은 다음 Powershell을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-197">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="66e28-198">결과에는 ID, 이름 및 지역과 같은 다른 정보 외에도 DefaultServiceNumber가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-198">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="66e28-199">**예를** 들어, 지정을 해지하기 위해 DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="66e28-199">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="66e28-200">자세한 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="66e28-200">About Windows PowerShell</span></span>

<span data-ttu-id="66e28-201">이 Windows PowerShell 사용자 및 사용자가 할 수 있는 작업 또는 허용되지 않는 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-201">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="66e28-202">Windows PowerShell 사용하면 특히 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-202">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="66e28-203">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66e28-203">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="66e28-204">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="66e28-204">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="66e28-205">Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="66e28-205">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="66e28-206">Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-206">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="66e28-207">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-207">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="66e28-208">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="66e28-208">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="66e28-209">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="66e28-209">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="66e28-210">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66e28-210">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="66e28-211">관련 항목</span><span class="sxs-lookup"><span data-stu-id="66e28-211">Related topics</span></span>
[<span data-ttu-id="66e28-212">오디오 회의 브리지의 설정 변경</span><span class="sxs-lookup"><span data-stu-id="66e28-212">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
