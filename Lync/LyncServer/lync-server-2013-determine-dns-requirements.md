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
ms.openlocfilehash: fd8c1c95c3b8ba3671735447f098eca9173111ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-dns-requirements-for-lync-server-2013"></a><span data-ttu-id="5873c-102">Lync Server 2013에 대한 DNS 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="5873c-102">Determine DNS requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5873c-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="5873c-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="5873c-104">다음 순서도를 사용 하 여 DNS (Domain Name System) 요구 사항을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-104">Use the following flow chart to determine Domain Name System (DNS) requirements.</span></span> <span data-ttu-id="5873c-105">Lync Server 2013의 누적 업데이트에 대 한 변경 사항: 적용 되는 위치에는 2 월 2013이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-105">Changes for the Cumulative Updates for Lync Server 2013: February 2013 are noted where they apply.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5873c-106">Microsoft Lync Server 2013는 IPv6 주소 지정 사용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-106">Microsoft Lync Server 2013 supports the use of IPv6 addressing.</span></span> <span data-ttu-id="5873c-107">IPv6 주소를 사용 하려면 IPv6 DNS에 대 한 지원도 제공 하 고 DNS 호스트 AAAA ("쿼드 A") 레코드를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-107">To use IPv6 addresses, you must also provide support for IPv6 DNS and configure DNS host AAAA (known as “quad-A”) records.</span></span> <span data-ttu-id="5873c-108">IPv4 및 IPv6을 모두 사용 하는 배포에서 IPv4 용 호스트 A 레코드와 IPv6 용 호스트 AAAA를 모두 구성 하 고 유지 관리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-108">In deployments where both IPv4 and IPv6 are being used, it is best to configure and maintain both host A records for IPv4 and host AAAA for IPv6.</span></span> <span data-ttu-id="5873c-109">배포가 IPv6으로 완전히 전환 된 경우에도 외부 사용자가 IPv4를 계속 사용 중인 경우에는 IPv4 DNS 호스트 레코드가 계속 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-109">Even if your deployment has transitioned fully to IPv6, IPv4 DNS host records may still be required when external users are still using IPv4.</span></span>



</div>

<span data-ttu-id="5873c-110">**DNS 요구 사항 확인 순서도**</span><span class="sxs-lookup"><span data-stu-id="5873c-110">**Determining DNS Requirements Flow Chart**</span></span>

