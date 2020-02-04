---
title: 비즈니스용 Skype 서버의 비디오 Interop 서버 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: '요약: 비즈니스용 Skype 서버를 타사 teleconferencing 장치와 통합 하기 위해 계획 하는 동안이 항목을 검토 하세요.'
ms.openlocfilehash: 5531fd60cc2aa28202903fcc4392fe7830bcdfa0
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684191"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="0edd9-103">비즈니스용 Skype 서버의 비디오 Interop 서버 계획</span><span class="sxs-lookup"><span data-stu-id="0edd9-103">Plan for Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="0edd9-104">**요약:** 비즈니스용 Skype 서버와 타사 teleconferencing 장치를 통합 하는 계획을 수립할 때이 항목을 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="0edd9-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with third-party teleconferencing devices.</span></span>
  
<span data-ttu-id="0edd9-105">이제 비즈니스용 Skype 서버를 사용 하 여 특정 타사 VTC (비디오 Teleconferencing System) 솔루션과 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-105">Skype for Business Server now allows you to integrate with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="0edd9-106">이 비디오 회의 상호 운용성을 가능 하 게 하는 새로운 서버 역할은 현재 온-프레미스 설치에만 사용할 수 있는 독립 실행형 서버 역할로 구현 되는 VIS (동영상 Interop 서버)입니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-106">The new server role that enables this video conferencing interoperability is the Video Interop Server (VIS), which is currently implemented as a standalone server role available only for on-premises installations.</span></span> <span data-ttu-id="0edd9-107">VIS는 타사의 원격 회의 시스템 및 비즈니스용 Skype 서버 배포 간에 중개 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-107">A VIS acts as an intermediary between a third party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="0edd9-108">이번 릴리스의 경우 VIS는 Cisco/Tandberg 영상 시스템과의 상호 운용성에 중점을 두었습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-108">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span> <span data-ttu-id="0edd9-109">비즈니스용 Skype 서버 설치에이 기능을 사용할지 여부를 결정 하려면이 문서를 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="0edd9-109">Review this article to determine whether to use this feature in your Skype for Business Server installation.</span></span>
  
## <a name="device-interoperability"></a><span data-ttu-id="0edd9-110">장치 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="0edd9-110">Device interoperability</span></span>

<span data-ttu-id="0edd9-111">VTCs는 cisco 통합 커뮤니케이션 관리자 (CallManager 또는 CUCM) 버전 10.5 및 TCP SIP trunks에서 CUCM와 VIS 간에 설정 된 Cisco를 통해 테스트 및 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-111">Interoperation is tested and supported with Cisco VTCs registering with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 and TCP SIP trunks set up between CUCM and the VIS.</span></span>
  
<span data-ttu-id="0edd9-112">현재 지원 되는 VTCs는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-112">The currently supported VTCs are:</span></span>
  
- <span data-ttu-id="0edd9-113">Cisco C40</span><span class="sxs-lookup"><span data-stu-id="0edd9-113">Cisco C40</span></span>
    
- <span data-ttu-id="0edd9-114">Cisco C60</span><span class="sxs-lookup"><span data-stu-id="0edd9-114">Cisco C60</span></span>
    
- <span data-ttu-id="0edd9-115">Cisco C90</span><span class="sxs-lookup"><span data-stu-id="0edd9-115">Cisco C90</span></span>
    
- <span data-ttu-id="0edd9-116">Cisco MX200</span><span class="sxs-lookup"><span data-stu-id="0edd9-116">Cisco MX200</span></span>
    
- <span data-ttu-id="0edd9-117">Cisco MX300</span><span class="sxs-lookup"><span data-stu-id="0edd9-117">Cisco MX300</span></span>
    
- <span data-ttu-id="0edd9-118">Cisco DX80</span><span class="sxs-lookup"><span data-stu-id="0edd9-118">Cisco DX80</span></span>
    
- <span data-ttu-id="0edd9-119">Cisco EX60</span><span class="sxs-lookup"><span data-stu-id="0edd9-119">Cisco EX60</span></span>
    
- <span data-ttu-id="0edd9-120">Cisco EX90</span><span class="sxs-lookup"><span data-stu-id="0edd9-120">Cisco EX90</span></span>
    
