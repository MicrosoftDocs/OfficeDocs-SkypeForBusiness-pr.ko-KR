---
title: 'Lync Server 2013: 음성 정책'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Voice policies
ms:assetid: b7433c62-9d8c-48af-89a0-19f0d34806ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412891(v=OCS.15)
ms:contentKeyID: 48185223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 769524594496598581814462dcf8f6827d3c2616
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42120471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a><span data-ttu-id="0599b-102">Lync Server 2013의 음성 정책</span><span class="sxs-lookup"><span data-stu-id="0599b-102">Voice policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0599b-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0599b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0599b-104">Lync Server *음성 정책은* 정책이 할당 된 각 사용자, 사이트 또는 조직에 대해 다음을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-104">Lync Server *voice policies* define the following for each user, site, or organization that is assigned the policy:</span></span>

  - <span data-ttu-id="0599b-105">사용 하거나 사용 하지 않도록 설정할 수 있는 호출 기능 집합으로, 사용자가 사용할 수 있는 Enterprise Voice 기능을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-105">A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.</span></span>

  - <span data-ttu-id="0599b-106">승인할 통화 유형을 정의하는 PSTN(공중 전화망) 사용 레코드 집합</span><span class="sxs-lookup"><span data-stu-id="0599b-106">A set of public switched telephone network (PSTN) usage records that define what types of calls are authorized.</span></span>

<div>

## <a name="planning-for-voice-policies"></a><span data-ttu-id="0599b-107">음성 정책 계획</span><span class="sxs-lookup"><span data-stu-id="0599b-107">Planning for Voice Policies</span></span>

<span data-ttu-id="0599b-108">다음 단계는 Enterprise Voice 배포에 필요한 음성 정책을 계획 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-108">The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:</span></span>

  - <span data-ttu-id="0599b-109">전역 음성 정책(제품과 함께 설치되는 기본 음성 정책)을 구성할 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-109">Determine how you will configure your global voice policy (the default voice policy that is installed with the product).</span></span> <span data-ttu-id="0599b-110">이 정책은 사이트 수준 또는 사용자별 정책을 명시적으로 할당 받지 않은 모든 Enterprise 음성 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-110">This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.</span></span>

  - <span data-ttu-id="0599b-111">필요한 사이트 수준 음성 정책을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-111">Identify any site-level voice policies that you might need.</span></span>

  - <span data-ttu-id="0599b-112">필요한 사용자별 음성 정책을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-112">Identify any per-user voice policies that you might need.</span></span>

  - <span data-ttu-id="0599b-113">각 음성 정책에 대해 사용하도록 설정할 통화 기능을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-113">Decide which call features to enable for each voice policy.</span></span>

  - <span data-ttu-id="0599b-114">각 음성 정책에 대해 구성할 PSTN 사용 레코드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-114">Determine what PSTN usage records to configure for each voice policy.</span></span>

<div>

## <a name="voice-policy-scope"></a><span data-ttu-id="0599b-115">음성 정책 범위</span><span class="sxs-lookup"><span data-stu-id="0599b-115">Voice Policy Scope</span></span>

