---
title: Teams에서 메시지 정책 관리
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
description: 메시징 정책 및 이러한 정책이 Teams에서 채팅 메시징을 제어하는 데 사용할 수 있는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 800bc37ee25c073d0702c519196620faa1faf92e
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574167"
---
# <a name="manage-messaging-policies-in-teams"></a><span data-ttu-id="4f0cd-103">Teams에서 메시지 정책 관리</span><span class="sxs-lookup"><span data-stu-id="4f0cd-103">Manage messaging policies in Teams</span></span>

<!--- Add zone marker here--->

<span data-ttu-id="4f0cd-104">메시징 정책은 Microsoft Teams의 사용자(소유자 및 구성원)에게 사용할 수 있는 채팅 및 채널 메시징 기능을 [제어하는](assign-roles-permissions.md) 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-104">Messaging policies are used to control which chat and channel messaging features are available to [users (owners and members)](assign-roles-permissions.md) in Microsoft Teams.</span></span> <span data-ttu-id="4f0cd-105">자동으로 생성된 전역(Org-wide default) 정책을 사용하거나 사용자 지정 메시징 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-105">You can use the global (Org-wide default) policy that's created automatically or create and assign custom messaging policies.</span></span>

<span data-ttu-id="4f0cd-106">조직의 사용자는 사용자 지정 정책을 만들고 할당하지 않는 한 전역 정책을 자동으로 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-106">Users in your organization will automatically get the global policy, unless you create and assign a custom policy.</span></span> <span data-ttu-id="4f0cd-107">전역 정책의 설정을 편집하거나 하나 이상의 사용자 지정 정책을 만들어 할당하여 원하는 기능을 켜거나 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-107">Edit the settings in the global policy or create and assign one or more custom policies to turn on or turn off the features that you want.</span></span>

## <a name="create-a-custom-messaging-policy"></a><span data-ttu-id="4f0cd-108">사용자 지정 메시징 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4f0cd-108">Create a custom messaging policy</span></span>

1. <span data-ttu-id="4f0cd-109">Microsoft Teams 관리 센터의 왼쪽 탐색에서 메시징 정책 **으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="4f0cd-109">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="4f0cd-110">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-110">Select **Add**.</span></span>
3. <span data-ttu-id="4f0cd-111">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-111">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="4f0cd-112">원하는 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-112">Choose the settings that you want.</span></span>
5. <span data-ttu-id="4f0cd-113">저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f0cd-113">Select **Save**.</span></span>

<span data-ttu-id="4f0cd-114">예를 들어 보낸 메시지가 삭제되거나 변경되지 않은지 확인하려는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-114">For example, you want to make sure that sent messages aren't deleted or altered.</span></span> <span data-ttu-id="4f0cd-115">"보낸 메시지 보존"이라는 새 사용자 지정 정책을 만들고 다음 설정을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-115">Create a new custom policy named "Retain sent messages" and turn off the following settings:</span></span>

- <span data-ttu-id="4f0cd-116">소유자가 보낸 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-116">Owners can delete sent messages</span></span>
- <span data-ttu-id="4f0cd-117">사용자가 보낸 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-117">Users can delete sent messages</span></span>
- <span data-ttu-id="4f0cd-118">사용자가 보낸 메시지를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-118">Users can edit sent messages</span></span>

<span data-ttu-id="4f0cd-119">그런 다음 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-119">Then assign the policy to users.</span></span>

## <a name="edit-a-messaging-policy"></a><span data-ttu-id="4f0cd-120">메시징 정책 편집</span><span class="sxs-lookup"><span data-stu-id="4f0cd-120">Edit a messaging policy</span></span>

<span data-ttu-id="4f0cd-121">전역 정책 및 만든 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-121">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="4f0cd-122">Microsoft Teams 관리 센터의 왼쪽 탐색에서 메시징 정책 **으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="4f0cd-122">In the left navigation of the Microsoft Teams admin center, go to **Messaging policies**.</span></span>
2. <span data-ttu-id="4f0cd-123">정책 이름의 왼쪽을 클릭하여 정책을 선택한 다음 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f0cd-123">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>
3. <span data-ttu-id="4f0cd-124">여기서 원하는 내용을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-124">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="4f0cd-125">저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4f0cd-125">Select **Save**.</span></span>

