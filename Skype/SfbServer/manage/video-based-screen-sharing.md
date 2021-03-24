---
title: 비즈니스용 Skype 서버에 대한 비디오 기반 화면 공유
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: VbSS(비디오 기반 화면 공유)에 대한 비즈니스용 Skype 서버 계획 및 구성 정보
ms.openlocfilehash: 9d2466a314876a4ce576727c7673474003994365
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103064"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="12162-103">비즈니스용 Skype 서버에 대한 비디오 기반 화면 공유</span><span class="sxs-lookup"><span data-stu-id="12162-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="12162-104">비즈니스용 Skype 서버 2015의 VbSS(비디오 기반 화면 공유)를 다운로드할 수 있습니다. 비즈니스용 [Skype 서버 2015 누적 업데이트 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690).</span><span class="sxs-lookup"><span data-stu-id="12162-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690).</span></span> <span data-ttu-id="12162-105">VbSS는 비즈니스용 Skype 서버 2019에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="12162-106">비디오 기반 화면 공유 또는 VbSS는 Lync 화면 공유에서 증가했습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="12162-107">VbSS와 기존 화면 공유의 차이는 사용되는 프로토콜과 이러한 프로토콜이 Excel을 사용하는 경우와 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="12162-108">화면 공유는 사용자 컴퓨터 간에 수천 개의 일대일 세션을 만드는 데 매우 좋은 RDP(원격 데스크톱 프로토콜)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="12162-109">새로운 기술인 VbSS는 UDP(User Datagram Protocol)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="12162-110">비즈니스용 Skype 서버는 사용자 일대일 및 일대다(다대다) 대화 및 모임 환경을 개선하기를 원했습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="12162-111">VbSS는 비디오 시작 시간, 시청하는 보기 품질(특히 시청하는 것이 빠르게 이동하는 경우) 및 전반적인 안정성을 개선하기 위해 미디어 플랫폼(UDP를 기반 프로토콜로 사용)을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="12162-112">화면 공유 개선의 목표는 VbSS와 RDP 간 전환이 발생할 때 최대한 매끄럽게 전환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="12162-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="12162-113">VbSS는 비즈니스용 Skype 서버의 화면 공유에 사용되는 기술에 대한 업데이트이기 때문에 네트워크 트래픽에서 SIP 세부 정보를 보거나 빠르게 이동하거나 3D로 콘텐츠를 공유하지 않는 한 활용하고 있는 기술을 검색하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="12162-114">예를 들어 작업 공간에 많은 레거시 클라이언트가 있는 경우 RDP를 모임 및 대화에 장애 조치(failsafe)로 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="12162-115">비즈니스용 Skype 서버는 내부 논리를 사용하여 클라이언트가 연결할 때 적용할 두 가지 방법(VbSS 또는 기존 화면 공유)을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="12162-116">상황에 따라 보기 환경이 중단되지 않고 VbSS로 대체될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="12162-117">계획</span><span class="sxs-lookup"><span data-stu-id="12162-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="12162-118">VbSS 장단</span><span class="sxs-lookup"><span data-stu-id="12162-118">VbSS pros and cons</span></span>

<span data-ttu-id="12162-119">VbSS로 전환하는 목적은 다음 세 가지 주요 개선을 목표로 합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="12162-120">화면 공유 만들기(최대 5%) RDP 단독에 비해 안정성이 더 습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="12162-121">RDP 단독에 비해 세션 설정 및 비디오 환경을 더 빠르게 만들 수 있습니다(초당 프레임 수가 6:1이 향상되었습니다.)</span><span class="sxs-lookup"><span data-stu-id="12162-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="12162-122">3D 그래픽과 같은 동작 콘텐츠를 공유하는 경우에도 낮은 대역폭 조건에서 RDP보다 훨씬 더 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="12162-123">이러한 수치는 네트워크의 상태 및 적절한 성능 조정을 사용하며 클라이언트가 모바일 장치에 있는 경우 네트워크 외부에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="12162-124">또한 공유 콘텐츠의 일부 품질/선명도는 안정성, 속도 및 효율성으로 거래되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-124">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency.</span></span> <span data-ttu-id="12162-125">대부분의 경우 이러한 설정은 사용자에게 쉽게 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-125">In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="12162-126">포트 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="12162-126">Ports and protocols</span></span>

<span data-ttu-id="12162-127">**필수 서버 포트**</span><span class="sxs-lookup"><span data-stu-id="12162-127">**Required server ports**</span></span>

