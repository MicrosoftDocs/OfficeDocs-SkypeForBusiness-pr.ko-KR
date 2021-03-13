---
title: 메시지 위임
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: 자리 비움 상태 또는 방해 금지 상태의 사용자가 상태 메시지에 명시적으로 다른 사용자를 대리인으로 설정하는 방법을 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790470"
---
# <a name="message-delegation"></a><span data-ttu-id="7b593-103">메시지 위임</span><span class="sxs-lookup"><span data-stu-id="7b593-103">Message delegation</span></span>

<span data-ttu-id="7b593-104">사용자는 이미 명시적으로 자리 비움 또는 방해 금지로 상태를 설정한 다음 사용자 지정 텍스트를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="7b593-105">메시지 위임 기능은 다음과 같이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="7b593-106">@username의 사용자가 텍스트 상태 메시지의 일부분에서 다른 사용자를 언급하며 본인이 없는 동안 본인에게 연락하려는 사람들은 대신 @username이 언급한 사용자에게 연락하라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="7b593-107">대리인으로 할당된 사람은 본인이 대리인으로 지명되었다는 통지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="7b593-108">그러면 첫 번째 사용자에게 연락하려는 누군가가 지명된 대리인에게로 마우스를 이동하여 대신 대리인에게 쉽게 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="7b593-109">해당 기능은 클라이언트에서 사용자가 시작하는 프로세스이므로 이 기능을 사용하도록 설정하기 위해 관리자의 개입이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="7b593-110">의료 분야에서 위임 사용 시나리오</span><span class="sxs-lookup"><span data-stu-id="7b593-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="7b593-111">*위임을 설정하지 않은 사용 예:*  Dr. Franco Piccio는 방사선과 긴급 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="7b593-112">긴급한 개인 전화를 받고 이후 두 시간가량 자리를 비워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="7b593-113">박사는 방사선과의 동료 중 한 명인 Dr. Lena Ehrle에게 본인이 부재 중일 때 업무를 대신해달라고 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="7b593-114">그는 비공식적으로 본인의 무선 호출기를 Dr. Ehrle에게 넘기고 Dr. Ehrle은 현재 책임에 추가로 Dr. Piccio를 대신하여 호출기의 긴급 메시지와 호출을 수신하고 이에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="7b593-115">다른 팀원들은 비공식 위임이 있었음을 알지 못하고 환자를 돌보는 데 혼동이 일어납니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="7b593-116">*위임을 설정한 사용 예:* Dr. Franco Piccio는 방사선과 긴급 대기 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="7b593-117">긴급한 개인 전화를 받고 이후 두 시간가량 자리를 비워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="7b593-118">박사는 방사선과의 동료 중 한 명인 Dr. Lena Ehrle에게 본인이 부재 중일 때 업무를 대신해달라고 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="7b593-119">박사는 "다음 몇 시간 동안 자리를 비우니</span><span class="sxs-lookup"><span data-stu-id="7b593-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="7b593-120">긴급 상황 시 @DrEhrle에게 연락하세요"와 유사한 표현으로 본인의 사용자 지정 상태 메시지를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="7b593-121">다른 팀원들이 Dr. Piccio에게 연락하려 할 때 위임이 발생했음을 알고 그동안 Dr. Ehrle에게 연락해야 한다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="7b593-122">환자를 돌보는 데 있어 혼동이 전혀 또는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="7b593-123">공존 모드가 Teams 클라이언트의 사용자 상태에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="7b593-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="7b593-124">관리자는 상태 메모 및 위임 언급 동작이 부분적으로 사용자의 공존 모드에 의존하게 됨을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="7b593-125">이 행렬형은 다음과 같은 가능성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="7b593-126">공존 모드</span><span class="sxs-lookup"><span data-stu-id="7b593-126">Co-Existence Mode</span></span> | <span data-ttu-id="7b593-127">예상 동작</span><span class="sxs-lookup"><span data-stu-id="7b593-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="7b593-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="7b593-128">TeamsOnly</span></span> |<span data-ttu-id="7b593-129">사용자는 Teams에서만 메모를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="7b593-130">사용자의 Teams 메모는 Teams 및 SfB에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="7b593-131">Islands</span><span class="sxs-lookup"><span data-stu-id="7b593-131">Islands</span></span> | <span data-ttu-id="7b593-132">Teams에서 설정한 사용자 메모는 Teams에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="7b593-133">SfB에서 설정한 사용자 메모는 SfB에만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="7b593-134">SfB\* 모드</span><span class="sxs-lookup"><span data-stu-id="7b593-134">SfB\* modes</span></span> | <span data-ttu-id="7b593-135">사용자는 SfB에서만 메모를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="7b593-136">사용자의 SfB 메모는 SfB 및 Teams에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="7b593-137">사용자는 모드가 TeamsOnly 또는 Islands인 경우 Teams에서만 메모를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="7b593-138">비즈니스용 Skype에서 설정한 메모 표시</span><span class="sxs-lookup"><span data-stu-id="7b593-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="7b593-139">비즈니스용 Skype에서 설정된 메모라는 시각적 표시가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="7b593-140">비즈니스용 Skype에는 상태 메모의 문자 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="7b593-141">Microsoft Teams는 비즈니스용 Skype에서 설정된 메모의 처음 280자만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="7b593-142">메모 끝에 있는 생략 부호(...)는 메모가 잘렸음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="7b593-143">비즈니스용 Skype는 메모 만료 시간을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="7b593-144">사용자가 TeamsOnly 모드로 업그레이드된 경우 비즈니스용 Skype에서 Teams로 메모 마이그레이션이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b593-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7b593-145">관련 주제</span><span class="sxs-lookup"><span data-stu-id="7b593-145">Related topics</span></span>

[<span data-ttu-id="7b593-146">비즈니스용 Skype와 공존</span><span class="sxs-lookup"><span data-stu-id="7b593-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
