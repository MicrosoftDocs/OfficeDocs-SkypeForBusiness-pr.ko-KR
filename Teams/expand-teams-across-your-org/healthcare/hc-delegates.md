---
title: 메시지 위임
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: 사용자는 상태 메시지의 대리인으로 다른 사용자를 명시적으로 설정할 수 있습니다.
ms.openlocfilehash: cc9895ec639589ec260a03b0a1828ccf2a4eb9b1
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36232350"
---
# <a name="message-delegation"></a><span data-ttu-id="1fe37-103">메시지 위임</span><span class="sxs-lookup"><span data-stu-id="1fe37-103">Message delegation</span></span>

<span data-ttu-id="1fe37-104">사용자는 이미 상태를 자리 비움 또는 방해 금지로 명시적으로 설정 하 고 사용자 지정 텍스트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="1fe37-105">메시지 위임 기능은 다음과 같이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="1fe37-106">사용자 @username 텍스트 상태 메시지의 일부에서 다른 사용자에 게 멘 션을 사용할 수 없는 동안 대화 상대에 게 연락 하려는 사용자가 대신 해당 사용자에 @username 게 연락 하는 것을 제안 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="1fe37-107">대리인으로 지정 된 사용자에 게 대리인 이라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="1fe37-108">첫 번째 사용자에 게 연락 하려고 하는 누군가가 지정한 대리인 위에 마우스를 놓고 대리인에 게 쉽게 메시지를 전송 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="1fe37-109">이것은 클라이언트에서 사용자가 시작한 프로세스 이며,이 기능을 사용 하도록 설정 하는 데 관리자가 관여 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="1fe37-110">의료의 위임 사용 시나리오</span><span class="sxs-lookup"><span data-stu-id="1fe37-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="1fe37-111">*대리인 설정 없이 사용 예제:*  Franco  Cio는 radiology 부서에서 통화 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="1fe37-112">긴급 한 개인 통화를 수신 하 고 다음 몇 시간 동안 작업을 한 번에 한 곳으로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="1fe37-113">Radiology 부서별, Dr. Lena Ehrle에서 자신의 피어 중 하나를 요청 하 여, 그 사람을 죽 였을 때 그에 대해 다루겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="1fe37-114">그는 자신의 호출기를 Dr. Hrle에 게 전달 하며,이는 호출기에서 긴급 한 메시지 및 ping을 수신 대기 하 고 현재 책임 외에도 Dr. 를 대신 하 여 해당 사용자에 게 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="1fe37-115">팀의 다른 멤버가 비공식적인 위임이 발생 하는 것을 모르고, 환자를 ensues 혼동을 겪을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="1fe37-116">*대리인 설정의 사용 예:* Franco  Cio는 radiology 부서에서 통화 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="1fe37-117">긴급 한 개인 통화를 수신 하 고 다음 몇 시간 동안 작업을 한 번에 한 곳으로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="1fe37-118">그는 radiology 부서별, Dr. Lena Ehrle에 속한 동료 중 한 명에 게 그 사람을 이야기 하는 것을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="1fe37-119">"다음 몇 시간 동안 사용할 수 없습니다."와 유사한 사용자 지정 상태 메시지를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="1fe37-120">모든 비상시에 게 연락 @DrEhrle 주십시오. "</span><span class="sxs-lookup"><span data-stu-id="1fe37-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="1fe37-121">팀의 다른 사용자는 이제 Dr. t e t t e t t e t t e t t e t t e t t e t t e t t e t e.</span><span class="sxs-lookup"><span data-stu-id="1fe37-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="1fe37-122">환자에 대 한 주의를 ensues 혼란 스 러 울 수는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="1fe37-123">팀 클라이언트의 사용자 상태에 대 한 공존 모드의 영향</span><span class="sxs-lookup"><span data-stu-id="1fe37-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="1fe37-124">관리자는 상태 메모와 위임 멘 션 동작은 부분적으로 사용자의 공동 존재 모드에 따라 달라 지는 것을 인식 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user’s co-existence mode.</span></span> <span data-ttu-id="1fe37-125">이 행렬은 다음의 가능성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="1fe37-126">동시 존재 모드</span><span class="sxs-lookup"><span data-stu-id="1fe37-126">Co-Existence Mode</span></span> | <span data-ttu-id="1fe37-127">예상 되는 동작</span><span class="sxs-lookup"><span data-stu-id="1fe37-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="1fe37-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="1fe37-128">TeamsOnly</span></span> |<span data-ttu-id="1fe37-129">사용자는 팀에서 메모를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="1fe37-130">팀 & SfB에서 사용자의 팀 메모를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-130">User’s Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="1fe37-131">분리</span><span class="sxs-lookup"><span data-stu-id="1fe37-131">Islands</span></span> | <span data-ttu-id="1fe37-132">팀에서 설정한 사용자의 메모는 팀 에서만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-132">User’s note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="1fe37-133">SfB에서 설정한 사용자의 메모는 SfB에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-133">User’s note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="1fe37-134">SfB \* 모드</span><span class="sxs-lookup"><span data-stu-id="1fe37-134">SfB\* modes</span></span> | <span data-ttu-id="1fe37-135">사용자는 SfB에서 메모를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="1fe37-136">사용자의 SfB 메모는 SfB & 팀에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-136">User’s SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="1fe37-137">사용자는 해당 모드가 팀 전용 또는 아일랜드 인 경우에만 팀에서 메모를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="1fe37-138">비즈니스용 Skype에서 설정한 노트 표시</span><span class="sxs-lookup"><span data-stu-id="1fe37-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="1fe37-139">비즈니스용 Skype에서 메모가 설정 되었음을 시각적으로 알 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="1fe37-140">비즈니스용 Skype는 상태 메모에 대해 문자 제한을 적용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-140">Skype for Business doesn’t enforce a character limit on status notes.</span></span> <span data-ttu-id="1fe37-141">Microsoft 팀은 비즈니스용 Skype에서 설정한 첫 번째 280 자만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="1fe37-142">메모 끝에 있는 타원 (...)이 잘린 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="1fe37-143">비즈니스용 Skype는 노트의 만료 시간을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-143">Skype for Business doesn’t support expiry times for notes.</span></span>

<span data-ttu-id="1fe37-144">사용자가 TeamsOnly 모드로 업그레이드 된 경우 비즈니스용 Skype에서 팀으로 노트 마이그레이션이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1fe37-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1fe37-145">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1fe37-145">Related topics</span></span>

[<span data-ttu-id="1fe37-146">비즈니스용 Skype와 공존</span><span class="sxs-lookup"><span data-stu-id="1fe37-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
