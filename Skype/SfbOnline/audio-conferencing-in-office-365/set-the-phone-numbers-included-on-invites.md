---
title: 온라인에서 초대에 포함된 전화 비즈니스용 Skype 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '발신자들이 온라인 모임에 참가할 수 있는 기본 전화 번호를 만드는 비즈니스용 Skype 단계를 하세요. '
ms.openlocfilehash: 84bf0240270bfc9633f9d845130a6049d36c8cad
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237734"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="85b83-103">온라인에서 초대에 포함된 전화 비즈니스용 Skype 설정</span><span class="sxs-lookup"><span data-stu-id="85b83-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="85b83-104">모임 초대 전화 번호에 대한 자세한 Microsoft Teams 의 초대에 포함된 전화 번호 [Microsoft Teams.](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)</span><span class="sxs-lookup"><span data-stu-id="85b83-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="85b83-105">또는 Microsoft 365 Office 365 오디오 회의를 사용하면 조직의 사용자가 비즈니스용 Skype 모임을 만든 다음 사용자가 전화를 사용하여 해당 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-105">Audio Conferencing in Microsoft 365 or Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="85b83-106">Microsoft 365 및 Office 365 경우 승인된 ACP(오디오 회의 공급자)가 호스트하는 타사 오디오 회의 브리지 또는 Microsoft 오디오 회의 브리지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-106">In Microsoft 365 and Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="85b83-107">오디오 회의에 대한 모든 전화 접속 번호 목록을 포함하는 리소스는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-107">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="85b83-108">지역 또는 국가/지역에 전화 접속 전화 번호가 있는지 확인하려면 관리 센터 음성 비즈니스용 Skype 전화 번호 전화 다음 새 서비스 번호 추가를  >    >   **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="85b83-108">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="85b83-109">국가/지역,  **주/지역** 및 도시에  대한 목록을 사용하여 search.> 무료 서비스 번호를 찾고 있는 경우 **주/지역** 목록에서 무료 **전화(Toll-Free)를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-109">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="85b83-110">회의 브리지는 조직에 대한 전화 접속 전화 번호 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-110">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="85b83-111">모두 모임 이끌이가 만든 모임에 참가하는 데 사용할 수 있지만 모임 초대에 포함될 모임을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-111">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85b83-112">모임 이끌이에 대한 모임 초대에는 최대 1개의 전화 번호와 무료 전화 번호가 있을 수 있지만, 각 모임 초대의 아래쪽에 모임에 참가하는 데 사용할 수 있는 모든 전화 접속 전화 번호의 전체 목록을 여는 링크도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="85b83-113">모임 이끌이에 대한 기본 전화 접속 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="85b83-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="85b83-114">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-114">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="85b83-115">관리자 **센터를**  >  **비즈니스용 Skype.**</span><span class="sxs-lookup"><span data-stu-id="85b83-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="85b83-116">사용자를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="85b83-116">Choose **Users**.</span></span>
    
    ![관리 센터에서 비즈니스용 Skype 표시](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="85b83-118">편집할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-118">Choose the users you want to edit:</span></span>
    
   - <span data-ttu-id="85b83-119">단일 사용자를 선택하려면 사용자의 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-119">To select a single user, select the user's name.</span></span>
    
   - <span data-ttu-id="85b83-120">페이지의 모든 사용자를 선택하려면 목록 맨  위에 있는 표시 이름 옆에 있는 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
   - <span data-ttu-id="85b83-121">여러 사용자를 선택하려면 각 사용자의 이름 옆에 있는 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="85b83-122">오른쪽 패널에서 편집을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="85b83-122">In the right panel, choose **Edit**.</span></span>
    
    ![편집 아이콘을 선택 합니다.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="85b83-124">오디오 **회의를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="85b83-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="85b83-125">속성 **페이지에서** 공급자 **이름** 목록에서 사용자에 대한 공급자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-125">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="85b83-126">공급자에 따라 다음 상자를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-126">Depending on the provider, complete the following boxes.</span></span>
    
   - <span data-ttu-id="85b83-127">**Microsoft는** 공급자: 기본  무료 전화  번호 및 기본 무료 번호 목록을 사용하여 사용자의 기본 번호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="85b83-128">사용자 기본 무료 번호로 설정할 수 있도록 하기 전에 회의 브리지에 하나 이상의 무료 전화 번호가 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-128">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="85b83-129">무료 전화 번호를 얻은 경우 에 대한 서비스 전화 [번호 비즈니스용 Skype.](/microsoftteams/getting-service-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="85b83-129">To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers).</span></span> 
  
   - <span data-ttu-id="85b83-130">**타사는** 공급자입니다. 사용자에  대한 번호를  입력하기 위해 무료 전화 번호 및 무료 번호 필드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="85b83-131">오디오 회의 전화 번호 재설정</span><span class="sxs-lookup"><span data-stu-id="85b83-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="85b83-132">관리 **비즈니스용 Skype** 에서 오디오 회의 **를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="85b83-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="85b83-133">페이지 맨 위에 있는 사용자를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="85b83-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="85b83-134">다시 설정할 사용자를 선택한 다음 작업 창에서 지우기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85b83-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="85b83-135">기본적으로 사용자의 회의 설정을 변경하면 사용자에게 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-135">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="85b83-136">이를 변경하려면 오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 사용 안 [을 참조하세요.](enable-or-disable-sending-emails-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="85b83-136">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="85b83-137">사용자의 오디오 회의 설정을 변경하면 모임을 다시 비즈니스용 Skype 모임을 업데이트하고 참석자에게 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="85b83-138">사용자와 함께 관리하는 방법을 알고 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="85b83-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="85b83-139">시간을 절약하거나 자동화하기 위해 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="85b83-140">[Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet을 사용하여 특정 사용자의 기본 전화 또는 무료 전화 번호를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-140">Use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="85b83-141">사용자에 대한 기본 무료 번호를 변경하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-141">To change the default toll-free number for a user, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="85b83-142">**Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용하여 원래 기본 번호 또는 해당 위치에 따라 기본 무료 사용자 수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="85b83-143">BridgeID를 찾으신 경우 **Get-CsOnlineDialInConferencingBridge** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="85b83-144">+18005551234로 모든 사용자의 기본 무료 번호를 설정하면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="85b83-145">기본 무료 전화 번호로 +18005551234가 있는 모든 사용자의 기본 무료 수를 +18005551239로 변경하면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="85b83-146">미국에 있는 모든 사용자의 기본 무료 수를 +18005551234로 설정하면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="85b83-147">자세한 내용은 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="85b83-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="85b83-148">사용자 관리에 Windows PowerShell 사용자가 허용되거나 허용되지 않는 작업을 모두 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-148">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="85b83-149">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 Office 365 비즈니스용 Skype 단일 관리 지점을 사용하여 온라인 및 온라인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-149">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="85b83-150">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85b83-150">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="85b83-151">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="85b83-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="85b83-152">PowerShell 또는 Microsoft 365 Office 365 이유</span><span class="sxs-lookup"><span data-stu-id="85b83-152">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="85b83-153">Windows PowerShell 많은 사용자에 대해 한 Microsoft 365 설정하는 경우와 같이 관리 센터를 사용하는 것만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-153">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="85b83-154">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="85b83-154">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="85b83-155">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="85b83-155">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="85b83-156">온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="85b83-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="85b83-157">일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="85b83-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="85b83-158">관련 항목</span><span class="sxs-lookup"><span data-stu-id="85b83-158">Related topics</span></span>

[<span data-ttu-id="85b83-159">오디오 회의를 시도하거나 Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="85b83-159">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
