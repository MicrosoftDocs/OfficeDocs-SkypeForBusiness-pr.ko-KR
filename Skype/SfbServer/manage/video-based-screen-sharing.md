---
title: 비즈니스용 Skype 서버에 대 한 비디오 기반 화면 공유
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: 비디오 기반 화면 공유에 대 한 비즈니스용 Skype 서버 계획 및 구성 정보 (VbSS)
ms.openlocfilehash: d6b66da2994db892bc193103bca75e844c62197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009571"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a><span data-ttu-id="c4d4e-103">비즈니스용 Skype 서버에 대 한 비디오 기반 화면 공유</span><span class="sxs-lookup"><span data-stu-id="c4d4e-103">Video based Screen Sharing for Skype for Business Server</span></span> 
 
<span data-ttu-id="c4d4e-104">이제 비즈니스용 Skype 서버 2015에서 비디오 기반 화면 공유 (VbSS)를 다운로드할 수 있습니다. [비즈니스용 Skype 서버 2015 누적 업데이트 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690).</span><span class="sxs-lookup"><span data-stu-id="c4d4e-104">Video-based Screen Sharing (VbSS) in Skype For Business Server 2015 is now available for download: [Skype for Business Server 2015 Cumulative Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690).</span></span> <span data-ttu-id="c4d4e-105">VbSS는 비즈니스용 Skype 서버 2019에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-105">VbSS is included with Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="c4d4e-106">비디오 기반 화면 공유 또는 VbSS가 Lync 화면 공유에서 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-106">Video-based Screen Sharing, or VbSS, grew out of Lync screen-sharing.</span></span> <span data-ttu-id="c4d4e-107">VbSS와 전통적인 화면 공유의 차이점은 사용 된 기본 프로토콜과 excel에서 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-107">The difference between VbSS and traditional screen-sharing has to do with the underlying protocols used, and what they excel at.</span></span> <span data-ttu-id="c4d4e-108">화면 공유에서는 RDP (원격 데스크톱 프로토콜)를 사용 하므로 사용자 컴퓨터 간에 수천 개의 세션을 만들 때 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-108">Screen-sharing uses the remote desktop protocol (RDP), which is great at creating thousands of 1-to-1 sessions between people's computers.</span></span> <span data-ttu-id="c4d4e-109">신형 기술인 VbSS는 UDP (사용자 데이터 그램 프로토콜)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-109">Newer technology, VbSS, will make use of User Datagram Protocol (UDP).</span></span>
  
<span data-ttu-id="c4d4e-110">비즈니스용 Skype 서버는 사용자의 일대일 및 일대다 (멀티 파티) 대화 및 모임 환경을 개선 하기 위해 원했습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-110">Skype for Business Server wanted to improve people's 1-to-1, and their 1-to-many (multi-party) conversations and meeting experiences.</span></span> <span data-ttu-id="c4d4e-111">VbSS는 미디어 플랫폼을 기본 프로토콜로 사용 하 여, 비디오 시작 시간을 개선 하는 목표, 시청 하 고 있는 대상의 품질 (특히 시청 하 고 있는 작업을 수행 하는 경우)을 전체적으로 확인 하는 등의 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-111">VbSS makes use of the media platform (which relies on UDP as the underlying protocol), with the goal of improving your video start times, the viewing quality of what you're watching (especially if what you're watching is moving fast), and reliability overall.</span></span>
  
