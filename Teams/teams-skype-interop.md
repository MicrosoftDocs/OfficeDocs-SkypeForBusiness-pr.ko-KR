---
title: 팀 및 Skype 상호 운용성
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 조직의 팀 사용자와 Skype (소비자) 사용자 간의 상호 운용성 기능에 대해 알아봅니다.
localization_priority: Normal
ms.openlocfilehash: 18031f9d1f4ae9a4e42525f8c722259590349c24
ms.sourcegitcommit: e95519cbcc4078810b251c6725863e4610323319
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925430"
---
# <a name="teams-and-skype-interoperability"></a><span data-ttu-id="bb01c-103">팀 및 Skype 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="bb01c-103">Teams and Skype interoperability</span></span>

<span data-ttu-id="bb01c-104">이 문서에서는 Microsoft 팀과 Skype (소비자) 간의 상호 운용성 기능에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-104">This article gives you an overview of the interoperability capabilities between Microsoft Teams and Skype (Consumer).</span></span> <span data-ttu-id="bb01c-105">팀 사용자와 Skype 사용자가 채팅 및 통화와 적용 되는 관리 제어를 통해 통신 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-105">Learn how Teams users and Skype users can communicate through chats and calls and the admin controls that apply.</span></span>

<span data-ttu-id="bb01c-106">조직의 팀 사용자는 전자 메일 주소를 사용 하 여 Skype 사용자와 채팅 하 고 그 반대의 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-106">Teams users in your organization can chat with and call Skype users by using their email address and vice versa.</span></span>

- <span data-ttu-id="bb01c-107">팀 사용자는 일대일 텍스트 대화 또는 Skype 사용자와의 음성/영상 통화를 검색 하 고 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-107">Teams users can search for and start a one-on-one text-only conversation or an audio/video call with a Skype user.</span></span>
- <span data-ttu-id="bb01c-108">Skype 사용자는 일대일 텍스트 대화 또는 팀 사용자와의 음성/영상 통화를 검색 하 고 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-108">Skype users can search for and start a one-on-one text-only conversation or an audio/video call with a Teams user.</span></span>

<span data-ttu-id="bb01c-109">이러한 접근 권한 값은 팀과 Skype 모두를 위한 데스크톱, 웹, 모바일 (Android 및 iOS) 클라이언트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-109">These capabilities are available on the desktop, web, and mobile (Android and iOS) clients for both Teams and Skype.</span></span> <span data-ttu-id="bb01c-110">최상의 환경을 위해서는 Skype 버전 8.58 이상을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-110">For an optimal experience, we recommend Skype version 8.58 and later.</span></span>

> [!NOTE]
> <span data-ttu-id="bb01c-111">이 문서에서 설명 하는 팀 및 Skype interop 기능은 GCC, GCC 높음 또는 DOD 배포 또는 사설 클라우드 환경에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-111">The Teams and Skype interop capabilities discussed in this article aren't available in GCC, GCC High, or DOD deployments, or in private cloud environments.</span></span>

## <a name="chat-and-calling-experience"></a><span data-ttu-id="bb01c-112">채팅 및 통화 환경</span><span class="sxs-lookup"><span data-stu-id="bb01c-112">Chat and calling experience</span></span>

<span data-ttu-id="bb01c-113">다음은 채팅 및 통화 환경에 대 한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-113">Here's an overview of the chat and calling experience.</span></span>

### <a name="teams-user-starts-a-chat-or-call-with-a-skype-user"></a><span data-ttu-id="bb01c-114">팀 사용자가 Skype 사용자와 채팅 또는 통화 시작</span><span class="sxs-lookup"><span data-stu-id="bb01c-114">Teams user starts a chat or call with a Skype user</span></span>

<span data-ttu-id="bb01c-115">팀 사용자는 새 채팅 또는 검색 창에 전자 메일 주소를 입력 하 여 Skype 사용자를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-115">Teams users can search for a Skype user by typing their email address in a new chat or in the search bar.</span></span>  <span data-ttu-id="bb01c-116">그런 다음 팀 사용자는 검색 결과에서 Skype 사용자를 선택 하 여 채팅 또는 통화를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-116">The Teams user can then select the Skype user in the search results to start a chat or call with them.</span></span>

