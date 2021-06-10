---
title: Microsoft Teams 앱 사용 권한 및 고려 사항
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
description: 관리자는 앱에서 조직에서 요청하는 Microsoft Teams 및 권한을 알 수 있습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae050080814afe12ce2ba791c6b68058d5e4bc58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120860"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="19a6d-103">Microsoft Teams 앱 사용 권한 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="19a6d-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="19a6d-104">Microsoft Teams 앱은 설치, 업그레이드 및 제거될 수  있는 하나 이상의 기능을 앱 패키지에 집계하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="19a6d-105">기능에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-105">The capabilities include:</span></span>

- <span data-ttu-id="19a6d-106">봇</span><span class="sxs-lookup"><span data-stu-id="19a6d-106">Bots</span></span>
- <span data-ttu-id="19a6d-107">메시징 확장</span><span class="sxs-lookup"><span data-stu-id="19a6d-107">Messaging extensions</span></span>
- <span data-ttu-id="19a6d-108">탭</span><span class="sxs-lookup"><span data-stu-id="19a6d-108">Tabs</span></span>
- <span data-ttu-id="19a6d-109">커넥터</span><span class="sxs-lookup"><span data-stu-id="19a6d-109">Connectors</span></span>

<span data-ttu-id="19a6d-110">앱은 사용자가 동의하고 정책 관점에서 IT에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="19a6d-111">그러나 대부분의 경우 앱의 사용 권한 및 위험 프로필은 앱에 포함된 기능의 사용 권한 및 위험 프로필에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="19a6d-112">따라서 이 문서에서는 기능 수준에서 사용 권한 및 고려 사항을 중점적으로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="19a6d-113">아래 대문자에 나열된 권한(예: RECEIVE_MESSAGE 및 REPLYTO_MESSAGE)은 개발자 설명서 또는 [](/microsoftteams/platform/overview) [Microsoft](/graph/permissions-reference)Microsoft Teams 에 대한 사용 권한에 Graph.</span><span class="sxs-lookup"><span data-stu-id="19a6d-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](/microsoftteams/platform/overview) or the [permissions for Microsoft Graph](/graph/permissions-reference).</span></span> <span data-ttu-id="19a6d-114">이 문서는 이 문서의 목적에 대한 설명적인 짧은 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="19a6d-115">제목</span><span class="sxs-lookup"><span data-stu-id="19a6d-115">Title</span></span>   | <span data-ttu-id="19a6d-116">설명</span><span class="sxs-lookup"><span data-stu-id="19a6d-116">Description</span></span>    |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="19a6d-118">결정 지점</span><span class="sxs-lookup"><span data-stu-id="19a6d-118">Decision point</span></span>|<ul><li><span data-ttu-id="19a6d-119">아래 표를 가이드로 사용하여 조사하는 앱이 요청하는 권한을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/><span data-ttu-id="19a6d-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="19a6d-121">Next step</span></span>|<ul><li><span data-ttu-id="19a6d-122">앱 또는 서비스 자체를 조사하여 조직 내에서 액세스 권한을 허용할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="19a6d-123">예를 들어 봇은 사용자로부터 메시지를 보내고 수신하며 엔터프라이즈 사용자 지정 봇을 제외하고는 규정 준수 경계 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="19a6d-124">따라서 봇을 포함하는 모든 앱에는 이러한 권한이 필요하며 최소한 위험 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

<span data-ttu-id="19a6d-125">탭에 대한 디바이스 [사용 권한 Microsoft Teams 참조하세요.](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions)</span><span class="sxs-lookup"><span data-stu-id="19a6d-125">See also [Request device permissions for your Microsoft Teams tab](/microsoftteams/platform/concepts/device-capabilities/native-device-permissions).</span></span>

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="19a6d-126">글로벌 앱 사용 권한 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="19a6d-126">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="19a6d-127">필수 사용 권한</span><span class="sxs-lookup"><span data-stu-id="19a6d-127">Required permissions</span></span>

