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
ms.openlocfilehash: 4dc50b7eedf6aa815c52b44ed4c1ddb88cea5217
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="f345d-102">Lync Server 2013에 대 한 자동 검색 서비스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f345d-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f345d-103">_**마지막으로 수정 된 항목:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="f345d-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="f345d-104">디렉터 및 프런트 엔드 풀 서버에서 실행 되는 Microsoft Lync Server 2013 자동 검색 서비스와 DNS에 게시 된 경우 Lync Mobile을 실행 하는 모바일 장치에서 모바일 서비스를 찾는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="f345d-105">Lync Mobile을 실행 하는 모바일 장치에서는 자동 검색 기능을 활용할 수 있도록 하기 전에 자동화 서비스를 실행 하는 모든 디렉터 및 프런트 엔드 서버에서 인증서 주체 대체 이름 목록을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="f345d-106">또한 역방향 프록시에 대한 외부 웹 서비스 게시 규칙에 사용되는 인증서에서도 주체 대체 이름 목록을 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="f345d-107">디렉터, 프런트 엔드 서버 및 역방향 프록시에 필요한 주체 대체 이름 항목에 대 한 자세한 내용은 모바일 기능 계획의 [Lync Server 2013에서 모바일 기능에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f345d-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="f345d-108">자동 검색 서비스를 게시하는 포트(포트 80 또는 포트 443)에 따라 역방향 프록시에서 주체 대체 이름 목록을 사용할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="f345d-109">**포트 80**   에 게시 자동 검색 서비스에 대 한 초기 쿼리가 포트 80를 통해 수행 되는 경우 인증서 변경이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="f345d-110">Lync를 실행 하는 모바일 장치는 외부에서 포트 80의 역방향 프록시에 액세스 한 다음 내부적으로 포트 8080에서 디렉터 또는 프런트 엔드 서버로 리디렉션되도록 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="f345d-111">자세한 내용은 이 항목 뒷부분의 "포트 80을 사용하는 초기 자동 검색 프로세스" 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f345d-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="f345d-112">**포트 443**   에 게시 외부 웹 서비스 게시 규칙에서 사용 하는 인증서의 주체 대체 이름 목록에는 \*lyncdiscover가 포함\< 되어야 합니다. 조직\> \* 내의 각 SIP 도메인에 대 한 microsoft.rtc.management.xds.sipdomain object 항목</span><span class="sxs-lookup"><span data-stu-id="f345d-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="f345d-113">내부 인증 기관을 사용 하 여 인증서 재발급은 일반적으로 단순 진행 되지만, 웹 서비스 게시 규칙에 사용 되는 공용 인증서의 경우에는 여러 주체 대체 이름 항목을 추가 하는 데 많은 비용이 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="f345d-114">이 문제를 해결 하려면 포트 80을 통한 초기 자동 검색 연결을 지원 하며, 그러면 디렉터 또는 프런트 엔드 서버의 포트 8080로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="f345d-115">예를 들어 Lync Mobile을 실행 하는 모바일 클라이언트는 초기 요청에 대해 HTTP를 사용 하 여 자동 검색 기능을 사용 하 여 Lync Server 2013에 로그인 하도록 구성 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="f345d-116">포트 80을 사용 하는 모바일 장치에 대 한 초기 자동 검색 프로세스</span><span class="sxs-lookup"><span data-stu-id="f345d-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="f345d-117">Lync Mobile을 실행 하는 모바일 장치가 DNS를 사용 하 여 A 레코드가 있는 lyncdiscover.contoso.com을 조회 합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="f345d-118">외부 DNS는 외부 웹 서비스의 IP 주소를 클라이언트에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="f345d-119">Lync Mobile을 실행 하는 모바일 http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com 장치가 역방향 프록시로 요청을 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="f345d-120">웹 게시 규칙은 포트 80에서 포트 8080 내부로 요청을 브리지로 연결 하 여 디렉터 또는 프런트 엔드 서버로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="f345d-121">요청은 HTTPS가 아닌 HTTP이므로 자동 검색 서비스를 지원하기 위해 외부 웹 서비스 게시 규칙의 인증서를 수정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="f345d-122">자동 검색 서비스에서 외부 웹 서비스 URL을 HTTPS 형식으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="f345d-123">Lync Mobile을 실행 하는 모바일 장치는 포트 443의 역방향 프록시에 다시 연결 하 고 4443을 통해 사용자의 홈 풀에서 실행 되는 모바일 서비스로 리디렉션될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="f345d-124">HTTPS 쿼리는 외부 웹 서비스 URL과 자동 검색 서비스 URL을 비교하므로, 인증서에 외부 웹 서비스 FQDN(정규화된 도메인 이름)에 대한 주체 대체 이름 항목이 이미 포함되어 있기 때문에 정상적으로 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="f345d-125">이 시나리오에서는 모바일 기능을 지원하기 위해 인증서를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f345d-126">대상 웹 서버의 인증서에 주체 대체 이름 목록 값으로 lyncdiscover.contoso.com과 일치하는 값이 포함되어 있지 않은 경우에는 다음과 같은 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="f345d-127">&nbsp;는 "server Hello"로 응답 하며 인증서를 포함 하지&nbsp;&nbsp;않습니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="f345d-128">b. Lync mobile을 실행 하는&nbsp;모바일 장치에서 즉시 세션을 종료 합니다.&nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="f345d-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="f345d-129">대상 웹 서버의 인증서에 주체 대체 이름 목록 값으로 lyncdiscover.contoso.com이 포함되어 있는 경우에는 다음과 같은 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="f345d-130">a.&nbsp;&nbsp;&nbsp;웹 서버는 "서버 hello"와 인증서로 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="f345d-131">b. Lync mobile을 실행 하는&nbsp;모바일 장치가 인증서의 유효성을 검사 하 고 핸드셰이크를 완료 합니다.&nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="f345d-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="f345d-132">역방향 프록시 서버에서 포트 80을 사용하는 초기 자동 검색 서비스 연결을 지원하려면 Forefront Threat Management Gateway 2010 역방향 프록시 웹 게시 규칙에 대해 이 예제와 비슷한 http 게시 규칙을 만들면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="f345d-133">**Lync Server 자동 검색(HTTP)** 과 같은 새 웹 게시 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="f345d-134">**공개 이름**에 lyncdiscover.contoso.com을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="f345d-135">**브리징** 탭에서 포트 80에서 포트 8080으로의 요청을 브리지하는 옵션만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="f345d-136">**인증** 탭에서 **인증 안 함** 및 **클라이언트에서 직접 인증할 수 없음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="f345d-137">변경 내용을 커밋하고 규칙을 Lync 규칙 목록 맨 위로 이동 합니다 (먼저 처리 순서 대로).</span><span class="sxs-lookup"><span data-stu-id="f345d-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="f345d-138">분할 도메인 배포의 모바일 기능</span><span class="sxs-lookup"><span data-stu-id="f345d-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="f345d-139">*분할 도메인* 또는 *하이브리드 배포*라고도 하는 공유 SIP 주소 공간은 사용자가 온-프레미스 배포 및 온라인 환경 전체에 배포되는 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="f345d-140">이 경우 적절한 결과는 홈 서버의 위치(온-프레미스 또는 온라인)에 관계없이 사용자가 배포로 로그인하면 홈 서버 위치로 리디렉션되도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="f345d-141">이 작업을 수행 하기 위해 Microsoft Lync Server 2013의 자동 검색 기능을 사용 하 여 온라인 사용자를 온라인 토폴로지로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="f345d-142">이 작업은 Lync Server 관리 셸을 사용 하 여 자동 검색 URL (uniform resource locator) 및 cmdlet **Get-cshostingprovider** 및 **Set-cshostingprovider**를 구성 하 여 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="f345d-143">수집 및 기록해야 하는 배포된 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="f345d-144">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="f345d-p105">결과에서 **ProxyFQDN** 특성이 포함된 온라인 공급자를 찾습니다. 예를 들면 sipfed.online.lync.com과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-p105">In the results, find the online provider with the attribute **ProxyFQDN**. For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="f345d-147">ProxyFQDN의 값을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="f345d-148">온-프레미스 Lync Server 제어판에서 페더레이션을 사용 하도록 설정 하 여 온라인 공급자와의 페더레이션을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="f345d-p106">온라인 공급자에 대한 페더레이션을 사용하도록 설정합니다. 기본적으로 모든 온라인 사용자는 도메인 페더레이션에 대해 사용하도록 설정되며 모든 도메인과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-p106">Enable federation for the online provider. By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="f345d-151">차단 도메인 및 허용 도메인을 정의하려는 경우 명시적으로 허용하거나 차단할 도메인을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="f345d-152">온라인 페더레이션의 경우 방화벽 예외, 인증서 및 DNS 호스트(A 또는 IPv6 사용 시 AAAA) 레코드를 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="f345d-153">또한 페더레이션 정책도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f345d-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="f345d-154">자세한 내용은 [Lync Server 2013 및 Office Communications Server Federation 계획](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f345d-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

