---
title: 비즈니스용 Skype 서버의 위치 정책 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 이 항목을 통해 비즈니스용 Skype 서버 2013에서 E9-1-1(Enhanced Emergency Services) 배포에 대한 위치 정책을 계획하는 Enterprise Voice.
ms.openlocfilehash: 3d9c574d18351594d9773f02770e960c993ae401
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101454"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="6a5db-103">비즈니스용 Skype 서버의 위치 정책 계획</span><span class="sxs-lookup"><span data-stu-id="6a5db-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="6a5db-104">이 항목을 통해 비즈니스용 Skype 서버 2013에서 E9-1-1(Enhanced Emergency Services) 배포에 대한 위치 정책을 계획하는 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6a5db-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6a5db-105">비즈니스용 Skype 서버는 이제 클라이언트에 대해 여러 긴급 번호의 구성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="6a5db-106">여러 긴급 번호를 구성하려면 비즈니스용 Skype 서버에서 여러 긴급 번호 계획 및 비즈니스용 [Skype에서](multiple-emergency-numbers.md) 여러 긴급 번호 구성의 정보를 [따라야 합니다.](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="6a5db-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="6a5db-107">비즈니스용 Skype 제어판 또는 [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet을 사용하여 위치 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="6a5db-108">자세한 내용은 비즈니스용 Skype 서버에서 위치 정책 [만들기를 참조하세요.](../../deploy/deploy-enterprise-voice/create-location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6a5db-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="6a5db-109">각 위치 정책에는 다음 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="6a5db-110">**고급 9-1-1 사용**</span><span class="sxs-lookup"><span data-stu-id="6a5db-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="6a5db-111">이 값을 사용하도록 설정하면 클라이언트가 E9-1-1(고급 응급 서비스)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="6a5db-112">클라이언트가 등록하면 위치 정보 서비스에서 위치를 취득하려고 시도하고 위치 정보를 긴급 통화의 일부로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="6a5db-113">**위치**</span><span class="sxs-lookup"><span data-stu-id="6a5db-113">**Location**</span></span>
  
<span data-ttu-id="6a5db-114">이 설정은 고급 **9-1-1** 사용이 설정된 경우만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="6a5db-115">다음과 같이 클라이언트 동작을 정의하도록 **위치** 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="6a5db-116">이 값을 **아니요** 로 지정하면 사용자에게 위치를 입력하라는 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="6a5db-117">반면 **예** 로 지정하면 사용자에게 위치를 입력하라는 해제 가능한 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="6a5db-118">이 값을 **고지 사항** 으로 지정하면 사용자에게 위치를 입력하라는 메시지가 표시되며, 메시지를 해제할 때도 고지 사항이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-118">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="6a5db-119">어느 옵션을 선택해도 사용자는 클라이언트를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-119">In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6a5db-p105">E9-1-1을 사용하도록 설정되기 전에 사용자가 위치를 수동으로 입력한 경우에는 고지 사항 텍스트가 표시되지 않습니다. 고지 사항을 이미 본 사용자에게는 고지 사항 텍스트에 대한 업데이트가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="6a5db-122">**향상된 긴급 서비스 고지 사항**</span><span class="sxs-lookup"><span data-stu-id="6a5db-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="6a5db-123">이 설정은 위치를 입력하라는 메시지를 해제하는 사용자에게 표시되는 고지 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="6a5db-124">비즈니스용 Skype 서버에서 위치 정책을 사용하여 로 로컬 또는 사용자 집합에 대해 서로 다른 고지 조항을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="6a5db-125">**긴급 전화 문자열(E9-1-1 전화 번호)**</span><span class="sxs-lookup"><span data-stu-id="6a5db-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="6a5db-126">이 전화 걸기 문자열(선행 "+"를 포함하지 않지만 사용자의 다이얼 플랜에서 수행한 정규화 포함)은 통화가 긴급 통화라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="6a5db-127">**긴급 전화 문자열** 은 클라이언트가 통화와 함께 위치 및 회신 전화 정보를 포함하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a5db-128">조직에서 외부 라인 액세스 prefix를 사용하지 않는 경우 비즈니스용 Skype 서버를 실행하는 서버에서 아웃바운드 라우팅으로 통화를 보내기 전에 911 문자열에 "+"를 추가하는 해당 다이얼 플랜 정규화 규칙을 만들 필요가 없습니다. 위치 정책의 결과로 비즈니스용 Skype 클라이언트가 "+"를 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="6a5db-129">그러나 사이트에서 외부 액세스 prefix를 사용하는 경우 외부 액세스 prefix를 제거하고 "+"를 추가하는 해당 다이얼 플랜 정책에 정규화 규칙을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="6a5db-130">예를 들어 위치가 외부 액세스 번호 9를 사용하는 경우 사용자가 9 911로 전화를 걸고 긴급 통화를 하는 경우 클라이언트는 전화 걸기 번호가 발신자 위치 프로필의 경로에 의해 평가되기 전에 다이얼 플랜 정책을 사용하여 이 번호를 +911로 정규화합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="6a5db-131">**긴급 전화 문자열 마스크(E9-1-1 다이얼 마스크)**</span><span class="sxs-lookup"><span data-stu-id="6a5db-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="6a5db-132">지정된 **긴급 전화 문자열** 로 변환되는 세미콜론으로 구분된 전화 문자열 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="6a5db-133">예를 들어, 대부분 유럽 지역에서 긴급 서비스 번호로 사용되는 112를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="6a5db-134">유럽의 방문 비즈니스용 Skype 사용자는 911이 미국 응급 번호인지 모를 수 있지만 112로 전화를 걸고 동일한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="6a5db-135">긴급 전화 문자열과 함께 각 번호 앞에 "+"를 포함하지 말고, 외부 라인 액세스 코드를 사용하는 경우 사용자의 다이얼 플랜 정책에 액세스 코드 숫자를 제거하기 위한 정규화 규칙이 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a5db-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="6a5db-136">**PSTN 사용**</span><span class="sxs-lookup"><span data-stu-id="6a5db-136">**PSTN usage**</span></span>
  
<span data-ttu-id="6a5db-137">SIP 트렁크, PSTN 게이트웨이 또는 ELIN 게이트웨이 긴급 전화가 연결될 위치를 결정하는 라우팅 경로를 포함하는 PSTN 사용 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a5db-138">위치 정책에 하나의 사용만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="6a5db-139">이 PSTN 사용은 사용자의 음성 정책에 할당된 PSTN 사용에 대해 재지정되지만 긴급 전화 문자열 또는 긴급 전화 문자열 마스크 중 하나에 걸려 있는 통화에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="6a5db-140">**알림 URI**</span><span class="sxs-lookup"><span data-stu-id="6a5db-140">**Notification URI**</span></span>
  
<span data-ttu-id="6a5db-p111">긴급 전화가 걸려올 때 IM(인스턴트 메시징) 알림을 수신할 보안 담당자의 SIP URI를 하나 이상 지정합니다. 메일 그룹이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="6a5db-143">**회의 URI**</span><span class="sxs-lookup"><span data-stu-id="6a5db-143">**Conference URI**</span></span>
  
<span data-ttu-id="6a5db-144">긴급 전화가 걸려올 때 회의를 열어야 하는 DID(자동 착신) 번호(일반적으로 보안 데스크 번호)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="6a5db-145">**전화 회의 모드**</span><span class="sxs-lookup"><span data-stu-id="6a5db-145">**Conference Mode**</span></span>
  
<span data-ttu-id="6a5db-146">회의 URI가 단방향 또는 양방향 통신을 사용하여 긴급 전화에 참가하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="6a5db-147">**위치 새로 고침 간격(Location Refresh Interval)**</span><span class="sxs-lookup"><span data-stu-id="6a5db-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="6a5db-148">위치 정보 서비스에서 위치 업데이트를 요청하는 클라이언트 요청 사이의 시간(시간)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="6a5db-149">이 값은 1에서 12 사이의 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="6a5db-150">기본값은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="6a5db-150">The default value is 4.</span></span>
