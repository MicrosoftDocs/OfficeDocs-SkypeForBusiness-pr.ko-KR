---
title: Microsoft Teams의 제한 사항 및 사양
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 이 문서에서는 Microsoft Teams에 적용되는 몇 가지 제한 사항, 사양 및 기타 요구 사항에 대해 설명합니다.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ae0583225de5eabfd6cad77895859f9c7159276f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508085"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="0ab32-103">Microsoft Teams의 제한 사항 및 사양</span><span class="sxs-lookup"><span data-stu-id="0ab32-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="0ab32-104">이 문서에서는 Microsoft Teams에 적용되는 몇 가지 제한 사항, 사양 및 기타 요구 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="0ab32-105">팀 및 채널</span><span class="sxs-lookup"><span data-stu-id="0ab32-105">Teams and channels</span></span>

|<span data-ttu-id="0ab32-106">기능</span><span class="sxs-lookup"><span data-stu-id="0ab32-106">Feature</span></span>    | <span data-ttu-id="0ab32-107">최대 한도</span><span class="sxs-lookup"><span data-stu-id="0ab32-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="0ab32-108">사용자가 만들 수 있는 팀의 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-108">Number of teams a user can create</span></span> | <span data-ttu-id="0ab32-109">250개체 제한 적용&sup1;</span><span class="sxs-lookup"><span data-stu-id="0ab32-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="0ab32-110">사용자가 구성원이 될 수 있는 그룹 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="0ab32-111">1,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="0ab32-111">1,000&sup2;</span></span>|
|<span data-ttu-id="0ab32-112">팀의 구성원 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-112">Number of members in a team</span></span> | <span data-ttu-id="0ab32-113">10,000</span><span class="sxs-lookup"><span data-stu-id="0ab32-113">10,000</span></span>       |
|<span data-ttu-id="0ab32-114">팀당 소유자 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-114">Number of owners per team</span></span> | <span data-ttu-id="0ab32-115">100</span><span class="sxs-lookup"><span data-stu-id="0ab32-115">100</span></span>   |
|<span data-ttu-id="0ab32-116">테넌트에 허용되는 조직 전체 팀 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="0ab32-117">5</span><span class="sxs-lookup"><span data-stu-id="0ab32-117">5</span></span>     |
|<span data-ttu-id="0ab32-118">[조직 전체 팀](create-an-org-wide-team.md)의 구성원 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="0ab32-119">5,000</span><span class="sxs-lookup"><span data-stu-id="0ab32-119">5,000</span></span>       |
|<span data-ttu-id="0ab32-120">전역 관리자가 만들 수 있는 팀의 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="0ab32-121">500,000</span><span class="sxs-lookup"><span data-stu-id="0ab32-121">500,000</span></span>   |
|<span data-ttu-id="0ab32-122">Microsoft 365 또는 Office 365 조직이 보유할 수 있는 팀 개수</span><span class="sxs-lookup"><span data-stu-id="0ab32-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="0ab32-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="0ab32-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="0ab32-124">팀당 채널 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-124">Number of channels per team</span></span>    | <span data-ttu-id="0ab32-125">200(삭제된 채널 포함)&sup3;</span><span class="sxs-lookup"><span data-stu-id="0ab32-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="0ab32-126">팀당 비공개 채널 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-126">Number of Private channels per team</span></span>    |<span data-ttu-id="0ab32-127">30</span><span class="sxs-lookup"><span data-stu-id="0ab32-127">30</span></span>| <span data-ttu-id="0ab32-128">(삭제된 채널 포함)&sup3;</span><span class="sxs-lookup"><span data-stu-id="0ab32-128">(includes deleted channels)&sup3;</span></span>
|<span data-ttu-id="0ab32-129">비공개 채널 회원수</span><span class="sxs-lookup"><span data-stu-id="0ab32-129">Number of members in a Private channel</span></span>    |<span data-ttu-id="0ab32-130">250</span><span class="sxs-lookup"><span data-stu-id="0ab32-130">250</span></span>|
|<span data-ttu-id="0ab32-131">Office 365 그룹에서 팀으로 전환할 수 있는 최대 구성원 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-131">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="0ab32-132">10,000</span><span class="sxs-lookup"><span data-stu-id="0ab32-132">10,000</span></span>|
|<span data-ttu-id="0ab32-133">채널 대화 게시 크기</span><span class="sxs-lookup"><span data-stu-id="0ab32-133">Channel conversation post size</span></span> | <span data-ttu-id="0ab32-134">게시물당 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="0ab32-134">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="0ab32-p101"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span><span class="sxs-lookup"><span data-stu-id="0ab32-p101"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="0ab32-p102"><sup>2</sup> This limit includes archived teams. To go beyond the maximum limit, you must contact Microsoft support.</span><span class="sxs-lookup"><span data-stu-id="0ab32-p102"><sup>2</sup> This limit includes archived teams. To go beyond the maximum limit, you must contact Microsoft support.</span></span>

