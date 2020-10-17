---
title: 'Lync Server 2013: 사용자 관리 cmdlet'
description: 'Lync Server 2013: 사용자 관리 cmdlet'
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
ms.openlocfilehash: b94f2b48017fd29fa7a5a814da8a3c80d8f57968
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569784"
---
# <a name="user-management-cmdlets-in-lync-server-2013"></a><span data-ttu-id="095ac-103">Lync Server 2013의 사용자 관리 cmdlet</span><span class="sxs-lookup"><span data-stu-id="095ac-103">User management cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="095ac-104">_**마지막으로 수정 된 항목:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="095ac-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="095ac-105">Microsoft Lync Server 2013에 포함 된 사용자 관리 cmdlet은 Lync Server 사용자 계정을 사용 하거나 사용 하지 않도록 설정 하 고 수정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="095ac-105">The user management cmdlets included in Microsoft Lync Server 2013 allow you to enable, disable, and modify Lync Server user accounts.</span></span>

<div>

## <a name="user-management-cmdlets"></a><span data-ttu-id="095ac-106">사용자 관리 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="095ac-106">User Management Cmdlets</span></span>

<span data-ttu-id="095ac-107">사용자 및 사용자 계정에 적용 되는 대부분의 관리 작업은 Lync Server 제어판에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="095ac-107">Most management tasks that apply to users and user accounts can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="095ac-108">주된 예외는 오디오 회의 공급자를 처리하는 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="095ac-108">The primary exceptions are the cmdlets that deal with audio conferencing providers.</span></span> <span data-ttu-id="095ac-109">사용자 관리 작업은 Lync Server 관리 셸 또는 스크립트 내에서 cmdlet을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="095ac-109">User management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script.</span></span> <span data-ttu-id="095ac-110">스크립트를 사용하는 경우 특정 작업을 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="095ac-110">By using a script, you can automate certain tasks.</span></span> <span data-ttu-id="095ac-111">다음은 사용자 및 사용자 계정 관리에 직접적으로 관련된 cmdlet 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="095ac-111">The following is a list of cmdlets that relate directly to managing users and user accounts:</span></span>

  - <span></span>  
    [<span data-ttu-id="095ac-112">Get-CsAdContact</span><span class="sxs-lookup"><span data-stu-id="095ac-112">Get-CsAdContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdContact)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="095ac-113">Get-CsAdUser</span><span class="sxs-lookup"><span data-stu-id="095ac-113">Get-CsAdUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAdUser)

<!-- end list -->

  - [<span data-ttu-id="095ac-114">Get-CsClientAccessLicense</span><span class="sxs-lookup"><span data-stu-id="095ac-114">Get-CsClientAccessLicense</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsClientAccessLicense)

<!-- end list -->

  - [<span data-ttu-id="095ac-115">Get-cseffectivepolicy</span><span class="sxs-lookup"><span data-stu-id="095ac-115">Get-CsEffectivePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsEffectivePolicy)

<!-- end list -->

  - [<span data-ttu-id="095ac-116">Invoke-csucsrollback-를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="095ac-116">Invoke-CsUcsRollback</span></span>](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback)

<!-- end list -->

  - [<span data-ttu-id="095ac-117">Test-csunifiedcontactstore</span><span class="sxs-lookup"><span data-stu-id="095ac-117">Debug-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Debug-CsUnifiedContactStore)

  - [<span data-ttu-id="095ac-118">Test-csunifiedcontactstore</span><span class="sxs-lookup"><span data-stu-id="095ac-118">Test-CsUnifiedContactStore</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="095ac-119">사용 안 함-CsUser</span><span class="sxs-lookup"><span data-stu-id="095ac-119">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)

  - <span></span>  
    [<span data-ttu-id="095ac-120">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="095ac-120">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Enable-CsUser)

  - <span></span>  
    [<span data-ttu-id="095ac-121">Get-CsUser</span><span class="sxs-lookup"><span data-stu-id="095ac-121">Get-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)

  - <span></span>  
    [<span data-ttu-id="095ac-122">CsUser 이동</span><span class="sxs-lookup"><span data-stu-id="095ac-122">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Move-CsUser)

  - <span></span>  
    [<span data-ttu-id="095ac-123">설정-CsUser</span><span class="sxs-lookup"><span data-stu-id="095ac-123">Set-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUser)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="095ac-124">Get-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="095ac-124">Get-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="095ac-125">제거-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="095ac-125">Remove-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="095ac-126">설정-CsUserAcp</span><span class="sxs-lookup"><span data-stu-id="095ac-126">Set-CsUserAcp</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp)

  - <span></span>  
    [<span data-ttu-id="095ac-127">Test-csaudioconferencingprovider</span><span class="sxs-lookup"><span data-stu-id="095ac-127">Test-CsAudioConferencingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAudioConferencingProvider)

<!-- end list -->

  - <span></span>  
    [<span data-ttu-id="095ac-128">Get-CsUserPoolInfo</span><span class="sxs-lookup"><span data-stu-id="095ac-128">Get-CsUserPoolInfo</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserPoolInfo)

<!-- end list -->

  - [<span data-ttu-id="095ac-129">Get-Csuser서비스 정책</span><span class="sxs-lookup"><span data-stu-id="095ac-129">Get-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserServicesPolicy)

  - [<span data-ttu-id="095ac-130">부여-Csuser서비스 정책</span><span class="sxs-lookup"><span data-stu-id="095ac-130">Grant-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsUserServicesPolicy)

  - [<span data-ttu-id="095ac-131">새-Csuser서비스 정책</span><span class="sxs-lookup"><span data-stu-id="095ac-131">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)

  - [<span data-ttu-id="095ac-132">Csuser서비스 정책 제거</span><span class="sxs-lookup"><span data-stu-id="095ac-132">Remove-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsUserServicesPolicy)

  - [<span data-ttu-id="095ac-133">설정-Csuser서비스 정책</span><span class="sxs-lookup"><span data-stu-id="095ac-133">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="095ac-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="095ac-134">See Also</span></span>


[<span data-ttu-id="095ac-135">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="095ac-135">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

