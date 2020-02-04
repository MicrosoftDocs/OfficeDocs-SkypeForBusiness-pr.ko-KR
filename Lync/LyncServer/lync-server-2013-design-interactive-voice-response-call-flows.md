---
title: 'Lync Server 2013: 대화형 음성 응답 통화 흐름 설계'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd53ac8d06ec336940abe53d7da1353faf4f9414
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="b1894-102">Lync Server 2013에서 대화형 음성 응답 통화 흐름 설계</span><span class="sxs-lookup"><span data-stu-id="b1894-102">Design interactive voice response call flows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1894-103">_**마지막으로 수정한 주제:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="b1894-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="b1894-104">IVR (대화형 음성 응답)을 사용 하 여 발신자의 정보를 얻고 해당 큐로 전화를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-104">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="b1894-105">질문 및 답변 쌍에 따라 사용할 대기열이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-105">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="b1894-106">호출자의 응답에 따라 호출자가 후속 질문을 알리거나 해당 큐에 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-106">Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="b1894-107">IVR 질문이 나 발신자의 응답은 통화를 수락 하는 응답 에이전트에 제공 되며, 상담원에 게 중요 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-107">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="b1894-108">IVR 기능 개요</span><span class="sxs-lookup"><span data-stu-id="b1894-108">Overview of IVR Features</span></span>

<span data-ttu-id="b1894-109">응답 그룹 응용 프로그램은 26 개 언어의 음성 인식 및 텍스트 음성 변환 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-109">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="b1894-110">텍스트 음성 변환 또는 웨이브 (.wav) 또는 Windows Media 오디오 (.wma) 파일을 사용 하 여 IVR 질문을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-110">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="b1894-111">발신자는 음성 또는 DTMF (multifrequency) 응답을 사용 하 여 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-111">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="b1894-112">대화형 워크플로는 두 가지 수준의 질문을 지원 하며 각 질문에 대 한 답변은 4 개까지 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-112">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="b1894-113">IVR은 호출자에 게 질문을 하 고 호출자의 응답에 따라 호출자를 큐에 라우팅하고 또는 두 번째 질문을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-113">The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="b1894-114">두 번째 질문에는 네 가지 가능한 답을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-114">The second question can also have four possible answers.</span></span> <span data-ttu-id="b1894-115">두 번째 수준 질문에 대 한 응답에 따라 호출자가 적절 한 큐로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-115">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b1894-116">Lync Server Management Shell을 사용 하 여 통화 흐름을 디자인 하는 경우 다양 한 수의 IVR 질문 및 답변을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-116">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="b1894-117">그러나 호출자의 사용 편리성을 위해 각각 6 개 이상의 질문을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="b1894-118">또한 세 개 이상의 질문에 대 한 통화 흐름을 디자인 하는 경우 각각 다섯 명 이상의 답변을 사용할 경우 Lync Server 2013 제어판을 사용 하 여 통화 흐름을 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-118">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="b1894-119">IVR 질문이 나 발신자의 응답은 통화를 수락 하는 응답 하는 상담원에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-119">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="b1894-120">음성 기술 사용</span><span class="sxs-lookup"><span data-stu-id="b1894-120">Working with Speech Technologies</span></span>

