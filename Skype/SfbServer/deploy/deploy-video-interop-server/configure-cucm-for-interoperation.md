---
title: 비즈니스용 Skype 서버와 상호 운용할 CUCM 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: '요약: 비즈니스용 Skype 서버에서 작동 하도록 CUCM를 구성 합니다.'
ms.openlocfilehash: 8324e146147480bb682c2cc18c62a96e95a130e3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235654"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="3ed47-103">비즈니스용 Skype 서버와 상호 운용할 CUCM 구성</span><span class="sxs-lookup"><span data-stu-id="3ed47-103">Configure CUCM for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="3ed47-104">**요약:** 비즈니스용 Skype 서버에서 작동 하도록 CUCM를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-104">**Summary:** Configure CUCM to work with Skype for Business Server.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3ed47-105">이 접근 권한 값은 Trunks 설치를 사용 하 여 TCP만을 통해 Cisco 통합 커뮤니케이션 관리자 (CallManager 또는 CUCM) 버전 10.5에서 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-105">This capability is tested with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 using Trunks setup over TCP only.</span></span> <span data-ttu-id="3ed47-106">계속 하기 전에 CUCM 환경이 이러한 기준을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-106">Verify that the CUCM environment meets these criteria before proceeding.</span></span> 
  
<span data-ttu-id="3ed47-107">여기에서 설명 하는 설정은 VIS와 작동 하도록 CUCM를 구성할 수 있는 방법의 예제로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-107">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="3ed47-108">다른 설정 및/또는 대체 CUCM 기능을 사용 하 여 동일한 결과를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-108">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="3ed47-109">특정 시나리오에 대 한 최적 구성에 대 한 권장 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-109">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
<span data-ttu-id="3ed47-110">VIS와의 상호 운용을 위해 몇 가지 CUCM 설정을 확인 하거나 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-110">A number of CUCM settings need to be confirmed or changed for interoperation with the VIS.</span></span> <span data-ttu-id="3ed47-111">필요한 설정이 누락 되지 않도록 하려면 아래 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="3ed47-111">Follow the procedures below in order to avoid missing required settings.</span></span>
  
### <a name="configure-the-cucm"></a><span data-ttu-id="3ed47-112">CUCM 구성</span><span class="sxs-lookup"><span data-stu-id="3ed47-112">Configure the CUCM</span></span>

1. <span data-ttu-id="3ed47-113">CUCM에 로그인 하 여 Cisco 통합 CM 관리로 이동-\>호출 라우팅-\>제어\>파티션의 종류</span><span class="sxs-lookup"><span data-stu-id="3ed47-113">Log in to CUCM and navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Partition.</span></span>
    
2. <span data-ttu-id="3ed47-114">파티션 구성 화면에서 파티션 이름과 설명을 입력 하 고 **새로 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-114">In the Partition Configuration screen, enter the partition name and description and click on **Add New**.</span></span>
    
3. <span data-ttu-id="3ed47-115">Cisco 통합 CM 관리로 이동-\>호출 라우팅-\>컨트롤\>호출 검색 공간 클래스</span><span class="sxs-lookup"><span data-stu-id="3ed47-115">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Calling Search Space.</span></span>
    
4. <span data-ttu-id="3ed47-116">호출 검색 공간 구성 화면에서 호출 검색 공간의 이름을 입력 하 고 선택한 파티션에는 방금 만든 파티션의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-116">In the Calling Search Space Configuration screen, enter the name for the calling search space, and in Selected Partitions, enter the name of the partition you just created.</span></span> <span data-ttu-id="3ed47-117">완료 되 면 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-117">Click **Save** when done.</span></span>
    
5. <span data-ttu-id="3ed47-118">Cisco 통합 CM 관리-\>시스템\>보안-\>SIP 트렁크 보안 프로필로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-118">Navigate to Cisco Unified CM Administration-\>System-\>Security-\>SIP Trunk Security Profile.</span></span>
    
