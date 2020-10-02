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
ms.openlocfilehash: fadc9fbeb82b4cb808b9beb698c0726c22f78c44
ms.sourcegitcommit: 762e303509940f830c304e00a98b05796bf5537f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333268"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="05350-103">Microsoft Teams의 제한 사항 및 사양</span><span class="sxs-lookup"><span data-stu-id="05350-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="05350-104">이 문서에서는 Microsoft Teams에 적용되는 몇 가지 제한 사항, 사양 및 기타 요구 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="05350-105">팀 및 채널</span><span class="sxs-lookup"><span data-stu-id="05350-105">Teams and channels</span></span>

|<span data-ttu-id="05350-106">기능</span><span class="sxs-lookup"><span data-stu-id="05350-106">Feature</span></span>    | <span data-ttu-id="05350-107">최대 한도</span><span class="sxs-lookup"><span data-stu-id="05350-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="05350-108">사용자가 만들 수 있는 팀의 수</span><span class="sxs-lookup"><span data-stu-id="05350-108">Number of teams a user can create</span></span> | <span data-ttu-id="05350-109">250개체 제한 적용&sup1;</span><span class="sxs-lookup"><span data-stu-id="05350-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="05350-110">사용자가 구성원이 될 수 있는 그룹 수</span><span class="sxs-lookup"><span data-stu-id="05350-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="05350-111">1,000</span><span class="sxs-lookup"><span data-stu-id="05350-111">1,000</span></span>|
|<span data-ttu-id="05350-112">팀 구성원 수 </span><span class="sxs-lookup"><span data-stu-id="05350-112">Number of members in a team</span></span> | <span data-ttu-id="05350-113">10,000</span><span class="sxs-lookup"><span data-stu-id="05350-113">10,000</span></span>       |
|<span data-ttu-id="05350-114">팀당 소유자 수</span><span class="sxs-lookup"><span data-stu-id="05350-114">Number of owners per team</span></span> | <span data-ttu-id="05350-115">100</span><span class="sxs-lookup"><span data-stu-id="05350-115">100</span></span>   |
|<span data-ttu-id="05350-116">테넌트에 허용되는 조직 전체 팀 수</span><span class="sxs-lookup"><span data-stu-id="05350-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="05350-117">5</span><span class="sxs-lookup"><span data-stu-id="05350-117">5</span></span>     |
|<span data-ttu-id="05350-118">[조직 전체 팀](create-an-org-wide-team.md)의 구성원 수</span><span class="sxs-lookup"><span data-stu-id="05350-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="05350-119">5,000</span><span class="sxs-lookup"><span data-stu-id="05350-119">5,000</span></span>       |
|<span data-ttu-id="05350-120">전역 관리자가 만들 수 있는 팀의 수</span><span class="sxs-lookup"><span data-stu-id="05350-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="05350-121">500,000</span><span class="sxs-lookup"><span data-stu-id="05350-121">500,000</span></span>   |
|<span data-ttu-id="05350-122">Microsoft 365 또는 Office 365 조직이 보유할 수 있는 팀 개수</span><span class="sxs-lookup"><span data-stu-id="05350-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="05350-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="05350-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="05350-124">팀당 채널 수</span><span class="sxs-lookup"><span data-stu-id="05350-124">Number of channels per team</span></span>    | <span data-ttu-id="05350-125">200(삭제된 채널 포함)&sup3;</span><span class="sxs-lookup"><span data-stu-id="05350-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="05350-126">팀당 비공개 채널 수</span><span class="sxs-lookup"><span data-stu-id="05350-126">Number of Private channels per team</span></span>    |<span data-ttu-id="05350-127">30</span><span class="sxs-lookup"><span data-stu-id="05350-127">30</span></span>|
|<span data-ttu-id="05350-128">비공개 채널 회원수</span><span class="sxs-lookup"><span data-stu-id="05350-128">Number of members in a Private channel</span></span>    |<span data-ttu-id="05350-129">250</span><span class="sxs-lookup"><span data-stu-id="05350-129">250</span></span>|
|<span data-ttu-id="05350-130">Office 365 그룹에서 팀으로 전환할 수 있는 최대 구성원 수</span><span class="sxs-lookup"><span data-stu-id="05350-130">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="05350-131">10,000</span><span class="sxs-lookup"><span data-stu-id="05350-131">10,000</span></span>|
|<span data-ttu-id="05350-132">채널 대화 게시 크기</span><span class="sxs-lookup"><span data-stu-id="05350-132">Channel conversation post size</span></span> | <span data-ttu-id="05350-133">게시물당 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="05350-133">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="05350-134"><sup>1</sup> Azure Active Directory의 모든 디렉터리 개체는 이 제한에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-134"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="05350-135">전역 관리자는 [응용 프로그램 사용 권한](https://docs.microsoft.com/graph/permissions-reference)을 사용하여 Microsoft Graph를 호출하는 앱과 마찬가지로 이 제한에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-135">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="05350-136"><sup>2</sup>이 제한에는 보관된 팀이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-136"><sup>2</sup> This limit includes archived teams.</span></span>