<span data-ttu-id="c4d4e-112">화면 공유 기능을 향상 시킬 수 있는 목표 중 일부는 VbSS와 RDP 간의 전환이 가능한 한 원활 하 게 진행 된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-112">Part of the goal of improving screen-sharing is that transitions between VbSS and RDP be as seamless as possible when they occur.</span></span> <span data-ttu-id="c4d4e-113">VbSS는 비즈니스용 Skype 서버에 대 한 화면 공유에 사용 되는 기본 기술에 대 한 업데이트 이므로 네트워크 트래픽에 SIP 세부 정보를 확인 하거나 콘텐츠를 공유 하는 경우가 아니면 활용 중인 기술을 검색 하기 어려울 수 있습니다. 은 빠른 이동 이나 3 차원입니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-113">Since VbSS is an update to underlying technology that is used in screen sharing for Skype for Business Server, it may be difficult to detect which technology you're leveraging unless you're looking at SIP details in the network traffic, or you're sharing content that is fast moving or 3-D.</span></span> <span data-ttu-id="c4d4e-114">예를 들어 회사의 레거시 클라이언트가 많은 경우에도 사용자의 모임 및 대화에 대 한 안전에 따라 RDP를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-114">If, for example, your workplace has a lot of legacy clients, RDP will still be available as a failsafe to your meetings and conversations.</span></span> <span data-ttu-id="c4d4e-115">비즈니스용 Skype 서버는 내부 논리를 사용 하 여 클라이언트가 연결할 때 적용할 두 가지 방법 (VbSS 또는 전통적인 화면 공유)을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-115">Skype for Business Server uses internal logic to decide which of the two methods (VbSS or traditional screen-sharing) to apply when clients connect.</span></span> <span data-ttu-id="c4d4e-116">RDP가 요청을 호출 하는 경우, 사용자의 보기 환경이 중단 되지 않도록이를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-116">RDP can, and will, be substituted for VbSS when the situation calls for it, so that your viewing experience won't be interrupted.</span></span>
  
## <a name="planning"></a><span data-ttu-id="c4d4e-117">계획</span><span class="sxs-lookup"><span data-stu-id="c4d4e-117">Planning</span></span>

### <a name="vbss-pros-and-cons"></a><span data-ttu-id="c4d4e-118">VbSS의 장단점</span><span class="sxs-lookup"><span data-stu-id="c4d4e-118">VbSS pros and cons</span></span>

<span data-ttu-id="c4d4e-119">VbSS 목표로 전환 하면 다음과 같은 세 가지 주요 기능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-119">Switching to VbSS aims to make three key improvements:</span></span>
  
1. <span data-ttu-id="c4d4e-120">화면 공유 설정 (최대 5%) 신뢰할 수 있는 RDP에 비해 더 안정적입니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-120">Make screen-sharing (up to 5%) more reliable compared to RDP alone.</span></span>

2. <span data-ttu-id="c4d4e-121">RDP를 사용 하는 경우에 비해 세션 설정 및 비디오 환경이 더 빠르게 수행 되도록 설정 (2 초에 6:1을 개선 하는 동시에 시간을 절반으로 설치) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-121">Make the session setup and video experience faster compared to RDP alone (setup in half the time, with a 6:1 improvement in frames-per-second).</span></span>

3. <span data-ttu-id="c4d4e-122">3 차원 그래픽과 같은 높은 모션 콘텐츠를 공유 하는 경우에도 낮은 대역폭 조건의 RDP 보다 훨씬 더 효율적으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-122">Works much better than RDP in low bandwidth conditions, even when sharing high motion content, such as 3-D graphics.</span></span>
    
<span data-ttu-id="c4d4e-123">이러한 수치는 네트워크의 상태 및 적절 한 성능 조정에 의존 하며, 클라이언트가 모바일 장치에 있는 경우에는 자체 외부 네트워크를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-123">Please keep in mind that these numbers rely on the health and proper performance tuning of your network, and may involve networks external to your own, if your clients are on mobile devices.</span></span>
  
<span data-ttu-id="c4d4e-124">또한 공유 콘텐츠의 일부 충실도/crispness가 안정성, 속도 및 효율성을 위한 것 이라는 점을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-124">You should also be aware that some fidelity/crispness of your shared content has been traded for reliability, speed, and efficiency.</span></span> <span data-ttu-id="c4d4e-125">대부분의 경우이는 사용자에 게 즉시 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-125">In most cases this will not be readily visible to users.</span></span>
  
### <a name="ports-and-protocols"></a><span data-ttu-id="c4d4e-126">포트 및 프로토콜</span><span class="sxs-lookup"><span data-stu-id="c4d4e-126">Ports and protocols</span></span>

<span data-ttu-id="c4d4e-127">**필요한 서버 포트**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-127">**Required server ports**</span></span>

