---
title: 비즈니스용 Skype 서버에서 E9-1-1 음성 경로 구성
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: 비즈니스용 Skype 서버에서 E9-1-1 음성 Enterprise Voice.
ms.openlocfilehash: b5f3d12bb586a65fc1c553a021c1a27efb0c7f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804178"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="0f407-103">비즈니스용 Skype 서버에서 E9-1-1 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="0f407-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="0f407-104">비즈니스용 Skype 서버에서 E9-1-1 음성 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0f407-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="0f407-105">E9-1-1을 배포하려면 먼저 긴급 통화 음성 경로를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="0f407-106">음성 경로를 만드는 데 대한 자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 또는 [수정을 참조하세요.](create-or-modify-a-voice-route.md)</span><span class="sxs-lookup"><span data-stu-id="0f407-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="0f407-107">예를 들어 배포에 기본 SIP 트렁크와 보조 SIP 트렁크가 포함된 경우 두 개 이상의 경로를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0f407-108">E9-1-1 INVITE에 위치 정보를 포함하려면 게이트웨이를 통해 긴급 통화를 라우팅하도록 E9-1-1 서비스 공급자에 연결하는 SIP 트렁크를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="0f407-109">이렇게하려면 **Set-CsTrunkConfiguration** cmdlet에서 EnablePIDFLOSupport 플래그를 True로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="0f407-110">EnablePIDFLOSupport의 기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="0f407-111">예를 들어 PSTN(Public Switched Telephone Network) 게이트웨이 및 ELIN(Emergency Location Identification Number) 게이트웨이에 대해 수신 위치를 사용하도록 설정할 `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="0f407-112">E9-1-1 음성 경로를 구성하는 경우</span><span class="sxs-lookup"><span data-stu-id="0f407-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="0f407-113">RTCUniversalServerAdmins 그룹의 구성원인 계정 또는 CsVoiceAdministrator 관리 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="0f407-114">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0f407-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0f407-115">다음 cmdlet을 실행하여 새 PSTN 사용 레코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="0f407-116">위치 정책의 **PSTN** 설정에 사용할 이름과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="0f407-117">배포에 여러 전화 사용 레코드가 사용 가능하기는 하지만 다음 예제에서는 사용 가능한 PSTN 사용법의 현재 목록에 "긴급 사용"을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="0f407-118">자세한 내용은 [비즈니스용 Skype에서 음성 정책, PSTN](voice-and-pstn.md)사용 레코드 및 음성 경로 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f407-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="0f407-119">다음 cmdlet을 실행하여 이전 단계에서 만든 PSTN 사용 레코드를 사용하여 새 음성 경로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="0f407-120">번호 패턴은 위치 정책의 긴급 전화  문자열 설정에 사용되는 번호 패턴과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="0f407-121">비즈니스용 Skype가 긴급 통화에 "+"를 추가하기 때문에 "+" 기호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="0f407-122">"Co1-pstngateway-1"은 E9-1-1 서비스 공급자 또는 ELIN 게이트웨이 서비스 ID의 SIP 트렁크 서비스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="0f407-123">다음 예에서는 음성 경로의 이름으로 "EmergencyRoute"를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="0f407-124">SIP 트렁크 연결의 경우 다음 cmdlet을 실행하여 E9-1-1 서비스 공급자의 SIP 트렁크에서 처리되지 않는 통화에 대한 로컬 경로를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="0f407-125">E9-1-1 서비스 공급자에 대한 연결을 사용할 수 없는 경우 이 경로가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="0f407-126">다음 예에서는 사용자가 음성 정책에 "로컬" 사용법을 사용했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f407-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


