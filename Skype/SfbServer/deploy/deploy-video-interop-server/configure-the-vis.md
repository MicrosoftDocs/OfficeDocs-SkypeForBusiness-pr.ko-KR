---
title: 비즈니스용 Skype 서버에서 비디오 Interop 서버 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: '요약: 비즈니스용 Skype 서버에서 VIS (비디오 Interop Server) 역할을 구성 합니다.'
ms.openlocfilehash: 3c0b211897afdde0fc0a01e255cdc14bc466f65c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197349"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="9e31c-103">비즈니스용 Skype 서버에서 비디오 Interop 서버 구성</span><span class="sxs-lookup"><span data-stu-id="9e31c-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="9e31c-104">**요약:** 비즈니스용 Skype 서버에서 VIS (영상 Interop 서버) 역할을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="9e31c-105">Windows PowerShell을 사용 하 여 VIS에서 비디오 trunks 연결 하는 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="9e31c-106">VIS 서비스가 설치 되 면 전역 범위를 포함 하는 비디오 트렁크 구성이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="9e31c-107">이 비디오 트렁크 구성은 더 구체적인 범위를 사용 하 여 영상 트렁크 구성이 없는 모든 trunks에 VIS에 의해 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="9e31c-108">비디오 트렁크 구성은 비디오 trunks 적용 되는 설정 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="9e31c-109">비디오 트렁크 및 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="9e31c-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="9e31c-110">다음 Windows PowerShell 명령을 사용 하 여 VIS 및 모든 비디오 게이트웨이 간의 토폴로지 문서에 정의 된 새로 정의 된 트렁크와 연결할 비디오 트렁크 구성 및 다이얼 플랜을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="9e31c-111">이러한 모든 설정은 전역, 사이트 또는 서비스 (비디오 게이트웨이) 수준에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="9e31c-112">전역 범위를 사용 하는 다이얼 플랜은 비즈니스용 Skype 서버 배포 별로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="9e31c-113">이 다이얼 플랜은 보다 구체적인 범위를 포함 하는 다이얼 플랜이 없는 모든 trunks에 VIS 하 여 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="9e31c-114">Windows PowerShell을 사용 하 여 VIS 구성</span><span class="sxs-lookup"><span data-stu-id="9e31c-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="9e31c-115">다음 Windows PowerShell cmdlet을 사용 하 여 VIS 및 Cisco 통합 커뮤니케이션 관리자 (CallManager 또는 CUCM) 간 트렁크에서 사용할 새 비디오 트렁크 구성 (설정 모음)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="9e31c-116">수정 해야 하는 기존 비디오 트렁크가 있는 경우 다음 Windows PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="9e31c-117">특정 비디오 트렁크 구성과 관련 된 설정을 보려면 다음 Windows PowerShell cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="9e31c-118">특정 비디오 트렁크 구성을 제거 하려면 다음 Windows PowerShell cmdlet을 사용 하세요 (특정 트렁크에 대 한 보다 구체적으로 범위가 지정 된 비디오 트렁크 구성이 없는 경우 전역으로 범위를 설정한 비디오 트렁크 구성이 적용 됨).</span><span class="sxs-lookup"><span data-stu-id="9e31c-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="9e31c-119">다음 Windows PowerShell cmdlet을 사용 하 여 트렁크와 연결할 다이얼 플랜을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="9e31c-120">**CsVoiceNormalizationRule** 명령은 예상 VIS 및 CUCM 조작에 방해가 되는 기본 규칙을 재정의 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="9e31c-121">[제거-csdialplan 다이얼](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) 플랜을 제거 하는 데 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="9e31c-122">요청 URI에 VIS가 아닌 번호를 포함 하는 비디오 게이트웨이에서의 영상 SIP 트렁크 전화의 경우, 연결 된 트렁크와 연결 된 다이얼 플랜의 이름을 읽고 해당 하는 경우 요청 URI의 휴대폰 컨텍스트 부분에 다이얼 플랜 이름을 포함 합니다. 님이 프론트 엔드에 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="9e31c-123">그러면 프런트 엔드에서 번역 응용 프로그램이 다이얼 플랜에 연결 된 정규화 규칙을 추출 하 여 요청 URI에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="9e31c-124">트렁크 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="9e31c-124">Trunk configuration options</span></span>

<span data-ttu-id="9e31c-125">앞에서 설명한 비디오 트렁크 용 Windows PowerShell cmdlet은 이전에 비즈니스용 Skype 서버 2015에서 새롭게 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="9e31c-126">영상 트렁크 구성과 관련 된 설정에 대 한 간략 한 설명이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="9e31c-127">**GatewaySendsRtcpForActiveCalls** 이 매개 변수는 활성 통화에 대 한 RTCP 패킷을 VTC에서 VIS로 보낼지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="9e31c-128">여기서 활성 통화란 미디어가 하나 이상의 방향으로 흐르도록 허용되는 통화를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="9e31c-129">GatewaySendsRtcpForActiveCalls가 True로 설정 된 경우 30 초를 초과 하는 기간 동안 RTCP 패킷을 받지 못하면 VIS에서 통화를 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="9e31c-130">기본값은 **True**입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-130">The default is **True**.</span></span>
  
 <span data-ttu-id="9e31c-131">**GatewaySendsRtcpForCallsOnHold** 이 매개 변수는 대기 중인 통화에 대해 RTCP 패킷을 계속 보낼지 여부를 결정 하 고 어느 방향으로도 이동할 수 있는 미디어 패킷이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="9e31c-132">통화가 대기 중인 동안 VTC에서 RTCP packets가 VIS 되지 않는 경우 VIS에서 통화를 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="9e31c-133">기본값은 **True**입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-133">The default is **True**.</span></span> <span data-ttu-id="9e31c-134">SIPTransport 프로토콜이 TCP로 설정 되 면이 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="9e31c-135">**EnableMediaEncryptionForSipOverTls** 이 매개 변수는 SIPTransport 프로토콜이 TLS로 설정 된 경우 미디어 SRTP를 사용 하거나 사용 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="9e31c-136">기본값은 **True**입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-136">The default is **True**.</span></span> <span data-ttu-id="9e31c-137">SIPTransport 프로토콜이 TCP로 설정 되 면이 설정은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="9e31c-138">**Enablesessiontimer** 이 매개 변수는 비디오 SIP 트렁크에 연결 된 각 SIP 대화 상자의 VIS 측면에서 세션 타이머를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="9e31c-139">기본값은 **False**입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-139">The default is **False**.</span></span>
  
 <span data-ttu-id="9e31c-140">**ForwardErrorCorrectionType** 이 매개 변수는 비디오 스트림에 대 한 FEC (정방향 오류 수정)가 비디오 Interop 서버와 비디오 게이트웨이 간의 레그에 적용 되는지 여부를 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="9e31c-141">ForwardErrorCorrectionType를 "없음"으로 설정 하는 것은 VIS와 비디오 게이트웨이/r e t e r t e r t e t/</span><span class="sxs-lookup"><span data-stu-id="9e31c-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="9e31c-142">ForwardErrorCorrectionType를 "Cisco"로 설정 하면 cisco의 비디오 게이트웨이와 FEC 호환 됩니다 (예: Cisco 통합 커뮤니케이션 관리자 (CUCM)).</span><span class="sxs-lookup"><span data-stu-id="9e31c-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="9e31c-143">기본값은 **없음**입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9e31c-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e31c-144">See also</span></span>

[<span data-ttu-id="9e31c-145">비즈니스용 Skype 서버와 상호 운용할 CUCM 구성</span><span class="sxs-lookup"><span data-stu-id="9e31c-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
