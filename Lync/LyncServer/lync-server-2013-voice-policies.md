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
ms.openlocfilehash: 3998bd6f879b20b1a22f46818a22f26bbb2cc29a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-policies-in-lync-server-2013"></a><span data-ttu-id="9d246-102">Lync Server 2013의 음성 정책</span><span class="sxs-lookup"><span data-stu-id="9d246-102">Voice policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d246-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9d246-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9d246-104">Lync Server *음성 정책은* 정책이 할당 된 각 사용자, 사이트 또는 조직에 대해 다음을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-104">Lync Server *voice policies* define the following for each user, site, or organization that is assigned the policy:</span></span>

  - <span data-ttu-id="9d246-105">사용자가 사용할 수 있는 엔터프라이즈 음성 기능을 결정 하기 위해 사용 하거나 사용 하지 않도록 설정할 수 있는 통화 기능 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-105">A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.</span></span>

  - <span data-ttu-id="9d246-106">권한 있는 통화 유형을 정의 하는 공공 PSTN (교환 통신망) 사용 레코드 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-106">A set of public switched telephone network (PSTN) usage records that define what types of calls are authorized.</span></span>

<div>

## <a name="planning-for-voice-policies"></a><span data-ttu-id="9d246-107">음성 정책 계획</span><span class="sxs-lookup"><span data-stu-id="9d246-107">Planning for Voice Policies</span></span>

<span data-ttu-id="9d246-108">다음 단계는 엔터프라이즈 음성 배포에 필요한 음성 정책을 계획 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-108">The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:</span></span>

  - <span data-ttu-id="9d246-109">전역 음성 정책 (제품과 함께 설치 된 기본 음성 정책)을 구성 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-109">Determine how you will configure your global voice policy (the default voice policy that is installed with the product).</span></span> <span data-ttu-id="9d246-110">이 정책은 사이트 수준 또는 사용자 단위 정책을 명시적으로 할당 하지 않은 모든 Enterprise Voice 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-110">This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.</span></span>

  - <span data-ttu-id="9d246-111">필요할 수 있는 사이트 수준의 음성 정책을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-111">Identify any site-level voice policies that you might need.</span></span>

  - <span data-ttu-id="9d246-112">필요할 수 있는 사용자 단위 음성 정책을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-112">Identify any per-user voice policies that you might need.</span></span>

  - <span data-ttu-id="9d246-113">각 음성 정책에 사용할 전화 기능을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-113">Decide which call features to enable for each voice policy.</span></span>

  - <span data-ttu-id="9d246-114">각 음성 정책에 대해 구성할 PSTN 사용 레코드를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-114">Determine what PSTN usage records to configure for each voice policy.</span></span>

<div>

## <a name="voice-policy-scope"></a><span data-ttu-id="9d246-115">음성 정책 범위</span><span class="sxs-lookup"><span data-stu-id="9d246-115">Voice Policy Scope</span></span>

