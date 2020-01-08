---
title: 'Lync Server 2013: 에지 서버 계획에 영향을 주는 Lync Server의 변경 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d13b40430455c87a60c0fadc20980df5a8aa1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="caf5a-102">에지 서버 계획에 영향을 주는 Lync Server 2013의 변경 사항</span><span class="sxs-lookup"><span data-stu-id="caf5a-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="caf5a-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="caf5a-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="caf5a-104">Lync Server 2013는 사용자의 기능 및 통신 방법을 확장 하는 새로운 기능을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="caf5a-105">또한 Lync Server 2013는 조직에서 사용할 수 있는 서비스를 더욱 효율적으로 통합 하 고 확장 하기 위해 기존 서비스에 대 한 변경 사항을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="caf5a-106">다음은 Lync Server 2013 Edge 서버 서비스의 계획 및 배포에 영향을 줄 수 있는 변경 내용에 대 한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="caf5a-107">IPv6 주소 지정 지원</span><span class="sxs-lookup"><span data-stu-id="caf5a-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="caf5a-108">Lync Server 2013는 모든 Edge 서버 서비스에 대 한 IPv6 주소 지정을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="caf5a-109">Windows Server의 구성을 통해 인터페이스에 대 한 IPv6 주소를 제공한 경우 토폴로지 작성기의 IP 주소 구성을 통해 Edge 서버 구성에서 IPv6 주소를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="caf5a-110">또한 XMPP는 확장 가능한 메시징 및 현재 상태 프로토콜을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="caf5a-111">추가 구성은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-111">No additional configuration is required.</span></span> <span data-ttu-id="caf5a-112">토폴로지에서 IPv6이 구성 된 경우 XMPP는 IPv6을 사용 합니다 (필요한 경우).</span><span class="sxs-lookup"><span data-stu-id="caf5a-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="caf5a-113">Lync Server 2013에서 IPv6을 지원 하기 위해 추가 요구 사항은 검색 하 고 IPv6 주소로 확인 해야 하는 레코드에 대 한 도메인 이름 시스템 레코드를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="caf5a-114">IPv6 DNS는 **AAAA** 로 정의 되 고 "쿼드 A" 라고 하는 호스트 레코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="caf5a-115">다른 레코드 형식은 해당 IPv4와 일관성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="caf5a-116">XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 배포 지원</span><span class="sxs-lookup"><span data-stu-id="caf5a-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="caf5a-117">Edge 서버에는 완전 하 게 통합 된 XMPP 프록시 (Edge 서버에 배포 됨)와 XMPP 게이트웨이 (프런트 엔드 서버에 배포 됨)가 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="caf5a-118">XMPP 페더레이션은 선택적 구성 요소로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="caf5a-119">XMPP 프록시 및 XMPP 게이트웨이를 추가 하 고 구성 하면 사용자가 인스턴트 메시지 (IM) 및 현재 상태에 대 한 XMPP 기반 파트너의 연락처를 추가 하도록 2013 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="caf5a-120">현재 Edge 서버의 XMPP 서비스는 Lync Server 클라이언트와 XMPP 기반 연락처 간에 IM 및 현재 상태를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="caf5a-121">또한 XMPP는 하나의 사이트 에서만 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="caf5a-122">Google 대화가 포함 된 인스턴트 메시징 페더레이션에 대해 Microsoft에서 Lync Server 2013의 XMPP 기능을 테스트 하 고 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-122">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="caf5a-123">다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션이 지원 되는지 여부와 배포 또는 문제 해결에 대 한 권장 사항을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-123">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="caf5a-124">오디오/비디오 인증 및 서버에서 서버에 대 한 인증 인증서 롤링 지원</span><span class="sxs-lookup"><span data-stu-id="caf5a-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="caf5a-125">인증서는 클라이언트 및 A/V 인증 서비스의 다른 소비자와 서버에서 서버에 대 한 인증을 위해 발급 되는 토큰을 생성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-125">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication.</span></span> <span data-ttu-id="caf5a-126">오디오/비디오 인증 인증서의 형식은 e *Videoauthentication* 이며 서버 대 서버 인증 인증서의 형식은 *Oauthtokenissuer*입니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-126">The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="caf5a-127">오디오/비디오 인증을 위해 토큰은 포트 할당 요청을 인증 하는 데 사용 되며 최대 8 시간 동안 토큰의 기본 수명으로 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-127">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token.</span></span> <span data-ttu-id="caf5a-128">정상 작동 중에는 인증 자료를 만들어 A/V 소비자에 게 배포 하는 매우 안정적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-128">Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers.</span></span> <span data-ttu-id="caf5a-129">그러나 인증서는 정해진 날짜와 시간에 만료 되며, 생성 날짜 및 인증서를 만든 인증 기관에 적용 되는 정책 (일반적으로 이러한 유형의 인증서에 대해 2 년)에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-129">However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate).</span></span> <span data-ttu-id="caf5a-130">인증서가 만료 되 면 만료 된 인증서로 생성 되 고 소비자가 캐시 한 모든 토큰이 유효 하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-130">When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid.</span></span> <span data-ttu-id="caf5a-131">만료 된 인증서로 만든 토큰을 사용 하려는 경우 미디어 릴레이 할당이 실패 하 고 현재 오디오/비디오 세션이 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-131">Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail.</span></span> <span data-ttu-id="caf5a-132">클라이언트는 일반 오디오 및 비디오 기능을 다시 시작 하기 위해 유효한 인증서로 만든 새 토큰을 취득 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-132">The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="caf5a-133">서버 대 서버 인증은 배포의 모든 서버에 요청 되 고 적용 되는 전역 인증서로 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="caf5a-134">이 인증서는 Lync Server 2013에서 서버를 인증 하는 것은 물론 Exchange 2013 및 Microsoft SharePoint Server 2013에 대 한 인증을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="caf5a-135">서버에서 서버 인증을 수행 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="caf5a-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="caf5a-136">오디오/비디오 인증 프로세스와 서버 간 인증 프로세스 간에 매우 중요 한 차이점은 인증 또는 토큰의 수명입니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="caf5a-137">오디오/비디오 인증의 경우 8 시간 후에 인증이 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="caf5a-138">서버 간 인증의 수명은 24 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="caf5a-139">각 인증서 유형에 대해 적절 하 게 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="caf5a-140">Lync Server 2013에 대 한 새로운 기능은 현재 인증서의 만료에 앞서 대체 오디오/비디오 인증 인증서 및 서버에서 서버 인증 인증서를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="caf5a-141">새 인증서는 새 토큰 또는 새 인증 요청을 생성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="caf5a-142">하지만 현재 세션과 인증을 확인 하기 위한 이전 인증서는 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="caf5a-143">이는 토큰 및 인증서 만료로 인해 거의 모든 오류를 효과적으로 방지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="caf5a-144">이 기능에 대 한 자세한 내용과 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013 using-롤에서 설정-CsCertificate에서 AV 및 OAuth 인증서 준비](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="caf5a-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="caf5a-145">쿠키 기반 선호도에 대 한 의존도 감소</span><span class="sxs-lookup"><span data-stu-id="caf5a-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="caf5a-146">이전 버전의 Lync Server 및 Office Communications Server에서 쿠키 기반 선호도는 웹 서비스에서 클라이언트 및 웹 서비스 세션 상태가 유지 되도록 하는 데 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="caf5a-147">Lync Server 2013 웹 서비스는 쿠키 기반 선호도에 대 한 대부분의 요구 사항을 제거 하는 기본 제공 선호도 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="caf5a-148">Microsoft Lync 2010 모바일 클라이언트는 여전히 쿠키 기반 접근 허용을 사용 해야 하며, 예정 된 Microsoft Lync 모바일 클라이언트로 모든 클라이언트를 마이그레이션할 때까지 쿠키 기반 선호도를 구성 해야 합니다 (릴리스의 날짜가 아직 결정 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="caf5a-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="caf5a-149">Lync Server 2013의 쿠키 기반 선호도에 대 한 자세한 내용은 [Lync server 2013의 외부 사용자 액세스에 필요한 구성 요소](lync-server-2013-components-required-for-external-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="caf5a-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="caf5a-150">자동 검색 기능 향상</span><span class="sxs-lookup"><span data-stu-id="caf5a-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="caf5a-151">Lync Server 2013의 자동 검색 기능을 통해 클라이언트는 통신에 사용할 수 있는 추가 기능을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="caf5a-152">자동 검색은 Lync Server 2010의 누적 업데이트에서 처음 도입 되었으며, 이동성 및 Microsoft Lync 2010 Mobile 용 2011 11 월입니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="caf5a-153">자동 검색 기능 (DNS 레코드 이름에는 LyncDiscover 및 LyncDiscoverInternal이 라고도 함)은 클라이언트가 모바일 서비스 (Microsoft Lync 2010 모바일 클라이언트), Microsoft Lync Web App 및 Lync Web scheduler을 찾아 사용할 수 있도록 합니다. Microsoft Exchange Server 및 SharePoint Server와 통신</span><span class="sxs-lookup"><span data-stu-id="caf5a-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="caf5a-154">자동 검색은 인프라 및 Lync Server 2013 서버 설정 및 배포의 일반적인 부분으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="caf5a-155">토폴로지 작성기 및 Lync Server 배포 마법사는 Lync Server 2010의 누적 업데이트에 필요한 대부분의 구성 작업을 제거 합니다 (2011 년 11 월).</span><span class="sxs-lookup"><span data-stu-id="caf5a-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="caf5a-156">모바일 클라이언트용 서비스</span><span class="sxs-lookup"><span data-stu-id="caf5a-156">Services for Mobile Clients</span></span>