- <span data-ttu-id="0edd9-121">Cisco SX20</span><span class="sxs-lookup"><span data-stu-id="0edd9-121">Cisco SX20</span></span>
    
> [!NOTE]
>  <span data-ttu-id="0edd9-122">비즈니스용 Skype Server와 통합 하기 위해 이러한 시스템에서는 Cisco 소프트웨어 릴리스 TC 7.0.0 이상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-122">Cisco software release TC7.0.0 or above is required on these systems for integration with Skype for Business Server to work as expected.</span></span>
  
## <a name="sip-trunks"></a><span data-ttu-id="0edd9-123">SIP trunks</span><span class="sxs-lookup"><span data-stu-id="0edd9-123">SIP trunks</span></span>

<span data-ttu-id="0edd9-124">VTCs가 기존 Cisco 인프라에 계속 등록 되는 SIP 트렁크 모드의 비디오 Interop 서버 기능 (예: CUCM (Cisco Call Manager)).</span><span class="sxs-lookup"><span data-stu-id="0edd9-124">The Video Interop Server functions in SIP trunk mode, where the VTCs continue to register with the existing Cisco infrastructure - for example, Cisco Call Manager (CUCM).</span></span> <span data-ttu-id="0edd9-125">비디오 SIP 트렁크는 CUCM와 VIS 사이에 정의 되어 있으며, 두 시스템 간에 통화가 라우팅될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-125">A video SIP trunk is defined between CUCM and the VIS so that calls can be routed between the two systems.</span></span> <span data-ttu-id="0edd9-126">VTC에서 VIS로의 SIP 트렁크에 대 한 호출만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-126">Only calls over the SIP trunk from the VTC to the VIS are supported.</span></span> <span data-ttu-id="0edd9-127">따라서 VTCs는 비즈니스용 Skype 컨퍼런스 (자동 전화 교환과 연결 된 전화 번호로 전화를 걸고)로 전화를 걸 수 있지만, 회의에 끌어서 놓을 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-127">Thus, VTCs can dial into a Skype for Business conference (by dialing the phone number associated with the Call Automated Attendant), but cannot be dragged and dropped into the conference.</span></span>
  