<span data-ttu-id="0ab32-p103"><sup>3</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.</span><span class="sxs-lookup"><span data-stu-id="0ab32-p103"><sup>3</sup> Deleted channels can be restored within 30 days. During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit. After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.</span></span>

<span data-ttu-id="0ab32-142"><sup>4</sup> 28 KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션, 커넥터 수, 반응이 포함되기 때문에 대략적인 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-142"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="0ab32-143">메시징</span><span class="sxs-lookup"><span data-stu-id="0ab32-143">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="0ab32-144">채팅</span><span class="sxs-lookup"><span data-stu-id="0ab32-144">Chat</span></span>

<span data-ttu-id="0ab32-p104">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span><span class="sxs-lookup"><span data-stu-id="0ab32-p104">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="0ab32-151">Teams 채팅은 Microsoft Exchange 백 엔드에서 작동하므로 Exchange 메시징 제한은 Teams 내의 채팅 기능에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-151">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="0ab32-152">기능</span><span class="sxs-lookup"><span data-stu-id="0ab32-152">Feature</span></span>  | <span data-ttu-id="0ab32-153">최대 한도</span><span class="sxs-lookup"><span data-stu-id="0ab32-153">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="0ab32-154">비공개 채팅에 참가 중인 사용자 수<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0ab32-154">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="0ab32-155">250</span><span class="sxs-lookup"><span data-stu-id="0ab32-155">250</span></span> |
|<span data-ttu-id="0ab32-156">채팅에서 영상 또는 음성 통화 중인 사용자 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-156">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="0ab32-157">20</span><span class="sxs-lookup"><span data-stu-id="0ab32-157">20</span></span> |
|<span data-ttu-id="0ab32-158">첨부 파일 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0ab32-158">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="0ab32-159">10</span><span class="sxs-lookup"><span data-stu-id="0ab32-159">10</span></span>     |
|<span data-ttu-id="0ab32-160">채팅 크기</span><span class="sxs-lookup"><span data-stu-id="0ab32-160">Chat size</span></span> | <span data-ttu-id="0ab32-161">게시물당 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="0ab32-161">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="0ab32-p105"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span><span class="sxs-lookup"><span data-stu-id="0ab32-p105"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="0ab32-164"><sup>2</sup>첨부 파일 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-164"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="0ab32-165"><sup>3</sup> 28 KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션, 반응이 포함되기 때문에 대략적인 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-165"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="0ab32-166">채널 전자 메일 보내기 </span><span class="sxs-lookup"><span data-stu-id="0ab32-166">Emailing a channel</span></span>

 <span data-ttu-id="0ab32-p106">If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.</span><span class="sxs-lookup"><span data-stu-id="0ab32-p106">If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="0ab32-170">기능</span><span class="sxs-lookup"><span data-stu-id="0ab32-170">Feature</span></span>  | <span data-ttu-id="0ab32-171">최대 한도</span><span class="sxs-lookup"><span data-stu-id="0ab32-171">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="0ab32-172">메시지 크기<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="0ab32-172">Message size<sup>1<sup></span></span> | <span data-ttu-id="0ab32-173">24KB</span><span class="sxs-lookup"><span data-stu-id="0ab32-173">24 KB</span></span> |
