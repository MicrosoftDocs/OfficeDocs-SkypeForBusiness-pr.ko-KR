---
title: 비즈니스용 Skype 서버와의 상호 연결에 대해 CUCM 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: '요약: 비즈니스용 Skype 서버에서 작동하도록 CUCM을 구성합니다.'
ms.openlocfilehash: 82fa48a185b22973d35bc19484e733e6436ba43e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837118"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="4f287-103">비즈니스용 Skype 서버와의 상호 연결에 대해 CUCM 구성</span><span class="sxs-lookup"><span data-stu-id="4f287-103">Configure CUCM for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="4f287-104">**요약:** 비즈니스용 Skype 서버에서 작동하도록 CUCM을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-104">**Summary:** Configure CUCM to work with Skype for Business Server.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4f287-105">이 기능은 TCP를 사용하는 트렁크 설정만 사용하여 Cisco Unified Communications Manager(CallManager 또는 CUCM) 버전 10.5에서 테스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-105">This capability is tested with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 using Trunks setup over TCP only.</span></span> <span data-ttu-id="4f287-106">계속하기 전에 CUCM 환경이 이러한 기준을 충족하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-106">Verify that the CUCM environment meets these criteria before proceeding.</span></span> 
  
<span data-ttu-id="4f287-107">여기에 설명된 설정은 VIS에서 작동하도록 CUCM을 구성하는 방법의 예로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-107">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="4f287-108">다른 설정 및/또는 대체 CUCM 기능의 사용법을 사용하여 동일한 결과를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-108">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="4f287-109">특정 시나리오에 대해 최적의 구성을 권장하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-109">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
<span data-ttu-id="4f287-110">VIS와의 상호 연동을 위해 여러 CUCM 설정을 확인하거나 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-110">A number of CUCM settings need to be confirmed or changed for interoperation with the VIS.</span></span> <span data-ttu-id="4f287-111">필요한 설정이 누락되는 것을 방지하려면 아래 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4f287-111">Follow the procedures below in order to avoid missing required settings.</span></span>
  
### <a name="configure-the-cucm"></a><span data-ttu-id="4f287-112">CUCM 구성</span><span class="sxs-lookup"><span data-stu-id="4f287-112">Configure the CUCM</span></span>

1. <span data-ttu-id="4f287-113">CUCM에 로그인하고 Cisco 통합 CM 관리 - 통화 \> 라우팅- \> 제어 클래스- 파티션으로 \> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-113">Log in to CUCM and navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Partition.</span></span>
    
2. <span data-ttu-id="4f287-114">파티션 구성 화면에서 파티션 이름과 설명을 입력하고 새로 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f287-114">In the Partition Configuration screen, enter the partition name and description and click on **Add New**.</span></span>
    
3. <span data-ttu-id="4f287-115">Cisco 통합 CM 관리 - \> 통화 라우팅- \> 제어 클래스- 호출 검색 \> 공간으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-115">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Calling Search Space.</span></span>
    
4. <span data-ttu-id="4f287-116">호출 검색 공간 구성 화면에서 호출하는 검색 공간의 이름을 입력하고 선택한 파티션에 방금 만든 파티션의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-116">In the Calling Search Space Configuration screen, enter the name for the calling search space, and in Selected Partitions, enter the name of the partition you just created.</span></span> <span data-ttu-id="4f287-117">완료되면 **저장을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-117">Click **Save** when done.</span></span>
    
5. <span data-ttu-id="4f287-118">Cisco 통합 CM 관리 - \> 시스템 - 보안 - \> \> SIP 트렁크 보안 프로필로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-118">Navigate to Cisco Unified CM Administration-\>System-\>Security-\>SIP Trunk Security Profile.</span></span>
    