6. <span data-ttu-id="3ed47-119">SIP 트렁크 보안 프로필 구성 화면에서 표시 된 대로 SIP 트렁크 보안 프로필 정보 옵션을 설정 하 고 **새로 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-119">In the SIP Trunk Security Profile Configuration screen, set the SIP Trunk Security Profile Information options as shown, and click on **Add New**.</span></span>
    
   |<span data-ttu-id="3ed47-120">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="3ed47-120">**Parameter**</span></span>|<span data-ttu-id="3ed47-121">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="3ed47-121">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="3ed47-122">이름</span><span class="sxs-lookup"><span data-stu-id="3ed47-122">Name</span></span>  <br/> |<span data-ttu-id="3ed47-123">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="3ed47-123">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
   |<span data-ttu-id="3ed47-124">장치 보안 모드</span><span class="sxs-lookup"><span data-stu-id="3ed47-124">Device Security Mode</span></span>  <br/> |<span data-ttu-id="3ed47-125">비보안</span><span class="sxs-lookup"><span data-stu-id="3ed47-125">Non Secure</span></span>  <br/> |
   |<span data-ttu-id="3ed47-126">들어오는 전송 종류</span><span class="sxs-lookup"><span data-stu-id="3ed47-126">Incoming Transport Type</span></span>  <br/> |<span data-ttu-id="3ed47-127">TCP + UDP</span><span class="sxs-lookup"><span data-stu-id="3ed47-127">TCP + UDP</span></span>  <br/> |
   |<span data-ttu-id="3ed47-128">보내는 전송 종류</span><span class="sxs-lookup"><span data-stu-id="3ed47-128">Outgoing Transport Type</span></span>  <br/> |<span data-ttu-id="3ed47-129">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="3ed47-129">TCP</span></span>  <br/> |
   |<span data-ttu-id="3ed47-130">수신 포트</span><span class="sxs-lookup"><span data-stu-id="3ed47-130">Incoming Port</span></span>  <br/> |<span data-ttu-id="3ed47-131">5060</span><span class="sxs-lookup"><span data-stu-id="3ed47-131">5060</span></span>  <br/> |
   
7. <span data-ttu-id="3ed47-132">Cisco 통합 CM 관리-\>장치-\>장치 설정-\>SIP 프로필으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-132">Navigate to Cisco Unified CM Administration-\>Device-\>Device Settings-\>SIP Profile.</span></span>
    
8. <span data-ttu-id="3ed47-133">SIP 프로필 구성 화면에서 표시 된 대로 SIP 프로필 정보 옵션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-133">In the SIP Profile Configuration screen, set the SIP Profile Information options as shown.</span></span> 
    
   |<span data-ttu-id="3ed47-134">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="3ed47-134">**Parameter**</span></span>|<span data-ttu-id="3ed47-135">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="3ed47-135">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="3ed47-136">이름</span><span class="sxs-lookup"><span data-stu-id="3ed47-136">Name</span></span>  <br/> |<span data-ttu-id="3ed47-137">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="3ed47-137">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   |<span data-ttu-id="3ed47-138">설명</span><span class="sxs-lookup"><span data-stu-id="3ed47-138">Description</span></span>  <br/> |<span data-ttu-id="3ed47-139">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="3ed47-139">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   
9. <span data-ttu-id="3ed47-140">동일한 화면에서 SDP 프로필 정보 섹션이 나올 때까지 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-140">On the same screen, scroll down to the SDP Profile Information section.</span></span> <span data-ttu-id="3ed47-141">**조기 제공 및 재 초대 옵션에 대 한 SDP 세션 수준의 대역폭 한정자** 는 기본적으로 및의 tias 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-141">The **SDP Session-level Bandwidth Modifier for Early Offer and Re-invites** option is set by default to TIAS and AS.</span></span> <span data-ttu-id="3ed47-142">이 옵션을 ' 팁 '으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-142">Change this option to TIAS only.</span></span> <span data-ttu-id="3ed47-143">이 옵션을 기본 설정으로 두면 비즈니스용 Skype 서버에서 SIP 메시지의 대역폭 한정자 정보를 인식 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-143">If you leave this option at its default setting, Skype for Business Server will not understand the bandwidth modifier information in the SIP message.</span></span> <span data-ttu-id="3ed47-144">TIAS는 특정 응용 프로그램에만 해당 하는 경우를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-144">TIAS means Transport Independent Application Specific while AS means Application Specific.</span></span> <span data-ttu-id="3ed47-145">RFC3890에 지정 된 SIP 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-145">These are SIP options specified in RFC3890.</span></span>
    
