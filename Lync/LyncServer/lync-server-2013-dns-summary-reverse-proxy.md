---
title: 'Lync Server 2013: DNS 요약 - 역방향 프록시'
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
ms.openlocfilehash: ae4834ce608f6726403e8742a4d506b173309b35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="79107-102">Lync Server 2013의 DNS 요약 - 역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="79107-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79107-103">_**마지막으로 수정한 주제:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="79107-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="79107-104">리버스 프록시에서 다음과 같이 두 개의 네트워크 어댑터를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="79107-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="79107-105">역방향 프록시 네트워크 어댑터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="79107-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="79107-106">**네트워크 어댑터 1 (내부 인터페이스)** 예제</span><span class="sxs-lookup"><span data-stu-id="79107-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="79107-107">172.25.33.40이 할당 된 내부 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="79107-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="79107-108">기본 게이트웨이가 정의 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79107-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="79107-109">역방향 프록시 내부 인터페이스를 포함 하는 네트워크에서 Lync Server 프런트 엔드 풀 서버를 포함 하는 네트워크 (예: 172.25.33.0에서 192.168.10.0)가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="79107-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="79107-110">**네트워크 어댑터 2 (외부 인터페이스)** 예제</span><span class="sxs-lookup"><span data-stu-id="79107-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="79107-111">최소 하나의 공용 IP 주소가이 네트워크 어댑터에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79107-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="79107-112">게이트웨이는 외부 경계에서 라우터 또는 통합 방화벽을 가리키도록 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79107-112">Gateway is defined to point to the router or integrated firewall in your outer perimeter.</span></span> <span data-ttu-id="79107-113">(시나리오 예제에서 10.45.16.1)</span><span class="sxs-lookup"><span data-stu-id="79107-113">(10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="79107-114">역방향 프록시에 필요한 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="79107-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79107-115">위치/형식/포트</span><span class="sxs-lookup"><span data-stu-id="79107-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="79107-116">Q</span><span class="sxs-lookup"><span data-stu-id="79107-116">FQDN</span></span></th>
<th><span data-ttu-id="79107-117">IP 주소</span><span class="sxs-lookup"><span data-stu-id="79107-117">IP address</span></span></th>
<th><span data-ttu-id="79107-118">/메모에 매핑</span><span class="sxs-lookup"><span data-stu-id="79107-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79107-119">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="79107-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="79107-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79107-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="79107-121">외부 게시 리소스에 할당 된 수신기</span><span class="sxs-lookup"><span data-stu-id="79107-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="79107-122">내부 배포의 외부 웹 서비스.</span><span class="sxs-lookup"><span data-stu-id="79107-122">External web services from the internal deployment.</span></span> <span data-ttu-id="79107-123">이 리버스 프록시를 사용 하 고 외부 웹 서비스를 정의한 모든 SIP 도메인에 대해 모든 풀 및 단일 서버에 대해 추가 레코드를 정의 하 고 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79107-123">Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79107-124">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="79107-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="79107-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79107-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="79107-126">외부 게시 리소스에 할당 된 수신기</span><span class="sxs-lookup"><span data-stu-id="79107-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="79107-127">배포의 감독 또는 디렉터 풀에 대 한 외부 웹 서비스.</span><span class="sxs-lookup"><span data-stu-id="79107-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="79107-128">다른 SIP 도메인에 연결 될 수 있는 별도의 디렉터 중에서 디렉터를 한 개까지 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79107-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="79107-129">디렉터에 대 한 DNS 레코드를 정의 하 고 게시 하는 것은 프런트 엔드 풀 또는 디렉터 결정이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="79107-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="79107-130">디렉터를 사용 하는 경우에는 감독 및 프런트 엔드 풀 외부 웹 서비스를 모두 정의 하 고 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79107-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="79107-131">토폴로지에 정의 되어 있는 경우 인증 및 기타 사용에 대 한 특정 트래픽 종류가 먼저 디렉터로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79107-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79107-132">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="79107-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="79107-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79107-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="79107-134">외부 게시 리소스에 할당 된 수신기</span><span class="sxs-lookup"><span data-stu-id="79107-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="79107-135">전화 접속 회의 외부에 게시 됨</span><span class="sxs-lookup"><span data-stu-id="79107-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79107-136">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="79107-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="79107-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79107-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="79107-138">외부 게시 리소스에 할당 된 수신기</span><span class="sxs-lookup"><span data-stu-id="79107-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="79107-139">회의가 외부적으로 발표 됨</span><span class="sxs-lookup"><span data-stu-id="79107-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79107-140">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="79107-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="79107-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79107-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="79107-142">Office Web Apps Server에 할당 된 수신기</span><span class="sxs-lookup"><span data-stu-id="79107-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="79107-143">내부 또는 주변에 배포 되 고 외부 클라이언트 액세스용으로 게시 된 Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="79107-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79107-144">외부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="79107-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="79107-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="79107-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="79107-146">외부 게시 리소스에 할당 된 수신기</span><span class="sxs-lookup"><span data-stu-id="79107-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="79107-147">Lync에서 외부 게시 된 자동 검색을 비롯 하 여 모바일, Microsoft Lync Web App, 스케줄러 웹 앱을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="79107-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

