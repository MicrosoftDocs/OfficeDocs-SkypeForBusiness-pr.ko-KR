---
title: 비즈니스용 Skype 서버와의 상호 연계를 위한 VTC 구성
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
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: '요약: 비즈니스용 Skype 서버에서 작동하도록 VTC 장치를 구성합니다.'
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802078"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="85bd3-103">비즈니스용 Skype 서버와의 상호 연계를 위한 VTC 구성</span><span class="sxs-lookup"><span data-stu-id="85bd3-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="85bd3-104">**요약:** 비즈니스용 Skype 서버에서 작동하도록 VTC 장치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="85bd3-105">SIP 트렁크 및 Cisco Unified Communications Manager(CallManager 또는 CUCM) 비디오 게이트웨이를 통해 비즈니스용 Skype VIS 서버에 연결할 각 VTC에 대해 다음 구성 사용자 지정 절차를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="85bd3-106">여기에 설명된 설정은 VIS에서 작동하도록 CUCM을 구성하는 방법의 예로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="85bd3-107">다른 설정 및/또는 대체 CUCM 기능의 사용법을 사용하여 동일한 결과를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="85bd3-108">특정 시나리오에 대해 최적의 구성을 권장하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="85bd3-109">CUCM에 등록된 VTC 구성</span><span class="sxs-lookup"><span data-stu-id="85bd3-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="85bd3-110">Cisco VTC 장치에 로그인하고 Configuration- \> System Configuration- \> Provisioning으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="85bd3-111">다음 설정을 확인하고 필요한 경우 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="85bd3-112">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="85bd3-112">**Parameter**</span></span>|<span data-ttu-id="85bd3-113">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="85bd3-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="85bd3-114">프로비저닝 모드</span><span class="sxs-lookup"><span data-stu-id="85bd3-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="85bd3-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="85bd3-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="85bd3-116">ExternalManager 주소</span><span class="sxs-lookup"><span data-stu-id="85bd3-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="85bd3-117">CUCM의 FQDN</span><span class="sxs-lookup"><span data-stu-id="85bd3-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="85bd3-118">ExternalManager 도메인</span><span class="sxs-lookup"><span data-stu-id="85bd3-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="85bd3-119">CUCM의 도메인</span><span class="sxs-lookup"><span data-stu-id="85bd3-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="85bd3-120">구성 - \> 시스템 구성 - \> 네트워크로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="85bd3-121">다음 설정을 확인하고 필요한 경우 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="85bd3-122">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="85bd3-122">**Parameter**</span></span>|<span data-ttu-id="85bd3-123">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="85bd3-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="85bd3-124">DNS 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="85bd3-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="85bd3-125">CUCM의 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="85bd3-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="85bd3-126">DNS Server 1 주소</span><span class="sxs-lookup"><span data-stu-id="85bd3-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="85bd3-127">원하는 DNS 서버 주소</span><span class="sxs-lookup"><span data-stu-id="85bd3-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="85bd3-128">구성- 시스템 구성 \> - \> 네트워크 서비스로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="85bd3-129">H.323 모드가 꺼져 있으며 SIP 모드가 켜져 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="85bd3-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="85bd3-130">이러한 옵션은 끝점이 CUCM에 등록될 때 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="85bd3-131">다음 설정을 확인하고 필요한 경우 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="85bd3-132">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="85bd3-132">**Parameter**</span></span>|<span data-ttu-id="85bd3-133">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="85bd3-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="85bd3-134">H.323 모드</span><span class="sxs-lookup"><span data-stu-id="85bd3-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="85bd3-135">해제</span><span class="sxs-lookup"><span data-stu-id="85bd3-135">Off</span></span> <br/> |
   |<span data-ttu-id="85bd3-136">HTTP 모드</span><span class="sxs-lookup"><span data-stu-id="85bd3-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="85bd3-137">켜짐</span><span class="sxs-lookup"><span data-stu-id="85bd3-137">On</span></span> <br/> |
   | <span data-ttu-id="85bd3-138">SIP 모드</span><span class="sxs-lookup"><span data-stu-id="85bd3-138">SIP Mode</span></span> <br/> | <span data-ttu-id="85bd3-139">켜짐</span><span class="sxs-lookup"><span data-stu-id="85bd3-139">On</span></span> <br/> |
   |<span data-ttu-id="85bd3-140">텔넷 모드</span><span class="sxs-lookup"><span data-stu-id="85bd3-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="85bd3-141">켜짐</span><span class="sxs-lookup"><span data-stu-id="85bd3-141">On</span></span> <br/> |
   |<span data-ttu-id="85bd3-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="85bd3-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="85bd3-143">켜짐</span><span class="sxs-lookup"><span data-stu-id="85bd3-143">On</span></span> <br/> |
   |<span data-ttu-id="85bd3-144">XMLAPI 모드</span><span class="sxs-lookup"><span data-stu-id="85bd3-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="85bd3-145">켜짐</span><span class="sxs-lookup"><span data-stu-id="85bd3-145">On</span></span> <br/> |
   
