---
title: 비즈니스용 Skype 서버에 대 한 계획 위치 정책
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: 비즈니스용 Skype Server Enterprise Voice에서 향상 된 응급 서비스 (E9-1) 배포의 위치 정책을 계획 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: 5064197dd8d23113d7bfeca30fd3596d5ee89c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802808"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="d9ce1-103">비즈니스용 Skype 서버에 대 한 계획 위치 정책</span><span class="sxs-lookup"><span data-stu-id="d9ce1-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="d9ce1-104">비즈니스용 Skype Server Enterprise Voice에서 향상 된 응급 서비스 (E9-1) 배포의 위치 정책을 계획 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d9ce1-105">비즈니스용 Skype 서버는 이제 클라이언트에 대 한 여러 응급 번호 구성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="d9ce1-106">여러 비상 번호를 구성 하려는 경우 비즈니스용 [Skype 서버에서 여러 응급 번호 계획](multiple-emergency-numbers.md) 의 정보를 따르고 [비즈니스용 skype에서 여러 응급 번호를 구성](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="d9ce1-107">비즈니스용 Skype 제어판을 사용 하거나 [새로운-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet을 사용 하 여 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="d9ce1-108">자세한 내용은 [비즈니스용 Skype 서버에서 위치 정책 만들기](../../deploy/deploy-enterprise-voice/create-location-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="d9ce1-109">각 위치 정책에는 다음 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="d9ce1-110">**향상 된 9-1-1 사용**</span><span class="sxs-lookup"><span data-stu-id="d9ce1-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="d9ce1-111">이 값을 사용 하도록 설정 하면 클라이언트는 향상 된 응급 서비스 (E9-1-1)에 대해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="d9ce1-112">클라이언트가 등록 되 면 위치 정보 서비스에서 위치를 얻으려고 시도 하 고 비상 전화의 일부로 위치 정보를 포함 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="d9ce1-113">**위치**</span><span class="sxs-lookup"><span data-stu-id="d9ce1-113">**Location**</span></span>
  
<span data-ttu-id="d9ce1-114">이 설정은 **확장 가능 9-1-1 사용** 이 설정 된 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="d9ce1-115">아래와 같이 **위치** 설정을 구성 하 여 클라이언트 동작을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="d9ce1-116">값을 **No** 로 설정 하면 사용자에 게 위치를 묻지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="d9ce1-117">값을 **예/y e s** 로 설정 하면 사용자에 게 위치를 묻는 메시지가 표시 되지만 메시지가 해제 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="d9ce1-118">값을 고로 설정 하면 사용자에 게 위치를 입력 하 라는 메시지가 표시 되 **고, 프롬프트** 를 해제 하려고 할 경우에도 고 지 사항이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="d9ce1-119">모든 경우에 사용자는 계속 해 서 클라이언트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d9ce1-120">E9-1-1에 대해 사용 하도록 설정 하기 전에 사용자가 수동으로 위치를 입력 한 경우에는 고 지 사항 텍스트가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-120">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1.</span></span> <span data-ttu-id="d9ce1-121">부인 내용에 대 한 업데이트는 이미 고 지를 본 사용자가 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-121">Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="d9ce1-122">**향상 된 응급 서비스 책임의 부인**</span><span class="sxs-lookup"><span data-stu-id="d9ce1-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="d9ce1-123">이 설정은 위치에 대 한 프롬프트를 해제할 때 사용자에 게 표시 되는 부인 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="d9ce1-124">비즈니스용 Skype 서버에서 위치 정책을 사용 하 여 로캘에 따라 또는 사용자 집합에 따라 다른 법적 고 지를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="d9ce1-125">**비상 다이얼 문자열 (E9-1-전화 번호)**</span><span class="sxs-lookup"><span data-stu-id="d9ce1-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="d9ce1-126">이 다이얼 문자열 (선행 "+"는 제외 하 고 사용자의 다이얼 플랜에서 표준화를 포함 하 여)는 통화가 비상 통화 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="d9ce1-127">**비상 다이얼 문자열** 을 사용 하면 클라이언트는 전화와 함께 위치 및 콜백 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9ce1-128">조직에서 외부 회선 액세스 접두사를 사용 하지 않는 경우 비즈니스용 Skype Server를 실행 하는 서버에서 아웃 바운드 라우팅에 대 한 통화를 전송 하기 전에 911 문자열에 "+"를 추가 하는 해당 다이얼 플랜 정규화 규칙을 만들 필요가 없습니다. 위치 정책의 결과로 "+"가 비즈니스용 Skype 클라이언트에 의해 자동으로 앞에 놓이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="d9ce1-129">그러나 사이트에서 외부 액세스 접두사를 사용 하는 경우 외부 액세스 접두사를 제거 하 고 "+"를 추가 하는 해당 다이얼 플랜 정책에 정규화 규칙을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="d9ce1-130">예를 들어 위치에 외부 액세스 접두사 9를 사용 하는 경우 사용자가 9 911을 전화 접속 하 여 비상 전화를 거는 경우, 클라이언트는 전화 걸기 계획 정책을 사용 하 여 전화를 건 사람의 위치 프로필에 있는 경로에 따라이 번호를 + 911으로 표준화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="d9ce1-131">**비상 다이얼 문자열 마스크 (E9-1-1 다이얼 마스크)**</span><span class="sxs-lookup"><span data-stu-id="d9ce1-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="d9ce1-132">지정 된 **긴급 전화 걸기 문자열로**번역 된 다이얼 문자열의 세미콜론으로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="d9ce1-133">예를 들어 대부분의 유럽에 대 한 응급 서비스 번호로 112를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="d9ce1-134">유럽의 비즈니스용 Skype 사용자는 911이 미국 긴급 전화 번호 임을 알지 못할 수도 있지만, 112를 사용 하 여 동일한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="d9ce1-135">비상 다이얼 문자열의 경우 각 번호 앞에 "+"를 포함 하지 않으며, 외부 회선 액세스 코드를 사용 하는 경우 사용자의 다이얼 플랜 정책에 정규화 규칙이 있어야 access 코드 자릿수를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="d9ce1-136">**PSTN 사용**</span><span class="sxs-lookup"><span data-stu-id="d9ce1-136">**PSTN usage**</span></span>
  
