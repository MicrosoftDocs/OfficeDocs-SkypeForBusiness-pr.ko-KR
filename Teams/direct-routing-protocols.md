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
f1.keywords:
- NOCSH
description: 직접 라우팅 프로토콜
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569206"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a><span data-ttu-id="92b5c-103">직접 라우팅 - 정의 및 RFC 표준</span><span class="sxs-lookup"><span data-stu-id="92b5c-103">Direct Routing - Definitions and RFC standards</span></span>

<span data-ttu-id="92b5c-104">이 문서에서는 시스템 Microsoft 전화 라우팅에서 RFC 표준 프로토콜을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-104">This article describes how Microsoft Phone System Direct Routing implements RFC standard protocols.</span></span> <span data-ttu-id="92b5c-105">이 문서는 SBC(On-Premises Session Border Controller)와 SIP(세션 시작 프로토콜) 프록시 서비스 간의 연결을 구성할 책임이 있는 음성 관리자를 위한 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises Session Border Controller (SBC) and the Session Initiation Protocol (SIP) proxy service.</span></span>

<span data-ttu-id="92b5c-106">고객 SBC는 백end의 다음 구성 요소와 Microsoft Teams 인터페이스합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-106">The customer SBC interfaces with the following components in the Microsoft Teams backend:</span></span> 

- <span data-ttu-id="92b5c-107">**신호에 대한 SIP** 프록시입니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-107">**The SIP proxy** for signaling.</span></span> <span data-ttu-id="92b5c-108">SBC와 직접 라우팅 간의 SIP(TLS) 연결을 처리하는 직접 라우팅의 인터넷 연결 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-108">This is the Internet-facing component of Direct Routing that handles SIP (TLS) connections between the SBCs and Direct Routing.</span></span>

- <span data-ttu-id="92b5c-109">**미디어용** 미디어 프로세서입니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-109">**The media processors** for media.</span></span> <span data-ttu-id="92b5c-110">미디어 트래픽을 처리하는 직접 라우팅의 인터넷 연결 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-110">This is the Internet-facing component of Direct Routing that handles media traffic.</span></span> <span data-ttu-id="92b5c-111">이 구성 요소는 SRTP 및 SRTCP 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-111">This component uses SRTP and SRTCP protocols.</span></span>


