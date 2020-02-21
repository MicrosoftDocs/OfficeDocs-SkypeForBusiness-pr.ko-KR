---
title: 'Lync Server 2013: 대화형 음성 응답 통화 흐름 디자인'
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
ms.openlocfilehash: 78032a23fce6bb210ecec6eb828178aabddf9b52
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a><span data-ttu-id="429f4-102">Lync Server 2013의 대화형 음성 응답 통화 흐름 디자인</span><span class="sxs-lookup"><span data-stu-id="429f4-102">Design interactive voice response call flows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="429f4-103">_**마지막으로 수정 된 항목:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="429f4-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="429f4-104">IVR (대화형 음성 응답)을 사용 하 여 발신자 로부터 정보를 가져오고 해당 큐로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-104">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="429f4-105">사용할 큐는 질문과 대답 쌍으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-105">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="429f4-106">발신자의 응답에 따라 발신자가 후속 질문을 듣게 되거나 해당 큐로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-106">Depending on the caller’s response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="429f4-107">IVR 질문과 발신자의 응답은 전화를 수락한 응답 에이전트에 제공 되어 에이전트에 중요 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-107">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

<div>

## <a name="overview-of-ivr-features"></a><span data-ttu-id="429f4-108">IVR 기능 개요</span><span class="sxs-lookup"><span data-stu-id="429f4-108">Overview of IVR Features</span></span>

<span data-ttu-id="429f4-109">응답 그룹 응용 프로그램은 26 가지 언어로 음성 인식과 텍스트 음성 변환 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-109">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="429f4-110">텍스트 음성 변환 또는 웨이브 (.wav) 또는 Windows Media 오디오 (.wma) 파일을 사용 하 여 IVR 질문을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-110">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="429f4-111">발신자는 음성 또는 DTMF (이중 톤 dual-tone multifrequency) 응답을 사용 하 여 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-111">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="429f4-112">대화형 워크플로는 최대 두 가지 수준의 질문을 지원하며, 각 질문에는 최대 4개의 가능한 응답이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-112">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="429f4-113">IVR은 발신자에 게 질문을 묻고 발신자의 응답에 따라 발신자를 큐로 라우트 하거나 두 번째 질문을 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-113">The IVR asks the caller a question, and depending on the caller’s response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="429f4-114">두 번째 질문 역시 가능한 응답은 4개입니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-114">The second question can also have four possible answers.</span></span> <span data-ttu-id="429f4-115">두 번째 수준의 질문에 대한 응답에 따라 적합한 큐로 발신자가 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-115">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="429f4-116">Lync Server 관리 셸을 사용 하 여 통화 흐름을 디자인 하는 경우 다양 한 수의 IVR 질문과 대답 및 수에 상관 없이 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-116">When you design call flows by using Lync Server Management Shell, you can define any number levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="429f4-117">그러나 발신자의 사용 가능성을 위해 최대 5 개 이상의 질문에 대 한 대답을 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-117">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="429f4-118">또한 두 개 이상의 질문에 대 한 답변을 세 개 이상 포함 하는 통화 흐름을 디자인 하는 경우에는 Lync Server 2013 제어판을 사용 하 여 통화 흐름을 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-118">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Lync Server 2013 Control Panel.</span></span>



</div>

<span data-ttu-id="429f4-119">IVR 질문과 발신자의 응답은 통화를 수락한 응답 에이전트에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-119">The IVR questions and the caller’s responses are provided to the responding agent who accepts the call.</span></span>

</div>

<div>

## <a name="working-with-speech-technologies"></a><span data-ttu-id="429f4-120">음성 기술 사용</span><span class="sxs-lookup"><span data-stu-id="429f4-120">Working with Speech Technologies</span></span>

