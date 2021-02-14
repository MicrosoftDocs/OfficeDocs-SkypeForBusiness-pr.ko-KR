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
description: 부재 중 상태 또는 방해 금지 상태가 있는 사용자가 상태 메시지에서 다른 사용자를 대리인으로 명시적으로 설정하는 방법을 배워야 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790470"
---
# <a name="message-delegation"></a><span data-ttu-id="2246b-103">메시지 위임</span><span class="sxs-lookup"><span data-stu-id="2246b-103">Message delegation</span></span>

<span data-ttu-id="2246b-104">사용자는 이미 자신의 상태를 부재 중 또는 방해 금지로 명시적으로 설정하고 사용자 지정 텍스트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="2246b-105">메시지 위임 기능은 다음과 같이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="2246b-106">사용자가 @username 상태 메시지의 일부로 다른 사용자를 언급하여 연락할 수 없는 사용자를 대신 언급한 사용자에게 @username 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="2246b-107">대리인으로 할당된 사용자에게는 대리인으로 지명된 사람이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="2246b-108">그런 다음 첫 번째 사용자에게 연락하려는 누군가가 지명된 대리인을 마우스로 이동하고 대신 대리인에게 쉽게 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="2246b-109">이 프로세스는 클라이언트에서 사용자가 시작한 프로세스로, 기능을 사용하도록 설정하는 데 관리자 개입이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="2246b-110">의료에서 위임 사용 시나리오</span><span class="sxs-lookup"><span data-stu-id="2246b-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="2246b-111">*대리자를 설정하지 않은 사용 예:*  Dr. Franco Piccio는 방사통과에서 통화 중입니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="2246b-112">긴급한 개인 전화가 걸려오고 몇 시간 동안 멀어지기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="2246b-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for he while he' gone.</span><span class="sxs-lookup"><span data-stu-id="2246b-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="2246b-114">그는 비공식적으로 이진에게 전달합니다. 이진국씨는 현재의 책임 외에도 긴급한 메시지와 ping을 수신하고 Dr. Piccio를 대신하여 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="2246b-115">팀의 다른 사람들은 비공식 위임이 발생했다는 것을 알지 못하고 환자 관리에 혼동을 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="2246b-116">*대리자를 설정하는 사용 예:* Dr. Franco Piccio는 방사통과에서 통화 중입니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="2246b-117">긴급한 개인 전화가 걸려오고 몇 시간 동안 멀어지기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="2246b-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover he while he' gone.</span><span class="sxs-lookup"><span data-stu-id="2246b-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="2246b-119">"다음 몇 시간 동안 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="2246b-120">긴급한 @DrEhrle 문의하시기 바랍니다."</span><span class="sxs-lookup"><span data-stu-id="2246b-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="2246b-121">팀의 다른 사람들은 Dr. Piccio에게 연락하려고 할 때 위임이 발생했다는 것을 알고 있으므로, 그동안 이성화에게 연락할 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="2246b-122">환자를 진료하는 데 혼동을 거의 발생하지도 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="2246b-123">Teams 클라이언트의 사용자 상태에 대한 공 존재 모드의 영향</span><span class="sxs-lookup"><span data-stu-id="2246b-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="2246b-124">관리자는 상태 메모 및 위임 언급 동작이 사용자의 공 존재 모드에 따라 부분적으로 달라 진다는 것을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="2246b-125">이 행렬은 가능성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="2246b-126">Co-Existence 모드</span><span class="sxs-lookup"><span data-stu-id="2246b-126">Co-Existence Mode</span></span> | <span data-ttu-id="2246b-127">예상 동작</span><span class="sxs-lookup"><span data-stu-id="2246b-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="2246b-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="2246b-128">TeamsOnly</span></span> |<span data-ttu-id="2246b-129">사용자는 Teams에서만 메모를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="2246b-130">사용자의 Teams 메모는 Teams 및 SfB에 & 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="2246b-131">아일랜드</span><span class="sxs-lookup"><span data-stu-id="2246b-131">Islands</span></span> | <span data-ttu-id="2246b-132">Teams에서만 볼 수 있는 Teams의 사용자 노트 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="2246b-133">SfB에서만 볼 수 있는 SfB의 사용자 메모 집합</span><span class="sxs-lookup"><span data-stu-id="2246b-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="2246b-134">SfB\* 모드</span><span class="sxs-lookup"><span data-stu-id="2246b-134">SfB\* modes</span></span> | <span data-ttu-id="2246b-135">사용자는 SfB에서만 메모를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="2246b-136">사용자의 SfB 메모는 Teams의 SfB에 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="2246b-137">사용자는 TeamsOnly 또는 Islands 모드인 경우 Teams에서 메모를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="2246b-138">비즈니스용 Skype에서 노트 집합 표시</span><span class="sxs-lookup"><span data-stu-id="2246b-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="2246b-139">비즈니스용 Skype에서 메모가 설정되어 있는 시각적 표시는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="2246b-140">비즈니스용 Skype는 상태 노트에 문자 제한을 적용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="2246b-141">Microsoft Teams는 비즈니스용 Skype에서 노트 집합의 처음 280자만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="2246b-142">노트 끝에 있는 타원(...)은 자국을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="2246b-143">비즈니스용 Skype는 노트의 만료 시간을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="2246b-144">사용자가 TeamsOnly 모드로 업그레이드된 경우 비즈니스용 Skype에서 Teams로 노트 마이그레이션이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2246b-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2246b-145">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2246b-145">Related topics</span></span>

[<span data-ttu-id="2246b-146">비즈니스용 Skype와 공존</span><span class="sxs-lookup"><span data-stu-id="2246b-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
