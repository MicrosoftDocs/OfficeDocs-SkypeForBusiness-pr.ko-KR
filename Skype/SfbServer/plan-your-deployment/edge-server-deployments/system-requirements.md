---
title: 비즈니스용 Skype 서버의에 지 서버 시스템 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: ed53a566-0504-46f9-81a7-116a637833af
description: '요약: 비즈니스용 Skype 서버에서에 지 서버에 대 한 시스템 요구 사항에 대해 알아봅니다.'
ms.openlocfilehash: ce68475ffc2534f686b39bbcdbcd46b7cdee735a
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221028"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a><span data-ttu-id="3a584-103">비즈니스용 Skype 서버의에 지 서버 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a584-103">Edge Server system requirements in Skype for Business Server</span></span>
 
<span data-ttu-id="3a584-104">**요약:** 비즈니스용 Skype 서버에서에 지 서버에 대 한 시스템 요구 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-104">**Summary:** Learn about the system requirements for Edge Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="3a584-105">비즈니스용 Skype 서버에 지 서버 배포의 경우 환경 구조에 대 한 계획 뿐 아니라 환경 자체에 있는 서버에 대해 수행 해야 하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-105">When it comes to your Skype for Business Server Edge Server deployment, these are the things you'll need to do for the server or servers that are in the environment itself, as well as planning for the environment structure.</span></span> <span data-ttu-id="3a584-106">토폴로지, DNS, 인증서 및 기타 인프라 관련 문제에 대 한 자세한 내용은 환경 요구 사항 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a584-106">For more information on topology, DNS, certificates, and other infrastructure concerns, check out the environmental requirements documentation.</span></span>
  
## <a name="components"></a><span data-ttu-id="3a584-107">구성 요소</span><span class="sxs-lookup"><span data-stu-id="3a584-107">Components</span></span>

<span data-ttu-id="3a584-108">에 지 서버 환경에 대 한 자세한 내용은 경계 네트워크에 배포 된 구성 요소 (예를 들어, 작업 그룹이 나 비즈니스용 Skype 서버 도메인 구조 외부에 있는 도메인)를 포함 하는 대부분의 경우에 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-108">When discussing the Edge Server environment, we're referencing components that are, for the most part, deployed in a perimeter network (that's to say it's either in a workgroup or a domain that's outside your Skype for Business Server domain structure).</span></span>
  
<span data-ttu-id="3a584-109">이에 대 한 자세한 내용은 Edge를 배포할 때 염두에 두어야 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-109">Keeping that in mind, these are the components you're going to need to keep in mind for deploying your Edge successfully:</span></span>
  
