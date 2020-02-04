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
ms.openlocfilehash: a93cee85afec1e3943af692d598d0d02ab678d58
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="56913-102">Lync Server 2013에서 위치 데이터베이스 채우기</span><span class="sxs-lookup"><span data-stu-id="56913-102">Populate the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56913-103">_**마지막으로 수정한 주제:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="56913-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="56913-104">네트워크 내에서 클라이언트를 자동으로 찾으려면 먼저 네트워크 요소를 도시 (즉, 거리) 주소로 매핑하는 network *wiremap 매핑*으로 위치 데이터베이스를 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-104">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses.</span></span> <span data-ttu-id="56913-105">서브넷, 무선 액세스 지점, 스위치 및 포트를 사용 하 여 wiremap 매핑 정의를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-105">You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="56913-106">다음 표에 설명 된 열 서식이 포함 된 CSV 파일을 사용 하 여 위치 데이터베이스에 개별적으로 또는 대량으로 주소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="56913-107">비상 위치 Id 번호 (ELIN) 게이트웨이를 사용 하는 경우 각 위치에 대 한 **CompanyName** 필드에 elin을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-107">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location.</span></span> <span data-ttu-id="56913-108">각각 세미콜론으로 구분 하 여 각 위치에 여러 개의 ELINs을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-108">You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56913-109">네트워크 요소</span><span class="sxs-lookup"><span data-stu-id="56913-109">Network Element</span></span></th>
<th><span data-ttu-id="56913-110">필수 열</span><span class="sxs-lookup"><span data-stu-id="56913-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56913-111"><strong>무선 액세스 지점의</strong></span><span class="sxs-lookup"><span data-stu-id="56913-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="56913-112">&lt;BSSID&gt;,&lt;설명&gt;,&lt;위치&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="56913-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="56913-113">... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;시&gt;,&lt;주&gt;,&lt;우편&gt;,&lt;국가&gt;</span><span class="sxs-lookup"><span data-stu-id="56913-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56913-114"><strong>서브넷</strong></span><span class="sxs-lookup"><span data-stu-id="56913-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="56913-115">&lt;서브넷&gt;,&lt;설명&gt;,&lt;위치&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="56913-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="56913-116">... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;시&gt;,&lt;주&gt;,&lt;우편&gt;,&lt;국가&gt;</span><span class="sxs-lookup"><span data-stu-id="56913-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56913-117"><strong>포트</strong></span><span class="sxs-lookup"><span data-stu-id="56913-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="56913-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;설명&gt;,&lt;위치&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,...</span><span class="sxs-lookup"><span data-stu-id="56913-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="56913-119">... &lt;Predirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;구&gt;/&lt;군&gt;/&lt;시&gt;,&lt;주, PostalCode, 국가&gt;</span><span class="sxs-lookup"><span data-stu-id="56913-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56913-120"><strong>바꾸려면</strong></span><span class="sxs-lookup"><span data-stu-id="56913-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="56913-121">&lt;ChassisID&gt;,&lt;설명&gt;,&lt;위치&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="56913-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="56913-122">... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;시&gt;,&lt;주&gt;,&lt;우편&gt;,&lt;국가&gt;</span><span class="sxs-lookup"><span data-stu-id="56913-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="56913-123">위치 데이터베이스를 채우지 않고 위치 정책에 **필요한 위치가** **예** 또는 **부인**로 설정 된 경우 클라이언트는 사용자에 게 위치를 수동으로 입력 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="56913-124">위치 데이터베이스를 채우는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="56913-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="56913-125">**Get-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="56913-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="56913-126">**Set-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="56913-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="56913-127">제거-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="56913-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="56913-128">**Get-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="56913-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="56913-129">**Set-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="56913-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="56913-130">**제거-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="56913-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="56913-131">**Get-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="56913-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="56913-132">**Set-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="56913-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="56913-133">**제거-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="56913-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="56913-134">**Get-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="56913-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="56913-135">**Set-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="56913-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="56913-136">**제거-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="56913-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="56913-137">위치 데이터베이스에 네트워크 요소를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="56913-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="56913-138">다음 cmdlet을 실행 하 여 위치 데이터베이스에 서브넷 위치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="56913-139">게이트웨이에서 ELIN 대해 CompanyName 필드에 ELIN 넣으십시오.</span><span class="sxs-lookup"><span data-stu-id="56913-139">For ELIN gateways, put the ELIN in the CompanyName field.</span></span> <span data-ttu-id="56913-140">두 개 이상의 ELIN을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-140">You can include more than one ELIN.</span></span> <span data-ttu-id="56913-141">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-141">For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="56913-142">또는 다음 cmdlet을 실행 하 고 "subnet. .csv" 이라는 파일을 사용 하 여 서브넷 위치를 대량으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="56913-143">다음 cmdlet을 실행 하 여 위치 데이터베이스에 무선 위치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="56913-144">또는 다음 cmdlet을 실행 하 고 "waps" 라는 파일을 사용 하 여 무선 위치를 대량으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="56913-145">다음 cmdlet을 실행 하 여 위치 데이터베이스에 전환 위치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="56913-146">또는 다음 cmdlet을 실행 하 고 "스위치인 .csv" 라는 파일을 사용 하 여 스위치 위치를 대량으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="56913-147">다음 cmdlet을 실행 하 여 위치 데이터베이스에 포트 위치를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="56913-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="56913-148">PortIDSubType의 기본값은 LocallyAssigned입니다.</span><span class="sxs-lookup"><span data-stu-id="56913-148">The default for PortIDSubType is LocallyAssigned.</span></span> <span data-ttu-id="56913-149">또한이를 인터페이스 별칭 또는 InterfaceName로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-149">You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="56913-150">또는 다음 cmdlet을 실행 하 고 "포트인 .csv" 이라는 파일을 사용 하 여 포트 위치를 대량으로 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56913-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

