---
title: Microsoft Teams의 제한 사항 및 사양
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: Microsoft Teams에 적용되는 제한 사항, 사양 및 기타 요구 사항에 대해 알아보세요.
localization_priority: Priority
ms.collection:
- M365-collaboration
- SPO_Content
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 098477cc36237736009e1ec2010fea625d08937c
ms.sourcegitcommit: 57304ac641931eed87e649555fd5eb5e58732dc5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "39679238"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="eb249-103">Microsoft Teams의 제한 사항 및 사양</span><span class="sxs-lookup"><span data-stu-id="eb249-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="eb249-104">이 문서에서는 Microsoft Teams에 적용되는 몇 가지 제한 사항, 사양 및 기타 요구 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="eb249-105">팀 및 채널</span><span class="sxs-lookup"><span data-stu-id="eb249-105">Teams and channels</span></span>

|<span data-ttu-id="eb249-106">기능</span><span class="sxs-lookup"><span data-stu-id="eb249-106">Feature</span></span>    | <span data-ttu-id="eb249-107">최대 한도</span><span class="sxs-lookup"><span data-stu-id="eb249-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="eb249-108">사용자가 만들 수 있는 팀의 수</span><span class="sxs-lookup"><span data-stu-id="eb249-108">Number of teams a user can create</span></span> | <span data-ttu-id="eb249-109">250개체 제한 적용&sup1;</span><span class="sxs-lookup"><span data-stu-id="eb249-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="eb249-110">사용자가 구성원이 될 수 있는 그룹 수</span><span class="sxs-lookup"><span data-stu-id="eb249-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="eb249-111">1,000</span><span class="sxs-lookup"><span data-stu-id="eb249-111">1,000</span></span>|
|<span data-ttu-id="eb249-112">팀 구성원 수 </span><span class="sxs-lookup"><span data-stu-id="eb249-112">Number of members in a team</span></span> | <span data-ttu-id="eb249-113">5,000</span><span class="sxs-lookup"><span data-stu-id="eb249-113">5,000</span></span>       |
|<span data-ttu-id="eb249-114">테넌트에 허용되는 조직 전체 팀 수</span><span class="sxs-lookup"><span data-stu-id="eb249-114">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="eb249-115">5</span><span class="sxs-lookup"><span data-stu-id="eb249-115">5</span></span>     |
|<span data-ttu-id="eb249-116">[조직 전체 팀](create-an-org-wide-team.md)의 구성원 수</span><span class="sxs-lookup"><span data-stu-id="eb249-116">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="eb249-117">5,000</span><span class="sxs-lookup"><span data-stu-id="eb249-117">5,000</span></span>       |
|<span data-ttu-id="eb249-118">전역 관리자가 만들 수 있는 팀의 수</span><span class="sxs-lookup"><span data-stu-id="eb249-118">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="eb249-119">500,000</span><span class="sxs-lookup"><span data-stu-id="eb249-119">500,000</span></span>   |
|<span data-ttu-id="eb249-120">Office 365 테넌트가 보유할 수 있는 팀의 수</span><span class="sxs-lookup"><span data-stu-id="eb249-120">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="eb249-121">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="eb249-121">500,000&sup2;</span></span>     |
|<span data-ttu-id="eb249-122">팀당 채널 수</span><span class="sxs-lookup"><span data-stu-id="eb249-122">Number of channels per team</span></span>    | <span data-ttu-id="eb249-123">200(삭제된 채널 포함)&sup3;</span><span class="sxs-lookup"><span data-stu-id="eb249-123">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="eb249-124">팀당 비공개 채널 수</span><span class="sxs-lookup"><span data-stu-id="eb249-124">Number of channels per team</span></span>    |<span data-ttu-id="eb249-125">30</span><span class="sxs-lookup"><span data-stu-id="eb249-125">30</span></span>|

