---
title: 'Lync Server 2013: 자동 검색 서비스 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 777d70b20a51e5408fe9d9248028c3dbcaebeba2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="215ec-102">Lync Server 2013에 대한 자동 검색 서비스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="215ec-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="215ec-103">_**마지막으로 수정한 주제:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="215ec-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="215ec-104">Microsoft Lync Server 2013 자동 검색 서비스는 디렉터 및 프런트 엔드 풀 서버에서 실행 되며 DNS에 게시 되는 경우 Lync Mobile을 실행 하는 모바일 장치에서 모바일 서비스를 찾기 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="215ec-105">Lync Mobile을 실행 하는 모바일 장치에서 자동 검색 기능을 활용할 수 있으려면 우선 검색 서비스를 실행 하는 모든 디렉터 및 프런트 엔드 서버에서 인증서 주체 대체 이름 목록을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="215ec-106">또한 역방향 프록시에서 외부 웹 서비스 게시 규칙에 사용 되는 인증서의 주체 대체 이름 목록을 수정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="215ec-107">디렉터, 프런트 엔드 서버 및 역방향 프록시에 필요한 주체 대체 이름 항목에 대 한 자세한 내용은 모바일 기능 계획에서 [Lync Server 2013의 모바일 기능에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="215ec-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="215ec-108">리버스 프록시에서 주체 대체 이름 목록을 사용 하는 것에 대 한 결정은 포트 80 또는 포트 443에 자동 검색 서비스를 게시할지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="215ec-109">**포트 80**   에 게시 된 자동 검색 서비스에 대 한 초기 쿼리가 포트 80를 통해 발생 하는 경우 인증서 변경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="215ec-110">Lync를 실행 하는 모바일 장치는 포트 80의 역방향 프록시에 액세스 한 다음 내부적으로 포트 8080의 디렉터 또는 프런트 엔드 서버로 리디렉션되 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="215ec-111">자세한 내용은이 항목의 뒷부분에 나오는 "포트 80를 사용 하 여 초기 자동 검색 프로세스" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="215ec-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="215ec-112">**포트 443**   에 게시 됨 외부 웹 서비스 게시 규칙에 사용 되는 인증서의 주체 대체 이름 목록에는 \*lyncdiscover을\< 포함 해야 합니다. 조직\> \* 내 각 SIP 도메인에 대 한 sipdomain 항목.</span><span class="sxs-lookup"><span data-stu-id="215ec-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="215ec-113">내부 인증 기관을 사용 하 여 인증서를 재발급 하는 것은 일반적으로 간단한 프로세스 이지만, 웹 서비스 게시 규칙에 사용 되는 공개 인증서의 경우 여러 주체의 대체 이름 항목을 추가 하는 데 많은 비용이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="215ec-114">이 문제를 해결 하려면 포트 80을 통한 초기 자동 검색 연결을 지원 하 고, 그런 다음 디렉터 또는 프런트 엔드 서버의 포트 8080로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="215ec-115">예를 들어 Lync Mobile을 실행 하는 모바일 클라이언트가 초기 요청에 대해 HTTP를 사용 하 여 자동 검색 기능을 사용 하 여 Lync Server 2013에 로그인 하도록 구성 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="215ec-116">포트 80를 사용 하는 모바일 장치에 대 한 초기 자동 검색 프로세스</span><span class="sxs-lookup"><span data-stu-id="215ec-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="215ec-117">Lync Mobile을 실행 하는 모바일 장치가 DNS를 사용 하 여 A 레코드가 있는 lyncdiscover.contoso.com을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="215ec-118">외부 DNS는 외부 웹 서비스의 IP 주소를 클라이언트에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="215ec-119">Lync Mobile을 실행 하는 모바일 http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com 장치가 리버스 프록시로 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="215ec-120">웹 게시 규칙은 포트 80에서 내부적으로 포트 8080로 요청을 연결 하 고, 그 후에는 디렉터 또는 프런트 엔드 서버로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="215ec-121">요청이 HTTP이 고 HTTPS가 아니기 때문에 자동 검색 서비스를 지원 하기 위해 외부 웹 서비스 게시 규칙의 인증서에 대 한 수정이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="215ec-122">자동 검색 서비스는 외부 웹 서비스 Url (HTTPS 형식)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="215ec-123">그러면 Lync Mobile을 실행 하는 모바일 장치에서 포트 443의 역방향 프록시에 다시 연결할 수 있으며, 사용자의 홈 풀에서 실행 되는 모바일 서비스로 4443을 통해 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="215ec-124">HTTPS 쿼리는 외부 웹 서비스 URL 및 자동 검색 서비스 URL에 대 한 것 이기 때문에, 인증서에는 외부 웹 서비스의 정규화 된 도메인 이름 (Fqdn)에 대 한 주체 대체 이름 항목이 이미 포함 되어 있기 때문에 성공적으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="215ec-125">이 시나리오에서는 이동성을 지 원하는 데 필요한 인증서 변경이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="215ec-126">대상 웹 서버에 lyncdiscover.contoso.com에 대 한 일치 하는 값이 없는 인증서가 주체 대체 이름 목록 값으로 표시 되는 경우:</span><span class="sxs-lookup"><span data-stu-id="215ec-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="215ec-127">&nbsp;는 "서버 Hello" 및 인증서 없이 응답&nbsp;&nbsp;합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="215ec-128">b. Lync mobile을 실행 하는&nbsp;모바일 장치에서 즉시 세션을 종료 합니다.&nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="215ec-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="215ec-129">대상 웹 서버에 lyncdiscover.contoso.com를 주체 대체 이름 목록 값으로 포함 하는 인증서가 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="215ec-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="215ec-130">a.&nbsp;&nbsp;&nbsp;웹 서버는 "서버 hello" 및 인증서로 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="215ec-131">b. Lync mobile을 실행 하는&nbsp;모바일 장치에서 인증서의 유효성을 검사 하 고 핸드셰이크를 완료 합니다.&nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="215ec-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="215ec-132">역방향 프록시 서버에서 포트 80를 사용 하 여 자동 검색 서비스에 대 한 초기 연결을 지원 하기 위해, Forefront Threat Management Gateway 2010 리버스 프록시 웹 게시 규칙에 대해이 예제와 유사한 http 게시 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="215ec-133">새 웹 게시 규칙을 만듭니다 (예: **Lync Server 자동 검색 (HTTP)**).</span><span class="sxs-lookup"><span data-stu-id="215ec-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="215ec-134">**공개 이름**에 lyncdiscover.contoso.com를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="215ec-135">**브리징** 탭에서 포트 80에서 포트 8080로의 브리지 요청에 대 한 옵션만 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="215ec-136">**인증** 탭에서 **인증 없음을**선택 하면 **클라이언트가 직접 인증할 수 없습니다**.</span><span class="sxs-lookup"><span data-stu-id="215ec-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="215ec-137">변경 내용을 커밋하고 규칙을 Lync 규칙 목록 맨 위로 이동 합니다 (첫 번째 처리 순서).</span><span class="sxs-lookup"><span data-stu-id="215ec-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="215ec-138">도메인 분할 배포에 대 한 이동성</span><span class="sxs-lookup"><span data-stu-id="215ec-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="215ec-139">공유 SIP 주소 공간 ( *분할 도메인*이 라고도 함) 또는 *하이브리드 배포* 는 사용자가 온-프레미스 배포 및 온라인 환경에서 배포 하는 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="215ec-140">원하는 결과는 사용자가 홈 서버의 위치 (온-프레미스 또는 온라인)에 관계 없이 배포에 로그인 하 고 해당 홈 서버 위치로 리디렉션되도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="215ec-141">이를 위해 Microsoft Lync Server 2013의 자동 검색 기능은 온라인 사용자를 온라인 토폴로지로 리디렉션하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="215ec-142">이 작업은 Lync Server 관리 셸 및 cmdlet **Get-cshostingprovider** 및 **Set/cshostingprovider**를 사용 하 여 URL 자동 검색을 구성 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="215ec-143">다음과 같은 배포 된 특성을 수집 하 여 기록해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="215ec-144">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="215ec-145">결과에서 **Proxyfqdn**특성이 있는 온라인 공급자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-145">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="215ec-146">예를 들어 sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="215ec-146">For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="215ec-147">ProxyFQDN의 값을 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="215ec-148">온라인 공급자와 페더레이션 할 수 있도록 온-프레미스 Lync Server 제어판에서 페더레이션 사용</span><span class="sxs-lookup"><span data-stu-id="215ec-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="215ec-149">온라인 공급자에 대해 페더레이션을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-149">Enable federation for the online provider.</span></span> <span data-ttu-id="215ec-150">기본적으로 모든 온라인 사용자는 도메인 페더레이션에 대해 사용 하도록 설정 되어 있으며 모든 도메인과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-150">By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="215ec-151">차단 되 고 허용 된 도메인을 정의 하는 경우 명시적으로 허용 하거나 차단 하는 도메인을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="215ec-152">온라인 페더레이션의 경우 방화벽 예외, 인증서 및 DNS 호스트 (IPv6을 사용 하는 경우 A 또는 AAAA) 레코드를 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="215ec-153">또한 페더레이션 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="215ec-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="215ec-154">자세한 내용은 [Lync server 2013 및 Office Communications server federation에 대 한 계획](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="215ec-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

