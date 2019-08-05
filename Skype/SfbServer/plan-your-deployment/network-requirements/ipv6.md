---
title: 비즈니스용 Skype의 IPv6 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: '요약: 비즈니스용 Skype 서버를 설치 하기 전에 IPv6을 구현 합니다.'
ms.openlocfilehash: e4af5403ce416332ec7c75ca26522038fd9c42df
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196858"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a><span data-ttu-id="61c61-103">비즈니스용 Skype의 IPv6 계획</span><span class="sxs-lookup"><span data-stu-id="61c61-103">Plan for IPv6 in Skype for Business</span></span>
 
<span data-ttu-id="61c61-104">**요약:** 비즈니스용 Skype 서버를 설치 하기 전에 IPv6을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-104">**Summary:** Implement IPv6 before you install Skype for Business Server.</span></span>
  
<span data-ttu-id="61c61-105">비즈니스용 Skype 서버에는 ip 버전 6(Ipv6) 주소에 대 한 지원과 함께 IP 버전 4 (IPv4) 주소를 계속 사용할 수 있는 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-105">Skype for Business Server includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> 

<span data-ttu-id="61c61-106">IPv4 주소는 컴퓨터에서 인터넷을 통해 통신할 수 있도록 하는 32 비트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="61c61-107">전세계 장치 수가 증가 함에 따라 사용 가능한 IPv4 주소가 초과 되었습니다. 이 때문에 많은 새 장치가 IPv6 주소를 사용 하도록 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="61c61-108">IPv6 주소는 IPv4 주소와 동일한 기능을 수행 하지만 (일부 추가 기능 포함), 32 비트만 사용 하는 대신 128 비트를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="61c61-109">이렇게 하면 새 주소 집합 뿐만 아니라 훨씬 더 많은 수가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> 

<span data-ttu-id="61c61-110">일반적인 IPv4 주소는 다음과 같이 표시 됩니다. 192.0.2.235, IPv6 주소는 다음과 같습니다: 2001:0db8:85a3:0000:0000:8a2e: 0370:7334.</span><span class="sxs-lookup"><span data-stu-id="61c61-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="61c61-111">IPv6 주소를 사용 하는 디바이스의 서식 및 기능 변경에는 비즈니스용 Skype 서버 설치에 몇 가지 배포 및 구성 고려 사항이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Skype for Business Server installation.</span></span> 

<span data-ttu-id="61c61-112">이 항목에서는 다음 섹션을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-112">This topic includes the following sections:</span></span>
  