|<span data-ttu-id="12162-128">**서버 역할**</span><span class="sxs-lookup"><span data-stu-id="12162-128">**Server role**</span></span>|<span data-ttu-id="12162-129">**서비스 이름**</span><span class="sxs-lookup"><span data-stu-id="12162-129">**Service name**</span></span>|<span data-ttu-id="12162-130">**포트 또는 포트 범위**</span><span class="sxs-lookup"><span data-stu-id="12162-130">**Port or port range**</span></span>|<span data-ttu-id="12162-131">**Protocol(프로토콜)**</span><span class="sxs-lookup"><span data-stu-id="12162-131">**Protocol**</span></span>|<span data-ttu-id="12162-132">**참고**</span><span class="sxs-lookup"><span data-stu-id="12162-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="12162-133">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="12162-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="12162-134">비즈니스용 Skype 서버 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="12162-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="12162-135">5065</span><span class="sxs-lookup"><span data-stu-id="12162-135">5065</span></span>  <br/> |<span data-ttu-id="12162-136">TCP</span><span class="sxs-lookup"><span data-stu-id="12162-136">TCP</span></span>  <br/> |<span data-ttu-id="12162-137">응용 프로그램 공유의 받는 SIP 수신 대기 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="12162-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="12162-138">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="12162-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="12162-139">비즈니스용 Skype 서버 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="12162-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="12162-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="12162-140">49152-65535</span></span>  <br/> |<span data-ttu-id="12162-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="12162-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="12162-142">응용 프로그램 공유에 사용되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="12162-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="12162-143">**필수 클라이언트 포트**</span><span class="sxs-lookup"><span data-stu-id="12162-143">**Required client ports**</span></span>

|<span data-ttu-id="12162-144">**구성 요소**</span><span class="sxs-lookup"><span data-stu-id="12162-144">**Component**</span></span>|<span data-ttu-id="12162-145">**포트 범위**</span><span class="sxs-lookup"><span data-stu-id="12162-145">**Port range**</span></span>|<span data-ttu-id="12162-146">**Protocol(프로토콜)**</span><span class="sxs-lookup"><span data-stu-id="12162-146">**Protocol**</span></span>|<span data-ttu-id="12162-147">**참고**</span><span class="sxs-lookup"><span data-stu-id="12162-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="12162-148">클라이언트</span><span class="sxs-lookup"><span data-stu-id="12162-148">Clients</span></span>  <br/> |<span data-ttu-id="12162-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="12162-149">1024-65535</span></span>  <br/> |<span data-ttu-id="12162-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="12162-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="12162-151">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="12162-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="12162-152">다음 미디어 포트에 대해 QoS를 사용하도록 설정하고 VbSS도 사용하도록 설정된 경우 AS MCU를 공유하는 데스크톱을 포함하는 회의 중에 화면 공유 트래픽에 대해 아래 표시된 비디오 포트 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="12162-153">이러한 설정은 특수한 경우로, 이러한 두 기능을 모두 구현할 때 이러한 정확한 설정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="12162-154">이 설정은 [QoS에](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos)대한 설명서의 다른 권장 설정을 대신합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-154">This overrides other recommended settings in the [documentation for QoS](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos).</span></span> <span data-ttu-id="12162-155">응용 프로그램 공유의 경우 이러한 포트 값을 정의하는 ASMCUSVC.exe 뿐만 아니라 QoS GPO에서도 응용 프로그램을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-155">For application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="12162-156">**응용 프로그램 서버 QoS/VbSS 필수 설정**</span><span class="sxs-lookup"><span data-stu-id="12162-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="12162-157">**속성**</span><span class="sxs-lookup"><span data-stu-id="12162-157">**Property**</span></span>|<span data-ttu-id="12162-158">**포트 값**</span><span class="sxs-lookup"><span data-stu-id="12162-158">**Port value**</span></span>|<span data-ttu-id="12162-159">**Protocol(프로토콜)**</span><span class="sxs-lookup"><span data-stu-id="12162-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="12162-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="12162-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="12162-161">49152</span><span class="sxs-lookup"><span data-stu-id="12162-161">49152</span></span>  <br/> |<span data-ttu-id="12162-162">UDP</span><span class="sxs-lookup"><span data-stu-id="12162-162">UDP</span></span>  <br/> |
|<span data-ttu-id="12162-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="12162-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="12162-164">8348</span><span class="sxs-lookup"><span data-stu-id="12162-164">8348</span></span>  <br/> |<span data-ttu-id="12162-165">UDP</span><span class="sxs-lookup"><span data-stu-id="12162-165">UDP</span></span>  <br/> |
|<span data-ttu-id="12162-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="12162-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="12162-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="12162-167">**57501**</span></span> <br/> |<span data-ttu-id="12162-168">UDP</span><span class="sxs-lookup"><span data-stu-id="12162-168">UDP</span></span>  <br/> |
|<span data-ttu-id="12162-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="12162-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="12162-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="12162-170">**8034**</span></span> <br/> |<span data-ttu-id="12162-171">UDP</span><span class="sxs-lookup"><span data-stu-id="12162-171">UDP</span></span>  <br/> |
|<span data-ttu-id="12162-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="12162-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="12162-173">40803</span><span class="sxs-lookup"><span data-stu-id="12162-173">40803</span></span>  <br/> |<span data-ttu-id="12162-174">TCP</span><span class="sxs-lookup"><span data-stu-id="12162-174">TCP</span></span>  <br/> |
|<span data-ttu-id="12162-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="12162-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="12162-176">8348</span><span class="sxs-lookup"><span data-stu-id="12162-176">8348</span></span>  <br/> |<span data-ttu-id="12162-177">TCP</span><span class="sxs-lookup"><span data-stu-id="12162-177">TCP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="12162-178">용량 계획</span><span class="sxs-lookup"><span data-stu-id="12162-178">Capacity planning</span></span>

