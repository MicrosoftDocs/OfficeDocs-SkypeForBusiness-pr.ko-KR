---
title: 'Lync Server 2013: 큐 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 672752856d7f36e374646782cc36a031c81a9af0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="04d80-102">Lync Server 2013에서 큐 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="04d80-102">Create or modify a queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04d80-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="04d80-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="04d80-104">다음 절차를 사용하여 큐를 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-104">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="04d80-105">Lync Server 제어판을 사용 하 여 큐를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="04d80-105">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="04d80-106">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04d80-107">관리 워크플로의 위임된 응답 그룹 관리자 중 하나인 경우 응답 그룹 큐를 만들거나 수정하고 여러분이 관리하는 워크플로에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-107">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="04d80-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="04d80-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04d80-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="04d80-110">왼쪽 탐색 모음에서 **응답 그룹**을 클릭하고 **큐**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-110">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="04d80-111">**큐** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-111">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="04d80-112">새 큐를 만들려면 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-112">To create a new queue, click **New**.</span></span> <span data-ttu-id="04d80-113">**서비스 선택**에서 검색 필드에 큐를 추가할 **ApplicationServer** 서비스의 이름 일부나 전체를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-113">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="04d80-114">서비스 결과 목록에서 원하는 서비스를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="04d80-p103">기존 큐를 수정하려면 검색 필드에 큐의 이름을 모두 또는 일부분 입력합니다. 결과 큐 목록에서 원하는 큐를 클릭하고 **편집**을 클릭한 다음 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="04d80-117">**이름**에 큐를 식별하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-117">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="04d80-118">**설명**에 큐의 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-118">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="04d80-p104">**그룹**에서 큐를 할당할 그룹을 지정합니다. 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span>
    
      - <span data-ttu-id="04d80-p105">큐에 그룹을 추가하려면 **선택**을 클릭하고 **그룹 선택** 검색 필드에 큐에 할당할 에이전트 그룹의 이름을 일부분 또는 모두 입력한 다음 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="04d80-123">큐에서 그룹을 제거하려면 에이전트 그룹 목록에서 제거할 그룹을 클릭한 다음 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-123">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="04d80-124">에이전트가 검색되는 순서를 변경하려면 에이전트 그룹 목록에서 그룹을 클릭한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-124">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="04d80-p106">서버는 큐에서 사용 가능한 에이전트를 검색할 때 그룹 순서를 사용합니다. 즉, 목록의 첫 번째 그룹이 먼저 검색되고 목록의 두 번째 그룹 등이 차례로 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="04d80-127">에이전트가 전화를 받을 때까지 발신자가 대기하도록 할 최대 시간을 지정하려면 **큐 시간 초과 사용** 확인란을 선택하고 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-127">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="04d80-128">**제한 시간(초)** 에서 에이전트가 전화를 받을 때까지 발신자가 대기하는 최대 시간(초)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-128">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="04d80-129">**통화 작업**에서 통화 시간이 초과되면 수행할 작업을 다음 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-129">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="04d80-130">제한 시간 이후에 전화를 끊으려면 **연결 끊기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-130">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="04d80-131">통화를 음성 메일로 착신 전환 하려면 **음성 메일로 착신 전환**을 클릭 한 다음 **sip 주소** 필드에 음성 메일 사용자\<이름\>@\<domainname\> 을 입력 합니다 (예: sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="04d80-131">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="04d80-132">통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 착신 전환을**클릭 한 다음 **sip 주소** \<필드에 전화 번호를 sip: number\>@\<domainname\> (예: sip:+14255550121@contoso.com) 형식으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-132">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="04d80-133">통화를 다른 사용자에 게 착신 전환 하려면 sip **주소로 전달을**클릭 한 다음 **sip 주소** 필드에 사용자의 URI를 sip\<: username\>@\<도메인\>형식으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-133">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="04d80-134">통화를 다른 큐로 착신 전환하려면 **다른 큐로 착신 전환**을 클릭한 다음 사용할 큐를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-134">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="04d80-135">큐에 보관할 최대 통화 수를 지정하려면 **큐 오버플로 사용** 확인란을 선택하고 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-135">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="04d80-136">**최대 통화 수**에서 큐에 보관할 최대 통화 수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-136">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="04d80-137">**착신 전환**에서 큐가 가득 차면 착신 전환할 통화를 **가장 최근 통화** 또는 **가장 오래된 통화** 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-137">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="04d80-138">**통화 작업**에서 오버플로 임계값에 도달하면 수행할 작업을 다음 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-138">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="04d80-139">제한 시간 이후에 전화를 끊으려면 **연결 끊기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-139">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="04d80-140">통화를 음성 메일로 착신 전환 하려면 **음성 메일로 착신 전환**을 클릭 한 다음 **sip 주소** 필드에 음성 메일 사용자\<이름\>@\<domainname\> 을 입력 합니다 (예: sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="04d80-140">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="04d80-141">통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 착신 전환을**클릭 한 다음 **sip 주소** \<필드에 전화 번호를 sip: number\>@\<domainname\> (예: sip:+14255550121@contoso.com) 형식으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-141">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="04d80-142">통화를 다른 사용자에 게 착신 전환 하려면 sip **주소로 전달을**클릭 한 다음 **sip 주소** 필드에 사용자의 URI를 sip\<: username\>@\<도메인\>형식으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-142">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="04d80-143">통화를 다른 큐로 착신 전환하려면 **다른 큐로 착신 전환**을 클릭한 다음 사용할 큐를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-143">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="04d80-144">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-144">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="04d80-145">Windows PowerShell을 사용 하 여 큐를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="04d80-145">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="04d80-146">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-146">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04d80-147">관리 워크플로의 위임된 응답 그룹 관리자 중 하나인 경우 에이전트 그룹을 만들 에이전트 그룹을 큐에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-147">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="04d80-148">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="04d80-p107">명령줄에서 다음을 실행하여 큐 시간 초과 임계값에 도달하면 재생할 음성 안내를 만들고 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-p107">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="04d80-151">예:</span><span class="sxs-lookup"><span data-stu-id="04d80-151">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04d80-152">오디오 파일을 음성 안내에 사용하려면 <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-152">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="04d80-153">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">import-csrgsaudiofile</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04d80-153">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="04d80-p109">명령줄에서 다음을 실행하여 큐 시간 초과 임계값에 도달하면 수행할 동작을 정의하고 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-p109">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04d80-156">가능한 작업 및 해당 구문에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">new-csrgscallaction</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04d80-156">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="04d80-157">예:</span><span class="sxs-lookup"><span data-stu-id="04d80-157">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="04d80-p110">명령줄에서 다음을 실행하여 큐 오버플로 임계값에 도달하면 재생할 음성 안내를 만들고 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-p110">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="04d80-160">예:</span><span class="sxs-lookup"><span data-stu-id="04d80-160">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04d80-161">오디오 파일을 음성 안내에 사용하려면 <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-161">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="04d80-162">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">import-csrgsaudiofile</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04d80-162">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="04d80-p112">명령줄에서 다음을 실행하여 큐 오버플로 임계값에 도달하면 수행할 동작을 정의하고 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-p112">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04d80-165">가능한 작업 및 해당 구문에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">new-csrgscallaction</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04d80-165">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="04d80-166">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-166">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="04d80-167">응답 그룹 서비스의 서비스 이름을 검색하여 변수 하나에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-167">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="04d80-168">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-168">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="04d80-169">큐에 할당할 에이전트 그룹의 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-169">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="04d80-170">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-170">At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="04d80-171">에이전트 그룹을 만드는 방법에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">get-csrgsagentgroup</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="04d80-171">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="04d80-p115">명령줄에서 다음을 실행하여 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-p115">Create the queue. At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="04d80-174">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-174">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="04d80-p116">다음을 실행하여 큐가 만들어졌는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-p116">Confirm that the queue is created. Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="04d80-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04d80-177">See Also</span></span>


[<span data-ttu-id="04d80-178">Get-csrgsqueue</span><span class="sxs-lookup"><span data-stu-id="04d80-178">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="04d80-179">Get-csrgsqueue</span><span class="sxs-lookup"><span data-stu-id="04d80-179">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="04d80-180">New-csrgsprompt</span><span class="sxs-lookup"><span data-stu-id="04d80-180">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="04d80-181">New-csrgscallaction</span><span class="sxs-lookup"><span data-stu-id="04d80-181">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="04d80-182">Get-csrgsqueue</span><span class="sxs-lookup"><span data-stu-id="04d80-182">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="04d80-183">Import-csrgsaudiofile</span><span class="sxs-lookup"><span data-stu-id="04d80-183">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="04d80-184">Get-csrgsqueue을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="04d80-184">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