## <a name="assign-a-custom-messaging-policy-to-users"></a><span data-ttu-id="4f0cd-126">사용자에게 사용자 지정 메시징 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4f0cd-126">Assign a custom messaging policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="4f0cd-127">사용자는 한 번씩 하나의 메시징 정책만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-127">A user can only be assigned one messaging policy at a time.</span></span>

> [!NOTE]
> <span data-ttu-id="4f0cd-128">사용자가 할당된 경우 정책을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-128">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="4f0cd-129">먼저 영향을 받는 모든 사용자에게 다른 정책을 할당한 다음 원래 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-129">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

<!--- End zone marker here--->

## <a name="messaging-policy-settings"></a><span data-ttu-id="4f0cd-130">메시징 정책 설정</span><span class="sxs-lookup"><span data-stu-id="4f0cd-130">Messaging policy settings</span></span>

<span data-ttu-id="4f0cd-131">구성할 수 있는 메시징 정책 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-131">Here are the messaging policy settings that you can configure.</span></span>

- <span data-ttu-id="4f0cd-132">**소유자가 보낸 메시지를 삭제할 수 있습니다.**  이 설정을 사용하여 소유자가 채팅에서 보낸 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-132">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="4f0cd-133">**사용자가 보낸 메시지를 삭제할 수 있습니다.** 이 설정을 사용하여 사용자가 채팅에서 보낸 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-133">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="4f0cd-134">**사용자가 보낸 메시지를 편집할 수 있습니다.** 이 설정을 사용하여 사용자가 채팅에서 보낸 메시지를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-134">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="4f0cd-135">**영수증 읽기** 읽기 확인을 사용하면 받는 사람이 메시지를 1:1로 읽거나 그룹 채팅을 20명 이하로 읽은 경우 채팅 메시지 보낸 사람에게 알림을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-135">**Read receipts** Read receipts allow the sender of a chat message to be notified when their message was read by the recipient in 1:1 and group chats 20 people or fewer.</span></span> <span data-ttu-id="4f0cd-136">메시지 읽기 확인은 메시지를 읽은지 여부에 대한 불확실성을 제거하고 팀 통신을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-136">Message read receipts remove uncertainly about whether a message was read, and improve team communication.</span></span> <span data-ttu-id="4f0cd-137">읽기 확인은 eDiscovery 보고에 캡처되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-137">Read receipts aren't captured in eDiscovery reporting.</span></span>  
    - <span data-ttu-id="4f0cd-138">**사용자 제어** 즉, 사용자가 확인 확인을 ON 또는 OFF로 읽을지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-138">**User controlled** This means that users get to decide if they want read receipts ON or OFF.</span></span> <span data-ttu-id="4f0cd-139">앱 내의 기본 설정은 ON입니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-139">Default setting within the app is ON.</span></span> <span data-ttu-id="4f0cd-140">그런 다음 사용자가 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-140">Users can then turn it OFF.</span></span>
    - <span data-ttu-id="4f0cd-141">**모든 사람에 대한 On** 즉, 테넌트의 모든 사람이 기능을 해제할 수 있는 옵션이 없는 ON 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-141">**On for everyone** This means everyone in the tenant will have the feature ON with no option to turn it off.</span></span> <span data-ttu-id="4f0cd-142">모든 테넌트에 대한 수신 확인을 설정하는 유일한 방법은 전체 테넌트에 대해 하나의 메시징 정책("전역(Org-wide Default)"이라는 기본 정책)을 설정하거나 테넌트의 모든 메시징 정책이 수신에 대해 동일한 설정을 사용하는 것입니다. </span><span class="sxs-lookup"><span data-stu-id="4f0cd-142">When using the **On for everyone** setting, the only way to set receipts for the whole tenant is either to have only one messaging policy for the whole tenant (the default policy named "Global (Org-wide Default)") or to have all messaging policies in the tenant use the same settings for receipts.</span></span> <span data-ttu-id="4f0cd-143">읽음 확인 기능은 **모든 사용자에 대해 사용** 으로 설정된 경우 가장 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-143">The read receipts feature is most effective when the feature is enabled to **On for everyone**.</span></span>
    - <span data-ttu-id="4f0cd-144">**모든 사람에 대한 해제** 즉, 기능을 사용하지 않도록 설정하고 테넌트의 아무도 읽은 영수증을 읽지 않으며 켜지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-144">**Off for everyone** This means the feature is disabled and no one in the tenant has read receipts nor can they turn it on.</span></span>