<span data-ttu-id="429f4-121">음성 인식과 텍스트 음성 변환 같은 음성 기술은 사용자 환경을 개선 하 고 사람들이 보다 자연스럽 고 효과적으로 정보에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-121">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="429f4-122">그러나 음성 엔진에서 지정 된 텍스트 또는 사용자 음성 응답을 올바르게 인식 하지 못하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-122">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="429f4-123">예를 들어 "\#" 기호는 텍스트 음성 변환 엔진에서 단어 "number"로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-123">For example, the "\#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="429f4-124">이 문제는 다음과 같은 경우 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-124">This issue can be mitigated by the following:</span></span>

  - <span data-ttu-id="429f4-125">음성 엔진은 발신자에 게 질문에 대 한 답변을 5 회 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-125">The speech engine gives the caller five attempts to answer the question.</span></span> <span data-ttu-id="429f4-126">발신자가 질문에 대 한 답변을 잘못 했거나 (즉, 대답이 지정 된 응답에 해당 하지 않음) 대답을 제공 하지 않으면 발신자가 질문에 답변할 수 있는 또 다른 기회를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-126">If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question.</span></span> <span data-ttu-id="429f4-127">발신자가 연결을 끊기 전에 질문에 대 한 답변을 5 회 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-127">The caller has five attempts to answer the question before being disconnected.</span></span> <span data-ttu-id="429f4-128">각 발신자 오류가 발생 한 후 사용자 지정 된 메시지를 재생 하도록 IVR을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-128">You can configure the IVR to play a customized message after each caller error.</span></span> <span data-ttu-id="429f4-129">이 질문은 매번 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-129">The question is repeated each time.</span></span>

  - <span data-ttu-id="429f4-130">음성 엔진에서 응답으로 주위 노이즈가 해석 될 가능성을 최소화 하려면 긴 응답을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-130">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses.</span></span> <span data-ttu-id="429f4-131">예를 들어, 답은 둘 이상의 음절을 가져야 하며 서로 크게 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-131">For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

  - <span data-ttu-id="429f4-132">음성 및 DTMF 응답이 모두 있는 질문 인 경우 DTMF 응답 대신 개념을 나타내는 단어를 사용 하 여 음성 응답을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-132">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response.</span></span> <span data-ttu-id="429f4-133">예를 들어 "다음을 누르거나 말하기"를 사용 하는 대신 "다음을 누르세요."를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-133">For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

  - <span data-ttu-id="429f4-134">IVR을 디자인 한 후에는 워크플로를 호출 하 고 메시지를 듣고 음성을 사용 하는 각 음성 안내에 응답 하 고 IVR이 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-134">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="429f4-135">그런 다음 IVR을 수정 하 여 모든 해석 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-135">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="429f4-136">앞의 예제를 따라 \# 키를 참조 해야 하는 경우에는 \# 기호 대신 키 이름을 사용 하도록 IVR 프롬프트를 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-136">Following the previous example, if you need to refer to the \# key, you can rewrite your IVR prompt to use the key name, rather than the \# symbol.</span></span> <span data-ttu-id="429f4-137">예를 들어 "sales와 대화 하려면 파운드 키를 누릅니다."</span><span class="sxs-lookup"><span data-stu-id="429f4-137">For example, "To talk to sales, press the pound key."</span></span>

</div>

<div>

## <a name="ivr-design-examples"></a><span data-ttu-id="429f4-138">IVR 디자인 예제</span><span class="sxs-lookup"><span data-stu-id="429f4-138">IVR Design Examples</span></span>

<span data-ttu-id="429f4-139">다음 섹션에는 다양 한 IVR 시나리오 및 질문과 대답 쌍의 예가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-139">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

<div>

## <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="429f4-140">한 가지 수준의 질문이 있는 IVR</span><span class="sxs-lookup"><span data-stu-id="429f4-140">IVR with One Level of Questions</span></span>

<span data-ttu-id="429f4-141">다음 예에서는 한 가지 수준의 질문을 사용 하는 IVR을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-141">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="429f4-142">음성 인식을 사용 하 여 발신자의 응답을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-142">It uses speech recognition to detect the caller’s response.</span></span>