<span data-ttu-id="12162-179">비즈니스용 Skype 서버 2015 CU2(누적 업데이트 2) 이상을 실행하는 각 프런트 엔드 서버는 RDP를 사용하여 화면 공유에 최대 375명이 지원됩니다(모임당 250개만 지원).</span><span class="sxs-lookup"><span data-stu-id="12162-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="12162-180">VbSS가 도입 및 사용되는 경우 CU3 후의 이 용량은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="12162-181">테스트에서 성능 및 스트레스 테스트를 수행했기 때문에 자체 배포와 관련하여 다음 측정도 고려해야 합니다(물론 사용에 따라 다를 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="12162-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="12162-182">전제:</span><span class="sxs-lookup"><span data-stu-id="12162-182">Assuming:</span></span>
  
- <span data-ttu-id="12162-183">배포에서 비즈니스용 Skype 서버 2015 CU2 이상을 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="12162-184">비즈니스용 Skype 서버 환경의 모든 사용자는 화면 해상도가 1920x1080 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="12162-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="12162-185">전체 용량(위에서 설명한 대로 모임당 250명만 사용 가능) 프런트 엔드 서버당 총 375명 화면 공유 참가자 수가 1기가비트 네트워크 카드의 89%를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="12162-186">이는 RDP(비즈니스용 Skype 서버 CU2)의 기존 화면 공유 기술이 발표자 PC의 기본 해상도로 화면 콘텐츠를 전송하기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="12162-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="12162-187">따라서 화면 해상도가 더 높을수록 비즈니스용 Skype 서버 2015 CU2와 화면 공유에 대한 네트워크 병목 현상이 이미 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="12162-188">이를 완화하기 위해 다음 옵션 중 하나 이상이 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="12162-189">1기가비트 네트워크 카드에서 10기가비트 이더넷 카드로 프런트 엔드 서버를 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="12162-190">트래픽 부하를 균형 조정하기 위해 프런트 엔드 서버 수를 늘입니다.</span><span class="sxs-lookup"><span data-stu-id="12162-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="12162-191">두 채널 중 하나에서 사용하는 최대 대역폭에 한도를 두어 VbSS 및 RDP에 사용되는 대역폭(비트 속도)을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="12162-192">이 표의 숫자는 개별 네트워크 및 공유되는 콘텐츠의 영향을 습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-192">The numbers in this table are influenced by individual networks and by the content being shared.</span></span> <span data-ttu-id="12162-193">테스트하여 네트워크 또는 네트워크에 대한 기준을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="12162-193">Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="12162-194">**1080p 콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="12162-194">**1080p Content**</span></span>|<span data-ttu-id="12162-195">**RDP Average**</span><span class="sxs-lookup"><span data-stu-id="12162-195">**RDP Average**</span></span>|<span data-ttu-id="12162-196">**RDP 최대**</span><span class="sxs-lookup"><span data-stu-id="12162-196">**RDP Peak**</span></span>|<span data-ttu-id="12162-197">**VbSS Average**</span><span class="sxs-lookup"><span data-stu-id="12162-197">**VbSS Average**</span></span>|<span data-ttu-id="12162-198">**VbSS Peak**</span><span class="sxs-lookup"><span data-stu-id="12162-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="12162-199">PPT</span><span class="sxs-lookup"><span data-stu-id="12162-199">PPT</span></span>  <br/> |<span data-ttu-id="12162-200">200kbps</span><span class="sxs-lookup"><span data-stu-id="12162-200">200kbps</span></span>  <br/> |<span data-ttu-id="12162-201">12mbps</span><span class="sxs-lookup"><span data-stu-id="12162-201">12mbps</span></span>  <br/> |<span data-ttu-id="12162-202">100kbps</span><span class="sxs-lookup"><span data-stu-id="12162-202">100kbps</span></span>  <br/> |<span data-ttu-id="12162-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="12162-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="12162-204">CAD</span><span class="sxs-lookup"><span data-stu-id="12162-204">CAD</span></span>  <br/> |<span data-ttu-id="12162-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="12162-205">3mbps</span></span>  <br/> |<span data-ttu-id="12162-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="12162-206">7mbps</span></span>  <br/> |<span data-ttu-id="12162-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="12162-207">1mbps</span></span>  <br/> |<span data-ttu-id="12162-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="12162-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="12162-209">비디오</span><span class="sxs-lookup"><span data-stu-id="12162-209">Video</span></span>  <br/> |<span data-ttu-id="12162-210">5mbps</span><span class="sxs-lookup"><span data-stu-id="12162-210">5mbps</span></span>  <br/> |<span data-ttu-id="12162-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="12162-211">7mbps</span></span>  <br/> |<span data-ttu-id="12162-212">1.3mbps</span><span class="sxs-lookup"><span data-stu-id="12162-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="12162-213">2.2mbps</span><span class="sxs-lookup"><span data-stu-id="12162-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="12162-214">미디어 트래픽에 대한 네트워크 대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="12162-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="12162-215">VbSS 대역폭은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="12162-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="12162-216">**비디오 코덱**</span><span class="sxs-lookup"><span data-stu-id="12162-216">**Video codec**</span></span>|<span data-ttu-id="12162-217">**해상도 및 가로 세로 비율**</span><span class="sxs-lookup"><span data-stu-id="12162-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="12162-218">**최대 비디오 페이로드 비트 속도(Kbps)**</span><span class="sxs-lookup"><span data-stu-id="12162-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="12162-219">**최소 비디오 페이로드 비트 속도(Kbps)**</span><span class="sxs-lookup"><span data-stu-id="12162-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="12162-220">H.264</span><span class="sxs-lookup"><span data-stu-id="12162-220">H.264</span></span>  <br/> |<span data-ttu-id="12162-221">1920x1080(16:9)</span><span class="sxs-lookup"><span data-stu-id="12162-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="12162-222">(세로 비율은 공유자 모니터 해상도에 따라 달라지며 항상 16:9가 아는 것은 아는 경우)</span><span class="sxs-lookup"><span data-stu-id="12162-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="12162-223">4000</span><span class="sxs-lookup"><span data-stu-id="12162-223">4000</span></span>  <br/> |<span data-ttu-id="12162-224">1500</span><span class="sxs-lookup"><span data-stu-id="12162-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="12162-225">클라이언트 및 서버 지원</span><span class="sxs-lookup"><span data-stu-id="12162-225">Clients and servers support</span></span>

