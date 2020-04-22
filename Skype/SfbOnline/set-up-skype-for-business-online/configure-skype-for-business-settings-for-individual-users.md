---
title: 관리자 개별 사용자에 대 한 비즈니스용 Skype 설정 구성
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: '오디오 및 비디오 회의, 통화 기록, 모임 기록과 같은 개별 사용자의 비즈니스용 Skype 설정을 변경 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 5247d814429d8d1f62fe9ea963aa76b7aafe40df
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776323"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="4e8a1-103">관리자: 개별 사용자에 대해 비즈니스용 Skype 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="4e8a1-104">이 문서에서는 관리자가 소수의 사용자에 대해 비즈니스용 Skype를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="4e8a1-105">이러한 단계를 대량으로 수행 하기 위해 사용할 수 있는 Windows PowerShell cmdlet에 대 한 링크를 포함 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="4e8a1-106">비즈니스의 모든 사용자가 외부 사용자와 통신 하도록 허용 (또는 차단) 하려면 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="4e8a1-107">[사용자가 외부 비즈니스용 skype 사용자에 게 연락할 수 있도록 허용](allow-users-to-contact-external-skype-for-business-users.md): 조직에서 신뢰할 수 있는 특정 (페더레이션된) 비즈니스 사용자와 통신 하려면 고급 Skype for business 기능 (데스크톱 공유, 온라인 상태 확인 등)을 사용 하도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="4e8a1-108">또한 특정 도메인과의 통신을 차단 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="4e8a1-109">비즈니스용 [skype 사용자가 skype 연락처를 추가할 수](let-skype-for-business-users-add-skype-contacts.md)있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="4e8a1-110">회사에서 비즈니스용 Skype를 사용 하 여 Skype를 사용 하는 사람을 검색 하 고 IM을 사용할 수 있습니다 (무료 앱).</span><span class="sxs-lookup"><span data-stu-id="4e8a1-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="4e8a1-111">한 명의 사용자에 대 한 일반 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4e8a1-111">Configure general settings for one user</span></span>
<span data-ttu-id="4e8a1-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="4e8a1-112"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="4e8a1-113">이 단계를 수행 하려면 [관리자 권한이](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="4e8a1-114">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="4e8a1-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="4e8a1-115">회사 또는 학교 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-115">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="4e8a1-116">**관리 센터** > **비즈니스용 Skype를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-116">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="4e8a1-117">**사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-117">Choose **Users**.</span></span>
    
    ![비즈니스용 Skype 관리 센터에서 사용자를 선택 합니다.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="4e8a1-119">편집 하려는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-119">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="4e8a1-120">오른쪽 창에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-120">In the right panel, choose **Edit**.</span></span>
    
    ![편집 아이콘을 선택 합니다.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="4e8a1-122">**일반** 옵션 페이지에서 변경 하려는 기능 옆에 있는 확인란을 선택 하거나 선택을 취소 한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-122">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="4e8a1-123">**방법을**</span><span class="sxs-lookup"><span data-stu-id="4e8a1-123">**Option**</span></span>|<span data-ttu-id="4e8a1-124">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="4e8a1-124">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4e8a1-125">오디오 및 HD 비디오</span><span class="sxs-lookup"><span data-stu-id="4e8a1-125">Audio and HD video</span></span>  <br/> |<span data-ttu-id="4e8a1-126">이 사람이 오디오 모임, 오디오 및 비디오 모임을 녹음/녹화할 수 있도록 허용 하거나 모임 예약을 허용 하지 않습니다 (없음).</span><span class="sxs-lookup"><span data-stu-id="4e8a1-126">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="4e8a1-127">대화 및 모임 기록</span><span class="sxs-lookup"><span data-stu-id="4e8a1-127">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="4e8a1-128">이 사용자가 녹화할 수 있는 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-128">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="4e8a1-129">이 옵션은 비즈니스용 Skype Basic에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-129">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="4e8a1-130">준수를 위해 보관 되지 않는 기능 해제</span><span class="sxs-lookup"><span data-stu-id="4e8a1-130">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="4e8a1-131">전자적으로 저장 된 정보를 보존 해야 하는 경우이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-131">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="4e8a1-132">이 옵션을 선택 하면 Exchange 관리 센터에 원본 [위치 유지](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) 가 설정 되어 있는 경우에는 캡처되지 않은 기능이 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-132">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="4e8a1-133">이 기능은 다음 기능을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-133">It turns off the following features:</span></span> <br/>  <span data-ttu-id="4e8a1-134">인스턴트 메시지를 사용 하 여 파일 전송</span><span class="sxs-lookup"><span data-stu-id="4e8a1-134">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="4e8a1-135">공유 OneNote 페이지</span><span class="sxs-lookup"><span data-stu-id="4e8a1-135">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="4e8a1-136">PowerPoint 주석</span><span class="sxs-lookup"><span data-stu-id="4e8a1-136">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="4e8a1-137">이러한 설정을 일괄적으로 구성 하려면 PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-137">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="4e8a1-138">[Windows PowerShell에 대 한 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-138">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="4e8a1-139">외부 통신 차단</span><span class="sxs-lookup"><span data-stu-id="4e8a1-139">Block external communications</span></span>
<span data-ttu-id="4e8a1-140"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="4e8a1-140"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="4e8a1-141">[비즈니스용 skype 사용자가](let-skype-for-business-users-add-skype-contacts.md) 회사의 모든 사용자에 게 skype 연락처를 추가 하도록 하면 이러한 단계를 사용 하 여 특정 개인에 대 한 외부 통신을 선택적으로 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-141">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="4e8a1-142">**사용자**를 선택 하 고 설정을 사용 하지 않도록 설정할 사용자를 선택한 다음 ![](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) **편집 편집을 선택 합니다** .</span><span class="sxs-lookup"><span data-stu-id="4e8a1-142">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="4e8a1-143">**외부 통신**을 선택 하 고 필요에 따라 옵션의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-143">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="4e8a1-144">**외부 비즈니스용 skype 사용자**: 사용자가 페더레이션 도메인의 비즈니스용 skype 사용자와 통신할 수 없도록 하려면이 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-144">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="4e8a1-145">**외부 Skype 사용자**: freeSkype 앱을 사용 하는 사용자와 통신할 수 없도록 하려면이 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-145">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="4e8a1-146">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-146">Click **Save**.</span></span>
    
<span data-ttu-id="4e8a1-147">이러한 설정을 일괄적으로 구성 하려면 PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-147">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="4e8a1-148">[Windows PowerShell에 대 한 컴퓨터 설정을](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-148">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="4e8a1-149">한 명의 사용자에 대 한 오디오 회의 설정 편집</span><span class="sxs-lookup"><span data-stu-id="4e8a1-149">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="4e8a1-150"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="4e8a1-150"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="4e8a1-151">**사용자**를 선택 하 고, wan을 사용 하 여 편집할 사용자를 선택 하 고 ![편집](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)을 **선택 합니다** .</span><span class="sxs-lookup"><span data-stu-id="4e8a1-151">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="4e8a1-152">**오디오 회의**를 선택 하 고 오디오 회의 공급자를 선택 하 고 요청 된 정보를 입력 하거나 변경한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-152">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="4e8a1-153">**오디오 회의 설정**</span><span class="sxs-lookup"><span data-stu-id="4e8a1-153">**Audio conferencing setting**</span></span>|<span data-ttu-id="4e8a1-154">**설명**</span><span class="sxs-lookup"><span data-stu-id="4e8a1-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4e8a1-155">**공급자 이름**</span><span class="sxs-lookup"><span data-stu-id="4e8a1-155">**Provider name**</span></span> <br/> |<span data-ttu-id="4e8a1-156">목록에서 공급자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-156">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="4e8a1-157">**유료 전화 번호** (필수)</span><span class="sxs-lookup"><span data-stu-id="4e8a1-157">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="4e8a1-158">타사 ACP의 경우 이러한 전화 번호는 오디오 회의 공급자 로부터 받은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-158">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="4e8a1-159">사용자가 Microsoft를 오디오 회의 공급자로 사용 하는 경우 오디오 회의 브리지에 설정 된 숫자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-159">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="4e8a1-160">비즈니스용 Skype 및 Microsoft 팀 모임 요청에 표시할 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-160">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="4e8a1-161">**무료 번호**</span><span class="sxs-lookup"><span data-stu-id="4e8a1-161">**Toll-free number**</span></span> <br/> |<span data-ttu-id="4e8a1-162">타사 ACP의 경우 이러한 전화 번호는 오디오 회의 공급자 로부터 받은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="4e8a1-163">사용자가 Microsoft를 오디오 회의 공급자로 사용 하는 경우 오디오 회의 브리지에 설정 된 숫자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="4e8a1-164">비즈니스용 Skype 및 Microsoft 팀 모임 요청에 표시할 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="4e8a1-165">**전화 회의 ID 및 PIN** (필수)</span><span class="sxs-lookup"><span data-stu-id="4e8a1-165">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="4e8a1-166">이 사용자가 예약한 모임에 참가 하는 데 사용 되는 참가자 PIN 또는 회의 코드는 타사 오디오 회의 공급자 로부터 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-166">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="4e8a1-167">사용자가 Microsoft를 오디오 회의 공급자로 사용 하는 경우에는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-167">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="4e8a1-168">이러한 설정을 일괄적으로 구성 하려면 PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-168">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="4e8a1-169">[Windows PowerShell에 대 한 컴퓨터 설정](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) [에는 초대에 포함 된 전화 번호 설정을](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e8a1-169">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="4e8a1-170">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4e8a1-170">Related topics</span></span> 

[<span data-ttu-id="4e8a1-171">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="4e8a1-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="4e8a1-172">비즈니스용 Skype 및 Microsoft 팀 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="4e8a1-172">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
