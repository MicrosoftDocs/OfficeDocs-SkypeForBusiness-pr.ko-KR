---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 정책 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 정책 구성
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815038"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="5c92b-103">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5c92b-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="5c92b-104">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5c92b-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="5c92b-105">스트레스 및 성능 도구를 실행하기 전에 비즈니스용 Skype 서버 2015에서 구성할 수 있는 몇 가지 정책 및 기타 영역이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="5c92b-106">보관 정책</span><span class="sxs-lookup"><span data-stu-id="5c92b-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="5c92b-107">회의 정책</span><span class="sxs-lookup"><span data-stu-id="5c92b-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="5c92b-108">연락처 정책</span><span class="sxs-lookup"><span data-stu-id="5c92b-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="5c92b-109">페더전 정책</span><span class="sxs-lookup"><span data-stu-id="5c92b-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="5c92b-110">통화 제어 정책</span><span class="sxs-lookup"><span data-stu-id="5c92b-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="5c92b-111">음성 라우팅 규칙</span><span class="sxs-lookup"><span data-stu-id="5c92b-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="5c92b-112">회의 참석자 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="5c92b-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="5c92b-113">서버 통화 파크 서비스</span><span class="sxs-lookup"><span data-stu-id="5c92b-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="5c92b-114">긴급 통화</span><span class="sxs-lookup"><span data-stu-id="5c92b-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="5c92b-115">응답 그룹 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="5c92b-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="5c92b-116">보관 정책</span><span class="sxs-lookup"><span data-stu-id="5c92b-116">Archiving policy</span></span>
<span data-ttu-id="5c92b-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="5c92b-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="5c92b-118">비즈니스용 Skype 서버 토폴로지에서 보관 서버를 배포한 경우 이 스크립트를 ArchivingPolicy.ps1 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="5c92b-119">추가 지원이 필요한 경우 보관 및 웹 회의 cmdlet을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="5c92b-120">회의 정책</span><span class="sxs-lookup"><span data-stu-id="5c92b-120">Conferencing policy</span></span>
<span data-ttu-id="5c92b-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="5c92b-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="5c92b-122">회의의 경우 이 MeetingPolicy.ps1 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="5c92b-123">추가 지원이 필요한 경우 웹 회의 cmdlet을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="5c92b-124">연락처 정책</span><span class="sxs-lookup"><span data-stu-id="5c92b-124">Contacts policy</span></span>
<span data-ttu-id="5c92b-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="5c92b-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="5c92b-126">ContactsPolicy.ps1 스크립트는 검토해야 하는 샘플이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="5c92b-127">추가 참조가 필요한 경우 IM 및 현재 상태 cmdlet을 사용하면 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="5c92b-128">페더전 정책</span><span class="sxs-lookup"><span data-stu-id="5c92b-128">Federation policy</span></span>
<span data-ttu-id="5c92b-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="5c92b-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="5c92b-130">페더링에 대한 샘플 스크립트는 FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="5c92b-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="5c92b-131">추가 정보를 파악해야 하는 경우 검토할 cmdlet은 에지 서버, 페더ation 및 외부 액세스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="5c92b-132">통화 제어 정책</span><span class="sxs-lookup"><span data-stu-id="5c92b-132">Call Admission Control policy</span></span>
<span data-ttu-id="5c92b-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="5c92b-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="5c92b-134">이 정책에 대한 BandwidthPolicy.ps1 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="5c92b-135">통화 입장 제어 cmdlet에는 추가 정보도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="5c92b-136">음성 라우팅 규칙</span><span class="sxs-lookup"><span data-stu-id="5c92b-136">Voice Routing rules</span></span>
<span data-ttu-id="5c92b-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="5c92b-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="5c92b-138">음성 라우팅을 위한 RoutingRules.ps1 스크립트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="5c92b-139">이러한 규칙을 구성할 때 사용자를 만들 때 지정할 수 있도록 전화 컨텍스트(/Location Profile 또는 /SimpleName) 및 내부/외부 영역 코드를 메모합니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="5c92b-140">또한 LyncPerfTool 구성(특히 PSTN-UC 및 UC-PSTN용) 중에도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="5c92b-141">예를 들어 RoutingRules.ps1 예제에서 **New-CsDialPlan** cmdlet 호출의 SimpleName 매개 변수를 다음 UserProfileGenerator.exe.</span><span class="sxs-lookup"><span data-stu-id="5c92b-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![비즈니스용 Skype 로드 구성 도구, 음성 시나리오 탭, 대화에 대한 고급 설정](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="5c92b-143">자세한 내용은 cmdlet의 Enterprise Voice 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="5c92b-144">회의 참석자 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="5c92b-144">Conference Attendant application</span></span>
<span data-ttu-id="5c92b-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="5c92b-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="5c92b-146">먼저 스크립트를 ConferenceAutoAttendantConfiguration.ps1 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="5c92b-147">아래와 같은 구성 생성을 위해 LyncPerfTool 구성 도구에 입력할 수 있도록 ConferencingAutoAttendant 전화 번호(기본적으로 11211111111)를 기록해 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![회의 부하 수준 및 전화 번호를 보여 주며 음성 시나리오 탭](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="5c92b-149">회의 및 전화 접속 회의 cmdlet에서 더 많은 세부 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="5c92b-150">서버 통화 파크 서비스</span><span class="sxs-lookup"><span data-stu-id="5c92b-150">Server Call Park service</span></span>
<span data-ttu-id="5c92b-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="5c92b-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="5c92b-152">이 설정은 기본적으로 실제로 사용하지 않도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-152">This is actually disabled by default.</span></span> <span data-ttu-id="5c92b-153">테스트해야 CallParkConfiguration.ps1 스크립트를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="5c92b-154">또한 필요한 경우 통화 파킹 응용 프로그램 cmdlet을 체크 아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="5c92b-155">긴급 통화</span><span class="sxs-lookup"><span data-stu-id="5c92b-155">Emergency calls</span></span>
<span data-ttu-id="5c92b-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="5c92b-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="5c92b-157">다음 단계를 수행하여 긴급 통화에 대한 스트레스 및 성능 테스트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="5c92b-158">긴급 통화에 대한 음성 경로를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="5c92b-159">이 음성 RoutingRules.ps1 설정하는 방법의 예는 **"E911에서 PSTN으로** 경로" 설명 아래에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="5c92b-160">예제 명령은 RoutingRules.ps1 911이 아닌 119를 포함하는 숫자 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="5c92b-161">부하 테스트 중에 911(또는 실제 로컬 긴급 번호)을 사용하여 로컬 응급 운영자에게 실수로 전화를 걸지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="5c92b-162">이 구성은 시뮬레이션 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="5c92b-163">다음 그림과 같이 UserProvisioningTool의 위치 정보 서비스 구성 탭에 있는 값을 입력하여 주소를 구성합니다. </span><span class="sxs-lookup"><span data-stu-id="5c92b-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![주소, 서브넷, 스위치 및 포트 수를 표시하는 사용자 프로비전 도구입니다.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="5c92b-165">UserProvisioningTool에 모든 것을 입력한 후 **LIS 구성** 파일 생성 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="5c92b-166">이제 포트, 서브넷, 스위치 및 WAP(무선 액세스 지점)에 대한 CSV 파일과 스트레스 및 성능 도구용 XML 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="5c92b-167">LIS(위치 정보 서비스)를 구성할 때 CSV 파일을 입력에 사용할 LisConfiguration.ps1 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="5c92b-168">이렇게하려면 스트레스 및 성능 도구 실행 파일(Locations0.xml)과 동일한 폴더로 LyncPerfTool.exe.</span><span class="sxs-lookup"><span data-stu-id="5c92b-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="5c92b-169">이렇게 하면 위치 프로필(다이얼 플랜) 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="5c92b-170">응답 그룹 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="5c92b-170">Configuring Response Group application</span></span>
<span data-ttu-id="5c92b-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="5c92b-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="5c92b-172">샘플 스크립트는 ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="5c92b-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="5c92b-173">추가 구성 세부 정보를 검토할 응답 그룹 응용 프로그램 cmdlet도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="5c92b-174">다음 다이어그램에는 몇 가지 구성 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c92b-174">The following diagram will show some of the configuration details:</span></span>
  
![테스트할 기존 워크플로를 보여 주며 응답 그룹 구성 도구](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

