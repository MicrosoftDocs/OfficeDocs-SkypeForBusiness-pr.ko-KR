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
description: 사용자에 대한 범위를 확장하기 위해 전화 회의 브리지에 새 서비스 전화 번호를 할당하는 데 필요한 단계를 알아보십시오.
ms.openlocfilehash: e2e1aa3d5626f6592f22e0850a8c7419d7549b38
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569190"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a><span data-ttu-id="b6f1b-103">오디오 회의 브리지에서 전화 번호 변경</span><span class="sxs-lookup"><span data-stu-id="b6f1b-103">Change the phone numbers on your Audio Conferencing bridge</span></span>

<span data-ttu-id="b6f1b-104">오디오 회의  라이선스를 구입할 때 Microsoft는 조직에 대한 오디오 회의 브리지를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-104">When you buy **Audio Conferencing** licenses, Microsoft is hosting your audio conferencing bridge for your organization.</span></span> <span data-ttu-id="b6f1b-105">오디오 회의 브리지는 모임 이끌이와 참가자가 휴대폰을 사용하여 비즈니스용 Skype 또는 Microsoft Teams 모임에 참가하는 데 사용할 수 있도록 여러 위치에서 전화 접속 전화 번호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-105">The audio conferencing bridge gives out dial-in phone numbers from different locations so that meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.</span></span>
  
<span data-ttu-id="b6f1b-106">회의 브리지에 이미 할당된 전화 번호 외에도 다른 [](/microsoftteams/getting-service-phone-numbers) 위치에서 추가 서비스 번호(오디오 회의에 사용되는 무료 전화 번호)를 얻은 다음 회의 브리지에 할당하여 사용자에 대한 범위를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-106">In addition to the phone numbers already assigned to your conferencing bridge, you can [get additional service numbers](/microsoftteams/getting-service-phone-numbers) (toll and toll-free numbers used for audio conferencing) from other locations, and then assign them to the conferencing bridge so you can expand coverage for your users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b6f1b-107">회의 브리지에 대한 전화 번호를 할당/할당을 해지하려면 전화 번호가 *'서비스' 번호가 되어야* 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-107">To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number.</span></span> <span data-ttu-id="b6f1b-108">Microsoft Teams 관리 센터에서 음성 전화 번호로 돌아다니고 숫자 형식 열을 통해 해당 번호의 유형을 볼  >   **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-108">You can see the type of number it is by navigating to **Voice** > **Phone numbers** in the Microsoft Teams admin center and looking in the **Number Type** column.</span></span> <span data-ttu-id="b6f1b-109">사용자가 무료 번호로 브리지에 전화 접속하려면 Microsoft 365 또는 Office 365 Communications 크레딧을 먼저 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-109">Microsoft 365 or Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll-free number.</span></span>

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a><span data-ttu-id="b6f1b-110">회의 브리지에 새 서비스 전화 번호를 할당하는 단계</span><span class="sxs-lookup"><span data-stu-id="b6f1b-110">Steps when you are assigning a new service phone number to your conference bridge</span></span>

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a><span data-ttu-id="b6f1b-111">1단계 - 오디오 회의 브리지에 새 전화 번호 할당</span><span class="sxs-lookup"><span data-stu-id="b6f1b-111">Step 1 - Assign the new phone number to your audio conferencing bridge</span></span>

<span data-ttu-id="b6f1b-112">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b6f1b-113">왼쪽 탐색 창에서 **음성** 전화  >  **번호로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-113">On the left navigation pane, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="b6f1b-114">목록에서 전화 번호를 선택하고 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-114">Select the phone number from the list, and click **Edit**.</span></span>