10. <span data-ttu-id="3ed47-146">같은 화면에서 더 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-146">On the same screen, scroll down further.</span></span> <span data-ttu-id="3ed47-147">SIP 프로필의 트렁크 구성 아래에서 **음성 및 영상 통화에 대 한 초기 지원 제공** 을 선택 하 고 **필수 (필요한 경우 MTP 삽입)** 옵션으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-147">Under the SIP Profile's Trunk Specific Configuration, select **Early Offer Support for voice and video calls** and set it to the **Mandatory (insert MTP if needed)** option.</span></span> <span data-ttu-id="3ed47-148">이렇게 하면 CUCM에서 초기 제공으로 보내는 SIP 통화를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-148">This will enable CUCM to set up an outgoing SIP call with Early Offer.</span></span> <span data-ttu-id="3ed47-149">CUCM 8.5 및 그 이상의 새로운 기능 중 하나는 MTP (미디어 종료 시점 없음)를 사용 하지 않고 초기 제공으로 나가는 통화 설정을 지원 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-149">One new feature in CUCM 8.5 and beyond is that it supports outgoing call setup with Early Offer without requiring Media Termination Point (MTP).</span></span>
    
11. <span data-ttu-id="3ed47-150">SIP 옵션 ping 섹션에서 "옵션 선택 Ping을 사용 하 여 서비스 종류가 ' 없음 (기본값) ' 인 Trunks에 대 한 대상 상태 모니터링" 확인란 옆에 있음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-150">Verify that in the SIP Options ping section, the box is checked next to "Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'."</span></span>
    
12. <span data-ttu-id="3ed47-151">마쳤으면 **새로 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-151">When you are finished, click on **Add New**.</span></span>
    
13. <span data-ttu-id="3ed47-152">Cisco 통합 CM 관리-\>장치\>트렁크로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-152">Navigate to Cisco Unified CM Administration-\>Device-\>Trunk.</span></span> 
    
14. <span data-ttu-id="3ed47-153">장치 프로토콜을 SIP로 설정 하 고 **다음**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-153">Set the Device Protocol to SIP and press **Next**.</span></span>
    
15. <span data-ttu-id="3ed47-154">장치 정보에서 디바이스 이름 및 설명 (예: SfBVideoInterop_SIPTrunk)을 설정 하 고 미디어 리소스 그룹 목록을 올바른 미디어 리소스를 포함 하는 MRGL로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-154">Under Device Information, Set the Device Name and Description (probably to something like SfBVideoInterop_SIPTrunk), and set the Media Resource Group List to an MRGL that contains the right media resources.</span></span> 
    
16. <span data-ttu-id="3ed47-155">아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-155">Scroll down further.</span></span> <span data-ttu-id="3ed47-156">비디오 통화에 MTP (미디어 종료 시점)가 필요 하지 않으면 아직 선택 되어 있지 않은 경우 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-156">Media Termination Point (MTP) is not required for Video Calls, if it is not already unchecked, uncheck it.</span></span> <span data-ttu-id="3ed47-157">**모든 활성 통합 CM 노드에서 실행할**옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-157">Check the option to **Run on all active Unified CM Nodes**.</span></span> <span data-ttu-id="3ed47-158">모든 CUCM 노드를 비즈니스용 Skype 서버 구성에 추가 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ed47-158">Please note that you should add all CUCM nodes to the Skype for Business Server configuration.</span></span>
    
17. <span data-ttu-id="3ed47-159">아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-159">Scroll down further.</span></span> <span data-ttu-id="3ed47-160">표시 된 대로 인바운드 통화 및 연결 된 파티 설정 옵션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-160">Set the Inbound Calls and Connected Party Settings options as shown.</span></span>
    
    |<span data-ttu-id="3ed47-161">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="3ed47-161">**Parameter**</span></span>|<span data-ttu-id="3ed47-162">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="3ed47-162">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3ed47-163">검색 공간 호출</span><span class="sxs-lookup"><span data-stu-id="3ed47-163">Calling Search Space</span></span>  <br/> |<span data-ttu-id="3ed47-164">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3ed47-164">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="3ed47-165">AAR 통화 검색 공간</span><span class="sxs-lookup"><span data-stu-id="3ed47-165">AAR Calling Search Space</span></span>  <br/> |<span data-ttu-id="3ed47-166">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3ed47-166">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="3ed47-167">연결 된 파티 변형 CSS</span><span class="sxs-lookup"><span data-stu-id="3ed47-167">Connected Party Transformation CSS</span></span>  <br/> |<span data-ttu-id="3ed47-168">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3ed47-168">CSS_SfBVideoInterop</span></span>  <br/> |
   
