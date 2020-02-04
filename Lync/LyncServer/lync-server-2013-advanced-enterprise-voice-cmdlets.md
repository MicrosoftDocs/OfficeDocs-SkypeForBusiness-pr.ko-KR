---
title: 'Lync Server 2013: 고급 엔터프라이즈 음성 cmdlet'
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
ms.openlocfilehash: a2eb83fe91f9c1f2cc0a79adc1232a051534e22e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="advanced-enterprise-voice-cmdlets-in-lync-server-2013"></a><span data-ttu-id="e018e-102">Lync Server 2013의 고급 엔터프라이즈 음성 cmdlet</span><span class="sxs-lookup"><span data-stu-id="e018e-102">Advanced Enterprise Voice cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e018e-103">_**마지막으로 수정한 주제:** 2016-04-12_</span><span class="sxs-lookup"><span data-stu-id="e018e-103">_**Topic Last Modified:** 2016-04-12_</span></span>

<span data-ttu-id="e018e-104">조직에서 엔터프라이즈 음성을 구현 하는 경우 사용자 환경과 조직의 효율성을 개선할 수 있는 추가 기능 및 응용 프로그램을 구현 하는 옵션도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e018e-104">When you implement Enterprise Voice in your organization, you also have the option of implementing additional features and applications that can improve the user experience and the efficiency of your organization.</span></span> <span data-ttu-id="e018e-105">이러한 기능에는 통화 허용 제어, 향상 된 9-1-1 (E9-1-1) 비상 통화, 미디어 구성 설정 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e018e-105">These features include call admission control, Enhanced 9-1-1 (E9-1-1) emergency calling, and media configuration settings.</span></span>

<div>

## <a name="advanced-enterprise-voice-cmdlets"></a><span data-ttu-id="e018e-106">고급 엔터프라이즈 음성 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e018e-106">Advanced Enterprise Voice Cmdlets</span></span>

<span data-ttu-id="e018e-107">다음 목록에는 엔터프라이즈 음성 배포의 고급 기능을 관리 하는 데 사용할 수 있는 cmdlet이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e018e-107">The following lists contain cmdlets that allow you to manage advanced features of an Enterprise Voice deployment:</span></span>

