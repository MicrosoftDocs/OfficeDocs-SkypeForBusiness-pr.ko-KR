---
title: Microsoft 팀의 외부 (페더레이션된) 사용자를 위한 기본 채팅 환경
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 모든 사용자가 팀 전용 업그레이드 모드에 있는 외부 사용자 간에 사용할 수 있는 Microsoft 팀의 외부 액세스 (페더레이션된) 사용자를 위한 기본 팀 채팅 환경에 대해 알아봅니다.
ms.openlocfilehash: 1274e71f5854e05049c8d766bd3456a0792b1032
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583847"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="f590d-103">Microsoft 팀의 외부 (페더레이션된) 사용자를 위한 기본 채팅 환경</span><span class="sxs-lookup"><span data-stu-id="f590d-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>
======================================

<span data-ttu-id="f590d-104">Microsoft 팀 사용자가 외부 (페더레이션된) 사용자와 채팅을 하는 경우 채팅 환경은 텍스트로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="f590d-105">그러나 팀 사용자와 외부 사용자가 모두 TeamsOnly 업그레이드 모드인 경우, 다양 한 서식, @mentions, 기타 채팅 기능을 포함 하는 "기본 팀 채팅 환경"을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-105">However, if both your Teams user and the external user is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="f590d-106">즉, 조직의 사용자와 마찬가지로, 적격 외부 사용자와 동일한 다양 한 1:1 팀 채팅 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible external users as you'd have with users in your organization.</span></span> <span data-ttu-id="f590d-107">외부 사용자와의 기본 팀 채팅은 여전히 1:1 채팅으로 제한 됩니다 (외부 사용자는 그룹 채팅을 수행할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="f590d-107">Native Teams chats with external users are still limited to 1:1 chats only (external users can't do group chats).</span></span>

<span data-ttu-id="f590d-108">외부 사용자에 대 한 기본 채팅 환경은 모든 팀 테 넌 트에 대해 설정 되어 있지만 모든 사용자가 사용할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-108">The native chat experience for external users is turned on for all Teams tenants, but not all users are eligible.</span></span> <span data-ttu-id="f590d-109">기본 채팅 환경을 제공 하려면, 팀 전용 업그레이드 모드에 대해 발신자와 수신자를 모두 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="f590d-110">업그레이드 정책에 대해 자세히 알아보려면 [공존 및 업그레이드 설정 설정을](setting-your-coexistence-and-upgrade-settings.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f590d-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="f590d-111">팀의 외부 액세스 사용자에 대 한 기능 목록을 보려면 [외부 및 게스트 액세스 비교](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f590d-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="f590d-112">기본 채팅을 하 고 있는지 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="f590d-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="f590d-113">외부 사용자와 채팅의 텍스트만 교환할 수 있는 경우에는 표준 외부 액세스 (페더레이션된) 채팅을 사용 하 고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-113">If you can only exchange text in your chat with an external user, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="f590d-114">서식, @mentions, emojis 등의 다른 채팅 기능을 모두 사용 하는 경우, 외부 사용자와의 기본 팀 채팅을 하 고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat with your external user.</span></span> 

<span data-ttu-id="f590d-115">팀은 외부 사용자에 대 한 업그레이드 모드를 정기적으로 확인 하 고, 팀의 다른 업그레이드 모드에서 실행 중인 외부 사용자가 발견 되 면 기본 팀 채팅으로 전환 하 여 원래 채팅을 잠그려고 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-115">Teams periodically checks the upgrade mode for external users and, when it finds an external user running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="f590d-116">기본 팀 채팅으로 전환 하는 경우 팀은 두 대화를 병합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="f590d-117">대신 채팅 피드의 채팅을 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="f590d-118">새로운 기본 팀 채팅은 활성 이지만, 이전 텍스트 전용 채팅은 잠겨 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="f590d-119">사용자가 팀 전용 모드에 있지 않은 경우에는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="f590d-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="f590d-120">외부 사용자와 기본 팀이 채팅을 하 고 있는 경우, 팀은 자신에 게 기본 팀 채팅을 잠그고 제한 된 텍스트만 채팅에 대 한 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-120">If you were having a native Teams chat with an external user and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="f590d-121">기본 팀 채팅에서 계속할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="f590d-122">기본 팀 채팅은 계속 읽을 수 있지만, 대화를 계속 진행 하는 것은 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="f590d-123">팀이이 외부 사용자와 함께 오래 된 텍스트 전용 채팅을 발견 하면 해당 채팅을 회복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-123">If Teams finds an old text-only chat with this external user, it'll revive that chat.</span></span> <span data-ttu-id="f590d-124">그렇지 않으면 팀이 새로운 텍스트 전용 채팅을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f590d-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f590d-125">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f590d-125">Related topics</span></span>

[<span data-ttu-id="f590d-126">팀에서 외부 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="f590d-126">Manage external access in Teams</span></span>](manage-external-access.md)
