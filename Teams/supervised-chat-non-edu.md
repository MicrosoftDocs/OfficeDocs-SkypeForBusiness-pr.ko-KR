---
title: 교육적이지 않은 테넌트에 감독 채팅 사용
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 교육용이 아닌 테넌트에 대한 감독된 채팅에 대해 Microsoft Teams 있습니다.
ms.openlocfilehash: 9d3e7707632a384f82a89a965f6db51f786f9d66
ms.sourcegitcommit: 4d2e1328dee2b6c60ba0022976da8dfe5efba2ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53203734"
---
# <a name="supervised-chats-for-non-educational-tenants"></a><span data-ttu-id="62c15-103">교육이 아닌 테넌트에 대한 감독 채팅</span><span class="sxs-lookup"><span data-stu-id="62c15-103">Supervised chats for non-educational tenants</span></span>

<span data-ttu-id="62c15-104">감독된 채팅을 사용하면 지정된 감독자는 조직 내 모든 사용자와 채팅을 시작할 수 있으며, 적절한 감독자가 없는 한 제한된 사용자가 새 채팅을 시작하는 데 제한을 두지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-104">Supervised chat allows designated supervisors to initiate chats with anyone in their organization and blocks restricted users from starting new chats unless an appropriate supervisor is present.</span></span> <span data-ttu-id="62c15-105">채팅 감독을 사용하도록 설정하면 감독자는 채팅을 떠날 수 없습니다. 다른 참가자는 채팅을 제거할 수 없습니다. 제한된 사용자와 관련된 채팅이 적절하게 감독될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-105">When chat supervision is enabled, supervisors aren't allowed to leave chats and other participants aren't allowed to remove them, ensuring that chats involving restricted users are properly supervised.</span></span>

<span data-ttu-id="62c15-106">이러한 제한은 감독된 채팅이 완전히 활성화된 후에 생성된 새 개인 채팅에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-106">These limitations are only applied to new private chats that are created after supervised chat has been fully enabled.</span></span> <span data-ttu-id="62c15-107">기존 개인 채팅, 모임 채팅 또는 채널에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-107">They don't apply to existing private chats, meetings chats, or channels.</span></span>

<span data-ttu-id="62c15-108">감독된 채팅은 교육 기관 요구에 맞게 조정되지만 교육이 아닌 테넌트도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-108">Supervised chat is tailored for educational institution needs, but it is also available to non-educational tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="62c15-109">감독 채팅은 기능이 적용된 후 생성된 새 채팅을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-109">Supervised chat protects new chats created after the feature is enforced.</span></span> <span data-ttu-id="62c15-110">기존 채팅을 보호하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-110">It doesn't protect existing chats.</span></span>

## <a name="enable-supervised-chat"></a><span data-ttu-id="62c15-111">감독 채팅 사용</span><span class="sxs-lookup"><span data-stu-id="62c15-111">Enable supervised chat</span></span>

> [!NOTE]
> <span data-ttu-id="62c15-112">기관에 대해 채팅을 사용하도록 설정하기 전에 채팅 권한 역할 및 역할 기반 채팅 권한 정책을 설정하여 관리되지 않은 채팅에 대한 원치 않는 제한된 사용자 액세스가 방지되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-112">Ensure that you set up chat permission roles and the role-based chat permission policies before enabling chat for your institution to avoid unwanted restricted user access to unsupervised chats.</span></span>

<span data-ttu-id="62c15-113">**환경의 각 사용자에 대한 채팅 권한 역할 정의**</span><span class="sxs-lookup"><span data-stu-id="62c15-113">**Define chat permission roles for each user in your environment**</span></span>

<span data-ttu-id="62c15-114">감독된 채팅이 환경 내의 각 사용자에게 예상대로 작동하려면 올바른 채팅 권한 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-114">For supervised chat to work as expected each user within your environment needs to be assigned the correct chat permission role.</span></span> <span data-ttu-id="62c15-115">사용자가 할당할 수 있는 세 가지 역할이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-115">There are three roles that a user can have assigned:</span></span>

