---
title: 'Lync Server 2013: 음성 정책 수정 및 PSTN 사용 레코드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c11ae10476d286fd24f82b96ba9191b0e758e276
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="41d0a-102">Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="41d0a-102">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41d0a-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="41d0a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="41d0a-104">음성 정책을 수정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-104">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="41d0a-105">새 음성 정책을 만들려는 경우이 절차를 수행 하려면 [음성 정책 만들기 및 Lync Server 2013에서 PSTN 사용 레코드 구성을](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-105">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41d0a-106">음성 정책에 할당 된 사용자에 게는 PSTN (공중 전화망) 사용 레코드가 연결 되어 있지 않으면 사용자가 아웃 바운드 호출을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-106">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="41d0a-107">Enterprise Voice 배포에서 사용할 수 있는 모든 PSTN 사용 레코드를 나열 하 고 해당 속성을 보려면 <A href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013에서 pstn 사용 레코드 보기</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="41d0a-107">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="41d0a-108">음성 정책을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="41d0a-108">To modify a voice policy</span></span>

1.  <span data-ttu-id="41d0a-109">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="41d0a-110">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="41d0a-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="41d0a-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="41d0a-113">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **음성 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-113">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="41d0a-114">**음성 정책** 페이지에서 음성 정책 이름을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-114">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41d0a-115">음성 정책이 만들어질 때 범위 및 이름이 설정 된 경우</span><span class="sxs-lookup"><span data-stu-id="41d0a-115">The scope and name were set when the voice policy was created.</span></span> <span data-ttu-id="41d0a-116">이러한 설정은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-116">They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="41d0a-117">반드시 **음성 정책 편집**에서 음성 정책에 대 한 추가 설명 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-117">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="41d0a-118">각 **통화 기능**을 사용 하거나 사용 하지 않도록 설정 하려면 다음 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-118">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="41d0a-119">**음성 메일 이스케이프** 는 동시 벨 울림이 구성 되 고 전화가 꺼져 있거나, 배터리가 부족 하거나, 범위를 벗어날 때 전화가 사용자의 휴대폰 음성 메일 시스템으로 즉시 라우팅되지 않도록 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-119">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="41d0a-120">이 기능은 Lync Server 관리 셸을 통해서만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-120">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="41d0a-121">**착신 전환** - 통화를 다른 전화 및 클라이언트 장치로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="41d0a-122">Lync Server 2013에서는 착신 전환에 대 한 보다 광범위 한 구성 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-122">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="41d0a-123">예를 들어 조직에서 들어오는 전화가 PSTN에 외부적으로 전달 되는 것을 허용 하지 않으려는 경우 관리자는 특수 음성 정책을 적용 하 여이 제한을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="41d0a-124">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-124">Enabled by default.</span></span>
    
      - <span data-ttu-id="41d0a-125">**위임** - 자신을 대신해 전화를 걸거나 받을 다른 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="41d0a-126">Lync Server 2013에서는 대리인이 자신의 관리자에 게 들어오는 호출을 사용 하 여 모든 대리인의 동시 벨 울림 대상에 연결할 수 있도록 하는 동시 울림을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-126">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="41d0a-127">이를 통해 대리인이 관리자에 게 전송 되는 호출에 보다 유연성 있게 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="41d0a-128">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="41d0a-129">**통화 전송** - 통화를 다른 사람에게 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-129">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="41d0a-130">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-130">Enabled by default.</span></span>
    
      - <span data-ttu-id="41d0a-131">**통화** 대기를 통해 사용자는 통화 보류를 선택 하 고 다른 전화나 클라이언트에서 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-131">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="41d0a-132">이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-132">Disabled by default.</span></span>
    
      - <span data-ttu-id="41d0a-133">**동시 울림** 은 추가 전화기 (예: 휴대폰) 또는 기타 끝점 장치에서 수신 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="41d0a-134">Lync Server 2013에서는 동시 울림을 위한 보다 광범위 한 구성 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-134">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="41d0a-135">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-135">Enabled by default.</span></span>
    
      - <span data-ttu-id="41d0a-136">**팀 호출** - 정의된 팀의 사용자가 팀의 다른 구성원에 대한 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="41d0a-137">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-137">Enabled by default.</span></span>
    
      - <span data-ttu-id="41d0a-138">**Pstn 재 경로** 설정은 WAN이 혼잡 하거나 사용할 수 없는 경우이 정책이 할당 된 사용자의 통화를 pstn (공중 전화망)에서 다시 라우팅할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="41d0a-139">이 확인란은 기본적으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="41d0a-140">**대역폭 정책 재정의** 는 관리자가 특정 사용자에 대 한 CAC (통화 허용 제어) 정책 결정을 재정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-140">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user.</span></span> <span data-ttu-id="41d0a-141">이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-141">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="41d0a-142">정책은 사용자에 대 한 수신 전화에 대해서만 무시 되 고 사용자가 보내는 통화에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-142">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="41d0a-143">세션이 설정 되 면 대역폭 소비를 정확 하 게 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-143">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="41d0a-144">이 설정은 가급적 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-144">This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="41d0a-145">**악의적인 통화 추적** 을 통해 사용자는 클라이언트 UI를 사용 하 여이에 대 한 악성 통화 (예: cdrs (통화 정보 기록)의 호출 플래그를 설정 하 여 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-145">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="41d0a-146">이 확인란은 기본적으로 선택 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-146">Disabled by default.</span></span>

7.  <span data-ttu-id="41d0a-147">이 음성 정책에 대 한 PSTN 사용 레코드를 연결 및 구성 하려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-147">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="41d0a-148">Enterprise Voice 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-148">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="41d0a-149">이 음성 정책에 연결할 레코드를 강조 표시 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-149">Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="41d0a-150">이 음성 정책에서 PSTN 사용 레코드를 제거 하려면 레코드를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-150">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="41d0a-151">새 PSTN 사용 레코드를 정의 하 고이 음성 정책과 연결 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-151">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="41d0a-152">**새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-152">Click **New**.</span></span>
        
        2.  <span data-ttu-id="41d0a-153">**이름** 필드에 레코드에 대 한 설명이 포함 된 고유 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-153">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="41d0a-154">예를 들어 Redmond에 위치한 전일 근무 직원에 대해 **redmond** 라는 PSTN 사용 레코드를 만들고 임시 직원에 게는 **RedmondTemps** 이라는 다른 레코드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-154">For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="41d0a-155">PSTN 사용 레코드 이름은 Enterprise Voice 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-155">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="41d0a-156">레코드를 저장한 후에는 <STRONG>이름</STRONG> 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-156">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="41d0a-157">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-157">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="41d0a-158">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-158">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="41d0a-159">PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-159">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="41d0a-160">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-160">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="41d0a-161">자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="41d0a-162">이 PSTN 사용 레코드에 이미 연결 되어 있는 경로를 편집 하려면 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-162">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="41d0a-163">자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="41d0a-164">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-164">Click **OK**.</span></span>
    
      - <span data-ttu-id="41d0a-165">이 음성 정책에 이미 연결 된 PSTN 사용 레코드를 편집 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-165">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="41d0a-166">편집할 PSTN 사용 레코드를 강조 표시 하 고 **자세한 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-166">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="41d0a-167">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-167">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="41d0a-168">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-168">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="41d0a-169">이 PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-169">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="41d0a-170">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-170">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="41d0a-171">자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-171">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="41d0a-172">이 PSTN 사용 레코드에 이미 연결 되어 있는 경로를 편집 하려면 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-172">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="41d0a-173">자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-173">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="41d0a-174">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-174">Click **OK**.</span></span>

8.  <span data-ttu-id="41d0a-175">최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-175">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="41d0a-176">목록에서 레코드의 위치를 변경 하려면 레코드 이름을 강조 표시 하 고 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-176">To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41d0a-177">PSTN 사용 레코드가 음성 정책에 나열 되는 순서는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-177">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="41d0a-178">Lync Server가 목록을 위에서 아래로 트래버스 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-178">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="41d0a-179">RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup 등의 사용 빈도에 따라 목록을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-179">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="41d0a-180">이 음성 정책에서 착신 전환 및 동시 신호 울림에 대 한 PSTN 사용 레코드를 연결 및 구성 하려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-180">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="41d0a-181">이 음성 정책으로 착신 전환 및 동시 신호 울림에 동일한 PSTN 사용 레코드를 사용 하려면 드롭다운 메뉴에서 **통화 PSTN 사용을 사용한 옵션 경로** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-181">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="41d0a-182">내부 Lync 사용자에 대해서만 착신 전환 및 동시 신호 울림을 허용 하려면 드롭다운 메뉴에서 **내부 Lync 사용자에 대해서만 경로** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-182">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="41d0a-183">통화가 외부 PSTN 번호로 전달 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-183">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="41d0a-184">이 음성 정책에 사용 된 것 보다 착신 전환 및 동시 신호 울림에 대해 서로 다른 PSTN 사용 레코드를 지정 하려면 드롭다운 메뉴에서 **사용자 지정 PSTN 사용을 사용한 옵션 경로** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-184">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="41d0a-185">이 옵션은 기존 PSTN 사용 레코드를 선택 하거나, 특히 착신 전환 및 동시 신호 울림을 위해 새 PSTN 사용 레코드를 만드는 컨트롤을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-185">This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="41d0a-186">착신 전환 및 동시 신호 울림에 대 한 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-186">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**.</span></span> <span data-ttu-id="41d0a-187">이 착신 전환 및 동시 신호 울림 정책과 연결 하려는 레코드를 강조 표시 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-187">Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="41d0a-188">이 착신 전환 및 동시 신호 울림 정책에서 PSTN 사용 레코드를 제거 하려면 레코드를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-188">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="41d0a-189">새 PSTN 사용 레코드를 정의 하 고이 착신 전환 및 동시 신호 울림 정책과 연결 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-189">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="41d0a-190">**새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-190">Click **New**.</span></span>
            
            2.  <span data-ttu-id="41d0a-191">**이름** 필드에 레코드에 대 한 설명이 포함 된 고유 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-191">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="41d0a-192">PSTN 사용 레코드 이름은 Enterprise Voice 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-192">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="41d0a-193">레코드를 저장한 후에는 <STRONG>이름</STRONG> 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-193">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="41d0a-194">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-194">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="41d0a-195">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-195">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="41d0a-196">PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-196">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="41d0a-197">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-197">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="41d0a-198">자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-198">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="41d0a-199">이 PSTN 사용 레코드에 이미 연결 되어 있는 경로를 편집 하려면 경로를 강조 표시 하 고 **자세한 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-199">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="41d0a-200">자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-200">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="41d0a-201">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-201">Click **OK**.</span></span>
        
          - <span data-ttu-id="41d0a-202">이 음성 정책에 이미 연결 된 PSTN 사용 레코드를 편집 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-202">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="41d0a-203">편집할 PSTN 사용 레코드를 강조 표시 하 고 **자세한 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-203">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="41d0a-204">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-204">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="41d0a-205">Enterprise Voice 배포에서 사용 가능한 모든 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-205">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="41d0a-206">이 PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-206">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="41d0a-207">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-207">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="41d0a-208">자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-208">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="41d0a-209">이 PSTN 사용 레코드에 이미 연결 되어 있는 경로를 편집 하려면 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-209">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="41d0a-210">자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-210">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="41d0a-211">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-211">Click **OK**.</span></span>

10. <span data-ttu-id="41d0a-212">반드시 전화 번호를 입력 하 여 음성 정책을 테스트 하 고 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-212">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="41d0a-213">테스트 결과가 변환 된 번호 아래 **에**표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-213">The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41d0a-214">아직 테스트를 통과 하지 않은 음성 정책을 저장 한 다음 나중에 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-214">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="41d0a-215">자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-215">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="41d0a-216">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-216">Click **OK**.</span></span>

12. <span data-ttu-id="41d0a-217">**음성 정책** 페이지에서 **커밋을**클릭 하 고 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-217">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41d0a-218">음성 정책을 만들거나 수정할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-218">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="41d0a-219">자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-219">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="41d0a-220">반드시 음성 메일 이스케이프는 통화가 사용자의 휴대폰 음성 메일에 의해 즉시 응답 되었음을 감지 하 고 전화를 휴대폰 음성 메일로 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-220">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="41d0a-221">이를 통해 사용자가 통화에 응답할 수 있도록 하는 사용자의 다른 끝점에 대 한 통화가 계속 해 서 켜 집니다.</span><span class="sxs-lookup"><span data-stu-id="41d0a-221">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="41d0a-222">음성 메일 정책을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 음성 메일 이스케이프 구성을](lync-server-2013-configuring-voice-mail-escape.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="41d0a-222">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41d0a-223">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41d0a-223">See Also</span></span>


[<span data-ttu-id="41d0a-224">Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="41d0a-224">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="41d0a-225">Lync Server 2013에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="41d0a-225">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="41d0a-226">Lync Server 2013에서 음성 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="41d0a-226">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="41d0a-227">Lync Server 2013에서 음성 경로 수정</span><span class="sxs-lookup"><span data-stu-id="41d0a-227">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="41d0a-228">Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="41d0a-228">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="41d0a-229">Lync Server 2013에서 음성 메일 이스케이프 구성</span><span class="sxs-lookup"><span data-stu-id="41d0a-229">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="41d0a-230">Lync Server 2013에서 음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="41d0a-230">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

