---
title: 비표준 사용자에 대한 Teams 앱 동작
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams의 앱이 비표준 사용자에 대해 어떻게 행동하는지 배워야 합니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 66754565737929ec9d34125ca421c7e3eed9fe65
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278548"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="1771e-103">비표준 사용자에 대한 Microsoft Teams 앱 동작</span><span class="sxs-lookup"><span data-stu-id="1771e-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="1771e-104">이 문서에서는 게스트, 외부(페더러티) 및 익명 사용자가 Teams 컨텍스트에 있을 때 Teams의 앱이 어떻게 행동하는지 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="1771e-105">게스트 **사용자는** 조직의 직원, 학생 또는 구성원이 아닌 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="1771e-106">조직에 학교 또는 직장 계정을 가지고 있지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="1771e-107">**외부(페더러화)** 사용자는 다른 도메인에 속하며 조직의 팀 또는 팀 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

>[!Note]
> <span data-ttu-id="1771e-108">게스트와 외부 사용자 비교에 대한 자세한 비교는 다른 조직의 사용자와 [통신을 참조합니다.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations)</span><span class="sxs-lookup"><span data-stu-id="1771e-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations).</span></span>

- <span data-ttu-id="1771e-109">익명 **사용자는** 사용자가 링크를 통해 모임에 참가한 Teams 모임의 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="1771e-110">사용자가 자신의 Microsoft 또는 조직의 계정으로 로그인하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="1771e-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-user-access"></a><span data-ttu-id="1771e-111">게스트 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="1771e-111">Guest user access</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="1771e-112">게스트 사용자에 대한 설치, 업데이트 및 삭제</span><span class="sxs-lookup"><span data-stu-id="1771e-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="1771e-113">게스트는 채팅, 채널 또는 모임과 같은 공유 컨텍스트에 앱을 설치, 업데이트 또는 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting.</span></span> <span data-ttu-id="1771e-114">메시지 확장 및 직접 링크를 사용하여 앱을 개인 범위로 설치, 업데이트 또는 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-114">They can install, update, or delete apps to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="1771e-115">게스트는 Teams 앱 스토어에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-115">Guests don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="1771e-116">게스트 사용자에 대한 사용 동작 및 정책</span><span class="sxs-lookup"><span data-stu-id="1771e-116">Usage behavior and policy for guest users</span></span>

<span data-ttu-id="1771e-117">네이티브 사용자가 앱을 설치한 경우 게스트는 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-117">Guests can use an app if the app was installed by a native user.</span></span>

<span data-ttu-id="1771e-118">봇은 게스트 사용자에게 사전 메시지를 보낼 수 있지만 게스트는 봇과 상호 작용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="1771e-119">게스트는 봇에 1:1 메시지를 보내거나@ 봇을 언급하거나 봇과 통신하는 적응형 카드와 상호 작용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-119">Guests can't message the bot 1:1, @ mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

<span data-ttu-id="1771e-120">게스트는 모든 앱에 대한 호스트 테넌트에 대해 설정된 전역 및 전체 권한 정책을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-120">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="1771e-121">즉, 전체 호스트 조직에 대해 앱이 차단된 경우 게스트는 앱을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-121">In other words, if an app is blocked for the whole host organization, then guests can't use the app either.</span></span>

<span data-ttu-id="1771e-122">설치 정책은 게스트 사용자에게 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-122">Setup policies don't apply to guest users.</span></span> <span data-ttu-id="1771e-123">즉, 기본 정책에서 관리자가 고정한 앱은 게스트 사용자에게 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-123">This means admin pinned app from the default policy doesn't affect guest users.</span></span>

## <a name="external-federated-user-access"></a><span data-ttu-id="1771e-124">외부(페더러화) 사용자 액세스</span><span class="sxs-lookup"><span data-stu-id="1771e-124">External (Federated) user access</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="1771e-125">외부 사용자에 대한 설치, 업데이트 및 삭제</span><span class="sxs-lookup"><span data-stu-id="1771e-125">Install, update, and delete for external users</span></span>

<span data-ttu-id="1771e-126">외부 사용자는 개인, 채팅, 채널 또는 모임과 같은 컨텍스트에 앱을 설치, 업데이트 또는 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-126">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="1771e-127">Teams 앱 스토어에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-127">They don't have access to the Teams app store.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="1771e-128">외부 사용자에 대한 사용 동작 및 정책</span><span class="sxs-lookup"><span data-stu-id="1771e-128">Usage behavior and policy for external users</span></span>

<span data-ttu-id="1771e-129">외부 사용자는 Teams 앱을 사용할 수 없습니다. 외부 사용자가 네이티브 사용자와 함께 컨텍스트에 추가될 때 모든 사용자(네이티브 및 외부)는 더 이상 앱을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-129">External users can't use any Teams apps, and when an external user is added to a context with native users, all users – native and external – can no longer use apps.</span></span>

<span data-ttu-id="1771e-130">외부 사용자는 Teams 앱을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-130">External users aren't impacted by app policies, because they can't use Teams apps.</span></span>

## <a name="anonymous-user-in-meetings-access"></a><span data-ttu-id="1771e-131">모임 액세스의 익명 사용자</span><span class="sxs-lookup"><span data-stu-id="1771e-131">Anonymous user in meetings access</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="1771e-132">익명 사용자에 대한 설치, 업데이트 및 삭제</span><span class="sxs-lookup"><span data-stu-id="1771e-132">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="1771e-133">익명 사용자는 모임에서 앱을 설치, 업데이트 또는 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-133">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="1771e-134">익명 사용자에 대한 사용 동작 및 정책</span><span class="sxs-lookup"><span data-stu-id="1771e-134">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="1771e-135">익명 사용자는 모임에서 앱을 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-135">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="1771e-136">익명 사용자가 있는 경우 네이티브 사용자는 모임 앱을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-136">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="1771e-137">앱에서 채팅에서 적응형 카드를 보내는 경우 익명 사용자는 카드와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-137">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span>

<span data-ttu-id="1771e-138">익명 사용자는 사용자 수준 전역 기본 사용 권한 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-138">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="1771e-139">이 컨트롤을 사용하면 익명 사용자가 사용자 수준 사용 권한 정책이 앱을 사용하도록 설정한 경우 Teams 모임에서 앱과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-139">This control allows anonymous users to interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="1771e-140">익명 사용자는 모임에서 이미 사용할 수 있으며 이러한 앱을 획득 및/또는 관리할 수 없는 앱과만 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1771e-140">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