<span data-ttu-id="bb01c-117">Skype 사용자가 검색 결과에 표시 하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-117">A Skype user may choose not to appear in search results.</span></span> <span data-ttu-id="bb01c-118">이 경우 팀에서 검색 결과에 표시 되지 않으며 팀 사용자가 찾을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-118">In this case, they won't show up in the search results in Teams and Teams users won't be able to find them.</span></span>

### <a name="skype-user-starts-a-chat-or-call-with-a-teams-user"></a><span data-ttu-id="bb01c-119">Skype 사용자와의 채팅 또는 팀 사용자와의 통화 시작</span><span class="sxs-lookup"><span data-stu-id="bb01c-119">Skype user starts a chat or call with a Teams user</span></span>

<span data-ttu-id="bb01c-120">Skype 사용자는 전자 메일 주소를 사용 하 여 팀 사용자와 채팅을 검색 하 고 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-120">Skype users can search for and start a chat with a Teams user by using their email address.</span></span> <span data-ttu-id="bb01c-121">팀 사용자에 게는 Skype 사용자가 보낸 새 메시지가 있고 먼저 메시지를 수락 하 고 회신할 수 있다는 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-121">The Teams user is notified that they have a new message from a Skype user, and has to first accept the message before they can reply to it.</span></span>

- <span data-ttu-id="bb01c-122">팀 사용자가 **수락** 을 선택 하면 대화가 수락 되 고 두 사용자 모두 서로 채팅 하 고 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-122">If the Teams user selects **Accept** , the conversation is accepted, and both users can chat and call each other.</span></span>
- <span data-ttu-id="bb01c-123">팀 사용자가 **블록** 을 선택 하면 대화가 차단 되 고 이후 해당 Skype 사용자의 후속 메시지와 통화가 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-123">If the Teams user selects **Block** , the conversation is blocked, and subsequent messages and calls from that Skype user are blocked.</span></span>
- <span data-ttu-id="bb01c-124">팀 사용자가 **메시지 보기** 를 선택 하면 해당 메시지가 팀에 표시 되므로 사용자는 대화를 수락 하거나 차단할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-124">If the Teams user selects **View messages** , the message is displayed in Teams, which helps the user decide whether to accept or block the conversation.</span></span>

> [!NOTE]
> <span data-ttu-id="bb01c-125">비즈니스용 Skype에서 팀으로 업그레이드 한 경우 사용자가 팀 전용 모드 이면 Skype 사용자와의 채팅 및 통화가 팀에 게 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-125">If you upgraded from Skype for Business to Teams and your users are in Teams Only mode, chats and calls from Skype users to Teams users are delivered to Teams.</span></span> <span data-ttu-id="bb01c-126">사용자가 군도 모드에 있는 경우 Skype 사용자에 대 한 채팅 및 전화 통화는 비즈니스용 Skype로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-126">If your users are in Islands mode, chats and calls from Skype users to Teams users are delivered to Skype for Business.</span></span>

### <a name="teams-user-blocks-or-unblocks-a-skype-user"></a><span data-ttu-id="bb01c-127">팀 사용자가 Skype 사용자를 차단 하거나 차단을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-127">Teams user blocks or unblocks a Skype user</span></span>

<span data-ttu-id="bb01c-128">팀 사용자가 Skype 사용자의 초기 대화 요청을 수락 하거나 차단 하 게 되 면 언제 든 지 해당 사용자를 차단 또는 차단 해제 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-128">After a Teams user accepts or blocks the initial conversation request from a Skype user, they can choose to block or unblock that person at any time.</span></span> <span data-ttu-id="bb01c-129">이 작업은 대화 또는 팀의 개인 정보 설정에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-129">They can do this either in the conversation or in their privacy settings in Teams.</span></span> <span data-ttu-id="bb01c-130">Skype 사용자는 이들이 차단 되었음을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-130">Skype users won't know that they've been blocked.</span></span>