<span data-ttu-id="b1894-121">음성 인식과 텍스트 음성 변환 등의 음성 기술은 고객 환경을 개선 하 고 사람들이 정보에 더욱 자연스럽 게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-121">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="b1894-122">그러나 음성 엔진에서 지정 된 텍스트 또는 사용자 음성 응답을 올바르게 인식 하지 못하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-122">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="b1894-123">예를 들어 "\#" 기호는 텍스트 음성 변환 엔진에 의해 "number" 라는 단어로 번역 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-123">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="b1894-124">이 문제는 다음과 같은 방법으로 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-124">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="b1894-125">음성 엔진은 발신자의 5 회 질문에 대 한 답변을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-125">The speech engine gives the caller five attempts to answer the question.</span></span> <span data-ttu-id="b1894-126">발신자가 질문에 잘못 대답 하거나 (즉, 답변이 지정 된 응답 중 하나가 아님) 대답을 제공 하지 않으면 호출자가 질문에 대답할 수 있는 또 다른 기회를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-126">If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question.</span></span> <span data-ttu-id="b1894-127">발신자는 연결이 끊어지기 전에 질문에 대 한 답변을 5 회 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-127">The caller has five attempts to answer the question before being disconnected.</span></span> <span data-ttu-id="b1894-128">각 발신자 오류 발생 후 사용자 지정 메시지를 재생 하도록 IVR을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-128">You can configure the IVR to play a customized message after each caller error.</span></span> <span data-ttu-id="b1894-129">질문은 매번 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-129">The question is repeated each time.</span></span>

  - <span data-ttu-id="b1894-130">음성 엔진에서 응답으로 앰비언트 노이즈가 해석 될 가능성을 최소화 하려면 긴 응답을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-130">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses.</span></span> <span data-ttu-id="b1894-131">예를 들어 답은 두 개 이상 음절을가지고 있으며 서로 크게 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-131">For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="b1894-132">질문에 음성 및 DTMF 응답이 둘 다 있는 경우 DTMF 응답 대신 개념을 나타내는 단어를 사용 하 여 음성 응답을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-132">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response.</span></span> <span data-ttu-id="b1894-133">예를 들어 "누르기"를 사용 하는 대신 "단 1 또는 대금 청구"를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-133">For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="b1894-134">IVR을 디자인 한 후에는 워크플로를 호출 하 고, 메시지를 듣고, 음성을 사용 하는 각 프롬프트에 응답 하 고, IVR의 사운드가 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-134">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="b1894-135">그런 다음 IVR을 수정 하 여 해석 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-135">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="b1894-136">앞의 예제를 따라 \# 키를 참조 해야 하는 경우에는 \# 기호 대신 키 이름을 사용 하도록 IVR 프롬프트를 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-136">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="b1894-137">예를 들어 "영업부와 대화 하려면 우물 정자" 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-137">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="b1894-138">IVR 디자인 예제</span><span class="sxs-lookup"><span data-stu-id="b1894-138">IVR Design Examples</span></span>

<span data-ttu-id="b1894-139">다음 섹션에는 다양 한 IVR 시나리오 및 질문과 대답 쌍의 예가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-139">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="b1894-140">한 가지 수준의 질문이 있는 IVR</span><span class="sxs-lookup"><span data-stu-id="b1894-140">IVR with One Level of Questions</span></span>

<span data-ttu-id="b1894-141">다음 예제에서는 한 가지 수준의 질문을 사용 하는 IVR을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-141">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="b1894-142">음성 인식을 사용 하 여 발신자의 응답을 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-142">It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="b1894-143">**질문:** "인적 자원을 통화 해 주셔서 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-143">**Question:** "Thank you for calling Human Resources.</span></span> <span data-ttu-id="b1894-144">급여에 대 한 통화를 원하시면 급여를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-144">If you would like to speak to payroll, say payroll.</span></span> <span data-ttu-id="b1894-145">그렇지 않으면 HR "이라고 말합니다."</span><span class="sxs-lookup"><span data-stu-id="b1894-145">Otherwise, say HR."</span></span>

  - <span data-ttu-id="b1894-146">**옵션 1이 선택 되어 있습니다.** 호출자는 급여 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-146">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="b1894-147">**옵션 2가 선택 되었습니다.** 발신자는 인적 자원 팀에 게 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-147">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="b1894-148">다음 그림은 통화 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-148">The following figure shows the call flow.</span></span>

<span data-ttu-id="b1894-149">**한 수준의 대화형 통화 흐름**</span><span class="sxs-lookup"><span data-stu-id="b1894-149">**One-level interactive call flow**</span></span>

