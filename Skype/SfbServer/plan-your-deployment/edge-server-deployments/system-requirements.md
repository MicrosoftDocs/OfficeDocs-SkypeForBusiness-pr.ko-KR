---
title: 비즈니스용 Skype 서버의 에지 서버 시스템 요구 사항
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '요약: 비즈니스용 Skype 서버의 에지 서버에 대한 시스템 요구 사항에 대해 자세히 알아보십시오.'
ms.openlocfilehash: e066249498febbd5e622546533f49422320c7c87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813768"
---
# <a name="edge-server-system-requirements-in-skype-for-business-server"></a><span data-ttu-id="2e92b-103">비즈니스용 Skype 서버의 에지 서버 시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e92b-103">Edge Server system requirements in Skype for Business Server</span></span>
 
<span data-ttu-id="2e92b-104">**요약:** 비즈니스용 Skype 서버의 에지 서버에 대한 시스템 요구 사항에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="2e92b-104">**Summary:** Learn about the system requirements for Edge Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="2e92b-105">비즈니스용 Skype 서버 에지 서버 배포의 경우 환경 자체에 있는 서버 및 환경 구조를 계획하는 데 필요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-105">When it comes to your Skype for Business Server Edge Server deployment, these are the things you'll need to do for the server or servers that are in the environment itself, as well as planning for the environment structure.</span></span> <span data-ttu-id="2e92b-106">토폴로지, DNS, 인증서 및 기타 인프라 관련 사항에 대한 자세한 내용은 환경 요구 사항 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2e92b-106">For more information on topology, DNS, certificates, and other infrastructure concerns, check out the environmental requirements documentation.</span></span>
  
## <a name="components"></a><span data-ttu-id="2e92b-107">구성 요소</span><span class="sxs-lookup"><span data-stu-id="2e92b-107">Components</span></span>

<span data-ttu-id="2e92b-108">에지 서버 환경에 대해 설명할 때 경계 네트워크에 배포되는 구성 요소는 대부분 경계 네트워크에 배포되는 구성 요소를 참조합니다(즉, 비즈니스용 Skype 서버 도메인 구조 외부에 있는 도메인 또는 작업 영역의 경우).</span><span class="sxs-lookup"><span data-stu-id="2e92b-108">When discussing the Edge Server environment, we're referencing components that are, for the most part, deployed in a perimeter network (that's to say it's either in a workgroup or a domain that's outside your Skype for Business Server domain structure).</span></span>
  
<span data-ttu-id="2e92b-109">이러한 구성 요소는 Edge를 성공적으로 배포하기 위해 유의해야 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-109">Keeping that in mind, these are the components you're going to need to keep in mind for deploying your Edge successfully:</span></span>
  
