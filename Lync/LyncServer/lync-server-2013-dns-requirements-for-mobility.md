---
title: 'Lync Server 2013: 모바일 기능에 대 한 DNS 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7da4910594581f253db155bfceb85c0dcd78f60
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a><span data-ttu-id="14a63-102">Lync Server 2013의 모바일 기능에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="14a63-102">DNS requirements for mobility with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14a63-103">_**마지막으로 수정 된 항목:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="14a63-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="14a63-104">Lync Server 2013 모바일 기능을 배포할 때는 Microsoft Lync Server 2013 자동 검색 서비스에서 사용할 수 있는 새 Url을 사용 하거나 기존 웹 서비스 Url을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-104">When you deploy the Lync Server 2013 mobility feature, you can use the new URLs that are available with the Microsoft Lync Server 2013 Autodiscover Service, or you can use your existing Web Services URLs.</span></span> <span data-ttu-id="14a63-105">기존 URL을 사용하는 경우 사용자는 모바일 장치 설정에 URL을 수동으로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-105">If you use your existing URLs, users need to manually enter the URLs in their mobile device settings.</span></span> <span data-ttu-id="14a63-106">이 옵션은 보통 문제 해결용으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-106">This option is typically used for troubleshooting.</span></span> <span data-ttu-id="14a63-107">새 Url을 사용 하는 경우 모바일 클라이언트는 Lync Server 2013 리소스를 자동으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-107">When you use the new URLs, mobile clients can automatically discover Lync Server 2013 resources.</span></span> <span data-ttu-id="14a63-108">자동 검색을 지원하는 경우에는 새 DNS(Domain Name System) 레코드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-108">When you support automatic discovery, you need to add new Domain Name System (DNS) records.</span></span> <span data-ttu-id="14a63-109">이 섹션에서는 자동 검색에 필요한 DNS 레코드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-109">This section describes the DNS records that are required for automatic discovery.</span></span>

<span data-ttu-id="14a63-110">자동 검색을 지원하려면 각 SIP 도메인에 대해 다음 DNS 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-110">To support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="14a63-111">조직 네트워크 내에서 연결하는 모바일 사용자를 지원하기 위한 내부 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="14a63-111">An internal DNS record to support mobile users who connect from within your organization's network</span></span>

  - <span data-ttu-id="14a63-112">인터넷에서 연결하는 모바일 사용자를 지원하기 위한 외부(공용) DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="14a63-112">An external, or public, DNS record to support mobile users who connect from the Internet</span></span>

<span data-ttu-id="14a63-p102">내부 자동 검색 URL의 주소는 네트워크 외부에서 확인할 수 없어야 하며, 외부 자동 검색 URL의 주소는 네트워크 내에서 확인할 수 없어야 합니다. 그러나 외부 URL에 대해 이 요구 사항을 충족할 수 없는 경우에도 모바일 클라이언트의 기능에 영향이 있어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-p102">The internal automatic discovery URL should not be addressable from outside your network. The external automatic discovery URL should not be addressable from within your network. However, if you cannot meet this requirement for the external URL, mobile client functionally should not be affected.</span></span>

<span data-ttu-id="14a63-116">DNS 레코드는 CNAME 레코드 또는 A(호스트) 레코드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-116">The DNS records can be either CNAME records or A (host) records.</span></span>

<span data-ttu-id="14a63-117">**내부 DNS 레코드**</span><span class="sxs-lookup"><span data-stu-id="14a63-117">**Internal DNS records**</span></span>

<span data-ttu-id="14a63-118">다음 내부 DNS 레코드 중 하나를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-118">You need to create one of the following internal DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14a63-119">레코드 유형</span><span class="sxs-lookup"><span data-stu-id="14a63-119">Record type</span></span></th>
<th><span data-ttu-id="14a63-120">호스트 이름 또는 SRV 정의</span><span class="sxs-lookup"><span data-stu-id="14a63-120">Host name or SRV definition</span></span></th>
<th><span data-ttu-id="14a63-121">확인 대상</span><span class="sxs-lookup"><span data-stu-id="14a63-121">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14a63-122">CNAME</span><span class="sxs-lookup"><span data-stu-id="14a63-122">CNAME</span></span></p></td>
<td><p><span data-ttu-id="14a63-123">lyncdiscoverinternal. &lt;microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="14a63-123">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="14a63-124">디렉터 풀에 대 한 내부 웹 서비스 FQDN (정규화 된 도메인 이름) (있는 경우) 또는 디렉터가 없는 경우 프런트 엔드 풀에 대해</span><span class="sxs-lookup"><span data-stu-id="14a63-124">Internal Web Services fully qualified domain name (FQDN) for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a63-125">A(호스트)</span><span class="sxs-lookup"><span data-stu-id="14a63-125">A (host)</span></span></p></td>
<td><p><span data-ttu-id="14a63-126">lyncdiscoverinternal. &lt;microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="14a63-126">lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="14a63-127">디렉터 풀의 내부 웹 서비스 IP 주소 (부하 분산 장치를 사용 하는 경우 VIP (가상 IP) 주소), 디렉터가 없는 경우 하나 또는 프런트 엔드 풀이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="14a63-127">Internal Web Services IP address (virtual IP (VIP) address if you use a load balancer) of your Director pool, if you have one, or of your Front End pool if you do not have a Director</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="14a63-128">**외부 DNS 레코드**</span><span class="sxs-lookup"><span data-stu-id="14a63-128">**External DNS records**</span></span>