<span data-ttu-id="19a6d-128">없음</span><span class="sxs-lookup"><span data-stu-id="19a6d-128">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="19a6d-129">선택적 사용 권한</span><span class="sxs-lookup"><span data-stu-id="19a6d-129">Optional permissions</span></span>

<span data-ttu-id="19a6d-130">없음</span><span class="sxs-lookup"><span data-stu-id="19a6d-130">None</span></span>

### <a name="considerations"></a><span data-ttu-id="19a6d-131">고려 사항</span><span class="sxs-lookup"><span data-stu-id="19a6d-131">Considerations</span></span>

- <span data-ttu-id="19a6d-132">앱은 사용하는 데이터와 해당 사용 약관 및 개인 정보 취급 방침 링크에 사용되는 데이터를 공개해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-132">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="19a6d-133">[리소스별 동의는](resource-specific-consent.md) 앱의 설치 화면에 나타나는 앱에 요청할 수 있는 사용 권한 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-133">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="19a6d-134">리소스별 동의 권한에 대한 자세한 내용은 사용 [권한 Graph 참조를 참조합니다.](/graph/permissions-reference#teams-resource-specific-consent-permissions)</span><span class="sxs-lookup"><span data-stu-id="19a6d-134">To learn more about resource-specific consent permissions, see [Graph permissions reference](/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="19a6d-135">앱에 리소스별 동의 권한 외의 사용 권한이 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-135">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="19a6d-136">앱이 설치되면 앱에서 동의 프롬프트를 통해 Graph 권한을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-136">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="19a6d-137">자세한 내용은 Azure AD 애플리케이션 [동의 환경 이해 를 참조하세요.](/azure/active-directory/develop/application-consent-experience)</span><span class="sxs-lookup"><span data-stu-id="19a6d-137">To learn more, see [Understanding Azure AD application consent experiences](/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="19a6d-138">Azure Portal에서 API 사용 권한 및 동의를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-138">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="19a6d-139">자세한 내용은 동의 [Azure Active Directory 참조합니다.](/azure/active-directory/develop/consent-framework)</span><span class="sxs-lookup"><span data-stu-id="19a6d-139">To learn more, see [Azure Active Directory consent framework](/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="19a6d-140">봇 및 메시징 확장</span><span class="sxs-lookup"><span data-stu-id="19a6d-140">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="19a6d-141">필수 사용 권한</span><span class="sxs-lookup"><span data-stu-id="19a6d-141">Required permissions</span></span>

- <span data-ttu-id="19a6d-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="19a6d-142">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="19a6d-143">봇은 사용자로부터 메시지를 받고 회신할 수 있습니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="19a6d-143">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="19a6d-144">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="19a6d-144">POST_MESSAGE_USER.</span></span> <span data-ttu-id="19a6d-145">사용자가 봇에 메시지를 보낸 후 봇은 사용자 직접 메시지(사전 메시지라고도도)를 보낼 *수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-145">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="19a6d-146">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="19a6d-146">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="19a6d-147">팀에 추가된 봇은 팀의 채널 이름 및 아이디 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-147">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="19a6d-148">선택적 사용 권한</span><span class="sxs-lookup"><span data-stu-id="19a6d-148">Optional permissions</span></span>

- <span data-ttu-id="19a6d-149">ID.</span><span class="sxs-lookup"><span data-stu-id="19a6d-149">IDENTITY.</span></span> <span data-ttu-id="19a6d-150">채널에서 사용되는 경우 앱의 봇은 팀 구성원의 기본 ID 정보(이름, 성, 사용자 주체 이름 [UPN], 전자 메일 주소)에 액세스할 수 있습니다. 개인 채팅 또는 그룹 채팅에 사용되는 경우 봇은 해당 사용자에 대해 동일한 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-150">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="19a6d-151">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="19a6d-151">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="19a6d-152">사용자가 전에 봇과 대화한 적이 없는 경우에도 앱의 봇이 팀 구성원에게 직접(사전 예방) 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-152">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="19a6d-153">다음은 명시적 사용 권한이 아니라 매니페스트에서 선언된 RECEIVE_MESSAGE REPLYTO_MESSAGE 및 봇을 사용할 수 있는 범위에 의해 암시됩니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-153">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="19a6d-154">RECEIVE_MESSAGE_PERSONAL REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="19a6d-154">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="19a6d-155">RECEIVE_MESSAGE_GROUPCHAT REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="19a6d-155">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="19a6d-156">RECEIVE_MESSAGE_TEAM REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="19a6d-156">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="19a6d-157">SEND_FILES RECEIVE_FILES. <sup>2</sup> 봇이 개인 채팅에서 파일을 보내고 받을 수 있는지 여부를 제어합니다(그룹 채팅 또는 채널에 대해 아직 지원되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="19a6d-157">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="19a6d-158">고려 사항</span><span class="sxs-lookup"><span data-stu-id="19a6d-158">Considerations</span></span>

- <span data-ttu-id="19a6d-159">봇은 추가된 팀 또는 설치한 사용자에게만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-159">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="19a6d-160">봇은 사용자가 명시적으로 언급한 메시지만 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-160">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="19a6d-161">이 데이터는 회사 네트워크를 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-161">This data leaves the corporate network.</span></span>

- <span data-ttu-id="19a6d-162">봇은 언급된 대화에만 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-162">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="19a6d-163">사용자가 봇과 대화한 후 봇이 해당 사용자의 ID를 저장하는 경우 해당 사용자 직접 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-163">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="19a6d-164">이론적으로 봇 메시지에 피싱 또는 맬웨어 사이트에 대한 링크가 포함될 수 있지만 사용자, 테넌트 관리자 또는 Microsoft에서 전역적으로 봇을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-164">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="19a6d-165">봇은 앱이 추가된 팀 구성원 또는 개인 또는 그룹 채팅의 개별 사용자에 대한 매우 기본적인 ID 정보를 검색(저장)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-165">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="19a6d-166">이러한 사용자에 대한 자세한 정보를 얻게하려면 봇이 Azure AD(Azure AD)에 로그인해야 Azure Active Directory 합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-166">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="19a6d-167">봇은 팀의 채널 목록을 검색(저장)할 수 있습니다. 이 데이터는 회사 네트워크를 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-167">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="19a6d-168">파일이 봇에 전송된 경우 파일이 회사 네트워크를 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-168">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="19a6d-169">파일을 보내고 받는 경우 각 파일에 대한 사용자 승인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-169">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="19a6d-170">기본적으로 봇은 사용자를 대신하여 행동할 수 없지만 봇은 사용자에게 로그인을 요청할 수 있습니다. 사용자가 로그인하면 봇에 추가 작업을 할 수 있는 액세스 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-170">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="19a6d-171">이러한 추가 작업의 정확한 구성은 봇에 따라 달라지며 사용자가 로그인하는 위치는 봇이 등록된 Azure AD 앱으로, 자체 사용 권한 집합을 사용할 https://apps.dev.microsoft.com/ 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-171">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="19a6d-172">봇은 사용자가 팀에 추가되거나 삭제될 때마다 통보됩니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-172">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="19a6d-173">봇은 사용자의 IP 주소 또는 기타 참조 정보를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-173">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="19a6d-174">모든 정보는 Microsoft에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-174">All information comes from Microsoft.</span></span> <span data-ttu-id="19a6d-175">(한 가지 예외가 있습니다. 봇이 자체 로그인 환경을 구현하는 경우 로그인 UI에서 사용자의 IP 주소 및 참조 정보를 볼 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="19a6d-175">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="19a6d-176">반면 메시징 확장은 사용자의 IP 주소 및 참조 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19a6d-176">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="19a6d-177">앱 지침(및 AppSource 검토 프로세스)은 유효한 목적으로 사용자에게 개인 채팅 메시지를 게시하는 데 POST_MESSAGE_TEAM 재량이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-177">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="19a6d-178">남용이 발생하면 사용자가 봇을 차단할 수 있으며, 테넌트 관리자는 앱을 차단할 수 있으며, 필요한 경우 Microsoft는 봇을 중앙에서 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-178">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="19a6d-179"><sup>1</sup> 일부 봇은 메시지만 전송합니다(POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="19a6d-179"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="19a6d-180">"알림 전용" 봇이라고 하지만 용어는 봇이 허용하거나 허용하지 않는 것을 의미하지 않습니다. 이는 봇이 대화 환경을 노출하지 않을 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-180">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="19a6d-181">Teams 이 필드를 사용하여 기본적으로 사용하도록 설정되는 UI의 기능을 사용하지 않도록 설정합니다. 봇은 대화 환경을 노출하는 봇과 비교하여 허용되는 작업을 제한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-181">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="19a6d-182"><sup>2</sup> 지원에 의해 관리되는 봇 개체의 manifest.js파일의 부울 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-182"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="19a6d-183">봇에 자체 로그인이 있는 경우 사용자가 처음 로그인할 때 동의 경험이 다른 두 번째가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-183">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="19a6d-184">현재 앱 내 기능(Teams 봇, 탭, 커넥터 또는 메시징 확장)에 연결된 Azure AD 사용 권한은 Teams 권한과 완전히 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-184">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="19a6d-185">탭</span><span class="sxs-lookup"><span data-stu-id="19a6d-185">Tabs</span></span>

<span data-ttu-id="19a6d-186">탭은 웹 사이트 내에서 실행되는 Teams.</span><span class="sxs-lookup"><span data-stu-id="19a6d-186">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="19a6d-187">필수 사용 권한</span><span class="sxs-lookup"><span data-stu-id="19a6d-187">Required permissions</span></span>

<span data-ttu-id="19a6d-188">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="19a6d-188">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="19a6d-189">선택적 사용 권한</span><span class="sxs-lookup"><span data-stu-id="19a6d-189">Optional permissions</span></span>

<span data-ttu-id="19a6d-190">없음(현재)</span><span class="sxs-lookup"><span data-stu-id="19a6d-190">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="19a6d-191">고려 사항</span><span class="sxs-lookup"><span data-stu-id="19a6d-191">Considerations</span></span>

- <span data-ttu-id="19a6d-192">탭의 위험 프로필은 브라우저 탭에서 실행되는 동일한 웹 사이트와 거의 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-192">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="19a6d-193">또한 탭은 현재 사용자의 로그인 이름 및 UPN, 현재 사용자의 Azure AD 개체 ID, 현재 사용자가 상주하는 Microsoft 365 그룹의 ID, 테넌트 ID 및 사용자의 현재 로일을 포함하여 실행 중인 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-193">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="19a6d-194">그러나 이러한 ID를 사용자의 정보에 매핑하기 위해 탭에서 사용자가 Azure AD에 로그인하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-194">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="19a6d-195">커넥터</span><span class="sxs-lookup"><span data-stu-id="19a6d-195">Connectors</span></span>

<span data-ttu-id="19a6d-196">커넥터는 외부 시스템의 이벤트가 발생할 때 채널에 메시지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-196">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="19a6d-197">필수 사용 권한</span><span class="sxs-lookup"><span data-stu-id="19a6d-197">Required permissions</span></span>

<span data-ttu-id="19a6d-198">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="19a6d-198">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="19a6d-199">선택적 사용 권한</span><span class="sxs-lookup"><span data-stu-id="19a6d-199">Optional permissions</span></span>

<span data-ttu-id="19a6d-200">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="19a6d-200">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="19a6d-201">특정 커넥터는 사용자가 연결선 메시지에 대한 대상 응답을 게시할 수 있도록 하는 실행 가능한 메시지를 지원합니다(예: GitHub 메시지에 대한 응답을 추가하거나 Trello 카드에 날짜를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-201">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="19a6d-202">고려 사항</span><span class="sxs-lookup"><span data-stu-id="19a6d-202">Considerations</span></span>

- <span data-ttu-id="19a6d-203">커넥터 메시지를 게시하는 시스템은 받는 사람에 대한 정보가 공개되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-203">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="19a6d-204">(Microsoft는 테넌트가 아닌 실제 받는 사람입니다. Microsoft는 채널에 대한 실제 게시물을 합니다.)</span><span class="sxs-lookup"><span data-stu-id="19a6d-204">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="19a6d-205">커넥터 메시지가 채널에 게시되는 경우 데이터가 회사 네트워크를 떠날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-205">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="19a6d-206">실행 가능한 메시지(REPLYTO_CONNECTOR_MESSAGE 권한)를 지원하는 커넥터도 IP 주소 및 참조 정보를 볼 수 없습니다. 이 정보는 Microsoft로 전송된 다음 커넥터 포털에서 이전에 Microsoft에 등록된 HTTP 엔드포인트로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-206">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="19a6d-207">채널에 대해 커넥터를 구성할 때마다 해당 커넥터 인스턴스에 대한 고유한 URL이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-207">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="19a6d-208">해당 커넥터 인스턴스가 삭제되면 URL을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-208">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="19a6d-209">커넥터 메시지에는 파일 첨부 파일이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-209">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="19a6d-210">커넥터 인스턴스 URL은 비밀/기밀로 처리해야 합니다. 해당 URL이 있는 모든 사용자가 전자 메일 주소와 같이 해당 URL에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-210">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="19a6d-211">따라서 스팸 또는 피싱 또는 맬웨어 사이트에 대한 링크의 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-211">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="19a6d-212">이 경우 팀 소유자는 커넥터 인스턴스를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-212">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="19a6d-213">커넥터 메시지를 보내는 서비스가 손상되고 스팸/피싱/맬웨어 링크를 보내기 시작하는 경우 테넌트 관리자가 새 커넥터 인스턴스를 만들지 못하게 할 수 있으며 Microsoft는 이를 중앙에서 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-213">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="19a6d-214">현재 실행 가능한 메시지(사용 권한)를 지원하는 커넥터를 알 수 REPLYTO_CONNECTOR_MESSAGE 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-214">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="19a6d-215">진행하는 웹후크</span><span class="sxs-lookup"><span data-stu-id="19a6d-215">Outgoing webhooks</span></span>

<span data-ttu-id="19a6d-216">*팀 소유자 또는* 팀 구성원이 진행하는 웹후크가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-216">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="19a6d-217">앱의 기능이 Teams 없습니다. 이 정보는 완전성을 위해 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-217">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="19a6d-218">필수 사용 권한</span><span class="sxs-lookup"><span data-stu-id="19a6d-218">Required permissions</span></span>

<span data-ttu-id="19a6d-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="19a6d-219">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="19a6d-220">사용자로부터 메시지를 받고 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-220">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="19a6d-221">선택적 사용 권한</span><span class="sxs-lookup"><span data-stu-id="19a6d-221">Optional permissions</span></span>

<span data-ttu-id="19a6d-222">없음</span><span class="sxs-lookup"><span data-stu-id="19a6d-222">None</span></span>

### <a name="considerations"></a><span data-ttu-id="19a6d-223">고려 사항</span><span class="sxs-lookup"><span data-stu-id="19a6d-223">Considerations</span></span>

- <span data-ttu-id="19a6d-224">진행하는 웹후크는 봇과 비슷하지만 권한이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-224">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="19a6d-225">봇과 마찬가지로 명시적으로 언급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-225">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="19a6d-226">발신 웹후크가 등록될 때 비밀이 생성되어 발신 웹후크가 악성 공격자가 Microsoft Teams 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-226">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="19a6d-227">이 비밀은 비밀로 유지됩니다. 액세스 권한이 있는 모든 사용자에 대해 가장할 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="19a6d-227">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="19a6d-228">비밀이 손상되면 발신 웹후크를 삭제하고 다시 만들 수 있으며 새 비밀이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-228">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="19a6d-229">비밀의 유효성을 검사하지 않는 진행하는 웹후크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-229">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="19a6d-230">메시지 수신 및 회신 외에, 발신 웹후크는 많은 작업을 할 수 없습니다. 즉, 메시지를 사전적으로 보낼 수 없습니다. 파일을 보내거나 받을 수 없습니다. 봇은 메시지 수신 및 회신 외에 할 수 있는 다른 작업을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19a6d-230">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>