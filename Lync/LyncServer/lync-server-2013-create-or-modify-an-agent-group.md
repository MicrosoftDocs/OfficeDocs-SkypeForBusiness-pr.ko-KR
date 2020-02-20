---
title: 'Lync Server 2013: 에이전트 그룹 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an agent group
ms:assetid: f1461fff-51c1-4f4b-9311-8cba02c333fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205370(v=OCS.15)
ms:contentKeyID: 48185784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8dd855edfcef9d9503d433426492f0cc1517b61
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-agent-group-in-lync-server-2013"></a><span data-ttu-id="f2503-102">Lync Server 2013에서 에이전트 그룹 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="f2503-102">Create or modify an agent group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2503-103">_**마지막으로 수정 된 항목:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="f2503-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="f2503-104">다음 절차 중 하나를 사용 하 여 에이전트 그룹을 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-104">Use one of the following procedures to create or modify an agent group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2503-105">관리자 (예: CsVoiceAdministrator)는 사용자를 에이전트 그룹에 할당 하기 전에 Enterprise Voice 및 Lync Server에 대해 사용자를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-105">An Administrator—for example, CsVoiceAdministrator—must enable users for Enterprise Voice and Lync Server before the users can be assigned to agent groups.</span></span> <span data-ttu-id="f2503-106">관리 되는 워크플로에 대 한 위임 된 응답 그룹 관리자 중 하나인 경우 에이전트 그룹을 만들고 관리 하는 워크플로에서 에이전트 그룹을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-106">If you are one of the delegated Response Group Managers for a managed workflow, you can create agent groups and use the agent groups in the workflows that you manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f2503-p102">사용자를 응답 그룹 에이전트로 할당할 때 해당 사용자가 개인 정보 보호 모드를 사용하도록 설정한 경우 "RGS Presence Watcher" 대화 상대를 검색하여 대화 상대 목록에 추가해야 합니다. 개인 정보 보호 모드를 사용하도록 설정한 에이전트의 대화 상대 목록에 "RGS Presence Watcher"가 없으면 응답 그룹으로 걸려 온 전화를 받을 수 없습니다. 개인 정보 보호 모드를 사용하도록 설정하지 않은 에이전트는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-p102">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-an-agent-group"></a><span data-ttu-id="f2503-110">Lync Server 제어판을 사용 하 여 에이전트 그룹을 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="f2503-110">To use Lync Server Control Panel to create or modify an agent group</span></span>

1.  <span data-ttu-id="f2503-111">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-111">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f2503-112">관리 되는 워크플로에 대 한 위임 된 응답 그룹 관리자 중 하나인 경우 관리 되는 워크플로에서 그룹을 만들고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-112">If you are one of the delegated Response Group Managers for a managed workflow, you can create groups and use them in the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="f2503-113">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f2503-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f2503-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f2503-115">왼쪽 탐색 모음에서 **응답 그룹**을 클릭한 다음 **그룹**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-115">In the left navigation bar, click **Response Groups**, and then click **Group**.</span></span>

4.  <span data-ttu-id="f2503-116">**그룹** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-116">On the **Group** page, do one of the following:</span></span>
    
      - <span data-ttu-id="f2503-117">새 에이전트 그룹을 만들려면 **새로**만들기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-117">To create a new agent group, click **New**.</span></span> <span data-ttu-id="f2503-118">**서비스 선택** 검색 필드에 그룹을 추가할 **applicationserver** 서비스의 이름 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-118">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service where you want to add the group.</span></span> <span data-ttu-id="f2503-119">서비스 결과 목록에서 원하는 서비스를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-119">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="f2503-120">기존 에이전트 그룹을 수정 하려면 검색 필드에 에이전트 그룹의 이름 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-120">To modify an existing agent group, type all or part of the name of the agent group in the search field.</span></span> <span data-ttu-id="f2503-121">결과 목록에서 원하는 그룹을 클릭 하 고 **편집**을 클릭 한 후에 **자세한 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-121">In the resulting list, click the group that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f2503-122">**이름**에 에이전트 그룹의 식별 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-122">In **Name**, type an identifying name for the agent group.</span></span>

6.  <span data-ttu-id="f2503-123">**설명**에 그룹에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-123">In **Description**, type a description for the group.</span></span>

