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
description: 관리자는 Microsoft Teams 앱이 조직에서 요청하는 데이터 및 권한을 알 수 있습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 295bee65120e3c349efe1aa5fbc1e7b42c8da87a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739386"
---
# <a name="microsoft-teams-apps-permissions-and-considerations"></a><span data-ttu-id="efbc4-103">Microsoft Teams 앱 사용 권한 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="efbc4-103">Microsoft Teams apps permissions and considerations</span></span>

<span data-ttu-id="efbc4-104">Microsoft Teams 앱은 설치, 업그레이드 및 제거될  수 있는 하나 이상의 기능을 앱 패키지로 집계하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-104">Microsoft Teams apps are a way to aggregate one or more capabilities into an _app package_ that can be installed, upgraded, and uninstalled.</span></span> <span data-ttu-id="efbc4-105">기능에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-105">The capabilities include:</span></span>

- <span data-ttu-id="efbc4-106">봇</span><span class="sxs-lookup"><span data-stu-id="efbc4-106">Bots</span></span>
- <span data-ttu-id="efbc4-107">메시징 확장</span><span class="sxs-lookup"><span data-stu-id="efbc4-107">Messaging extensions</span></span>
- <span data-ttu-id="efbc4-108">탭</span><span class="sxs-lookup"><span data-stu-id="efbc4-108">Tabs</span></span>
- <span data-ttu-id="efbc4-109">커넥터</span><span class="sxs-lookup"><span data-stu-id="efbc4-109">Connectors</span></span>

<span data-ttu-id="efbc4-110">앱은 사용자가 동의하고 정책 관점에서 IT에서 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-110">Apps are consented to by users and managed by IT from a policy perspective.</span></span> <span data-ttu-id="efbc4-111">그러나 대부분의 경우 앱의 사용 권한 및 위험 프로필은 앱에 포함된 기능의 권한 및 위험 프로필에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-111">However, for the most part, an app's permissions and risk profile are defined by the permissions and risk profiles of the capabilities that the app contains.</span></span> <span data-ttu-id="efbc4-112">따라서 이 문서에서는 기능 수준에서 사용 권한 및 고려 사항을 중점적으로 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-112">Therefore, this article focuses on permissions and considerations at the capability level.</span></span>

