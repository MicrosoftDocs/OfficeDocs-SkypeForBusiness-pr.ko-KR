---
title: 'Lync Server 2013: 향상 된 9-1-1 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enhanced 9-1-1 cmdlets
ms:assetid: e560c688-7b34-4bd7-8104-24f390644105
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415678(v=OCS.15)
ms:contentKeyID: 48185650
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59b626f05bdbb2d8a93f23f2f5afdb3cc03e07b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-cmdlets-in-lync-server-2013"></a><span data-ttu-id="ae4f4-102">Lync Server 2013의 향상 된 9-1-1 cmdlet</span><span class="sxs-lookup"><span data-stu-id="ae4f4-102">Enhanced 9-1-1 cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae4f4-103">_**마지막으로 수정한 주제:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="ae4f4-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="ae4f4-104">Microsoft Lync Server 2013에는 엔터프라이즈 음성 솔루션의 향상 된 9-1-1 (E9-1) 구현을 구현 하 고 관리 하는 데 사용할 수 있는 cmdlet이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f4-104">Microsoft Lync Server 2013 ships with cmdlets that allow you to implement and manage the Enhanced 9-1-1 (E9-1-1) implementation of an Enterprise Voice solution.</span></span> <span data-ttu-id="ae4f4-105">이러한 cmdlet을 사용 하 여 연결 지점을 실제 주소로 매핑하고 엔터프라이즈 음성 사용자에 게 긴급 통화를 성공적으로 완료 하는 데 필요한 설정을 구성 하 고 비상 서비스 공급자에 게 자동으로 위치를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f4-105">Use these cmdlets to map connection points to physical addresses and to configure settings required for Enterprise Voice users to successfully complete emergency calls and automatically send a location to the emergency services provider.</span></span> <span data-ttu-id="ae4f4-106">Lync Server 제어판의 E9-1-1을 구성할 수 없습니다. cmdlet을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae4f4-106">You cannot configure E9-1-1 from the Lync Server Control Panel, you must use cmdlets.</span></span>

<div>

## <a name="enhanced-9-1-1-cmdlets"></a><span data-ttu-id="ae4f4-107">향상 된 9-1-1 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ae4f4-107">Enhanced 9-1-1 Cmdlets</span></span>

<span data-ttu-id="ae4f4-108">다음 cmdlet을 사용 하 여 E9를 구성 합니다-1-1</span><span class="sxs-lookup"><span data-stu-id="ae4f4-108">Use the following cmdlets to configure E9-1-1.</span></span>

<span data-ttu-id="ae4f4-109">**향상 된 9-1-1**</span><span class="sxs-lookup"><span data-stu-id="ae4f4-109">**Enhanced 9-1-1**</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-110">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-110">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-111">[제거-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-111">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-112">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-112">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ae4f4-113">[Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-113">[Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-114">[테스트-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-114">[Test-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ae4f4-115">[Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-115">[Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-116">[가져오기-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-116">[Import-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-117">[디버그-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-117">[Debug-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-118">[Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-118">[Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-119">[게시-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-119">[Publish-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-120">[게시 취소-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-120">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ae4f4-121">[Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-121">[Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-122">[제거-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-122">[Remove-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-123">[Set-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-123">[Set-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ae4f4-124">[Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-124">[Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-125">[제거-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-125">[Remove-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-126">[Set-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-126">[Set-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ae4f4-127">[Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-127">[Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-128">[제거-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-128">[Remove-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-129">[Set-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-129">[Set-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ae4f4-130">[Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-130">[Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-131">[제거-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-131">[Remove-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-132">[Set-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-132">[Set-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ae4f4-133">[Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-133">[Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-134">[제거-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-134">[Remove-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-135">[Set-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-135">[Set-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ae4f4-136">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-136">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-137">[제거-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-137">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-138">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-138">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ae4f4-139">[Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-139">[Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-140">[허용-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-140">[Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-141">[New-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-141">[New-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-142">[Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-142">[Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-143">[Set-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-143">[Set-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-144">[Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-144">[Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ae4f4-145">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-145">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-146">[새-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-146">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-147">[CsNetworkSite 사이트 제거](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-147">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ae4f4-148">[집합-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ae4f4-148">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ae4f4-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae4f4-149">See Also</span></span>


[<span data-ttu-id="ae4f4-150">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="ae4f4-150">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