<span data-ttu-id="14a63-129">다음 외부 DNS 레코드 중 하나를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-129">You need to create one of the following external DNS records:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14a63-130">레코드 유형</span><span class="sxs-lookup"><span data-stu-id="14a63-130">Record type</span></span></th>
<th><span data-ttu-id="14a63-131">호스트 이름</span><span class="sxs-lookup"><span data-stu-id="14a63-131">Host name</span></span></th>
<th><span data-ttu-id="14a63-132">확인 대상</span><span class="sxs-lookup"><span data-stu-id="14a63-132">Resolves to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14a63-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="14a63-133">CNAME</span></span></p></td>
<td><p><span data-ttu-id="14a63-134">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="14a63-134">lyncdiscover.</span></span> <span data-ttu-id="14a63-135">&lt;microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="14a63-135">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="14a63-136">디렉터 풀에 대 한 외부 웹 서비스 FQDN (있는 경우) 또는 사용자에 게 디렉터가 없는 경우 프런트 엔드 풀의 경우</span><span class="sxs-lookup"><span data-stu-id="14a63-136">External Web Services FQDN for your Director pool, if you have one, or for your Front End pool if you do not have a Director</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14a63-137">A(호스트)</span><span class="sxs-lookup"><span data-stu-id="14a63-137">A (host)</span></span></p></td>
<td><p><span data-ttu-id="14a63-138">lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="14a63-138">lyncdiscover.</span></span> <span data-ttu-id="14a63-139">&lt;microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="14a63-139">&lt;sipdomain&gt;</span></span></p></td>
<td><p><span data-ttu-id="14a63-140">역방향 프록시의 외부(공용) IP 주소(부하 분산 장치를 사용하는 경우 VIP 주소)</span><span class="sxs-lookup"><span data-stu-id="14a63-140">External or public IP address (VIP address if you use a load balancer) of the reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14a63-141">SRV</span><span class="sxs-lookup"><span data-stu-id="14a63-141">SRV</span></span></p></td>
<td><p><span data-ttu-id="14a63-142">_tcp을 _sipfederationtls 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-142">_sipfederationtls._tcp.</span></span> <span data-ttu-id="14a63-143">&lt;microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="14a63-143">&lt;sipdomain&gt;</span></span></p>
<p><span data-ttu-id="14a63-144">액세스에 지 서비스에 대 한 호스트 (A 또는 AAAA) 레코드로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-144">Resolves to host (A or AAAA) record for the Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="14a63-145">푸시 알림 서비스 및 Apple 푸시 알림 서비스를 지원 하려면 Microsoft Lync Mobile 클라이언트를 포함 하는 각 SIP 도메인에 대해 하나의 SRV 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-145">To support Push Notification Service and Apple Push Notification service, you create one SRV record for each SIP domain that has Microsoft Lync Mobile clients.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="14a63-146">이 요구 사항은 Apple 또는 Microsoft 기반 모바일 장치에서 Microsoft Lync 모바일 클라이언트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-146">This requirement applies only to Microsoft Lync Mobile clients on Apple or Microsoft based mobile devices.</span></span> <span data-ttu-id="14a63-147">Andriod 및 Nokia Symbian 장치에서는 푸시 알림을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-147">Andriod and Nokia Symbian devices do not use push notification.</span></span>


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="14a63-148">자동 검색이 라고도 하는 lyncdiscover 트래픽은 역방향 프록시를 통해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-148">Lyncdiscover, also known as autodiscover, traffic goes through the reverse proxy.</span></span> <span data-ttu-id="14a63-149">SRV 레코드는 액세스에 지 서비스를 통해 확인 되는 레코드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="14a63-149">SRV record points to a record that resolves through the Access Edge service.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

