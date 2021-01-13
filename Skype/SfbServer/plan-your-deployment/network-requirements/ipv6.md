---
title: 비즈니스용 Skype의 IPv6 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: '요약: 비즈니스용 Skype 서버를 설치하기 전에 IPv6을 구현합니다.'
ms.openlocfilehash: dbb9977d8d11b130387eca9e87213c2760226142
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825248"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a><span data-ttu-id="143da-103">비즈니스용 Skype의 IPv6 계획</span><span class="sxs-lookup"><span data-stu-id="143da-103">Plan for IPv6 in Skype for Business</span></span>
 
<span data-ttu-id="143da-104">**요약:** 비즈니스용 Skype 서버를 설치하기 전에 IPv6을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-104">**Summary:** Implement IPv6 before you install Skype for Business Server.</span></span>
  
<span data-ttu-id="143da-105">비즈니스용 Skype 서버에는 IPv6(IP 버전 6) 주소에 대한 지원과 IPv4(IP 버전 4) 주소가 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="143da-105">Skype for Business Server includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> 

<span data-ttu-id="143da-106">IPv4 주소는 컴퓨터가 인터넷을 통해 통신할 수 있도록 하는 32비트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="143da-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="143da-107">전 세계적으로 증가하는 장치 수로 인해 사용 가능한 IPv4 주소가 모두 사용되었습니다. 이 때문에 많은 새 장치가 IPv6 주소를 사용하여 이동하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="143da-108">IPv6 주소는 IPv4 주소와 같은 기능을 수행하며 일부 추가 기능을 제공하지만, 32비트만 사용하는 대신 128비트도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="143da-109">따라서 새로운 주소 집합이 매우 많이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="143da-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> 

<span data-ttu-id="143da-110">일반적인 IPv4 주소는 192.0.2.235와 같으며, IPv6 주소는 2001:0db8:85a3:0000:0000:8a2e:0370:7334와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="143da-111">IPv6 주소를 사용하는 장치의 서식과 기능이 변경될 경우 비즈니스용 Skype 서버 설치 시 몇 가지 배포 및 구성을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Skype for Business Server installation.</span></span> 

<span data-ttu-id="143da-112">이 항목에는 다음 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-112">This topic includes the following sections:</span></span>
  