<span data-ttu-id="429f4-143">**질문:** "인적 자원 통화를 주셔서 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-143">**Question:** "Thank you for calling Human Resources.</span></span> <span data-ttu-id="429f4-144">급여를 지불 하려면 급여를 지불 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-144">If you would like to speak to payroll, say payroll.</span></span> <span data-ttu-id="429f4-145">그렇지 않으면 HR. "를 말합니다."</span><span class="sxs-lookup"><span data-stu-id="429f4-145">Otherwise, say HR."</span></span>

  - <span data-ttu-id="429f4-146">**옵션 1이 선택 되어 있습니다.** 발신자가 급여 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-146">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

  - <span data-ttu-id="429f4-147">**옵션 2가 선택 되어 있습니다.** 발신자가 인사 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-147">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="429f4-148">다음 그림에서는 통화 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-148">The following figure shows the call flow.</span></span>

<span data-ttu-id="429f4-149">**1 단계 대화형 통화 흐름**</span><span class="sxs-lookup"><span data-stu-id="429f4-149">**One-level interactive call flow**</span></span>

<span data-ttu-id="429f4-150">![대화형 음성 설계을 사용 하 여 통화 흐름 디자인](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "대화형 음성 설계을 사용 하 여 통화 흐름 디자인")</span><span class="sxs-lookup"><span data-stu-id="429f4-150">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="429f4-151">두 가지 수준의 질문이 있는 IVR</span><span class="sxs-lookup"><span data-stu-id="429f4-151">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="429f4-152">다음 예에서는 두 가지 수준의 질문을 사용 하는 IVR을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-152">The following example shows an IVR that uses two levels of questions.</span></span> <span data-ttu-id="429f4-153">이를 통해 발신자는 음성 또는 DTMF 키패드 입력을 사용 하 여 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-153">It allows callers to respond using either speech or DTMF keypad input.</span></span>

<span data-ttu-id="429f4-154">**질문:** "IT 지원 센터에 문의 해 주셔서 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-154">**Question:** "Thank you for calling the IT Help Desk.</span></span> <span data-ttu-id="429f4-155">네트워크 액세스 문제가 있는 경우 1을 누르거나 네트워크를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-155">If you have a network access problem, press 1 or say network.</span></span> <span data-ttu-id="429f4-156">소프트웨어 문제가 있는 경우 2를 누르거나 음성으로 소프트웨어를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-156">If you have a software problem, press 2 or say software.</span></span> <span data-ttu-id="429f4-157">하드웨어 문제가 있는 경우 3을 누르거나 하드웨어를 말합니다. "</span><span class="sxs-lookup"><span data-stu-id="429f4-157">If you have a hardware problem, press 3 or say hardware."</span></span>

  - <span data-ttu-id="429f4-158">**옵션 1이 선택 되어 있습니다.** 발신자가 네트워크 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-158">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

  - <span data-ttu-id="429f4-159">**옵션 2가 선택 되어 있습니다.** 발신자에 게 다음과 같은 질문을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-159">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="429f4-160">**질문:** "이 문제가 운영 체제 문제인 경우 1을 누르거나 운영 체제를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-160">**Question:** "If this is an operating system problem, press 1 or say operating system.</span></span> <span data-ttu-id="429f4-161">내부 응용 프로그램에 문제가 있는 경우에는 2를 누르거나 내부 응용 프로그램을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="429f4-161">If this is a problem with an internal application, press 2 or say internal application.</span></span> <span data-ttu-id="429f4-162">그렇지 않고 3을 누르거나 다른 단어를 말하기</span><span class="sxs-lookup"><span data-stu-id="429f4-162">Otherwise, press 3 or say other."</span></span>
    
      - <span data-ttu-id="429f4-163">**옵션 1이 선택 되어 있습니다.** 발신자가 운영 체제 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-163">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>
    
      - <span data-ttu-id="429f4-164">**옵션 2가 선택 되어 있습니다.** 발신자가 내부 응용 프로그램 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-164">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>
    
      - <span data-ttu-id="429f4-165">**옵션 3이 선택 되어 있습니다.** 발신자가 소프트웨어 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-165">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

  - <span data-ttu-id="429f4-166">**옵션 3이 선택 되어 있습니다.** 발신자에 게 다음과 같은 질문을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-166">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>
    
    <span data-ttu-id="429f4-167">**질문:** "프린터 문제인 경우 1을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-167">**Question:** "If this is a printer problem press 1.</span></span> <span data-ttu-id="429f4-168">그렇지 않으면 2를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-168">Otherwise, press 2."</span></span>
    
      - <span data-ttu-id="429f4-169">**옵션 1이 선택 되어 있습니다.** 발신자가 프린터 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-169">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>
    
      - <span data-ttu-id="429f4-170">**옵션 2가 선택 되어 있습니다.** 발신자가 하드웨어 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-170">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="429f4-171">다음 그림에서는 통화 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-171">The following figure shows the call flow.</span></span>

