---
title: Teams 및 Skype 상호 연동성
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
description: 조직의 사용자와 소비자(소비자) Teams 사용자 간의 상호 Skype 기능에 대해 자세히 알아보습니다.
localization_priority: Normal
ms.openlocfilehash: e3203c03043dbcdb04370cf3aa26b435fad4a728
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093958"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="58305-103">Teams 및 Skype 상호 연동성</span><span class="sxs-lookup"><span data-stu-id="58305-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="58305-104">이 문서에서는 사용자와 소비자(소비자) 간의 상호 Microsoft Teams Skype 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58305-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="58305-105">사용자 및 Teams 사용자가 Skype 및 적용되는 관리자 컨트롤을 통해 통신할 수 있는 방법에 대해 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="58305-106">Teams 사용자가 전자 메일 주소를 사용하여 사용자와 채팅하고 Skype 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="58305-107">Teams 사용자와 일대일 텍스트 전용 대화 또는 오디오/비디오 통화를 검색하고 시작할 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="58305-108">Skype 사용자와 일대일 텍스트 전용 대화 또는 오디오/비디오 통화를 검색하고 시작할 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="58305-109">이러한 기능은 데스크톱, 웹 및 모바일(Android 및 iOS) 클라이언트에서 Teams 및 Skype.</span><span class="sxs-lookup"><span data-stu-id="58305-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="58305-110">최적의 환경을 위해 버전 Skype 8.58 이상을 추천합니다.</span><span class="sxs-lookup"><span data-stu-id="58305-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="58305-111">이 문서에서 Teams 및 Skype 인터로프 기능은 GCC 또는 높은 GCC DOD 배포 또는 사설 클라우드 환경에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="58305-112">채팅 및 통화 환경</span><span class="sxs-lookup"><span data-stu-id="58305-112">Chat and calling experience</span></span>

<span data-ttu-id="58305-113">다음은 채팅 및 통화 경험에 대한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="58305-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="58305-114">Teams 사용자와 채팅 또는 Skype 시작</span><span class="sxs-lookup"><span data-stu-id="58305-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="58305-115">Teams 사용자가 새 채팅 또는 검색 Skype 전자 메일 주소를 입력하여 사용자 검색을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="58305-116">그러면 Teams 사용자가 검색 결과에서 Skype 사용자를 선택하여 채팅을 시작하거나 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="58305-117">사용자가 Skype 결과에 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="58305-118">이 경우 사용자가 검색 결과에 표시되지 Teams Teams 사용자가 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="58305-119">Skype 사용자와 채팅 또는 Teams 시작</span><span class="sxs-lookup"><span data-stu-id="58305-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="58305-120">Skype 사용자가 전자 메일 주소를 사용하여 Teams 채팅을 검색하고 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="58305-121">Teams 사용자가 새 메시지를 Skype 메시지가 표시되고 먼저 메시지를 수락해야 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="58305-122">사용자가 Teams 수락을 선택하면 대화가 수락됩니다. 두 사용자가 서로 채팅하고 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="58305-123">사용자 Teams 차단을 선택하면 대화가 차단되어 해당 사용자로부터의 후속 메시지와 Skype 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="58305-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="58305-124">Teams 사용자가 메시지 보기를 선택하면 메시지가 Teams 표시되어 사용자가 대화를 수락하거나 차단할지 여부를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58305-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="58305-125">사용자가 비즈니스용 Skype Teams 전용 모드에 있는 경우 Teams 사용자로부터 Skype 사용자로 Teams 채팅 및 통화가 Teams.</span><span class="sxs-lookup"><span data-stu-id="58305-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="58305-126">사용자가 제도 모드인 경우 사용자로부터 Skype 사용자가 Teams 채팅 및 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="58305-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="58305-127">Teams 사용자 차단 또는 차단 Skype 차단 해제</span><span class="sxs-lookup"><span data-stu-id="58305-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="58305-128">사용자가 Teams 사용자로부터 초기 대화 요청을 수락하거나 차단한 Skype 사용자는 해당 사용자를 차단하거나 차단 해제하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="58305-129">대화 또는 개인 정보 설정에서 이 작업을 Teams.</span><span class="sxs-lookup"><span data-stu-id="58305-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="58305-130">Skype 사용자가 차단된 것을 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="58305-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="58305-131">차단된 Skype 사용자가 차단한 다른 사용자 및 공용 PSTN(공용 전화 네트워크) 전화 번호와 함께 Teams 사용자가 차단한 연락처 목록에 Teams.</span><span class="sxs-lookup"><span data-stu-id="58305-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="58305-132">제한 사항</span><span class="sxs-lookup"><span data-stu-id="58305-132">Limitations</span></span>