|<span data-ttu-id="0ab32-174">첨부 파일 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0ab32-174">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="0ab32-175">20</span><span class="sxs-lookup"><span data-stu-id="0ab32-175">20</span></span>     |
|<span data-ttu-id="0ab32-176">각 첨부 파일의 크기</span><span class="sxs-lookup"><span data-stu-id="0ab32-176">Size of each file attachment</span></span> | <span data-ttu-id="0ab32-177">10MB 미만</span><span class="sxs-lookup"><span data-stu-id="0ab32-177">Less than 10 MB</span></span> |
|<span data-ttu-id="0ab32-178">인라인 이미지 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0ab32-178">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="0ab32-179">50</span><span class="sxs-lookup"><span data-stu-id="0ab32-179">50</span></span>   |

<span data-ttu-id="0ab32-180"><sup>1</sup>메시지가 이 한도를 초과하는 경우 미리 보기 메시지가 생성되고, 사용자에게 제공된 링크에서 원본 전자 메일을 다운로드하여 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-180"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="0ab32-181"><sup>2</sup>첨부 파일이나 이미지 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-181"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="0ab32-182">자세한 내용은 [Exchange Online 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ab32-182">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="0ab32-p107">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.</span><span class="sxs-lookup"><span data-stu-id="0ab32-p107">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.</span></span>



## <a name="channel-names"></a><span data-ttu-id="0ab32-185">채널 이름</span><span class="sxs-lookup"><span data-stu-id="0ab32-185">Channel names</span></span>

<span data-ttu-id="0ab32-186">채널 이름에는 다음 문자나 단어가 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-186">Channel names can't contain the following characters or words.</span></span>

|<span data-ttu-id="0ab32-187">유형</span><span class="sxs-lookup"><span data-stu-id="0ab32-187">Type</span></span>|<span data-ttu-id="0ab32-188">예제</span><span class="sxs-lookup"><span data-stu-id="0ab32-188">Example</span></span>|
|---------|---------|
|<span data-ttu-id="0ab32-189">문자</span><span class="sxs-lookup"><span data-stu-id="0ab32-189">Characters</span></span>     | <span data-ttu-id="0ab32-190">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="0ab32-190">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="0ab32-191">&#124; ' " , .</span><span class="sxs-lookup"><span data-stu-id="0ab32-191">&#124; ' " , .</span></span>        |
|<span data-ttu-id="0ab32-192">해당 범위에 있는 문자</span><span class="sxs-lookup"><span data-stu-id="0ab32-192">Characters in these ranges</span></span>    | <span data-ttu-id="0ab32-193">0~1F</span><span class="sxs-lookup"><span data-stu-id="0ab32-193">0 to 1F</span></span><br><span data-ttu-id="0ab32-194">80~9F</span><span class="sxs-lookup"><span data-stu-id="0ab32-194">80 to 9F</span></span>        |
|<span data-ttu-id="0ab32-195">단어</span><span class="sxs-lookup"><span data-stu-id="0ab32-195">Words</span></span>     | <span data-ttu-id="0ab32-196">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1~COM9, LPT1~LPT9, desktop.ini,  &#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="0ab32-196">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="0ab32-197">또한 채널 이름은 밑줄(_) 또는 마침표(.)로 시작하거나 마침표(.)로 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-197">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="0ab32-198">모임 및 통화</span><span class="sxs-lookup"><span data-stu-id="0ab32-198">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ab32-199">**Microsoft 365 라이브 이벤트 한도가 늘어납니다**</span><span class="sxs-lookup"><span data-stu-id="0ab32-199">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="0ab32-200">**고객 지원을 돕기 위해 2021년 1월 1일까지 Teams, Stream 및 Yammer에서 주최하는 라이브 이벤트에 대해 임시 제한 증가를 연장합니다(** 포함).</span><span class="sxs-lookup"><span data-stu-id="0ab32-200">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for live events hosted in Teams, Stream, and Yammer, including**:</span></span>
>
>- <span data-ttu-id="0ab32-201">이벤트당 최대 20,000명의 참석자가 참석합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-201">Up to 20,000 attendees per event</span></span>
>- <span data-ttu-id="0ab32-202">Teams 테넌트당 최대 50개의 동시 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-202">Up to 50 simultaneous events per Teams tenant</span></span>
>- <span data-ttu-id="0ab32-203">브로드캐스트당 최대 16시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-203">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="0ab32-204">추가로 참가자 100,000명 이상의 라이브 이벤트는 Microsoft 365 지원 프로그램을 통해 계획 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-204">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program.</span></span> <span data-ttu-id="0ab32-205">팀에서 각 요청을 평가하고 사용자와 작업을 수행하여 사용 가능한 옵션을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-205">The team will assess each request and work with you to determine options that may be available.</span></span> <span data-ttu-id="0ab32-206">[자세한 정보](https://aka.ms/Stream/Blog/LiveEventOptions)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-206">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="0ab32-207">**2021년 1월 1일 이후 이러한 제한 증가가 필요한 고객은 [고급 통신 추가 기능](teams-add-on-licensing/advanced-communications.md)을 구입해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0ab32-207">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>


|<span data-ttu-id="0ab32-208">기능</span><span class="sxs-lookup"><span data-stu-id="0ab32-208">Feature</span></span>     | <span data-ttu-id="0ab32-209">최대 한도</span><span class="sxs-lookup"><span data-stu-id="0ab32-209">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="0ab32-210">모임에 참가 중인 사용자 수(채팅 및 전화를 걸 수 있음)</span><span class="sxs-lookup"><span data-stu-id="0ab32-210">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="0ab32-211">300</span><span class="sxs-lookup"><span data-stu-id="0ab32-211">300</span></span> |
|<span data-ttu-id="0ab32-212">채팅에서 영상 또는 음성 통화 중인 사용자 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-212">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="0ab32-213">20</span><span class="sxs-lookup"><span data-stu-id="0ab32-213">20</span></span> |
|<span data-ttu-id="0ab32-214">최대 PowerPoint 파일 크기</span><span class="sxs-lookup"><span data-stu-id="0ab32-214">Max PowerPoint File Size</span></span> | <span data-ttu-id="0ab32-215">2GB</span><span class="sxs-lookup"><span data-stu-id="0ab32-215">2GB</span></span>|
|<span data-ttu-id="0ab32-216">Teams는 Microsoft Stream에 업로드되지 않은 [모임 녹화](cloud-recording.md)를 보관하며 로컬로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-216">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="0ab32-217">20일</span><span class="sxs-lookup"><span data-stu-id="0ab32-217">20 days</span></span> |

>[!Note]
> <span data-ttu-id="0ab32-218">Microsoft Stream에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](tmr-meeting-recording-change.md)로의 변경은 단계별로 접근합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-218">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="0ab32-219">출시하면 이 환경에 대해 옵트인할 수 있고 11월에는 Stream을 계속 사용하려는 경우 옵트아웃해야 합니다. 2021년 초에는 모든 고객이 새 모임 녹음/녹화를 위해 비즈니스용 OneDrive와 SharePoint를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-219">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="meeting-expiration"></a><span data-ttu-id="0ab32-220">모임 만료</span><span class="sxs-lookup"><span data-stu-id="0ab32-220">Meeting expiration</span></span>

