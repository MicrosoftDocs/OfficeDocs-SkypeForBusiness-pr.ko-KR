---
title: 'Lync Server 2013: DNS 요약-역방향 프록시'
description: 'Lync Server 2013: DNS 요약-역방향 프록시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc2d806893786a11317be1eff9bfdc08c9230bf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544794"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="1c7cf-103">Lync Server 2013의 DNS 요약-역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="1c7cf-103">DNS summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c7cf-104">_**마지막으로 수정 된 항목:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="1c7cf-104">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="1c7cf-105">다음과 같이 역방향 프록시에 네트워크 어댑터 두 개를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7cf-105">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="1c7cf-106">역방향 프록시 네트워크 어댑터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c7cf-106">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="1c7cf-107">**네트워크 어댑터 1(내부 인터페이스)** 예</span><span class="sxs-lookup"><span data-stu-id="1c7cf-107">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="1c7cf-108">172.25.33.40이 할당된 내부 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1c7cf-108">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="1c7cf-109">기본 게이트웨이가 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7cf-109">No default gateway is defined.</span></span>
    
    <span data-ttu-id="1c7cf-110">역방향 프록시 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 프런트 엔드 풀 서버가 포함 된 네트워크 (예: 172.25.33.0에서 192.168.10.0로의 경로)가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7cf-110">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="1c7cf-111">**네트워크 어댑터 2(외부 인터페이스)** 예</span><span class="sxs-lookup"><span data-stu-id="1c7cf-111">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="1c7cf-112">이 네트워크 어댑터에는 최소 하나의 공용 IP 주소가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7cf-112">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="1c7cf-p101">게이트웨이는 외부 경계의 통합 방화벽 또는 라우터를 가리키도록 정의됩니다(시나리오 예에서는 10.45.16.1).</span><span class="sxs-lookup"><span data-stu-id="1c7cf-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="1c7cf-115">역방향 프록시에 필요한 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="1c7cf-115">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c7cf-116">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="1c7cf-116">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="1c7cf-117">FQDN</span><span class="sxs-lookup"><span data-stu-id="1c7cf-117">FQDN</span></span></th>
<th><span data-ttu-id="1c7cf-118">IP 주소</span><span class="sxs-lookup"><span data-stu-id="1c7cf-118">IP address</span></span></th>
<th><span data-ttu-id="1c7cf-119">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="1c7cf-119">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c7cf-120">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1c7cf-120">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-121">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1c7cf-121">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-122">외부에 게시된 리소스에 할당되는 수신기</span><span class="sxs-lookup"><span data-stu-id="1c7cf-122">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-p102">내부 배포의 외부 웹 서비스입니다. 이 역방향 프록시를 사용하며 외부 웹 서비스를 정의한 모든 SIP 도메인에 대해 모든 풀과 단일 서버용으로 추가 레코드를 정의하고 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7cf-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c7cf-125">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1c7cf-125">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-126">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1c7cf-126">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-127">외부에 게시된 리소스에 할당되는 수신기</span><span class="sxs-lookup"><span data-stu-id="1c7cf-127">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-128">배포에 있는 디렉터 또는 디렉터 풀에 대 한 외부 웹 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="1c7cf-128">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="1c7cf-129">다른 SIP 도메인과 연결 될 수 있는 여러 디렉터를 각 디렉터로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7cf-129">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="1c7cf-130">디렉터에 대 한 DNS 레코드를 정의 하 고이를 게시 하는 것은 프런트 엔드 풀 또는 디렉터 결정이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1c7cf-130">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="1c7cf-131">감독을 사용 하는 경우에는 디렉터 및 프런트 엔드 풀 외부 웹 서비스를 모두 정의 하 고 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7cf-131">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="1c7cf-132">토폴로지에 정의 된 경우 인증 및 기타 사용을 위한 특정 트래픽 유형이 디렉터로 먼저 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7cf-132">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c7cf-133">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1c7cf-133">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-134">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1c7cf-134">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-135">외부에 게시된 리소스에 할당되는 수신기</span><span class="sxs-lookup"><span data-stu-id="1c7cf-135">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-136">전화 접속 회의를 외부적으로 게시하는 데 사용됨</span><span class="sxs-lookup"><span data-stu-id="1c7cf-136">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c7cf-137">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1c7cf-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-138">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1c7cf-138">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-139">외부에 게시된 리소스에 할당되는 수신기</span><span class="sxs-lookup"><span data-stu-id="1c7cf-139">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-140">전화 회의를 외부적으로 게시하는 데 사용됨</span><span class="sxs-lookup"><span data-stu-id="1c7cf-140">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c7cf-141">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1c7cf-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-142">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1c7cf-142">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-143">Office Web Apps 서버에 대해 할당 된 수신기</span><span class="sxs-lookup"><span data-stu-id="1c7cf-143">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-144">내부 또는 경계에 배포 되 고 외부 클라이언트 액세스용으로 게시 된 Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="1c7cf-144">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c7cf-145">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="1c7cf-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-146">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1c7cf-146">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-147">외부에 게시된 리소스에 할당되는 수신기</span><span class="sxs-lookup"><span data-stu-id="1c7cf-147">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="1c7cf-148">외부에서 게시 된 자동 검색 및 모바일 기능, Microsoft Lync Web App 및 스케줄러 웹 앱을 포함 하는 Lync 검색 외부 레코드</span><span class="sxs-lookup"><span data-stu-id="1c7cf-148">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