- [<span data-ttu-id="2e92b-110">에지 서버</span><span class="sxs-lookup"><span data-stu-id="2e92b-110">Edge Servers</span></span>](system-requirements.md#EdgeServers)
    
- [<span data-ttu-id="2e92b-111">역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="2e92b-111">Reverse proxies</span></span>](system-requirements.md#ReverseProxies)
    
- [<span data-ttu-id="2e92b-112">방화벽</span><span class="sxs-lookup"><span data-stu-id="2e92b-112">Firewalls</span></span>](system-requirements.md#Firewalls)
    
- <span data-ttu-id="2e92b-113">[Director(선택](system-requirements.md#Directors) 사항이며 포함된 경우 내부 네트워크에 위치)</span><span class="sxs-lookup"><span data-stu-id="2e92b-113">[Directors](system-requirements.md#Directors) (these are optional, and if they're included, they'll be located on your internal network)</span></span>
    
- <span data-ttu-id="2e92b-114">[부하 분산(DNS](system-requirements.md#LoadBalancers) 부하 분산 또는 HLB(하드웨어 부하 분산)을 사용할 수 있지만 단일 에지 서버에는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-114">[Load Balancers](system-requirements.md#LoadBalancers) (you can have DNS load balancing or a hardware load balancer (HLB), but for a single Edge Server, this isn't needed)</span></span>
    
<span data-ttu-id="2e92b-115">아래 각 내용에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-115">We have more detail on each of these below:</span></span>
  
### <a name="edge-servers"></a><span data-ttu-id="2e92b-116">에지 서버</span><span class="sxs-lookup"><span data-stu-id="2e92b-116">Edge Servers</span></span>
<span data-ttu-id="2e92b-117"><a name="EdgeServers"> </a></span><span class="sxs-lookup"><span data-stu-id="2e92b-117"><a name="EdgeServers"> </a></span></span>

<span data-ttu-id="2e92b-118">경계 환경에 배포된 비즈니스용 Skype 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-118">These are the Skype for Business servers deployed in your perimeter environment.</span></span> <span data-ttu-id="2e92b-119">해당 역할은 내부 비즈니스용 Skype 서버 배포에서 제공하는 서비스를 위해 외부 사용자에게 네트워크 트래픽을 보내고 받는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-119">Their role is to send and receive network traffic to external users for the services offered by your internal Skype for Business Server deployment.</span></span> <span data-ttu-id="2e92b-120">이 작업을 성공적으로 실행하기 위해 각 에지 서버는 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-120">To do this successfully, each Edge Server runs:</span></span>
  
- <span data-ttu-id="2e92b-121">**액세스 에지 서비스:** 아웃바운드 및 인바운드 SIP(Session Initiation Protocol) 트래픽 모두에 대해 신뢰할 수 있는 단일 연결 지점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-121">**Access Edge service**: Provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>
    
- <span data-ttu-id="2e92b-122">**웹 회의 에지 서비스:** 외부 사용자가 내부 비즈니스용 Skype 서버 환경에서 호스팅되는 모임에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-122">**Web Conferencing Edge service**: Enables external users to join meetings that are hosted on your internal Skype for Business Server environment.</span></span>
    
- <span data-ttu-id="2e92b-123">**A/V 에지 서비스:** 외부 사용자가 오디오, 비디오, 응용 프로그램 공유 및 파일 전송을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-123">**A/V Edge service**: Makes audio, video, application sharing and file transfer available to external users.</span></span>
    
- <span data-ttu-id="2e92b-124">**XMPP 프록시 서비스: 구성된 XMPP** 페더리트 파트너와 XMPP(Extensible Messaging and Presence Protocol) 메시지를 수락하고 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-124">**XMPP Proxy service**: Accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>
    
<span data-ttu-id="2e92b-125">권한이 부여된 외부 사용자는 에지 서버를 사용하여 내부 비즈니스용 Skype 서버 배포에 연결할 수 있지만, 그렇지 않으면 누구도 내부 네트워크에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-125">Authorized external users can use your Edge Servers to connect to your internal Skype for Business Server deployment, but otherwise, they provide no other access to your internal network for anyone.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2e92b-126">에지 서버는 사용하도록 설정된 비즈니스용 Skype 클라이언트 및 기타 에지 서버에 대한 연결을 제공하기 위해 배포됩니다(페더화 시나리오).</span><span class="sxs-lookup"><span data-stu-id="2e92b-126">Edge Servers are deployed to provide connections for enabled Skype for Business clients and other Edge Servers (in federation scenarios).</span></span> <span data-ttu-id="2e92b-127">다른 끝점 클라이언트 또는 서버 유형에서는 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-127">You can't connect from other end point client or server types.</span></span> <span data-ttu-id="2e92b-128">XMPP 게이트웨이 서버는 구성된 XMPP 파트너와의 연결을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-128">The XMPP Gateway server can allow connections with configured XMPP partners.</span></span> <span data-ttu-id="2e92b-129">그러나 이 두 가지 유형이 작동할 수 있는 유일한 클라이언트 및 연결 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-129">But again, those are the only client and federation types that will work.</span></span> 

> [!NOTE]
> <span data-ttu-id="2e92b-130">XMPP 게이트웨이 및 XMPP 게이트웨이는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-130">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2e92b-131">자세한 [내용은 XMPP 페더링 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e92b-131">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="reverse-proxies"></a><span data-ttu-id="2e92b-132">역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="2e92b-132">Reverse proxies</span></span>
<span data-ttu-id="2e92b-133"><a name="ReverseProxies"> </a></span><span class="sxs-lookup"><span data-stu-id="2e92b-133"><a name="ReverseProxies"> </a></span></span>

<span data-ttu-id="2e92b-134">RP(역방향 프록시) 서버에는 비즈니스용 Skype 서버 역할이 없지만 에지 서버 배포의 필수 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-134">A reverse proxy (RP) server has no Skype for Business Server role, but is an essential component of an Edge Server deployment.</span></span> <span data-ttu-id="2e92b-135">역방향 프록시를 사용하면 외부 사용자가</span><span class="sxs-lookup"><span data-stu-id="2e92b-135">A reverse proxy allows external users to:</span></span>
  
- <span data-ttu-id="2e92b-136">단순 URL을 사용하여 모임 또는 전화 접속 회의에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-136">connect to meetings or dial-in conferences using simple URLs.</span></span>
    
- <span data-ttu-id="2e92b-137">모임 콘텐츠를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-137">download meeting content.</span></span>
    
- <span data-ttu-id="2e92b-138">메일 그룹을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-138">expand distribution groups.</span></span>
    
- <span data-ttu-id="2e92b-139">클라이언트 인증서 기반 인증에 대한 사용자 기반 인증서를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-139">get user-based certificates for client certificate based authentication</span></span>
    
- <span data-ttu-id="2e92b-140">주소부 서버에서 파일을 다운로드하거나 주소 책 웹 쿼리 서비스로 쿼리를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-140">download files from the Address Book Server, or to submit queries to the Address Book Web Query service.</span></span>
    
- <span data-ttu-id="2e92b-141">클라이언트 및 장치 소프트웨어에 대한 업데이트를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-141">obtain updates to client and device software.</span></span>
    
<span data-ttu-id="2e92b-142">모바일 장치의 경우:</span><span class="sxs-lookup"><span data-stu-id="2e92b-142">And for mobile devices:</span></span>
  
- <span data-ttu-id="2e92b-143">모바일 서비스를 제공하는 프런트 엔드 서버를 자동으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-143">it lets them automatically discover Front End Servers offering mobility services.</span></span>
    
- <span data-ttu-id="2e92b-144">Microsoft 365 또는 Office 365에서 모바일 장치로 푸시 알림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-144">it enables push notifications from Microsoft 365 or Office 365 to mobile devices.</span></span>
    
<span data-ttu-id="2e92b-145">현재 역방향 프록시 권장 사항은 비즈니스용 [Skype의](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) 전화 통신 인프라 페이지에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-145">Our current reverse proxy recommendations can be found on the [Telephony Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) page.</span></span> <span data-ttu-id="2e92b-146">따라서 역방향 프록시:</span><span class="sxs-lookup"><span data-stu-id="2e92b-146">So your reverse proxy:</span></span>
  
- <span data-ttu-id="2e92b-147">공용 인증서를 통해 환경에 도입된 TLS(전송 계층 보안)를 사용하여 다음의 게시된 외부 웹 서비스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-147">should be able to use transport layer security (TLS) that's introduced to your environment via public certificates to connect to the published external Web services of:</span></span>
    
  - <span data-ttu-id="2e92b-148">디렉터 또는 디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="2e92b-148">Director or Director pool</span></span>
    
  - <span data-ttu-id="2e92b-149">프런트 엔드 서버 또는 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="2e92b-149">Front End Server or Front End pool</span></span>
    
- <span data-ttu-id="2e92b-150">암호화를 위해 인증서를 사용하여 내부 웹 사이트를 게시하거나 필요한 경우 암호화되지 않은 수단을 통해 게시할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-150">needs to be able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>
    
- <span data-ttu-id="2e92b-151">FQDN(FQDN)을 사용하여 내부적으로 호스팅되는 웹 사이트를 외부에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-151">should be able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>
    
- <span data-ttu-id="2e92b-152">호스팅된 웹 사이트의 모든 콘텐츠를 게시할 수 있도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-152">needs to be able to publish all the contents of your hosted web site.</span></span> <span data-ttu-id="2e92b-153">기본적으로 대부분의 웹 서버에서 "웹 서버에 모든 콘텐츠 게시"를 의미하는 _지시문을 사용할 **/\\** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-153">By default, you can use the **/\\** _ directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="2e92b-154">"Ucwa 가상 디렉터리 아래에 모든 콘텐츠 게시"를 의미하는 _*/Uwca와 \\* \*_ 같은 지시문을 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-154">You can also modify the directive—for example, _*/Uwca/\\*\*_, which means "Publish all content under the virtual directory Ucwa."</span></span>
    
- <span data-ttu-id="2e92b-155">게시된 웹 사이트에서 콘텐츠를 요청하는 클라이언트와의 TLS 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-155">must require TLS connections with clients that request content from your published website.</span></span>
    
- <span data-ttu-id="2e92b-156">은 SAN(주체 대체 이름) 항목이 있는 인증서를 수락해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-156">has to accept certificates with subject alternative name (SAN) entries.</span></span>
    
- <span data-ttu-id="2e92b-157">외부 웹 서비스 FQDN이 확인되는 수신기 또는 인터페이스에 인증서를 바인딩할 수 있도록 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-157">needs to be able to allow the binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="2e92b-158">수신기 구성은 인터페이스보다 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-158">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="2e92b-159">많은 수신기들을 단일 인터페이스에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-159">Many listeners can be configured on a single interface.</span></span>
    
- <span data-ttu-id="2e92b-160">호스트 헤더 처리 구성을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-160">must allow for the configuration of host header handling.</span></span> <span data-ttu-id="2e92b-161">요청 클라이언트가 전송한 원래 호스트 헤더는 역방향 프록시에서 수정하는 대신 투명하게 전달해야 하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-161">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>
    
- <span data-ttu-id="2e92b-162">외부에서 정의된 포트(예: TCP 443)에서 정의된 다른 포트(예: TCP 4443)로의 TLS 트래픽 브리그링을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-162">should allow bridging of TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="2e92b-163">역방향 프록시는 수신 시 패킷의 암호를 해독한 다음 전송 시 패킷을 다시 암호화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-163">Your reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>
    
- <span data-ttu-id="2e92b-164">암호화되지 않은 TCP 트래픽(예: TCP 80)을 다른 포트(예: TCP 8080)로 브리그링할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-164">should allow bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>
    
- <span data-ttu-id="2e92b-165">NTLM 인증, 인증 및 통과 인증을 허용하거나 수락해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-165">needs to allow configuration of, or accept, NTLM authentication, no authentication, and pass-through authentication.</span></span>
    
<span data-ttu-id="2e92b-166">역방향 프록시가 이 목록의 모든 요구 사항을 해결할 수 있는 경우 이동하는 것이 좋지만 위에 제공된 링크에서 권장 사항을 염두에 두어 주세요.</span><span class="sxs-lookup"><span data-stu-id="2e92b-166">If your reverse proxy can address all the needs in this list, you should be good to go, but please keep in mind our recommendations at the link provided above.</span></span>
  
### <a name="firewalls"></a><span data-ttu-id="2e92b-167">방화벽</span><span class="sxs-lookup"><span data-stu-id="2e92b-167">Firewalls</span></span>
<span data-ttu-id="2e92b-168"><a name="Firewalls"> </a></span><span class="sxs-lookup"><span data-stu-id="2e92b-168"><a name="Firewalls"> </a></span></span>

<span data-ttu-id="2e92b-169">에지 배포를 외부 방화벽 뒤에 배치해야 하지만 에지 환경과 내부 환경 간에 방화벽 2개,외부 방화벽 1개와 내부 방화벽 1개가 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-169">You need to put your Edge deployment behind an external firewall, but we recommend having two firewalls, one external, and one internal between the Edge environment and your internal environment.</span></span> <span data-ttu-id="2e92b-170">시나리오의 모든 설명서에는 두 개의 방화벽이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-170">All our documentation in our Scenarios will have two firewalls.</span></span> <span data-ttu-id="2e92b-171">한 네트워크 에지에서 다른 네트워크 에지로 엄격한 라우팅을 보장하고 내부 네트워크에 대한 방화벽 보호를 두 배로 강화하기 때문에 두 개의 방화벽을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-171">We recommend two firewalls because it ensures strict routing from one network edge to the other, and doubles the firewall protection for your internal network.</span></span>
  
### <a name="directors"></a><span data-ttu-id="2e92b-172">Director</span><span class="sxs-lookup"><span data-stu-id="2e92b-172">Directors</span></span>
<span data-ttu-id="2e92b-173"><a name="Directors"> </a></span><span class="sxs-lookup"><span data-stu-id="2e92b-173"><a name="Directors"> </a></span></span>

<span data-ttu-id="2e92b-174">선택적 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-174">This is an optional role.</span></span> <span data-ttu-id="2e92b-175">단일 서버 또는 Director 역할을 실행하는 서버 풀일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-175">It can be a single server or a pool of servers running the Director role.</span></span> <span data-ttu-id="2e92b-176">내부 비즈니스용 Skype 서버 환경에 있는 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-176">It's a role found on the internal Skype for Business Server environment.</span></span>
  
<span data-ttu-id="2e92b-177">디렉터는 비즈니스용 Skype 서버 내부 서버로 전송되는 에지 서버에서 인바운드 SIP 트래픽을 받는 내부 다음 홉 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-177">The Director is an internal next hop server which receives inbound SIP traffic from the Edge Servers that's destined for Skype for Business Server internal servers.</span></span> <span data-ttu-id="2e92b-178">인바운드 요청을 미리 인증하고 사용자의 홈 풀 또는 서버로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-178">It preauthenticates inbound requests and redirects them to a user's home pool or server.</span></span> <span data-ttu-id="2e92b-179">이 사전 사용은 ID가 없는 사용자 계정 요청을 삭제하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-179">This preauthentication allows you to drop unidentified user account requests.</span></span>
  
<span data-ttu-id="2e92b-180">그 이유는 무엇일까요?</span><span class="sxs-lookup"><span data-stu-id="2e92b-180">Why does that matter?</span></span> <span data-ttu-id="2e92b-181">Director의 중요한 기능은 DoS(서비스 거부) 공격과 같은 악의적인 트래픽으로부터 Standard Edition 서버 및 프런트 엔드 서버 또는 프런트 엔드 풀을 보호하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-181">An important function for a Director is to protect Standard Edition servers and Front End Servers or Front End pools from malicious traffic, such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="2e92b-182">네트워크에 잘못된 외부 트래픽이 넘쳐나면 해당 트래픽이 감독에서 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-182">If your network is flooded with invalid external traffic, the traffic stops at the Director.</span></span>
  
### <a name="load-balancers"></a><span data-ttu-id="2e92b-183">부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="2e92b-183">Load Balancers</span></span>
<span data-ttu-id="2e92b-184"><a name="LoadBalancers"> </a></span><span class="sxs-lookup"><span data-stu-id="2e92b-184"><a name="LoadBalancers"> </a></span></span>

<span data-ttu-id="2e92b-185">비즈니스용 Skype 서버 확장 통합 에지 토폴로지는 새 배포를 위한 DNS 부하 분산에 최적화되어 있으며 이 토폴로지가 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-185">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments, and we recommend this.</span></span> <span data-ttu-id="2e92b-186">고가용성이 필요한 경우 한 가지 특정 상황에 대해 하드웨어 부하 균형 조정을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-186">If you need high availability, we recommend using a hardware load balancer for one specific situation:</span></span>
  
- <span data-ttu-id="2e92b-187">Exchange 2013 이전의Exchange UM _을 사용하는 원격 사용자용 Exchange UM</span><span class="sxs-lookup"><span data-stu-id="2e92b-187">Exchange UM for remote users using Exchange UM _ *prior*\* to Exchange 2013.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="2e92b-188">부하-균형 조정기를 혼합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-188">It's vital to note that you can't mix load-balancers.</span></span> <span data-ttu-id="2e92b-189">비즈니스용 Skype 서버 환경에서 모든 인터페이스는 DNS 또는 HLB를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-189">In your Skype for Business Server environment all interfaces must use either DNS or HLB.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2e92b-190">비즈니스용 Skype 서버에서는 DSR(직접 서버 반환) NAT가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-190">Direct server return (DSR) NAT isn't supported for Skype for Business Server.</span></span> 
  
#### <a name="hardware-load-balancer-requirements-for-edge-servers-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="2e92b-191">A/V 에지 서비스를 실행하는 에지 서버 에지 서버에 대한 하드웨어 부하 관리 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e92b-191">hardware load balancer requirements for Edge Servers Edge Servers running the A/V Edge service</span></span>

<span data-ttu-id="2e92b-192">A/V 에지 서비스를 실행하는 모든 에지 서버의 경우 다음 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-192">For any Edge Server running the A/V Edge service, these are the requirements:</span></span>
  
- <span data-ttu-id="2e92b-193">내부 및 외부 포트 443 둘 다에 대해 TCP nagling을 끄세요(nagling은 보다 효율적인 전송을 위해 여러 개의 작은 패킷을 더 큰 단일 패킷으로 결합하는 프로세스입니다).</span><span class="sxs-lookup"><span data-stu-id="2e92b-193">Turn off TCP nagling for both internal and external ports 443 (nagling is the process of combining several small packets into a single, larger packet for more efficient transmission).</span></span>
    
- <span data-ttu-id="2e92b-194">외부 포트 범위 50000 - 59999에 대해 TCP Nagling을 끄기</span><span class="sxs-lookup"><span data-stu-id="2e92b-194">Turn off TCP nagling for the external port range 50000 - 59999.</span></span>
    
- <span data-ttu-id="2e92b-195">내부 또는 외부 방화벽에서 NAT를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-195">Don't use NAT on your internal or external firewalls.</span></span>
    
- <span data-ttu-id="2e92b-196">에지 내부 인터페이스는 에지 서버 외부 인터페이스와 다른 네트워크에 있어야 하며, 에지 서버 간의 라우팅을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-196">Your Edge internal interface must be on a different network than your Edge Server external interface, and routing between them must be disabled.</span></span>
    
- <span data-ttu-id="2e92b-197">A/V 에지 서비스를 실행하는 에지 서버의 외부 인터페이스는 공개적으로 라우팅 가능한 IP 주소를 사용하며 에지 외부 IP 주소에 NAT 또는 포트 변환이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-197">The external interface of any Edge Server running the A/V Edge service must use publicly routable IP addresses and no NAT or port translation on any of the Edge external IP addresses.</span></span>
    
#### <a name="hlb-requirements"></a><span data-ttu-id="2e92b-198">HLB 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e92b-198">HLB requirements</span></span>

<span data-ttu-id="2e92b-199">비즈니스용 Skype 서버에는 쿠키 기반의 많은 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-199">Skype for Business Server doesn't have a lot of cookie-based affinity requirements.</span></span> <span data-ttu-id="2e92b-200">따라서 비즈니스용 Skype 서버 환경에 Lync  Server 2010 프런트 엔드 서버 또는 프런트 엔드 풀이 있는 경우(및 비즈니스용 Skype 서버 2015와 관련되지 않은 경우) 쿠키 기반 지속성은 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-200">So you don't need to use a cookie-based persistence **unless** (and this is Skype for Business Server 2015-specific) you're going to have Lync Server 2010 Front End Servers or Front End pools in your Skype for Business Server environment.</span></span> <span data-ttu-id="2e92b-201">Lync Server 2010에 권장되는 구성 방법에는 쿠키 기반의 효율성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-201">They would need cookie-based affinity in the configuration method recommended for Lync Server 2010.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2e92b-202">HLB에 대해 쿠키 기반 애정을 설정하기로 결정한 경우 환경에 필요하지 않은 경우에도 이 작업을 수행해도 문제가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-202">If you decide to turn cookie-based affinity on for your HLB, there won't be a problem doing so, even if your environment doesn't need it.</span></span> 
  
<span data-ttu-id="2e92b-203">사용자 환경에 **쿠키** 기반의 효율성이 필요하지 않은 경우:</span><span class="sxs-lookup"><span data-stu-id="2e92b-203">If your environment **doesn't** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="2e92b-204">포트 443에 대한 역방향 프록시  게시 규칙에서 호스트 헤더를 **True로 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="2e92b-204">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="2e92b-205">이렇게 하면 원래 URL이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-205">This will ensure the original URL is forwarded.</span></span>
    
<span data-ttu-id="2e92b-206">쿠키 **기반의 효율성이** 필요한 배포의 경우:</span><span class="sxs-lookup"><span data-stu-id="2e92b-206">For deployments that **do** need cookie-based affinity:</span></span>
  
- <span data-ttu-id="2e92b-207">포트 443에 대한 역방향 프록시  게시 규칙에서 호스트 헤더를 **True로 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="2e92b-207">On the reverse proxy publishing rule for port 443, set **Forward host header** to **True**.</span></span> <span data-ttu-id="2e92b-208">이렇게 하면 원래 URL이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-208">This will ensure the original URL is forwarded.</span></span>
    
- <span data-ttu-id="2e92b-209">하드웨어 부하 균형 조정기 **쿠키를** httpOnly로 표시하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-209">The hardware load balancer cookie **must not** be marked httpOnly.</span></span>
    
- <span data-ttu-id="2e92b-210">하드웨어 부하 균형 조정기 **쿠키에는 만료** 시간이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-210">The hardware load balancer cookie **must not** have an expiration time.</span></span>
    
- <span data-ttu-id="2e92b-211">하드웨어 부하 균형  조정기 쿠키의 이름은 **MS-WSMAN(웹** 서비스에서 기대하는 값으로 변경할 수 없습니다)입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-211">The hardware load balancer cookie **must** be named **MS-WSMAN** (this is the value that the Web services expect, and it can't be changed).</span></span>
    
- <span data-ttu-id="2e92b-212">동일한 TCP  연결의 이전 HTTP 응답에서 쿠키를 수신한지 여부에 관계없이 들어오는 HTTP 요청에 쿠키가 없는 모든 HTTP 응답에서 하드웨어 부하 균형 조정기 쿠키를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-212">The hardware load balancer cookie **must** be set in every HTTP response for which the incoming HTTP request didn't have a cookie, regardless of whether a previous HTTP response on that same TCP connection had gotten a cookie.</span></span> <span data-ttu-id="2e92b-213">하드웨어 부하 균형 조정 도구가 TCP 연결당 한 번만 발생하도록 쿠키 삽입을 최적화하는 경우 해당 최적화를 **사용하지** 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-213">If your hardware load balancer optimizes cookie insert to only occur once per TCP connection, that optimization **must not** be used.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2e92b-214">세션 상태는 클라이언트 사용 및/또는 응용 프로그램 상호 작용을 통해 유지 관리하기 때문에 비즈니스용 Skype 서버 및 클라이언트에 대해 좋은 원본-애매한성 및 20분 TCP 세션 수명을 사용하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-214">It's typical for HLB configurations to use source-affinity and 20 minute TCP session lifetime, which is fine for Skype for Business Server and its clients, because session state is maintained through client usage, and/or application interaction.</span></span> 
  
<span data-ttu-id="2e92b-215">모바일 장치를 배포하는 경우 HLB는 TCP 세션 내에서 개별 요청의 부하를 균형 있게 조정할 수 있어야 합니다(실제로는 대상 IP 주소를 기반으로 개별 요청의 부하를 균형 있게 조정해야 합니다).</span><span class="sxs-lookup"><span data-stu-id="2e92b-215">If you're deploying mobile devices, your HLB must be able to load balance individual requests within a TCP session (in effect, you need to be able to load balance an individual request based on the target IP address).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2e92b-216">F5 HB에는 OneConnect라는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-216">F5 HLBs have a feature called OneConnect.</span></span> <span data-ttu-id="2e92b-217">TCP 연결 내의 각 요청이 개별적으로 부하를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-217">It ensures that each request within a TCP connection is individually load balanced.</span></span> <span data-ttu-id="2e92b-218">모바일 장치를 배포하는 경우 HLB 공급업체에서 동일한 기능을 지원하는지 확인</span><span class="sxs-lookup"><span data-stu-id="2e92b-218">If you're deploying mobile devices, ensure your HLB vendor supports the same functionality.</span></span> <span data-ttu-id="2e92b-219">최신 iOS 모바일 앱에는 TLS 버전 1.2가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-219">The latest iOS mobile apps require TLS version 1.2.</span></span> <span data-ttu-id="2e92b-220">자세한 정보를 알아야 하는 경우 F5는 이에 대한 특정 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-220">If you need to know more, F5 provides specific settings for this.</span></span> 
  
<span data-ttu-id="2e92b-221">다음은 (선택 사항) Director 및 (필수) 프런트 엔드 풀 웹 서비스에 대한 HLB 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-221">Here are the HLB requirements for the (optional) Director and (required) Front End pool Web Services:</span></span>
  
- <span data-ttu-id="2e92b-222">내부 웹 서비스 VI의 경우 HLB에 Source_addr(내부 포트 80, 443)를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="2e92b-222">For your internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on your HLB.</span></span> <span data-ttu-id="2e92b-223">비즈니스용 Skype 서버의 경우 Source_addr 지속성은 세션 상태를 유지하기 위해 단일 IP 주소에서 오는 여러 연결이 항상 하나의 서버로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-223">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server, to maintain session state.</span></span>
    
- <span data-ttu-id="2e92b-224">TCP 유휴 시간 제한을 1800초로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="2e92b-224">Use a TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="2e92b-225">역방향 프록시와 다음 홉 풀의 HLB 간의 방화벽에서 역방향 프록시에서 HLB로의 https: 포트 4443의 트래픽을 허용하는 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-225">On the firewall between your reverse proxy and your next hop pool's HLB, create a rule to allow https: traffic on port 4443, from your reverse proxy to your HLB.</span></span> <span data-ttu-id="2e92b-226">HLB는 포트 80, 443 및 4443에서 수신하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-226">Your HLB needs to be configured to listen on ports 80, 443, and 4443.</span></span>
    
#### <a name="summary-of-hlb-affinity-requirements"></a><span data-ttu-id="2e92b-227">HLB의 효율성 요구 사항 요약</span><span class="sxs-lookup"><span data-stu-id="2e92b-227">Summary of HLB affinity requirements</span></span>

|<span data-ttu-id="2e92b-228">**클라이언트/사용자 위치**</span><span class="sxs-lookup"><span data-stu-id="2e92b-228">**Client/user location**</span></span>|<span data-ttu-id="2e92b-229">**외부 웹 서비스 FQDN 선호도 요구 사항**</span><span class="sxs-lookup"><span data-stu-id="2e92b-229">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="2e92b-230">**내부 웹 서비스 FQSN 연결 요구 사항**</span><span class="sxs-lookup"><span data-stu-id="2e92b-230">**Internal web services FQSN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e92b-231">비즈니스용 Skype Web App(내부 및 외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="2e92b-231">Skype for Business Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="2e92b-232">모바일 장치(내부 및 외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="2e92b-232">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="2e92b-233">선호도 없음</span><span class="sxs-lookup"><span data-stu-id="2e92b-233">No affinity</span></span>  <br/> |<span data-ttu-id="2e92b-234">원본 주소 선호도</span><span class="sxs-lookup"><span data-stu-id="2e92b-234">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="2e92b-235">비즈니스용 Skype Web App(외부 사용자만 해당)</span><span class="sxs-lookup"><span data-stu-id="2e92b-235">Skype for Business Web App (external users only)</span></span>  <br/> <span data-ttu-id="2e92b-236">모바일 장치(내부 및 외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="2e92b-236">Mobile device (internal and external users</span></span>  <br/> |<span data-ttu-id="2e92b-237">선호도 없음</span><span class="sxs-lookup"><span data-stu-id="2e92b-237">No affinity</span></span>  <br/> |<span data-ttu-id="2e92b-238">원본 주소 선호도</span><span class="sxs-lookup"><span data-stu-id="2e92b-238">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="2e92b-239">비즈니스용 Skype Web App(내부 사용자만 해당)</span><span class="sxs-lookup"><span data-stu-id="2e92b-239">Skype for Business Web App (internal users only)</span></span>  <br/> <span data-ttu-id="2e92b-240">모바일 장치(배포되지 않음)</span><span class="sxs-lookup"><span data-stu-id="2e92b-240">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="2e92b-241">선호도 없음</span><span class="sxs-lookup"><span data-stu-id="2e92b-241">No affinity</span></span>  <br/> |<span data-ttu-id="2e92b-242">원본 주소 선호도</span><span class="sxs-lookup"><span data-stu-id="2e92b-242">Source address affinity</span></span>  <br/> |
   
#### <a name="port-monitoring-for-hlbs"></a><span data-ttu-id="2e92b-243">HB에 대한 포트 모니터링</span><span class="sxs-lookup"><span data-stu-id="2e92b-243">Port monitoring for HLBs</span></span>

<span data-ttu-id="2e92b-244">하드웨어 부하 균형 조정기에서 포트 모니터링을 정의하여 하드웨어 또는 통신 오류로 인해 특정 서비스를 더 이상 사용할 수 없는 경우를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-244">You define port monitoring on your hardware load balancers to determine when specific services are no longer available, due to hardware or communications failure.</span></span> <span data-ttu-id="2e92b-245">예를 들어 프런트 엔드 서버 또는 프런트 엔드 풀에 오류가 발생하여 RTCSRV(프런트 엔드 서버 서비스)가 중지되는 경우 HLB 모니터링도 웹 서비스에서 트래픽 수신을 중지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-245">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="2e92b-246">HLB 외부 인터페이스에 대해 다음을 모니터링하기 위해 HLB에서 포트 모니터링을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-246">You should implement port monitoring on the HLB to monitor the following for your HLB external interface:</span></span>
  
|<span data-ttu-id="2e92b-247">**가상 IP/포트**</span><span class="sxs-lookup"><span data-stu-id="2e92b-247">**Virtual IP/Port**</span></span>|<span data-ttu-id="2e92b-248">**노드 포트**</span><span class="sxs-lookup"><span data-stu-id="2e92b-248">**Node Port**</span></span>|<span data-ttu-id="2e92b-249">**노드 컴퓨터/모니터**</span><span class="sxs-lookup"><span data-stu-id="2e92b-249">**Node Machine/Monitor**</span></span>|<span data-ttu-id="2e92b-250">**지속성 프로필**</span><span class="sxs-lookup"><span data-stu-id="2e92b-250">**Persistence Profile**</span></span>|<span data-ttu-id="2e92b-251">**참고**</span><span class="sxs-lookup"><span data-stu-id="2e92b-251">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2e92b-252">\<pool\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="2e92b-252">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="2e92b-253">443</span><span class="sxs-lookup"><span data-stu-id="2e92b-253">443</span></span>  <br/> |<span data-ttu-id="2e92b-254">4443</span><span class="sxs-lookup"><span data-stu-id="2e92b-254">4443</span></span>  <br/> |<span data-ttu-id="2e92b-255">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="2e92b-255">Front End</span></span>  <br/> <span data-ttu-id="2e92b-256">5061</span><span class="sxs-lookup"><span data-stu-id="2e92b-256">5061</span></span>  <br/> |<span data-ttu-id="2e92b-257">없음</span><span class="sxs-lookup"><span data-stu-id="2e92b-257">None</span></span>  <br/> |<span data-ttu-id="2e92b-258">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2e92b-258">HTTPS</span></span>  <br/> |
|<span data-ttu-id="2e92b-259">\<pool\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="2e92b-259">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="2e92b-260">80</span><span class="sxs-lookup"><span data-stu-id="2e92b-260">80</span></span>  <br/> |<span data-ttu-id="2e92b-261">8080</span><span class="sxs-lookup"><span data-stu-id="2e92b-261">8080</span></span>  <br/> |<span data-ttu-id="2e92b-262">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="2e92b-262">Front End</span></span>  <br/> <span data-ttu-id="2e92b-263">5061</span><span class="sxs-lookup"><span data-stu-id="2e92b-263">5061</span></span>  <br/> |<span data-ttu-id="2e92b-264">없음</span><span class="sxs-lookup"><span data-stu-id="2e92b-264">None</span></span>  <br/> |<span data-ttu-id="2e92b-265">HTTP</span><span class="sxs-lookup"><span data-stu-id="2e92b-265">HTTP</span></span>  <br/> |
   
## <a name="hardware-and-software-requirements"></a><span data-ttu-id="2e92b-266">하드웨어 및 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e92b-266">Hardware and software requirements</span></span>

<span data-ttu-id="2e92b-267">비즈니스용 Skype 서버 [2015에](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 대한 전체 서버 요구 사항과 비즈니스용  [Skype 서버 2019](../../../SfBServer2019/plan/system-requirements.md) 설명서에 대한 시스템 요구 사항에서 에지 서버 하드웨어 및 소프트웨어 요구 사항을 다루고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e92b-267">We've covered Edge Server hardware and software requirements in our overall [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and  [System requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md) documentation.</span></span>
  
## <a name="collocation"></a><span data-ttu-id="2e92b-268">Collocation</span><span class="sxs-lookup"><span data-stu-id="2e92b-268">Collocation</span></span>

<span data-ttu-id="2e92b-269">비즈니스용 Skype 서버용 토폴로지 기본 문서에서 에지 서버의 [병행에 대해 설명했습니다.](../../plan-your-deployment/topology-basics/topology-basics.md)</span><span class="sxs-lookup"><span data-stu-id="2e92b-269">We've covered Edge Server collocation in our [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md) documentation.</span></span>
  

