---
title: 팀에서 메시징 정책 관리
ms.author: lolaj
author: lolajacobsen
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
description: 이 문서에서는 메시징 정책과이를 사용 하 여 팀의 채팅 메시지를 제어 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: b010f26beeab29b1f7362d3ebee57f092d8a28ec
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938567"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="cd0df-103">팀에서 메시징 정책 관리</span><span class="sxs-lookup"><span data-stu-id="cd0df-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="cd0df-104">메시징 정책은 Microsoft Teams에서 사용자에게 제공되는 채팅 및 채널 메시징 기능을 제어하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="cd0df-105">자동으로 생성 되는 전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 메시징 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-105">You can use the global (Org-wide default) policy that's created automatically or create and assign custom messaging policies.</span></span>

<span data-ttu-id="cd0df-106">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-106">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="cd0df-107">전역 정책의 설정을 편집 하거나 하나 이상의 사용자 지정 정책을 만들어 지정 하 여 원하는 기능을 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-107">You can edit the settings in the global policy or create and assign one or more custom policies to turn on or turn off the features that you want.</span></span>

## <a name="create-a-custom-messaging-policy"></a><span data-ttu-id="cd0df-108">사용자 지정 메시징 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="cd0df-108">Create a custom messaging policy</span></span>

1. <span data-ttu-id="cd0df-109">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **메시징 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-109">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="cd0df-110">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-110">Click **Add**.</span></span>
3. <span data-ttu-id="cd0df-111">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-111">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="cd0df-112">원하는 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-112">Choose the settings that you want.</span></span>
5. <span data-ttu-id="cd0df-113">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-113">Click **Save**.</span></span>

<span data-ttu-id="cd0df-114">예를 들어 보낸 메시지가 삭제 되거나 변경 되지 않도록 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-114">For example, say you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="cd0df-115">"보낸 메시지 보존" 이라는 새 사용자 지정 정책을 만들고 다음 설정을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-115">Create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="cd0df-116">소유자가 보낸 메시지를 삭제할 수 있음</span><span class="sxs-lookup"><span data-stu-id="cd0df-116">Owners can delete sent messages</span></span>
- <span data-ttu-id="cd0df-117">사용자가 보낸 메시지를 삭제할 수 있음</span><span class="sxs-lookup"><span data-stu-id="cd0df-117">Users can delete sent messages</span></span>
- <span data-ttu-id="cd0df-118">사용자가 보낸 메시지를 편집할 수 있음</span><span class="sxs-lookup"><span data-stu-id="cd0df-118">Users can edit sent messages</span></span>

<span data-ttu-id="cd0df-119">그런 다음 사용자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-119">Then assign the policy to users.</span></span>

## <a name="edit-a-messaging-policy"></a><span data-ttu-id="cd0df-120">메시징 정책 편집</span><span class="sxs-lookup"><span data-stu-id="cd0df-120">Edit a messaging policy</span></span>

<span data-ttu-id="cd0df-121">만드는 모든 사용자 지정 정책에 대 한 전역 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-121">You can edit the global policy an any custom policies that you create.</span></span> 

1. <span data-ttu-id="cd0df-122">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **메시징 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-122">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="cd0df-123">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-123">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="cd0df-124">여기서 원하는 대로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-124">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="cd0df-125">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-125">Click **Save**.</span></span>

## <a name="assign-a-custom-messaging-policy-to-users"></a><span data-ttu-id="cd0df-126">사용자에 게 사용자 지정 메시징 정책 할당</span><span class="sxs-lookup"><span data-stu-id="cd0df-126">Assign a custom messaging policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="cd0df-127">사용자는 한 번에 하나의 메시징 정책만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-127">A user can only be assigned one messaging policy at a time.</span></span>

> [!NOTE]
> <span data-ttu-id="cd0df-128">사용자가 할당 된 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-128">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="cd0df-129">먼저 영향을 받는 모든 사용자에 게 다른 정책을 할당 한 다음 원래 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-129">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="cd0df-130">메시징 정책 설정</span><span class="sxs-lookup"><span data-stu-id="cd0df-130">Messaging policy settings</span></span>

<span data-ttu-id="cd0df-131">구성할 수 있는 메시징 정책 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-131">Here are the messaging policy settings that you can configure.</span></span>