<span data-ttu-id="92b5c-112">직접 라우팅에 대한 자세한 내용은 직접 [라우팅 전화 시스템 참조하세요.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="92b5c-112">For more information about Direct Routing, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="92b5c-113">직접 라우팅이 SIP 프로토콜을 구현하는 방법에 대한 자세한 내용은 직접 라우팅 [- SIP 프로토콜 을 참조하세요.](direct-routing-protocols-sip.md)</span><span class="sxs-lookup"><span data-stu-id="92b5c-113">For more information about how Direct Routing implements the SIP protocol, see [Direct Routing - SIP protocol](direct-routing-protocols-sip.md).</span></span>

## <a name="rfc-standards"></a><span data-ttu-id="92b5c-114">RFC 표준</span><span class="sxs-lookup"><span data-stu-id="92b5c-114">RFC standards</span></span>

<span data-ttu-id="92b5c-115">직접 라우팅은 RFC 표준을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-115">Direct Routing complies with RFC standards.</span></span>  <span data-ttu-id="92b5c-116">직접 라우팅에 연결된 SBC도 다음 RFC(또는 해당 후속자)를 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-116">The SBC connected to Direct Routing must also comply with the following RFCs (or their successors).</span></span> 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a><span data-ttu-id="92b5c-117">비미디어 우회 모드를 지원하는 디바이스에 적용되는 표준</span><span class="sxs-lookup"><span data-stu-id="92b5c-117">Standards applicable to devices that support non-media bypass mode</span></span> 

<span data-ttu-id="92b5c-118">다음 표준은 비미디어 우회 모드만 지원하는 디바이스에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-118">The following standards are applicable to devices that support only non-media bypass mode:</span></span>

- <span data-ttu-id="92b5c-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): 세션 시작 프로토콜</span><span class="sxs-lookup"><span data-stu-id="92b5c-119">[RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol</span></span>
- <span data-ttu-id="92b5c-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span><span class="sxs-lookup"><span data-stu-id="92b5c-120">[RFC 3325](https://www.ietf.org/rfc/rfc3325).</span></span> <span data-ttu-id="92b5c-121">신뢰할 수 있는 네트워크 내의 ID에 대한 세션 시작 프로토콜에 대한 개인 확장--P-Asserted-Identity 헤더 처리에 대한 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-121">Private Extension to the Session Initiation Protocol for asserted identity within Trusted Networks--Sections about handling P-Asserted-Identity header.</span></span> <span data-ttu-id="92b5c-122">직접 라우팅은 개인 정보 ID 헤더를 통해 P-Asserted-Identity를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-122">Direct Routing sends P-Asserted-Identity with Privacy ID headers.</span></span> 
- <span data-ttu-id="92b5c-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) 필수 기록 정보에 대한 SIP(세션 시작 프로토콜)에 대한 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-123">[RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) An extension to Session Initiation Protocol (SIP) for required History Information.</span></span> <span data-ttu-id="92b5c-124">자세한 내용은 라우팅 SIP 프로토콜 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92b5c-124">See also: Routing SIP Protocol description for more information.</span></span>
- <span data-ttu-id="92b5c-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) 세션 시작 프로토콜 Referred-By 메커니즘</span><span class="sxs-lookup"><span data-stu-id="92b5c-125">[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) The Session Initiation Protocol Referred-By mechanism</span></span>
- <span data-ttu-id="92b5c-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) SIP(세션 시작 프로토콜) "대체" 헤더</span><span class="sxs-lookup"><span data-stu-id="92b5c-126">[RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) The Session Initiation Protocol (SIP) "Replaces" Header</span></span> 
- <span data-ttu-id="92b5c-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) 제품/답변 모델의 SIP(세션 시작 프로토콜) 사용.</span><span class="sxs-lookup"><span data-stu-id="92b5c-127">[RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Usage of the Offer/Answer Model.</span></span>
  <span data-ttu-id="92b5c-128">"RFC의 일차" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92b5c-128">See the “Deviations from RFC” section.</span></span>
- <span data-ttu-id="92b5c-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) 및 [RFC 4771](https://tools.ietf.org/html/rfc4771).</span><span class="sxs-lookup"><span data-stu-id="92b5c-129">[RFC 3711](https://tools.ietf.org/html/rfc3711) and [RFC 4771](https://tools.ietf.org/html/rfc4771).</span></span> <span data-ttu-id="92b5c-130">SRTP를 사용하여 RTP 트래픽을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-130">Protect RTP traffic using SRTP.</span></span> <span data-ttu-id="92b5c-131">SBC는 SDES를 사용하여 키를 설정할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-131">The SBC must be able to establish keys using SDES.</span></span> 
- <span data-ttu-id="92b5c-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) RTP/RTCP 다중화에 대한 SDP(세션 설명 프로토콜) 제품/답변 설명</span><span class="sxs-lookup"><span data-stu-id="92b5c-132">[RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Offer/Answer Clarifications for RTP/RTCP Multiplexing</span></span>

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a><span data-ttu-id="92b5c-133">미디어 우회 모드를 지원하는 디바이스에 적용되는 표준</span><span class="sxs-lookup"><span data-stu-id="92b5c-133">Standards applicable to devices that support media bypass mode</span></span>

<span data-ttu-id="92b5c-134">비우회 모드에 적용되는 표준 외에도 미디어 우회 모드에 다음 표준이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-134">In addition to the standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:</span></span>

- <span data-ttu-id="92b5c-135">[미디어 우회에 대한 RFC 5245 ICE(대화형 연결 설치)입니다.](https://tools.ietf.org/html/rfc5245)</span><span class="sxs-lookup"><span data-stu-id="92b5c-135">[RFC 5245 Interactive Connectivity Establishment (ICE) for media bypass](https://tools.ietf.org/html/rfc5245).</span></span>  <span data-ttu-id="92b5c-136">SBC는 다음을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-136">The SBC must support the following:</span></span>
  - <span data-ttu-id="92b5c-137">ICE Lite - Teams 클라이언트가 전체 ICE 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-137">ICE Lite - the Teams clients are full ICE clients</span></span>
  - <span data-ttu-id="92b5c-138">[ICE가 다시 시작됩니다.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)</span><span class="sxs-lookup"><span data-stu-id="92b5c-138">[ICE Restarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span> <span data-ttu-id="92b5c-139">ICE 다시 시작 사용 사례 및 ICE 다시 시작의 예제에 대한 자세한 내용은 미디어 우회를 지원하지 않는 엔드포인트로 전송된 미디어 우회 호출을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-139">See more on ICE restarts use case and examples in ICE Restart:  Media bypass call transferred to an endpoint which does not support media bypass</span></span>   
- <span data-ttu-id="92b5c-140">[RFC RFC 5589 SIP(세션 시작 프로토콜) 호출 제어 - 전송.](https://tools.ietf.org/html/rfc5589)</span><span class="sxs-lookup"><span data-stu-id="92b5c-140">[RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589).</span></span> 
- <span data-ttu-id="92b5c-141">[RFC 3960](https://tools.ietf.org/html/rfc3960)세션 시작 프로토콜(SIP)의 초기 미디어 및 벨링 톤 생성 , 3.1, 포킹 및 3.2 섹션, 벨킹 톤 생성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92b5c-141">[RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation</span></span> 
- [<span data-ttu-id="92b5c-142">NAT(STUN)에 대한 RFC 5389 세션 트래버스널 유틸리티</span><span class="sxs-lookup"><span data-stu-id="92b5c-142">RFC 5389 Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5389)
- [<span data-ttu-id="92b5c-143">RFC 5766 NAT 주변 릴레이 사용(TURN): NAT용 세션 트래버스 유틸리티로 릴레이 확장(STUN)</span><span class="sxs-lookup"><span data-stu-id="92b5c-143">RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)</span></span>](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a><span data-ttu-id="92b5c-144">E911 공급자에 위치 정보를 전달하는 데 적용되는 표준</span><span class="sxs-lookup"><span data-stu-id="92b5c-144">Standards applicable to support conveying location information to E911 providers</span></span>

- [<span data-ttu-id="92b5c-145">RFC 6442, 세션 시작 프로토콜에 대한 위치 전달</span><span class="sxs-lookup"><span data-stu-id="92b5c-145">RFC 6442, Location Conveyance for the Session Initiation Protocol</span></span>](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a><span data-ttu-id="92b5c-146">RFC의 일차</span><span class="sxs-lookup"><span data-stu-id="92b5c-146">Deviations from the RFC's</span></span>

<span data-ttu-id="92b5c-147">다음 표에서는 Microsoft의 SIP 또는 미디어 스택 구현이 표준에서 을 이연하는 RFC의 섹션을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-147">The following table lists the sections of the RFC(s) in which Microsoft's implementation of the SIP or media stack deviates from the standard:</span></span>

| <span data-ttu-id="92b5c-148">RFC 및 섹션</span><span class="sxs-lookup"><span data-stu-id="92b5c-148">RFC and sections</span></span> | <span data-ttu-id="92b5c-149">설명</span><span class="sxs-lookup"><span data-stu-id="92b5c-149">Description</span></span> | <span data-ttu-id="92b5c-150">일차</span><span class="sxs-lookup"><span data-stu-id="92b5c-150">Deviation</span></span> |
| :---------------------  |:---------------------- |:-----------------------|
| [<span data-ttu-id="92b5c-151">RFC 6337, 섹션 5.3 미디어 보유 및 재개</span><span class="sxs-lookup"><span data-stu-id="92b5c-151">RFC 6337, section 5.3 Hold and Resume of Media</span></span>](https://tools.ietf.org/html/rfc6337#section-5.3) | <span data-ttu-id="92b5c-152">RFC를 사용하면 "a=inactive", "a=sendonly", a=recvonly"를 사용하여 통화를 보류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-152">RFC allows using “a=inactive”, “a=sendonly”, a=recvonly” to place a call on hold.</span></span> |<span data-ttu-id="92b5c-153">SIP 프록시는 "a=비활성"만 지원하며 SBC에서 "a=sendonly" 또는 "a=recvonly"를 보내는지 이해하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-153">The SIP proxy only supports “a=inactive” and does not understand if the SBC sends “a=sendonly” or “a=recvonly”.</span></span>
| [<span data-ttu-id="92b5c-154">RFC 6337, 섹션 5.4 "c=0.0.0.0을 사용하여 SDP 수신 동작</span><span class="sxs-lookup"><span data-stu-id="92b5c-154">RFC 6337, section 5.4 “Behavior on Receiving SDP with c=0.0.0.0</span></span>](https://tools.ietf.org/html/rfc6337#section-5.4) | <span data-ttu-id="92b5c-155">[RFC3264는](https://tools.ietf.org/html/rfc3264) 에이전트가 0.0.0.0의 연결 주소로 SDP를 받을 수 있도록 요구합니다. 이 경우 RTP 또는 RTCP를 피어로 보내지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-155">[RFC3264](https://tools.ietf.org/html/rfc3264) requires that an agent is capable of receiving SDP with a connection address of 0.0.0.0, in which case it means that neither  RTP nor RTCP should be sent to the peer.</span></span> | <span data-ttu-id="92b5c-156">SIP 프록시는 이 옵션을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-156">The SIP proxy does not support this option.</span></span> |

## <a name="operational-modes"></a><span data-ttu-id="92b5c-157">작동 모드</span><span class="sxs-lookup"><span data-stu-id="92b5c-157">Operational modes</span></span>

<span data-ttu-id="92b5c-158">직접 라우팅에는 두 가지 운영 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-158">There are two operational modes for Direct Routing:</span></span>

- <span data-ttu-id="92b5c-159">**모든** RTP 트래픽이 클라이언트, 미디어 Teams SBC 간에 흐르는 미디어 우회가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-159">**Without media bypass** in which all RTP traffic flows between the Teams client, the media processors, and the SBC.</span></span>  

- <span data-ttu-id="92b5c-160">**모든** RTP 미디어가 Teams 엔드포인트와 SBC 간에 흐르는 미디어 우회.</span><span class="sxs-lookup"><span data-stu-id="92b5c-160">**With media bypass** in which all RTP media flows between the Teams endpoints and the SBC.</span></span> 

<span data-ttu-id="92b5c-161">SIP 트래픽은 항상 SIP 프록시를 통해 흐를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-161">Note that SIP traffic always flows via the SIP proxy.</span></span> 

## <a name="dtmf"></a><span data-ttu-id="92b5c-162">DTMF</span><span class="sxs-lookup"><span data-stu-id="92b5c-162">DTMF</span></span>
<span data-ttu-id="92b5c-163">대역 내 DTMF는 미디어 스택에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92b5c-163">In-band DTMF is not supported by media stack.</span></span>