- <span data-ttu-id="62c15-116">전체 사용 권한: 이 역할은 사용자 환경의 채팅 감독자에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-116">Full permissions: This role should be assigned to the chat supervisors in your environment.</span></span> <span data-ttu-id="62c15-117">사용자 환경 내의 모든 사용자와 채팅을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-117">They can start chats with any user within your environment.</span></span> <span data-ttu-id="62c15-118">모든 권한이 있는 사용자는 참여하는 채팅을 감독해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-118">Users with full permissions are expected to supervise the chats they participate in.</span></span> <span data-ttu-id="62c15-119">시작한 채팅 또는 페더링된 테넌트에서 감독하는 채팅에서 떠날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-119">They can't leave or be removed from chats that they start or chats that they're supervising in federated tenants.</span></span>

- <span data-ttu-id="62c15-120">제한된 사용 권한: 이 역할은 제한된 사용자에 대한 감독 액세스만 해야 하는 직원 구성원에게 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-120">Limited permissions: This role is ideal for staff members who should only have supervised access to restricted users.</span></span> <span data-ttu-id="62c15-121">전체 사용자 또는 제한된 사용자와 채팅을 시작할 수 있지만 제한된 사용자와 채팅을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-121">They can start chats with any full or limited users but can't start chats with restricted users.</span></span> <span data-ttu-id="62c15-122">전체 사용 권한이 있는 사용자가 제한된 사용자와 채팅을 시작하는 경우 제한된 사용자를 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-122">If a user with full permissions begins a chat with a restricted user, limited users can be brought into the conversation.</span></span> <span data-ttu-id="62c15-123">이 액세스는 제한된 사용자와 제한된 사용자 간의 공동 작업을 감독할 수 있는 전체 권한이 있는 사용자가 있기 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-123">This access happens because a user with full permissions is present to supervise collaboration between limited and restricted users.</span></span>

- <span data-ttu-id="62c15-124">제한된 사용 권한: 이 역할은 감독해야 하는 사용자에게 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-124">Restricted permissions: This role is ideal for users who need to be supervised.</span></span> <span data-ttu-id="62c15-125">모든 권한이 있는 사용자와의 채팅을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-125">They can only start chats with users who have full permissions.</span></span> <span data-ttu-id="62c15-126">모든 권한이 있는 사용자가 초대하는 모든 대화에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-126">They can participate in any conversation that a user with full permissions invites them to.</span></span> <span data-ttu-id="62c15-127">페더리드 채팅의 경우 제한된 사용자만 제한된 사용자의 테넌트에서 제공된 모든 권한이 있는 사용자가 채팅에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-127">In federated chat cases, restricted users can only be added to chats by a user with full permissions who is from the restricted user’s tenant.</span></span>

