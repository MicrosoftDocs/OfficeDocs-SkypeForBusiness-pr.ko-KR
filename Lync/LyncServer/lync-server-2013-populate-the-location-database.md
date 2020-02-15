---
title: 'Lync Server 2013: 위치 데이터베이스 채우기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7b443e257ee45c15974ba96a50b8217113ac942
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="5cbd4-102">Lync Server 2013에서 위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="5cbd4-102">Populate the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cbd4-103">_**마지막으로 수정 된 항목:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="5cbd4-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="5cbd4-p101">네트워크에서 클라이언트를 자동으로 찾으려면 먼저 네트워크 요소를 구/군/시 주소로 매핑하는 네트워크 *와이어맵(wiremap)* 으로 위치 데이터베이스를 채워야 합니다. 서브넷, 무선 액세스 지점, 스위치 및 포트를 사용하여 와이어맵(wiremap)을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-p101">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses. You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="5cbd4-106">위치 데이터베이스에는 주소를 개별적으로 추가하거나 다음 표에 설명된 열 형식이 포함된 CSV 파일을 사용하여 일괄적으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="5cbd4-p102">ELIN(Emergency Location Identification Number) 게이트웨이를 사용하는 경우 각 위치의 **CompanyName** 필드에 ELIN을 포함합니다. 각 위치마다 세미콜론으로 구분하여 여러 ELIN을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-p102">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cbd4-109">네트워크 요소</span><span class="sxs-lookup"><span data-stu-id="5cbd4-109">Network Element</span></span></th>
<th><span data-ttu-id="5cbd4-110">필수 열</span><span class="sxs-lookup"><span data-stu-id="5cbd4-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cbd4-111"><strong>무선 액세스 지점</strong></span><span class="sxs-lookup"><span data-stu-id="5cbd4-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="5cbd4-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="5cbd4-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="5cbd4-113">... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;구&gt;/&lt;군&gt;/&lt;시&gt;,&lt;시/도, PostalCode, 국가&gt;</span><span class="sxs-lookup"><span data-stu-id="5cbd4-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cbd4-114"><strong>서브넷</strong></span><span class="sxs-lookup"><span data-stu-id="5cbd4-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="5cbd4-115">&lt;서브넷&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="5cbd4-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="5cbd4-116">... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;구&gt;/&lt;군&gt;/&lt;시&gt;,&lt;시/도, PostalCode, 국가&gt;</span><span class="sxs-lookup"><span data-stu-id="5cbd4-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cbd4-117"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="5cbd4-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="5cbd4-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,...</span><span class="sxs-lookup"><span data-stu-id="5cbd4-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="5cbd4-119">... &lt;Predirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;구&gt;/&lt;군&gt;/&lt;시&gt;,&lt;PostalCode, 국가&gt;</span><span class="sxs-lookup"><span data-stu-id="5cbd4-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cbd4-120"><strong>Switch</strong></span><span class="sxs-lookup"><span data-stu-id="5cbd4-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="5cbd4-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="5cbd4-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="5cbd4-122">... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;구&gt;/&lt;군&gt;/&lt;시&gt;,&lt;시/도, PostalCode, 국가&gt;</span><span class="sxs-lookup"><span data-stu-id="5cbd4-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cbd4-123">위치 정책에서 **위치 필요**가 **예**나 **고지 사항**으로 설정되었을 때 위치 데이터베이스를 채우지 않으면 위치를 수동으로 입력하라는 메시지가 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="5cbd4-124">위치 데이터베이스를 채우는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="5cbd4-125">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="5cbd4-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="5cbd4-126">**CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="5cbd4-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="5cbd4-127">CsLisSubnet을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="5cbd4-128">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="5cbd4-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="5cbd4-129">**CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="5cbd4-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="5cbd4-130">**CsLisWirelessAccessPoint을 제거 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cbd4-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="5cbd4-131">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="5cbd4-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="5cbd4-132">**CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="5cbd4-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="5cbd4-133">**CsLisSwitch을 제거 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cbd4-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="5cbd4-134">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="5cbd4-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="5cbd4-135">**CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="5cbd4-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="5cbd4-136">**CsLisPort을 제거 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5cbd4-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="5cbd4-137">위치 데이터베이스에 네트워크 요소를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="5cbd4-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="5cbd4-138">다음 cmdlet를 실행하여 위치 데이터베이스에 서브넷 위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="5cbd4-p103">ELIN 게이트웨이의 경우, CompanyName 필드에 ELIN을 추가합니다. 두 개 이상의 ELIN을 포함할 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-p103">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="5cbd4-142">또는 다음 cmdlet를 실행하고 'subnets.csv' 파일을 사용하여 서브넷 위치를 일괄적으로 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="5cbd4-143">다음 cmdlet를 실행하여 위치 데이터베이스에 무선 위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="5cbd4-144">또는 다음 cmdlet를 실행하고 csv 파일 ‘waps.csv’를 사용하여 무선 위치를 일괄적으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="5cbd4-145">다음 cmdlet를 실행하여 위치 데이터베이스에 스위치 위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="5cbd4-146">또는 다음 cmdlet를 실행하고 csv 파일 ‘switches.csv’를 사용하여 스위치 위치를 일괄적으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="5cbd4-147">다음 cmdlet를 실행하여 위치 데이터베이스에 포트 위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="5cbd4-p104">PortIDSubType의 기본값은 LocallyAssigned이며, 이 값을 InterfaceAlias 또는 InterfaceName으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-p104">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="5cbd4-150">또는 다음 cmdlet를 실행하고 'ports.csv' 파일을 사용하여 포트 위치를 일괄적으로 업데이트할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbd4-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