7.  <span data-ttu-id="f2503-124">**참가 정책**에서 다음 중 하나를 선택하여 그룹의 로그인 동작을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-124">In the **Participation policy**, select one of the following to set up the sign-in behavior for the group:</span></span>
    
      - <span data-ttu-id="f2503-125">그룹의 에이전트가 그룹에 로그인 및 로그아웃할 필요가 없도록 지정하려면 **비공식**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-125">Select **Informal** to specify that agents in the group do not need to sign in and out of the group.</span></span> <span data-ttu-id="f2503-126">에이전트는 Lync Server 2013에 로그인 할 때 그룹에 자동으로 로그인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-126">Agents are automatically signed in to the group when they sign in to Lync Server 2013.</span></span>
    
      - <span data-ttu-id="f2503-127">그룹의 에이전트가 그룹에 로그인 및 로그아웃해야 하도록 지정하려면 **공식**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-127">Select **Formal** to specify that agents in the group must sign in and out of the group.</span></span> <span data-ttu-id="f2503-128">이 옵션을 선택 하면 에이전트가 Lync에서 메뉴 항목을 클릭 하 여 Internet Explorer를 열고 그룹에 로그인 하 고 로그 아웃 하기 위한 웹 페이지 콘솔을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-128">When you select this option, agents click a menu item in Lync to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

8.  <span data-ttu-id="f2503-129">**알림 시간(초)** 에 사용 가능한 다음 에이전트에 통화를 전달하기 전에 현재 에이전트에 신호음을 울릴 시간(초)을 지정합니다(기본값은 20초).</span><span class="sxs-lookup"><span data-stu-id="f2503-129">In **Alert time (seconds)**, specify the number of seconds to ring an agent before offering the call to the next available agent (the default is 20 seconds).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f2503-130">에이전트 경고 시간 설정은 180 초를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-130">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="f2503-131">에이전트 경고 시간이 180 초를 초과 하는 경우 SIP 트랜잭션 타이머가 최대 대기 시간에 도달 하기 때문에 클라이언트 응용 프로그램에서 통화를 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-131">If the agent alert time exceeds 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

9.  <span data-ttu-id="f2503-132">**라우팅 방법**에서 그룹의 에이전트에 통화가 라우팅되는 방법을 다음과 같이 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-132">In **Routing method**, select the method for routing calls to agents in the group as follows:</span></span>
    
      - <span data-ttu-id="f2503-133">가장 오랫동안 유휴 상태 였던 에이전트에 대 한 새 통화를 먼저 제공 하려면 (Lync Server에서 가장 오랫동안 **사용 가능** 또는 **비활성** 상태임) **가장 긴 유휴 시간**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-133">To offer a new call first to the agent who has been idle the longest (has had a presence of **Available** or **Inactive** in Lync Server the longest), click **Longest idle**.</span></span>
    
      - <span data-ttu-id="f2503-p109">대화 가능한 모든 에이전트에 동시에 새 통화를 제공하려면 **병렬**을 클릭합니다. 통화를 수락하는 첫 번째 에이전트에 통화가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-p109">To offer a new call to all available agents at the same time, click **Parallel**. The call is sent to the first agent who accepts it.</span></span>
    
      - <span data-ttu-id="f2503-136">각 에이전트에 차례로 새 통화를 제공하려면 **라운드 로빈**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-136">To offer a new call to each agent in turn, click **Round robin**.</span></span>
    
      - <span data-ttu-id="f2503-137">항상 **에이전트** 목록에 나열된 순서대로 에이전트에 새 통화를 제공하려면 **직렬**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-137">To always offer a new call to the agents in the order in which they are listed in the **Agent** list, click **Serial**.</span></span>
    
      - <span data-ttu-id="f2503-138">현재 현재 상태에 관계 없이 Lync Server 2013 및 응답 그룹 응용 프로그램에 동시에 로그인 한 모든 에이전트에 대 한 새 통화를 제공 하려면 **전화 교환을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-138">To offer a new call to all agents who are signed into Lync Server 2013 and the Response Group application at the same time, regardless of their current presence, click **Attendant**.</span></span> <span data-ttu-id="f2503-139">Lync 2010 Attendant 에이전트로 구성 된 사용자는 대기 중인 모든 통화를 확인 하 고 순서에 상관 없이 대기 중인 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-139">Lync 2010 Attendant users who are configured as agents can see all the calls that are waiting and answer waiting calls in any order.</span></span> <span data-ttu-id="f2503-140">통화가 수락 된 첫 번째 에이전트로 전송 된 후 다른 Lync 2010 Attendant 사용자에 게 통화가 더 이상 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-140">The call is sent to the first agent who accepts it, after which the other Lync 2010 Attendant users no longer see the call.</span></span>

