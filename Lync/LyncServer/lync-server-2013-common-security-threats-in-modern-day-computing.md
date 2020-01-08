---
title: 'Lync Server 2013: 현대의 일 컴퓨팅의 일반적인 보안 위협'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2446ee0755f4544f17f6c04c6059d70576a466f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "40983410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="08295-102">현대의 일상 컴퓨팅의 일반적인 보안 위협</span><span class="sxs-lookup"><span data-stu-id="08295-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08295-103">_**마지막으로 수정한 주제:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="08295-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="08295-104">Lync Server 2013는 엔터프라이즈급 통신 시스템 이므로 인프라 및 통신에 영향을 줄 수 있는 일반적인 보안 공격에 대해 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="08295-105">손상 된 키 공격</span><span class="sxs-lookup"><span data-stu-id="08295-105">Compromised-Key Attack</span></span>

<span data-ttu-id="08295-106">키는 비밀 정보를 암호화, 해독 또는 유효성을 검사 하는 데 사용 되는 비밀 코드 또는 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="08295-106">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="08295-107">PKI (공개 키 인프라)에서 사용 되는 두 가지 중요 한 키로 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-107">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="08295-108">각 인증서 소유자에 게 있는 개인 키</span><span class="sxs-lookup"><span data-stu-id="08295-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="08295-109">통신 파트너에의 한 확인 및 세션 키 교환이 완료 된 후 사용 되는 세션 키</span><span class="sxs-lookup"><span data-stu-id="08295-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="08295-110">공격자가 개인 키 또는 세션 키를 결정할 때 노출 된 키 공격이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-110">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="08295-111">공격자가 키를 확인 하는 데 성공 하면 공격자는 키를 사용 하 여 보낸 사람에 대 한 지식 없이 암호화 된 데이터의 암호를 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-111">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="08295-112">Lync Server 2013는 Windows Server 운영 체제의 PKI 기능을 사용 하 여 TLS (전송 계층 보안) 연결에 대 한 암호화에 사용 되는 키 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="08295-113">미디어 암호화에 사용 되는 키는 TLS 연결을 통해 교환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08295-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="08295-114">네트워크 서비스 거부 공격</span><span class="sxs-lookup"><span data-stu-id="08295-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="08295-115">*서비스 거부 공격은* 공격자가 일반 네트워크 사용을 차단 하 고 유효한 사용자에 의해 작동 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-115">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="08295-116">이 작업은 공격자가 합법적인 사용자가 서비스를 사용 하는 것을 방해 하는 합법적인 요청으로 서비스를 초과 하는 경우에 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08295-116">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="08295-117">서비스 거부 공격을 사용 하 여 공격자는 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-117">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="08295-118">공격 대상 네트워크에서 실행 되는 응용 프로그램 및 서비스에 잘못 된 데이터를 보내서 정상 작동을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="08295-119">많은 양의 소통량을 보내고, 시스템이 응답을 중지할 때까지 시스템을 오버 로드 하거나, 합법적인 요청에 느리게 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="08295-120">공격의 증거를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="08295-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="08295-121">사용자가 네트워크 리소스에 액세스 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="08295-122">도청 (스니핑, Snooping)</span><span class="sxs-lookup"><span data-stu-id="08295-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="08295-123">*도청* 은 공격자가 네트워크의 데이터 경로에 대 한 액세스 권한을 얻어 트래픽을 모니터링 하 고 읽을 수 있는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-123">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="08295-124">이것을 *스니핑* 또는 *snooping*이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-124">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="08295-125">트래픽이 일반 텍스트인 경우 공격자가 경로에 대 한 액세스 권한을 얻으면 트래픽을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-125">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="08295-126">데이터 경로의 라우터를 제어 하 여 공격을 수행 하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-126">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="08295-127">Microsoft Lync Server 2013 내부의 트래픽에 대 한 기본 권장 사항과 클라이언트 간 신뢰 된 서버와 TLS 사이에 상호 TLS (MTLS)를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="08295-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="08295-128">이러한 보호 조치는 특정 대화가 발생 하는 기간 내에 공격을 매우 어렵거나 불가능 하 게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="08295-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="08295-129">TLS는 모든 당사자를 인증 하 고 모든 트래픽을 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="08295-130">이는 도청을 방지 하지 않지만 공격자가 트래픽을 읽을 수 없는 경우에는 암호화가 손상 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="08295-131">릴레이 NAT (TURN) 프로토콜을 사용 하는 순회는 암호화 되는 트래픽을 보장 하지 않으며 보내는 정보는 메시지 무결성으로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08295-131">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="08295-132">도청을 하기는 하지만 보내는 정보 (즉, IP 주소 및 포트)는 단순히 패킷의 원본 및 대상 주소를 보고 직접 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-132">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="08295-133">A/V Edge 서비스는 일반 텍스트로 전송 되지 않는 선반 가공 비밀 번호를 포함 하 여 일부 항목에서 파생 된 키를 사용 하 여 메시지의 메시지 무결성을 확인 하 여 유효한 데이터 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-133">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="08295-134">보안 실시간 프로토콜 (SRTP)을 사용 하는 경우 미디어 트래픽도 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08295-134">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="08295-135">Id 스푸핑 (IP 주소 스푸핑)</span><span class="sxs-lookup"><span data-stu-id="08295-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="08295-136">*스푸핑은* 공격자가 네트워크, 컴퓨터 또는 네트워크 구성 요소의 IP 주소를 확인 하 고 사용할 권한이 없는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="08295-137">공격이 성공 하면 공격자가 일반적으로 IP 주소로 식별 되는 엔터티인 것 처럼 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="08295-138">Microsoft Lync Server 2013의 컨텍스트 내에서 관리자가 다음을 모두 수행 하는 경우에만이 상황이 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08295-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="08295-139">TCP (전송 제어 프로토콜)만 지원 하는 구성 된 연결 (TCP 통신은 암호화 되지 않기 때문에 권장 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="08295-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="08295-140">해당 연결의 IP 주소를 신뢰할 수 있는 호스트로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="08295-141">TLS (전송 계층 보안) 연결에는 모든 당사자를 인증 하 고 모든 트래픽을 암호화 하는 데 문제가 발생 하는 것이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="08295-142">TLS를 사용 하면 공격자가 특정 연결에 대해 IP 주소 스푸핑을 수행할 수 없습니다 (예: 상호 TLS 연결).</span><span class="sxs-lookup"><span data-stu-id="08295-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="08295-143">하지만 공격자는 Lync Server 2013에서 사용 하는 DNS 서버의 주소를 계속 스푸핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="08295-144">그러나 Lync의 인증은 인증서를 사용 하 여 수행 되므로 공격자는 통신 중인 파티 중 하나를 위장 하는 데 필요한 유효한 인증서를 보유 하 고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="08295-145">중간자 개입 공격</span><span class="sxs-lookup"><span data-stu-id="08295-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="08295-146">침입자가 두 명의 통신 사용자에 대 한 지식 없이도 공격자의 컴퓨터를 통해 두 사용자 간의 의사 소통을 전환할 때 사람이 중간에 공격이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="08295-147">공격자는 받는 사람에 게 전송 하기 전에 트래픽을 모니터링 하 고 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="08295-148">통신의 각 사용자는 의도 된 사용자와만 통신 하는 동안 모르는 사이에 트래픽을 보내고 공격자 로부터 트래픽을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="08295-149">이 문제는 공격자가 Active Directory 도메인 서비스를 수정 하 여 서버를 신뢰할 수 있는 서버로 추가 하거나 DNS (Domain Name System)를 수정 하 여 클라이언트가 공격자를 통해 서버에 연결 하도록 하는 경우에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="08295-150">두 클라이언트 간의 미디어 소통으로 인 한 중간자 공격이 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="08295-151">그러나 Microsoft Lync Server 2013 지점간 오디오, 비디오 및 응용 프로그램 공유에서는 TLS를 통해 SIP (세션 초기화 프로토콜)를 사용 하는 피어 간에 협상 되는 암호화 키를 사용 하 여 SRTP로 스트림을 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="08295-152">그룹 채팅 등의 서버는 HTTPS를 사용 하 여 웹 소통량의 보안을 강화 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="08295-153">RTP 재생 공격</span><span class="sxs-lookup"><span data-stu-id="08295-153">RTP Replay Attack</span></span>

<span data-ttu-id="08295-154">*재생 공격은* 두 파티 간의 올바른 미디어 전송이 악의적인 목적으로 차단 되 고 다시 전송 될 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-154">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="08295-155">보안 신호 프로토콜을 사용 하 여 연결에 사용 되는 SRTP 수신기에서 이미 수신 된 RTP 패킷의 인덱스를 유지 하 고 각 새 패킷을 인덱스에 나열 된 것과 비교할 수 있도록 하 여 재생 공격 으로부터 전송을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-155">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="08295-156">스</span><span class="sxs-lookup"><span data-stu-id="08295-156">Spim</span></span>

<span data-ttu-id="08295-157">*스 핌* 은 원치 않는 상업성 인스턴트 메시지 또는 현재 상태 구독 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="08295-157">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="08295-158">네트워크를 사용 하는 것이 유일한 것은 아니지만, 가장 적은 시간에, 리소스 가용성과 프로덕션을 줄일 수 있으며, 네트워크를 손상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-158">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="08295-159">예를 들어 사용자가 요청을 보내 서로 spimming 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-159">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="08295-160">사용자는이를 방지 하기 위해 서로 차단할 수 있지만, 페더레이션에서는 통합 된 스 핌 공격이 설정 된 경우 파트너에 대해 페더레이션을 사용 하지 않도록 설정 하지 않는 한 극복 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-160">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="08295-161">바이러스 및 웜</span><span class="sxs-lookup"><span data-stu-id="08295-161">Viruses and Worms</span></span>

<span data-ttu-id="08295-162">*바이러스* 는 비슷한 코드 단위를 추가로 재현 하는 데 목적이 있는 코드 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="08295-162">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="08295-163">작업을 수행 하려면 바이러스에 파일, 전자 메일 또는 프로그램과 같은 호스트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-163">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="08295-164">*웜은* 다른 비슷한 코드 단위를 재현 하는 데 목적이 있지만 호스트가 필요 하지 않은 코드 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="08295-164">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="08295-165">바이러스와 웜은 주로 클라이언트 간 파일 전송 중 또는 다른 사용자가 Url을 보내는 경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08295-165">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="08295-166">컴퓨터에 바이러스가 있는 경우, 예를 들어 사용자를 대신 하 여 본인의 신원을 확인 하 고 인스턴트 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-166">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="08295-167">개인 식별 가능 정보</span><span class="sxs-lookup"><span data-stu-id="08295-167">Personally Identifiable Information</span></span>

<span data-ttu-id="08295-168">Microsoft Lync Server 2013에는 개인에 연결 될 수 있는 공용 네트워크를 통해 정보를 공개할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="08295-169">정보 유형을 두 가지 특정 범주로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="08295-170">**향상 된 현재 상태 데이터** 향상 된 현재 상태 데이터는 사용자가 페더레이션 파트너 또는 조직 내 연락처에 대 한 링크를 통해 공유 하거나 공유 하지 않도록 선택할 수 있는 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="08295-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="08295-171">이 데이터는 공용 메신저 네트워크의 사용자와 공유 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="08295-172">클라이언트 정책 및 기타 클라이언트 구성은 일부 컨트롤을 시스템 관리자에 게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="08295-173">Lync Server 2013에서는 사용자의 대화 상대 목록에 없는 Lync 사용자가 사용자의 현재 상태 정보를 보지 못하도록 개별 사용자에 대해 향상 된 현재 상태 개인 정보 모드를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="08295-174">향상 된 현재 상태 개인 정보 모드에서는 Microsoft Office Communicator 2007 및 Microsoft Office Communicator 2007 R2 사용자가 사용자의 현재 상태 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="08295-175">자세한 내용은 배포 설명서의 [Lync server 2013에서 시작 설명서 및 향상 된 현재 상태 개인 정보 보호 모드 구성](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) 에 있는 [lync server 2013의 클라이언트에 대 한 새로운 기능](lync-server-2013-what-s-new-for-clients.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08295-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="08295-176">**필수 데이터** 필수 데이터는 서버나 클라이언트의 적절 한 작동에 필요 하며 클라이언트 또는 시스템 관리의 제어를 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="08295-177">이 정보는 라우팅, 상태 유지 관리, 신호 등의 목적으로 서버나 네트워크 수준에서 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="08295-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="08295-178">다음 표에는 공용 네트워크를 통해 노출 되는 데이터가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08295-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="08295-179">향상 된 현재 상태 데이터</span><span class="sxs-lookup"><span data-stu-id="08295-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08295-180">데이터 공개</span><span class="sxs-lookup"><span data-stu-id="08295-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="08295-181">가능 설정</span><span class="sxs-lookup"><span data-stu-id="08295-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08295-182">개인 데이터</span><span class="sxs-lookup"><span data-stu-id="08295-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="08295-183">이름, 직함, 회사, 전자 메일 주소, 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="08295-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08295-184">전화 번호</span><span class="sxs-lookup"><span data-stu-id="08295-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="08295-185">회사, 휴대폰, 가정용</span><span class="sxs-lookup"><span data-stu-id="08295-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08295-186">일정 정보</span><span class="sxs-lookup"><span data-stu-id="08295-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="08295-187">약속 있음/없음, 도심 알림, 모임 세부 정보 (일정에 액세스할 수 있는 사용자에 게)</span><span class="sxs-lookup"><span data-stu-id="08295-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08295-188">현재 상태</span><span class="sxs-lookup"><span data-stu-id="08295-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="08295-189">자리 비움, 사용 가능, 다른 용무 중, 방해 금지, 오프 라인</span><span class="sxs-lookup"><span data-stu-id="08295-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="08295-190">필수 데이터</span><span class="sxs-lookup"><span data-stu-id="08295-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08295-191">데이터 공개</span><span class="sxs-lookup"><span data-stu-id="08295-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="08295-192">예제 정보</span><span class="sxs-lookup"><span data-stu-id="08295-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08295-193">IP 주소</span><span class="sxs-lookup"><span data-stu-id="08295-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="08295-194">컴퓨터의 실제 주소 또는 NATed 있는 주소</span><span class="sxs-lookup"><span data-stu-id="08295-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08295-195">SIP URI</span><span class="sxs-lookup"><span data-stu-id="08295-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="08295-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="08295-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

