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
ms.openlocfilehash: 809f7a94a4ab211f1bf21483729519cd53de2a2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="fef4d-102">Lync Server 2013에서 SIP 트렁크 구성 설정 수정</span><span class="sxs-lookup"><span data-stu-id="fef4d-102">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fef4d-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="fef4d-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="fef4d-104">SIP 트렁크 구성 설정은 중재 서버와 PSTN (공개 통신 네트워크) 게이트웨이, IP-공용 분기 교환 (PBX) 또는 서비스 공급자의 SBC (세션 경계 컨트롤러) 간에 관계와 접근 권한 값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="fef4d-105">이러한 설정은 다음을 지정 하는 등의 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="fef4d-106">Trunks에서 미디어 바이패스를 사용 해야 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="fef4d-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="fef4d-107">RTCP (실시간 전송 제어 프로토콜) 패킷이 전송 되는 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="fef4d-108">각 트렁크에서 보안 실시간 프로토콜 (SRTP) 암호화가 필요한 지 여부</span><span class="sxs-lookup"><span data-stu-id="fef4d-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="fef4d-109">Microsoft Lync Server 2013을 설치할 때 SIP 트렁크 구성 설정의 전역 컬렉션이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="fef4d-110">또한 관리자는 사이트 범위 또는 서비스 범위 (PSTN 게이트웨이 서비스에만 해당)에서 사용자 지정 설정 모음을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="fef4d-111">나중에 Lync Server 제어판 또는 Windows PowerShell을 사용 하 여 이러한 컬렉션을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-111">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="fef4d-112">Lync Server 제어판을 사용 하 여 SIP 트렁크 구성 설정을 수정 하는 경우 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-112">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef4d-113">UI 설정</span><span class="sxs-lookup"><span data-stu-id="fef4d-113">UI Setting</span></span></th>
<th><span data-ttu-id="fef4d-114">PowerShell 매개 변수</span><span class="sxs-lookup"><span data-stu-id="fef4d-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="fef4d-115">설명</span><span class="sxs-lookup"><span data-stu-id="fef4d-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef4d-116">이름</span><span class="sxs-lookup"><span data-stu-id="fef4d-116">Name</span></span></p></td>
<td><p><span data-ttu-id="fef4d-117">Identity</span><span class="sxs-lookup"><span data-stu-id="fef4d-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="fef4d-118">컬렉션의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-118">Unique identifier for the collection.</span></span> <span data-ttu-id="fef4d-119">이 속성은 읽기 전용입니다. 트렁크 구성 설정 모음의 Id는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-119">This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef4d-120">설명</span><span class="sxs-lookup"><span data-stu-id="fef4d-120">Description</span></span></p></td>
<td><p><span data-ttu-id="fef4d-121">설명</span><span class="sxs-lookup"><span data-stu-id="fef4d-121">Description</span></span></p></td>
<td><p><span data-ttu-id="fef4d-122">관리자가 설정에 대 한 추가 정보 (예: 트렁크 구성의 용도)를 저장할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-122">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef4d-123">지원 되는 최대 빠른 대화 상자</span><span class="sxs-lookup"><span data-stu-id="fef4d-123">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="fef4d-124">Maxlya 대화 상자</span><span class="sxs-lookup"><span data-stu-id="fef4d-124">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="fef4d-125">서비스 공급자의 PSTN 게이트웨이, IP PBX 또는 SBC가 조정 서버로 전송 된 초대에 받을 수 있는 분기 응답의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-125">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef4d-126">암호화 지원 수준</span><span class="sxs-lookup"><span data-stu-id="fef4d-126">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="fef4d-127">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="fef4d-127">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="fef4d-128">서비스 공급자에서 중재 서버와 PSTN 게이트웨이, IP PBX 또는 SBC 간의 미디어 트래픽 보호에 대 한 지원 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-128">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="fef4d-129">미디어 우회의 경우 이 값은 미디어 구성의 EncryptionLevel 설정과 호환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-129">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="fef4d-130">미디어 구성은 <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> 및 <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">CsMediaConfiguration</a> cmdlet을 사용 하 여 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-130">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="fef4d-131">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-131">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="fef4d-132">필수: SRTP 암호화를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-132">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="fef4d-133">선택 사항: 게이트웨이에서 지 원하는 경우 SRTP가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-133">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="fef4d-134">지원 되지 않음: SRTP 암호화가 지원 되지 않으므로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-134">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="fef4d-135">SRTPMode는 게이트웨이가 TLS (전송 계층 보안)를 사용 하도록 구성 된 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-135">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS).</span></span> <span data-ttu-id="fef4d-136">게이트웨이가 TCP (전송 제어 프로토콜)를 전송으로 구성한 경우에는 SRTPMode가 내부적으로 지원 되지 않는 것으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-136">If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef4d-137">지원 참조</span><span class="sxs-lookup"><span data-stu-id="fef4d-137">Refer support</span></span></p></td>
<td><p><span data-ttu-id="fef4d-138">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="fef4d-138">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="fef4d-139">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="fef4d-139">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="fef4d-140">보내기를 사용 하도록 설정 하는 경우 <strong>게이트웨이를 참조</strong>하는 경우 트렁크가 조정 서버의 수신 참조 요청을 지원함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-140">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="fef4d-141">이 기능을 사용 하도록 설정 하면 <strong>타사 통화 제어를 사용</strong>하는 것이 3pcc 프로토콜을 사용 하 여 호스팅된 사이트를 우회 하도록 할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-141">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="fef4d-142">3pcc는 타사 컨트롤이 라고도 &quot;&quot; 하며, 타사를 사용 하 여 한 쌍의 호출자를 연결 하는 경우 (예: A 사람에 게 a에 게 전화를 거는 운영자)에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-142">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef4d-143">미디어 바이패스 사용</span><span class="sxs-lookup"><span data-stu-id="fef4d-143">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="fef4d-144">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="fef4d-144">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="fef4d-145">이 트렁크에 미디어 바이패스를 사용 하도록 설정 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-145">Indicates whether media bypass is enabled for this trunk.</span></span> <span data-ttu-id="fef4d-146">미디어 바이패스는 <strong>중앙 집중화 된 미디어 처리</strong> 도 사용할 수 있는 경우에만 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-146">Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef4d-147">중앙 집중화 된 미디어 처리</span><span class="sxs-lookup"><span data-stu-id="fef4d-147">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="fef4d-148">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="fef4d-148">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="fef4d-149">잘 알려진 미디어 종료 지점이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-149">Indicates whether there is a well-known media termination point.</span></span> <span data-ttu-id="fef4d-150">알려진 미디어 종료 지점의 예로는 미디어 종료가 신호 종료의 IP와 동일한 PSTN 게이트웨이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-150">(An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef4d-151">RTP latching 사용</span><span class="sxs-lookup"><span data-stu-id="fef4d-151">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="fef4d-152">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="fef4d-152">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="fef4d-153">SIP 트렁크가 RTP 래치를 지원하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-153">Indicates whether or not the SIP trunks support RTP latching.</span></span> <span data-ttu-id="fef4d-154">RTP 래치는 NAT(Network Address Translator) 장치 또는 방화벽을 통한 RTP/RTCP 연결을 설정하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-154">RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef4d-155">착신 통화 기록 사용</span><span class="sxs-lookup"><span data-stu-id="fef4d-155">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="fef4d-156">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="fef4d-156">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="fef4d-157">트렁크를 통해 통화 기록 정보를 전달할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-157">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef4d-158">앞으로 P-어설션된-Id 데이터 사용</span><span class="sxs-lookup"><span data-stu-id="fef4d-158">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="fef4d-159">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="fef4d-159">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="fef4d-160">PAI(P-Asserted-Identity) 헤더를 통화와 함께 전달할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-160">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="fef4d-161">PAI 헤더를 사용하면 발신자 번호를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-161">The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef4d-162">아웃 바운드 라우팅 장애 조치 타이머 사용</span><span class="sxs-lookup"><span data-stu-id="fef4d-162">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="fef4d-163">Enablefailovertimer</span><span class="sxs-lookup"><span data-stu-id="fef4d-163">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="fef4d-164">게이트웨이에서 응답 하지 않은 아웃 바운드 통화가 10 초 이내에 사용 가능한 다음 트렁크로 라우팅되도록 할지 여부를 표시 합니다. 추가 trunks 없으면 통화가 자동으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-164">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped.</span></span> <span data-ttu-id="fef4d-165">느린 네트워크 및 게이트웨이 응답을 사용 하는 조직에서 호출이 불필요 하 게 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-165">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef4d-166">연결 된 PSTN 용도</span><span class="sxs-lookup"><span data-stu-id="fef4d-166">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="fef4d-167">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="fef4d-167">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="fef4d-168">트렁크에 할당된 PSTN 사용 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-168">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef4d-169">테스트를 위해 번역 된 번호</span><span class="sxs-lookup"><span data-stu-id="fef4d-169">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="fef4d-170">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fef4d-170">N/A</span></span></p></td>
<td><p><span data-ttu-id="fef4d-171">트렁크 구성 설정의 임시 테스트를 수행 하는 데 사용할 수 있는 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-171">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef4d-172">연결 된 번역 규칙</span><span class="sxs-lookup"><span data-stu-id="fef4d-172">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="fef4d-173">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="fef4d-173">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="fef4d-174">아웃 바운드 라우팅이 처리 하는 통화에 적용 되는 전화 번호 번역 규칙 (PBX 또는 PSTN 대상으로 라우팅된 통화)을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-174">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef4d-175">전화 번호 번역 규칙</span><span class="sxs-lookup"><span data-stu-id="fef4d-175">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="fef4d-176">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="fef4d-176">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="fef4d-177">트렁크에 할당된 아웃바운드 호출 번호 변환 규칙 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-177">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef4d-178">테스트할 전화 번호</span><span class="sxs-lookup"><span data-stu-id="fef4d-178">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="fef4d-179">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fef4d-179">N/A</span></span></p></td>
<td><p><span data-ttu-id="fef4d-180">번역 규칙의 특별 테스트를 수행 하는 데 사용할 수 있는 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-180">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef4d-181">전화 번호</span><span class="sxs-lookup"><span data-stu-id="fef4d-181">Calling number</span></span></p></td>
<td><p><span data-ttu-id="fef4d-182">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fef4d-182">N/A</span></span></p></td>
<td><p><span data-ttu-id="fef4d-183">테스트 하려는 전화 번호가 발신자의 전화 번호 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-183">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef4d-184">전화 번호</span><span class="sxs-lookup"><span data-stu-id="fef4d-184">Called number</span></span></p></td>
<td><p><span data-ttu-id="fef4d-185">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fef4d-185">N/A</span></span></p></td>
<td><p><span data-ttu-id="fef4d-186">전화 번호가 통화 중인 사람의 전화 번호 라는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-186">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fef4d-187">Lync Server Set-cstrunkconfiguration cmdlet은 Lync Server 제어판에 표시 되지 않는 추가 속성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-187">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="fef4d-188">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-set-cstrunkconfiguration</A> cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fef4d-188">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="fef4d-189">Lync Server 제어판을 사용 하 여 SIP 트렁크 구성 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="fef4d-189">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fef4d-190">Lync Server 제어판에서 **음성 라우팅을**클릭 한 다음 **트렁크 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-190">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="fef4d-191">**트렁크 구성** 탭에서 수정할 트렁크 구성 설정을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-191">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified.</span></span> <span data-ttu-id="fef4d-192">한 번에 하나의 설정 컬렉션만 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-192">Note that you can only edit one collection of settings at a time.</span></span> <span data-ttu-id="fef4d-193">여러 컬렉션에서 동일한 변경 작업을 수행 하려면 Windows PowerShell을 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-193">If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="fef4d-194">**트렁크 구성 편집** 대화 상자에서 적절 하 게 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-194">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="fef4d-195">컬렉션에 대 한 State 속성이 **커밋되지**않은 **상태로** 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-195">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="fef4d-196">변경 내용을 커밋하고 컬렉션을 삭제 하려면 **커밋을** 클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-196">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="fef4d-197">커밋되지 않은 **음성 구성 설정** 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="fef4d-198">**Microsoft Lync Server 2013 제어판** 대화 상자에서 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fef4d-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

