---
title: Microsoft Teams의 제한 사항 및 사양
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: e9b4b5e9d862596e91bcb6d30112e5f70a9c8263
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637647"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="c5725-103">Microsoft Teams의 제한 사항 및 사양</span><span class="sxs-lookup"><span data-stu-id="c5725-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="c5725-104">이 문서에서는 Microsoft Teams에 적용되는 몇 가지 제한 사항, 사양 및 기타 요구 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="c5725-105">팀 및 채널</span><span class="sxs-lookup"><span data-stu-id="c5725-105">Teams and channels</span></span>

|<span data-ttu-id="c5725-106">기능</span><span class="sxs-lookup"><span data-stu-id="c5725-106">Feature</span></span>    | <span data-ttu-id="c5725-107">최대 한도</span><span class="sxs-lookup"><span data-stu-id="c5725-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="c5725-108">사용자가 만들 수 있는 팀의 수</span><span class="sxs-lookup"><span data-stu-id="c5725-108">Number of teams a user can create</span></span> | <span data-ttu-id="c5725-109">250개체 제한 적용&sup1;</span><span class="sxs-lookup"><span data-stu-id="c5725-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="c5725-110">사용자가 구성원이 될 수 있는 그룹 수</span><span class="sxs-lookup"><span data-stu-id="c5725-110">Number of teams a user can be a member of</span></span>|<span data-ttu-id="c5725-111">1,000</span><span class="sxs-lookup"><span data-stu-id="c5725-111">1,000</span></span>|
|<span data-ttu-id="c5725-112">팀 구성원 수 </span><span class="sxs-lookup"><span data-stu-id="c5725-112">Number of members in a team</span></span> | <span data-ttu-id="c5725-113">10,000</span><span class="sxs-lookup"><span data-stu-id="c5725-113">10,000</span></span>       |
|<span data-ttu-id="c5725-114">팀당 소유자 수</span><span class="sxs-lookup"><span data-stu-id="c5725-114">Number of owners per team</span></span> | <span data-ttu-id="c5725-115">100</span><span class="sxs-lookup"><span data-stu-id="c5725-115">100</span></span>   |
|<span data-ttu-id="c5725-116">테넌트에 허용되는 조직 전체 팀 수</span><span class="sxs-lookup"><span data-stu-id="c5725-116">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="c5725-117">5</span><span class="sxs-lookup"><span data-stu-id="c5725-117">5</span></span>     |
|<span data-ttu-id="c5725-118">[조직 전체 팀](create-an-org-wide-team.md)의 구성원 수</span><span class="sxs-lookup"><span data-stu-id="c5725-118">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="c5725-119">5,000</span><span class="sxs-lookup"><span data-stu-id="c5725-119">5,000</span></span>       |
|<span data-ttu-id="c5725-120">전역 관리자가 만들 수 있는 팀의 수</span><span class="sxs-lookup"><span data-stu-id="c5725-120">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="c5725-121">500,000</span><span class="sxs-lookup"><span data-stu-id="c5725-121">500,000</span></span>   |
|<span data-ttu-id="c5725-122">Microsoft 365 또는 Office 365 조직이 보유할 수 있는 팀 개수</span><span class="sxs-lookup"><span data-stu-id="c5725-122">Number of teams a Microsoft 365 or Office 365 organization can have</span></span>    | <span data-ttu-id="c5725-123">500,000&sup2;</span><span class="sxs-lookup"><span data-stu-id="c5725-123">500,000&sup2;</span></span>     |
|<span data-ttu-id="c5725-124">팀당 채널 수</span><span class="sxs-lookup"><span data-stu-id="c5725-124">Number of channels per team</span></span>    | <span data-ttu-id="c5725-125">200(삭제된 채널 포함)&sup3;</span><span class="sxs-lookup"><span data-stu-id="c5725-125">200 (includes deleted channels)&sup3;</span></span>         |
|<span data-ttu-id="c5725-126">팀당 비공개 채널 수</span><span class="sxs-lookup"><span data-stu-id="c5725-126">Number of Private channels per team</span></span>    |<span data-ttu-id="c5725-127">30</span><span class="sxs-lookup"><span data-stu-id="c5725-127">30</span></span>|
|<span data-ttu-id="c5725-128">비공개 채널 회원수</span><span class="sxs-lookup"><span data-stu-id="c5725-128">Number of members in a Private channel</span></span>    |<span data-ttu-id="c5725-129">250</span><span class="sxs-lookup"><span data-stu-id="c5725-129">250</span></span>|
|<span data-ttu-id="c5725-130">채널 대화 게시 크기</span><span class="sxs-lookup"><span data-stu-id="c5725-130">Channel conversation post size</span></span> | <span data-ttu-id="c5725-131">게시물당 28 KB<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="c5725-131">Approximately 28 KB per post<sup>4</sup></span></span> |

