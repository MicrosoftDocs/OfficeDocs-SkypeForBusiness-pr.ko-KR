---
title: 'Lync Server 2013: DNS 요구 사항 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine DNS requirements
ms:assetid: 95777017-6282-44c0-a685-f246af0501b4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398758(v=OCS.15)
ms:contentKeyID: 48184839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79f1c27f48beddd0c1fd3260193a71bb79b034bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="2cd66-102">Lync Server 2013에 대 한 DNS 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="2cd66-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cd66-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2cd66-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2cd66-104">다음 순서도를 사용하여 DNS(Domain Name System) 요구 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="2cd66-105">Lync Server 2013의 누적 업데이트에 대 한 변경 사항: 적용 되는 위치에는 2 월 2013이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2cd66-106">Microsoft Lync Server 2013는 IPv6 주소 지정 사용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="2cd66-107">또한 IPv6 주소를 사용 하려면 IPv6 DNS에 대 한 지원을 제공 하 고 DNS 호스트 AAAA ("쿼드-A") 레코드를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="2cd66-108">IPv4와 IPv6을 모두 사용 하는 배포에서는 IPv4 용 호스트 A 레코드와 i p v 6 용 호스트를 모두 구성 하 고 유지 관리 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="2cd66-109">배포가 IPv6으로 완전히 전환 된 경우에도 외부 사용자가 IPv4를 계속 사용 하는 경우에는 IPv4 DNS 호스트 레코드가 여전히 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="2cd66-110">**DNS 요구 사항 확인 순서도**</span><span class="sxs-lookup"><span data-stu-id="2cd66-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="2cd66-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="2cd66-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2cd66-112">기본적으로 도메인에 가입 되지 않은 컴퓨터의 컴퓨터 이름은 FQDN (정규화 된 도메인 이름)이 아닌 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="2cd66-113">토폴로지 작성기는 호스트 이름이 아닌 Fqdn을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="2cd66-114">따라서 도메인이 가입되지 않은 에지 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="2cd66-115">Lync Server, 에지 서버 및 풀의 FQDN을 지정할 때는 <STRONG>표준 문자</STRONG>(A-Z, a-z, 0-9 및 하이픈 포함)만 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="2cd66-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="2cd66-116">유니코드 문자나 밑줄을 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2cd66-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="2cd66-117">FQDN의 비표준 문자는 외부 DNS 및 공용 CA에서 지원되지 않는 경우가 많습니다(인증서의 SN에 FQDN을 할당해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="2cd66-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="2cd66-118">자세한 내용은 <A href="lync-server-2013-configure-dns-host-records.md">CONFIGURE DNS Host records For Lync Server 2013</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2cd66-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="2cd66-119">Lync 클라이언트가 서비스를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="2cd66-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="2cd66-120">Microsoft Lync 2010, Lync 2013 및 Lync Mobile은 클라이언트가 Lync Server 2013에서 서비스를 찾고 액세스 하는 방법과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="2cd66-121">중요 한 예외는 다른 서비스 위치 프로세스를 사용 하는 Lync Windows 스토어 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="2cd66-122">이 섹션에서는 클라이언트에서 서비스를 찾는 방법과 먼저 자동 검색 서비스 레코드만을 사용 하 여 일련의 SRV 및 호스트 레코드를 사용 하는 전통적인 방법을 보여 주는 두 가지 시나리오에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="2cd66-123">데스크톱 클라이언트에 대 한 누적 업데이트 모든 클라이언트에 대해 Lync Server 2010의 DNS 위치 프로세스를 변경 하거나, 쿼리 프로세스가 성공적으로 반환 되거나, 가능한 DNS 레코드 목록이 고갈 되며, 최종 오류가 반환 됩니다. 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="2cd66-124">DNS 조회 중에 Lync Windows 스토어 앱을 **제외한** 모든 클라이언트에 대해 SRV 레코드를 쿼리하여 다음 순서 대로 클라이언트에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="2cd66-125">lyncdiscoverinternal. \<내부\> 웹 서비스의 자동 검색 서비스에 대 한 도메인 A (호스트) 레코드</span><span class="sxs-lookup"><span data-stu-id="2cd66-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="2cd66-126">lyncdiscover. \<외부\> 웹 서비스의 자동 검색 서비스에 대 한 도메인 A (호스트) 레코드</span><span class="sxs-lookup"><span data-stu-id="2cd66-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="2cd66-127">\_sipinternaltls. \_tcp를 \<내부\> TLS 연결에 대 한 도메인 SRV (서비스 로케이터) 레코드</span><span class="sxs-lookup"><span data-stu-id="2cd66-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="2cd66-128">\_sipinternal. \_tcp를 \<내부\> tcp 연결에 대 한 도메인 SRV (서비스 로케이터) 레코드 (TCP가 허용 되는 경우에만 수행 됨)</span><span class="sxs-lookup"><span data-stu-id="2cd66-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="2cd66-129">\_호흡. \_tls \<외부\> TLS 연결에 대 한 도메인 SRV (서비스 로케이터) 레코드</span><span class="sxs-lookup"><span data-stu-id="2cd66-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="2cd66-130">sipinternal. \<프런트\> 엔드 풀 또는 디렉터에 대 한 도메인 A (호스트) 레코드 (내부 네트워크 에서만 확인할 때)</span><span class="sxs-lookup"><span data-stu-id="2cd66-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="2cd66-131">호흡. \<내부\> 네트워크의 프런트 엔드 풀 또는 디렉터에 대 한 도메인 A (호스트) 레코드 또는 클라이언트가 외부에 있는 경우 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="2cd66-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="2cd66-132">sipexternal. \<클라이언트가\> 외부에 있는 경우 액세스에 지 서비스에 대 한 도메인 A (호스트) 레코드</span><span class="sxs-lookup"><span data-stu-id="2cd66-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="2cd66-133">Lync Windows 스토어 앱은 두 개의 레코드를 사용 하므로 프로세스를 완전히 변경 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="2cd66-134">lyncdiscoverinternal. \<내부\> 웹 서비스의 자동 검색 서비스에 대 한 도메인 A (호스트) 레코드</span><span class="sxs-lookup"><span data-stu-id="2cd66-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="2cd66-135">lyncdiscover. \<외부\> 웹 서비스의 자동 검색 서비스에 대 한 도메인 A (호스트) 레코드</span><span class="sxs-lookup"><span data-stu-id="2cd66-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="2cd66-136">다른 레코드 종류에 대 한 대체 기능은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="2cd66-137">이전 클라이언트와 비교 하 여 최신 클라이언트에 사용 되는 방법의 차이점은 자동 검색 서비스가 모든 서비스를 찾기 위한 기본 방법이 되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="2cd66-138">연결에 성공 하면 자동 검색 서비스가 모바일 서비스 (IIS의 서비스에 대해 생성 된 가상 디렉터리를 통해 Mcx로 알려짐), Microsoft Lync Web App 및 웹 스케줄러 Url을 포함 하 여 사용자의 홈 풀에 대 한 모든 웹 서비스 Url을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="2cd66-139">그러나 내부 모바일 서비스 URL과 외부 모바일 서비스 URL 둘 다 외부 웹 서비스 FQDN에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="2cd66-140">따라서 모바일 장치는 네트워크 내부에 있든 외부에 있든 관계없이 항상 역방향 프록시를 통해 외부적으로 Mobility Service에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="2cd66-141">Lync Server 2013 2013에 대 한 누적 업데이트가 설치 된 경우에는 자동 검색 서비스에서 내부/일부 WA, External/UPWA 및 기타 wa에 대 한 참조도 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="2cd66-142">이러한 항목은 UCWA(통합 커뮤니케이션 웹 API) 웹 구성 요소를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="2cd66-143">현재로 서는 entry를 사용 해야 하며 웹 구성 요소의 URL에 대 한 참조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="2cd66-144">(C)는 Lync 2010 모바일 클라이언트에서 사용 하는 Mcx Mobility Service 대신 Lync 2013 모바일 클라이언트에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cd66-145">SRV 레코드를 만들 때 DNS SRV 레코드를 만들 때와 동일한 도메인에 있는 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드를 가리켜야 한다는 점을 기억해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="2cd66-146">예를 들어 SRV 레코드가 contoso.com에 있는 경우 A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드는 fabrikam.com에 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="2cd66-147">기본 구성은 모든 모바일 클라이언트 트래픽을 외부 사이트를 통해 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="2cd66-148">필요한 경우 내부 URL만 반환 하도록 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="2cd66-149">이 구성을 사용 하면 사용자가 회사 네트워크 내에 있는 경우에만 모바일 장치에서 Lync 모바일 응용 프로그램을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="2cd66-150">이 구성을 정의 하려면 <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="2cd66-151">모바일 응용 프로그램 에서도 주소록 서비스와 같은 다른 Lync Server 2013 서비스에 연결할 수 있지만 내부 모바일 응용 프로그램 웹 요청은 모바일 서비스에 대 한 외부 웹 FQDN으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="2cd66-152">주소록 요청 등의 다른 서비스 요청에는 이 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="2cd66-153">모바일 장치는 수동 서비스 검색을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-153">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="2cd66-154">이 경우 각 사용자는 프로토콜과 경로를 포함하여 전체 내부/외부 자동 검색 서비스 URI로 모바일 장치 설정을 다음과 같이 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-154">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="2cd66-155">외부\<액세스용 Https://extpoolfqdn\>https://</span><span class="sxs-lookup"><span data-stu-id="2cd66-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="2cd66-156">내부\<액세스용 Https://intpoolfqdn\>https://</span><span class="sxs-lookup"><span data-stu-id="2cd66-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="2cd66-157">수동 검색 대신 자동 검색을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="2cd66-158">그러나 수동 설정은 모바일 장치 연결 문제를 해결 하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="2cd66-159">Lync Server를 사용 하 여 분할 된 DNS 구성</span><span class="sxs-lookup"><span data-stu-id="2cd66-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="2cd66-160">분할 DNS 또는 분할 된 dns와 같은 여러 가지 이름으로 DNS를 사용 하는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-160">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="2cd66-161">간단히 말하자면 네임 스페이스가 같은 dns 영역이 두 개 있지만 DNS 영역 서비스 내부 요청만 있고 다른 DNS 영역은 외부 전용 요청을 사용 하는 DNS 구성에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-161">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="2cd66-162">그러나 내부 DNS에 포함된 많은 DNS SRV 및 A 레코드가 외부 DNS에는 포함되지 않으며, 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-162">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="2cd66-163">내부 및 외부 DNS 둘 다에 동일한 DNS 레코드가 있는 경우 (예: www.contoso.com) 반환 되는 IP 주소는 쿼리 시작 위치 (내부 또는 외부)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-163">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2cd66-164">현재는 모바일 기능에 대 한 분할을 지원 하지 않으며, 더 구체적으로는 LLyncDiscoverInternal Cdiscover 및 DNS 레코드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-164">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="2cd66-165">LLyncDiscoverInternal Cdiscover는 외부 DNS 서버에서 정의 해야 하며, 내부 DNS 서버에서를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-165">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="2cd66-166">이러한 항목을 위해 분할 된 DNS 라는 용어를 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="2cd66-167">분할 DNS를 구성하는 경우 다음 내부 및 외부 영역에 각 영역에서 필요한 DNS 레코드 유형에 대한 요약이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="2cd66-168">자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2cd66-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="2cd66-169">**내부 DNS**</span><span class="sxs-lookup"><span data-stu-id="2cd66-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="2cd66-170">신뢰할 수 있는 contoso.com이라는 DNS 영역을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="2cd66-171">내부 contoso.com 영역에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="2cd66-172">DNS A 및 AAAA (IPv6 주소 지정을 사용 하는 경우) 및 내부 Lync Server 2013 클라이언트 자동 구성에 대 한 SRV 레코드 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="2cd66-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="2cd66-173">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 또는 Lync Server 2013 웹 서비스의 자동 검색을 위한 CNAME 레코드 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="2cd66-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="2cd66-174">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 프런트 엔드 풀 이름, 디렉터 또는 디렉터 풀 이름에 대 한 레코드 및 회사 네트워크에서 Lync Server 2013을 실행 하는 모든 내부 서버</span><span class="sxs-lookup"><span data-stu-id="2cd66-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="2cd66-175">경계 네트워크에 있는 각 Lync Server 2013,에 지 서버의에 지 내부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드</span><span class="sxs-lookup"><span data-stu-id="2cd66-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="2cd66-176">경계 네트워크에 있는 각 역방향 프록시 서버의 내부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드 (역방향 프록시 관리를 위해 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="2cd66-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="2cd66-177">경계 네트워크의 모든 Lync Server 2013에 지 서버 내부에 지 인터페이스 contoso.com에 대 한 쿼리 확인을 위해 내부 DNS 영역 사용</span><span class="sxs-lookup"><span data-stu-id="2cd66-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="2cd66-178">Lync Server 2013을 실행 하는 모든 서버 및 회사 네트워크에서 Lync 2013를 실행 하는 클라이언트는 contoso.com에 대 한 쿼리를 확인 하거나 각에 지 서버에서 호스트 파일을 사용 하 고 목록 A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드를 수신 하는 내부 DNS 서버를 가리킵니다. 다음 홉 서버, 특히 디렉터 또는 디렉터 VIP, 프런트 엔드 풀 VIP 또는 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="2cd66-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="2cd66-179">**외부 DNS**</span><span class="sxs-lookup"><span data-stu-id="2cd66-179">**External DNS:**</span></span>

  - <span data-ttu-id="2cd66-180">신뢰할 수 있는 contoso.com이라는 DNS 영역을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="2cd66-181">외부 contoso.com 영역에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="2cd66-182">DNS A 및 AAAA (IPv6 주소 지정을 사용 하는 경우) 및 Lync Server 2013 클라이언트 자동 구성에 대 한 SRV 레코드 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="2cd66-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="2cd66-183">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 또는 모바일 기능에 사용할 Lync Server 2013 웹 서비스의 자동 검색을 위한 CNAME 레코드</span><span class="sxs-lookup"><span data-stu-id="2cd66-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="2cd66-184">경계 네트워크에 있는 각 Lync Server 2013,에 지 서버 또는 하드웨어 부하 분산 장치 VIP (가상 IP)의에 지 외부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="2cd66-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="2cd66-185">경계 네트워크에 있는 역방향 프록시 서버의 풀에 대 한 역방향 프록시 서버 또는 VIP의 외부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드</span><span class="sxs-lookup"><span data-stu-id="2cd66-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="2cd66-186">분할 DNS를 사용하지 않는 자동 구성</span><span class="sxs-lookup"><span data-stu-id="2cd66-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="2cd66-187">내부 DNS 영역에 \_sipinternaltls가 포함 되어 있는 경우 내부적으로 로그인 하는 Lync Server 2013 사용자는 자동 구성을 활용할 수 있습니다. \_사용 중인 각 SIP 도메인에 대 한 tcp SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="2cd66-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="2cd66-188">그러나 분할 하지 않은 DNS를 사용 하지 않는 경우에는이 섹션의 뒷부분에 설명 된 해결 방법 중 하나를 구현 하지 않으면 Lync를 실행 하는 클라이언트의 내부 자동 구성이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="2cd66-189">이는 Lync Server 2013에서 자동 구성에 지정 된 프런트 엔드 풀의 도메인에 사용자의 SIP URI가 일치 해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="2cd66-190">이전 버전의 Communicator와 함께 사용 되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="2cd66-191">예를 들어 두 개의 SIP 도메인을 사용 중인 경우 다음 DNS 서비스(SRV) 레코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="2cd66-192">사용자가 bob@contoso.com으로 로그인 하는 경우 사용자의 SIP 도메인 (contoso.com)이 자동 구성 프런트 엔드 풀의 도메인과 일치 하기 때문에 다음 SRV 레코드는 자동 구성에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="2cd66-193">\_sipinternaltls. \_tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="2cd66-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="2cd66-195">사용자가 alice@fabrikam.com로 로그인 하는 경우 다음 DNS SRV 레코드는 두 번째 SIP 도메인의 자동 구성에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="2cd66-196">\_sipinternaltls. \_tcp.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="2cd66-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="2cd66-198">비교를 위해 사용자가 tim@litwareinc.com로 로그인 하는 경우 클라이언트의 SIP 도메인 (litwareinc.com)이 해당 풀이 있는 도메인 (fabrikam.com)과 일치 하지 않으므로 다음 DNS SRV 레코드는 자동 구성에 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="2cd66-199">\_sipinternaltls. \_tcp.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="2cd66-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="2cd66-201">Lync를 실행 하는 클라이언트에 대해 자동 구성이 필요한 경우에는 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="2cd66-202">**그룹 정책 개체**   는 gpo (그룹 정책 개체)를 사용 하 여 올바른 서버 값을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2cd66-203">이 옵션은 자동 구성을 사용하지 않도록 설정하지만 수동 구성 프로세스를 자동화하므로 이 접근 방법을 사용할 경우 자동 구성과 연결된 SRV 레코드가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="2cd66-204">**일치 하는 내부 영역**   내부 dns에 외부 dns 영역 (예: contoso.com)과 일치 하는 영역을 만들고 자동 구성에 사용 되는 Lync Server 2013 풀에 해당 하는 dns a 및 AAAA (IPv6 주소를 사용 하는 경우)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="2cd66-205">예를 들어 사용자가 pool01.contoso.net에 있고 Lync에 bob@contoso.com에 로그인 하는 경우 contoso.com 라는 내부 DNS 영역을 만들고 pool01.contoso.com에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="2cd66-206">**핀 포인트 내부 영역**   내부 DNS에 전체 영역을 만드는 경우에는 자동 구성에 필요한 SRV 레코드에 해당 하는 pin 포인트 (즉, 전용) 영역을 만들고 해당 영역을 dnscmd을 사용 하 여 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="2cd66-207">Dnscmd.exe는 DNS 사용자 인터페이스가 핀 포인트 영역 만들기를 지원하지 않기 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="2cd66-208">예를 들어 SIP 도메인이 contoso.com이고 두 개의 프런트 엔드 서버가 포함된 pool01이라는 프런트 엔드 풀이 있는 경우 내부 DNS에 다음 핀 포인트 영역과 A 레코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="2cd66-209">환경에 두 번째 SIP 도메인(예: fabrikam.com)이 있는 경우 내부 DNS에 다음 핀 포인트 영역과 A 레코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="2cd66-p121">프런트 엔드 풀 FQDN이 두 번 나타나지만 서로 다른 IP 주소를 사용합니다. 이는 DNS 부하 분산이 사용되지만 하드웨어 부하 분산이 사용되는 경우 프런트 엔드 풀 항목이 하나만 있기 때문입니다. 또한 프런트 엔드 풀 FQDN 값은 contoso.com 예와 fabrikam.com 예 간에 변경되지만 IP 주소는 동일하게 유지됩니다. 이는 SIP 도메인에서 로그인한 사용자가 자동 구성에 동일한 프런트 엔드 풀을 사용하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-p121">The Front End pool FQDN appears twice, but with two different IP addresses. This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry. Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same. This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="2cd66-214">자세한 내용은 DMTF 블로그 문서 "Communicator 자동 구성 및 분할-두뇌 DNS"를 참조 [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707)하세요.</span><span class="sxs-lookup"><span data-stu-id="2cd66-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cd66-215">각 블로그의 콘텐츠와 해당 URL은 사전 통지 없이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="2cd66-216">재해 복구를 위한 DNS (domain name system) 구성</span><span class="sxs-lookup"><span data-stu-id="2cd66-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="2cd66-217">Lync Server 2013 웹 트래픽을 재해 복구 및 장애 조치 사이트로 리디렉션하도록 DNS를 구성 하려면 GeoDNS를 지 원하는 DNS 공급자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="2cd66-218">전체 프런트 엔드 풀 하나가 다운 되더라도 웹 서비스를 사용 하는 기능이 계속 작동 하도록 재해 복구를 지원 하도록 웹에 대 한 DNS 레코드를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="2cd66-219">이 재해 복구 기능은 자동 검색 (Lyncdiscover URL), 모임 및 전화 접속 단순 Url을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="2cd66-220">GeoDNS 공급자에서 웹 서비스의 내부 및 외부 확인에 대 한 추가 DNS 호스트 (A 및 i p v을 사용 하는 경우 A 및 AAAA) 레코드를 정의 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-220">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="2cd66-221">다음은 라운드 로빈 DNS를 사용 하 여 공급자가 지 원하는 연결 된 풀, 지리적으로 분산 및 GeoDNS를 Pool1)으로 기본 설정으로 구성 하 고 통신 손실 또는 하드웨어 오류 발생 시 호스트인로 장애 조치 (failover) 하는 경우를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-221">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cd66-222">GeoDNS 레코드 (예제)</span><span class="sxs-lookup"><span data-stu-id="2cd66-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="2cd66-223">풀 레코드 (예제)</span><span class="sxs-lookup"><span data-stu-id="2cd66-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="2cd66-224">CNAME 레코드 (예제)</span><span class="sxs-lookup"><span data-stu-id="2cd66-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="2cd66-225">DNS 설정 (한 옵션 선택)</span><span class="sxs-lookup"><span data-stu-id="2cd66-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cd66-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-229">Meet.contoso.com 별칭을 Pool1InternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-230">Meet.contoso.com 별칭을 Pool2InternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-231">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="2cd66-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="2cd66-232">보조를 사용 합니다 (예를 들어, 오류가 발생 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="2cd66-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cd66-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-236">Meet.contoso.com 별칭을 Pool1ExternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-237">Meet.contoso.com 별칭을 Pool2ExternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-238">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="2cd66-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="2cd66-239">보조를 사용 합니다 (예를 들어, 오류가 발생 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="2cd66-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cd66-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-243">Dialin.contoso.com 별칭을 Pool1InternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-244">Dialin.contoso.com 별칭을 Pool2InternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-245">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="2cd66-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="2cd66-246">보조를 사용 합니다 (예를 들어, 오류가 발생 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="2cd66-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cd66-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-250">Dialin.contoso.com 별칭을 Pool1ExternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-251">Dialin.contoso.com 별칭을 Pool2ExternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-252">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="2cd66-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="2cd66-253">보조를 사용 합니다 (예를 들어, 오류가 발생 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="2cd66-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cd66-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-257">Lyncdiscoverinternal.contoso.com 별칭을 Pool1InternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-258">Lyncdiscoverinternal.contoso.com 별칭을 Pool2InternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-259">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="2cd66-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="2cd66-260">보조를 사용 합니다 (예를 들어, 오류가 발생 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="2cd66-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cd66-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-264">Lyncdiscover.contoso.com 별칭을 Pool1ExternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-265">Lyncdiscover.contoso.com 별칭을 Pool2ExternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-266">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="2cd66-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="2cd66-267">보조를 사용 합니다 (예를 들어, 오류가 발생 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="2cd66-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cd66-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-271">Scheduler.contoso.com 별칭을 Pool1InternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-272">Scheduler.contoso.com 별칭을 Pool2InternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-273">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="2cd66-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="2cd66-274">보조를 사용 합니다 (예를 들어, 오류가 발생 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="2cd66-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cd66-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cd66-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-278">Scheduler.contoso.com 별칭을 Pool1ExternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="2cd66-279">Scheduler.contoso.com 별칭을 Pool2ExternalWebFQDN.contoso.com로</span><span class="sxs-lookup"><span data-stu-id="2cd66-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cd66-280">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="2cd66-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="2cd66-281">보조를 사용 합니다 (예를 들어, 오류가 발생 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="2cd66-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="2cd66-282">DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="2cd66-282">DNS Load Balancing</span></span>

<span data-ttu-id="2cd66-283">DNS 부하 분산은 일반적으로 응용 프로그램 수준에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="2cd66-284">Lync를 실행 하는 클라이언트와 같은 응용 프로그램은 풀 FQDN (정규화 된 도메인 이름)에 대해 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드 쿼리를 통해 반환 된 IP 주소 중 하나에 연결 하 여 풀의 서버에 연결을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="2cd66-285">예를 들어 pool01.contoso.com이라는 풀에 세 개의 프런트 엔드 서버가 있는 경우 다음과 같은 상황이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="2cd66-286">Pool01.contoso.com 용 Lync 쿼리 DNS를 실행 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="2cd66-287">쿼리는 IP 주소를 3 개 반환 하 고 다음과 같이 캐시 합니다 (이 순서에 해당 하지 않을 수도 있습니다).</span><span class="sxs-lookup"><span data-stu-id="2cd66-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="2cd66-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="2cd66-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="2cd66-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="2cd66-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="2cd66-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="2cd66-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="2cd66-291">클라이언트가 IP 주소 중 하나에 대 한 TCP (전송 제어 프로토콜) 연결을 설정 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="2cd66-292">연결에 실패하면 캐시의 다음 IP 주소에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="2cd66-293">TCP 연결이 성공 하면 클라이언트는 TLS를 협상 하 여 pool01.contoso.com의 기본 등록자에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="2cd66-294">성공적인 연결 없이 모든 캐시 된 항목을 클라이언트에서 시도 하면 Lync Server 2013을 실행 하는 서버를 현재 사용할 수 없다는 메시지가 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2cd66-295">DNS 기반 부하 분산은 일반적으로 DNS를 사용 하 여 풀의 서버에 해당 하는 다른 IP 주소 순서를 제공 하는 부하 분산을 지칭 하는 DNS (라운드 로빈)와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="2cd66-296">일반적으로 DNS RR은 부하 배포를 허용 하지만 장애 조치 (failover)를 사용 하도록 설정 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="2cd66-297">예를 들어 DNS A와 AAAA (IPv6 주소 지정을 사용 하는 경우)가 반환한 IP 주소에 대 한 연결이 실패 하면 연결이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="2cd66-298">따라서 dns 라운드 로빈 자체는 DNS 기반 부하 분산 보다 안정성이 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="2cd66-299">Dns 부하 분산과 함께 DNS 라운드 로빈을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="2cd66-300">DNS 부하 분산은 다음에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="2cd66-301">서버 간 SIP를에 지 서버에 대 한 부하 분산</span><span class="sxs-lookup"><span data-stu-id="2cd66-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="2cd66-302">회의 자동 길잡이, 응답 그룹 및 통화 대기와 같은 UCAS(Unified Communications Application Services) 응용 프로그램 부하 분산</span><span class="sxs-lookup"><span data-stu-id="2cd66-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="2cd66-303">UCAS 응용 프로그램에 대한 새 연결 방지("드레이닝"이라고도 함)</span><span class="sxs-lookup"><span data-stu-id="2cd66-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="2cd66-304">클라이언트와 에지 서버 간의 모든 클라이언트-서버 트래픽 부하 분산</span><span class="sxs-lookup"><span data-stu-id="2cd66-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="2cd66-305">DNS 부하 분산은 다음에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="2cd66-306">디렉터 또는 프런트 엔드 서버에 대 한 클라이언트-서버 웹 트래픽</span><span class="sxs-lookup"><span data-stu-id="2cd66-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="2cd66-307">DNS 부하 분산 및 페더레이션 트래픽</span><span class="sxs-lookup"><span data-stu-id="2cd66-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="2cd66-308">DNS SRV 쿼리에서 여러 DNS 레코드를 반환 하는 경우 액세스에 지 서비스는 항상 우선 순위가 가장 낮은 DNS SRV 레코드와 가장 높은 숫자 가중치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="2cd66-309">인터넷 엔지니어링 작업 강제 문서 "서비스 위치를 지정 하는 DNS RR (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt> 은 정의 된 dns srv 레코드가 여러 개 있는 경우 우선 순위를 먼저 사용한 다음 가중치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="2cd66-310">예를 들어 DNS SRV 레코드 A의 가중치는 20이 고 우선 순위는 40이 고 DNS SRV 레코드 B의 가중치는 10이 고 우선 순위는 50입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="2cd66-311">우선 순위가 40 인 DNS SRV 레코드 A가 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="2cd66-312">DNS SRV 레코드 선택에는 다음과 같은 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="2cd66-313">우선 순위가 가장 먼저 고려 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-313">Priority is considered first.</span></span> <span data-ttu-id="2cd66-314">클라이언트는 DNS SRV 레코드에 정의 된 대상 호스트에 연결 하 여 연결할 수 있는 가장 낮은 우선 순위의 연결을 시도해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="2cd66-315">우선 순위가 같은 대상은 가중치 필드에 정의 된 순서 대로 시도해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="2cd66-316">Weight 필드는 우선 순위가 같은 항목에 대 한 상대적 가중치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="2cd66-317">가중치를 더 많이 지정 하려면 선택 하는 확률이 더 높은 것을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="2cd66-318">DNS 관리자는 어떤 서버에서 작업을 선택 하지 않은 경우 가중치 0을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="2cd66-319">가중치가 0 보다 큰 레코드가 있으면 가중치가 0 인 레코드는 선택 하기에 매우 적게 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="2cd66-320">우선 순위와 가중치가 같은 여러 DNS SRV 레코드가 반환 되 면 액세스에 지 서비스가 DNS 서버에서 먼저 받은 SRV 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd66-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