<span data-ttu-id="b1894-150">![대화형 음성 응답을 사용하여 통화 흐름 설계](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "대화형 음성 응답을 사용하여 통화 흐름 설계")</span><span class="sxs-lookup"><span data-stu-id="b1894-150">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="b1894-151">두 가지 수준의 질문이 있는 IVR</span><span class="sxs-lookup"><span data-stu-id="b1894-151">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="b1894-152">다음 예제에서는 두 가지 수준의 질문을 사용 하는 IVR을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-152">The following example shows an IVR that uses two levels of questions.</span></span> <span data-ttu-id="b1894-153">이를 통해 발신자는 음성 또는 DTMF 키패드 입력을 사용 하 여 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-153">It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="b1894-154">**질문:** "IT 지원 센터에 전화 해 주셔서 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-154">**Question:** "Thank you for calling the IT Help Desk.</span></span> <span data-ttu-id="b1894-155">네트워크 액세스 문제가 있는 경우 1 번 누르거나 네트워크를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-155">If you have a network access problem, press 1 or say network.</span></span> <span data-ttu-id="b1894-156">소프트웨어 문제가 있는 경우 2 또는 말 소프트웨어를 누르세요.</span><span class="sxs-lookup"><span data-stu-id="b1894-156">If you have a software problem, press 2 or say software.</span></span> <span data-ttu-id="b1894-157">하드웨어 문제가 있는 경우 3 번을 누르거나 하드웨어를 말합니다. "</span><span class="sxs-lookup"><span data-stu-id="b1894-157">If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="b1894-158">**옵션 1이 선택 되어 있습니다.** 발신자는 네트워크 지원 팀에 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-158">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="b1894-159">**옵션 2가 선택 되었습니다.** 발신자에 게 후속 질문을 하는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-159">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="b1894-160">**질문:** "운영 체제 문제 라면 1 번을 누르거나 운영 체제를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-160">**Question:** "If this is an operating system problem, press 1 or say operating system.</span></span> <span data-ttu-id="b1894-161">내부 응용 프로그램에 문제가 있는 경우 2를 누르거나 내부 응용 프로그램을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-161">If this is a problem with an internal application, press 2 or say internal application.</span></span> <span data-ttu-id="b1894-162">그렇지 않으면 3을 누르거나 다른 단어를 말하기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-162">Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="b1894-163">**옵션 1이 선택 되어 있습니다.** 발신자는 운영 체제 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-163">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="b1894-164">**옵션 2가 선택 되었습니다.** 호출자는 내부 응용 프로그램 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-164">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="b1894-165">**옵션 3이 선택 되어 있습니다.** 발신자는 소프트웨어 지원 팀에 게 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-165">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="b1894-166">**옵션 3이 선택 되어 있습니다.** 발신자에 게 후속 질문을 하는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-166">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="b1894-167">**질문:** "프린터 문제인 경우 1을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-167">**Question:** "If this is a printer problem press 1.</span></span> <span data-ttu-id="b1894-168">그렇지 않으면 2를 누릅니다. "</span><span class="sxs-lookup"><span data-stu-id="b1894-168">Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="b1894-169">**옵션 1이 선택 되어 있습니다.** 발신자는 프린터 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-169">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="b1894-170">**옵션 2가 선택 되었습니다.** 발신자는 하드웨어 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-170">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="b1894-171">다음 그림은 통화 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-171">The following figure shows the call flow.</span></span>

<span data-ttu-id="b1894-172">**2 수준 대화형 통화 흐름**</span><span class="sxs-lookup"><span data-stu-id="b1894-172">**Two-level interactive call flow**</span></span>

<span data-ttu-id="b1894-173">![대화형 음성 응답을 사용하여 통화 흐름 설계](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "대화형 음성 응답을 사용하여 통화 흐름 설계")</span><span class="sxs-lookup"><span data-stu-id="b1894-173">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="b1894-174">모범 사례</span><span class="sxs-lookup"><span data-stu-id="b1894-174">Best Practices</span></span>

<span data-ttu-id="b1894-175">다음 목록에서는 IVR을 디자인 하기 위한 몇 가지 모범 사례에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-175">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="b1894-176">호출자가 작업에 빠르게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-176">Let the caller get to the task quickly.</span></span> <span data-ttu-id="b1894-177">IVR에 너무 많은 정보나 긴 마케팅 메시지를 제공 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b1894-177">Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="b1894-178">긴 메시지를 포함 하려는 경우 환영 메시지 대신 첫 번째 질문에 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-178">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message.</span></span> <span data-ttu-id="b1894-179">발신자는 질문에 대답 하 여 첫 번째 질문의 일부인 경우 메시지를 무시할 수 있지만,이 경우 환영 메시지를 우회할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-179">Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="b1894-180">발신자의 언어로 말합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-180">Speak in the caller’s language.</span></span> <span data-ttu-id="b1894-181">Stilted 언어를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b1894-181">Avoid stilted language.</span></span> <span data-ttu-id="b1894-182">자연스럽 게 말할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-182">Speak naturally.</span></span>

  - <span data-ttu-id="b1894-183">효율적이 고 효과적인 메시지를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-183">Write efficient and effective prompts.</span></span> <span data-ttu-id="b1894-184">불필요 한 옵션을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-184">Remove any unnecessary options.</span></span> <span data-ttu-id="b1894-185">호출자의 예상 응답이 문장의 끝에 오도록 정보를 구조화 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-185">Structure the information so that the caller’s expected response is at the end of the sentence.</span></span> <span data-ttu-id="b1894-186">예를 들어 영업 팀에 게 문의 하려면 1을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-186">For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="b1894-187">음성 응답을 사용자에 게 친숙 하 게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-187">Make voice responses user friendly.</span></span> <span data-ttu-id="b1894-188">예를 들어, DTMF 및 음성 응답을 모두 지정 하는 경우 "영업 팀에 게 말을 하려면 1을 누르고, 판매를 예로 들어"를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-188">For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="b1894-189">조직 전반에 배포 하기 전에 사용자 그룹에서 IVR을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1894-189">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