<span data-ttu-id="caf5a-157">Lync Server에 대 한 누적 업데이트 2010: lync 2013 Server의 모바일 서비스에서 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용 하 여 Lync Mobile 및 태블릿 장치를 실행 하는 모바일 전화를 사용할 수 있습니다 2011. 인스턴트 메시지 보내기, 받기, 연락처 보기, 현재 상태 보기 등의 활동</span><span class="sxs-lookup"><span data-stu-id="caf5a-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="caf5a-158">또한 모바일 장치는 클릭 하 여 회의에 참가 하 고, 회사, 단일 전화 접속, 음성 메일, 부재 중 전화 알림 등 일부 엔터프라이즈 음성 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="caf5a-159">모바일 서비스는 프런트 엔드 서버에 배포 되는 리버스 프록시 및 게시 된 서비스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="caf5a-160">Edge 서버를 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="caf5a-161">최소한 Lync Server 액세스 Edge 서비스를 실행 하는 서버에서 아웃 바운드 SIP/TCP/5061from 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="caf5a-162">디렉터 역할은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-162">Director Role is Optional</span></span>

<span data-ttu-id="caf5a-163">Lync Server 2013 토폴로지에서 디렉터 서버의 역할은 변경 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="caf5a-164">계속 해 서 웹 서비스를 호스팅하고, 들어오는 사용자 요청을 사전 인증 하 고, 외부 사용자를 홈 풀로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="caf5a-165">디렉터를 권장 역할에서 선택적 역할으로 변경 하는 것은 Microsoft가 디렉터 값을 감소 시 게 하지 않으려는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="caf5a-166">이는 기능과 기능을 손상 시 키 지 않고 서버 수 및 기타 하드웨어 요구 사항 (예: 디렉터의 하드웨어 부하 분산 장치)을 줄이는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="caf5a-167">프런트 엔드 서버는 제공 되는 서비스에 영향을 주지 않고 디렉터와 동일한 작업을 수행할 수 있기 때문에를 선택 하는 경우에는 디렉터를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="caf5a-168">프런트 엔드 서버가 디렉터 대신 동일한 서비스를 제공 한다는 확신 없이 디렉터를 안전 하 게 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf5a-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

