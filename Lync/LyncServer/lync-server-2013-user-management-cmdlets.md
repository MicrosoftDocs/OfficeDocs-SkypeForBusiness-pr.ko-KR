---
title: 'Lync Server 2013: 사용자 관리 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User management cmdlets
ms:assetid: 85312f3f-28e8-421c-b94c-e6ead1f5f755
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398677(v=OCS.15)
ms:contentKeyID: 48184702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2396cb1a157b88d8beb9458006c1c8a44874dba3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="9f15f-102">Lync Server 2013의 사용자 관리 cmdlet</span><span class="sxs-lookup"><span data-stu-id="9f15f-102">User management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f15f-103">_**마지막으로 수정한 주제:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="9f15f-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="9f15f-104">Microsoft Lync Server 2013에 포함 된 사용자 관리 cmdlet을 사용 하 여 Lync Server 사용자 계정을 설정, 해제, 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f15f-104">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="9f15f-105">사용자 관리 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="9f15f-105">User Management Cmdlets</span></span>

<span data-ttu-id="9f15f-106">사용자 및 사용자 계정에 적용 되는 대부분의 관리 작업은 Lync Server 제어판에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f15f-106">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="9f15f-107">기본 예외는 오디오 회의 공급자를 처리 하는 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="9f15f-107">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="9f15f-108">Lync Server 관리 셸에서 또는 스크립트 내에서 cmdlet을 사용 하 여 사용자 관리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f15f-108">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="9f15f-109">스크립트를 사용 하 여 특정 작업을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f15f-109">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="9f15f-110">다음은 사용자 및 사용자 계정 관리와 직접 관련 된 cmdlet의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9f15f-110">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="9f15f-111">Get-CsAdContact</span><span class="sxs-lookup"><span data-stu-id="9f15f-111">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="9f15f-112">Get-CsAdUser</span><span class="sxs-lookup"><span data-stu-id="9f15f-112">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="9f15f-113">Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="9f15f-113">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="9f15f-114">Get-CsEffectivePolicy</span><span class="sxs-lookup"><span data-stu-id="9f15f-114">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="9f15f-115">CsUcsRollback-호출</span><span class="sxs-lookup"><span data-stu-id="9f15f-115">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="9f15f-116">디버그-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="9f15f-116">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="9f15f-117">Test-CsUnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="9f15f-117">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="9f15f-118">-CsUser 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="9f15f-118">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="9f15f-119">사용-CsUser</span><span class="sxs-lookup"><span data-stu-id="9f15f-119">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="9f15f-120">Get-CsUser</span><span class="sxs-lookup"><span data-stu-id="9f15f-120">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="9f15f-121">CsUser 이동</span><span class="sxs-lookup"><span data-stu-id="9f15f-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="9f15f-122">집합-CsUser</span><span class="sxs-lookup"><span data-stu-id="9f15f-122">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="9f15f-123">Get-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="9f15f-123">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="9f15f-124">제거-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="9f15f-124">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="9f15f-125">Set-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="9f15f-125">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="9f15f-126">Test-CsAudioConferencingProvider</span><span class="sxs-lookup"><span data-stu-id="9f15f-126">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="9f15f-127">Get-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="9f15f-127">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="9f15f-128">Get-Csuser서비스 정책</span><span class="sxs-lookup"><span data-stu-id="9f15f-128">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="9f15f-129">부여-Csuser서비스 정책</span><span class="sxs-lookup"><span data-stu-id="9f15f-129">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="9f15f-130">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="9f15f-130">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="9f15f-131">-Csuser서비스 정책 제거</span><span class="sxs-lookup"><span data-stu-id="9f15f-131">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="9f15f-132">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="9f15f-132">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9f15f-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f15f-133">See Also</span></span>


[<span data-ttu-id="9f15f-134">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="9f15f-134">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

