---
title: 비즈니스용 Skype 서버에서 새 보관 정책 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: '요약: 비즈니스용 Skype 서버에 대한 새 보관 정책을 만드는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: fe3a80708d3810a085f1814e6d16ff3cd4c6057c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095422"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="3b071-103">비즈니스용 Skype 서버에서 새 보관 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3b071-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="3b071-104">**요약:** 비즈니스용 Skype 서버에 대한 새 보관 정책을 만드는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="3b071-105">제어판을 사용하거나 cmdlet을 사용하여 새 보관 정책을 만들 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="3b071-106">제어판을 사용하여 새 보관 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3b071-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="3b071-107">제어판을 사용하여 새 보관 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="3b071-108">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="3b071-109">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3b071-110">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="3b071-111">**다음** 을 클릭하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="3b071-112">사이트 수준 보관 정책을 만들려면 사이트 정책을 클릭한 다음 사이트 선택에서 정책을 적용할 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="3b071-113">사용자 수준의 보관 정책을 만들려면 **사용자 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="3b071-114">**새 보관 정책** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="3b071-115">**이름** 에 새 정책의 이름을 지정합니다(예: externalContoso).</span><span class="sxs-lookup"><span data-stu-id="3b071-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="3b071-116">**설명** 에 정책에 대한 자세한 설명을 입력합니다(예: Contoso용 외부 사용자 보관 정책).</span><span class="sxs-lookup"><span data-stu-id="3b071-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="3b071-117">내부 사용자와의 통신 내용의 보관을 제어하려면 **내부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="3b071-118">외부 사용자와의 통신 내용의 보관을 제어하려면 **외부 통신 보관** 확인란을 선택하거나 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="3b071-119">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3b071-120">사용자 정책 설정은 관리자가 정책을 적용한 특정 사용자 및 사용자 그룹에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="3b071-121">자세한 내용은 비즈니스용 Skype 서버에서 사용자에게 보관 정책 [적용을 참조하세요.](apply-a-policy-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="3b071-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="3b071-122">보관 정책을 사용하여 새 보관 정책을 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b071-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="3b071-123">**New-CsArchivingPolicy** cmdlet을 사용하여 새 보관 정책을 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="3b071-124">자세한 내용은 [New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b071-124">For more information, see the help topic for the [New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="3b071-125">사이트 수준에서 새 보관 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="3b071-126">이 명령은 Redmond 사이트에 대한 새로운 보관 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="3b071-127">사용자 수준에서 새 보관 정책을 만들면</span><span class="sxs-lookup"><span data-stu-id="3b071-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="3b071-128">사용자 수준에서 새 보관 정책을 만들 경우 정책을 만들 때 고유한 ID를 지정하기만하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="3b071-129">내부 통신 세션의 보관을 사용할 수 있는 새 보관 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="3b071-130">이전 명령에서는 필수 Identity 매개 변수를 제외하고 어떤 매개 변수도 지정되지 않았기 때문에 새로운 정책이 모든 속성에 대해 기본값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="3b071-131">다른 속성 값을 사용하는 정책을 만들려면 적합한 매개 변수 및 매개 변수 값을 포함하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="3b071-132">예를 들어 다음 명령은 내부 인스턴트 메시징 세션의 보관을 허용하는 보관 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="3b071-133">내부 및 외부 통신 세션 모두의 보관을 사용할 수 있는 새 보관 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="3b071-134">여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-134">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="3b071-135">예를 들어 다음 명령은 내부 및 외부 인스턴트 메시징 세션을 모두 보관하도록 새 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3b071-135">For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```