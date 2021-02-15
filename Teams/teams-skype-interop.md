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
description: 조직의 Teams 사용자와 Skype(소비자) 사용자 간의 상호 연동성 기능에 대해 자세히 배워야 합니다.
localization_priority: Normal
ms.openlocfilehash: 8bb6a83eddc60ff680d1a08c7266e082dd8b0188
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055650"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="076c9-103">Teams 및 Skype 상호 연동성</span><span class="sxs-lookup"><span data-stu-id="076c9-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="076c9-104">이 문서에서는 Microsoft Teams와 Skype(소비자) 간의 상호 연동성 기능에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="076c9-105">Teams 사용자와 Skype 사용자가 채팅 및 통화 및 적용되는 관리 컨트롤을 통해 통신하는 방법을 배워보는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="076c9-106">조직의 Teams 사용자는 전자 메일 주소를 사용하여 Skype 사용자와 채팅하고 전화를 걸 수 있으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="076c9-107">Teams 사용자는 Skype 사용자와 일대일 텍스트 전용 대화 또는 오디오/비디오 통화를 검색하고 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="076c9-108">Skype 사용자는 Teams 사용자와 일대일 텍스트 전용 대화 또는 오디오/비디오 통화를 검색하고 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="076c9-109">이러한 기능은 Teams와 Skype 모두에 대한 데스크톱, 웹 및 모바일(Android 및 iOS) 클라이언트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="076c9-110">최적의 환경을 위해 Skype 버전 8.58 이상을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="076c9-111">이 문서에서 설명하는 Teams 및 Skype Interop 기능은 GCC, GCC High 또는 DOD 배포 또는 사설 클라우드 환경에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="076c9-112">채팅 및 통화 환경</span><span class="sxs-lookup"><span data-stu-id="076c9-112">Chat and calling experience</span></span>

<span data-ttu-id="076c9-113">다음은 채팅 및 통화 환경의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="076c9-114">Teams 사용자가 Skype 사용자와 채팅 또는 통화를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="076c9-115">Teams 사용자는 새 채팅 또는 검색 표시줄에 전자 메일 주소를 입력하여 Skype 사용자를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="076c9-116">그러면 Teams 사용자는 검색 결과에서 Skype 사용자를 선택하여 채팅을 시작하거나 해당 사용자와 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="076c9-117">Skype 사용자는 검색 결과에 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="076c9-118">이 경우 Teams의 검색 결과에는 표시되지 않습니다. Teams 사용자는 검색 결과를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="076c9-119">Skype 사용자가 Teams 사용자와 채팅 또는 통화를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="076c9-120">Skype 사용자는 전자 메일 주소를 사용하여 Teams 사용자와 채팅을 검색하고 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="076c9-121">Teams 사용자는 Skype 사용자의 새 메시지가 표시되고, 먼저 메시지를 수락해야 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="076c9-122">Teams 사용자가 수락을 선택하면 대화가 수락됩니다. 두 사용자가 서로 채팅하고 통화할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="076c9-122">If the Teams user selects **Accept**, the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="076c9-123">Teams 사용자가 차단을 선택하면 대화가 차단된 후 해당 Skype 사용자의 후속 메시지와 통화가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-123">If the Teams user selects **Block**, the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="076c9-124">Teams 사용자가 메시지 보기를 선택하면 메시지가 Teams에 표시되어 사용자가 대화를 수락하거나 차단할지 여부를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-124">If the Teams user selects **View messages**, the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="076c9-125">비즈니스용 Skype에서 Teams로 업그레이드하고 사용자가 Teams 전용 모드인 경우 Skype 사용자에서 Teams 사용자로의 채팅 및 통화가 Teams로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="076c9-126">사용자가 제도 모드인 경우 Skype 사용자에서 Teams 사용자로의 채팅 및 통화가 비즈니스용 Skype로 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="076c9-127">Teams 사용자 차단 또는 Skype 사용자 차단 해제</span><span class="sxs-lookup"><span data-stu-id="076c9-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="076c9-128">Teams 사용자가 Skype 사용자의 초기 대화 요청을 수락하거나 차단한 후 사용자는 해당 사용자를 차단하거나 차단을 해제하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="076c9-129">대화 또는 Teams의 개인 정보 설정에서 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="076c9-130">Skype 사용자는 차단된 것을 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="076c9-131">차단된 Skype 사용자는 Teams 사용자가 차단한 다른 사용자 및 PSTN(공용 전화망) 전화 번호와 함께 Teams의 사용자의 차단된 연락처 목록에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="076c9-132">제한 사항</span><span class="sxs-lookup"><span data-stu-id="076c9-132">Limitations</span></span>

