---
title: 전화 시스템 직접 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888577"
---
# <a name="overview"></a><span data-ttu-id="85dae-103">개요</span><span class="sxs-lookup"><span data-stu-id="85dae-103">Overview</span></span>

<span data-ttu-id="85dae-104">이 문서에서는 [RFC 5245에서](https://tools.ietf.org/html/rfc5245)설명한 바와 같이 DIRECT 라우팅이 ICE Lite에 대해 사용하도록 설정된 SBC(세션 테두리 컨트롤러)를 사용하여 미디어 우회를 지원하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="85dae-105">이 문서는 프레미스 SBC와 SIP 프록시 서비스 간의 연결을 구성할 책임이 있는 음성 관리자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="85dae-106">이 문서에서는 ICE Lite 시나리오의 개요와 상호 작동을 위한 요구 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="85dae-107">이 문서에서는 신뢰할 수 있는 호출 및 미디어 흐름을 보장하기 위해 메시지 형식 및 필요한 상태 컴퓨터 전환에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="85dae-108">용어</span><span class="sxs-lookup"><span data-stu-id="85dae-108">Terminology</span></span>

- <span data-ttu-id="85dae-109">첫 번째 Hello – 발신자 및 호출자에 의해 발신된 첫 번째 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="85dae-110">엔드포인트의 첫 번째 패킷이 대부분의 사용 사례에 대해 안정적으로 전달되도록 모든 노력을 기울이는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="85dae-111">포크 – 발신자로부터의 제안은 여러 장치에서 발신자를 사용할 수 있는 경우 여러 발신자 엔드포인트로 배달될 수 있습니다(예: Teams 사용자는 Windows용 Teams 및 Android 또는 iPhone용 Teams에 로그인할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="85dae-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="85dae-112">프로비전 답변(183) – 더 빠른 통화 설정을 위한 수신자 엔드포인트는 미디어 흐름을 설정하는 데 필요한 후보 및 키로 답변을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="85dae-113">이는 사용자가 해당 특정 호출자 인스턴스에서 호출(200OK)에 잠재적으로 응답할 것으로 예상하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="85dae-114">포크를 사용하여 호출자는 여러 개의 프로비전 답변을 받을 준비가 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="85dae-115">Re-Invite – ICE 제어 엔드포인트에서 선택한 최종 후보가 있는 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="85dae-116">여기에는 여러 포크를 처리하지 못하게 하는 경마 조건을 해결하기 위한 a=remote-candidate 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="85dae-117">Teams 엔드포인트 – 서버(미디어 프로세서, 전송 릴레이) 또는 Teams 클라이언트일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="85dae-118">메시지 형식</span><span class="sxs-lookup"><span data-stu-id="85dae-118">Message format</span></span>

<span data-ttu-id="85dae-119">Teams 인프라는 ICE-Lite용 RFC 5245를 따르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="85dae-120">즉, 모든 STUN 메시지가 [RFC 5389를 준수하게 됩니다.](https://tools.ietf.org/html/rfc5389)</span><span class="sxs-lookup"><span data-stu-id="85dae-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="85dae-121">RFC 5389에서 요구하는 SBC는 인식할 수 없는 STUN 특성을 무시하고 알려진 특성으로 메시지를 계속 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="85dae-122">오타가 있는 패킷이 수신되는 경우 미디어 세션 설치에 영향을 주지 않고 패킷을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="85dae-123">ICE Lite 요구 사항</span><span class="sxs-lookup"><span data-stu-id="85dae-123">ICE Lite requirements</span></span>

<span data-ttu-id="85dae-124">이 섹션에서는 ICE Lite에 대한 요구 사항을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="85dae-125">후보 수집</span><span class="sxs-lookup"><span data-stu-id="85dae-125">Candidate gathering</span></span>

<span data-ttu-id="85dae-126">SBC는 공개적으로 도달할 수 있는 후보를 하나만 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="85dae-127">현재 IPV4 후보만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="85dae-128">연결 확인</span><span class="sxs-lookup"><span data-stu-id="85dae-128">Connectivity checks</span></span>

<span data-ttu-id="85dae-129">ICE Lite 구현은 수신된 연결 확인에 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="85dae-130">ICE Lite 엔드포인트는 연결 확인 요청을 보내지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="85dae-131">(연결 검사가 위반으로 전송된 경우 전체 구현이 응답하여 예기치 않은 피어 파생 후보가 검색되고 호출 오류가 발생할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="85dae-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="85dae-132">후보</span><span class="sxs-lookup"><span data-stu-id="85dae-132">Nominations</span></span>

<span data-ttu-id="85dae-133">ICE 전체 구현 엔드포인트는 항상 제어 엔드포인트로 사용하며 미디어 흐름에 사용할 최종 후보를 선택하기 위한 "일반" 후보를 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="85dae-134">ICE Lite 엔드포인트는 후보를 사용하여 미디어에 사용할 경로를 마무리하고 호출을 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="85dae-135">참고: 183개 임시 답변을 보내는 피어 엔드포인트로 포크하는 경우 SBC는 200OK 전에 지명이 발생하면 여러 엔드포인트의 검사 및 여러 엔드포인트의 지명에 응답할 준비가 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="85dae-136">최종 경로에 있는 ICE 상태 컴퓨터의 수렴과 사용자의 응답 타이밍에 따라 200OK 이전 또는 이후에 후보가 결정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="85dae-137">SBC는 두 경우 모두를 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="85dae-138">포크 수렴</span><span class="sxs-lookup"><span data-stu-id="85dae-138">Converging for forking</span></span>

<span data-ttu-id="85dae-139">SBC 포크에서 여러 Teams 엔드포인트로 제안이 제공된 경우 Teams 엔드포인트는 임시 응답으로 응답하고 연결 검사를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="85dae-140">SBC는 연결 검사를 수신하고 여러 피어 엔드포인트에서 연결 검사에 응답할 수 있도록 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="85dae-141">예를 들어 Teams 사용자는 데스크톱과 휴대폰 모두에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="85dae-142">두 디바이스 모두 인바운드 호출에 대한 알림을 제공하고 SBC를 통해 연결 검사를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="85dae-143">결국 엔드포인트 중 하나만 호출에 응답합니다(200OK).</span><span class="sxs-lookup"><span data-stu-id="85dae-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="85dae-144">200OK를 수신할 때 SBC는 미디어 패킷을 처리하기 위한 올바른 컨텍스트를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="85dae-145">시나리오</span><span class="sxs-lookup"><span data-stu-id="85dae-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="85dae-146">SBC의 인바운드 호출</span><span class="sxs-lookup"><span data-stu-id="85dae-146">Inbound call from SBC</span></span>

<span data-ttu-id="85dae-147">이 시나리오의 경우 SBC에서 처리해야 하는 몇 가지 가능한 피어 엔드포인트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="85dae-148">서버 엔드포인트는 일반적으로 200OK로 직접 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="85dae-149">일반적으로 음성 메일, 통화 큐 및 자동 전화 회의 시나리오와 관련된 전체 ICE 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="85dae-150">클라이언트 엔드포인트는 다른 From/To 태그(183)와 호출에 응답하는 엔드포인트에서 200OK를 사용하여 여러 개의 임시 답변을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="85dae-151">이러한 엔드포인트는 일반적으로 최종 사용자 클라이언트를 나타내는 전체 ICE 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="85dae-152">다른 SBC 엔드포인트.</span><span class="sxs-lookup"><span data-stu-id="85dae-152">Other SBC endpoints.</span></span> <span data-ttu-id="85dae-153">이는 일반적으로 클라이언트 엔드포인트와 다른 전화 번호에 동시에 연결되는 시나리오에 관련된 ICE Lite 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="85dae-154">SBC는 전체 ICE 엔드포인트에서 받은 유효한 모든 연결 확인 요청에 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="85dae-155">RFC당 전체 ICE 엔드포인트는 제어 엔드포인트가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="85dae-156">Teams(클라이언트/서버) 엔드포인트는 "일반" 지명을 수행하여 연결 검사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="85dae-157">최종 200Ok는 초기 미디어를 전송한 엔드포인트 또는 다른 엔드포인트에서 나타났을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="85dae-158">200Ok를 수신할 때 SBC는 미디어 흐름에 적합한 컨텍스트를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="85dae-159">초기 미디어</span><span class="sxs-lookup"><span data-stu-id="85dae-159">Early media</span></span>

<span data-ttu-id="85dae-160">초기 미디어 흐름이 있는 경우 SBC는 스트리밍 미디어를 시작하는 첫 번째 엔드포인트로 래치해야 합니다. 미디어 흐름은 후보가 지명되기 전에 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="85dae-161">SBC는 이 단계에서 IVR/음성 메일 시나리오를 사용하도록 설정하기 위해 DTMF를 전송하는 지원을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="85dae-162">SBC는 후보가 완료되지 않은 경우 확인을 받은 가장 높은 우선 순위 경로를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="85dae-163">SBC에 대한 아웃바운드 호출</span><span class="sxs-lookup"><span data-stu-id="85dae-163">Outbound call to SBC</span></span>

<span data-ttu-id="85dae-164">Teams 엔드포인트는 이 시나리오에 대한 호출자로, 제어 엔드포인트가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="85dae-165">임시 답변(183) 또는 최종 답변(200OK)을 수신하면 Teams 엔드포인트가 연결 검사를 시작하고 "일반" 후보로 진행하여 연결 검사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="85dae-166">참고: SBC에서 임시 답변(183)을 보내는 경우 SBC는 연결 확인 요청을 수신하고 200OK를 SBC에서 보내기 전에 후보를 완료할 준비가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="85dae-167">200OK를 수신하기 전에 검사 및/또는 후보가 완료된 경우 200OK가 수신된 후 검사 및/또는 지명은 다시 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="85dae-168">SBC는 ICE 후보, 암호 및 ufrag(사용자 이름 조각)를 183에서 200 사이로 변경하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="85dae-169">초기 미디어를 지원하기 위해 SBC는 Teams 엔드포인트에서 후보를 완료하기 전에 수신된 연결 확인을 기준으로 가장 높은 우선 순위를 통해 미디어를 피어 ICE 후보로 스트리밍하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="85dae-170">SBC는 후보가 완성될 때까지 Teams의 미디어를 모든 후보에 대해 예상해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="85dae-171">후보가 지명되면 SBC는 미디어 패킷을 보내고 받으기 위해 올바른 컨텍스트로 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="85dae-172">SRTP 지원 요구 사항</span><span class="sxs-lookup"><span data-stu-id="85dae-172">SRTP support requirements</span></span>

<span data-ttu-id="85dae-173">SBC는 다음 형식의 제안 및 AES_CM_128_HMAC_SHA1_80 SRTP 암호화를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="85dae-174">다음은 SBC의 SDP 제품에서 암호화 특성의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="85dae-175">MKI 및 Length 매개 변수는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="85dae-176">자세한 내용은 [RFC 4568, 섹션 6.1을 참조하세요.](https://tools.ietf.org/html/rfc4568#section-6.1)</span><span class="sxs-lookup"><span data-stu-id="85dae-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="85dae-177">SDES 지원 요구 사항</span><span class="sxs-lookup"><span data-stu-id="85dae-177">SDES support requirements</span></span>

<span data-ttu-id="85dae-178">디바이스는 아래 설명된 형식으로 SDES를 제공할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="85dae-179">Microsoft 미디어 프로세서는 항상 SDES를 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="85dae-180">미디어가 아닌 우회를 사용할 경우 클라이언트가 DTLS만 지원하는 경우에도 미디어 프로세서는 SDES로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="85dae-181">미디어 우회를 사용하여 클라이언트가 DTLS 전용인 경우(향후 Google Chrome 상태) 직접 라우팅은 경로에 MP를 삽입하여 미디어 우회에서 비 미디어 우회로 호출을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="85dae-182">직접 라우팅의 SBC와 미디어 프로세서 구성 요소 사이에는 SDES가 항상 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="85dae-183">현재 DTLS만 제공하는 Teams 클라이언트는 없습니다. 그러나 Google은 어느 시점에 SDES 지원을 중지할 예정이라 발표했습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="85dae-184">우회 모드의 SBC에서 제안에 대한 형식</span><span class="sxs-lookup"><span data-stu-id="85dae-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="85dae-185">제안은 SDES를 포함해야 합니다. DTLS 선택적 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85dae-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="85dae-186">SDES를 포함하는 SBC에 대한 답변 형식</span><span class="sxs-lookup"><span data-stu-id="85dae-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="85dae-187">Teams에서 SBC로 제품 서식 지정</span><span class="sxs-lookup"><span data-stu-id="85dae-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="85dae-188">SDES용 형식만 SBC에 제공</span><span class="sxs-lookup"><span data-stu-id="85dae-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