<span data-ttu-id="5873c-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span><span class="sxs-lookup"><span data-stu-id="5873c-111">![175782ac-363e-408a-912f-8991bf152970](images/Gg398758.175782ac-363e-408a-912f-8991bf152970(OCS.15).jpg "175782ac-363e-408a-912f-8991bf152970")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5873c-112">기본적으로 도메인에 연결 되지 않은 컴퓨터의 컴퓨터 이름은 FQDN (정규화 된 도메인 이름)이 아닌 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-112">By default the computer name of a computer that is not joined to a domain is a host name, not a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="5873c-113">토폴로지 작성기는 호스트 이름이 아닌 Fqdn을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-113">Topology Builder uses FQDNs, not host names.</span></span> <span data-ttu-id="5873c-114">따라서 도메인에 가입 되어 있지 않은 Edge 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-114">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="5873c-115">Lync Server, Edge 서버 및 풀의 Fqdn을 할당할 때는 표준 문자 (-Z, a-z, 0 – 9, 하이픈 포함) <STRONG>만 사용</STRONG> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-115"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="5873c-116">유니코드 문자나 밑줄은 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5873c-116">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="5873c-117">FQDN의 비표준 문자는 외부 DNS 및 공개 Ca (즉 FQDN을 인증서의 SN에 할당 해야 하는 경우)에서 지원 되지 않는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-117">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (that is, when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="5873c-118">자세한 내용은 <A href="lync-server-2013-configure-dns-host-records.md">Lync Server 용 DNS 호스트 레코드 구성 2013</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5873c-118">For additional details, see <A href="lync-server-2013-configure-dns-host-records.md">Configure DNS Host records for Lync Server 2013</A></span></span>



</div>

<div>

## <a name="how-lync-clients-locate-services"></a><span data-ttu-id="5873c-119">Lync 클라이언트가 서비스를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="5873c-119">How Lync Clients Locate Services</span></span>

<span data-ttu-id="5873c-120">Microsoft Lync 2010, Lync 2013, Lync Mobile은 클라이언트가 Lync Server 2013에서 서비스를 찾고 액세스 하는 방법과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-120">Microsoft Lync 2010, Lync 2013, and Lync Mobile are similar in how the client finds and accesses services in Lync Server 2013.</span></span> <span data-ttu-id="5873c-121">주목할 만한 예외는 다른 서비스 위치 프로세스를 사용 하는 Lync Windows 스토어 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-121">The notable exception is the Lync Windows Store app that uses a different service location process.</span></span> <span data-ttu-id="5873c-122">이 섹션에서는 클라이언트가 서비스를 찾는 방법에 대 한 두 가지 시나리오, 먼저 일련의 SRV 및 호스트 레코드를 사용 하는 기존 메서드, 자동 검색 서비스 레코드만을 사용 하 여 초에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-122">This section details two scenarios of how the clients locate services, first the traditional method using a series of SRV and A host records, second using only the Autodiscover service records.</span></span> <span data-ttu-id="5873c-123">데스크톱 클라이언트에 대 한 누적 업데이트는 모든 클라이언트에 대 한 Lync Server 2010에서 DNS 위치 프로세스를 변경 하거나, 쿼리를 성공적으로 반환 하거나, 사용 가능 DNS 레코드 목록이 모두 소모 되 고, 최종 오류가 반환 됩니다. 클라이언트.</span><span class="sxs-lookup"><span data-stu-id="5873c-123">Cumulative updates to the desktop clients change the DNS location process from Lync Server 2010 For all clients, the DNS query process continues until a successful query is returned, or the list of possible DNS records is exhausted, and the final error is returned to the client.</span></span>

<span data-ttu-id="5873c-124">DNS 조회 중에 Lync Windows 스토어 앱을 **제외한** 모든 클라이언트에 대해 SRV 레코드를 쿼리하여 다음 순서 대로 클라이언트에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-124">For all clients **except** for the Lync Windows Store app During DNS lookup, SRV records are queried and returned to the client in the following order:</span></span>

1.  <span data-ttu-id="5873c-125">lyncdiscoverinternal. \<내부\> 웹 서비스의 자동 검색 서비스에 대 한 도메인 A (호스트) 레코드</span><span class="sxs-lookup"><span data-stu-id="5873c-125">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="5873c-126">lyncdiscover. \<외부\> 웹 서비스의 자동 검색 서비스에 대 한 도메인 A (호스트) 레코드</span><span class="sxs-lookup"><span data-stu-id="5873c-126">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

3.  <span data-ttu-id="5873c-127">\_sipinternaltls. \_tcp. \<내부\> TLS 연결에 대 한 도메인 SRV (서비스 로케이터) 레코드</span><span class="sxs-lookup"><span data-stu-id="5873c-127">\_sipinternaltls.\_tcp.\<domain\>   SRV (service locator) record for internal TLS connections</span></span>

4.  <span data-ttu-id="5873c-128">\_sipinternal. \_tcp. \<내부\> TCP 연결에 대 한 도메인 SRV (서비스 로케이터) 레코드 (TCP가 허용 되는 경우에만 수행 됨)</span><span class="sxs-lookup"><span data-stu-id="5873c-128">\_sipinternal.\_tcp.\<domain\>   SRV (service locator) record for internal TCP connections (performed only if TCP is allowed)</span></span>

5.  <span data-ttu-id="5873c-129">\_sip. \_tls. \<외부\> TLS 연결에 대 한 도메인 SRV (서비스 로케이터) 레코드</span><span class="sxs-lookup"><span data-stu-id="5873c-129">\_sip.\_tls.\<domain\>   SRV (service locator) record for external TLS connections</span></span>

6.  <span data-ttu-id="5873c-130">sipinternal. \<프런트\> 엔드 풀 또는 디렉터에 대 한 도메인 A (호스트) 레코드로, 내부 네트워크 에서만 확인할만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-130">sipinternal.\<domain\>   A (host) record for the Front End pool or Director, resolvable only on the internal network</span></span>

7.  <span data-ttu-id="5873c-131">sip. \<내부\> 네트워크의 프런트 엔드 풀 또는 디렉터에 대 한 도메인 A (호스트) 레코드 또는 클라이언트가 외부에 있는 경우 액세스 경계 서비스</span><span class="sxs-lookup"><span data-stu-id="5873c-131">sip.\<domain\>   A (host) record for the Front End pool or Director on the internal network, or the Access Edge service when the client is external</span></span>

8.  <span data-ttu-id="5873c-132">sipexternal. \<클라이언트가\> 외부에 있는 경우 액세스에 지 서비스에 대 한 도메인 A (호스트) 레코드</span><span class="sxs-lookup"><span data-stu-id="5873c-132">sipexternal.\<domain\>   A (host) record for the Access Edge service when the client is external</span></span>

<span data-ttu-id="5873c-133">Lync Windows 스토어 앱은 두 개의 레코드를 사용 하기 때문에 프로세스가 완전히 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-133">The Lync Windows Store app changes the process completely because it uses two records:</span></span>

1.  <span data-ttu-id="5873c-134">lyncdiscoverinternal. \<내부\> 웹 서비스의 자동 검색 서비스에 대 한 도메인 A (호스트) 레코드</span><span class="sxs-lookup"><span data-stu-id="5873c-134">lyncdiscoverinternal.\<domain\>   A (host) record for the Autodiscover service on the internal Web services</span></span>

2.  <span data-ttu-id="5873c-135">lyncdiscover. \<외부\> 웹 서비스의 자동 검색 서비스에 대 한 도메인 A (호스트) 레코드</span><span class="sxs-lookup"><span data-stu-id="5873c-135">lyncdiscover.\<domain\>   A (host) record for the Autodiscover service on the external Web services</span></span>

<span data-ttu-id="5873c-136">다른 레코드 형식에 대 한 대체 기능은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-136">There is no fallback to the other record types.</span></span>

<span data-ttu-id="5873c-137">이전 클라이언트와 비교 하 여 최신 클라이언트에 사용 되는 방법 간의 차이점은 자동 검색 서비스가 모든 서비스를 찾는 선호 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-137">The difference between the methods used for newer clients as compared to older clients is that the Autodiscover service is becoming the preferred method to locate all services.</span></span>

<span data-ttu-id="5873c-138">연결에 성공 하면 자동 검색 서비스는 모바일 서비스 (IIS의 서비스에 대해 생성 된 가상 디렉터리의 Mcx), Microsoft Lync Web App 및 웹 스케줄러 Url을 포함 하 여 사용자의 홈 풀에 대 한 모든 웹 서비스 Url을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-138">When a connection is successful, the Autodiscover Service returns all the Web Services URLs for the user's home pool, including the Mobility Service (known as Mcx by the virtual directory created for the service in IIS), Microsoft Lync Web App and Web scheduler URLs.</span></span> <span data-ttu-id="5873c-139">그러나 내부 모바일 서비스 URL과 외부 모바일 서비스 URL은 모두 외부 웹 서비스 FQDN과 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-139">However, both the internal Mobility Service URL and the external Mobility Service URL is associated with the external Web Services FQDN.</span></span> <span data-ttu-id="5873c-140">따라서 모바일 장치가 네트워크 내부 또는 외부에 있는지 여부에 관계 없이 디바이스는 항상 역방향 프록시를 통해 외부의 모바일 서비스에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-140">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Mobility Service externally through the reverse proxy.</span></span>

<span data-ttu-id="5873c-141">Lync Server 2013 2013의 누적 업데이트가 설치 된 경우 자동 검색 서비스는 내부/일부 WA, External/ldor와 함께 참조를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-141">If the Cumulative Updates for Lync Server 2013: February 2013 has been installed, the Autodiscover Service also returns references to Internal/UCWA, External/UCWA and UCWA.</span></span> <span data-ttu-id="5873c-142">이러한 항목은 통합 커뮤니케이션 웹 API (웹 구성 요소)를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-142">These entries refer to the Unified Communications Web API (UCWA) web component.</span></span> <span data-ttu-id="5873c-143">현재는 엔트리 셀만 사용 되며 웹 구성 요소의 URL에 대 한 참조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-143">Currently, only the entry UCWA is used and provides a reference to a URL for the web component.</span></span> <span data-ttu-id="5873c-144">이 (가) lync 2010 모바일 클라이언트에서 사용 하는 Mcx Mobility Service 대신 Lync 2013 모바일 클라이언트에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-144">UCWA is used by Lync 2013 Mobile clients instead of the Mcx Mobility Service used by the Lync 2010 Mobile clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5873c-145">SRV 레코드를 만들 때 DNS SRV 레코드를 만드는 동일한 도메인에서 DNS A 및 AAAA (IPv6 주소 사용을 하는 경우) 레코드를 가리켜야 한다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-145">When creating SRV records, it is important to remember that they must point to a DNS A and AAAA (if you are using IPv6 addressing) record in the same domain in which the DNS SRV record is created.</span></span> <span data-ttu-id="5873c-146">예를 들어 SRV 레코드가 contoso.com 인 경우 A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드는 fabrikam.com에 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-146">For example, if the SRV record is in contoso.com, the A and AAAA (if you are using IPv6 addressing) record it points to cannot be in fabrikam.com.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="5873c-147">기본 구성은 외부 사이트를 통해 모든 모바일 클라이언트 트래픽을 안내할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-147">The default configuration is to direct all mobile client traffic through the external site.</span></span> <span data-ttu-id="5873c-148">요구 사항에 더 적합 한 경우 내부 URL만 반환 하도록 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-148">You can modify settings to return only the internal URL, if this is more preferable for your requirements.</span></span> <span data-ttu-id="5873c-149">이 구성을 사용 하면 사용자가 회사 네트워크 내에 있는 경우에만 모바일 장치에서 Lync 모바일 응용 프로그램을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-149">With this configuration, users can use Lync mobile applications on their mobile devices only when they are inside the corporate network.</span></span> <span data-ttu-id="5873c-150">이 구성을 정의 하려면 <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-150">To define this configuration, you use the <STRONG>Set-CsMcxConfiguration</STRONG> cmdlet.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="5873c-151">모바일 응용 프로그램 에서도 주소록 서비스와 같은 다른 Lync Server 2013 서비스에 연결할 수 있지만 내부 모바일 응용 프로그램 웹 요청은 모바일 서비스에 대 한 외부 웹 FQDN으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-151">Although mobile applications can also connect to other Lync Server 2013 services, such as Address Book Service, internal mobile application web requests go to the external web FQDN only for the Mobility Service.</span></span> <span data-ttu-id="5873c-152">주소록 요청과 같은 다른 서비스 요청은이 구성을 요구 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-152">Other service requests, such as Address Book requests, do not require this configuration.</span></span>



</div>

<span data-ttu-id="5873c-153">모바일 장치는 서비스의 수동 검색을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-153">Mobile devices support manual discovery of services.</span></span> <span data-ttu-id="5873c-154">이 경우 각 사용자는 다음과 같이 프로토콜 및 경로를 포함 하 여 전체 내부 및 외부 자동 검색 서비스 Uri를 사용 하 여 모바일 장치 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-154">In this case, each user must configure the mobile device settings with the full internal and external Autodiscover Service URIs, including the protocol and path, as follows:</span></span>

  - <span data-ttu-id="5873c-155">외부\<액세스를 위한\>Https://extpoolfqdn/Autodiscover/autodiscoverservice.svc/Root</span><span class="sxs-lookup"><span data-stu-id="5873c-155">https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access</span></span>

  - <span data-ttu-id="5873c-156">내부\<액세스용 Https://intpoolfqdn\>/AutoDiscover/AutoDiscover.svc/Root</span><span class="sxs-lookup"><span data-stu-id="5873c-156">https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root for internal access</span></span>

<span data-ttu-id="5873c-157">수동 검색 대신 자동 검색을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-157">We recommend that you use automatic discovery, rather than manual discovery.</span></span> <span data-ttu-id="5873c-158">그러나 수동 설정은 모바일 장치 연결 문제를 해결 하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-158">However, manual settings can be useful for troubleshooting mobile device connectivity issues.</span></span>

</div>

<div>

## <a name="configuring-split-brain-dns-with-lync-server"></a><span data-ttu-id="5873c-159">Lync Server를 사용 하 여 분할 두뇌 DNS 구성</span><span class="sxs-lookup"><span data-stu-id="5873c-159">Configuring Split-Brain DNS with Lync Server</span></span>

<span data-ttu-id="5873c-160">분할 하는 dns는 여러 이름 (예: DNS 분할 또는 분할-수평 DNS)에 의해 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-160">Split-brain DNS is known by a number of names, for example, split DNS or split-horizon DNS.</span></span> <span data-ttu-id="5873c-161">단지 같은 네임 스페이스를 가진 두 개의 DNS 영역이 있지만, 하나의 DNS 영역 서비스 내부 전용 요청과 다른 DNS 영역 서비스 외부만 요청이 있는 DNS 구성을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-161">Simply, it describes a DNS configuration where there are two DNS zones with the same namespace – but one DNS zone services internal-only requests, and the other DNS zone services external-only requests.</span></span> <span data-ttu-id="5873c-162">그러나 내부 DNS에 포함 된 많은 DNS SRV 및 레코드는 외부 DNS에 포함 되지 않으며 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-162">However, many of the DNS SRV and A records contained in the internal DNS will not be contained in the external DNS, and the reverse is also true.</span></span> <span data-ttu-id="5873c-163">내부 및 외부 DNS에 동일한 DNS 레코드가 있는 경우 (예: www.contoso.com), 반환 되는 IP 주소는 쿼리가 시작 된 위치 (내부 또는 외부)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-163">In cases where the same DNS record exists in both the internal and external DNS (for example, www.contoso.com), the IP address returned will be different based on where (internal or external) the query was initiated.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5873c-164">현재, 이동성, 특히 LyncDiscover DNS 레코드에 대 한 분할 두뇌 DNS가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-164">Currently, Split-Brain DNS is not supported for the mobility, or more specifically, the LyncDiscover and LyncDiscoverInternal DNS records.</span></span> <span data-ttu-id="5873c-165">LyncDiscover는 외부 DNS 서버에서 정의 해야 하며, 내부 DNS 서버에서 LyncDiscoverInternal를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-165">LyncDiscover must be defined on an external DNS server and LyncDiscoverInternal must be defined on an internal DNS server.</span></span>



</div>

<span data-ttu-id="5873c-166">이러한 항목의 목적에 따라 분할의 두뇌 DNS가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-166">For the purposes of these topics, the term split-brain DNS will be used.</span></span>

<span data-ttu-id="5873c-167">분할 두뇌 DNS를 구성 하는 경우 다음 내부 및 외부 영역에 각 영역에 필요한 DNS 레코드의 종류에 대 한 요약이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-167">If you are configuring split-brain DNS, the following internal and external zone contain a summary of the types of DNS records required in each zone.</span></span> <span data-ttu-id="5873c-168">자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5873c-168">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="5873c-169">**내부 DNS:**</span><span class="sxs-lookup"><span data-stu-id="5873c-169">**Internal DNS:**</span></span>

  - <span data-ttu-id="5873c-170">권한이 있는 contoso.com 이라는 DNS 영역 포함</span><span class="sxs-lookup"><span data-stu-id="5873c-170">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="5873c-171">내부 contoso.com 영역에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-171">The internal contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="5873c-172">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 내부 Lync Server 2013 클라이언트 자동 구성에 대 한 SRV 레코드 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="5873c-172">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for internal Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="5873c-173">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 또는 Lync Server 2013 웹 서비스의 자동 검색을 위한 CNAME 레코드 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="5873c-173">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services (optional)</span></span>
    
      - <span data-ttu-id="5873c-174">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드를 프런트 엔드 풀 이름, 디렉터 또는 디렉터 풀 이름 및 회사 네트워크에서 Lync Server 2013을 실행 하는 모든 내부 서버</span><span class="sxs-lookup"><span data-stu-id="5873c-174">DNS A and AAAA (if you are using IPv6 addressing) records for Front End pool name, Director or Director pool name, and all internal servers running Lync Server 2013 in the corporate network</span></span>
    
      - <span data-ttu-id="5873c-175">각 Lync Server 2013, Edge 서버의 경계 네트워크에 대 한 Edge 내부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드</span><span class="sxs-lookup"><span data-stu-id="5873c-175">DNS A and AAAA (if you are using IPv6 addressing) records for the Edge internal interface of each Lync Server 2013, Edge Server in the perimeter network</span></span>
    
      - <span data-ttu-id="5873c-176">경계 네트워크에서 각 역방향 프록시 서버의 내부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드 (리버스 프록시 관리의 경우 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="5873c-176">DNS A and AAAA (if you are using IPv6 addressing) records for the internal interface of each reverse proxy server in the perimeter network (optional for management of reverse proxy)</span></span>
    
      - <span data-ttu-id="5873c-177">주변 네트워크의 모든 Lync Server 2013 Edge 서버 내부 Edge 인터페이스 contoso.com에 대 한 쿼리 확인을 위해 내부 DNS 영역 사용</span><span class="sxs-lookup"><span data-stu-id="5873c-177">All Lync Server 2013  Edge Server internal edge interfaces in the perimeter network use the internal DNS zone for resolving queries to contoso.com</span></span>
    
      - <span data-ttu-id="5873c-178">회사 네트워크에서 lync 2013를 실행 하는 Lync Server 2013 및 클라이언트를 실행 하는 모든 서버는 contoso.com에 대 한 쿼리를 확인 하거나 각 Edge 서버에서 HOSTS 파일을 사용 하거나 목록 A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드에 대 한 내부 DNS 서버를 가리킵니다. 다음 홉 서버, 구체적으로 디렉터 또는 디렉터 VIP, 프론트 End pool VIP 또는 Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="5873c-178">All servers running Lync Server 2013 and clients running Lync 2013 in the corporate network point to the internal DNS servers for resolving queries to contoso.com, or use of HOSTS file on each Edge server and list A and AAAA (if you are using IPv6 addressing) records for next hop server, specifically the Director or Director VIP, Front End pool VIP, or Standard Edition server</span></span>

<span data-ttu-id="5873c-179">**외부 DNS:**</span><span class="sxs-lookup"><span data-stu-id="5873c-179">**External DNS:**</span></span>

  - <span data-ttu-id="5873c-180">권한이 있는 contoso.com 이라는 DNS 영역 포함</span><span class="sxs-lookup"><span data-stu-id="5873c-180">Contains a DNS zone called contoso.com for which it is authoritative</span></span>

  - <span data-ttu-id="5873c-181">외부 contoso.com 영역에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-181">The external contoso.com zone contains:</span></span>
    
      - <span data-ttu-id="5873c-182">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 Lync Server 2013 클라이언트 자동 구성에 대 한 SRV 레코드 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="5873c-182">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for Lync Server 2013 client autoconfiguration (optional)</span></span>
    
      - <span data-ttu-id="5873c-183">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 또는 모바일에서 사용할 Lync Server 2013 웹 서비스의 자동 검색을 위한 CNAME 레코드</span><span class="sxs-lookup"><span data-stu-id="5873c-183">DNS A and AAAA (if you are using IPv6 addressing) or CNAME records for automatic discovery of Lync Server 2013 Web Services for use with mobility</span></span>
    
      - <span data-ttu-id="5873c-184">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 경계 네트워크의 각 Lync Server 2013, Edge 서버 또는 하드웨어 부하 분산 장치 VIP (가상 IP)의 Edge 외부 인터페이스에 대 한 SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="5873c-184">DNS A and AAAA (if you are using IPv6 addressing) and SRV records for the Edge external interface of each Lync Server 2013, Edge Server or hardware load balancer virtual IP (VIP) in the perimeter network</span></span>
    
      - <span data-ttu-id="5873c-185">경계 네트워크의 역방향 프록시 서버 풀의 외부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드</span><span class="sxs-lookup"><span data-stu-id="5873c-185">DNS A and AAAA (if you are using IPv6 addressing) records for the external interface of the reverse proxy server or VIP for a pool of reverse proxy servers in the perimeter network</span></span>

</div>

<div>

## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="5873c-186">분할 하는 DNS 없이 자동 구성</span><span class="sxs-lookup"><span data-stu-id="5873c-186">Automatic Configuration without Split-Brain DNS</span></span>

<span data-ttu-id="5873c-187">분할 하는 DNS를 사용 하는 경우 내부 DNS 영역에 \_sipinternaltls 포함 된 경우 내부적으로 로그인 하는 Lync Server 2013 사용자가 자동 구성을 활용할 수 있습니다. \_사용 중인 각 SIP 도메인에 대 한 tcp SRV 레코드.</span><span class="sxs-lookup"><span data-stu-id="5873c-187">Using split-brain DNS, a Lync Server 2013 user that signs in internally can take advantage of automatic configuration if the internal DNS zone contains a \_sipinternaltls.\_tcp SRV record for each SIP domain in use.</span></span> <span data-ttu-id="5873c-188">그러나 분할 하는 DNS를 사용 하지 않는 경우이 섹션의 뒷부분에 설명 된 해결 방법 중 하나를 구현 하지 않으면 Lync를 실행 하는 클라이언트의 내부 자동 구성이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-188">However, if you do not use split-brain DNS, internal automatic configuration of clients running Lync will not work unless one of the workarounds described in later in this section is implemented.</span></span> <span data-ttu-id="5873c-189">이는 Lync Server 2013에서 자동 구성에 대해 지정 된 프런트 엔드 풀의 도메인과 일치 시키기 위해 사용자의 SIP URI가 필요 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-189">This is because Lync Server 2013 requires the user’s SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="5873c-190">이전 버전의 Communicator를 사용 하는 경우에도이 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-190">This was also the case with earlier versions of Communicator.</span></span>

<span data-ttu-id="5873c-191">예를 들어 두 개의 SIP 도메인을 사용 하는 경우 다음 DNS 서비스 (SRV) 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-191">For example, if you have two SIP domains in use, the following DNS service (SRV) records would be required:</span></span>

  - <span data-ttu-id="5873c-192">사용자가 bob@contoso.com로 로그인 하는 경우 사용자의 SIP 도메인 (contoso.com)이 자동 구성 프런트 엔드 풀의 도메인과 일치 하기 때문에 다음 SRV 레코드가 자동 구성에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-192">If a user signs in as bob@contoso.com the following SRV record will work for automatic configuration because the user’s SIP domain (contoso.com) matches the domain of automatic configuration Front End pool):</span></span>
    
     <span data-ttu-id="5873c-193">\_sipinternaltls. \_tcp.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5873c-193">\_sipinternaltls.\_tcp.contoso.com.</span></span> <span data-ttu-id="5873c-194">SRV 0 0 5061 pool01.contoso.com의 86400</span><span class="sxs-lookup"><span data-stu-id="5873c-194">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>

  - <span data-ttu-id="5873c-195">사용자가 alice@fabrikam.com로 로그인 하는 경우 다음 DNS SRV 레코드는 두 번째 SIP 도메인의 자동 구성에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-195">If a user signs in as alice@fabrikam.com the following DNS SRV record will work for automatic configuration of the second SIP domain.</span></span>
    
     <span data-ttu-id="5873c-196">\_sipinternaltls. \_tcp.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="5873c-196">\_sipinternaltls.\_tcp.fabrikam.com.</span></span> <span data-ttu-id="5873c-197">SRV 0 0 5061 pool01.fabrikam.com의 86400</span><span class="sxs-lookup"><span data-stu-id="5873c-197">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="5873c-198">비교할 때, 클라이언트의 SIP 도메인 (litwareinc.com)이 풀이 있는 도메인 (fabrikam.com)과 일치 하지 않기 때문에 사용자가 tim@litwareinc.com로 로그인 하는 경우 자동 구성에 대해 다음 DNS SRV 레코드가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-198">For comparison, if a user signs in as tim@litwareinc.com the following DNS SRV record will not work for automatic configuration, because the client’s SIP domain (litwareinc.com) does not match the domain that the pool is in (fabrikam.com):</span></span>

 <span data-ttu-id="5873c-199">\_sipinternaltls. \_tcp.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5873c-199">\_sipinternaltls.\_tcp.litwareinc.com.</span></span> <span data-ttu-id="5873c-200">SRV 0 0 5061 pool01.fabrikam.com의 86400</span><span class="sxs-lookup"><span data-stu-id="5873c-200">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>

<span data-ttu-id="5873c-201">Lync를 실행 하는 클라이언트에 자동 구성이 필요한 경우 다음 옵션 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-201">If automatic configuration is required for clients running Lync, select one of the following options:</span></span>

  - <span data-ttu-id="5873c-202">**그룹 정책 개체**   는 gpo (그룹 정책 개체)를 사용 하 여 올바른 서버 값을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-202">**Group Policy Objects**   Use Group Policy objects (GPOs) to populate the correct server values.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5873c-203">이 옵션은 자동 구성을 사용 하지 않지만 수동 구성 프로세스를 자동화 하므로이 방법을 사용 하는 경우 자동 구성에 연결 된 SRV 레코드가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-203">This option does not enable automatic configuration, but it does automate the process of manual configuration, so if this approach is used, the SRV records associated with automatic configuration are not required.</span></span>

    
    </div>

  - <span data-ttu-id="5873c-204">**일치 하는 내부 영역**   외부 dns 영역 (예: contoso.com)과 일치 하는 내부 dns에 영역을 만들고 자동 구성에 사용 되는 Lync Server 2013 풀에 해당 하는 DNS a 및 AAAA (IPv6 주소를 사용 하는 경우)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-204">**Matching internal zone**   Create a zone in the internal DNS that matches the external DNS zone (for example, contoso.com) and create DNS A and AAAA (if you are using IPv6 addressing) records corresponding to the Lync Server 2013 pool used for automatic configuration.</span></span> <span data-ttu-id="5873c-205">예를 들어 사용자가 pool01.contoso.net에 있는 경우 Lync에 bob@contoso.com에 로그인 하 고, contoso.com 이라는 내부 DNS 영역을 만들고, DNS A 및 AAAA (IPv6 주소 지정이 사용 되는 경우)를 pool01.contoso.com에 대 한 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-205">For example, if a user is homed on pool01.contoso.net but signs into Lync as bob@contoso.com, create an internal DNS zone called contoso.com and inside it, create a DNS A and AAAA (if IPv6 addressing is used) record for pool01.contoso.com.</span></span>

  - <span data-ttu-id="5873c-206">**핀 포인트 내부 영역**   내부 DNS에서 전체 영역을 만드는 경우 자동 구성에 필요한 SRV 레코드에 해당 하는 pin 포인트 (즉, 전용) 영역을 만들고 dnscmd를 사용 하 여 해당 영역을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-206">**Pin-point internal zone**   If you are creating an entire zone in the internal DNS is not an option, you can create pin-point (that is, dedicated) zones that correspond to the SRV records that are required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="5873c-207">DNS 사용자 인터페이스가 pin 포인트 영역 만들기를 지원 하지 않으므로 Dnscmd이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-207">Dnscmd.exe is required because the DNS user interface does not support creation of pin-point zones.</span></span> <span data-ttu-id="5873c-208">예를 들어 SIP 도메인이 contoso.com이 고 두 프런트 엔드 서버를 포함 하는 pool01 라는 프런트 엔드 풀을 사용 하는 경우에는 내부 DNS에 다음과 같은 핀 위치 영역과 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-208">For example, if the SIP domain is contoso.com and you have a Front End pool called pool01 that contains two Front End Servers, you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
        dnscmd . /zoneadd pool01.contoso.com. /dsprimary
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
    
    <span data-ttu-id="5873c-209">환경에 두 번째 SIP 도메인 (예: fabrikam.com)이 포함 되어 있는 경우에는 내부 DNS에 다음과 같은 핀 위치 영역과 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-209">If your environment contains a second SIP domain (for example, fabrikam.com), you need the following pin-point zones and A records in your internal DNS:</span></span>
    
        dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
        dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
        dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
        dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
        dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>

<div>


> [!NOTE]  
> <span data-ttu-id="5873c-210">프런트 엔드 풀 FQDN은 두 개의 서로 다른 IP 주소를 사용 하 여 두 번 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-210">The Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="5873c-211">DNS 부하 분산을 사용 하지만 하드웨어 부하 분산을 사용 하는 경우에는 프런트 엔드 풀 항목을 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-211">This is because DNS load balancing is used, but if hardware load balancing is used, there would be only a single Front End pool entry.</span></span> <span data-ttu-id="5873c-212">또한 contoso.com 예제와 fabrikam.com 예제 간에 프런트 엔드 풀 FQDN 값이 변경 되지만 IP 주소는 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-212">Also, the Front End pool FQDN values change between the contoso.com example and the fabrikam.com example, but the IP addresses remain the same.</span></span> <span data-ttu-id="5873c-213">이는 사용자가 SIP 도메인 중 하나에서 로그인 한 후 자동 구성에 동일한 프런트 엔드 풀을 사용 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-213">This is because users signing in from either SIP domain, use the same Front End pool for automatic configuration.</span></span>



</div>

<span data-ttu-id="5873c-214">자세한 내용은 DMTF 블로그 문서, "Communicator 자동 구성 및 분할-두뇌 DNS"를 참조 하세요 [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).</span><span class="sxs-lookup"><span data-stu-id="5873c-214">For details, see the DMTF blog article, "Communicator Automatic Configuration and Split-Brain DNS," at [http://go.microsoft.com/fwlink/p/?linkId=200707](http://go.microsoft.com/fwlink/p/?linkid=200707).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5873c-215">각 블로그 및 해당 URL의 콘텐츠는 예 고 없이 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-215">The content of each blog and its URL are subject to change without notice.</span></span>



</div>

</div>

<div>

## <a name="configuring-the-domain-name-system-dns-for-disaster-recovery"></a><span data-ttu-id="5873c-216">재해 복구를 위해 DNS (domain name system) 구성</span><span class="sxs-lookup"><span data-stu-id="5873c-216">Configuring the domain name system (DNS) for Disaster Recovery</span></span>

<span data-ttu-id="5873c-217">Lync Server 2013 웹 트래픽을 재해 복구 및 장애 조치 사이트로 리디렉션하도록 DNS를 구성 하려면 GeoDNS를 지 원하는 DNS 공급자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-217">To configure DNS to redirect Lync Server 2013 Web traffic to your disaster recovery and failover sites, you must be using a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="5873c-218">장애 복구를 지원 하도록 웹에 대 한 DNS 레코드를 설정 하 여 전체 프런트 엔드 풀 하나가 다운 되는 경우에도 웹 서비스를 사용 하는 기능이 계속 작동 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-218">You can set up your DNS records for Web to support disaster recovery, so that features that use Web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="5873c-219">이 재해 복구 기능은 자동 검색 (Lyncdiscover URL), 모임 및 전화 접속 간단한 Url을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-219">This disaster recovery feature supports the Autodiscover (Lyncdiscover URL), Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="5873c-220">GeoDNS 공급자에서 웹 서비스의 내부 및 외부 해상도에 대 한 추가 DNS 호스트 (A 및 IPv6을 사용 하는 경우 AAAA) 레코드를 정의 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-220">You define and configure additional DNS host (A and AAAA if using IPv6) records for internal and external resolution of Web services at your GeoDNS provider.</span></span> <span data-ttu-id="5873c-221">다음 세부 정보는 라운드 로빈 DNS를 사용 하 여 공급자가 지 원하는 쌍의 풀, 지리적으로 분산 된 연결 및 Pool1를 기본으로 사용할 수 있도록 구성 하 고 통신 손실 또는 하드웨어 오류 발생 시 Pool2로 장애 조치를 수행 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-221">The following details assume paired pools, geographically dispersed, and GeoDNS supported by your provider with either round-robin DNS, or configured to use Pool1 as primary, and fail over to Pool2 in the event of communications loss or hardware failure.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5873c-222">GeoDNS 레코드 (예)</span><span class="sxs-lookup"><span data-stu-id="5873c-222">GeoDNS record (example)</span></span></th>
<th><span data-ttu-id="5873c-223">풀 레코드 (예)</span><span class="sxs-lookup"><span data-stu-id="5873c-223">Pool records (example)</span></span></th>
<th><span data-ttu-id="5873c-224">CNAME 레코드 (예)</span><span class="sxs-lookup"><span data-stu-id="5873c-224">CNAME records (example)</span></span></th>
<th><span data-ttu-id="5873c-225">DNS 설정 (한 옵션 선택)</span><span class="sxs-lookup"><span data-stu-id="5873c-225">DNS settings (select one option)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5873c-226">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-226">Meet-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-227">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-227">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-228">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-228">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-229">Pool1InternalWebFQDN.contoso.com에 Meet.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-229">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-230">Pool2InternalWebFQDN.contoso.com에 Meet.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-230">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-231">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="5873c-231">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5873c-232">기본 사용, 보조 if 실패에 연결</span><span class="sxs-lookup"><span data-stu-id="5873c-232">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5873c-233">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-233">Meet-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-234">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-234">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-235">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-235">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-236">Pool1ExternalWebFQDN.contoso.com에 Meet.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-236">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-237">Pool2ExternalWebFQDN.contoso.com에 Meet.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-237">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-238">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="5873c-238">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5873c-239">기본 사용, 보조 if 실패에 연결</span><span class="sxs-lookup"><span data-stu-id="5873c-239">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5873c-240">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-240">Dialin-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-241">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-241">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-242">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-242">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-243">Pool1InternalWebFQDN.contoso.com에 Dialin.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-243">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-244">Pool2InternalWebFQDN.contoso.com에 Dialin.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-244">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-245">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="5873c-245">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5873c-246">기본 사용, 보조 if 실패에 연결</span><span class="sxs-lookup"><span data-stu-id="5873c-246">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5873c-247">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-247">Dialin-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-248">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-248">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-249">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-249">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-250">Pool1ExternalWebFQDN.contoso.com에 Dialin.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-250">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-251">Pool2ExternalWebFQDN.contoso.com에 Dialin.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-251">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-252">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="5873c-252">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5873c-253">기본 사용, 보조 if 실패에 연결</span><span class="sxs-lookup"><span data-stu-id="5873c-253">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5873c-254">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-254">Lyncdiscoverint-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-255">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-255">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-256">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-256">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-257">Pool1InternalWebFQDN.contoso.com에 Lyncdiscoverinternal.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-257">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-258">Pool2InternalWebFQDN.contoso.com에 Lyncdiscoverinternal.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-258">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-259">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="5873c-259">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5873c-260">기본 사용, 보조 if 실패에 연결</span><span class="sxs-lookup"><span data-stu-id="5873c-260">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5873c-261">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-261">Lyncdiscover-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-262">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-262">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-263">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-263">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-264">Pool1ExternalWebFQDN.contoso.com에 Lyncdiscover.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-264">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-265">Pool2ExternalWebFQDN.contoso.com에 Lyncdiscover.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-265">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-266">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="5873c-266">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5873c-267">기본 사용, 보조 if 실패에 연결</span><span class="sxs-lookup"><span data-stu-id="5873c-267">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5873c-268">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-268">Scheduler-int.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-269">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-269">Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-270">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-270">Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-271">Pool1InternalWebFQDN.contoso.com에 Scheduler.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-271">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-272">Pool2InternalWebFQDN.contoso.com에 Scheduler.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-272">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-273">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="5873c-273">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5873c-274">기본 사용, 보조 if 실패에 연결</span><span class="sxs-lookup"><span data-stu-id="5873c-274">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5873c-275">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-275">Scheduler-ext.geolb.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-276">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-276">Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-277">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5873c-277">Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-278">Pool1ExternalWebFQDN.contoso.com에 Scheduler.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-278">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span></p>
<p><span data-ttu-id="5873c-279">Pool2ExternalWebFQDN.contoso.com에 Scheduler.contoso.com 별칭</span><span class="sxs-lookup"><span data-stu-id="5873c-279">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5873c-280">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="5873c-280">Round Robin between pools</span></span></p>
<p><span data-ttu-id="5873c-281">기본 사용, 보조 if 실패에 연결</span><span class="sxs-lookup"><span data-stu-id="5873c-281">Use primary, connect to secondary if failure</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-load-balancing"></a><span data-ttu-id="5873c-282">DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="5873c-282">DNS Load Balancing</span></span>

<span data-ttu-id="5873c-283">DNS 부하 분산은 일반적으로 응용 프로그램 수준에서 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-283">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="5873c-284">응용 프로그램 (예: Lync를 실행 하는 클라이언트)은 DNS A 및 AAAA (IPv6 주소 지정을 사용 하는 경우)에서 반환 되는 IP 주소 중 하나에 연결 하 여 풀의 서버에 연결 하려고 시도 합니다. FQDN (정규화 된 도메인 이름)에 대 한 쿼리 기록</span><span class="sxs-lookup"><span data-stu-id="5873c-284">The application (for example, a client running Lync), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="5873c-285">예를 들어 pool01.contoso.com 이라는 풀에 프런트 엔드 서버가 세 개 있는 경우 다음이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-285">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>

  - <span data-ttu-id="5873c-286">Pool01.contoso.com 용 Lync 쿼리 DNS를 실행 하는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="5873c-286">Clients running Lync query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="5873c-287">쿼리는 세 개의 IP 주소를 반환 하 고 다음과 같이 캐시 합니다 (이 순서는 필요 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="5873c-287">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="5873c-288">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="5873c-288">pool01.contoso.com      192.168.10.90</span></span>
    
    <span data-ttu-id="5873c-289">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="5873c-289">pool01.contoso.com      192.168.10.91</span></span>
    
    <span data-ttu-id="5873c-290">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="5873c-290">pool01.contoso.com      192.168.10.92</span></span>

  - <span data-ttu-id="5873c-291">클라이언트가 IP 주소 중 하나에 대 한 TCP (전송 제어 프로토콜) 연결을 설정 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-291">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="5873c-292">이 오류가 발생 하면 클라이언트는 캐시에서 다음 IP 주소를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-292">If that fails, the client tries the next IP address in the cache.</span></span>

  - <span data-ttu-id="5873c-293">TCP 연결이 성공 하면 클라이언트는 pool01.contoso.com의 기본 등록 기관에 연결 하도록 TLS를 협상 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-293">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>

  - <span data-ttu-id="5873c-294">클라이언트가 연결 되지 않고 모든 캐시 된 항목을 시도 하는 경우, 현재 Lync Server 2013을 실행 하는 서버를 사용할 수 없다는 알림을 사용자에 게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-294">If the client tries all cached entries without a successful connection, the user is notified that no servers running Lync Server 2013 are available at the moment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5873c-295">DNS 기반 부하 분산은 dns를 사용 하 여 풀의 서버에 해당 하는 IP 주소를 서로 다른 순서로 제공 하 여 로드 균형 조정을 가리키는 DNS 라운드 로빈 (DNS RR)과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-295">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="5873c-296">일반적으로 DNS RR은 로드 배포만 가능 하지만 장애 조치를 사용 하도록 설정 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-296">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="5873c-297">예를 들어 DNS A와 AAAA (IPv6 주소 지정을 사용 하는 경우)에 의해 반환 된 하나의 IP 주소에 대 한 연결에 실패 하면 연결이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-297">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="5873c-298">따라서 dns 라운드 로빈 자체는 DNS 기반 부하 분산 보다 안정성이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-298">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="5873c-299">Dns 부하 분산을 함께 사용 하 여 DNS 라운드 로빈을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-299">You can use DNS round robin in conjunction with DNS load balancing.</span></span>



</div>

<span data-ttu-id="5873c-300">DNS 부하 분산은 다음에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-300">DNS load balancing is used for the following:</span></span>

  - <span data-ttu-id="5873c-301">서버 간 SIP의 부하 분산을 Edge 서버로</span><span class="sxs-lookup"><span data-stu-id="5873c-301">Load balancing server-to-server SIP to the Edge Servers</span></span>

  - <span data-ttu-id="5873c-302">회의 자동 전화 교환, 응답 그룹, 통화 공원 등 통합 커뮤니케이션 응용 프로그램 서비스 (c) 응용 프로그램 로드 균형 조정</span><span class="sxs-lookup"><span data-stu-id="5873c-302">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>

  - <span data-ttu-id="5873c-303">다른 항목에 대 한 새 연결을 응용 프로그램으로 방지 ("드레이닝"이 라고도 함)</span><span class="sxs-lookup"><span data-stu-id="5873c-303">Preventing new connections to UCAS applications (also known as "draining")</span></span>

  - <span data-ttu-id="5873c-304">클라이언트와 Edge 서버 간의 모든 클라이언트 간 트래픽 부하 분산</span><span class="sxs-lookup"><span data-stu-id="5873c-304">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>

<span data-ttu-id="5873c-305">DNS 부하 분산은 다음에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-305">DNS load balancing cannot be used for the following:</span></span>

  - <span data-ttu-id="5873c-306">디렉터 또는 프런트 엔드 서버에 대 한 클라이언트 대 서버 웹 트래픽</span><span class="sxs-lookup"><span data-stu-id="5873c-306">Client-to-server web traffic to Director or Front End Servers</span></span>

<span data-ttu-id="5873c-307">DNS 부하 분산 및 페더레이션 트래픽:</span><span class="sxs-lookup"><span data-stu-id="5873c-307">DNS load balancing and federated traffic:</span></span>

<span data-ttu-id="5873c-308">DNS SRV 쿼리에서 여러 DNS 레코드를 반환 하는 경우 액세스에 지 서비스가 항상 가장 낮은 숫자 우선 순위와 가장 높은 숫자 가중치를 사용 하 여 DNS SRV 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-308">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="5873c-309">인터넷 엔지니어링 작업 강제 문서 "서비스 위치를 지정 하는 DNS RR (DNS SRV)" <http://www.ietf.org/rfc/rfc2782.txt> 은 정의 된 dns srv 레코드가 여러 개 있는 경우 우선 순위를 먼저 사용한 다음 weight를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-309">The Internet Engineering Task Force document “A DNS RR for specifying the location of services (DNS SRV)” <http://www.ietf.org/rfc/rfc2782.txt> specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="5873c-310">예를 들어 DNS SRV 레코드 A의 가중치가 20이 고 우선 순위가 40이 고 DNS SRV 레코드 B의 가중치가 10이 고 우선 순위가 50입니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-310">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="5873c-311">우선 순위가 40 인 DNS SRV 레코드 A가 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-311">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="5873c-312">DNS SRV 레코드 선택에는 다음과 같은 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-312">The following rules apply to DNS SRV record selection:</span></span>

  - <span data-ttu-id="5873c-313">우선 순위가 가장 먼저 고려 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-313">Priority is considered first.</span></span> <span data-ttu-id="5873c-314">클라이언트가 DNS SRV 레코드가 정의한 대상 호스트에 연결 하는 데 사용할 수 있는 가장 낮은 우선 순위로 연결을 시도 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-314">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="5873c-315">우선 순위가 같은 대상은 weight 필드에 정의 된 순서 대로 시도해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-315">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>

  - <span data-ttu-id="5873c-316">Weight 필드는 우선 순위가 동일한 항목에 대 한 상대적 가중치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-316">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="5873c-317">가중치가 클수록 선택 되는 확률을 비례적으로 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-317">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="5873c-318">DNS 관리자는 수행할 서버 선택이 없는 경우 가중치 0을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-318">DNS administrators SHOULD use Weight 0 when there isn’t any server selection to do.</span></span> <span data-ttu-id="5873c-319">가중치가 0 보다 큰 레코드가 있는 경우 가중치가 0 인 레코드는 선택할 확률이 매우 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-319">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>

<span data-ttu-id="5873c-320">우선 순위와 가중치가 같은 DNS SRV 레코드가 여러 개 반환 되는 경우 액세스에 지 서비스가 DNS 서버에서 먼저 받은 SRV 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5873c-320">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

