---
title: 비즈니스용 Skype에서 큐 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: 비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 큐를 만들거나 수정 합니다.
ms.openlocfilehash: b58ec9065eea1cc2dd8686b07ea798ac71c460fa
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233677"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="a3b6b-103">비즈니스용 Skype에서 큐 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="a3b6b-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="a3b6b-104">비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 큐를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="a3b6b-105">큐는 에이전트가 전화를 대답할 때까지 호출자를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="a3b6b-106">응답 그룹 응용 프로그램이 사용 가능한 에이전트를 검색 하는 경우 목록에 나열 된 순서 대로 에이전트 그룹을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="a3b6b-107">큐에 할당 되는 에이전트 그룹을 선택 하 고 큐에 대기 시킬 수 있는 호출 수를 제한 하는 방법, 에이전트가 전화를 받을 때까지 대기 하는 시간 간격 등의 대기열 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="a3b6b-108">다음 절차 중 하나를 사용 하 여 큐를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="a3b6b-109">비즈니스용 Skype Server 제어판을 사용 하 여 큐를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="a3b6b-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="a3b6b-110">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a3b6b-111">관리 되는 워크플로에 대 한 위임 된 응답 그룹 관리자 중 하나에 해당 하는 경우 응답 그룹 큐를 만들거나 수정 하 고 관리 하는 워크플로에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="a3b6b-112">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a3b6b-113">왼쪽 탐색 모음에서 **응답 그룹**을 클릭 한 다음 **대기열**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="a3b6b-114">**큐** 페이지에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="a3b6b-115">새 큐를 만들려면 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="a3b6b-116">**서비스 선택**에서 검색 필드에 큐를 추가 하려는 **applicationserver** 서비스 이름의 일부나 전부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="a3b6b-117">서비스 결과 목록에서 원하는 서비스를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="a3b6b-118">기존 대기열을 수정 하려면 검색 필드에 대기열 이름 전체 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-118">To modify an existing queue, type all or part of the queue name in the search field.</span></span> <span data-ttu-id="a3b6b-119">결과 대기열 목록에서 원하는 대기열을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-119">In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a3b6b-120">**이름**에 큐 식별 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="a3b6b-121">**설명**에 대기열에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="a3b6b-122">**그룹**에서 큐에 할당 하려는 그룹을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-122">In **Groups**, specify the groups you want to assign to the queue.</span></span> <span data-ttu-id="a3b6b-123">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-123">Do one of the following:</span></span> 
    
   - <span data-ttu-id="a3b6b-124">큐에 그룹을 추가 하려면 **선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-124">To add a group to the queue, click **Select**.</span></span> <span data-ttu-id="a3b6b-125">그룹 검색 **선택** 필드에 큐에 할당할 에이전트 그룹의 이름 전체 또는 일부를 입력 하 고 원하는 에이전트 그룹을 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-125">In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="a3b6b-126">큐에서 그룹을 제거 하려면 에이전트 그룹 목록에서 제거 하려는 그룹을 클릭 한 다음 **제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="a3b6b-127">에이전트를 검색 하는 순서를 변경 하려면 에이전트 그룹 목록에서 그룹을 클릭 한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="a3b6b-128">서버에서 큐에 대해 사용 가능한 에이전트를 검색할 때 그룹 순서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-128">When the server searches for an available agent for the queue, it uses group order.</span></span> <span data-ttu-id="a3b6b-129">즉, 목록의 첫 번째 그룹이 먼저 검색 되 고, 그 다음에 목록의 두 번째 그룹이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-129">That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="a3b6b-130">에이전트가 전화에 응답 하기 전에 호출자가 대기를 대기할 최대 기간을 지정 하려면 **큐 시간 초과 사용** 확인란을 선택 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="a3b6b-131">에서.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-131">a.</span></span> <span data-ttu-id="a3b6b-132">**시간 제한 (초)** 에 호출자가 상담원의 전화 응답을 대기할 수 있는 최대 시간 (초)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="a3b6b-133">b.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-133">b.</span></span> <span data-ttu-id="a3b6b-134">**통화 동작**에서 다음과 같이 통화 시간이 초과 될 때 발생 하는 동작을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="a3b6b-135">제한 시간 후에 통화 연결을 끊으려면 **연결 끊기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="a3b6b-136">음성 메일로 통화를 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 **sip 주소** 필드에 sip: \* \<username (사용자 이름\>\*\*\<\> \* @ domainname) 형식으로 음성 메일 주소를 입력 합니다. 예: sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a3b6b-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="a3b6b-137">통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 **sip 주소** 필드에 sip: \* \<number\>\*@ *\<\>* (예: sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a3b6b-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="a3b6b-138">다른 사용자에 게 통화를 착신 전환 하려면 **sip 주소로 전달을**클릭 한 다음 **sip 주소** 필드에 sip: _ \<username\>_@ _\<domainname\>_ 형식으로 사용자의 URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="a3b6b-139">다른 대기열로 통화를 착신 전환 하려면 **다른 대기열로 전달을**클릭 한 다음 사용 하려는 대기열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="a3b6b-140">큐에 저장할 수 있는 최대 통화 수를 지정 하려면 **큐 오버플로 사용** 확인란을 선택 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="a3b6b-141">에서.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-141">a.</span></span> <span data-ttu-id="a3b6b-142">**최대 통화 수**에서 큐에 대기 시킬 최대 통화 수를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="a3b6b-143">b.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-143">b.</span></span> <span data-ttu-id="a3b6b-144">**통화를 착신 전환**하는 동안 큐가 꽉 차면 착신 전환 되는 통화를 선택 합니다. **최신** 통화 또는 **가장 오래 된 통화**입니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="a3b6b-145">c.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-145">c.</span></span> <span data-ttu-id="a3b6b-146">**통화 동작**에서 오버플로 임계값이 다음과 같이 충족 될 때 발생 하는 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="a3b6b-147">제한 시간 후에 통화 연결을 끊으려면 **연결 끊기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="a3b6b-148">음성 메일로 통화를 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 **sip 주소** 필드에 sip: \* \<username (사용자 이름\>\*\*\<\> \* @ domainname) 형식으로 음성 메일 주소를 입력 합니다. 예: sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a3b6b-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="a3b6b-149">통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 **sip 주소** 필드에 sip: \* \<number\>\*@ *\<\>* (예: sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="a3b6b-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="a3b6b-150">다른 사용자에 게 통화를 착신 전환 하려면 **sip 주소로 전달을**클릭 한 다음 **sip 주소** 필드에 sip: _ \<username\>_@ _\<domainname\>_ 형식으로 사용자의 URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="a3b6b-151">다른 대기열로 통화를 착신 전환 하려면 **다른 대기열로 전달을**클릭 한 다음 사용 하려는 대기열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="a3b6b-152">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="a3b6b-153">비즈니스용 Skype Server Management Shell을 사용 하 여 큐를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="a3b6b-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="a3b6b-154">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a3b6b-155">관리 되는 워크플로에 대해 위임 된 응답 그룹 관리자 중 하나에 해당 하는 경우 에이전트 그룹 및 큐를 만들고 에이전트 그룹을 큐에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="a3b6b-156">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a3b6b-157">큐 시간 제한 임계값에 도달 했을 때 재생할 프롬프트를 만들고 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-157">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="a3b6b-158">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-158">At the command line, run:</span></span>
    
   ```
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="a3b6b-159">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-159">For example:</span></span>
    
   ```
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="a3b6b-160">프롬프트에 오디오 파일을 사용 하려면 **CsRgsAudioFile** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="a3b6b-161">자세한 내용은 [가져오기-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-161">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="a3b6b-162">큐 시간 제한 임계값에 도달 했을 때 수행할 작업을 정의 하 고 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-162">Define the action to be taken when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="a3b6b-163">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-163">At the command line, run:</span></span>
    
   ```
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="a3b6b-164">사용할 수 있는 동작과 해당 구문에 대 한 자세한 내용은 [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="a3b6b-165">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-165">For example:</span></span>
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="a3b6b-166">큐 오버플로 임계값에 도달 했을 때 재생 되는 프롬프트를 만들고 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-166">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="a3b6b-167">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-167">At the command line, run:</span></span>
    
   ```
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="a3b6b-168">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-168">For example:</span></span>
    
   ```
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="a3b6b-169">프롬프트에 오디오 파일을 사용 하려면 **CsRgsAudioFile** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="a3b6b-170">자세한 내용은 [가져오기-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-170">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="a3b6b-171">큐 오버플로 임계값에 도달 했을 때 수행할 작업을 정의 하 고 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-171">Define the action to be taken when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="a3b6b-172">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-172">At the command line, run:</span></span>
    
   ```
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="a3b6b-173">사용할 수 있는 동작과 해당 구문에 대 한 자세한 내용은 [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="a3b6b-174">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-174">For example:</span></span>
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="a3b6b-175">응답 그룹 서비스의 서비스 이름을 검색 하 고 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-175">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="a3b6b-176">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-176">At the command line, run:</span></span>
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="a3b6b-177">큐에 할당할 에이전트 그룹의 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-177">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="a3b6b-178">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-178">At the command line, run:</span></span>
    
   ```
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="a3b6b-179">에이전트 그룹을 만드는 방법에 대 한 자세한 내용은 [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-179">For details about creating the agent group, see [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="a3b6b-180">큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-180">Create the queue.</span></span> <span data-ttu-id="a3b6b-181">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-181">At the command line, run:</span></span>
    
   ```
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="a3b6b-182">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-182">For example:</span></span>
    
   ```
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="a3b6b-183">대기열이 생성 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3b6b-183">Confirm that the queue is created.</span></span> <span data-ttu-id="a3b6b-184">런</span><span class="sxs-lookup"><span data-stu-id="a3b6b-184">Run:</span></span>
    
    ```
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="a3b6b-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3b6b-185">See also</span></span>

[<span data-ttu-id="a3b6b-186">새로운 CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="a3b6b-186">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="a3b6b-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="a3b6b-187">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="a3b6b-188">새로운 CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="a3b6b-188">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="a3b6b-189">새로운 CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="a3b6b-189">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="a3b6b-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="a3b6b-190">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="a3b6b-191">가져오기-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="a3b6b-191">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="a3b6b-192">제거-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="a3b6b-192">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
