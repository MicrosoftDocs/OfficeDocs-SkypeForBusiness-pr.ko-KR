---
title: Microsoft Teams의 외부(페더리화) 사용자에 대한 네이티브 채팅 환경
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 두 사용자가 TeamsOnly 업그레이드 모드에 있는 Microsoft Teams의 외부 액세스(페더리화) 사용자에 대한 네이티브 Teams 채팅 경험에 대해 자세히 알아보습니다.
ms.openlocfilehash: a06532ab4cd1d1c5ffe3f30d2a6036b2c34c716f
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030118"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="535ab-103">Microsoft Teams의 외부(페더리화) 사용자에 대한 네이티브 채팅 환경</span><span class="sxs-lookup"><span data-stu-id="535ab-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>

<span data-ttu-id="535ab-104">Microsoft Teams 사용자가 외부(페더리화) 사용자와 채팅하는 경우 채팅 환경은 텍스트로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="535ab-105">그러나 Teams 사용자와 다른 조직의 사용자 모두 TeamsOnly 업그레이드 모드에 있는 경우 서식, 서식 및 기타 채팅 기능을 포함하는 "네이티브-teams 채팅 환경"을 @mentions 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-105">However, if both your Teams user and the person in another organization are in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="535ab-106">다른 조직의 사용자와의 네이티브 Teams 채팅은 1:1 채팅으로만 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-106">Native Teams chats with people in other organizations are limited to 1:1 chats only.</span></span>

<span data-ttu-id="535ab-107">다른 조직의 사용자에 대한 네이티브 채팅 환경은 모든 Teams 테넌트에 대해 켜져 있지만 모든 사람이 자격이 있는 것은 않습니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-107">The native chat experience for people in other organizations is turned on for all Teams tenants, but not all people are eligible.</span></span> <span data-ttu-id="535ab-108">네이티브 채팅 환경을 제공하려면 발신자 및 수신기를 TeamsOnly 업그레이드 모드로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-108">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="535ab-109">업그레이드 정책에 대한 자세한 내용은 공존 및 업그레이드 설정 설정을 [읽어 보십시오.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="535ab-109">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="535ab-110">Teams에서 외부 액세스 사용자에 대한 기능 목록을 보시고 외부 및 게스트 액세스 [비교를 참조하세요.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="535ab-110">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="535ab-111">네이티브 채팅에 있는 경우 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="535ab-111">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="535ab-112">채팅의 텍스트만 다른 조직의 사용자와 교환할 수 있는 경우 표준 외부 액세스(페더리화된) 채팅에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-112">If you can only exchange text in your chat with people in other organizations, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="535ab-113">서식, @mentions, 이모티콘 등 다른 모든 채팅 기능이 있는 경우 네이티브 Teams 채팅에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-113">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat.</span></span> 

<span data-ttu-id="535ab-114">팀은 다른 조직의 사용자에 대한 업그레이드 모드를 주기적으로 검사하고 TeamsOnly 업그레이드 모드에서 Teams를 실행하는 사람이 발견될 때 네이티브 Teams 채팅으로 전환하고 원래 채팅을 잠그는 것을 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-114">Teams periodically checks the upgrade mode for people in other organizations and, when it finds an them running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="535ab-115">네이티브 Teams 채팅으로 전환하면 Teams는 두 대화를 병합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-115">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="535ab-116">대신 채팅 피드에 두 채팅이 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-116">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="535ab-117">새 네이티브-Teams 채팅이 활성화되지만 이전 텍스트 전용 채팅은 잠겨 있습니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-117">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="535ab-118">사용자가 Teams Only 모드가 아닌 경우 더 이상 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="535ab-118">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="535ab-119">다른 조직의 사용자와 네이티브 Teams 채팅을 하다가 TeamsOnly 업그레이드 모드에서 전환되는 경우 Teams는 네이티브 Teams 채팅을 잠그고 제한된 텍스트 전용 채팅에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-119">If you were having a native Teams chat with people in other organizations and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="535ab-120">네이티브 Teams 채팅에서 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-120">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="535ab-121">네이티브 Teams 채팅을 읽을 수 있지만 대화를 계속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-121">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="535ab-122">Teams에서 이 사용자와 이전 텍스트 전용 채팅을 찾은 경우 해당 채팅이 다시 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-122">If Teams finds an old text-only chat with this person, it'll revive that chat.</span></span> <span data-ttu-id="535ab-123">그렇지 않으면 Teams에서 새 텍스트 전용 채팅을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="535ab-123">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="535ab-124">관련 항목</span><span class="sxs-lookup"><span data-stu-id="535ab-124">Related topics</span></span>

[<span data-ttu-id="535ab-125">Teams에서 외부 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="535ab-125">Manage external access in Teams</span></span>](manage-external-access.md)