|<span data-ttu-id="0ab32-221">모임 유형</span><span class="sxs-lookup"><span data-stu-id="0ab32-221">Meeting type</span></span>  |<span data-ttu-id="0ab32-222">이만큼 시간이 지나면 모임이 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-222">Meeting expires after this much time</span></span>  |<span data-ttu-id="0ab32-223">모임을 시작하거나 업데이트할 때마다 만료 시간이 이 시간만큼 연장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-223">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0ab32-224">모임 시작</span><span class="sxs-lookup"><span data-stu-id="0ab32-224">Meet now</span></span>     |<span data-ttu-id="0ab32-225">시작 시간 + 8시간</span><span class="sxs-lookup"><span data-stu-id="0ab32-225">Start time + 8 hours</span></span>         |<span data-ttu-id="0ab32-226">해당 없음</span><span class="sxs-lookup"><span data-stu-id="0ab32-226">N/A</span></span>         |
|<span data-ttu-id="0ab32-227">정규(종료 시간 없음)</span><span class="sxs-lookup"><span data-stu-id="0ab32-227">Regular with no end time</span></span>     |<span data-ttu-id="0ab32-228">시작 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="0ab32-228">Start time + 60 days</span></span>         | <span data-ttu-id="0ab32-229">60일</span><span class="sxs-lookup"><span data-stu-id="0ab32-229">60 days</span></span>        |
|<span data-ttu-id="0ab32-230">정규(종료 시간 있음)</span><span class="sxs-lookup"><span data-stu-id="0ab32-230">Regular with end time</span></span>     |<span data-ttu-id="0ab32-231">종료 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="0ab32-231">End time + 60 days</span></span>         |<span data-ttu-id="0ab32-232">60일</span><span class="sxs-lookup"><span data-stu-id="0ab32-232">60 days</span></span>         |
|<span data-ttu-id="0ab32-233">되풀이(종료 시간 없음)</span><span class="sxs-lookup"><span data-stu-id="0ab32-233">Recurring with no end time</span></span>     |<span data-ttu-id="0ab32-234">시작 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="0ab32-234">Start time + 60 days</span></span>         |<span data-ttu-id="0ab32-235">60일</span><span class="sxs-lookup"><span data-stu-id="0ab32-235">60 days</span></span>         |
|<span data-ttu-id="0ab32-236">되풀이(종료 시간 있음)</span><span class="sxs-lookup"><span data-stu-id="0ab32-236">Recurring with end time</span></span>     |<span data-ttu-id="0ab32-237">마지막 발생 항목의 종료 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="0ab32-237">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="0ab32-238">60일</span><span class="sxs-lookup"><span data-stu-id="0ab32-238">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="0ab32-239">Microsoft Teams 모임의 제한 시간은 24시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-239">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="0ab32-240">Teams 라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="0ab32-240">Teams live events</span></span>