<span data-ttu-id="62c15-128">사용자의 채팅 권한 역할을 설정하려면  관리자 포털의 메시징 정책 옵션에 있는 채팅 권한 역할 정책을 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-128">To set your users’ chat permission role, use the **Chat permissions role** policy found within your Messaging policy options in the Teams admin portal.</span></span> <span data-ttu-id="62c15-129">PowerShell을 사용하여 Full, Limited 또는 Limited 값으로 ChatPermissionRole 정책을 사용하여 역할을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-129">You can use PowerShell to define roles using the ChatPermissionRole policy with the values Full, Limited, or Restricted.</span></span> <span data-ttu-id="62c15-130">이 정책은 [CsTeamsMessagingPolicy 에 있습니다.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="62c15-130">This policy is under [CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span></span>

<span data-ttu-id="62c15-131">테넌트의 게스트에게 역할을 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-131">Roles can't be assigned to guests in your tenant.</span></span> <span data-ttu-id="62c15-132">게스트에게는 제한된 역할이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-132">Guests are assigned the limited role.</span></span>

## <a name="allow-supervised-chat"></a><span data-ttu-id="62c15-133">감독 채팅 허용</span><span class="sxs-lookup"><span data-stu-id="62c15-133">Allow supervised chat</span></span>

<span data-ttu-id="62c15-134">감독된 채팅은 기본적으로 테넌트에 대해 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-134">Supervised chat is disabled by default for your tenant.</span></span> <span data-ttu-id="62c15-135">사용자에 대한 채팅 권한 역할을 설정한 후 **Org-wide** 설정으로 이동하고 역할 기반 채팅 사용 Teams 설정 설정하여 테넌트 내에서 감독된 채팅을 사용하도록 설정할 수  >    있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-135">After you've set chat permission roles for your users, you can enable supervised chat within your tenant by going to **Org-wide settings** > **Teams Settings** and setting **Role-based chat permissions** policy to **On**.</span></span> <span data-ttu-id="62c15-136">PowerShell을 사용하여 AllowRoleBasedChatPermissions를 True로 설정하여 감독 채팅을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-136">You can also use PowerShell to enable Supervised Chat by setting AllowRoleBasedChatPermissions to True.</span></span> <span data-ttu-id="62c15-137">이 cmdlet은 [CsTeamsClientConfiguration 에 있습니다.](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="62c15-137">This cmdlet is under [CsTeamsClientConfiguration](/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps).</span></span>

<span data-ttu-id="62c15-138">테넌트의 모든 사용자에 대해 감독 채팅을 사용하도록 설정해야 합니다. 사용자의 일부에만 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-138">Supervised chat must be enabled for all users in the tenant and cannot be enabled for only a portion of your users.</span></span>

<span data-ttu-id="62c15-139">**채팅 사용**</span><span class="sxs-lookup"><span data-stu-id="62c15-139">**Enable chat**</span></span>

<span data-ttu-id="62c15-140">관리 센터에서 사용할 수 있는 기존 채팅 정책을 사용하여 모든 Teams 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-140">Enable chat for all your users using the existing Chat policy available in Teams admin center.</span></span>

<span data-ttu-id="62c15-141">**감독되는 채팅 유지 관리**</span><span class="sxs-lookup"><span data-stu-id="62c15-141">**Maintain supervised chats**</span></span>

<span data-ttu-id="62c15-142">감독 채팅을 처음 사용하도록 설정한 후 환경의 채팅이 감독된 상태로 유지되도록 몇 가지 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-142">After supervised chat is initially enabled, you'll need to do a few things to ensure that the chats in your environment remain supervised:</span></span>

- <span data-ttu-id="62c15-143">테넌트에 참가하는 모든 새 사용자에게 적절한 역할을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-143">Assign appropriate roles to any new users that join your tenant.</span></span> <span data-ttu-id="62c15-144">기본적으로 사용자는 제한된 역할이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-144">By default, users will be assigned a restricted role.</span></span>

- <span data-ttu-id="62c15-145">모든 권한이 있는 사용자가 테넌트에서 나가거나 제거된 경우 감독하고 있는 채팅은 무인으로 남게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-145">If a user with full permissions leaves or is removed from a tenant, the chats they were supervising will be left unattended.</span></span> <span data-ttu-id="62c15-146">원래 사용자를 제거하기 전에 채팅을 감독할 수 있도록 모든 권한이 있는 다른 사용자가 이러한 대화에 추가되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-146">Before you remove the original user, ensure that another user with full permissions is added to these conversations so that the chat can remain supervised.</span></span> <span data-ttu-id="62c15-147">원래 감독자가 제거되면 새 참가자를 대화에 추가할 수 없지만 현재 참가자는 계속 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62c15-147">Once the original supervisor is removed, new participants can't be added to the conversation, but current participants can continue to communicate.</span></span>