6. <span data-ttu-id="4f287-119">SIP 트렁크 보안 프로필 구성 화면에서 표시된 SIP 트렁크 보안 프로필 정보 옵션을 설정하고 새로 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f287-119">In the SIP Trunk Security Profile Configuration screen, set the SIP Trunk Security Profile Information options as shown, and click on **Add New**.</span></span>
    
   |<span data-ttu-id="4f287-120">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="4f287-120">**Parameter**</span></span>|<span data-ttu-id="4f287-121">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="4f287-121">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="4f287-122">이름</span><span class="sxs-lookup"><span data-stu-id="4f287-122">Name</span></span>  <br/> |<span data-ttu-id="4f287-123">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="4f287-123">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
   |<span data-ttu-id="4f287-124">장치 보안 모드</span><span class="sxs-lookup"><span data-stu-id="4f287-124">Device Security Mode</span></span>  <br/> |<span data-ttu-id="4f287-125">비보안</span><span class="sxs-lookup"><span data-stu-id="4f287-125">Non Secure</span></span>  <br/> |
   |<span data-ttu-id="4f287-126">들어오는 전송 유형</span><span class="sxs-lookup"><span data-stu-id="4f287-126">Incoming Transport Type</span></span>  <br/> |<span data-ttu-id="4f287-127">TCP + UDP</span><span class="sxs-lookup"><span data-stu-id="4f287-127">TCP + UDP</span></span>  <br/> |
   |<span data-ttu-id="4f287-128">전송 유형</span><span class="sxs-lookup"><span data-stu-id="4f287-128">Outgoing Transport Type</span></span>  <br/> |<span data-ttu-id="4f287-129">TCP</span><span class="sxs-lookup"><span data-stu-id="4f287-129">TCP</span></span>  <br/> |
   |<span data-ttu-id="4f287-130">들어오는 포트</span><span class="sxs-lookup"><span data-stu-id="4f287-130">Incoming Port</span></span>  <br/> |<span data-ttu-id="4f287-131">5060</span><span class="sxs-lookup"><span data-stu-id="4f287-131">5060</span></span>  <br/> |
   
7. <span data-ttu-id="4f287-132">Cisco 통합 CM 관리 - \> 장치- \> 장치 설정 - \> SIP 프로필로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-132">Navigate to Cisco Unified CM Administration-\>Device-\>Device Settings-\>SIP Profile.</span></span>
    
8. <span data-ttu-id="4f287-133">SIP 프로필 구성 화면에서 SIP 프로필 정보 옵션을 다음과 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-133">In the SIP Profile Configuration screen, set the SIP Profile Information options as shown.</span></span> 
    
   |<span data-ttu-id="4f287-134">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="4f287-134">**Parameter**</span></span>|<span data-ttu-id="4f287-135">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="4f287-135">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="4f287-136">이름</span><span class="sxs-lookup"><span data-stu-id="4f287-136">Name</span></span>  <br/> |<span data-ttu-id="4f287-137">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="4f287-137">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   |<span data-ttu-id="4f287-138">설명</span><span class="sxs-lookup"><span data-stu-id="4f287-138">Description</span></span>  <br/> |<span data-ttu-id="4f287-139">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="4f287-139">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   
9. <span data-ttu-id="4f287-140">동일한 화면에서 아래로 스크롤하여 SDP 프로필 정보 섹션으로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-140">On the same screen, scroll down to the SDP Profile Information section.</span></span> <span data-ttu-id="4f287-141">조기 제안 및 다시 초대에 대한 **SDP** 세션 수준 대역폭 수정자는 기본적으로 TIAS 및 AS로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-141">The **SDP Session-level Bandwidth Modifier for Early Offer and Re-invites** option is set by default to TIAS and AS.</span></span> <span data-ttu-id="4f287-142">이 옵션을 TIAS로만 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-142">Change this option to TIAS only.</span></span> <span data-ttu-id="4f287-143">이 옵션을 기본 설정으로 두면 비즈니스용 Skype 서버가 SIP 메시지의 대역폭 수정자 정보를 이해하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-143">If you leave this option at its default setting, Skype for Business Server will not understand the bandwidth modifier information in the SIP message.</span></span> <span data-ttu-id="4f287-144">TIAS는 전송 독립 응용 프로그램 관련을 의미하고 AS는 응용 프로그램 관련을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-144">TIAS means Transport Independent Application Specific while AS means Application Specific.</span></span> <span data-ttu-id="4f287-145">RFC3890에 지정된 SIP 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-145">These are SIP options specified in RFC3890.</span></span>
    
