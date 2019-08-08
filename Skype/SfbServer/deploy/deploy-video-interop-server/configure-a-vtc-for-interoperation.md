---
title: 비즈니스용 Skype 서버와 상호 운용을 위한 VTC 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: '요약: 비즈니스용 Skype 서버에서 작동 하도록 VTC 장치를 구성 합니다.'
ms.openlocfilehash: 8c5310479aea38f5623f8ac2e10ef64978aa4aee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235674"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="e015d-103">비즈니스용 Skype 서버와 상호 운용을 위한 VTC 구성</span><span class="sxs-lookup"><span data-stu-id="e015d-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="e015d-104">**요약:** 비즈니스용 Skype 서버에서 작동 하도록 VTC 장치를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="e015d-105">SIP 트렁크 및 Cisco 통합 커뮤니케이션 관리자 (CallManager 또는 CUCM) 비디오 게이트웨이를 통해 비즈니스용 Skype VIS 서버에 연결 하는 각 VTC에 대해 다음 구성 사용자 지정 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="e015d-106">여기에서 설명 하는 설정은 VIS와 작동 하도록 CUCM를 구성할 수 있는 방법의 예제로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="e015d-107">다른 설정 및/또는 대체 CUCM 기능을 사용 하 여 동일한 결과를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="e015d-108">특정 시나리오에 대 한 최적 구성에 대 한 권장 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="e015d-109">CUCM를 사용 하 여 등록 된 VTC 구성</span><span class="sxs-lookup"><span data-stu-id="e015d-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="e015d-110">Cisco VTC 장치에 로그인 하 여 구성-\>시스템 구성-\>프로비저닝으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="e015d-111">필요에 따라 다음 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e015d-112">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="e015d-112">**Parameter**</span></span>|<span data-ttu-id="e015d-113">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="e015d-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e015d-114">프로 비전 모드</span><span class="sxs-lookup"><span data-stu-id="e015d-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="e015d-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="e015d-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="e015d-116">ExternalManager 주소</span><span class="sxs-lookup"><span data-stu-id="e015d-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="e015d-117">CUCM의 FQDN</span><span class="sxs-lookup"><span data-stu-id="e015d-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="e015d-118">ExternalManager 도메인</span><span class="sxs-lookup"><span data-stu-id="e015d-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="e015d-119">CUCM의 도메인</span><span class="sxs-lookup"><span data-stu-id="e015d-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="e015d-120">구성-\>시스템 구성-\>네트워크로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="e015d-121">필요에 따라 다음 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e015d-122">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="e015d-122">**Parameter**</span></span>|<span data-ttu-id="e015d-123">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="e015d-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e015d-124">DNS 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="e015d-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="e015d-125">CUCM의 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="e015d-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="e015d-126">DNS 서버 1 주소</span><span class="sxs-lookup"><span data-stu-id="e015d-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="e015d-127">원하는 DNS 서버 주소</span><span class="sxs-lookup"><span data-stu-id="e015d-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="e015d-128">구성-\>시스템 구성-\>네트워크 서비스를 탐색 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="e015d-129">323 모드가 꺼져 있고 SIP 모드가 켜져 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="e015d-130">이러한 옵션은 끝점을 CUCM에 등록할 때 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="e015d-131">필요에 따라 다음 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e015d-132">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="e015d-132">**Parameter**</span></span>|<span data-ttu-id="e015d-133">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="e015d-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e015d-134">323 모드</span><span class="sxs-lookup"><span data-stu-id="e015d-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="e015d-135">끄십시오</span><span class="sxs-lookup"><span data-stu-id="e015d-135">Off</span></span> <br/> |
   |<span data-ttu-id="e015d-136">HTTP 모드</span><span class="sxs-lookup"><span data-stu-id="e015d-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="e015d-137">등</span><span class="sxs-lookup"><span data-stu-id="e015d-137">On</span></span> <br/> |
   | <span data-ttu-id="e015d-138">SIP 모드</span><span class="sxs-lookup"><span data-stu-id="e015d-138">SIP Mode</span></span> <br/> | <span data-ttu-id="e015d-139">등</span><span class="sxs-lookup"><span data-stu-id="e015d-139">On</span></span> <br/> |
   |<span data-ttu-id="e015d-140">Telnet 모드</span><span class="sxs-lookup"><span data-stu-id="e015d-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="e015d-141">등</span><span class="sxs-lookup"><span data-stu-id="e015d-141">On</span></span> <br/> |
   |<span data-ttu-id="e015d-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="e015d-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="e015d-143">등</span><span class="sxs-lookup"><span data-stu-id="e015d-143">On</span></span> <br/> |
   |<span data-ttu-id="e015d-144">XMLAPI 모드</span><span class="sxs-lookup"><span data-stu-id="e015d-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="e015d-145">등</span><span class="sxs-lookup"><span data-stu-id="e015d-145">On</span></span> <br/> |
   
