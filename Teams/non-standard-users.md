---
title: Teams 사용자에 대한 앱 동작
author: cichur
ms.author: v-cichur
ms.reviewer: joglocke
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 비표준 사용자에 대해 Microsoft Teams 앱이 어떻게 행동하는지 알아보습니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7b79371cdc8ff5109bf67b1c78639106a83a95e
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796651"
---
# <a name="microsoft-teams-apps-behavior-for-non-standard-users"></a><span data-ttu-id="70ea3-103">Microsoft Teams 사용자에 대한 앱 동작</span><span class="sxs-lookup"><span data-stu-id="70ea3-103">Microsoft Teams apps behavior for non-standard users</span></span>

<span data-ttu-id="70ea3-104">이 문서에서는 게스트, 외부 Teams 및 익명 사용자가 특정 컨텍스트에 있을 때 앱의 Teams 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-104">This article describes how apps in Teams behave when guest, external (federated), and anonymous users are present in a Teams context.</span></span>

- <span data-ttu-id="70ea3-105">게스트 **사용자는** 직원, 학생 또는 조직의 구성원이 아닌 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-105">A **guest user** is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="70ea3-106">조직에 학교 또는 직장 계정을 가지고 있지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-106">They don't have a school or work account with your organization.</span></span>

- <span data-ttu-id="70ea3-107">**외부(페더리드)** 사용자는 다른 도메인에 속하며 조직의 팀 또는 팀 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-107">An **external (federated) user** belongs to another domain and has no access to your organization's teams or team resources.</span></span>

  > [!Note]
  > <span data-ttu-id="70ea3-108">게스트와 외부 사용자에 대한 자세한 비교는 다른 조직의 사용자와 [통신을 참조합니다.](./communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="70ea3-108">For a more detailed comparison of guest versus external users, [see communicate with users from other organizations](./communicate-with-users-from-other-organizations.md).</span></span>

- <span data-ttu-id="70ea3-109">익명 **사용자는** 사용자가 링크를 통해 Teams 모임에 참가한 모임의 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-109">An **anonymous user** is a concept in Teams meetings where the user has joined the meeting via a link.</span></span> <span data-ttu-id="70ea3-110">사용자가 Microsoft 또는 조직의 계정으로 로그인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-110">The user hasn't logged in with their Microsoft or organization’s account.</span></span>

## <a name="guest-users"></a><span data-ttu-id="70ea3-111">게스트 사용자</span><span class="sxs-lookup"><span data-stu-id="70ea3-111">Guest users</span></span>

### <a name="install-update-and-delete-for-guest-users"></a><span data-ttu-id="70ea3-112">게스트 사용자에 대한 설치, 업데이트 및 삭제</span><span class="sxs-lookup"><span data-stu-id="70ea3-112">Install, update, and delete for guest users</span></span>

<span data-ttu-id="70ea3-113">게스트는 채팅, 채널 또는 모임과 같은 공유 컨텍스트에 앱을 설치, 업데이트 또는 삭제할 수 없지만 메시지 확장 및 직접 링크를 사용하여 개인 범위로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-113">Guests can't install, update, or delete apps into a shared context, such as a chat, channel, or meeting, but they can to their personal scope using message extensions and direct links.</span></span> <span data-ttu-id="70ea3-114">게스트는 데스크톱 애플리케이션에서 Teams 앱 스토어에 Teams 없지만 직접 링크로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-114">Guests don't have access to the Teams app store from the Teams desktop application, but they can access it with a direct link.</span></span>

### <a name="usage-behavior-and-policy-for-guest-users"></a><span data-ttu-id="70ea3-115">게스트 사용자에 대한 사용 동작 및 정책</span><span class="sxs-lookup"><span data-stu-id="70ea3-115">Usage behavior and policy for guest users</span></span> 

<span data-ttu-id="70ea3-116">게스트는 네이티브 사용자가 앱을 설치한 경우 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-116">Guests can use an app if the app was installed by a native user.</span></span>

#### <a name="bots-installed-to-a-channel"></a><span data-ttu-id="70ea3-117">채널에 설치된 봇</span><span class="sxs-lookup"><span data-stu-id="70ea3-117">Bots installed to a channel</span></span>

<span data-ttu-id="70ea3-118">봇은 게스트 사용자에게 사전 메시지를 보낼 수 있지만 게스트는 봇과 상호 작용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-118">Bots can proactively message guest users, but guests can't interact with the bot.</span></span> <span data-ttu-id="70ea3-119">게스트는 봇에게 일대일 메시지를 보내거나, 봇을 언급하거나, 봇과 통신하는 적응형 카드와 상호 작용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-119">Guests can't message the bot one-to-one, mention the bot, or interact with adaptive cards that communicate with the bot.</span></span>

#### <a name="personal-bots-installed-with-policies"></a><span data-ttu-id="70ea3-120">정책이 설치된 개인 봇</span><span class="sxs-lookup"><span data-stu-id="70ea3-120">Personal bots installed with policies</span></span>

- <span data-ttu-id="70ea3-121">게스트는 모든 앱에 대한 호스트 테넌트에 대해 설정된 전역 및 전체 권한 정책을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-121">Guests will adhere to global and org-wide permission policies set for the host tenant for any app.</span></span> <span data-ttu-id="70ea3-122">전체 호스트 조직에 대해 앱이 차단된 경우 게스트는 앱을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-122">If an app is blocked for the whole host organization, then guests can't use the app either.</span></span>
- <span data-ttu-id="70ea3-123">전역 기본 앱 설정 정책에 포함된 모든 봇도 게스트에 대해 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-123">Any bot included in the global default app setup policy will also be installed for guests.</span></span>
- <span data-ttu-id="70ea3-124">봇을 설치한 후 봇은 게스트와 사전 통신할 수 있으며 게스트는 봇과 다시 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-124">After a bot is installed, bots can proactively communicate with guests and guests can communicate back with bots.</span></span>
- <span data-ttu-id="70ea3-125">전역 기본 앱 설정 정책에서 게스트를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-125">You can't remove a guest from the global default app setup policy.</span></span>
- <span data-ttu-id="70ea3-126">게스트가 봇에 액세스하지 않도록하려면 더 많은 앱 설치 정책을 만들고, 내부 사용자에게 할당하고, 사용자 지정 정책으로 봇을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-126">To avoid guest from accessing bots, you can create more app setup policies, assign them to internal users, and install bots with the custom policies.</span></span>

## <a name="external-federated-users"></a><span data-ttu-id="70ea3-127">외부(페더리화) 사용자</span><span class="sxs-lookup"><span data-stu-id="70ea3-127">External (Federated) users</span></span>

### <a name="install-update-and-delete-for-external-users"></a><span data-ttu-id="70ea3-128">외부 사용자에 대한 설치, 업데이트 및 삭제</span><span class="sxs-lookup"><span data-stu-id="70ea3-128">Install, update, and delete for external users</span></span>

<span data-ttu-id="70ea3-129">외부 사용자는 개인, 채팅, 채널 또는 모임과 같은 상황에 맞는 앱을 설치, 업데이트 또는 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-129">External users can't install, update, or delete apps into any context, such as a personal, chat, channel, or meeting.</span></span> <span data-ttu-id="70ea3-130">호스팅 조직의 앱 Teams 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-130">They don't have access to the Teams app store of the hosting organization.</span></span>

### <a name="usage-behavior-and-policy-for-external-users"></a><span data-ttu-id="70ea3-131">외부 사용자에 대한 사용 동작 및 정책</span><span class="sxs-lookup"><span data-stu-id="70ea3-131">Usage behavior and policy for external users</span></span>

- <span data-ttu-id="70ea3-132">다른 조직의 사람들은 호스팅 조직의 전역(조직 전체 기본값) 정책을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-132">People from other organizations adhere to the hosting organization's global (org-wide default) policy</span></span>
- <span data-ttu-id="70ea3-133">호스팅 조직의 사용자는 다른 조직의 사용자와의 모임 채팅에서 앱을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-133">Users in the hosting organization can add apps in meeting chats with people from other organizations.</span></span> <span data-ttu-id="70ea3-134">다른 조직의 사람들은 모임 채팅에서 앱을 추가할 수 없지만 채팅에 추가된 봇, 탭 및 메시지 확장과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-134">People from other organizations cannot add apps in meeting chats but can interact with bots, tabs and message extensions once added to the chat.</span></span>
- <span data-ttu-id="70ea3-135">모임 채팅에 봇이 설치되면 해당 채팅의 다른 조직의 사용자와 사전 통신할 수 있으며 해당 사용자도 봇과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-135">After a bot is installed in a meeting chat, it can proactively communicate with people from other organizations in that chat and those people can communicate with bot.</span></span>
- <span data-ttu-id="70ea3-136">호스팅 조직의 데이터 정책과 해당 사용자의 조직에서 공유하는 타사 앱의 데이터 공유 관행이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-136">The data policies of the hosting organization, as well as the data sharing practices of any third-party apps shared by that user's organization, are applied.</span></span>

## <a name="anonymous-users"></a><span data-ttu-id="70ea3-137">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="70ea3-137">Anonymous users</span></span>

### <a name="install-update-and-delete-for-anonymous-users"></a><span data-ttu-id="70ea3-138">익명 사용자에 대한 설치, 업데이트 및 삭제</span><span class="sxs-lookup"><span data-stu-id="70ea3-138">Install, update, and delete for anonymous users</span></span>

<span data-ttu-id="70ea3-139">익명 사용자는 모임에서 앱을 설치, 업데이트 또는 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-139">Anonymous users can't install, update, or delete apps in meetings.</span></span>

### <a name="usage-behavior-and-policy-for-anonymous-users"></a><span data-ttu-id="70ea3-140">익명 사용자에 대한 사용 동작 및 정책</span><span class="sxs-lookup"><span data-stu-id="70ea3-140">Usage behavior and policy for anonymous users</span></span>

<span data-ttu-id="70ea3-141">익명 사용자는 모임에서 앱을 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-141">Anonymous users can't directly use apps in meetings.</span></span> <span data-ttu-id="70ea3-142">익명 사용자가 있는 경우 네이티브 사용자는 모임 앱을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-142">Native users can continue to use meetings apps if anonymous users are present.</span></span> <span data-ttu-id="70ea3-143">앱에서 채팅에서 적응형 카드를 보내는 경우 익명 사용자가 카드와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-143">If an app sends an adaptive card in the chat, anonymous users can interact with the card.</span></span> <span data-ttu-id="70ea3-144">자세한 내용은 익명 사용자가 [모임에 참가하도록 허용 을 참조하십시오.](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings)</span><span class="sxs-lookup"><span data-stu-id="70ea3-144">For more information, read [Allow anonymous users to join meetings](/meeting-settings-in-teams#allow-anonymous-users-to-join-meetings).</span></span>

<span data-ttu-id="70ea3-145">익명 사용자는 사용자 수준 전역 기본 사용 권한 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-145">Anonymous users will inherit the user-level global default permission policy.</span></span> <span data-ttu-id="70ea3-146">사용자 수준 사용 권한 정책이 앱을 사용하도록 설정한 Teams 모임에서 앱과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-146">They can interact with apps in Teams meetings if the user-level permission policy has enabled the app.</span></span> <span data-ttu-id="70ea3-147">익명 사용자는 모임에서 이미 사용할 수 있으며 이러한 앱을 획득 및/또는 관리할 수 없는 앱과만 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ea3-147">Anonymous users can only interact with apps that are already available in a meeting and can't acquire and/or manage these apps.</span></span>