10. <span data-ttu-id="4f287-146">같은 화면에서 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-146">On the same screen, scroll down further.</span></span> <span data-ttu-id="4f287-147">SIP 프로필의 트렁크 관련 구성에서  음성 및 비디오 통화에 대한 조기 제공 지원을 선택하고 필수(필요한 경우 **MTP 삽입)** 옵션으로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="4f287-147">Under the SIP Profile's Trunk Specific Configuration, select **Early Offer Support for voice and video calls** and set it to the **Mandatory (insert MTP if needed)** option.</span></span> <span data-ttu-id="4f287-148">이렇게 하면 CUCM에서 Early Offer를 사용하여 발신 SIP 호출을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-148">This will enable CUCM to set up an outgoing SIP call with Early Offer.</span></span> <span data-ttu-id="4f287-149">CUCM 8.5 이상의 새로운 기능 중 하나는 MTP(미디어 종료 지점)를 요구하지 않고 Early Offer를 사용하여 발신 전화 설정을 지원하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-149">One new feature in CUCM 8.5 and beyond is that it supports outgoing call setup with Early Offer without requiring Media Termination Point (MTP).</span></span>
    
11. <span data-ttu-id="4f287-150">SIP 옵션 ping 섹션에서 "OPTIONS Ping을 사용하여 서비스 유형 '없음(기본값)'을 사용하여 트렁크의 대상 상태를 모니터링합니다." 옆의 확인란이 선택되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="4f287-150">Verify that in the SIP Options ping section, the box is checked next to "Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'."</span></span>
    
12. <span data-ttu-id="4f287-151">완료되면 새로 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f287-151">When you are finished, click on **Add New**.</span></span>
    
13. <span data-ttu-id="4f287-152">Cisco 통합 CM 관리 - \> 장치- \> 트렁크로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-152">Navigate to Cisco Unified CM Administration-\>Device-\>Trunk.</span></span> 
    
14. <span data-ttu-id="4f287-153">장치 프로토콜을 SIP로 설정하고 **다음을 니다.**</span><span class="sxs-lookup"><span data-stu-id="4f287-153">Set the Device Protocol to SIP and press **Next**.</span></span>
    
15. <span data-ttu-id="4f287-154">장치 정보에서 장치 이름 및 설명(예: SfBVideoInterop_SIPTrunk)을 설정하고 미디어 리소스 그룹 목록을 올바른 미디어 리소스가 포함된 MRGL로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-154">Under Device Information, Set the Device Name and Description (probably to something like SfBVideoInterop_SIPTrunk), and set the Media Resource Group List to an MRGL that contains the right media resources.</span></span> 
    
16. <span data-ttu-id="4f287-155">아래로 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-155">Scroll down further.</span></span> <span data-ttu-id="4f287-156">비디오 통화에 MTP(미디어 종료 지점)가 필요하지 않습니다( 아직 이를 아직 확정하지 않은 경우, MTP(미디어 종료 지점)</span><span class="sxs-lookup"><span data-stu-id="4f287-156">Media Termination Point (MTP) is not required for Video Calls, if it is not already unchecked, uncheck it.</span></span> <span data-ttu-id="4f287-157">모든 활성 통합 **CM 노드에서** 실행 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-157">Check the option to **Run on all active Unified CM Nodes**.</span></span> <span data-ttu-id="4f287-158">비즈니스용 Skype 서버 구성에 모든 CUCM 노드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-158">Please note that you should add all CUCM nodes to the Skype for Business Server configuration.</span></span>
    
17. <span data-ttu-id="4f287-159">아래로 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-159">Scroll down further.</span></span> <span data-ttu-id="4f287-160">인바운드 통화 및 연결된 파티 설정 옵션을 다음과 같이 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="4f287-160">Set the Inbound Calls and Connected Party Settings options as shown.</span></span>
    
    |<span data-ttu-id="4f287-161">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="4f287-161">**Parameter**</span></span>|<span data-ttu-id="4f287-162">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="4f287-162">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="4f287-163">검색 공간 호출</span><span class="sxs-lookup"><span data-stu-id="4f287-163">Calling Search Space</span></span>  <br/> |<span data-ttu-id="4f287-164">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="4f287-164">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="4f287-165">AAR 호출 검색 공간</span><span class="sxs-lookup"><span data-stu-id="4f287-165">AAR Calling Search Space</span></span>  <br/> |<span data-ttu-id="4f287-166">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="4f287-166">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="4f287-167">연결된 파티 변환 CSS</span><span class="sxs-lookup"><span data-stu-id="4f287-167">Connected Party Transformation CSS</span></span>  <br/> |<span data-ttu-id="4f287-168">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="4f287-168">CSS_SfBVideoInterop</span></span>  <br/> |
   