- <span data-ttu-id="cd0df-132">**소유자가 보낸 메시지를 삭제할 수 있음**  이 설정을 사용 하 여 사용자가 채팅에서 보낸 메시지를 소유자가 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-132">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="cd0df-133">**사용자가 보낸 메시지를 삭제할 수 있음** 이 설정을 사용 하 여 사용자가 채팅에서 보낸 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-133">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="cd0df-134">**사용자가 보낸 메시지를 편집할 수 있음** 이 설정을 사용 하 여 사용자가 채팅에서 보낸 메시지를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-134">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="cd0df-135">**읽음** 확인 읽음 확인을 통해 메시지를 보낸 사람이 1:1 및 그룹 채팅 20 명 이하의 받는 사람에 게 메시지가 읽었을 때 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-135">**Read receipts** Read receipts allow the sender of a chat message to be notified when their message was read by the recipient in 1:1 and group chats 20 people or less.</span></span> <span data-ttu-id="cd0df-136">메시지 읽음 확인 메시지의 읽음 여부에 대 한 uncertainly를 제거 하 고 팀 의사 소통을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-136">Message read receipts remove uncertainly about whether a message was read, and improve team communication.</span></span> <span data-ttu-id="cd0df-137">읽음 확인은 eDiscovery 보고에서 캡처되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-137">Please note that read receipts are not captured in eDiscovery reporting.</span></span>  
    - <span data-ttu-id="cd0df-138">**사용자 제어** 즉, 사용자가 읽음 확인을 설정 하거나 해제 하도록 할 것인지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-138">**User controlled** This means that users get to decide if they want read receipts ON or OFF.</span></span> <span data-ttu-id="cd0df-139">앱 내의 기본 설정이 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-139">Default setting within the app is ON.</span></span> <span data-ttu-id="cd0df-140">사용자는이 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-140">Users can then turn it OFF.</span></span>
    - <span data-ttu-id="cd0df-141">**모든 사용자 용** 이것은 테 넌 트의 모든 사용자가 기능을 해제 하는 옵션이 없다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-141">**On for everyone** This means everyone in the tenant will have the feature ON with no option to turn it off.</span></span> <span data-ttu-id="cd0df-142">**모든 사용자** 에 대해 확인을 사용 하는 경우 전체 테 넌 트에 대해 확인 메일을 한 개만 설정 ("Global (Org wide default)" 이라는 기본 정책) 하거나 테 넌 트의 모든 메시징 정책에 동일한 확인 설정을 사용 하는 유일한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-142">Be aware that when using the **On for everyone** setting, the only way to set receipts for the whole tenant is either to have only one messaging policy for the whole tenant (the default policy named "Global (Org-wide Default)") or to have all messaging policies in the tenant use the same settings for receipts.</span></span> <span data-ttu-id="cd0df-143">읽음 확인 기능은 **모든 사용자**가 기능을 사용 하도록 설정 하는 경우에 가장 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-143">The read receipts feature is most effective when the feature is enabled to **On for everyone**.</span></span>
    - <span data-ttu-id="cd0df-144">**모든 사용자에 대해 끄기** 즉, 기능을 사용할 수 없으며, 테 넌 트에서 읽음 확인을 사용 하지 않거나이를 켤 방법이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-144">**Off for everyone** This means the feature is disabled and no one in the tenant has read receipts nor can they turn it on.</span></span>
<span data-ttu-id="cd0df-145"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="cd0df-145"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="cd0df-146">**채팅**  조직의 사용자가 팀 앱을 사용 하 여 다른 사용자와 채팅할 수 있도록 하려면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-146">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="cd0df-147">**대화에서 Giphy 사용**  이 기능을 설정 하면 사용자가 다른 사용자와 채팅 대화에 Giphy를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-147">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="cd0df-148">Giphy는 사용자가 애니메이션 GIF 파일을 검색하고 공유할 수 있는 온라인 데이터베이스 및 검색 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-148">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="cd0df-149">각 Giphy에는 콘텐츠 등급이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-149">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="cd0df-150">**Giphy 콘텐츠 등급**</span><span class="sxs-lookup"><span data-stu-id="cd0df-150">**Giphy content rating**</span></span>
    - <span data-ttu-id="cd0df-151">**제한 사항 없음** 즉, 사용자가 콘텐츠 등급에 관계 없이 채팅에 모든 Giphy를 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-151">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="cd0df-152">**보통**  즉, 사용자가 채팅에 Giphy를 삽입할 수 있으 나, 성인 콘텐츠에서 중급으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-152">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="cd0df-153">**Strict**  즉, 사용자가 채팅에 Giphy를 삽입할 수 있지만 성인 콘텐츠는 완전히 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-153">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="cd0df-154">**대화에서 Memes 사용** 이 기능을 설정 하는 경우 사용자는 다른 사용자와 대화를 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-154">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span>
