---
title: 'Lync Server 2013: 역방향 프록시 서버 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef13f2351ab74c0e3b2ba558a9dbf0aef43d71b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="6fd63-102">Lync Server 2013에 대한 역방향 프록시 서버 설치</span><span class="sxs-lookup"><span data-stu-id="6fd63-102">Setting up reverse proxy servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fd63-103">_**마지막으로 수정한 주제:** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="6fd63-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="6fd63-104">Microsoft Lync Server 2013 Edge 서버 배포의 경우 외부 클라이언트에서 주변 네트워크의 HTTPS 역방향 프록시를 사용 하 여 디렉터와 사용자의 홈 풀에서 Lync Server 2013 웹 서비스 (Office Communications Server의 *웹 구성 요소* )에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-104">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="6fd63-105">리버스 프록시를 통해 외부 액세스를 필요로 하는 일부 기능에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-105">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="6fd63-106">외부 사용자가 모임에 대 한 모임 콘텐츠를 다운로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-106">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="6fd63-107">외부 사용자가 메일 그룹을 확장할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-107">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="6fd63-108">원격 사용자가 주소록 서비스에서 파일을 다운로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-108">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="6fd63-109">Lync Web App 클라이언트에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-109">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="6fd63-110">전화 접속 회의 설정 웹 페이지에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-110">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="6fd63-111">외부 장치에서 장치 업데이트 웹 서비스에 연결 하 고 업데이트를 얻을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-111">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="6fd63-112">모바일 응용 프로그램이 인터넷에서 이동성 (Mcx) Url을 자동으로 검색 하 고 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-112">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="6fd63-113">Lync 2013 클라이언트, Lync Windows 스토어 앱 및 Lync 2013 모바일 클라이언트를 사용 하도록 설정 하 여 Lync 검색 (검색) Url을 찾고 통합 커뮤니케이션 웹 API (c)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-113">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="6fd63-114">모든 풀의 모든 웹 서비스를 게시 하도록 HTTP 역방향 프록시를 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-114">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="6fd63-115">Https://ExternalFQDN/게시\* -풀에 대 한 모든 IIS 가상 디렉터리를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-115">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="6fd63-116">조직의 각 스탠더드 버전 서버, 프런트 엔드 풀 또는 디렉터 또는 디렉터 풀에 대해 하나의 게시 규칙이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-116">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="6fd63-117">또한 간단한 Url을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-117">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="6fd63-118">조직에 디렉터 또는 디렉터 풀이 있으면 HTTP 역방향 프록시가 간단한 Url에 대 한 HTTP/HTTPS 요청을 수신 하 고 디렉터 또는 디렉터 풀의 외부 웹 서비스 가상 디렉터리에이를 프록시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-118">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="6fd63-119">디렉터를 배포 하지 않은 경우에는 단순 Url에 대 한 요청을 처리 하도록 풀을 하나 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-119">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="6fd63-120">(이 사용자의 홈 풀이 아닌 경우 사용자의 홈 풀에 있는 웹 서비스로 이동 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="6fd63-120">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="6fd63-121">간단한 Url은 전용 웹 게시 규칙을 통해 처리 되거나, 디렉터에 대 한 웹 게시 규칙의 공개 이름에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-121">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="6fd63-122">외부 자동 검색 서비스 URL도 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-122">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="6fd63-123">Microsoft Forefront 위협 관리 게이트웨이 2010, Microsoft 인터넷 보안 및 가속 (ISA) Server 2006 SP1 또는 IIS ARR (응용 프로그램 요청 라우팅)을 사용 하는 인터넷 정보 서버 7.0, 7.5 또는 8.0을 리버스 프록시로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-123">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="6fd63-124">이 섹션의 자세한 단계에서는 Forefront Threat Management 게이트웨이 2010를 구성 하는 방법에 대해 설명 하 고 ISA Server 2006를 구성 하는 단계는 거의 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-124">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="6fd63-125">IIS ARR에 대 한 지침도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-125">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="6fd63-126">다른 리버스 프록시를 사용 하는 경우 해당 제품에 대 한 설명서를 참조 하 고 여기에 정의 된 요구 사항을 다른 역방향 프록시의 관련 기능에 매핑하십시오.</span><span class="sxs-lookup"><span data-stu-id="6fd63-126">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6fd63-127">인터넷 정보 서버 응용 프로그램 요청 라우팅 (IIS ARR)은 Lync Server 2010 및 Lync Server 2013에 대 한 리버스 프록시를 구현 하기 위해 완전히 테스트 되 고 지원 되는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-127">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="6fd63-128">11 월 2012 일에는 ForeFront Threat Management Gateway 2010 또는 TMG의 Microsoft 멈추는 라이선스 sales가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-128">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="6fd63-129">TMG는 완벽 하 게 지원 되는 제품이 며 제 3 자에서 판매한 기기에 대 한 할인 판매를 계속 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-129">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="6fd63-130">또한 많은 서드 파티 하드웨어 부하 분산 장치 및 방화벽이 리버스 프록시 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-130">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="6fd63-131">역방향 프록시 기능을 제공 하는 하드웨어 부하 분산 장치 및 방화벽의 경우, 해당 제품을 구성 하 여 Lync Server에 대 한 리버스 프록시 지원을 제공 하는 방법에 대 한 구체적인 지침이 공급 업체에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="6fd63-131">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="6fd63-132">제품에 대 한 설명서를 Microsoft에 제출한 타사 파티를 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-132">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="6fd63-133">지원은 해당 솔루션의 제 3 자에 의해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-133">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="6fd63-134">솔루션을 제공 하는 데 활성 상태인 제 3 자가 표시 되는 경우 <A href="http://go.microsoft.com/fwlink/?linkid=268730">Microsoft Lync의 인프라 적격</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6fd63-134">To see third parties that are active in providing solutions, see <A href="http://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="6fd63-135">다음 항목 및 절차에서는 배포 및 구성 절차의 기반으로 Forefront Threat Management 게이트웨이 2010 및 IIS ARR을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-135">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="6fd63-136">Lync Server 2013에 대한 웹 팜 FQDN 구성</span><span class="sxs-lookup"><span data-stu-id="6fd63-136">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="6fd63-137">Lync Server 2013에서 네트워크 어댑터 구성</span><span class="sxs-lookup"><span data-stu-id="6fd63-137">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="6fd63-138">Lync Server 2013에서 HTTP 역방향 프록시에 대한 인증서 요청 및 구성</span><span class="sxs-lookup"><span data-stu-id="6fd63-138">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="6fd63-139">Lync Server 2013에서 단일 내부 풀에 대한 웹 게시 규칙 구성</span><span class="sxs-lookup"><span data-stu-id="6fd63-139">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="6fd63-140">Lync Server 2013에서 IIS 가상 디렉터리에 대한 인증 확인 또는 구성</span><span class="sxs-lookup"><span data-stu-id="6fd63-140">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="6fd63-141">Lync Server 2013에서 역방향 프록시 서버에 대한 DNS 레코드 만들기</span><span class="sxs-lookup"><span data-stu-id="6fd63-141">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="6fd63-142">Lync Server 2013에서 역방향 프록시를 통해 액세스 확인</span><span class="sxs-lookup"><span data-stu-id="6fd63-142">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="6fd63-143">시작 하기 전에</span><span class="sxs-lookup"><span data-stu-id="6fd63-143">Before You Begin</span></span>