<span data-ttu-id="9d246-116">*음성 정책 범위* 는 정책을 적용할 수 있는 계층 수준을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-116">*Voice policy scope* determines the hierarchical level at which the policy can be applied.</span></span> <span data-ttu-id="9d246-117">Lync Server에서는 다음 범위 수준을 사용 하 여 음성 정책을 구성할 수 있습니다 (가장 구체적인 방법에서 가장 일반적인 것부터 나열).</span><span class="sxs-lookup"><span data-stu-id="9d246-117">In Lync Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).</span></span>

  - <span data-ttu-id="9d246-118">**사용자 음성 정책은** 개인 사용자, 그룹 또는 연락처 개체에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-118">**User voice policy** can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="9d246-119">가장 낮은 수준의 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-119">This is the lowest level policy.</span></span> <span data-ttu-id="9d246-120">사이트에서 특정 사용자 또는 그룹에 대 한 기능을 사용 하도록 설정할 수 있지만, 같은 사이트에 있는 다른 사람에 게는 해당 정책이 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-120">User voice policies can be deployed to enable features for certain users or groups at a site, but not for others in the same site.</span></span> <span data-ttu-id="9d246-121">예를 들어 일부 직원에 대해 시외 전화 걸기를 사용 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-121">For example, you may want to disable long distance dialing for some employees.</span></span> <span data-ttu-id="9d246-122">음성 정책을 할당 하기 위해 연락처 개체는 개별 사용자로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-122">For the purpose of assigning a voice policy, a contact object is treated as an individual user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9d246-123">중앙 사이트 배포에 등록 된 지점 사이트 Enterprise Voice 사용자 또는 Survivable Branch 기기에 등록 된 사용자에 대해 사용자 음성 정책을 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-123">We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance.</span></span>

    
    </div>

  - <span data-ttu-id="9d246-124">**사이트 음성 정책은** 사용자 음성 정책이 할당 된 사용자, 그룹 또는 연락처 개체를 제외한 전체 사이트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-124">**Site voice policy** applies to an entire site, except for any users, groups, or contact objects that are assigned a user voice policy.</span></span> <span data-ttu-id="9d246-125">사이트 음성 정책을 정의 하려면 정책이 적용 되는 사이트를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-125">To define a site voice policy, you must specify the site to which the policy applies.</span></span> <span data-ttu-id="9d246-126">사용자 음성 정책이 할당 되지 않으면 사이트 음성 정책이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-126">If a user voice policy is not assigned, the site voice policy is used.</span></span>

  - <span data-ttu-id="9d246-127">**전역 음성 정책은** 제품과 함께 설치 되는 기본 음성 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-127">**Global voice policy** is the default voice policy that is installed with the product.</span></span> <span data-ttu-id="9d246-128">조직의 특정 요구 사항에 맞게 전역 음성 정책을 편집할 수 있지만 이름을 바꾸거나 삭제할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-128">You can edit the global voice policy to meet the specific needs of your organization, but you cannot rename or delete it.</span></span> <span data-ttu-id="9d246-129">이 음성 정책은 더 구체적인 범위를 사용 하 여 음성 정책을 구성 하 고 할당 하지 않는 한 배포의 모든 Enterprise Voice 사용자, 그룹 및 연락처 개체에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-129">This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope.</span></span> <span data-ttu-id="9d246-130">이 정책을 완전히 사용 하지 않으려면 모든 사이트와 사용자에 게 사용자 지정 정책이 할당 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-130">If you want to disable this policy entirely, be sure that all sites and users have custom policies assigned to them.</span></span>

</div>

<div>

## <a name="call-features"></a><span data-ttu-id="9d246-131">통화 기능</span><span class="sxs-lookup"><span data-stu-id="9d246-131">Call Features</span></span>