<span data-ttu-id="efbc4-113">아래 나열된 사용 권한은 대문자로 나열됩니다(예: RECEIVE_MESSAGE 및 REPLYTO_MESSAGE [Microsoft Teams](https://aka.ms/teamsdevdocs) 개발자 설명서 또는 Microsoft Graph에 대한 사용 권한은 아무 곳에도 [나타나지 않습니다.](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)</span><span class="sxs-lookup"><span data-stu-id="efbc4-113">The permissions listed below in capital letters, for example RECEIVE_MESSAGE and REPLYTO_MESSAGE, don't appear anywhere in the [Microsoft Teams developer documentation](https://aka.ms/teamsdevdocs) or the [permissions for Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span> <span data-ttu-id="efbc4-114">이 문서의 목적에 대한 설명이 짧습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-114">They're simply a descriptive shorthand for the purpose of this article.</span></span>


| <span data-ttu-id="efbc4-115">제목</span><span class="sxs-lookup"><span data-stu-id="efbc4-115">Title</span></span>   | <span data-ttu-id="efbc4-116">설명</span><span class="sxs-lookup"><span data-stu-id="efbc4-116">Description</span></span>    |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="efbc4-118">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="efbc4-118">Decision point</span></span>|<ul><li><span data-ttu-id="efbc4-119">아래 표를 지침으로 사용하여 조사하는 앱이 요청하는 권한을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-119">Use the tables below as a guide to understand which permissions the apps you're investigating are requesting.</span></span></li></ul> |
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/><span data-ttu-id="efbc4-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="efbc4-121">Next step</span></span>|<ul><li><span data-ttu-id="efbc4-122">앱 또는 서비스 자체를 조사하여 조직 내에서 앱에 대한 액세스를 허용할지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-122">Research the app or service itself to decide whether you want to allow access to it within your organization.</span></span> <span data-ttu-id="efbc4-123">예를 들어 봇은 사용자로부터 메시지를 보내고 받고, 엔터프라이즈 사용자 지정 봇을 제외하고는 규정 준수 경계 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-123">For example, bots send and receive messages from users, and—except for enterprise custom bots—they're located outside the compliance boundary.</span></span> <span data-ttu-id="efbc4-124">따라서 봇을 포함하는 모든 앱에는 최소한 해당 권한이 필요하며 최소한 해당 위험 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-124">Therefore, any app that includes a bot requires those permissions and has that risk profile, at a minimum.</span></span> </li></ul>|

## <a name="global-app-permissions-and-considerations"></a><span data-ttu-id="efbc4-125">전역 앱 사용 권한 및 고려 사항</span><span class="sxs-lookup"><span data-stu-id="efbc4-125">Global app permissions and considerations</span></span>

### <a name="required-permissions"></a><span data-ttu-id="efbc4-126">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="efbc4-126">Required permissions</span></span>

<span data-ttu-id="efbc4-127">없음</span><span class="sxs-lookup"><span data-stu-id="efbc4-127">None</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="efbc4-128">선택적 권한</span><span class="sxs-lookup"><span data-stu-id="efbc4-128">Optional permissions</span></span>

<span data-ttu-id="efbc4-129">없음</span><span class="sxs-lookup"><span data-stu-id="efbc4-129">None</span></span>

### <a name="considerations"></a><span data-ttu-id="efbc4-130">고려 사항</span><span class="sxs-lookup"><span data-stu-id="efbc4-130">Considerations</span></span>

- <span data-ttu-id="efbc4-131">앱은 사용하는 데이터와 사용 약관 및 개인정보처리방침 링크에서 사용되는 데이터를 공개해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-131">An app must disclose what data it uses and what the data is used for in its terms of use and privacy policy links.</span></span>

- <span data-ttu-id="efbc4-132">[리소스별 동의는](resource-specific-consent.md) 앱이 요청할 수 있는 권한 집합을 제공합니다. 이 권한은 앱의 설치 화면에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-132">[Resource-specific consent](resource-specific-consent.md) provides a set of permissions that apps can request, which appears on the installation screen of the app.</span></span> <span data-ttu-id="efbc4-133">리소스별 동의 권한에 대한 자세한 내용은 Graph 권한 [참조를 참조합니다.](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions)</span><span class="sxs-lookup"><span data-stu-id="efbc4-133">To learn more about resource-specific consent permissions, see [Graph permissions reference](https://docs.microsoft.com/graph/permissions-reference#teams-resource-specific-consent-permissions).</span></span>

- <span data-ttu-id="efbc4-134">앱에 리소스별 동의 권한 외의 사용 권한이 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-134">Apps may also need permissions other than resource-specific consent permissions.</span></span> <span data-ttu-id="efbc4-135">앱이 설치되면 앱은 동의 프롬프트를 통해 Graph 권한을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-135">After an app is installed, the app may request Graph permissions through a consent prompt.</span></span> <span data-ttu-id="efbc4-136">자세한 내용은 Azure AD 애플리케이션 동의 환경 [이해를 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)</span><span class="sxs-lookup"><span data-stu-id="efbc4-136">To learn more, see [Understanding Azure AD application consent experiences](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience).</span></span> <span data-ttu-id="efbc4-137">Azure Portal에서 API 권한 및 동의를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-137">You can configure API permissions and consent in the Azure portal.</span></span> <span data-ttu-id="efbc4-138">자세한 내용은 Azure Active Directory 동의 [프레임워크를 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/consent-framework)</span><span class="sxs-lookup"><span data-stu-id="efbc4-138">To learn more, see [Azure Active Directory consent framework](https://docs.microsoft.com/azure/active-directory/develop/consent-framework).</span></span>

## <a name="bots-and-messaging-extensions"></a><span data-ttu-id="efbc4-139">봇 및 메시징 확장</span><span class="sxs-lookup"><span data-stu-id="efbc4-139">Bots and messaging extensions</span></span>

### <a name="required-permissions"></a><span data-ttu-id="efbc4-140">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="efbc4-140">Required permissions</span></span>

- <span data-ttu-id="efbc4-141">RECEIVE_MESSAGE REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="efbc4-141">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="efbc4-142">봇은 사용자로부터 메시지를 받고 회신할 수 있습니다. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="efbc4-142">The bot can receive messages from users and reply to them.<sup>1</sup></span></span>

- <span data-ttu-id="efbc4-143">POST_MESSAGE_USER.</span><span class="sxs-lookup"><span data-stu-id="efbc4-143">POST_MESSAGE_USER.</span></span> <span data-ttu-id="efbc4-144">사용자가 봇에 메시지를 보낸 후 봇은 사용자 직접 메시지(또는 사전 메시지라고도 하는)를 보낼 *수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-144">After a user has sent a message to a bot, the bot can send the user direct messages (also called *proactive messages* at any time.</span></span>

- <span data-ttu-id="efbc4-145">GET_CHANNEL_LIST.</span><span class="sxs-lookup"><span data-stu-id="efbc4-145">GET_CHANNEL_LIST.</span></span> <span data-ttu-id="efbc4-146">팀에 추가된 봇은 팀의 채널 이름 및 신원 목록을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-146">Bots added to teams can get a list of names and IDs of the channels in a team.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="efbc4-147">선택적 권한</span><span class="sxs-lookup"><span data-stu-id="efbc4-147">Optional permissions</span></span>

- <span data-ttu-id="efbc4-148">IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="efbc4-148">IDENTITY.</span></span> <span data-ttu-id="efbc4-149">채널에서 사용되는 경우 앱의 봇은 팀 구성원의 기본 ID 정보(이름, 성, 사용자 계정 이름 [UPN], 전자 메일 주소)에 액세스할 수 있습니다. 개인 또는 그룹 채팅에서 사용되는 경우 봇은 해당 사용자에 대해 동일한 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-149">When it's used in a channel, the app's bots can access basic identity information of team members (first name, last name, user principal name [UPN], email address); when it's used in a personal or group chat, the bot can access the same information for those users.</span></span>

- <span data-ttu-id="efbc4-150">POST_MESSAGE_TEAM.</span><span class="sxs-lookup"><span data-stu-id="efbc4-150">POST_MESSAGE_TEAM.</span></span> <span data-ttu-id="efbc4-151">앱의 봇이 사용자가 전에 봇과 대화한 적이 없는 경우에도 팀 구성원에게 직접(사전) 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-151">Allows an app's bots to send direct (proactive) messages to any team member at any time, even if the user has never talked to the bot before.</span></span>

- <span data-ttu-id="efbc4-152">다음은 명시적 권한은 아니지만 매니페스트에 선언된 RECEIVE_MESSAGE 및 REPLYTO_MESSAGE 및 봇을 사용할 수 있는 범위에 의해 암시됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-152">The following are not explicit permissions, but are implied by RECEIVE_MESSAGE and REPLYTO_MESSAGE and the scopes into which the bots can be used, declared in the manifest:</span></span>
 
    - <span data-ttu-id="efbc4-153">RECEIVE_MESSAGE_PERSONAL REPLYTO_MESSAGE_PERSONAL</span><span class="sxs-lookup"><span data-stu-id="efbc4-153">RECEIVE_MESSAGE_PERSONAL, REPLYTO_MESSAGE_PERSONAL</span></span>
    - <span data-ttu-id="efbc4-154">RECEIVE_MESSAGE_GROUPCHAT REPLYTO_MESSAGE_GROUPCHAT</span><span class="sxs-lookup"><span data-stu-id="efbc4-154">RECEIVE_MESSAGE_GROUPCHAT, REPLYTO_MESSAGE_GROUPCHAT</span></span>
    - <span data-ttu-id="efbc4-155">RECEIVE_MESSAGE_TEAM REPLYTO_MESSAGE_TEAM</span><span class="sxs-lookup"><span data-stu-id="efbc4-155">RECEIVE_MESSAGE_TEAM, REPLYTO_MESSAGE_TEAM</span></span>

- <span data-ttu-id="efbc4-156">SEND_FILES RECEIVE_FILES. <sup>2 봇이</sup> 개인 채팅에서 파일을 보내고 받을 수 있는지 여부를 제어합니다(아직 그룹 채팅 또는 채널에 지원되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="efbc4-156">SEND_FILES, RECEIVE_FILES.<sup>2</sup> Controls whether a bot can send and receive files in personal chat (not yet supported for group chat or channels).</span></span>

### <a name="considerations"></a><span data-ttu-id="efbc4-157">고려 사항</span><span class="sxs-lookup"><span data-stu-id="efbc4-157">Considerations</span></span>

- <span data-ttu-id="efbc4-158">봇은 추가된 팀 또는 해당 팀을 설치한 사용자에게만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-158">Bots only have access to teams to which they've been added or to users who have installed them.</span></span>

- <span data-ttu-id="efbc4-159">봇은 사용자가 명시적으로 언급한 메시지만 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-159">Bots only receive messages in which they're explicitly mentioned by users.</span></span> <span data-ttu-id="efbc4-160">이 데이터는 회사 네트워크를 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-160">This data leaves the corporate network.</span></span>

- <span data-ttu-id="efbc4-161">봇은 언급된 대화에만 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-161">Bots can only reply to conversations in which they're mentioned.</span></span>

- <span data-ttu-id="efbc4-162">사용자가 봇과 대화한 후, 봇이 해당 사용자의 ID를 저장하는 경우, 사용자가 직접 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-162">After a user has conversed with a bot, if the bot stores that user's ID, it can send that user direct messages at any time.</span></span>

- <span data-ttu-id="efbc4-163">이론적으로 봇 메시지에 피싱 또는 맬웨어 사이트에 대한 링크가 포함될 수 있지만 사용자, 테넌트 관리자 또는 Microsoft에서 전역적으로 봇을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-163">It is theoretically possible for bot messages to contain links to phishing or malware sites, but bots can be blocked by the user, the tenant admin, or globally by Microsoft.</span></span>

- <span data-ttu-id="efbc4-164">봇은 앱이 추가된 팀 구성원 또는 개인 또는 그룹 채팅의 개별 사용자에 대한 매우 기본적인 ID 정보를 검색(및 저장할 수 있습니다)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-164">A bot can retrieve (and might store) very basic identity information for the team members the app has been added to, or for individual users in personal or group chats.</span></span> <span data-ttu-id="efbc4-165">이러한 사용자에 대한 추가 정보를 얻습니다. 봇은 Azure AD(Azure Active Directory)에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-165">To get further information about these users, the bot must require them to sign in to Azure Active Directory (Azure AD).</span></span>

- <span data-ttu-id="efbc4-166">봇은 팀의 채널 목록을 검색(및 저장할 수 있습니다.) 이 데이터는 회사 네트워크를 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-166">Bots can retrieve (and might store) the list of channels in a team; this data leaves the corporate network.</span></span>

- <span data-ttu-id="efbc4-167">파일이 봇에 전송된 경우 파일은 회사 네트워크를 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-167">When a file is sent to a bot, the file leaves the corporate network.</span></span> <span data-ttu-id="efbc4-168">파일을 보내고 받는 경우 각 파일에 대한 사용자 승인이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-168">Sending and receiving files requires user approval for each file.</span></span> 

- <span data-ttu-id="efbc4-169">기본적으로 봇은 사용자를 대신하여 행동할 수 없지만, 봇은 사용자에게 로그인하도록 요청할 수 있습니다. 사용자가 로그인하는 즉시 봇에는 추가 작업을 할 수 있는 액세스 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-169">By default, bots don't have the ability to act on behalf of the user, but bots can ask users to sign in; as soon as the user signs in, the bot will have an access token with which it can do additional things.</span></span> <span data-ttu-id="efbc4-170">이러한 추가 사항의 정확한 것은 봇에 따라 달라지며, 사용자가 로그인하는 위치는 봇이 등록된 Azure AD 앱으로, 자체 사용 권한 집합을 사용할 https://apps.dev.microsoft.com/ 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-170">Exactly what those additional things are depends on the bot and where the user signs in: a bot is an Azure AD app registered at https://apps.dev.microsoft.com/ and can have its own set of permissions.</span></span>

- <span data-ttu-id="efbc4-171">봇은 사용자가 팀에 추가되거나 삭제될 때마다 통보됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-171">Bots are informed whenever users are added to or deleted from a team.</span></span>

- <span data-ttu-id="efbc4-172">봇은 사용자의 IP 주소 또는 기타 참조 참조 정보를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-172">Bots don't see users' IP addresses or other referrer information.</span></span> <span data-ttu-id="efbc4-173">모든 정보는 Microsoft에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-173">All information comes from Microsoft.</span></span> <span data-ttu-id="efbc4-174">(한 가지 예외가 있습니다. 봇이 자체 로그인 환경을 구현하는 경우 로그인 UI에 사용자의 IP 주소 및 참조 정보도 볼 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="efbc4-174">(There is one exception: if a bot implements its own sign-in experience, the sign-in UI will see users' IP addresses and referrer information.)</span></span>

- <span data-ttu-id="efbc4-175">반면 메시징 확장은 사용자의 IP 주소 및 참조 정보도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-175">Messaging extensions, on the other hand, do see users' IP addresses and referrer information.</span></span>

- <span data-ttu-id="efbc4-176">앱 지침(및 AppSource 검토 프로세스)은 유효한 목적으로 사용자에게 개인 채팅 메시지를 게시하는 데 POST_MESSAGE_TEAM 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-176">App guidelines (and our AppSource review process) require discretion in posting personal chat messages to users (via the POST_MESSAGE_TEAM permission) for valid purposes.</span></span> <span data-ttu-id="efbc4-177">남용이 발생하면 사용자가 봇을 차단할 수 있으며, 테넌트 관리자는 앱을 차단할 수 있으며, 필요한 경우 Microsoft는 봇을 중앙에서 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-177">In the event of abuse, users can block the bot, tenant admins can block the app, and Microsoft can block bots centrally if necessary.</span></span>

<span data-ttu-id="efbc4-178"><sup>1</sup> 일부 봇은 메시지만 전송합니다(POST_MESSAGE_USER).</span><span class="sxs-lookup"><span data-stu-id="efbc4-178"><sup>1</sup> Some bots only send messages (POST_MESSAGE_USER).</span></span> <span data-ttu-id="efbc4-179">"알림 전용" 봇이라고 하지만 용어는 봇이 허용되거나 허용되지 않는 작업을 참조하지 않습니다. 즉, 봇이 대화형 환경을 노출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-179">They're called "notification-only" bots, but the term doesn't refer to what a bot is allowed or not allowed to do, it means that the bot doesn't want to expose a conversational experience.</span></span> <span data-ttu-id="efbc4-180">Teams는 이 필드를 사용하여 기본적으로 사용하도록 설정된 UI의 기능을 사용하지 않도록 설정합니다. 봇은 대화 환경을 노출하는 봇에 비해 허용되는 작업을 제한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-180">Teams uses this field to disable functionality in the UI that would ordinarily be enabled; the bot isn't restricted in what it's allowed to do compared to bots that do expose a conversational experience.</span></span>

<span data-ttu-id="efbc4-181"><sup>2</sup> 앱에 대한 manifest.js봇 개체의 supportsFiles 부울 속성이 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-181"><sup>2</sup> Governed by the supportsFiles Boolean property on the bot object in the manifest.json file for the app.</span></span>

> [!NOTE]
> <span data-ttu-id="efbc4-182">봇에 자체 로그인이 있는 경우 사용자가 처음 로그인할 때 다른 두 번째 동의 환경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-182">If a bot has its own sign-in, there's a second—different—consent experience the first time the user signs in.</span></span>
>
><span data-ttu-id="efbc4-183">현재 Teams 앱(봇, 탭, 커넥터 또는 메시징 확장) 내 기능과 연결된 Azure AD 권한은 여기에 나열된 Teams 권한과 완전히 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-183">Currently, the Azure AD permissions associated with any of the capabilities inside a Teams app (bot, tab, connector, or messaging extension) are completely separate from the Teams permissions listed here.</span></span>

## <a name="tabs"></a><span data-ttu-id="efbc4-184">탭</span><span class="sxs-lookup"><span data-stu-id="efbc4-184">Tabs</span></span>

<span data-ttu-id="efbc4-185">탭은 Teams 내에서 실행되는 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-185">A tab is a website running inside Teams.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="efbc4-186">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="efbc4-186">Required permissions</span></span>

<span data-ttu-id="efbc4-187">SEND_AND_RECEIVE_WEB_DATA</span><span class="sxs-lookup"><span data-stu-id="efbc4-187">SEND_AND_RECEIVE_WEB_DATA</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="efbc4-188">선택적 권한</span><span class="sxs-lookup"><span data-stu-id="efbc4-188">Optional permissions</span></span>

<span data-ttu-id="efbc4-189">없음(현재)</span><span class="sxs-lookup"><span data-stu-id="efbc4-189">None (currently)</span></span>

### <a name="considerations"></a><span data-ttu-id="efbc4-190">고려 사항</span><span class="sxs-lookup"><span data-stu-id="efbc4-190">Considerations</span></span>

- <span data-ttu-id="efbc4-191">탭의 위험 프로필은 브라우저 탭에서 실행되는 동일한 웹 사이트와 거의 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-191">The risk profile for a tab is almost identical to that same website running in a browser tab.</span></span> 

- <span data-ttu-id="efbc4-192">또한 탭은 현재 사용자의 로그인 이름 및 UPN, 현재 사용자의 Azure AD 개체 ID, 팀이 있는 Microsoft 365 그룹의 ID, 테넌트 ID 및 사용자의 현재 로일을 포함하여 실행 중인 컨텍스트를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-192">A tab also gets the context in which it's running, including the sign-in name and UPN of the current user, the Azure AD Object ID for the current user, the ID of the Microsoft 365 Group in which it resides (if it's a team), the tenant ID, and the current locale of the user.</span></span> <span data-ttu-id="efbc4-193">그러나 이러한 ID를 사용자의 정보에 매핑하기 위해 탭에서 사용자가 Azure AD에 로그인하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-193">However, to map these IDs to a user's information, the tab would have to make the user sign in to Azure AD.</span></span>

## <a name="connectors"></a><span data-ttu-id="efbc4-194">커넥터</span><span class="sxs-lookup"><span data-stu-id="efbc4-194">Connectors</span></span>

<span data-ttu-id="efbc4-195">커넥터는 외부 시스템의 이벤트가 발생할 때 채널에 메시지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-195">A connector posts messages to a channel when events in an external system occur.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="efbc4-196">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="efbc4-196">Required permissions</span></span>

<span data-ttu-id="efbc4-197">POST_MESSAGE_CHANNEL</span><span class="sxs-lookup"><span data-stu-id="efbc4-197">POST_MESSAGE_CHANNEL</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="efbc4-198">선택적 권한</span><span class="sxs-lookup"><span data-stu-id="efbc4-198">Optional permissions</span></span>

<span data-ttu-id="efbc4-199">REPLYTO_CONNECTOR_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="efbc4-199">REPLYTO_CONNECTOR_MESSAGE.</span></span> <span data-ttu-id="efbc4-200">특정 커넥터는 GitHub 문제의 응답을 추가하거나 Trello 카드에 날짜를 추가하는 등 사용자가 대상이 지정한 응답을 커넥터 메시지에 게시할 수 있는 실행 가능한 메시지를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-200">Certain connectors support actionable messages, which allow users to post targeted replies to the connector message, for example by adding a response to a GitHub issue or adding a date to a Trello card.</span></span>

### <a name="considerations"></a><span data-ttu-id="efbc4-201">고려 사항</span><span class="sxs-lookup"><span data-stu-id="efbc4-201">Considerations</span></span>

- <span data-ttu-id="efbc4-202">커넥터 메시지를 게시하는 시스템은 커넥터 메시지를 게시하는 사람 또는 메시지를 받는 사람을 알 수 없습니다. 받는 사람에 대한 정보는 공개되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-202">The system that posts connector messages doesn't know who it's posting to or who receives the messages: no information about the recipient is disclosed.</span></span> <span data-ttu-id="efbc4-203">(Microsoft는 테넌트가 아닌 실제 받는 사람입니다. Microsoft는 채널에 실제 게시물을 게시합니다.)</span><span class="sxs-lookup"><span data-stu-id="efbc4-203">(Microsoft is the actual recipient, not the tenant; Microsoft does the actual post to the channel.)</span></span>

- <span data-ttu-id="efbc4-204">커넥터 메시지가 채널에 게시되는 경우 데이터가 회사 네트워크에서 나가지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-204">No data leaves the corporate network when connector messages are posted to a channel.</span></span>

- <span data-ttu-id="efbc4-205">실행 가능한 메시지(REPLYTO_CONNECTOR_MESSAGE 권한)를 지원하는 커넥터도 IP 주소 및 참조 정보도 볼 수 없습니다. 이 정보는 Microsoft로 전송된 다음 커넥터 포털에서 이전에 Microsoft에 등록된 HTTP 엔드포인트로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-205">Connectors that support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission) also don't see IP address and referrer information; this information is sent to Microsoft and then routed to HTTP endpoints that were previously registered with Microsoft in the Connectors portal.</span></span>

- <span data-ttu-id="efbc4-206">채널에 대해 커넥터를 구성할 때마다 해당 커넥터 인스턴스에 대한 고유한 URL이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-206">Each time a connector is configured for a channel, a unique URL for that connector instance is created.</span></span> <span data-ttu-id="efbc4-207">해당 커넥터 인스턴스가 삭제되면 URL을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-207">If that connector instance is deleted, the URL can no longer be used.</span></span>

- <span data-ttu-id="efbc4-208">커넥터 메시지에는 파일 첨부 파일이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-208">Connector messages can't contain file attachments.</span></span>

- <span data-ttu-id="efbc4-209">커넥터 인스턴스 URL은 비밀/기밀로 처리해야 합니다. 해당 URL이 있는 모든 사용자가 전자 메일 주소와 같이 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-209">The connector instance URL should be treated as secret/confidential: anyone who has that URL can post to it, like an email address.</span></span> <span data-ttu-id="efbc4-210">따라서 스팸 또는 피싱 또는 맬웨어 사이트에 대한 링크의 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-210">Therefore, there's some risk of spam or links to phishing or malware sites.</span></span> <span data-ttu-id="efbc4-211">이 경우 팀 소유자는 커넥터 인스턴스를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-211">If that were to happen, team owners can delete the connector instance.</span></span>

- <span data-ttu-id="efbc4-212">커넥터 메시지를 보내는 서비스가 손상되고 스팸/피싱/맬웨어 링크 전송을 시작하는 경우 테넌트 관리자는 새 커넥터 인스턴스가 생성되지 않도록 방지할 수 있으며 Microsoft는 이를 중앙에서 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-212">If the service that sends connector messages were to become compromised and start sending spam/phishing/malware links, a tenant administrator can prevent new connector instances from being created and Microsoft can block them centrally.</span></span>

> [!NOTE]
> <span data-ttu-id="efbc4-213">현재 어떤 커넥터가 실행 가능한 메시지(사용 권한)를 지원하는지 REPLYTO_CONNECTOR_MESSAGE 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-213">It's not currently possible to know which connectors support actionable messages (REPLYTO_CONNECTOR_MESSAGE permission).</span></span>

## <a name="outgoing-webhooks"></a><span data-ttu-id="efbc4-214">유출 웹후크</span><span class="sxs-lookup"><span data-stu-id="efbc4-214">Outgoing webhooks</span></span>

<span data-ttu-id="efbc4-215">*팀 소유자 또는* 팀 구성원이 진행하는 웹후크가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-215">*Outgoing webhooks* are created on the fly by team owners or team members.</span></span> <span data-ttu-id="efbc4-216">Teams 앱의 기능은 지원되지 않습니다. 이 정보는 완전성을 위해 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-216">They aren't capabilities of Teams apps; this information is included for completeness.</span></span>

### <a name="required-permissions"></a><span data-ttu-id="efbc4-217">필요한 권한</span><span class="sxs-lookup"><span data-stu-id="efbc4-217">Required permissions</span></span>

<span data-ttu-id="efbc4-218">RECEIVE_MESSAGE REPLYTO_MESSAGE.</span><span class="sxs-lookup"><span data-stu-id="efbc4-218">RECEIVE_MESSAGE, REPLYTO_MESSAGE.</span></span> <span data-ttu-id="efbc4-219">사용자로부터 메시지를 받고 회신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-219">Can receive messages from users and reply to them.</span></span>

### <a name="optional-permissions"></a><span data-ttu-id="efbc4-220">선택적 권한</span><span class="sxs-lookup"><span data-stu-id="efbc4-220">Optional permissions</span></span>

<span data-ttu-id="efbc4-221">없음</span><span class="sxs-lookup"><span data-stu-id="efbc4-221">None</span></span>

### <a name="considerations"></a><span data-ttu-id="efbc4-222">고려 사항</span><span class="sxs-lookup"><span data-stu-id="efbc4-222">Considerations</span></span>

- <span data-ttu-id="efbc4-223">유출되는 웹후크는 봇과 비슷하지만 권한이 적습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-223">Outgoing webhooks are similar to bots but have fewer privileges.</span></span> <span data-ttu-id="efbc4-224">봇과 마찬가지로 명시적으로 언급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-224">They must be explicitly mentioned, just like bots.</span></span>

- <span data-ttu-id="efbc4-225">보내는 웹후크가 등록된 경우 보내는 웹후크가 악의적인 공격자가 아니라 보낸 사람이 Microsoft Teams인 것을 확인할 수 있는 비밀이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-225">When an outgoing webhook is registered, a secret is generated, which allows the outgoing webhook to verify that the sender is Microsoft Teams as opposed to a malicious attacker.</span></span> <span data-ttu-id="efbc4-226">이 비밀은 비밀로 유지해야 하는 경우 액세스 권한이 있는 모든 사람이 Microsoft Teams를 가장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-226">This secret should remain a secret; anyone who has access to it can impersonate Microsoft Teams.</span></span> <span data-ttu-id="efbc4-227">비밀이 손상되면 발신 웹후크를 삭제하고 다시 만들 수 있으며 새 비밀이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-227">If the secret is compromised, the outgoing webhook can be deleted and re-created, and a new secret will be generated.</span></span>

- <span data-ttu-id="efbc4-228">비밀의 유효성을 검사하지 않는 유출된 웹후크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-228">Although it's possible to create an outgoing webhook that doesn't validate the secret, we recommend against it.</span></span>

- <span data-ttu-id="efbc4-229">메시지 수신 및 회신 외에, 보내는 웹후크는 많은 작업을 할 수 없습니다. 즉, 메시지를 사전적으로 보낼 수 없습니다. 파일을 보내거나 받을 수 없습니다. 봇은 메시지 수신 및 회신을 제외하고 할 수 있는 다른 작업을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efbc4-229">Other than receiving and replying to messages, outgoing webhooks can't do much: they can't proactively send messages, they can't send or receive files, they can't do anything else that bots can do except receive and reply to messages.</span></span>
