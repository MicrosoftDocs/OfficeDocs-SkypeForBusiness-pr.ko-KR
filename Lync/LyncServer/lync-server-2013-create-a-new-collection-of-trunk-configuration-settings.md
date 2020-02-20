---
title: 'Lync Server 2013: 트렁크 구성 설정의 새 컬렉션 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07e5dc814887a7304a48602e04f48a00137bf8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="8b140-102">Lync Server 2013에서 새 트렁크 구성 설정 컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="8b140-102">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b140-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8b140-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8b140-p101">SIP 트렁크 구성 설정은 중재 서버 및 PSTN(공중 전화망) 게이트웨이, IP-PBX(Public Branch Exchange) 또는 서비스 공급자의 SBC(세션 경계 컨트롤러) 사이의 관계 및 기능을 정의합니다. 이러한 설정은 지정할 경우 다음과 같은 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="8b140-106">트렁크에 미디어 우회를 설정할지 여부</span><span class="sxs-lookup"><span data-stu-id="8b140-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="8b140-107">RTCP(Real-time Transport Control Protocol) 패킷이 전송되는 조건</span><span class="sxs-lookup"><span data-stu-id="8b140-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="8b140-108">SRTP(Secure Real-time Protocol) 암호화가 각 트렁크에 필요한지 여부</span><span class="sxs-lookup"><span data-stu-id="8b140-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="8b140-109">Microsoft Lync Server 2013을 설치 하면 SIP 트렁크 구성 설정의 전역 모음이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="8b140-110">또한 관리자가 사이트 범위 또는 서비스 범위(PSTN 게이트웨이 서비스 전용)에서 사용자 지정 설정 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="8b140-111">Lync Server 제어판을 사용 하 여 SIP 트렁크 구성 설정을 만들 때 사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-111">When creating SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b140-112">UI 설정</span><span class="sxs-lookup"><span data-stu-id="8b140-112">UI Setting</span></span></th>
<th><span data-ttu-id="8b140-113">PowerShell 매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b140-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="8b140-114">설명</span><span class="sxs-lookup"><span data-stu-id="8b140-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b140-115">이름</span><span class="sxs-lookup"><span data-stu-id="8b140-115">Name</span></span></p></td>
<td><p><span data-ttu-id="8b140-116">ID</span><span class="sxs-lookup"><span data-stu-id="8b140-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="8b140-p103">컬렉션에 대한 고유 식별자입니다. 이 속성은 읽기 전용이며 트렁크 구성 설정의 컬렉션에 대한 Identity를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b140-119">설명</span><span class="sxs-lookup"><span data-stu-id="8b140-119">Description</span></span></p></td>
<td><p><span data-ttu-id="8b140-120">설명</span><span class="sxs-lookup"><span data-stu-id="8b140-120">Description</span></span></p></td>
<td><p><span data-ttu-id="8b140-121">관리자가 설정에 대한 추가 정보를 저장할 수 있는 방법을 제공합니다(예: 트렁크 구성 용도).</span><span class="sxs-lookup"><span data-stu-id="8b140-121">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b140-122">지원되는 최대 초기 대화 상자</span><span class="sxs-lookup"><span data-stu-id="8b140-122">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="8b140-123">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="8b140-123">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="8b140-124">서비스 공급자의 PSTN 게이트웨이, IP-PBX 또는 SBC(세션 경계 컨트롤러)가 Invite로 수신하여 중재 서버로 보낼 수 있는 분기 응답의 최대 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-124">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b140-125">암호화 지원 수준</span><span class="sxs-lookup"><span data-stu-id="8b140-125">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="8b140-126">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="8b140-126">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="8b140-127">중재 서버와 서비스 공급자 쪽 PSTN 게이트웨이, IP-PBX 또는 SBC 간의 미디어 트래픽을 보호하는 지원 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-127">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="8b140-128">미디어 우회의 경우 이 값은 미디어 구성의 EncryptionLevel 설정과 호환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-128">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="8b140-129">미디어 구성은 <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">get-csmediaconfiguration</a> 및 <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">get-csmediaconfiguration</a> cmdlet을 사용 하 여 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-129">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="8b140-130">허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-130">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b140-131">필수: SRTP 암호화를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-131">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="8b140-132">선택: 게이트웨이가 지원하는 경우 SRTP가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-132">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="8b140-133">지원되지 않음: SRTP 암호화가 지원되지 않으므로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-133">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="8b140-p105">SRTPMode는 게이트웨이가 TLS(전송 계층 보안)를 사용하도록 구성된 경우에만 사용됩니다. 게이트웨이가 TCP(Transmission Control Protocol)를 전송 프로토콜로 사용하여 구성된 경우 SRTPMode는 내부적으로 지원되지 않음으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b140-136">참조 지원</span><span class="sxs-lookup"><span data-stu-id="8b140-136">Refer support</span></span></p></td>
<td><p><span data-ttu-id="8b140-137">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="8b140-137">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="8b140-138">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="8b140-138">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="8b140-139"><strong>게이트웨이에 대한 참조 전송 사용</strong>으로 설정된 경우 트렁크가 중재 서버에서 참조 요청 수신을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-139">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="8b140-140"><strong>타사 통화 제어를 사용하여 참조 사용</strong>으로 설정된 경우 3pcc 프로토콜을 사용해서 전송 통화가 호스팅된 사이트를 우회하도록 허용할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-140">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="8b140-141">3pcc는 타사 컨트롤이 라고도 &quot;하며,&quot; 타사를 사용 하 여 한 명 이상의 발신자를 연결할 때 발생 합니다 (예: 사용자 a에서 a로 B에 게 전화를 거는 운영자).</span><span class="sxs-lookup"><span data-stu-id="8b140-141">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b140-142">미디어 바이패스 사용</span><span class="sxs-lookup"><span data-stu-id="8b140-142">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="8b140-143">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="8b140-143">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="8b140-p107">이 트렁크에 대해 미디어 바이패스가 설정되었는지 여부를 나타냅니다. 미디어 바이패스는 <strong>중앙 집중식 미디어 처리</strong>가 설정된 경우에만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b140-146">중앙 집중식 미디어 처리</span><span class="sxs-lookup"><span data-stu-id="8b140-146">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="8b140-147">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="8b140-147">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="8b140-p108">알려진 미디어 종료 지점이 있는지 여부를 나타냅니다. 알려진 미디어 종료 지점의 예로는 미디어 종료가 신호 종료와 동일한 IP를 갖는 PSTN 게이트웨이를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b140-150">RTP 래칭 사용</span><span class="sxs-lookup"><span data-stu-id="8b140-150">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="8b140-151">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="8b140-151">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="8b140-p109">SIP 트렁크가 RTP 래칭을 지원하는지 여부를 나타냅니다. RTP 래칭은 NAT(네트워크 주소 변환기) 장치 또는 방화벽을 통해 RTP/RTCP 연결을 설정하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b140-154">통화 기록 전달 사용</span><span class="sxs-lookup"><span data-stu-id="8b140-154">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="8b140-155">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="8b140-155">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="8b140-156">트렁크를 통해 통화 기록 정보를 전달할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-156">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b140-157">P-Asserted-Identity 데이터 전달 사용</span><span class="sxs-lookup"><span data-stu-id="8b140-157">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="8b140-158">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="8b140-158">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="8b140-p110">통화와 함께 PAI(P-Asserted-Identity) 헤더를 전달할지 여부를 나타냅니다. PAI 헤더는 발신자의 ID를 확인하기 위한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b140-161">아웃바운드 라우팅 장애 조치(failover) 타이머 사용</span><span class="sxs-lookup"><span data-stu-id="8b140-161">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="8b140-162">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="8b140-162">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="8b140-p111">10초 내에 게이트웨이에서 응답되지 않은 아웃바운드 통화를 사용 가능한 다음 트렁크로 라우팅할지 여부를 나타냅니다. 추가 트렁크가 없으면 통화가 자동으로 삭제됩니다. 네트워크 및 게이트웨이 응답 속도가 느린 조직에서는 불필요하게 통화가 삭제될 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b140-165">연결된 PSTN 사용</span><span class="sxs-lookup"><span data-stu-id="8b140-165">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="8b140-166">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="8b140-166">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="8b140-167">트렁크에 지정된 PSTN 사용 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-167">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b140-168">테스트할 변환 번호</span><span class="sxs-lookup"><span data-stu-id="8b140-168">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="8b140-169">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8b140-169">N/A</span></span></p></td>
<td><p><span data-ttu-id="8b140-170">트렁크 구성 설정에 대한 임시 테스트를 수행하는 데 사용할 수 있는 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-170">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b140-171">연결된 변환 규칙</span><span class="sxs-lookup"><span data-stu-id="8b140-171">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="8b140-172">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="8b140-172">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="8b140-173">아웃바운드 라우팅에서 처리하는 통화(PBX 또는 PSTN 대상으로 라우팅되는 통화)에 적용되는 전화 번호 변환 규칙 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-173">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b140-174">호출된 번호 변환 규칙</span><span class="sxs-lookup"><span data-stu-id="8b140-174">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="8b140-175">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="8b140-175">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="8b140-176">트렁크에 지정된 아웃바운드 통화 번호 변환 규칙의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-176">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b140-177">테스트할 전화 번호</span><span class="sxs-lookup"><span data-stu-id="8b140-177">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="8b140-178">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8b140-178">N/A</span></span></p></td>
<td><p><span data-ttu-id="8b140-179">변환 규칙에 대한 임시 테스트를 수행하는 데 사용할 수 있는 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-179">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b140-180">호출 중인 번호</span><span class="sxs-lookup"><span data-stu-id="8b140-180">Calling number</span></span></p></td>
<td><p><span data-ttu-id="8b140-181">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8b140-181">N/A</span></span></p></td>
<td><p><span data-ttu-id="8b140-182">테스트할 전화 번호가 발신자의 전화 번호인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-182">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b140-183">호출된 번호</span><span class="sxs-lookup"><span data-stu-id="8b140-183">Called number</span></span></p></td>
<td><p><span data-ttu-id="8b140-184">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8b140-184">N/A</span></span></p></td>
<td><p><span data-ttu-id="8b140-185">테스트할 전화 번호가 수신 중인 사용자의 전화 번호인지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-185">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="8b140-186">Lync Server Get-cstrunkconfiguration cmdlet은 Lync Server 제어판에 표시 되지 않는 추가 속성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-186">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="8b140-187">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">get-cstrunkconfiguration</A> cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b140-187">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="8b140-188">Lync Server 제어판을 사용 하 여 새 트렁크 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="8b140-188">To create new trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8b140-189">Lync Server 제어판에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-189">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="8b140-190">**트렁크 구성** 탭에서 **새로 만들기**를 클릭하고 **사이트 트렁크**를 클릭하여 사이트 범위에서 새 설정을 만들거나 **풀 트렁크**를 클릭하여 서비스 범위에서 새 설정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-190">On the **Trunk Configuration** tab, click **New**, and then click **Site trunk** to create the new settings at the site scope, or **Pool trunk** to create the new settings at the service scope.</span></span>

