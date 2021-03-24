---
title: 비즈니스용 Skype에서 큐 만들기 또는 수정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: 비즈니스용 Skype 서버 2016에서 응답 그룹 큐를 만들거나 Enterprise Voice.
ms.openlocfilehash: b355cde0d8a99938538488152276a6c8eb4c6d4b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103584"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="c555e-103">비즈니스용 Skype에서 큐 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="c555e-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="c555e-104">비즈니스용 Skype 서버 2016에서 응답 그룹 큐를 만들거나 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c555e-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="c555e-105">큐는 에이전트가 통화에 응답할 때까지 발신자를 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="c555e-106">응답 그룹 응용 프로그램은 사용 가능한 에이전트를 검색할 때 에이전트 그룹을 나열하는 순서대로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="c555e-107">큐에 지정되는 에이전트 그룹을 선택할 수 있으며, 큐에 보관할 수 있는 통화 수 및 에이전트가 통화에 응답할 때까지의 통화 대기 시간을 제한하는 등 큐 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="c555e-108">다음 절차를 사용하여 큐를 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="c555e-109">비즈니스용 Skype 서버 제어판을 사용하여 큐를 만들거나 수정하려면</span><span class="sxs-lookup"><span data-stu-id="c555e-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="c555e-110">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c555e-111">관리 워크플로의 위임된 응답 그룹 관리자 중 하나인 경우 응답 그룹 큐를 만들거나 수정하고 여러분이 관리하는 워크플로에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="c555e-112">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="c555e-113">왼쪽 탐색 모음에서 **응답 그룹** 을 클릭하고 **큐** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="c555e-114">**큐** 페이지에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="c555e-115">새 큐를 만들려면 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="c555e-116">**서비스 선택** 에서 검색 필드에 큐를 추가할 **ApplicationServer** 서비스의 이름 일부나 전체를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="c555e-117">서비스 결과 목록에서 원하는 서비스를 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="c555e-p103">기존 큐를 수정하려면 검색 필드에 큐의 이름을 모두 또는 일부분 입력합니다. 결과 큐 목록에서 원하는 큐를 클릭하고 **편집** 을 클릭한 다음 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c555e-120">**이름** 에 큐를 식별하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="c555e-121">**설명** 에 큐의 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="c555e-p104">**그룹** 에서 큐를 할당할 그룹을 지정합니다. 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span> 
    
   - <span data-ttu-id="c555e-p105">큐에 그룹을 추가하려면 **선택** 을 클릭하고 **그룹 선택** 검색 필드에 큐에 할당할 에이전트 그룹의 이름을 일부분 또는 모두 입력한 다음 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="c555e-126">큐에서 그룹을 제거하려면 에이전트 그룹 목록에서 제거할 그룹을 클릭한 다음 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="c555e-127">에이전트가 검색되는 순서를 변경하려면 에이전트 그룹 목록에서 그룹을 클릭한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="c555e-p106">서버는 큐에서 사용 가능한 에이전트를 검색할 때 그룹 순서를 사용합니다. 즉, 목록의 첫 번째 그룹이 먼저 검색되고 목록의 두 번째 그룹 등이 차례로 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="c555e-130">에이전트가 전화를 받을 때까지 발신자가 대기하도록 할 최대 시간을 지정하려면 **큐 시간 초과 사용** 확인란을 선택하고 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="c555e-131">a.</span><span class="sxs-lookup"><span data-stu-id="c555e-131">a.</span></span> <span data-ttu-id="c555e-132">**제한 시간(초)** 에서 에이전트가 전화를 받을 때까지 발신자가 대기하는 최대 시간(초)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="c555e-133">b.</span><span class="sxs-lookup"><span data-stu-id="c555e-133">b.</span></span> <span data-ttu-id="c555e-134">**통화 작업** 에서 통화 시간이 초과되면 수행할 작업을 다음 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="c555e-135">제한 시간 이후에 전화를 끊으려면 **연결 끊기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="c555e-136">통화를 음성 메일로 전달하려면 음성 메일로 전달을 클릭한 다음 **SIP** 주소 필드에 음성 메일 주소를 sip: 형식으로 입력합니다(예:  *\<username\>* @  *\<domainname\>* sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c555e-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="c555e-137">통화를 다른 전화 번호로 전달하려면 전화 번호로 전달을 클릭한 다음 **SIP** 주소 필드에 전화 번호를 sip: 형식으로 입력합니다(예: *\<number\>* @  *\<domainname\>* sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c555e-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="c555e-138">통화를 다른 사용자에게 전달하려면 **SIP** 주소로 전달을 클릭한 다음 **SIP** 주소 필드에 사용자의 URI를 sip: 형식으로 입력합니다. _\<username\>_ @  _\<domainname\>_</span><span class="sxs-lookup"><span data-stu-id="c555e-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="c555e-139">통화를 다른 큐로 착신 전환하려면 **다른 큐로 착신 전환** 을 클릭한 다음 사용할 큐를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="c555e-140">큐에 보관할 최대 통화 수를 지정하려면 **큐 오버플로 사용** 확인란을 선택하고 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="c555e-141">a.</span><span class="sxs-lookup"><span data-stu-id="c555e-141">a.</span></span> <span data-ttu-id="c555e-142">**최대 통화 수** 에서 큐에 보관할 최대 통화 수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="c555e-143">b.</span><span class="sxs-lookup"><span data-stu-id="c555e-143">b.</span></span> <span data-ttu-id="c555e-144">**착신 전환** 에서 큐가 가득 차면 착신 전환할 통화를 **가장 최근 통화** 또는 **가장 오래된 통화** 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="c555e-145">c.</span><span class="sxs-lookup"><span data-stu-id="c555e-145">c.</span></span> <span data-ttu-id="c555e-146">**통화 작업** 에서 오버플로 임계값에 도달하면 수행할 작업을 다음 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="c555e-147">제한 시간 이후에 전화를 끊으려면 **연결 끊기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="c555e-148">통화를 음성 메일로 전달하려면 음성 메일로 전달을 클릭한 다음 **SIP** 주소 필드에 음성 메일 주소를 sip: 형식으로 입력합니다(예:  *\<username\>* @  *\<domainname\>* sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c555e-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="c555e-149">통화를 다른 전화 번호로 전달하려면 전화 번호로 전달을 클릭한 다음 **SIP** 주소 필드에 전화 번호를 sip: 형식으로 입력합니다(예: *\<number\>* @  *\<domainname\>* sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c555e-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="c555e-150">통화를 다른 사용자에게 전달하려면 **SIP** 주소로 전달을 클릭한 다음 **SIP** 주소 필드에 사용자의 URI를 sip: 형식으로 입력합니다. _\<username\>_ @  _\<domainname\>_</span><span class="sxs-lookup"><span data-stu-id="c555e-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="c555e-151">통화를 다른 큐로 착신 전환하려면 **다른 큐로 착신 전환** 을 클릭한 다음 사용할 큐를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="c555e-152">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="c555e-153">비즈니스용 Skype 서버 관리 셸을 사용하여 큐를 만들거나 수정하려면</span><span class="sxs-lookup"><span data-stu-id="c555e-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="c555e-154">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c555e-155">관리 워크플로의 위임된 응답 그룹 관리자 중 하나인 경우 에이전트 그룹을 만들 에이전트 그룹을 큐에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="c555e-156">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="c555e-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c555e-p112">명령줄에서 다음을 실행하여 큐 시간 초과 임계값에 도달하면 재생할 음성 안내를 만들고 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-p112">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="c555e-159">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-159">For example:</span></span>
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="c555e-160">오디오 파일을 음성 안내에 사용하려면 **Import-CsRgsAudioFile** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="c555e-161">자세한 내용은 [Import-CsRgsAudioFile을 참조합니다.](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c555e-161">For details, see [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="c555e-p114">명령줄에서 다음을 실행하여 큐 시간 초과 임계값에 도달하면 수행할 동작을 정의하고 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-p114">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="c555e-164">가능한 작업 및 구문에 대한 자세한 내용은 [New-CsRgsCallAction을 참조하세요.](/powershell/module/skype/new-csrgscallaction?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c555e-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="c555e-165">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-165">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="c555e-p115">명령줄에서 다음을 실행하여 큐 오버플로 임계값에 도달하면 재생할 음성 안내를 만들고 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-p115">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="c555e-168">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-168">For example:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="c555e-169">오디오 파일을 음성 안내에 사용하려면 **Import-CsRgsAudioFile** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="c555e-170">자세한 내용은 [Import-CsRgsAudioFile을 참조합니다.](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c555e-170">For details, see [Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="c555e-p117">명령줄에서 다음을 실행하여 큐 오버플로 임계값에 도달하면 수행할 동작을 정의하고 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-p117">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="c555e-173">가능한 작업 및 구문에 대한 자세한 내용은 [New-CsRgsCallAction을 참조하세요.](/powershell/module/skype/new-csrgscallaction?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c555e-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="c555e-174">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-174">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="c555e-175">응답 그룹 서비스의 서비스 이름을 검색하여 변수 하나에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-175">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="c555e-176">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-176">At the command line, run:</span></span>
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="c555e-177">큐에 할당할 에이전트 그룹의 ID를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-177">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="c555e-178">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-178">At the command line, run:</span></span>
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="c555e-179">에이전트 그룹을 만드는 데 대한 자세한 내용은 [New-CsRgsAgentGroup을 참조합니다.](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c555e-179">For details about creating the agent group, see [New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="c555e-p120">명령줄에서 다음을 실행하여 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-p120">Create the queue. At the command line, run:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="c555e-182">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-182">For example:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="c555e-p121">다음을 실행하여 큐가 만들어졌는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c555e-p121">Confirm that the queue is created. Run:</span></span>
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="c555e-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c555e-185">See also</span></span>

[<span data-ttu-id="c555e-186">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="c555e-186">New-CsRgsQueue</span></span>](/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="c555e-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="c555e-187">Set-CsRgsQueue</span></span>](/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="c555e-188">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="c555e-188">New-CsRgsPrompt</span></span>](/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="c555e-189">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="c555e-189">New-CsRgsCallAction</span></span>](/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="c555e-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="c555e-190">Get-CsRgsQueue</span></span>](/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="c555e-191">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="c555e-191">Import-CsRgsAudioFile</span></span>](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="c555e-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="c555e-192">Remove-CsRgsQueue</span></span>](/powershell/module/skype/remove-csrgsqueue?view=skype-ps)