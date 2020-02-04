---
title: 'Lync Server 2013: 음성 정책 만들기 및 PSTN 사용 레코드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80537aabe132f1b83714d42244409224ca53f72d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="501b1-102">Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="501b1-102">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="501b1-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="501b1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="501b1-104">새 음성 정책을 만들려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-104">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="501b1-105">음성 정책을 편집 하려는 경우에는 [Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성을](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-105">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="501b1-106">각 음성 정책에는 하나 이상의 연결 된 PSTN (공개 통신 네트워크) 사용 레코드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-106">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="501b1-107">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록을 보고 해당 속성을 볼 수 있도록 <A href="lync-server-2013-view-pstn-usage-records.md">Lync Server 2013에서 pstn 사용 레코드 보기</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-107">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="501b1-108">음성 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="501b1-108">To create a voice policy</span></span>

1.  <span data-ttu-id="501b1-109">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="501b1-110">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="501b1-111">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="501b1-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="501b1-113">왼쪽 탐색 모음에서 **음성 라우팅을** 클릭 한 다음 **음성 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-113">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="501b1-114">**음성 정책** 페이지에서 **새로 만들기** 를 클릭 한 다음 새 정책에 대 한 범위를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-114">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="501b1-115">**사이트 정책은** 사용자 정책에 할당 된 사용자 또는 그룹을 제외한 전체 사이트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-115">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy.</span></span> <span data-ttu-id="501b1-116">정책 범위에 대 한 사이트를 선택 하는 경우 **사이트 선택** 대화 상자에서 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-116">If you select Site for a policy scope, choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="501b1-117">사이트에 대 한 음성 정책이 이미 만들어졌으면 사이트 **선택** 대화 상자에 해당 사이트가 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-117">If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="501b1-118">지정 된 사용자 또는 그룹에 **사용자 정책을** 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-118">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="501b1-119">음성 정책 범위가 사용자 인 경우 **이름** 필드에 정책에 대 한 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-119">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="501b1-120">음성 정책 범위가 사이트인 경우 <STRONG>새 음성 정책의</STRONG> <STRONG>이름</STRONG> 필드는 사이트 이름으로 미리 채워 있으므로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-120">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="501b1-121">) 음성 정책에 대 한 추가 설명 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-121">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="501b1-122">이 음성 정책에 대 한 각 **호출 기능** 을 사용 하거나 사용 하지 않도록 다음 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-122">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="501b1-123">**음성 메일 esc** 키를 누르면 동시 벨 울림이 구성 되 고, 전화가 꺼졌거나, 배터리 부족 상태 이거나, 범위를 벗어날 때 사용자의 휴대폰 음성 메일 시스템으로 즉시 착신 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-123">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="501b1-124">이 기능은 Lync Server Management Shell을 통해서만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-124">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="501b1-125">**착신 통화 전환** 기능을 통해 사용자는 다른 전화 및 클라이언트 장치로 전화를 착신 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-125">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="501b1-126">Lync Server 2013는 착신 전환에 대 한 다양 한 구성 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-126">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="501b1-127">예를 들어 조직에서 들어오는 통화가 PSTN에 외부적으로 착신 전환 되는 것을 허용 하지 않을 경우 관리자는 특수 음성 정책을 적용 하 여이 제한을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-127">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="501b1-128">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="501b1-129">**위임을** 통해 사용자는 다른 사용자가 대신 전화를 보내고 받을 수 있도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-129">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="501b1-130">Lync Server 2013에서 대리인은 자신의 관리자에 게 들어오는 호출을 사용 하 여 대리인의 동시 연결 대상을 모두 링 하는 동시 연결을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-130">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="501b1-131">이렇게 하면 대리인에 게 관리자를 대상으로 하는 통화에 대 한 응답을 보다 유연 하 게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-131">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="501b1-132">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-132">Enabled by default.</span></span>
    
      - <span data-ttu-id="501b1-133">**통화 전송을** 통해 사용자는 통화를 다른 사용자에 게 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-133">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="501b1-134">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-134">Enabled by default.</span></span>
    
      - <span data-ttu-id="501b1-135">**통화** 대기를 통해 사용자는 통화를 보류 했다가 다른 휴대폰 또는 클라이언트에서 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-135">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="501b1-136">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-136">Disabled by default.</span></span>
    
      - <span data-ttu-id="501b1-137">**동시** 연결을 통해 추가 전화기 (예: 휴대 전화) 또는 기타 끝점 장치에서 수신 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-137">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="501b1-138">Lync Server 2013는 동시 신호음을 위한 광범위 한 구성 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-138">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="501b1-139">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="501b1-140">**팀 통화** 는 정의 된 팀의 사용자가 팀의 다른 구성원에 대 한 통화에 대답할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-140">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="501b1-141">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-141">Enabled by default.</span></span>
    
      - <span data-ttu-id="501b1-142">**Pstn re** 는 WAN이 혼잡 하거나 사용할 수 없는 경우 다른 enterprise 사용자에 게이 정책을 할당 하는 사용자가 PSTN (공개 교환 전화 네트워크)에서 경로를 조정 하도록 하는 통화를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-142">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="501b1-143">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-143">Enabled by default.</span></span>
    
      - <span data-ttu-id="501b1-144">**대역폭 정책 재정의** 를 통해 관리자는 특정 사용자에 대 한 통화 허용 제어 정책 결정을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-144">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="501b1-145">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-145">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="501b1-146">정책은 사용자에 게 들어오는 통화에 대해서만 무시 되 고 사용자가 설정한 발신 통화에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-146">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="501b1-147">세션을 설정한 후에는 대역폭 소비가 정확 하 게 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-147">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="501b1-148">이 설정은 가끔씩만 사용 해야 하며 적절 한 통화 허용 제어 결정을 위해 예약 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-148">This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="501b1-149">**악의적인 통화 추적** 을 통해 사용자는 클라이언트 UI를 사용 하 여 악의적인 통화 (예: 폭탄 위협)를 보고할 수 있으며,이는 다시 cdrs (호출 정보 레코드)에 호출에 플래그를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-149">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="501b1-150">기본적으로 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-150">Disabled by default.</span></span>