3.  <span data-ttu-id="8b140-p113">**사이트 선택** 또는 **서비스 선택** 대화 상자(표시되는 대화 상자는 만들려는 설정이 사이트 범위 또는 서비스 범위 설정인지 여부에 따라 다름)에서 새 구성 설정의 위치를 선택하고 **확인**을 클릭합니다. 대화 상자가 비어 있으면 새 설정을 만들 수 있는 위치가 없음을 의미합니다. 예를 들어 **사이트 선택** 대화 상자가 비어 있으면 모든 사이트가 트렁크 구성 사이트의 컬렉션에 이미 지정되었음을 의미하고 각 사이트(및 각 서비스)가 그러한 컬렉션을 하나만 호스팅할 수 있음을 의미합니다. 이 경우 기존 컬렉션을 삭제하고 새 컬렉션을 만들거나 기존 컬렉션을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-p113">In the **Select a Site** or the **Select a Service** dialog box (the dialog box that appears will depend on whether you are creating site-scoped or service-scoped settings) select the location for the new configuration settings and then click **OK**. If the dialog box is blank, that means there is no place to create the new settings; for example, if the **Select a Site** dialog box is blank that means that all of your sites have already been assigned a collection of trunk configuration sites, and each site (and each service) can only host one such collection. In that case, you can either delete the existing collection and create a new collection, or simply modify the existing collection.</span></span>

4.  <span data-ttu-id="8b140-194">**새 트렁크 구성** 대화 상자에서 적합한 항목을 선택한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-194">In the **New Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

5.  <span data-ttu-id="8b140-p114">컬렉션의 **상태** 속성은 **커밋되지 않음**으로 업데이트됩니다. 변경 내용을 커밋하고 컬렉션을 삭제하려면 **커밋**을 클릭한 후 **모두 커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

6.  <span data-ttu-id="8b140-197">**커밋되지 않은 음성 구성 설정** 대화 상자에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="8b140-198">**Microsoft Lync Server 2013 제어판** 대화 상자에서 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8b140-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