- [<span data-ttu-id="143da-113">IP 주소 유형 개요</span><span class="sxs-lookup"><span data-stu-id="143da-113">Overview of IP address types</span></span>](ipv6.md#over)
    
- [<span data-ttu-id="143da-114">IPv6에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="143da-114">Technical requirements for IPv6</span></span>](ipv6.md#tech)
    
- [<span data-ttu-id="143da-115">IPv6에 대한 마이그레이션 및 동시 사용 고려 사항</span><span class="sxs-lookup"><span data-stu-id="143da-115">Migration and coexistence considerations for IPv6</span></span>](ipv6.md#migration)
    
<span data-ttu-id="143da-116">IPv6 주소를 사용할 것으로 결정되면 비즈니스용 Skype 문서의 IP 주소 유형 [구성을 참조하세요.](ip-address-types.md)</span><span class="sxs-lookup"><span data-stu-id="143da-116">If you determine you will be using IPv6 addresses, refer to the [Configure IP address types in Skype for Business](ip-address-types.md) article.</span></span>
  
## <a name="overview-of-ip-address-types"></a><span data-ttu-id="143da-117">IP 주소 유형 개요</span><span class="sxs-lookup"><span data-stu-id="143da-117">Overview of IP address types</span></span>
<span data-ttu-id="143da-118"><a name="over"> </a></span><span class="sxs-lookup"><span data-stu-id="143da-118"><a name="over"> </a></span></span>

<span data-ttu-id="143da-119">비즈니스용 Skype 서버에서 IP 주소를 구성할 때 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-119">You have three options when configuring IP addresses in Skype for Business Server.</span></span> <span data-ttu-id="143da-120">IPv4(IP 버전 4), IPv6(IP 버전 6) 또는 두 가지의 조합(이중 스택)만 지원하도록 비즈니스용 Skype 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-120">You can configure Skype for Business Server to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a dual stack).</span></span> <span data-ttu-id="143da-121">구성 유형마다 고려해야 할 몇 가지 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-121">There are several issues to consider with each type of configuration:</span></span>
  
- <span data-ttu-id="143da-122">**IPv4만** IPv6은 IPv4 주소가 다수 사용 중이기 때문에 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-122">**IPv4 only** IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="143da-123">궁극적으로 IPv6은 전 세계에 완전히 지원되지만, 현재 기업에서 통신해야 할 수 있는 많은 회사 및 장치는 IPv6을 아직 지원하지 않고 당분 동안은 지원하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-123">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="143da-124">IPv4 전용 구성은 비즈니스용 Skype 서버 구현이 대부분의 기존 장치와 통신할 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="143da-124">An IPv4-only configuration will help to ensure that your Skype for Business Server implementation can communicate with most existing devices.</span></span>
    
- <span data-ttu-id="143da-125">**IPv6만** 반대로, 전체 IPv6 구현은 많은 기존 장치와의 통신을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-125">**IPv6 only** Conversely, a full IPv6 implementation will exclude communication with many existing devices.</span></span>
    
- <span data-ttu-id="143da-126">**이중 스택** 이중 스택은 IPv4 및 IPv6 주소가 모두 사용하도록 설정된 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="143da-126">**Dual Stack** Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="143da-127">이 구성은 대부분의 경우 전체 IPv4에서 전체 IPv6으로 전환하는 데 몇 년이 걸릴 것이기 때문에 비즈니스용 Skype 서버에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="143da-127">This configuration is supported in Skype for Business Server because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>
    
<span data-ttu-id="143da-128">다음 섹션에서는 다양한 비즈니스용 Skype 서버 기능에 대한 이러한 세 가지 구성 간 호환성을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-128">The following sections outline the compatibility among these three configurations for various Skype for Business Server features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="143da-p106">IPv6를 사용한 클라이언트 또는 서버 구성은 연구 또는 검사 목적으로만 지원됩니다. IPv6 전용 구성은 프로덕션 배포에는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-p106">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span> 
  
### <a name="client-registration"></a><span data-ttu-id="143da-131">클라이언트 등록</span><span class="sxs-lookup"><span data-stu-id="143da-131">Client Registration</span></span>
<span data-ttu-id="143da-132"><a name="client"> </a></span><span class="sxs-lookup"><span data-stu-id="143da-132"><a name="client"> </a></span></span>

|<span data-ttu-id="143da-133">**클라이언트 끝점 네트워크**</span><span class="sxs-lookup"><span data-stu-id="143da-133">**Client endpoint network**</span></span>|<span data-ttu-id="143da-134">**서버 네트워크**</span><span class="sxs-lookup"><span data-stu-id="143da-134">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="143da-135">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-135">IPv4</span></span>  <br/> |<span data-ttu-id="143da-136">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-136">IPv4</span></span>  <br/> |
|<span data-ttu-id="143da-137">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-137">IPv4</span></span>  <br/> |<span data-ttu-id="143da-138">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-138">Dual stack</span></span>  <br/> |
|<span data-ttu-id="143da-139">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-139">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-140">IPv4</span></span>  <br/> |
|<span data-ttu-id="143da-141">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-141">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-142">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-142">Dual stack</span></span>  <br/> |
|<span data-ttu-id="143da-143">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-143">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-144">IPv6</span></span>  <br/> |
|<span data-ttu-id="143da-145">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-145">IPv6</span></span>  <br/> |<span data-ttu-id="143da-146">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-146">Dual stack</span></span>  <br/> |
|<span data-ttu-id="143da-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-147">IPv6</span></span>  <br/> |<span data-ttu-id="143da-148">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-148">IPv6</span></span>  <br/> |
   
### <a name="peer-to-peer-client"></a><span data-ttu-id="143da-149">피어 투 피어 클라이언트</span><span class="sxs-lookup"><span data-stu-id="143da-149">Peer-to-Peer Client</span></span>
<span data-ttu-id="143da-150"><a name="peer"> </a></span><span class="sxs-lookup"><span data-stu-id="143da-150"><a name="peer"> </a></span></span>

<span data-ttu-id="143da-151">피어 투 피어 통신에는 오디오, 오디오/비디오, 응용 프로그램 공유 및 파일 전송이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="143da-151">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="143da-152">두 클라이언트가 성공적으로 등록된 후에는 다음 조합이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="143da-152">After both clients have successfully registered, the following combinations are supported.</span></span>
  
|<span data-ttu-id="143da-153">**클라이언트 끝점 1**</span><span class="sxs-lookup"><span data-stu-id="143da-153">**Client endpoint 1**</span></span>|<span data-ttu-id="143da-154">**클라이언트 끝점 2**</span><span class="sxs-lookup"><span data-stu-id="143da-154">**Client endpoint 2**</span></span>|
|:-----|:-----|
|<span data-ttu-id="143da-155">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-155">IPv4</span></span>  <br/> |<span data-ttu-id="143da-156">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-156">IPv4</span></span>  <br/> |
|<span data-ttu-id="143da-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-157">IPv4</span></span>  <br/> |<span data-ttu-id="143da-158">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-158">Dual stack</span></span>  <br/> |
|<span data-ttu-id="143da-159">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-159">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-160">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-160">Dual stack</span></span>  <br/> |
|<span data-ttu-id="143da-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-161">IPv6</span></span>  <br/> |<span data-ttu-id="143da-162">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-162">Dual stack</span></span>  <br/> |
|<span data-ttu-id="143da-163">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-163">IPv6</span></span>  <br/> |<span data-ttu-id="143da-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-164">IPv6</span></span>  <br/> |
   
### <a name="conferencing"></a><span data-ttu-id="143da-165">전화 회의</span><span class="sxs-lookup"><span data-stu-id="143da-165">Conferencing</span></span>
<span data-ttu-id="143da-166"><a name="conf"> </a></span><span class="sxs-lookup"><span data-stu-id="143da-166"><a name="conf"> </a></span></span>

<span data-ttu-id="143da-167">회의에는 오디오/비디오, 응용 프로그램 공유 및 화이트보드 및 파일 공유와 같은 데이터 공동 작업 응용 프로그램이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="143da-167">Conferencing includes audio/video, application sharing, and data collaboration applications like whiteboarding and file sharing.</span></span>
  
|<span data-ttu-id="143da-168">**클라이언트 끝점 네트워크**</span><span class="sxs-lookup"><span data-stu-id="143da-168">**Client endpoint network**</span></span>|<span data-ttu-id="143da-169">**서버 네트워크**</span><span class="sxs-lookup"><span data-stu-id="143da-169">**Server network**</span></span>|
|:-----|:-----|
|<span data-ttu-id="143da-170">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-170">IPv4</span></span>  <br/> |<span data-ttu-id="143da-171">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-171">IPv4</span></span>  <br/> |
|<span data-ttu-id="143da-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-172">IPv4</span></span>  <br/> |<span data-ttu-id="143da-173">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-173">Dual stack</span></span>  <br/> |
|<span data-ttu-id="143da-174">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-174">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-175">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-175">IPv4</span></span>  <br/> |
|<span data-ttu-id="143da-176">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-176">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-177">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-177">Dual stack</span></span>  <br/> |
|<span data-ttu-id="143da-178">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-178">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-179">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-179">IPv6</span></span>  <br/> |
|<span data-ttu-id="143da-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-180">IPv6</span></span>  <br/> |<span data-ttu-id="143da-181">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-181">Dual stack</span></span>  <br/> |
|<span data-ttu-id="143da-182">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-182">IPv6</span></span>  <br/> |<span data-ttu-id="143da-183">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-183">IPv6</span></span>  <br/> |
   
### <a name="mediation-serverpstn"></a><span data-ttu-id="143da-184">중재 서버/PSTN</span><span class="sxs-lookup"><span data-stu-id="143da-184">Mediation Server/PSTN</span></span>
<span data-ttu-id="143da-185"><a name="med"> </a></span><span class="sxs-lookup"><span data-stu-id="143da-185"><a name="med"> </a></span></span>

<span data-ttu-id="143da-186">트래픽이 IPv6 인터페이스를 통해 전송되는 경우 비즈니스용 Skype 서버는 PSTN(Public Switched Telephone Network) 통화에 대한 미디어 우회를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-186">Skype for Business Server does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="143da-187">미디어 바이패스가 필요할 경우 PSTN 게이트웨이를 IPv4로 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-187">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span> 
  
|<span data-ttu-id="143da-188">**기본 인터페이스 1**</span><span class="sxs-lookup"><span data-stu-id="143da-188">**Primary interface 1**</span></span>|<span data-ttu-id="143da-189">**PSTN 인터페이스(중재 서버)**</span><span class="sxs-lookup"><span data-stu-id="143da-189">**PSTN interface (on Mediation Server)**</span></span>|<span data-ttu-id="143da-190">**PSTN 게이트웨이 설정**</span><span class="sxs-lookup"><span data-stu-id="143da-190">**PSTN gateway setting**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="143da-191">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-191">IPv4</span></span>  <br/> |<span data-ttu-id="143da-192">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-192">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-193">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-193">IPv4</span></span>  <br/> |
|<span data-ttu-id="143da-194">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-194">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-195">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-195">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-196">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-196">IPv4</span></span>  <br/> |
|<span data-ttu-id="143da-197">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-197">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-198">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-198">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-199">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-199">IPv6</span></span>  <br/> |
   
1. <span data-ttu-id="143da-200">기본 인터페이스는 비즈니스용 Skype 서버 구성 요소와 통신하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="143da-200">The primary interface is the interface that communicates with the Skype for Business Server components.</span></span>
  
### <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="143da-201">원격 사용자 피어 투 피어 통신</span><span class="sxs-lookup"><span data-stu-id="143da-201">Remote User Peer-to-Peer Communications</span></span>
<span data-ttu-id="143da-202"><a name="remote"> </a></span><span class="sxs-lookup"><span data-stu-id="143da-202"><a name="remote"> </a></span></span>

<span data-ttu-id="143da-203">원격 사용자와의 피어 투 피어 통신에는 인스턴트 메시징, 오디오/비디오, 응용 프로그램 공유 및 파일 전송이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="143da-203">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>
  
|<span data-ttu-id="143da-204">**원격 사용자 네트워크**</span><span class="sxs-lookup"><span data-stu-id="143da-204">**Remote user network**</span></span>|<span data-ttu-id="143da-205">**에지 서버(외부 에지)**</span><span class="sxs-lookup"><span data-stu-id="143da-205">**Edge server (External edge)**</span></span>|
|:-----|:-----|
|<span data-ttu-id="143da-206">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-206">IPv4</span></span>  <br/> |<span data-ttu-id="143da-207">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-207">IPv4</span></span>  <br/> |
|<span data-ttu-id="143da-208">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-208">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-209">IPv4</span><span class="sxs-lookup"><span data-stu-id="143da-209">IPv4</span></span>  <br/> |
|<span data-ttu-id="143da-210">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-210">Dual stack</span></span>  <br/> |<span data-ttu-id="143da-211">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-211">Dual stack</span></span>  <br/> |
|<span data-ttu-id="143da-212">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-212">IPv6</span></span>  <br/> |<span data-ttu-id="143da-213">이중 스택</span><span class="sxs-lookup"><span data-stu-id="143da-213">Dual stack</span></span>  <br/> |
|<span data-ttu-id="143da-214">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-214">IPv6</span></span>  <br/> |<span data-ttu-id="143da-215">IPv6</span><span class="sxs-lookup"><span data-stu-id="143da-215">IPv6</span></span>  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="143da-216">프런트 엔드 풀과 에지 풀 구성</span><span class="sxs-lookup"><span data-stu-id="143da-216">Front End Pool and Edge Pool Configuration</span></span>
<span data-ttu-id="143da-217"><a name="FE_pool"> </a></span><span class="sxs-lookup"><span data-stu-id="143da-217"><a name="FE_pool"> </a></span></span>

<span data-ttu-id="143da-218">다음 표에서는 프런트 엔드 서버 풀과 내부 에지 서버 풀 간의 지원 매트릭스를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="143da-218">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>
  
<span data-ttu-id="143da-219">**프런트 엔드 풀과 에지 풀(내부 에지) 매트릭스**</span><span class="sxs-lookup"><span data-stu-id="143da-219">**Front End Pool and Edge Pool (Internal Edge) Matrix**</span></span>

||<span data-ttu-id="143da-220">**에지 풀: IPv4**</span><span class="sxs-lookup"><span data-stu-id="143da-220">**Edge Pool: IPv4**</span></span> <br/> |<span data-ttu-id="143da-221">**에지 풀: 이중 스택**</span><span class="sxs-lookup"><span data-stu-id="143da-221">**Edge Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="143da-222">**에지 풀: IPv6**</span><span class="sxs-lookup"><span data-stu-id="143da-222">**Edge Pool: IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="143da-223">**프런트 엔드 풀: IPv4**</span><span class="sxs-lookup"><span data-stu-id="143da-223">**Front End Pool: IPv4**</span></span> <br/> |<span data-ttu-id="143da-224">예</span><span class="sxs-lookup"><span data-stu-id="143da-224">Yes</span></span>  <br/> |<span data-ttu-id="143da-225">예</span><span class="sxs-lookup"><span data-stu-id="143da-225">Yes</span></span>  <br/> |<span data-ttu-id="143da-226">아니요</span><span class="sxs-lookup"><span data-stu-id="143da-226">No</span></span>  <br/> |
|<span data-ttu-id="143da-227">**프런트 엔드 풀: 이중 스택**</span><span class="sxs-lookup"><span data-stu-id="143da-227">**Front End Pool: Dual Stack**</span></span> <br/> |<span data-ttu-id="143da-228">예</span><span class="sxs-lookup"><span data-stu-id="143da-228">Yes</span></span>  <br/> |<span data-ttu-id="143da-229">예</span><span class="sxs-lookup"><span data-stu-id="143da-229">Yes</span></span>  <br/> |<span data-ttu-id="143da-230">아니요</span><span class="sxs-lookup"><span data-stu-id="143da-230">No</span></span>  <br/> |
|<span data-ttu-id="143da-231">**프런트 엔드 풀: IPv6**</span><span class="sxs-lookup"><span data-stu-id="143da-231">**Front End Pool: IPv6**</span></span> <br/> |<span data-ttu-id="143da-232">아니요</span><span class="sxs-lookup"><span data-stu-id="143da-232">No</span></span>  <br/> |<span data-ttu-id="143da-233">아니요</span><span class="sxs-lookup"><span data-stu-id="143da-233">No</span></span>  <br/> |<span data-ttu-id="143da-234">예\*</span><span class="sxs-lookup"><span data-stu-id="143da-234">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="143da-235">\* 이 조합은 랩 환경에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-235">\* Use this combination only in a lab environment.</span></span>
  
<span data-ttu-id="143da-236">다음 표는 지원되는 내부 및 외부 에지 인터페이스 조합 매트릭스입니다.</span><span class="sxs-lookup"><span data-stu-id="143da-236">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>
  
<span data-ttu-id="143da-237">**에지 풀(내부 에지)과 에지 풀(외부 에지) 매트릭스**</span><span class="sxs-lookup"><span data-stu-id="143da-237">**Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix**</span></span>

||<span data-ttu-id="143da-238">**에지 풀(외부 에지) : IPv4**</span><span class="sxs-lookup"><span data-stu-id="143da-238">**Edge Pool (External Edge) : IPv4**</span></span> <br/> |<span data-ttu-id="143da-239">**에지 풀(외부 에지): 이중 스택**</span><span class="sxs-lookup"><span data-stu-id="143da-239">**Edge Pool (External Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="143da-240">**에지 풀(외부 에지) : IPv6**</span><span class="sxs-lookup"><span data-stu-id="143da-240">**Edge Pool (External Edge): IPv6**</span></span> <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="143da-241">**에지 풀(내부 에지) : IPv4**</span><span class="sxs-lookup"><span data-stu-id="143da-241">**Edge Pool (Internal Edge): IPv4**</span></span> <br/> |<span data-ttu-id="143da-242">예</span><span class="sxs-lookup"><span data-stu-id="143da-242">Yes</span></span>  <br/> |<span data-ttu-id="143da-243">예</span><span class="sxs-lookup"><span data-stu-id="143da-243">Yes</span></span>  <br/> |<span data-ttu-id="143da-244">아니요</span><span class="sxs-lookup"><span data-stu-id="143da-244">No</span></span>  <br/> |
|<span data-ttu-id="143da-245">**에지 풀(내부 에지): 이중 스택**</span><span class="sxs-lookup"><span data-stu-id="143da-245">**Edge Pool (Internal Edge): Dual Stack**</span></span> <br/> |<span data-ttu-id="143da-246">아니요</span><span class="sxs-lookup"><span data-stu-id="143da-246">No</span></span>  <br/> |<span data-ttu-id="143da-247">예</span><span class="sxs-lookup"><span data-stu-id="143da-247">Yes</span></span>  <br/> |<span data-ttu-id="143da-248">아니요</span><span class="sxs-lookup"><span data-stu-id="143da-248">No</span></span>  <br/> |
|<span data-ttu-id="143da-249">**에지 풀(내부 에지) : IPv6**</span><span class="sxs-lookup"><span data-stu-id="143da-249">**Edge Pool (Internal Edge): IPv6**</span></span> <br/> |<span data-ttu-id="143da-250">아니요</span><span class="sxs-lookup"><span data-stu-id="143da-250">No</span></span>  <br/> |<span data-ttu-id="143da-251">아니요</span><span class="sxs-lookup"><span data-stu-id="143da-251">No</span></span>  <br/> |<span data-ttu-id="143da-252">예\*</span><span class="sxs-lookup"><span data-stu-id="143da-252">Yes\*</span></span>  <br/> |
   
<span data-ttu-id="143da-253">\* 이 조합은 랩 환경에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-253">\* Use this combination only in a lab environment.</span></span>
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="143da-254">IPv6에 대한 고급 Enterprise Voice 지원</span><span class="sxs-lookup"><span data-stu-id="143da-254">Advanced Enterprise Voice Support for IPv6</span></span>
<span data-ttu-id="143da-255"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="143da-255"><a name="Ent_V"> </a></span></span>

<span data-ttu-id="143da-256">CAC(통화 허용 제어 서비스), E9-1-1(고급 9-1-1) 또는 미디어 바이패스를 포함하는 배포는 IPv4 전용 또는 이중 스택 구현으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-256">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span> <span data-ttu-id="143da-257">IPv6만 사용하는 끝점에서는 이러한 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-257">Endpoints using only IPv6 cannot use any of these features.</span></span>
  
> [!NOTE]
> <span data-ttu-id="143da-258">이중 스택 배포에서는 비즈니스용 Skype 서버 클라이언트가 IPv6을 사용하여 비즈니스용 Skype 서버에 연결한 경우에도 비즈니스용 Skype 서버는 E9-1-1을 지원하기 위해 적절한 IPv4 주소를 매핑하기 위해 최선을 다합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-258">In a dual-stacked deployment, even if a Skype for Business Server client connects to a Skype for Business Server by using IPv6, Skype for Business Server will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span> 
  
<span data-ttu-id="143da-259">IPv6 주소가 있는 위치 정보 서비스는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-259">Location Information service with IPv6 addresses is not supported.</span></span>
  
<span data-ttu-id="143da-p110">Exchange UM(통합 메시징)에서는 IPv6을 지원하지 않습니다. Exchange UM의 경우 DNS 확인 시 IPv6 주소가 반환되지 않습니다. IPv6을 사용하면 통화가 음성 사서함로 올바르게 전송될 때 실패할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-p110">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span> 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a><span data-ttu-id="143da-263">IPv6에 대한 기타 비즈니스용 Skype 서버 기능 지원</span><span class="sxs-lookup"><span data-stu-id="143da-263">Other Skype for Business Server Feature Support for IPv6</span></span>
<span data-ttu-id="143da-264"><a name="Ent_V"> </a></span><span class="sxs-lookup"><span data-stu-id="143da-264"><a name="Ent_V"> </a></span></span>

<span data-ttu-id="143da-265">비즈니스용 Skype 서버는 앞서 언급한 기능 및 구성 요소 외에도 다음과 같은 기능에 대해 IPv6을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-265">In addition to the features and components mentioned previously, Skype for Business Server supports IPv6 for the following features:</span></span>
  
- <span data-ttu-id="143da-266">**영구 채팅**</span><span class="sxs-lookup"><span data-stu-id="143da-266">**Persistent Chat**</span></span>
    
    <span data-ttu-id="143da-267">토폴로지 작성기에서 영구 채팅에 대해 IPv6을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-267">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="143da-268">영구 채팅 구성에 대한 자세한 내용은 영구 채팅 서버 배포 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="143da-268">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>
    
- <span data-ttu-id="143da-269">**QoE(체감 품질)과 CDR(통화 정보 기록) 보고서**</span><span class="sxs-lookup"><span data-stu-id="143da-269">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="143da-270">모니터링 보고서에는 IPv4 형식인지 IPv6 형식인지에 관계 없이 모니터링 서버 데이터베이스에 저장된 IP 주소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="143da-270">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>
    
## <a name="technical-requirements-for-ipv6"></a><span data-ttu-id="143da-271">IPv6에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="143da-271">Technical requirements for IPv6</span></span>
<span data-ttu-id="143da-272"><a name="tech"> </a></span><span class="sxs-lookup"><span data-stu-id="143da-272"><a name="tech"> </a></span></span>

<span data-ttu-id="143da-273">IPv6용 비즈니스용 Skype 서버를 구성할 계획인 경우 다음 요구 사항에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="143da-273">If you plan to configure Skype for Business Server for IPv6, keep the following requirements in mind:</span></span>
  
- <span data-ttu-id="143da-274">비즈니스용 Skype 서버에서 IPv6 주소를 사용하려면 검색하고 IPv6 주소로 확인해야 하는 레코드에 대한 DNS(Domain Name System) 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-274">To use IPv6 addresses with Skype for Business Server, you need to create domain name system (DNS) records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="143da-275">IPv6 DNS는 호스트 AAAA(4개의 A) 레코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-275">IPv6 DNS uses host AAAA (quad-A) records.</span></span> <span data-ttu-id="143da-276">배포 환경에 IPv4 및 IPv6를 모두 사용하는 경우 IPv4에 대한 호스트 A 레코드 및 IPv6에 대한 호스트 AAAA 레코드를 모두 구성하고 유지 관리하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-276">If you use both IPv4 and IPv6 in your deployment, it is best to configure and maintain both host A records for IPv4 and host AAAA records for IPv6.</span></span> <span data-ttu-id="143da-277">배포 환경을 IPv6로 완전히 전환하는 경우라도 IPv4를 계속 사용하는 외부 사용자를 위해 IPv4 DNS 호스트 레코드가 계속 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-277">Even when you fully transition your deployment to IPv6, you may still require IPv4 DNS host records for external users who still use IPv4.</span></span>
    
    <span data-ttu-id="143da-278">IPv6의 사용을 시작하기 전에 IPv6 DNS 호스트 레코드를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-278">You can deploy IPv6 DNS host records before you start using IPv6.</span></span> <span data-ttu-id="143da-279">클라이언트 또는 서버가 IPv6를 사용하지 않는 경우 레코드는 참조되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-279">If the client or server doesn't use IPv6, the record will not be referenced.</span></span> <span data-ttu-id="143da-280">변환 기술 구성 및 정책에 기반하여 사용할 레코드가 변환 기술에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="143da-280">Transitional technologies will make the decision about which record to use, based on transition technology configuration and policies.</span></span>
    
- <span data-ttu-id="143da-281">각 IPv6 주소에는 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-281">Each IPv6 address has a scope.</span></span> <span data-ttu-id="143da-282">IPv6 주소 지정에 사용할 수 있는 세 가지 범위는 IPv6 전역 주소(공용 IPv4 주소와 유사), IPv6 고유 로컬 주소(개인 IPv4 주소 범위와 유사) 및 IPv6 링크 로컬 주소(IPv4용 Windows Server의 자동 개인 IP 주소와 유사)입니다.</span><span class="sxs-lookup"><span data-stu-id="143da-282">The three scopes that you can use for IPv6 addressing are IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges), and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4).</span></span> <span data-ttu-id="143da-283">풀 내의 모든 서버는 동일한 범위의 IPv6 주소를 보유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-283">All the servers within a pool should have IPv6 addresses with the same scope.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="143da-284">IPv6은 복잡한 항목으로, Windows Server 수준 및 비즈니스용 Skype 서버 수준에서 할당하는 주소가 예상대로 작동하도록 하기 위해 네트워킹 팀 및 인터넷 공급자와 신중하게 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-284">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to help ensure that the addresses that you assign at the Windows Server level and at the Skype for Business Server level work as expected.</span></span> <span data-ttu-id="143da-285">IPv6 주소 지정 및 계획에 대한 추가 리소스는 이 항목의 끝에 있는 링크를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="143da-285">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span> 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a><span data-ttu-id="143da-286">IPv6에 대한 마이그레이션 및 동시 사용 고려 사항</span><span class="sxs-lookup"><span data-stu-id="143da-286">Migration and coexistence considerations for IPv6</span></span>
<span data-ttu-id="143da-287"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="143da-287"><a name="migration"> </a></span></span>

<span data-ttu-id="143da-288">Lync Server 2010 또는 Office Communications Server에서는 IPv6(IP 버전 6)이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-288">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="143da-289">파일럿을 위해 Lync Server 2010 및 비즈니스용 Skype 서버 이중 스택 공존을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-289">For piloting purposes, you can test Lync Server 2010 and Skype for Business Server dual-stack coexistence.</span></span> <span data-ttu-id="143da-290">특정 중앙 사이트의 모든 풀은 모든 풀에 대해 IPv6(이중 스택 네트워크)을 사용하도록 설정하기 전에 비즈니스용 Skype 서버로 업그레이드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-290">We recommend that all pools for a given central site are upgraded to Skype for Business Server before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="143da-291">IPv6 전용의 풀을 구성해야 할 경우에는 랩 환경에서 테스트 목적으로 IPv6 전용 풀을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="143da-291">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>
  
<span data-ttu-id="143da-292">마이그레이션 및 동시 사용 중에는 다음과 같은 시나리오가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="143da-292">The following scenarios are supported during migration and coexistence:</span></span>
  
- <span data-ttu-id="143da-293">비즈니스용 Skype 서버, Lync Server 2013 및 Lync Server 2010 풀(IPv4 모드)은 이중 스택 모드로 비즈니스용 Skype 서버와 공존합니다.</span><span class="sxs-lookup"><span data-stu-id="143da-293">Skype for Business Server, Lync Server 2013, and Lync Server 2010 pools in IPv4 mode, coexisting with Skype for Business Server in dual-stack mode.</span></span>
    
- <span data-ttu-id="143da-294">IPv6 전용 풀이 사일로인 경우 IPv6 전용 모드의 비즈니스용 Skype 서버 풀</span><span class="sxs-lookup"><span data-stu-id="143da-294">Skype for Business Server pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="143da-295">참고 항목</span><span class="sxs-lookup"><span data-stu-id="143da-295">See also</span></span>
<span data-ttu-id="143da-296"><a name="migration"> </a></span><span class="sxs-lookup"><span data-stu-id="143da-296"><a name="migration"> </a></span></span>

[<span data-ttu-id="143da-297">비즈니스용 Skype에서 IP 주소 유형 구성</span><span class="sxs-lookup"><span data-stu-id="143da-297">Configure IP address types in Skype for Business</span></span>](ip-address-types.md)

[<span data-ttu-id="143da-298">IP 버전 6 주소 아키텍처</span><span class="sxs-lookup"><span data-stu-id="143da-298">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)
  
[<span data-ttu-id="143da-299">IPv6 전역 유니캐스트 주소 형식</span><span class="sxs-lookup"><span data-stu-id="143da-299">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)
  
[<span data-ttu-id="143da-300">고유한 로컬 IPv6 유니캐스트 주소</span><span class="sxs-lookup"><span data-stu-id="143da-300">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)
