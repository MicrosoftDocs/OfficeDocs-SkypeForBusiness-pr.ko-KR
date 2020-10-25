---
title: Skype 모임 브로드캐스트 사용
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: 조직의 사용자가 Skype 모임 브로드캐스트를 사용 하기 전에 먼저 사용 하도록 설정 해야 합니다. 이렇게 하려면 Windows PowerShell을 사용 하는 방법을 알고 있어야 합니다. Windows PowerShell을 모르는 경우 Microsoft 파트너를 고용 하 여이 단계를 수행 하는 것이 좋습니다.
ms.openlocfilehash: 20d3671beb608413c5d0d61f599f65a47b55732d
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753433"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="66807-105">Skype 모임 브로드캐스트 사용</span><span class="sxs-lookup"><span data-stu-id="66807-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66807-106">Microsoft 팀 관리 센터에서 비즈니스용 Skype 관리 센터 (레거시 포털)를 대체 했습니다.</span><span class="sxs-lookup"><span data-stu-id="66807-106">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="66807-107">비즈니스용 Skype 관리에 대 한 모든 설정이 이제 팀 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66807-107">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="66807-108">팀 관리 센터에서 비즈니스용 Skype 기능을 관리 하려면 전역 관리자 또는 비즈니스용 Skype 관리자의 [AZURE AD 관리자 역할이](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-108">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="66807-109">자세히 알아보려면 [Microsoft 팀 관리 센터에서 비즈니스용 Skype 설정 관리](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66807-109">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="66807-110">조직의 사용자가 Skype 모임 브로드캐스트를 사용 하기 전에 먼저 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-110">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="66807-111">이렇게 하려면 Windows PowerShell을 사용 하는 방법을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-111">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="66807-112">Windows PowerShell을 모르는 경우 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089) 를 고용 하 여이 단계를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66807-112">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="66807-113">비즈니스용 Skype 관리 센터를 사용 하 여 Skype 모임 브로드캐스트 사용</span><span class="sxs-lookup"><span data-stu-id="66807-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="66807-114">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="66807-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="66807-115">전역 관리자 계정 또는에서 비즈니스용 Skype 관리자 계정을 사용 하 여 로그인 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-115">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="66807-116">관리 센터에서 **관리 센터**  >  **팀**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-116">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="66807-117">**팀 관리 센터**에서 **기존 포털**  >  **온라인 모임**  >  **브로드캐스트 모임**으로 이동한 다음 **Skype 모임 브로드캐스트 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-117">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="66807-118">PowerShell을 사용 하 여 Skype 모임 브로드캐스트 사용</span><span class="sxs-lookup"><span data-stu-id="66807-118">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="66807-119">Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-119">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="66807-120">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴**에서  >  **Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-120">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="66807-121">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-121">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="66807-122">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-122">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="66807-123">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-123">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="66807-124">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-124">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="66807-125">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-125">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="66807-126">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66807-126">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="66807-127">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-127">Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="66807-128">**시작 메뉴**에서 **Windows PowerShell**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-128">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="66807-129">**Windows PowerShell** 창에서 다음을 실행 하 여 Microsoft 365 또는 Office 365에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-129">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="66807-130">다음을 실행 하 여 현재 Skype 모임 브로드캐스트 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-130">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="66807-131">매개 변수  _EnableBroadcastMeeting_ 가로 설정 되어 있는지 확인 `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-131">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype 모임 브로드캐스트 조직 cmdlet을 사용 하도록 설정 합니다.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="66807-133">다음을 실행 하 여 조직에 대해 Skype 모임 브로드캐스트를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-133">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="66807-134">다시 실행 하 여 설정을 사용 하도록 설정 했는지 확인할 수 있습니다  `Get-CsBroadcastMeetingConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="66807-134">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype 모임 브로드캐스트 조직 Cmdlet을 사용 하도록 설정 합니다.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="66807-136">변경 후 Skype 모임 브로드캐스트 포털에 영향을 주는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66807-136">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="66807-137">이제 사용자가 비즈니스의 다른 사용자와 브로드캐스트 모임을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66807-137">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="66807-138">시작 하려면 [Skype 모임 브로드캐스트를 선택](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) 하세요.</span><span class="sxs-lookup"><span data-stu-id="66807-138">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="66807-139">외부 참석자와의 모임을 브로드캐스트하도록 네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="66807-139">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="66807-140">방화벽이 있고 회사 외부의 사람들과 브로드캐스트를 보관 하려는 경우 (페더레이션 비즈니스 사용자가 아닌 경우) 다음 지침을 사용 하 여 네트워크를 구성 해야 합니다. [Skype 모임 브로드캐스트에 맞게 네트워크를 설정](set-up-your-network-for-skype-meeting-broadcast.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="66807-140">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="66807-141">방화벽 구성에 대 한 경험이 없는 경우 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089) 를 고용 하 여이 단계를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66807-141">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="66807-142">이 단계를 건너뛰고 대신 다른 비즈니스를 페더레이션에 추가 하려면 [사용자가 외부 비즈니스용 Skype 사용자에 게 연락할 수 있도록 허용](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66807-142">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="66807-143">관련 항목</span><span class="sxs-lookup"><span data-stu-id="66807-143">Related topics</span></span>

[<span data-ttu-id="66807-144">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="66807-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="66807-145">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="66807-145">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
