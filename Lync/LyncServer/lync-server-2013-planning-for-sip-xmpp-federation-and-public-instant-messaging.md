---
title: SIP, XMPP 페더레이션 및 공용 인스턴트 메시징 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f213b584d62a9a40810de2a05676b6d0737258e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513465"
---
# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="0cdd9-102">Lync Server 2013에서 SIP, XMPP 페더레이션 및 공용 인스턴트 메시징 계획</span><span class="sxs-lookup"><span data-stu-id="0cdd9-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cdd9-103">_**마지막으로 수정 된 항목:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="0cdd9-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="0cdd9-104">내부 및 외부 사용자가 파트너 조직이 나 서비스에서 연락처에 액세스할 수 있도록에 지 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="0cdd9-105">페더레이션이라고도 하는 이러한 파트너 계약은 다음 기능 중 하나 또는 모든 기능을 파트너 페더레이션에 포함된 사용자 조직 내의 연락처 또는 사용자에 대한 파트너 페더레이션 내의 연락처에게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="0cdd9-106">인스턴트 메시징 및 현재 상태</span><span class="sxs-lookup"><span data-stu-id="0cdd9-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="0cdd9-107">공동 작업 및 회의(예: 웹 회의)</span><span class="sxs-lookup"><span data-stu-id="0cdd9-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="0cdd9-108">오디오 회의나 비디오 회의 중 하나 또는 둘 다</span><span class="sxs-lookup"><span data-stu-id="0cdd9-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="0cdd9-109">경우에 따라 Microsoft Lync Server 2013와 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 연락처 사이의 IM (인스턴트 메시징) 및 현재 상태 간 통신은 피어 투 피어 전용 이며 페더레이션 파트너의 대화 상대와만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="0cdd9-110">Lync server와 같은 lync server 2010 lync server 2013 페더레이션에 연결 하는 다른 경우에는 여러 참가자가 대화에 참가 하도록 초대를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="0cdd9-111">Lync Server 및 Office Communications Server 페더레이션</span><span class="sxs-lookup"><span data-stu-id="0cdd9-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="0cdd9-112">Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server 간의 페더레이션에서는 피어-투-피어 및 멀티 당사자 통신을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="0cdd9-113">피어 투 피어 대화는 단체 대화로 확대되어 임시 모임을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="0cdd9-114">웹 회의 또는 오디오/비디오 회의 같은 모임은 페더레이션 파트너의 대화 상대뿐 아니라 조직 내 대화 상대를 포함하도록 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="0cdd9-115">페더레이션은 Microsoft Office Live Communications Server 2005에 처음 표시 되며 한 종류의 페더레이션 (직접 페더레이션)을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="0cdd9-116">직접 페더레이션에서는 페더레이션 파트너의 SIP (세션 시작 프로토콜) 도메인과 파트너에 지 서버의 FQDN (정규화 된 도메인 이름)을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="0cdd9-117">Live Communications Server 2005 SP1에는 추가 페더레이션 유형이 도입 되었으며, 모든 필수 DNS (domain name system) SRV 레코드를 페더레이션 파트너가 해당에 지 서버를 찾기 위해 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="0cdd9-118">해당 릴리스에 사용되는 용어는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="0cdd9-119">*확장 페더레이션 열기*: 모든 SIP 도메인 이름을 수락 하 고 DNS SRV를 사용 하 여 파트너에 지 서버를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="0cdd9-120">*확장 페더레이션*: 파트너의 SIP 도메인 이름을 조직의 페더레이션 파트너로 구성 하 고 DNS SRV를 사용 하 여 파트너에 지 서버를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="0cdd9-121">*직접 페더레이션*: 파트너의 SIP 도메인 이름과 FQDN을 파트너의에 지 서버에 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="0cdd9-122">*서버 허용 목록*: 모든 도메인을 수락 하 고, DNS SRV를 사용 하 여 호스팅 공급자 또는 공용 IM (인스턴트 메시징) 연결 공급자의에 지 서버를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="0cdd9-123">Microsoft Office Communications Server 2007에서는 실제로 수행 되는 각 페더레이션 유형에 대해 보다 효율적으로 정의할 수 있도록 페더레이션 유형에 대 한 명명 된 이름이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="0cdd9-124">개방형 확장 페더레이션은 *검색된 파트너 도메인*으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="0cdd9-125">확장 페더레이션은 *허용된 파트너 도메인*으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="0cdd9-126">직접 페더레이션은 *허용된 파트너 서버*로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="0cdd9-127">서버 허용 목록은 *호스팅 공급자* 및 *공용 메신저 공급자*로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="0cdd9-128">Microsoft Lync Server 2010에서는 Microsoft Lync Online 2010 및 Microsoft Office 365에 따라 호스팅 공급자가 보다 제한적으로 정의 되었으며, 허용 되는 파트너 도메인 페더레이션 유형에 서 정의 된 것과 동일한 허용 목록을 적용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="0cdd9-129">Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server 간 페더레이션을 사용 하도록 설정에서는에 지 서버 및 역방향 프록시를 사용 하 여 사용자가 정의한 규칙과 허용 되는 파트너 도메인을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="0cdd9-130">계획 측면에서 다른 Lync Server와 페더레이션-Office Communications Server에는 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="0cdd9-131">토폴로지 작성기에서 페더레이션을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="0cdd9-132">자세한 내용은 [Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공용 인스턴트 메시징 구성](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)에 대 한 배포 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="0cdd9-133">페더레이션 도메인 검색에 필요한 요구 사항을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="0cdd9-134">페더레이션 수동 구성을 사용 하려면 Lync Server 제어판, **페더레이션 및 외부 액세스**, **SIP 페더레이션 도메인**에 입력 된 파트너에 지 서버 및 도메인 이름 또는 온라인 도메인 이름의 FQDN (정규화 된 도메인 이름)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="0cdd9-135">FQDN으로 도메인을 허용하거나 차단하려면 **새로 만들기**로 정책을 새로 만들거나 **편집**으로 기존 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="0cdd9-136">페더레이션 파트너의에 지 서버를 수동으로 구성 하면 파트너가 해당에 지 서버의 IP 주소를 변경 하는 경우 오류가 발생할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="0cdd9-137"><STRONG>새 SIP 페더레이션 도메인</STRONG>의 경우 Microsoft Lync Online 및 microsoft 365 또는 Office 365의 <STRONG>도메인 이름 (또는 FQDN)</STRONG> 을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online and Microsoft 365 or Office 365.</span></span> <span data-ttu-id="0cdd9-138">Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server의 경우에는 <STRONG>FQDN (액세스에 지 서비스)</STRONG> 도 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="0cdd9-139">파트너가에 지 서버를 검색할 수 있는 검색 된 파트너 페더레이션에 대해 외부 DNS-sipfederationtls에 SRV 레코드를 만듭니다 \_ . \_ tcp.contoso.com –에 지 서버에 대 한 포트 5061 및 호스트 (A) 레코드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="0cdd9-140">Windows Phone 또는 Apple iPhone, iPad 또는 기타 Apple 장치에서 Microsoft Lync 모바일 클라이언트를 지원 하 고 푸시 알림 서비스 또는 푸시 알림 서비스를 사용 하는 경우에는 _sipfederationtls에 대 한 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="0cdd9-141">&lt;&gt;Lync Mobile 클라이언트를 가진 각 sip 도메인에 대 한 SIP 도메인 SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="0cdd9-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="0cdd9-142">Android 및 Nokia Symbian Lync Mobile에서는 푸시 알림을 사용 하지 않으며,이 요구 사항이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="0cdd9-143">페더레이션 도메인을 지원하도록 외부 사용자 액세스 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="0cdd9-144">사용하는 대화 상대 또는 페더레이션을 수용할 수 있도록 SIP(Session Initiation Protocol), 웹 회의 및 오디오/비디오용 방화벽 포트를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="0cdd9-145">자세한 내용은: [External A/V 방화벽 및 포트 요구 사항 확인에서 Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="0cdd9-146">다음 정보는 Microsoft Lync Server 2013 및 Lync Server 2010와의 페더레이션에 대 한 인증서, 포트/프로토콜 및 DNS 요구 사항을 정의 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="0cdd9-147">인증서, 방화벽 및 포트/프로토콜 요구 사항에 대 한 계획은 일반적으로 Microsoft Lync Server 2013에 지 서버를 계획 하거나 배포한 경우의 직선 전달 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="0cdd9-148">페더레이션은 기존에 지 서버를 사용 하는 추가 기능이 기 때문에, 계획 요구 사항은 일반적으로에 지 서버 계획 및 배포에 의해 충족 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="0cdd9-149">다음 표를 참조하여 현재 요구 사항이 충족되는지, 표에 따라 포트/프로토콜 및 DNS를 변경해야 하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="0cdd9-150">에 지 서버 풀이 있고 Lync Server 2013 또는 Lync Server 2010 파트너와 페더레이션 중인 경우에는에 지 서버의 내부 및 외부 측면에서 DNS 부하 분산 또는 하드웨어 부하 분산 장치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="0cdd9-151">Office Communications Server 2007 또는 Office Communications Server 2007 r 2와 페더레이션 하는 경우 하드웨어 부하 분산은에 지 서버의 경우 장애 조치 (failover) 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="0cdd9-152">Office Communications Server 2007 및 Office Communications Server 2007 R2는 DNS 부하 분산을 고려 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="0cdd9-153">파트너에 지 서버는 풀에서 응답 하는 첫 번째에 지 서버와의 통신을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="0cdd9-154">해당에 지 서버에 오류가 발생 하면 통신이 자동으로 장애 조치 (failover) 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="0cdd9-155">일반적으로 선택한에 지 서버 또는 풀링된에 지 서버 계획에 대 한 인증서를 계획 하는 과정을 통해 인증서 요구 사항을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="0cdd9-156">공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="0cdd9-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="0cdd9-157">공용 인스턴트 메시징 연결은 페더레이션 클래스 이며 내부 및 외부 Lync Server 2013 사용자가 다음 중 하나에서 연락처를 추가할 수 있도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="0cdd9-158">메신저 대화 상대</span><span class="sxs-lookup"><span data-stu-id="0cdd9-158">Messenger contacts</span></span>

  - <span data-ttu-id="0cdd9-159">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="0cdd9-159">Yahoo\!</span></span> <span data-ttu-id="0cdd9-160">연락처만</span><span class="sxs-lookup"><span data-stu-id="0cdd9-160">contacts</span></span>

  - <span data-ttu-id="0cdd9-161">북아메리카 온라인 (AOL) 연락처</span><span class="sxs-lookup"><span data-stu-id="0cdd9-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="0cdd9-162">2012 년 9 월 1 일부 터 신규 또는 갱신 계약에 대 한 Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 (PIC USL)를 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="0cdd9-163">활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="0cdd9-164">서비스 종료 날짜까지 (정확한 날짜는 계속 결정 되지만 6 월 2013 일 보다 일찍) Messenger.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="0cdd9-165">PIC USL은 Lync Server 또는 Office Communications Server가 Yahoo!과 페더레이션 하는 데 필요한 사용자별 구독 라이선스 (매달)입니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="0cdd9-166">메신저로.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-166">Messenger.</span></span> <span data-ttu-id="0cdd9-167">이 서비스를 제공 하는 Microsoft의 기능은 갱신 되지 않을 기본 규약 인 Yahoo!을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="0cdd9-168">이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="0cdd9-169">Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="0cdd9-170">Lync 사용자가 IM 및 음성을 통해 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="0cdd9-171">이 페더레이션 클래스를 사용 하려면 다음과 같은 계획 고려 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="0cdd9-172">Windows Live Messenger 사용자는 인스턴트 메시징과 함께 Lync Server 2013 사용자와 피어 투 피어 오디오/시각적 통신을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="0cdd9-173">에 지 서버는 특정 포트 및 프로토콜 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="0cdd9-174">자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="0cdd9-175">Yahoo 인스턴트 메시징의 경우에는 페더레이션을 제공 하는 일반에 지 서버를 계획 및 배포 하는 데 주로 사용 되는 것과는 다른 고유한 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="0cdd9-176">아메리카 온라인에서 액세스에 지 서비스에 할당 된에 지 서버 인증서에는 클라이언트 EKU (확장 된 키 사용)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="0cdd9-177">XMPP (Extensible Messaging and 거점 Protocol) 페더레이션</span><span class="sxs-lookup"><span data-stu-id="0cdd9-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="0cdd9-178">이전 버전의 Lync Server 및 Office Communications Server에서는 XMPP 배포와의 페더레이션을 허용 하기 위해 별도의 서버 역할로 배포할 수 있는 XMPP (extensible messaging and 거점 protocol) 게이트웨이를 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="0cdd9-179">Microsoft Lync Server 2013에서는 XMPP 기능을 기능으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="0cdd9-180">XMPP 기능은에 지 서버에서 실행 되는 XMPP 프록시 및 프런트 엔드 서버에서 실행 되는 XMPP 게이트웨이로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="0cdd9-181">XMPP의 배포 및 구성은 [Lync Server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 에서 설명 하며, 방화벽에 포트 및 프로토콜 규칙을 정의 하 고, 인증서를 구성 하 고, DNS 레코드를 추가 하 여 조직에서 xmpp를 지원 하기 위한 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="0cdd9-182">이 섹션의 다음 항목에서는 배포에 대해 XMPP 페더레이션을 계획 하는 데 필요한 정보를 요약 하 여 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="0cdd9-183">Lync Server 2013의 XMPP 기능은 Google 대화를 사용한 인스턴트 메시징 페더레이션을 위해 Microsoft에서 테스트 하 고 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-183">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="0cdd9-184">다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션과 모든 배포 또는 문제 해결 권장 사항을 지원 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-184">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="0cdd9-185">XMPP 페더레이션은 sba (survivable branch 기기에 있는 사용자에 대해서는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="0cdd9-186">이는 현재 상태 정보를 확인 하 고 IM 메시지를 교환 하는 방법에 모두 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="0cdd9-187">다음 항목에는 지원 되는 페더레이션 시나리오 유형에 대해 인증서, 방화벽 포트 및 DNS 항목을 정의 하기 위한 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cdd9-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="0cdd9-188">인증서 요약-Lync Server 2013의 SIP, XMPP 페더레이션 및 공용 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="0cdd9-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="0cdd9-189">포트 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공용 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="0cdd9-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="0cdd9-190">DNS 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공용 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="0cdd9-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0cdd9-191">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0cdd9-191">See Also</span></span>


[<span data-ttu-id="0cdd9-192">Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성</span><span class="sxs-lookup"><span data-stu-id="0cdd9-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="0cdd9-193">Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오</span><span class="sxs-lookup"><span data-stu-id="0cdd9-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="0cdd9-194">Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="0cdd9-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="0cdd9-195">Lync Server 2013에 대 한 DNS 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="0cdd9-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="0cdd9-196">Lync Server 2013에서 조직에 대 한 액세스에 지 구성 관리</span><span class="sxs-lookup"><span data-stu-id="0cdd9-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="0cdd9-197">Lync Server 2013에서 조직에 대 한 SIP 페더레이션 도메인 관리</span><span class="sxs-lookup"><span data-stu-id="0cdd9-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="0cdd9-198">Lync Server 2013에서 조직에 대 한 SIP 페더레이션 공급자 관리</span><span class="sxs-lookup"><span data-stu-id="0cdd9-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