18. <span data-ttu-id="3ed47-169">아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-169">Scroll down further.</span></span> <span data-ttu-id="3ed47-170">SIP 트렁크 구성의 SIP 정보 대상 섹션에서 VIS 풀의 FQDN 또는 풀에 있는 개별 VIS 서버의 IP 주소 (여러 항목 추가)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-170">Under the SIP Information Destination section of the SIP Trunk configuration, specify the VIS Pool's FQDN or the IP address of individual VIS servers in the pool (adding multiple entries).</span></span> <span data-ttu-id="3ed47-171">대상 포트에서 VIS가 CUCM에서의 연결을 수신 대기 하는 포트를 지정 합니다 (기본값은 6001).</span><span class="sxs-lookup"><span data-stu-id="3ed47-171">In the Destination Port specify the Port that VIS is listening at for connections from CUCM (the default is 6001).</span></span> <span data-ttu-id="3ed47-172">다음과 같이 앞에서 만든 SIP 트렁크 보안 프로필 및 SIP 프로필도 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-172">Also specify the SIP Trunk security profile and SIP profile you created earlier, as shown.</span></span>
    
    |<span data-ttu-id="3ed47-173">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="3ed47-173">**Parameter**</span></span>|<span data-ttu-id="3ed47-174">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="3ed47-174">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3ed47-175">SIP 트렁크 보안 프로필</span><span class="sxs-lookup"><span data-stu-id="3ed47-175">SIP Trunk Security Profile</span></span>  <br/> |<span data-ttu-id="3ed47-176">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="3ed47-176">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
    |<span data-ttu-id="3ed47-177">호출 검색 공간 다시 라우팅</span><span class="sxs-lookup"><span data-stu-id="3ed47-177">Rerouting Calling Search Space</span></span>  <br/> |<span data-ttu-id="3ed47-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3ed47-178">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="3ed47-179">대화 종료-검색 공간 호출 참조</span><span class="sxs-lookup"><span data-stu-id="3ed47-179">Out-of-Dialog Refer Calling Search Space</span></span>  <br/> |<span data-ttu-id="3ed47-180">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3ed47-180">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="3ed47-181">통화 검색 공간 등록</span><span class="sxs-lookup"><span data-stu-id="3ed47-181">Subscribe Calling Search Space</span></span>  <br/> |<span data-ttu-id="3ed47-182">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="3ed47-182">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="3ed47-183">SIP 프로필</span><span class="sxs-lookup"><span data-stu-id="3ed47-183">SIP Profile</span></span>  <br/> |<span data-ttu-id="3ed47-184">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="3ed47-184">SfBVideoInterop_SIPProfile</span></span>  <br/> |
    |<span data-ttu-id="3ed47-185">DTMF 신호 방법</span><span class="sxs-lookup"><span data-stu-id="3ed47-185">DTMF Signaling Method</span></span>  <br/> |<span data-ttu-id="3ed47-186">RFC 2833</span><span class="sxs-lookup"><span data-stu-id="3ed47-186">RFC 2833</span></span>  <br/> |
   
19.  <span data-ttu-id="3ed47-187">아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-187">Scroll down further.</span></span> <span data-ttu-id="3ed47-188">기록 정보를 시스템에 맞게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-188">Set the Recording Information as appropriate for your system.</span></span> <span data-ttu-id="3ed47-189">' **없음**'으로 설정 하는 것은 괜찮습니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-189">It's fine to leave it set to **None**.</span></span> 
    
20. <span data-ttu-id="3ed47-190">마쳤으면 **새로 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-190">When you are finished, click on **Add New**.</span></span>
    
21. <span data-ttu-id="3ed47-191">Cisco 통합 CM 관리-\>호출 라우팅-\>경로/헌트\>경로 패턴으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-191">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Route/Hunt-\>Route pattern.</span></span>
    