7. <span data-ttu-id="85bd3-146">구성- \> 시스템 구성 - \> SIP로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="85bd3-147">다음 설정을 확인하고 필요한 경우 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="85bd3-148">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="85bd3-148">**Parameter**</span></span>|<span data-ttu-id="85bd3-149">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="85bd3-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="85bd3-150">프로필 1 - DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="85bd3-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="85bd3-151">TCP</span><span class="sxs-lookup"><span data-stu-id="85bd3-151">TCP</span></span> <br/> |
   |<span data-ttu-id="85bd3-152">프로필 1 - 아웃바운드</span><span class="sxs-lookup"><span data-stu-id="85bd3-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="85bd3-153">해제</span><span class="sxs-lookup"><span data-stu-id="85bd3-153">Off</span></span> <br/> |
   |<span data-ttu-id="85bd3-154">프로필 1 - TlsVerify</span><span class="sxs-lookup"><span data-stu-id="85bd3-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="85bd3-155">켜짐</span><span class="sxs-lookup"><span data-stu-id="85bd3-155">On</span></span> <br/> |
   |<span data-ttu-id="85bd3-156">프로필 1 - 유형</span><span class="sxs-lookup"><span data-stu-id="85bd3-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="85bd3-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="85bd3-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="85bd3-158">프로필 1 - URI</span><span class="sxs-lookup"><span data-stu-id="85bd3-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="85bd3-159">CUCM 등록 시 자동으로 할당</span><span class="sxs-lookup"><span data-stu-id="85bd3-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="85bd3-160">프록시 1 - 주소</span><span class="sxs-lookup"><span data-stu-id="85bd3-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="85bd3-161">CUCM의 호스트 이름</span><span class="sxs-lookup"><span data-stu-id="85bd3-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="85bd3-162">이제 VTC가 상호 연결에 대해 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="85bd3-163">서비스를 시작하기 전에 CUCM 쪽에서 수행할 마지막 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="85bd3-164">CUCM에서 VTC 장치 구성</span><span class="sxs-lookup"><span data-stu-id="85bd3-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="85bd3-165">CUCM에 로그인하고 Cisco 통합 CM 관리 - \> 장치 - \> 전화 찾기로 \> 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="85bd3-166">구성할 VTC 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="85bd3-167">전화 구성 화면에서 다음 설정을 확인하고 필요한 경우 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="85bd3-168">이러한 설정을 변경하거나 확인한 후 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="85bd3-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="85bd3-169">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="85bd3-169">**Parameter**</span></span>|<span data-ttu-id="85bd3-170">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="85bd3-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="85bd3-171">장치 정보 - 전화 단추 템플릿</span><span class="sxs-lookup"><span data-stu-id="85bd3-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="85bd3-172">Standard Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="85bd3-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="85bd3-173">장치 정보 - 일반 전화 프로필</span><span class="sxs-lookup"><span data-stu-id="85bd3-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="85bd3-174">표준 일반 전화 프로필</span><span class="sxs-lookup"><span data-stu-id="85bd3-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="85bd3-175">장치 정보 - 검색 공간 호출</span><span class="sxs-lookup"><span data-stu-id="85bd3-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="85bd3-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="85bd3-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="85bd3-177">장치 정보 - AAR 호출 검색 공간</span><span class="sxs-lookup"><span data-stu-id="85bd3-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="85bd3-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="85bd3-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="85bd3-179">장치 정보 - 미디어 리소스 그룹 목록</span><span class="sxs-lookup"><span data-stu-id="85bd3-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="85bd3-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="85bd3-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="85bd3-181">프로토콜 관련 정보 - 장치 보안 프로필</span><span class="sxs-lookup"><span data-stu-id="85bd3-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="85bd3-182">Cisco Telepresence Codec C40</span><span class="sxs-lookup"><span data-stu-id="85bd3-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="85bd3-183">프로토콜 관련 정보 - 호출 검색 공간 다시우기</span><span class="sxs-lookup"><span data-stu-id="85bd3-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="85bd3-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="85bd3-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="85bd3-185">프로토콜 관련 정보 - 구독 호출 검색 공간</span><span class="sxs-lookup"><span data-stu-id="85bd3-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="85bd3-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="85bd3-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="85bd3-187">프로토콜 관련 정보 -SIP 프로필</span><span class="sxs-lookup"><span data-stu-id="85bd3-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="85bd3-188">표준 SIP Profile for Telepresence Endpoint</span><span class="sxs-lookup"><span data-stu-id="85bd3-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="85bd3-189">VTC 구성을 저장한 후 장치의 전화 구성 화면으로 다시 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="85bd3-190">연결 그룹의 화면 맨 위에 있는 비디오 Interop에 대한 연결(연결)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="85bd3-191">그러면 디렉터리 번호 구성 화면이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="85bd3-192">다음 설정을 확인하고 필요한 경우 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="85bd3-193">디렉터리 번호 정보 및 디렉터리 번호 설정에 표시된 적절하게 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="85bd3-194">**매개 변수**</span><span class="sxs-lookup"><span data-stu-id="85bd3-194">**Parameter**</span></span>|<span data-ttu-id="85bd3-195">**권장 설정**</span><span class="sxs-lookup"><span data-stu-id="85bd3-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="85bd3-196">디렉터리 번호 정보 - 경로 파티션</span><span class="sxs-lookup"><span data-stu-id="85bd3-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="85bd3-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="85bd3-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="85bd3-198">디렉터리 번호 설정 - 검색 공간 호출</span><span class="sxs-lookup"><span data-stu-id="85bd3-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="85bd3-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="85bd3-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="85bd3-200">MLPP 대체 사용자 및 기밀 액세스 수준 설정 - MLPP 호출 검색 공간</span><span class="sxs-lookup"><span data-stu-id="85bd3-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="85bd3-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="85bd3-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="85bd3-202">디바이스의 줄 1 - 디스플레이(발신자 ID)</span><span class="sxs-lookup"><span data-stu-id="85bd3-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="85bd3-203">원하는 경우</span><span class="sxs-lookup"><span data-stu-id="85bd3-203">As desired</span></span> <br/> |
   |<span data-ttu-id="85bd3-204">디바이스의 줄 1 - ASCII 디스플레이(발신자 ID)</span><span class="sxs-lookup"><span data-stu-id="85bd3-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="85bd3-205">원하는 경우</span><span class="sxs-lookup"><span data-stu-id="85bd3-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="85bd3-206">완료되면 화면 맨 위로 스크롤하고 저장을 **누르고 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="85bd3-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="85bd3-207">이제 이 VTC 장치에 대한 구성이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="85bd3-208">기업의 다른 VTC 장치에 대해 이 프로세스를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85bd3-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