- <span data-ttu-id="58305-133">대화는 텍스트 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="58305-133">Conversations are text-only.</span></span> <span data-ttu-id="58305-134">즉, 기본 채팅 환경 에서 사용할 수 있는 다양한 서식, @mentions, 이모지 또는 기타 다른 채팅 기능이 Teams [없습니다.](native-chat-for-external-users.md)</span><span class="sxs-lookup"><span data-stu-id="58305-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="58305-135">대화는 일대일 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="58305-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="58305-136">그룹 채팅은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="58305-137">Teams 사용자 및 Skype 사용자가 서로의 현재 상태는 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="58305-138">자신의 Skype ID 또는 전화 번호를 사용하여 Skype 사용자를 검색하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="58305-139">Skype 다른 사용자의 Teams 대리자 번호 또는 PSTN(공용 전환 전화 네트워크) 번호로 통화를 설정한 사용자에게 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="58305-140">음성메일만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="58305-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="58305-141">인터팝 에스컬레이터, 그룹 호출 및 모임은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="58305-142">대리인이 사용자를 대신하여 Skype 사용자를 호출하는 Teams 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="58305-143">채팅과 화면 공유는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="58305-144">사용자가 Teams 통신할 수 있는지 Skype 설정</span><span class="sxs-lookup"><span data-stu-id="58305-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="58305-145">관리자는 관리 센터 또는 Microsoft Teams PowerShell을 사용하여 외부 액세스 설정을 설정하여 조직의 Teams 사용자와 통신할 수 있는지 여부를 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="58305-146">기본적으로 이 기능은 새 테넌트에 대해 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="58305-147">그러나 도메인에 아직 사용할 수 없는 경우 IT 관리자가 다음 DNS SRV 레코드를 구성해야 합니다(예: _sipfederationtls.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="58305-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="58305-148">**서비스**: sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="58305-148">**Service**: sipfederationtls</span></span><br/>
<span data-ttu-id="58305-149">**프로토콜**: TCP</span><span class="sxs-lookup"><span data-stu-id="58305-149">**Protocol**: TCP</span></span><br/>
<span data-ttu-id="58305-150">**우선** 순위 : 100</span><span class="sxs-lookup"><span data-stu-id="58305-150">**Priority**: 100</span></span><br/>
<span data-ttu-id="58305-151">**무게**: 1</span><span class="sxs-lookup"><span data-stu-id="58305-151">**Weight**: 1</span></span><br/>
<span data-ttu-id="58305-152">**포트**: 5061</span><span class="sxs-lookup"><span data-stu-id="58305-152">**Port**: 5061</span></span><br/>
<span data-ttu-id="58305-153">**대상**: sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="58305-153">**Target**: sipfed.online.lync.com</span></span>

<span data-ttu-id="58305-154">비즈니스용 Skype Teams 업그레이드한 경우 비즈니스용 Skype 관리 센터에서 구성한 외부 통신 설정이 Teams.</span><span class="sxs-lookup"><span data-stu-id="58305-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="58305-155">Microsoft Teams 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="58305-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="58305-156">Microsoft Teams 관리 센터에서 **Org-wide 설정** 외부 액세스로 이동한 다음 사용자를 켜면 사용자와 통신할  >   **Skype 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="58305-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="58305-157">이 및 기타 외부 액세스 설정을 구성하는 방법에 대한 단계별 지침은 에서 외부 [액세스 관리를 Teams.](./manage-external-access.md#allow-or-block-domains)</span><span class="sxs-lookup"><span data-stu-id="58305-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](./manage-external-access.md#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="58305-158">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="58305-158">Using PowerShell</span></span>

<span data-ttu-id="58305-159">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="58305-159">Do the following:</span></span> 
1. <span data-ttu-id="58305-160">[Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet을 매개 변수와 함께 사용하여 Teams 사용자와 통신할 수 있는지 Skype ```EnablePublicCloudAccess``` 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="58305-160">Use the [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="58305-161">매개 변수를 설정하여 Teams ```true``` 사용자와 통신할 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="58305-162">매개 변수를 ```EnablePublicCloudAudioVideoAccess``` 사용하여 오디오/비디오 통화를 사용하도록 설정/사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="58305-163">[Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet을 매개 변수 집합과 함께 사용하여 Teams 사용자와 통신할 Skype ```Provider``` ```"WindowsLive"``` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58305-163">Use the [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="58305-164">관련 항목</span><span class="sxs-lookup"><span data-stu-id="58305-164">Related topics</span></span>

- [<span data-ttu-id="58305-165">외부 액세스 관리 Teams</span><span class="sxs-lookup"><span data-stu-id="58305-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="58305-166">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="58305-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)