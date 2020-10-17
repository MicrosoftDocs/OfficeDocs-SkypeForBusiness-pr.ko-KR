---
title: 'Lync Server 2013: 인증서 요약-자동 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 196b3dacec792097a4760ef134ead91f267a53d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499315"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="e14ce-102">Lync Server 2013의 인증서 요약-자동 검색</span><span class="sxs-lookup"><span data-stu-id="e14ce-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e14ce-103">_**마지막으로 수정 된 항목:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="e14ce-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="e14ce-104">Lync Server 2013 자동 검색 서비스는 디렉터 및 프런트 엔드 풀 서버에서 실행 되며, DNS에 게시 될 때 Lync 클라이언트에서 서버 및 사용자 서비스를 찾는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="e14ce-105">Lync Server 2010에서 업그레이드 하는 중 이며, 모바일을 배포 하지 않은 경우 클라이언트가 자동 검색을 사용할 수 있도록 하려면 모든 디렉터 및 자동 검색 서비스를 실행 하는 프런트 엔드 서버에서 인증서 주체 대체 이름 목록을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="e14ce-106">또한 역방향 프록시에 대한 외부 웹 서비스 게시 규칙에 사용되는 인증서에서도 주체 대체 이름 목록을 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="e14ce-107">역방향 프록시에서 주체 대체 이름 목록을 사용할지 여부에 대 한 결정은 포트 80 또는 포트 443에 자동 검색 서비스를 게시할지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="e14ce-108">**포트 80**     에 게시 됨 포트 80을 통해 자동 검색 서비스에 대 한 초기 쿼리를 수행 하는 경우에는 인증서를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="e14ce-109">Lync를 실행 하는 모바일 장치는 외부에서 포트 80의 역방향 프록시에 액세스 한 다음 내부적으로 포트 8080의 디렉터 또는 프런트 엔드 서버에 브리지 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="e14ce-110">자세한 내용은 [Lync Server 2013에서 모바일 기능에 대 한](lync-server-2013-technical-requirements-for-mobility.md)"포트 80을 사용 하 여 초기 자동 검색 프로세스" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e14ce-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="e14ce-111">**포트 443**     에 게시 됨 외부 웹 서비스 게시 규칙에서 사용 하는 인증서의 주체 대체 이름 목록에는 \*lyncdiscover \<sipdomain\> \* 가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>*</span></span> <span data-ttu-id="e14ce-112">조직 내의 각 SIP 도메인에 대 한 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-112">entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e14ce-113">HTTPS over HTTP를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-113">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="e14ce-114">HTTPS는 인증서를 사용 하 여 트래픽을 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-114">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="e14ce-115">HTTP는 암호화를 제공 하지 않으며 전송 되는 데이터는 일반 텍스트로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-115">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="e14ce-116">내부 인증 기관을 사용 하 여 인증서를 재발급 하는 것은 일반적으로 간단한 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-116">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="e14ce-117">그러나 웹 서비스 게시 규칙에 사용 되는 공용 인증서의 경우 여러 주체 대체 이름 항목을 추가 하는 데 많은 비용이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-117">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="e14ce-118">이 문제를 해결 하려면 포트 80을 통한 초기 자동 검색 연결을 지원 하며, 그러면 디렉터 또는 프런트 엔드 서버의 포트 8080로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-118">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e14ce-119">Lync Server 2013 인프라에서 내부 CA (인증 기관)에서 발급 된 내부 인증서를 사용 하 고 무선으로 연결 되는 모바일 장치를 지원 하려는 경우에는 내부 CA의 루트 인증서 체인을 모바일 장치에 설치 해야 하거나 Lync Server 2013 인프라의 공용 인증서로 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-119">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="e14ce-120">이 항목에서는 디렉터, 프런트 엔드 서버 및 역방향 프록시에 필요한 추가 주체 대체 이름에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-120">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="e14ce-121">추가 된 SAN (주체 대체 이름)만 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-121">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="e14ce-122">인증서의 다른 항목에 대 한 지침은 계획 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e14ce-122">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="e14ce-123">자세한 내용은 Lync server 2013, lync server [2013의 외부 사용자 액세스 시나리오](lync-server-2013-scenarios-for-external-user-access.md)및 [lync server 2013의 역방향 프록시 시나리오](lync-server-2013-scenarios-for-reverse-proxy.md)에서 [디렉터에 대 한](lync-server-2013-scenarios-for-the-director.md)시나리오를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e14ce-123">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="e14ce-124">다음 표에서는 디렉터 풀, 프런트 엔드 풀 및 역방향 프록시에 대 한 자동 검색 SAN 항목을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-124">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="e14ce-125">디렉터 풀 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e14ce-125">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e14ce-126">설명</span><span class="sxs-lookup"><span data-stu-id="e14ce-126">Description</span></span></th>
<th><span data-ttu-id="e14ce-127">주체 대체 이름 항목</span><span class="sxs-lookup"><span data-stu-id="e14ce-127">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e14ce-128">내부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="e14ce-128">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="e14ce-129">SAN = lyncdiscoverinternal. &lt; 내부 도메인 이름&gt;</span><span class="sxs-lookup"><span data-stu-id="e14ce-129">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e14ce-130">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="e14ce-130">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="e14ce-131">SAN = lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="e14ce-131">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e14ce-132">새 SAN 항목을 사용 하 여 새로 업데이트 된 인증서를 기본 인증서에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-132">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="e14ce-133">또는 SAN = \*를 사용할 수 있습니다. &lt; microsoft.rtc.management.xds.sipdomain object &gt;</span><span class="sxs-lookup"><span data-stu-id="e14ce-133">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="e14ce-134">프런트 엔드 풀 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e14ce-134">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e14ce-135">설명</span><span class="sxs-lookup"><span data-stu-id="e14ce-135">Description</span></span></th>
<th><span data-ttu-id="e14ce-136">주체 대체 이름 항목</span><span class="sxs-lookup"><span data-stu-id="e14ce-136">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e14ce-137">내부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="e14ce-137">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="e14ce-138">SAN = lyncdiscoverinternal. &lt; 내부 도메인 이름&gt;</span><span class="sxs-lookup"><span data-stu-id="e14ce-138">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e14ce-139">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="e14ce-139">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="e14ce-140">SAN = lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="e14ce-140">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e14ce-141">새 SAN 항목을 사용 하 여 새로 업데이트 된 인증서를 기본 인증서에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-141">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="e14ce-142">또는 SAN = \*를 사용할 수 있습니다. &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="e14ce-142">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="e14ce-143">역방향 프록시(공용 CA) 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e14ce-143">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e14ce-144">설명</span><span class="sxs-lookup"><span data-stu-id="e14ce-144">Description</span></span></th>
<th><span data-ttu-id="e14ce-145">주체 대체 이름 항목</span><span class="sxs-lookup"><span data-stu-id="e14ce-145">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e14ce-146">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="e14ce-146">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="e14ce-147">SAN = lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="e14ce-147">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e14ce-148">새 SAN 항목을 사용 하 여 새로 업데이트 된 인증서를 역방향 프록시의 SSL 수신기에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e14ce-148">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

