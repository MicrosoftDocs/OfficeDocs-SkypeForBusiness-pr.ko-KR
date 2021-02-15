---
title: Microsoft Teams의 제한 사항 및 사양
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: siunies
description: 이 문서에서는 Microsoft Teams에 적용되는 몇 가지 제한 사항, 사양 및 기타 요구 사항에 대해 설명합니다.
localization_priority: Priority
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- SPO_Content
- m365initiative-deployteams
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: daba993118348bbd4de2b1677e6a75cbce7c0ae9
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196792"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="482b5-103">Microsoft Teams의 제한 사항 및 사양</span><span class="sxs-lookup"><span data-stu-id="482b5-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="482b5-104">이 문서에서는 Microsoft Teams에 적용되는 몇 가지 제한 사항, 사양 및 기타 요구 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="482b5-105">팀 및 채널</span><span class="sxs-lookup"><span data-stu-id="482b5-105">Teams and channels</span></span>

|<span data-ttu-id="482b5-106">기능</span><span class="sxs-lookup"><span data-stu-id="482b5-106">Feature</span></span>    | <span data-ttu-id="482b5-107">최대 한도</span><span class="sxs-lookup"><span data-stu-id="482b5-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="482b5-108">사용자가 만들 수 있는 팀의 수</span><span class="sxs-lookup"><span data-stu-id="482b5-108">Number of teams a user can create</span></span> | <span data-ttu-id="482b5-109">250개체 제한 적용&sup1;</span><span class="sxs-lookup"><span data-stu-id="482b5-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="482b5-110">사용자가 구성원이 될 수 있는 그룹 수</span><span class="sxs-lookup"><span data-stu-id="482b5-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="482b5-111">1,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="482b5-111">1,000&sup2;</span></span>|
|<span data-ttu-id="482b5-112">팀 구성원 수 </span><span class="sxs-lookup"><span data-stu-id="482b5-112">Number of members in a team</span></span> | <span data-ttu-id="482b5-113">10,000<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="482b5-113">10,000<sup>6</sup></span></span>     |
|<span data-ttu-id="482b5-114">팀당 소유자 수</span><span class="sxs-lookup"><span data-stu-id="482b5-114">Number of owners per team</span></span> | <span data-ttu-id="482b5-115">100</span><span class="sxs-lookup"><span data-stu-id="482b5-115">100</span></span>   |
|<span data-ttu-id="482b5-116">테넌트에 허용되는 조직 전체 팀 수</span><span class="sxs-lookup"><span data-stu-id="482b5-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="482b5-117">5</span><span class="sxs-lookup"><span data-stu-id="482b5-117">5</span></span>     |
|<span data-ttu-id="482b5-118">[조직 전체 팀](create-an-org-wide-team.md)의 구성원 수</span><span class="sxs-lookup"><span data-stu-id="482b5-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="482b5-119">10,000</span><span class="sxs-lookup"><span data-stu-id="482b5-119">10,000</span></span>       |
|<span data-ttu-id="482b5-120">전역 관리자가 만들 수 있는 팀의 수</span><span class="sxs-lookup"><span data-stu-id="482b5-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="482b5-121">500,000</span><span class="sxs-lookup"><span data-stu-id="482b5-121">500,000</span></span>   |
|<span data-ttu-id="482b5-122">Microsoft 365 또는 Office 365 조직이 보유할 수 있는 팀 개수</span><span class="sxs-lookup"><span data-stu-id="482b5-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="482b5-123">500,000&sup3;</span><span class="sxs-lookup"><span data-stu-id="482b5-123">500,000&sup3;</span></span>     |
|<span data-ttu-id="482b5-124">팀당 채널 수</span><span class="sxs-lookup"><span data-stu-id="482b5-124">Number of channels per team</span></span>    | <span data-ttu-id="482b5-125">200(삭제된 채널 포함)&sup4;</span><span class="sxs-lookup"><span data-stu-id="482b5-125">200 (includes deleted channels)&sup4;</span></span>         |
|<span data-ttu-id="482b5-126">팀당 비공개 채널 수</span><span class="sxs-lookup"><span data-stu-id="482b5-126">Number of Private channels per team</span></span>    |<span data-ttu-id="482b5-127">30</span><span class="sxs-lookup"><span data-stu-id="482b5-127">30</span></span>| <span data-ttu-id="482b5-128">(삭제된 채널 포함)&sup4;</span><span class="sxs-lookup"><span data-stu-id="482b5-128">(includes deleted channels)&sup4;</span></span>
|<span data-ttu-id="482b5-129">비공개 채널 회원수</span><span class="sxs-lookup"><span data-stu-id="482b5-129">Number of members in a Private channel</span></span>    |<span data-ttu-id="482b5-130">250</span><span class="sxs-lookup"><span data-stu-id="482b5-130">250</span></span>|
|<span data-ttu-id="482b5-131">팀으로 가져올 수 있는 전자 메일 그룹, 보안 그룹 또는 Office 365 그룹의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-131">Maximum size of distribution list, security group or Office 365 group that can be imported in to a team</span></span>    |<span data-ttu-id="482b5-132">3,500</span><span class="sxs-lookup"><span data-stu-id="482b5-132">3,500</span></span>|
|<span data-ttu-id="482b5-133">Office 365 그룹에서 팀으로 전환할 수 있는 최대 구성원 수</span><span class="sxs-lookup"><span data-stu-id="482b5-133">Maximum number of members in an Office 365 group that can be converted to a team</span></span>    |<span data-ttu-id="482b5-134">10,000<sup>6</sup></span><span class="sxs-lookup"><span data-stu-id="482b5-134">10,000<sup>6</sup></span></span>     |
|<span data-ttu-id="482b5-135">채널 대화 게시 크기</span><span class="sxs-lookup"><span data-stu-id="482b5-135">Channel conversation post size</span></span> | <span data-ttu-id="482b5-136">게시물당 약 28KB<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="482b5-136">Approximately 28 KB per post<sup>5</sup></span></span> |

