---
title: 'Lync Server 2013: 인증서 요약-자동 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c3777f9b13dc18e3e52e80120009f93c20db3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="a9b97-102">인증서 요약-Lync Server 2013의 자동 검색</span><span class="sxs-lookup"><span data-stu-id="a9b97-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9b97-103">_**마지막으로 수정한 주제:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="a9b97-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="a9b97-104">Lync Server 2013 자동 검색 서비스는 디렉터 및 프런트 엔드 풀 서버에서 실행 되며 DNS에 게시 되는 경우 Lync 클라이언트에서 서버 및 사용자 서비스를 찾을 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="a9b97-105">Lync Server 2010에서 업그레이드 하는 경우 클라이언트가 자동 검색을 사용 하도록 설정 하기 전에, 클라이언트에 대 한 대체 서비스를 실행 하는 프런트 엔드 서버와 디렉터에 대 한 인증서 주체 대체 이름 목록을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="a9b97-106">또한 역방향 프록시에서 외부 웹 서비스 게시 규칙에 사용 되는 인증서의 주체 대체 이름 목록을 수정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="a9b97-107">리버스 프록시에서 주체 대체 이름 목록을 사용할지 여부에 대 한 결정은 포트 80 또는 포트 443에 자동 검색 서비스를 게시할지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="a9b97-108">**포트 80**   에 게시 된 자동 검색 서비스에 대 한 초기 쿼리가 포트 80를 통해 발생 하는 경우 인증서 변경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="a9b97-109">Lync를 실행 하는 모바일 장치는 포트 80의 역방향 프록시에 액세스 한 다음 내부적으로 포트 8080의 디렉터 또는 프런트 엔드 서버에 브리지 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="a9b97-110">자세한 내용은 [Lync Server 2013의 이동성에 대 한 기술 요구 사항](lync-server-2013-technical-requirements-for-mobility.md)"포트 80를 사용 하 여 초기 자동 검색 프로세스" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9b97-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="a9b97-111">**포트 443**   에 게시 됨 외부 웹 서비스 게시 규칙에 사용 되는 인증서의 주체 대체 이름 목록에는 \*lyncdiscover을\< 포함 해야 합니다. 조직\> \* 내 각 SIP 도메인에 대 한 sipdomain 항목.</span><span class="sxs-lookup"><span data-stu-id="a9b97-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a9b97-112">HTTP를 통해 HTTPS를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="a9b97-113">HTTPS는 인증서를 사용 하 여 트래픽을 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="a9b97-114">HTTP는 암호화를 제공 하지 않으며 전송 되는 모든 데이터는 일반 텍스트로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="a9b97-115">내부 인증 기관을 사용 하 여 인증서를 재발급 하는 것은 일반적으로 간단한 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="a9b97-116">그러나 웹 서비스 게시 규칙에 사용 되는 공개 인증서의 경우 여러 주체의 대체 이름 항목을 추가 하는 데 많은 비용이 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="a9b97-117">이 문제를 해결 하려면 포트 80을 통한 초기 자동 검색 연결을 지원 하 고, 그런 다음 디렉터 또는 프런트 엔드 서버의 포트 8080로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a9b97-118">Lync Server 2013 인프라에서 내부 CA (인증 기관)에서 발급 한 내부 인증서를 사용 하는 경우 무선으로 연결 되는 모바일 장치를 지원 하려면 내부 CA의 루트 인증서 체인을 설치 해야 합니다. 모바일 장치에서 또는 Lync Server 2013 인프라에서 공용 인증서로 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="a9b97-119">이 항목에서는 디렉터, 프런트 엔드 서버 및 리버스 프록시에 필요한 추가 된 제목 대체 이름에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="a9b97-120">추가 된 SAN (주체 대체 이름)만 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="a9b97-121">인증서의 다른 항목에 대 한 지침은 계획 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9b97-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="a9b97-122">자세한 내용은 lync [server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md), [lync server 2013에서 외부 사용자 액세스를 위한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)및 [lync server 2013의 리버스 프록시](lync-server-2013-scenarios-for-reverse-proxy.md)에 대 한 시나리오를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9b97-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="a9b97-123">다음 표에서는 디렉터 풀, 프런트 엔드 풀 및 역방향 프록시에 대 한 자동 검색 SAN 항목을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="a9b97-124">디렉터 풀 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9b97-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b97-125">설명</span><span class="sxs-lookup"><span data-stu-id="a9b97-125">Description</span></span></th>
<th><span data-ttu-id="a9b97-126">주체 대체 이름 항목</span><span class="sxs-lookup"><span data-stu-id="a9b97-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b97-127">내부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="a9b97-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="a9b97-128">SAN = lyncdiscoverinternal. &lt;내부 도메인 이름&gt;</span><span class="sxs-lookup"><span data-stu-id="a9b97-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b97-129">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="a9b97-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="a9b97-130">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a9b97-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a9b97-131">새 SAN 항목을 사용 하 여 새로 업데이트 한 인증서를 기본 인증서에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="a9b97-132">또는 SAN = \*를 사용할 수 있습니다. &lt;sipdomain&gt;.</span><span class="sxs-lookup"><span data-stu-id="a9b97-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="a9b97-133">프런트 엔드 풀 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9b97-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b97-134">설명</span><span class="sxs-lookup"><span data-stu-id="a9b97-134">Description</span></span></th>
<th><span data-ttu-id="a9b97-135">주체 대체 이름 항목</span><span class="sxs-lookup"><span data-stu-id="a9b97-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b97-136">내부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="a9b97-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="a9b97-137">SAN = lyncdiscoverinternal. &lt;내부 도메인 이름&gt;</span><span class="sxs-lookup"><span data-stu-id="a9b97-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9b97-138">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="a9b97-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="a9b97-139">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a9b97-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a9b97-140">새 SAN 항목을 사용 하 여 새로 업데이트 한 인증서를 기본 인증서에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="a9b97-141">또는 SAN = \*를 사용할 수 있습니다. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a9b97-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="a9b97-142">역방향 프록시 (공개 CA) 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9b97-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9b97-143">설명</span><span class="sxs-lookup"><span data-stu-id="a9b97-143">Description</span></span></th>
<th><span data-ttu-id="a9b97-144">주체 대체 이름 항목</span><span class="sxs-lookup"><span data-stu-id="a9b97-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9b97-145">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="a9b97-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="a9b97-146">SAN = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a9b97-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a9b97-147">새 SAN 항목을 사용 하 여 새로 업데이트 된 인증서를 리버스 프록시의 SSL 수신기에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b97-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

