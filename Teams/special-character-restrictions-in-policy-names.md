---
title: Teams 정책의 특수 문자 제한 사항
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: 정책 이름에 특수 문자가 있는 문제와 이를 해결하기 위해 할 수 있는 작업을 참조합니다.
ms.openlocfilehash: 15df8b64f423d1ee20df6e230e4a9cdbebcb56db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116986"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="f36db-103">정책의 특수 문자 제한은 Teams 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="f36db-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="f36db-104">관리 센터의 이름에 특수 문자가 있는 정책(메시징, 모임 **등)을 만들거나** 편집할 수 Microsoft Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="f36db-105">정책 이름에 특수 문자가 포함된 경우 관리 센터에서 이러한 정책을 Microsoft Teams 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f36db-106">**따라서 정책 이름에** 특수 문자가 포함되지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="f36db-107">PowerShell을 사용하여 만든 정책 이름은 Teams@,#,$과 같은 특수 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="f36db-108">그러나 관리 센터에서 정책을 변경하려는 경우 Microsoft Teams 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="f36db-109">특수 문자가 있는 정책이 있는 경우 이전 정책과 동일한 설정으로 Windows PowerShell(영원)를 사용하여 정책을 편집하거나 Microsoft Teams 관리 센터에서 새 정책을 만들고 동일한 사용자 그룹에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="f36db-110">특수 문자를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="f36db-110">To remove special characters</span></span>

<span data-ttu-id="f36db-111">**1단계 - PowerShell을 사용하여 원격 연결합니다.**</span><span class="sxs-lookup"><span data-stu-id="f36db-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="f36db-112">비즈니스용 Skype 온라인 커넥터는 현재 최신 PowerShell Teams 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="f36db-113">최신 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


<span data-ttu-id="f36db-114">**2단계 - 이전 정책에 대한 설정을 표시하고 출력을 캡처합니다.**</span><span class="sxs-lookup"><span data-stu-id="f36db-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="f36db-115">이 예제는 메시징 [정책에 대한](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-115">This example is for a [Messaging](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="f36db-116">단계는 다른 정책 유형과 동일하지만 올바른 cmdlet을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="f36db-117">**3단계 - 새 정책 만들기**</span><span class="sxs-lookup"><span data-stu-id="f36db-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="f36db-118">관리 센터 또는 PowerShell을 사용하여 동일한 설정으로 새 정책을 Microsoft Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="f36db-119">이 정책을 실행하면 새 정책이 생성되지만 [Set-CsTeamsMessagingPolicy를](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) 보고 올바른 설정을 추가한 다음 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="f36db-120">**4단계 - 정책을 할당합니다.**</span><span class="sxs-lookup"><span data-stu-id="f36db-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="f36db-121">이 cmdlet에 대한 자세한 내용은 [Grant-CsTeamsMessagingPolicy를](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f36db-121">See, [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="f36db-122">**5단계 - 이전 정책을 삭제합니다.**</span><span class="sxs-lookup"><span data-stu-id="f36db-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="f36db-123">이렇게 하면 특수 문자가 있는 이전 정책이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="f36db-124">이 cmdlet에 대한 자세한 내용은 [Remove-CsTeamsMessagingPolicy를](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f36db-124">See, [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="f36db-125">이 명령이 성공하면 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="f36db-126">위의 명령이 오류를 반환하는 경우 이전 정책이 사용자에게 할당되어 있으므로 정책에서 할당된 모든 사용자를 제거하기 위해 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f36db-127">사용자와 함께 관리하는 방법을 알고 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f36db-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="f36db-128">Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f36db-129">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f36db-130">다음 항목을 Windows PowerShell 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f36db-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f36db-131">PowerShell을 Office 365 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="f36db-131">Why you need to use Office 365 PowerShell?</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="f36db-132">[사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f36db-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="f36db-133">Windows PowerShell 많은 사용자에 대한 설정을 한 Microsoft 365 경우와 같이 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="f36db-134">다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="f36db-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f36db-135">Windows PowerShell 및 비즈니스용 Skype Online 소개</span><span class="sxs-lookup"><span data-stu-id="f36db-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [<span data-ttu-id="f36db-136">온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="f36db-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="f36db-137">일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용</span><span class="sxs-lookup"><span data-stu-id="f36db-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="f36db-138">Windows PowerShell 온라인용 비즈니스용 Skype 모듈을 사용하면 Windows PowerShell 온라인 및 비즈니스용 Skype 원격 세션을 만들 수 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f36db-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="f36db-139">64비트 컴퓨터에서만 지원되는 이 모듈은 온라인용 Microsoft 다운로드 센터에서 Windows PowerShell 다운로드할 [비즈니스용 Skype 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="f36db-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
