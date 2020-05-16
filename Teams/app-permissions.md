---
title: Microsoft 팀 앱 사용 권한 및 고려 사항
author: rmw2890
ms.author: rowille
manager: serdars
ms.date: 06/27/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
ms.reviewer: rowille
description: 관리자는 Microsoft 팀 앱에서 조직에 게 요청 하는 데이터 및 사용 권한을 확인할 수 있습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f19cbbba6df7c43c69af35893466344e8df1d17d
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256483"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="64e98-103">Microsoft 팀 앱 사용 권한 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="64e98-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="64e98-104">Microsoft 팀 앱은 하나 이상의 기능을 설치, 업그레이드 및 제거할 수 있는 _앱 패키지로_ 집계 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="64e98-105">접근 권한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-105">The capabilities include:</span></span>

- <span data-ttu-id="64e98-106">봇</span><span class="sxs-lookup"><span data-stu-id="64e98-106">Bots</span></span>
- <span data-ttu-id="64e98-107">메시징 확장</span><span class="sxs-lookup"><span data-stu-id="64e98-107">Messaging extensions</span></span>
- <span data-ttu-id="64e98-108">탭</span><span class="sxs-lookup"><span data-stu-id="64e98-108">Tabs</span></span>
- <span data-ttu-id="64e98-109">기가</span><span class="sxs-lookup"><span data-stu-id="64e98-109">Connectors</span></span>

