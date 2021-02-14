---
title: Microsoft Teams 및 비즈니스용 Skype와 공존
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드 - 공존
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
# <a name="coexistence-with-teams-and-skype-for-business"></a><span data-ttu-id="d34de-103">Teams 및 비즈니스용 Skype와 공존</span><span class="sxs-lookup"><span data-stu-id="d34de-103">Coexistence with Teams and Skype for Business</span></span>

<span data-ttu-id="d34de-104">이 문서에서는 어떤 모드와 어떤 업그레이드 방법이 사용됐는가에 관계없이 동일한 조직에서 Teams 및 비즈니스용 Skype 클라이언트를 모두 실행하는 경우 경험할 수 있는 동작을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-104">This article summarizes behavior that may be experienced when running both Teams and Skype for Business clients in the same organization, regardless of what mode and what upgrade method is used:</span></span>

- [<span data-ttu-id="d34de-105">모임</span><span class="sxs-lookup"><span data-stu-id="d34de-105">Meetings</span></span>](#meetings)
- [<span data-ttu-id="d34de-106">상호 연동성</span><span class="sxs-lookup"><span data-stu-id="d34de-106">Interoperability</span></span>](#interoperability)
- [<span data-ttu-id="d34de-107">Teams 대화-Interop 및 네이티브 스레드</span><span class="sxs-lookup"><span data-stu-id="d34de-107">Teams conversations-Interop versus native threads</span></span>](#teams-conversations---interop-versus-native-threads)
- [<span data-ttu-id="d34de-108">현재 상태</span><span class="sxs-lookup"><span data-stu-id="d34de-108">Presence</span></span>](#presence)
- [<span data-ttu-id="d34de-109">페더레이션</span><span class="sxs-lookup"><span data-stu-id="d34de-109">Federation</span></span>](#federation)
- [<span data-ttu-id="d34de-110">연락처</span><span class="sxs-lookup"><span data-stu-id="d34de-110">Contacts</span></span>](#contacts)



## <a name="meetings"></a><span data-ttu-id="d34de-111">모임</span><span class="sxs-lookup"><span data-stu-id="d34de-111">Meetings</span></span>

<span data-ttu-id="d34de-112">모드에 관계없이 사용자는 비즈니스용 Skype 또는 Teams에 관계없이 초대된 모든 유형의 모임에 언제든지 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-112">Regardless of their mode, users can always join any type of meeting they are invited to, whether it is Skype for Business or Teams.</span></span>  <span data-ttu-id="d34de-113">그러나 사용자는 모임 유형과 일치하는 해당 클라이언트를 통해 모임에 참가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-113">However, users must join the meeting with a corresponding client that matches the meeting type:</span></span>

- <span data-ttu-id="d34de-114">모임이 Teams 모임인 경우 모든 참가자(TeamsOnly, Islands 또는 비즈니스용 Skype 사용자)가 Teams 클라이언트를 사용하여 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-114">If the meeting is a Teams meeting, all participants (whether they are TeamsOnly, Islands, or Skype for Business users) use the Teams client to join the meeting.</span></span> <span data-ttu-id="d34de-115">Teams가 설치되지 않은 경우 사용자는 모임에 참가하려고 할 때 웹으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-115">If Teams is not installed, the user will be directed to the web, upon attempting to join a meeting.</span></span>

- <span data-ttu-id="d34de-116">모임이 비즈니스용 Skype 모임인 경우 모든 참가자(TeamsOnly, Islands 또는 비즈니스용 Skype 사용자)가 비즈니스용 Skype 클라이언트를 사용하여 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-116">If the meeting is a Skype for Business meeting, all participants (whether they are TeamsOnly, Islands, or Skype for Business users) use the Skype for Business client to join the meeting.</span></span> <span data-ttu-id="d34de-117">비즈니스용 Skype 클라이언트가 설치되어 있지 않은 경우 사용자는 Skype 모임 앱을 통해 참가하도록 웹으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-117">If the Skype for Business client is not installed, the user will be directed to the web to join via the Skype Meeting App.</span></span>

<span data-ttu-id="d34de-118">모임을 구성할 때 예약되는 모임 유형은 다음 표와 같이 이끌이의 모드를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-118">When organizing meetings, the meeting type that gets scheduled is based on the mode of the organizer, as shown in the following table:</span></span>

| <span data-ttu-id="d34de-119">이끌이 모드</span><span class="sxs-lookup"><span data-stu-id="d34de-119">Mode of organizer</span></span>    |      <span data-ttu-id="d34de-120">동작</span><span class="sxs-lookup"><span data-stu-id="d34de-120">Behavior</span></span> |
| :------------------ | :---------------- |
| <span data-ttu-id="d34de-121">TeamsOnly, SfbWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="d34de-121">TeamsOnly, SfbWithTeamsCollabAndMeetings</span></span> |    <span data-ttu-id="d34de-122">Teams에서 예약된 모든 모임.</span><span class="sxs-lookup"><span data-stu-id="d34de-122">All meetings scheduled in Teams.</span></span> <span data-ttu-id="d34de-123">Outlook에서는 비즈니스용 Skype 추가 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-123">Skype for Business add-in is not available in Outlook.</span></span> | 
| <span data-ttu-id="d34de-124">SfbWithTeamsCollab, SfbOnly</span><span class="sxs-lookup"><span data-stu-id="d34de-124">SfbWithTeamsCollab, SfbOnly</span></span>   | <span data-ttu-id="d34de-125">비즈니스용 Skype에서 예약된 모든 모임입니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-125">All meetings scheduled in Skype for Business.</span></span> <span data-ttu-id="d34de-126">Outlook에서는 Teams 추가 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-126">Teams add-in is not available in Outlook.</span></span> | 
| <span data-ttu-id="d34de-127">아일랜드</span><span class="sxs-lookup"><span data-stu-id="d34de-127">Islands</span></span> | <span data-ttu-id="d34de-128">기본적으로 비즈니스용 Skype 또는 Teams에서 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-128">By default, meetings can be scheduled in either Skype for Business or Teams.</span></span> <span data-ttu-id="d34de-129">두 추가 기능을 모두 Outlook에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-129">Both add-ins are available in Outlook.</span></span> <span data-ttu-id="d34de-130">그러나 경우에 따라 Islands의 사용자가 PreferredMeetingProviderForIslandsMode=Teams를 사용하여 TeamsMeetingPolicy 인스턴스를 할당하여 Teams에서 항상 모임을 예약해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-130">However, you can optionally require that users in Islands always schedule meetings in Teams by assigning them an instance of TeamsMeetingPolicy with the PreferredMeetingProviderForIslandsMode=Teams.</span></span>| 


## <a name="interoperability"></a><span data-ttu-id="d34de-131">상호 연동성</span><span class="sxs-lookup"><span data-stu-id="d34de-131">Interoperability</span></span>

<span data-ttu-id="d34de-132">Teams는 특정 시나리오에서 비즈니스용 Skype와의 상호 연동성("interop")을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-132">Teams supports interoperability (“interop”) with Skype for Business in certain scenarios.</span></span> <span data-ttu-id="d34de-133">상호 통신은 비즈니스용 Skype 사용자와 Teams 사용자 간의 채팅 또는 통화를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-133">Interop communication refers to a chat or call between a Skype for Business user and a Teams user.</span></span>  <span data-ttu-id="d34de-134">상호 통신은 두 사용자 간에만 가능합니다. 다자 채팅/통화 또는 추가 사용자 추가는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-134">Interop communication is only possible between two users; multi-party chat/calling or adding additional users is not supported.</span></span>

<span data-ttu-id="d34de-135">다음 각각이 참일 때 두 사용자 간의 상호 채팅 또는 통화가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-135">An interop chat or call between two users is created when each of the following are true:</span></span>

- <span data-ttu-id="d34de-136">한 사용자가 Teams를 사용하고 다른 사용자는 비즈니스용 Skype를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-136">One user is using Teams and the other is using Skype for Business.</span></span>

- <span data-ttu-id="d34de-137">초기 통신을 받는 사람의 모드는 두 사용자가 동일한 조직에 있는 경우 NOT Islands(그렇지 않으면 통신이 동일한 클라이언트에 연결)입니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-137">The mode of the recipient of the initial communication is NOT Islands (otherwise the communication would land in the same client) if both users are in the same organization.</span></span> <span data-ttu-id="d34de-138">페더러드 시나리오에서 보내는 사용자는 Teams를 사용하고 받는 사람이 TeamsOnly 모드가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-138">In federated scenarios, the sending user is using Teams, and the recipient is not in TeamsOnly mode.</span></span> 

- <span data-ttu-id="d34de-139">Teams 사용자에게는 비즈니스용 Skype 계정이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-139">The Teams user does NOT also have a Skype for Business account homed on-premises.</span></span> 

<span data-ttu-id="d34de-140">Interop 통신 내에서 채팅은 일반 텍스트 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-140">Within the interop communication, chat is plain-text only.</span></span> <span data-ttu-id="d34de-141">또한 상호 채팅 자체에서는 파일 공유 및 화면 공유가 *불가능합니다.*</span><span class="sxs-lookup"><span data-stu-id="d34de-141">In addition, file sharing and screen sharing are not possible *in the interop chat itself*.</span></span> <span data-ttu-id="d34de-142">그러나 Interop 대화의 사용자는 아래 설명된 바와 같이 Interop 채팅 내에서, 즉, 대화형 모임을 만들어 파일 및/또는 화면 공유를 쉽게 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-142">However, users in an interop conversation can easily achieve file and/or screen sharing by creating an on-demand meeting, from within the interop chat, as described below:</span></span>

- <span data-ttu-id="d34de-143">Teams 사용자가 화면을 공유하려고 시도하면 요청 시 Teams 모임이 자동으로 만들어지며 해당 모임에 대한 초대 링크가 비즈니스용 Skype 사용자의 클라이언트로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-143">If the Teams user attempts to share their screen, an on-demand Teams meeting is automatically created and an invite link to that meeting is sent to the Skype for Business user’s client.</span></span> <span data-ttu-id="d34de-144">링크를 클릭하면 비즈니스용 Skype 사용자가 Teams를 열고 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-144">Upon clicking the link, the Skype for Business user will open Teams and join the meeting.</span></span> <span data-ttu-id="d34de-145">이제 두 사용자가 Teams 모임에 참가하고 있으며, 필요한 경우 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-145">Both users are now in a Teams meeting and can share as needed.</span></span>

- <span data-ttu-id="d34de-146">비즈니스용 Skype 사용자가 2018년 이후의 클라이언트를 사용 중일 때 콘텐츠 공유를 시도하면 비즈니스용 Skype 모임이 자동으로 만들어지며 해당 모임에 대한 초대 링크가 Teams 사용자의 클라이언트로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-146">If the Skype for Business user is using a client from 2018 or later and attempts to share any content, an on-demand Skype for Business meeting is automatically created and an invite link to that meeting is sent to the Teams user’s client.</span></span> <span data-ttu-id="d34de-147">링크를 클릭하면 Teams 사용자가 비즈니스용 Skype 모임에 참가하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-147">Upon clicking the link, the Teams user will attempt to join the Skype for Business meeting.</span></span> <span data-ttu-id="d34de-148">Teams 사용자에게 비즈니스용 Skype 클라이언트가 설치되어 있는 경우 해당 클라이언트가 열리며 로그인하라는 메시지가 표시됩니다(아직 로그인하지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="d34de-148">If the Teams user has the Skype for Business client installed, it will open and the user is prompted to sign in (if not already signed in).</span></span>  <span data-ttu-id="d34de-149">Teams 사용자에게 비즈니스용 Skype 클라이언트가 설치되어 있지 않은 경우 웹 버전을 사용하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-149">If the Teams user does not have the Skype for Business client installed, the user will be prompted to use the web version.</span></span> <span data-ttu-id="d34de-150">두 사용자가 모두 로그인하면 비즈니스용 Skype 모임에 있으며 필요한 경우 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-150">Once both users are signed in, they are in a Skype for Business meeting and can share as needed.</span></span>

## <a name="teams-conversations---interop-versus-native-threads"></a><span data-ttu-id="d34de-151">Teams 대화 - Interop 및 네이티브 스레드</span><span class="sxs-lookup"><span data-stu-id="d34de-151">Teams conversations - Interop versus native threads</span></span>

<span data-ttu-id="d34de-152">상호 운영 통신은 네이티브 Teams 대화의 일부 기능을 지원하지 않습니다. Teams 클라이언트는 Teams 간 및 Teams-To-Business 통신을 위해 별도의 대화 스레드를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-152">Because interop communications do not support all the features of native Teams conversation, the Teams client maintains separate conversation threads for Teams-to-Teams and Teams-to-Skype for Business communication.</span></span> <span data-ttu-id="d34de-153">이러한 대화는 사용자 인터페이스에서 다르게 렌더링됩니다. Interop 스레드는 다음을 통해 일반 네이티브 Teams 스레드와 차별화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-153">These conversations are rendered differently in the user interface: Interop threads can be differentiated from a regular native Teams thread by:</span></span>

- <span data-ttu-id="d34de-154">풍부한 텍스트, 파일/화면 공유, 사용자를 추가할 수 없는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-154">Lack of controls for rich text, file/screen sharing, inability to add users.</span></span>
- <span data-ttu-id="d34de-155">비즈니스용 Skype에 대한 "S"를 표시하는 대상 사용자의 아이콘을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-155">A modification to the target user’s icon, showing an “S” for Skype for Business.</span></span>

<span data-ttu-id="d34de-156">이러한 차이점은 다음 스크린샷에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-156">These differences are shown in the following screenshots:</span></span>

<span data-ttu-id="d34de-157">사용자 G3 테스트와의 네이티브 Teams-팀 대화</span><span class="sxs-lookup"><span data-stu-id="d34de-157">A native Teams-to-Teams conversation with User G3 Test</span></span>

![기본 Teams-팀 대화를 보여주는 다이어그램](media/teams-upgrade-native-thread.png)

<span data-ttu-id="d34de-159">동일한 사용자 G3 테스트와의 interop 대화</span><span class="sxs-lookup"><span data-stu-id="d34de-159">An interop conversation with the same User G3 Test</span></span>

![Teams 간 대화를 보여주는 다이어그램](media/teams-upgrade-interop-thread.png)

<span data-ttu-id="d34de-161">대화 스레드가 만들어지면 해당 형식은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-161">Once a conversation thread is created, its type never changes.</span></span> <span data-ttu-id="d34de-162">생성되면 Teams의 interop 스레드는 항상 대상 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-162">Once created, an interop thread in Teams will always route to the target user’s Skype for Business client.</span></span> <span data-ttu-id="d34de-163">네이티브 스레드는 항상 대상 사용자의 Teams 클라이언트로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-163">A native thread will always route to the target user’s Teams client.</span></span>  <span data-ttu-id="d34de-164">받는 사람의 모드가 변경되면 해당 사용자에 대한 기존 Teams 스레드가 더 이상 작동하지 않습니다. 다음 스크린샷과 같이 새 네이티브 대화를 시작하는 링크가 있는 메모가 해당 채팅에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-164">If a recipient user’s mode changes, existing Teams threads to that user will no longer function and a note will be displayed on that chat with a link to start a new native conversation as shown in the following screenshot.</span></span>


![업그레이드된 비즈니스용 Skype 사용자와의 채팅을 보여주는 다이어그램](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a><span data-ttu-id="d34de-166">현재 상태</span><span class="sxs-lookup"><span data-stu-id="d34de-166">Presence</span></span>

<span data-ttu-id="d34de-167">주어진 사용자의 현재 상태는 클라이언트를 통한 서비스의 사용자 활동을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-167">Presence for a given user is based on the user’s activity in the service via the client.</span></span> <span data-ttu-id="d34de-168">그러면 다른 사용자가 볼 수 있도록 현재 상태가 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-168">The presence is then published for other users to see.</span></span>  <span data-ttu-id="d34de-169">비즈니스용 Skype와 Teams는 별도의 클라이언트가 있는 별도 서비스이기 때문에 각 서비스에는 사용자에 대한 자체 스테이트 상태가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-169">Skype for Business and Teams are separate services with separate clients, so each service has its own presence state for a user.</span></span>   <span data-ttu-id="d34de-170">Teams와 비즈니스용 Skype Online의 현재 상태 서비스 간에도 동기화가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-170">There is also synchronization between the presence services in Teams and in Skype for Business Online.</span></span>  <span data-ttu-id="d34de-171">이렇게 하면 한 서비스가 필요한 경우 다른 서비스에서 사용자의 존재를 잠재적으로 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-171">This allows one service to potentially publish the presence of the user from the other service if needed.</span></span> 

<span data-ttu-id="d34de-172">현재 상태 게시 동작은 사용자의 모드를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-172">Presence publishing behavior is based on the user’s mode.</span></span> <span data-ttu-id="d34de-173">세 가지 기본 사례가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-173">There are three basic cases:</span></span>

- <span data-ttu-id="d34de-174">사용자가 TeamsOnly 모드인 경우 사용하는 클라이언트에 관계없이 다른 모든 사용자에게 해당 사용자의 Teams 현재 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-174">If a user is in TeamsOnly mode, all other users see Teams presence for that user, regardless of which client they use.</span></span>

- <span data-ttu-id="d34de-175">사용자가 비즈니스용 Skype 모드에 있는 경우 사용하는 클라이언트에 관계없이 다른 모든 사용자에게 해당 사용자의 비즈니스용 Skype 현재 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-175">If a user is in any of the Skype for Business modes, all other users see Skype for Business presence for that user, regardless of which client they use.</span></span>

- <span data-ttu-id="d34de-176">사용자가 제도 모드에 있는 경우 비즈니스용 Skype 및 Teams에 게시된 현재 상태는 독립적이기 때문에 동일한 조직 내의 사용자에게 표시되는 현재 상태는 다른 사용자의 클라이언트에 따라 달라 갑니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-176">If a user is in Islands mode, presence published in Skype for Business and Teams are independent, so the presence shown to users within the same organization will depend on the client of the other user.</span></span> <span data-ttu-id="d34de-177">페더맹된 조직의 사용자는 비즈니스용 Skype에 대한 페더러드 트래픽이 비즈니스용 Skype에 제공된 것이기 때문에 비즈니스용 Skype 활동을 기반으로 해당 사용자의 현재 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-177">Users in federated organizations will see presence of that user based on their Skype for Business activity, since federated traffic to an Islands mode user lands in Skype for Business.</span></span>

<span data-ttu-id="d34de-178">예를 들어 사용자 A가 제도 모드에 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-178">For example, Assume User A is in Islands mode.</span></span> <span data-ttu-id="d34de-179">사용자 A가 Teams에서 활성 상태이지만 비즈니스용 Skype에 로그인하지 않은 경우 다른 사용자는 사용자 A가 Teams 클라이언트에서 활성으로 표시되지만 비즈니스용 Skype 클라이언트에서는 사용자 A를 오프라인으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-179">If User A is active in Teams but is not signed in to Skype for Business, other users would see User A as active from their Teams client, but in their Skype for Business client they would see User A as offline.</span></span> <span data-ttu-id="d34de-180">클라이언트를 실행하지 않는 경우 사용자 A에 도달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-180">This is by design, since User A cannot be reached if they are not running the client.</span></span> 


## <a name="federation"></a><span data-ttu-id="d34de-181">페더레이션</span><span class="sxs-lookup"><span data-stu-id="d34de-181">Federation</span></span>

<span data-ttu-id="d34de-182">Teams에서 비즈니스용 Skype를 사용하는 다른 사용자로 페더맹을 사용하려면 Teams 사용자가 비즈니스용 Skype에서 온라인으로 돌아와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-182">Federation from Teams to another user using Skype for Business requires the Teams user to be homed online in Skype for Business.</span></span> <span data-ttu-id="d34de-183">TeamsUpgradePolicy는 들어오는 페더레이드 채팅 및 통화에 대한 라우팅을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-183">TeamsUpgradePolicy governs routing for incoming federated chats and calls.</span></span> <span data-ttu-id="d34de-184">페더러드 라우팅 동작은 제도 모드를 제외한 동일한 테넌트 시나리오의 경우와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-184">Federated routing behavior is the same as for same-tenant scenarios, except in Islands mode.</span></span> <span data-ttu-id="d34de-185">받는 사람이 제도 모드인 경우:</span><span class="sxs-lookup"><span data-stu-id="d34de-185">When recipients are in Islands mode:</span></span>

- <span data-ttu-id="d34de-186">Teams에서 시작된 채팅 및 통화는 받는 사람이 페더넌트 테넌트에 있는 경우 비즈니스용 Skype에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-186">Chats and calls initiated from Teams land in Skype for Business if the recipient is in a federated tenant.</span></span>
- <span data-ttu-id="d34de-187">받는 사람이 동일한 테넌트에 있는 경우 Teams에서 시작된 채팅 및 통화가 Teams에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-187">Chats and calls initiated from Teams land in Teams if the recipient is in the same tenant.</span></span>
- <span data-ttu-id="d34de-188">비즈니스용 Skype에서 시작된 채팅 및 통화는 항상 비즈니스용 Skype에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-188">Chats and calls initiated from Skype for Business always land in Skype for Business.</span></span>

<span data-ttu-id="d34de-189">페더러드 채팅은 네이티브 스레드 또는 interop 스레드일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-189">A federated chat can either be a native thread or an interop thread.</span></span> <span data-ttu-id="d34de-190">Teams [대화---interop-vss-native-threads를 참조합니다.](#teams-conversations---interop-versus-native-threads)</span><span class="sxs-lookup"><span data-stu-id="d34de-190">See [Teams Conversations ---interop-versus-native-threads](#teams-conversations---interop-versus-native-threads).</span></span>

- <span data-ttu-id="d34de-191">받는 사람과 보낸 사람이 TeamsOnly 업그레이드 모드에 있는 경우 대화는 모든 풍부한 메시징 및 통화 기능을 포함하는 기본 채팅 환경이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-191">If the receiver and sender are both in TeamsOnly upgrade mode, the conversation will be a native chat experience which includes all the rich messaging and calling capabilities.</span></span> <span data-ttu-id="d34de-192">자세한 내용은 Teams에서 외부(페더러리) 사용자에 대한 네이티브 채팅 환경을 [읽어보아야 합니다.](native-chat-for-external-users.md)</span><span class="sxs-lookup"><span data-stu-id="d34de-192">To learn more, read [Native chat experience for external (federated) users in Teams](native-chat-for-external-users.md).</span></span> 

- <span data-ttu-id="d34de-193">대화 참가자 중 한 자가 TeamsOnly 업그레이드 모드가 아닌 경우 대화는 텍스트 전용 메시지와 상호 운영 환경으로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-193">If either of the conversation participants is NOT in TeamsOnly upgrade mode, the conversation remains an interop experience with text-only messages.</span></span> <span data-ttu-id="d34de-194">사용자 인터페이스는 사용자가 외부에 있는 것을 나타내는 메모가 있는 것을 제외하고 동일한 테넌트 interop 스레드와 비슷한 방식으로 페더링된 채팅을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-194">The user interface exposes federated chats in a similar manner to same-tenant interop threads, except there is a note indicating the user is external.</span></span>

<span data-ttu-id="d34de-195">자세한 내용은 [Teams의](manage-external-access.md) 외부 사용자에 대한 Microsoft Teams 및 네이티브 채팅 환경의 외부 액세스 [관리를 참조하세요.](native-chat-for-external-users.md)</span><span class="sxs-lookup"><span data-stu-id="d34de-195">For more details, see [Manage external access in Microsoft Teams](manage-external-access.md) and [Native chat experience for external (federated) users in Teams](native-chat-for-external-users.md).</span></span>

## <a name="contacts"></a><span data-ttu-id="d34de-196">연락처</span><span class="sxs-lookup"><span data-stu-id="d34de-196">Contacts</span></span>

<span data-ttu-id="d34de-197">Teams와 비즈니스용 Skype에는 별도의 연락처 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-197">Teams and Skype for Business have separate lists of contacts.</span></span> <span data-ttu-id="d34de-198">즉, 한 시스템에서 만든 연락처 추가, 제거 및 수정 내용이 다른 시스템과 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-198">This means that contact additions, removal, and modifications made in one system are not synchronized to the other system.</span></span> <span data-ttu-id="d34de-199">그러나 비즈니스용 Skype의 연락처는 다음 두 가지 특정 이벤트 중 하나에서 발생하는 경우 자동으로 Teams로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-199">However, contacts from Skype for Business are automatically copied over to Teams when either of two specific events occur:</span></span> 

- <span data-ttu-id="d34de-200">비즈니스용 Skype Online 사용자의 경우 Teams에 처음 로그인하면 비즈니스용 Skype의 연락처가 Teams로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-200">For any Skype for Business Online user, the first time they log onto Teams, contacts from Skype for Business will be copied over to Teams.</span></span>  <span data-ttu-id="d34de-201">이 동작은 비즈니스용 Skype Server의 프레미스 계정이 있는 사용자에게는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-201">This behavior is not available for users with an on-premises account in Skype for Business Server.</span></span>  

- <span data-ttu-id="d34de-202">사용자가 TeamsUpgradePolicy 할당을 통해 또는 Move-CsUser -MoveToTeams를 통해 TeamsOnly로 업그레이드된 후 다음에 사용자가 Teams에 로그인하면 비즈니스용 Skype의 기존 연락처가 Teams에 이미 있는 기존 연락처와 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-202">After a user is upgraded to TeamsOnly (either via assigning TeamsUpgradePolicy or via Move-CsUser -MoveToTeams), the next time a user logs into Teams, existing contacts in Skype for Business will be merged with existing contacts already in Teams.</span></span> <span data-ttu-id="d34de-203">이 동작은 사용자의 비즈니스용 Skype 계정이 홈 또는 온라인에 있는지 여부에 따라 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-203">This behavior happens whether the user’s Skype for Business Account is homed on-premises or online.</span></span> 

<span data-ttu-id="d34de-204">두 경우 모두 비즈니스용 Skype에서 Teams로 연락처를 이전하는 것은 비동기적이기 때문에 연락처가 Teams에 표시되기 몇 분 정도가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-204">In both cases, the transfer of contacts from Skype for Business to Teams is asynchronous so it may be a few minutes before contacts appear in Teams.</span></span> <span data-ttu-id="d34de-205">위의 두 이벤트는 복사를 트리거하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="d34de-205">The two events above are what trigger the copy.</span></span>  

## <a name="related-links"></a><span data-ttu-id="d34de-206">관련 링크</span><span class="sxs-lookup"><span data-stu-id="d34de-206">Related links</span></span>

[<span data-ttu-id="d34de-207">비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침</span><span class="sxs-lookup"><span data-stu-id="d34de-207">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="d34de-208">비즈니스용 Skype Server와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="d34de-208">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="d34de-209">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="d34de-209">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="d34de-210">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="d34de-210">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="d34de-211">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="d34de-211">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="d34de-212">MMS(모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="d34de-212">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