- [<span data-ttu-id="3a584-110">에 지 서버</span><span class="sxs-lookup"><span data-stu-id="3a584-110">Edge Servers</span></span>](system-requirements.md#EdgeServers)
    
- [<span data-ttu-id="3a584-111">역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="3a584-111">Reverse proxies</span></span>](system-requirements.md#ReverseProxies)
    
- [<span data-ttu-id="3a584-112">방화벽</span><span class="sxs-lookup"><span data-stu-id="3a584-112">Firewalls</span></span>](system-requirements.md#Firewalls)
    
- <span data-ttu-id="3a584-113">[디렉터](system-requirements.md#Directors) (이 옵션은 선택 사항이 며 포함 된 경우 내부 네트워크에 배치 됨)</span><span class="sxs-lookup"><span data-stu-id="3a584-113">[Directors](system-requirements.md#Directors) (these are optional, and if they're included, they'll be located on your internal network)</span></span>
    
- <span data-ttu-id="3a584-114">[부하 분산 장치](system-requirements.md#LoadBalancers) (DNS 부하 분산 또는 HLB (하드웨어 부하 분산 장치)를 사용할 수 있지만 단일에 지 서버에 대해이는 필요 하지 않음)</span><span class="sxs-lookup"><span data-stu-id="3a584-114">[Load Balancers](system-requirements.md#LoadBalancers) (you can have DNS load balancing or a hardware load balancer (HLB), but for a single Edge Server, this isn't needed)</span></span>
    
<span data-ttu-id="3a584-115">아래에서 각 작업에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-115">We have more detail on each of these below:</span></span>
  
### <a name="edge-servers"></a><span data-ttu-id="3a584-116">에지 서버</span><span class="sxs-lookup"><span data-stu-id="3a584-116">Edge Servers</span></span>
<span data-ttu-id="3a584-117"><a name="EdgeServers"> </a></span><span class="sxs-lookup"><span data-stu-id="3a584-117"><a name="EdgeServers"> </a></span></span>

<span data-ttu-id="3a584-118">주변 환경에 배포 된 비즈니스용 Skype 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-118">These are the Skype for Business servers deployed in your perimeter environment.</span></span> <span data-ttu-id="3a584-119">여기서는 내부 비즈니스용 Skype 서버 배포에서 제공 하는 서비스에 대해 외부 사용자에 게 네트워크 트래픽을 보내고 수신 하는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-119">Their role is to send and receive network traffic to external users for the services offered by your internal Skype for Business Server deployment.</span></span> <span data-ttu-id="3a584-120">이 작업을 성공적으로 수행 하기 위해 각에 지 서버는 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-120">To do this successfully, each Edge Server runs:</span></span>
  
- <span data-ttu-id="3a584-121">**액세스에 지 서비스**: 아웃 바운드 및 인바운드 SIP (Session 착수 프로토콜) 트래픽에 대해 신뢰할 수 있는 단일 연결 지점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-121">**Access Edge service**: Provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>
    
- <span data-ttu-id="3a584-122">**웹 회의에 지 서비스**: 외부 사용자가 내부 비즈니스용 Skype 서버 환경에서 호스팅되는 모임에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-122">**Web Conferencing Edge service**: Enables external users to join meetings that are hosted on your internal Skype for Business Server environment.</span></span>
    
- <span data-ttu-id="3a584-123">**A/V에 지 서비스**: 외부 사용자가 오디오, 비디오, 응용 프로그램 공유 및 파일 전송을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-123">**A/V Edge service**: Makes audio, video, application sharing and file transfer available to external users.</span></span>
    
- <span data-ttu-id="3a584-124">**Xmpp 프록시 서비스**: 구성 된 Xmpp 페더레이션 파트너와의 xmpp (extensible messaging and 현재 상태 프로토콜) 메시지를 수락 하 고 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-124">**XMPP Proxy service**: Accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>
    
<span data-ttu-id="3a584-125">권한 있는 외부 사용자는에 지 서버를 사용 하 여 내부 비즈니스용 Skype 서버 배포에 연결할 수 있지만 그렇지 않은 경우에는 모든 사용자에 대해 내부 네트워크에 대 한 다른 액세스 권한을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-125">Authorized external users can use your Edge Servers to connect to your internal Skype for Business Server deployment, but otherwise, they provide no other access to your internal network for anyone.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a584-126">에 지 서버는 사용 하도록 설정 된 비즈니스용 Skype 클라이언트 및 기타에 지 서버 (페더레이션 시나리오)에 대 한 연결을 제공 하기 위해 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-126">Edge Servers are deployed to provide connections for enabled Skype for Business clients and other Edge Servers (in federation scenarios).</span></span> <span data-ttu-id="3a584-127">다른 끝점 클라이언트 또는 서버 유형에 서 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-127">You can't connect from other end point client or server types.</span></span> <span data-ttu-id="3a584-128">XMPP 게이트웨이 서버는 구성 된 XMPP 파트너와의 연결을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-128">The XMPP Gateway server can allow connections with configured XMPP partners.</span></span> <span data-ttu-id="3a584-129">하지만 다시 사용할 수 있는 유일한 클라이언트 및 페더레이션 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-129">But again, those are the only client and federation types that will work.</span></span> 

> [!NOTE]
> <span data-ttu-id="3a584-130">XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-130">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3a584-131">자세한 내용은 [XMPP 페더레이션 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a584-131">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="reverse-proxies"></a><span data-ttu-id="3a584-132">역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="3a584-132">Reverse proxies</span></span>
<span data-ttu-id="3a584-133"><a name="ReverseProxies"> </a></span><span class="sxs-lookup"><span data-stu-id="3a584-133"><a name="ReverseProxies"> </a></span></span>

<span data-ttu-id="3a584-134">역방향 프록시 (RP) 서버에는 비즈니스용 Skype 서버 역할이 없지만에는에 지 서버 배포의 필수 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-134">A reverse proxy (RP) server has no Skype for Business Server role, but is an essential component of an Edge Server deployment.</span></span> <span data-ttu-id="3a584-135">역방향 프록시를 통해 외부 사용자는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-135">A reverse proxy allows external users to:</span></span>
  
- <span data-ttu-id="3a584-136">단순 Url을 사용 하 여 모임 또는 전화 접속 회의에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-136">connect to meetings or dial-in conferences using simple URLs.</span></span>
    
- <span data-ttu-id="3a584-137">모임 콘텐츠를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-137">download meeting content.</span></span>
    
- <span data-ttu-id="3a584-138">메일 그룹을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-138">expand distribution groups.</span></span>
    
- <span data-ttu-id="3a584-139">클라이언트 인증서 기반 인증을 위해 사용자 기반 인증서 가져오기</span><span class="sxs-lookup"><span data-stu-id="3a584-139">get user-based certificates for client certificate based authentication</span></span>
    
- <span data-ttu-id="3a584-140">주소록 서버에서 파일을 다운로드 하거나 주소록 웹 쿼리 서비스에 쿼리를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-140">download files from the Address Book Server, or to submit queries to the Address Book Web Query service.</span></span>
    
- <span data-ttu-id="3a584-141">클라이언트 및 장치 소프트웨어에 대 한 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-141">obtain updates to client and device software.</span></span>
    
<span data-ttu-id="3a584-142">및 모바일 장치용:</span><span class="sxs-lookup"><span data-stu-id="3a584-142">And for mobile devices:</span></span>
  
- <span data-ttu-id="3a584-143">모바일 서비스를 제공 하는 프런트 엔드 서버를 자동으로 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-143">it lets them automatically discover Front End Servers offering mobility services.</span></span>
    
- <span data-ttu-id="3a584-144">Microsoft 365 또는 Office 365에서 모바일 장치로의 푸시 알림을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-144">it enables push notifications from Microsoft 365 or Office 365 to mobile devices.</span></span>
    
<span data-ttu-id="3a584-145">현재 역방향 프록시 권장 사항은 [비즈니스용 Skype에 대 한 전화 통신 인프라](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) 페이지에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-145">Our current reverse proxy recommendations can be found on the [Telephony Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span> <span data-ttu-id="3a584-146">따라서 역방향 프록시:</span><span class="sxs-lookup"><span data-stu-id="3a584-146">So your reverse proxy:</span></span>
  
- <span data-ttu-id="3a584-147">공용 인증서를 통해 환경에 도입 된 TLS (전송 계층 보안)를 사용 하 여 다음의 게시 된 외부 웹 서비스에 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-147">should be able to use transport layer security (TLS) that's introduced to your environment via public certificates to connect to the published external Web services of:</span></span>
    
  - <span data-ttu-id="3a584-148">디렉터 또는 디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="3a584-148">Director or Director pool</span></span>
    
  - <span data-ttu-id="3a584-149">프런트 엔드 서버 또는 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="3a584-149">Front End Server or Front End pool</span></span>
    
- <span data-ttu-id="3a584-150">암호화를 위해 인증서를 사용 하 여 내부 웹 사이트를 게시 하거나, 필요한 경우 암호화 되지 않은 방법으로 게시를 게시할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-150">needs to be able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>
    
- <span data-ttu-id="3a584-151">FQDN (정규화 된 도메인 이름)을 사용 하 여 외부적으로 호스트 된 웹 사이트를 게시할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-151">should be able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>
    
- <span data-ttu-id="3a584-152">호스트 된 웹 사이트의 모든 콘텐츠를 게시할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-152">needs to be able to publish all the contents of your hosted web site.</span></span> <span data-ttu-id="3a584-153">기본적으로 **/\\** 대부분의 웹 서버에서 인식 되는 \* 지시문을 사용 하 여 "웹 서버의 모든 콘텐츠 게시"를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-153">By default, you can use the **/\\**\* directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="3a584-154">\* \*/Uwca/ \\ \* \* \*와 같이 "가상 디렉터리의 모든 콘텐츠 게시"를 의미 하는 지시어를 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-154">You can also modify the directive—for example, \*\*/Uwca/\\*\*\*, which means "Publish all content under the virtual directory Ucwa."</span></span>
    
- <span data-ttu-id="3a584-155">게시 된 웹 사이트에서 콘텐츠를 요청 하는 클라이언트와의 TLS 연결이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-155">must require TLS connections with clients that request content from your published website.</span></span>
    
- <span data-ttu-id="3a584-156">주체 대체 이름 (SAN) 항목을 포함 하는 인증서를 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-156">has to accept certificates with subject alternative name (SAN) entries.</span></span>
    
- <span data-ttu-id="3a584-157">외부 웹 서비스 FQDN이 확인 하는 수신기 또는 인터페이스에 인증서 바인딩을 허용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-157">needs to be able to allow the binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="3a584-158">수신기 구성은 인터페이스 보다 더 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-158">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="3a584-159">단일 인터페이스에 여러 수신기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-159">Many listeners can be configured on a single interface.</span></span>
    
- <span data-ttu-id="3a584-160">호스트 헤더 처리의 구성을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-160">must allow for the configuration of host header handling.</span></span> <span data-ttu-id="3a584-161">요청 하는 클라이언트에서 보내는 원래 호스트 헤더를 역방향 프록시에서 수정 하는 대신 투명 하 게 전달 해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-161">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>
    
- <span data-ttu-id="3a584-162">외부적으로 정의 된 특정 포트 (예: TCP 443)에서 정의 된 다른 포트 (예: TCP 4443)로 TLS 트래픽을 브리징 하도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-162">should allow bridging of TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="3a584-163">역방향 프록시는 수신 시에 패킷을 암호 해독 한 다음 송신 시에 패킷을 다시 암호화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-163">Your reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>
    
- <span data-ttu-id="3a584-164">tcp 80와 같은 한 포트에서 다른 포트로 암호화 되지 않은 TCP 트래픽을 브리징 하도록 허용 해야 합니다 (예: TCP 8080).</span><span class="sxs-lookup"><span data-stu-id="3a584-164">should allow bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>
    
- <span data-ttu-id="3a584-165">구성, 허용, NTLM 인증, 인증 안 함 및 통과 인증을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-165">needs to allow configuration of, or accept, NTLM authentication, no authentication, and pass-through authentication.</span></span>
    
<span data-ttu-id="3a584-166">역방향 프록시가이 목록의 모든 요구 사항을 처리할 수 있는 경우에는이 단계를 수행 하는 것이 좋지만, 앞에서 제공 하는 링크에 대 한 권장 사항을 염두에 두십시오.</span><span class="sxs-lookup"><span data-stu-id="3a584-166">If your reverse proxy can address all the needs in this list, you should be good to go, but please keep in mind our recommendations at the link provided above.</span></span>
  
### <a name="firewalls"></a><span data-ttu-id="3a584-167">방화벽</span><span class="sxs-lookup"><span data-stu-id="3a584-167">Firewalls</span></span>
<span data-ttu-id="3a584-168"><a name="Firewalls"> </a></span><span class="sxs-lookup"><span data-stu-id="3a584-168"><a name="Firewalls"> </a></span></span>

<span data-ttu-id="3a584-169">에 지 배포를 외부 방화벽 뒤에 배치 해야 하지만, 외부와에 지 및 내부 환경 간에 두 개의 방화벽을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-169">You need to put your Edge deployment behind an external firewall, but we recommend having two firewalls, one external, and one internal between the Edge environment and your internal environment.</span></span> <span data-ttu-id="3a584-170">이 시나리오의 모든 설명서에는 두 개의 방화벽이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-170">All our documentation in our Scenarios will have two firewalls.</span></span> <span data-ttu-id="3a584-171">두 개의 방화벽은 네트워크에 지 간에 엄격한 라우팅을 보장 하 고 내부 네트워크에 대 한 방화벽 보호를 두 배로 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-171">We recommend two firewalls because it ensures strict routing from one network edge to the other, and doubles the firewall protection for your internal network.</span></span>
  
### <a name="directors"></a><span data-ttu-id="3a584-172">디렉터</span><span class="sxs-lookup"><span data-stu-id="3a584-172">Directors</span></span>
<span data-ttu-id="3a584-173"><a name="Directors"> </a></span><span class="sxs-lookup"><span data-stu-id="3a584-173"><a name="Directors"> </a></span></span>

<span data-ttu-id="3a584-174">이는 선택적 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-174">This is an optional role.</span></span> <span data-ttu-id="3a584-175">디렉터 역할을 실행 하는 단일 서버 또는 서버 풀 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-175">It can be a single server or a pool of servers running the Director role.</span></span> <span data-ttu-id="3a584-176">이 역할은 내부 비즈니스용 Skype 서버 환경에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-176">It's a role found on the internal Skype for Business Server environment.</span></span>
  
<span data-ttu-id="3a584-177">디렉터는 비즈니스용 Skype 서버 내부 서버에 대해 향하는에 지 서버에서 인바운드 SIP 트래픽을 수신 하는 내부 다음 홉 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-177">The Director is an internal next hop server which receives inbound SIP traffic from the Edge Servers that's destined for Skype for Business Server internal servers.</span></span> <span data-ttu-id="3a584-178">인바운드 요청을 사전에 인증 하 고 사용자의 홈 풀이나 서버로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-178">It preauthenticates inbound requests and redirects them to a user's home pool or server.</span></span> <span data-ttu-id="3a584-179">이 사전 인증을 사용 하면 미확인 사용자 계정 요청을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-179">This preauthentication allows you to drop unidentified user account requests.</span></span>
  
<span data-ttu-id="3a584-180">이와 같은 문제가 있는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="3a584-180">Why does that matter?</span></span> <span data-ttu-id="3a584-181">디렉터에 대 한 중요 한 기능은 DoS (서비스 거부) 공격과 같은 악의적인 트래픽에 대해 Standard Edition 서버 및 프런트 엔드 서버 또는 프런트 엔드 풀을 보호 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-181">An important function for a Director is to protect Standard Edition servers and Front End Servers or Front End pools from malicious traffic, such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="3a584-182">네트워크의 외부 트래픽이 잘못 된 경우에는 디렉터에서 트래픽이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-182">If your network is flooded with invalid external traffic, the traffic stops at the Director.</span></span>
  
### <a name="load-balancers"></a><span data-ttu-id="3a584-183">부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="3a584-183">Load Balancers</span></span>
<span data-ttu-id="3a584-184"><a name="LoadBalancers"> </a></span><span class="sxs-lookup"><span data-stu-id="3a584-184"><a name="LoadBalancers"> </a></span></span>

<span data-ttu-id="3a584-185">비즈니스용 Skype 서버의 확장 된 통합에 지 토폴로지는 새 배포에 대 한 DNS 부하 분산에 최적화 되어 있으며 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-185">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments, and we recommend this.</span></span> <span data-ttu-id="3a584-186">고가용성이 필요한 경우 한 가지 특정 상황에 대해 하드웨어 부하 분산 장치를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-186">If you need high availability, we recommend using a hardware load balancer for one specific situation:</span></span>
  
- <span data-ttu-id="3a584-187">Exchange 2013 **이전** 에 exchange um을 사용 하는 원격 사용자의 exchange um</span><span class="sxs-lookup"><span data-stu-id="3a584-187">Exchange UM for remote users using Exchange UM **prior** to Exchange 2013.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="3a584-188">부하 분산 장치를 혼합할 수 없다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-188">It's vital to note that you can't mix load-balancers.</span></span> <span data-ttu-id="3a584-189">비즈니스용 Skype 서버 환경에서 모든 인터페이스는 DNS 또는 HLB를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-189">In your Skype for Business Server environment all interfaces must use either DNS or HLB.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3a584-190">DSR (Direct server return) NAT는 비즈니스용 Skype 서버에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-190">Direct server return (DSR) NAT isn't supported for Skype for Business Server.</span></span> 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="3a584-191">A/V에 지 서비스를 실행 하는에 지 서버에 지 서버에 대 한 하드웨어 부하 분산 장치 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a584-191">hardware load balancer requirements for Edge Servers Edge Servers running the A/V Edge service</span></span>

<span data-ttu-id="3a584-192">A/V에 지 서비스를 실행 하는 모든에 지 서버에 대 한 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-192">For any Edge Server running the A/V Edge service, these are the requirements:</span></span>
  
- <span data-ttu-id="3a584-193">내부 및 외부 포트 모두에 대해 TCP nagling을 해제 합니다. 443 (nagling는 여러 개의 작은 패킷을 보다 효율적인 단일 패킷으로 결합 하 여 보다 효율적으로 전송 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-193">Turn off TCP nagling for both internal and external ports 443 (nagling is the process of combining several small packets into a single, larger packet for more efficient transmission).</span></span>
    
- <span data-ttu-id="3a584-194">외부 포트 범위 5만-59999에 대해 TCP nagling을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-194">Turn off TCP nagling for the external port range 50000 - 59999.</span></span>
    
- <span data-ttu-id="3a584-195">내부 또는 외부 방화벽에 NAT를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="3a584-195">Don't use NAT on your internal or external firewalls.</span></span>
    
- <span data-ttu-id="3a584-196">에 지 내부 인터페이스는에 지 서버 외부 인터페이스와 다른 네트워크에 있어야 하며, 이러한 간의 라우팅은 사용 하지 않도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-196">Your Edge internal interface must be on a different network than your Edge Server external interface, and routing between them must be disabled.</span></span>
    
- <span data-ttu-id="3a584-197">A/V에 지 서비스를 실행 하는 모든에 지 서버의 외부 인터페이스는 공용으로 라우팅할 수 있는 IP 주소를 사용 해야 하며,에 지 외부 IP 주소에 NAT 또는 포트 변환이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-197">The external interface of any Edge Server running the A/V Edge service must use publicly routable IP addresses and no NAT or port translation on any of the Edge external IP addresses.</span></span>
    
#### <a name="hlb-requirements"></a><span data-ttu-id="3a584-198">HLB 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a584-198">HLB requirements</span></span>

<span data-ttu-id="3a584-199">비즈니스용 Skype 서버에는 쿠키 기반 선호도 요구 사항이 많지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-199">Skype for Business Server doesn't have a lot of cookie-based affinity requirements.</span></span> <span data-ttu-id="3a584-200">따라서 비즈니스용 skype 서버 환경에서 Lync Server 2010 프런트 엔드 서버 또는 프런트 엔드 풀을 사용 해야 하는 **경우가 2015 아니면** 쿠키 기반 지 속성을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-200">So you don't need to use a cookie-based persistence **unless** (and this is Skype for Business Server 2015-specific) you're going to have Lync Server 2010 Front End Servers or Front End pools in your Skype for Business Server environment.</span></span> <span data-ttu-id="3a584-201">Lync Server 2010에 권장 되는 구성 방법에는 쿠키 기반 선호도가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-201">They would need cookie-based affinity in the configuration method recommended for Lync Server 2010.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a584-202">HLB에 대해 쿠키 기반 선호도를 설정 하도록 결정 한 경우 사용자 환경에 필요 하지 않은 경우에도 문제가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-202">If you decide to turn cookie-based affinity on for your HLB, there won't be a problem doing so, even if your environment doesn't need it.</span></span> 
  
<span data-ttu-id="3a584-203">사용자 환경에 쿠키 기반 선호도가 필요 **하지** 않은 경우:</span><span class="sxs-lookup"><span data-stu-id="3a584-203">If your environment **doesn't** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="3a584-204">포트 443에 대 한 역방향 프록시 게시 규칙에서 **정방향 호스트 헤더** 를 **True**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-204">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="3a584-205">이렇게 하면 원래 URL이 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-205">This will ensure the original URL is forwarded.</span></span>
    
<span data-ttu-id="3a584-206">쿠키 기반 선호도 **가 필요한** 배포의 경우:</span><span class="sxs-lookup"><span data-stu-id="3a584-206">For deployments that **do** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="3a584-207">포트 443에 대 한 역방향 프록시 게시 규칙에서 **정방향 호스트 헤더** 를 **True**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-207">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="3a584-208">이렇게 하면 원래 URL이 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-208">This will ensure the original URL is forwarded.</span></span>
    
- <span data-ttu-id="3a584-209">하드웨어 부하 분산 장치 쿠키를 httpOnly로 표시 **해서는 안** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-209">The hardware load balancer cookie **must not** be marked httpOnly.</span></span>
    
- <span data-ttu-id="3a584-210">하드웨어 부하 분산 장치 쿠키에 만료 시간이 있어서는 **안** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-210">The hardware load balancer cookie **must not** have an expiration time.</span></span>
    
- <span data-ttu-id="3a584-211">하드웨어 부하 분산 장치 쿠키 이름은 **MS-WSMAN** (웹 서비스가 예상 하며 변경할 수 없는 값) **이어야 합니다** .</span><span class="sxs-lookup"><span data-stu-id="3a584-211">The hardware load balancer cookie **must** be named **MS-WSMAN** (this is the value that the Web services expect, and it can't be changed).</span></span>
    
- <span data-ttu-id="3a584-212">같은 TCP 연결에 대 한 이전 HTTP 응답에서 쿠키를 얻 었는 지 여부에 관계 없이 들어오는 HTTP 요청에 쿠키가 없는 모든 HTTP 응답에서 하드웨어 부하 분산 장치 쿠키를 설정 **해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-212">The hardware load balancer cookie **must** be set in every HTTP response for which the incoming HTTP request didn't have a cookie, regardless of whether a previous HTTP response on that same TCP connection had gotten a cookie.</span></span> <span data-ttu-id="3a584-213">하드웨어 부하 분산 장치에서 쿠키를 최적화 하는 경우 TCP 연결 당 해당 최적화를 사용 **하지 않는** 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-213">If your hardware load balancer optimizes cookie insert to only occur once per TCP connection, that optimization **must not** be used.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3a584-214">HLB 구성에서는 클라이언트 사용량 및/또는 응용 프로그램 상호 작용을 통해 세션 상태를 유지 관리 하므로 비즈니스용 Skype 서버 및 클라이언트에 적절 한 원본 선호도 및 20 분간 TCP 세션 수명을 사용 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-214">It's typical for HLB configurations to use source-affinity and 20 minute TCP session lifetime, which is fine for Skype for Business Server and its clients, because session state is maintained through client usage, and/or application interaction.</span></span> 
  
<span data-ttu-id="3a584-215">모바일 장치를 배포 하는 경우에는 HLB에서 TCP 세션 내의 개별 요청에 대 한 부하를 분산할 수 있어야 합니다 (실제로, 대상 IP 주소를 기준으로 개별 요청의 부하를 분산 해야 함).</span><span class="sxs-lookup"><span data-stu-id="3a584-215">If you're deploying mobile devices, your HLB must be able to load balance individual requests within a TCP session (in effect, you need to be able to load balance an individual request based on the target IP address).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3a584-216">F5 HLBs에는 OneConnect 라는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-216">F5 HLBs have a feature called OneConnect.</span></span> <span data-ttu-id="3a584-217">이를 통해 TCP 연결 내의 각 요청이 개별적으로 부하 분산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-217">It ensures that each request within a TCP connection is individually load balanced.</span></span> <span data-ttu-id="3a584-218">모바일 장치를 배포 하는 경우 HLB 공급 업체가 같은 기능을 지원 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-218">If you're deploying mobile devices, ensure your HLB vendor supports the same functionality.</span></span> <span data-ttu-id="3a584-219">최신 iOS 모바일 앱에는 TLS 버전 1.2이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-219">The latest iOS mobile apps require TLS version 1.2.</span></span> <span data-ttu-id="3a584-220">더 자세히 알고 있어야 하는 경우에는 F5 키를 눌러이에 대 한 설정을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-220">If you need to know more, F5 provides specific settings for this.</span></span> 
  
<span data-ttu-id="3a584-221">(선택 사항) 디렉터 및 (필수) 프런트 엔드 풀 웹 서비스에 대 한 HLB 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-221">Here are the HLB requirements for the (optional) Director and (required) Front End pool Web Services:</span></span>
  
- <span data-ttu-id="3a584-222">내부 웹 서비스 Vip에 대해 HLB에서 Source_addr 지 속성 (내부 포트 80, 443)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-222">For your internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on your HLB.</span></span> <span data-ttu-id="3a584-223">비즈니스용 Skype Source_addr 서버의 경우에는 단일 IP 주소에서 들어오는 여러 연결이 세션 상태를 유지 하기 위해 항상 하나의 서버로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-223">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server, to maintain session state.</span></span>
    
- <span data-ttu-id="3a584-224">TCP 유휴 시간 제한 (1800 초)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-224">Use a TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="3a584-225">역방향 프록시와 다음 홉 풀의 HLB 사이에 있는 방화벽에서 https: 포트의 트래픽 4443, 역방향 프록시에서 HLB로의 트래픽을 허용 하는 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-225">On the firewall between your reverse proxy and your next hop pool's HLB, create a rule to allow https: traffic on port 4443, from your reverse proxy to your HLB.</span></span> <span data-ttu-id="3a584-226">HLB는 포트 80, 443 및 4443에서 수신 대기 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-226">Your HLB needs to be configured to listen on ports 80, 443, and 4443.</span></span>
    
#### <a name="summary-of-hlb-affinity-requirements"></a><span data-ttu-id="3a584-227">HLB 선호도 요구 사항 요약</span><span class="sxs-lookup"><span data-stu-id="3a584-227">Summary of HLB affinity requirements</span></span>

|<span data-ttu-id="3a584-228">**클라이언트/사용자 위치**</span><span class="sxs-lookup"><span data-stu-id="3a584-228">**Client/user location**</span></span>|<span data-ttu-id="3a584-229">**외부 웹 서비스 FQDN 선호도 요구 사항**</span><span class="sxs-lookup"><span data-stu-id="3a584-229">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="3a584-230">**내부 웹 서비스 FQSN 선호도 요구 사항**</span><span class="sxs-lookup"><span data-stu-id="3a584-230">**Internal web services FQSN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3a584-231">비즈니스용 Skype 웹 앱 (내부 및 외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="3a584-231">Skype for Business Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="3a584-232">모바일 장치 (내부 및 외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="3a584-232">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="3a584-233">선호도 없음</span><span class="sxs-lookup"><span data-stu-id="3a584-233">No affinity</span></span>  <br/> |<span data-ttu-id="3a584-234">원본 주소 선호도</span><span class="sxs-lookup"><span data-stu-id="3a584-234">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="3a584-235">비즈니스용 Skype 웹 앱 (외부 사용자만 해당)</span><span class="sxs-lookup"><span data-stu-id="3a584-235">Skype for Business Web App (external users only)</span></span>  <br/> <span data-ttu-id="3a584-236">모바일 장치 (내부 및 외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="3a584-236">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="3a584-237">선호도 없음</span><span class="sxs-lookup"><span data-stu-id="3a584-237">No affinity</span></span>  <br/> |<span data-ttu-id="3a584-238">원본 주소 선호도</span><span class="sxs-lookup"><span data-stu-id="3a584-238">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="3a584-239">비즈니스용 Skype 웹 앱 (내부 사용자만 해당)</span><span class="sxs-lookup"><span data-stu-id="3a584-239">Skype for Business Web App (internal users only)</span></span>  <br/> <span data-ttu-id="3a584-240">모바일 장치(배포되지 않음)</span><span class="sxs-lookup"><span data-stu-id="3a584-240">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="3a584-241">선호도 없음</span><span class="sxs-lookup"><span data-stu-id="3a584-241">No affinity</span></span>  <br/> |<span data-ttu-id="3a584-242">원본 주소 선호도</span><span class="sxs-lookup"><span data-stu-id="3a584-242">Source address affinity</span></span>  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a><span data-ttu-id="3a584-243">HLBs에 대 한 포트 모니터링</span><span class="sxs-lookup"><span data-stu-id="3a584-243">Port monitoring for HLBs</span></span>

<span data-ttu-id="3a584-244">하드웨어 부하 분산 장치에서 포트 모니터링을 정의 하 여 하드웨어 또는 통신 오류로 인해 특정 서비스를 더 이상 사용할 수 없는 시기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-244">You define port monitoring on your hardware load balancers to determine when specific services are no longer available, due to hardware or communications failure.</span></span> <span data-ttu-id="3a584-245">예를 들어 프런트 엔드 서버 또는 프런트 엔드 풀에 오류가 발생 하 여 프런트 엔드 서버 서비스 (RTCSRV)가 중지 되는 경우 HLB 모니터링에서는 웹 서비스의 트래픽 수신도 중지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-245">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="3a584-246">HLB 외부 인터페이스에 대해 다음을 모니터링 하려면 HLB에 대해 포트 모니터링을 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-246">You should implement port monitoring on the HLB to monitor the following for your HLB external interface:</span></span>
  
|<span data-ttu-id="3a584-247">**가상 IP/포트**</span><span class="sxs-lookup"><span data-stu-id="3a584-247">**Virtual IP/Port**</span></span>|<span data-ttu-id="3a584-248">**노드 포트**</span><span class="sxs-lookup"><span data-stu-id="3a584-248">**Node Port**</span></span>|<span data-ttu-id="3a584-249">**노드 컴퓨터/모니터**</span><span class="sxs-lookup"><span data-stu-id="3a584-249">**Node Machine/Monitor**</span></span>|<span data-ttu-id="3a584-250">**지속성 프로필**</span><span class="sxs-lookup"><span data-stu-id="3a584-250">**Persistence Profile**</span></span>|<span data-ttu-id="3a584-251">**참고**</span><span class="sxs-lookup"><span data-stu-id="3a584-251">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3a584-252">\<풀 \> web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="3a584-252">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="3a584-253">443</span><span class="sxs-lookup"><span data-stu-id="3a584-253">443</span></span>  <br/> |<span data-ttu-id="3a584-254">4443</span><span class="sxs-lookup"><span data-stu-id="3a584-254">4443</span></span>  <br/> |<span data-ttu-id="3a584-255">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="3a584-255">Front End</span></span>  <br/> <span data-ttu-id="3a584-256">5061</span><span class="sxs-lookup"><span data-stu-id="3a584-256">5061</span></span>  <br/> |<span data-ttu-id="3a584-257">없음</span><span class="sxs-lookup"><span data-stu-id="3a584-257">None</span></span>  <br/> |<span data-ttu-id="3a584-258">H</span><span class="sxs-lookup"><span data-stu-id="3a584-258">HTTPS</span></span>  <br/> |
|<span data-ttu-id="3a584-259">\<풀 \> web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="3a584-259">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="3a584-260">80</span><span class="sxs-lookup"><span data-stu-id="3a584-260">80</span></span>  <br/> |<span data-ttu-id="3a584-261">8080</span><span class="sxs-lookup"><span data-stu-id="3a584-261">8080</span></span>  <br/> |<span data-ttu-id="3a584-262">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="3a584-262">Front End</span></span>  <br/> <span data-ttu-id="3a584-263">5061</span><span class="sxs-lookup"><span data-stu-id="3a584-263">5061</span></span>  <br/> |<span data-ttu-id="3a584-264">없음</span><span class="sxs-lookup"><span data-stu-id="3a584-264">None</span></span>  <br/> |<span data-ttu-id="3a584-265">HTTP</span><span class="sxs-lookup"><span data-stu-id="3a584-265">HTTP</span></span>  <br/> |
   
## <a name="hardware-and-software-requirements"></a><span data-ttu-id="3a584-266">하드웨어 및 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a584-266">Hardware and software requirements</span></span>

<span data-ttu-id="3a584-267">Microsoft는 비즈니스용 skype 서버 2019 설명서에 대 한 전체 [2015 서버](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 하드웨어 요구 사항 및 [시스템 요구](../../../SfBServer2019/plan/system-requirements.md) 사항</span><span class="sxs-lookup"><span data-stu-id="3a584-267">We've covered Edge Server hardware and software requirements in our overall [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and  [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) documentation.</span></span>
  
## <a name="collocation"></a><span data-ttu-id="3a584-268">배치</span><span class="sxs-lookup"><span data-stu-id="3a584-268">Collocation</span></span>

<span data-ttu-id="3a584-269">Microsoft [는 비즈니스용 Skype 서버 설명서의 토폴로지 기본 사항](../../plan-your-deployment/topology-basics/topology-basics.md) 에에 지 서버 위치를 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a584-269">We've covered Edge Server collocation in our [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.</span></span>
  