<span data-ttu-id="bb01c-131">차단 된 Skype 사용자, 팀 사용자가 차단한 다른 사용자 및 PSTN (공개 전화 네트워크) 전화 번호와 함께 팀의 사용자 차단 연락처 목록에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-131">Blocked Skype users, along with other people and public switched telephone network (PSTN) phone numbers that a Teams user has blocked, are listed on the user's blocked contact list in Teams.</span></span>

## <a name="limitations"></a><span data-ttu-id="bb01c-132">따릅니다</span><span class="sxs-lookup"><span data-stu-id="bb01c-132">Limitations</span></span>

- <span data-ttu-id="bb01c-133">대화는 텍스트 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-133">Conversations are text-only.</span></span> <span data-ttu-id="bb01c-134">즉, [기본 팀 채팅 환경](native-chat-for-external-users.md)에서 사용할 수 있는 다양 한 서식, @mentions, emojis 또는 기타 채팅 기능을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-134">This means that there's no rich formatting, @mentions, emojis, or other any of the other chat features that are available in a [native Teams chat experience](native-chat-for-external-users.md).</span></span>
- <span data-ttu-id="bb01c-135">대화는 일대일로만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-135">Conversations are one-on-one only.</span></span> <span data-ttu-id="bb01c-136">그룹 채팅은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-136">Group chats aren't supported.</span></span>
- <span data-ttu-id="bb01c-137">팀 사용자와 Skype 사용자는 서로의 현재 상태를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-137">Teams users and Skype users can't see each other's presence.</span></span>
- <span data-ttu-id="bb01c-138">Skype ID 또는 전화 번호를 사용 하 여 Skype 사용자를 검색 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-138">Searching for Skype users by using their Skype ID or phone number isn't supported.</span></span>
- <span data-ttu-id="bb01c-139">Skype 사용자는 다른 사용자의 번호로 착신 전환을 설정한 팀 사용자, 대리인 번호 또는 PSTN (공개 통신 네트워크) 번호로 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-139">Skype users can't call Teams users who set up call forwarding to another user's number, a delegate's number, or a Public Switched Telephone Network (PSTN) number.</span></span>  <span data-ttu-id="bb01c-140">보이스 메일만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-140">Only voicemail is supported.</span></span>
- <span data-ttu-id="bb01c-141">Interop 에스컬레이션, 그룹 통화 및 회의가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-141">Interop escalation, group calls, and meetings aren't supported.</span></span>
- <span data-ttu-id="bb01c-142">대리인이 팀 사용자 대신 Skype 사용자에 게 전화를 걸 수 있는 능력은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-142">The ability for a delegate to call a Skype user on behalf of a Teams user isn't supported.</span></span>
- <span data-ttu-id="bb01c-143">채팅을 사용한 화면 공유는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-143">Screen sharing with chat isn't supported.</span></span>

## <a name="set-whether-teams-users-can-communicate-with-skype-users"></a><span data-ttu-id="bb01c-144">팀 사용자가 Skype 사용자와 통신할 수 있는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="bb01c-144">Set whether Teams users can communicate with Skype users</span></span>

<span data-ttu-id="bb01c-145">관리자는 Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 조직의 사용자가 Skype 사용자와 통신할 수 있는지 여부를 제어 하는 외부 액세스 설정을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-145">As an admin, you use the Microsoft Teams admin center or PowerShell to set external access settings to control whether Teams users in your organization can communicate with Skype users.</span></span> <span data-ttu-id="bb01c-146">기본적으로이 접근 권한 값은 새 테 넌 트에 대해 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-146">By default, this capability is turned on for new tenants.</span></span> <span data-ttu-id="bb01c-147">그러나 다음과 같이 도메인에 대해 아직 사용할 수 없는 경우에는 IT 관리자가 다음 DNS SRV 레코드를 구성 해야 한다는 전제 조건이 있습니다 _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="bb01c-147">However, there's a prerequisite that the following DNS SRV record needs to be configured by the IT Admin if not already available for your domain, for example _sipfederationtls.contoso.com.</span></span>  