<span data-ttu-id="12162-226">비디오 기반 화면 공유를 사용하려면 비즈니스용 Skype 서버 2015 CU3 이상이 필요하며, 비즈니스용 [Skype](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) 및 모임 지원에 대한 모바일 클라이언트 기능 비교에 나열된 지원 클라이언트의 현재 [버전이 필요합니다.](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)</span><span class="sxs-lookup"><span data-stu-id="12162-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="12162-227">화면 공유가 RDP로 전환되는 상황은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="12162-228">계정이 ASMCU가 VbSS를 지원하는 최소 빌드를 충족하지 않는 환경에서 호스팅되는 경우</span><span class="sxs-lookup"><span data-stu-id="12162-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="12162-229">이전 버전의 비즈니스용 Skype 클라이언트를 사용하는 사용자가 세션에 참가하는 경우(예: 16.0.6330.1000보다 낮은 모든 Windows 클라이언트 버전, 비즈니스용 Skype 룸 시스템 장치 또는 비즈니스용 Skype 모바일 앱 사용).</span><span class="sxs-lookup"><span data-stu-id="12162-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="12162-230">사용자가 비즈니스용 Skype 웹앱에서 공유하는 경우</span><span class="sxs-lookup"><span data-stu-id="12162-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="12162-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span><span class="sxs-lookup"><span data-stu-id="12162-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span></span>
- <span data-ttu-id="12162-232">누군가가 프로그램/Windows 공유를 시작하는 경우.</span><span class="sxs-lookup"><span data-stu-id="12162-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="12162-233">다른 사용자가 세션 녹음/녹화를 시작하는 경우</span><span class="sxs-lookup"><span data-stu-id="12162-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="12162-234">세션 중에 다른 사용자가 원격 화면 제어를 호출하는 경우</span><span class="sxs-lookup"><span data-stu-id="12162-234">If someone invokes Remote Screen Control during the session.</span></span> 
- <span data-ttu-id="12162-235">참가자가 250명 이상인 모임(현재 VbSS가 지원되지 않는 경우)</span><span class="sxs-lookup"><span data-stu-id="12162-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>