![SfB의 VIS 다이어그램](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a><span data-ttu-id="0edd9-129">기능</span><span class="sxs-lookup"><span data-stu-id="0edd9-129">Features</span></span>

<span data-ttu-id="0edd9-130">이 서버 역할은 다음을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-130">This server role provides:</span></span>
  
- <span data-ttu-id="0edd9-131">타사 비디오 시스템 및 비즈니스용 Skype 서버 배포에 사용 되는 .H 264 형식 간의 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-131">Conversion between the H.264 formats used by 3rd party video systems and the Skype for Business Server deployment.</span></span>
    
- <span data-ttu-id="0edd9-132">VTC에서 지정 된 해상도의 단일 비디오 스트림을 비즈니스용 Skype 서버 배포에 사용 되는 다른 해상도의 여러 simulcast 스트림으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-132">Conversion of a single video stream at a given resolution from a VTC into multiple simulcast streams of different resolutions for use in the Skype for Business Server deployment.</span></span> <span data-ttu-id="0edd9-133">이러한 스트림은 AVMCU에 게 전송 된 다음 다른 해결 방법을 요청한 비즈니스용 Skype 서버 끝점 및 기타 영상 시스템으로 보내질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-133">These streams can be sent to the AVMCU and then to Skype for Business Server endpoints and other video systems that have requested different resolutions.</span></span> <span data-ttu-id="0edd9-134">이 변환은 타사 영상 시스템을 비즈니스용 Skype A/V 컨퍼런스 통화에 참여 하는 경우에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-134">This conversion is also used when the third party video system is involved in a Skype for Business A/V conference call.</span></span> <span data-ttu-id="0edd9-135">특정 VIS 서버에서 코드 변환 제한에 도달 하면 다른 해결 방법에 대 한 다음 요청은 해상도가 가장 낮은 스트림만 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-135">Once the transcoding limit is reached in a particular VIS server, any following requests for different resolutions will only receive a stream with the lowest resolution.</span></span> 
    
- <span data-ttu-id="0edd9-136">CUCM 게이트웨이와 비즈니스용 Skype Server 비디오 Interop 서버 간 비디오 SIP 트렁크 지원 VTCs 계속 Cisco 게이트웨이에 등록 하 고 게이트웨이를 통해 비즈니스용 Skype 배포에 대 한 통화를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-136">Support for a video SIP trunk between the CUCM gateway and a Skype for Business Server Video Interop Server; VTCs continue to register with the Cisco gateway, and initiate calls to the Skype for Business deployment through the gateway.</span></span> <span data-ttu-id="0edd9-137">통화는 게이트웨이에서 비디오 SIP 트렁크로 Skype for 비즈니스용 비디오 Interop 서버로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-137">Calls are routed from the gateway to the Skype for Business Video Interop Server over the video SIP trunk.</span></span>
    
- <span data-ttu-id="0edd9-138">시스템에서 전화를 걸어 열려 있거나 종료 된 회의에 참가할 수 있는 지원 되는 비디오 시스템을 사용 하 여 회의실의 사용자 지원</span><span class="sxs-lookup"><span data-stu-id="0edd9-138">Support for a user in a conference room with a supported video system to dial from that system to join an open or closed conference.</span></span> <span data-ttu-id="0edd9-139">이 통화는 비디오 SIP 트렁크를 통과 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-139">This call will traverse the video SIP trunk.</span></span>
    
- <span data-ttu-id="0edd9-140">비즈니스용 Skype 클라이언트에 게 전화를 걸 수 있는 지원 되는 비디오 시스템을 사용 하 여 회의실의 사용자 지원</span><span class="sxs-lookup"><span data-stu-id="0edd9-140">Support for a user in a conference room with a supported video system to call a Skype for Business client.</span></span> <span data-ttu-id="0edd9-141">통화가 SIP 트렁크를 통과 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-141">The call will traverse the SIP trunk.</span></span>
    
- <span data-ttu-id="0edd9-142">비즈니스용 Skype 서버 쪽 또는 지원 되는 VTC 시스템 (음소거/음소거 해제, 비디오 일시 중지/다시 시작, 비디오 잠금, 보류/제거 통화)에 대 한 지원이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-142">Support for mid-call control from the Skype for Business Server side or from the supported VTC system for both point to point and multipoint calls including mute/un-mute audio, pause/resume video, lock video, and hold/un-hold call.</span></span>
    
## <a name="known-limitations"></a><span data-ttu-id="0edd9-143">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="0edd9-143">Known limitations</span></span>

<span data-ttu-id="0edd9-144">이 서버 역할에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-144">This server role has the following limitations:</span></span>
  
- <span data-ttu-id="0edd9-145">비즈니스용 Skype 배포에서 비디오 SIP 트렁크를 통해 VTCs에 대 한 새로운 통화는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-145">New calls from the Skype for Business deployment to the VTCs over the video SIP trunk are not supported.</span></span> <span data-ttu-id="0edd9-146">.</span><span class="sxs-lookup"><span data-stu-id="0edd9-146">.</span></span> <span data-ttu-id="0edd9-147">즉, 비디오 SIP 트렁크에서 VTCs의 비즈니스용 Skype 배포에 대 한 새로운 호출만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-147">This means that only new calls from the VTCs into the Skype for Business deployment are supported over the video SIP trunk.</span></span> <span data-ttu-id="0edd9-148">지원 되는 비디오 시스템에 대 한 현재 상태는 비디오 SIP 트렁크에서 VIS에 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-148">Presence for the supported video system will not be available over the video SIP trunk to the VIS.</span></span> 
    
- <span data-ttu-id="0edd9-149">비디오 SIP 트렁크 모드에서는 독립 실행형 VIS 풀만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-149">Only a standalone VIS pool will be supported for video SIP trunk mode.</span></span>
    
-  <span data-ttu-id="0edd9-150">TLS + SRTP 또는 TCP + RTP는 비디오 SIP 트렁크를 통해 VTC와 VIS 간 통신에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-150">TLS + SRTP or TCP + RTP will be supported for communications between the VTC and VIS over the video SIP trunk.</span></span>
    
- <span data-ttu-id="0edd9-151">응용 프로그램 공유가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-151">Application sharing is not supported.</span></span> <span data-ttu-id="0edd9-152">회의실의 비즈니스용 Skype 사용자는 비즈니스용 Skype 컨퍼런스 (예: 랩톱)에 참가 하 고 VTC에 연결 되지 않은 회의실의 무료 모니터 중 하나에 앱 공유 화면을 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-152">A Skype for Business user in the conference room needs to join the Skype for Business conference (via a laptop for example) and display the app sharing screens on one of the free monitors in the conference room not associated with the VTC.</span></span>
    
- <span data-ttu-id="0edd9-153">VTC가 VIS를 통해 페더레이션된 모임에 참가할 수 있는 기능은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-153">The ability for a VTC to join a federated meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="0edd9-154">VTC가 VIS를 통해 온라인 모임에 참가할 수 있는 기능은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-154">The ability for a VTC to join an online meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="0edd9-155">VTC에서 VIS를 통해 PSTN으로 거는 호출은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-155">Calls from a VTC to the PSTN via VIS are not supported.</span></span>
    
- <span data-ttu-id="0edd9-156">PSTN에서 VIS를 통해 VTC로 거는 호출은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-156">Calls from the PSTN to a VTC via VIS are not supported.</span></span>
    
## <a name="resiliency-mechanisms"></a><span data-ttu-id="0edd9-157">복원 메커니즘</span><span class="sxs-lookup"><span data-stu-id="0edd9-157">Resiliency mechanisms</span></span>
<span data-ttu-id="0edd9-158"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="0edd9-158"><a name="resiliency"> </a></span></span>

<span data-ttu-id="0edd9-159">VIS는 비디오 SIP 트렁크를 통해 운반 된 CUCM에서 걸려오는 전화를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-159">The VIS supports incoming calls from a CUCM that are carried over a video SIP trunk.</span></span> <span data-ttu-id="0edd9-160">업스트림 또는 다운스트림에 대 한 연결이 끊어질 수 있으므로 강력한 탄력성을 위해 두 가지 가능성을 모두 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-160">It's possible to lose connectivity either upstream or downstream, so for robust resiliency consider both possibilities:</span></span>
  
1. <span data-ttu-id="0edd9-161">**VIS 풀 장애 조치** 비디오 게이트웨이가 가리키는 기본 VIS 풀이 작동 하지 않는 경우 비디오 게이트웨이가 두 개 이상의 VIS 풀로 trunks를 정의한 경우 복구 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-161">**VIS Pool Failover** If the main VIS pool that the video gateway points to is down, recovery is possible if the video gateway has defined trunks to two (or more) VIS pools.</span></span> <span data-ttu-id="0edd9-162">비디오 게이트웨이에서 기본 VIS 풀로 전화를 걸 수 없는 것으로 판단 되는 경우에는 단순히 보조 VIS 풀로 착신 경로를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-162">If the video gateway determines it cannot make calls to the primary VIS pool, it simply routes the calls to a secondary VIS pool.</span></span>
    
     ![VIS 풀 장애 조치 다이어그램](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    <span data-ttu-id="0edd9-164">특정 VIS 풀은 여러 게이트웨이에 trunks 수 있지만, 일반적으로 특정 게이트웨이는 여러 VIS 풀에 trunks 수 없으므로 이러한 장애 조치를 지원 하기 위해 트릭을 수행 해야 합니다. DNS에서 두 FDQNs을 정의 하 여 비디오 게이트웨이의 동일한 IP 주소로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-164">A particular VIS pool can have trunks to multiple gateways, but normally a particular gateway can't have trunks to multiple VIS pools, so a trick needs to be done to support this failover: Define 2 FDQNs in DNS which resolve to the same IP address of a video gateway.</span></span> <span data-ttu-id="0edd9-165">각 비디오 게이트웨이에서 다른 VIS 풀로 트렁크를 보유 하 고 있으며 이제 복구가 가능 하는 토폴로지 문서에서 각 FQDN을 별도의 비디오 게이트웨이로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-165">Represent each FQDN as a separate video gateway in the Topology Document where each video gateway has a trunk to a different VIS pool, and recovery is now possible.</span></span> <span data-ttu-id="0edd9-166">TLS를 사용 하는 경우에는 여러 이름이 비디오 게이트웨이 인증서의 SAN에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-166">(If TLS is used, the multiple names will need to be in the SAN of the video gateway certificate.)</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0edd9-167">VIS는 토폴로지 문서에 구성 된 게이트웨이에서 수신 호출만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-167">VIS only allows incoming calls from gateways configured in the Topology Document.</span></span> 
  
2. <span data-ttu-id="0edd9-168">**프론트 엔드 장애 조치** VIS 풀이 CUCM에서 전화를 받지만 기본 다음 홉 등록자 또는 프런트 엔드 풀에 도달할 수 없는 경우에는 통화가 백업 프런트 엔드 풀로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-168">**Front End failover** If a VIS pool receives a call from CUCM but cannot reach its primary next-hop Registrar or Front End pool, calls are routed to a backup Front End pool.</span></span>
    
     ![프런트 엔드 장애 조치 다이어그램](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    <span data-ttu-id="0edd9-170">VIS는 기본 프런트 엔드 풀 및 해당 백업 프런트 엔드 풀의 상태를 추적 합니다 (이 설정은 토폴로지 문서의 등록자 서비스에 대 한 백업 설정에 있음).</span><span class="sxs-lookup"><span data-stu-id="0edd9-170">The VIS will keep track of the status of its primary Front End pool and its backup Front End pool (the setting is found in the backup setting for the Registrar service in the Topology Document).</span></span> <span data-ttu-id="0edd9-171">이 옵션은 두 풀에 1 분에 한 번만 투표 하 고 다섯 개의 연속 된 실패가 있으면 VIS는 특정 프론트 엔드 풀이 중단 되었다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-171">It sends Options polls once a minute to both pools, and if there are five consecutive failures the VIS assumes that a particular Front End pool is down.</span></span> <span data-ttu-id="0edd9-172">기본 프런트 엔드 풀이 down으로 표시 되어 있고 사용 가능한 구성 된 백업이 있는 경우 VIS는 게이트웨이에서 새 통화를 백업 프런트 엔드 풀에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-172">If the primary Front End pool is marked as down and there is an available configured backup the VIS sends new calls from the gateway to the backup Front End pool.</span></span> <span data-ttu-id="0edd9-173">기본 프런트 엔드 풀이 다시 들어오면 VIS에서 새 통화에 기본 프런트 엔드 풀을 사용 하 여 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-173">Once the primary Front End pool comes back, the VIS will resume using the primary Front End pool for new calls.</span></span>
    
    <span data-ttu-id="0edd9-174">VIS는 또한 비디오 SIP 트렁크에서 전화를 걸 수 있도록 10 초의 타이머를 구현 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-174">The VIS will also implement a 10 second timer for calls from the video SIP trunk.</span></span> <span data-ttu-id="0edd9-175">기본 다음 홉 프런트 엔드 풀을 비디오 SIP 트렁크에서 전화를 거는 데 사용 했지만 기본 다음 홉 프런트 엔드 풀이이 타이머 값 내에 전송 된 초대에 대 한 일부 SIP 메시지 (100를 포함 하 여)에 응답 하지 않은 경우, 통화에 대 한 백업 다음 홉 프록시 구성 된 경우 hould을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-175">If the primary next-hop Front End pool was used for a call from the video SIP trunk, and the primary next-hop Front End pool did not answer with some SIP message (including 100 Trying) to the Invite sent to it within this timer value, the backup next-hop proxy for the call should be tried if configured.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0edd9-176">다음 홉을 먼저 시도한 경우에는 기본 백업이 다음에 시도 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-176">If the backup next hop was tried first, the primary will not be tried next.</span></span> 
  
    <span data-ttu-id="0edd9-177">또한 관리자는 Windows PowerShell 장애 조치 (failover) 명령을 사용 하 여 기본 프런트 엔드 풀에서 유지 관리를 수행 해야 하는 경우와 같이 VIS에서 백업 프런트 엔드 풀을 사용 하도록 강제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-177">The admin could also use the Windows PowerShell failover command to force VIS to use the backup Front End pool, for example, when maintenance has to be performed on the primary Front End pool.</span></span>
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a><span data-ttu-id="0edd9-178">동일한 게이트웨이 피어에 음성 및 비디오 Trunks의 공존</span><span class="sxs-lookup"><span data-stu-id="0edd9-178">Co-existence of Voice and Video Trunks to the Same Gateway Peer</span></span>
<span data-ttu-id="0edd9-179"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="0edd9-179"><a name="resiliency"> </a></span></span>

<span data-ttu-id="0edd9-180">비즈니스용 Skype 서버는 동일한 게이트웨이 피어를 사용 하는 음성 및 비디오 SIP trunks 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-180">Skype for Business Server supports having voice and video SIP trunks use the same gateway peer.</span></span> <span data-ttu-id="0edd9-181">따라서 동일한 CUCM 배포 시 중재 서버와 동영상 SIP trunks에 대 한 음성 SIP trunks를 VIS 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-181">So the same CUCM deployment could have voice SIP trunks to the Mediation Server and video SIP trunks to VIS.</span></span>
  
- <span data-ttu-id="0edd9-182">PSTN 게이트웨이는 음성 SIP trunks에 대 한 토폴로지 문서의 특정 FQDN으로 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-182">A PSTN Gateway will need to be defined with a particular FQDN in the Topology Document for the voice SIP trunks.</span></span>
    
- <span data-ttu-id="0edd9-183">PSTN 게이트웨이에 대 한 피어는 중재 서버가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-183">The peer to the PSTN Gateway will be the Mediation Server.</span></span>
    
- <span data-ttu-id="0edd9-184">여러 음성 trunks 필요한 경우 PSTN 게이트웨이에서 여러 중재 서버 풀로 스패닝을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-184">Multiple voice trunks can be defines spanning from a PSTN Gateway to multiple Mediation Server pools if necessary.</span></span>
    
- <span data-ttu-id="0edd9-185">비디오 게이트웨이는 PSTN 게이트웨이와 동일한 FQDN의 비디오 SIP 트렁크에 대 한 토폴로지 문서에서 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-185">A Video Gateway will need to be defined in the Topology Document for the video SIP trunk with the same FQDN as for the PSTN Gateway.</span></span>
    
- <span data-ttu-id="0edd9-186">비디오 게이트웨이의 피어가 VIS 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-186">The peer to the Video Gateway will be VIS.</span></span>
    
- <span data-ttu-id="0edd9-187">단일 영상 트렁크를 비디오 게이트웨이에서 특정 VIS 풀로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-187">A single video trunk can be defined from a Video Gateway to a particular VIS pool.</span></span>
    
- <span data-ttu-id="0edd9-188">CUCM는 음성 트렁크 및 영상 트렁크를 통해 착신 통화를 제대로 라우팅하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-188">CUCM will need to be configured to correctly route calls over the voice trunk vs. the video trunk.</span></span> <span data-ttu-id="0edd9-189">예를 들어 VTC에서 전화를 걸 때 특별 한 전화 번호를 사용할 수 있습니다. CUCM는이 다이얼 접두 번호를 VIS에 연결할 수 있으며, 적절 한 번역 규칙이 SIP 초대에서 VIS로이 접두어를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-189">For example, a special dial prefix could be used when dialing from the VTC; CUCM could associate this dial prefix with calls to VIS, and appropriate translation rules would strip this prefix from the SIP Invite to VIS.</span></span>
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a><span data-ttu-id="0edd9-190">이전 버전의 Lync를 사용 하 여 비즈니스용 Skype 릴리스에 VIS의 공존</span><span class="sxs-lookup"><span data-stu-id="0edd9-190">Co-existence of VIS in the Skype for Business Release with Previous Releases of Lync</span></span>
<span data-ttu-id="0edd9-191"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="0edd9-191"><a name="resiliency"> </a></span></span>

<span data-ttu-id="0edd9-192">VIS는 비즈니스용 Skype 배포의 일부로만 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-192">VIS can only be deployed as part of Skype for Business deployment.</span></span> <span data-ttu-id="0edd9-193">기존 배포의 일부인 Lync 2013 컨퍼런스 및 클라이언트와 상호 작용할 수 있습니다. 이러한 경우 VIS 풀은 VIS 풀의 다음 홉 인 등록자/FE 풀을 포함 하는 비즈니스용 Skype 배포에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-193">It can interoperate with Lync 2013 conferences and clients that are a part of an existing deployment; in those cases, the VIS pool will need to be part of a Skype for Business deployment that includes a Registrar/FE pool that is the next-hop for the VIS pool.</span></span>
  
<span data-ttu-id="0edd9-194">VIS는 RTV와 .H 간의 코드 변환을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-194">VIS does not support transcoding between RTV and H.264.</span></span> <span data-ttu-id="0edd9-195">프리 Lync 2013 클라이언트와 회의의 VTC 참가자 간에는 영상 상호 운영성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-195">There is no video interoperability between pre-Lync 2013 clients and VTC participants in a conference.</span></span>
  
<span data-ttu-id="0edd9-196">전화 회의 중에 Lync 2013 클라이언트를 사용 하면 모바일 클라이언트가 기준 스피커가 될 때 VTCs에서 비디오를 받지 않도록 하는 RTV를 통해 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-196">Having pre-Lync 2013 clients in a conference will cause mobile clients to send using RTV resulting in VTCs receiving no video when the mobile client becomes the dominant speaker.</span></span>
  
<span data-ttu-id="0edd9-197">비즈니스용 Skype 배포의 일부인 VIS에서 Lync 2013이 제대로 작동 하도록 하려면 lync 2013에서 Lync 2013 클라이언트, CAA 및 AVMCU를 업그레이드 하 여 VIS와 함께 작동 하도록 적절 한 CU (을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-197">In order for Lync 2013 to work correctly with VIS that is part of a Skype for Business deployment, Lync 2013 needs the appropriate CU to be applied that upgrades the Lync 2013 client, CAA, and AVMCU to work with VIS.</span></span>
  
<span data-ttu-id="0edd9-198">Lync 2013 및 비즈니스용 Skype 데스크톱 클라이언트와 VIS의 상호 운영성이 테스트 되었으며 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-198">Interoperability of VIS with Lync 2013 and Skype for Business desktop clients has been tested and is supported.</span></span>
  
<span data-ttu-id="0edd9-199">비 데스크톱 (Android, Ipad, Iphone, Windows Phone, LMX 등)과 VIS의 상호 운용성 VIS 릴리스가 테스트 되 고 지원 되는 시점에는 해당 앱 스토어에서 사용할 수 있는 비즈니스용 Skype 클라이언트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-199">Interoperability of VIS with non-desktop (Android, Ipad, Iphone, Windows Phone, LMX, etc.) Skype for Business clients available from the applicable Apps Store at the time of VIS release has been tested and is supported.</span></span>
  
## <a name="recovery-from-packet-loss-via-fec"></a><span data-ttu-id="0edd9-200">FEC를 통한 패킷 손실 복구</span><span class="sxs-lookup"><span data-stu-id="0edd9-200">Recovery from Packet Loss via FEC</span></span>
<span data-ttu-id="0edd9-201"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="0edd9-201"><a name="resiliency"> </a></span></span>

<span data-ttu-id="0edd9-202">패킷 손실에 대 한 복구를 돕기 위해 FEC을 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-202">FEC can be turned on to aid in recovery from packet loss.</span></span> <span data-ttu-id="0edd9-203">켜져 있는 경우 50% 이상의 비디오 대역폭이 VIS에서 VTC 방향으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-203">If turned on, 50% more video bandwidth will be used in the VIS to VTC direction.</span></span>
  
## <a name="vis-sizing-and-transcoding-costs"></a><span data-ttu-id="0edd9-204">VIS 크기 조정 및 코드 변환 비용</span><span class="sxs-lookup"><span data-stu-id="0edd9-204">VIS Sizing and Transcoding Costs</span></span>
<span data-ttu-id="0edd9-205"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="0edd9-205"><a name="resiliency"> </a></span></span>

<span data-ttu-id="0edd9-206">Cisco VTC에서 여러 simulcast 스트림으로 단일 비디오 스트림을 코드 변환 하는 것은 CPU 용량을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-206">Transcoding the single video streams from the Cisco VTC to multiple simulcast streams uses CPU capacity.</span></span> <span data-ttu-id="0edd9-207">약 16 개의 VTCs 비디오 코드 변환이 가능 합니다 (각 VTC의 720p 비디오 스트림이 720p, 360p, 180p)의 3 개의 개별 simulcast 스트림으로 트랜스 코딩 되는 것으로 가정 하 여 Lync 2013 권장 FE 플랫폼에 해당 하는 단일 VIS를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-207">Approximately 16 VTCs can have their video transcoded (assuming a 720p video stream from each VTC is transcoded into 3 separate simulcast streams at 720p, 360p, and 180p) in a single VIS running on the equivalent of the Lync 2013 recommended FE platform.</span></span> <span data-ttu-id="0edd9-208">코드 변환이 해제 되어 있으면 VIS CPU에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-208">If Transcoding is turned off, this will save on VIS CPU.</span></span> <span data-ttu-id="0edd9-209">그러나 VTC에서 VIS에 의해 요청 된 비디오 이미지는 비즈니스용 Skype 측의 모든 수신기를 충족 하는 가장 낮은 수준의 해상도입니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-209">However, the video image requested by VIS from the VTC will be the lowest common resolution to satisfy all receivers on the Skype for Business side.</span></span> <span data-ttu-id="0edd9-210">코드 변환 해제를 사용 하는 경우에도 비즈니스용 Skype 클라이언트가 VTCs에서 보낼 수 없는 특정 저해상도 해상도를 요청 하면 코드 변환이 활성화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-210">Note that even with transcoding off, transcoding may be activated when Skype for Business clients request certain low resolutions that VTCs cannot send.</span></span>
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a><span data-ttu-id="0edd9-211">영상 게이트웨이에서 VIS에 게 배포 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="0edd9-211">Call Distribution from the Video Gateway to VIS</span></span>
<span data-ttu-id="0edd9-212"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="0edd9-212"><a name="resiliency"> </a></span></span>

<span data-ttu-id="0edd9-213">배포는 CUCM 배포 메커니즘 중 하나를 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-213">Distribution is accomplished via one of the CUCM distribution mechanisms:</span></span>
  
- <span data-ttu-id="0edd9-214">DNS를 동적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-214">Dynamically using DNS.</span></span>
    
- <span data-ttu-id="0edd9-215">CUCM side에서는 각 트렁크가 VIS 풀의 다른 서버에서 종료 되는 개별 trunks 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-215">On the CUCM side, you can define individual trunks, where each trunk terminates on a different server in the VIS pool.</span></span> <span data-ttu-id="0edd9-216">CUCM는 다른 trunks에 걸친 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-216">CUCM will route calls across the different trunks.</span></span>
    
## <a name="no-hybrid-interoperability"></a><span data-ttu-id="0edd9-217">하이브리드 상호 운용성 없음</span><span class="sxs-lookup"><span data-stu-id="0edd9-217">No Hybrid Interoperability</span></span>
<span data-ttu-id="0edd9-218"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="0edd9-218"><a name="resiliency"> </a></span></span>

<span data-ttu-id="0edd9-219">온-프레미스 VIS를 통한 온라인 모임 VTCs에 대 한 지원은 비즈니스용 Skype에 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-219">Support for VTCs joining online meetings via on-premises VIS is not part of Skype for Business.</span></span>
  
## <a name="no-federation-support"></a><span data-ttu-id="0edd9-220">페더레이션 지원 없음</span><span class="sxs-lookup"><span data-stu-id="0edd9-220">No Federation Support</span></span>
<span data-ttu-id="0edd9-221"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="0edd9-221"><a name="resiliency"> </a></span></span>

<span data-ttu-id="0edd9-222">VIS를 통한 페더레이션된 모임 참가 VTCs에 대 한 지원은 비즈니스용 Skype에 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0edd9-222">Support for VTCs joining federated meetings via VIS is not part of Skype for Business.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0edd9-223">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0edd9-223">See also</span></span>
<span data-ttu-id="0edd9-224"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="0edd9-224"><a name="resiliency"> </a></span></span>

[<span data-ttu-id="0edd9-225">비즈니스용 Skype 서버에서 비디오 Interop 서버 배포</span><span class="sxs-lookup"><span data-stu-id="0edd9-225">Deploy Video Interop Server in Skype for Business Server</span></span>](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