<span data-ttu-id="e018e-108">**[Lync Server 2013의 통화 허용 제어 cmdlet](lync-server-2013-call-admission-control-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e018e-108">**[Call admission control cmdlets in Lync Server 2013](lync-server-2013-call-admission-control-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-109">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-109">[Get-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-110">[새로운 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-110">[New-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398175(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-111">[제거-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-111">[Remove-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg398877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-112">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-112">[Set-CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/en-us/library/Gg412863(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-113">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-113">[Get-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg425815(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-114">[새로운 CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-114">[New-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398675(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-115">[제거-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-115">[Remove-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398609(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-116">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-116">[Set-CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/en-us/library/Gg398338(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-117">[새로운 CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-117">[New-CsNetworkBWAlternatePath](https://technet.microsoft.com/en-us/library/Gg398732(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-118">[새-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-118">[New-CsNetworkBWPolicy](https://technet.microsoft.com/en-us/library/Gg412916(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-119">[Get-Set-csnetworkconfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-119">[Get-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-120">[제거-Set-csnetworkconfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-120">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-121">[Set-Set-csnetworkconfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-121">[Set-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-122">[Get-Csnetworkinter국가 경로](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-122">[Get-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg425817(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-123">[새-Csnetworkinter국가 경로](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-123">[New-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398779(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-124">[제거-Csnetworkinter국가 경로](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-124">[Remove-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398743(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-125">[Set-Csnetworkinter국가 경로](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-125">[Set-CsNetworkInterRegionRoute](https://technet.microsoft.com/en-us/library/Gg398410(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-126">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-126">[Get-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg412769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-127">[새로운 CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-127">[New-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398994(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-128">[제거-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-128">[Remove-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398963(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-129">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-129">[Set-CsNetworkInterSitePolicy](https://technet.microsoft.com/en-us/library/Gg398772(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-130">[Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-130">[Get-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398406(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-131">[새-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-131">[New-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg425829(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-132">[CsNetworkRegion 제거](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-132">[Remove-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg398466(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-133">[Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-133">[Set-CsNetworkRegion](https://technet.microsoft.com/en-us/library/Gg413089(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-134">[Get-Csnetwork국가 링크](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-134">[Get-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398972(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-135">[새-Csnetwork국가 링크](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-135">[New-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg398437(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-136">[-Csnetwork국가 링크 제거](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-136">[Remove-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg413012(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-137">[Set-Csnetwork국가 링크](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-137">[Set-CsNetworkRegionLink](https://technet.microsoft.com/en-us/library/Gg412867(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-138">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-138">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-139">[새-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-139">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-140">[CsNetworkSite 사이트 제거](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-140">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-141">[집합-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-141">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-142">[Get-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412825(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-143">[새-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-143">[New-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg398226(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-144">[CsNetworkSubnet 제거](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-144">[Remove-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg425726(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-145">[Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-145">[Set-CsNetworkSubnet](https://technet.microsoft.com/en-us/library/Gg412739(v=OCS.15))</span></span>

<span data-ttu-id="e018e-146">**[Lync Server 2013의 향상 된 9-1-1 cmdlet](lync-server-2013-enhanced-9-1-1-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e018e-146">**[Enhanced 9-1-1 cmdlets in Lync Server 2013](lync-server-2013-enhanced-9-1-1-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-147">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-147">[Get-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg412877(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-148">[제거-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-148">[Remove-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg425810(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-149">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-149">[Set-CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/en-us/library/Gg398620(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-150">[Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-150">[Get-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg398459(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-151">[테스트-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-151">[Test-CsLisCivicAddress](https://technet.microsoft.com/en-us/library/Gg425914(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-152">[Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-152">[Export-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398539(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-153">[가져오기-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-153">[Import-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398380(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-154">[디버그-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-154">[Debug-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398710(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-155">[Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-155">[Test-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398497(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-156">[게시-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-156">[Publish-CsLisConfiguration](https://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-157">[게시 취소-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-157">[Unpublish-CsLisConfiguration](unhttps://technet.microsoft.com/en-us/library/Gg398364(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-158">[Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-158">[Get-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg412834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-159">[제거-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-159">[Remove-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg425722(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-160">[Set-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-160">[Set-CsLisLocation](https://technet.microsoft.com/en-us/library/Gg398757(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-161">[Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-161">[Get-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398820(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-162">[제거-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-162">[Remove-CsLisPort](https://technet.microsoft.com/en-us/library/Gg412899(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-163">[Set-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-163">[Set-CsLisPort](https://technet.microsoft.com/en-us/library/Gg398700(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-164">[Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-164">[Get-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398116(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-165">[제거-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-165">[Remove-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg398904(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-166">[Set-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-166">[Set-CsLisServiceProvider](https://technet.microsoft.com/en-us/library/Gg425911(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-167">[Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-167">[Get-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg398473(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-168">[제거-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-168">[Remove-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg413053(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-169">[Set-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-169">[Set-CsLisSubnet](https://technet.microsoft.com/en-us/library/Gg399016(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-170">[Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-170">[Get-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg425769(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-171">[제거-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-171">[Remove-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg398352(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-172">[Set-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-172">[Set-CsLisSwitch](https://technet.microsoft.com/en-us/library/Gg412823(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-173">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-173">[Get-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398117(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-174">[제거-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-174">[Remove-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg398461(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-175">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-175">[Set-CsLisWirelessAccessPoint](https://technet.microsoft.com/en-us/library/Gg412723(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-176">[Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-176">[Get-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398911(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-177">[허용-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-177">[Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg413049(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-178">[New-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-178">[New-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398231(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-179">[Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-179">[Remove-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg398727(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-180">[Set-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-180">[Set-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg412987(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-181">[Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-181">[Test-CsLocationPolicy](https://technet.microsoft.com/en-us/library/Gg425962(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-182">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-182">[Get-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398766(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-183">[새-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-183">[New-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398365(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-184">[CsNetworkSite 사이트 제거](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-184">[Remove-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398135(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-185">[집합-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-185">[Set-CsNetworkSite](https://technet.microsoft.com/en-us/library/Gg398295(v=OCS.15))</span></span>

<span data-ttu-id="e018e-186">**[SLA (공유 선 모양) cmdlet](shared-line-appearance-sla-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e018e-186">**[Shared Line Appearance (SLA) cmdlets](shared-line-appearance-sla-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-187">[Get-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703200(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-187">[Get-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703200(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-188">[Set-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703202(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-188">[Set-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703202(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-189">[제거-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703201(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-189">[Remove-CsSlaConfiguration](https://technet.microsoft.com/en-us/library/Mt703201(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-190">[추가-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703199(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-190">[Add-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703199(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-191">[제거-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703203(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-191">[Remove-CsSlaDelegates](https://technet.microsoft.com/en-us/library/Mt703203(v=OCS.15))</span></span>

<span data-ttu-id="e018e-192">**[Lync Server 2013의 미디어 바이패스 cmdlet](lync-server-2013-media-bypass-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e018e-192">**[Media bypass cmdlets in Lync Server 2013](lync-server-2013-media-bypass-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-193">[새-Csnetworkmediabyp을 구성 합니다.](https://technet.microsoft.com/en-us/library/Gg425718(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-193">[New-CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/en-us/library/Gg425718(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="e018e-194">[Get-Set-csnetworkconfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-194">[Get-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398140(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-195">[제거-Set-csnetworkconfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-195">[Remove-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398938(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-196">[Set-Set-csnetworkconfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-196">[Set-CsNetworkConfiguration](https://technet.microsoft.com/en-us/library/Gg398927(v=OCS.15))</span></span>

<span data-ttu-id="e018e-197">**[Lync Server 2013의 미디어 구성 cmdlet](lync-server-2013-media-configuration-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="e018e-197">**[Media configuration cmdlets in Lync Server 2013](lync-server-2013-media-configuration-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-198">[Get-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-198">[Get-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398128(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-199">[새로운 CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg425881(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-199">[New-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg425881(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-200">[제거-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398705(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-200">[Remove-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398705(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="e018e-201">[Set-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398580(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="e018e-201">[Set-CsMediaConfiguration](https://technet.microsoft.com/en-us/library/Gg398580(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e018e-202">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e018e-202">See Also</span></span>


[<span data-ttu-id="e018e-203">Lync Server 2013의 엔터프라이즈 음성 cmdlet</span><span class="sxs-lookup"><span data-stu-id="e018e-203">Enterprise Voice cmdlets in Lync Server 2013</span></span>](lync-server-2013-enterprise-voice-cmdlets.md)  


[<span data-ttu-id="e018e-204">Lync Server PowerShell 블로그</span><span class="sxs-lookup"><span data-stu-id="e018e-204">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