- <span data-ttu-id="076c9-133">대화는 텍스트 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-133">Conversations are text-only.</span></span> <span data-ttu-id="076c9-134">즉, 기본 Teams 채팅 경험에서 사용할 수 있는 다양한 서식, @mentions, 이모지 또는 기타 채팅 기능이 [없습니다.](native-chat-for-external-users.md)</span><span class="sxs-lookup"><span data-stu-id="076c9-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="076c9-135">대화는 일대일 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="076c9-136">그룹 채팅은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="076c9-137">Teams 사용자와 Skype 사용자는 서로의 현재 상태는 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="076c9-138">Skype ID 또는 전화 번호를 사용하여 Skype 사용자를 검색하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="076c9-139">Skype 사용자는 통화 전달을 다른 사용자의 번호, 대리인 번호 또는 PSTN(공용 전화 네트워크) 번호로 설정한 Teams 사용자에게 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="076c9-140">음성메일만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="076c9-141">Interop 에스컬레이터, 그룹 통화 및 모임은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="076c9-142">대리인이 Teams 사용자를 대신하여 Skype 사용자를 호출하는 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="076c9-143">채팅을 통해 화면 공유는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="076c9-144">Teams 사용자가 Skype 사용자와 통신할 수 있는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="076c9-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="076c9-145">관리자는 Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 외부 액세스 설정을 설정하여 조직의 Teams 사용자가 Skype 사용자와 통신할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="076c9-146">기본적으로 이 기능은 새 테넌트에 대해 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="076c9-147">그러나 도메인에 대해 아직 사용할 수 없는 경우(예: _sipfederationtls.contoso.com) IT 관리자가 다음 DNS SRV 레코드를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="076c9-148">**서비스:** sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="076c9-148">**Service**: sipfederationtls</span></span><br/>
<span data-ttu-id="076c9-149">**프로토콜:** TCP</span><span class="sxs-lookup"><span data-stu-id="076c9-149">**Protocol**: TCP</span></span><br/>
<span data-ttu-id="076c9-150">**우선** 순위: 100</span><span class="sxs-lookup"><span data-stu-id="076c9-150">**Priority**: 100</span></span><br/>
<span data-ttu-id="076c9-151">**가중치:** 1</span><span class="sxs-lookup"><span data-stu-id="076c9-151">**Weight**: 1</span></span><br/>
<span data-ttu-id="076c9-152">**포트:** 5061</span><span class="sxs-lookup"><span data-stu-id="076c9-152">**Port**: 5061</span></span><br/>
<span data-ttu-id="076c9-153">**대상:** sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="076c9-153">**Target**: sipfed.online.lync.com</span></span>

<span data-ttu-id="076c9-154">비즈니스용 Skype에서 Teams로 업그레이드한 경우 비즈니스용 Skype 관리 센터에서 구성한 외부 통신 설정이 Teams로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="076c9-155">Microsoft Teams 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="076c9-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="076c9-156">Microsoft Teams 관리 센터에서 전체 설정 외부 액세스로 이동한 다음, 사용자를 켜면 Skype 사용자와  >   **통신할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="076c9-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access**, and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="076c9-157">이 설정 및 기타 외부 액세스 설정을 구성하는 방법에 대한 단계별 지침은 Teams에서 외부 액세스 [관리를 참조하세요.](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)</span><span class="sxs-lookup"><span data-stu-id="076c9-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="076c9-158">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="076c9-158">Using PowerShell</span></span>

<span data-ttu-id="076c9-159">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-159">Do the following:</span></span> 
1. <span data-ttu-id="076c9-160">[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet을 매개 변수와 함께 사용하여 Teams 사용자가 Skype 사용자와 통신할 수 있는지 ```EnablePublicCloudAccess``` 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-160">Use the [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="076c9-161">Teams 사용자가 Skype 사용자와 통신할 수 있도록 매개 ```true``` 변수를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="076c9-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="076c9-162">매개 변수를 ```EnablePublicCloudAudioVideoAccess``` 사용하여 오디오/비디오 통화를 활성화/비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="076c9-163">Teams 사용자가 Skype 사용자와 통신할 수 있도록 설정된 매개 변수와 함께 [Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet을 ```Provider``` ```"WindowsLive"``` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="076c9-163">Use the [Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="076c9-164">관련 항목</span><span class="sxs-lookup"><span data-stu-id="076c9-164">Related topics</span></span>

- [<span data-ttu-id="076c9-165">Teams에서 외부 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="076c9-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="076c9-166">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="076c9-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
