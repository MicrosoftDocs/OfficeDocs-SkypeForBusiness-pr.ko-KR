---
title: 'Lync Server 2013: 위치 정책 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the location policy
ms:assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398962(v=OCS.15)
ms:contentKeyID: 48185553
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bdb3b556f5b9a8d552a3c48e300b8c4b7b19f5f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504525"
---
# <a name="defining-the-location-policy-for-lync-server-2013"></a><span data-ttu-id="12afa-102">Lync Server 2013에 대 한 위치 정책 정의</span><span class="sxs-lookup"><span data-stu-id="12afa-102">Defining the location policy for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12afa-103">_**마지막으로 수정 된 항목:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="12afa-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="12afa-104">각 위치 정책에는 다음 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-104">Each location policy contains the following information:</span></span>

  - <span data-ttu-id="12afa-105">**긴급 서비스 사용**</span><span class="sxs-lookup"><span data-stu-id="12afa-105">**Emergency Services Enabled**</span></span>  
    <span data-ttu-id="12afa-106">이 값이 **예**인 경우 클라이언트가 E9-1-1을 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-106">When this value is **Yes**, the client is enabled for E9-1-1.</span></span> <span data-ttu-id="12afa-107">클라이언트가 등록 되 면 위치 정보 서비스에서 위치를 얻으려고 시도 하 고 비상 통화의 일부로 위치 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-107">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>

<!-- end list -->

  - <span data-ttu-id="12afa-108">**위치 필요**</span><span class="sxs-lookup"><span data-stu-id="12afa-108">**Location Required**</span></span>  
    <span data-ttu-id="12afa-109">이 설정은 **긴급 서비스 사용**   이 **예/y e s**로 설정 된 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-109">This setting is used only when **Emergence Services Enabled** is set to **Yes**.</span></span>
    
    <span data-ttu-id="12afa-p102">**위치 필요** 설정을 구성하여 클라이언트 동작을 정의할 수 있습니다. 이 값을 **아니요**로 지정하면 사용자에게 위치를 입력하라는 메시지가 표시되지 않습니다. 반면 **예**로 지정하면 사용자에게 위치를 입력하라는 해제 가능한 메시지가 표시됩니다. 이 값을 **고지 사항**으로 지정하면 사용자에게 위치를 입력하라는 메시지가 표시되며, 메시지를 해제할 때도 고지 사항이 표시됩니다. 어느 옵션을 선택해도 사용자는 클라이언트를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-p102">You can configure the **Location Required** setting to define the client behavior. Setting the value to **No** means that the user will not be prompted for a location. Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt. Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12afa-p103">E9-1-1을 사용하도록 설정되기 전에 사용자가 위치를 수동으로 입력한 경우에는 고지 사항 텍스트가 표시되지 않습니다. 고지 사항을 이미 본 사용자에게는 고지 사항 텍스트에 대한 업데이트가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-p103">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="12afa-117">**향상된 긴급 서비스 고지 사항**</span><span class="sxs-lookup"><span data-stu-id="12afa-117">**Enhanced Emergency Service Disclaimer**</span></span>  
    <span data-ttu-id="12afa-118">이 설정은 위치를 입력하라는 메시지를 해제하는 사용자에게 표시되는 고지 사항을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-118">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="12afa-119">Lync Server 2013에서는 위치 정책을 사용 하 여 서로 다른 로캘 또는 다른 사용자 집합에 대 한 다른 법적 고 지를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-119">In Lync Server 2013, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12afa-120">이 위치 정책 설정은 <STRONG>CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet을 사용 하 여 전체 조직에 대 한 전역 고 지 사항을 설정한 Lync Server 2010와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-120">This location policy setting differs from Lync Server 2010, where you used the <STRONG>Set-CsEnhancedEmergencyServiceDisclaimer</STRONG> cmdlet to set a global disclaimer for the entire organization.</span></span> <span data-ttu-id="12afa-121">전역 고 지 사항이 이미 있는 경우에는 위치 정책에서 고 지 사항을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-121">If a global disclaimer already exists, you need to specify that disclaimer in location policy.</span></span> <span data-ttu-id="12afa-122">즉, Lync Server 2013에서는 위치 정책에 지정 된 부인만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-122">That is, Lync Server 2013 uses only disclaimers specified in location policy.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="12afa-123">**긴급 전화 문자열**</span><span class="sxs-lookup"><span data-stu-id="12afa-123">**Emergency Dial String**</span></span>  
    <span data-ttu-id="12afa-p106">이 전화 문자열(선행 “+”를 제외하며 Lync 사용자의 다이얼 플랜에서 수행된 정규화 포함)은 통화가 긴급 전화임을 나타냅니다. **긴급 전화 문자열**은 클라이언트가 통화와 함께 위치 및 회신 전화 정보를 포함하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-p106">This dial string (less the leading “+”, but including any normalization done by the Lync user’s Dial Plan) signifies that a call is an emergency call. The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12afa-126">조직에서 외부 회선 액세스 접두사를 사용 하지 않는 경우 Lync 풀 서버의 아웃 바운드 라우팅에 대 한 호출을 보내기 전에 911 문자열에 "+"를 추가 하는 해당 다이얼 플랜 정규화 규칙을 만들 필요가 없습니다. 위치 정책의 결과로 Lync 클라이언트에서 "+"가 자동으로 앞에 놓이게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-126">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a “+” to the 911 string prior to sending the call to Outbound Routing on a Lync pool server; the “+” will be automatically prepended by the Lync client as a result of the location policy.</span></span> <span data-ttu-id="12afa-127">그러나 사이트에서 외부 액세스 접두사를 사용 하는 경우에는 외부 액세스 접두사를 제거 하 고 "+"를 추가 하는 해당 다이얼 플랜 정책에 정규화 규칙을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-127">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the “+”.</span></span> <span data-ttu-id="12afa-128">예를 들어 위치에서 외부 액세스 접두사 9를 사용 하 고 사용자가 응급 통화를 시작 하기 위해 9 911을 전화를 걸고 있으면 &nbsp; 클라이언트는 전화 걸기 번호를 사용 하 여이를 + 911로 정규화 한 후 발신자의 위치 프로필에 있는 경로에 의해이 번호가 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-128">For example, if your location uses an external access prefix of 9 and a user dials 9&nbsp;911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller’s location profile.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="12afa-129">**긴급 전화 문자열 마스크**</span><span class="sxs-lookup"><span data-stu-id="12afa-129">**Emergency Dial String Masks**</span></span>  
    <span data-ttu-id="12afa-p108">지정된 **긴급 전화 문자열**로 변환되는 세미콜론으로 구분된 전화 문자열 목록입니다. 예를 들어, 대부분 유럽 지역에서 긴급 서비스 번호로 사용되는 112를 추가할 수 있습니다. 유럽에서 방문하는 Lync 사용자가 911이 미국의 긴급 번호라는 사실을 모르고 112로 전화를 걸어도 긴급 서비스에 연결됩니다. 긴급 전화 문자열과 마찬가지로, 각 번호 앞에 "+"를 포함하지 않으며 외부 회선 액세스 코드를 사용하는 경우 사용자의 다이얼 플랜 정책에 액세스 코드 숫자를 제거하는 정규화 규칙이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-p108">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**. For example, you may want to add 112, which is the emergency service number for most of Europe. A visiting Lync user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result. As with the Emergency Dial String, do not include a “+” before each number, and if you use external line access codes, be sure there are normalization rules in the user’s Dial Plan policy to strip off the access code digit.</span></span>