<span data-ttu-id="4f0cd-145"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="4f0cd-145"><a name="bkchat"> </a></span></span>

- <span data-ttu-id="4f0cd-146">**채팅**  조직의 사용자가 Teams 앱을 사용하여 다른 사용자와 채팅할 수 있도록 하려는 경우 이 설정을 켜 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-146">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="4f0cd-147">**대화에서 Giphys 사용**  Giphys를 설정하면 사용자는 다른 사용자와의 채팅 대화에 Giphys를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-147">**Use Giphys in conversations**  If you turn on Giphys, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="4f0cd-148">Giphy는 사용자가 애니메이션 GIF 파일을 검색하고 공유할 수 있는 온라인 데이터베이스 및 검색 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-148">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="4f0cd-149">각 Giphy에는 콘텐츠 등급이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-149">Each Giphy is assigned a content rating.</span></span> <span data-ttu-id="4f0cd-150">이 설정을 켜는 것 외에도 선택적 [](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) 연결된 환경을 사용하도록 설정하여 대화에서 Giphys를 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-150">In addition to turning on this setting, you need to enable [Optional Connected Experiences](/deployoffice/privacy/manage-privacy-controls#policy-setting-for-optional-connected-experiences) to allow Giphys in conversations.</span></span>
- <span data-ttu-id="4f0cd-151">**Gipsy 콘텐츠 등급**</span><span class="sxs-lookup"><span data-stu-id="4f0cd-151">**Gipsy content rating**</span></span>
    - <span data-ttu-id="4f0cd-152">**제한 없음** 즉, 사용자가 콘텐츠 등급에 관계없이 채팅에 Giphy를 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-152">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="4f0cd-153">**보통**  즉, 사용자가 채팅에 Giphys를 삽입할 수 있지만 성인 콘텐츠에서 적당히 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-153">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="4f0cd-154">**엄격한**  즉, 사용자가 채팅에 Giphys를 삽입할 수 있지만 성인 콘텐츠에서 엄격히 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-154">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="4f0cd-155">**대화에서 Memes 사용** Memes를 켜면 다른 사용자와의 채팅 대화에 Memes를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-155">**Use Memes in conversations** If you turn Memes on, users can include Memes in chat conversations with other people.</span></span>
- <span data-ttu-id="4f0cd-156">\*\*대화에서 스티커를 사용.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-156">\*\*Use Stickers in conversations.</span></span> <span data-ttu-id="4f0cd-157">이 기능을 설정하면 다른 사용자와의 채팅 대화에 스티커를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-157">If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="4f0cd-158">**URL 미리 보기 허용** 이 설정을 사용하여 메시지에서 자동 URL 미리 보기를 켜거나 끄세요.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-158">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="4f0cd-159">**사용자가 메시지를 번역할 수 있도록 허용** 이 설정을 켜면 사용자가 Teams 메시지를 Microsoft 365 또는 Office 365에 대한 개인 언어 설정에서 지정한 언어로 자동으로 번역할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-159">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Microsoft 365 or Office 365.</span></span>
- <span data-ttu-id="4f0cd-160">**메시지 보기에 몰입형 판독기 허용** 이 설정을 켜서 사용자가 Microsoft 몰입형 읽기에서 메시지를 볼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-160">**Allow immersive reader for viewing messages** Turn this setting on to let users view messages in Microsoft Immersive Reader.</span></span> <span data-ttu-id="4f0cd-161">몰입형 읽기 프로그램은 텍스트의 가독성을 높이기 위해 전체 화면 읽기 환경을 제공하는 학습 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-161">Immersive Reader is a learning tool that provides a full screen reading experience to increase readability of text.</span></span>
- <span data-ttu-id="4f0cd-162">우선 순위 알림을 **사용하여 긴급 메시지 보내기** 이 기능을 켜면 사용자는 우선 순위 알림을 사용하여 메시지를 [보낼 수 있습니다.](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462)</span><span class="sxs-lookup"><span data-stu-id="4f0cd-162">**Send urgent messages using priority notifications** If you turn this on, users can send messages using [priority notifications](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462).</span></span> <span data-ttu-id="4f0cd-163">우선 순위 알림은 사용자에게 20분마다 또는 긴급으로 표시된  메시지가 수신자가 선택하고 읽을 때까지 사용자에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-163">Priority notifications notify users every 2 minutes for 20 minutes or until messages that are marked as *urgent* are picked up and read by the recipient.</span></span> <span data-ttu-id="4f0cd-164">이 기능은 메시지가 시기적절하게 행동할 가능성을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-164">This feature increases the likelihood that the message is acted upon in a timely manner.</span></span>
- <span data-ttu-id="4f0cd-165">**오디오 메시지 만들기**</span><span class="sxs-lookup"><span data-stu-id="4f0cd-165">**Audio message creation**</span></span>
  > [!Important]
  > <span data-ttu-id="4f0cd-166">오디오 메시지는 eDiscovery 보고에 캡처되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-166">Audio messages are not captured in eDiscovery reporting.</span></span>
    - <span data-ttu-id="4f0cd-167">**채팅 및 채널에서 허용** 즉, 사용자는 채팅과 채널 모두에서 오디오 메시지를 남길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-167">**Allowed in chats and channels** This means that users can leave audio messages in both chats and channels.</span></span>
    - <span data-ttu-id="4f0cd-168">**채팅에서만 허용** 즉, 사용자가 채팅에 오디오 메시지를 남길 수 있지만 채널에는 남길 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-168">**Allowed in chats only** This means that users can leave audio messages in chats, but not in channels.</span></span>
    - <span data-ttu-id="4f0cd-169">**사용하지 않도록 설정** 즉, 사용자가 채팅 또는 채널에서 오디오 메시지를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-169">**Disabled** This means that users cannot create audio messages in chats or channels.</span></span>  
