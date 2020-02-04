---
title: 'Lync Server 2013: 트렁크 구성 설정의 새 모음 만들기'
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
ms.openlocfilehash: dc29d75fc90156516751ad53712b53f4848ab5bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="73cd5-102">Lync Server 2013에서 새 트렁크 구성 설정 모음 만들기</span><span class="sxs-lookup"><span data-stu-id="73cd5-102">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73cd5-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="73cd5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="73cd5-104">SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="73cd5-105">이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="73cd5-106">Trunks에서 미디어 바이패스를 사용 해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="73cd5-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="73cd5-107">RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="73cd5-108">각 트렁크에서 보안 실시간 프로토콜 (SRTP) 암호화가 필요한 지 여부</span><span class="sxs-lookup"><span data-stu-id="73cd5-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="73cd5-109">Microsoft Lync Server 2013을 설치할 때 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="73cd5-110">또한 관리자는 사이트 범위 또는 서비스 범위 (PSTN 게이트웨이 서비스에만 해당)에서 사용자 지정 설정 모음을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="73cd5-111">Lync Server 제어판을 사용 하 여 SIP 트렁크 구성 설정을 만들 때 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-111">When creating SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73cd5-112">UI 설정</span><span class="sxs-lookup"><span data-stu-id="73cd5-112">UI Setting</span></span></th>
<th><span data-ttu-id="73cd5-113">PowerShell 매개 변수</span><span class="sxs-lookup"><span data-stu-id="73cd5-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="73cd5-114">설명</span><span class="sxs-lookup"><span data-stu-id="73cd5-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73cd5-115">이름</span><span class="sxs-lookup"><span data-stu-id="73cd5-115">Name</span></span></p></td>
<td><p><span data-ttu-id="73cd5-116">Identity</span><span class="sxs-lookup"><span data-stu-id="73cd5-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="73cd5-117">컬렉션의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-117">Unique identifier for the collection.</span></span> <span data-ttu-id="73cd5-118">이 속성은 읽기 전용입니다. 트렁크 구성 설정 모음의 Id는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-118">This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73cd5-119">설명</span><span class="sxs-lookup"><span data-stu-id="73cd5-119">Description</span></span></p></td>
<td><p><span data-ttu-id="73cd5-120">설명</span><span class="sxs-lookup"><span data-stu-id="73cd5-120">Description</span></span></p></td>
<td><p><span data-ttu-id="73cd5-121">관리자가 설정에 대 한 추가 정보 (예: 트렁크 구성의 용도)를 저장할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-121">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73cd5-122">지원 되는 최대 빠른 대화 상자</span><span class="sxs-lookup"><span data-stu-id="73cd5-122">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="73cd5-123">Maxlya 대화 상자</span><span class="sxs-lookup"><span data-stu-id="73cd5-123">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="73cd5-124">서비스 공급자의 PSTN 게이트웨이, IP PBX 또는 SBC가 조정 서버로 전송 된 초대에 받을 수 있는 분기 응답의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-124">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73cd5-125">암호화 지원 수준</span><span class="sxs-lookup"><span data-stu-id="73cd5-125">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="73cd5-126">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="73cd5-126">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="73cd5-127">서비스 공급자에서 중재 서버와 PSTN 게이트웨이, IP PBX 또는 SBC 간의 미디어 트래픽 보호에 대 한 지원 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-127">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="73cd5-128">미디어 우회의 경우 이 값은 미디어 구성의 EncryptionLevel 설정과 호환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-128">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="73cd5-129">미디어 구성은 <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> 및 <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">CsMediaConfiguration</a> cmdlet을 사용 하 여 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-129">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="73cd5-130">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-130">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="73cd5-131">필수: SRTP 암호화를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-131">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="73cd5-132">선택 사항: 게이트웨이에서 지 원하는 경우 SRTP가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-132">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="73cd5-133">지원 되지 않음: SRTP 암호화가 지원 되지 않으므로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-133">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="73cd5-134">SRTPMode는 게이트웨이가 TLS (전송 계층 보안)를 사용 하도록 구성 된 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-134">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS).</span></span> <span data-ttu-id="73cd5-135">게이트웨이가 TCP (전송 제어 프로토콜)를 전송으로 구성한 경우에는 SRTPMode가 내부적으로 지원 되지 않는 것으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-135">If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73cd5-136">지원 참조</span><span class="sxs-lookup"><span data-stu-id="73cd5-136">Refer support</span></span></p></td>
<td><p><span data-ttu-id="73cd5-137">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="73cd5-137">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="73cd5-138">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="73cd5-138">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="73cd5-139">보내기를 사용 하도록 설정 하는 경우 <strong>게이트웨이를 참조</strong>하는 경우 트렁크가 조정 서버의 수신 참조 요청을 지원함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-139">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="73cd5-140">이 기능을 사용 하도록 설정 하면 <strong>타사 통화 제어를 사용</strong>하는 것이 3pcc 프로토콜을 사용 하 여 호스팅된 사이트를 우회 하도록 할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-140">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="73cd5-141">3pcc는 타사 컨트롤이 라고도 &quot;&quot; 하며, 타사를 사용 하 여 한 쌍의 호출자를 연결 하는 경우 (예: A 사람에 게 a에 게 전화를 거는 운영자)에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-141">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73cd5-142">미디어 바이패스 사용</span><span class="sxs-lookup"><span data-stu-id="73cd5-142">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="73cd5-143">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="73cd5-143">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="73cd5-144">이 트렁크에 미디어 바이패스를 사용 하도록 설정 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-144">Indicates whether media bypass is enabled for this trunk.</span></span> <span data-ttu-id="73cd5-145">미디어 바이패스는 <strong>중앙 집중화 된 미디어 처리</strong> 도 사용할 수 있는 경우에만 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-145">Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73cd5-146">중앙 집중화 된 미디어 처리</span><span class="sxs-lookup"><span data-stu-id="73cd5-146">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="73cd5-147">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="73cd5-147">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="73cd5-148">잘 알려진 미디어 종료 지점이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-148">Indicates whether there is a well-known media termination point.</span></span> <span data-ttu-id="73cd5-149">알려진 미디어 종료 지점의 예로는 미디어 종료가 신호 종료의 IP와 동일한 PSTN 게이트웨이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-149">(An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73cd5-150">RTP latching 사용</span><span class="sxs-lookup"><span data-stu-id="73cd5-150">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="73cd5-151">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="73cd5-151">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="73cd5-152">SIP 트렁크가 RTP 래치를 지원하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-152">Indicates whether or not the SIP trunks support RTP latching.</span></span> <span data-ttu-id="73cd5-153">RTP 래치는 NAT(Network Address Translator) 장치 또는 방화벽을 통한 RTP/RTCP 연결을 설정하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-153">RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73cd5-154">착신 통화 기록 사용</span><span class="sxs-lookup"><span data-stu-id="73cd5-154">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="73cd5-155">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="73cd5-155">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="73cd5-156">트렁크를 통해 통화 기록 정보를 전달할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-156">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73cd5-157">앞으로 P-어설션된-Id 데이터 사용</span><span class="sxs-lookup"><span data-stu-id="73cd5-157">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="73cd5-158">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="73cd5-158">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="73cd5-159">PAI(P-Asserted-Identity) 헤더를 통화와 함께 전달할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-159">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="73cd5-160">PAI 헤더를 사용하면 발신자 번호를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-160">The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73cd5-161">아웃 바운드 라우팅 장애 조치 타이머 사용</span><span class="sxs-lookup"><span data-stu-id="73cd5-161">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="73cd5-162">Enablefailovertimer</span><span class="sxs-lookup"><span data-stu-id="73cd5-162">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="73cd5-163">게이트웨이에서 응답 하지 않은 아웃 바운드 통화가 10 초 이내에 사용 가능한 다음 트렁크로 라우팅되도록 할지 여부를 표시 합니다. 추가 trunks 없으면 통화가 자동으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-163">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped.</span></span> <span data-ttu-id="73cd5-164">느린 네트워크 및 게이트웨이 응답을 사용 하는 조직에서 호출이 불필요 하 게 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-164">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73cd5-165">연결 된 PSTN 용도</span><span class="sxs-lookup"><span data-stu-id="73cd5-165">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="73cd5-166">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="73cd5-166">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="73cd5-167">트렁크에 할당된 PSTN 사용 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-167">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73cd5-168">테스트를 위해 번역 된 번호</span><span class="sxs-lookup"><span data-stu-id="73cd5-168">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="73cd5-169">해당 없음</span><span class="sxs-lookup"><span data-stu-id="73cd5-169">N/A</span></span></p></td>
<td><p><span data-ttu-id="73cd5-170">트렁크 구성 설정의 임시 테스트를 수행 하는 데 사용할 수 있는 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-170">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73cd5-171">연결 된 번역 규칙</span><span class="sxs-lookup"><span data-stu-id="73cd5-171">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="73cd5-172">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="73cd5-172">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="73cd5-173">아웃 바운드 라우팅이 처리 하는 통화에 적용 되는 전화 번호 번역 규칙 (PBX 또는 PSTN 대상으로 라우팅된 통화)을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-173">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73cd5-174">전화 번호 번역 규칙</span><span class="sxs-lookup"><span data-stu-id="73cd5-174">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="73cd5-175">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="73cd5-175">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="73cd5-176">트렁크에 할당된 아웃바운드 호출 번호 변환 규칙 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-176">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73cd5-177">테스트할 전화 번호</span><span class="sxs-lookup"><span data-stu-id="73cd5-177">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="73cd5-178">해당 없음</span><span class="sxs-lookup"><span data-stu-id="73cd5-178">N/A</span></span></p></td>
<td><p><span data-ttu-id="73cd5-179">번역 규칙의 특별 테스트를 수행 하는 데 사용할 수 있는 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-179">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73cd5-180">전화 번호</span><span class="sxs-lookup"><span data-stu-id="73cd5-180">Calling number</span></span></p></td>
<td><p><span data-ttu-id="73cd5-181">해당 없음</span><span class="sxs-lookup"><span data-stu-id="73cd5-181">N/A</span></span></p></td>
<td><p><span data-ttu-id="73cd5-182">테스트 하려는 전화 번호가 발신자의 전화 번호 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-182">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73cd5-183">전화 번호</span><span class="sxs-lookup"><span data-stu-id="73cd5-183">Called number</span></span></p></td>
<td><p><span data-ttu-id="73cd5-184">해당 없음</span><span class="sxs-lookup"><span data-stu-id="73cd5-184">N/A</span></span></p></td>
<td><p><span data-ttu-id="73cd5-185">전화 번호가 통화 중인 사람의 전화 번호 라는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-185">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="73cd5-186">Lync Server Set-cstrunkconfiguration cmdlet은 Lync Server 제어판에 표시 되지 않는 추가 속성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-186">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="73cd5-187">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">새 set-cstrunkconfiguration</A> cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73cd5-187">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="73cd5-188">Lync Server 제어판을 사용 하 여 새 트렁크 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="73cd5-188">To create new trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="73cd5-189">Lync Server 제어판에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-189">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="73cd5-190">**트렁크 구성** 탭에서 **새로 만들기**를 클릭 한 다음 **사이트 트렁크** 를 클릭 하 여 사이트 범위에서 새 설정을 만들거나, **풀 트렁크** 에서 서비스 범위에 새 설정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-190">On the **Trunk Configuration** tab, click **New**, and then click **Site trunk** to create the new settings at the site scope, or **Pool trunk** to create the new settings at the service scope.</span></span>

