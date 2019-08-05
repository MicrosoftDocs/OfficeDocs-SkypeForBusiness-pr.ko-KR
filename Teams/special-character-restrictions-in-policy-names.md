---
title: 팀 정책의 특수 문자 제한 사항은 무엇 인가요?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: 정책 이름에 특수 문자와 문제 해결을 위해 수행할 수 있는 작업에 대해 알아봅니다.
ms.openlocfilehash: 03858de420cf77f8a8088f86c8c5feae5828c21a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182399"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="4756e-103">팀 정책의 특수 문자 제한 사항은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="4756e-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="4756e-104">**Microsoft 팀 관리 센터에서 이름에 특수 문자를 포함 하는 정책을 만들거나 편집할 수 없습니다 (메시징, 모임 등)**.</span><span class="sxs-lookup"><span data-stu-id="4756e-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="4756e-105">정책 이름에 특수 문자가 포함 된 경우 Microsoft 팀 관리 센터에서 이러한 정책 관리에 제한을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4756e-106">따라서 **정책 이름에 특수 문자를 포함 하지 않는 것이 좋습니다**.</span><span class="sxs-lookup"><span data-stu-id="4756e-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="4756e-107">팀에서 모임 및 메시지에 대해 PowerShell을 사용 하 여 만든 정책 이름은 @, #, $와 같은 특수 문자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="4756e-108">그러나 Microsoft 팀 관리 센터에서 정책을 변경 하려는 경우에는이 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="4756e-109">특수 문자를 사용 하는 정책이 있는 경우 Windows PowerShell을 사용 하 여 정책 편집 (계속) 하거나 기존 정책과 동일한 설정을 사용 하 여 Microsoft 팀 관리 센터에서 새 정책을 만든 다음 동일한 사용자 그룹에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="4756e-110">특수 문자를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="4756e-110">To remove special characters</span></span>

<span data-ttu-id="4756e-111">**1 단계-PowerShell을 사용 하 여 원격 연결을 설정 합니다.** 
아직 설치 하지 않은 경우 [Windows PowerShell 용 컴퓨터를 설정](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 합니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="4756e-112">**2 단계-이전 정책에 대 한 설정을 가져오고 출력을 캡처합니다.**</span><span class="sxs-lookup"><span data-stu-id="4756e-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="4756e-113">이 예제는 [메시징](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 정책에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="4756e-114">단계는 다른 정책 유형의 경우와 동일 하지만 올바른 cmdlet을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="4756e-115">**3 단계-새 정책 만들기**</span><span class="sxs-lookup"><span data-stu-id="4756e-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="4756e-116">Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 동일한 설정으로 새 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-116">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="4756e-117">이 작업을 실행 하면 새 정책이 만들어지지만, [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) 를 표시 한 다음 실행 하 여 올바른 설정을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="4756e-118">**4 단계-정책을 할당 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4756e-118">**Step 4 - Assign the policy.**</span></span>
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="4756e-119">이 cmdlet에 대 한 자세한 내용은 [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4756e-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="4756e-120">**5 단계-이전 정책 삭제**</span><span class="sxs-lookup"><span data-stu-id="4756e-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="4756e-121">이렇게 하면 특수 문자를 사용 하 여 이전 정책이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-121">This will delete the old policy with the special characters.</span></span>
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="4756e-122">이 cmdlet에 대 한 자세한 내용은 [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4756e-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="4756e-123">이 명령이 성공 하면 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="4756e-124">위의 명령에서 오류를 반환 하는 경우 정책에서 할당 된 모든 사용자를 제거 하기 위해 이전 정책이 사용자에 게 할당 되므로이는 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4756e-125">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="4756e-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="4756e-126">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4756e-127">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-127">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="4756e-128">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4756e-128">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4756e-129">Office 365 PowerShell을 사용 해야 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="4756e-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4756e-130">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="4756e-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="4756e-131">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="4756e-132">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4756e-132">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4756e-133">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="4756e-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="4756e-134">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="4756e-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4756e-135">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="4756e-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="4756e-136">비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online 및 Microsoft 팀에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="4756e-137">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4756e-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