<span data-ttu-id="c5725-132">&sup1;Azure Active Directory의 모든 디렉터리 개체는 이 제한에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-132">&sup1; Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="c5725-133">전역 관리자는 [응용 프로그램 사용 권한](https://docs.microsoft.com/graph/permissions-reference)을 사용하여 Microsoft Graph를 호출하는 앱과 마찬가지로 이 제한에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-133">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="c5725-134">&sup2;이 제한에는 보관된 팀이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-134">&sup2; This limit includes archived teams.</span></span>

<span data-ttu-id="c5725-135">&sup3;삭제된 채널은 30일 이내에 복원될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-135">&sup3; Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="c5725-136">이 30일 동안에는 삭제된 채널이 팀당 200채널 한도에 계속 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-136">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="c5725-137">30일 후에는 삭제된 채널과 해당 콘텐츠가 영구적으로 삭제되고 채널이 더 이상 팀당 200채널 한도에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-137">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

<span data-ttu-id="c5725-138"><sup>4</sup> 28 KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션, 커넥터 숫자, 반응이 포함되기 때문에 대략적인 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-138"><sup>4</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, number of connectors, and reactions.</span></span>

## <a name="messaging"></a><span data-ttu-id="c5725-139">메시징</span><span class="sxs-lookup"><span data-stu-id="c5725-139">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="c5725-140">채팅</span><span class="sxs-lookup"><span data-stu-id="c5725-140">Chat</span></span>

<span data-ttu-id="c5725-141">Teams의 채팅 목록의 일부인 대화에 참여하는 사용자는 관리자가 채팅 대화를 검색할 수 있도록 Exchange Online(클라우드 기반) 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-141">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="c5725-142">채팅 목록의 일부인 대화는 채팅 참가자의 클라우드 기반 사서함에 저장되기기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-142">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="c5725-143">채팅 참가자에게 Exchange Online 사서함이 없는 경우 관리자는 채팅 대화에 대한 보류 또는 저장을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-143">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="c5725-144">예를 들어 Exchange 하이브리드 배포에서는 온-프레미스 사서함이 있는 사용자가 Teams 채팅 목록에 포함된 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-144">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="c5725-145">하지만 이 경우에는 사용자에게 클라우드 기반 사서함이 없으므로 이 대화의 콘텐츠를 검색할 수 없고 보류 상태로 둘 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-145">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="c5725-146">(자세한 내용은 [Exchange와 Microsoft Teams의 상호 작용 방식](exchange-teams-interact.md)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="c5725-146">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="c5725-147">Teams 채팅은 Microsoft Exchange 백 엔드에서 작동하므로 Exchange 메시징 제한은 Teams 내의 채팅 기능에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-147">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="c5725-148">기능</span><span class="sxs-lookup"><span data-stu-id="c5725-148">Feature</span></span>  | <span data-ttu-id="c5725-149">최대 한도</span><span class="sxs-lookup"><span data-stu-id="c5725-149">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="c5725-150">비공개 채팅에 참가 중인 사용자 수<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c5725-150">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="c5725-151">250</span><span class="sxs-lookup"><span data-stu-id="c5725-151">250</span></span><br><br><span data-ttu-id="c5725-152">**참고:** 정부용 Teams(GCC, GCC High, DoD)에 대한 제한은 여전히 100입니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-152">**Note:** For Teams for Government (GCC, GCC High, DoD), the limit is still 100.</span></span> <span data-ttu-id="c5725-153">정부 클라우드 제한이 100에서 250으로 늘어나면 이 문서를 업데이트 할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-153">We'll update this article when the government cloud limit increases from 100 to 250.</span></span>    |
|<span data-ttu-id="c5725-154">채팅에서 영상 또는 음성 통화 중인 사용자 수</span><span class="sxs-lookup"><span data-stu-id="c5725-154">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="c5725-155">20</span><span class="sxs-lookup"><span data-stu-id="c5725-155">20</span></span> |
|<span data-ttu-id="c5725-156">첨부 파일 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c5725-156">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="c5725-157">10</span><span class="sxs-lookup"><span data-stu-id="c5725-157">10</span></span>     |
|<span data-ttu-id="c5725-158">채팅 크기</span><span class="sxs-lookup"><span data-stu-id="c5725-158">Chat size</span></span> | <span data-ttu-id="c5725-159">게시물당 28 KB<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="c5725-159">Approximately 28 KB per post<sup>3</sup></span></span> |

