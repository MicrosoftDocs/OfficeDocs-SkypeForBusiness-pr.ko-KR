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
ms.openlocfilehash: 1b06f327fa59ec8e90c9b014db8a252ca7b40579
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010611"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="8df9b-105">Skype 모임 브로드캐스트 사용</span><span class="sxs-lookup"><span data-stu-id="8df9b-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="8df9b-106">조직의 사용자가 Skype 모임 브로드캐스트를 사용 하기 전에 먼저 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-106">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="8df9b-107">이렇게 하려면 Windows PowerShell을 사용 하는 방법을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-107">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="8df9b-108">Windows PowerShell을 모르는 경우 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089) 를 고용 하 여이 단계를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-108">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="8df9b-109">비즈니스용 Skype 관리 센터를 사용 하 여 Skype 모임 브로드캐스트 사용</span><span class="sxs-lookup"><span data-stu-id="8df9b-109">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="8df9b-110">![비즈니스용 skype](../images/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="8df9b-110">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="8df9b-111">Office 365 전역 관리자 계정 또는에서 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)비즈니스용 Skype 관리자 계정을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-111">Sign in with your Office 365 global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="8df9b-112">관리 센터에서 **관리 센터** > **팀**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-112">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="8df9b-113">**팀 관리 센터**에서 **기존 포털** > **온라인 모임** > **브로드캐스트 모임**으로 이동한 다음 **Skype 모임 브로드캐스트 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-113">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="8df9b-114">PowerShell을 사용 하 여 Skype 모임 브로드캐스트 사용</span><span class="sxs-lookup"><span data-stu-id="8df9b-114">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="8df9b-115">Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-115">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="8df9b-116">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-116">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="8df9b-117">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-117">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="8df9b-118">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-118">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="8df9b-119">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-119">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="8df9b-120">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-120">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="8df9b-121">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-121">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="8df9b-122">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-122">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="8df9b-123">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-123">Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="8df9b-124">**시작 메뉴**에서 **Windows PowerShell**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-124">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="8df9b-125">**Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="8df9b-126">다음을 실행 하 여 현재 Skype 모임 브로드캐스트 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-126">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="8df9b-127">매개 변수 _EnableBroadcastMeeting_ 가로 `False`설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-127">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype 모임 브로드캐스트 조직 cmdlet을 사용 하도록 설정 합니다.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="8df9b-129">다음을 실행 하 여 조직에 대해 Skype 모임 브로드캐스트를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-129">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="8df9b-130">다시 실행 `Get-CsBroadcastMeetingConfiguration` 하 여 설정을 사용 하도록 설정 했는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-130">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype 모임 브로드캐스트 조직 Cmdlet을 사용 하도록 설정 합니다.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="8df9b-132">변경 후 Skype 모임 브로드캐스트 포털에 영향을 주는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-132">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="8df9b-133">이제 사용자가 비즈니스의 다른 사용자와 브로드캐스트 모임을 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-133">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="8df9b-134">시작 하려면 [Skype 모임 브로드캐스트를 선택](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) 하세요.</span><span class="sxs-lookup"><span data-stu-id="8df9b-134">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="8df9b-135">외부 참석자와의 모임을 브로드캐스트하도록 네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="8df9b-135">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="8df9b-136">방화벽이 있고 회사 외부의 사람들과 브로드캐스트를 보관 하려는 경우 (페더레이션 비즈니스 사용자가 아닌 경우) 다음 지침을 사용 하 여 네트워크를 구성 해야 합니다. [Skype 모임 브로드캐스트에 맞게 네트워크를 설정](set-up-your-network-for-skype-meeting-broadcast.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-136">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="8df9b-137">방화벽 구성에 대 한 경험이 없는 경우 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089) 를 고용 하 여이 단계를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8df9b-137">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="8df9b-138">이 단계를 건너뛰고 대신 다른 비즈니스를 페더레이션에 추가 하려면 [사용자가 외부 비즈니스용 Skype 사용자에 게 연락할 수 있도록 허용](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8df9b-138">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="8df9b-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8df9b-139">Related topics</span></span>

[<span data-ttu-id="8df9b-140">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="8df9b-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="8df9b-141">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="8df9b-141">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