18. <span data-ttu-id="4f287-169">아래로 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-169">Scroll down further.</span></span> <span data-ttu-id="4f287-170">SIP 트렁크 구성의 SIP 정보 대상 섹션에서 VIS 풀의 FQDN 또는 풀에 있는 개별 VIS 서버의 IP 주소를 지정합니다(여러 항목 추가).</span><span class="sxs-lookup"><span data-stu-id="4f287-170">Under the SIP Information Destination section of the SIP Trunk configuration, specify the VIS Pool's FQDN or the IP address of individual VIS servers in the pool (adding multiple entries).</span></span> <span data-ttu-id="4f287-171">대상 포트에서 VIS가 CUCM의 연결을 수신하는 데 사용할 포트를 지정합니다(기본값은 6001).</span><span class="sxs-lookup"><span data-stu-id="4f287-171">In the Destination Port specify the Port that VIS is listening at for connections from CUCM (the default is 6001).</span></span> <span data-ttu-id="4f287-172">또한 앞에서 만든 SIP 트렁크 보안 프로필 및 SIP 프로필을 다음과 같이 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-172">Also specify the SIP Trunk security profile and SIP profile you created earlier, as shown.</span></span>
    
    |<span data-ttu-id="4f287-173">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="4f287-173">**Parameter**</span></span>|<span data-ttu-id="4f287-174">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="4f287-174">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="4f287-175">SIP 트렁크 보안 프로필</span><span class="sxs-lookup"><span data-stu-id="4f287-175">SIP Trunk Security Profile</span></span>  <br/> |<span data-ttu-id="4f287-176">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="4f287-176">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
    |<span data-ttu-id="4f287-177">호출 검색 공간 다시우기</span><span class="sxs-lookup"><span data-stu-id="4f287-177">Rerouting Calling Search Space</span></span>  <br/> |<span data-ttu-id="4f287-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="4f287-178">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="4f287-179">대화 상자 부재 중 검색 공간 호출</span><span class="sxs-lookup"><span data-stu-id="4f287-179">Out-of-Dialog Refer Calling Search Space</span></span>  <br/> |<span data-ttu-id="4f287-180">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="4f287-180">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="4f287-181">통화 검색 공간 구독</span><span class="sxs-lookup"><span data-stu-id="4f287-181">Subscribe Calling Search Space</span></span>  <br/> |<span data-ttu-id="4f287-182">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="4f287-182">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="4f287-183">SIP 프로필</span><span class="sxs-lookup"><span data-stu-id="4f287-183">SIP Profile</span></span>  <br/> |<span data-ttu-id="4f287-184">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="4f287-184">SfBVideoInterop_SIPProfile</span></span>  <br/> |
    |<span data-ttu-id="4f287-185">DTMF 신호 방법</span><span class="sxs-lookup"><span data-stu-id="4f287-185">DTMF Signaling Method</span></span>  <br/> |<span data-ttu-id="4f287-186">RFC 2833</span><span class="sxs-lookup"><span data-stu-id="4f287-186">RFC 2833</span></span>  <br/> |
   
19.  <span data-ttu-id="4f287-187">아래로 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-187">Scroll down further.</span></span> <span data-ttu-id="4f287-188">기록 정보를 시스템에 적절하게 설정</span><span class="sxs-lookup"><span data-stu-id="4f287-188">Set the Recording Information as appropriate for your system.</span></span> <span data-ttu-id="4f287-189">없음으로 설정한 그대로 두면 **괜찮습니다.**</span><span class="sxs-lookup"><span data-stu-id="4f287-189">It's fine to leave it set to **None**.</span></span> 
    
20. <span data-ttu-id="4f287-190">완료되면 새로 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f287-190">When you are finished, click on **Add New**.</span></span>
    
21. <span data-ttu-id="4f287-191">Cisco 통합 CM 관리 - \> 통화 라우팅 - \> 경로/헌트- \> 경로 패턴으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-191">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Route/Hunt-\>Route pattern.</span></span>
    