- <span data-ttu-id="cd0df-155">**대화에서 스티커 사용** 이 기능을 켜면 다른 사용자와 채팅 대화에 스티커를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-155">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="cd0df-156">**URL 미리 보기 허용** 이 설정을 사용 하 여 메시지에서 자동 URL 미리 보기를 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-156">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="cd0df-157">**사용자가 메시지를 번역할 수 있도록 허용** 사용자가 팀 메시지를 Microsoft 365 또는 Office 365의 개인 언어 설정에서 지정한 언어로 자동으로 번역할 수 있도록 하려면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-157">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="cd0df-158">**몰입 형 리더의 메시지 보기 허용** 이 설정을 사용 하면 사용자가 Microsoft 몰입 형 리더에서 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-158">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="cd0df-159">몰입 형 리더는 텍스트의 가독성을 높이기 위해 전체 화면 읽기 환경을 제공 하는 학습 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-159">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="cd0df-160">**우선 순위 알림을 사용 하 여 긴급 메시지 보내기** 이 기능을 설정 하면 사용자는 [우선 순위 알림을](https://support.microsoft.com/en-us/office/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)사용 하 여 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-160">**Send urgent messages using priority notifications** If you turn this on, users can send messages using [priority notifications](https://support.microsoft.com/en-us/office/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462).</span></span> <span data-ttu-id="cd0df-161">우선 순위 알림은 사용자에 게 20 분 동안 또는 *긴급* 으로 표시 된 메시지가 받는 사람에 의해 선택 되 고 읽으 며 메시지가 적시에 처리 될 가능성을 극대화할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-161">Priority notifications notify users every 2 minutes for a period of 20 minutes or until messages that are marked as *urgent* are picked up and read by the recipient, maximizing the likelihood that the message is acted upon in a timely manner.</span></span>
- <span data-ttu-id="cd0df-162">**오디오 메시지 만들기**</span><span class="sxs-lookup"><span data-stu-id="cd0df-162">**Audio message creation**</span></span> 
  > [!Important]
  > <span data-ttu-id="cd0df-163">EDiscovery 보고에서 오디오 메시지가 캡처되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-163">Audio messages are not captured in eDiscovery reporting.</span></span>
    - <span data-ttu-id="cd0df-164">**채팅 및 채널에서 허용** 즉, 사용자가 채팅 및 채널 모두에서 오디오 메시지를 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-164">**Allowed in chats and channels** This means that users can leave audio messages in both chats and channels.</span></span>
    - <span data-ttu-id="cd0df-165">**채팅에만 허용 됨** 즉, 사용자가 채팅에 오디오 메시지를 남길 수 있지만 채널에는 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-165">**Allowed in chats only** This means that users can leave audio messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="cd0df-166">**사용 안 함** 이는 사용자가 채팅 또는 채널에서 오디오 메시지를 만들 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-166">**Disabled** This means that users cannot create audio messages in chats or channels.</span></span>  
- <span data-ttu-id="cd0df-167">**모바일 장치에서 최근 채팅 위에 즐겨찾기 채널 표시** 사용자가 스크롤할 필요가 없도록 즐겨찾기 채널을 모바일 디바이스 화면 위쪽으로 이동 하려면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-167">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span>
- <span data-ttu-id="cd0df-168">**사용자가 그룹 채팅에서 사용자를 제거할 수 있도록 허용** 사용자가 그룹 채팅에서 다른 사용자를 제거할 수 있도록 하려면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-168">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="cd0df-169">이 기능을 사용 하면 채팅 기록을 잃지 않고 더 적은 그룹의 사람들과 채팅을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-169">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>
- <span data-ttu-id="cd0df-170">**제안 된 회신 사용**  채팅 메시지에 대해 제안 된 회신을 사용 하도록 설정 하려면이 설정을 켜십시오.</span><span class="sxs-lookup"><span data-stu-id="cd0df-170">**Enable suggested replies**  Turn this setting on to enable suggested replies for chat messages.</span></span>

> [!NOTE]
> <span data-ttu-id="cd0df-171">Giphy를 사용 하는 등 이러한 설정 중 일부는 팀 소유자에 의해 또는 개인 채널 소유자가 개인 채널 수준에 따라 팀 수준에서 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0df-171">Some of these settings, such using Giphys, can also be configured at the team level by team owners and at the private channel level by private channel owners.</span></span>

### <a name="related-topics"></a><span data-ttu-id="cd0df-172">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cd0df-172">Related topics</span></span>

- [<span data-ttu-id="cd0df-173">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="cd0df-173">Assign policies to your users in Teams</span></span>](assign-policies.md)
