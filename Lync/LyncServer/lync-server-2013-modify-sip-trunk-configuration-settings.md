---
title: 'Lync Server 2013: SIP 트렁크 구성 설정 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5eb0d3d535a4ba5b3e8ffd9a9c712edd601fbbbc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="da66e-102">Lync Server 2013에서 SIP 트렁크 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="da66e-102">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da66e-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="da66e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="da66e-p101">SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다. 이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="da66e-106">트렁크에 미디어 우회를 설정할지 여부</span><span class="sxs-lookup"><span data-stu-id="da66e-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="da66e-107">RTCP(Real-time Transport Control Protocol) 패킷이 전송되는 조건</span><span class="sxs-lookup"><span data-stu-id="da66e-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="da66e-108">SRTP(Secure Real-time Protocol) 암호화가 각 트렁크에 필요한지 여부</span><span class="sxs-lookup"><span data-stu-id="da66e-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="da66e-109">Microsoft Lync Server 2013을 설치 하면 SIP 트렁크 구성 설정의 전역 모음이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="da66e-110">또한 관리자가 사이트 범위 또는 서비스 범위(PSTN 게이트웨이 서비스 전용)에서 사용자 지정 설정 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="da66e-111">나중에 Lync Server 제어판 또는 Windows PowerShell을 사용 하 여 이러한 컬렉션을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-111">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="da66e-112">Lync Server 제어판을 사용 하 여 SIP 트렁크 구성 설정을 수정할 때 사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-112">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da66e-113">UI 설정</span><span class="sxs-lookup"><span data-stu-id="da66e-113">UI Setting</span></span></th>
<th><span data-ttu-id="da66e-114">PowerShell 매개 변수</span><span class="sxs-lookup"><span data-stu-id="da66e-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="da66e-115">설명</span><span class="sxs-lookup"><span data-stu-id="da66e-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da66e-116">이름</span><span class="sxs-lookup"><span data-stu-id="da66e-116">Name</span></span></p></td>
<td><p><span data-ttu-id="da66e-117">ID</span><span class="sxs-lookup"><span data-stu-id="da66e-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="da66e-p103">컬렉션에 대한 고유 식별자입니다. 이 속성은 읽기 전용이며 트렁크 구성 설정의 컬렉션에 대한 Identity를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da66e-120">설명</span><span class="sxs-lookup"><span data-stu-id="da66e-120">Description</span></span></p></td>
<td><p><span data-ttu-id="da66e-121">설명</span><span class="sxs-lookup"><span data-stu-id="da66e-121">Description</span></span></p></td>
<td><p><span data-ttu-id="da66e-122">관리자가 설정에 대한 추가 정보를 저장할 수 있는 방법을 제공합니다(예: 트렁크 구성 용도).</span><span class="sxs-lookup"><span data-stu-id="da66e-122">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da66e-123">지원되는 최대 초기 대화 상자</span><span class="sxs-lookup"><span data-stu-id="da66e-123">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="da66e-124">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="da66e-124">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="da66e-125">서비스 공급자의 PSTN 게이트웨이, IP-PBX 또는 SBC(세션 경계 컨트롤러)가 Invite로 수신하여 중재 서버로 보낼 수 있는 분기 응답의 최대 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-125">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da66e-126">암호화 지원 수준</span><span class="sxs-lookup"><span data-stu-id="da66e-126">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="da66e-127">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="da66e-127">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="da66e-128">중재 서버와 서비스 공급자 쪽 PSTN 게이트웨이, IP-PBX 또는 SBC 간의 미디어 트래픽을 보호하는 지원 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-128">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="da66e-129">미디어 우회의 경우 이 값은 미디어 구성의 EncryptionLevel 설정과 호환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-129">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="da66e-130">미디어 구성은 <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">get-csmediaconfiguration</a> 및 <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">get-csmediaconfiguration</a> cmdlet을 사용 하 여 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-130">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="da66e-131">허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-131">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="da66e-132">필수: SRTP 암호화를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-132">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="da66e-133">선택: 게이트웨이가 지원하는 경우 SRTP가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-133">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="da66e-134">지원되지 않음: SRTP 암호화가 지원되지 않으므로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-134">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="da66e-p105">SRTPMode는 게이트웨이가 TLS(전송 계층 보안)를 사용하도록 구성된 경우에만 사용됩니다. 게이트웨이가 TCP(Transmission Control Protocol)를 전송 프로토콜로 사용하여 구성된 경우 SRTPMode는 내부적으로 지원되지 않음으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da66e-137">참조 지원</span><span class="sxs-lookup"><span data-stu-id="da66e-137">Refer support</span></span></p></td>
<td><p><span data-ttu-id="da66e-138">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="da66e-138">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="da66e-139">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="da66e-139">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="da66e-140"><strong>게이트웨이에 대한 참조 전송 사용</strong>으로 설정된 경우 트렁크가 중재 서버에서 참조 요청 수신을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-140">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="da66e-141"><strong>타사 통화 제어를 사용하여 참조 사용</strong>으로 설정된 경우 3pcc 프로토콜을 사용해서 전송 통화가 호스팅된 사이트를 우회하도록 허용할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-141">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="da66e-142">3pcc는 타사 컨트롤이 라고도 &quot;하며,&quot; 타사를 사용 하 여 한 명 이상의 발신자를 연결할 때 발생 합니다 (예: 사용자 a에서 a로 B에 게 전화를 거는 운영자).</span><span class="sxs-lookup"><span data-stu-id="da66e-142">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da66e-143">미디어 바이패스 사용</span><span class="sxs-lookup"><span data-stu-id="da66e-143">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="da66e-144">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="da66e-144">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="da66e-p107">이 트렁크에 대해 미디어 바이패스가 설정되었는지 여부를 나타냅니다. 미디어 바이패스는 <strong>중앙 집중식 미디어 처리</strong>가 설정된 경우에만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da66e-147">중앙 집중식 미디어 처리</span><span class="sxs-lookup"><span data-stu-id="da66e-147">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="da66e-148">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="da66e-148">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="da66e-p108">알려진 미디어 종료 지점이 있는지 여부를 나타냅니다. 알려진 미디어 종료 지점의 예로는 미디어 종료가 신호 종료와 동일한 IP를 갖는 PSTN 게이트웨이를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da66e-151">RTP 래칭 사용</span><span class="sxs-lookup"><span data-stu-id="da66e-151">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="da66e-152">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="da66e-152">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="da66e-p109">SIP 트렁크가 RTP 래칭을 지원하는지 여부를 나타냅니다. RTP 래칭은 NAT(네트워크 주소 변환기) 장치 또는 방화벽을 통해 RTP/RTCP 연결을 설정하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da66e-155">통화 기록 전달 사용</span><span class="sxs-lookup"><span data-stu-id="da66e-155">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="da66e-156">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="da66e-156">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="da66e-157">트렁크를 통해 통화 기록 정보를 전달할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-157">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da66e-158">P-Asserted-Identity 데이터 전달 사용</span><span class="sxs-lookup"><span data-stu-id="da66e-158">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="da66e-159">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="da66e-159">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="da66e-p110">통화와 함께 PAI(P-Asserted-Identity) 헤더를 전달할지 여부를 나타냅니다. PAI 헤더는 발신자의 ID를 확인하기 위한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da66e-162">아웃바운드 라우팅 장애 조치(failover) 타이머 사용</span><span class="sxs-lookup"><span data-stu-id="da66e-162">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="da66e-163">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="da66e-163">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="da66e-p111">10초 내에 게이트웨이에서 응답되지 않은 아웃바운드 통화를 사용 가능한 다음 트렁크로 라우팅할지 여부를 나타냅니다. 추가 트렁크가 없으면 통화가 자동으로 삭제됩니다. 네트워크 및 게이트웨이 응답 속도가 느린 조직에서는 불필요하게 통화가 삭제될 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da66e-166">연결된 PSTN 사용</span><span class="sxs-lookup"><span data-stu-id="da66e-166">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="da66e-167">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="da66e-167">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="da66e-168">트렁크에 지정된 PSTN 사용 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-168">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da66e-169">테스트할 변환 번호</span><span class="sxs-lookup"><span data-stu-id="da66e-169">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="da66e-170">해당 없음</span><span class="sxs-lookup"><span data-stu-id="da66e-170">N/A</span></span></p></td>
<td><p><span data-ttu-id="da66e-171">트렁크 구성 설정에 대한 임시 테스트를 수행하는 데 사용할 수 있는 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-171">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da66e-172">연결된 변환 규칙</span><span class="sxs-lookup"><span data-stu-id="da66e-172">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="da66e-173">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="da66e-173">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="da66e-174">아웃바운드 라우팅에서 처리하는 통화(PBX 또는 PSTN 대상으로 라우팅되는 통화)에 적용되는 전화 번호 변환 규칙 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-174">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da66e-175">호출된 번호 변환 규칙</span><span class="sxs-lookup"><span data-stu-id="da66e-175">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="da66e-176">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="da66e-176">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="da66e-177">트렁크에 지정된 아웃바운드 통화 번호 변환 규칙의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-177">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da66e-178">테스트할 전화 번호</span><span class="sxs-lookup"><span data-stu-id="da66e-178">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="da66e-179">해당 없음</span><span class="sxs-lookup"><span data-stu-id="da66e-179">N/A</span></span></p></td>
<td><p><span data-ttu-id="da66e-180">변환 규칙에 대한 임시 테스트를 수행하는 데 사용할 수 있는 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-180">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da66e-181">호출 중인 번호</span><span class="sxs-lookup"><span data-stu-id="da66e-181">Calling number</span></span></p></td>
<td><p><span data-ttu-id="da66e-182">해당 없음</span><span class="sxs-lookup"><span data-stu-id="da66e-182">N/A</span></span></p></td>
<td><p><span data-ttu-id="da66e-183">테스트할 전화 번호가 발신자의 전화 번호인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-183">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da66e-184">호출된 번호</span><span class="sxs-lookup"><span data-stu-id="da66e-184">Called number</span></span></p></td>
<td><p><span data-ttu-id="da66e-185">해당 없음</span><span class="sxs-lookup"><span data-stu-id="da66e-185">N/A</span></span></p></td>
<td><p><span data-ttu-id="da66e-186">테스트할 전화 번호가 수신 중인 사용자의 전화 번호인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-186">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="da66e-187">Lync Server Get-cstrunkconfiguration cmdlet은 Lync Server 제어판에 표시 되지 않는 추가 속성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-187">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="da66e-188">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">get-cstrunkconfiguration</A> cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="da66e-188">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="da66e-189">Lync Server 제어판을 사용 하 여 SIP 트렁크 구성 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="da66e-189">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="da66e-190">Lync Server 제어판에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-190">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="da66e-p113">**트렁크 구성** 탭에서 수정할 트렁크 구성 설정을 두 번 클릭합니다. 설정 컬렉션은 한 번에 하나만 편집할 수 있습니다. 여러 컬렉션에서 동일 항목을 변경하려면 Windows PowerShell을 대신 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="da66e-p113">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified. Note that you can only edit one collection of settings at a time. If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="da66e-194">**트렁크 구성 편집** 대화 상자에서 적절 한 항목을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-194">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="da66e-p114">컬렉션의 **상태** 속성은 **커밋되지 않음**으로 업데이트됩니다. 변경 내용을 커밋하고 컬렉션을 삭제하려면 **커밋**을 클릭한 후 **모두 커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="da66e-197">**커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="da66e-198">**Microsoft Lync Server 2013 제어판** 대화 상자에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da66e-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