<!-- end list -->

  - <span data-ttu-id="12afa-134">**PSTN 사용**</span><span class="sxs-lookup"><span data-stu-id="12afa-134">**PSTN Usage**</span></span>  
    <span data-ttu-id="12afa-135">SIP 트렁크, PSTN 게이트웨이 또는 ELIN 게이트웨이 긴급 전화가 연결될 위치를 결정하는 라우팅 경로를 포함하는 PSTN 사용 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-135">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12afa-p109">위치 정책에 하나의 사용만 할당할 수 있습니다. 이 PSTN 사용은 사용자의 음성 정책에 할당된 PSTN 사용을 재정의하지만, 긴급 전화 문자열이나 긴급 전화 문자열 마스크 중 하나로 건 통화에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-p109">Only one usage can be assigned to a location policy. This PSTN Usage overrides the PSTN Usages assigned to the user’s voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span>

    
    </div>

<!-- end list -->

  - <span data-ttu-id="12afa-138">**알림 URI**</span><span class="sxs-lookup"><span data-stu-id="12afa-138">**Notification URI**</span></span>  
    <span data-ttu-id="12afa-p110">긴급 전화가 걸려올 때 IM(인스턴트 메시징) 알림을 수신할 보안 담당자의 SIP URI를 하나 이상 지정합니다. 메일 그룹이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-p110">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>

<!-- end list -->

  - <span data-ttu-id="12afa-141">**회의 URI**</span><span class="sxs-lookup"><span data-stu-id="12afa-141">**Conference URI**</span></span>  
    <span data-ttu-id="12afa-142">긴급 전화가 걸려올 때 회의를 열어야 하는 DID(자동 착신) 번호(일반적으로 보안 데스크 번호)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-142">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span>

<!-- end list -->

  - <span data-ttu-id="12afa-143">**전화 회의 모드**</span><span class="sxs-lookup"><span data-stu-id="12afa-143">**Conference Mode**</span></span>  
    <span data-ttu-id="12afa-144">회의 URI가 단방향 또는 양방향 통신을 사용하여 긴급 전화에 참가하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-144">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span>

<!-- end list -->

  - <span data-ttu-id="12afa-145">**위치 새로 고침 간격(Location Refresh Interval)**</span><span class="sxs-lookup"><span data-stu-id="12afa-145">**Location Refresh Interval**</span></span>  
    <span data-ttu-id="12afa-146">위치 정보 서비스에서 위치 업데이트에 대 한 클라이언트 요청 간 시간 (시간)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-146">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="12afa-147">이 값은 1에서 12 사이의 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-147">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="12afa-148">기본값은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="12afa-148">The default value is 4.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

