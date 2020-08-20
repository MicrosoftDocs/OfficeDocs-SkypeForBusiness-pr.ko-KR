---
title: Teams에서 메시내기 정책 관리
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.messagingpolicies.overview
- seo-marvel-apr2020
description: 이 문서에서는 메시오기 정책과 메시래스를 사용하여 Teams에서 채팅 메시지를 제어하는 방법을 알아봅니다.
ms.openlocfilehash: 0a548eee32fc196157b6a363dd0427b187e52112
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814184"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="e4972-103">Teams에서 메시내기 정책 관리</span><span class="sxs-lookup"><span data-stu-id="e4972-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="e4972-104">메시지 정책은 Microsoft Teams의 사용자(소유자 및 구성원)가 사용할 수 있는 채팅 및 채널 메시오프 [등을 제어하는](assign-roles-permissions.md) 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-104">Messaging policies are used to control which chat and channel messaging features are available to [users (owners and members)](assign-roles-permissions.md) in Microsoft Teams.</span></span> <span data-ttu-id="e4972-105">자동으로 만들어지거나 사용자 지정 메시지 정책을 만들고 할당하는 전역(조직 전체 기본값) 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-105">You can use the global (Org-wide default) policy that's created automatically or create and assign custom messaging policies.</span></span>

<span data-ttu-id="e4972-106">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-106">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="e4972-107">전역 정책에서 설정을 편집하거나 하나 이상의 사용자 지정 정책을 만들어 할당하여 원하는 기능을 설정하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-107">You can edit the settings in the global policy or create and assign one or more custom policies to turn on or turn off the features that you want.</span></span>

## <a name="create-a-custom-messaging-policy"></a><span data-ttu-id="e4972-108">사용자 지정 메시지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="e4972-108">Create a custom messaging policy</span></span>

1. <span data-ttu-id="e4972-109">Microsoft Teams 관리 센터의 왼쪽 창에서 **메시지 정책으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="e4972-109">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="e4972-110">추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e4972-110">Click **Add**.</span></span>
3. <span data-ttu-id="e4972-111">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-111">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="e4972-112">원하는 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-112">Choose the settings that you want.</span></span>
5. <span data-ttu-id="e4972-113">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-113">Click **Save**.</span></span>

<span data-ttu-id="e4972-114">예를 들어 보낸 메시지가 삭제되지 않거나 변경되지 않고 해당 메시지를 삭제하거나 변경된 상태여부를 확인하려 한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-114">For example, say you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="e4972-115">"보낸 메시지 보존"이라는 새 사용자 지정 정책을 만들고 다음 설정을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-115">Create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="e4972-116">소유자는 보낸 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-116">Owners can delete sent messages</span></span>
- <span data-ttu-id="e4972-117">사용자가 보낸 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-117">Users can delete sent messages</span></span>
- <span data-ttu-id="e4972-118">사용자가 보낸 메시지를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-118">Users can edit sent messages</span></span>

<span data-ttu-id="e4972-119">그런 다음 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-119">Then assign the policy to users.</span></span>

## <a name="edit-a-messaging-policy"></a><span data-ttu-id="e4972-120">메시지 정책 편집</span><span class="sxs-lookup"><span data-stu-id="e4972-120">Edit a messaging policy</span></span>

<span data-ttu-id="e4972-121">전역 정책 및 사용자가 만든 모든 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-121">You can edit the global policy and any custom policies that you create.</span></span> 

1. <span data-ttu-id="e4972-122">Microsoft Teams 관리 센터의 왼쪽 창에서 **메시지 정책으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="e4972-122">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="e4972-123">정책 이름의 왼쪽을 클릭하여 정책을 선택한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e4972-123">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="e4972-124">여기에서 원하는 대로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-124">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="e4972-125">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-125">Click **Save**.</span></span>

## <a name="assign-a-custom-messaging-policy-to-users"></a><span data-ttu-id="e4972-126">사용자에게 사용자 지정 메시이드 정책 할당</span><span class="sxs-lookup"><span data-stu-id="e4972-126">Assign a custom messaging policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="e4972-127">한 번에 하나의 메시지 정책만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-127">A user can only be assigned one messaging policy at a time.</span></span>

> [!NOTE]
> <span data-ttu-id="e4972-128">사용자가 정책에 할당된 경우 정책을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-128">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="e4972-129">먼저 영향을 받은 모든 사용자에게 다른 정책을 할당한 후에 원래 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-129">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="e4972-130">메시지 정책 설정</span><span class="sxs-lookup"><span data-stu-id="e4972-130">Messaging policy settings</span></span>

<span data-ttu-id="e4972-131">다음은 구성할 수 있는 메시어오는 정책 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-131">Here are the messaging policy settings that you can configure.</span></span>