<span data-ttu-id="d9ce1-137">게이트웨이 비상 전화의 SIP 트렁크, PSTN 게이트웨이 또는 ELIN 결정 하는 라우팅 경로를 포함 하는 PSTN 사용의 이름으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d9ce1-138">위치 정책에는 하나의 사용만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="d9ce1-139">이 PSTN 사용은 사용자의 음성 정책에 할당 된 PSTN 사용량 보다 우선 하지만 비상 다이얼 문자열 또는 비상 다이얼 문자열 마스크 중 하나에 대 한 통화에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="d9ce1-140">**알림 URI**</span><span class="sxs-lookup"><span data-stu-id="d9ce1-140">**Notification URI**</span></span>
  
<span data-ttu-id="d9ce1-141">긴급 통화를 할 때 IM (인스턴트 메시징) 알림을 받는 보안 인력의 하나 이상의 SIP Uri를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-141">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed.</span></span> <span data-ttu-id="d9ce1-142">배포 그룹이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-142">Distribution groups are supported.</span></span>
  
 <span data-ttu-id="d9ce1-143">**컨퍼런스 URI**</span><span class="sxs-lookup"><span data-stu-id="d9ce1-143">**Conference URI**</span></span>
  
<span data-ttu-id="d9ce1-144">비상 전화를 걸 때 conferenced 되는 직접적인 안쪽 전화 걸기 (연결 된) 번호 (일반적으로 보안 데스크 번호)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="d9ce1-145">**컨퍼런스 모드**</span><span class="sxs-lookup"><span data-stu-id="d9ce1-145">**Conference Mode**</span></span>
  
<span data-ttu-id="d9ce1-146">회의 URI가 단방향 또는 양방향 통신을 사용 하 여 긴급 통화에 conferenced 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="d9ce1-147">**위치 새로 고침 간격**</span><span class="sxs-lookup"><span data-stu-id="d9ce1-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="d9ce1-148">위치 정보 서비스에서 위치 업데이트에 대 한 클라이언트 요청 사이의 시간 (시간)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="d9ce1-149">값을 1에서 12 사이의 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="d9ce1-150">기본값은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ce1-150">The default value is 4.</span></span>
  