<span data-ttu-id="eb249-126">&sup1;Azure Active Directory의 모든 디렉터리 개체는 이 제한에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-126">&sup1;Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="eb249-127">전역 관리자는 [응용 프로그램 사용 권한](https://docs.microsoft.com/graph/permissions-reference)을 사용하여 Microsoft Graph를 호출하는 앱과 마찬가지로 이 제한에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-127">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="eb249-128">&sup2;이 제한에는 보관된 팀이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-128">&sup2;This limit includes archived teams.</span></span>

<span data-ttu-id="eb249-129">&sup3;삭제된 채널은 30일 이내에 복원될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-129">&sup3;Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="eb249-130">이 30일 동안에는 삭제된 채널이 팀당 200채널 한도에 계속 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-130">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="eb249-131">30일 후에는 삭제된 채널과 해당 콘텐츠가 영구적으로 삭제되고 채널이 더 이상 팀당 200채널 한도에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-131">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

## <a name="messaging"></a><span data-ttu-id="eb249-132">메시징</span><span class="sxs-lookup"><span data-stu-id="eb249-132">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="eb249-133">채팅</span><span class="sxs-lookup"><span data-stu-id="eb249-133">Chat</span></span>

<span data-ttu-id="eb249-134">Teams의 채팅 목록의 일부인 대화에 참여하는 사용자는 관리자가 채팅 대화를 검색할 수 있도록 Exchange Online(클라우드 기반) 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-134">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="eb249-135">채팅 목록의 일부인 대화는 채팅 참가자의 클라우드 기반 사서함에 저장되기기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-135">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="eb249-136">채팅 참가자에게 Exchange Online 사서함이 없는 경우 관리자는 채팅 대화에 대한 보류 또는 저장을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-136">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="eb249-137">예를 들어 Exchange 하이브리드 배포에서는 온-프레미스 사서함이 있는 사용자가 Teams 채팅 목록에 포함된 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-137">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="eb249-138">하지만 이 경우에는 사용자에게 클라우드 기반 사서함이 없으므로 이 대화의 콘텐츠를 검색할 수 없고 보류 상태로 둘 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-138">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="eb249-139">(자세한 내용은 [Exchange와 Microsoft Teams의 상호 작용 방식](exchange-teams-interact.md)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="eb249-139">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="eb249-140">Teams 채팅은 Microsoft Exchange 백 엔드에서 작동하므로 Exchange 메시징 제한은 Teams 내의 채팅 기능에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-140">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="eb249-141">기능</span><span class="sxs-lookup"><span data-stu-id="eb249-141">Feature</span></span>  | <span data-ttu-id="eb249-142">최대 한도</span><span class="sxs-lookup"><span data-stu-id="eb249-142">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="eb249-143">비공개 채팅에 참가 중인 사용자 수<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="eb249-143">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="eb249-144">100</span><span class="sxs-lookup"><span data-stu-id="eb249-144">100</span></span>    |
|<span data-ttu-id="eb249-145">첨부 파일 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eb249-145">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="eb249-146">10</span><span class="sxs-lookup"><span data-stu-id="eb249-146">EXAMPLE 10</span></span>     |

<span data-ttu-id="eb249-147"><sup>1</sup>채팅에 20명 이상의 사용자가 있는 경우 다음과 같은 채팅 기능이 꺼집니다. Outlook 자동 회신 및 Teams 상태 메시지, 입력 표시기, 비디오 및 오디오 통화, 공유, 읽음 확인.</span><span class="sxs-lookup"><span data-stu-id="eb249-147"><sup>1</sup>If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="eb249-148"><sup>2</sup>첨부 파일 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-148"><sup>2</sup>If the number of attachments exceeds this limit, you'll see an error message.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="eb249-149">채널 전자 메일 보내기 </span><span class="sxs-lookup"><span data-stu-id="eb249-149">Emailing a channel</span></span>

 <span data-ttu-id="eb249-150">사용자가 Teams의 채널에 전자 메일을 보내려면 채널 전자 메일 주소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-150">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="eb249-151">전자 메일이 채널의 일부인 경우 누구나 답장을 보내 대화를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-151">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="eb249-152">다음은 채널에 전자 메일을 보낼 때 적용되는 몇 가지 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-152">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="eb249-153">기능</span><span class="sxs-lookup"><span data-stu-id="eb249-153">Feature</span></span>  | <span data-ttu-id="eb249-154">최대 한도</span><span class="sxs-lookup"><span data-stu-id="eb249-154">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="eb249-155">메시지 크기<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="eb249-155">Message size<sup>1<sup></span></span> | <span data-ttu-id="eb249-156">24KB</span><span class="sxs-lookup"><span data-stu-id="eb249-156">24 KB</span></span> |
