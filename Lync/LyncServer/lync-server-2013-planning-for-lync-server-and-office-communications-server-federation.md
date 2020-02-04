---
title: Lync Server 및 Office Communications Server federation 계획
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
ms.openlocfilehash: 015f824ff2b8510559a7bd4910be76321d44d242
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="3641d-102">Lync Server 2013 및 Office Communications Server federation에 대 한 계획</span><span class="sxs-lookup"><span data-stu-id="3641d-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3641d-103">_**마지막으로 수정한 주제:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="3641d-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="3641d-104">Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server 간 페더레이션은 피어 투 피어 및 멀티 파티 통신을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="3641d-105">피어 투 피어 대화를 여러 파티 대화로 에스컬레이션 하 여 임시 모임을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="3641d-106">모임 – 웹 회의 또는 오디오/시각적 회의-조직 내부의 연락처 및 페더레이션 하는 파트너의 연락처를 포함 하도록 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="3641d-107">페더레이션이 먼저 Microsoft Office Live Communications Server 2005에 표시 되며 한 종류의 페더레이션 (직접 페더레이션)이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="3641d-108">직접 페더레이션에서는 페더레이션 파트너의 SIP (세션 초기화 프로토콜) 도메인과 파트너의 Edge 서버에 대 한 FQDN (정규화 된 도메인 이름)을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="3641d-109">실시간 통신 서버 2005에는 해당 Edge 서버를 찾기 위해 페더레이션 파트너가 게시 하는 필수 DNS (domain name system) SRV 레코드가 추가 페더레이션 유형이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="3641d-110">해당 릴리스의 용어는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="3641d-111">*확장 페더레이션 열기*: 모든 SIP 도메인 이름 수락 및 DNS SRV를 사용 하 여 파트너에 지 서버 찾기</span><span class="sxs-lookup"><span data-stu-id="3641d-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="3641d-112">*확장 페더레이션*: 파트너의 SIP 도메인 이름을 조직의 페더레이션 파트너로 구성 하 고 DNS SRV를 사용 하 여 파트너에 지 서버를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="3641d-113">*직접 페더레이션*: 파트너의 SIP 도메인 이름 및 FQDN을 파트너의 Edge 서버로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="3641d-114">*서버 허용 목록*: 모든 도메인 허용, DNS SRV를 사용 하 여 호스팅 공급자 또는 공용 인스턴트 메시징 (IM) 연결 공급자의 Edge 서버 찾기</span><span class="sxs-lookup"><span data-stu-id="3641d-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="3641d-115">Microsoft Office 통신 서버 2007은 페더레이션 형식에 대 한 명명 된 이름을 업데이트 하 여 각 페더레이션 형식이 실제로 수행 하는 항목을 더 잘 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="3641d-116">개방형 확장 페더레이션이 검색 된 *파트너 도메인* 이라고 함</span><span class="sxs-lookup"><span data-stu-id="3641d-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="3641d-117">확장 페더레이션이 허용 된 *파트너 도메인* 이라고 함</span><span class="sxs-lookup"><span data-stu-id="3641d-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="3641d-118">직접 페더레이션이 허용 된 *파트너 서버* 라고 됨</span><span class="sxs-lookup"><span data-stu-id="3641d-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="3641d-119">서버 허용 목록을 *호스팅 공급자* 및 *공용 IM 공급자* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="3641d-120">Microsoft Lync Server 2010는 Microsoft Lync Online 2010 및 Microsoft Office 365에 따라 호스팅 공급자의 좁은 정의를 도입 했으며, 허용 된 파트너 도메인 페더레이션 유형에 의해 정의 된 것과 동일한 허용 목록을 적용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="3641d-121">Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server 간 페더레이션을 사용 하도록 설정 하는 경우 Edge 서버 및 역방향 프록시를 사용 하 여 사용자가 정의한 규칙과 허용 된 파트너 도메인을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="3641d-122">다른 Lync Server와 페더레이션 하는 계획의 관점에서 Office Communications Server에는 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="3641d-123">토폴로지 작성기에서 페더레이션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="3641d-124">자세한 내용은 [Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공개 인스턴트 메시지 구성](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)배포 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3641d-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="3641d-125">페더레이션 도메인 검색에 대 한 요구 사항 결정:</span><span class="sxs-lookup"><span data-stu-id="3641d-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="3641d-126">페더레이션을 수동으로 구성 하려면 파트너의 Edge 서버 및 도메인 이름에 대 한 FQDN (정규화 된 도메인 이름)과 Lync Server 제어판, **페더레이션 및 외부 액세스**, **SIP 페더레이션 도메인**에 입력 한 온라인 도메인 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="3641d-127">**새** 정책을 만들거나 기존 정책을 **편집** 하 여 도메인을 FQDN으로 허용 하거나 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="3641d-128">페더레이션 파트너의 Edge 서버의 수동 구성은 파트너가 해당 Edge 서버의 IP 주소를 변경 하는 경우 오류가 발생 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="3641d-129"><STRONG>새로운 SIP 페더레이션 도메인</STRONG>의 경우 Microsoft Lync Online, microsoft Office 365에 대 한 <STRONG>도메인 이름 (FQDN)</STRONG> 을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="3641d-130">Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server의 경우에도 액세스에 <STRONG>지 서비스 (FQDN)</STRONG> 를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="3641d-131">파트너가 Edge 서버를 검색할 수 있는 검색 된 파트너 페더레이션의 경우 외부 DNS- \_SIPFEDERATIONTLS에 SRV 레코드를 만듭니다. \_tcp.contoso.com – 포트 5061 및 Edge 서버의 호스트 (A) 레코드를 가리키는 위치</span><span class="sxs-lookup"><span data-stu-id="3641d-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="3641d-132">Windows Phone 또는 Apple iPhone, iPad 또는 기타 Apple 장치에서 Microsoft Lync 모바일 클라이언트를 지원 하며 푸시 알림 서비스 또는 푸시 알림 서비스를 사용 하는 경우에는 _sipfederationtls에 대 한 계획을 세워야 합니다 _tcp.</span><span class="sxs-lookup"><span data-stu-id="3641d-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="3641d-133">&lt;Lync 모바일&gt; 클라이언트를 사용 하는 각 sip 도메인에 대 한 sip 도메인 SRV 레코드.</span><span class="sxs-lookup"><span data-stu-id="3641d-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="3641d-134">Android 및 Nokia Symbian Lync Mobile은 푸시 알림을 사용 하지 않으며이 요구 사항이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="3641d-135">페더레이션 도메인을 지원 하도록 외부 사용자 액세스 정책 구성</span><span class="sxs-lookup"><span data-stu-id="3641d-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="3641d-136">SIP (세션 시작 프로토콜), 웹 회의 및 오디오/시각적에 대 한 방화벽 포트를 열어 활성화 하려는 페더레이션 또는 대화 상대를 수용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="3641d-137">자세한 내용은 다음을 참조 하세요. [Lync Server 2013의 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="3641d-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="3641d-138">다음 정보는 Microsoft Lync Server 2013 및 Lync Server 2010의 페더레이션에 대 한 인증서, 포트/프로토콜 및 DNS 요구 사항을 정의 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="3641d-139">Microsoft Lync Server 2013 Edge 서버를 계획 하거나 배포한 경우 인증서, 방화벽, 포트/프로토콜 요구 사항 및 DNS 요구 사항에 대 한 계획은 일반적으로 직선 전달 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="3641d-140">페더레이션은 기존 Edge 서버를 사용 하는 추가 기능이 기 때문에 Edge 서버 계획 및 배포에 의해 일반적으로 계획 요구 사항이 충족 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="3641d-141">다음 표를 사용 하 여 요구 사항이 충족 되는지 확인 하 고 포트/프로토콜 및 DNS에서 적절 하 게 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3641d-142">Edge 서버 풀이 있고 Lync Server 2013 또는 Lync Server 2010 파트너와 페더레이션 하는 경우에는 Edge 서버의 내부 및 외부 측면에서 DNS 부하 분산 또는 하드웨어 부하 분산 장치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="3641d-143">Office Communications Server 2007 또는 Office Communications Server 2007 R2에 페더레이션 하는 경우 하드웨어 로드 균형 조정은 Edge 서버의 이벤트에 장애 조치 (failover) 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="3641d-144">Office Communications Server 2007 및 Office Communications Server 2007 R2는 DNS 부하 분산을 인식 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="3641d-145">파트너에 지 서버는 풀에서 응답 하는 첫 번째 Edge 서버와 통신을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="3641d-146">해당 Edge 서버에 장애가 발생 하면 통신은 자동으로 장애 조치 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="3641d-147">일반적으로 인증서 요구 사항은 선택한 Edge 서버 또는 풀링된 Edge 서버 요금제의 인증서 계획을 통해 충족 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3641d-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3641d-148">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="3641d-148">In This Section</span></span>

  - [<span data-ttu-id="3641d-149">인증서 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공개 인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="3641d-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="3641d-150">포트 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공개 인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="3641d-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="3641d-151">DNS 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공개 인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="3641d-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3641d-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3641d-152">See Also</span></span>


[<span data-ttu-id="3641d-153">Lync Server 2013에서 페더레이션 사용자 액세스를 제어할 정책 구성</span><span class="sxs-lookup"><span data-stu-id="3641d-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="3641d-154">Lync Server 2013의 외부 사용자 액세스에 대한 시나리오</span><span class="sxs-lookup"><span data-stu-id="3641d-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="3641d-155">Lync Server 2013에 대한 외부 A/V 방화벽 및 포트 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="3641d-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="3641d-156">Lync Server 2013에 대한 DNS 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="3641d-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="3641d-157">Lync Server 2013에서 조직에 대한 액세스 에지 구성 관리</span><span class="sxs-lookup"><span data-stu-id="3641d-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="3641d-158">Lync Server 2013에서 조직의 SIP 페더레이션된 도메인 관리</span><span class="sxs-lookup"><span data-stu-id="3641d-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="3641d-159">Lync Server 2013에서 조직에 대한 SIP 페더레이션 공급자 관리</span><span class="sxs-lookup"><span data-stu-id="3641d-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