<span data-ttu-id="c5725-160"><sup>1</sup>채팅에 20명 이상의 사용자가 있는 경우 다음과 같은 채팅 기능이 꺼집니다. Outlook 자동 회신 및 Teams 상태 메시지, 입력 표시기, 비디오 및 오디오 통화, 공유, 읽음 확인.</span><span class="sxs-lookup"><span data-stu-id="c5725-160"><sup>1</sup> If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="c5725-161"><sup>2</sup>첨부 파일 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-161"><sup>2</sup> If the number of attachments exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="c5725-162"><sup>3</sup> 28 KB는 메시지 자체(텍스트, 이미지 링크 등), @-멘션, 반응이 포함되기 때문에 대략적인 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-162"><sup>3</sup> 28 KB is an approximate limit because it includes the message itself (text, image links, etc.), @-mentions, and reactions.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="c5725-163">채널 전자 메일 보내기 </span><span class="sxs-lookup"><span data-stu-id="c5725-163">Emailing a channel</span></span>

 <span data-ttu-id="c5725-164">사용자가 Teams의 채널에 전자 메일을 보내려면 채널 전자 메일 주소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-164">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="c5725-165">전자 메일이 채널의 일부인 경우 누구나 답장을 보내 대화를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-165">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="c5725-166">다음은 채널에 전자 메일을 보낼 때 적용되는 몇 가지 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-166">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="c5725-167">기능</span><span class="sxs-lookup"><span data-stu-id="c5725-167">Feature</span></span>  | <span data-ttu-id="c5725-168">최대 한도</span><span class="sxs-lookup"><span data-stu-id="c5725-168">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="c5725-169">메시지 크기<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="c5725-169">Message size<sup>1<sup></span></span> | <span data-ttu-id="c5725-170">24KB</span><span class="sxs-lookup"><span data-stu-id="c5725-170">24 KB</span></span> |
|<span data-ttu-id="c5725-171">첨부 파일 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c5725-171">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="c5725-172">20</span><span class="sxs-lookup"><span data-stu-id="c5725-172">20</span></span>     |
|<span data-ttu-id="c5725-173">각 첨부 파일의 크기</span><span class="sxs-lookup"><span data-stu-id="c5725-173">Size of each file attachment</span></span> | <span data-ttu-id="c5725-174">10MB 미만</span><span class="sxs-lookup"><span data-stu-id="c5725-174">Less than 10 MB</span></span> |
|<span data-ttu-id="c5725-175">인라인 이미지 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="c5725-175">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="c5725-176">50</span><span class="sxs-lookup"><span data-stu-id="c5725-176">50</span></span>   |