|<span data-ttu-id="eb249-157">첨부 파일 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eb249-157">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="eb249-158">20</span><span class="sxs-lookup"><span data-stu-id="eb249-158">Default: 20</span></span>     |
|<span data-ttu-id="eb249-159">각 첨부 파일의 크기</span><span class="sxs-lookup"><span data-stu-id="eb249-159">Size of each file attachment</span></span> | <span data-ttu-id="eb249-160">10MB 미만</span><span class="sxs-lookup"><span data-stu-id="eb249-160">Less than 10 MB</span></span> |
|<span data-ttu-id="eb249-161">인라인 이미지 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="eb249-161">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="eb249-162">50</span><span class="sxs-lookup"><span data-stu-id="eb249-162">50</span></span>   |

<span data-ttu-id="eb249-163"><sup>1</sup>메시지가 이 한도를 초과하는 경우 미리 보기 메시지가 생성되고, 사용자에게 제공된 링크에서 원본 전자 메일을 다운로드하여 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-163"><sup>1</sup>If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="eb249-164"><sup>2</sup>첨부 파일이나 이미지 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-164"><sup>2</sup>If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="eb249-165">자세한 내용은 [Exchange Online 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb249-165">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="eb249-166">모든 Office 365 라이선스에서 메시지 크기, 첨부 파일 및 인라인 이미지 제한이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-166">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="eb249-167">채널 이름</span><span class="sxs-lookup"><span data-stu-id="eb249-167">Channel names</span></span>

<span data-ttu-id="eb249-168">채널 이름에는 다음 문자나 단어가 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-168">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="eb249-169">문자</span><span class="sxs-lookup"><span data-stu-id="eb249-169">Characters</span></span>     | <span data-ttu-id="eb249-170">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="eb249-170">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="eb249-171">&#124; ' " ..</span><span class="sxs-lookup"><span data-stu-id="eb249-171">&#124; ' " ..</span></span>        |
|<span data-ttu-id="eb249-172">해당 범위에 있는 문자</span><span class="sxs-lookup"><span data-stu-id="eb249-172">Characters in these ranges</span></span>    | <span data-ttu-id="eb249-173">0~1F</span><span class="sxs-lookup"><span data-stu-id="eb249-173">0 to 1F</span></span><br><span data-ttu-id="eb249-174">80~9F</span><span class="sxs-lookup"><span data-stu-id="eb249-174">80 to 9F</span></span>        |
|<span data-ttu-id="eb249-175">단어</span><span class="sxs-lookup"><span data-stu-id="eb249-175">Words</span></span>     | <span data-ttu-id="eb249-176">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1~COM9, LPT1~LPT9, desktop.ini,  &#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="eb249-176">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="eb249-177">또한 채널 이름은 밑줄(_) 또는 마침표(.)로 시작하거나 마침표(.)로 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-177">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="eb249-178">모임 및 통화</span><span class="sxs-lookup"><span data-stu-id="eb249-178">Meetings and calls</span></span>

|<span data-ttu-id="eb249-179">기능</span><span class="sxs-lookup"><span data-stu-id="eb249-179">Feature</span></span>     | <span data-ttu-id="eb249-180">최대 한도</span><span class="sxs-lookup"><span data-stu-id="eb249-180">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="eb249-181">모임에 참가 중인 사용자 수</span><span class="sxs-lookup"><span data-stu-id="eb249-181">Number of people in a meeting</span></span>  | <span data-ttu-id="eb249-182">250</span><span class="sxs-lookup"><span data-stu-id="eb249-182">250</span></span>    |
|<span data-ttu-id="eb249-183">최대 PowerPoint 파일 크기</span><span class="sxs-lookup"><span data-stu-id="eb249-183">Max PowerPoint File Size</span></span> | <span data-ttu-id="eb249-184">2GB</span><span class="sxs-lookup"><span data-stu-id="eb249-184">2GB</span></span>|

## <a name="teams-live-events"></a><span data-ttu-id="eb249-185">Teams 라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="eb249-185">Teams live events</span></span>

|<span data-ttu-id="eb249-186">기능</span><span class="sxs-lookup"><span data-stu-id="eb249-186">Feature</span></span>     | <span data-ttu-id="eb249-187">최대 한도</span><span class="sxs-lookup"><span data-stu-id="eb249-187">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="eb249-188">대상 그룹 크기</span><span class="sxs-lookup"><span data-stu-id="eb249-188">Audience size</span></span> | <span data-ttu-id="eb249-189">10,000 참석자</span><span class="sxs-lookup"><span data-stu-id="eb249-189">10,000 attendees</span></span> |
|<span data-ttu-id="eb249-190">이벤트 기간</span><span class="sxs-lookup"><span data-stu-id="eb249-190">Duration of event</span></span> | <span data-ttu-id="eb249-191">4시간</span><span class="sxs-lookup"><span data-stu-id="eb249-191">4 hours</span></span> |
|<span data-ttu-id="eb249-192">Office 365 테넌트의 동시 라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="eb249-192">Concurrent live events in an Office 365 tenant</span></span> | <span data-ttu-id="eb249-193">15</span><span class="sxs-lookup"><span data-stu-id="eb249-193">15 GB</span></span> |

<span data-ttu-id="eb249-194">라이브 이벤트와 Teams 라이브 이벤트와 Skype 모임 브로드캐스트 비교에 대한 자세한 내용은 [Teams 라이브 이벤트 및 Skype 모임 브로드캐스트](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb249-194">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="eb249-195">Outlook에서의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="eb249-195">Presence in Outlook</span></span>

<span data-ttu-id="eb249-196">Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-196">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="eb249-197">팀의 현재 상태에 대해 자세히 알아보려면 [팀의 사용자 현재 상태](presence-admins.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb249-197">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="eb249-198">저장소</span><span class="sxs-lookup"><span data-stu-id="eb249-198">Storage</span></span>

<span data-ttu-id="eb249-199">Microsoft Teams의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 채널은 기본 팀 사이트 문서 라이브러리 내에 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-199">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="eb249-200">대화 내에서 공유된 파일은 문서 라이브러리에 자동으로 추가되고, SharePoint에 설정된 사용 권한 및 파일 보안 옵션은 Teams에서 자동으로 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-200">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="eb249-201">테넌트에서 SharePoint Online을 사용하지 않는 경우 Microsoft Teams 사용자는 팀에서 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-201">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="eb249-202">비즈니스용 OneDrive(SharePoint 라이선스에 연결됨)가 해당 기능에 필요하므로 개인 채팅 사용자도 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-202">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="eb249-203">SharePoint Online 문서 라이브러리와 비즈니스용 OneDrive에 파일을 저장하면 테넌트 수준에서 구성된 모든 규정 준수 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-203">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="eb249-204">(자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive가 Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="eb249-204">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="eb249-205">Teams는 파일 공유를 위해 SharePoint Online 백 엔드에서 실행되므로 SharePoint 제한 사항은 팀 내의 파일 섹션에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-205">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="eb249-206">다음은 SharePoint Online에 적용할 수 있는 저장소 용량 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-206">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="eb249-207">기능</span><span class="sxs-lookup"><span data-stu-id="eb249-207">Feature</span></span>                 |<span data-ttu-id="eb249-208">Office 365 Business Essentials</span><span class="sxs-lookup"><span data-stu-id="eb249-208">Office 365 Business Essentials</span></span>  |<span data-ttu-id="eb249-209">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="eb249-209">Office 365 Business Premium</span></span>   |<span data-ttu-id="eb249-210">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="eb249-210">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="eb249-211">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="eb249-211">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="eb249-212">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="eb249-212">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="eb249-213">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="eb249-213">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="eb249-214">저장소</span><span class="sxs-lookup"><span data-stu-id="eb249-214">Storage</span></span>                 |<span data-ttu-id="eb249-215">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="eb249-215">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="eb249-216">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="eb249-216">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="eb249-217">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="eb249-217">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="eb249-218">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="eb249-218">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="eb249-219">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="eb249-219">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="eb249-220">조직당 1TB</span><span class="sxs-lookup"><span data-stu-id="eb249-220">1 TB per organization</span></span>           |
|<span data-ttu-id="eb249-221">Teams 파일용 저장소</span><span class="sxs-lookup"><span data-stu-id="eb249-221">Storage for Teams Files</span></span> |<span data-ttu-id="eb249-222">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="eb249-222">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="eb249-223">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="eb249-223">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="eb249-224">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="eb249-224">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="eb249-225">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="eb249-225">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="eb249-226">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="eb249-226">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="eb249-227">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="eb249-227">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="eb249-228">파일 업로드 제한(파일당)</span><span class="sxs-lookup"><span data-stu-id="eb249-228">File upload limit  (per file)</span></span>    |<span data-ttu-id="eb249-229">15GB</span><span class="sxs-lookup"><span data-stu-id="eb249-229">15 GB</span></span>    |<span data-ttu-id="eb249-230">15GB</span><span class="sxs-lookup"><span data-stu-id="eb249-230">15 GB</span></span>    |<span data-ttu-id="eb249-231">15GB</span><span class="sxs-lookup"><span data-stu-id="eb249-231">15 GB</span></span>    |<span data-ttu-id="eb249-232">15GB</span><span class="sxs-lookup"><span data-stu-id="eb249-232">15 GB</span></span>    |<span data-ttu-id="eb249-233">15GB</span><span class="sxs-lookup"><span data-stu-id="eb249-233">15 GB</span></span>    |<span data-ttu-id="eb249-234">15GB</span><span class="sxs-lookup"><span data-stu-id="eb249-234">15 GB</span></span>    |

<span data-ttu-id="eb249-235">채널은 팀을 위해 만든 SharePoint Online 사이트 모음의 폴더에 의해 지원되므로 채널 내의 파일 탭은 속해 있는 팀의 저장소 용량 한도를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-235">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="eb249-236">자세한 내용은 [SharePoint Online 제한](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb249-236">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="contacts"></a><span data-ttu-id="eb249-237">연락처</span><span class="sxs-lookup"><span data-stu-id="eb249-237">Contacts</span></span>

<span data-ttu-id="eb249-238">Teams에서 사용하는 연락처:</span><span class="sxs-lookup"><span data-stu-id="eb249-238">Teams uses these contacts:</span></span>

- <span data-ttu-id="eb249-239">조직의 Active Directory에 있는 연락처</span><span class="sxs-lookup"><span data-stu-id="eb249-239">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="eb249-240">사용자의 Outlook 기본 폴더에 추가된 연락처</span><span class="sxs-lookup"><span data-stu-id="eb249-240">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="eb249-241">Teams 사용자는 조직의 Active Directory에 있는 모든 사용자와 커뮤니케이션할 수 있으며, 조직의 Active Directory에 있는 모든 사용자를 **채팅** > **연락처** 또는 **통화** > **연락처**로 이동하여 대화 상대 및 대화 상대 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-241">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="eb249-242">팀 사용자는 조직 내의 Active Directory에 없는 사용자를 **통화** > **연락처**로 이동하여 연락처로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb249-242">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="eb249-243">브라우저</span><span class="sxs-lookup"><span data-stu-id="eb249-243">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="eb249-244">운영 체제</span><span class="sxs-lookup"><span data-stu-id="eb249-244">Operating systems</span></span>

<span data-ttu-id="eb249-245">운영 체제 요구 사항에 대한 자세한 내용은 [Microsoft Teams용 클라이언트 다운로드](get-clients.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eb249-245">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
