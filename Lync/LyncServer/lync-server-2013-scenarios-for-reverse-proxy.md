---
title: 'Lync Server 2013: 역방향 프록시에 대 한 시나리오'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82d5874393e69083ee7058e4e737d21a2fe865ad
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="89b88-102">Lync Server 2013의 역방향 프록시에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="89b88-102">Scenarios for reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89b88-103">_**마지막으로 수정 된 항목:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="89b88-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="89b88-104">Lync Server 2013에는 모임 및 전화 접속 단순 Url, 주소록, 모임 콘텐츠, 메일 그룹 확장, 모바일 서비스 등의 서비스 및 리소스에 대 한 액세스 권한을 제공 하기 위해 역방향 프록시가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-104">Reverse proxies are required in Lync Server 2013 for providing access to services and resources such as the meeting and dial-in Simple URLs, address book, meeting content, distribution list expansion, mobility services, and others.</span></span> <span data-ttu-id="89b88-105">Lync Server 2013의 일반적인 역방향 프록시 시나리오는 디렉터 또는 프런트 엔드 서버 외부 웹 서비스에 대 한 외부 클라이언트 (예: 데스크톱 클라이언트 또는 Lync Web App 클라이언트) 액세스를 허용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-105">The typical reverse proxy scenario in Lync Server 2013 is to allow external clients (for example, the desktop client or Lync Web App client) access to the Director or Front End Server external Web Services.</span></span>

<span data-ttu-id="89b88-106">**역방향 프록시 및 외부 웹 서비스**</span><span class="sxs-lookup"><span data-stu-id="89b88-106">**Reverse proxy and external web services**</span></span>

<span data-ttu-id="89b88-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="89b88-107">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>

<span data-ttu-id="89b88-108">계획 단계 중에 Lync Server 2013 배포의 역방향 프록시에 대 한 요구 사항을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-108">During the planning phase, you define the requirements for the reverse proxy in a Lync Server 2013 deployment.</span></span> <span data-ttu-id="89b88-109">역방향 프록시를 사용 하면 다음 외부 클라이언트의 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-109">The reverse proxy enables access to features for the following external clients:</span></span>

  - <span data-ttu-id="89b88-110">Microsoft Lync 2013 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="89b88-110">Microsoft Lync 2013 desktop client</span></span>

  - <span data-ttu-id="89b88-111">Microsoft Lync Web App</span><span class="sxs-lookup"><span data-stu-id="89b88-111">Microsoft Lync Web App</span></span>

  - <span data-ttu-id="89b88-112">Microsoft Lync 모바일</span><span class="sxs-lookup"><span data-stu-id="89b88-112">Microsoft Lync Mobile</span></span>

  - <span data-ttu-id="89b88-113">Lync Windows 스토어 앱</span><span class="sxs-lookup"><span data-stu-id="89b88-113">Lync Windows Store app</span></span>

<span data-ttu-id="89b88-114">Lync Server 2013 배포를 계획할 때는 Lync Server 2013에 대 한 실제 요구 사항을 역방향 프록시 기능에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-114">When planning your Lync Server 2013 deployment, you map the actual requirements for Lync Server 2013 to the reverse proxy features.</span></span>

1.  <span data-ttu-id="89b88-115">외부 클라이언트는 TCP 443 포트의 역방향 프록시에 연결 되 고 SSL (secure sockets layer) 또는 TLS (전송 계층 보안)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-115">External clients will connect to the reverse proxy on port TCP 443 and will use secure socket layer (SSL) or transport layer security (TLS).</span></span> <span data-ttu-id="89b88-116">Microsoft Lync 모바일 클라이언트는 TCP 80 포트에 연결할 수 있지만, Lync 검색 서비스에 대 한 초기 연결을 수행 하 고 관리자가 적절 한 DNS (domain name system) CNAME (또는 별칭) 레코드를 구성한 경우에만이 통신은 암호화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-116">Microsoft Lync Mobile clients can connect on port TCP 80, but only when performing the initial connection to the Lync discover services and the administrator has configured the proper domain name system (DNS) CNAME (or alias) records, and accepts that this communication will not be encrypted.</span></span>