<span data-ttu-id="c5725-177"><sup>1</sup>메시지가 이 한도를 초과하는 경우 미리 보기 메시지가 생성되고, 사용자에게 제공된 링크에서 원본 전자 메일을 다운로드하여 확인하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-177"><sup>1</sup> If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="c5725-178"><sup>2</sup>첨부 파일이나 이미지 수가 이 제한을 초과하는 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-178"><sup>2</sup> If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="c5725-179">자세한 내용은 [Exchange Online 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5725-179">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="c5725-180">모든 Microsoft 365 및 Office 365 라이선스에서 메시지 크기, 첨부 파일 및 인라인 이미지 제한이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-180">Message size, file attachments, and inline images limits are the same across all Microsoft 365 and Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="c5725-181">채널 이름</span><span class="sxs-lookup"><span data-stu-id="c5725-181">Channel names</span></span>

<span data-ttu-id="c5725-182">채널 이름에는 다음 문자나 단어가 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-182">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="c5725-183">문자</span><span class="sxs-lookup"><span data-stu-id="c5725-183">Characters</span></span>     | <span data-ttu-id="c5725-184">~ # % & \* { } + / \ : < > ?</span><span class="sxs-lookup"><span data-stu-id="c5725-184">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="c5725-185">&#124; ' " ..</span><span class="sxs-lookup"><span data-stu-id="c5725-185">&#124; ' " ..</span></span>        |
|<span data-ttu-id="c5725-186">해당 범위에 있는 문자</span><span class="sxs-lookup"><span data-stu-id="c5725-186">Characters in these ranges</span></span>    | <span data-ttu-id="c5725-187">0~1F</span><span class="sxs-lookup"><span data-stu-id="c5725-187">0 to 1F</span></span><br><span data-ttu-id="c5725-188">80~9F</span><span class="sxs-lookup"><span data-stu-id="c5725-188">80 to 9F</span></span>        |
|<span data-ttu-id="c5725-189">단어</span><span class="sxs-lookup"><span data-stu-id="c5725-189">Words</span></span>     | <span data-ttu-id="c5725-190">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1~COM9, LPT1~LPT9, desktop.ini,  &#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="c5725-190">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="c5725-191">또한 채널 이름은 밑줄(_) 또는 마침표(.)로 시작하거나 마침표(.)로 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-191">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="c5725-192">모임 및 통화</span><span class="sxs-lookup"><span data-stu-id="c5725-192">Meetings and calls</span></span>

|<span data-ttu-id="c5725-193">기능</span><span class="sxs-lookup"><span data-stu-id="c5725-193">Feature</span></span>     | <span data-ttu-id="c5725-194">최대 한도</span><span class="sxs-lookup"><span data-stu-id="c5725-194">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="c5725-195">모임에 참가 중인 사용자 수(채팅 및 전화를 걸 수 있음)</span><span class="sxs-lookup"><span data-stu-id="c5725-195">Number of people in a meeting (can chat and call in)</span></span>  | <span data-ttu-id="c5725-196">250</span><span class="sxs-lookup"><span data-stu-id="c5725-196">250</span></span>    |
|<span data-ttu-id="c5725-197">채팅에서 영상 또는 음성 통화 중인 사용자 수</span><span class="sxs-lookup"><span data-stu-id="c5725-197">Number of people in a video or audio call from chat</span></span> | <span data-ttu-id="c5725-198">20</span><span class="sxs-lookup"><span data-stu-id="c5725-198">20</span></span> |
|<span data-ttu-id="c5725-199">최대 PowerPoint 파일 크기</span><span class="sxs-lookup"><span data-stu-id="c5725-199">Max PowerPoint File Size</span></span> | <span data-ttu-id="c5725-200">2GB</span><span class="sxs-lookup"><span data-stu-id="c5725-200">2GB</span></span>|
|<span data-ttu-id="c5725-201">Teams는 Microsoft Stream에 업로드되지 않은 [모임 녹화](cloud-recording.md)를 보관하며 로컬로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-201">Teams keeps [meeting recordings](cloud-recording.md) that don't get uploaded to Microsoft Stream, available for local download</span></span> | <span data-ttu-id="c5725-202">20일</span><span class="sxs-lookup"><span data-stu-id="c5725-202">20 days</span></span> |

### <a name="meeting-expiration"></a><span data-ttu-id="c5725-203">모임 만료</span><span class="sxs-lookup"><span data-stu-id="c5725-203">Meeting expiration</span></span>

|<span data-ttu-id="c5725-204">모임 유형</span><span class="sxs-lookup"><span data-stu-id="c5725-204">Meeting type</span></span>  |<span data-ttu-id="c5725-205">이만큼 시간이 지나면 모임이 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-205">Meeting expires after this much time</span></span>  |<span data-ttu-id="c5725-206">모임을 시작하거나 업데이트할 때마다 만료 시간이 이 시간만큼 연장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-206">Each time you start or update a meeting, expiration extends by this much time</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="c5725-207">모임 시작</span><span class="sxs-lookup"><span data-stu-id="c5725-207">Meet now</span></span>     |<span data-ttu-id="c5725-208">시작 시간 + 8시간</span><span class="sxs-lookup"><span data-stu-id="c5725-208">Start time + 8 hours</span></span>         |<span data-ttu-id="c5725-209">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c5725-209">N/A</span></span>         |
|<span data-ttu-id="c5725-210">정규(종료 시간 없음)</span><span class="sxs-lookup"><span data-stu-id="c5725-210">Regular with no end time</span></span>     |<span data-ttu-id="c5725-211">시작 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="c5725-211">Start time + 60 days</span></span>         | <span data-ttu-id="c5725-212">60일</span><span class="sxs-lookup"><span data-stu-id="c5725-212">60 days</span></span>        |
|<span data-ttu-id="c5725-213">정규(종료 시간 있음)</span><span class="sxs-lookup"><span data-stu-id="c5725-213">Regular with end time</span></span>     |<span data-ttu-id="c5725-214">종료 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="c5725-214">End time + 60 days</span></span>         |<span data-ttu-id="c5725-215">60일</span><span class="sxs-lookup"><span data-stu-id="c5725-215">60 days</span></span>         |
|<span data-ttu-id="c5725-216">되풀이(종료 시간 없음)</span><span class="sxs-lookup"><span data-stu-id="c5725-216">Recurring with no end time</span></span>     |<span data-ttu-id="c5725-217">시작 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="c5725-217">Start time + 60 days</span></span>         |<span data-ttu-id="c5725-218">60일</span><span class="sxs-lookup"><span data-stu-id="c5725-218">60 days</span></span>         |
|<span data-ttu-id="c5725-219">되풀이(종료 시간 있음)</span><span class="sxs-lookup"><span data-stu-id="c5725-219">Recurring with end time</span></span>     |<span data-ttu-id="c5725-220">마지막 발생 항목의 종료 시간 + 60일</span><span class="sxs-lookup"><span data-stu-id="c5725-220">End time of last occurrence + 60 days</span></span>         |<span data-ttu-id="c5725-221">60일</span><span class="sxs-lookup"><span data-stu-id="c5725-221">60 days</span></span>         |

## <a name="teams-live-events"></a><span data-ttu-id="c5725-222">Teams 라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="c5725-222">Teams live events</span></span>

|<span data-ttu-id="c5725-223">기능</span><span class="sxs-lookup"><span data-stu-id="c5725-223">Feature</span></span>     | <span data-ttu-id="c5725-224">최대 한도</span><span class="sxs-lookup"><span data-stu-id="c5725-224">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="c5725-225">대상 그룹 크기</span><span class="sxs-lookup"><span data-stu-id="c5725-225">Audience size</span></span> | <span data-ttu-id="c5725-226">10,000 참석자</span><span class="sxs-lookup"><span data-stu-id="c5725-226">10,000 attendees</span></span> |
|<span data-ttu-id="c5725-227">이벤트 기간</span><span class="sxs-lookup"><span data-stu-id="c5725-227">Duration of event</span></span> | <span data-ttu-id="c5725-228">4시간</span><span class="sxs-lookup"><span data-stu-id="c5725-228">4 hours</span></span> |
|<span data-ttu-id="c5725-229">Microsoft 365 또는 Office 365 조직에서 실행되는 동시 발생 라이브 이벤트 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c5725-229">Concurrent live events running in a Microsoft 365 or Office 365 organization <sup>1</sup></span></span> | <span data-ttu-id="c5725-230">15</span><span class="sxs-lookup"><span data-stu-id="c5725-230">15</span></span> |

<span data-ttu-id="c5725-231"><sup>1</sup> 여러 라이브 이벤트를 원하는 대로 예약할 수 있지만, 한 번에 15개만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-231"><sup>1</sup> You can schedule as many live events as you want, but you can only run 15 at a time.</span></span> <span data-ttu-id="c5725-232">프로듀서가 라이브 이벤트에 참가하는 즉시 실행 중인 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-232">As soon as the producer joins a live event, it's considered to be running.</span></span> <span data-ttu-id="c5725-233">16번째 라이브 이벤트에 참가하려고 시도하는 프로듀서는 오류 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-233">The producer who attempts to join the 16th live event gets an error.</span></span>

<span data-ttu-id="c5725-234">라이브 이벤트와 Teams 라이브 이벤트와 Skype 모임 브로드캐스트 비교에 대한 자세한 내용은 [Teams 라이브 이벤트 및 Skype 모임 브로드캐스트](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5725-234">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5725-235">**Microsoft 365 라이브 이벤트 한도가 늘어납니다**</span><span class="sxs-lookup"><span data-stu-id="c5725-235">**Microsoft 365 live event limit increases**</span></span>
> 
> <span data-ttu-id="c5725-236">고객들이 급변하는 통신 요구 사항을 충족시키는 데 도움을 주기 위해 Microsoft 365 라이브 이벤트는 Teams에서 호스트하는 라이브 이벤트에 대한 기본 한도를 2020년 7월 1일까지 일시적으로 늘릴 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-236">To help customers meet rapidly changing communication needs, Microsoft 365 live events will temporarily raise default limits until July 1, 2020, for live events hosted in Teams.</span></span> <span data-ttu-id="c5725-237">다음의 한도 확장은 2020년 4월말에 반영되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-237">The following increases are being rolled out in late April 2020:</span></span>
> - <span data-ttu-id="c5725-238">참석자 제한: 이벤트는 최대 20,000명의 참석자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-238">Attendee limit: events can support up to 20,000 attendees</span></span>
> - <span data-ttu-id="c5725-239">동시 이벤트: 한 테넌트에 걸쳐 동시에 50개의 이벤트 호스트가 가능</span><span class="sxs-lookup"><span data-stu-id="c5725-239">Concurrent events: 50 events can be hosted simultaneously across a tenant</span></span>
> - <span data-ttu-id="c5725-240">이벤트 기간: 이벤트 시간이 브로드캐스트 당 16시간으로 늘어났습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-240">Event duration: event length has been increased to 16 hours per broadcast</span></span>



## <a name="presence-in-outlook"></a><span data-ttu-id="c5725-241">Outlook에서의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="c5725-241">Presence in Outlook</span></span>

<span data-ttu-id="c5725-242">Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-242">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span> <span data-ttu-id="c5725-243">팀의 현재 상태에 대해 자세히 알아보려면 [팀의 사용자 현재 상태](presence-admins.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5725-243">To learn more about presence in Teams, see [User presence in Teams](presence-admins.md).</span></span>

## <a name="storage"></a><span data-ttu-id="c5725-244">저장소</span><span class="sxs-lookup"><span data-stu-id="c5725-244">Storage</span></span>

<span data-ttu-id="c5725-245">Microsoft Teams의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 채널은 기본 팀 사이트 문서 라이브러리 내에 폴더가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-245">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="c5725-246">대화 내에서 공유된 파일은 문서 라이브러리에 자동으로 추가되고, SharePoint에 설정된 사용 권한 및 파일 보안 옵션은 Teams에서 자동으로 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-246">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="c5725-247">테넌트에서 SharePoint Online을 사용하지 않는 경우 Microsoft Teams 사용자는 팀에서 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-247">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="c5725-248">비즈니스용 OneDrive(SharePoint 라이선스에 연결됨)가 해당 기능에 필요하므로 개인 채팅 사용자도 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-248">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="c5725-249">SharePoint Online 문서 라이브러리와 비즈니스용 OneDrive에 파일을 저장하면 테넌트 수준에서 구성된 모든 규정 준수 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-249">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="c5725-250">(자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive가 Teams와 상호 작용하는 방법](sharepoint-onedrive-interact.md)을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="c5725-250">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="c5725-251">Teams는 파일 공유를 위해 SharePoint Online 백 엔드에서 실행되므로 SharePoint 제한 사항은 팀 내의 파일 섹션에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-251">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="c5725-252">다음은 SharePoint Online에 적용할 수 있는 저장소 용량 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-252">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="c5725-253">기능</span><span class="sxs-lookup"><span data-stu-id="c5725-253">Feature</span></span>                 |<span data-ttu-id="c5725-254">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="c5725-254">Microsoft 365 Business Basic</span></span>  |<span data-ttu-id="c5725-255">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="c5725-255">Microsoft 365 Business Standard</span></span>   |<span data-ttu-id="c5725-256">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="c5725-256">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="c5725-257">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="c5725-257">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="c5725-258">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="c5725-258">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="c5725-259">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="c5725-259">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="c5725-260">저장소</span><span class="sxs-lookup"><span data-stu-id="c5725-260">Storage</span></span>                 |<span data-ttu-id="c5725-261">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="c5725-261">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="c5725-262">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="c5725-262">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="c5725-263">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="c5725-263">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="c5725-264">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="c5725-264">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="c5725-265">조직당 1TB 및 구매한 라이선스당 10GB</span><span class="sxs-lookup"><span data-stu-id="c5725-265">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="c5725-266">조직당 1TB</span><span class="sxs-lookup"><span data-stu-id="c5725-266">1 TB per organization</span></span>           |
|<span data-ttu-id="c5725-267">Teams 파일용 저장소</span><span class="sxs-lookup"><span data-stu-id="c5725-267">Storage for Teams Files</span></span> |<span data-ttu-id="c5725-268">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="c5725-268">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="c5725-269">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="c5725-269">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="c5725-270">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="c5725-270">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="c5725-271">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="c5725-271">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="c5725-272">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="c5725-272">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="c5725-273">사이트 모음 또는 그룹당 최대 25TB</span><span class="sxs-lookup"><span data-stu-id="c5725-273">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="c5725-274">파일 업로드 제한(파일당)</span><span class="sxs-lookup"><span data-stu-id="c5725-274">File upload limit  (per file)</span></span>    |<span data-ttu-id="c5725-275">15GB</span><span class="sxs-lookup"><span data-stu-id="c5725-275">15 GB</span></span>    |<span data-ttu-id="c5725-276">15GB</span><span class="sxs-lookup"><span data-stu-id="c5725-276">15 GB</span></span>    |<span data-ttu-id="c5725-277">15GB</span><span class="sxs-lookup"><span data-stu-id="c5725-277">15 GB</span></span>    |<span data-ttu-id="c5725-278">15GB</span><span class="sxs-lookup"><span data-stu-id="c5725-278">15 GB</span></span>    |<span data-ttu-id="c5725-279">15GB</span><span class="sxs-lookup"><span data-stu-id="c5725-279">15 GB</span></span>    |<span data-ttu-id="c5725-280">15GB</span><span class="sxs-lookup"><span data-stu-id="c5725-280">15 GB</span></span>    |

<span data-ttu-id="c5725-281">채널은 팀을 위해 만든 SharePoint Online 사이트 모음의 폴더에 의해 지원되므로 채널 내의 파일 탭은 속해 있는 팀의 저장소 용량 한도를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-281">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="c5725-282">자세한 내용은 [SharePoint Online 제한](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5725-282">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="tags"></a><span data-ttu-id="c5725-283">태그</span><span class="sxs-lookup"><span data-stu-id="c5725-283">Tags</span></span>

|<span data-ttu-id="c5725-284">기능</span><span class="sxs-lookup"><span data-stu-id="c5725-284">Feature</span></span>  |<span data-ttu-id="c5725-285">최대 한도</span><span class="sxs-lookup"><span data-stu-id="c5725-285">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="c5725-286">팀당 태그 수</span><span class="sxs-lookup"><span data-stu-id="c5725-286">Number of tags per team</span></span>    | <span data-ttu-id="c5725-287">100</span><span class="sxs-lookup"><span data-stu-id="c5725-287">100</span></span>        |
|<span data-ttu-id="c5725-288">팀당 제안된 기본 태그 수</span><span class="sxs-lookup"><span data-stu-id="c5725-288">Number of suggested default tags per team</span></span>    | <span data-ttu-id="c5725-289">25</span><span class="sxs-lookup"><span data-stu-id="c5725-289">25</span></span>        |
|<span data-ttu-id="c5725-290">태그에 할당되는 팀 구성원 수</span><span class="sxs-lookup"><span data-stu-id="c5725-290">Number of team members assign to a tag</span></span>    |<span data-ttu-id="c5725-291">100</span><span class="sxs-lookup"><span data-stu-id="c5725-291">100</span></span>         |
|<span data-ttu-id="c5725-292">사용자에게 할당되는 태그 수</span><span class="sxs-lookup"><span data-stu-id="c5725-292">Number of tags assigned to a user</span></span>    |<span data-ttu-id="c5725-293">25</span><span class="sxs-lookup"><span data-stu-id="c5725-293">25</span></span>         |

## <a name="contacts"></a><span data-ttu-id="c5725-294">연락처</span><span class="sxs-lookup"><span data-stu-id="c5725-294">Contacts</span></span>

<span data-ttu-id="c5725-295">Teams에서 사용하는 연락처:</span><span class="sxs-lookup"><span data-stu-id="c5725-295">Teams uses these contacts:</span></span>

- <span data-ttu-id="c5725-296">조직의 Active Directory에 있는 연락처</span><span class="sxs-lookup"><span data-stu-id="c5725-296">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="c5725-297">사용자의 Outlook 기본 폴더에 추가된 연락처</span><span class="sxs-lookup"><span data-stu-id="c5725-297">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="c5725-298">Teams 사용자는 조직의 Active Directory에 있는 모든 사용자와 커뮤니케이션할 수 있으며, 조직의 Active Directory에 있는 모든 사용자를 **채팅** > **연락처** 또는 **통화** > **연락처**로 이동하여 대화 상대 및 대화 상대 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-298">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="c5725-299">팀 사용자는 조직 내의 Active Directory에 없는 사용자를 **통화** > **연락처**로 이동하여 연락처로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5725-299">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="c5725-300">브라우저</span><span class="sxs-lookup"><span data-stu-id="c5725-300">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="c5725-301">운영 체제</span><span class="sxs-lookup"><span data-stu-id="c5725-301">Operating systems</span></span>

<span data-ttu-id="c5725-302">운영 체제 요구 사항에 대한 자세한 내용은 [Microsoft Teams용 클라이언트 다운로드](get-clients.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5725-302">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
