---
title: 'Lync Server 2013: 고급 Enterprise Voice cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Advanced Enterprise Voice cmdlets
ms:assetid: 247179fb-1c66-4edb-8401-1c1aad189062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415637(v=OCS.15)
ms:contentKeyID: 48183637
ms.date: 04/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec794a0aceb4e0eade260a99337f1eb62e41470f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="advanced-enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="ca200-102">Lync Server 2013의 고급 Enterprise Voice cmdlet</span><span class="sxs-lookup"><span data-stu-id="ca200-102">Advanced Enterprise Voice cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca200-103">_**마지막으로 수정 된 항목:** 2016-04-12_</span><span class="sxs-lookup"><span data-stu-id="ca200-103">_**Topic Last Modified:** 2016-04-12_</span></span>

<span data-ttu-id="ca200-104">조직에서 Enterprise Voice를 구현 하는 경우 사용자 환경 및 조직의 효율성을 향상 시킬 수 있는 추가 기능 및 응용 프로그램을 구현 하는 옵션도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca200-104">When you implement Enterprise Voice in your organization, you also have the option of implementing additional features and applications that can improve the user experience and the efficiency of your organization.</span></span> <span data-ttu-id="ca200-105">이러한 기능에는 통화 허용 제어, 향상 된 9-1-1 (E9-1-1) 긴급 통화 및 미디어 구성 설정이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca200-105">These features include call admission control, Enhanced 9-1-1 (E9-1-1) emergency calling, and media configuration settings.</span></span>

<div>

## <a name="advanced-enterprise-voice-cmdlets"></a><span data-ttu-id="ca200-106">고급 Enterprise Voice Cmdlet</span><span class="sxs-lookup"><span data-stu-id="ca200-106">Advanced Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="ca200-107">다음 목록에는 Enterprise Voice 배포의 고급 기능을 관리 하는 데 사용할 수 있는 cmdlet이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca200-107">The following lists contain cmdlets that allow you to manage advanced features of an Enterprise Voice deployment:</span></span>

