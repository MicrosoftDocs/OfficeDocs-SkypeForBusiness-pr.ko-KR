---
title: 비즈니스용 Skype Server 2015 스트레스 및 성능 도구에 맞게 정책 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 정책 구성입니다.
ms.openlocfilehash: bfdf0d9875a37f7f4a1f98aa24cd6fd5c3176a00
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816197"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="ed586-103">비즈니스용 Skype Server 2015 스트레스 및 성능 도구에 맞게 정책 구성</span><span class="sxs-lookup"><span data-stu-id="ed586-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="ed586-104">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 정책 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="ed586-105">스트레스 및 성능 도구를 실행 하기 전에 비즈니스용 Skype Server 2015에서 구성할 수 있는 몇 가지 정책과 기타 영역이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="ed586-106">보관 정책</span><span class="sxs-lookup"><span data-stu-id="ed586-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="ed586-107">회의 정책</span><span class="sxs-lookup"><span data-stu-id="ed586-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="ed586-108">연락처 정책</span><span class="sxs-lookup"><span data-stu-id="ed586-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="ed586-109">페더레이션 정책</span><span class="sxs-lookup"><span data-stu-id="ed586-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="ed586-110">통화 허용 제어 정책</span><span class="sxs-lookup"><span data-stu-id="ed586-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="ed586-111">음성 라우팅 규칙</span><span class="sxs-lookup"><span data-stu-id="ed586-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="ed586-112">컨퍼런스 전화 교환 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ed586-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="ed586-113">서버 통화 공원 서비스</span><span class="sxs-lookup"><span data-stu-id="ed586-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="ed586-114">비상 전화</span><span class="sxs-lookup"><span data-stu-id="ed586-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="ed586-115">응답 그룹 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="ed586-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="ed586-116">보관 정책</span><span class="sxs-lookup"><span data-stu-id="ed586-116">Archiving policy</span></span>
<span data-ttu-id="ed586-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ed586-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="ed586-118">비즈니스용 Skype 서버 토폴로지에 배포 된 보관 서버가 있는 경우 ArchivingPolicy 스크립트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="ed586-119">추가 지원이 필요한 경우 보관 및 웹 회의 cmdlet을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed586-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="ed586-120">회의 정책</span><span class="sxs-lookup"><span data-stu-id="ed586-120">Conferencing policy</span></span>
<span data-ttu-id="ed586-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ed586-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="ed586-122">회의의 경우 MeetingPolicy 스크립트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="ed586-123">추가 지원이 필요한 경우 웹 회의 cmdlet을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed586-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="ed586-124">연락처 정책</span><span class="sxs-lookup"><span data-stu-id="ed586-124">Contacts policy</span></span>
<span data-ttu-id="ed586-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ed586-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="ed586-126">연락처 Spolicy 스크립트는 검토 해야 하는 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="ed586-127">추가 참조가 필요한 경우 메신저 대화 및 현재 상태 cmdlet이 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="ed586-128">페더레이션 정책</span><span class="sxs-lookup"><span data-stu-id="ed586-128">Federation policy</span></span>
<span data-ttu-id="ed586-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ed586-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="ed586-130">페더레이션에 대 한 샘플 스크립트는 FederationPolicy입니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="ed586-131">검토가 필요한 경우에는 Edge 서버, 페더레이션 및 외부 액세스를 확인할 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="ed586-132">통화 허용 제어 정책</span><span class="sxs-lookup"><span data-stu-id="ed586-132">Call Admission Control policy</span></span>
<span data-ttu-id="ed586-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ed586-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="ed586-134">이 정책에 대해 BandwidthPolicy를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="ed586-135">또한 통화 허용 제어 cmdlet에는 추가 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="ed586-136">음성 라우팅 규칙</span><span class="sxs-lookup"><span data-stu-id="ed586-136">Voice Routing rules</span></span>
<span data-ttu-id="ed586-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="ed586-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="ed586-138">음성 라우팅에 대 한 RoutingRules 샘플 스크립트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="ed586-139">이러한 규칙을 구성 하는 경우 사용자를 만들 때 지정할 수 있도록 전화 컨텍스트 (/위치 프로필 또는/SimpleName) 및 내부/외부 지역 코드를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="ed586-140">또한 L Cperf도구 구성 중에도 필요 합니다 (특히 PSTN-UC 및 UC-PSTN 용).</span><span class="sxs-lookup"><span data-stu-id="ed586-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="ed586-141">예를 들어 RoutingRules의 **새-CsDialPlan 플랜** cmdlet에 대 한 호출의 simplename 매개 변수는 다음 UserProfileGenerator 그림의 locationprofile 값에 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![비즈니스용 Skype 부하 구성 도구, 음성 시나리오 탭, 대화에 대 한 고급 설정.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="ed586-143">자세한 내용은 엔터프라이즈 음성 cmdlet을 검토 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="ed586-144">컨퍼런스 전화 교환 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="ed586-144">Conference Attendant application</span></span>
<span data-ttu-id="ed586-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="ed586-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="ed586-146">먼저 ConferenceAutoAttendantConfiguration 스크립트를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="ed586-147">다음과 같이 구성 생성을 위한 LConferencingAutoAttendant Cperf도구 구성 도구에 입력할 수 있도록 기본적으로 1121111111 전화 번호를 기록해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![회의 로드 수준 및 전화 번호를 보여주는 음성 시나리오 탭](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="ed586-149">회의 및 전화 접속 회의 cmdlet에서 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="ed586-150">서버 통화 공원 서비스</span><span class="sxs-lookup"><span data-stu-id="ed586-150">Server Call Park service</span></span>
<span data-ttu-id="ed586-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="ed586-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="ed586-152">기본적으로이 기능은 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-152">This is actually disabled by default.</span></span> <span data-ttu-id="ed586-153">이를 테스트 해야 하는 경우 CallParkConfiguration 샘플 스크립트를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="ed586-154">또한 필요에 따라 통화 공원 응용 프로그램 cmdlet을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed586-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="ed586-155">비상 전화</span><span class="sxs-lookup"><span data-stu-id="ed586-155">Emergency calls</span></span>
<span data-ttu-id="ed586-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="ed586-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="ed586-157">비상 전화에 대 한 스트레스 및 성능 테스트를 구성 하려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="ed586-158">비상 전화에 대 한 음성 경로를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="ed586-159">RoutingRules 스크립트를 사용 하 고 " **PSTN으로 E911 라우팅** " 설명 아래에서이 음성 경로를 설정 하는 방법에 대 한 예를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ed586-160">RoutingRules의 예제 명령에 911이 아닌 숫자 119를 포함 하는 숫자 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="ed586-161">911 (또는 실제 지역 비상 전화 번호)을 사용 하 여 부하 테스트 중에 지역 긴급 운영자에 게 실수로 전화를 하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="ed586-162">이 구성은 시뮬레이션 용도로만 사용 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed586-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="ed586-163">다음 그림과 같이 UserProvisioningTool의 **위치 정보 서비스 구성** 탭에 있는 값을 입력 하 여 주소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![주소, 서브넷, 스위치 및 포트 수를 보여 주는 사용자 프로비저닝 도구](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="ed586-165">모든 내용을 UserProvisioningTool에 입력 한 후에는 **LIS Config 파일 생성** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="ed586-166">이제 스트레스 및 성능 도구에 대 한 XML 파일은 물론 포트, 서브넷, 스위치 및 WAPs (무선 액세스 지점)에 대 한 CSV 파일도 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="ed586-167">LisConfiguration. ps1 스크립트를 사용 하 여 LIS (위치 정보 서비스)를 구성할 때 입력에 CSV 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="ed586-168">이 작업을 수행 하려면 스트레스 및 성능 도구 실행 파일 (L<c13> Cperftool. exe)과 동일한 폴더를 Locations0로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="ed586-169">이렇게 하면 위치 프로필 (다이얼 플랜) 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="ed586-170">응답 그룹 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="ed586-170">Configuring Response Group application</span></span>
<span data-ttu-id="ed586-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="ed586-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="ed586-172">샘플 스크립트는 ResponseGroupConfiguration. ps1입니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="ed586-173">추가 구성 세부 정보를 검토 하는 응답 그룹 응용 프로그램 cmdlet도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="ed586-174">다음 다이어그램은 몇 가지 구성 세부 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed586-174">The following diagram will show some of the configuration details:</span></span>
  
![테스트에 대 한 기존 워크플로를 보여 주는 응답 그룹 구성 도구입니다.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

