---
title: 'Lync Server 2013: IM 및 현재 상태 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence cmdlets
ms:assetid: 7b882480-f3d5-44a2-bb75-fffb7e5caede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398611(v=OCS.15)
ms:contentKeyID: 48184589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17a99610f003d3ca74d1dfb9d1df1ac048aed517
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526735"
---
# <a name="im-and-presence-cmdlets-in-lync-server-2013"></a><span data-ttu-id="ecd33-102">Lync Server 2013의 IM 및 현재 상태 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ecd33-102">IM and presence cmdlets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ecd33-103">_**마지막으로 수정 된 항목:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="ecd33-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="ecd33-104">IM (인스턴트 메시징) 및 현재 상태 cmdlet을 사용 하면 Windows PowerShell을 통해 이러한 클라이언트 기능을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecd33-104">Instant Messaging (IM) and presence cmdlets allow you to manage those client features through Windows PowerShell.</span></span> <span data-ttu-id="ecd33-105">전역, 사이트 또는 사용자별 범위에서 사용자에게 적용되는 현재 상태 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecd33-105">You can set presence policies that apply to users at the global, site, or per-user scope.</span></span> <span data-ttu-id="ecd33-106">또한 다양한 개인 정보 및 IM 기능을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecd33-106">You can also configure various privacy and IM features.</span></span>

<div>

## <a name="im-and-presence-cmdlets"></a><span data-ttu-id="ecd33-107">IM 및 현재 상태 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ecd33-107">IM and Presence Cmdlets</span></span>

<span data-ttu-id="ecd33-108">IM 및 현재 상태를 구성하려면 다음 cmdlet를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ecd33-108">The configure IM and presence, use the following cmdlets:</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-109">[Get-cspresencepolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-109">[Get-CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-110">[Get-cspresencepolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-110">[Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-111">[Get-cspresencepolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-111">[New-CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-112">[Get-cspresencepolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg399070(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-112">[Remove-CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-113">[Get-cspresencepolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-113">[Set-CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="ecd33-114">[Remove-cspresenceprovider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-114">[Get-CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))</span></span>

  - <span data-ttu-id="ecd33-115">[Remove-cspresenceprovider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-115">[New-CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))</span></span>

  - <span data-ttu-id="ecd33-116">[Remove-cspresenceprovider을 제거 합니다.](https://technet.microsoft.com/library/JJ205036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-116">[Remove-CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))</span></span>

  - <span data-ttu-id="ecd33-117">[Remove-cspresenceprovider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-117">[Set-CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecd33-118">[Get-csprivacyconfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-118">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-119">[Get-csprivacyconfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-119">[New-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-120">[Get-csprivacyconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-120">[Remove-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-121">[Get-csprivacyconfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-121">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecd33-122">[설정-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-122">[Set-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecd33-123">[Get-Csuser서비스 구성](https://technet.microsoft.com/library/Gg398133(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-123">[Get-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-124">[새-Csuser서비스 구성](https://technet.microsoft.com/library/Gg412926(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-124">[New-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-125">[Csuser서비스 구성 제거](https://technet.microsoft.com/library/Gg398722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-125">[Remove-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-126">[Csuser서비스 구성](https://technet.microsoft.com/library/Gg398340(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-126">[Set-CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecd33-127">[CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-127">[Get-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-128">[CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-128">[New-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-129">[CsFileTransferFilterConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg413064(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-129">[Remove-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-130">[CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-130">[Set-CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecd33-131">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-131">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-132">[새-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-132">[New-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-133">[제거-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-133">[Remove-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ecd33-134">[Set-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-134">[Set-CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecd33-135">[테스트-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-135">[Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecd33-136">[테스트-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-136">[Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecd33-137">[Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-137">[Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecd33-138">[Test-csp2pav](https://technet.microsoft.com/library/Gg412821(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-138">[Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ecd33-139">[테스트-cspres](https://technet.microsoft.com/library/Gg398148(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ecd33-139">[Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ecd33-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ecd33-140">See Also</span></span>


[<span data-ttu-id="ecd33-141">Lync Server 2013의 클라이언트 관리 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ecd33-141">Client management cmdlets in Lync Server 2013</span></span>](lync-server-2013-client-management-cmdlets.md)  


[<span data-ttu-id="ecd33-142">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="ecd33-142">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

