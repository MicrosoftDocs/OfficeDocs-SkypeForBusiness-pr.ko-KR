---
title: 비즈니스용 Skype 서버의 E9-1-1 음성 경로 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: 비즈니스용 Skype Server Enterprise Voice에서 E9 구성-1 ~ 1 개의 음성 경로
ms.openlocfilehash: c835aa2ab2b20f7877aa6a0deeb70c7459bcd8cc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001398"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="671d6-103">비즈니스용 Skype 서버의 E9-1-1 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="671d6-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="671d6-104">비즈니스용 Skype Server Enterprise Voice에서 E9 구성-1 ~ 1 개의 음성 경로</span><span class="sxs-lookup"><span data-stu-id="671d6-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="671d6-105">E9-1-1을 배포 하려면 먼저 긴급 통화 음성 경로를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="671d6-106">음성 경로를 만드는 방법에 대 한 자세한 내용은 비즈니스용 [Skype에서 음성 경로 만들기 또는 수정을](create-or-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="671d6-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="671d6-107">예를 들어 배포에 기본 SIP 트렁크 및 보조 SIP 트렁크가 포함 되어 있는 경우 둘 이상의 경로를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="671d6-108">E9-1-1 초대에 위치 정보를 포함 하려면 E9-1 서비스 공급자에 연결 된 SIP 트렁크를 구성 하 여 게이트웨이를 통해 비상 전화를 경로를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="671d6-109">이렇게 하려면 **집합-set-cstrunkconfiguration** Cmdlet의 EnablePIDFLOSupport 플래그를 True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="671d6-110">EnablePIDFLOSupport의 기본 값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="671d6-111">예를 들어 `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` , 대체 PSTN (공개 통신 네트워크) 게이트웨이와 긴급 위치 id 번호 (elin) 게이트웨이에서는 위치를 수신할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="671d6-112">E9-1-1 음성 경로를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="671d6-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="671d6-113">RTCUniversalServerAdmins 그룹의 구성원 인 계정이 나 CsVoiceAdministrator 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="671d6-114">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="671d6-115">다음 cmdlet을 실행 하 여 새 PSTN 사용 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="671d6-116">이 이름은 위치 정책의 **PSTN** 설정에 사용 하는 이름과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="671d6-117">배포에 여러 개의 전화 사용 레코드가 있지만, 다음 예에서는 사용 가능한 PSTN 사용량의 현재 목록에 "비상 사용량"을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="671d6-118">자세한 내용은 [비즈니스용 Skype에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성을](voice-and-pstn.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="671d6-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="671d6-119">다음 cmdlet을 실행 하 여 이전 단계에서 만든 PSTN 사용 레코드를 사용 하 여 새 음성 경로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="671d6-120">번호 패턴은 위치 정책의 **긴급 전화 걸기 문자열** 설정에 사용 되는 번호 패턴을 동일 하 게 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="671d6-121">비즈니스용 Skype가 긴급 통화에 "+"를 추가 하기 때문에 "+" 기호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="671d6-122">"Co1-pstngateway-1"은 E9-1-1 서비스 공급자의 SIP 트렁크 서비스 ID 이거나 게이트웨이 서비스 ID의 ELIN입니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="671d6-123">다음 예에서는 "EmergencyRoute"를 음성 경로의 이름으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="671d6-124">선택적으로 SIP 트렁크 연결에 대해 다음 cmdlet을 실행 하 여 E9-1 서비스 공급자의 SIP 트렁크에서 처리 되지 않는 통화에 대 한 로컬 경로를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="671d6-125">이 경로는 E9 서비스 공급자에 대 한 연결을 사용할 수 없는 경우에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="671d6-126">다음 예제에서는 사용자가 음성 정책에 "로컬"을 사용 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="671d6-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


