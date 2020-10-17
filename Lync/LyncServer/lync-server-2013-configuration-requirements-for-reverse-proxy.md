---
title: 'Lync Server 2013: 역방향 프록시에 대 한 구성 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 555169f6de67ae23bc63d81aad549b0033a6696c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507745"
---
# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="897c2-102">Lync Server 2013의 역방향 프록시에 대 한 구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="897c2-102">Configuration requirements for reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="897c2-103">_**마지막으로 수정 된 항목:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="897c2-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="897c2-104">Lync Server 2013에서는 외부 클라이언트와의 통신에 대 한 몇 가지 요구 사항이 디렉터, 디렉터 풀, 프런트 엔드 서버 또는 프런트 엔드 풀에 호스트 되는 외부 웹 서비스로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-104">Lync Server 2013 imposes a few requirements on communications from the external client that are then passed on to the external Web services hosted on the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="897c2-105">또한 사용자에 게 회의를 제공 하는 경우에는 역방향 프록시가 Office Web Apps 서버 게시를 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-105">The reverse proxy is also responsible for publishing the Office Web Apps Server, if you are offering conferencing to your users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="897c2-106">Lync Server 2013에서 사용 해야 하는 특정 역방향 프록시를 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-106">Lync Server 2013 does not specify a particular reverse proxy that you must use.</span></span> <span data-ttu-id="897c2-107">Lync Server 2013는 역방향 프록시가 수행할 수 있어야 하는 운영 요구 사항을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-107">Lync Server 2013 only defines operational requirements that the reverse proxy must be able to do.</span></span> <span data-ttu-id="897c2-108">일반적으로 인프라에 이미 배포 된 역방향 프록시는 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-108">Typically, the reverse proxy that you already have deployed in your infrastructure may be able to meet the requirements.</span></span>



</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="897c2-109">역방향 프록시 요구 사항</span><span class="sxs-lookup"><span data-stu-id="897c2-109">Reverse Proxy Requirements</span></span>

<span data-ttu-id="897c2-110">Lync Server 2013에서 역방향 프록시가 수행 해야 하는 기능 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-110">The functional operations that Lync Server 2013 expect a reverse proxy to perform are:</span></span>

  - <span data-ttu-id="897c2-111">공용 인증 기관에서 획득 한 인증서를 사용 하 여 디렉터, 디렉터 풀, 프런트 엔드 서버 또는 프런트 엔드 풀의 게시 된 외부 웹 서비스에 연결 하 여 구현 되는 SSL (secure sockets layer) 및 TLS (전송 계층 보안)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-111">Use secure socket layer (SSL) and transport layer security (TLS) implemented by using certificates acquired from a public certification authority to connect to the published external Web services of the Director, Director pool, Front End Server or Front End pool.</span></span> <span data-ttu-id="897c2-112">디렉터 및 프런트 엔드 서버는 하드웨어 부하 분산 장치를 사용 하 여 부하가 분산 된 풀에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-112">The Director and the Front End Server can be in a load-balanced pool by using hardware load balancers.</span></span>

  - <span data-ttu-id="897c2-113">필요한 경우 암호화를 위해 인증서를 사용 하 여 내부 웹 사이트를 게시 하거나 암호화 되지 않은 방법으로 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-113">Able to publish internal Web sites using certificates for encryption, or publish them over an unencrypted means, if needed.</span></span>

  - <span data-ttu-id="897c2-114">FQDN (정규화 된 도메인 이름)을 사용 하 여 외부적으로 호스트 된 웹 사이트를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-114">Able to publish an internally hosted web site externally by using a fully qualified domain name (FQDN).</span></span>

  - <span data-ttu-id="897c2-115">호스트 된 웹 사이트의 모든 콘텐츠를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-115">Able to publish all contents of the hosted web site.</span></span> <span data-ttu-id="897c2-116">기본적으로 **/\*** 대부분의 웹 서버에서 인식 되는이 지시어를 사용 하 여 "웹 서버의 모든 콘텐츠 게시"를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-116">By default, you can use the **/\*** directive, which is recognized by most web servers to mean "Publish all content on the web server."</span></span> <span data-ttu-id="897c2-117">"가상 디렉터리에 있는 모든 콘텐츠 게시"를 의미 하는 \*\*/Uwca/ \* \*\*와 같은 지시문을 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-117">You can also modify the directive—for example, **/Uwca/\***, which means "Publish all content under the virtual directory Ucwa."</span></span>

  - <span data-ttu-id="897c2-118">게시 된 웹 사이트의 콘텐츠를 요청 하는 클라이언트와 SSL (Secure Sockets layer) 및/또는 TLS (전송 계층 보안) 연결이 필요 하도록 구성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-118">Must be configurable to require Secure Sockets Layer (SSL) and/or Transport Layer Security (TLS) connections with clients that request content from a published website.</span></span>

  - <span data-ttu-id="897c2-119">주체 대체 이름 (SAN) 항목을 포함 하는 인증서를 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-119">Must accept certificates with subject alternative name (SAN) entries.</span></span>

  - <span data-ttu-id="897c2-120">외부 웹 서비스 FQDN이 확인 하는 수신기 또는 인터페이스에 대 한 인증서 바인딩을 허용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-120">Must be able to allow binding of a certificate to a listener or interface through which the external web services FQDN will resolve.</span></span> <span data-ttu-id="897c2-121">수신기 구성은 인터페이스 보다 더 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-121">Listener configurations are preferable to interfaces.</span></span> <span data-ttu-id="897c2-122">단일 인터페이스에 여러 수신기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-122">Many listeners can be configured on a single interface.</span></span>

  - <span data-ttu-id="897c2-123">호스트 헤더 처리의 구성을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-123">Must allow for the configuration of host header handling.</span></span> <span data-ttu-id="897c2-124">요청 하는 클라이언트에서 보내는 원래 호스트 헤더를 역방향 프록시에서 수정 하는 대신 투명 하 게 전달 해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-124">Often, the original host header sent by the requesting client must be passed transparently, instead of being modified by the reverse proxy.</span></span>

  - <span data-ttu-id="897c2-125">외부에서 정의 된 하나의 포트 (예: TCP 443)에서 다른 정의 된 포트 (예: TCP 4443)로 SSL 및 TLS 트래픽을 브리징 합니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-125">Bridging of SSL and TLS traffic from one externally defined port (for example, TCP 443) to another defined port (for example, TCP 4443).</span></span> <span data-ttu-id="897c2-126">역방향 프록시는 수신 시 패킷 암호를 해독 한 다음 송신 시에 패킷을 다시 암호화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-126">The reverse proxy may decrypt the packet on receipt and then reencrypt the packet on sending.</span></span>

  - <span data-ttu-id="897c2-127">한 포트 (예: tcp 80)에서 다른 포트로 암호화 되지 않은 TCP 트래픽을 브리지 합니다 (예: TCP 8080).</span><span class="sxs-lookup"><span data-stu-id="897c2-127">Bridging of unencrypted TCP traffic from one port (for example, TCP 80) to another (for example, TCP 8080).</span></span>

  - <span data-ttu-id="897c2-128">구성 또는 수락, NTLM 인증, 인증 안 함 및 통과 인증을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="897c2-128">Allow configuration of, or accept, NTLM authentication, No authentication and Pass-through authentication.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

