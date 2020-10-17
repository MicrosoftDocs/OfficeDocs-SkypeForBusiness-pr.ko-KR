---
title: Microsoft 팀과 비즈니스용 Skype 동시 사용
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 팀으로 업그레이드-공존
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0690af8226f3f992dcc12f68c6135c953eb043f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533615"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a><span data-ttu-id="07286-103">팀과 비즈니스용 Skype 동시 사용</span><span class="sxs-lookup"><span data-stu-id="07286-103">Coexistence with Teams and Skype for Business</span></span>

<span data-ttu-id="07286-104">이 문서에서는 모드와 사용 되는 업그레이드 방법에 관계 없이 동일한 조직의 비즈니스용 Skype 클라이언트와 팀을 모두 실행할 때 발생할 수 있는 문제에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-104">This article summarizes behavior that may be experienced when running both Teams and Skype for Business clients in the same organization, regardless of what mode and what upgrade method is used:</span></span>

- [<span data-ttu-id="07286-105">모임</span><span class="sxs-lookup"><span data-stu-id="07286-105">Meetings</span></span>](#meetings)
- [<span data-ttu-id="07286-106">운용할</span><span class="sxs-lookup"><span data-stu-id="07286-106">Interoperability</span></span>](#interoperability)
- [<span data-ttu-id="07286-107">팀 대화-상호 운용성 및 네이티브 스레드</span><span class="sxs-lookup"><span data-stu-id="07286-107">Teams conversations-Interop versus native threads</span></span>](#teams-conversations---interop-versus-native-threads)
- [<span data-ttu-id="07286-108">현재 상태</span><span class="sxs-lookup"><span data-stu-id="07286-108">Presence</span></span>](#presence)
- [<span data-ttu-id="07286-109">페더레이션</span><span class="sxs-lookup"><span data-stu-id="07286-109">Federation</span></span>](#federation)
- [<span data-ttu-id="07286-110">연락처</span><span class="sxs-lookup"><span data-stu-id="07286-110">Contacts</span></span>](#contacts)



## <a name="meetings"></a><span data-ttu-id="07286-111">모임</span><span class="sxs-lookup"><span data-stu-id="07286-111">Meetings</span></span>

<span data-ttu-id="07286-112">이 모드에 관계 없이 사용자는 자신이 초대 하는 모든 유형의 모임에 언제 든 지 참가할 수 있습니다 (비즈니스용 Skype 또는 팀).</span><span class="sxs-lookup"><span data-stu-id="07286-112">Regardless of their mode, users can always join any type of meeting they are invited to, whether it is Skype for Business or Teams.</span></span>  <span data-ttu-id="07286-113">그러나 사용자는 모임 형식과 일치 하는 해당 클라이언트를 사용 하 여 모임에 참가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-113">However, users must join the meeting with a corresponding client that matches the meeting type:</span></span>

- <span data-ttu-id="07286-114">모임이 팀에 참가 하는 경우 모든 참가자 (예를 들어 출장만, 군도 또는 비즈니스용 Skype 사용자)는 팀 클라이언트를 사용 하 여 모임에 참석 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-114">If the meeting is a Teams meeting, all participants (whether they are TeamsOnly, Islands, or Skype for Business users) use the Teams client to join the meeting.</span></span> <span data-ttu-id="07286-115">팀이 설치 되어 있지 않은 경우, 모임에 참가 하려고 할 때 사용자가 웹으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-115">If Teams is not installed, the user will be directed to the web, upon attempting to join a meeting.</span></span>

- <span data-ttu-id="07286-116">모임이 비즈니스용 Skype 모임 인 경우 모든 참가자 (이 팀이 TeamsOnly, 군도 또는 비즈니스용 Skype 사용자 인지 여부)에는 비즈니스용 Skype 클라이언트를 사용 하 여 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-116">If the meeting is a Skype for Business meeting, all participants (whether they are TeamsOnly, Islands, or Skype for Business users) use the Skype for Business client to join the meeting.</span></span> <span data-ttu-id="07286-117">비즈니스용 Skype 클라이언트가 설치 되어 있지 않으면 사용자가 Skype 모임 앱을 통해 참가 하도록 웹으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-117">If the Skype for Business client is not installed, the user will be directed to the web to join via the Skype Meeting App.</span></span>

<span data-ttu-id="07286-118">모임을 구성할 때 예약 된 모임 유형은 다음 표에 표시 된 대로 이끌이의 모드를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-118">When organizing meetings, the meeting type that gets scheduled is based on the mode of the organizer, as shown in the following table:</span></span>

| <span data-ttu-id="07286-119">구성 도우미 모드</span><span class="sxs-lookup"><span data-stu-id="07286-119">Mode of organizer</span></span>    |      <span data-ttu-id="07286-120">결과가</span><span class="sxs-lookup"><span data-stu-id="07286-120">Behavior</span></span> |
| :------------------ | :---------------- |
| <span data-ttu-id="07286-121">TeamsOnly, SfbWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="07286-121">TeamsOnly, SfbWithTeamsCollabAndMeetings</span></span> |    <span data-ttu-id="07286-122">팀에서 예약 된 모든 모임</span><span class="sxs-lookup"><span data-stu-id="07286-122">All meetings scheduled in Teams.</span></span> <span data-ttu-id="07286-123">Outlook에서는 비즈니스용 Skype 추가 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-123">Skype for Business add-in is not available in Outlook.</span></span> | 
| <span data-ttu-id="07286-124">SfbWithTeamsCollab, SfbOnly</span><span class="sxs-lookup"><span data-stu-id="07286-124">SfbWithTeamsCollab, SfbOnly</span></span>   | <span data-ttu-id="07286-125">비즈니스용 Skype에서 예약 된 모든 모임</span><span class="sxs-lookup"><span data-stu-id="07286-125">All meetings scheduled in Skype for Business.</span></span> <span data-ttu-id="07286-126">Outlook에서는 팀 추가 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-126">Teams add-in is not available in Outlook.</span></span> | 
| <span data-ttu-id="07286-127">아일랜드</span><span class="sxs-lookup"><span data-stu-id="07286-127">Islands</span></span> | <span data-ttu-id="07286-128">기본적으로 Skype for Business 또는 팀에서 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-128">By default, meetings can be scheduled in either Skype for Business or Teams.</span></span> <span data-ttu-id="07286-129">두 추가 기능은 모두 Outlook에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-129">Both add-ins are available in Outlook.</span></span> <span data-ttu-id="07286-130">그러나 경우에 따라 아일랜드 사용자가 항상 PreferredMeetingProviderForIslandsMode = 팀으로 TeamsMeetingPolicy 인스턴스를 할당 하 여 팀에서 모임을 예약 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-130">However, you can optionally require that users in Islands always schedule meetings in Teams by assigning them an instance of TeamsMeetingPolicy with the PreferredMeetingProviderForIslandsMode=Teams.</span></span>| 


## <a name="interoperability"></a><span data-ttu-id="07286-131">운용할</span><span class="sxs-lookup"><span data-stu-id="07286-131">Interoperability</span></span>

<span data-ttu-id="07286-132">팀은 특정 시나리오에서 비즈니스용 Skype와의 상호 운용성 ("interop")을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-132">Teams supports interoperability (“interop”) with Skype for Business in certain scenarios.</span></span> <span data-ttu-id="07286-133">Interop 통신은 비즈니스용 Skype 사용자와 팀 사용자 간의 채팅 또는 통화를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-133">Interop communication refers to a chat or call between a Skype for Business user and a Teams user.</span></span>  <span data-ttu-id="07286-134">Interop 통신은 두 사용자 간에만 가능 합니다. 여러 명의 파티 채팅/통화 또는 추가 사용자 추가는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-134">Interop communication is only possible between two users; multi-party chat/calling or adding additional users is not supported.</span></span>

<span data-ttu-id="07286-135">두 사용자 간 interop 채팅 또는 통화는 다음 각 조건이 충족 될 때 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="07286-135">An interop chat or call between two users is created when each of the following are true:</span></span>

- <span data-ttu-id="07286-136">한 명의 사용자가 팀을 사용 하는 경우와 다른 하나는 비즈니스용 Skype를 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-136">One user is using Teams and the other is using Skype for Business.</span></span>

- <span data-ttu-id="07286-137">최초 통신의 받는 사람 모드는 아일랜드가 되지 않습니다 (그렇지 않은 경우 두 사용자가 같은 조직에 있는 경우 통신은 동일한 클라이언트에 연결 됨).</span><span class="sxs-lookup"><span data-stu-id="07286-137">The mode of the recipient of the initial communication is NOT Islands (otherwise the communication would land in the same client) if both users are in the same organization.</span></span> <span data-ttu-id="07286-138">페더레이션 시나리오에서 보내는 사용자는 팀을 사용 하 고 있으며 받는 사람이 TeamsOnly 모드에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-138">In federated scenarios, the sending user is using Teams, and the recipient is not in TeamsOnly mode.</span></span> 

- <span data-ttu-id="07286-139">또한 팀 사용자는 비즈니스용 Skype 계정을 온-프레미스로가지고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-139">The Teams user does NOT also have a Skype for Business account homed on-premises.</span></span> 

<span data-ttu-id="07286-140">Interop 통신 내에서 채팅은 일반 텍스트 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="07286-140">Within the interop communication, chat is plain-text only.</span></span> <span data-ttu-id="07286-141">또한 *interop 채팅 자체에서는*파일 공유 및 화면 공유를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-141">In addition, file sharing and screen sharing are not possible *in the interop chat itself*.</span></span> <span data-ttu-id="07286-142">그러나 interop 대화의 사용자는 아래에 설명 된 대로 interop 채팅 내에서 주문형 모임을 만들어 파일 및/또는 화면 공유를 쉽게 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-142">However, users in an interop conversation can easily achieve file and/or screen sharing by creating an on-demand meeting, from within the interop chat, as described below:</span></span>

- <span data-ttu-id="07286-143">팀 사용자가 자신의 화면을 공유 하려고 시도 하는 경우 주문형 팀 모임이 자동으로 만들어지고 해당 모임에 대 한 초대 링크가 비즈니스용 Skype 사용자의 클라이언트로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-143">If the Teams user attempts to share their screen, an on-demand Teams meeting is automatically created and an invite link to that meeting is sent to the Skype for Business user’s client.</span></span> <span data-ttu-id="07286-144">링크를 클릭 하면 비즈니스용 Skype 사용자가 팀을 열고 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-144">Upon clicking the link, the Skype for Business user will open Teams and join the meeting.</span></span> <span data-ttu-id="07286-145">이제 두 사용자 모두 팀 모임에 있으며 필요에 따라 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-145">Both users are now in a Teams meeting and can share as needed.</span></span>

- <span data-ttu-id="07286-146">비즈니스용 Skype 사용자가 2018 이상에서 클라이언트를 사용 하는 경우 콘텐츠를 공유 하려고 하면 주문형 비즈니스용 Skype 모임이 자동으로 만들어지고 해당 모임에 대 한 초대 링크가 팀 사용자의 클라이언트로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-146">If the Skype for Business user is using a client from 2018 or later and attempts to share any content, an on-demand Skype for Business meeting is automatically created and an invite link to that meeting is sent to the Teams user’s client.</span></span> <span data-ttu-id="07286-147">링크를 클릭 하면 팀 사용자가 비즈니스용 Skype 모임에 참가 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-147">Upon clicking the link, the Teams user will attempt to join the Skype for Business meeting.</span></span> <span data-ttu-id="07286-148">팀 사용자가 비즈니스용 Skype 클라이언트를 설치한 경우, 로그인 하 라는 메시지가 사용자에 게 표시 됩니다 (아직 로그인 하지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="07286-148">If the Teams user has the Skype for Business client installed, it will open and the user is prompted to sign in (if not already signed in).</span></span>  <span data-ttu-id="07286-149">팀 사용자에 게 비즈니스용 Skype 클라이언트가 설치 되어 있지 않으면 사용자에 게 웹 버전을 사용 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-149">If the Teams user does not have the Skype for Business client installed, the user will be prompted to use the web version.</span></span> <span data-ttu-id="07286-150">두 사용자가 모두 로그인 한 후에는 비즈니스용 Skype 모임에 있으며 필요에 따라 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-150">Once both users are signed in, they are in a Skype for Business meeting and can share as needed.</span></span>

## <a name="teams-conversations---interop-versus-native-threads"></a><span data-ttu-id="07286-151">팀 대화-상호 운용성 및 네이티브 스레드</span><span class="sxs-lookup"><span data-stu-id="07286-151">Teams conversations - Interop versus native threads</span></span>

<span data-ttu-id="07286-152">Interop 통신은 네이티브 팀 대화의 모든 기능을 지원 하지 않으므로 팀 클라이언트는 팀과 팀 간 또는 팀에서 비즈니스용 Skype 통신에 대해 별도의 대화 스레드를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-152">Because interop communications do not support all the features of native Teams conversation, the Teams client maintains separate conversation threads for Teams-to-Teams and Teams-to-Skype for Business communication.</span></span> <span data-ttu-id="07286-153">이러한 대화는 사용자 인터페이스에서 다르게 렌더링 됩니다. Interop 스레드는 다음과 같이 일반 네이티브 팀 스레드와 차별화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-153">These conversations are rendered differently in the user interface: Interop threads can be differentiated from a regular native Teams thread by:</span></span>

- <span data-ttu-id="07286-154">서식 있는 텍스트, 파일/화면 공유에 대 한 컨트롤이 부족 하 여 사용자를 추가 하지 못하는 경우</span><span class="sxs-lookup"><span data-stu-id="07286-154">Lack of controls for rich text, file/screen sharing, inability to add users.</span></span>
- <span data-ttu-id="07286-155">비즈니스용 Skype에 대 한 "S"를 표시 하는 대상 사용자의 아이콘 수정입니다.</span><span class="sxs-lookup"><span data-stu-id="07286-155">A modification to the target user’s icon, showing an “S” for Skype for Business.</span></span>

<span data-ttu-id="07286-156">이러한 차이점은 다음 스크린샷에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-156">These differences are shown in the following screenshots:</span></span>

<span data-ttu-id="07286-157">사용자 G3 테스트에 대 한 기본 팀 간 대화</span><span class="sxs-lookup"><span data-stu-id="07286-157">A native Teams-to-Teams conversation with User G3 Test</span></span>

![기본 팀 간 대화를 보여 주는 다이어그램](media/teams-upgrade-native-thread.png)

<span data-ttu-id="07286-159">동일한 사용자 G3 테스트를 사용 하는 interop 대화</span><span class="sxs-lookup"><span data-stu-id="07286-159">An interop conversation with the same User G3 Test</span></span>

![Interop 팀 간 대화를 보여 주는 다이어그램](media/teams-upgrade-interop-thread.png)

<span data-ttu-id="07286-161">대화 스레드를 만든 후에는 해당 형식이 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-161">Once a conversation thread is created, its type never changes.</span></span> <span data-ttu-id="07286-162">생성 된 팀의 interop 스레드는 항상 대상 사용자의 비즈니스용 Skype 클라이언트로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-162">Once created, an interop thread in Teams will always route to the target user’s Skype for Business client.</span></span> <span data-ttu-id="07286-163">네이티브 스레드는 항상 대상 사용자의 팀 클라이언트로 라우팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-163">A native thread will always route to the target user’s Teams client.</span></span>  <span data-ttu-id="07286-164">받는 사람 사용자의 모드가 변경 되 면 해당 사용자에 대 한 기존 팀 스레드가 더 이상 작동 하지 않으며 다음 스크린샷에 표시 된 대로 새 기본 대화를 시작 하는 링크가 포함 된 메모가 해당 채팅에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-164">If a recipient user’s mode changes, existing Teams threads to that user will no longer function and a note will be displayed on that chat with a link to start a new native conversation as shown in the following screenshot.</span></span>


![업그레이드 된 비즈니스용 Skype 사용자와의 채팅을 보여 주는 다이어그램](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a><span data-ttu-id="07286-166">현재 상태</span><span class="sxs-lookup"><span data-stu-id="07286-166">Presence</span></span>

<span data-ttu-id="07286-167">지정 된 사용자에 대 한 현재 상태는 클라이언트를 통한 서비스의 사용자 활동을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-167">Presence for a given user is based on the user’s activity in the service via the client.</span></span> <span data-ttu-id="07286-168">그런 다음 다른 사용자가 볼 수 있도록 현재 상태가 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-168">The presence is then published for other users to see.</span></span>  <span data-ttu-id="07286-169">비즈니스용 Skype와 팀은 별도의 클라이언트가 있는 별도의 서비스 이므로 각 서비스에는 사용자에 대 한 고유한 현재 상태가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-169">Skype for Business and Teams are separate services with separate clients, so each service has its own presence state for a user.</span></span>   <span data-ttu-id="07286-170">또한 팀의 현재 상태 서비스와 비즈니스용 Skype Online 간에 동기화가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-170">There is also synchronization between the presence services in Teams and in Skype for Business Online.</span></span>  <span data-ttu-id="07286-171">이렇게 하면 한 서비스가 필요한 경우 다른 서비스의 사용자 현재 상태를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-171">This allows one service to potentially publish the presence of the user from the other service if needed.</span></span> 

<span data-ttu-id="07286-172">현재 상태 게시 동작은 사용자의 모드를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-172">Presence publishing behavior is based on the user’s mode.</span></span> <span data-ttu-id="07286-173">다음과 같은 세 가지 기본 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-173">There are three basic cases:</span></span>

- <span data-ttu-id="07286-174">사용자가 팀 전용 모드일 경우 다른 모든 사용자는 사용 하는 클라이언트에 관계 없이 해당 사용자에 대 한 팀 현재 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-174">If a user is in TeamsOnly mode, all other users see Teams presence for that user, regardless of which client they use.</span></span>

- <span data-ttu-id="07286-175">사용자가 비즈니스용 Skype 모드에 있는 경우 다른 사용자는 사용 하는 클라이언트에 관계 없이 해당 사용자에 대 한 비즈니스용 Skype의 현재 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-175">If a user is in any of the Skype for Business modes, all other users see Skype for Business presence for that user, regardless of which client they use.</span></span>

- <span data-ttu-id="07286-176">사용자가 군도 모드에 있는 경우 비즈니스용 Skype 및 팀에 게시 된 상태는 독립적 이므로 같은 조직 내의 사용자에 게 표시 되는 현재 상태는 다른 사용자의 클라이언트에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="07286-176">If a user is in Islands mode, presence published in Skype for Business and Teams are independent, so the presence shown to users within the same organization will depend on the client of the other user.</span></span> <span data-ttu-id="07286-177">페더레이션 조직의 사용자는 비즈니스용 Skype에서 고립 모드 사용자에 게 연결 된 페더레이션 트래픽을 통해 비즈니스용 Skype 활동을 기준으로 해당 사용자의 현재 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-177">Users in federated organizations will see presence of that user based on their Skype for Business activity, since federated traffic to an Islands mode user lands in Skype for Business.</span></span>

<span data-ttu-id="07286-178">예를 들어 사용자 A가 군도 모드 라고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-178">For example, Assume User A is in Islands mode.</span></span> <span data-ttu-id="07286-179">사용자 A가 팀에서 활성 상태 이지만 비즈니스용 Skype에 로그인 되어 있지 않은 경우에는 다른 사용자가 팀 클라이언트에서 사용자 A의 활성 상태로 표시 되지만 비즈니스용 Skype 클라이언트에서는 사용자 A가 오프 라인으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-179">If User A is active in Teams but is not signed in to Skype for Business, other users would see User A as active from their Teams client, but in their Skype for Business client they would see User A as offline.</span></span> <span data-ttu-id="07286-180">이것은 사용자 A가 클라이언트를 실행 하지 않는 경우에 도달할 수 없기 때문에 의도적으로 설계 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07286-180">This is by design, since User A cannot be reached if they are not running the client.</span></span> 


## <a name="federation"></a><span data-ttu-id="07286-181">페더레이션</span><span class="sxs-lookup"><span data-stu-id="07286-181">Federation</span></span>

<span data-ttu-id="07286-182">비즈니스용 Skype를 사용 하 여 팀에서 다른 사용자에 게 페더레이션 하려면 비즈니스용 Skype에서 팀 사용자를 온라인으로 홈에 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-182">Federation from Teams to another user using Skype for Business requires the Teams user to be homed online in Skype for Business.</span></span> <span data-ttu-id="07286-183">TeamsUpgradePolicy는 들어오는 페더레이션된 채팅 및 통화에 대 한 라우팅을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-183">TeamsUpgradePolicy governs routing for incoming federated chats and calls.</span></span> <span data-ttu-id="07286-184">페더레이션된 라우팅 동작은 아일랜드 모드를 제외 하 고 동일한 테 넌 트 시나리오와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-184">Federated routing behavior is the same as for same-tenant scenarios, except in Islands mode.</span></span> <span data-ttu-id="07286-185">받는 사람이 아일랜드 모드일 때:</span><span class="sxs-lookup"><span data-stu-id="07286-185">When recipients are in Islands mode:</span></span>

- <span data-ttu-id="07286-186">받는 사람이 페더레이션 테 넌 트에 있는 경우 비즈니스용 Skype의 팀에서 시작한 채팅 및 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="07286-186">Chats and calls initiated from Teams land in Skype for Business if the recipient is in a federated tenant.</span></span>
- <span data-ttu-id="07286-187">받는 사람이 동일한 테 넌 트에 있는 경우 팀에서 팀에서 시작한 채팅 및 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="07286-187">Chats and calls initiated from Teams land in Teams if the recipient is in the same tenant.</span></span>
- <span data-ttu-id="07286-188">비즈니스용 skype에서 시작 된 채팅 및 통화는 항상 비즈니스용 Skype에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-188">Chats and calls initiated from Skype for Business always land in Skype for Business.</span></span>

<span data-ttu-id="07286-189">페더레이션 채팅은 네이티브 스레드 또는 interop 스레드 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-189">A federated chat can either be a native thread or an interop thread.</span></span> <span data-ttu-id="07286-190">[팀 대화---interop vs-네이티브 스레드](#teams-conversations---interop-versus-native-threads)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07286-190">See [Teams Conversations ---interop-versus-native-threads](#teams-conversations---interop-versus-native-threads).</span></span>

- <span data-ttu-id="07286-191">받는 사람과 보낸 사람이 모두 TeamsOnly 모드인 경우 대화는 다양 한 메시징 및 통화 기능을 모두 포함 하는 기본 채팅 환경이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-191">If the receiver and sender are both in TeamsOnly upgrade mode, the conversation will be a native chat experience which includes all the rich messaging and calling capabilities.</span></span> <span data-ttu-id="07286-192">자세한 내용은 [팀의 외부 (페더레이션된) 사용자를 위한 기본 채팅 환경에 대해](native-chat-for-external-users.md)알아보세요.</span><span class="sxs-lookup"><span data-stu-id="07286-192">To learn more, read [Native chat experience for external (federated) users in Teams](native-chat-for-external-users.md).</span></span> 

- <span data-ttu-id="07286-193">대화 참가자 중 하나가 TeamsOnly 모드에 있지 않은 경우 대화는 텍스트 전용 메시지를 사용 하 여 interop 환경으로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-193">If either of the conversation participants is NOT in TeamsOnly upgrade mode, the conversation remains an interop experience with text-only messages.</span></span> <span data-ttu-id="07286-194">사용자 인터페이스는 사용자가 외부 임을 나타내는 메모가 있다는 점을 제외 하 고 동일한 테 넌 트 interop 스레드와 비슷한 방식으로 페더레이션 채팅을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-194">The user interface exposes federated chats in a similar manner to same-tenant interop threads, except there is a note indicating the user is external.</span></span>

<span data-ttu-id="07286-195">자세한 내용은 [팀의 외부 (페더레이션된) 사용자를 위한 Microsoft 팀 및 기본 채팅 환경](native-chat-for-external-users.md) [에서 외부 액세스 관리](manage-external-access.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07286-195">For more details, see [Manage external access in Microsoft Teams](manage-external-access.md) and [Native chat experience for external (federated) users in Teams](native-chat-for-external-users.md).</span></span>

## <a name="contacts"></a><span data-ttu-id="07286-196">연락처</span><span class="sxs-lookup"><span data-stu-id="07286-196">Contacts</span></span>

<span data-ttu-id="07286-197">팀과 비즈니스용 Skype에는 별도의 연락처 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-197">Teams and Skype for Business have separate lists of contacts.</span></span> <span data-ttu-id="07286-198">즉, 한 시스템에서 이루어진 연락처 추가, 제거, 수정 내용이 다른 시스템과 동기화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-198">This means that contact additions, removal, and modifications made in one system are not synchronized to the other system.</span></span> <span data-ttu-id="07286-199">그러나 비즈니스용 Skype의 연락처는 다음 두 가지 특정 이벤트 중 하나가 발생할 때 자동으로 팀에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-199">However, contacts from Skype for Business are automatically copied over to Teams when either of two specific events occur:</span></span> 

- <span data-ttu-id="07286-200">비즈니스용 Skype Online 사용자는 처음으로 팀에 로그온 할 때 비즈니스용 Skype의 연락처가 팀에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-200">For any Skype for Business Online user, the first time they log onto Teams, contacts from Skype for Business will be copied over to Teams.</span></span>  <span data-ttu-id="07286-201">비즈니스용 Skype 서버에서 온-프레미스 계정을 사용 하는 사용자는이 동작을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-201">This behavior is not available for users with an on-premises account in Skype for Business Server.</span></span>  

- <span data-ttu-id="07286-202">사용자가 TeamsUpgradePolicy를 할당 하거나 Move-CsUser-MoveToTeams를 통해 팀 전용으로 업그레이드 한 후에는 다음에 사용자가 팀에 로그인 할 때 비즈니스용 Skype의 기존 연락처가 이미 팀에 있는 기존 연락처와 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07286-202">After a user is upgraded to TeamsOnly (either via assigning TeamsUpgradePolicy or via Move-CsUser -MoveToTeams), the next time a user logs into Teams, existing contacts in Skype for Business will be merged with existing contacts already in Teams.</span></span> <span data-ttu-id="07286-203">이 동작은 사용자의 비즈니스용 Skype 계정이 온-프레미스 또는 온라인 인지에 관계 없이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="07286-203">This behavior happens whether the user’s Skype for Business Account is homed on-premises or online.</span></span> 

<span data-ttu-id="07286-204">두 경우 모두 비즈니스용 Skype에서 팀으로 연락처를 전송 하는 것이 비동기적 이므로 연락처가 팀에 표시 되기까지 몇 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07286-204">In both cases, the transfer of contacts from Skype for Business to Teams is asynchronous so it may be a few minutes before contacts appear in Teams.</span></span> <span data-ttu-id="07286-205">위의 두 가지 이벤트는 복사본을 트리거하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07286-205">The two events above are what trigger the copy.</span></span>  

## <a name="related-links"></a><span data-ttu-id="07286-206">관련 링크</span><span class="sxs-lookup"><span data-stu-id="07286-206">Related links</span></span>

[<span data-ttu-id="07286-207">비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="07286-207">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="07286-208">비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="07286-208">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="07286-209">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="07286-209">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="07286-210">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="07286-210">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="07286-211">부여-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="07286-211">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="07286-212">MMS (모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="07286-212">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

