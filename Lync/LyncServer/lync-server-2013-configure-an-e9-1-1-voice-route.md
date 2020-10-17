---
title: 'Lync Server 2013: E9-1-1 음성 경로 구성'
description: 'Lync Server 2013: E9-1-1 음성 경로를 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 869e9eaeb454943ccd877e90a21461c73065873e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546734"
---
# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a><span data-ttu-id="e7acb-103">Lync Server 2013에서 E9-1-1 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="e7acb-103">Configure an E9-1-1 voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7acb-104">_**마지막으로 수정 된 항목:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="e7acb-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="e7acb-105">E9-1-1을 배포 하려면 먼저 긴급 통화 음성 경로를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="e7acb-106">음성 경로를 만드는 방법에 대 한 자세한 내용은 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7acb-106">For details about creating voice routes, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span> <span data-ttu-id="e7acb-107">예를 들어 배포에 기본 SIP 트렁크와 보조 SIP 트렁크가 포함 되어 있는 경우 둘 이상의 경로를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7acb-108">E9-1-1 초대에 위치 정보를 포함 하려면 E9-1-1 서비스 공급자에 연결 하는 SIP 트렁크를 구성 해야 게이트웨이를 통해 긴급 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="e7acb-109">이 작업을 수행 하려면 <STRONG>get-cstrunkconfiguration</STRONG> Cmdlet에서 EnablePIDFLOSupport 플래그를 True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-109">To do this, set the EnablePIDFLOSupport flag on the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to True.</span></span> <span data-ttu-id="e7acb-110">EnablePIDFLOSupport의 기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="e7acb-111">예를 들어: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span><span class="sxs-lookup"><span data-stu-id="e7acb-111">For example: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span></span><BR><span data-ttu-id="e7acb-112">대체 PSTN (공중 전화망) 게이트웨이 및 비상 위치 식별 번호 (ELIN) 게이트웨이에 대 한 수신 위치를 사용 하도록 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-112">It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>



</div>

<span data-ttu-id="e7acb-113">음성 경로를 사용 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7acb-113">For details about working with voice routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="e7acb-114">**설정-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="e7acb-114">**Set-CsPstnUsage**</span></span>

  - <span data-ttu-id="e7acb-115">**G-CsPstnUsage 사용**</span><span class="sxs-lookup"><span data-stu-id="e7acb-115">**Get-CsPstnUsage**</span></span>

  - <span data-ttu-id="e7acb-116">**Get-csvoiceroute**</span><span class="sxs-lookup"><span data-stu-id="e7acb-116">**New-CsVoiceRoute**</span></span>

  - <span data-ttu-id="e7acb-117">**Get-csvoiceroute**</span><span class="sxs-lookup"><span data-stu-id="e7acb-117">**Get-CsVoiceRoute**</span></span>

  - <span data-ttu-id="e7acb-118">**Get-csvoiceroute**</span><span class="sxs-lookup"><span data-stu-id="e7acb-118">**Set-CsVoiceRoute**</span></span>

  - <span data-ttu-id="e7acb-119">**Get-csvoiceroute을 제거 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e7acb-119">**Remove-CsVoiceRoute**</span></span>

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="e7acb-120">E9-1-1 음성 경로를 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="e7acb-120">To configure an E9-1-1 voice route</span></span>

1.  <span data-ttu-id="e7acb-121">RTCUniversalServerAdmins 그룹의 구성원 이거나 CsVoiceAdministrator 관리 역할의 구성원 인 계정을 사용 하 여 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-121">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>

2.  <span data-ttu-id="e7acb-122">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e7acb-123">다음 cmdlet를 실행 하 여 새 PSTN 사용 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-123">Run the following cmdlet to create a new PSTN usage record.</span></span>
    
    <span data-ttu-id="e7acb-124">이 이름은 위치 정책의 **PSTN** 설정에 사용 하는 것과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-124">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="e7acb-125">배포에는 여러 전화 사용 레코드가 포함 되지만, 다음 예에서는 사용 가능한 PSTN 사용법의 현재 목록에 "응급 사용"을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-125">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="e7acb-126">자세한 내용은 [Lync Server 2013의 통화 기능 및 권한을 부여 하도록 음성 정책 및 PSTN 사용 레코드 구성을](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e7acb-126">For details, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  <span data-ttu-id="e7acb-127">다음 cmdlet를 실행 하 여 이전 단계에서 만든 PSTN 사용 레코드를 사용 하 여 새 음성 경로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-127">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="e7acb-128">번호 패턴은 위치 정책의 **비상 다이얼 문자열** 설정에 사용 되는 번호 패턴을 동일 하 게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-128">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="e7acb-129">Lync가 긴급 통화에 "+"를 추가 하기 때문에 "+" 부호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-129">A "+" sign is needed because Lync adds "+" to emergency calls.</span></span> <span data-ttu-id="e7acb-130">"Co1-1"은 E9-1-1 서비스 공급자 또는 ELIN 게이트웨이 서비스 ID에 대 한 SIP 트렁크 서비스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-130">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="e7acb-131">다음 예에서는 "EmergencyRoute"을 음성 경로의 이름으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-131">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  <span data-ttu-id="e7acb-132">SIP 트렁크 연결의 경우에는 다음 cmdlet를 실행 하 여 E9-1-1 서비스 공급자의 SIP 트렁크에서 처리 하지 않는 통화에 대 한 로컬 경로를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-132">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider’s SIP trunk.</span></span> <span data-ttu-id="e7acb-133">E9-1-1 서비스 공급자에 대 한 연결을 사용할 수 없는 경우이 경로가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-133">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span>
    
    <span data-ttu-id="e7acb-134">다음 예제에서는 사용자의 음성 정책에 "Local" 사용이 있음을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7acb-134">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