3. <span data-ttu-id="b6f1b-115">편집 **페이지에서** 에 **할당된** 에서 드롭다운을 확장한 **다음, 컨퍼런스 브리지 적용 을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-115">On the **Edit** page, under **Assigned to**, expand the dropdown and then select **Conference bridge** > **Apply**.</span></span>

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a><span data-ttu-id="b6f1b-116">2단계 - 회의 브리지의 기본 전화 번호 변경(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b6f1b-116">Step 2 - Change the default phone number of your conference bridge (optional)</span></span>

<span data-ttu-id="b6f1b-117">회의 브리지의 기본 전화 번호는 참가자 또는 이끌이가 모임 내에서 아웃바운드 호출을 배치할 때 사용할 발신자 ID를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-117">The default phone number of your conference bridge defines the caller ID that will be used when an outbound call is placed by a participant or the organizer from within a meeting.</span></span>

<span data-ttu-id="b6f1b-118">회의 브리지의 기본 번호로 서비스 에일리트 번호만 설정할 수 있습니다. **서비스 무료 번호는** 회의 브리지의 기본 번호로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-118">Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**.</span></span> <span data-ttu-id="b6f1b-119">서비스 요금 번호를 할당하고 오디오 회의 브리지의 새 기본 번호로 설정하고자 하는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-119">If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, perform these steps:</span></span>

<span data-ttu-id="b6f1b-120">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b6f1b-121">왼쪽 탐색 창에서 모임 회의  >  **브리지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-121">On the left navigation pane, go to **Meetings** > **Conference bridges**.</span></span>

2. <span data-ttu-id="b6f1b-122">기본값으로 구성하려는 서비스 요금 번호를 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-122">Highlight the service toll number that you want to configure as the default.</span></span>

3. <span data-ttu-id="b6f1b-123">기본값으로 **설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-123">Select **Set as default**.</span></span>
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a><span data-ttu-id="b6f1b-124">3단계 - 사용자의 모임 초대에 포함된 기본 전화 번호 변경(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b6f1b-124">Step 3 - Change the default phone numbers that are included in the meeting invites of users (optional)</span></span>

<span data-ttu-id="b6f1b-125">사용자의 기본 전화 번호는 모임을 예약할 때 모임 초대에 포함된 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-125">The default phone numbers of a user are the ones that are included on their meeting invites when they schedule a meeting.</span></span> <span data-ttu-id="b6f1b-126">새 사용자에게 기본 전화 번호가 할당되는 방법을 비롯한 자세한 내용은 [Microsoft Teams의](set-the-phone-numbers-included-on-invites-in-teams.md) 초대에 포함된 전화 번호 설정 또는 [비즈니스용 Skype Online의](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)초대에 포함된 전화 번호 설정 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-126">For more information, including how the default phone numbers are assigned for new users, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

<span data-ttu-id="b6f1b-127">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-127">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b6f1b-128">왼쪽 탐색 창에서 사용자로 **이동하여** 목록에서 원하는 사용자의 표시 이름을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-128">On the left navigation pane, go to **Users** and click the Display name of the desired user on the list.</span></span>

2. <span data-ttu-id="b6f1b-129">오디오 **회의** 옆에 있는 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-129">Next to **Audio conferencing**, click on **Edit**.</span></span>

3. <span data-ttu-id="b6f1b-130">**전화 번호 또는** 무료 전화 번호에서 드롭다운에서 번호를 선택하고 적용을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="b6f1b-130">Under **Toll number** or **Toll-free number**, select the number from the dropdown and click **Apply**.</span></span>

<span data-ttu-id="b6f1b-131">변경 내용이 적용된 후 다음에 새 모임을 예약할 때 이끌이의 모임 초대에 새 기본 전화 번호가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-131">After the changes have been applied, the new default phone numbers will be included on the meeting invites of organizers the next time they schedule a new meeting.</span></span>

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a><span data-ttu-id="b6f1b-132">4단계 - 모임 마이그레이션 서비스를 사용하여 사용자의 기존 모임 초대 업데이트(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b6f1b-132">Step 4 - Update existing meeting invites of users using the Meeting Migration Service (optional)</span></span>

<span data-ttu-id="b6f1b-133">다음 두 단계의 경우 다음 단계를 시작해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-133">For the next two steps, you will need to start Windows PowerShell.</span></span>
  
<span data-ttu-id="b6f1b-134">일부 또는 전체 사용자의 모임 초대에 포함된 기본 전화 번호를 업데이트한 경우 모임 마이그레이션 서비스를 사용하여 기본 전화 번호가 변경되기 전에 조직 내 사용자에게 이미 전송된 모임 초대를 선택적으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-134">If you updated the default phone numbers that are included in the meeting invites for some or all of your users, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed using the Meeting Migration Service.</span></span> <span data-ttu-id="b6f1b-135">자세한 내용은 [MMS(모임 마이그레이션 서비스) 설정을 참조하세요.](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="b6f1b-135">For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
- <span data-ttu-id="b6f1b-136">2단계에서 기본 전화 번호가 변경된 사용자에 대해 MMS(모임 마이그레이션 서비스)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-136">Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2.</span></span> <span data-ttu-id="b6f1b-137">이렇게 하여 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-137">To do this, run the following command:</span></span>

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- <span data-ttu-id="b6f1b-138">모임 마이그레이션 상태를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-138">You can also view the meeting migration status.</span></span> <span data-ttu-id="b6f1b-139">보류 중 또는 진행 중인 상태의 작업이 없는  경우 모든 모임이 다시 *예약됩니다.*</span><span class="sxs-lookup"><span data-stu-id="b6f1b-139">All meetings would be rescheduled once there are no operations in  *Pending*  or *In-Progress*  state.</span></span>

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a><span data-ttu-id="b6f1b-140">회의 브리지에 대한 서비스 전화 번호를 부가할 때 단계</span><span class="sxs-lookup"><span data-stu-id="b6f1b-140">Steps when you are unassigning a service phone number for a conferencing bridge</span></span>


<span data-ttu-id="b6f1b-141">회의 브리지에서 전화 번호를 부가하면 사용자는 더 이상 해당 전화 번호를 사용하여 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-141">When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore.</span></span> <span data-ttu-id="b6f1b-142">전화 번호가 변경되기 때문에 전화 번호가 기본 번호로 있을 수 있는 모든 사용자를 업데이트하고(있는 경우) 오디오 회의 브리지에서 전화 번호가 부적당하지 않은 경우 기존 모임 초대를 업데이트하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-142">Because the phone number is changing, it's important to update all users who could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.</span></span>

<span data-ttu-id="b6f1b-143">사용자 및 모임을 업데이트하지 않고 전화 번호가 제거된 경우 기존 모임 초대에는 모임에 참가하기 위해 작동하지 않는 전화 번호가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-143">If the phone number is removed without updating the users and their meetings, their existing meeting invites could contain a phone number that won't work for joining their meetings.</span></span>

<span data-ttu-id="b6f1b-144">처음 3단계의 경우 시작해야 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-144">For the first three steps, you will need to start Windows PowerShell.</span></span> <span data-ttu-id="b6f1b-145">이 작업을 하는 방법을 보려면 이 작업을 사용하여 관리 방법을 알고 [Windows PowerShell.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="b6f1b-145">To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)</span></span>

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a><span data-ttu-id="b6f1b-146">1단계 - 기본 번호 중 하나에 전화 번호가 지정되지 않은 사용자를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-146">Step 1 - Update users who have the phone number to be unassigned as one of their default numbers</span></span>

<span data-ttu-id="b6f1b-147">번호가 기본 번호로 지정되지 않은 모든 사용자의 기본 통행료 또는 무료 번호를 바꾸고 모임을 다시 구성하는 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-147">Replace the default toll or toll-free number for all users who have the number to be unassigned as a default number and start the process of rescheduling their meetings.</span></span> <span data-ttu-id="b6f1b-148">이렇게 하여 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-148">To do this, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 ><span data-ttu-id="b6f1b-149">Microsoft Teams 관리 센터에서 기본 사용자 수 또는 무료 사용자 수를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-149">You can also change the default toll or toll-free number of users in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b6f1b-150">그러나 모임을 자동으로 다시 조정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-150">However, this won't automatically reschedule their meetings.</span></span> 
 
 <span data-ttu-id="b6f1b-151">자세한 내용은 [Microsoft Teams의](set-the-phone-numbers-included-on-invites-in-teams.md) 초대에 포함된 전화 번호 설정 또는 비즈니스용 Skype Online의 초대에 포함된 전화 번호 설정 을 [참조하세요.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)</span><span class="sxs-lookup"><span data-stu-id="b6f1b-151">For additional information, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) or [Set the phone numbers included on invites in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b6f1b-152">조직의 크기에 따라 완료하는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-152">Depending on the size of your organization, this could take some time to complete.</span></span>

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a><span data-ttu-id="b6f1b-153">2단계 - 모임 마이그레이션 상태를 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6f1b-153">Step 2 - View meeting migration status using Windows PowerShell</span></span>

<span data-ttu-id="b6f1b-154">보류 중 또는 진행 중인 상태의 작업이 없는  경우 모든 모임이 다시 *예약됩니다.*</span><span class="sxs-lookup"><span data-stu-id="b6f1b-154">All meetings will be rescheduled once there are no operations in *Pending* or *In-Progress* state.</span></span>

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="b6f1b-155">모임 마이그레이션 서비스에 대한 자세한 내용은 [MMS(모임 마이그레이션 서비스) 설정을 참조하세요.](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)</span><span class="sxs-lookup"><span data-stu-id="b6f1b-155">For more information about the Meeting Migration Service, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).</span></span>
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a><span data-ttu-id="b6f1b-156">3단계 - 오디오 회의 브리지에서 이전 전화 번호의 부호를 매기지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-156">Step 3 - Unassign the old phone number from the audio conferencing bridge</span></span>

<span data-ttu-id="b6f1b-157">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-157">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b6f1b-158">왼쪽 탐색에서 **음성** 전화  >  **번호로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-158">In the left navigation, go to **Voice** > **Phone numbers**.</span></span>

2. <span data-ttu-id="b6f1b-159">전화 번호가 무료 전화 번호인 경우 목록에서 전화 번호를 선택하고 릴리스를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-159">If the phone number is a toll-free number, select the phone number from the list, and click **Release**.</span></span> <span data-ttu-id="b6f1b-160">전화 번호가 통행료 번호인 경우 [Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) 지원에 전화 번호가 부인되지 않은지 문의해 주세요.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-160">If the phone number is a toll number, please contact [Microsoft support](https://go.microsoft.com/fwlink/?linkid=2091806) to have the phone number unassigned.</span></span>

3. <span data-ttu-id="b6f1b-161">전화 번호가 무료 전화 번호인 경우 확인 창에서 **예를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-161">If the phone number is a toll-free number, click **Yes** in the confirmation window.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="b6f1b-162">오디오 회의 브리지에서 전화 번호가 부가되지 않은 경우 사용자가 새 모임 또는 기존 모임에 참가할 수 있는 전화 번호를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-162">After a phone number is unassigned from an audio conferencing bridge, the phone number will no longer be available for users to join new or existing meetings.</span></span>

### <a name="save-time-and-automate"></a><span data-ttu-id="b6f1b-163">시간 절약 및 자동화</span><span class="sxs-lookup"><span data-stu-id="b6f1b-163">Save time and automate</span></span>

<span data-ttu-id="b6f1b-164">이 프로세스를 자동화하여 시간을 절약하기 위해 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) 또는 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-164">To save time by automating this process, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) or the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlets.</span></span>

- <span data-ttu-id="b6f1b-165">[Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet을 사용하여 특정 사용자의 기본 전화 또는 무료 전화 번호를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-165">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>

  - <span data-ttu-id="b6f1b-166">사용자에 대한 기본 무료 번호를 변경하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-166">To change the default toll-free number for a user, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- <span data-ttu-id="b6f1b-167">**Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용하여 원래 기본 번호 또는 해당 위치에 따라 기본 무료 사용자 수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-167">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b6f1b-168">BridgeID를 찾으신 경우 **Get-CsOnlineDialInConferencingBridge 를 사용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-168">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>

  - <span data-ttu-id="b6f1b-169">8005551234로 1개가 없는 모든 사용자의 기본 무료 번호를 설정하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-169">To set the default toll-free number for all users without one to 8005551234, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="b6f1b-170">기본 무료 전화 번호로 8005551234가 있는 모든 사용자의 기본 무료 수를 8005551239로 변경하고 모임을 자동으로 다시 조정하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-170">To change the default toll-free number of all users that have 8005551234 as their default toll-free number to 8005551239 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - <span data-ttu-id="b6f1b-171">미국에 있는 모든 사용자의 기본 무료 전화 수를 8005551234로 설정하고 모임을 자동으로 다시 조정하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-171">To set the default toll-free number of all users located in the U.S. to 8005551234 and automatically reschedule their meetings, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > <span data-ttu-id="b6f1b-172">위에 사용된 위치는 Microsoft 365 관리 센터에 설정된 사용자의 연락처 정보와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-172">The location that is used above needs to match the contact information of user(s) that is set in the Microsoft 365 admin center.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b6f1b-173">문제 해결</span><span class="sxs-lookup"><span data-stu-id="b6f1b-173">Troubleshooting</span></span>

<span data-ttu-id="b6f1b-174">**선택하지 않는 단추를 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="b6f1b-174">**Unassign button isn't available**</span></span>

<span data-ttu-id="b6f1b-175">번호의 배정을 해지하려는 경우 단추를 사용할 수 없습니다. 단추를 마우스로 이동하는 동안 지원에 "기본 또는 공유 번호는 브리지에서 부적당할 수 _없습니다. 전용 통행료_ 번호를 부적당하지 않은 경우 지원에 문의하시기 바랍니다. ".</span><span class="sxs-lookup"><span data-stu-id="b6f1b-175">You want to Unassign a number but the button isn't available, and if while hovering over it, you are redirected to contact Support with the following message _"Default or shared numbers can´t be unassigned from the bridge. To unassign dedicated toll numbers, please contact support._".</span></span>

<span data-ttu-id="b6f1b-176">브리지에 대한 자세한 내용은 다음 Powershell을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-176">To obtain more information about the bridge(s), run the following Powershell :</span></span>
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

<span data-ttu-id="b6f1b-177">그 결과 ID, 이름 및 지역과 같은 다른 정보도 DefaultServiceNumber를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-177">The result, aside other information like Identity, Name and Region, should also contain the DefaultServiceNumber.</span></span>

<span data-ttu-id="b6f1b-178">**예제** 를 지정하지 않는 경우 DefaultServiceNumber "8005551234"</span><span class="sxs-lookup"><span data-stu-id="b6f1b-178">**Example**, to unassign, the DefaultServiceNumber "8005551234"</span></span>
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a><span data-ttu-id="b6f1b-179">About Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6f1b-179">About Windows PowerShell</span></span>

<span data-ttu-id="b6f1b-180">이 Windows PowerShell 사용자 및 사용자가 할 수 있는 작업 또는 허용되지 않는 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-180">With Windows PowerShell you can manage users and what they are or are not allowed to do.</span></span> <span data-ttu-id="b6f1b-181">Windows PowerShell 작업을 여러 번 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-181">Windows PowerShell  can help you manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do.</span></span> <span data-ttu-id="b6f1b-182">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-182">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="b6f1b-183">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="b6f1b-183">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="b6f1b-184">Office 365 PowerShell을 사용해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="b6f1b-184">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

<span data-ttu-id="b6f1b-185">Windows PowerShell 사용자에 대한 설정을 한 번씩 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-185">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b6f1b-186">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-186">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="b6f1b-187">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6f1b-187">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="b6f1b-188">비즈니스용 skype Windows PowerShell 관리하기 위해 사용</span><span class="sxs-lookup"><span data-stu-id="b6f1b-188">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="b6f1b-189">비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1b-189">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="b6f1b-190">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b6f1b-190">Related topics</span></span>
[<span data-ttu-id="b6f1b-191">오디오 회의 브리지의 설정 변경</span><span class="sxs-lookup"><span data-stu-id="b6f1b-191">Change the settings for an Audio Conferencing bridge</span></span>](change-the-settings-for-an-audio-conferencing-bridge.md)