<span data-ttu-id="12162-236">세션이 RDP로 전환하면 VbSS로 다시 전환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-236">Be aware that once the session transitions to RDP it will not transition back to VbSS.</span></span> <span data-ttu-id="12162-237">즉, VbSS에서 전환하는 것은 매끄럽게 하기 위한 것이기 때문에 대부분의 상황에서는 쉽게 감지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-237">Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="12162-238">비즈니스용 Skype 화면 공유에서 VbSS에서 RDP로의 전환을 차단하거나 차단하려고 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="12162-239">VbSS 사용, 사용 안 하게 및 구성</span><span class="sxs-lookup"><span data-stu-id="12162-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="12162-240">좋은 점은 비즈니스용 Skype 서버 2015 CU3(누적 업데이트 3) 이상을 설치한 경우 모든 사용자가 기본적으로 일대일 및 다자 VbSS를 사용할 수 있도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="12162-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="12162-241">모든 사용자에 대해 이 기능을 사용하도록 설정하지 않은 이유가 있는 경우 이 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="12162-242">이 경우 다음 단계를 사용하여 사용자를 사용하지 않도록 설정할 수 있습니다(사용자 사용 단계가 수행됨).</span><span class="sxs-lookup"><span data-stu-id="12162-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="12162-243">사용자가 VbSS를 사용하지 않도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="12162-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="12162-244">비즈니스용 Skype 관리 콘솔에서 이 cmdlet을 실행하여 VbSS를 사용할 수 없는 사용자에게 VbSS를 허용하지 않는 사용자 정책을 할당할 수 있습니다.([PolicyName]을 이 작업을 수행하고 있는 정책으로 바꾸기).</span><span class="sxs-lookup"><span data-stu-id="12162-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="12162-245">할당된 정책이 없는 모든 사용자에게 영향을 주는 전역 회의 정책을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="12162-246">이 명령에 대한 자세한 내용은 [Set-CsConferencingPolicy를 참조하세요.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="12162-246">For more information on this command, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="12162-247">VbSS를 완전히 해제해야 하는 경우 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="12162-248">이 명령에 대한 자세한 내용은 [Set-CsMediaConfiguration을 참조하세요.](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="12162-248">For more information on this command, see [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="12162-249">여러 비즈니스용 Skype 모임에서 모든 클라이언트 끝점은 모임 이끌이에 대한 정책 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="12162-250">사용자가 VbSS를 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="12162-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="12162-251">비즈니스용 Skype 관리 콘솔에서 이 cmdlet을 실행하여 VbSS를 사용해야 하는 모든 사용자에게 VbSS를 허용하는 특정 사용자 정책을 할당할 수 있습니다([PolicyName]을 이 작업을 수행 중인 정책으로 바꾸기).</span><span class="sxs-lookup"><span data-stu-id="12162-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="12162-252">할당된 정책이 없는 모든 사용자에게 영향을 주는 전역 회의 정책을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="12162-253">이 명령에 대한 자세한 내용은 [Set-CsConferencingPolicy를 참조하세요.](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="12162-253">For more information on this command, see [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="12162-254">VbSS를 끄고(기본적으로 켜진) VbSS를 다시 켜야 하는 경우 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="12162-255">이 명령에 대한 자세한 내용은 [Set-CsMediaConfiguration을 참조하세요.](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="12162-255">For more information on this command, see [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="12162-256">여러 비즈니스용 Skype 모임에서 모든 클라이언트 끝점은 모임 이끌이에 대한 정책 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="12162-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="12162-257">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12162-257">See also</span></span>

[<span data-ttu-id="12162-258">비즈니스용 Skype 서버 2015 누적 업데이트 KB3061064</span><span class="sxs-lookup"><span data-stu-id="12162-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/download/details.aspx?id=47690)
  
[<span data-ttu-id="12162-259">VBSS(비디오 기반 화면 공유)는 비즈니스용 Skype 서버 2015에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12162-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/kb/3170163)