22. <span data-ttu-id="4f287-192">경로 패턴 구성 화면에서 아래 표시된 패턴 정의 매개 변수를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-192">In the Route Pattern Configuration screen, enter the Pattern definition parameters shown below.</span></span> <span data-ttu-id="4f287-193">호출된 Party Transformations 섹션까지 아래로 스크롤하고 표시된 마스크를  설정한 다음 새로 추가를 클릭하면 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-193">Scroll down to the Called Party Transformations section and set the mask as shown, and then click on **Add New** when finished.</span></span>
    
    |<span data-ttu-id="4f287-194">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="4f287-194">**Parameter**</span></span>|<span data-ttu-id="4f287-195">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="4f287-195">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="4f287-196">경로 패턴</span><span class="sxs-lookup"><span data-stu-id="4f287-196">Route Pattern</span></span>  <br/> |<span data-ttu-id="4f287-197">7779999</span><span class="sxs-lookup"><span data-stu-id="4f287-197">7779999</span></span>  <br/> |
    |<span data-ttu-id="4f287-198">경로 파티션</span><span class="sxs-lookup"><span data-stu-id="4f287-198">Route Partition</span></span>  <br/> |<span data-ttu-id="4f287-199">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="4f287-199">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="4f287-200">설명</span><span class="sxs-lookup"><span data-stu-id="4f287-200">Description</span></span>  <br/> |<span data-ttu-id="4f287-201">SfBVideoInterop용 파티션</span><span class="sxs-lookup"><span data-stu-id="4f287-201">Partition for SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="4f287-202">게이트웨이/경로 목록</span><span class="sxs-lookup"><span data-stu-id="4f287-202">Gateway/Route List</span></span>  <br/> |<span data-ttu-id="4f287-203">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="4f287-203">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="4f287-204">파티 변형 마스크라고 불리는</span><span class="sxs-lookup"><span data-stu-id="4f287-204">Called Party Transform Mask</span></span>  <br/> |<span data-ttu-id="4f287-205">+1425779999</span><span class="sxs-lookup"><span data-stu-id="4f287-205">+14257779999</span></span>  <br/> |
   
23. <span data-ttu-id="4f287-206">Cisco 통합 CM 관리 - \> 통화 라우팅 - \> SIP 경로 패턴으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-206">Navigate to Cisco Unified CM Administration-\>Call Routing-\>SIP Route Pattern.</span></span>
    
24. <span data-ttu-id="4f287-207">SIP 경로 패턴 구성 화면에서 패턴 정의 옵션을 표시된 것으로 설정하고 새로 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f287-207">In the SIP Route Pattern Configuration screen, set the Pattern Definition options as shown, and click on **Add New**.</span></span>
    
    |<span data-ttu-id="4f287-208">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="4f287-208">**Parameter**</span></span>|<span data-ttu-id="4f287-209">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="4f287-209">**Recommended setting**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="4f287-210">패턴 사용</span><span class="sxs-lookup"><span data-stu-id="4f287-210">Pattern Usage</span></span> <br/> |<span data-ttu-id="4f287-211">도메인 라우팅</span><span class="sxs-lookup"><span data-stu-id="4f287-211">Domain Routing</span></span>  <br/> |
    |<span data-ttu-id="4f287-212">IPv4 패턴</span><span class="sxs-lookup"><span data-stu-id="4f287-212">IPv4 Pattern</span></span>  <br/> |<span data-ttu-id="4f287-213">contoso.com(IPv6을 사용하는 경우 비워 두기)</span><span class="sxs-lookup"><span data-stu-id="4f287-213">contoso.com (leave blank if using IPv6)</span></span>  <br/> |
    |<span data-ttu-id="4f287-214">IPv6 패턴</span><span class="sxs-lookup"><span data-stu-id="4f287-214">IPv6 Pattern</span></span>  <br/> |<span data-ttu-id="4f287-215">contoso.com(IPv4를 사용하는 경우 비워 두기)</span><span class="sxs-lookup"><span data-stu-id="4f287-215">contoso.com (leave blank if using IPv4)</span></span>  <br/> |
    |<span data-ttu-id="4f287-216">설명</span><span class="sxs-lookup"><span data-stu-id="4f287-216">Description</span></span>  <br/> |<span data-ttu-id="4f287-217">Mediarv로의 SIPRoute 패턴</span><span class="sxs-lookup"><span data-stu-id="4f287-217">SIPRoute Pattern to mediarv</span></span>  <br/> |
    |<span data-ttu-id="4f287-218">경로 파티션</span><span class="sxs-lookup"><span data-stu-id="4f287-218">Route Partition</span></span>  <br/> |<span data-ttu-id="4f287-219">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="4f287-219">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="4f287-220">SIP 트렁크/경로 목록</span><span class="sxs-lookup"><span data-stu-id="4f287-220">SIP Trunk/Route List</span></span>  <br/> |<span data-ttu-id="4f287-221">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="4f287-221">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="4f287-222">차단 패턴 확인란</span><span class="sxs-lookup"><span data-stu-id="4f287-222">Block Pattern checkbox</span></span>  <br/> |<span data-ttu-id="4f287-223">그대로 두기</span><span class="sxs-lookup"><span data-stu-id="4f287-223">leave unchecked</span></span>  <br/> |
   