|<span data-ttu-id="c4d4e-128">**서버 역할**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-128">**Server role**</span></span>|<span data-ttu-id="c4d4e-129">**서비스 이름**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-129">**Service name**</span></span>|<span data-ttu-id="c4d4e-130">**포트 또는 포트 범위**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-130">**Port or port range**</span></span>|<span data-ttu-id="c4d4e-131">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-131">**Protocol**</span></span>|<span data-ttu-id="c4d4e-132">**참고**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-132">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c4d4e-133">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="c4d4e-133">Front End Servers</span></span>  <br/> |<span data-ttu-id="c4d4e-134">비즈니스용 Skype 서버 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="c4d4e-134">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="c4d4e-135">5065</span><span class="sxs-lookup"><span data-stu-id="c4d4e-135">5065</span></span>  <br/> |<span data-ttu-id="c4d4e-136">TCP</span><span class="sxs-lookup"><span data-stu-id="c4d4e-136">TCP</span></span>  <br/> |<span data-ttu-id="c4d4e-137">응용 프로그램 공유의 받는 SIP 수신 대기 요청에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-137">Used for incoming SIP listening requests for application sharing.</span></span>  <br/> |
|<span data-ttu-id="c4d4e-138">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="c4d4e-138">Front End Servers</span></span>  <br/> |<span data-ttu-id="c4d4e-139">비즈니스용 Skype 서버 응용 프로그램 공유 서비스</span><span class="sxs-lookup"><span data-stu-id="c4d4e-139">Skype for Business Server Application Sharing service</span></span>  <br/> |<span data-ttu-id="c4d4e-140">49152-65535</span><span class="sxs-lookup"><span data-stu-id="c4d4e-140">49152-65535</span></span>  <br/> |<span data-ttu-id="c4d4e-141">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c4d4e-141">TCP/UDP</span></span>  <br/> |<span data-ttu-id="c4d4e-142">응용 프로그램 공유에 사용되는 미디어 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-142">Media port range used for application sharing.</span></span>  <br/> |
   
<span data-ttu-id="c4d4e-143">**필요한 클라이언트 포트**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-143">**Required client ports**</span></span>

|<span data-ttu-id="c4d4e-144">**구성 요소**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-144">**Component**</span></span>|<span data-ttu-id="c4d4e-145">**포트 범위**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-145">**Port range**</span></span>|<span data-ttu-id="c4d4e-146">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-146">**Protocol**</span></span>|<span data-ttu-id="c4d4e-147">**참고**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-147">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c4d4e-148">클라이언트</span><span class="sxs-lookup"><span data-stu-id="c4d4e-148">Clients</span></span>  <br/> |<span data-ttu-id="c4d4e-149">1024-65535</span><span class="sxs-lookup"><span data-stu-id="c4d4e-149">1024-65535</span></span>  <br/> |<span data-ttu-id="c4d4e-150">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c4d4e-150">TCP/UDP</span></span>  <br/> |<span data-ttu-id="c4d4e-151">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="c4d4e-151">Application sharing.</span></span>  <br/> |
   
