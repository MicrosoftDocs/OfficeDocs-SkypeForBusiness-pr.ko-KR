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
# <a name="overview"></a><span data-ttu-id="3dbb5-103">개요</span><span class="sxs-lookup"><span data-stu-id="3dbb5-103">Overview</span></span>

<span data-ttu-id="3dbb5-104">이 문서에서는 [RFC 5245에서](https://tools.ietf.org/html/rfc5245)설명한 바와 같이 ICE Lite에 대해 사용하도록 설정된 SBC(세션 테두리 컨트롤러)를 사용하여 직접 라우팅이 미디어 우회를 지원하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-104">This article describes how Direct Routing supports media bypass with a Session Border Controller (SBC) enabled for ICE Lite as described in [RFC 5245](https://tools.ietf.org/html/rfc5245).</span></span> <span data-ttu-id="3dbb5-105">이 문서는 프레미스 SBC와 SIP 프록시 서비스 간의 연결을 구성할 책임이 있는 음성 관리자를 위한 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-105">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

<span data-ttu-id="3dbb5-106">이 문서에서는 ICE Lite 시나리오 및 상호 작동성에 대한 요구 사항에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-106">This article provides an overview of the ICE Lite scenarios and requirements for interoperability.</span></span> <span data-ttu-id="3dbb5-107">이 문서에서는 신뢰할 수 있는 호출 및 미디어 흐름을 보장하기 위해 메시지 형식 및 필요한 상태 머신 전환을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-107">The article describes the message formats and the required state machine transitions for ensuring reliable call and media flow.</span></span>

## <a name="terminology"></a><span data-ttu-id="3dbb5-108">용어</span><span class="sxs-lookup"><span data-stu-id="3dbb5-108">Terminology</span></span>

- <span data-ttu-id="3dbb5-109">첫 번째 안녕하세요 - 발신자 및 호출자에서 말한 첫 번째 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-109">First Hello – The first words spoken by the caller and callee.</span></span> <span data-ttu-id="3dbb5-110">엔드포인트의 첫 번째 패킷이 대부분의 사용 사례에 대해 안정적으로 전달되도록 모든 노력을 기울이는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-110">It is important that all efforts are made to ensure that the first packets from the endpoints are delivered reliably for most use cases.</span></span>

- <span data-ttu-id="3dbb5-111">포킹 – 호출자를 여러 장치에서 사용할 수 있는 경우 발신자로부터의 제안이 여러 발신자 엔드포인트에 전달될 수 있습니다(예: Teams 사용자가 Android 또는 Teams Windows Teams 수 iPhone.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-111">Forking – The offer from the caller might be delivered to multiple callee endpoints if the callee is available on multiple devices (for example, a Teams user might be signed into Teams for Windows and Teams for Android or iPhone).</span></span>

- <span data-ttu-id="3dbb5-112">잠정 답변(183) – 빠른 통화 설정을 위한 발신자 엔드포인트는 미디어 흐름을 설정하는 데 필요한 후보 및 키와 함께 답변을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-112">Provisional Answer (183) – The callee endpoints for faster call setup send an answer with the candidates and keys required to establish media flow.</span></span> <span data-ttu-id="3dbb5-113">이는 사용자가 해당 특정 호출자 인스턴스에서 호출(200OK)에 잠재적으로 응답할 수 있도록 예상하기 위해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-113">This is done in anticipation of the user potentially answering the call(200OK) from that specific callee instance.</span></span> <span data-ttu-id="3dbb5-114">포크를 사용하여 호출자는 여러 임시 답변을 받을 준비가 돼야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-114">With forking, the caller should be ready to receive multiple provisional answers.</span></span>

- <span data-ttu-id="3dbb5-115">Re-Invite – ICE 제어 엔드포인트에서 선택한 최종 후보가 있는 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-115">Re-Invite – Offer with final candidates selected by the ICE controlling endpoint.</span></span> <span data-ttu-id="3dbb5-116">여기에는 여러 포크를 처리하지 못하게 하는 모든 레이스 조건을 해결하는 a=remote-candidate 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-116">This will have the a=remote-candidate attribute to resolve any race conditions from handling multiple forks.</span></span>

- <span data-ttu-id="3dbb5-117">Teams 엔드포인트 – 서버(Media Processor, 전송 릴레이) 또는 클라이언트 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-117">Teams Endpoint – This could either be a server (Media Processor, Transport Relay) or the Teams client.</span></span>

## <a name="message-format"></a><span data-ttu-id="3dbb5-118">메시지 형식</span><span class="sxs-lookup"><span data-stu-id="3dbb5-118">Message format</span></span>

<span data-ttu-id="3dbb5-119">이 Teams 인프라는 ICE-Lite용 RFC 5245를 따르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-119">The Teams infrastructure follows RFC 5245 for ICE-Lite.</span></span> <span data-ttu-id="3dbb5-120">이는 모든 STUN 메시지가 [RFC 5389를 준수할 것임을 암시합니다.](https://tools.ietf.org/html/rfc5389)</span><span class="sxs-lookup"><span data-stu-id="3dbb5-120">This implies that all the STUN messages will be compliant with [RFC 5389](https://tools.ietf.org/html/rfc5389).</span></span>

<span data-ttu-id="3dbb5-121">RFC 5389에서 요구하는 SBC는 인식할 수 없는 STUN 특성을 무시하고 알려진 특성으로 메시지를 계속 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-121">The SBCs as required by RFC 5389 must ignore any STUN attributes that they do not recognize, and continue to process the messages with the known attributes.</span></span> 

<span data-ttu-id="3dbb5-122">변형된 패킷이 수신되는 경우 미디어 세션 설치에 영향을주지 않고 패킷을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-122">If any malformed packets are received, the packets must be discarded without impacting the media session establishment.</span></span>

## <a name="ice-lite-requirements"></a><span data-ttu-id="3dbb5-123">ICE Lite 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3dbb5-123">ICE Lite requirements</span></span>

<span data-ttu-id="3dbb5-124">이 섹션에서는 ICE Lite에 대한 요구 사항을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-124">This section briefly captures the requirements for ICE Lite.</span></span>

### <a name="candidate-gathering"></a><span data-ttu-id="3dbb5-125">후보자 모임</span><span class="sxs-lookup"><span data-stu-id="3dbb5-125">Candidate gathering</span></span>

<span data-ttu-id="3dbb5-126">SBC는 공개적으로 도달할 수 있는 하나의 후보만 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-126">The SBC must offer only one candidate that is publicly reachable.</span></span> <span data-ttu-id="3dbb5-127">현재 IPV4 후보만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-127">Currently, only IPV4 candidates are supported.</span></span>


#### <a name="connectivity-checks"></a><span data-ttu-id="3dbb5-128">연결 확인</span><span class="sxs-lookup"><span data-stu-id="3dbb5-128">Connectivity checks</span></span>

<span data-ttu-id="3dbb5-129">ICE Lite 구현은 수신된 모든 연결 검사에 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-129">The ICE Lite implementation must respond to any connectivity checks received.</span></span> <span data-ttu-id="3dbb5-130">ICE Lite 엔드포인트는 연결 확인 요청을 보내면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-130">The ICE Lite endpoint must not send any connectivity check requests.</span></span> <span data-ttu-id="3dbb5-131">(연결 검사가 위반으로 전송되는 경우 전체 구현이 응답하여 예기치 않은 피어 파생 후보가 검색되고 호출 실패가 발생할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="3dbb5-131">(If connectivity checks are sent in violation, the full implementation will respond, which can result in unexpected peer-derived candidates being discovered and potentially result in call failures.)</span></span>

#### <a name="nominations"></a><span data-ttu-id="3dbb5-132">후보</span><span class="sxs-lookup"><span data-stu-id="3dbb5-132">Nominations</span></span>

<span data-ttu-id="3dbb5-133">ICE 전체 구현 엔드포인트는 항상 제어 엔드포인트가 며 미디어 흐름에 사용할 최종 후보를 선택하는 "일반" 지명을 따르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-133">The ICE full implementation endpoint will always be the Controlling endpoint, and will follow “Regular” nominations for selecting the final candidates to be used for media flow.</span></span> <span data-ttu-id="3dbb5-134">ICE Lite 엔드포인트는 지명을 사용하여 미디어에 사용할 경로를 마무리하고 통화를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-134">The ICE Lite endpoint can use the nominations to conclude the path to be used for media and complete call establishment.</span></span>

<span data-ttu-id="3dbb5-135">참고: 183개 임시 답변을 보내는 피어 엔드포인트를 사용하는 포크의 경우 SBC는 200OK 전에 지명이 발생하면 여러 엔드포인트의 검사 및 여러 엔드포인트의 지명에 응답할 준비가 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-135">Note: In the case of forking with peer endpoints sending 183 provisional answers, the SBC must be ready to respond to checks from multiple endpoints and also nominations from multiple endpoints if the nominations happen before 200OK.</span></span> <span data-ttu-id="3dbb5-136">사용자의 최종 경로 및 응답 타이밍에 있는 ICE 상태 머신의 수렴에 따라 200OK 전후에 지명될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-136">Depending on the convergence of the ICE state machine on the final path and timing of the user answering, the nominations can happen before or after 200OK.</span></span> <span data-ttu-id="3dbb5-137">SBC는 두 사례를 모두 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-137">The SBC must be able to handle both cases.</span></span>

#### <a name="converging-for-forking"></a><span data-ttu-id="3dbb5-138">포크 수렴</span><span class="sxs-lookup"><span data-stu-id="3dbb5-138">Converging for forking</span></span>

<span data-ttu-id="3dbb5-139">SBC 포크에서 여러 엔드포인트로의 Teams 엔드포인트가 Teams 응답하고 연결 검사를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-139">If the offer from the SBC forks to multiple Teams endpoints, the Teams endpoints may respond with a provisional answer and start connectivity checks.</span></span> <span data-ttu-id="3dbb5-140">SBC는 연결 검사를 수신하고 여러 피어 엔드포인트에서 연결 검사에 응답할 준비가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-140">The SBC must be prepared to receive connectivity checks and respond to connectivity checks from multiple peer endpoints.</span></span> <span data-ttu-id="3dbb5-141">예를 들어 데스크톱 Teams 휴대폰에 모두 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-141">For example, the Teams user could be signed on to both a desktop and a cell phone.</span></span> <span data-ttu-id="3dbb5-142">두 디바이스 모두 인바운드 호출에 대한 알림을 제공하고 SBC를 통해 연결 검사를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-142">Both devices will be notified of the inbound call and will attempt connectivity checks with the SBC.</span></span>

<span data-ttu-id="3dbb5-143">결국 엔드포인트 중 하나만 호출에 응답합니다(200OK).</span><span class="sxs-lookup"><span data-stu-id="3dbb5-143">Eventually only one of the endpoints will answer the call (200OK).</span></span> <span data-ttu-id="3dbb5-144">200OK를 수신할 때 SBC는 미디어 패킷을 처리하는 데 적합한 컨텍스트를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-144">On receiving the 200OK, the SBC can set up the right context for processing the media packets.</span></span>

## <a name="scenarios"></a><span data-ttu-id="3dbb5-145">시나리오</span><span class="sxs-lookup"><span data-stu-id="3dbb5-145">Scenarios</span></span>

###  <a name="inbound-call-from-sbc"></a><span data-ttu-id="3dbb5-146">SBC에서 인바운드 호출</span><span class="sxs-lookup"><span data-stu-id="3dbb5-146">Inbound call from SBC</span></span>

<span data-ttu-id="3dbb5-147">이 시나리오의 경우 SBC에서 처리해야 하는 몇 가지 피어 엔드포인트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-147">For this scenario, there are several possible peer endpoints that the SBC must handle:</span></span>

- <span data-ttu-id="3dbb5-148">서버 엔드포인트는 일반적으로 200OK로 직접 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-148">Server endpoints will typically respond directly with 200OK.</span></span> <span data-ttu-id="3dbb5-149">일반적으로 Voicemail, 통화 큐 및 자동 참석 시나리오에 관련된 전체 ICE 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-149">These are full ICE endpoints that are typically involved in Voicemail, Call queue, and Auto attendant scenarios.</span></span>

- <span data-ttu-id="3dbb5-150">클라이언트 엔드포인트는 다른 From/To 태그(183)와 통화에 응답하는 엔드포인트에서 200OK를 사용하여 여러 임시 답변을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-150">Client endpoints can send multiple provisional answers with different From/To tags (183) followed by a 200OK from the endpoint that answers the call.</span></span> <span data-ttu-id="3dbb5-151">일반적으로 최종 사용자 클라이언트를 나타내는 전체 ICE 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-151">These are full ICE endpoints typically representing end user clients.</span></span>

- <span data-ttu-id="3dbb5-152">다른 SBC 엔드포인트.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-152">Other SBC endpoints.</span></span> <span data-ttu-id="3dbb5-153">일반적으로 클라이언트 엔드포인트와 다른 전화 번호를 동시에 울리는 시나리오에 관련된 ICE Lite 엔드포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-153">These are ICE Lite endpoints typically involved in the scenario of simultaneously ringing client endpoints and another phone number(s).</span></span>

<span data-ttu-id="3dbb5-154">SBC는 전체 ICE 엔드포인트에서 수신된 모든 유효한 연결 검사 요청에 응답해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-154">The SBC must respond to all valid connectivity check requests received from the full ICE endpoints.</span></span> <span data-ttu-id="3dbb5-155">RFC당 전체 ICE 엔드포인트가 제어 엔드포인트가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-155">Per RFC, the full ICE endpoints will become Controlling endpoints.</span></span> <span data-ttu-id="3dbb5-156">Teams(클라이언트/서버) 엔드포인트는 "일반" 지명을 수행하여 연결 검사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-156">The Teams (client/server) endpoints will perform “Regular” nominations to complete connectivity checks.</span></span> <span data-ttu-id="3dbb5-157">최종 200Ok는 초기 미디어를 전송한 엔드포인트 또는 다른 엔드포인트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-157">The final 200Ok can either be from an endpoint that sent early media or from a different endpoint.</span></span> <span data-ttu-id="3dbb5-158">200Ok를 수신할 때 SBC는 미디어 흐름에 적합한 컨텍스트를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-158">On receiving the 200Ok, the SBC must set up the right context for media flow.</span></span> 

###  <a name="early-media"></a><span data-ttu-id="3dbb5-159">초기 미디어</span><span class="sxs-lookup"><span data-stu-id="3dbb5-159">Early media</span></span>

<span data-ttu-id="3dbb5-160">초기 미디어 흐름이 있는 경우 SBC는 스트리밍 미디어를 시작하는 첫 번째 엔드포인트로 래치해야 합니다. 후보가 지명되기 전에 미디어 흐름을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-160">If there is early media flow, the SBC must latch to the first endpoint that starts streaming media; media flow can start before candidates are nominated.</span></span> <span data-ttu-id="3dbb5-161">SBC는 IVR/voicemail 시나리오를 사용하도록 설정하기 위해 이 단계에서 DTMF를 보내기 위한 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-161">The SBC should have support for sending DTMF during this phase to enable IVR/voicemail scenarios.</span></span> <span data-ttu-id="3dbb5-162">SBC는 지명을 완료하지 않은 경우 확인을 받은 가장 높은 우선 순위 경로를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-162">The SBC should use the highest priority path on which it has received checks if nominations have not completed.</span></span>

### <a name="outbound-call-to-sbc"></a><span data-ttu-id="3dbb5-163">SBC에 대한 아웃바운드 호출</span><span class="sxs-lookup"><span data-stu-id="3dbb5-163">Outbound call to SBC</span></span>

<span data-ttu-id="3dbb5-164">Teams 엔드포인트는 이 시나리오의 호출자이며 제어 엔드포인트가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-164">The Teams endpoints are the Caller for this scenario and will be the Controlling Endpoint.</span></span> <span data-ttu-id="3dbb5-165">임시 답변(183) 또는 최종 답변(200OK)을 수신할 때 Teams 엔드포인트는 연결 검사를 시작하고 "일반" 지명을 진행하여 연결 검사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-165">On receiving either a provisional answer (183) or a final answer(200OK), the Teams endpoint  will start connectivity checks and proceed to “Regular” nominations to complete the connectivity checks.</span></span>

<span data-ttu-id="3dbb5-166">참고: SBC에서 잠정 답변(183)을 보내는 경우 SBC는 SBC에서 200OK를 보내기 전에 연결 검사 요청을 수신하고 지명을 완료할 준비가 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-166">Note: If the SBC sends a provisional answer (183), the SBC must be ready to receive connectivity check requests and potentially complete the nominations  before the 200OK is sent by the SBC.</span></span> <span data-ttu-id="3dbb5-167">200OK가 수신되기 전에 확인 및/또는 지명을 완료하면 200OK가 수신된 후 다시 검사 및/또는 지명이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-167">If checks and/or nominations are completed before the 200OK is received, checks and/or nominations will not be performed again after 200OK is received.</span></span> <span data-ttu-id="3dbb5-168">SBC는 183에서 200 사이의 ICE 후보, 암호 및 ufrag(사용자 이름 조각)를 변경하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-168">The SBC must not change ICE candidates, password, and ufrag (username fragment) between 183 and 200.</span></span>

<span data-ttu-id="3dbb5-169">초기 미디어를 지원하기 위해 SBC는 최종 엔드포인트에서 지명을 완료하기 전에 수신된 연결 검사에 따라 가장 높은 우선 순위를 가지는 피어 ICE 후보로 미디어 스트리밍을 시작할 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-169">To support early media, the SBC may start streaming the media to the peer ICE candidate, with the highest priority based on received connectivity checks, even before nominations are completed by Teams endpoint.</span></span> <span data-ttu-id="3dbb5-170">SBC는 후보가 완료될 Teams 모든 후보에 대한 미디어를 예상해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-170">The SBC should expect media from Teams on any candidate until nominations are completed.</span></span> <span data-ttu-id="3dbb5-171">후보가 지명되면 SBC는 미디어 패킷을 보내고 받기 위해 올바른 컨텍스트로 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-171">Once a candidate is nominated, the SBC must reset to the right context to send and receive media packets.</span></span>

## <a name="srtp-support-requirements"></a><span data-ttu-id="3dbb5-172">SRTP 지원 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3dbb5-172">SRTP support requirements</span></span>

<span data-ttu-id="3dbb5-173">SBC는 제품 및 답변을 위해 SRTP 암호화 AES_CM_128_HMAC_SHA1_80 암호화 암호화를 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-173">The SBC must support SRTP encryption cipher AES_CM_128_HMAC_SHA1_80 for offer and answer in the following format:</span></span>

```console
"inline:" <key||salt> ["|" lifetime]
```

<span data-ttu-id="3dbb5-174">다음은 SBC의 SDP 제품에서 암호화 특성의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-174">The following is an example of the crypto attribute in the SDP offer from the SBC:</span></span>

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

<span data-ttu-id="3dbb5-175">MKI 및 길이 매개 변수는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-175">MKI and Length parameters are not required.</span></span>

<span data-ttu-id="3dbb5-176">자세한 내용은 [RFC 4568, 섹션 6.1 을 참조하세요.](https://tools.ietf.org/html/rfc4568#section-6.1)</span><span class="sxs-lookup"><span data-stu-id="3dbb5-176">For more information, see [RFC 4568, section 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).</span></span>

## <a name="sdes-support-requirements"></a><span data-ttu-id="3dbb5-177">SDES 지원 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3dbb5-177">SDES support requirements</span></span>

<span data-ttu-id="3dbb5-178">디바이스는 아래 설명된 형식으로 SDES를 제공할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-178">The device must be able to offer SDES in the format as described below.</span></span> <span data-ttu-id="3dbb5-179">Microsoft Media Processor는 항상 SDES를 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-179">Microsoft Media Processors always prefer SDES.</span></span>

- <span data-ttu-id="3dbb5-180">비미디어 우회를 통해 클라이언트가 DTLS만 지원하는 경우에도 Media Processor는 SDES로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-180">With non-media bypass, even if a client only supports DTLS, the Media Processors will convert to SDES.</span></span>

- <span data-ttu-id="3dbb5-181">미디어 우회를 사용하여 클라이언트가 DTLS(향후 Google Chrome 상태)인 경우 직접 라우팅은 경로에 MP를 삽입하여 미디어 우회에서 비미디어 우회로로 호출을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-181">With media bypass, if a client is DTLS only (future Google Chrome state), Direct Routing will insert an MP in the path, converting the call from media bypass to non-media bypass.</span></span> <span data-ttu-id="3dbb5-182">직접 라우팅의 SBC와 미디어 프로세서 구성 요소 간에는 SDES가 항상 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-182">Between the SBC and media processor component of Direct Routing, SDES is always used.</span></span>

<span data-ttu-id="3dbb5-183">현재 DTLS만 제공하는 Teams 클라이언트는 없습니다. 그러나 Google은 어떤 시점에 SDES 지원이 중지될 것으로 발표했습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-183">Currently, there are no Teams client that offer only DTLS; however Google has announced that at some point in time they will stop supporting SDES.</span></span>

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a><span data-ttu-id="3dbb5-184">우회 모드에서 SBC의 제품 서식</span><span class="sxs-lookup"><span data-stu-id="3dbb5-184">Format for offer from SBC in bypass mode</span></span> 

<span data-ttu-id="3dbb5-185">제품에는 SDES가 포함되어야 합니다. DTLS 선택적 형식은 다음 형식으로 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbb5-185">Offer must contain SDES and can contain DTLS optional in the following format:</span></span>

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a><span data-ttu-id="3dbb5-186">SDES가 포함된 SBC에 대한 답변 서식</span><span class="sxs-lookup"><span data-stu-id="3dbb5-186">Format for answer containing SDES to SBC</span></span>

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a><span data-ttu-id="3dbb5-187">SBC로의 Teams 형식</span><span class="sxs-lookup"><span data-stu-id="3dbb5-187">Format for offer from Teams to SBC</span></span> 

### <a name="format-for-sdes-only-offer-to-sbc"></a><span data-ttu-id="3dbb5-188">SDES에 대한 형식만 SBC에 제공</span><span class="sxs-lookup"><span data-stu-id="3dbb5-188">Format for SDES only offer to SBC</span></span>

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