2.  <span data-ttu-id="89b88-117">Lync Server 2013 external web services (프런트 엔드 서버 및/또는 디렉터에 배포 됨)는 TCP 4443 포트의 역방향 프록시 연결을 기대 하며 연결이 SSL/TLS가 될 것으로 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-117">Lync Server 2013 external web services (deployed on the Front End Server and/or the Director) expect a connection from a reverse proxy on port TCP 4443, and it expects that the connection will be SSL/TLS.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="89b88-118">외부 웹 서비스에 대해 제안 되는 기본 수신 대기 포트는 HTTP 트래픽의 경우 TCP 8080이 고 HTTPS 트래픽의 경우 TCP 4443입니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-118">The suggested default listening ports for the external web services are TCP 8080 for HTTP traffic, and TCP 4443 for HTTPS traffic.</span></span> <span data-ttu-id="89b88-119">토폴로지 작성기를 통해 기본 설정을 재정의 하 고 외부 웹 서비스에 대해 자체 수신 대기 포트를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-119">Topology Builder provides an opportunity to override the defaults and define your own listening ports for the external web services.</span></span> <span data-ttu-id="89b88-120">역방향 프록시는 외부 웹 서비스와 통신 하 고 외부 클라이언트는 역방향 프록시와 통신 한다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-120">It’s important to note that the reverse proxy communicates with the external web services, and the external clients communicate with the reverse proxy.</span></span> <span data-ttu-id="89b88-121">외부 클라이언트는 포트 TCP 443의 역방향 프록시와 통신 하지만 역방향 프록시가 외부 웹 서비스와 통신 하는 포트를 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-121">The external client communicates with the reverse proxy on port TCP 443, but you can redefine what port the reverse proxy communicates with the external web services on.</span></span> <span data-ttu-id="89b88-122">토폴로지 작성기의 옵션을 사용 하 여 웹 서비스의 기본 수신 대기 포트를 재정의 하면 인프라에서 발생할 수 있는 수신 대기 포트 충돌을 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-122">The options in Topology Builder to override the default listening ports for the web services allows you to resolve listening port conflicts that may arise in your infrastructure.</span></span>

    
    </div>

3.  <span data-ttu-id="89b88-123">Lync Server 2013 외부 웹 서비스는 클라이언트에서 수정 되지 않은 호스트 헤더가 클라이언트에서 사용 하려는 서비스 및 웹 서버 디렉터리를 식별 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-123">Lync Server 2013 external web services expect an unmodified Host Header from the client to identify what service and web server directory the client is attempting to use.</span></span> <span data-ttu-id="89b88-124">요청이 역방향 프록시에서 보낸 것 처럼 표시 되어야 함</span><span class="sxs-lookup"><span data-stu-id="89b88-124">Requests should appear as if they came from the reverse proxy</span></span>

