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
ms.openlocfilehash: 4a672eea92c820970b3cc4cc1c112c15fcffd641
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="83426-102">Lync Server 2013의 사용자 관리 cmdlet</span><span class="sxs-lookup"><span data-stu-id="83426-102">User management cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83426-103">_**마지막으로 수정 된 항목:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="83426-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="83426-104">Microsoft Lync Server 2013에 포함 된 사용자 관리 cmdlet은 Lync Server 사용자 계정을 사용 하거나 사용 하지 않도록 설정 하 고 수정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="83426-104">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="83426-105">사용자 관리 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="83426-105">User Management Cmdlets</span></span>

<span data-ttu-id="83426-106">사용자 및 사용자 계정에 적용 되는 대부분의 관리 작업은 Lync Server 제어판에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83426-106">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="83426-107">주된 예외는 오디오 회의 공급자를 처리하는 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="83426-107">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="83426-108">사용자 관리 작업은 Lync Server 관리 셸 또는 스크립트 내에서 cmdlet을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83426-108">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="83426-109">스크립트를 사용하는 경우 특정 작업을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83426-109">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="83426-110">다음은 사용자 및 사용자 계정 관리에 직접적으로 관련된 cmdlet 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="83426-110">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="83426-111">Get-CsAdContact</span><span class="sxs-lookup"><span data-stu-id="83426-111">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="83426-112">Get-CsAdUser</span><span class="sxs-lookup"><span data-stu-id="83426-112">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="83426-113">Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="83426-113">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="83426-114">Get-cseffectivepolicy</span><span class="sxs-lookup"><span data-stu-id="83426-114">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="83426-115">Invoke-csucsrollback-를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="83426-115">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="83426-116">Test-csunifiedcontactstore</span><span class="sxs-lookup"><span data-stu-id="83426-116">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="83426-117">Test-csunifiedcontactstore</span><span class="sxs-lookup"><span data-stu-id="83426-117">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="83426-118">사용 안 함-CsUser</span><span class="sxs-lookup"><span data-stu-id="83426-118">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="83426-119">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="83426-119">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="83426-120">Get-CsUser</span><span class="sxs-lookup"><span data-stu-id="83426-120">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="83426-121">CsUser 이동</span><span class="sxs-lookup"><span data-stu-id="83426-121">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="83426-122">설정-CsUser</span><span class="sxs-lookup"><span data-stu-id="83426-122">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="83426-123">Get-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="83426-123">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="83426-124">제거-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="83426-124">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="83426-125">설정-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="83426-125">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="83426-126">Test-csaudioconferencingprovider</span><span class="sxs-lookup"><span data-stu-id="83426-126">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="83426-127">Get-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="83426-127">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="83426-128">Get-Csuser서비스 정책</span><span class="sxs-lookup"><span data-stu-id="83426-128">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="83426-129">부여-Csuser서비스 정책</span><span class="sxs-lookup"><span data-stu-id="83426-129">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="83426-130">새-Csuser서비스 정책</span><span class="sxs-lookup"><span data-stu-id="83426-130">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="83426-131">Csuser서비스 정책 제거</span><span class="sxs-lookup"><span data-stu-id="83426-131">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="83426-132">설정-Csuser서비스 정책</span><span class="sxs-lookup"><span data-stu-id="83426-132">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="83426-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83426-133">See Also</span></span>


[<span data-ttu-id="83426-134">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="83426-134">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