7. <span data-ttu-id="e015d-146">구성으로 이동-\>시스템 구성-\>SIP.</span><span class="sxs-lookup"><span data-stu-id="e015d-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="e015d-147">필요에 따라 다음 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="e015d-148">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="e015d-148">**Parameter**</span></span>|<span data-ttu-id="e015d-149">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="e015d-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e015d-150">프로필 1-DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="e015d-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="e015d-151">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="e015d-151">TCP</span></span> <br/> |
   |<span data-ttu-id="e015d-152">프로필 1-아웃 바운드</span><span class="sxs-lookup"><span data-stu-id="e015d-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="e015d-153">끄십시오</span><span class="sxs-lookup"><span data-stu-id="e015d-153">Off</span></span> <br/> |
   |<span data-ttu-id="e015d-154">프로필 1-TlsVerify</span><span class="sxs-lookup"><span data-stu-id="e015d-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="e015d-155">등</span><span class="sxs-lookup"><span data-stu-id="e015d-155">On</span></span> <br/> |
   |<span data-ttu-id="e015d-156">프로필 1-종류</span><span class="sxs-lookup"><span data-stu-id="e015d-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="e015d-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="e015d-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="e015d-158">프로필 1-URI</span><span class="sxs-lookup"><span data-stu-id="e015d-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="e015d-159">CUCM 등록 시 자동으로 할당 됨</span><span class="sxs-lookup"><span data-stu-id="e015d-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="e015d-160">프록시 1-주소</span><span class="sxs-lookup"><span data-stu-id="e015d-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="e015d-161">CUCM의 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="e015d-162">이제 VTC가 상호 운용을 위해 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="e015d-163">서비스를 시작 하기 전에 CUCM 측면에서 수행할 마지막 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="e015d-164">CUCM에서 VTC 디바이스 구성</span><span class="sxs-lookup"><span data-stu-id="e015d-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="e015d-165">CUCM에 로그인 하 여 Cisco 통합 CM 관리-\>장치-\>휴대폰-\>검색으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="e015d-166">구성할 VTC 장치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="e015d-167">전화 구성 화면에서 필요에 따라 수정 하 여 다음 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="e015d-168">이러한 설정이 변경 되거나 확인 되 면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="e015d-169">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="e015d-169">**Parameter**</span></span>|<span data-ttu-id="e015d-170">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="e015d-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="e015d-171">장치 정보-전화 단추 서식 파일</span><span class="sxs-lookup"><span data-stu-id="e015d-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="e015d-172">표준 Cisco Telepresence 코덱 C40</span><span class="sxs-lookup"><span data-stu-id="e015d-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="e015d-173">장치 정보-공통 전화 프로필</span><span class="sxs-lookup"><span data-stu-id="e015d-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="e015d-174">표준 일반 전화 프로필</span><span class="sxs-lookup"><span data-stu-id="e015d-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="e015d-175">장치 정보-검색 공간 호출</span><span class="sxs-lookup"><span data-stu-id="e015d-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="e015d-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e015d-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e015d-177">장치 정보-AAR 통화 검색 공간</span><span class="sxs-lookup"><span data-stu-id="e015d-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="e015d-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e015d-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e015d-179">장치 정보-미디어 리소스 그룹 목록</span><span class="sxs-lookup"><span data-stu-id="e015d-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="e015d-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e015d-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e015d-181">프로토콜 관련 정보-장치 보안 프로필</span><span class="sxs-lookup"><span data-stu-id="e015d-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="e015d-182">Cisco Telepresence 코덱 C40</span><span class="sxs-lookup"><span data-stu-id="e015d-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="e015d-183">프로토콜 관련 정보-호출 검색 공간 다시 라우팅</span><span class="sxs-lookup"><span data-stu-id="e015d-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="e015d-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e015d-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e015d-185">프로토콜 관련 정보-통화 검색 공간 구독</span><span class="sxs-lookup"><span data-stu-id="e015d-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="e015d-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e015d-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e015d-187">프로토콜 관련 정보-SIP 프로필</span><span class="sxs-lookup"><span data-stu-id="e015d-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="e015d-188">Telepresence 끝점에 대 한 표준 SIP 프로필</span><span class="sxs-lookup"><span data-stu-id="e015d-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="e015d-189">VTC 구성이 저장 되 면 장치에 대 한 전화 구성 화면으로 다시 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="e015d-190">연결 그룹의 화면 맨 위에서 비디오 Interop 연결을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="e015d-191">이렇게 하면 디렉터리 번호 구성 화면이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="e015d-192">필요에 따라 다음 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="e015d-193">디렉터리 번호 정보와 디렉터리 번호 설정에 표시 된 대로 적절 하 게 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="e015d-194">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="e015d-194">**Parameter**</span></span>|<span data-ttu-id="e015d-195">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="e015d-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="e015d-196">디렉터리 번호 정보-경로 파티션</span><span class="sxs-lookup"><span data-stu-id="e015d-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="e015d-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="e015d-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="e015d-198">디렉터리 번호 설정-검색 공간 호출</span><span class="sxs-lookup"><span data-stu-id="e015d-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="e015d-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e015d-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e015d-200">MLPP 대체 파티 및 기밀 액세스 수준 설정-MLPP 검색 공간 호출</span><span class="sxs-lookup"><span data-stu-id="e015d-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="e015d-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="e015d-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="e015d-202">장치 디스플레이의 라인 1 (발신자 ID)</span><span class="sxs-lookup"><span data-stu-id="e015d-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="e015d-203">필요에 따라</span><span class="sxs-lookup"><span data-stu-id="e015d-203">As desired</span></span> <br/> |
   |<span data-ttu-id="e015d-204">장치-ASCII 표시의 줄 1 (발신자 ID)</span><span class="sxs-lookup"><span data-stu-id="e015d-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="e015d-205">필요에 따라</span><span class="sxs-lookup"><span data-stu-id="e015d-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="e015d-206">완료 되 면 화면 맨 위로 스크롤하고 **저장**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="e015d-207">이제이 VTC 장치에 대 한 구성이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="e015d-208">엔터프라이즈의 다른 VTC 장치에 대해이 과정을 반복 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e015d-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

