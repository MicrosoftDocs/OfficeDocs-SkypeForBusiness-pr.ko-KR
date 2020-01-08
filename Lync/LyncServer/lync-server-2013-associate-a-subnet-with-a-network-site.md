---
title: 'Lync Server 2013: 네트워크 사이트에 서브넷 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associate a subnet with a network site
ms:assetid: aa69e3ac-542a-4ba1-9582-2e6bee29f633
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412804(v=OCS.15)
ms:contentKeyID: 48185043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec5a896af6312fecf53259ac10e72f99598d4a7e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associate-a-subnet-with-a-network-site-in-lync-server-2013"></a><span data-ttu-id="99f5e-102">Lync Server 2013 에서 네트워크 사이트에 서브넷 연결</span><span class="sxs-lookup"><span data-stu-id="99f5e-102">Associate a subnet with a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99f5e-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="99f5e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="99f5e-104">네트워크의 모든 서브넷은 새 세션이 시작 되는 동안 끝점이 위치한 네트워크 사이트를 결정 하는 데 사용 되므로 서브넷 정보는 특정 네트워크 사이트와 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-104">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="99f5e-105">세션에서 각 파티의 위치를 알고 있는 경우 고급 엔터프라이즈 음성 기능에서 해당 정보를 적용 하 여 전화 설정 또는 라우팅 처리 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-105">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="99f5e-106">배포에 있는 오디오/비디오에 지 서버의 모든 구성 된 공용 IP 주소를 네트워크 구성 설정에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-106">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="99f5e-107">이러한 IP 주소는 32의 마스크로 서브넷으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-107">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="99f5e-108">연결 된 네트워크 사이트는 적절 하 게 구성 된 네트워크 사이트와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-108">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="99f5e-109">예를 들어 중앙 사이트 시카고의 A/V에 지 서버에 해당 하는 공용 IP 주소는 NetworkSiteID 시카고입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-109">For example, the public IP address that corresponds to the A/V Edge Server in central site Chicago would be NetworkSiteID Chicago.</span></span> <span data-ttu-id="99f5e-110">공용 IP 주소에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">외부 A/V 방화벽 및 Lync Server 2013의 포트 요구 사항 결정</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f5e-110">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="99f5e-111">네트워크에는 있지만 서브넷에 연결 되지 않았거나 IP 주소가 포함 된 서브넷이 네트워크 사이트와 연결 되어 있지 않은 경우 KHI (키 상태 표시기) 경고가 발생 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-111">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="99f5e-112">이 알림은 8 시간 내에 두 번 이상 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-112">This alert will not be raised more than once within an 8-hour period.</span></span> <span data-ttu-id="99f5e-113">관련 경고 정보 및 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-113">The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="99f5e-114"><STRONG>원본:</STRONG> CS (대역폭 정책 서비스) (Core)</span><span class="sxs-lookup"><span data-stu-id="99f5e-114"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="99f5e-115"><STRONG>이벤트 번호:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="99f5e-115"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="99f5e-116"><STRONG>수준:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="99f5e-116"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="99f5e-117"><STRONG>설명:</STRONG> 다음 IP 주소의 서브넷: &lt;ip 주소&gt; 목록이 구성 되지 않았거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-117"><STRONG>Description:</STRONG> The subnets for the following IP addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a Network Site.</span></span><BR><span data-ttu-id="99f5e-118"><STRONG>원인:</STRONG> 해당 IP 주소에 대 한 서브넷이 네트워크 구성 설정에 없거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-118"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="99f5e-119"><STRONG>해결 방법:</STRONG> IP 주소 목록에 해당 하는 서브넷을 네트워크 구성 설정에 추가 하 고 모든 서브넷을 네트워크 사이트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-119"><STRONG>Resolution:</STRONG> Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="99f5e-120">예를 들어 alert의 IP 주소 목록에서 10.121.248.226 및 10.121.249.20를 지정 하는 경우 이러한 IP 주소가 서브넷과 연결 되어 있지 않거나 연결 된 서브넷이 네트워크 사이트에 속해 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-120">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site.</span></span> <span data-ttu-id="99f5e-121">10.121.248.0/24 및 10.121.249.0/24가 이러한 주소에 해당 하는 서브넷 이면 다음과 같이이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-121">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="99f5e-122">IP 주소 10.121.248.226이 10.121.248.0/24 서브넷 및 IP 주소 10.121.249.20와 연결 되어 있는지 확인 하 고 10.121.249.0/24 서브넷과 연결 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-122">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
> <LI>
> <P><span data-ttu-id="99f5e-123">10.121.248.0/24 및 10.121.249.0/24 서브넷이 각각 네트워크 사이트와 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-123">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>



</div>

<span data-ttu-id="99f5e-124">네트워크 서브넷 작업에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f5e-124">For details about working with network subnets, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="99f5e-125">새-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="99f5e-125">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)

  - [<span data-ttu-id="99f5e-126">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="99f5e-126">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)

  - [<span data-ttu-id="99f5e-127">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="99f5e-127">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)

  - [<span data-ttu-id="99f5e-128">CsNetworkSubnet 제거</span><span class="sxs-lookup"><span data-stu-id="99f5e-128">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)