22. <span data-ttu-id="3ed47-192">경로 패턴 구성 화면에서 아래에 표시 된 패턴 정의 매개 변수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-192">In the Route Pattern Configuration screen, enter the Pattern definition parameters shown below.</span></span> <span data-ttu-id="3ed47-193">' 파티 변형 ' 섹션으로 아래로 스크롤하여 표시 된 대로 마스크를 설정한 다음 완료 되 면 **새로 추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-193">Scroll down to the Called Party Transformations section and set the mask as shown, and then click on **Add New** when finished.</span></span>
    
    |<span data-ttu-id="3ed47-194">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="3ed47-194">**Parameter**</span></span>|<span data-ttu-id="3ed47-195">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="3ed47-195">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3ed47-196">경로 패턴</span><span class="sxs-lookup"><span data-stu-id="3ed47-196">Route Pattern</span></span>  <br/> |<span data-ttu-id="3ed47-197">7779999</span><span class="sxs-lookup"><span data-stu-id="3ed47-197">7779999</span></span>  <br/> |
    |<span data-ttu-id="3ed47-198">경로 파티션</span><span class="sxs-lookup"><span data-stu-id="3ed47-198">Route Partition</span></span>  <br/> |<span data-ttu-id="3ed47-199">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="3ed47-199">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="3ed47-200">설명</span><span class="sxs-lookup"><span data-stu-id="3ed47-200">Description</span></span>  <br/> |<span data-ttu-id="3ed47-201">SfBVideoInterop 용 파티션</span><span class="sxs-lookup"><span data-stu-id="3ed47-201">Partition for SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="3ed47-202">게이트웨이/경로 목록</span><span class="sxs-lookup"><span data-stu-id="3ed47-202">Gateway/Route List</span></span>  <br/> |<span data-ttu-id="3ed47-203">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="3ed47-203">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="3ed47-204">파티 변환 마스크 호출</span><span class="sxs-lookup"><span data-stu-id="3ed47-204">Called Party Transform Mask</span></span>  <br/> |<span data-ttu-id="3ed47-205">+ 14257779999</span><span class="sxs-lookup"><span data-stu-id="3ed47-205">+14257779999</span></span>  <br/> |
   
23. <span data-ttu-id="3ed47-206">Cisco 통합 CM 관리-\>호출 라우팅-\>SIP 경로 패턴으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-206">Navigate to Cisco Unified CM Administration-\>Call Routing-\>SIP Route Pattern.</span></span>
    