10. <span data-ttu-id="f2503-141">**에이전트**에서 에이전트 목록을 만드는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-141">In **Agents**, specify how you want to create your agents list:</span></span>
    
      - <span data-ttu-id="f2503-142">사용자 지정 에이전트 목록을 사용 하려면 **사용자 지정 에이전트 그룹 정의**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-142">To use a custom list of agents, click **Define a custom group of agents**, and do one of the following:</span></span>
        
          - <span data-ttu-id="f2503-143">에이전트 그룹에 사용자를 추가 하려면 **선택을**클릭 하 고 **에이전트 검색 선택** 필드에이 그룹에 추가할 사용자의 이름 일부나 전체를 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-143">To add a user to the agent group, click **Select**, and then in the **Select Agents** search field, type all or part of the name of the user that you want to add to this group, and then click **Find**.</span></span> <span data-ttu-id="f2503-144">결과 에이전트 목록에서 사용자를 클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-144">In the resulting list of agents, click the user, and then click **OK**.</span></span>
        
          - <span data-ttu-id="f2503-145">에이전트 그룹에서 사용자를 제거 하려면 에이전트 목록에서 제거할 사용자를 클릭 한 다음 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-145">To remove a user from the agent group, in the list of agents, click the user you want to remove, and then click **Remove**.</span></span>
        
          - <span data-ttu-id="f2503-146">라운드 로빈 라우팅 또는 직렬 라우팅을 사용 하는 그룹에서 호출이 제공 되는 에이전트의 순서를 변경 하려면 에이전트 목록에서 사용자를 클릭 한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-146">To change the order in which agents are offered calls in groups that use either round robin routing or serial routing, in the list of agents, click a user, and then click the up arrow or down arrow.</span></span>
    
      - <span data-ttu-id="f2503-147">Microsoft Exchange Server 메일 그룹을 에이전트로 사용 하려면 **기존 전자 메일 메일 그룹 사용**을 클릭 한 다음 **메일 그룹 주소**에 메일 그룹의 전자 메일 주소 (예: NetworkSupport@contoso.com)를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-147">To use a Microsoft Exchange Server distribution list as your agent group, click **Use an existing email distribution list**, and then in **Distribution list address**, type the email address of the distribution list (for example, NetworkSupport@contoso.com).</span></span>
        
        <span data-ttu-id="f2503-148">전자 메일 그룹을 사용하는 경우 다음과 같은 제약 조건이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-148">If you use an email distribution list, you are subject to the following constraints:</span></span>
        
          - <span data-ttu-id="f2503-p112">에이전트 그룹에 대해 메일 그룹을 여러 개 선택할 수는 없습니다. 각 그룹이 하나의 메일 그룹만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-p112">You cannot select multiple distribution lists for the agent group. Each group supports only a single distribution list.</span></span>
        
          - <span data-ttu-id="f2503-151">메일 그룹에 하나 이상의 메일 그룹이 포함되어 있는 경우 중첩된 메일 그룹의 구성원은 에이전트 목록에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-151">If the distribution list contains one or more distribution lists, members of the nested distribution lists are not added to the agent list.</span></span>
        
          - <span data-ttu-id="f2503-152">Serial 또는 라운드 로빈 라우팅이 선택 된 경우 서버는 라우팅 방법 및 에이전트가 메일 그룹에 나열 되는 순서에 따라 수신 전화를 적절 한 에이전트에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-152">If serial or round robin routing is selected, the server offers an incoming call to the appropriate agent according to the routing method and according to the order in which agents are listed in the distribution list.</span></span>
        
          - <span data-ttu-id="f2503-153">메일 그룹에 Lync Server 2010이 사용 하도록 설정 되었지만 Enterprise Voice가 사용 하도록 설정 되지 않은 사용자가 포함 되어 있는 경우에는 dysfunctional 에이전트로 해당 관리자에 게 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-153">If the distribution list contains users for which Lync Server 2010 is enabled but Enterprise Voice is not enabled, they will be added to the agent group as dysfunctional agents.</span></span> <span data-ttu-id="f2503-154">메일 그룹의 모든 구성원에 게 해당 사용자 계정에 Enterprise Voice가 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-154">Make sure that all members of the distribution list have Enterprise Voice enabled for their user accounts.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="f2503-155">전자 메일 그룹을 사용 하는 경우에는 숨겨진 구성원 또는 숨겨진 목록이 응답 그룹 관리자 또는 사용자에 게 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-155">If you use an email distribution list, hidden memberships or hidden lists might become visible to the Response Group administrator or users.</span></span>

        
        </div>
        
        <span data-ttu-id="f2503-156">숨겨진 구성원 또는 숨겨진 목록은 다음과 같이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-156">Hidden memberships or hidden lists can become visible as follows:</span></span>
        
          - <span data-ttu-id="f2503-157">메일 그룹을 구성 하 여 구성원 자격이 숨겨 응답 그룹이 관리자가 배포 목록을 에이전트 목록에 할당 하는 경우 사용자가 그룹을 호출 하 여 구성원을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-157">If a distribution list was configured so that the membership is hidden and the Response Group administrator assigns the distribution list to the agent list, users can call the group to find out who the members are.</span></span>
        
          - <span data-ttu-id="f2503-158">메일 그룹이 Exchange 전체 주소 목록에서 숨겨지도록 구성 된 경우 응답 그룹 프로세스에서 해당 하는 사용자 권한이 있는 상태에서 메일 그룹을 보고 에이전트 목록에 할당할 수 있습니다. 권한 (관리자에 게 적절 한 사용자 권한 및 사용 권한이 없는 경우 포함)</span><span class="sxs-lookup"><span data-stu-id="f2503-158">If a distribution list was configured so that it is hidden in the Exchange Global Address List, the Response Group administrator might be able to see the distribution list and assign it to the agent list if the Response Group process has the appropriate user rights and permissions, even if the administrator does not have the appropriate user rights and permissions.</span></span>

