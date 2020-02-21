---
title: 'Lync Server 2013: 외부 사용자 액세스에 대 한 인증서 요구 사항'
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
ms.openlocfilehash: dda45706b8c55bf99120ec3776702060998a6921
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="da45e-102">Lync Server 2013의 외부 사용자 액세스에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="da45e-102">Certificate requirements for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da45e-103">_**마지막으로 수정 된 항목:** 2016-03-29_</span><span class="sxs-lookup"><span data-stu-id="da45e-103">_**Topic Last Modified:** 2016-03-29_</span></span>

<span data-ttu-id="da45e-104">Microsoft Lync Server 2013 communications software는 access 및 웹 회의에 지 외부 인터페이스와 A/V 인증 서비스에 대해 단일 공용 인증서를 사용할 것을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-104">Microsoft Lync Server 2013 communications software supports the use of a single public certificate for access and web conferencing Edge external interfaces, plus the A/V Authentication service.</span></span> <span data-ttu-id="da45e-105">에 지 내부 인터페이스는 일반적으로 내부 CA (인증 기관)에서 발급 한 개인 인증서를 사용 하지만, 신뢰할 수 있는 공용 CA가 제공 하는 경우에는 공용 인증서를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-105">The Edge internal interface typically uses a private certificate issued by an internal certification authority (CA), but can also use a public certificate, provided that it is from a trusted public CA.</span></span> <span data-ttu-id="da45e-106">배포의 역방향 프록시는 공용 인증서를 사용 하 고 역방향 프록시에서 클라이언트로의 통신을 암호화 하 고, HTTP를 사용 하 여 내부 서버 (HTTP를 통한 전송 계층 보안)에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-106">The reverse proxy in your deployment uses a public certificate and encrypts the communication from the reverse proxy to clients and the reverse proxy to internal servers by using HTTP (that is, Transport Layer Security over HTTP).</span></span>

