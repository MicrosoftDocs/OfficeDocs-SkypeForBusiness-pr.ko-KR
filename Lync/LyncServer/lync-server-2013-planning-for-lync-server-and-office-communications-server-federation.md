---
title: Lync Server 및 Office Communications Server 페더레이션 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22c94254921e3aa1cde8d93998f8fe5bf122ac92
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="fbfb7-102">Lync Server 2013 및 Office Communications Server federation 계획</span><span class="sxs-lookup"><span data-stu-id="fbfb7-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbfb7-103">_**마지막으로 수정 된 항목:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="fbfb7-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="fbfb7-104">Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server 간의 페더레이션에서는 피어-투-피어 및 멀티 당사자 통신을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="fbfb7-105">피어 투 피어 대화는 단체 대화로 확대되어 임시 모임을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="fbfb7-106">웹 회의 또는 오디오/비디오 회의 같은 모임은 페더레이션 파트너의 대화 상대뿐 아니라 조직 내 대화 상대를 포함하도록 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="fbfb7-107">페더레이션은 Microsoft Office Live Communications Server 2005에 처음 표시 되며 한 종류의 페더레이션 (직접 페더레이션)을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="fbfb7-108">직접 페더레이션에서는 페더레이션 파트너의 SIP (세션 시작 프로토콜) 도메인과 파트너에 지 서버의 FQDN (정규화 된 도메인 이름)을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="fbfb7-109">Live Communications Server 2005 SP1에는 추가 페더레이션 유형이 도입 되었으며, 모든 필수 DNS (domain name system) SRV 레코드를 페더레이션 파트너가 해당에 지 서버를 찾기 위해 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="fbfb7-110">해당 릴리스에 사용되는 용어는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="fbfb7-111">*확장 페더레이션 열기*: 모든 SIP 도메인 이름을 수락 하 고 DNS SRV를 사용 하 여 파트너에 지 서버를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="fbfb7-112">*확장 페더레이션*: 파트너의 SIP 도메인 이름을 조직의 페더레이션 파트너로 구성 하 고 DNS SRV를 사용 하 여 파트너에 지 서버를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="fbfb7-113">*직접 페더레이션*: 파트너의 SIP 도메인 이름과 FQDN을 파트너의에 지 서버에 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="fbfb7-114">*서버 허용 목록*: 모든 도메인을 수락 하 고, DNS SRV를 사용 하 여 호스팅 공급자 또는 공용 IM (인스턴트 메시징) 연결 공급자의에 지 서버를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="fbfb7-115">Microsoft Office Communications Server 2007에서는 실제로 수행 되는 각 페더레이션 유형에 대해 보다 효율적으로 정의할 수 있도록 페더레이션 유형에 대 한 명명 된 이름이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="fbfb7-116">개방형 확장 페더레이션은 *검색된 파트너 도메인*으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="fbfb7-117">확장 페더레이션은 *허용된 파트너 도메인*으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="fbfb7-118">직접 페더레이션은 *허용된 파트너 서버*로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="fbfb7-119">서버 허용 목록은 *호스팅 공급자* 및 *공용 메신저 공급자*로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="fbfb7-120">Microsoft Lync Server 2010에서는 Microsoft Lync Online 2010 및 Microsoft Office 365에 따라 호스팅 공급자가 보다 제한적으로 정의 되었으며, 허용 되는 파트너 도메인 페더레이션 유형에 서 정의 된 것과 동일한 허용 목록을 적용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="fbfb7-121">Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server 간 페더레이션을 사용 하도록 설정에서는에 지 서버 및 역방향 프록시를 사용 하 여 사용자가 정의한 규칙과 허용 되는 파트너 도메인을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="fbfb7-122">계획 측면에서 다른 Lync Server와 페더레이션-Office Communications Server에는 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="fbfb7-123">토폴로지 작성기에서 페더레이션을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="fbfb7-124">자세한 내용은 [Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공용 인스턴트 메시징 구성](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)에 대 한 배포 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="fbfb7-125">페더레이션 도메인 검색에 필요한 요구 사항을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="fbfb7-126">페더레이션 수동 구성을 사용 하려면 Lync Server 제어판, **페더레이션 및 외부 액세스**, **SIP 페더레이션 도메인**에 입력 된 파트너에 지 서버 및 도메인 이름 또는 온라인 도메인 이름의 FQDN (정규화 된 도메인 이름)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="fbfb7-127">FQDN으로 도메인을 허용하거나 차단하려면 **새로 만들기**로 정책을 새로 만들거나 **편집**으로 기존 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="fbfb7-128">페더레이션 파트너의에 지 서버를 수동으로 구성 하면 파트너가 해당에 지 서버의 IP 주소를 변경 하는 경우 오류가 발생할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="fbfb7-129"><STRONG>새 SIP 페더레이션 도메인</STRONG>의 경우 microsoft Office 365에 대 한 사용자의 <STRONG>도메인 이름 (또는 FQDN)</STRONG> 을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="fbfb7-130">Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server의 경우에는 <STRONG>FQDN (액세스에 지 서비스)</STRONG> 도 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="fbfb7-131">파트너가에 지 서버를 검색할 수 있는 검색 된 파트너 페더레이션에 대해 외부 DNS- \_SIPFEDERATIONTLS에 SRV 레코드를 만듭니다. \_tcp.contoso.com –에 지 서버에 대 한 포트 5061 및 호스트 (A) 레코드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="fbfb7-132">Windows Phone 또는 Apple iPhone, iPad 또는 기타 Apple 장치에서 Microsoft Lync 모바일 클라이언트를 지원 하 고 푸시 알림 서비스 또는 푸시 알림 서비스를 사용 하는 경우에는 _sipfederationtls에 대 한 계획을 세워야 합니다 _tcp.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="fbfb7-133">&lt;Lync Mobile&gt; 클라이언트를 가진 각 sip 도메인에 대 한 SIP 도메인 SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="fbfb7-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="fbfb7-134">Android 및 Nokia Symbian Lync Mobile에서는 푸시 알림을 사용 하지 않으며,이 요구 사항이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="fbfb7-135">페더레이션 도메인을 지원하도록 외부 사용자 액세스 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="fbfb7-136">사용하는 대화 상대 또는 페더레이션을 수용할 수 있도록 SIP(Session Initiation Protocol), 웹 회의 및 오디오/비디오용 방화벽 포트를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="fbfb7-137">자세한 내용은: [External A/V 방화벽 및 포트 요구 사항 확인에서 Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="fbfb7-138">다음 정보는 Microsoft Lync Server 2013 및 Lync Server 2010와의 페더레이션에 대 한 인증서, 포트/프로토콜 및 DNS 요구 사항을 정의 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="fbfb7-139">인증서, 방화벽 및 포트/프로토콜 요구 사항에 대 한 계획은 일반적으로 Microsoft Lync Server 2013에 지 서버를 계획 하거나 배포한 경우의 직선 전달 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="fbfb7-140">페더레이션은 기존에 지 서버를 사용 하는 추가 기능이 기 때문에, 계획 요구 사항은 일반적으로에 지 서버 계획 및 배포에 의해 충족 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="fbfb7-141">다음 표를 참조하여 현재 요구 사항이 충족되는지, 표에 따라 포트/프로토콜 및 DNS를 변경해야 하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="fbfb7-142">에 지 서버 풀이 있고 Lync Server 2013 또는 Lync Server 2010 파트너와 페더레이션 중인 경우에는에 지 서버의 내부 및 외부 측면에서 DNS 부하 분산 또는 하드웨어 부하 분산 장치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="fbfb7-143">Office Communications Server 2007 또는 Office Communications Server 2007 r 2와 페더레이션 하는 경우 하드웨어 부하 분산은에 지 서버의 경우 장애 조치 (failover) 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="fbfb7-144">Office Communications Server 2007 및 Office Communications Server 2007 R2는 DNS 부하 분산을 고려 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="fbfb7-145">파트너에 지 서버는 풀에서 응답 하는 첫 번째에 지 서버와의 통신을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="fbfb7-146">해당에 지 서버에 오류가 발생 하면 통신이 자동으로 장애 조치 (failover) 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="fbfb7-147">일반적으로 선택한에 지 서버 또는 풀링된에 지 서버 계획에 대 한 인증서를 계획 하는 과정을 통해 인증서 요구 사항을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbfb7-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fbfb7-148">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="fbfb7-148">In This Section</span></span>

  - [<span data-ttu-id="fbfb7-149">인증서 요약-Lync Server 2013의 SIP, XMPP 페더레이션 및 공용 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="fbfb7-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="fbfb7-150">포트 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공용 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="fbfb7-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="fbfb7-151">DNS 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공용 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="fbfb7-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fbfb7-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbfb7-152">See Also</span></span>


[<span data-ttu-id="fbfb7-153">Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="fbfb7-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="fbfb7-154">Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="fbfb7-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="fbfb7-155">Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="fbfb7-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="fbfb7-156">Lync Server 2013에 대 한 DNS 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="fbfb7-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="fbfb7-157">Lync Server 2013에서 조직에 대 한 액세스에 지 구성 관리</span><span class="sxs-lookup"><span data-stu-id="fbfb7-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="fbfb7-158">Lync Server 2013에서 조직에 대 한 SIP 페더레이션 도메인 관리</span><span class="sxs-lookup"><span data-stu-id="fbfb7-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="fbfb7-159">Lync Server 2013에서 조직에 대 한 SIP 페더레이션 공급자 관리</span><span class="sxs-lookup"><span data-stu-id="fbfb7-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