4.  <span data-ttu-id="89b88-125">외부 웹 서비스는 클라이언트에 제공 되는 서비스를 제공 하는 정의 된 vDir (웹 서버 가상 디렉터리)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-125">The external web services use defined web server virtual directories (vDir) that provide the services offered to clients.</span></span> <span data-ttu-id="89b88-126">특정 외부에서 식별할 수 있는 웹 서비스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-126">Specific externally identifiable web services are:</span></span>
    
      - <span data-ttu-id="89b88-127">웹 전화 회의에 대 한 vDir "모임"</span><span class="sxs-lookup"><span data-stu-id="89b88-127">The “Meet” vDir for web conference meetings</span></span>
    
      - <span data-ttu-id="89b88-128">전화 액세스 및 전화 회의에 대 한 "전화 접속" vDir</span><span class="sxs-lookup"><span data-stu-id="89b88-128">The “Dialin” vDir for phone access and phone conferencing</span></span>
    
      - <span data-ttu-id="89b88-129">Lync Windows 스토어 앱, Lync Mobile 및 데스크톱 클라이언트 Lync 2013에 대 한 "자동 검색" vDir</span><span class="sxs-lookup"><span data-stu-id="89b88-129">The “Autodiscover” vDir for Lync Windows Store app, Lync Mobile, and the desktop client Lync 2013.</span></span> <span data-ttu-id="89b88-130">Lync Server 2013의 자동 검색은 DNS 이름 "lyncdiscover"에서 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-130">Autodiscover in Lync Server 2013 is known by the DNS name “lyncdiscover”</span></span>
    
      - <span data-ttu-id="89b88-131">정의 되지 않은 서비스는 외부 웹 서비스를 직접 호출 하 여 외부 클라이언트에서 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-131">Services not defined are accessed by the external client by direct calls to the external web services.</span></span> <span data-ttu-id="89b88-132">예를 들어 DLX (메일 그룹 확장) 및 ABS (주소록 서비스)에는 외부 웹 서비스 및 관련 vDirs에 대 한 직접 호출을 통해 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-132">For example, distribution group expansion (DLX) and the address book service (ABS) are accessed by direct calls to the external web services and associated vDirs.</span></span> <span data-ttu-id="89b88-133">클라이언트는 vDir의 실제 경로를 알고 있으며이 정보를 기반으로 하 여 URL (uniform record locator)을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-133">The client knows the actual path to the vDir and constructs a uniform record locator (URL) based on this information.</span></span> <span data-ttu-id="89b88-134">클라이언트는 다음과 비슷한 URL을 사용 하 여 주소록 서비스에 액세스 합니다.`https://externalweb.contoso.com/abs/handler`</span><span class="sxs-lookup"><span data-stu-id="89b88-134">The client would access the address book service using a URL similar to `https://externalweb.contoso.com/abs/handler`</span></span>
    
      - <span data-ttu-id="89b88-135">Lync Server 토폴로지의 일부로 회의를 정의 하 고 구성 하는 경우 Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="89b88-135">The Office Web Apps Server when conferencing is defined and configured as part of the Lync Server topology</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="89b88-136">Office Web Apps 서버는 별도의 역할 서버 이며, 외부 웹 서비스의 일부로 구성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-136">The Office Web Apps Server is a separate role server and is not configured as part of the external web services.</span></span> <span data-ttu-id="89b88-137">이 서버는 클라이언트 액세스를 위해 별도로 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-137">This server is separately published for client access.</span></span>

        
        </div>

5.  <span data-ttu-id="89b88-138">각 서비스에 대해 SSL 브리징을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-138">Define SSL bridging for each service.</span></span> <span data-ttu-id="89b88-139">외부 포트 TCP 443이 TCP 4443의 외부 웹 서비스 포트에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-139">The external port TCP 443 is mapped to the external web services port of TCP 4443.</span></span> <span data-ttu-id="89b88-140">암호화 되지 않은 HTTP의 경우 tcp 80 포트가 외부 웹 서비스 포트 TCP 8080에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-140">For unencrypted HTTP, port TCP 80 is mapped to the external web services port TCP 8080</span></span>

6.  <span data-ttu-id="89b88-141">웹 서버 리소스를 게시 하는 역방향 프록시 수신기 계획</span><span class="sxs-lookup"><span data-stu-id="89b88-141">Plan for reverse proxy listeners to publish web server resources</span></span>

7.  <span data-ttu-id="89b88-142">제공 될 서비스를 기반으로 역방향 프록시에 대 한 인증서를 요청 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-142">Request and configure the certificate for the reverse proxy based on the services that will be offered.</span></span> <span data-ttu-id="89b88-143">올바른 주체 대체 이름으로 구성 된 경우이 인증서는 역방향 프록시 서버의 구성 된 모든 수신기에서 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b88-143">If configured with the correct subject alternative names, this certificate can be shared by all configured listeners on the reverse proxy server</span></span>

<span data-ttu-id="89b88-144">역방향 프록시 배포 계획 시 사용 가능한 리소스</span><span class="sxs-lookup"><span data-stu-id="89b88-144">Resources available for planning your reverse proxy deployment:</span></span>

  - [<span data-ttu-id="89b88-145">Lync Server 2013의 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="89b88-145">Data collection in Lync Server 2013</span></span>](lync-server-2013-data-collection.md)

  - [<span data-ttu-id="89b88-146">인증서 요약-Lync Server 2013의 역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="89b88-146">Certificate summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [<span data-ttu-id="89b88-147">포트 요약-Lync Server 2013의 역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="89b88-147">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="89b88-148">Lync Server 2013의 DNS 요약-역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="89b88-148">DNS summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