- [<span data-ttu-id="61c61-113">IP 주소 유형 개요</span><span class="sxs-lookup"><span data-stu-id="61c61-113">Overview of IP address types</span></span>](ipv6.md#over)
    
- [<span data-ttu-id="61c61-114">IPv6에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="61c61-114">Technical requirements for IPv6</span></span>](ipv6.md#tech)
    
- [<span data-ttu-id="61c61-115">IPv6에 대한 마이그레이션 및 동시 사용 고려 사항</span><span class="sxs-lookup"><span data-stu-id="61c61-115">Migration and coexistence considerations for IPv6</span></span>](ipv6.md#migration)
    
<span data-ttu-id="61c61-116">IPv6 주소를 사용 하 게 되는 경우 비즈니스용 [Skype 문서에서 IP 주소 유형 구성](ip-address-types.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61c61-116">If you determine you will be using IPv6 addresses, refer to the [Configure IP address types in Skype for Business](ip-address-types.md) article.</span></span>
  
## <a name="overview-of-ip-address-types"></a><span data-ttu-id="61c61-117">IP 주소 유형 개요</span><span class="sxs-lookup"><span data-stu-id="61c61-117">Overview of IP address types</span></span>
<span data-ttu-id="61c61-118"><a name="over"> </a></span><span class="sxs-lookup"><span data-stu-id="61c61-118"></span></span>

<span data-ttu-id="61c61-119">비즈니스용 Skype 서버에서 IP 주소를 구성할 때는 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-119">You have three options when configuring IP addresses in Skype for Business Server.</span></span> <span data-ttu-id="61c61-120">IPv4 (IP 버전 4)만 지원 하도록 비즈니스용 Skype 서버를 구성 하거나 (IP 버전 6), IPv6 또는 둘 다 (이중 스택 이라고 함)를 조합 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-120">You can configure Skype for Business Server to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a dual stack).</span></span> <span data-ttu-id="61c61-121">각 구성 유형에 대해 고려해 야 할 몇 가지 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-121">There are several issues to consider with each type of configuration:</span></span>
  
- <span data-ttu-id="61c61-122">**IPv4만** 세계에 IPv4 주소가 부족 하 여 IPv6이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-122">**IPv4 only** IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="61c61-123">궁극적으로 IPv6은 전세계에서 완벽 하 게 지원 되지만 이번에는 엔터프라이즈에서 아직 IPv6을 지원 하지 않는 것으로 통신 해야 하는 많은 회사 및 장치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-123">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="61c61-124">IPv4 전용 구성은 비즈니스용 Skype 서버 구현이 대부분의 기존 장치와 통신할 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-124">An IPv4-only configuration will help to ensure that your Skype for Business Server implementation can communicate with most existing devices.</span></span>
    
- <span data-ttu-id="61c61-125">**IPv6만** 반대로, 전체 IPv6 구현은 기존의 여러 장치와 통신을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-125">**IPv6 only** Conversely, a full IPv6 implementation will exclude communication with many existing devices.</span></span>
    
- <span data-ttu-id="61c61-126">**이중 스택** 이중 스택은 IPv4 및 IPv6 주소를 모두 사용할 수 있는 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-126">**Dual Stack** Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="61c61-127">이 구성은 대부분의 경우 전체 IPv4에서 full-IPv6으로 전환 하는 데 몇 년이 소요 되므로 비즈니스용 Skype 서버에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-127">This configuration is supported in Skype for Business Server because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>
    
<span data-ttu-id="61c61-128">다음 섹션에서는 다양 한 비즈니스용 Skype 서버 기능에 대 한 세 가지 구성 간의 호환성을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-128">The following sections outline the compatibility among these three configurations for various Skype for Business Server features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61c61-129">IPv6을 사용 하는 클라이언트 또는 서버 구성은 랩 또는 유효성 검사 용도로만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-129">Client or server configuration with IPv6 only is supported only for lab or validation purposes.</span></span> <span data-ttu-id="61c61-130">IPv6 전용 구성은 프로덕션 배포에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-130">IPv6 only configuration is not supported in the production deployment.</span></span> 
  
### <a name="client-registration"></a><span data-ttu-id="61c61-131">클라이언트 등록</span><span class="sxs-lookup"><span data-stu-id="61c61-131">Client Registration</span></span>
<span data-ttu-id="61c61-132"><a name="client"> </a></span><span class="sxs-lookup"><span data-stu-id="61c61-132"></span></span>

|<span data-ttu-id="61c61-133">**클라이언트 끝점 네트워크**</span><span class="sxs-lookup"><span data-stu-id="61c61-133">**Client endpoint network**</span></span>|<span data-ttu-id="61c61-134">**서버 네트워크**</span><span class="sxs-lookup"><span data-stu-id="61c61-134">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61c61-135">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-135">IPv4</span></span>  <br/> |<span data-ttu-id="61c61-136">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-136">IPv4</span></span>  <br/> |
|<span data-ttu-id="61c61-137">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-137">IPv4</span></span>  <br/> |<span data-ttu-id="61c61-138">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-138">Dual stack</span></span>  <br/> |
|<span data-ttu-id="61c61-139">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-139">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-140">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-140">IPv4</span></span>  <br/> |
|<span data-ttu-id="61c61-141">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-141">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-142">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-142">Dual stack</span></span>  <br/> |
|<span data-ttu-id="61c61-143">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-143">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-144">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-144">IPv6</span></span>  <br/> |
|<span data-ttu-id="61c61-145">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-145">IPv6</span></span>  <br/> |<span data-ttu-id="61c61-146">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-146">Dual stack</span></span>  <br/> |
|<span data-ttu-id="61c61-147">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-147">IPv6</span></span>  <br/> |<span data-ttu-id="61c61-148">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-148">IPv6</span></span>  <br/> |
   
### <a name="peer-to-peer-client"></a><span data-ttu-id="61c61-149">피어 투 피어 클라이언트</span><span class="sxs-lookup"><span data-stu-id="61c61-149">Peer-to-Peer Client</span></span>
<span data-ttu-id="61c61-150"><a name="peer"> </a></span><span class="sxs-lookup"><span data-stu-id="61c61-150"></span></span>

<span data-ttu-id="61c61-151">피어 투 피어 통신에는 오디오, 오디오/비디오, 응용 프로그램 공유, 파일 전송이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-151">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="61c61-152">두 클라이언트가 성공적으로 등록 되 면 다음 조합이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-152">After both clients have successfully registered, the following combinations are supported.</span></span>
  
|<span data-ttu-id="61c61-153">**클라이언트 끝점 1**</span><span class="sxs-lookup"><span data-stu-id="61c61-153">**Client endpoint 1**</span></span>|<span data-ttu-id="61c61-154">**클라이언트 끝점 2**</span><span class="sxs-lookup"><span data-stu-id="61c61-154">**Client endpoint 2**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61c61-155">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-155">IPv4</span></span>  <br/> |<span data-ttu-id="61c61-156">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-156">IPv4</span></span>  <br/> |
|<span data-ttu-id="61c61-157">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-157">IPv4</span></span>  <br/> |<span data-ttu-id="61c61-158">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-158">Dual stack</span></span>  <br/> |
|<span data-ttu-id="61c61-159">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-159">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-160">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-160">Dual stack</span></span>  <br/> |
|<span data-ttu-id="61c61-161">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-161">IPv6</span></span>  <br/> |<span data-ttu-id="61c61-162">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-162">Dual stack</span></span>  <br/> |
|<span data-ttu-id="61c61-163">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-163">IPv6</span></span>  <br/> |<span data-ttu-id="61c61-164">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-164">IPv6</span></span>  <br/> |
   
### <a name="conferencing"></a><span data-ttu-id="61c61-165">회의</span><span class="sxs-lookup"><span data-stu-id="61c61-165">Conferencing</span></span>
<span data-ttu-id="61c61-166"><a name="conf"> </a></span><span class="sxs-lookup"><span data-stu-id="61c61-166"></span></span>

<span data-ttu-id="61c61-167">회의에는 오디오/비디오, 응용 프로그램 공유, whiteboarding 및 파일 공유와 같은 데이터 공동 작업 응용 프로그램이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-167">Conferencing includes audio/video, application sharing, and data collaboration applications like whiteboarding and file sharing.</span></span>
  
|<span data-ttu-id="61c61-168">**클라이언트 끝점 네트워크**</span><span class="sxs-lookup"><span data-stu-id="61c61-168">**Client endpoint network**</span></span>|<span data-ttu-id="61c61-169">**서버 네트워크**</span><span class="sxs-lookup"><span data-stu-id="61c61-169">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61c61-170">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-170">IPv4</span></span>  <br/> |<span data-ttu-id="61c61-171">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-171">IPv4</span></span>  <br/> |
|<span data-ttu-id="61c61-172">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-172">IPv4</span></span>  <br/> |<span data-ttu-id="61c61-173">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-173">Dual stack</span></span>  <br/> |
|<span data-ttu-id="61c61-174">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-174">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-175">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-175">IPv4</span></span>  <br/> |
|<span data-ttu-id="61c61-176">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-176">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-177">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-177">Dual stack</span></span>  <br/> |
|<span data-ttu-id="61c61-178">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-178">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-179">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-179">IPv6</span></span>  <br/> |
|<span data-ttu-id="61c61-180">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-180">IPv6</span></span>  <br/> |<span data-ttu-id="61c61-181">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-181">Dual stack</span></span>  <br/> |
|<span data-ttu-id="61c61-182">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-182">IPv6</span></span>  <br/> |<span data-ttu-id="61c61-183">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-183">IPv6</span></span>  <br/> |
   
### <a name="mediation-serverpstn"></a><span data-ttu-id="61c61-184">중재 서버/PSTN</span><span class="sxs-lookup"><span data-stu-id="61c61-184">Mediation Server/PSTN</span></span>
<span data-ttu-id="61c61-185"><a name="med"> </a></span><span class="sxs-lookup"><span data-stu-id="61c61-185"></span></span>

<span data-ttu-id="61c61-186">비즈니스용 Skype 서버는 트래픽이 IPv6 인터페이스를 사용 하는 경우에는 PSTN (공개 통신 네트워크) 통화에 대 한 미디어 바이패스를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-186">Skype for Business Server does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="61c61-187">미디어 바이패스가 필요한 경우 PSTN 게이트웨이가 IPv4로 구성 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-187">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span> 
  
|<span data-ttu-id="61c61-188">**기본 인터페이스 1**</span><span class="sxs-lookup"><span data-stu-id="61c61-188">**Primary interface 1**</span></span>|<span data-ttu-id="61c61-189">**PSTN 인터페이스 (중재 서버에서)**</span><span class="sxs-lookup"><span data-stu-id="61c61-189">**PSTN interface (on Mediation Server)**</span></span>|<span data-ttu-id="61c61-190">**PSTN 게이트웨이 설정**</span><span class="sxs-lookup"><span data-stu-id="61c61-190">**PSTN gateway setting**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="61c61-191">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-191">IPv4</span></span>  <br/> |<span data-ttu-id="61c61-192">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-192">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-193">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-193">IPv4</span></span>  <br/> |
|<span data-ttu-id="61c61-194">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-194">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-195">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-195">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-196">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-196">IPv4</span></span>  <br/> |
|<span data-ttu-id="61c61-197">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-197">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-198">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-198">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-199">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-199">IPv6</span></span>  <br/> |
   
1. <span data-ttu-id="61c61-200">기본 인터페이스는 비즈니스용 Skype 서버 구성 요소와 통신 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-200">The primary interface is the interface that communicates with the Skype for Business Server components.</span></span>
  
### <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="61c61-201">원격 사용자 피어 투 피어 통신</span><span class="sxs-lookup"><span data-stu-id="61c61-201">Remote User Peer-to-Peer Communications</span></span>
<span data-ttu-id="61c61-202"><a name="remote"> </a></span><span class="sxs-lookup"><span data-stu-id="61c61-202"></span></span>

<span data-ttu-id="61c61-203">원격 사용자와의 피어 투 피어 통신에는 인스턴트 메시지, 오디오/비디오, 응용 프로그램 공유, 파일 전송 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-203">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>
  
|<span data-ttu-id="61c61-204">**원격 사용자 네트워크**</span><span class="sxs-lookup"><span data-stu-id="61c61-204">**Remote user network**</span></span>|<span data-ttu-id="61c61-205">**Edge 서버 (외부 가장자리)**</span><span class="sxs-lookup"><span data-stu-id="61c61-205">**Edge server (External edge)**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61c61-206">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-206">IPv4</span></span>  <br/> |<span data-ttu-id="61c61-207">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-207">IPv4</span></span>  <br/> |
|<span data-ttu-id="61c61-208">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-208">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-209">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="61c61-209">IPv4</span></span>  <br/> |
|<span data-ttu-id="61c61-210">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-210">Dual stack</span></span>  <br/> |<span data-ttu-id="61c61-211">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-211">Dual stack</span></span>  <br/> |
|<span data-ttu-id="61c61-212">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-212">IPv6</span></span>  <br/> |<span data-ttu-id="61c61-213">이중 스택</span><span class="sxs-lookup"><span data-stu-id="61c61-213">Dual stack</span></span>  <br/> |
|<span data-ttu-id="61c61-214">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-214">IPv6</span></span>  <br/> |<span data-ttu-id="61c61-215">Ipv4/ipv6</span><span class="sxs-lookup"><span data-stu-id="61c61-215">IPv6</span></span>  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="61c61-216">프런트 엔드 풀 및 Edge 풀 구성</span><span class="sxs-lookup"><span data-stu-id="61c61-216">Front End Pool and Edge Pool Configuration</span></span>
<span data-ttu-id="61c61-217"><a name="FE_pool"> </a></span><span class="sxs-lookup"><span data-stu-id="61c61-217"></span></span>

<span data-ttu-id="61c61-218">다음 표에는 프런트 엔드 서버 풀과 내부 Edge 서버 풀 사이의 지원 행렬이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-218">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>
  
<span data-ttu-id="61c61-219">**프런트 엔드 풀 및 Edge 풀 (내부에 지) 행렬**</span><span class="sxs-lookup"><span data-stu-id="61c61-219">**Front End Pool and Edge Pool (Internal Edge) Matrix**</span></span>

||<span data-ttu-id="61c61-220">**Edge 풀: IPv4**</span><span class="sxs-lookup"><span data-stu-id="61c61-220">**Edge Pool: IPv4**</span></span> <br/> |<span data-ttu-id="61c61-221">**Edge 풀: 이중 스택**</span><span class="sxs-lookup"><span data-stu-id="61c61-221">**Edge Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="61c61-222">**Edge 풀: IPv6**</span><span class="sxs-lookup"><span data-stu-id="61c61-222">**Edge Pool: IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61c61-223">**프런트 엔드 풀: IPv4**</span><span class="sxs-lookup"><span data-stu-id="61c61-223">**Front End Pool: IPv4**</span></span> <br/> |<span data-ttu-id="61c61-224">'</span><span class="sxs-lookup"><span data-stu-id="61c61-224">Yes</span></span>  <br/> |<span data-ttu-id="61c61-225">'</span><span class="sxs-lookup"><span data-stu-id="61c61-225">Yes</span></span>  <br/> |<span data-ttu-id="61c61-226">아니요</span><span class="sxs-lookup"><span data-stu-id="61c61-226">No</span></span>  <br/> |
|<span data-ttu-id="61c61-227">**프런트 엔드 풀: 이중 스택**</span><span class="sxs-lookup"><span data-stu-id="61c61-227">**Front End Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="61c61-228">'</span><span class="sxs-lookup"><span data-stu-id="61c61-228">Yes</span></span>  <br/> |<span data-ttu-id="61c61-229">'</span><span class="sxs-lookup"><span data-stu-id="61c61-229">Yes</span></span>  <br/> |<span data-ttu-id="61c61-230">아니요</span><span class="sxs-lookup"><span data-stu-id="61c61-230">No</span></span>  <br/> |
|<span data-ttu-id="61c61-231">**프런트 엔드 풀: IPv6**</span><span class="sxs-lookup"><span data-stu-id="61c61-231">**Front End Pool: IPv6**</span></span> <br/> |<span data-ttu-id="61c61-232">아니요</span><span class="sxs-lookup"><span data-stu-id="61c61-232">No</span></span>  <br/> |<span data-ttu-id="61c61-233">아니요</span><span class="sxs-lookup"><span data-stu-id="61c61-233">No</span></span>  <br/> |<span data-ttu-id="61c61-234">'\*</span><span class="sxs-lookup"><span data-stu-id="61c61-234">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="61c61-235">\*랩 환경 에서만이 조합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-235">\* Use this combination only in a lab environment.</span></span>
  
<span data-ttu-id="61c61-236">다음 표는 내부 및 외부 경계 인터페이스의 지원 되는 조합의 행렬입니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-236">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>
  
<span data-ttu-id="61c61-237">**Edge 풀 (내부에 지) 및 Edge 풀 (외부 가장자리) 행렬**</span><span class="sxs-lookup"><span data-stu-id="61c61-237">**Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix**</span></span>

||<span data-ttu-id="61c61-238">**Edge 풀 (외부 가장자리): IPv4**</span><span class="sxs-lookup"><span data-stu-id="61c61-238">**Edge Pool (External Edge) : IPv4**</span></span> <br/> |<span data-ttu-id="61c61-239">**Edge 풀 (외부 가장자리): 이중 스택**</span><span class="sxs-lookup"><span data-stu-id="61c61-239">**Edge Pool (External Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="61c61-240">**Edge 풀 (외부에 지): IPv6**</span><span class="sxs-lookup"><span data-stu-id="61c61-240">**Edge Pool (External Edge): IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61c61-241">**Edge 풀 (내부에 지): IPv4**</span><span class="sxs-lookup"><span data-stu-id="61c61-241">**Edge Pool (Internal Edge): IPv4**</span></span> <br/> |<span data-ttu-id="61c61-242">'</span><span class="sxs-lookup"><span data-stu-id="61c61-242">Yes</span></span>  <br/> |<span data-ttu-id="61c61-243">'</span><span class="sxs-lookup"><span data-stu-id="61c61-243">Yes</span></span>  <br/> |<span data-ttu-id="61c61-244">아니요</span><span class="sxs-lookup"><span data-stu-id="61c61-244">No</span></span>  <br/> |
|<span data-ttu-id="61c61-245">**Edge 풀 (내부에 지): 이중 스택**</span><span class="sxs-lookup"><span data-stu-id="61c61-245">**Edge Pool (Internal Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="61c61-246">아니요</span><span class="sxs-lookup"><span data-stu-id="61c61-246">No</span></span>  <br/> |<span data-ttu-id="61c61-247">'</span><span class="sxs-lookup"><span data-stu-id="61c61-247">Yes</span></span>  <br/> |<span data-ttu-id="61c61-248">아니요</span><span class="sxs-lookup"><span data-stu-id="61c61-248">No</span></span>  <br/> |
|<span data-ttu-id="61c61-249">**Edge 풀 (내부에 지): IPv6**</span><span class="sxs-lookup"><span data-stu-id="61c61-249">**Edge Pool (Internal Edge): IPv6**</span></span> <br/> |<span data-ttu-id="61c61-250">아니요</span><span class="sxs-lookup"><span data-stu-id="61c61-250">No</span></span>  <br/> |<span data-ttu-id="61c61-251">아니요</span><span class="sxs-lookup"><span data-stu-id="61c61-251">No</span></span>  <br/> |<span data-ttu-id="61c61-252">'\*</span><span class="sxs-lookup"><span data-stu-id="61c61-252">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="61c61-253">\*랩 환경 에서만이 조합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-253">\* Use this combination only in a lab environment.</span></span>
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="61c61-254">IPv6에 대 한 고급 엔터프라이즈 음성 지원</span><span class="sxs-lookup"><span data-stu-id="61c61-254">Advanced Enterprise Voice Support for IPv6</span></span>
<span data-ttu-id="61c61-255"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="61c61-255"></span></span>

<span data-ttu-id="61c61-256">CAC (호출 허용 제어), 향상 된 9-1-1 (E9-1-1) 또는 미디어 바이패스를 포함 하는 배포는 IPv4 전용 또는 듀얼 누적 구현으로 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-256">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span> <span data-ttu-id="61c61-257">IPv6만 사용 하는 끝점은 이러한 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-257">Endpoints using only IPv6 cannot use any of these features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61c61-258">듀얼 누적 배포의 경우 비즈니스용 skype 서버 클라이언트가 IPv6을 사용 하 여 비즈니스용 Skype 서버에 연결 하더라도 비즈니스용 Skype 서버는 E9-1-1을 지원 하기 위해 적절 한 IPv4 주소를 매핑하는 데 가장 좋은 노력을 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-258">In a dual-stacked deployment, even if a Skype for Business Server client connects to a Skype for Business Server by using IPv6, Skype for Business Server will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span> 
  
<span data-ttu-id="61c61-259">IPv6 주소를 사용 하는 위치 정보 서비스는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-259">Location Information service with IPv6 addresses is not supported.</span></span>
  
<span data-ttu-id="61c61-260">UM (통합 메시징)는 IPv6을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-260">Exchange Unified Messaging (UM) does not support IPv6.</span></span> <span data-ttu-id="61c61-261">Exchange UM의 경우 DNS 확인이 IPv6 주소를 반환 하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-261">For Exchange UM, be sure that DNS resolution does not return an IPv6 address.</span></span> <span data-ttu-id="61c61-262">전화를 음성 메일로 보내면 IPv6을 사용 하면 오류를 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-262">Using IPv6 may cause failure when calls are sent to voice mail.</span></span> 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a><span data-ttu-id="61c61-263">IPv6에 대 한 다른 비즈니스용 Skype 서버 기능 지원</span><span class="sxs-lookup"><span data-stu-id="61c61-263">Other Skype for Business Server Feature Support for IPv6</span></span>
<span data-ttu-id="61c61-264"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="61c61-264"></span></span>

<span data-ttu-id="61c61-265">앞에서 언급 한 기능 및 구성 요소 외에도 비즈니스용 Skype Server는 다음 기능에 대 한 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-265">In addition to the features and components mentioned previously, Skype for Business Server supports IPv6 for the following features:</span></span>
  
- <span data-ttu-id="61c61-266">**영구 채팅**</span><span class="sxs-lookup"><span data-stu-id="61c61-266">**Persistent Chat**</span></span>
    
    <span data-ttu-id="61c61-267">토폴로지 작성기를 사용 하 여 영구 채팅을 위해 IPv6을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-267">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="61c61-268">영구 채팅 구성에 대 한 자세한 내용은 영구 채팅 서버 배포 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61c61-268">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>
    
- <span data-ttu-id="61c61-269">**경력 (체감 품질) 및 통화 정보 기록 (CDR) 보고서**</span><span class="sxs-lookup"><span data-stu-id="61c61-269">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="61c61-270">모니터링 보고서에는 IPv4 또는 IPv6 유형에 관계 없이 모니터링 서버 데이터베이스에 저장 되는 IP 주소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-270">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>
    
## <a name="technical-requirements-for-ipv6"></a><span data-ttu-id="61c61-271">IPv6에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="61c61-271">Technical requirements for IPv6</span></span>
<span data-ttu-id="61c61-272"><a name="tech"> </a></span><span class="sxs-lookup"><span data-stu-id="61c61-272"></span></span>

<span data-ttu-id="61c61-273">IPv6 용 비즈니스용 Skype Server를 구성 하려는 경우 다음 요구 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-273">If you plan to configure Skype for Business Server for IPv6, keep the following requirements in mind:</span></span>
  
- <span data-ttu-id="61c61-274">비즈니스용 Skype Server에서 IPv6 주소를 사용 하려면 IPv6 주소로 검색 하 고 확인 해야 하는 레코드에 대 한 DNS (domain name system) 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-274">To use IPv6 addresses with Skype for Business Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="61c61-275">IPv6 DNS가 호스트 AAAA (쿼드-A) 레코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-275">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="61c61-276">배포에 IPv4와 IPv6을 모두 사용 하는 경우 IPv4에 대 한 호스트 A 레코드와 IPv6의 호스트 AAAA 레코드를 모두 구성 하 고 유지 관리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-276">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="61c61-277">배포를 IPv6으로 완전히 전환 하더라도 여전히 IPv4를 사용 하는 외부 사용자에 대해 IPv4 DNS 호스트 레코드가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-277">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="61c61-278">Ipv6 사용을 시작 하기 전에 IPv6 DNS 호스트 레코드를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-278">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="61c61-279">클라이언트나 서버에서 IPv6을 사용 하지 않는 경우 레코드가 참조 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-279">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="61c61-280">전환 기술에는 변환 기술 구성 및 정책에 따라 어떤 레코드를 사용할지 결정 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-280">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>
    
- <span data-ttu-id="61c61-281">각 IPv6 주소에는 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-281">Each IPv6 address has a scope.</span></span> <span data-ttu-id="61c61-282">Ipv6 주소 지정에 사용할 수 있는 세 가지 범위는 IPv6 전역 주소 (공용 IPv4 주소와 유사), IPv6 고유 로컬 주소 (사설 IPv4 주소 범위와 비슷함), IPv6 링크 로컬 주소 (다음의 자동 개인 IP 주소와 유사) IPv4 용 Windows Server).</span><span class="sxs-lookup"><span data-stu-id="61c61-282">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="61c61-283">풀 내의 모든 서버에는 동일한 범위의 IPv6 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-283">All the servers within a pool should have IPv6 addresses with the same scope.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="61c61-284">IPv6은 복잡 한 주제로, 네트워크 팀과 인터넷 공급자와의 신중한 계획이 필요 하며, Windows Server 수준에서 지정 하는 주소와 비즈니스용 Skype 서버 수준이 제대로 작동 하는지 확인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-284">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Skype for Business Server level work as expected.</span></span> <span data-ttu-id="61c61-285">IPv6 주소 지정 및 계획에 대 한 추가 리소스는이 항목의 끝부분에 있는 링크를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61c61-285">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span> 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a><span data-ttu-id="61c61-286">IPv6에 대한 마이그레이션 및 동시 사용 고려 사항</span><span class="sxs-lookup"><span data-stu-id="61c61-286">Migration and coexistence considerations for IPv6</span></span>
<span data-ttu-id="61c61-287"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="61c61-287"></span></span>

<span data-ttu-id="61c61-288">Lync Server 2010 또는 Office Communications Server에서는 IPv6 (IP 버전 6)이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-288">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="61c61-289">시험 운용 목적으로 Lync Server 2010 및 비즈니스용 Skype 서버 이중 스택 공존을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-289">For piloting purposes, you can test Lync Server 2010 and Skype for Business Server dual-stack coexistence.</span></span> <span data-ttu-id="61c61-290">모든 풀에 대해 IPv6 (듀얼 스택 네트워크)을 사용 하도록 설정 하기 전에 지정 된 중앙 사이트의 모든 풀을 비즈니스용 Skype 서버로 업그레이드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-290">We recommend that all pools for a given central site are upgraded to Skype for Business Server before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="61c61-291">IPv6에 대해서만 풀을 구성 해야 하는 경우 테스트를 위해 랩 환경에서 IPv6 전용 풀을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-291">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>
  
<span data-ttu-id="61c61-292">마이그레이션 및 공존 중에 지원 되는 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-292">The following scenarios are supported during migration and coexistence:</span></span>
  
- <span data-ttu-id="61c61-293">IPv4 모드의 비즈니스용 skype 서버, Lync Server 2013 및 Lync Server 2010 풀은 듀얼 스택 모드의 비즈니스용 Skype 서버와 함께 공존할만 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-293">Skype for Business Server, Lync Server 2013, and Lync Server 2010 pools in IPv4 mode, coexisting with Skype for Business Server in dual-stack mode.</span></span>
    
- <span data-ttu-id="61c61-294">Ipv6 전용 풀에 siloed 인 경우에는 비즈니스용 Skype 서버 풀 for IPv6 전용 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="61c61-294">Skype for Business Server pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="61c61-295">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61c61-295">See also</span></span>
<span data-ttu-id="61c61-296"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="61c61-296"></span></span>

[<span data-ttu-id="61c61-297">비즈니스용 Skype에서 IP 주소 유형 구성</span><span class="sxs-lookup"><span data-stu-id="61c61-297">Configure IP address types in Skype for Business</span></span>](ip-address-types.md)

[<span data-ttu-id="61c61-298">IP 버전 6 주소 지정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="61c61-298">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)
  
[<span data-ttu-id="61c61-299">IPv6 글로벌 유니캐스트 주소 형식</span><span class="sxs-lookup"><span data-stu-id="61c61-299">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)
  
[<span data-ttu-id="61c61-300">고유한 로컬 IPv6 유니캐스트 주소</span><span class="sxs-lookup"><span data-stu-id="61c61-300">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)