<span data-ttu-id="482b5-p101"><sup>1</sup> Azure Active Directory의 모든 디렉터리 개체는 이 제한에 포함됩니다. 전역 관리자는 [응용 프로그램 사용 권한](https://docs.microsoft.com/graph/permissions-reference)을 사용하여 Microsoft Graph를 호출하는 앱과 마찬가지로 이 제한에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-p101"><sup>1</sup> Any directory object in Azure Active Directory counts towards this limit. Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="482b5-139"><sup>2</sup> 이 제한에는 보관된 팀이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-139"><sup>2</sup> This limit includes archived teams.</span></span> 

<span data-ttu-id="482b5-140"><sup>3</sup> Microsoft 지원에 문의하여 테넌트에서의 Azure Active Directory 개체 수의 추가적 증가를 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-140"><sup>3</sup> To further increase the number of teams, you must contact Microsoft support and request further increase to the number of Azure Active Directory objects in your tenant.</span></span> <span data-ttu-id="482b5-141">증가는 실제 프로덕션 시나리오에만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-141">Increase is only made for real-life production scenarios.</span></span>

<span data-ttu-id="482b5-142"><sup>4</sup>삭제된 채널은 30일 이내에 복원될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-142"><sup>4</sup> Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="482b5-143">이 30일 동안에는 삭제된 채널이 200채널 혹은 팀 한도 딩 30개의 개인 채널로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-143">During these 30 days, a deleted channel continues to be counted towards the 200 channel or 30 private channel per team limit.</span></span> <span data-ttu-id="482b5-144">30일 후에는 삭제된 채널과 해당 콘텐츠가 영구적으로 삭제되고 채널이 더 이상 팀당 한도에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-144">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the per team limit.</span></span>

<span data-ttu-id="482b5-145"><sup>5</sup> 28 KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션, 커넥터 수, 반응이 포함되기 때문에 대략적인 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-145"><sup>5</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

<span data-ttu-id="482b5-146"><sup>6</sup> GCC Teams에서는 5,000명만 수용할 수 있고 GCCH/DoD Teams에서는 2,500명만 수용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-146"><sup>6</sup> Teams in GCC can only accommodate 5,000 members and teams in GCCH/DoD can only accommodate 2,500 members.</span></span>

## <a name="messaging"></a><span data-ttu-id="482b5-147">메시징</span><span class="sxs-lookup"><span data-stu-id="482b5-147">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="482b5-148">채팅</span><span class="sxs-lookup"><span data-stu-id="482b5-148">Chat</span></span>

<span data-ttu-id="482b5-p104">Teams의 채팅 목록의 일부인 대화에 참여하는 사용자는 관리자가 채팅 대화를 검색할 수 있도록 Exchange Online(클라우드 기반) 사서함이 있어야 합니다. 채팅 목록의 일부인 대화는 채팅 참가자의 클라우드 기반 사서함에 저장되기기 때문입니다. 채팅 참가자에게 Exchange Online 사서함이 없는 경우 관리자는 채팅 대화에 대한 보류 또는 저장을 수행할 수 없습니다. 예를 들어 Exchange 하이브리드 배포에서는 온-프레미스 사서함이 있는 사용자가 Teams 채팅 목록에 포함된 대화에 참여할 수 있습니다. 하지만 이 경우에는 사용자에게 클라우드 기반 사서함이 없으므로 이 대화의 콘텐츠를 검색할 수 없고 보류 상태로 둘 수 없습니다. (자세한 내용은 [Exchange와 Microsoft Teams의 상호 작용 방식](exchange-teams-interact.md)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="482b5-p104">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations. That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations. For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams. However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes. (For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="482b5-155">Teams 채팅은 Microsoft Exchange 백 엔드에서 작동하므로 Exchange 메시징 제한은 Teams 내의 채팅 기능에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-155">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="482b5-156">기능</span><span class="sxs-lookup"><span data-stu-id="482b5-156">Feature</span></span>  | <span data-ttu-id="482b5-157">최대 한도</span><span class="sxs-lookup"><span data-stu-id="482b5-157">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="482b5-158">비공개 채팅에 참가 중인 사용자 수<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="482b5-158">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="482b5-159">250<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="482b5-159">250<sup>2</sup></span></span> |
|<span data-ttu-id="482b5-160">채팅에서 영상 또는 음성 통화 중인 사용자 수</span><span class="sxs-lookup"><span data-stu-id="482b5-160">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="482b5-161">20</span><span class="sxs-lookup"><span data-stu-id="482b5-161">20</span></span> |
|<span data-ttu-id="482b5-162">첨부 파일 수<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="482b5-162">Number of file attachments<sup>3</sup></span></span>  |<span data-ttu-id="482b5-163">10</span><span class="sxs-lookup"><span data-stu-id="482b5-163">10</span></span>     |
|<span data-ttu-id="482b5-164">채팅 크기</span><span class="sxs-lookup"><span data-stu-id="482b5-164">Chat size</span></span> | <span data-ttu-id="482b5-165">게시물당 약 28KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="482b5-165">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="482b5-p105"><sup>1</sup>채팅에 20명 이상의 사용자가 있는 경우 다음과 같은 채팅 기능이 꺼집니다. Outlook 자동 회신 및 Teams 상태 메시지, 입력 표시기, 비디오 및 오디오 통화, 공유, 읽음 확인. 개인 그룹 채팅에 20명 이상의 구성원이 포함 된 경우에도 "배달 옵션 설정" 단추 (!)가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-p105"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts. The "Set Delivery Options" button (!) is also removed when private group chats contain more than 20 members.</span></span>

<span data-ttu-id="482b5-168"><sup>2</sup> 한 번에 200명의 구성원만 그룹 채팅에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-168"><sup>2</sup> Only 200 members at a time can be added to a group chat.</span></span> <span data-ttu-id="482b5-169">[자세한 내용은 이 문서를 참조하세요](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).</span><span class="sxs-lookup"><span data-stu-id="482b5-169">[See this article for more information](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/unable-send-message-group-chat).</span></span>

<span data-ttu-id="482b5-170"><sup>3</sup> 첨부 파일 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-170"><sup>3</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="482b5-171"><sup>4</sup> 28KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션 그리고 반응을 포함하기 때문에 대략적인 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-171"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="482b5-172">채널 전자 메일 보내기 </span><span class="sxs-lookup"><span data-stu-id="482b5-172">Emailing a channel</span></span>

 <span data-ttu-id="482b5-p107">사용자가 Teams의 채널에 전자 메일을 보내려면 채널 전자 메일 주소를 사용합니다. 전자 메일이 채널의 일부인 경우 누구나 답장을 보내 대화를 시작할 수 있습니다. 다음은 채널에 전자 메일을 보낼 때 적용되는 몇 가지 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-p107">If users want to send an email to a channel in Teams, they use the channel email address. When an email is part of a channel, anyone can reply to it to start a conversation. Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="482b5-176">기능</span><span class="sxs-lookup"><span data-stu-id="482b5-176">Feature</span></span>  | <span data-ttu-id="482b5-177">최대 한도</span><span class="sxs-lookup"><span data-stu-id="482b5-177">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="482b5-178">메시지 크기<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="482b5-178">Message size<sup>1<sup></span></span> | <span data-ttu-id="482b5-179">24KB</span><span class="sxs-lookup"><span data-stu-id="482b5-179">24 KB</span></span> |
|<span data-ttu-id="482b5-180">첨부 파일 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="482b5-180">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="482b5-181">20</span><span class="sxs-lookup"><span data-stu-id="482b5-181">20</span></span>     |
|<span data-ttu-id="482b5-182">각 첨부 파일의 크기</span><span class="sxs-lookup"><span data-stu-id="482b5-182">Size of each file attachment</span></span> | <span data-ttu-id="482b5-183">10MB 미만</span><span class="sxs-lookup"><span data-stu-id="482b5-183">Less than 10 MB</span></span> |
|<span data-ttu-id="482b5-184">인라인 이미지 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="482b5-184">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="482b5-185">50</span><span class="sxs-lookup"><span data-stu-id="482b5-185">50</span></span>   |

<span data-ttu-id="482b5-186"><sup>1</sup>메시지가 이 한도를 초과하는 경우 미리 보기 메시지가 생성되고, 사용자에게 제공된 링크에서 원본 전자 메일을 다운로드하여 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-186"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="482b5-187"><sup>2</sup>첨부 파일이나 이미지 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-187"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="482b5-188">자세한 내용은 [Exchange Online 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="482b5-188">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="482b5-p108">모든 Microsoft 365 및 Office 365 라이선스 간에 메시지 크기, 첨부 파일 및 인라인 이미지 제한이 동일합니다. Teams에서 Office GCC/GCCH/DOD 조직에 대해 전자 메일로 채널을 보내기는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-p108">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses. Emailing a channel is not available in Teams for Office GCC/GCCH/DOD organizations.</span></span>

## <a name="channel-names"></a><span data-ttu-id="482b5-191">채널 이름</span><span class="sxs-lookup"><span data-stu-id="482b5-191">Channel names</span></span>

<span data-ttu-id="482b5-192">채널 이름에는 다음 문자나 단어가 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-192">Channel names can't contain the following characters or words:</span></span>

|<span data-ttu-id="482b5-193">유형</span><span class="sxs-lookup"><span data-stu-id="482b5-193">Type</span></span>|<span data-ttu-id="482b5-194">예제</span><span class="sxs-lookup"><span data-stu-id="482b5-194">Example</span></span>|
|---------|---------|
|<span data-ttu-id="482b5-195">문자</span><span class="sxs-lookup"><span data-stu-id="482b5-195">Characters</span></span>     | <span data-ttu-id="482b5-p109">~ # % & \* { } + / \ : < > ? &#124; ' " , ..</span><span class="sxs-lookup"><span data-stu-id="482b5-p109">~ # % & \* { } + / \ : < > ? &#124; ' " , ..</span></span>        |
|<span data-ttu-id="482b5-198">이러한 범위에 있는 문자</span><span class="sxs-lookup"><span data-stu-id="482b5-198">Characters in these ranges</span></span>    | <span data-ttu-id="482b5-199">0~1F</span><span class="sxs-lookup"><span data-stu-id="482b5-199">0 to 1F</span></span><br><span data-ttu-id="482b5-200">80~9F</span><span class="sxs-lookup"><span data-stu-id="482b5-200">80 to 9F</span></span>        |
|<span data-ttu-id="482b5-201">단어</span><span class="sxs-lookup"><span data-stu-id="482b5-201">Words</span></span>     | <span data-ttu-id="482b5-202">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1~COM9, LPT1~LPT9, desktop.ini,  &#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="482b5-202">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="482b5-203">또한 채널 이름은 밑줄(_) 또는 마침표(.)로 시작하거나 마침표(.)로 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-203">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="482b5-204">모임 및 통화</span><span class="sxs-lookup"><span data-stu-id="482b5-204">Meetings and calls</span></span>

> [!IMPORTANT]
> <span data-ttu-id="482b5-205">**Microsoft 365 라이브 이벤트 한도가 늘어납니다**</span><span class="sxs-lookup"><span data-stu-id="482b5-205">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="482b5-206">**고객의 요구를 계속해서 지원하기 위해 2021년 6월 30일까지 다음을 포함하여 라이브 이벤트에 대한 임시 제한 증가 기간을 연장할 것입니다.**:</span><span class="sxs-lookup"><span data-stu-id="482b5-206">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="482b5-207">최대 20,000명의 참석자를 위한 이벤트 지원</span><span class="sxs-lookup"><span data-stu-id="482b5-207">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="482b5-208">한 테넌트에 걸쳐 동시에 50개의 이벤트가 호스트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-208">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="482b5-209">브로드캐스트당 16시간의 이벤트 시간</span><span class="sxs-lookup"><span data-stu-id="482b5-209">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="482b5-p110">또한 최대 100,000 참석자가 포함된 라이브 이벤트는 Microsoft 365 지원 프로그램을 통해 계획될 수 있습니다. 팀에서 각 요청을 평가하고 사용자와 작업을 수행하여 사용 가능한 옵션을 결정합니다. [자세한 정보](https://aka.ms/Stream/Blog/LiveEventOptions).</span><span class="sxs-lookup"><span data-stu-id="482b5-p110">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span>

|<span data-ttu-id="482b5-213">기능</span><span class="sxs-lookup"><span data-stu-id="482b5-213">Feature</span></span>     | <span data-ttu-id="482b5-214">최대 한도</span><span class="sxs-lookup"><span data-stu-id="482b5-214">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="482b5-215">모임에 참가 중인 사용자 수(채팅 및 전화를 걸 수 있음)</span><span class="sxs-lookup"><span data-stu-id="482b5-215">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="482b5-216">300. **보기 전용** 에서는 주최자가 E3/E5/A3/A5 SKU에 대한 라이선스를 보유한 모임에 최대 10,000명의 청취자만 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-216">300. **View-only** allows for up to 10,000 listen-only participants to join a meeting in which the organizer has a license for E3/E5/A3/A5 SKU.</span></span><br><span data-ttu-id="482b5-217">**참고:** 정부 기관용 Teams(GCC, GCC High, DoD)의 경우, 제한은 여전히 250입니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-217">**Note:** For Teams for Government (GCC, GCC High, DoD), the limit is still 250.</span></span> <span data-ttu-id="482b5-218">정부 클라우드 제한이 250에서 300으로 늘어나고 모임 오버플로를 지원하면 이 문서를 업데이트할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-218">We'll update this article when the government cloud limit increases from 250 to 300 and supports meeting overflow.</span></span> <span data-ttu-id="482b5-219">[보기 전용 환경](view-only-meeting-experience.md)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="482b5-219">Learn more about the [View-only experience](view-only-meeting-experience.md).</span></span>|
|<span data-ttu-id="482b5-220">채팅에서 영상 또는 음성 통화 중인 사용자 수</span><span class="sxs-lookup"><span data-stu-id="482b5-220">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="482b5-221">20</span><span class="sxs-lookup"><span data-stu-id="482b5-221">20</span></span> |
|<span data-ttu-id="482b5-222">최대 PowerPoint 파일 크기</span><span class="sxs-lookup"><span data-stu-id="482b5-222">Max PowerPoint File Size</span></span> | <span data-ttu-id="482b5-223">2GB</span><span class="sxs-lookup"><span data-stu-id="482b5-223">2GB</span></span>|
|<span data-ttu-id="482b5-224">Teams는 Microsoft Stream에 업로드되지 않은 [모임 녹화](cloud-recording.md)를 보관하며 로컬로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-224">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="482b5-225">20일</span><span class="sxs-lookup"><span data-stu-id="482b5-225">20 days</span></span> |

### <a name="meeting-expiration"></a><span data-ttu-id="482b5-226">모임 만료</span><span class="sxs-lookup"><span data-stu-id="482b5-226">Meeting expiration</span></span>

|<span data-ttu-id="482b5-227">모임 유형</span><span class="sxs-lookup"><span data-stu-id="482b5-227">Meeting type</span></span>  |<span data-ttu-id="482b5-228">이만큼 시간이 지나면 모임이 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-228">Meeting expires after this much time</span></span>  |<span data-ttu-id="482b5-229">모임을 시작하거나 업데이트할 때마다 만료 시간이 이 시간만큼 연장됩니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-229">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="482b5-230">모임 시작</span><span class="sxs-lookup"><span data-stu-id="482b5-230">Meet now</span></span>     |<span data-ttu-id="482b5-231">시작 시간 + 8시간</span><span class="sxs-lookup"><span data-stu-id="482b5-231">Start time + 8 hours</span></span>         |<span data-ttu-id="482b5-232">해당 없음</span><span class="sxs-lookup"><span data-stu-id="482b5-232">N/A</span></span>         |
|<span data-ttu-id="482b5-233">정규(종료 시간 없음)</span><span class="sxs-lookup"><span data-stu-id="482b5-233">Regular with no end time</span></span>     |<span data-ttu-id="482b5-234">시작 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="482b5-234">Start time + 60 days</span></span>         | <span data-ttu-id="482b5-235">60일</span><span class="sxs-lookup"><span data-stu-id="482b5-235">60 days</span></span>        |
|<span data-ttu-id="482b5-236">정규(종료 시간 있음)</span><span class="sxs-lookup"><span data-stu-id="482b5-236">Regular with end time</span></span>     |<span data-ttu-id="482b5-237">종료 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="482b5-237">End time + 60 days</span></span>         |<span data-ttu-id="482b5-238">60일</span><span class="sxs-lookup"><span data-stu-id="482b5-238">60 days</span></span>         |
|<span data-ttu-id="482b5-239">되풀이(종료 시간 없음)</span><span class="sxs-lookup"><span data-stu-id="482b5-239">Recurring with no end time</span></span>     |<span data-ttu-id="482b5-240">시작 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="482b5-240">Start time + 60 days</span></span>         |<span data-ttu-id="482b5-241">60일</span><span class="sxs-lookup"><span data-stu-id="482b5-241">60 days</span></span>         |
|<span data-ttu-id="482b5-242">되풀이(종료 시간 있음)</span><span class="sxs-lookup"><span data-stu-id="482b5-242">Recurring with end time</span></span>     |<span data-ttu-id="482b5-243">마지막 발생 항목의 종료 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="482b5-243">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="482b5-244">60일</span><span class="sxs-lookup"><span data-stu-id="482b5-244">60 days</span></span>         |

> [!NOTE]
> <span data-ttu-id="482b5-245">Microsoft Teams 모임의 제한 시간은 24시간입니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-245">Microsoft Teams meetings have a time limit of 24 hours.</span></span>

## <a name="teams-live-events"></a><span data-ttu-id="482b5-246">Teams 라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="482b5-246">Teams Live Events</span></span>

|<span data-ttu-id="482b5-247">기능</span><span class="sxs-lookup"><span data-stu-id="482b5-247">Feature</span></span>     | <span data-ttu-id="482b5-248">최대 한도</span><span class="sxs-lookup"><span data-stu-id="482b5-248">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="482b5-249">대상 그룹 크기</span><span class="sxs-lookup"><span data-stu-id="482b5-249">Audience size</span></span> | <span data-ttu-id="482b5-250">10,000 참석자</span><span class="sxs-lookup"><span data-stu-id="482b5-250">10,000 attendees</span></span> |
|<span data-ttu-id="482b5-251">이벤트 기간</span><span class="sxs-lookup"><span data-stu-id="482b5-251">Duration of event</span></span> | <span data-ttu-id="482b5-252">4시간</span><span class="sxs-lookup"><span data-stu-id="482b5-252">4 hours</span></span> |
|<span data-ttu-id="482b5-253">Microsoft 365 또는 Office 365 조직에서 실행되는 동시 발생 라이브 이벤트 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="482b5-253">Concurrent Live Events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="482b5-254">15</span><span class="sxs-lookup"><span data-stu-id="482b5-254">15</span></span> |

<span data-ttu-id="482b5-p112"><sup>1</sup> 여러 라이브 이벤트를 원하는 대로 예약할 수 있지만, 한 번에 15개만 실행할 수 있습니다. 프로듀서가 라이브 이벤트에 참가하는 즉시 실행 중인 것으로 간주합니다. 16번째 라이브 이벤트에 참가하려고 시도하는 프로듀서는 오류 메시지를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-p112"><sup>1</sup> You can schedule as many Live Events as you want, but you can only run 15 at a time. As soon as the producer joins a live event, it's considered to be running. The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="482b5-p113">라이브 이벤트 및 Teams 라이브 이벤트와 Skype 모임 브로드캐스트 비교에 대한 자세한 내용은 [Teams 라이브 이벤트 및 Skype 모임 브로드캐스트](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)를 참조하세요. 또한 [Teams 라이브 이벤트 예약](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="482b5-p113">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast). See also [Schedule a Teams live event](https://support.microsoft.com/office/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="482b5-260">**Microsoft 365 라이브 이벤트 한도 증가**</span><span class="sxs-lookup"><span data-stu-id="482b5-260">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="482b5-261">**고객의 요구를 계속해서 지원하기 위해 2021년 6월 30일까지 다음을 포함하여 라이브 이벤트에 대한 임시 제한 증가 기간을 연장할 것입니다.**:</span><span class="sxs-lookup"><span data-stu-id="482b5-261">**To continue supporting our customers' needs, through June 30, 2021, we will extend temporary limit increases for live events, including**:</span></span>
>
>- <span data-ttu-id="482b5-262">최대 20,000명의 참석자를 위한 이벤트 지원</span><span class="sxs-lookup"><span data-stu-id="482b5-262">Event support for up to 20,000 attendees</span></span>
>- <span data-ttu-id="482b5-263">한 테넌트에 걸쳐 동시에 50개의 이벤트가 호스트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-263">50 events can be hosted simultaneously across a tenant</span></span>
>- <span data-ttu-id="482b5-264">브로드캐스트당 16시간의 이벤트 시간</span><span class="sxs-lookup"><span data-stu-id="482b5-264">Event duration of 16 hours per broadcast</span></span>
>
> <span data-ttu-id="482b5-p114">또한 최대 100,000 참석자가 포함된 라이브 이벤트는 Microsoft 365 지원 프로그램을 통해 계획될 수 있습니다. 팀에서 각 요청을 평가하고 사용자와 작업을 수행하여 사용 가능한 옵션을 결정합니다. [자세한 정보](https://aka.ms/Stream/Blog/LiveEventOptions).</span><span class="sxs-lookup"><span data-stu-id="482b5-p114">Additionally, Live Events with up to 100,000 attendees can be planned through the Microsoft 365 assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).</span></span> 

## <a name="presence-in-outlook"></a><span data-ttu-id="482b5-268">Outlook에서의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="482b5-268">Presence in Outlook</span></span>

<span data-ttu-id="482b5-p115">Outlook에서의 Teams 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다. Teams의 현재 상태에 대해 자세히 알아보려면 [Teams에서 사용자 현재 상태](presence-admins.md)를 참조하세요..</span><span class="sxs-lookup"><span data-stu-id="482b5-p115">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later. To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="482b5-271">저장소</span><span class="sxs-lookup"><span data-stu-id="482b5-271">Storage</span></span>

<span data-ttu-id="482b5-p116">Microsoft Teams의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 채널은 기본 팀 사이트 문서 라이브러리 내에 폴더가 있습니다. 대화 내에서 공유된 파일은 문서 라이브러리에 자동으로 추가되고, SharePoint에서 설정된 사용 권한 및 파일 보안 옵션은 Teams 내에서 자동으로 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-p116">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library. Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="482b5-274">각 [개인 채널](https://docs.microsoft.com/microsoftteams/private-channels)에는 고유한 SharePoint 사이트 모음(이전에 “사이트 모음”이라 불림)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-274">Each [private channel](https://docs.microsoft.com/microsoftteams/private-channels) has its own SharePoint site (previously called "site collection").</span></span>

<span data-ttu-id="482b5-p117">테넌트에서 SharePoint Online을 사용하도록 설정하지 않은 경우, Microsoft Teams 사용자는 팀에서 파일을 항상 공유할 수 없습니다. 비즈니스용 OneDrive(SharePoint 라이선스에 연결됨)가 해당 기능에 필요하므로 개인 채팅 사용자도 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-p117">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams. Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="482b5-p118">SharePoint Online 문서 라이브러리와 비즈니스용 OneDrive에 파일을 저장하면, 테넌트 수준에서 구성된 모든 규정 준수 규칙을 따릅니다. (자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)을 참조하세요.) </span><span class="sxs-lookup"><span data-stu-id="482b5-p118">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed. (For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="482b5-p119">Teams는 파일 공유를 위해 SharePoint Online 백 엔드에서 실행되므로 SharePoint 제한 사항은 Teams 내의 파일 섹션에 적용됩니다. 다음은 SharePoint Online에 적용되는 저장소 용량 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-p119">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team. Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="482b5-281">기능</span><span class="sxs-lookup"><span data-stu-id="482b5-281">Feature</span></span>                 |<span data-ttu-id="482b5-282">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="482b5-282">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="482b5-283">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="482b5-283">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="482b5-284">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="482b5-284">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="482b5-285">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="482b5-285">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="482b5-286">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="482b5-286">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="482b5-287">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="482b5-287">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="482b5-288">저장소</span><span class="sxs-lookup"><span data-stu-id="482b5-288">Storage</span></span>                 |<span data-ttu-id="482b5-289">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="482b5-289">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="482b5-290">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="482b5-290">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="482b5-291">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="482b5-291">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="482b5-292">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="482b5-292">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="482b5-293">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="482b5-293">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="482b5-294">조직당 1TB</span><span class="sxs-lookup"><span data-stu-id="482b5-294">1 TB per organization</span></span>           |
|<span data-ttu-id="482b5-295">Teams 파일용 저장소</span><span class="sxs-lookup"><span data-stu-id="482b5-295">Storage for Teams Files</span></span> |<span data-ttu-id="482b5-296">사이트 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="482b5-296">Up to 25 TB per site or group</span></span> |<span data-ttu-id="482b5-297">사이트 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="482b5-297">Up to 25 TB per site or group</span></span> |<span data-ttu-id="482b5-298">사이트 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="482b5-298">Up to 25 TB per site or group</span></span> |<span data-ttu-id="482b5-299">사이트 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="482b5-299">Up to 25 TB per site or group</span></span> |<span data-ttu-id="482b5-300">사이트 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="482b5-300">Up to 25 TB per site or group</span></span> |<span data-ttu-id="482b5-301">사이트 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="482b5-301">Up to 25 TB per site or group</span></span> |
|<span data-ttu-id="482b5-302">파일 업로드 제한(파일당)</span><span class="sxs-lookup"><span data-stu-id="482b5-302">File upload limit  (per file)</span></span>    |<span data-ttu-id="482b5-303">100GB</span><span class="sxs-lookup"><span data-stu-id="482b5-303">100 GB</span></span>    |<span data-ttu-id="482b5-304">100GB</span><span class="sxs-lookup"><span data-stu-id="482b5-304">100 GB</span></span>    |<span data-ttu-id="482b5-305">100GB</span><span class="sxs-lookup"><span data-stu-id="482b5-305">100 GB</span></span>    |<span data-ttu-id="482b5-306">100GB</span><span class="sxs-lookup"><span data-stu-id="482b5-306">100 GB</span></span>    |<span data-ttu-id="482b5-307">100GB</span><span class="sxs-lookup"><span data-stu-id="482b5-307">100 GB</span></span>    |<span data-ttu-id="482b5-308">100GB</span><span class="sxs-lookup"><span data-stu-id="482b5-308">100 GB</span></span>    |

<span data-ttu-id="482b5-309">채널은 팀에 대해 생성된 SharePoint Online 사이트 모음(이전에 “사이트 모음”이라 불림) 내의 폴더로 백업되므로 채널 내의 파일 탭은 자신이 속한 팀의 저장소 제한을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-309">Channels are backed by folders within the SharePoint Online site (previously called "site collection") created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="482b5-310">자세한 내용은 [SharePoint Online 제한](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="482b5-310">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="class-teams"></a><span data-ttu-id="482b5-311">수업 팀</span><span class="sxs-lookup"><span data-stu-id="482b5-311">Class teams</span></span>

<span data-ttu-id="482b5-p120">교육용 Microsoft Teams는 교실 수업과 같은 고유한 교육 시나리오를 위해 설계된 템플릿을 제공합니다. 수업 팀을 포함한 팀 유형에 대한 자세한 내용은 [Microsoft Teams에서 공동 작업할 팀 유형 선택](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-p120">Microsoft Teams for Education provides templates designed for unique education scenarios, such as classroom teaching. More information about team types, including class teams, is available in [Choose a team type to collaborate in Microsoft Teams](https://support.microsoft.com/office/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67).</span></span>

<span data-ttu-id="482b5-314">한 개의 수업 팀은 추가 앱이 포함된 템플릿 유형이며, 팀 구성원의 수에 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-314">A class team is a template type with additional apps included, and with limits separate to the number of team members.</span></span>

> [!NOTE]
> <span data-ttu-id="482b5-315">수업 팀을 사용하려면 [Office 365 Education 라이선스](https://www.microsoft.com/education/products/office)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-315">Using class teams requires an [Office 365 Education license](https://www.microsoft.com/education/products/office).</span></span>

<span data-ttu-id="482b5-316">수업 팀 제한은 다음 표에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-316">Limits for class teams are listed in the following table:</span></span>

|<span data-ttu-id="482b5-317">기능</span><span class="sxs-lookup"><span data-stu-id="482b5-317">Feature</span></span>  |<span data-ttu-id="482b5-318">최대 한도</span><span class="sxs-lookup"><span data-stu-id="482b5-318">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="482b5-319">팀의 구성원 수</span><span class="sxs-lookup"><span data-stu-id="482b5-319">Number of members in a team</span></span>    | <span data-ttu-id="482b5-320">이 문서의 [Teams 및 채널](#teams-and-channels) 섹션을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-320">See the [Teams and channels](#teams-and-channels) section of this article</span></span>        |
|<span data-ttu-id="482b5-321">수업 팀에서 할당을 사용할 구성원 수</span><span class="sxs-lookup"><span data-stu-id="482b5-321">Number of members to use Assignments in a class team</span></span>    | <span data-ttu-id="482b5-322">200</span><span class="sxs-lookup"><span data-stu-id="482b5-322">200</span></span>        |
|<span data-ttu-id="482b5-323">수업 팀에서 OneNote 클래스 노트북을 사용할 구성원 수</span><span class="sxs-lookup"><span data-stu-id="482b5-323">Number of members to use a OneNote Class Notebook in a class team</span></span>     |<span data-ttu-id="482b5-324">200</span><span class="sxs-lookup"><span data-stu-id="482b5-324">200</span></span>         |

<span data-ttu-id="482b5-p121">한 개의 수업 팀은 200명 이상의 구성원을 지원할 수 있습니다. 그러나 팀 내에서 과제 앱 또는 수업용 전자 필기장 앱을 사용하려는 경우, 구성원 수를 위의 최대 한도 이하로 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-p121">A class team can support more than 200 members. However, if you plan to use either the Assignments app or Class Notebook app within your team, you will need to keep the number of members below the maximum limits above.</span></span>

## <a name="tags"></a><span data-ttu-id="482b5-327">태그</span><span class="sxs-lookup"><span data-stu-id="482b5-327">Tags</span></span>

|<span data-ttu-id="482b5-328">기능</span><span class="sxs-lookup"><span data-stu-id="482b5-328">Feature</span></span>  |<span data-ttu-id="482b5-329">최대 한도</span><span class="sxs-lookup"><span data-stu-id="482b5-329">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="482b5-330">팀당 태그 수</span><span class="sxs-lookup"><span data-stu-id="482b5-330">Number of tags per team</span></span>    | <span data-ttu-id="482b5-331">100</span><span class="sxs-lookup"><span data-stu-id="482b5-331">100</span></span>        |
|<span data-ttu-id="482b5-332">팀당 제안된 기본 태그 수</span><span class="sxs-lookup"><span data-stu-id="482b5-332">Number of suggested default tags per team</span></span>    | <span data-ttu-id="482b5-333">25</span><span class="sxs-lookup"><span data-stu-id="482b5-333">25</span></span>        |
|<span data-ttu-id="482b5-334">태그에 할당되는 팀 구성원 수</span><span class="sxs-lookup"><span data-stu-id="482b5-334">Number of team members assign to a tag</span></span>    |<span data-ttu-id="482b5-335">100</span><span class="sxs-lookup"><span data-stu-id="482b5-335">100</span></span>         |
|<span data-ttu-id="482b5-336">사용자에게 할당되는 태그 수</span><span class="sxs-lookup"><span data-stu-id="482b5-336">Number of tags assigned to a user</span></span>    |<span data-ttu-id="482b5-337">25</span><span class="sxs-lookup"><span data-stu-id="482b5-337">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="482b5-338">연락처</span><span class="sxs-lookup"><span data-stu-id="482b5-338">Contacts</span></span>

<span data-ttu-id="482b5-339">Teams에서 사용하는 연락처:</span><span class="sxs-lookup"><span data-stu-id="482b5-339">Teams uses these contacts:</span></span>

- <span data-ttu-id="482b5-340">조직의 Active Directory에 있는 연락처</span><span class="sxs-lookup"><span data-stu-id="482b5-340">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="482b5-341">사용자의 Outlook 기본 폴더에 추가된 연락처</span><span class="sxs-lookup"><span data-stu-id="482b5-341">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="482b5-342">Teams 사용자는 조직의 Active Directory에 있는 모든 사용자와 커뮤니케이션할 수 있으며, 조직의 Active Directory에 있는 모든 사용자를 **채팅** > **연락처** 또는 **통화** > **연락처** 로 이동하여 대화 상대 및 대화 상대 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-342">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="482b5-343">팀 사용자는 조직 내의 Active Directory에 없는 사용자를 **통화** > **연락처** 로 이동하여 연락처로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="482b5-343">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="482b5-344">브라우저</span><span class="sxs-lookup"><span data-stu-id="482b5-344">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="482b5-345">운영 체제</span><span class="sxs-lookup"><span data-stu-id="482b5-345">Operating systems</span></span>

<span data-ttu-id="482b5-346">운영 체제 요구 사항에 대한 자세한 내용은 [Microsoft Teams용 클라이언트 다운로드](get-clients.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="482b5-346">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