<span data-ttu-id="6fd63-144">Forefront Threat Management Gateway 2010를 리버스 프록시로 성공적으로 배포 하려면 Forefront Threat Management Gateway 2010 설명서에 정의 된 필수 구성 요소 및 하드웨어 요구 사항에 따라 서버를 설정 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-144">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="6fd63-145">계속 진행 하기 전에 하드웨어를 올바르게 구성 하 고 서버에 Forefront Threat Management 게이트웨이 2010를 설치 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6fd63-145">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="6fd63-146">Forefront TMG (위협 관리 게이트웨이) 2010</span><span class="sxs-lookup"><span data-stu-id="6fd63-146">Forefront Threat Management Gateway (TMG) 2010</span></span>](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="6fd63-147">Forefront TMG 2010 하드웨어 권장 사항</span><span class="sxs-lookup"><span data-stu-id="6fd63-147">Forefront TMG 2010 hardware recommendations</span></span>](http://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="6fd63-148">IIS ARR을 리버스 프록시로 성공적으로 배포 하려면 다음 항목을 검토 하 여 하드웨어 및 필수 구성 요소 소프트웨어를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-148">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="6fd63-149">Windows Server 2008 또는 Windows Server 2008 R2에 IIS를 설치 하려면 [Windows server 2008 또는 Windows server 2008 r2에 iis 7 설치](http://go.microsoft.com/fwlink/?linkid=291296) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6fd63-149">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](http://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="6fd63-150">Windows Server 2012에 IIS를 설치 하려면 [Windows server 2012에 iis 8 설치](http://go.microsoft.com/fwlink/?linkid=291297) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6fd63-150">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](http://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="6fd63-151">Windows Server 2012 R2에 IIS를 설치 하려면 [Windows server 2012 r2에 iis 8.5 설치](http://go.microsoft.com/fwlink/?linkid=330687) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6fd63-151">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="6fd63-152">IIS에 대 한 응용 프로그램 요청 라우팅 확장을 다운로드 하려면 [응용 프로그램 요청 라우팅 v 2.5 다운로드](http://go.microsoft.com/fwlink/?linkid=291298) 의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-152">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](http://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="6fd63-153">[설치 프로그램 요청 라우팅 버전 2](http://go.microsoft.com/fwlink/?linkid=291299) 의 지침에 대해 ARR을 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="6fd63-153">To install ARR, for the instructions at [Install Application Request Routing Version 2](http://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6fd63-154">현재 게시 된 지침은 ARR 2.0에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-154">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="6fd63-155">확장을 설치 하는 경우 두 버전 간에 차이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6fd63-155">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