- <span data-ttu-id="e4972-132">**소유자는 보낸 메시지를 삭제할 수 있습니다.**  이 설정을 사용하여 사용자가 채팅에서 전송된 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-132">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="e4972-133">**사용자가 보낸 메시지를 삭제할 수 있습니다.** 사용자가 채팅에서 전송된 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-133">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="e4972-134">**사용자가 보낸 메시지를 편집할 수 있습니다.** 사용자가 채팅에서 전송된 메시지를 편집할 수 있게 하려면 이 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-134">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="e4972-135">**읽음 확인** 읽음 확인을 사용하면 1:1 및 그룹 채팅을 통해 받는 사람 20명 이내의 메시지를 받는 사람이 보낸 메시지일 때 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-135">**Read receipts** Read receipts allow the sender of a chat message to be notified when their message was read by the recipient in 1:1 and group chats 20 people or less.</span></span> <span data-ttu-id="e4972-136">메시지 읽음 확인은 메시지를 읽은지 여부에 상관없이 불구하고 팀 통신을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-136">Message read receipts remove uncertainly about whether a message was read, and improve team communication.</span></span> <span data-ttu-id="e4972-137">eDiscovery 보고에서 읽음 확인이 캡처되지 않음에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="e4972-137">Please note that read receipts are not captured in eDiscovery reporting.</span></span>  
    - <span data-ttu-id="e4972-138">**사용자 제어됨** 즉, 사용자가 읽음 확인을 설정 또는 해제할지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-138">**User controlled** This means that users get to decide if they want read receipts ON or OFF.</span></span> <span data-ttu-id="e4972-139">앱 내의 기본 설정이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-139">Default setting within the app is ON.</span></span> <span data-ttu-id="e4972-140">그러면 사용자가 이 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-140">Users can then turn it OFF.</span></span>
    - <span data-ttu-id="e4972-141">**모든 사용자에 대해 설정** 즉, 테넌트에 있는 모든 사용자가 이 기능을 해제하는 옵션이 없는 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-141">**On for everyone** This means everyone in the tenant will have the feature ON with no option to turn it off.</span></span> <span data-ttu-id="e4972-142">모든 사용자에게 **설정된** 설정을 사용할 때 전체 테넌트에 대한 영수신 음소거를 설정하는 유일한 방법은 전체 테넌트에 대한 메시지 정책("전역(전역 기본값)"이라는 기본 정책에만 사용하거나 테넌트의 모든 메시지 정책을 거부에 대해 동일한 설정을 사용하도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-142">Be aware that when using the **On for everyone** setting, the only way to set receipts for the whole tenant is either to have only one messaging policy for the whole tenant (the default policy named "Global (Org-wide Default)") or to have all messaging policies in the tenant use the same settings for receipts.</span></span> <span data-ttu-id="e4972-143">읽음 확인 기능은 모든 사용자에 대해 기능이 설정된 시간에서 **효과적입니다.**</span><span class="sxs-lookup"><span data-stu-id="e4972-143">The read receipts feature is most effective when the feature is enabled to **On for everyone**.</span></span>
    - <span data-ttu-id="e4972-144">**모든 사용자에 대해 끄기** 즉, 이 기능이 사용할 수 없으며 테넌트에 있는 아무도 읽음 확인을 설정할 수 없으며 읽음 확인을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-144">**Off for everyone** This means the feature is disabled and no one in the tenant has read receipts nor can they turn it on.</span></span>
<span data-ttu-id="e4972-145"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="e4972-145"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="e4972-146">**채팅**  조직의 사용자들이 Teams 앱을 사용하여 다른 사람과 채팅할 수 있게 하려면 이 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-146">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="e4972-147">**대화에서 Giphy 사용**  이 기능을 켜면 사용자가 다른 사람과의 채팅 대화에 Giphy를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-147">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="e4972-148">Giphy는 사용자가 애니메이션 GIF 파일을 검색하고 공유할 수 있는 온라인 데이터베이스 및 검색 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-148">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="e4972-149">각 Giphy에는 콘텐츠 등급이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-149">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="e4972-150">**Giphy content rating**</span><span class="sxs-lookup"><span data-stu-id="e4972-150">**Giphy content rating**</span></span>
    - <span data-ttu-id="e4972-151">**제한 사항 없음** 즉, 사용자가 콘텐츠 등급에 상관없이 채팅에 Giphy를 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-151">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="e4972-152">**보통**  즉, 사용자가 채팅에 Giphy를 삽입할 수 있지만, 성인 콘텐츠에서 는 약간 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-152">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="e4972-153">**고**  즉, 사용자가 채팅에 Giphy를 삽입할 수 있지만, 성인 콘텐츠에서는 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-153">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="e4972-154">**대화에서 테마 사용** 이 기능을 설정하면 사용자가 다른 사람과의 채팅에 메모를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-154">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span>