25. <span data-ttu-id="4f287-224">오디오 또는 비디오 비트 요금을 기본 설정에서 변경한 경우 기본값으로 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-224">If you have changed the audio or video bit rates from the default settings, you will need to return them to the defaults.</span></span> <span data-ttu-id="4f287-225">오디오/비디오 통화에 대한 비트 비율을 설정하기 위해 Cisco 통합 CM 관리- 시스템- 지역 \> \> 정보- \> 지역으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-225">To set the bit rate for Audio/Video calls, navigate to Cisco Unified CM Administration-\>System-\>Region Information-\>Region.</span></span> <span data-ttu-id="4f287-226">참조를 위해 기본값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-226">The defaults are shown below for reference:</span></span>
    
    |<span data-ttu-id="4f287-227">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="4f287-227">**Parameter**</span></span>|<span data-ttu-id="4f287-228">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="4f287-228">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="4f287-229">Region</span><span class="sxs-lookup"><span data-stu-id="4f287-229">Region</span></span>  <br/> |<span data-ttu-id="4f287-230">기본</span><span class="sxs-lookup"><span data-stu-id="4f287-230">Default</span></span>  <br/> |
    |<span data-ttu-id="4f287-231">오디오 코덱 기본 설정 목록</span><span class="sxs-lookup"><span data-stu-id="4f287-231">Audio Codec Preference List</span></span>  <br/> |<span data-ttu-id="4f287-232">시스템 기본값</span><span class="sxs-lookup"><span data-stu-id="4f287-232">System Default</span></span>  <br/> |
    |<span data-ttu-id="4f287-233">최대 오디오 비트 속도</span><span class="sxs-lookup"><span data-stu-id="4f287-233">Maximum Audio Bit Rate</span></span>  <br/> |<span data-ttu-id="4f287-234">64개 kbps(G.722, G.711)</span><span class="sxs-lookup"><span data-stu-id="4f287-234">64 kbps (G.722, G.711)</span></span>  <br/> |
    |<span data-ttu-id="4f287-235">비디오 통화에 대한 최대 세션 비트 속도</span><span class="sxs-lookup"><span data-stu-id="4f287-235">Maximum Session Bit Rate for Video Calls</span></span>  <br/> |<span data-ttu-id="4f287-236">200000 kbps</span><span class="sxs-lookup"><span data-stu-id="4f287-236">200000 kbps</span></span>  <br/> |
    |<span data-ttu-id="4f287-237">최대 세션 비트 속도</span><span class="sxs-lookup"><span data-stu-id="4f287-237">Maximum Session Bit Rate</span></span>  <br/> |<span data-ttu-id="4f287-238">2000000000 kbps</span><span class="sxs-lookup"><span data-stu-id="4f287-238">2000000000 kbps</span></span>  <br/> |
   
<span data-ttu-id="4f287-239">이때 CUCM 비디오 게이트웨이는 VIS에서 작동하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-239">At this point the CUCM video gateway is configured to work with the VIS.</span></span> <span data-ttu-id="4f287-240">해당 구성은 통합하려는 각 VTC에서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-240">Corresponding configuration will need to be done on each VTC you wish to integrate.</span></span>
> [!NOTE]
> <span data-ttu-id="4f287-241">탄력성을 향상하기 위해 두 번째 Video Interop 서버 또는 VIS 풀에서 작동하도록 이 CUCM 게이트웨이를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f287-241">To improve resiliency, you may want to configure this CUCM gateway to work with a second Video Interop Server or VIS pool.</span></span> <span data-ttu-id="4f287-242">자세한 [내용은 탄력성](../../plan-your-deployment/video-interop-server.md#resiliency) 메커니즘을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f287-242">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4f287-243">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f287-243">See also</span></span>

[<span data-ttu-id="4f287-244">비즈니스용 Skype 서버와의 상호 연계를 위한 VTC 구성</span><span class="sxs-lookup"><span data-stu-id="4f287-244">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