<div>


> [!TIP]  
> <span data-ttu-id="99f5e-129">많은 수의 서브넷을 사용 하는 경우 CSV (쉼표로 구분 된 값) 파일을 사용 하 여 서브넷을 사이트에 연결 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-129">If you are working with a large number of subnets, we recommend using a comma-separated values (CSV) file to associate the subnets to sites.</span></span> <span data-ttu-id="99f5e-130">CSV 파일에는 <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>networksiteid</STRONG>와 같은 네 개의 열이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-130">The CSV file must have the following four columns: <STRONG>IPAddress</STRONG>, <STRONG>mask</STRONG>, <STRONG>description</STRONG>, <STRONG>NetworkSiteID</STRONG>.</span></span>



</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-management-shell"></a><span data-ttu-id="99f5e-131">관리 셸을 사용 하 여 서브넷을 네트워크 사이트와 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="99f5e-131">To associate a subnet with a network site by using Management Shell</span></span>

1.  <span data-ttu-id="99f5e-132">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="99f5e-133">**새-CsNetworkSubnet** cmdlet을 실행 하 여 서브넷을 네트워크 사이트와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-133">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>
    
        New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
    
    <span data-ttu-id="99f5e-134">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-134">For example:</span></span>
    
        New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
    
    <span data-ttu-id="99f5e-135">이 예제에서는 서브넷 172.11.12.13와 네트워크 사이트 "시카고" 간에 연결을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-135">In this example, you created an association between the subnet 172.11.12.13 and the network site “Chicago”.</span></span>

3.  <span data-ttu-id="99f5e-136">토폴로지의 모든 서브넷에 대해 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-136">Repeat step 2 for all subnets in your topology.</span></span>

</div>

<div>

## <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="99f5e-137">CSV 파일을 가져와 서브넷을 네트워크 사이트와 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="99f5e-137">To associate subnets with network sites by importing a CSV file</span></span>

1.  <span data-ttu-id="99f5e-138">추가 하려는 모든 서브넷을 포함 하는 CSV 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-138">Create a CSV file that includes all of the subnets you want to add.</span></span> <span data-ttu-id="99f5e-139">예를 들어 다음 콘텐츠를 사용 하 여 **subnet** 이라는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-139">For example, create a file named **subnet.csv** with the following content:</span></span>
    
    `IPAddress, mask, description, NetworkSiteID`
    
    `172.11.12.0, 24, "NA:Subnet in Portland", Portland`
    
    `172.11.13.0, 24, "NA:Subnet in Reno", Reno`
    
    `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`
    
    `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2.  <span data-ttu-id="99f5e-140">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="99f5e-141">다음 cmdlet을 실행 하 여 **서브넷 .csv**를 가져온 다음 Lync Server 관리 저장소에 해당 콘텐츠를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-141">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>
    
        import-csv subnet.csv | foreach {New-CSNCSSubnet  _.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}

</div>

<div>

## <a name="to-associate-a-subnet-with-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="99f5e-142">Lync Server 제어판을 사용 하 여 서브넷을 네트워크 사이트와 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="99f5e-142">To associate a subnet with a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="99f5e-143">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-143">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="99f5e-144">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f5e-144">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="99f5e-145">왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-145">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="99f5e-146">**서브넷** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-146">Click the **Subnet** navigation button.</span></span>

4.  <span data-ttu-id="99f5e-147">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-147">Click **New**.</span></span>

5.  <span data-ttu-id="99f5e-148">**새 서브넷** 페이지에서 **서브넷 ID**를 클릭 한 다음 네트워크 사이트와 연결 하려는 서브넷이 정의한 IP 주소 범위에 첫 번째 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-148">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6.  <span data-ttu-id="99f5e-149">**마스크**를 클릭 한 다음 서브넷에 적용할 비트 마스크를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-149">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7.  <span data-ttu-id="99f5e-150">**네트워크 사이트 id**를 클릭 한 다음이 서브넷을 추가할 사이트의 사이트 id를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-150">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99f5e-151">아직 네트워크 사이트를 만들지 않은 경우에는이 목록이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-151">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="99f5e-152">절차에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-network-site.md">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f5e-152">For details about the procedure, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="99f5e-153">또한 <STRONG>Get-CsNetworkSite</STRONG> cmdlet을 실행 하 여 배포에 대 한 사이트 id를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-153">You can also retrieve site IDs for your deployment by running the <STRONG>Get-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="99f5e-154">자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="99f5e-154">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="99f5e-155">필요에 따라 **설명을**클릭 한 다음 추가 정보를 입력 하 여이 서브넷을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-155">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9.  <span data-ttu-id="99f5e-156">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-156">Click **Commit**.</span></span>

<span data-ttu-id="99f5e-157">네트워크 사이트에 다른 서브넷을 추가 하려면이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="99f5e-157">Repeat these steps to add other subnets to a network site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