<span data-ttu-id="da45e-107">다음은 액세스 및 웹 회의 에지 외부 인터페이스 및 A/V 인증 서비스에 사용되는 공용 인증서에 대한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-107">Following are the requirements for the public certificate used for access and web conferencing Edge external interfaces, and the A/V authentication service:</span></span>

  - <span data-ttu-id="da45e-108">인증서는 주체 대체 이름을 지원하는 승인된 공용 CA에서 발급된 것이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-108">The certificate must be issued by an approved public CA that supports subject alternative name.</span></span> <span data-ttu-id="da45e-109">자세한 내용은 Microsoft 기술 자료 문서 929395, "Exchange Server 및 Communications Server에 대 한 통합 통신 인증서 파트너"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)하세요.</span><span class="sxs-lookup"><span data-stu-id="da45e-109">For details, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

  - <span data-ttu-id="da45e-p103">인증서가 에지 풀에서 사용되는 경우 에지 풀의 각 에지 서버에서 사용되는 동일한 인증서와 함께 내보낼 수 있는 상태로 만들어야 합니다. 내보낼 수 있는 개인 키 요구 사항은 풀의 모든 에지 서버에서 동일한 개인 키를 사용해야 하는 A/V 인증 서비스의 목적을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-p103">If the certificate will be used on an Edge pool, it must be created as exportable, with the same certificate used on each Edge Server in the Edge pool. The exportable private key requirement is for the purposes of the A/V Authentication service, which must use the same private key across all Edge Servers in the pool.</span></span>

  - <span data-ttu-id="da45e-112">오디오/비디오 서비스에 대 한 가동 시간을 최대화 하려면 분리 된 A/V에 지 서비스 인증서 (즉, 다른 외부에 지 인증서 용도 로부터의 별도 A/V에 지 서비스 인증서)를 구현 하기 위한 인증서 요구 사항을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-112">If you want to maximize the uptime for your Audio/Video services, review the certificate requirements for implementing a decoupled A/V Edge service certificate (that is, a separate A/V Edge service certificate from the other External Edge certificate purposes).</span></span> <span data-ttu-id="da45e-113">자세한 내용은에 [지 서버 계획에 영향을 주는 Lync server 2013의 변경 사항](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), lync server 2013의에 지 서버 인증서 및 [SET-CSCERTIFICATE의 준비 AV 및 OAuth 2013 인증서](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)에 [대 한 계획](lync-server-2013-plan-for-edge-server-certificates.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="da45e-113">For details, see [Changes in Lync Server 2013 that affect Edge Server planning](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [Plan for Edge Server certificates in Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) and [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).</span></span>

  - <span data-ttu-id="da45e-114">인증서의 주체 이름은 액세스에 지 서비스 외부 인터페이스 FQDN (정규화 된 도메인 이름) 또는 하드웨어 부하 분산 장치 VIP (예: access.contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-114">The subject name of the certificate is the Access Edge service external interface fully qualified domain name (FQDN) or hardware load balancer VIP (for example, access.contoso.com).</span></span> <span data-ttu-id="da45e-115">).</span><span class="sxs-lookup"><span data-stu-id="da45e-115">).</span></span> <span data-ttu-id="da45e-116">제목 이름에는 와일드 카드 문자를 사용할 수 없으며 명시적 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-116">The subject name can’t have a wildcard character, it must be an explicit name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da45e-117">Lync Server 2013의 경우에는 더 이상 필요 하지 않지만 Office Communications Server와의 호환성을 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-117">For Lync Server 2013, this is no longer a requirement, but it is still recommended for compatibility with Office Communications Server.</span></span>

    
    </div>

  - <span data-ttu-id="da45e-118">주체 대체 이름 목록에는 다음의 FQDN이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-118">The subject alternative name list contains the FQDNs of the following:</span></span>
    
      - <span data-ttu-id="da45e-119">액세스에 지 서비스 외부 인터페이스 또는 하드웨어 부하 분산 장치 VIP (예: sip.contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-119">The Access Edge service external interface or hardware load balancer VIP (for example, sip.contoso.com).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="da45e-120">인증서 주체 이름이 액세스 에지 FQDN과 동일한 경우에도 TLS(전송 계층 보안)가 주체 이름을 무시하고 유효성 검사를 위해 주체 대체 이름 항목을 사용하므로 주체 대체 이름에는 액세스 에지 FQDN이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-120">Even though the certificate subject name is equal to the access Edge FQDN, the subject alternative name must also contain the access Edge FQDN because Transport Layer Security (TLS) ignores the subject name and uses the subject alternative name entries for validation.</span></span>

        
        </div>
    
      - <span data-ttu-id="da45e-121">웹 회의 에지 외부 인터페이스 또는 하드웨어 부하 분산 장치 VIP(예: webcon.contoso.com)</span><span class="sxs-lookup"><span data-stu-id="da45e-121">The web conferencing Edge external interface or hardware load balancer VIP (for example, webcon.contoso.com).</span></span>
    
      - <span data-ttu-id="da45e-122">클라이언트 자동 구성 또는 페더레이션을 사용하는 경우 회사 내에서 사용되는 SIP 도메인 FQDN도 포함해야 합니다(예: sip.contoso.com, sip.fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="da45e-122">If you are using client auto-configuration or federation, also include any SIP domain FQDNs used within your company (for example, sip.contoso.com, sip.fabrikam.com).</span></span>
    
      - <span data-ttu-id="da45e-123">A/V에 지 서비스는 주체 이름 또는 주체 대체 이름 항목을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-123">The A/V Edge service does not use the subject name or the subject alternative names entries.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="da45e-124">주체 대체 이름 목록에서 FQDN의 순서는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-124">The order of the FQDNs in the subject alternative names list does not matter.</span></span>

    
    </div>

<span data-ttu-id="da45e-p106">한 사이트에 여러 부하 분산 에지 서버를 배포하는 경우 각 에지 서버에 설치된 A/V 인증 서비스 인증서가 동일한 CA에서 발급된 것이어야 하며 동일한 개인 키를 사용해야 합니다. 인증서의 개인 키는 한 에지 서버 또는 많은 에지 서버에서 사용되는지 여부에 관계없이 내보낼 수 있어야 합니다. 또한 에지 서버가 아닌 다른 컴퓨터에서 인증서를 요청하는 경우에도 내보낼 수 있어야 합니다. A/V 인증 서비스에는 주체 이름 또는 주체 대체 이름이 사용되지 않으므로 주체 이름 및 주체 대체 이름 요구 사항이 액세스 에지 및 웹 회의 에지에 대해 충족되고 인증서의 개인 키를 내보낼 수 있는 한 액세스 에지 인증서를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-p106">If you are deploying multiple, load-balanced Edge Servers at a site, the A/V authentication service certificate that is installed on each Edge Server must be from the same CA and must use the same private key. Note that the certificate's private key must be exportable, regardless of whether it is used on one Edge Server or many Edge Servers. It must also be exportable if you request the certificate from any computer other than the Edge Server. Because the A/V authentication service does not use the subject name or subject alternative name, you can reuse the access Edge certificate as long as the subject name and subject alternative name requirements are met for the access Edge and the web conferencing Edge and the certificate’s private key is exportable.</span></span>

<span data-ttu-id="da45e-129">에지 외부 인터페이스에 사용되는 개인(또는 공용) 인증서에 대한 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-129">Requirements for the private (or public) certificate used for the Edge internal interface are as follows:</span></span>

  - <span data-ttu-id="da45e-130">인증서는 내부 CA 또는 승인된 공용 인증서 CA에서 발급할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-130">The certificate can be issued by an internal CA or an approved public certificate CA.</span></span>

  - <span data-ttu-id="da45e-p107">인증서의 주체 이름은 일반적으로 에지 내부 인터페이스 FQDN 또는 하드웨어 부하 분산 장치 VIP(예: lsedge.contoso.com)입니다. 그러나 에지 내부에서 와일드카드 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-p107">The subject name of the certificate is typically the Edge internal interface FQDN or hardware load balancer VIP (for example, lsedge.contoso.com). However, you can use a wildcard certificate on the Edge internal.</span></span>

  - <span data-ttu-id="da45e-133">주체 대체 이름 목록은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-133">No subject alternative name list is required.</span></span>

<span data-ttu-id="da45e-134">배포에서 역방향 프록시는 다음에 대한 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-134">The reverse proxy in your deployment services requests for:</span></span>

  - <span data-ttu-id="da45e-135">모임 콘텐츠에 대한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="da45e-135">External user access to meeting content for meetings</span></span>

  - <span data-ttu-id="da45e-136">메일 그룹의 구성원을 확장 및 표시하기 위한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="da45e-136">External user access to expand and display members of distribution groups</span></span>

  - <span data-ttu-id="da45e-137">주소록에서 다운로드할 수 있는 파일에 대한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="da45e-137">External user access to downloadable files from the Address Book Service</span></span>

  - <span data-ttu-id="da45e-138">Lync Web App 클라이언트에 대 한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="da45e-138">External user access to the Lync Web App client</span></span>

  - <span data-ttu-id="da45e-139">전화 접속 회의 설정 웹 페이지에 대한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="da45e-139">External user access to the Dial-in Conferencing Settings web page</span></span>

  - <span data-ttu-id="da45e-140">위치 정보 서비스에 대한 외부 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="da45e-140">External user access to the Location Information Service</span></span>

  - <span data-ttu-id="da45e-141">장치 업데이트 서비스 및 업데이트 획득을 위한 외부 장치 액세스</span><span class="sxs-lookup"><span data-stu-id="da45e-141">External device access to the Device Update Service and obtain updates</span></span>

<span data-ttu-id="da45e-142">역방향 프록시는 내부 서버의 웹 구성 요소 URL을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-142">The reverse proxy publishes the internal server Web Components URLs.</span></span> <span data-ttu-id="da45e-143">웹 구성 요소 Url은 디렉터, 프런트 엔드 서버 또는 프런트 엔드 풀에서 토폴로지 작성기의 **외부 웹 서비스로** 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-143">The Web Components URLs are defined on the Director, Front End Server or Front End pool as the **External web services** in Topology Builder.</span></span>

<span data-ttu-id="da45e-144">와일드 카드 항목은 역방향 프록시에 할당된 인증서의 주체 대체 이름 필드에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="da45e-144">Wildcard entries are supported in the subject alternative name field of the certificate assigned to the reverse proxy.</span></span> <span data-ttu-id="da45e-145">역방향 프록시에 대 한 인증서 요청을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 역방향 HTTP 프록시에 대 한 인증서 요청 및 구성을](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="da45e-145">For details about how to configure the certificate request for the reverse proxy, see [Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="da45e-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da45e-146">See Also</span></span>


[<span data-ttu-id="da45e-147">Lync Server 2013의 와일드 카드 인증서 지원</span><span class="sxs-lookup"><span data-stu-id="da45e-147">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