- <span data-ttu-id="e4972-155">**대화에서 스티커 사용** 이 기능을 켜면 사용자는 다른 사용자와의 채팅 대화에 스티커를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-155">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="e4972-156">**URL 미리 보기 허용** 메시지에서 자동 URL 미리 보기를 설정하거나 해제하려면 이 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-156">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="e4972-157">**사용자가 메시지를 번역할 수 있도록 허용** 사용자가 Microsoft 365 또는 Office 365에 대한 개인 언어 설정에서 지정된 언어로 Teams 메시지를 자동 번역할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-157">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="e4972-158">**몰입형 메시지를 볼 수 있도록 몰입형 리더 허용** 사용자가 Microsoft 몰입형 리더에서 메시지를 볼 수 있도록 하려면 이 설정을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-158">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="e4972-159">몰입형 리더는 텍스트의 가독성을 향상시키기 위해 전체 화면 읽기 환경을 제공하는 학습 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-159">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="e4972-160">**우선 순위 알림을 사용하여 메시지 보내기** 이 설정을 켜면 사용자는 우선 순위 [알림을 사용하여 메시지를 보낼 수 있습니다.](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)</span><span class="sxs-lookup"><span data-stu-id="e4972-160">**Send urgent messages using priority notifications** If you turn this on, users can send messages using [priority notifications](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462).</span></span> <span data-ttu-id="e4972-161">우선 순위 알림은 20분간 또는 우수지로 표시된 메시지가 수신자가 선택되어 *urgent* 읽을 때까지 사용자에게 20분당 한 정도로 알림을 알립니다. 따라서 메시지가 제시간에 실행될 확정이 없을 가능성을 최대화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-161">Priority notifications notify users every 2 minutes for a period of 20 minutes or until messages that are marked as *urgent* are picked up and read by the recipient, maximizing the likelihood that the message is acted upon in a timely manner.</span></span>
- <span data-ttu-id="e4972-162">**오디오 메시지 만들기**</span><span class="sxs-lookup"><span data-stu-id="e4972-162">**Audio message creation**</span></span> 
  > [!Important]
  > <span data-ttu-id="e4972-163">오디오 메시지는 eDiscovery 보고에서 캡처되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-163">Audio messages are not captured in eDiscovery reporting.</span></span>
    - <span data-ttu-id="e4972-164">**채팅 및 채널에서 허용** 즉, 사용자가 채팅과 채널 모두에서 오디오 메시지는 남아둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-164">**Allowed in chats and channels** This means that users can leave audio messages in both chats and channels.</span></span>
    - <span data-ttu-id="e4972-165">**채팅에서만 허용** 즉, 사용자가 채팅에 음성 메시지는 남아 있지만 채널에는 그대로 참여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-165">**Allowed in chats only** This means that users can leave audio messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="e4972-166">**사용 안 함** 따라서 사용자가 채팅이나 채널에서 오디오 메시지를 작성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-166">**Disabled** This means that users cannot create audio messages in chats or channels.</span></span>  
- <span data-ttu-id="e4972-167">**모바일 디바이스의 경우 최근 채팅 위에 즐겨 찾는 채널 표시** 이 설정은 사용자가 스크롤할 필요가 없도록 즐겨 찾는 채널을 모바일 장치 화면의 맨 위로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-167">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span>
- <span data-ttu-id="e4972-168">**사용자가 그룹 채팅에서 사용자를 제거할 수 있도록 허용** 사용자가 그룹 채팅에서 다른 사용자를 제거할 수 있게 하려면 이 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-168">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="e4972-169">이 기능을 사용하면 채팅 기록을 그대로 두지 않고도 소규모 사용자 그룹과 채팅을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-169">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>
- <span data-ttu-id="e4972-170">**제안된 회신 사용**  채팅 메시지에 대해 제안된 회신을 사용할 수 있는 설정하려면 이 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-170">**Enable suggested replies**  Turn this setting on to enable suggested replies for chat messages.</span></span>

> [!NOTE]
> <span data-ttu-id="e4972-171">이러한 설정 중 일부는 팀 소유자가 팀 수준 및 비공개 채널 소유자에 의한 비공개 채널 수준에서 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4972-171">Some of these settings, such using Giphys, can also be configured at the team level by team owners and at the private channel level by private channel owners.</span></span>

### <a name="related-topics"></a><span data-ttu-id="e4972-172">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e4972-172">Related topics</span></span>

- [<span data-ttu-id="e4972-173">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="e4972-173">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="e4972-174">Microsoft Teams에서 팀 소유자 및 구성원 할당</span><span class="sxs-lookup"><span data-stu-id="e4972-174">Assign team owners and members in Microsoft Teams</span></span>](assign-roles-permissions.md)