<span data-ttu-id="c4d4e-152">다음 미디어 포트에 대해 QoS가 사용 하도록 설정 되어 있고 VbSS가 사용 되도록 설정 된 경우 데스크톱 공유를 포함 하는 회의 중에는 화면 공유 트래픽에 아래 굵게 표시 된 비디오 포트 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-152">If QoS is enabled for the following media ports and VbSS is also enabled, during a conference that includes desktop sharing the AS MCU will use the video port settings shown in bold below for the screen share traffic.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c4d4e-153">이러한 설정은 특수 한 경우 이며, 이러한 기능을 모두 구현할 때 이러한 설정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-153">These settings are a special case, and these exact settings must be used when implementing both of these features.</span></span> <span data-ttu-id="c4d4e-154">이렇게 하면 [QoS 설명서](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx)의 기타 권장 설정이 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-154">This overrides other recommended settings in the [documentation for QoS](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="c4d4e-155">응용 프로그램 공유의 경우 QoS GPO에서 ASMCUSVC를 지정 해야 하며 이러한 포트 값을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-155">For application sharing you will also need to specify ASMCUSVC.exe in the QoS GPO in addition to defining these port values.</span></span> 
  
<span data-ttu-id="c4d4e-156">**Application Server QoS/VbSS 필요한 설정**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-156">**Application Server QoS/VbSS required settings**</span></span>

|<span data-ttu-id="c4d4e-157">**속성**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-157">**Property**</span></span>|<span data-ttu-id="c4d4e-158">**포트 값**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-158">**Port value**</span></span>|<span data-ttu-id="c4d4e-159">**프로토콜**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-159">**Protocol**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c4d4e-160">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="c4d4e-160">AudioPortStart</span></span>  <br/> |<span data-ttu-id="c4d4e-161">49152</span><span class="sxs-lookup"><span data-stu-id="c4d4e-161">49152</span></span>  <br/> |<span data-ttu-id="c4d4e-162">P</span><span class="sxs-lookup"><span data-stu-id="c4d4e-162">UDP</span></span>  <br/> |
|<span data-ttu-id="c4d4e-163">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="c4d4e-163">AudioPortCount</span></span>  <br/> |<span data-ttu-id="c4d4e-164">8348</span><span class="sxs-lookup"><span data-stu-id="c4d4e-164">8348</span></span>  <br/> |<span data-ttu-id="c4d4e-165">P</span><span class="sxs-lookup"><span data-stu-id="c4d4e-165">UDP</span></span>  <br/> |
|<span data-ttu-id="c4d4e-166">**VideoPortStart**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-166">**VideoPortStart**</span></span> <br/> |<span data-ttu-id="c4d4e-167">**57501**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-167">**57501**</span></span> <br/> |<span data-ttu-id="c4d4e-168">P</span><span class="sxs-lookup"><span data-stu-id="c4d4e-168">UDP</span></span>  <br/> |
|<span data-ttu-id="c4d4e-169">**VideoPortCount**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-169">**VideoPortCount**</span></span> <br/> |<span data-ttu-id="c4d4e-170">**8034**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-170">**8034**</span></span> <br/> |<span data-ttu-id="c4d4e-171">P</span><span class="sxs-lookup"><span data-stu-id="c4d4e-171">UDP</span></span>  <br/> |
|<span data-ttu-id="c4d4e-172">AppSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="c4d4e-172">AppSharingPortStart</span></span>  <br/> |<span data-ttu-id="c4d4e-173">40803</span><span class="sxs-lookup"><span data-stu-id="c4d4e-173">40803</span></span>  <br/> |<span data-ttu-id="c4d4e-174">TCP</span><span class="sxs-lookup"><span data-stu-id="c4d4e-174">TCP</span></span>  <br/> |
|<span data-ttu-id="c4d4e-175">AppSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="c4d4e-175">AppSharingPortCount</span></span>  <br/> |<span data-ttu-id="c4d4e-176">8348</span><span class="sxs-lookup"><span data-stu-id="c4d4e-176">8348</span></span>  <br/> |<span data-ttu-id="c4d4e-177">TCP</span><span class="sxs-lookup"><span data-stu-id="c4d4e-177">TCP</span></span>  <br/> |
   
### <a name="capacity-planning"></a><span data-ttu-id="c4d4e-178">용량 계획</span><span class="sxs-lookup"><span data-stu-id="c4d4e-178">Capacity planning</span></span>

<span data-ttu-id="c4d4e-179">비즈니스용 Skype 서버 2015 C U 2 (누적 업데이트 2) 이상을 실행 하는 각 프런트 엔드 서버는 RDP를 사용 하 여 화면을 공유 하기 위해 최대 375 명의 참가자를 지원 합니다 (모임 당 250만 해당).</span><span class="sxs-lookup"><span data-stu-id="c4d4e-179">Each Front End Server running Skype for Business Server 2015 Cumulative Update 2 (CU2) or later supports up to 375 participants for screen sharing using RDP (though only 250 per meeting).</span></span> <span data-ttu-id="c4d4e-180">이 용량은 VbSS가 도입 되 고 사용 될 때 C U 3를 변경 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-180">This capacity doesn't change post-CU3, when VbSS is introduced and used.</span></span>
  
<span data-ttu-id="c4d4e-181">즉, 랩에서는 성능 및 스트레스 테스트를 완료 했으며, 사용에 따라 다음 측정법도 사용자의 배포와 관련 하 여 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-181">That being said, we've done performance and stress testing in our lab, and the following measurements should also be considered with regard to your own deployment (depending on usage, of course).</span></span>
  
<span data-ttu-id="c4d4e-182">없다고</span><span class="sxs-lookup"><span data-stu-id="c4d4e-182">Assuming:</span></span>
  
- <span data-ttu-id="c4d4e-183">배포에서 비즈니스용 Skype 서버 2015 C U 2 이상 버전을 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-183">You're using Skype for Business Server 2015 CU2 or later in your deployment.</span></span>
    
- <span data-ttu-id="c4d4e-184">비즈니스용 Skype 서버 환경의 모든 사용자에 게는 해상도 1920x1080 보다 높은 화면 해상도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-184">All the users in your Skype for Business Server environment have screen resolutions higher than 1920x1080.</span></span>
    
<span data-ttu-id="c4d4e-185">위에서 설명한 대로 전체 용량 (위에 설명 된 것 처럼, 모든 프런트 엔드 서버에서 총 1 회 (모임 당 250)로 표시 됨)에는 프런트 엔드 서버에서 375 비트의 네트워크 카드를 89 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-185">At full capacity (which as noted above, is 375 screen sharing participants per Front End Server in total, though only 250 per meeting), your Front End Server may be utilizing ~89% of the 1 Gigabit of network card.</span></span> <span data-ttu-id="c4d4e-186">이는 lync (비즈니스용 Skype 서버 C U 2)의 기존 화면 공유 기술이 발표자 PC의 기본 해상도로 화면상의 콘텐츠를 전송 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-186">This is because the existing screen sharing technology in Skype for Business Server CU2 (RDP) transmits the on-screen content at the native resolution of the presenter's PC.</span></span> <span data-ttu-id="c4d4e-187">더 높은 화면 해상도가 사용 되는 경우에는 비즈니스용 Skype 서버 2015 C U 2의 화면 공유에 대 한 네트워크 병목 현상이 이미 발생 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-187">So with higher screen resolutions factored in, you may already be experiencing network bottlenecks for screen sharing with Skype for Business Server 2015 CU2.</span></span>
  
<span data-ttu-id="c4d4e-188">이를 완화 하기 위해 다음 옵션 중 하나 이상이 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-188">To mitigate this, one or more of the following options may be helpful:</span></span>
  
- <span data-ttu-id="c4d4e-189">1 기가 비트 네트워크 카드에서 10 기가 비트 이더넷 카드로 프런트 엔드 서버를 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-189">Upgrade your Front End Server from a 1 Gigabit network card to a 10 Gigabit Ethernet card.</span></span>

- <span data-ttu-id="c4d4e-190">프런트 엔드 서버의 수를 늘려 트래픽을 부하 분산 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-190">Increase the number of Front End Servers to load-balance traffic.</span></span>

- <span data-ttu-id="c4d4e-191">각 채널에서 사용 되는 최대 대역폭에 cap를 추가 하 여 VbSS 및 RDP에 사용 되는 대역폭 (비트 전송률)을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-191">Limit the bandwidth (bitrate) used for VbSS and RDP by putting a cap on the maximum bandwidth used by either channels.</span></span>
    
<span data-ttu-id="c4d4e-192">이 표에 나와 있는 숫자는 개별 네트워크와 공유 되는 콘텐츠의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-192">The numbers in this table are influenced by individual networks and by the content being shared.</span></span> <span data-ttu-id="c4d4e-193">테스트를 통해 네트워크 또는 네트워크에 대 한 기준을 설정 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-193">Please test to establish baselines for your network or networks.</span></span>
  
|<span data-ttu-id="c4d4e-194">**1080p Content**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-194">**1080p Content**</span></span>|<span data-ttu-id="c4d4e-195">**RDP 평균**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-195">**RDP Average**</span></span>|<span data-ttu-id="c4d4e-196">**RDP 피크**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-196">**RDP Peak**</span></span>|<span data-ttu-id="c4d4e-197">**VbSS 평균**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-197">**VbSS Average**</span></span>|<span data-ttu-id="c4d4e-198">**VbSS 피크**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-198">**VbSS Peak**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c4d4e-199">.PPT</span><span class="sxs-lookup"><span data-stu-id="c4d4e-199">PPT</span></span>  <br/> |<span data-ttu-id="c4d4e-200">200kbps</span><span class="sxs-lookup"><span data-stu-id="c4d4e-200">200kbps</span></span>  <br/> |<span data-ttu-id="c4d4e-201">12mbps</span><span class="sxs-lookup"><span data-stu-id="c4d4e-201">12mbps</span></span>  <br/> |<span data-ttu-id="c4d4e-202">100kbps</span><span class="sxs-lookup"><span data-stu-id="c4d4e-202">100kbps</span></span>  <br/> |<span data-ttu-id="c4d4e-203">3mbps</span><span class="sxs-lookup"><span data-stu-id="c4d4e-203">3mbps</span></span>  <br/> |
|<span data-ttu-id="c4d4e-204">CAD</span><span class="sxs-lookup"><span data-stu-id="c4d4e-204">CAD</span></span>  <br/> |<span data-ttu-id="c4d4e-205">3mbps</span><span class="sxs-lookup"><span data-stu-id="c4d4e-205">3mbps</span></span>  <br/> |<span data-ttu-id="c4d4e-206">7mbps</span><span class="sxs-lookup"><span data-stu-id="c4d4e-206">7mbps</span></span>  <br/> |<span data-ttu-id="c4d4e-207">1mbps</span><span class="sxs-lookup"><span data-stu-id="c4d4e-207">1mbps</span></span>  <br/> |<span data-ttu-id="c4d4e-208">3mbps</span><span class="sxs-lookup"><span data-stu-id="c4d4e-208">3mbps</span></span>  <br/> |
|<span data-ttu-id="c4d4e-209">비디오</span><span class="sxs-lookup"><span data-stu-id="c4d4e-209">Video</span></span>  <br/> |<span data-ttu-id="c4d4e-210">5mbps</span><span class="sxs-lookup"><span data-stu-id="c4d4e-210">5mbps</span></span>  <br/> |<span data-ttu-id="c4d4e-211">7mbps</span><span class="sxs-lookup"><span data-stu-id="c4d4e-211">7mbps</span></span>  <br/> |<span data-ttu-id="c4d4e-212">1.3 mbps</span><span class="sxs-lookup"><span data-stu-id="c4d4e-212">1.3mbps</span></span>  <br/> |<span data-ttu-id="c4d4e-213">2.2 mbps</span><span class="sxs-lookup"><span data-stu-id="c4d4e-213">2.2mbps</span></span>  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a><span data-ttu-id="c4d4e-214">미디어 트래픽에 대 한 네트워크 대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4d4e-214">Network bandwidth requirements for media traffic</span></span>

<span data-ttu-id="c4d4e-215">VbSS 대역폭은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-215">The VbSS bandwidth is:</span></span>
  
|<span data-ttu-id="c4d4e-216">**비디오 코덱**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-216">**Video codec**</span></span>|<span data-ttu-id="c4d4e-217">**해상도 및 가로 세로 비율**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-217">**Resolution and aspect ratio**</span></span>|<span data-ttu-id="c4d4e-218">**최대 비디오 페이로드 비트 전송률 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-218">**Maximum video payload bit rate (Kbps)**</span></span>|<span data-ttu-id="c4d4e-219">**최소 비디오 페이로드 비트 전송률 (Kbps)**</span><span class="sxs-lookup"><span data-stu-id="c4d4e-219">**Minimum video payload bit rate (Kbps)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c4d4e-220">.H. 264</span><span class="sxs-lookup"><span data-stu-id="c4d4e-220">H.264</span></span>  <br/> |<span data-ttu-id="c4d4e-221">해상도 1920x1080 (16:9)</span><span class="sxs-lookup"><span data-stu-id="c4d4e-221">1920x1080 (16:9)</span></span>  <br/> <span data-ttu-id="c4d4e-222">가로 세로 비율은 공유자의 모니터 해상도에 따라 다르며 항상 16:9이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-222">(The aspect ratio depends on the sharer's monitor resolution, and will not always be 16:9)</span></span>  <br/> |<span data-ttu-id="c4d4e-223">4000</span><span class="sxs-lookup"><span data-stu-id="c4d4e-223">4000</span></span>  <br/> |<span data-ttu-id="c4d4e-224">1500</span><span class="sxs-lookup"><span data-stu-id="c4d4e-224">1500</span></span>  <br/> |
   
## <a name="clients-and-servers-support"></a><span data-ttu-id="c4d4e-225">클라이언트 및 서버 지원</span><span class="sxs-lookup"><span data-stu-id="c4d4e-225">Clients and servers support</span></span>

<span data-ttu-id="c4d4e-226">비디오 기반 화면 공유를 사용 하려면 비즈니스용 Skype 서버 2015 C U 3 이상이 필요 하며, [모바일 클라이언트 기능](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) 에 나열 된 지원 클라이언트의 현재 버전은 비즈니스용 Skype 및 [모임 지원을 지원](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-226">Video-based Screen Sharing requires Skype for Business Server 2015 CU3 or later, and a current version of the supporting clients listed in [Mobile client feature comparison for Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) and [Meetings support](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing).</span></span> 
  
<span data-ttu-id="c4d4e-227">다음과 같이 화면 공유가 RDP로 전환 되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-227">There are situations where screen-sharing will transition to RDP, like these:</span></span>
  
- <span data-ttu-id="c4d4e-228">계정이 VbSS를 지 원하는 최소 빌드를 충족 하지 않는 환경에서 호스트 되는 경우</span><span class="sxs-lookup"><span data-stu-id="c4d4e-228">If your account is hosted in an environment where the ASMCU doesn't meet the minimum build that supports VbSS.</span></span>
- <span data-ttu-id="c4d4e-229">이전 버전의 비즈니스용 Skype 클라이언트를 사용 하는 사용자가 16.0.6330.1000 보다 낮은 Windows 클라이언트 버전을 사용 하는 경우 (예: 비즈니스용 Skype 대화방 시스템 장치 또는 비즈니스용 Skype 모바일 앱) 사용자의 세션에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-229">If someone who uses an older version of the Skype for Business client joins your session, for example anyone using any Windows client version that is lower than 16.0.6330.1000, Skype for Business Room System Devices, or Skype for Business Mobile Apps.</span></span> 
- <span data-ttu-id="c4d4e-230">사용자가 비즈니스용 Skype Web App에서 공유 하는 경우</span><span class="sxs-lookup"><span data-stu-id="c4d4e-230">If a user is sharing from the Skype for Business Web App.</span></span>
- <span data-ttu-id="c4d4e-231">다른 사용자가 Mac에서 비즈니스용 Skype를 사용 하 고 있고 비즈니스용 skype Online 또는 비즈니스용 skype 서버 2015에서 7 월, 2018 누적 업데이트 (이상)가 있는 경우는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-231">If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).</span></span>
- <span data-ttu-id="c4d4e-232">다른 사용자가 프로그램/Windows 공유를 시작 하는 경우</span><span class="sxs-lookup"><span data-stu-id="c4d4e-232">If someone starts any Program/Windows Sharing.</span></span>
- <span data-ttu-id="c4d4e-233">누군가 세션 기록을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-233">If someone starts recording the session.</span></span>
- <span data-ttu-id="c4d4e-234">세션 중에 다른 사용자가 원격 화면 제어를 호출 하는 경우</span><span class="sxs-lookup"><span data-stu-id="c4d4e-234">If someone invokes Remote Screen Control during the session.</span></span> 
- <span data-ttu-id="c4d4e-235">참가자가 250 명 이상인 모임 (현재 VbSS가 지원 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="c4d4e-235">Meetings with more than 250 participants (where VbSS is not currently supported).</span></span>

<span data-ttu-id="c4d4e-236">세션이 RDP로 전환 되 면 다시 VbSS로 전환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-236">Be aware that once the session transitions to RDP it will not transition back to VbSS.</span></span> <span data-ttu-id="c4d4e-237">다시 말하지만, VbSS 로부터의 전환은 원활한 것 이며, 대부분의 상황에서 쉽게 검색할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-237">Again, the transition from VbSS is meant to be seamless, and, with hope, will not be easy to detect in most situations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c4d4e-238">비즈니스용 Skype 화면 공유에서 VbSS에서 RDP로의 전환을 차단 하거나 차단을 시도할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-238">It's not supported to block, or attempt to block, transition from VbSS to RDP in Skype for Business screen-sharing.</span></span> 
  
## <a name="enabling-disabling-and-configuring-vbss"></a><span data-ttu-id="c4d4e-239">VbSS 사용, 사용 안 함 및 구성</span><span class="sxs-lookup"><span data-stu-id="c4d4e-239">Enabling, disabling, and configuring VbSS</span></span>

<span data-ttu-id="c4d4e-240">C U 3 (비즈니스용 Skype 서버 2015 누적 업데이트 3) 이상을 설치한 후에는 모든 사용자가 기본적으로 1 ~ 1, 멀티 당사자 VbSS를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-240">The great thing is, once you've installed the Skype for Business Server 2015 Cumulative Update 3 (CU3) or later, all your users will be enabled for 1-to-1 and multi-party VbSS by default.</span></span> <span data-ttu-id="c4d4e-241">모든 사용자에 대해이 기능을 사용 하도록 설정 하지 않은 이유가 있는 경우에는이로 인해 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-241">This may be problematic for you if you have a reason to not have this functionality enabled for all your users.</span></span> <span data-ttu-id="c4d4e-242">이 경우 다음 단계를 사용 하 여 사용자가 사용 하지 않도록 설정할 수 있습니다 (사용자 단계를 수행할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="c4d4e-242">In that case, you're able to use these steps to disable users (the enable users steps will follow):</span></span>
  
### <a name="how-to-disable-users-from-using-vbss"></a><span data-ttu-id="c4d4e-243">사용자가 VbSS를 사용 하지 못하도록 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="c4d4e-243">How to disable users from using VbSS</span></span>

- <span data-ttu-id="c4d4e-244">비즈니스용 Skype 관리 콘솔에서이 cmdlet을 실행 하 여 vbss를 사용 하지 않는 사용자에 게 vbss를 허용 하지 않는 사용자 정책을 할당할 수 있습니다 ([PolicyName]을이 작업을 수행 하는 정책으로 바꾸기).</span><span class="sxs-lookup"><span data-stu-id="c4d4e-244">You can assign a user policy that doesn't allow VbSS to any users who shouldn't be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- <span data-ttu-id="c4d4e-245">또한 할당 된 정책이 없는 모든 사용자에 게 영향을 주는 전역 회의 정책을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-245">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    <span data-ttu-id="c4d4e-246">이 명령에 대 한 자세한 내용은 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-246">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="c4d4e-247">VbSS를 완전히 해제 해야 하는 경우 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-247">If you need to turn VbSS off completely, you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    <span data-ttu-id="c4d4e-248">이 명령에 대 한 자세한 내용은 [get-csmediaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-248">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c4d4e-249">단체 비즈니스용 Skype 모임에서 모든 클라이언트 끝점은 모임 이끌이의 정책 설정을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-249">In a multiparty Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
### <a name="how-to-enable-users-to-use-vbss"></a><span data-ttu-id="c4d4e-250">사용자가 VbSS를 사용할 수 있도록 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="c4d4e-250">How to enable users to use VbSS</span></span>

- <span data-ttu-id="c4d4e-251">비즈니스용 Skype 관리 콘솔에서이 cmdlet을 실행 하 여 vbss를 사용 해야 하는 사용자에 게 PolicyName를 허용 하는 특정 사용자 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-251">You can assign a specific user policy that allows VbSS to any users who need to be using VbSS by running this cmdlet in the Skype for Business Management Console (replace [PolicyName] with the policy you're doing this for):</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- <span data-ttu-id="c4d4e-252">또한 할당 된 정책이 없는 모든 사용자에 게 영향을 주는 전역 회의 정책을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-252">You also can update the global conferencing policy, which will affect all users without an assigned policy:</span></span>
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    <span data-ttu-id="c4d4e-253">이 명령에 대 한 자세한 내용은 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-253">For more information on this command, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
    
- <span data-ttu-id="c4d4e-254">일단 전원을 끈 후에 VbSS를 해제 해야 하는 경우 (기본적으로 설정), 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-254">If you need to turn VbSS back on after turning it off (it's on by default), you can run this command:</span></span>
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    <span data-ttu-id="c4d4e-255">이 명령에 대 한 자세한 내용은 [get-csmediaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-255">For more information on this command, see [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).</span></span>
    
> [!NOTE]
> <span data-ttu-id="c4d4e-256">여러 사용자의 비즈니스용 Skype 모임에서 모든 클라이언트 끝점은 모임 이끌이의 정책 설정을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d4e-256">In a multi-party Skype for Business meeting, all client endpoints will respect the policy setting for the meeting organizer.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c4d4e-257">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4d4e-257">See also</span></span>

[<span data-ttu-id="c4d4e-258">비즈니스용 Skype 서버 2015 누적 업데이트 KB3061064</span><span class="sxs-lookup"><span data-stu-id="c4d4e-258">Skype for Business Server 2015 Cumulative Update KB3061064</span></span>](https://www.microsoft.com/download/details.aspx?id=47690)
  
[<span data-ttu-id="c4d4e-259">비즈니스용 Skype 서버 2015에서 비디오 기반 화면 공유 (VBSS)를 사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="c4d4e-259">Video-based screen-sharing (VBSS) is available in Skype for Business Server 2015</span></span>](https://support.microsoft.com/kb/3170163)
