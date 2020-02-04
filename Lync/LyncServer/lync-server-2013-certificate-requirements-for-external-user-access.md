---
title: 'Lync Server 2013: 외부 사용자 액세스에 대한 인증서 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b6495dbad5350f94873099985922f1adc198f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="a742a-102">Lync Server 2013의 외부 사용자 액세스에 대한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a742a-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a742a-103">_**마지막으로 수정한 주제:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="a742a-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="a742a-104">Microsoft Lync Server 2013 통신 소프트웨어는 access 및 웹 회의에 지 외부 인터페이스와 A/V 인증 서비스에 대 한 단일 공용 인증서의 사용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="a742a-105">Edge 내부 인터페이스는 일반적으로 내부 CA (인증 기관)에서 발급 하는 개인 인증서를 사용 하지만, 신뢰할 수 있는 공용 CA에서 온 것으로 제공 되는 경우 공용 인증서를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="a742a-106">배포의 리버스 프록시는 공용 인증서를 사용 하 고 역방향 프록시에서 클라이언트로의 통신과 HTTP (HTTP를 통한 전송 계층 보안)를 사용 하 여 내부 서버에 대 한 역방향 프록시를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="a742a-107">다음은 access 및 웹 회의에 사용 되는 공용 인증서와 A/V 인증 서비스에 대 한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="a742a-108">인증서는 주체 대체 이름을 지 원하는 승인 된 공개 CA에 의해 발급 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="a742a-109">자세한 내용은 Microsoft 기술 자료 문서 929395, "Exchange Server 및 통신 서버용 통합 커뮤니케이션 인증서 파트너"를 참조 [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)하세요.</span><span class="sxs-lookup"><span data-stu-id="a742a-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="a742a-110">Edge 풀에서 인증서를 사용 하는 경우에는 edge 풀의 각 Edge 서버에서 동일한 인증서를 사용 하 여 내보낼 수 있는 것으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-110">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool.</span></span> <span data-ttu-id="a742a-111">내보낼 수 있는 개인 키 요구 사항은 풀의 모든 Edge 서버에서 동일한 개인 키를 사용 해야 하는 A/V 인증 서비스의 목적에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-111">The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="a742a-112">오디오/비디오 서비스의 가동 시간을 최대화 하려면 분리 된 A/V Edge 서비스 인증서를 구현 하기 위한 인증서 요구 사항 (즉, 다른 외부 Edge 인증서 용도를 사용 하는 별도의 A/V Edge 서비스 인증서)을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="a742a-113">자세한 내용은 Edge Server 계획, lync [server 2013의 Edge 서버 인증서에 대 한 계획](lync-server-2013-plan-for-edge-server-certificates.md) , lync server [2013 using-롤에서 CsCertificate의 OAuth 인증서 및 준비 AV](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)의 대/소문자를 사용 [하는 Lync server 2013의 변경 내용을](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a742a-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="a742a-114">인증서의 주체 이름은 액세스 경계 서비스 외부 인터페이스 FQDN (정규화 된 도메인 이름) 또는 하드웨어 부하 분산 장치 VIP (예: access.contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="a742a-115">).</span><span class="sxs-lookup"><span data-stu-id="a742a-115">).</span></span> <span data-ttu-id="a742a-116">제목 이름에는 와일드 카드 문자를 사용할 수 없으며, 이름을 명시적으로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a742a-117">Lync Server 2013의 경우에는 더 이상 요구 사항이 아니지만 Office Communications Server와의 호환성을 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="a742a-118">주체 대체 이름 목록에는 다음의 Fqdn이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="a742a-119">액세스에 지 서비스 외부 인터페이스 또는 하드웨어 부하 분산 장치 VIP (예: sip.contoso.com)</span><span class="sxs-lookup"><span data-stu-id="a742a-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a742a-120">인증서 주체 이름이 액세스에 지 FQDN과 동일 하더라도 TLS (전송 계층 보안)에서 주체 이름을 무시 하 고 주체 대체 이름 항목을 사용 하므로 주체 대체 이름에 액세스에 지 FQDN도 포함 해야 합니다. 유효성.</span><span class="sxs-lookup"><span data-stu-id="a742a-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="a742a-121">웹 회의에 지 외부 인터페이스 또는 하드웨어 부하 분산 장치 VIP (예: webcon.contoso.com)</span><span class="sxs-lookup"><span data-stu-id="a742a-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="a742a-122">클라이언트 자동 구성 또는 페더레이션을 사용 하는 경우 회사 내에서 사용 되는 모든 SIP 도메인 Fqdn (예: sip.contoso.com, sip.fabrikam.com)도 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="a742a-123">A/V Edge 서비스는 주체 이름 또는 주체 대체 이름 항목을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a742a-124">주체 대체 이름 목록의 Fqdn 순서는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="a742a-125">사이트에 부하 분산 된 여러 대의 Edge 서버를 배포 하는 경우 각 Edge 서버에 설치 된 A/V 인증 서비스 인증서가 같은 CA에 있어야 하 고 동일한 개인 키를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-125">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key.</span></span> <span data-ttu-id="a742a-126">한 Edge 서버 또는 다 수의 Edge 서버에서 사용 하는지 여부에 관계 없이 인증서의 개인 키를 내보낼 수 있어야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a742a-126">Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers.</span></span> <span data-ttu-id="a742a-127">Edge 서버 이외의 컴퓨터에서 인증서를 요청 하는 경우에도 내보낼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-127">It must also be exportable if you request the certificate from any computer other than the Edge Server.</span></span> <span data-ttu-id="a742a-128">A/V 인증 서비스는 주체 이름 또는 주체 대체 이름을 사용 하지 않으므로 액세스 가장자리에 대 한 주체 이름 및 주체 대체 이름 요구 사항이 충족 되 고 웹 회의 가장자리와 인증서의 개인 키를 내보낼 수 있는 동안에는 액세스에 지 인증서를 다시 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-128">Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="a742a-129">Edge 내부 인터페이스에 사용 되는 개인 (또는 공용) 인증서에 대 한 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="a742a-130">인증서는 내부 CA 또는 승인 된 공개 인증서 CA에 의해 발급 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="a742a-131">인증서의 주체 이름은 일반적으로 Edge 내부 인터페이스 FQDN 또는 하드웨어 부하 분산 장치 VIP (예: lsedge.contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-131">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com).</span></span> <span data-ttu-id="a742a-132">그러나 Edge 내부에서 와일드 카드 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-132">However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="a742a-133">주체 대체 이름 목록이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="a742a-134">배포 서비스의 리버스 프록시는 다음에 대 한 요청을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="a742a-135">모임 콘텐츠에 대 한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="a742a-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="a742a-136">메일 그룹 구성원을 확장 하 고 표시 하는 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="a742a-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="a742a-137">주소록 서비스에서 다운로드 가능한 파일에 대 한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="a742a-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="a742a-138">Lync Web App 클라이언트에 대 한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="a742a-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="a742a-139">전화 접속 회의 설정 웹 페이지에 대 한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="a742a-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="a742a-140">위치 정보 서비스에 대 한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="a742a-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="a742a-141">장치 업데이트 서비스에 대 한 외부 장치 액세스 및 업데이트 받기</span><span class="sxs-lookup"><span data-stu-id="a742a-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="a742a-142">역방향 프록시는 내부 서버 웹 구성 요소 Url을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="a742a-143">웹 구성 요소 Url은 디렉터, 프런트 엔드 서버 또는 프런트 엔드 풀에서 토폴로지 작성기의 **외부 웹 서비스로** 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="a742a-144">와일드 카드 항목은 리버스 프록시에 할당 된 인증서의 주체 대체 이름 필드에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a742a-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="a742a-145">리버스 프록시에 대 한 인증서 요청을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 역방향 HTTP 프록시에 대 한 인증서 요청 및 구성을](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a742a-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a742a-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a742a-146">See Also</span></span>


[<span data-ttu-id="a742a-147">Lync Server 2013의 와일드카드 인증서 지원</span><span class="sxs-lookup"><span data-stu-id="a742a-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