<span data-ttu-id="64e98-110">앱은 사용자가 였음을 하 고 정책 관점에서 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="64e98-111">그러나 대부분의 경우 앱의 사용 권한과 위험 프로필은 앱에 포함 된 기능의 사용 권한과 위험 프로필에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="64e98-112">따라서이 문서에서는 기능 수준에서 사용 권한과 고려 사항을 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="64e98-113">아래에 나열 된 사용 권한 (예: RECEIVE_MESSAGE 및 REPLYTO_MESSAGE)은 [Microsoft 팀 개발자 설명서](https://aka.ms/teamsdevdocs) 의 모든 위치나 [microsoft Graph에 대 한 사용 권한](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)으로 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="64e98-114">단지이 기사의 목적에 대해 설명 하는 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="64e98-116">판단 요점</span><span class="sxs-lookup"><span data-stu-id="64e98-116">Decision point</span></span>|<ul><li><span data-ttu-id="64e98-117">아래 표를 참조 하 여 조사 중인 앱에서 요청 하는 사용 권한을 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-117">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/><span data-ttu-id="64e98-119">다음 단계</span><span class="sxs-lookup"><span data-stu-id="64e98-119">Next step</span></span>|<ul><li><span data-ttu-id="64e98-120">앱 또는 서비스 자체를 조사 하 여 조직 내에서 해당 사용자에 게 액세스를 허용 하려는 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-120">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="64e98-121">예를 들어, 인공 지능은 사용자 로부터 메시지를 보내고 받으며 엔터프라이즈 사용자 지정 인공 지능을 제외 하 고 규정 준수 경계 외부에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-121">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="64e98-122">따라서 봇이 포함 된 앱에는 해당 권한이 필요 하며 최소한 위험 프로필을 보유 하 고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-122">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="64e98-123">전역 앱 사용 권한 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="64e98-123">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="64e98-124">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="64e98-124">Required permissions</span></span>

<span data-ttu-id="64e98-125">없음</span><span class="sxs-lookup"><span data-stu-id="64e98-125">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="64e98-126">선택 권한</span><span class="sxs-lookup"><span data-stu-id="64e98-126">Optional permissions</span></span>

<span data-ttu-id="64e98-127">없음</span><span class="sxs-lookup"><span data-stu-id="64e98-127">None</span></span>

### <a name="considerations"></a><span data-ttu-id="64e98-128">고려 사항</span><span class="sxs-lookup"><span data-stu-id="64e98-128">Considerations</span></span>

- <span data-ttu-id="64e98-129">앱은 사용 약관 및 개인 정보 취급 방침 링크에서 사용 하는 데이터와 데이터를 공개 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-129">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="64e98-130">[리소스 관련 동의](resource-specific-consent.md) 는 앱이 요청할 수 있는 권한 집합을 제공 하며 앱의 설치 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-130">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="64e98-131">리소스 관련 승인 권한에 대 한 자세한 내용은 [그래프 사용 권한 참조](https://docs.microsoft.com/graph/permissions-reference)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="64e98-131">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference).</span></span>

- <span data-ttu-id="64e98-132">앱에는 리소스 관련 승인 권한이 아닌 다른 권한도 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-132">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="64e98-133">앱이 설치 되 면 승인 프롬프트를 통해 앱에서 그래프 권한을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-133">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="64e98-134">자세한 내용은 [AZURE AD 응용 프로그램 승인 환경 이해](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64e98-134">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="64e98-135">Azure 포털에서 API 사용 권한과 승인을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-135">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="64e98-136">자세한 정보는 [Azure Active Directory 동의 프레임 워크](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="64e98-136">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="64e98-137">인공 지능 및 메시징 확장</span><span class="sxs-lookup"><span data-stu-id="64e98-137">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="64e98-138">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="64e98-138">Required permissions</span></span>

- <span data-ttu-id="64e98-139">RECEIVE_MESSAGE REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="64e98-139">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="64e98-140">봇은 사용자 로부터 메시지를 수신 하 고 회신할 수 있습니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="64e98-140">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="64e98-141">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="64e98-141">POST_MESSAGE_USER.</span></span> <span data-ttu-id="64e98-142">사용자가 봇으로 메시지를 보낸 후에는 봇이 사용자 직접 메시지 (언제 든 지 *사전 메시지* 라고도 함)를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-142">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="64e98-143">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="64e98-143">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="64e98-144">팀에 추가 된 bot 팀에 있는 채널의 이름 및 Id 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-144">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="64e98-145">선택 권한</span><span class="sxs-lookup"><span data-stu-id="64e98-145">Optional permissions</span></span>

- <span data-ttu-id="64e98-146">신분을.</span><span class="sxs-lookup"><span data-stu-id="64e98-146">IDENTITY.</span></span> <span data-ttu-id="64e98-147">채널에서 사용 하는 경우 앱의 봇이 팀 구성원의 기본 id 정보 (이름, 성, UPN (사용자 계정 이름), 전자 메일 주소)에 액세스할 수 있습니다. 개인 또는 그룹 채팅에 사용 되는 경우에는 봇이 해당 사용자에 대 한 동일한 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-147">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="64e98-148">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="64e98-148">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="64e98-149">사용자가 이전에 인공 지능으로가는 일이 없더라도 앱의 봇이 언제 든 지 팀 구성원에 게 직접 (사전) 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-149">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="64e98-150">다음은 명시적 권한은 아니지만 RECEIVE_MESSAGE 및 REPLYTO_MESSAGE 및 해당 인공 지능을 사용할 수 있는 범위 (매니페스트에서 선언 됨)에 의해 암시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-150">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="64e98-151">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="64e98-151">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="64e98-152">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="64e98-152">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="64e98-153">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="64e98-153">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="64e98-154">SEND_FILES RECEIVE_FILES. <sup>2</sup> 봇이 개인 채팅에서 파일을 보내고 받을 수 있는지 여부를 제어 합니다 (아직 그룹 채팅 또는 채널에 지원 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="64e98-154">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="64e98-155">고려 사항</span><span class="sxs-lookup"><span data-stu-id="64e98-155">Considerations</span></span>

- <span data-ttu-id="64e98-156">봇에는 자신이 추가 된 팀 또는이를 설치한 사용자만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-156">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="64e98-157">인공 지능은 사용자가 명시적으로 언급 한 메시지만 받습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-157">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="64e98-158">이 데이터는 회사 네트워크를 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-158">This data leaves the corporate network.</span></span>

- <span data-ttu-id="64e98-159">봇에는이를 언급 한 대화에만 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-159">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="64e98-160">사용자가 봇 대를 conversed 후에는 해당 사용자의 ID를 저장 하면 언제 든 지 해당 사용자에 게 직접 메시지를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-160">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="64e98-161">기본적으로 봇 메시지에 피싱 또는 맬웨어 사이트에 대 한 링크가 포함 될 수 있으 나 사용자, 테 넌 트 관리자 또는 Microsoft에서 전역으로 인공 지능을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-161">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="64e98-162">봇은 앱이 추가 된 팀 구성원 또는 개인 또는 그룹 채팅의 개별 사용자에 대 한 매우 기본적인 id 정보를 검색 하 고 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-162">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="64e98-163">이러한 사용자에 대 한 자세한 정보를 얻으려면 봇에서 Azure AD (Active Directory)에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-163">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="64e98-164">Bot은 팀에서 채널 목록을 검색 하 고 저장할 수 있습니다. 이 데이터는 회사 네트워크를 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-164">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="64e98-165">파일을 bot에 보내면 파일이 회사 네트워크를 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-165">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="64e98-166">파일을 보내고 받으려면 각 파일에 대 한 사용자 승인이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-166">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="64e98-167">기본적으로 인공 지능에서는 사용자를 대신 하 여 작업을 수행할 수 있지만 인공 지능 사용자에 게 로그인 하도록 요청할 수 있습니다. 사용자가 로그인 하자마자 추가 작업을 수행할 수 있는 액세스 토큰이 인공으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-167">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="64e98-168">그 외에는 봇과 사용자 로그인 위치에 따라 달라질 수 있습니다. 봇은에 등록 된 Azure AD 앱 이며 https://apps.dev.microsoft.com/ 고유한 사용 권한 집합을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-168">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="64e98-169">봇에는 사용자가 팀에 추가 되거나 삭제 될 때마다 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-169">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="64e98-170">봇에는 사용자의 IP 주소나 다른 참조 정보가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-170">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="64e98-171">모든 정보는 Microsoft에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-171">All information comes from Microsoft.</span></span> <span data-ttu-id="64e98-172">(한 가지 예외: 봇이 자체 로그인 환경을 구현 하는 경우 로그인 UI에는 사용자의 IP 주소 및 참조 정보가 표시 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="64e98-172">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="64e98-173">반면에 메시징 확장에는 사용자의 IP 주소 및 참조 정보 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-173">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="64e98-174">앱 지침 (및 AppSource review)을 사용 하 POST_MESSAGE_TEAM 여 사용자에 게 개인 채팅 메시지를 게시할 때 적절 한 용도에 대해 신중 하 게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-174">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="64e98-175">불건전 한 경우 사용자가 인공 지능을 차단 하 고, 테 넌 트 관리자가 앱을 차단 하 고, 필요한 경우 Microsoft에서 인공 지능을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-175">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="64e98-176"><sup>1</sup> 일부 봇만 메시지를 보냅니다 (POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="64e98-176"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="64e98-177">"알림 전용" 인공 지능 이라고 하는 데,이는 봇이 허용 되거나 허용 되지 않는 것을 의미 하지 않지만,이는 봇이 대화를 하는 것을 원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-177">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="64e98-178">팀에서는이 필드를 사용 하 여 일반적으로 사용 되는 UI의 기능을 사용 하지 않도록 설정 합니다. 이 봇은 대화를 표시 하는 것과 비교 하 여 허용 되는 것으로 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-178">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="64e98-179"><sup>2</sup> 앱에 대 한 manifest.xml 파일의 bot 개체에 대 한 Supportsfiles 부울 속성에 의해 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-179"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="64e98-180">봇에 자체 로그인이 있으면 두 번째, 즉 사용자가 처음 로그인 할 때 동의 하는 환경이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-180">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="64e98-181">현재 팀 앱 (봇, 탭, 커넥터 또는 메시징 확장) 내의 기능과 연결 된 Azure AD 권한은 여기에 나열 된 팀 권한과 완전히 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-181">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="64e98-182">탭</span><span class="sxs-lookup"><span data-stu-id="64e98-182">Tabs</span></span>

<span data-ttu-id="64e98-183">탭은 팀 내에서 실행 되는 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-183">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="64e98-184">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="64e98-184">Required permissions</span></span>

<span data-ttu-id="64e98-185">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="64e98-185">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="64e98-186">선택 권한</span><span class="sxs-lookup"><span data-stu-id="64e98-186">Optional permissions</span></span>

<span data-ttu-id="64e98-187">없음 (현재)</span><span class="sxs-lookup"><span data-stu-id="64e98-187">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="64e98-188">고려 사항</span><span class="sxs-lookup"><span data-stu-id="64e98-188">Considerations</span></span>

- <span data-ttu-id="64e98-189">탭에 대 한 위험 프로필은 브라우저 탭에서 실행 되는 동일한 웹 사이트와 거의 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-189">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="64e98-190">또한 탭은 현재 사용자의 로그인 이름 및 UPN, 현재 사용자의 Azure AD 개체 ID,이 계정이 상주 하는 Office 365 그룹의 ID (팀 인 경우), 테 넌 트 ID 및 사용자의 현재 로케일을 비롯 하 여 실행 중인 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-190">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Office 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="64e98-191">그러나 이러한 Id를 사용자 정보에 매핑하려면 탭에서 사용자가 Azure AD에 로그인 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-191">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="64e98-192">기가</span><span class="sxs-lookup"><span data-stu-id="64e98-192">Connectors</span></span>

<span data-ttu-id="64e98-193">외부 시스템의 이벤트가 발생할 때 커넥터는 메시지를 채널에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-193">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="64e98-194">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="64e98-194">Required permissions</span></span>

<span data-ttu-id="64e98-195">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="64e98-195">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="64e98-196">선택 권한</span><span class="sxs-lookup"><span data-stu-id="64e98-196">Optional permissions</span></span>

<span data-ttu-id="64e98-197">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="64e98-197">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="64e98-198">특정 커넥터는 사용자가 GitHub 문제에 대 한 응답을 추가 하거나 Trello 카드에 날짜를 추가 하는 등 커넥터 메시지에 대 한 대상 지정 된 회신을 게시할 수 있도록 하는 실행 가능한 메시지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-198">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="64e98-199">고려 사항</span><span class="sxs-lookup"><span data-stu-id="64e98-199">Considerations</span></span>

- <span data-ttu-id="64e98-200">커넥터 메시지를 게시 하는 시스템에서 메시지를 보내거나 받는 사람을 알 수 없는 경우 받는 사람에 대 한 정보가 공개 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-200">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="64e98-201">(Microsoft는 테 넌 트가 아닌 실제 받는 사람입니다. Microsoft는 채널의 실제 게시물을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-201">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="64e98-202">커넥터 메시지가 채널에 게시 되 면 데이터가 회사 네트워크를 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-202">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="64e98-203">실행 가능 메시지를 지 원하는 커넥터 (REPLYTO_CONNECTOR_MESSAGE 권한)에도 IP 주소 및 참조 정보가 표시 되지 않습니다. 이 정보는 Microsoft에 전송 된 후 커넥터 포털에서 이전에 Microsoft에 등록 한 HTTP 끝점으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-203">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="64e98-204">채널에 대해 커넥터가 구성 될 때마다 해당 커넥터 인스턴스에 대 한 고유 URL이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-204">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="64e98-205">해당 커넥터 인스턴스가 삭제 되 면 해당 URL을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-205">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="64e98-206">커넥터 메시지에 첨부 파일을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-206">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="64e98-207">커넥터 인스턴스 URL은 전자 메일 주소와 같이 해당 URL이 있는 모든 사용자가 게시할 수 있는 비밀/비밀 우편으로 처리 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-207">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="64e98-208">따라서 스팸 또는 피싱 또는 맬웨어 사이트에 대 한 링크에는 몇 가지 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-208">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="64e98-209">이런 일이 발생 하는 경우 팀 소유자는 커넥터 인스턴스를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-209">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="64e98-210">커넥터 메시지를 보내는 서비스가 손상 되 고 스팸/피싱/맬웨어 링크 보내기를 시작 하는 경우 테 넌 트 관리자가 새 커넥터 인스턴스가 만들어지지 않도록 하 고 Microsoft는 중앙에서 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-210">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="64e98-211">현재 어떤 커넥터가 실행 가능한 메시지를 지원 하는지 알 수 없습니다 (REPLYTO_CONNECTOR_MESSAGE 권한).</span><span class="sxs-lookup"><span data-stu-id="64e98-211">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="64e98-212">보내는 webhooks</span><span class="sxs-lookup"><span data-stu-id="64e98-212">Outgoing webhooks</span></span>

<span data-ttu-id="64e98-213">*보내는 webhooks* 는 팀 소유자 또는 팀 구성원에 의해 즉석에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-213">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="64e98-214">팀 앱의 기능을 제공 하지 않습니다. 이 정보는 완전성을 위해 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-214">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="64e98-215">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="64e98-215">Required permissions</span></span>

<span data-ttu-id="64e98-216">RECEIVE_MESSAGE REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="64e98-216">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="64e98-217">사용자에 게 메시지를 수신 하 고 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-217">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="64e98-218">선택 권한</span><span class="sxs-lookup"><span data-stu-id="64e98-218">Optional permissions</span></span>

<span data-ttu-id="64e98-219">없음</span><span class="sxs-lookup"><span data-stu-id="64e98-219">None</span></span>

### <a name="considerations"></a><span data-ttu-id="64e98-220">고려 사항</span><span class="sxs-lookup"><span data-stu-id="64e98-220">Considerations</span></span>

- <span data-ttu-id="64e98-221">보내는 webhooks는 봇과 비슷하지만 사용 권한이 더 적습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-221">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="64e98-222">봇과 같이 명시적으로 언급 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-222">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="64e98-223">송신 webhook이 등록 되 면 보내는 webhook이 생성 되어 보낸 사람이 악의적인 공격자와 반대 되는 Microsoft 팀 인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-223">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="64e98-224">비밀은 비밀로 유지 되어야 합니다. 액세스 권한이 있는 모든 사용자가 Microsoft 팀을 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-224">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="64e98-225">비밀이 손상 되 면 송신 webhook을 삭제 하 고 다시 만들 수 있으며 새 비밀이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-225">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="64e98-226">비밀의 유효성을 검사 하지 않는 송신 webhook을 만들 수 있지만, 그에 대해 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-226">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="64e98-227">보내는 webhooks는 메시지를 받고 회신 하는 것 외에는 더 이상 메시지를 보낼 수 없고, 파일을 보내거나 받을 수 없으며, 다른 사용자가 메시지를 수신 하 고 회신 하는 것 외에는 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64e98-227">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