<span data-ttu-id="bb01c-148">**서비스** : sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="bb01c-148">**Service** : sipfederationtls</span></span><br/>
<span data-ttu-id="bb01c-149">**프로토콜** : TCP</span><span class="sxs-lookup"><span data-stu-id="bb01c-149">**Protocol** : TCP</span></span><br/>
<span data-ttu-id="bb01c-150">**우선 순위** : 100</span><span class="sxs-lookup"><span data-stu-id="bb01c-150">**Priority** : 100</span></span><br/>
<span data-ttu-id="bb01c-151">**중량** : 1</span><span class="sxs-lookup"><span data-stu-id="bb01c-151">**Weight** : 1</span></span><br/>
<span data-ttu-id="bb01c-152">**포트** : 5061</span><span class="sxs-lookup"><span data-stu-id="bb01c-152">**Port** : 5061</span></span><br/>
<span data-ttu-id="bb01c-153">**대상** : sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="bb01c-153">**Target** : sipfed.online.lync.com</span></span>

<span data-ttu-id="bb01c-154">비즈니스용 Skype에서 팀으로 업그레이드 한 경우 비즈니스용 Skype 관리 센터에서 구성한 외부 통신 설정이 팀으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-154">If you upgraded from Skype for Business to Teams, the external communications settings that you configured in the Skype for Business admin center are migrated to Teams.</span></span>

### <a name="in-the-microsoft-teams-admin-center"></a><span data-ttu-id="bb01c-155">Microsoft Teams 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="bb01c-155">In the Microsoft Teams admin center</span></span>

<span data-ttu-id="bb01c-156">Microsoft 팀 관리 센터에서 **조직 전체 설정**  >  **외부 액세스** 로 이동한 다음 **사용자가 Skype 사용자와 통신할 수** 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-156">In the Microsoft Teams admin center, go to **Org-wide settings** > **External access** , and then turn on **Users can communicate with Skype users**.</span></span> <span data-ttu-id="bb01c-157">이 및 다른 외부 액세스 설정을 구성 하는 방법에 대 한 단계별 지침은 [팀에서 외부 액세스 관리](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb01c-157">For step-by-step guidance on how to configure this and other external access settings, see [Manage external access in Teams](https://docs.microsoft.com/microsoftteams/manage-external-access#allow-or-block-domains).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bb01c-158">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="bb01c-158">Using PowerShell</span></span>

<span data-ttu-id="bb01c-159">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-159">Do the following:</span></span> 
1. <span data-ttu-id="bb01c-160">[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet을 매개 변수와 함께 사용 ```EnablePublicCloudAccess``` 하 여 팀 사용자가 Skype 사용자와 통신할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-160">Use the [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy) cmdlet together with the ```EnablePublicCloudAccess``` parameter to control whether Teams users can communicate with Skype users.</span></span> <span data-ttu-id="bb01c-161">```true```팀 사용자가 Skype 사용자와 통신할 수 있도록 매개 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-161">Setting the parameter to ```true``` allows Teams users to communicate with Skype users.</span></span> <span data-ttu-id="bb01c-162">이 ```EnablePublicCloudAudioVideoAccess``` 매개 변수를 사용 하 여 오디오/비디오 통화를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb01c-162">You can use the ```EnablePublicCloudAudioVideoAccess``` parameter to enable/disable audio/video calls.</span></span>

2. <span data-ttu-id="bb01c-163">팀 사용자가 Skype 사용자와 통신할 수 있도록 [set-Csten앤틸리스 Publicprovider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet을 ```Provider``` 매개 변수 집합과 함께 사용 합니다 ```"WindowsLive"``` .</span><span class="sxs-lookup"><span data-stu-id="bb01c-163">Use the [Set-CsTenantPublicProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsTenantPublicProvider) cmdlet together with the ```Provider``` parameter set to ```"WindowsLive"``` so that Teams users can communicate with Skype users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb01c-164">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bb01c-164">Related topics</span></span>

- [<span data-ttu-id="bb01c-165">팀에서 외부 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="bb01c-165">Manage external access in Teams</span></span>](manage-external-access.md)
- [<span data-ttu-id="bb01c-166">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="bb01c-166">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