8.  <span data-ttu-id="501b1-151">이 음성 정책에 대 한 PSTN 사용 레코드를 연결 하 고 구성 하려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-151">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="501b1-152">엔터프라이즈 음성 배포에서 사용할 수 있는 모든 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-152">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="501b1-153">이 음성 정책에 연결 하려는 레코드를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-153">Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="501b1-154">이 음성 정책에서 PSTN 사용 레코드를 제거 하려면 해당 레코드를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-154">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="501b1-155">새 PSTN 사용 레코드를 정의 하 고이를이 음성 정책에 연결 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-155">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="501b1-156">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-156">Click **New**.</span></span>
        
        2.  <span data-ttu-id="501b1-157">**이름** 필드에 레코드에 대 한 고유한 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-157">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="501b1-158">예를 들어 Redmond에 거주 하는 정규 직원에 대해 **redmond** 라는 PSTN 사용 레코드를 만들고 임시 직원에 게 **RedmondTemps** 이라는 다른 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-158">For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="501b1-159">PSTN 사용 레코드 이름은 엔터프라이즈 음성 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-159">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="501b1-160">레코드가 저장 된 후에는 <STRONG>이름</STRONG> 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-160">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="501b1-161">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-161">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="501b1-162">엔터프라이즈 음성 배포의 모든 사용 가능한 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-162">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="501b1-163">PSTN 사용 레코드에서 경로를 제거 하려면 해당 경로를 강조 표시 한 다음 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-163">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="501b1-164">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-164">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="501b1-165">자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-165">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="501b1-166">이 PSTN 사용 레코드와 이미 연결 된 경로를 편집 하려면 해당 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-166">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="501b1-167">자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-167">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="501b1-168">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-168">Click **OK**.</span></span>
    
      - <span data-ttu-id="501b1-169">이 음성 정책에 이미 연결 된 PSTN 사용 레코드를 편집 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-169">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="501b1-170">편집 하려는 PSTN 사용 레코드를 강조 표시 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-170">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="501b1-171">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-171">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="501b1-172">엔터프라이즈 음성 배포의 모든 사용 가능한 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-172">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="501b1-173">이 PSTN 사용 레코드에서 경로를 제거 하려면 해당 경로를 강조 표시 한 다음 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-173">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="501b1-174">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-174">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="501b1-175">자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-175">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="501b1-176">이 PSTN 사용 레코드와 이미 연결 된 경로를 편집 하려면 경로를 강조 표시 하 고 **세부 정보**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-176">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="501b1-177">자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-177">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="501b1-178">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-178">Click **OK**.</span></span>