<span data-ttu-id="429f4-172">**2 수준 대화형 통화 흐름**</span><span class="sxs-lookup"><span data-stu-id="429f4-172">**Two-level interactive call flow**</span></span>

<span data-ttu-id="429f4-173">![대화형 음성 설계을 사용 하 여 통화 흐름 디자인](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "대화형 음성 설계을 사용 하 여 통화 흐름 디자인")</span><span class="sxs-lookup"><span data-stu-id="429f4-173">![Design Call Flows by Using Interactive Voice Respo](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "Design Call Flows by Using Interactive Voice Respo")</span></span>

</div>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="429f4-174">모범 사례</span><span class="sxs-lookup"><span data-stu-id="429f4-174">Best Practices</span></span>

<span data-ttu-id="429f4-175">다음 목록에서는 IVR 디자인을 위한 몇 가지 모범 사례에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-175">The following list describes some best practices for designing your IVR:</span></span>

  - <span data-ttu-id="429f4-176">발신자가 작업에 빠르게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-176">Let the caller get to the task quickly.</span></span> <span data-ttu-id="429f4-177">IVR에 너무 많은 정보나 긴 마케팅 메시지를 제공 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="429f4-177">Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

  - <span data-ttu-id="429f4-178">긴 메시지를 포함 하려면 환영 메시지 대신 첫 번째 질문에 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-178">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message.</span></span> <span data-ttu-id="429f4-179">발신자는 질문에 응답 하 여 첫 번째 질문의 일부인 경우 메시지를 무시할 수 있지만 환영 메시지를 무시할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-179">Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

  - <span data-ttu-id="429f4-180">발신자의 언어로 말합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-180">Speak in the caller’s language.</span></span> <span data-ttu-id="429f4-181">Stilted가 사용 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-181">Avoid stilted language.</span></span> <span data-ttu-id="429f4-182">자연스럽 게 말할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-182">Speak naturally.</span></span>

  - <span data-ttu-id="429f4-183">효율적이 고 효과적으로 메시지를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-183">Write efficient and effective prompts.</span></span> <span data-ttu-id="429f4-184">불필요 한 옵션을 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-184">Remove any unnecessary options.</span></span> <span data-ttu-id="429f4-185">호출자의 예상 응답이 문장의 끝에 나타나도록 정보를 구조화 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-185">Structure the information so that the caller’s expected response is at the end of the sentence.</span></span> <span data-ttu-id="429f4-186">예를 들어 "영업 팀에 게 문의 하려면 1."을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-186">For example, “To speak to the sales team, press 1."</span></span>

  - <span data-ttu-id="429f4-187">음성 응답 사용자에 게 친숙 하 게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-187">Make voice responses user friendly.</span></span> <span data-ttu-id="429f4-188">예를 들어 DTMF 및 음성 응답을 모두 지정 하는 경우 "영업 팀에 게 말을 하려면 1 또는 말 매출액을 누릅니다."와 같은 항목을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-188">For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

  - <span data-ttu-id="429f4-189">조직 전체에 배포 하기 전에 사용자 그룹에 대 한 IVR을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="429f4-189">Test the IVR on a group of users before you deploy it across your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

