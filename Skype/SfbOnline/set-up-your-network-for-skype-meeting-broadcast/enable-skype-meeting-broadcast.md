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
description: 조직의 사용자가 Skype 모임 브로드캐스트를 사용하기 전에 이를 사용하도록 설정해야 합니다. 이렇게하려면 이 작업을 사용하는 방법을 Windows PowerShell. Microsoft 파트너를 Windows PowerShell 모르는 경우 이 단계를 위해 Microsoft 파트너를 고용하는 것이 고려됩니다.
ms.openlocfilehash: ab59348d32ef130df6b0de6e1eb65c92d0222e04
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097114"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="b8954-105">Skype 모임 브로드캐스트 사용</span><span class="sxs-lookup"><span data-stu-id="b8954-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8954-106">비즈니스용 Skype Online이 2021년 7월 31일 사용 중지 중입니다. 그러면 서비스에 대한 액세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="b8954-107">고객이 Microsoft 365에서 통신 및 팀워크의 핵심 클라이언트인 Microsoft Teams로 업그레이드를 시작하는 것이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="b8954-108">조직의 사용자가 Skype 모임 브로드캐스트를 사용하기 전에 이를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="b8954-109">이렇게하려면 이 작업을 사용하는 방법을 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8954-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="b8954-110">Microsoft 파트너를 Windows PowerShell 모르는 경우 이 단계를 위해 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 파트너를 고용하는 것이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="b8954-111">Microsoft Teams 관리 센터가 비즈니스용 Skype 관리 센터(레거시 포털)를 대체했습니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="b8954-112">이제 비즈니스용 Skype를 관리하기 위한 모든 설정이 Teams 관리 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="b8954-113">Teams 관리 센터에서 [비즈니스용 Skype](/azure/active-directory/roles/permissions-reference) 기능을 관리하려면 글로벌 관리자 또는 비즈니스용 Skype 관리자의 Azure AD 관리자 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-113">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="b8954-114">자세한 내용은 [Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8954-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="b8954-115">비즈니스용 Skype 관리 센터를 사용하여 Skype 모임 브로드캐스트 사용</span><span class="sxs-lookup"><span data-stu-id="b8954-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="b8954-116">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="b8954-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="b8954-117">글로벌 관리자 계정 또는 비즈니스용 Skype 관리자 계정으로 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="b8954-118">관리 센터에서 관리 센터 **Teams로**  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="b8954-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="b8954-119">Teams 관리 **센터에서** 레거시 포털 온라인 모임 브로드캐스트 모임으로 이동한 다음 Skype 모임 브로드캐스트 사용  >    >   **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b8954-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="b8954-120">PowerShell을 사용하여 Skype 모임 브로드캐스트 사용</span><span class="sxs-lookup"><span data-stu-id="b8954-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="b8954-121">Teams [PowerShell 모듈을 설치합니다.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="b8954-121">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="b8954-122">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-122">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. <span data-ttu-id="b8954-123">실행하여 현재 Skype 모임 브로드캐스트 구성 확인:</span><span class="sxs-lookup"><span data-stu-id="b8954-123">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="b8954-124">_EnableBroadcastMeeting_ 매개 변수가 로 설정되어 있는지 `False` 확인</span><span class="sxs-lookup"><span data-stu-id="b8954-124">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Skype 모임 브로드캐스트 조직 cmdlet을 사용하도록 설정합니다.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="b8954-126">실행하여 조직에 Skype 모임 브로드캐스트 사용:</span><span class="sxs-lookup"><span data-stu-id="b8954-126">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="b8954-127">다시 실행하여 설정을 사용하도록 설정할 수  `Get-CsBroadcastMeetingConfiguration` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-127">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Skype 모임 브로드캐스트는 조직 Cmdlet을 사용하도록 설정합니다.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="b8954-129">변경한 후 Skype 모임 브로드캐스트 포털에서 적용하는 데 최대 1시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-129">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="b8954-130">이제 사용자는 비즈니스의 다른 사용자와 브로드캐스트 모임을 개최할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-130">Your users can now hold broadcast meetings with other users in your business.</span></span> <span data-ttu-id="b8954-131">시작을 위해 Skype 모임 [](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) 브로드캐스트란?</span><span class="sxs-lookup"><span data-stu-id="b8954-131">To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="b8954-132">외부 참석자들과 모임을 브로드캐스트하도록 네트워크 구성</span><span class="sxs-lookup"><span data-stu-id="b8954-132">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="b8954-133">방화벽이 있는 경우 비즈니스 외부 사용자(페더리드 비즈니스가 아닌 사용자)와 브로드캐스트를 보류하려는 경우 다음 지침을 사용하여 네트워크를 구성해야 [합니다. Skype 모임](set-up-your-network-for-skype-meeting-broadcast.md)브로드캐스트에 대한 네트워크 설정 입니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-133">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="b8954-134">방화벽을 구성하는 데 경험이 없는 경우 이 단계를 위해 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 파트너를 고용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b8954-134">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="b8954-135">이 단계를 건너뛰고 페더연맹에 다른 비즈니스를 추가하는 대신 사용자가 비즈니스용 외부 Skype 사용자에 문의하도록 허용을 [참조하세요.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)</span><span class="sxs-lookup"><span data-stu-id="b8954-135">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="b8954-136">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b8954-136">Related topics</span></span>

[<span data-ttu-id="b8954-137">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="b8954-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[<span data-ttu-id="b8954-138">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="b8954-138">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