<span data-ttu-id="ca200-108">**[Lync Server 2013의 통화 허용 제어 cmdlet](lync-server-2013-call-admission-control-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="ca200-108">**[Call admission control cmdlets in Lync Server 2013](lync-server-2013-call-admission-control-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-109">[CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-109">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-110">[CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-110">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-111">[CsBandwidthPolicyServiceConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-111">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-112">[CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-112">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-113">[Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-113">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-114">[Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-114">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-115">[Get-csnetworkbandwidthpolicyprofile을 제거 합니다.](https://technet.microsoft.com/library/Gg398609(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-115">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-116">[Get-csnetworkbandwidthpolicyprofile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-116">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-117">[CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-117">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-118">[새-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-118">[New-CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-119">[Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-119">[Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-120">[Get-csnetworkconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-120">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-121">[Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-121">[Set-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-122">[Get-Csnetworkinterroute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-122">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-123">[새-Csnetworkinterroute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-123">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-124">[제거-Csnetworkinterroute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-124">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-125">[설정-Csnetworkinter지역 경로](https://technet.microsoft.com/library/Gg398410(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-125">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-126">[Remove-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-126">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-127">[Remove-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-127">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-128">[Remove-csnetworkintersitepolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg398963(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-128">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-129">[Remove-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-129">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-130">[Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-130">[Get-CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-131">[새-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-131">[New-CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-132">[CsNetworkRegion 제거](https://technet.microsoft.com/library/Gg398466(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-132">[Remove-CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-133">[설정-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-133">[Set-CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-134">[Get-Csnetwork지역 링크](https://technet.microsoft.com/library/Gg398972(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-134">[Get-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-135">[새-Csnetwork지역 링크](https://technet.microsoft.com/library/Gg398437(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-135">[New-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-136">[-Csnetwork지역 링크 제거](https://technet.microsoft.com/library/Gg413012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-136">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-137">[설정-Csnetwork지역 링크](https://technet.microsoft.com/library/Gg412867(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-137">[Set-CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-138">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-138">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-139">[새-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-139">[New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-140">[CsNetworkSite를 제거 합니다.](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-140">[Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-141">[설정-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-141">[Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-143">[새-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-143">[New-CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-144">[제거-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-144">[Remove-CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-145">[설정-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-145">[Set-CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))</span></span>

<span data-ttu-id="ca200-146">**[Lync Server 2013의 향상 된 9-1-1 cmdlet](lync-server-2013-enhanced-9-1-1-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="ca200-146">**[Enhanced 9-1-1 cmdlets in Lync Server 2013](lync-server-2013-enhanced-9-1-1-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-147">[CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-147">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-148">[CsEnhancedEmergencyServiceDisclaimer을 제거 합니다.](https://technet.microsoft.com/library/Gg425810(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-148">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-149">[CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-149">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-150">[Test-csliscivicaddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-150">[Get-CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-151">[Test-csliscivicaddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-151">[Test-CsLisCivicAddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-152">[Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-152">[Export-CsLisConfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-153">[Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-153">[Import-CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-154">[Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-154">[Debug-CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-155">[Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-155">[Test-CsLisConfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-156">[게시-Export-cslisconfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-156">[Publish-CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-157">[게시 취소-Export-cslisconfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-157">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-158">[Get-cslislocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-158">[Get-CsLisLocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-159">[Get-cslislocation을 제거 합니다.](https://technet.microsoft.com/library/Gg425722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-159">[Remove-CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-160">[Get-cslislocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-160">[Set-CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-161">[CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-161">[Get-CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-162">[CsLisPort을 제거 합니다.](https://technet.microsoft.com/library/Gg412899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-162">[Remove-CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-163">[CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-163">[Set-CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-164">[CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-164">[Get-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-165">[CsLisServiceProvider을 제거 합니다.](https://technet.microsoft.com/library/Gg398904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-165">[Remove-CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-166">[CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-166">[Set-CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-167">[CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-167">[Get-CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-168">[CsLisSubnet을 제거 합니다.](https://technet.microsoft.com/library/Gg413053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-168">[Remove-CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-169">[CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-169">[Set-CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-170">[CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-170">[Get-CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-171">[CsLisSwitch을 제거 합니다.](https://technet.microsoft.com/library/Gg398352(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-171">[Remove-CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-172">[CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-172">[Set-CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-173">[CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-173">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-174">[CsLisWirelessAccessPoint을 제거 합니다.](https://technet.microsoft.com/library/Gg398461(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-174">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-175">[CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-175">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-176">[Get-CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-176">[Get-CsLocationPolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-177">[부여-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-177">[Grant-CsLocationPolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-178">[새-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-178">[New-CsLocationPolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-179">[제거-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-179">[Remove-CsLocationPolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-180">[설정-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-180">[Set-CsLocationPolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-181">[테스트-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-181">[Test-CsLocationPolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-182">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-182">[Get-CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-183">[새-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-183">[New-CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-184">[CsNetworkSite를 제거 합니다.](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-184">[Remove-CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-185">[설정-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-185">[Set-CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))</span></span>

<span data-ttu-id="ca200-186">**[SLA (공유 선 모양) cmdlet](shared-line-appearance-sla-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="ca200-186">**[Shared Line Appearance (SLA) cmdlets](shared-line-appearance-sla-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-187">[CsSlaConfiguration](https://technet.microsoft.com/library/Mt703200(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-187">[Get-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703200(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-188">[CsSlaConfiguration](https://technet.microsoft.com/library/Mt703202(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-188">[Set-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703202(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-189">[CsSlaConfiguration을 제거 합니다.](https://technet.microsoft.com/library/Mt703201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-189">[Remove-CsSlaConfiguration](https://technet.microsoft.com/library/Mt703201(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-190">[CsSlaDelegates 추가](https://technet.microsoft.com/library/Mt703199(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-190">[Add-CsSlaDelegates](https://technet.microsoft.com/library/Mt703199(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-191">[CsSlaDelegates을 제거 합니다.](https://technet.microsoft.com/library/Mt703203(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-191">[Remove-CsSlaDelegates](https://technet.microsoft.com/library/Mt703203(v=OCS.15))</span></span>

<span data-ttu-id="ca200-192">**[Lync Server 2013의 미디어 바이패스 cmdlet](lync-server-2013-media-bypass-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="ca200-192">**[Media bypass cmdlets in Lync Server 2013](lync-server-2013-media-bypass-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-193">[새-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-193">[New-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="ca200-194">[Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-194">[Get-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-195">[Get-csnetworkconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-195">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-196">[Get-csnetworkconfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-196">[Set-CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))</span></span>

<span data-ttu-id="ca200-197">**[Lync Server 2013의 미디어 구성 cmdlet](lync-server-2013-media-configuration-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="ca200-197">**[Media configuration cmdlets in Lync Server 2013](lync-server-2013-media-configuration-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-198">[Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg398128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-198">[Get-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398128(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-199">[Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg425881(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-199">[New-CsMediaConfiguration](https://technet.microsoft.com/library/Gg425881(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-200">[Get-csmediaconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-200">[Remove-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398705(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="ca200-201">[Get-csmediaconfiguration](https://technet.microsoft.com/library/Gg398580(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="ca200-201">[Set-CsMediaConfiguration](https://technet.microsoft.com/library/Gg398580(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca200-202">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca200-202">See Also</span></span>


[<span data-ttu-id="ca200-203">Lync Server 2013의 Enterprise Voice cmdlet</span><span class="sxs-lookup"><span data-stu-id="ca200-203">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="ca200-204">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="ca200-204">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