11. <span data-ttu-id="f2503-159">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-159">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-agent-group"></a><span data-ttu-id="f2503-160">Windows PowerShell을 사용 하 여 에이전트 그룹을 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="f2503-160">To use Windows PowerShell to create or modify an agent group</span></span>

1.  <span data-ttu-id="f2503-161">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-161">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="f2503-162">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-162">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f2503-163">새 에이전트 그룹을 만들려면 **get-csrgsagentgroup** 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-163">Use **New-CsRgsAgentGroup** to create a new agent group.</span></span> <span data-ttu-id="f2503-164">**Get-csrgsagentgroup** 을 사용 하 여 기존 에이전트 그룹을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-164">Use **Set-CsRgsAgentGroup** to modify an existing agent group.</span></span> <span data-ttu-id="f2503-165">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-165">At the command line, run:</span></span>
    
        New-CsRgsAgentGroup -Name "<agent group name>" -Parent $serviceId [-Description "<agent group description>"] -[AgentAlertTime <# seconds until call is routed to next agent>] [-ParticipationPolicy <Formal | Informal>] [-RoutingMethod <method for routing calls>] [-AgentsByUri("<first agent's SIP address>","<second agent's SIP address>")];
    
    <span data-ttu-id="f2503-166">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-166">For example:</span></span>
    
        New-CsRgsAgentGroup -Name "Help Desk" -Parent "service:ApplicationServer:atl-cs-001.contoso.com"  -Description "Contoso Help Desk" -AgentAlertTime 20 -ParticipationPolicy Formal -RoutingMethod RoundRobin -AgentsByUri("sip:mindy@contoso.com","sip:bob@contoso.com")
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f2503-167">에이전트 경고 시간 설정은 180 초를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-167">The agent alert time setting cannot exceed 180 seconds.</span></span> <span data-ttu-id="f2503-168">에이전트 경고 시간이 180 초 보다 크면 SIP 트랜잭션 타이머가 최대 대기 시간에 도달 하 여 클라이언트 응용 프로그램에서 통화를 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-168">If the agent alert time is greater than 180 seconds, the client application rejects the call because the SIP transaction timer reaches its maximum wait time.</span></span>

    
    </div>

4.  <span data-ttu-id="f2503-169">에이전트 그룹이 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-169">Confirm that the agent group is created.</span></span> <span data-ttu-id="f2503-170">를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f2503-170">Run:</span></span>
    
        Get-CsRgsAgentGroup -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2503-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2503-171">See Also</span></span>


[<span data-ttu-id="f2503-172">Lync Server 2013에서 에이전트 그룹 삭제</span><span class="sxs-lookup"><span data-stu-id="f2503-172">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)  


[<span data-ttu-id="f2503-173">Lync Server 2013에서 응답 그룹 에이전트 그룹 관리</span><span class="sxs-lookup"><span data-stu-id="f2503-173">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)  
[<span data-ttu-id="f2503-174">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="f2503-174">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="f2503-175">Get-csrgsagentgroup</span><span class="sxs-lookup"><span data-stu-id="f2503-175">New-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup)  
[<span data-ttu-id="f2503-176">Get-csrgsagentgroup</span><span class="sxs-lookup"><span data-stu-id="f2503-176">Set-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsAgentGroup)  
[<span data-ttu-id="f2503-177">Get-csrgsagentgroup</span><span class="sxs-lookup"><span data-stu-id="f2503-177">Get-CsRgsAgentGroup</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsAgentGroup)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

