---
title: 비즈니스용 Skype 서버의 비디오 Interop 서버 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: '요약: 비즈니스용 Skype 서버를 타사 전화 회의 장치와 통합할 계획을 세우는 동안 이 항목을 검토합니다.'
ms.openlocfilehash: c14d92042922f30ca5dd43acce12d11ef50a8683
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831948"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="4428b-103">비즈니스용 Skype 서버의 비디오 Interop 서버 계획</span><span class="sxs-lookup"><span data-stu-id="4428b-103">Plan for Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="4428b-104">**요약:** 비즈니스용 Skype 서버를 타사 전화 회의 장치와 통합할 계획을 세우는 동안 이 항목을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="4428b-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with third-party teleconferencing devices.</span></span>
  
<span data-ttu-id="4428b-105">이제 비즈니스용 Skype 서버를 통해 특정 타사 VTC(Video Teleconferencing System) 솔루션과 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-105">Skype for Business Server now allows you to integrate with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="4428b-106">이 비디오 회의 상호 연산을 가능하게 하는 새로운 서버 역할은 VIS(Video Interop Server)입니다. VIS는 현재는온-프레미스 설치에만 사용할 수 있는 독립 실행형 서버 역할로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-106">The new server role that enables this video conferencing interoperability is the Video Interop Server (VIS), which is currently implemented as a standalone server role available only for on-premises installations.</span></span> <span data-ttu-id="4428b-107">VIS는 타사 전화 회의 시스템과 비즈니스용 Skype 서버 배포 간의 중간 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-107">A VIS acts as an intermediary between a third party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="4428b-108">이 릴리스의 경우 VIS는 Cisco/Tandberg 비디오 시스템과의 상호 운영에 중점을 두고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-108">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span> <span data-ttu-id="4428b-109">이 문서를 검토하여 비즈니스용 Skype 서버 설치에서 이 기능을 사용할지 여부를 결정하십시오.</span><span class="sxs-lookup"><span data-stu-id="4428b-109">Review this article to determine whether to use this feature in your Skype for Business Server installation.</span></span>
  
## <a name="device-interoperability"></a><span data-ttu-id="4428b-110">장치 상호 연결성</span><span class="sxs-lookup"><span data-stu-id="4428b-110">Device interoperability</span></span>

<span data-ttu-id="4428b-111">CUCM과 VIS 간에 설정된 Cisco Unified Communications Manager(CallManager 또는 CUCM) 버전 10.5 및 TCP SIP 트렁크에 등록된 Cisco VTC를 통해 상호 연산이 테스트되고 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-111">Interoperation is tested and supported with Cisco VTCs registering with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 and TCP SIP trunks set up between CUCM and the VIS.</span></span>
  
<span data-ttu-id="4428b-112">현재 지원되는 VTC는 다음을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-112">The currently supported VTCs are:</span></span>
  
- <span data-ttu-id="4428b-113">Cisco C40</span><span class="sxs-lookup"><span data-stu-id="4428b-113">Cisco C40</span></span>
    
- <span data-ttu-id="4428b-114">Cisco C60</span><span class="sxs-lookup"><span data-stu-id="4428b-114">Cisco C60</span></span>
    
- <span data-ttu-id="4428b-115">Cisco C90</span><span class="sxs-lookup"><span data-stu-id="4428b-115">Cisco C90</span></span>
    
- <span data-ttu-id="4428b-116">Cisco MX200</span><span class="sxs-lookup"><span data-stu-id="4428b-116">Cisco MX200</span></span>
    
- <span data-ttu-id="4428b-117">Cisco MX300</span><span class="sxs-lookup"><span data-stu-id="4428b-117">Cisco MX300</span></span>
    
- <span data-ttu-id="4428b-118">Cisco DX80</span><span class="sxs-lookup"><span data-stu-id="4428b-118">Cisco DX80</span></span>
    
- <span data-ttu-id="4428b-119">Cisco EX60</span><span class="sxs-lookup"><span data-stu-id="4428b-119">Cisco EX60</span></span>
    