<span data-ttu-id="05350-137"><sup>3</sup>삭제된 채널은 30일 이내에 복원될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-137"><sup>3</sup> Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="05350-138">이 30일 동안에는 삭제된 채널이 팀당 200채널 한도에 계속 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-138">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="05350-139">30일 후에는 삭제된 채널과 해당 콘텐츠가 영구적으로 삭제되고 채널이 더 이상 팀당 200채널 한도에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-139">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="05350-140"><sup>4</sup> 28 KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션, 커넥터 숫자, 반응이 포함되기 때문에 대략적인 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="05350-140"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="05350-141">메시징</span><span class="sxs-lookup"><span data-stu-id="05350-141">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="05350-142">채팅</span><span class="sxs-lookup"><span data-stu-id="05350-142">Chat</span></span>

<span data-ttu-id="05350-143">Teams의 채팅 목록의 일부인 대화에 참여하는 사용자는 관리자가 채팅 대화를 검색할 수 있도록 Exchange Online(클라우드 기반) 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-143">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="05350-144">채팅 목록의 일부인 대화는 채팅 참가자의 클라우드 기반 사서함에 저장되기기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="05350-144">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="05350-145">채팅 참가자에게 Exchange Online 사서함이 없는 경우 관리자는 채팅 대화에 대한 보류 또는 저장을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-145">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="05350-146">예를 들어 Exchange 하이브리드 배포에서는 온-프레미스 사서함이 있는 사용자가 Teams 채팅 목록에 포함된 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-146">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="05350-147">하지만 이 경우에는 사용자에게 클라우드 기반 사서함이 없으므로 이 대화의 콘텐츠를 검색할 수 없고 보류 상태로 둘 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-147">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="05350-148">(자세한 내용은 [Exchange와 Microsoft Teams의 상호 작용 방식](exchange-teams-interact.md)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="05350-148">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="05350-149">Teams 채팅은 Microsoft Exchange 백 엔드에서 작동하므로 Exchange 메시징 제한은 Teams 내의 채팅 기능에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-149">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="05350-150">기능</span><span class="sxs-lookup"><span data-stu-id="05350-150">Feature</span></span>  | <span data-ttu-id="05350-151">최대 한도</span><span class="sxs-lookup"><span data-stu-id="05350-151">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="05350-152">비공개 채팅에 참가 중인 사용자 수<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="05350-152">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="05350-153">250</span><span class="sxs-lookup"><span data-stu-id="05350-153">250</span></span> |
|<span data-ttu-id="05350-154">채팅에서 영상 또는 음성 통화 중인 사용자 수</span><span class="sxs-lookup"><span data-stu-id="05350-154">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="05350-155">20</span><span class="sxs-lookup"><span data-stu-id="05350-155">20</span></span> |
|<span data-ttu-id="05350-156">첨부 파일 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="05350-156">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="05350-157">10</span><span class="sxs-lookup"><span data-stu-id="05350-157">10</span></span>     |
|<span data-ttu-id="05350-158">채팅 크기</span><span class="sxs-lookup"><span data-stu-id="05350-158">Chat size</span></span> | <span data-ttu-id="05350-159">게시물당 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="05350-159">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="05350-160"><sup>1</sup>채팅에 20명 이상의 사용자가 있는 경우 다음과 같은 채팅 기능이 꺼집니다. Outlook 자동 회신 및 Teams 상태 메시지, 입력 표시기, 비디오 및 오디오 통화, 공유, 읽음 확인.</span><span class="sxs-lookup"><span data-stu-id="05350-160"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span> <span data-ttu-id="05350-161">개인 그룹 채팅에 20명 이상의 구성원이 포함 된 경우에도 "배달 옵션 설정" 단추 (!)가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-161">The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="05350-162"><sup>2</sup>첨부 파일 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-162"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="05350-163"><sup>3</sup> 28 KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션, 반응이 포함되기 때문에 대략적인 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="05350-163"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="05350-164">채널 전자 메일 보내기 </span><span class="sxs-lookup"><span data-stu-id="05350-164">Emailing a channel</span></span>

 <span data-ttu-id="05350-165">사용자가 Teams의 채널에 전자 메일을 보내려면 채널 전자 메일 주소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-165">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="05350-166">전자 메일이 채널의 일부인 경우 누구나 답장을 보내 대화를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-166">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="05350-167">다음은 채널에 전자 메일을 보낼 때 적용되는 몇 가지 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="05350-167">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="05350-168">기능</span><span class="sxs-lookup"><span data-stu-id="05350-168">Feature</span></span>  | <span data-ttu-id="05350-169">최대 한도</span><span class="sxs-lookup"><span data-stu-id="05350-169">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="05350-170">메시지 크기<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="05350-170">Message size<sup>1<sup></span></span> | <span data-ttu-id="05350-171">24KB</span><span class="sxs-lookup"><span data-stu-id="05350-171">24 KB</span></span> |
|<span data-ttu-id="05350-172">첨부 파일 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="05350-172">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="05350-173">20</span><span class="sxs-lookup"><span data-stu-id="05350-173">20</span></span>     |
|<span data-ttu-id="05350-174">각 첨부 파일의 크기</span><span class="sxs-lookup"><span data-stu-id="05350-174">Size of each file attachment</span></span> | <span data-ttu-id="05350-175">10MB 미만</span><span class="sxs-lookup"><span data-stu-id="05350-175">Less than 10 MB</span></span> |
|<span data-ttu-id="05350-176">인라인 이미지 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="05350-176">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="05350-177">50</span><span class="sxs-lookup"><span data-stu-id="05350-177">50</span></span>   |

<span data-ttu-id="05350-178"><sup>1</sup>메시지가 이 한도를 초과하는 경우 미리 보기 메시지가 생성되고, 사용자에게 제공된 링크에서 원본 전자 메일을 다운로드하여 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-178"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="05350-179"><sup>2</sup>첨부 파일이나 이미지 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-179"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="05350-180">자세한 내용은 [Exchange Online 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05350-180">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="05350-181">모든 Microsoft 365 및 Office 365 라이선스에서 메시지 크기, 첨부 파일 및 인라인 이미지 제한이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-181">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="05350-182">채널 이름</span><span class="sxs-lookup"><span data-stu-id="05350-182">Channel names</span></span>

<span data-ttu-id="05350-183">채널 이름에는 다음 문자나 단어가 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-183">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="05350-184">문자</span><span class="sxs-lookup"><span data-stu-id="05350-184">Characters</span></span>     | <span data-ttu-id="05350-185">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="05350-185">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="05350-186">&#124; ' " , .</span><span class="sxs-lookup"><span data-stu-id="05350-186">&#124; ' " , .</span></span>        |
|<span data-ttu-id="05350-187">해당 범위에 있는 문자</span><span class="sxs-lookup"><span data-stu-id="05350-187">Characters in these ranges</span></span>    | <span data-ttu-id="05350-188">0~1F</span><span class="sxs-lookup"><span data-stu-id="05350-188">0 to 1F</span></span><br><span data-ttu-id="05350-189">80~9F</span><span class="sxs-lookup"><span data-stu-id="05350-189">80 to 9F</span></span>        |
|<span data-ttu-id="05350-190">단어</span><span class="sxs-lookup"><span data-stu-id="05350-190">Words</span></span>     | <span data-ttu-id="05350-191">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1~COM9, LPT1~LPT9, desktop.ini,  &#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="05350-191">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="05350-192">또한 채널 이름은 밑줄(_) 또는 마침표(.)로 시작하거나 마침표(.)로 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-192">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="05350-193">모임 및 통화</span><span class="sxs-lookup"><span data-stu-id="05350-193">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05350-194">**Microsoft 365 라이브 이벤트 한도가 늘어납니다**</span><span class="sxs-lookup"><span data-stu-id="05350-194">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="05350-195">**고객 지원을 돕기 위해 2021년 1월 1일까지 Teams, Stream 및 Yammer에서 주최하는 라이브 이벤트에 대해 임시 제한 증가를 연장합니다(** 포함).</span><span class="sxs-lookup"><span data-stu-id="05350-195">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for live events hosted in Teams, Stream, and Yammer, including**:</span></span>
>
>- <span data-ttu-id="05350-196">이벤트당 최대 20,000명의 참석자가 참석합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-196">Up to 20,000 attendees per event</span></span>
>- <span data-ttu-id="05350-197">Teams 테넌트당 최대 50개의 동시 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="05350-197">Up to 50 simultaneous events per Teams tenant</span></span>
>- <span data-ttu-id="05350-198">브로드캐스트당 최대 16시간입니다.</span><span class="sxs-lookup"><span data-stu-id="05350-198">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="05350-199">추가로 참가자 100,000명 이상의 라이브 이벤트는 Microsoft 365 지원 프로그램을 통해 계획 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-199">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program.</span></span> <span data-ttu-id="05350-200">팀에서 각 요청을 평가하고 사용자와 작업을 수행하여 사용 가능한 옵션을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-200">The team will assess each request and work with you to determine options that may be available.</span></span> <span data-ttu-id="05350-201">[자세한 정보](https://aka.ms/Stream/Blog/LiveEventOptions)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-201">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="05350-202">**2021년 1월 1일 이후 이러한 제한 증가가 필요한 고객은 [고급 통신 추가 기능](teams-add-on-licensing/advanced-communications.md)을 구입해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="05350-202">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>


|<span data-ttu-id="05350-203">기능</span><span class="sxs-lookup"><span data-stu-id="05350-203">Feature</span></span>     | <span data-ttu-id="05350-204">최대 한도</span><span class="sxs-lookup"><span data-stu-id="05350-204">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="05350-205">모임에 참가 중인 사용자 수(채팅 및 전화를 걸 수 있음)</span><span class="sxs-lookup"><span data-stu-id="05350-205">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="05350-206">300</span><span class="sxs-lookup"><span data-stu-id="05350-206">300</span></span> |
|<span data-ttu-id="05350-207">채팅에서 영상 또는 음성 통화 중인 사용자 수</span><span class="sxs-lookup"><span data-stu-id="05350-207">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="05350-208">20</span><span class="sxs-lookup"><span data-stu-id="05350-208">20</span></span> |
|<span data-ttu-id="05350-209">최대 PowerPoint 파일 크기</span><span class="sxs-lookup"><span data-stu-id="05350-209">Max PowerPoint File Size</span></span> | <span data-ttu-id="05350-210">2GB</span><span class="sxs-lookup"><span data-stu-id="05350-210">2GB</span></span>|
|<span data-ttu-id="05350-211">Teams는 Microsoft Stream에 업로드되지 않은 [모임 녹화](cloud-recording.md)를 보관하며 로컬로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-211">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="05350-212">20일</span><span class="sxs-lookup"><span data-stu-id="05350-212">20 days</span></span> |

>[!Note]
> <span data-ttu-id="05350-213">Microsoft Stream에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](tmr-meeting-recording-change.md)로의 변경은 단계별로 접근합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-213">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="05350-214">출시하면 이 환경에 대해 옵트인할 수 있고 11월에는 Stream을 계속 사용하려는 경우 옵트아웃해야 합니다. 2021년 초에는 모든 고객이 새 모임 녹음/녹화를 위해 비즈니스용 OneDrive와 SharePoint를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-214">At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

### <a name="meeting-expiration"></a><span data-ttu-id="05350-215">모임 만료</span><span class="sxs-lookup"><span data-stu-id="05350-215">Meeting expiration</span></span>

|<span data-ttu-id="05350-216">모임 유형</span><span class="sxs-lookup"><span data-stu-id="05350-216">Meeting type</span></span>  |<span data-ttu-id="05350-217">이만큼 시간이 지나면 모임이 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-217">Meeting expires after this much time</span></span>  |<span data-ttu-id="05350-218">모임을 시작하거나 업데이트할 때마다 만료 시간이 이 시간만큼 연장됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-218">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="05350-219">모임 시작</span><span class="sxs-lookup"><span data-stu-id="05350-219">Meet now</span></span>     |<span data-ttu-id="05350-220">시작 시간 + 8시간</span><span class="sxs-lookup"><span data-stu-id="05350-220">Start time + 8 hours</span></span>         |<span data-ttu-id="05350-221">해당 없음</span><span class="sxs-lookup"><span data-stu-id="05350-221">N/A</span></span>         |
|<span data-ttu-id="05350-222">정규(종료 시간 없음)</span><span class="sxs-lookup"><span data-stu-id="05350-222">Regular with no end time</span></span>     |<span data-ttu-id="05350-223">시작 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="05350-223">Start time + 60 days</span></span>         | <span data-ttu-id="05350-224">60일</span><span class="sxs-lookup"><span data-stu-id="05350-224">60 days</span></span>        |
|<span data-ttu-id="05350-225">정규(종료 시간 있음)</span><span class="sxs-lookup"><span data-stu-id="05350-225">Regular with end time</span></span>     |<span data-ttu-id="05350-226">종료 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="05350-226">End time + 60 days</span></span>         |<span data-ttu-id="05350-227">60일</span><span class="sxs-lookup"><span data-stu-id="05350-227">60 days</span></span>         |
|<span data-ttu-id="05350-228">되풀이(종료 시간 없음)</span><span class="sxs-lookup"><span data-stu-id="05350-228">Recurring with no end time</span></span>     |<span data-ttu-id="05350-229">시작 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="05350-229">Start time + 60 days</span></span>         |<span data-ttu-id="05350-230">60일</span><span class="sxs-lookup"><span data-stu-id="05350-230">60 days</span></span>         |
|<span data-ttu-id="05350-231">되풀이(종료 시간 있음)</span><span class="sxs-lookup"><span data-stu-id="05350-231">Recurring with end time</span></span>     |<span data-ttu-id="05350-232">마지막 발생 항목의 종료 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="05350-232">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="05350-233">60일</span><span class="sxs-lookup"><span data-stu-id="05350-233">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="05350-234">Microsoft Teams 모임의 제한 시간은 24시간입니다.</span><span class="sxs-lookup"><span data-stu-id="05350-234">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="05350-235">Teams 라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="05350-235">Teams live events</span></span>

|<span data-ttu-id="05350-236">기능</span><span class="sxs-lookup"><span data-stu-id="05350-236">Feature</span></span>     | <span data-ttu-id="05350-237">최대 한도</span><span class="sxs-lookup"><span data-stu-id="05350-237">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="05350-238">대상 그룹 크기</span><span class="sxs-lookup"><span data-stu-id="05350-238">Audience size</span></span> | <span data-ttu-id="05350-239">10,000 참석자</span><span class="sxs-lookup"><span data-stu-id="05350-239">10,000 attendees</span></span> |
|<span data-ttu-id="05350-240">이벤트 기간</span><span class="sxs-lookup"><span data-stu-id="05350-240">Duration of event</span></span> | <span data-ttu-id="05350-241">4시간</span><span class="sxs-lookup"><span data-stu-id="05350-241">4 hours</span></span> |
|<span data-ttu-id="05350-242">Microsoft 365 또는 Office 365 조직에서 실행되는 동시 발생 라이브 이벤트 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="05350-242">Concurrent live events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="05350-243">15</span><span class="sxs-lookup"><span data-stu-id="05350-243">15</span></span> |

<span data-ttu-id="05350-244"><sup>1</sup> 여러 라이브 이벤트를 원하는 대로 예약할 수 있지만, 한 번에 15개만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-244"><sup>1</sup> You can schedule as many live events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="05350-245">프로듀서가 라이브 이벤트에 참가하는 즉시 실행 중인 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-245">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="05350-246">16번째 라이브 이벤트에 참가하려고 시도하는 프로듀서는 오류 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-246">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="05350-247">라이브 이벤트와 Teams 라이브 이벤트와 Skype 모임 브로드캐스트 비교에 대한 자세한 내용은 [Teams 라이브 이벤트 및 Skype 모임 브로드캐스트](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05350-247">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05350-248">**Microsoft 365 라이브 이벤트 한도가 늘어납니다**</span><span class="sxs-lookup"><span data-stu-id="05350-248">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="05350-249">고객이 급변하는 커뮤니케이션 요구를 충족할 수 있도록 Teams, Stream, Yammer에서 주최하는 라이브 이벤트에 대해 2021년 1월 1일까지 한시적으로 기본값 제한을 상향 조정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-249">To help customers meet rapidly changing communication needs, we will temporarily raise default limits until January 1, 2021, for live events hosted in Teams, Stream, and Yammer.</span></span>
>
> - <span data-ttu-id="05350-250">참석자 제한: 이벤트는 최대 20,000명의 참석자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-250">Attendee limit: events can support up to 20,000 attendees</span></span>
> - <span data-ttu-id="05350-251">동시 이벤트: 한 테넌트에 걸쳐 동시에 50개의 이벤트 호스트가 가능</span><span class="sxs-lookup"><span data-stu-id="05350-251">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="05350-252">이벤트 기간: 이벤트 시간이 브로드캐스트 당 16시간으로 늘어났습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-252">Event duration: event length has been increased to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="05350-253">또한 Microsoft 라이브 이벤트 지원 프로그램을 통해 최대 100,000명의 참석자가 참여하는 라이브 이벤트를 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-253">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft live events assistance program.</span></span> <span data-ttu-id="05350-254">[자세한 정보](https://aka.ms/Stream/Blog/LiveEventOptions)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-254">[Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> <span data-ttu-id="05350-255">**2021년 1월 1일 이후 이러한 제한 증가가 필요한 고객은 [고급 통신 추가 기능](teams-add-on-licensing/advanced-communications.md)을 구입해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="05350-255">**After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](teams-add-on-licensing/advanced-communications.md).**</span></span>

## <a name="presence-in-outlook"></a><span data-ttu-id="05350-256">Outlook에서의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="05350-256">Presence in Outlook</span></span>

<span data-ttu-id="05350-257">Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-257">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="05350-258">팀의 현재 상태에 대해 자세히 알아보려면 [팀의 사용자 현재 상태](presence-admins.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05350-258">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="05350-259">저장소</span><span class="sxs-lookup"><span data-stu-id="05350-259">Storage</span></span>

<span data-ttu-id="05350-260">Microsoft Teams의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 채널은 기본 팀 사이트 문서 라이브러리 내에 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-260">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="05350-261">대화 내에서 공유된 파일은 문서 라이브러리에 자동으로 추가되고, SharePoint에 설정된 사용 권한 및 파일 보안 옵션은 Teams에서 자동으로 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-261">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="05350-262">각 [개인 채널](https://docs.microsoft.com/microsoftteams/private-channels)에는 고유한 SharePoint 사이트 모음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-262">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site collection.</span></span>

<span data-ttu-id="05350-263">테넌트에서 SharePoint Online을 사용하지 않는 경우 Microsoft Teams 사용자는 팀에서 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-263">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="05350-264">비즈니스용 OneDrive(SharePoint 라이선스에 연결됨)가 해당 기능에 필요하므로 개인 채팅 사용자도 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-264">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="05350-265">SharePoint Online 문서 라이브러리와 비즈니스용 OneDrive에 파일을 저장하면 테넌트 수준에서 구성된 모든 규정 준수 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="05350-265">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="05350-266">(자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive가 Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="05350-266">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="05350-267">Teams는 파일 공유를 위해 SharePoint Online 백 엔드에서 실행되므로 SharePoint 제한 사항은 팀 내의 파일 섹션에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="05350-267">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="05350-268">다음은 SharePoint Online에 적용할 수 있는 저장소 용량 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="05350-268">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="05350-269">기능</span><span class="sxs-lookup"><span data-stu-id="05350-269">Feature</span></span>                 |<span data-ttu-id="05350-270">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="05350-270">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="05350-271">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="05350-271">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="05350-272">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="05350-272">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="05350-273">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="05350-273">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="05350-274">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="05350-274">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="05350-275">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="05350-275">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="05350-276">저장소</span><span class="sxs-lookup"><span data-stu-id="05350-276">Storage</span></span>                 |<span data-ttu-id="05350-277">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="05350-277">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="05350-278">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="05350-278">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="05350-279">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="05350-279">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="05350-280">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="05350-280">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="05350-281">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="05350-281">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="05350-282">조직당 1TB</span><span class="sxs-lookup"><span data-stu-id="05350-282">1 TB per organization</span></span>           |
|<span data-ttu-id="05350-283">Teams 파일용 저장소</span><span class="sxs-lookup"><span data-stu-id="05350-283">Storage for Teams Files</span></span> |<span data-ttu-id="05350-284">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="05350-284">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="05350-285">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="05350-285">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="05350-286">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="05350-286">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="05350-287">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="05350-287">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="05350-288">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="05350-288">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="05350-289">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="05350-289">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="05350-290">파일 업로드 제한(파일당)</span><span class="sxs-lookup"><span data-stu-id="05350-290">File upload limit  (per file)</span></span>    |<span data-ttu-id="05350-291">100GB</span><span class="sxs-lookup"><span data-stu-id="05350-291">100 GB</span></span>    |<span data-ttu-id="05350-292">100GB</span><span class="sxs-lookup"><span data-stu-id="05350-292">100 GB</span></span>    |<span data-ttu-id="05350-293">100GB</span><span class="sxs-lookup"><span data-stu-id="05350-293">100 GB</span></span>    |<span data-ttu-id="05350-294">100GB</span><span class="sxs-lookup"><span data-stu-id="05350-294">100 GB</span></span>    |<span data-ttu-id="05350-295">100GB</span><span class="sxs-lookup"><span data-stu-id="05350-295">100 GB</span></span>    |<span data-ttu-id="05350-296">100GB</span><span class="sxs-lookup"><span data-stu-id="05350-296">100 GB</span></span>    |

<span data-ttu-id="05350-297">채널은 팀을 위해 만든 SharePoint Online 사이트 모음의 폴더에 의해 지원되므로 채널 내의 파일 탭은 속해 있는 팀의 저장소 용량 한도를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-297">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="05350-298">자세한 내용은 [SharePoint Online 제한](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05350-298">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="05350-299">수업 팀</span><span class="sxs-lookup"><span data-stu-id="05350-299">Class teams</span></span>

<span data-ttu-id="05350-300">교육용 Microsoft Teams는 강의실 교육과 같은 고유한 교육 시나리오를 위해 설계된 템플릿을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-300">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching.</span></span> <span data-ttu-id="05350-301">수업 팀을 포함한 팀 유형에 대한 자세한 내용은 [Microsoft Teams에서 공동 작업할 팀 유형 선택](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-301">More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="05350-302">수업 팀은 추가 앱이 포함된 템플릿 유형이며, 팀 구성원 수에는 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-302">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="05350-303">수업 팀을 사용하려면 [Office 365 Education 라이선스](https://www.microsoft.com/education/products/office)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-303">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="05350-304">수업 팀 제한은 다음 표에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-304">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="05350-305">기능</span><span class="sxs-lookup"><span data-stu-id="05350-305">Feature</span></span>  |<span data-ttu-id="05350-306">최대 한도</span><span class="sxs-lookup"><span data-stu-id="05350-306">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="05350-307">팀의 구성원 수</span><span class="sxs-lookup"><span data-stu-id="05350-307">Number of members in a team</span></span>    | <span data-ttu-id="05350-308">이 문서의 [Teams 및 채널](#teams-and-channels) 섹션을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-308">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="05350-309">수업 팀에서 할당을 사용할 구성원 수</span><span class="sxs-lookup"><span data-stu-id="05350-309">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="05350-310">200</span><span class="sxs-lookup"><span data-stu-id="05350-310">200</span></span>        |
|<span data-ttu-id="05350-311">수업 팀에서 OneNote 클래스 노트북을 사용할 구성원 수</span><span class="sxs-lookup"><span data-stu-id="05350-311">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="05350-312">200</span><span class="sxs-lookup"><span data-stu-id="05350-312">200</span></span>         |

<span data-ttu-id="05350-313">한 학급 팀이 200명 이상의 구성원을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-313">A class team can support more than 200 members.</span></span> <span data-ttu-id="05350-314">그러나 팀 내에서 Assignments 앱 또는 Class Notebook 앱을 사용하려는 경우 구성원 수를 위의 최대 제한 이하로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05350-314">However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>


## <a name="tags"></a><span data-ttu-id="05350-315">태그</span><span class="sxs-lookup"><span data-stu-id="05350-315">Tags</span></span>

|<span data-ttu-id="05350-316">기능</span><span class="sxs-lookup"><span data-stu-id="05350-316">Feature</span></span>  |<span data-ttu-id="05350-317">최대 한도</span><span class="sxs-lookup"><span data-stu-id="05350-317">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="05350-318">팀당 태그 수</span><span class="sxs-lookup"><span data-stu-id="05350-318">Number of tags per team</span></span>    | <span data-ttu-id="05350-319">100</span><span class="sxs-lookup"><span data-stu-id="05350-319">100</span></span>        |
|<span data-ttu-id="05350-320">팀당 제안된 기본 태그 수</span><span class="sxs-lookup"><span data-stu-id="05350-320">Number of suggested default tags per team</span></span>    | <span data-ttu-id="05350-321">25</span><span class="sxs-lookup"><span data-stu-id="05350-321">25</span></span>        |
|<span data-ttu-id="05350-322">태그에 할당되는 팀 구성원 수</span><span class="sxs-lookup"><span data-stu-id="05350-322">Number of team members assign to a tag</span></span>    |<span data-ttu-id="05350-323">100</span><span class="sxs-lookup"><span data-stu-id="05350-323">100</span></span>         |
|<span data-ttu-id="05350-324">사용자에게 할당되는 태그 수</span><span class="sxs-lookup"><span data-stu-id="05350-324">Number of tags assigned to a user</span></span>    |<span data-ttu-id="05350-325">25</span><span class="sxs-lookup"><span data-stu-id="05350-325">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="05350-326">연락처</span><span class="sxs-lookup"><span data-stu-id="05350-326">Contacts</span></span>

<span data-ttu-id="05350-327">Teams에서 사용하는 연락처:</span><span class="sxs-lookup"><span data-stu-id="05350-327">Teams uses these contacts:</span></span>

- <span data-ttu-id="05350-328">조직의 Active Directory에 있는 연락처</span><span class="sxs-lookup"><span data-stu-id="05350-328">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="05350-329">사용자의 Outlook 기본 폴더에 추가된 연락처</span><span class="sxs-lookup"><span data-stu-id="05350-329">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="05350-330">Teams 사용자는 조직의 Active Directory에 있는 모든 사용자와 커뮤니케이션할 수 있으며, 조직의 Active Directory에 있는 모든 사용자를 **채팅** > **연락처** 또는 **통화** > **연락처**로 이동하여 대화 상대 및 대화 상대 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-330">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="05350-331">팀 사용자는 조직 내의 Active Directory에 없는 사용자를 **통화** > **연락처**로 이동하여 연락처로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05350-331">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="05350-332">브라우저</span><span class="sxs-lookup"><span data-stu-id="05350-332">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="05350-333">운영 체제</span><span class="sxs-lookup"><span data-stu-id="05350-333">Operating systems</span></span>

<span data-ttu-id="05350-334">운영 체제 요구 사항에 대한 자세한 내용은 [Microsoft Teams용 클라이언트 다운로드](get-clients.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05350-334">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
