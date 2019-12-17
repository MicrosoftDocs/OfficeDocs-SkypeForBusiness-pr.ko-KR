---
title: 전화 시스템 직접 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
description: 다이렉트 라우팅 프로토콜
appliesto:
- Microsoft Teams
ms.openlocfilehash: a470c402ebfd4e70955f4e864d45dbaaca476dfd
ms.sourcegitcommit: 89106cfda0d900d8be541943b7d1537bc69ed57f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2019
ms.locfileid: "40065628"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="4179d-103">직접 라우팅-정의 및 RFC 표준</span><span class="sxs-lookup"><span data-stu-id="4179d-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="4179d-104">이 문서에서는 Microsoft 전화 시스템 다이렉트 라우팅이 RFC 표준 프로토콜을 구현 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="4179d-105">이 문서는 온-프레미스 세션 경계 컨트롤러 (SBC) 및 SIP (세션 시작 프로토콜) 프록시 서비스 간 연결 구성을 담당 하는 음성 관리자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="4179d-106">Microsoft 팀 백 엔드에서 다음 구성 요소를 사용 하는 고객 SBC 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="4179d-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="4179d-107">신호를 위한 **SIP 프록시** 입니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="4179d-108">이는 SBCs와 직접 라우팅과 간의 SIP (TLS) 연결을 처리 하는 바로 라우팅의 인터넷 연결 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="4179d-109">미디어 용 **미디어 프로세서** .</span><span class="sxs-lookup"><span data-stu-id="4179d-109">**The media processors** for media.</span></span> <span data-ttu-id="4179d-110">미디어 트래픽을 처리 하는 다이렉트 라우팅의 인터넷 연결 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="4179d-111">이 구성 요소는 SRTP 및 SRTCP 프로토콜을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="4179d-112">직접 라우팅에 대 한 자세한 내용은 [전화 시스템 직접 라우팅을](direct-routing-landing-page.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4179d-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="4179d-113">다이렉트 라우팅이 SIP 프로토콜을 구현 하는 방법에 대 한 자세한 내용은 [다이렉트 라우팅-SIP 프로토콜](direct-routing-protocols-sip.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4179d-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="4179d-114">RFC 표준</span><span class="sxs-lookup"><span data-stu-id="4179d-114">RFC standards</span></span>

<span data-ttu-id="4179d-115">직접 라우팅은 RFC 표준을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="4179d-116">직접적인 라우팅과 연결 된 SBC는 다음 Rfc (또는 해당 후속 작업)도 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="4179d-117">비 미디어 우회 모드를 지 원하는 장치에 적용할 수 있는 표준</span><span class="sxs-lookup"><span data-stu-id="4179d-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="4179d-118">다음 표준은 비 미디어 바이패스 모드만 지 원하는 장치에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="4179d-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): 세션 시작 프로토콜</span><span class="sxs-lookup"><span data-stu-id="4179d-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="4179d-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="4179d-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="4179d-121">신뢰할 수 있는 네트워크 내에서 어설션된 id에 대 한 세션 초기화 프로토콜에 대 한 개인 확장입니다--P-어설션된-Identity 헤더 처리에 대 한 섹션</span><span class="sxs-lookup"><span data-stu-id="4179d-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="4179d-122">다이렉트 라우팅은 개인 정보 ID 헤더가 포함 된 P-어설션된 Id를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="4179d-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) 필요한 기록 정보에 대 한 SIP (세션 초기화 프로토콜)의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="4179d-124">참고 항목: 자세한 내용은 SIP 프로토콜 설명을 라우팅 하세요.</span><span class="sxs-lookup"><span data-stu-id="4179d-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="4179d-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) 세션 시작 프로토콜 참조 메커니즘</span><span class="sxs-lookup"><span data-stu-id="4179d-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="4179d-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) SIP (세션 시작 프로토콜) "대체" 헤더</span><span class="sxs-lookup"><span data-stu-id="4179d-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="4179d-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) 제안/응답 모델의 SIP (세션 초기화 프로토콜) 사용</span><span class="sxs-lookup"><span data-stu-id="4179d-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="4179d-128">"RFC의 편차" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4179d-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="4179d-129">[Rfc 3711](https://tools.ietf.org/html/rfc3711) 및 [rfc 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="4179d-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="4179d-130">SRTP를 사용 하 여 RTP 트래픽을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="4179d-131">SBC는 SDES를 사용 하 여 키를 설정할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="4179d-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) RTP/RTCP 멀티플렉싱에 대 한 SDP (세션 설명 프로토콜) 제안/응답 설명</span><span class="sxs-lookup"><span data-stu-id="4179d-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="4179d-133">미디어 우회 모드를 지 원하는 장치에 적용 되는 표준</span><span class="sxs-lookup"><span data-stu-id="4179d-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="4179d-134">비 바이패스 모드에 적용 되는 표준 외에도 미디어 우회 모드에 사용 되는 표준은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="4179d-135">[미디어 바이패스에 대 한 RFC 5245 대화형 연결 설정 (ICE)](https://tools.ietf.org/html/rfc5245).</span><span class="sxs-lookup"><span data-stu-id="4179d-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="4179d-136">SBC는 다음을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="4179d-137">ICE Lite-팀 클라이언트는 완전 한 ICE 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="4179d-138">[ICE가 다시 시작](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)됩니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="4179d-139">ICE에 대 한 자세한 정보 ICE 다시 시작의 사용 사례 및 예제 미디어 바이패스를 지원 하지 않는 끝점으로 전송 된 미디어 건너뛰기 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="4179d-140">[RFC rfc 5589 SIP (세션 초기화 프로토콜) 통화 제어 – 전송](https://tools.ietf.org/html/rfc5589)</span><span class="sxs-lookup"><span data-stu-id="4179d-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="4179d-141">[RFC 3960 빠른 미디어 및 SIP (세션 초기화 프로토콜)의 발신음 생성](https://tools.ietf.org/html/rfc3960), 섹션 3.1, 포크 및 3.2, 신호음 생성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4179d-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="4179d-142">NAT에 대 한 RFC 5389 세션 트래버스 유틸리티 (STUN)</span><span class="sxs-lookup"><span data-stu-id="4179d-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="4179d-143">NAT 주변에서 릴레이를 사용 하 여 RFC 5766 통과 (TURN): NAT 용 세션 트래버스 유틸리티 (STUN)에 대 한 릴레이 확장</span><span class="sxs-lookup"><span data-stu-id="4179d-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="4179d-144">위치 정보를 E911 공급자에 게 전달 하는 것을 지원 하기에 적합 한 표준</span><span class="sxs-lookup"><span data-stu-id="4179d-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="4179d-145">RFC 6442, 위치 Conveyance 세션 시작 프로토콜</span><span class="sxs-lookup"><span data-stu-id="4179d-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="4179d-146">RFC의 편차</span><span class="sxs-lookup"><span data-stu-id="4179d-146">Deviations from the RFC's</span></span>

<span data-ttu-id="4179d-147">다음 표에는 Microsoft의 SIP 또는 미디어 스택의 구현이 표준에 따라 결정 되는 RFC의 섹션이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="4179d-148">RFC 및 섹션</span><span class="sxs-lookup"><span data-stu-id="4179d-148">RFC and sections</span></span> | <span data-ttu-id="4179d-149">설명</span><span class="sxs-lookup"><span data-stu-id="4179d-149">Description</span></span> | <span data-ttu-id="4179d-150">차이</span><span class="sxs-lookup"><span data-stu-id="4179d-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="4179d-151">RFC 6337, 섹션 5.3 미디어 보존 및 재개</span><span class="sxs-lookup"><span data-stu-id="4179d-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="4179d-152">RFC는 "a = 비활성", "a = sendonly", a = recvonly "를 사용 하 여 통화를 대기 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="4179d-153">SIP 프록시는 "a = 비활성"만 지원 하 고 SBC가 "a = sendonly" 또는 "a = recvonly"를 전송 하는지는 인식 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="4179d-154">RFC 6337, 섹션 5.4 "e-c를 사용 하 여 SDP를 받을 때의 동작</span><span class="sxs-lookup"><span data-stu-id="4179d-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="4179d-155">[RFC3264](https://tools.ietf.org/html/rfc3264) 는 연결 주소가 0.0.0.0 인 SDP를 수신할 수 있어야 하며,이 경우 RTP와 RTCP를 피어로 보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="4179d-156">SIP 프록시는이 옵션을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="4179d-157">운영 모드</span><span class="sxs-lookup"><span data-stu-id="4179d-157">Operational modes</span></span>

<span data-ttu-id="4179d-158">직접 라우팅에 대 한 작동 모드에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="4179d-159">**미디어 바이패스 없이** 팀 클라이언트, 미디어 프로세서, SBC 간에 모든 RTP 트래픽이 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="4179d-160">모든 RTP 미디어가 팀 끝점과 SBC 간에 흐르는 **미디어 바이패스를 사용** 합니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="4179d-161">SIP 트래픽은 항상 SIP 프록시를 통해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4179d-161">Note that SIP traffic always flows via the SIP proxy.</span></span>   