- <span data-ttu-id="4428b-120">Cisco EX90</span><span class="sxs-lookup"><span data-stu-id="4428b-120">Cisco EX90</span></span>
    
- <span data-ttu-id="4428b-121">Cisco SX20</span><span class="sxs-lookup"><span data-stu-id="4428b-121">Cisco SX20</span></span>
    
> [!NOTE]
>  <span data-ttu-id="4428b-122">비즈니스용 Skype 서버와의 통합이 예상대로 작동하려면 이러한 시스템에 Cisco 소프트웨어 릴리스 TC7.0.0 이상이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-122">Cisco software release TC7.0.0 or above is required on these systems for integration with Skype for Business Server to work as expected.</span></span>
  
## <a name="sip-trunks"></a><span data-ttu-id="4428b-123">SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="4428b-123">SIP trunks</span></span>

<span data-ttu-id="4428b-124">Video Interop 서버는 VTC가 기존 Cisco 인프라(예: CUCM(Cisco Call Manager)에 계속 등록되는 SIP 트렁크 모드로 기능합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-124">The Video Interop Server functions in SIP trunk mode, where the VTCs continue to register with the existing Cisco infrastructure - for example, Cisco Call Manager (CUCM).</span></span> <span data-ttu-id="4428b-125">두 시스템 간에 통화를 라우팅할 수 있도록 CUCM과 VIS 간에 비디오 SIP 트렁크가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-125">A video SIP trunk is defined between CUCM and the VIS so that calls can be routed between the two systems.</span></span> <span data-ttu-id="4428b-126">VTC에서 VIS로의 SIP 트렁크 호출만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-126">Only calls over the SIP trunk from the VTC to the VIS are supported.</span></span> <span data-ttu-id="4428b-127">따라서 VTC는 비즈니스용 Skype 회의(전화 자동 전화 번호와 연결된 전화 번호로 전화 걸기)로 전화를 걸 수 있지만 전화 회의에 끌어서 놓을 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-127">Thus, VTCs can dial into a Skype for Business conference (by dialing the phone number associated with the Call Automated Attendant), but cannot be dragged and dropped into the conference.</span></span>
  
![SfB의 VIS 다이어그램](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a><span data-ttu-id="4428b-129">기능</span><span class="sxs-lookup"><span data-stu-id="4428b-129">Features</span></span>

<span data-ttu-id="4428b-130">이 서버 역할은 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-130">This server role provides:</span></span>
  
- <span data-ttu-id="4428b-131">제3자 비디오 시스템에서 사용하는 H.264 형식과 비즈니스용 Skype 서버 배포 간 변환.</span><span class="sxs-lookup"><span data-stu-id="4428b-131">Conversion between the H.264 formats used by 3rd party video systems and the Skype for Business Server deployment.</span></span>
    
- <span data-ttu-id="4428b-132">VTC에서 제공된 해상도의 단일 비디오 스트림을 비즈니스용 Skype 서버 배포에서 사용할 수 있는 서로 다른 해상도의 여러 시모캐스트 스트림으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-132">Conversion of a single video stream at a given resolution from a VTC into multiple simulcast streams of different resolutions for use in the Skype for Business Server deployment.</span></span> <span data-ttu-id="4428b-133">이러한 스트림은 AVMCU로 전송된 다음 다른 해상도를 요청한 비즈니스용 Skype 서버 끝점 및 기타 비디오 시스템으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-133">These streams can be sent to the AVMCU and then to Skype for Business Server endpoints and other video systems that have requested different resolutions.</span></span> <span data-ttu-id="4428b-134">이 변환은 타사 비디오 시스템이 비즈니스용 Skype A/V 회의 통화에 관련된 경우도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-134">This conversion is also used when the third party video system is involved in a Skype for Business A/V conference call.</span></span> <span data-ttu-id="4428b-135">특정 VIS 서버에서 코드 변환 제한에 도달하면 다른 해상도에 대한 다음 요청은 가장 낮은 해상도의 스트림만 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-135">Once the transcoding limit is reached in a particular VIS server, any following requests for different resolutions will only receive a stream with the lowest resolution.</span></span> 
    
- <span data-ttu-id="4428b-136">CUCM 게이트웨이와 비즈니스용 Skype 서버 비디오 Interop 서버 간의 비디오 SIP 트렁크 지원 VTC는 Cisco 게이트웨이에 계속 등록되고 게이트웨이를 통해 비즈니스용 Skype 배포에 대한 호출을 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-136">Support for a video SIP trunk between the CUCM gateway and a Skype for Business Server Video Interop Server; VTCs continue to register with the Cisco gateway, and initiate calls to the Skype for Business deployment through the gateway.</span></span> <span data-ttu-id="4428b-137">비디오 SIP 트렁크를 통해 게이트웨이에서 비즈니스용 Skype 비디오 Interop 서버로 통화가 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-137">Calls are routed from the gateway to the Skype for Business Video Interop Server over the video SIP trunk.</span></span>
    
- <span data-ttu-id="4428b-138">지원되는 비디오 시스템이 있는 회의실의 사용자가 해당 시스템에서 전화를 걸 수 있도록 지원하여 열려 있는 회의 또는 닫힌 전화 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-138">Support for a user in a conference room with a supported video system to dial from that system to join an open or closed conference.</span></span> <span data-ttu-id="4428b-139">이 호출은 비디오 SIP 트렁크를 트래버스합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-139">This call will traverse the video SIP trunk.</span></span>
    
- <span data-ttu-id="4428b-140">지원되는 비디오 시스템을 통해 비즈니스용 Skype 클라이언트에 전화를 걸 수 있는 회의실의 사용자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-140">Support for a user in a conference room with a supported video system to call a Skype for Business client.</span></span> <span data-ttu-id="4428b-141">호출이 SIP 트렁크를 트래버스합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-141">The call will traverse the SIP trunk.</span></span>
    
- <span data-ttu-id="4428b-142">비즈니스용 Skype 서버 쪽 또는 지원되는 VTC 시스템에서 오디오 음소거/음소거 해제, 비디오 일시 중지/다시 시작, 비디오 잠금 및 보류/보류 해제를 비롯한 지점 및 다중 지점 통화에 대해 지원되는 VTC 시스템의 중간 통화 제어가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-142">Support for mid-call control from the Skype for Business Server side or from the supported VTC system for both point to point and multipoint calls including mute/un-mute audio, pause/resume video, lock video, and hold/un-hold call.</span></span>
    
## <a name="known-limitations"></a><span data-ttu-id="4428b-143">알려진 제한</span><span class="sxs-lookup"><span data-stu-id="4428b-143">Known limitations</span></span>

<span data-ttu-id="4428b-144">이 서버 역할에는 다음과 같은 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-144">This server role has the following limitations:</span></span>
  
- <span data-ttu-id="4428b-145">비디오 SIP 트렁크를 통해 비즈니스용 Skype 배포에서 VTC로의 새 호출은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-145">New calls from the Skype for Business deployment to the VTCs over the video SIP trunk are not supported.</span></span> <span data-ttu-id="4428b-146">.</span><span class="sxs-lookup"><span data-stu-id="4428b-146">.</span></span> <span data-ttu-id="4428b-147">즉, VTC에서 비즈니스용 Skype 배포로의 새 호출만 비디오 SIP 트렁크를 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-147">This means that only new calls from the VTCs into the Skype for Business deployment are supported over the video SIP trunk.</span></span> <span data-ttu-id="4428b-148">지원되는 비디오 시스템의 현재 상태는 VIS에 대한 비디오 SIP 트렁크를 통해 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-148">Presence for the supported video system will not be available over the video SIP trunk to the VIS.</span></span> 
    
- <span data-ttu-id="4428b-149">비디오 SIP 트렁크 모드에 대해 독립 실행형 VIS 풀만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-149">Only a standalone VIS pool will be supported for video SIP trunk mode.</span></span>
    
-  <span data-ttu-id="4428b-150">비디오 SIP 트렁크를 통해 VTC와 VIS 간의 통신에 대해 TLS + SRTP 또는 TCP + RTP가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-150">TLS + SRTP or TCP + RTP will be supported for communications between the VTC and VIS over the video SIP trunk.</span></span>
    
- <span data-ttu-id="4428b-151">응용 프로그램 공유는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-151">Application sharing is not supported.</span></span> <span data-ttu-id="4428b-152">회의실의 비즈니스용 Skype 사용자는 노트북을 통해 비즈니스용 Skype 회의에 참가하고 VTC와 연결되지 않은 회의실의 무료 모니터 중 하나에 앱 공유 화면을 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-152">A Skype for Business user in the conference room needs to join the Skype for Business conference (via a laptop for example) and display the app sharing screens on one of the free monitors in the conference room not associated with the VTC.</span></span>
    
- <span data-ttu-id="4428b-153">VTC가 VIS를 통해 페더전된 모임에 참가하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-153">The ability for a VTC to join a federated meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="4428b-154">VTC가 VIS를 통해 온라인 모임에 참가하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-154">The ability for a VTC to join an online meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="4428b-155">VIS를 통해 VTC에서 PSTN으로의 호출은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-155">Calls from a VTC to the PSTN via VIS are not supported.</span></span>
    
- <span data-ttu-id="4428b-156">VIS를 통해 PSTN에서 VTC로의 호출은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-156">Calls from the PSTN to a VTC via VIS are not supported.</span></span>
    
## <a name="resiliency-mechanisms"></a><span data-ttu-id="4428b-157">탄력성 메커니즘</span><span class="sxs-lookup"><span data-stu-id="4428b-157">Resiliency mechanisms</span></span>
<span data-ttu-id="4428b-158"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="4428b-158"><a name="resiliency"> </a></span></span>

<span data-ttu-id="4428b-159">VIS는 비디오 SIP 트렁크를 통해 수행되는 CUCM에서 들어오는 호출을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-159">The VIS supports incoming calls from a CUCM that are carried over a video SIP trunk.</span></span> <span data-ttu-id="4428b-160">업스트림 또는 다운스트림 연결이 손실될 수 있으므로 강력한 탄성을 위해 다음 두 가지 가능성을 모두 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-160">It's possible to lose connectivity either upstream or downstream, so for robust resiliency consider both possibilities:</span></span>
  
1. <span data-ttu-id="4428b-161">**VIS 풀 장애 조치(failover)** 비디오 게이트웨이가 지점하는 기본 VIS 풀이 다운된 경우 비디오 게이트웨이가 두 개 이상의 VIS 풀에 트렁크를 정의한 경우 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-161">**VIS Pool Failover** If the main VIS pool that the video gateway points to is down, recovery is possible if the video gateway has defined trunks to two (or more) VIS pools.</span></span> <span data-ttu-id="4428b-162">비디오 게이트웨이가 기본 VIS 풀로 전화를 걸 수 없다고 판단하면 단순히 통화를 보조 VIS 풀로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-162">If the video gateway determines it cannot make calls to the primary VIS pool, it simply routes the calls to a secondary VIS pool.</span></span>
    
     ![VIS 풀 장애 조치(failover) 다이어그램](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    <span data-ttu-id="4428b-164">특정 VIS 풀에는 여러 게이트웨이에 대한 트렁크가 있을 수 있지만 일반적으로 특정 게이트웨이에는 여러 VIS 풀에 대한 트렁크가 있을 수 없습니다. 따라서 이 장애 조치(failover)를 지원하기 위해 트렁크를 수행해야 합니다. 비디오 게이트웨이의 동일한 IP 주소로 확인되는 DNS에 FDQNs 2개 정의</span><span class="sxs-lookup"><span data-stu-id="4428b-164">A particular VIS pool can have trunks to multiple gateways, but normally a particular gateway can't have trunks to multiple VIS pools, so a trick needs to be done to support this failover: Define 2 FDQNs in DNS which resolve to the same IP address of a video gateway.</span></span> <span data-ttu-id="4428b-165">각 비디오 게이트웨이에 다른 VIS 풀에 대한 트렁크가 있으며 이제 복구가 가능한 토폴로지 문서에서 각 FQDN을 별도의 비디오 게이트웨이로 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-165">Represent each FQDN as a separate video gateway in the Topology Document where each video gateway has a trunk to a different VIS pool, and recovery is now possible.</span></span> <span data-ttu-id="4428b-166">TLS를 사용하는 경우 여러 이름이 비디오 게이트웨이 인증서의 SAN에 와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-166">(If TLS is used, the multiple names will need to be in the SAN of the video gateway certificate.)</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4428b-167">VIS에서는 토폴로지 문서에 구성된 게이트웨이로부터의 수신 전화만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-167">VIS only allows incoming calls from gateways configured in the Topology Document.</span></span> 
  
2. <span data-ttu-id="4428b-168">**프런트 엔드 장애 조치(failover)** VIS 풀이 CUCM에서 전화를 받지만 기본 다음 홉 등록자 또는 프런트 엔드 풀에 도달할 수 없는 경우 통화가 백업 프런트 엔드 풀로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-168">**Front End failover** If a VIS pool receives a call from CUCM but cannot reach its primary next-hop Registrar or Front End pool, calls are routed to a backup Front End pool.</span></span>
    
     ![프런트 엔드 장애 조치(failover) 다이어그램](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    <span data-ttu-id="4428b-170">VIS는 기본 프런트 엔드 풀 및 해당 백업 프런트 엔드 풀의 상태를 추적합니다(설정은 토폴로지 문서의 등록자 서비스에 대한 백업 설정에 있습니다).</span><span class="sxs-lookup"><span data-stu-id="4428b-170">The VIS will keep track of the status of its primary Front End pool and its backup Front End pool (the setting is found in the backup setting for the Registrar service in the Topology Document).</span></span> <span data-ttu-id="4428b-171">옵션 폴링을 1분에 한 번 두 풀로 보내며, 5번 연속 오류가 발생하면 VIS에서 특정 프런트 엔드 풀이 다운된 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-171">It sends Options polls once a minute to both pools, and if there are five consecutive failures the VIS assumes that a particular Front End pool is down.</span></span> <span data-ttu-id="4428b-172">기본 프런트 엔드 풀이 다운된 것으로 표시되어 있으며 구성된 백업을 사용할 수 있는 경우 VIS는 게이트웨이에서 백업 프런트 엔드 풀로 새 호출을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-172">If the primary Front End pool is marked as down and there is an available configured backup the VIS sends new calls from the gateway to the backup Front End pool.</span></span> <span data-ttu-id="4428b-173">기본 프런트 엔드 풀이 다시 돌아오면 VIS는 새 통화에 대해 기본 프런트 엔드 풀을 사용하여 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-173">Once the primary Front End pool comes back, the VIS will resume using the primary Front End pool for new calls.</span></span>
    
    <span data-ttu-id="4428b-174">VIS는 비디오 SIP 트렁크에서 걸린 통화에 대해 10초의 시간도 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-174">The VIS will also implement a 10 second timer for calls from the video SIP trunk.</span></span> <span data-ttu-id="4428b-175">비디오 SIP 트렁크의 통화에 기본 다음 홉 프런트 엔드 풀이 사용되어 있으며 이 Timer value 내에서 초대에 전송된 초대에 대한 일부 SIP 메시지(시도 포함)에 기본 홉 프런트 엔드 풀이 응답하지 않은 경우 구성된 경우 통화에 대한 백업 다음 홉 프록시를 시도해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-175">If the primary next-hop Front End pool was used for a call from the video SIP trunk, and the primary next-hop Front End pool did not answer with some SIP message (including 100 Trying) to the Invite sent to it within this timer value, the backup next-hop proxy for the call should be tried if configured.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4428b-176">백업 다음 홉을 먼저 시도한 경우 기본 홉은 다음에 시도되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-176">If the backup next hop was tried first, the primary will not be tried next.</span></span> 
  
    <span data-ttu-id="4428b-177">또한 관리자는 기본 프런트 엔드 풀에서 유지 관리 작업을 Windows PowerShell VIS가 백업 프런트 엔드 풀을 강제로 사용하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-177">The admin could also use the Windows PowerShell failover command to force VIS to use the backup Front End pool, for example, when maintenance has to be performed on the primary Front End pool.</span></span>
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a><span data-ttu-id="4428b-178">동일한 게이트웨이 피어에 음성 및 비디오 트렁크 동시 사용</span><span class="sxs-lookup"><span data-stu-id="4428b-178">Co-existence of Voice and Video Trunks to the Same Gateway Peer</span></span>
<span data-ttu-id="4428b-179"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="4428b-179"><a name="resiliency"> </a></span></span>

<span data-ttu-id="4428b-180">비즈니스용 Skype 서버는 음성 및 비디오 SIP 트렁크가 동일한 게이트웨이 피어를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-180">Skype for Business Server supports having voice and video SIP trunks use the same gateway peer.</span></span> <span data-ttu-id="4428b-181">따라서 동일한 CUCM 배포에 중재 서버에 대한 음성 SIP 트렁크와 VIS에 대한 비디오 SIP 트렁크가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-181">So the same CUCM deployment could have voice SIP trunks to the Mediation Server and video SIP trunks to VIS.</span></span>
  
- <span data-ttu-id="4428b-182">음성 SIP 트렁크에 대한 토폴로지 문서의 특정 FQDN으로 PSTN 게이트웨이를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-182">A PSTN Gateway will need to be defined with a particular FQDN in the Topology Document for the voice SIP trunks.</span></span>
    
- <span data-ttu-id="4428b-183">PSTN 게이트웨이에 대한 피어는 중재 서버가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-183">The peer to the PSTN Gateway will be the Mediation Server.</span></span>
    
- <span data-ttu-id="4428b-184">필요한 경우 PSTN 게이트웨이에서 여러 중재 서버 풀로 스패닝되는 여러 음성 트렁크를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-184">Multiple voice trunks can be defines spanning from a PSTN Gateway to multiple Mediation Server pools if necessary.</span></span>
    
- <span data-ttu-id="4428b-185">비디오 게이트웨이는 PSTN 게이트웨이와 FQDN이 동일한 비디오 SIP 트렁크에 대한 토폴로지 문서에 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-185">A Video Gateway will need to be defined in the Topology Document for the video SIP trunk with the same FQDN as for the PSTN Gateway.</span></span>
    
- <span data-ttu-id="4428b-186">비디오 게이트웨이에 대한 피어는 VIS가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-186">The peer to the Video Gateway will be VIS.</span></span>
    
- <span data-ttu-id="4428b-187">비디오 게이트웨이에서 특정 VIS 풀로 단일 비디오 트렁크를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-187">A single video trunk can be defined from a Video Gateway to a particular VIS pool.</span></span>
    
- <span data-ttu-id="4428b-188">음성 트렁크와 비디오 트렁크를 통해 통화를 올바르게 라우팅하도록 CUCM을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-188">CUCM will need to be configured to correctly route calls over the voice trunk vs. the video trunk.</span></span> <span data-ttu-id="4428b-189">예를 들어 VTC에서 전화를 걸 때 특수한 전화 걸기 prefix를 사용할 수 있습니다. CUCM은 이 전화 걸기 온-프레미스를 VIS 호출과 연결할 수 있으며 적절한 변환 규칙에 따라 SIP Invite에서 VIS로의 이 번호가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-189">For example, a special dial prefix could be used when dialing from the VTC; CUCM could associate this dial prefix with calls to VIS, and appropriate translation rules would strip this prefix from the SIP Invite to VIS.</span></span>
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a><span data-ttu-id="4428b-190">Lync의 이전 릴리스와 함께 비즈니스용 Skype 릴리스에 VIS 동시 사용</span><span class="sxs-lookup"><span data-stu-id="4428b-190">Co-existence of VIS in the Skype for Business Release with Previous Releases of Lync</span></span>
<span data-ttu-id="4428b-191"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="4428b-191"><a name="resiliency"> </a></span></span>

<span data-ttu-id="4428b-192">VIS는 비즈니스용 Skype 배포의 일부로만 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-192">VIS can only be deployed as part of Skype for Business deployment.</span></span> <span data-ttu-id="4428b-193">기존 배포의 일부인 Lync 2013 회의 및 클라이언트와 상호 연결될 수 있습니다. 이러한 경우 VIS 풀은 VIS 풀의 다음 홉인 등록자/FE 풀을 포함하는 비즈니스용 Skype 배포에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-193">It can interoperate with Lync 2013 conferences and clients that are a part of an existing deployment; in those cases, the VIS pool will need to be part of a Skype for Business deployment that includes a Registrar/FE pool that is the next-hop for the VIS pool.</span></span>
  
<span data-ttu-id="4428b-194">VIS는 RTV와 H.264 간의 변환을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-194">VIS does not support transcoding between RTV and H.264.</span></span> <span data-ttu-id="4428b-195">Lync 2013 전 클라이언트와 회의에 참가한 VTC 참가자 간에는 비디오 상호운용성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-195">There is no video interoperability between pre-Lync 2013 clients and VTC participants in a conference.</span></span>
  
<span data-ttu-id="4428b-196">Lync 2013 전 클라이언트를 전화 회의에 두면 모바일 클라이언트가 RTV를 사용하여 전송되어 모바일 클라이언트가 주 강연자일 때 VTC가 비디오를 수신하지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-196">Having pre-Lync 2013 clients in a conference will cause mobile clients to send using RTV resulting in VTCs receiving no video when the mobile client becomes the dominant speaker.</span></span>
  
<span data-ttu-id="4428b-197">Lync 2013이 비즈니스용 Skype 배포의 일부인 VIS에서 제대로 작동하려면 Lync 2013 클라이언트, CAA 및 AVMCU가 VIS에서 작동하도록 업그레이드하는 적절한 CU를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-197">In order for Lync 2013 to work correctly with VIS that is part of a Skype for Business deployment, Lync 2013 needs the appropriate CU to be applied that upgrades the Lync 2013 client, CAA, and AVMCU to work with VIS.</span></span>
  
<span data-ttu-id="4428b-198">Lync 2013 및 비즈니스용 Skype 데스크톱 클라이언트와의 VIS 상호 연산이 테스트되고 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-198">Interoperability of VIS with Lync 2013 and Skype for Business desktop clients has been tested and is supported.</span></span>
  
<span data-ttu-id="4428b-199">비 데스크톱(Android, Ipad, Iphone, Windows Phone, LMX 등)과의 VIS 상호 운영성 VIS 릴리스 당시 해당 앱 스토어에서 사용할 수 있는 비즈니스용 Skype 클라이언트가 테스트되고 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-199">Interoperability of VIS with non-desktop (Android, Ipad, Iphone, Windows Phone, LMX, etc.) Skype for Business clients available from the applicable Apps Store at the time of VIS release has been tested and is supported.</span></span>
  
## <a name="recovery-from-packet-loss-via-fec"></a><span data-ttu-id="4428b-200">FEC를 통한 패킷 손실에서 복구</span><span class="sxs-lookup"><span data-stu-id="4428b-200">Recovery from Packet Loss via FEC</span></span>
<span data-ttu-id="4428b-201"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="4428b-201"><a name="resiliency"> </a></span></span>

<span data-ttu-id="4428b-202">FEC를 켜서 패킷 손실을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-202">FEC can be turned on to aid in recovery from packet loss.</span></span> <span data-ttu-id="4428b-203">이 설정이 켜져 있는 경우 VIS에서 VTC 방향으로 50% 더 많은 비디오 대역폭이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-203">If turned on, 50% more video bandwidth will be used in the VIS to VTC direction.</span></span>
  
## <a name="vis-sizing-and-transcoding-costs"></a><span data-ttu-id="4428b-204">VIS 크기 조정 및 변환 비용</span><span class="sxs-lookup"><span data-stu-id="4428b-204">VIS Sizing and Transcoding Costs</span></span>
<span data-ttu-id="4428b-205"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="4428b-205"><a name="resiliency"> </a></span></span>

<span data-ttu-id="4428b-206">Cisco VTC에서 여러 simulcast 스트림으로 단일 비디오 스트림을 변환하는 경우 CPU 용량이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-206">Transcoding the single video streams from the Cisco VTC to multiple simulcast streams uses CPU capacity.</span></span> <span data-ttu-id="4428b-207">약 16개의 VTC는 Lync 2013 권장 FE 플랫폼에서 실행되는 단일 VIS에서 각 VTC의 720p 비디오 스트림을 720p, 360p 및 180p의 3개의 별도 시뮬레이션 스트림으로 코드 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-207">Approximately 16 VTCs can have their video transcoded (assuming a 720p video stream from each VTC is transcoded into 3 separate simulcast streams at 720p, 360p, and 180p) in a single VIS running on the equivalent of the Lync 2013 recommended FE platform.</span></span> <span data-ttu-id="4428b-208">변환이 해제되어 있는 경우 VIS CPU에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-208">If Transcoding is turned off, this will save on VIS CPU.</span></span> <span data-ttu-id="4428b-209">그러나 VTC에서 VIS에서 요청한 비디오 이미지는 비즈니스용 Skype 쪽의 모든 수신기를 충족하기 위한 가장 낮은 공통 해상도가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-209">However, the video image requested by VIS from the VTC will be the lowest common resolution to satisfy all receivers on the Skype for Business side.</span></span> <span data-ttu-id="4428b-210">비즈니스용 Skype 클라이언트에서 VTC가 보낼 수 없는 저해상도를 요청하면 변환이 활성화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-210">Note that even with transcoding off, transcoding may be activated when Skype for Business clients request certain low resolutions that VTCs cannot send.</span></span>
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a><span data-ttu-id="4428b-211">비디오 게이트웨이에서 VIS로의 통화 배포</span><span class="sxs-lookup"><span data-stu-id="4428b-211">Call Distribution from the Video Gateway to VIS</span></span>
<span data-ttu-id="4428b-212"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="4428b-212"><a name="resiliency"> </a></span></span>

<span data-ttu-id="4428b-213">배포는 CUCM 배포 메커니즘 중 하나를 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-213">Distribution is accomplished via one of the CUCM distribution mechanisms:</span></span>
  
- <span data-ttu-id="4428b-214">DNS를 동적으로 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="4428b-214">Dynamically using DNS.</span></span>
    
- <span data-ttu-id="4428b-215">CUCM 쪽에서는 각 트렁크가 VIS 풀의 다른 서버에서 종료되는 개별 트렁크를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-215">On the CUCM side, you can define individual trunks, where each trunk terminates on a different server in the VIS pool.</span></span> <span data-ttu-id="4428b-216">CUCM은 여러 트렁크를 통해 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-216">CUCM will route calls across the different trunks.</span></span>
    
## <a name="no-hybrid-interoperability"></a><span data-ttu-id="4428b-217">하이브리드 상호프러 가능성 없음</span><span class="sxs-lookup"><span data-stu-id="4428b-217">No Hybrid Interoperability</span></span>
<span data-ttu-id="4428b-218"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="4428b-218"><a name="resiliency"> </a></span></span>

<span data-ttu-id="4428b-219">온라인 모임에 참가하는 VTC는 비즈니스용 Skype에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-219">Support for VTCs joining online meetings via on-premises VIS is not part of Skype for Business.</span></span>
  
## <a name="no-federation-support"></a><span data-ttu-id="4428b-220">페더전 지원 없음</span><span class="sxs-lookup"><span data-stu-id="4428b-220">No Federation Support</span></span>
<span data-ttu-id="4428b-221"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="4428b-221"><a name="resiliency"> </a></span></span>

<span data-ttu-id="4428b-222">VIS를 통해 페더링된 모임에 참가하는 VTC는 비즈니스용 Skype에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4428b-222">Support for VTCs joining federated meetings via VIS is not part of Skype for Business.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4428b-223">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4428b-223">See also</span></span>
<span data-ttu-id="4428b-224"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="4428b-224"><a name="resiliency"> </a></span></span>

[<span data-ttu-id="4428b-225">비즈니스용 Skype 서버에서 비디오 Interop 서버 배포</span><span class="sxs-lookup"><span data-stu-id="4428b-225">Deploy Video Interop Server in Skype for Business Server</span></span>](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