9.  <span data-ttu-id="501b1-179">최적의 성능을 위해 PSTN 사용 레코드를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-179">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="501b1-180">목록에서 레코드의 위치를 변경 하려면 레코드 이름을 강조 표시 하 고 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-180">To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="501b1-181">PSTN 사용 레코드가 음성 정책에 나열 되는 순서는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-181">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="501b1-182">Lync Server가 목록을 위에서 아래로 트래버스 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-182">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="501b1-183">RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup 등의 사용 빈도 별로 목록을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-183">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="501b1-184">이 음성 정책에서 통화 전환 및 동시 연결에 대 한 PSTN 사용 레코드를 연결 하 고 구성 하려면 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-184">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="501b1-185">착신 전환 및 동시 연결에 같은 PSTN 사용 레코드를이 음성 정책으로 사용 하려면 드롭다운 메뉴에서 **통화 PSTN 사용을 사용해 경로** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-185">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="501b1-186">착신 전환을 허용 하 고 내부 Lync 사용자로 동시에 연결 하려면 드롭다운 메뉴에서 **내부 lync 사용자에 대 한 경로만** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-186">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="501b1-187">통화는 외부 PSTN 번호로 착신 전환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-187">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="501b1-188">이 음성 정책에 사용 되는 것 보다 착신 전환 및 동시 연결에 대해 다른 PSTN 사용 레코드를 지정 하려면 드롭다운 메뉴에서 **사용자 지정 PSTN 용도를 사용 하 여 경로** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-188">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="501b1-189">이 옵션은 기존 PSTN 사용 레코드를 선택 하거나, 착신 전환 및 동시 연결을 위해 특별히 새 PSTN 사용 레코드를 만드는 컨트롤을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-189">This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="501b1-190">통화 전환 및 동시 연결에 대 한 PSTN 사용 레코드 목록에서 하나 이상의 레코드를 선택 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-190">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**.</span></span> <span data-ttu-id="501b1-191">이 착신 전환 및 동시 연결 정책과 연결할 레코드를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-191">Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="501b1-192">이 착신 전환 및 동시 연결 정책에서 PSTN 사용 레코드를 제거 하려면 해당 레코드를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-192">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="501b1-193">새 PSTN 사용 레코드를 정의 하 고이를 착신 전환 및 동시 연결 정책과 연관 시키려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-193">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="501b1-194">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-194">Click **New**.</span></span>
            
            2.  <span data-ttu-id="501b1-195">**이름** 필드에 레코드에 대 한 고유한 설명적인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-195">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="501b1-196">PSTN 사용 레코드 이름은 엔터프라이즈 음성 배포 내에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-196">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="501b1-197">레코드가 저장 된 후에는 <STRONG>이름</STRONG> 필드를 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-197">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="501b1-198">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-198">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="501b1-199">엔터프라이즈 음성 배포의 모든 사용 가능한 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-199">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="501b1-200">PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-200">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="501b1-201">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-201">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="501b1-202">자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-202">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="501b1-203">이 PSTN 사용 레코드와 이미 연결 된 경로를 편집 하려면 해당 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-203">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="501b1-204">자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-204">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="501b1-205">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-205">Click **OK**.</span></span>
        
          - <span data-ttu-id="501b1-206">이 음성 정책에 이미 연결 된 PSTN 사용 레코드를 편집 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-206">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="501b1-207">편집 하려는 PSTN 사용 레코드를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-207">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="501b1-208">다음 방법 중 하나를 사용 하 여이 PSTN 사용 레코드에 대 한 경로를 연결 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-208">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="501b1-209">엔터프라이즈 음성 배포의 모든 사용 가능한 경로 목록에서 하나 이상의 경로를 선택 하려면 **선택을**클릭 하 고이 PSTN 사용 레코드와 연결할 경로를 강조 표시 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-209">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="501b1-210">이 PSTN 사용 레코드에서 경로를 제거 하려면 경로를 강조 표시 하 고 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-210">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="501b1-211">새 경로를 정의 하 고이 PSTN 사용 레코드와 연결 하려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-211">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="501b1-212">자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-212">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="501b1-213">이 PSTN 사용 레코드와 이미 연결 된 경로를 편집 하려면 해당 경로를 강조 표시 하 고 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-213">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="501b1-214">자세한 내용은 [Lync Server 2013에서 음성 경로 수정을](lync-server-2013-modify-a-voice-route.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-214">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="501b1-215">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-215">Click **OK**.</span></span>

11. <span data-ttu-id="501b1-216">) 번호를 입력 하 여 음성 정책을 테스트 하 고 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-216">(Optional) Enter a number to test the voice policy and click **Go**.</span></span> <span data-ttu-id="501b1-217">테스트 결과가 **테스트를 위해 번역 된 번호**아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-217">The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="501b1-218">아직 테스트를 통과 하지 않은 음성 정책을 저장 한 다음 나중에 다시 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-218">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="501b1-219">자세한 내용은 <A href="lync-server-2013-test-voice-routing.md">Lync Server 2013에서 음성 라우팅 테스트</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-219">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="501b1-220">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-220">Click **OK**.</span></span>

13. <span data-ttu-id="501b1-221">**음성 정책** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-221">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="501b1-222">음성 정책을 만들거나 수정할 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-222">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="501b1-223">자세한 내용은 운영 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-223">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="501b1-224">) 보이스 메일 감지는 전화가 사용자의 휴대폰 음성 메일로 바로 응답 하 고 휴대폰 음성 메일로 전화를 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-224">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="501b1-225">이렇게 하면 사용자가 전화를 받을 수 있도록 사용자가 다른 끝점을 계속 해 서 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="501b1-225">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="501b1-226">음성 메일 정책을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 음성 메일 Esc 구성을](lync-server-2013-configuring-voice-mail-escape.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="501b1-226">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="501b1-227">참고 항목</span><span class="sxs-lookup"><span data-stu-id="501b1-227">See Also</span></span>


[<span data-ttu-id="501b1-228">Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="501b1-228">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="501b1-229">Lync Server 2013에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="501b1-229">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="501b1-230">Lync Server 2013에서 음성 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="501b1-230">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="501b1-231">Lync Server 2013에서 음성 경로 수정</span><span class="sxs-lookup"><span data-stu-id="501b1-231">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="501b1-232">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="501b1-232">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="501b1-233">Lync Server 2013에서 음성 메일 esc 구성</span><span class="sxs-lookup"><span data-stu-id="501b1-233">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="501b1-234">Lync Server 2013에서 음성 라우팅 테스트</span><span class="sxs-lookup"><span data-stu-id="501b1-234">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