|<span data-ttu-id="0ab32-241">기능</span><span class="sxs-lookup"><span data-stu-id="0ab32-241">Feature</span></span>     | <span data-ttu-id="0ab32-242">최대 한도</span><span class="sxs-lookup"><span data-stu-id="0ab32-242">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="0ab32-243">대상 그룹 크기</span><span class="sxs-lookup"><span data-stu-id="0ab32-243">Audience size</span></span> | <span data-ttu-id="0ab32-244">10,000 참석자</span><span class="sxs-lookup"><span data-stu-id="0ab32-244">10,000 attendees</span></span> |
|<span data-ttu-id="0ab32-245">이벤트 기간</span><span class="sxs-lookup"><span data-stu-id="0ab32-245">Duration of event</span></span> | <span data-ttu-id="0ab32-246">4시간</span><span class="sxs-lookup"><span data-stu-id="0ab32-246">4 hours</span></span> |
|<span data-ttu-id="0ab32-247">Microsoft 365 또는 Office 365 조직에서 실행되는 동시 발생 라이브 이벤트 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0ab32-247">Concurrent live events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="0ab32-248">15</span><span class="sxs-lookup"><span data-stu-id="0ab32-248">15</span></span> |

<span data-ttu-id="0ab32-249"><sup>1</sup> 여러 라이브 이벤트를 원하는 대로 예약할 수 있지만, 한 번에 15개만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-249"><sup>1</sup> You can schedule as many live events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="0ab32-250">프로듀서가 라이브 이벤트에 참가하는 즉시 실행 중인 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-250">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="0ab32-251">16번째 라이브 이벤트에 참가하려고 시도하는 프로듀서는 오류 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-251">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="0ab32-252">라이브 이벤트와 Teams 라이브 이벤트와 Skype 모임 브로드캐스트 비교에 대한 자세한 내용은 [Teams 라이브 이벤트 및 Skype 모임 브로드캐스트](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ab32-252">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ab32-253">**Microsoft 365 라이브 이벤트 한도가 늘어납니다**</span><span class="sxs-lookup"><span data-stu-id="0ab32-253">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="0ab32-254">고객이 급변하는 커뮤니케이션 요구를 충족할 수 있도록 Teams, Stream, Yammer에서 주최하는 라이브 이벤트에 대해 2021년 1월 1일까지 한시적으로 기본값 제한을 상향 조정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-254">To help customers meet rapidly changing communication needs, we will temporarily raise default limits until January 1, 2021, for live events hosted in Teams, Stream, and Yammer.</span></span>
>
> - <span data-ttu-id="0ab32-255">참석자 제한: 이벤트는 최대 20,000명의 참석자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-255">Attendee limit: events can support up to 20,000 attendees</span></span>
> - <span data-ttu-id="0ab32-256">동시 이벤트: 한 테넌트에 걸쳐 동시에 50개의 이벤트 호스트가 가능</span><span class="sxs-lookup"><span data-stu-id="0ab32-256">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="0ab32-257">이벤트 기간: 이벤트 시간이 브로드캐스트 당 16시간으로 늘어났습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-257">Event duration: event length has been increased to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="0ab32-258">또한 Microsoft 라이브 이벤트 지원 프로그램을 통해 최대 100,000명의 참석자가 참여하는 라이브 이벤트를 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-258">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft live events assistance program.</span></span> <span data-ttu-id="0ab32-259">[자세한 정보](https://aka.ms/Stream/Blog/LiveEventOptions)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-259">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="0ab32-260">**2021년 1월 1일 이후 이러한 제한 증가가 필요한 고객은 [고급 통신 추가 기능](teams-add-on-licensing/advanced-communications.md)을 구입해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0ab32-260">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="0ab32-261">Outlook에서의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="0ab32-261">Presence in Outlook</span></span>

<span data-ttu-id="0ab32-262">Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-262">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="0ab32-263">팀의 현재 상태에 대해 자세히 알아보려면 [팀의 사용자 현재 상태](presence-admins.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ab32-263">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="0ab32-264">저장소</span><span class="sxs-lookup"><span data-stu-id="0ab32-264">Storage</span></span>

<span data-ttu-id="0ab32-265">Microsoft Teams의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 채널은 기본 팀 사이트 문서 라이브러리 내에 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-265">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="0ab32-266">대화 내에서 공유된 파일은 문서 라이브러리에 자동으로 추가되고, SharePoint에 설정된 사용 권한 및 파일 보안 옵션은 Teams에서 자동으로 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-266">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="0ab32-267">각 [개인 채널](https://docs.microsoft.com/microsoftteams/private-channels)에는 고유한 SharePoint 사이트 모음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-267">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site collection.</span></span>

<span data-ttu-id="0ab32-268">테넌트에서 SharePoint Online을 사용하지 않는 경우 Microsoft Teams 사용자는 팀에서 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-268">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="0ab32-269">비즈니스용 OneDrive(SharePoint 라이선스에 연결됨)가 해당 기능에 필요하므로 개인 채팅 사용자도 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-269">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="0ab32-270">SharePoint Online 문서 라이브러리와 비즈니스용 OneDrive에 파일을 저장하면 테넌트 수준에서 구성된 모든 규정 준수 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-270">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="0ab32-271">(자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive가 Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="0ab32-271">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="0ab32-272">Teams는 파일 공유를 위해 SharePoint Online 백 엔드에서 실행되므로 SharePoint 제한 사항은 팀 내의 파일 섹션에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-272">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="0ab32-273">다음은 SharePoint Online에 적용할 수 있는 저장소 용량 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-273">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="0ab32-274">기능</span><span class="sxs-lookup"><span data-stu-id="0ab32-274">Feature</span></span>                 |<span data-ttu-id="0ab32-275">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="0ab32-275">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="0ab32-276">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="0ab32-276">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="0ab32-277">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="0ab32-277">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="0ab32-278">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="0ab32-278">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="0ab32-279">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="0ab32-279">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="0ab32-280">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="0ab32-280">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="0ab32-281">저장소</span><span class="sxs-lookup"><span data-stu-id="0ab32-281">Storage</span></span>                 |<span data-ttu-id="0ab32-282">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="0ab32-282">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="0ab32-283">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="0ab32-283">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="0ab32-284">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="0ab32-284">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="0ab32-285">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="0ab32-285">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="0ab32-286">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="0ab32-286">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="0ab32-287">조직당 1TB</span><span class="sxs-lookup"><span data-stu-id="0ab32-287">1 TB per organization</span></span>           |
|<span data-ttu-id="0ab32-288">Teams 파일용 저장소</span><span class="sxs-lookup"><span data-stu-id="0ab32-288">Storage for Teams Files</span></span> |<span data-ttu-id="0ab32-289">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="0ab32-289">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="0ab32-290">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="0ab32-290">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="0ab32-291">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="0ab32-291">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="0ab32-292">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="0ab32-292">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="0ab32-293">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="0ab32-293">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="0ab32-294">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="0ab32-294">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="0ab32-295">파일 업로드 제한(파일당)</span><span class="sxs-lookup"><span data-stu-id="0ab32-295">File upload limit  (per file)</span></span>    |<span data-ttu-id="0ab32-296">100GB</span><span class="sxs-lookup"><span data-stu-id="0ab32-296">100 GB</span></span>    |<span data-ttu-id="0ab32-297">100GB</span><span class="sxs-lookup"><span data-stu-id="0ab32-297">100 GB</span></span>    |<span data-ttu-id="0ab32-298">100GB</span><span class="sxs-lookup"><span data-stu-id="0ab32-298">100 GB</span></span>    |<span data-ttu-id="0ab32-299">100GB</span><span class="sxs-lookup"><span data-stu-id="0ab32-299">100 GB</span></span>    |<span data-ttu-id="0ab32-300">100GB</span><span class="sxs-lookup"><span data-stu-id="0ab32-300">100 GB</span></span>    |<span data-ttu-id="0ab32-301">100GB</span><span class="sxs-lookup"><span data-stu-id="0ab32-301">100 GB</span></span>    |

<span data-ttu-id="0ab32-302">채널은 팀을 위해 만든 SharePoint Online 사이트 모음의 폴더에 의해 지원되므로 채널 내의 파일 탭은 속해 있는 팀의 저장소 용량 한도를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-302">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="0ab32-303">자세한 내용은 [SharePoint Online 제한](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ab32-303">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="0ab32-304">수업 팀</span><span class="sxs-lookup"><span data-stu-id="0ab32-304">Class teams</span></span>

<span data-ttu-id="0ab32-305">교육용 Microsoft Teams는 강의실 교육과 같은 고유한 교육 시나리오를 위해 설계된 템플릿을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-305">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching.</span></span> <span data-ttu-id="0ab32-306">수업 팀을 포함한 팀 유형에 대한 자세한 내용은 [Microsoft Teams에서 공동 작업할 팀 유형 선택](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-306">More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="0ab32-307">수업 팀은 추가 앱이 포함된 템플릿 유형이며, 팀 구성원 수에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-307">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="0ab32-308">수업 팀을 사용하려면 [Office 365 Education 라이선스](https://www.microsoft.com/education/products/office)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-308">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="0ab32-309">수업 팀 제한은 다음 표에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-309">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="0ab32-310">기능</span><span class="sxs-lookup"><span data-stu-id="0ab32-310">Feature</span></span>  |<span data-ttu-id="0ab32-311">최대 한도</span><span class="sxs-lookup"><span data-stu-id="0ab32-311">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="0ab32-312">팀의 구성원 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-312">Number of members in a team</span></span>    | <span data-ttu-id="0ab32-313">이 문서의 [Teams 및 채널](#teams-and-channels) 섹션을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-313">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="0ab32-314">수업 팀에서 할당을 사용할 구성원 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-314">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="0ab32-315">200</span><span class="sxs-lookup"><span data-stu-id="0ab32-315">200</span></span>        |
|<span data-ttu-id="0ab32-316">수업 팀에서 OneNote 클래스 노트북을 사용할 구성원 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-316">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="0ab32-317">200</span><span class="sxs-lookup"><span data-stu-id="0ab32-317">200</span></span>         |

<span data-ttu-id="0ab32-318">한 학급 팀이 200명 이상의 구성원을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-318">A class team can support more than 200 members.</span></span> <span data-ttu-id="0ab32-319">그러나 팀 내에서 Assignments 앱 또는 Class Notebook 앱을 사용하려는 경우 구성원 수를 위의 최대 제한 이하로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-319">However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>


## <a name="tags"></a><span data-ttu-id="0ab32-320">태그</span><span class="sxs-lookup"><span data-stu-id="0ab32-320">Tags</span></span>

|<span data-ttu-id="0ab32-321">기능</span><span class="sxs-lookup"><span data-stu-id="0ab32-321">Feature</span></span>  |<span data-ttu-id="0ab32-322">최대 한도</span><span class="sxs-lookup"><span data-stu-id="0ab32-322">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="0ab32-323">팀당 태그 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-323">Number of tags per team</span></span>    | <span data-ttu-id="0ab32-324">100</span><span class="sxs-lookup"><span data-stu-id="0ab32-324">100</span></span>        |
|<span data-ttu-id="0ab32-325">팀당 제안된 기본 태그 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-325">Number of suggested default tags per team</span></span>    | <span data-ttu-id="0ab32-326">25</span><span class="sxs-lookup"><span data-stu-id="0ab32-326">25</span></span>        |
|<span data-ttu-id="0ab32-327">태그에 할당되는 팀 구성원 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-327">Number of team members assign to a tag</span></span>    |<span data-ttu-id="0ab32-328">100</span><span class="sxs-lookup"><span data-stu-id="0ab32-328">100</span></span>         |
|<span data-ttu-id="0ab32-329">사용자에게 할당되는 태그 수</span><span class="sxs-lookup"><span data-stu-id="0ab32-329">Number of tags assigned to a user</span></span>    |<span data-ttu-id="0ab32-330">25</span><span class="sxs-lookup"><span data-stu-id="0ab32-330">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="0ab32-331">연락처</span><span class="sxs-lookup"><span data-stu-id="0ab32-331">Contacts</span></span>

<span data-ttu-id="0ab32-332">Teams에서 사용하는 연락처:</span><span class="sxs-lookup"><span data-stu-id="0ab32-332">Teams uses these contacts:</span></span>

- <span data-ttu-id="0ab32-333">조직의 Active Directory에 있는 연락처</span><span class="sxs-lookup"><span data-stu-id="0ab32-333">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="0ab32-334">사용자의 Outlook 기본 폴더에 추가된 연락처</span><span class="sxs-lookup"><span data-stu-id="0ab32-334">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="0ab32-335">Teams 사용자는 조직의 Active Directory에 있는 모든 사용자와 커뮤니케이션할 수 있으며, 조직의 Active Directory에 있는 모든 사용자를 **채팅** > **연락처** 또는 **통화** > **연락처**로 이동하여 대화 상대 및 대화 상대 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-335">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="0ab32-336">팀 사용자는 조직 내의 Active Directory에 없는 사용자를 **통화** > **연락처**로 이동하여 연락처로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ab32-336">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="0ab32-337">브라우저</span><span class="sxs-lookup"><span data-stu-id="0ab32-337">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="0ab32-338">운영 체제</span><span class="sxs-lookup"><span data-stu-id="0ab32-338">Operating systems</span></span>

<span data-ttu-id="0ab32-339">운영 체제 요구 사항에 대한 자세한 내용은 [Microsoft Teams용 클라이언트 다운로드](get-clients.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ab32-339">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