<span data-ttu-id="9d246-132">각 음성 정책에 대해 다음 통화 기능을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-132">You can enable or disable the following call features for each voice policy:</span></span>

  - <span data-ttu-id="9d246-133">**착신 통화 전환** 기능을 통해 사용자는 다른 전화 및 클라이언트 장치로 전화를 착신 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-133">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="9d246-134">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-134">Enabled by default.</span></span>

  - <span data-ttu-id="9d246-135">**위임을** 통해 사용자는 다른 사용자가 대신 전화를 보내고 받을 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-135">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="9d246-136">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-136">Enabled by default.</span></span>

  - <span data-ttu-id="9d246-137">**통화 전송을** 통해 사용자는 통화를 다른 사용자에 게 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-137">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="9d246-138">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-138">Enabled by default.</span></span>

  - <span data-ttu-id="9d246-139">**통화** 대기 전화를 통해 사용자는 전화를 걸고 다른 휴대폰 또는 클라이언트에서 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-139">**Call park** enables users to park calls and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="9d246-140">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-140">Disabled by default.</span></span>

  - <span data-ttu-id="9d246-141">**동시** 연결을 사용 하면 추가 전화기 (예: 휴대 전화) 또는 기타 끝점 장치에서 걸려오는 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-141">**Simultaneous ringing** enables incoming calls to ring on an additional phone (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="9d246-142">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-142">Enabled by default.</span></span>

  - <span data-ttu-id="9d246-143">**팀 통화** 는 정의 된 팀의 사용자가 팀의 다른 구성원에 대 한 통화에 대답할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-143">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="9d246-144">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-144">Enabled by default.</span></span>

  - <span data-ttu-id="9d246-145">**Pstn 경로** 조정 기능을 사용 하면 WAN이 혼잡 하거나 사용할 수 없는 경우 다른 enterprise 사용자에 게이 정책을 할당 한 사용자가 PSTN (공개 교환 통신 네트워크)에서 경로를 조정 하 여 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-145">**PSTN reroute** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="9d246-146">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-146">Enabled by default.</span></span>

  - <span data-ttu-id="9d246-147">**대역폭 정책 재정의** 를 통해 관리자는 특정 사용자에 대 한 통화 허용 제어 정책 결정을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-147">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="9d246-148">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-148">Disabled by default.</span></span>

  - <span data-ttu-id="9d246-149">**악의적인 통화 추적** 을 통해 사용자는 Lync 클라이언트를 사용 하 여 악의적인 통화를 보고할 수 있으며, 그 다음에는 호출 정보 레코드에서 이러한 호출에 플래그를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-149">**Malicious call tracing** enables users to report malicious calls by using the Lync client, and then flags such calls in the call detail records.</span></span> <span data-ttu-id="9d246-150">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-150">Disabled by default.</span></span>

  - <span data-ttu-id="9d246-151">보이스 **메일 이탈** 은 동시 연결을 구성 하 고 전화를 끄거나 배터리를 껐 거 나 범위를 벗어날 때 사용자의 휴대 전화 보이스 메일로 착신 전환 되는 것을 방지 하 고 타이머 값을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-151">**Voicemail escape** prevents calls from being immediately routed to the user’s mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value.</span></span> <span data-ttu-id="9d246-152">이 설정은 타이머를 사용 하거나 사용 하지 않도록 설정 하 고 타이머 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-152">This setting enables and disables the timer and sets the value of the timer.</span></span> <span data-ttu-id="9d246-153">Lync Server Management Shell을 사용해 서만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-153">It can be configured only by using the Lync Server Management Shell.</span></span> <span data-ttu-id="9d246-154">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-154">Disabled by default.</span></span>

  - <span data-ttu-id="9d246-155">착신 **전환 및 동시** 연결 설정 관리자는 착신 전환 및 동시 연결을 위해 음성 정책으로 동일한 PSTN 사용을 지정 하 고, 착신 전환 및 내부 Lync 사용자에 게 동시 연결을 제한 하거나, 음성 정책의 PSTN 사용과는 다른 사용자 지정 PSTN 사용을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-155">**Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Lync users only, or specify a custom PSTN usage that is different from the voice policy’s PSTN usage.</span></span> <span data-ttu-id="9d246-156">기본적으로 통화 전환 및 동시 연결에 대 한 음성 정책으로 동일한 PSTN 사용량을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-156">The default is to use the same PSTN usage as the voice policy for call forwarding and simultaneous ringing.</span></span>

</div>

<div>

## <a name="pstn-usage-records"></a><span data-ttu-id="9d246-157">PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="9d246-157">PSTN Usage Records</span></span>

<span data-ttu-id="9d246-158">각 음성 정책에는 하나 이상의 관련 PSTN 사용 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-158">Each voice policy should have one or more associated PSTN usage records.</span></span> <span data-ttu-id="9d246-159">PSTN 사용은 동시 연결/착신 전환을 위해 음성 정책에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-159">PSTN usages can be associated with a voice policy for the purpose of simultaneous ringing and call forwarding only.</span></span> <span data-ttu-id="9d246-160">PSTN 사용 레코드 계획에 대 한 자세한 내용은 [Lync Server 2013의 PSTN 사용 레코드](lync-server-2013-pstn-usage-records.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d246-160">For details about planning PSTN usage records, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9d246-161">PSTN 사용 순서는 사용자가 경로와 일치 하기 때문에, 아웃 바운드 라우팅 기능은 PSTN 사용량을 위에서 아래와 비교 하 여 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-161">PSTN usage order is critical because in matching users to routes, the outbound routing functionality compares PSTN usages from top to bottom.</span></span> <span data-ttu-id="9d246-162">첫 번째 사용이 통화 경로와 일치 하는 경우 해당 경로를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-162">If the first usage matches the call route, that route is used.</span></span> <span data-ttu-id="9d246-163">그렇지 않은 경우에는 아웃 바운드 라우팅 기능이 목록의 다음 PSTN 사용을 조회 하 고 일치 하는 항목이 발견 될 때까지 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-163">If not, the outbound routing functionality looks at the next PSTN usage on the list and continues until a match is found.</span></span> <span data-ttu-id="9d246-164">실제로, 목록의 첫 번째 항목을 사용할 수 없는 경우 후속 PSTN 용도에서 백업을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d246-164">In effect, the subsequent PSTN usages provide backup if the first one on the list is unavailable.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

