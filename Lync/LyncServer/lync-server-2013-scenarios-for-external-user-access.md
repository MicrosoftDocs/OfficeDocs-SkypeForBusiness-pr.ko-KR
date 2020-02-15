---
title: 'Lync Server 2013: 외부 사용자 액세스에 대 한 시나리오'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd560105303db5d09656c36620c9e8435feed86f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="b3a77-102">Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="b3a77-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3a77-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b3a77-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b3a77-104">Lync Server 2013에 대 한 외부 사용자 액세스를 제공 하려면 경계 네트워크에 하나 이상의에 지 서버와 하나의 역방향 프록시를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="b3a77-105">필요한 경우 내부 네트워크에 디렉터 또는 디렉터 풀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="b3a77-106">단일에 지 서버에서 제공할 수 있는 것 보다 많은 용량이 필요 하거나,에 지 서버 배포에 대 한 고가용성이 필요한 경우 부하 분산을 구성 하 고 부하 분산 된 풀에 여러 개의에 지 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="b3a77-107">조직에 데이터 센터가 여러 개 있는 경우에는 둘 이상의 위치에에 지 서버 또는에 지 풀 배포가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="b3a77-108">그러나에 지 서버 배포 중 하나만 페더레이션 경로로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="b3a77-109">이 섹션에서는에 지 서버 배포 시나리오를 정의 하 고 계획 섹션을 가능한 시나리오로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="b3a77-110">예를 들어 배포에 고가용성, 확장 가능한 메시징 및 현재 상태 (XMPP) 연락처 및 Lync mobility가 포함 된 페더레이션이 필요한 경우 다음 표에서 이러한 요구 사항을 충족 하는 일치 항목을 선택 하 고 다음 순서도에 설명 된 대로 배포를 정의 하기 위해 참조 하는 계획 섹션</span><span class="sxs-lookup"><span data-stu-id="b3a77-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="b3a77-111">**에 지 서버 배포 시나리오 선택 프로세스**</span><span class="sxs-lookup"><span data-stu-id="b3a77-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="b3a77-112">![샘플 배포 순서도](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "샘플 배포 순서도")</span><span class="sxs-lookup"><span data-stu-id="b3a77-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="b3a77-113">이 프로세스를 사용 하 여 사용자를 위해 배포할 모든 잠재적 기능의 구성을 계획 하 고 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="b3a77-114">그러나에 지 서버를 배포 하 고 다른 기능을 추가 하기 전에 올바른 작업을 확인 한 후에는 페더레이션 및 모바일 서비스를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="b3a77-115">기존에 지 서버 배포에 기능을 추가 하는 프로세스는 배포 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="b3a77-116">배포에 대 한 자세한 내용은 초기 계획 프로세스를 진행 하는 동안 이러한 기능에 대 한 계획을 포함 하 여 [Lync Server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하세요. 그러면 추가 된 기능에 대 한 dns, 방화벽 및 인증서 요구 사항을 준비 하 여 인증서를 얻고 dns 및 포트/프로토콜 요구 사항을 구성 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="b3a77-117">에 지 서버 및 역방향 프록시를 설치한 다음 나중에 (예: 페더레이션 및 모바일) 기능을 추가 하려는 경우 배포 후 모든 서비스에 필요한 인증서를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="b3a77-118">사전에 모든 기능에 대 한 인증서를 계획 하 고 취득 하기 위해 초기에 배포 하거나 보내지 않을 경우 페더레이션 요구 사항 (즉,에 지 서버) 또는 역방향 프록시 (즉, 모바일 기능에 대 한)를 충족 하기 위해 새 인증서를 주문할 필요가 없습니다. 서비스).</span><span class="sxs-lookup"><span data-stu-id="b3a77-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b3a77-119">모든에 지 서비스가 각에 지 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="b3a77-120">서로 다른 두에 지 서버 간에는 서비스를 분할할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="b3a77-121">확장성을 위해에 지 풀을 배포 하는 경우 모든에 지 서비스가 풀의 각에 지 서버에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="b3a77-122">XMPP 페더레이션, Office Communications Server 및 Lync Server 페더레이션, 공용 IM 연결 및 클라이언트 이동성은 첫 번째에 지 서버 또는에 지 풀을 배포한 후에 배포할 수 있는 추가 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="b3a77-123">모바일 서비스는 역방향 프록시를 사용 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="b3a77-124">모바일 서비스 설치는 기능을에 지 서버에 추가 하지는 않지만, 역방향 프록시를 다시 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="b3a77-125">이러한 기능을 나열 하는 <STRONG>설치 목표</STRONG> 열에서는 edge 서버를 설치 및 구성할 때 이러한 기능을 배포할 수 있도록 동시에 계획 하기 위한 <STRONG>섹션 이나에 지 서버 계획 섹션</STRONG> 의 관련 열에 있는 계획 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="b3a77-126">배포 목표 파악 및 매핑</span><span class="sxs-lookup"><span data-stu-id="b3a77-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3a77-127">설치 목표</span><span class="sxs-lookup"><span data-stu-id="b3a77-127">Installation goal</span></span></th>
<th><span data-ttu-id="b3a77-128">에 지 서버 계획 설명서</span><span class="sxs-lookup"><span data-stu-id="b3a77-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3a77-129">인프라의에 지 서비스에 대해 단일 서버를 충분히 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-129">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="b3a77-130">또한 NAT를 사용 하 여 인터넷에 대 한에 지 서버 외부 인터페이스에 대해 개인 IP 주소를 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-130">You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="b3a77-131">경계에 단일에 지 서버를 배포 하는 경우이 계획 섹션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="b3a77-132">에 지 서버에 대 한 전용 IP 주소를 할당 하는 Edge Server를 배포 하 고 NAT를 사용 하 여 인터넷의 외부 사용자에 대 한 공용 IP 주소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="b3a77-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Lync Server 2013의 개인 IP 주소 및 NAT를 포함 하는 단일 통합에 지</a></span><span class="sxs-lookup"><span data-stu-id="b3a77-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3a77-134">인프라의에 지 서비스에 대해 단일 서버를 충분히 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-134">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="b3a77-135">또한에 지 서버 외부 인터페이스에 대 한 공용 IP 주소를 인터넷에 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-135">You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="b3a77-136">경계에 단일에 지 서버를 배포 하는 경우이 계획 섹션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="b3a77-137">에 지 서버에 할당 된 공용 IP 주소를 사용 하 여에 지 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="b3a77-138">NAT 대신이 시나리오에서 라우팅을 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="b3a77-139">외부 사용자 연결에 대 한에 지 서버의 실제 공용 IP 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="b3a77-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Lync Server 2013의 공용 IP 주소를 포함 하는 단일 통합에 지</a></span><span class="sxs-lookup"><span data-stu-id="b3a77-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3a77-141">에 지 서비스의 고가용성은 사용자에 게 중요 하며이 풀에는 두 개 이상의에 지 서버를 배포 하도록 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-141">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="b3a77-142">또한 NAT를 사용 하 여 인터넷에 대 한에 지 서버 외부 인터페이스에 대해 개인 IP 주소를 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-142">You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="b3a77-143">경계에에 지 서버 풀을 배포 하는 경우이 계획 섹션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="b3a77-144">DNS 부하 분산을 사용 하 여 풀 전체에 통신을 분산 시켜에 지 서버에 할당 된 개인 IP 주소를 사용 하 여에 지 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="b3a77-145">NAT를 사용 하 여 인터넷의 외부 사용자에 대 한 공용 IP 주소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="b3a77-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Lync Server 2013의 확장 된 통합에 지, NAT 사용 개인 IP 주소의 DNS 부하 분산</a></span><span class="sxs-lookup"><span data-stu-id="b3a77-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3a77-147">에 지 서비스의 고가용성은 사용자에 게 중요 하며이 풀에는 두 개 이상의에 지 서버를 배포 하도록 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="b3a77-148">또한에 지 서버 외부 인터페이스에 대 한 공용 IP 주소를 인터넷에 사용 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="b3a77-149">경계에에 지 서버 풀을 배포 하는 경우이 계획 섹션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="b3a77-150">DNS 부하 분산을 사용 하 여 풀 전체에 통신을 분산 시켜에 지 서버에 할당 된 공용 IP 주소를 사용 하 여에 지 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="b3a77-151">NAT 대신 라우팅을 사용 하 여 인터넷의 외부 사용자에 대 한 공용 IP 주소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="b3a77-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Lync Server 2013의 확장 된 통합에 지, 공용 IP 주소의 DNS 부하 분산</a></span><span class="sxs-lookup"><span data-stu-id="b3a77-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3a77-153">에 지 서비스의 고가용성은 사용자에 게 중요 하며, 하드웨어 부하 분산 장치를 사용 하 여이 풀에 두 개 이상의에 지 서버를 배포 하도록 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="b3a77-154">경계에에 지 서버 풀을 배포 하는 경우이 계획 섹션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="b3a77-155">하드웨어 부하 분산 장치를 사용 하 여 풀 전체에 통신을 분산 시켜에 지 서버에 할당 된 공용 IP 주소를 사용 하 여에 지 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="b3a77-156">NAT 대신 라우팅을 사용 하 여 인터넷의 외부 사용자에 대 한 공용 IP 주소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="b3a77-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013의 하드웨어 부하 분산 장치로 확장 된 통합에 지</a></span><span class="sxs-lookup"><span data-stu-id="b3a77-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3a77-158">페더레이션 시나리오를 사용 하면 사용자가 통신할 수 있는 파트너 유형을 확장 하는 기능을 계획 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="b3a77-159">Lync Server 페더레이션</span><span class="sxs-lookup"><span data-stu-id="b3a77-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="b3a77-160">Office Communications Server 페더레이션</span><span class="sxs-lookup"><span data-stu-id="b3a77-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="b3a77-161">공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="b3a77-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="b3a77-162">XMPP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="b3a77-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="b3a77-163">페더레이션 시나리오 계획</span><span class="sxs-lookup"><span data-stu-id="b3a77-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="b3a77-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Lync Server 2013 및 Office Communications Server federation 계획</a></span><span class="sxs-lookup"><span data-stu-id="b3a77-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="b3a77-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Lync Server 2013의 공용 인스턴트 메시징 연결 계획</a></span><span class="sxs-lookup"><span data-stu-id="b3a77-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="b3a77-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Lync Server 2013의 XMPP (extensible messaging and 거점 protocol) 페더레이션 계획</a></span><span class="sxs-lookup"><span data-stu-id="b3a77-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3a77-167">모바일 서비스는 역방향 프록시를 통해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="b3a77-168">외부 사용자에 대해 모바일 기능을 사용 하도록 설정 하는 서비스는 프런트 엔드 서버 또는 프런트 엔드 풀에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="b3a77-169">외부 사용자에 대해 모바일 서비스를 사용 하도록 설정 하기 위해 역방향 프록시에서 기존 게시 규칙을 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="b3a77-170"><a href="lync-server-2013-planning-for-mobility.md">Lync Server 2013의 모바일 기능 계획</a></span><span class="sxs-lookup"><span data-stu-id="b3a77-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="b3a77-171">다음 시나리오에서는 참조 아키텍처, 예제 DNS, 포트/프로토콜 정의 및 인증서 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="b3a77-172">또한 DNS, 포트/프로토콜 정의 및 인증서 요구 사항에 대 한 다이어그램도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="b3a77-173">다이어그램은 다른 팀 (예: 조직의 네트워크 팀, 공개 키 인프라 팀 및 서버 배포 팀)에 입력 하 고 배포할 수 있는 서식 파일을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="b3a77-174">다이어그램의 목표는 통신을 향상 시키고 필수에 지 서버 구성 요소를 실제 구성 작업을 수행 하는 사용자에 게 전달할 때 성공 여부를 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="b3a77-175">다이어그램 및 관련 참조 아키텍처를 사용 하 여 배포를 계획 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a77-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