24. <span data-ttu-id="3ed47-207">SIP 경로 패턴 구성 화면에서 표시 된 패턴 정의 옵션을 설정 하 고 **새로 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-207">In the SIP Route Pattern Configuration screen, set the Pattern Definition options as shown, and click on **Add New**.</span></span>
    
    |<span data-ttu-id="3ed47-208">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="3ed47-208">**Parameter**</span></span>|<span data-ttu-id="3ed47-209">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="3ed47-209">**Recommended setting**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="3ed47-210">패턴 사용</span><span class="sxs-lookup"><span data-stu-id="3ed47-210">Pattern Usage</span></span> <br/> |<span data-ttu-id="3ed47-211">도메인 라우팅</span><span class="sxs-lookup"><span data-stu-id="3ed47-211">Domain Routing</span></span>  <br/> |
    |<span data-ttu-id="3ed47-212">IPv4 패턴</span><span class="sxs-lookup"><span data-stu-id="3ed47-212">IPv4 Pattern</span></span>  <br/> |<span data-ttu-id="3ed47-213">contoso.com (IPv6을 사용 하는 경우 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="3ed47-213">contoso.com (leave blank if using IPv6)</span></span>  <br/> |
    |<span data-ttu-id="3ed47-214">IPv6 패턴</span><span class="sxs-lookup"><span data-stu-id="3ed47-214">IPv6 Pattern</span></span>  <br/> |<span data-ttu-id="3ed47-215">contoso.com (IPv4를 사용 하는 경우 비워 둡니다.)</span><span class="sxs-lookup"><span data-stu-id="3ed47-215">contoso.com (leave blank if using IPv4)</span></span>  <br/> |
    |<span data-ttu-id="3ed47-216">설명</span><span class="sxs-lookup"><span data-stu-id="3ed47-216">Description</span></span>  <br/> |<span data-ttu-id="3ed47-217">SIPRoute 패턴-mediarv</span><span class="sxs-lookup"><span data-stu-id="3ed47-217">SIPRoute Pattern to mediarv</span></span>  <br/> |
    |<span data-ttu-id="3ed47-218">경로 파티션</span><span class="sxs-lookup"><span data-stu-id="3ed47-218">Route Partition</span></span>  <br/> |<span data-ttu-id="3ed47-219">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="3ed47-219">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="3ed47-220">SIP 트렁크/라우트 목록</span><span class="sxs-lookup"><span data-stu-id="3ed47-220">SIP Trunk/Route List</span></span>  <br/> |<span data-ttu-id="3ed47-221">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="3ed47-221">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="3ed47-222">블록 패턴 확인란</span><span class="sxs-lookup"><span data-stu-id="3ed47-222">Block Pattern checkbox</span></span>  <br/> |<span data-ttu-id="3ed47-223">선택 하지 않은 상태로 나가기</span><span class="sxs-lookup"><span data-stu-id="3ed47-223">leave unchecked</span></span>  <br/> |
   
25. <span data-ttu-id="3ed47-224">기본 설정에서 오디오 또는 비디오 비트 전송률을 변경한 경우이를 기본값으로 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-224">If you have changed the audio or video bit rates from the default settings, you will need to return them to the defaults.</span></span> <span data-ttu-id="3ed47-225">오디오/비디오 통화에 대 한 비트 전송률을 설정 하려면 Cisco 통합 CM 관리-\>시스템\>지역 정보-\>지역으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-225">To set the bit rate for Audio/Video calls, navigate to Cisco Unified CM Administration-\>System-\>Region Information-\>Region.</span></span> <span data-ttu-id="3ed47-226">참조에 대 한 기본값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-226">The defaults are shown below for reference:</span></span>
    
    |<span data-ttu-id="3ed47-227">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="3ed47-227">**Parameter**</span></span>|<span data-ttu-id="3ed47-228">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="3ed47-228">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="3ed47-229">영역인</span><span class="sxs-lookup"><span data-stu-id="3ed47-229">Region</span></span>  <br/> |<span data-ttu-id="3ed47-230">기본값</span><span class="sxs-lookup"><span data-stu-id="3ed47-230">Default</span></span>  <br/> |
    |<span data-ttu-id="3ed47-231">오디오 코덱 기본 설정 목록</span><span class="sxs-lookup"><span data-stu-id="3ed47-231">Audio Codec Preference List</span></span>  <br/> |<span data-ttu-id="3ed47-232">시스템 기본값</span><span class="sxs-lookup"><span data-stu-id="3ed47-232">System Default</span></span>  <br/> |
    |<span data-ttu-id="3ed47-233">최대 오디오 비트 전송률</span><span class="sxs-lookup"><span data-stu-id="3ed47-233">Maximum Audio Bit Rate</span></span>  <br/> |<span data-ttu-id="3ed47-234">64 kbps (722, 711)</span><span class="sxs-lookup"><span data-stu-id="3ed47-234">64 kbps (G.722, G.711)</span></span>  <br/> |
    |<span data-ttu-id="3ed47-235">비디오 통화에 대 한 최대 세션 비트 전송률</span><span class="sxs-lookup"><span data-stu-id="3ed47-235">Maximum Session Bit Rate for Video Calls</span></span>  <br/> |<span data-ttu-id="3ed47-236">20만 kbps</span><span class="sxs-lookup"><span data-stu-id="3ed47-236">200000 kbps</span></span>  <br/> |
    |<span data-ttu-id="3ed47-237">최대 세션 비트 전송률</span><span class="sxs-lookup"><span data-stu-id="3ed47-237">Maximum Session Bit Rate</span></span>  <br/> |<span data-ttu-id="3ed47-238">20억 kbps</span><span class="sxs-lookup"><span data-stu-id="3ed47-238">2000000000 kbps</span></span>  <br/> |
   
<span data-ttu-id="3ed47-239">이 시점에서 CUCM video gateway는 VIS와 함께 작동 하도록 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-239">At this point the CUCM video gateway is configured to work with the VIS.</span></span> <span data-ttu-id="3ed47-240">통합 하고자 하는 각 VTC에서 해당 구성을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-240">Corresponding configuration will need to be done on each VTC you wish to integrate.</span></span>
> [!NOTE]
> <span data-ttu-id="3ed47-241">복구 력을 향상 시키기 위해 두 번째 비디오 Interop 서버 또는 VIS 풀에서 작동 하도록이 CUCM gateway를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ed47-241">To improve resiliency, you may want to configure this CUCM gateway to work with a second Video Interop Server or VIS pool.</span></span> <span data-ttu-id="3ed47-242">자세한 내용은 [회복성 메커니즘](../../plan-your-deployment/video-interop-server.md#resiliency) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ed47-242">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3ed47-243">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ed47-243">See also</span></span>

[<span data-ttu-id="3ed47-244">비즈니스용 Skype 서버와 상호 운용을 위한 VTC 구성</span><span class="sxs-lookup"><span data-stu-id="3ed47-244">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