3.  <span data-ttu-id="73cd5-191">**사이트 선택** 또는 **서비스 선택** 대화 상자 (표시 되는 대화 상자는 사이트 범위 또는 서비스 범위 설정을 만들지 여부에 따라 달라 짐) 새 구성 설정의 위치를 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-191">In the **Select a Site** or the **Select a Service** dialog box (the dialog box that appears will depend on whether you are creating site-scoped or service-scoped settings) select the location for the new configuration settings and then click **OK**.</span></span> <span data-ttu-id="73cd5-192">대화 상자가 비어 있으면 새 설정을 만들 수 있는 위치가 없다는 의미입니다. 예를 들어 **사이트 선택** 대화 상자가 비어 있는 경우 모든 사이트에서 이미 트렁크 구성 사이트 모음을 할당 했으며 각 사이트 (및 각 서비스)는 그러한 컬렉션을 하나만 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-192">If the dialog box is blank, that means there is no place to create the new settings; for example, if the **Select a Site** dialog box is blank that means that all of your sites have already been assigned a collection of trunk configuration sites, and each site (and each service) can only host one such collection.</span></span> <span data-ttu-id="73cd5-193">이러한 경우 기존 컬렉션을 삭제 하 고 새 컬렉션을 만들거나 기존 컬렉션을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-193">In that case, you can either delete the existing collection and create a new collection, or simply modify the existing collection.</span></span>

4.  <span data-ttu-id="73cd5-194">**새 트렁크 구성** 대화 상자에서 적절 하 게 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-194">In the **New Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

5.  <span data-ttu-id="73cd5-195">컬렉션에 대 한 State 속성이 **커밋되지**않은 **상태로** 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-195">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="73cd5-196">변경 내용을 커밋하고 컬렉션을 삭제 하려면 **커밋을** 클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-196">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

6.  <span data-ttu-id="73cd5-197">커밋되지 않은 **음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="73cd5-198">**Microsoft Lync Server 2013 제어판** 대화 상자에서 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="73cd5-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