<span data-ttu-id="0599b-116">*음성 정책 범위*는 정책을 적용할 수 있는 계층 수준을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-116">*Voice policy scope* determines the hierarchical level at which the policy can be applied.</span></span> <span data-ttu-id="0599b-117">Lync Server에서는 다음과 같은 범위 수준 (가장 구체적인 것부터 가장 일반적인 것으로 나열 됨)을 사용 하 여 음성 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-117">In Lync Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).</span></span>

  - <span data-ttu-id="0599b-p103">**사용자 음성 정책**은 개별 사용자, 그룹 또는 연락처 개체에 할당할 수 있습니다. 최하위 수준의 정책입니다. 사용자 음성 정책을 배포하여 사이트의 특정 사용자 또는 그룹에 대해서만 기능을 허용할 수 있습니다. 예를 들어 일부 직원에 대해 시외 전화를 걸지 못하게 설정할 수 있습니다. 음성 정책을 할당하기 위해 연락처 개체는 개별 사용자로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-p103">**User voice policy** can be assigned to individual users, groups, or contact objects. This is the lowest level policy. User voice policies can be deployed to enable features for certain users or groups at a site, but not for others in the same site. For example, you may want to disable long distance dialing for some employees. For the purpose of assigning a voice policy, a contact object is treated as an individual user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0599b-123">중앙 사이트 배포에 등록 된 분기 사이트 Enterprise Voice 사용자 또는 Sba (survivable Branch 기기에 등록 된 사용자에 대 한 사용자 음성 정책을 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-123">We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance.</span></span>

    
    </div>

  - <span data-ttu-id="0599b-p104">**사이트 음성 정책**은 사용자 음성 정책이 할당된 사용자, 그룹 또는 연락처 개체를 제외한 전체 사이트에 적용됩니다. 사이트 음성 정책을 정의하려면 정책을 적용할 사이트를 지정해야 합니다. 사용자 음성 정책이 할당되지 않은 경우 사이트 음성 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-p104">**Site voice policy** applies to an entire site, except for any users, groups, or contact objects that are assigned a user voice policy. To define a site voice policy, you must specify the site to which the policy applies. If a user voice policy is not assigned, the site voice policy is used.</span></span>

  - <span data-ttu-id="0599b-127">**전역 음성 정책**은 제품과 함께 설치되는 기본 음성 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-127">**Global voice policy** is the default voice policy that is installed with the product.</span></span> <span data-ttu-id="0599b-128">조직의 특정 요구 사항에 맞게 전역 음성 정책을 편집할 수 있지만 이름을 변경하거나 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-128">You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it.</span></span> <span data-ttu-id="0599b-129">이 음성 정책은 더 구체적인 범위를 사용 하 여 음성 정책을 구성 및 할당 하지 않는 한 배포의 모든 Enterprise Voice 사용자, 그룹 및 연락처 개체에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-129">This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope.</span></span> <span data-ttu-id="0599b-130">이 정책을 완전히 사용하지 않도록 설정하려면 모든 사이트 및 사용자에게 사용자 지정 정책이 할당되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="0599b-130">If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.</span></span>

</div>

<div>

## <a name="call-features"></a><span data-ttu-id="0599b-131">통화 기능</span><span class="sxs-lookup"><span data-stu-id="0599b-131">Call Features</span></span>

<span data-ttu-id="0599b-132">각 음성 정책에 대해 다음과 같은 통화 기능을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-132">You can enable or disable the following call features for each voice policy:</span></span>

  - <span data-ttu-id="0599b-p106">**착신 전환** - 통화를 다른 전화 및 클라이언트 장치로 전달할 수 있습니다. 이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-p106">**Call forwarding** enables users to forward calls to other phones and client devices. Enabled by default.</span></span>

  - <span data-ttu-id="0599b-p107">**위임** - 자신을 대신해 전화를 걸거나 받을 다른 사용자를 지정할 수 있습니다. 이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-p107">**Delegation** enables users to specify other users to send and receive calls on their behalf. Enabled by default.</span></span>

  - <span data-ttu-id="0599b-p108">**통화 전송** - 통화를 다른 사람에게 전송할 수 있습니다. 이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>

  - <span data-ttu-id="0599b-p109">**통화 대기**는 사용자가 통화를 대기시킨 다음 다른 전화 또는 클라이언트에서 전화를 받는 데 사용됩니다. 이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-p109">**Call park** enables users to park calls and then pick up the call from a different phone or client. Disabled by default.</span></span>

  - <span data-ttu-id="0599b-p110">**동시 전화 신호 울림**은 전화가 올 때 다른 전화(예: 휴대폰) 또는 다른 끝점 장치에서 전화 신호가 울리도록 하는 데 사용됩니다. 이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-p110">**Simultaneous ringing** enables incoming calls to ring on an additional phone (for example, a mobile phone) or other endpoint devices. Enabled by default.</span></span>

  - <span data-ttu-id="0599b-p111">**팀 호출** - 정의된 팀의 사용자가 팀의 다른 구성원에 대한 통화에 응답할 수 있습니다. 이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>

  - <span data-ttu-id="0599b-p112">**PSTN 경로 조정**은 WAN이 지체되거나 사용할 수 없는 경우 이 정책이 할당된 사용자가 다른 엔터프라이즈 사용자에게 건 전화를 PSTN(공중 전화망)에서 경로 조정하는 데 사용됩니다. 이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-p112">**PSTN reroute** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>

  - <span data-ttu-id="0599b-p113">**대역폭 정책 무시**는 관리자가 특정 사용자의 통화 허용 제어 정책 결정을 무시하는 데 사용됩니다. 이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>

  - <span data-ttu-id="0599b-149">**악의적인 통화 추적** 을 사용 하면 사용자가 Lync 클라이언트를 사용 하 여 악의적인 통화를 보고 한 다음 통화 정보 기록에서 이러한 호출에 플래그를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-149">**Malicious call tracing** enables users to report malicious calls by using the Lync client, and then flags such calls in the call detail records.</span></span> <span data-ttu-id="0599b-150">이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-150">Disabled by default.</span></span>

  - <span data-ttu-id="0599b-151">**음성 메일 이스케이프**는 동시 전화 신호 울림이 구성된 상태에서 전화기가 꺼져 있거나, 배터리가 방전되거나, 망 범위를 벗어난 경우 통화가 사용자의 휴대폰 음성 메일 시스템으로 즉시 라우팅되지 않도록 하며 타이머 값을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-151">**Voicemail escape** prevents calls from being immediately routed to the user’s mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value.</span></span> <span data-ttu-id="0599b-152">이 설정은 타이머를 사용하거나 사용하지 않도록 설정하며 타이머 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-152">This setting enables and disables the timer and sets the value of the timer.</span></span> <span data-ttu-id="0599b-153">Lync Server 관리 셸을 사용 해야만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-153">It can be configured only by using the Lync Server Management Shell.</span></span> <span data-ttu-id="0599b-154">이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-154">Disabled by default.</span></span>

  - <span data-ttu-id="0599b-p116">**착신 전환 및 동시 전화 신호 울림 PSTN 사용**은 착신 전환과 동시 전화 신호 울림에 대한 음성 정책으로 동일한 PSTN 사용을 지정하거나, 착신 전환 및 동시 전화 신호 울림을 내부 Lync 사용자로 제한하거나, 음성 정책의 PSTN 사용과 다른 사용자 지정 PSTN 사용을 지정하는 데 사용됩니다. 기본값은 착신 전환과 동시 전화 신호 울림에 대한 음성 정책으로 동일한 PSTN 사용을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-p116">**Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Lync users only, or specify a custom PSTN usage that is different from the voice policy’s PSTN usage. The default is to use the same PSTN usage as the voice policy for call forwarding and simultaneous ringing.</span></span>

</div>

<div>

## <a name="pstn-usage-records"></a><span data-ttu-id="0599b-157">PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="0599b-157">PSTN Usage Records</span></span>

<span data-ttu-id="0599b-158">각 음성 정책에는 연결된 PSTN 사용 레코드가 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-158">Each voice policy should have one or more associated PSTN usage records.</span></span> <span data-ttu-id="0599b-159">PSTN 사용은 동시 전화 신호 울림 및 착신 전환 용도로만 음성 정책과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-159">PSTN usages can be associated with a voice policy for the purpose of simultaneous ringing and call forwarding only.</span></span> <span data-ttu-id="0599b-160">PSTN 사용 레코드를 계획 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 PSTN 사용 레코드](lync-server-2013-pstn-usage-records.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0599b-160">For details about planning PSTN usage records, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0599b-p118">사용자를 경로에 일치시킬 때 아웃바운드 라우팅 기능이 PSTN 사용을 위에서 아래로 비교하므로 PSTN 사용 순서가 중요합니다. 첫 번째 사용이 통화 경로와 일치하면 해당 경로가 사용됩니다. 그렇지 않은 경우 아웃바운드 라우팅 기능이 목록에서 다음 PSTN 사용을 보고 일치 항목이 발견될 때까지 계속 비교합니다. 목록에 첫 번째 사용이 없는 경우 이후 PSTN 사용이 백업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0599b-p118">PSTN usage order is critical because in matching users to routes, the outbound routing functionality compares PSTN usages from top to bottom. If the first usage matches the call route, that route is used. If not, the outbound routing functionality looks at the next PSTN usage on the list and continues until a match is found. In effect, the subsequent PSTN usages provide backup if the first one on the list is unavailable.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