- <span data-ttu-id="4f0cd-170">**모바일 장치에서 최근 채팅 위에 즐겨찾기 채널을 표시합니다.** 사용자가 해당 채널을 찾기 위해 스크롤할 필요가 없는 모바일 디바이스 화면의 맨 위로 즐겨찾기 채널을 이동하려면 이 설정을 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-170">**On mobile devices, display favorite channels above recent chats** Enable this setting to move favorite channels to the top of the mobile device screen so that a user doesn't need to scroll to find them.</span></span>
- <span data-ttu-id="4f0cd-171">**사용자가 그룹 채팅에서 사용자를 제거할 수 있도록 허용** 이 설정을 켜서 사용자가 그룹 채팅에서 다른 사용자를 제거하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-171">**Allow a user to remove users from a group chat** Turn this setting on to let a user remove other users from a group chat.</span></span> <span data-ttu-id="4f0cd-172">이 기능을 사용하면 채팅 기록을 잃지 않고 소규모 사용자 그룹과 채팅을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-172">This feature lets you continue a chat with a smaller group of people without losing the chat history.</span></span>
- <span data-ttu-id="4f0cd-173">**제안된 응답 사용**  채팅 메시지에 대해 제안된 응답을 사용하도록 설정하려면 이 설정을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-173">**Enable suggested replies**  Turn this setting on to enable suggested replies for chat messages.</span></span>
- <span data-ttu-id="4f0cd-174">**채팅 권한 역할** 이 설정을 사용하여 사용자의 감독된 채팅 역할을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-174">**Chat permission role** Use this setting to define the supervised chat role of the user.</span></span>  <span data-ttu-id="4f0cd-175">감독 채팅 [에 대해 자세히 알아보면 됩니다.](supervise-chats-edu.md)</span><span class="sxs-lookup"><span data-stu-id="4f0cd-175">Learn more about [supervised chat](supervise-chats-edu.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4f0cd-176">Giphys를 사용하는 등 이러한 설정 중 일부는 팀 소유자가 팀 수준에서 구성하고 개인 채널 소유자가 개인 채널 수준에서 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f0cd-176">Some of these settings, such using Giphys, can also be configured at the team level by team owners and at the private channel level by private channel owners.</span></span>

### <a name="related-topics"></a><span data-ttu-id="4f0cd-177">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4f0cd-177">Related topics</span></span>

- [<span data-ttu-id="4f0cd-178">Teams의 사용자 및 그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4f0cd-178">Assign policies to users and groups in Teams</span></span>](assign-policies-users-and-groups.md)
- [<span data-ttu-id="4f0cd-179">Microsoft Teams에서 팀 소유자 및 구성원 할당</span><span class="sxs-lookup"><span data-stu-id="4f0cd-179">Assign team owners and members in Microsoft Teams</span></span>](assign-roles-permissions.md)
