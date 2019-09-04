---
title: Microsoft 팀의 제한 사항 및 사양
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karuanag
description: Microsoft 팀에 적용 되는 제한, 사양 및 기타 요구 사항에 대해 알아봅니다.
localization_priority: Priority
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82fbaa955c080446619558a7a90410200f4be604
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715901"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="bc43e-103">Microsoft 팀의 제한 사항 및 사양</span><span class="sxs-lookup"><span data-stu-id="bc43e-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="bc43e-104">이 문서에서는 팀에 적용 되는 몇 가지 제한 사항, 사양 및 기타 요구 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="bc43e-105">팀 및 채널</span><span class="sxs-lookup"><span data-stu-id="bc43e-105">Teams and channels</span></span>

|<span data-ttu-id="bc43e-106">요소</span><span class="sxs-lookup"><span data-stu-id="bc43e-106">Feature</span></span>    | <span data-ttu-id="bc43e-107">최대 한도</span><span class="sxs-lookup"><span data-stu-id="bc43e-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="bc43e-108">사용자가 만들 수 있는 팀 수</span><span class="sxs-lookup"><span data-stu-id="bc43e-108">Number of teams a user can create</span></span> | <span data-ttu-id="bc43e-109">250 개체&제한에 따라 sup1.</span><span class="sxs-lookup"><span data-stu-id="bc43e-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="bc43e-110">팀의 구성원 수</span><span class="sxs-lookup"><span data-stu-id="bc43e-110">Number of members in a team</span></span> | <span data-ttu-id="bc43e-111">5000</span><span class="sxs-lookup"><span data-stu-id="bc43e-111">5,000</span></span>       |
|<span data-ttu-id="bc43e-112">테 넌 트에서 허용 되는 조직 차원의 팀 수</span><span class="sxs-lookup"><span data-stu-id="bc43e-112">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="bc43e-113">5mb</span><span class="sxs-lookup"><span data-stu-id="bc43e-113">5</span></span>     |
|<span data-ttu-id="bc43e-114">[조직 차원의 팀](create-an-org-wide-team.md) 구성원 수</span><span class="sxs-lookup"><span data-stu-id="bc43e-114">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="bc43e-115">5000</span><span class="sxs-lookup"><span data-stu-id="bc43e-115">5,000</span></span>       |
|<span data-ttu-id="bc43e-116">전역 관리자가 만들 수 있는 팀 수</span><span class="sxs-lookup"><span data-stu-id="bc43e-116">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="bc43e-117">50만</span><span class="sxs-lookup"><span data-stu-id="bc43e-117">500,000</span></span>   |
|<span data-ttu-id="bc43e-118">Office 365 테 넌 트가 가질 수 있는 팀 수</span><span class="sxs-lookup"><span data-stu-id="bc43e-118">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="bc43e-119">50만&sup2</span><span class="sxs-lookup"><span data-stu-id="bc43e-119">500,000&sup2;</span></span>     |
|<span data-ttu-id="bc43e-120">팀 당 채널 수</span><span class="sxs-lookup"><span data-stu-id="bc43e-120">Number of channels per team</span></span>    | <span data-ttu-id="bc43e-121">200 (삭제 된 채널 포함) &sup3</span><span class="sxs-lookup"><span data-stu-id="bc43e-121">200 (includes deleted channels)&sup3;</span></span>         |

<span data-ttu-id="bc43e-122">&sup1 Azure Active Directory의 모든 디렉터리 개체는이 제한에 대해 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-122">&sup1;Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="bc43e-123">전역 관리자는 [응용 프로그램 사용 권한을](https://docs.microsoft.com/graph/permissions-reference)사용 하 여 Microsoft Graph를 호출 하는 앱 처럼이 제한에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-123">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="bc43e-124">&sup2 이 제한에는 보관 된 팀이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-124">&sup2;This limit includes archived teams.</span></span>

<span data-ttu-id="bc43e-125">&sup3; 30 일 이내에 삭제 된 채널을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-125">&sup3;Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="bc43e-126">30 일 이내에 삭제 된 채널은 팀 제한에 따라 200 채널에 계속 해 서 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-126">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="bc43e-127">30 일이 지난 후 삭제 된 채널과 해당 콘텐츠는 영구적으로 삭제 되며 채널은 더 이상 팀 제한에 따라 200 채널에 대해 카운트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-127">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

## <a name="messaging"></a><span data-ttu-id="bc43e-128">메시지</span><span class="sxs-lookup"><span data-stu-id="bc43e-128">Messaging</span></span>

### <a name="chat"></a><span data-ttu-id="bc43e-129">채트</span><span class="sxs-lookup"><span data-stu-id="bc43e-129">Chat</span></span>

<span data-ttu-id="bc43e-130">팀에서 채팅 목록의 일부인 대화에 참여 하는 사용자는 관리자가 채팅 대화를 검색할 수 있도록 Exchange Online (클라우드 기반) 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-130">Users who participate in conversations that are part of the chat list in Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="bc43e-131">채팅 목록의 일부인 대화는 채팅 참가자의 클라우드 기반 사서함에 저장 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-131">That's because conversations that are part of the chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="bc43e-132">채팅 참가자에 게 Exchange Online 사서함이 없는 경우 관리자는 채팅을 통해 대화를 검색 하거나 보류할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-132">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="bc43e-133">예를 들어 Exchange 하이브리드 배포에서 온-프레미스 사서함을 사용 하는 사용자는 팀의 채팅 목록에 속하는 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-133">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the chat list in Teams.</span></span> <span data-ttu-id="bc43e-134">그러나이 경우 사용자에 게 클라우드 기반 사서함이 없기 때문에 이러한 대화의 콘텐츠를 검색할 수 없으며 보류 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-134">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="bc43e-135">자세한 내용은 [Exchange 및 Microsoft 팀의 상호 작용 방식을](exchange-teams-interact.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc43e-135">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="bc43e-136">팀 채팅은 Microsoft Exchange 백 엔드에서 작동 하므로 Exchange 메시징 한도가 팀 내의 채팅 기능에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-136">Teams chat works on a Microsoft Exchange backend, so Exchange messaging limits apply to the chat function within Teams.</span></span>

|<span data-ttu-id="bc43e-137">요소</span><span class="sxs-lookup"><span data-stu-id="bc43e-137">Feature</span></span>  | <span data-ttu-id="bc43e-138">최대 한도</span><span class="sxs-lookup"><span data-stu-id="bc43e-138">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="bc43e-139">개인 채팅<sup>1</sup> 의 사용자 수</span><span class="sxs-lookup"><span data-stu-id="bc43e-139">Number of people in a private chat<sup>1</sup></span></span>  | <span data-ttu-id="bc43e-140">100</span><span class="sxs-lookup"><span data-stu-id="bc43e-140">100</span></span>    |
|<span data-ttu-id="bc43e-141">첨부 파일 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bc43e-141">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="bc43e-142">1천만</span><span class="sxs-lookup"><span data-stu-id="bc43e-142">10</span></span>     |

<span data-ttu-id="bc43e-143"><sup>1</sup> 채팅에 20 명 이상의 사용자가 있는 경우에는 Outlook 자동 회신 및 팀 상태 메시지와 같은 채팅 기능을 사용할 수 없게 됩니다. 입력 표시기 영상 및 음성 통화 공유 읽음 확인</span><span class="sxs-lookup"><span data-stu-id="bc43e-143"><sup>1</sup>If you have more than 20 people in a chat, the following chat features are turned off: Outlook automatic replies and Teams status messages; typing indicator; video and audio calling; sharing; read receipts.</span></span>

<span data-ttu-id="bc43e-144"><sup>2</sup> 첨부 파일 수가이 제한을 초과 하는 경우 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-144"><sup>2</sup>If the number of attachments exceeds this limit, you'll see an error message.</span></span>

### <a name="emailing-a-channel"></a><span data-ttu-id="bc43e-145">채널 전자 메일</span><span class="sxs-lookup"><span data-stu-id="bc43e-145">Emailing a channel</span></span>

 <span data-ttu-id="bc43e-146">사용자가 팀의 채널에 전자 메일을 보내려고 하는 경우 채널 전자 메일 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-146">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="bc43e-147">전자 메일이 채널의 일부인 경우 누구나 회신할 수 있으므로 대화가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-147">When an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="bc43e-148">다음은 채널에 전자 메일을 보낼 때 적용 되는 몇 가지 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-148">Here are some of the applicable limits for sending email to a channel.</span></span>

|<span data-ttu-id="bc43e-149">요소</span><span class="sxs-lookup"><span data-stu-id="bc43e-149">Feature</span></span>  | <span data-ttu-id="bc43e-150">최대 한도</span><span class="sxs-lookup"><span data-stu-id="bc43e-150">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="bc43e-151">메시지 크기<sup>1<sup></span><span class="sxs-lookup"><span data-stu-id="bc43e-151">Message size<sup>1<sup></span></span> | <span data-ttu-id="bc43e-152">24kb</span><span class="sxs-lookup"><span data-stu-id="bc43e-152">24 KB</span></span> |
|<span data-ttu-id="bc43e-153">첨부 파일 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bc43e-153">Number of file attachments<sup>2</sup></span></span>  |<span data-ttu-id="bc43e-154">명</span><span class="sxs-lookup"><span data-stu-id="bc43e-154">20</span></span>     |
|<span data-ttu-id="bc43e-155">각 첨부 파일의 크기</span><span class="sxs-lookup"><span data-stu-id="bc43e-155">Size of each file attachment</span></span> | <span data-ttu-id="bc43e-156">10mb 미만</span><span class="sxs-lookup"><span data-stu-id="bc43e-156">Less than 10 MB</span></span> |
|<span data-ttu-id="bc43e-157">인라인 이미지의 수<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bc43e-157">Number of inline images<sup>2</sup></span></span> |<span data-ttu-id="bc43e-158">50</span><span class="sxs-lookup"><span data-stu-id="bc43e-158">50</span></span>   |

<span data-ttu-id="bc43e-159"><sup>1</sup> 메시지가이 제한을 초과 하는 경우 미리 보기 메시지가 생성 되 고 사용자에 게 제공 된 링크에서 원본 전자 메일을 다운로드 하 여 확인 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-159"><sup>1</sup>If the message exceeds this limit, a preview message is generated and the user is asked to download and view the original email from the link provided.</span></span>

<span data-ttu-id="bc43e-160"><sup>2</sup> 첨부 파일 또는 이미지 수가이 제한을 초과 하는 경우 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-160"><sup>2</sup>If the number of attachments or images exceeds this limit, you'll see an error message.</span></span>

<span data-ttu-id="bc43e-161">자세한 내용은 [Exchange Online 제한을](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc43e-161">For more information, see [Exchange Online limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).</span></span>

> [!NOTE]
> <span data-ttu-id="bc43e-162">모든 Office 365 라이선스에서 메시지 크기, 첨부 파일 및 인라인 이미지 제한은 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-162">Message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

## <a name="channel-names"></a><span data-ttu-id="bc43e-163">채널 이름</span><span class="sxs-lookup"><span data-stu-id="bc43e-163">Channel names</span></span>

<span data-ttu-id="bc43e-164">채널 이름에는 다음 문자 또는 단어를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-164">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="bc43e-165">자로</span><span class="sxs-lookup"><span data-stu-id="bc43e-165">Characters</span></span>     | <span data-ttu-id="bc43e-166">~ #% & \* {} +/\:  < > ?</span><span class="sxs-lookup"><span data-stu-id="bc43e-166">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="bc43e-167">&#124; ' "..</span><span class="sxs-lookup"><span data-stu-id="bc43e-167">&#124; ' " ..</span></span>        |
|<span data-ttu-id="bc43e-168">이 범위의 문자</span><span class="sxs-lookup"><span data-stu-id="bc43e-168">Characters in these ranges</span></span>    | <span data-ttu-id="bc43e-169">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="bc43e-169">0 to 1F</span></span><br><span data-ttu-id="bc43e-170">80-9F</span><span class="sxs-lookup"><span data-stu-id="bc43e-170">80 to 9F</span></span>        |
|<span data-ttu-id="bc43e-171">단어</span><span class="sxs-lookup"><span data-stu-id="bc43e-171">Words</span></span>     | <span data-ttu-id="bc43e-172">forms, CON, CONIN $, $ OUT $, PRN, AUX, NUL, COM1 to COM9, LPT1 ~ 사용할, desktop.ini, &#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="bc43e-172">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="bc43e-173">또한 채널 이름은 밑줄 (_) 또는 마침표 (.)로 시작 하거나 마침표 (.)로 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-173">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="bc43e-174">모임 및 통화</span><span class="sxs-lookup"><span data-stu-id="bc43e-174">Meetings and calls</span></span>

|<span data-ttu-id="bc43e-175">요소</span><span class="sxs-lookup"><span data-stu-id="bc43e-175">Feature</span></span>     | <span data-ttu-id="bc43e-176">최대 한도</span><span class="sxs-lookup"><span data-stu-id="bc43e-176">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="bc43e-177">모임에 참가 한 사용자 수</span><span class="sxs-lookup"><span data-stu-id="bc43e-177">Number of people in a meeting</span></span>  | <span data-ttu-id="bc43e-178">250</span><span class="sxs-lookup"><span data-stu-id="bc43e-178">250</span></span>    |

## <a name="teams-live-events"></a><span data-ttu-id="bc43e-179">팀 라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="bc43e-179">Teams live events</span></span>

|<span data-ttu-id="bc43e-180">요소</span><span class="sxs-lookup"><span data-stu-id="bc43e-180">Feature</span></span>     | <span data-ttu-id="bc43e-181">최대 한도</span><span class="sxs-lookup"><span data-stu-id="bc43e-181">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="bc43e-182">청중 크기</span><span class="sxs-lookup"><span data-stu-id="bc43e-182">Audience size</span></span> | <span data-ttu-id="bc43e-183">1만 참석자</span><span class="sxs-lookup"><span data-stu-id="bc43e-183">10,000 attendees</span></span> |
|<span data-ttu-id="bc43e-184">이벤트 기간</span><span class="sxs-lookup"><span data-stu-id="bc43e-184">Duration of event</span></span> | <span data-ttu-id="bc43e-185">4 시간</span><span class="sxs-lookup"><span data-stu-id="bc43e-185">4 hours</span></span> |
|<span data-ttu-id="bc43e-186">Office 365 테 넌 트의 동시 라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="bc43e-186">Concurrent live events in an Office 365 tenant</span></span> | <span data-ttu-id="bc43e-187">~</span><span class="sxs-lookup"><span data-stu-id="bc43e-187">15</span></span> |

<span data-ttu-id="bc43e-188">Live 이벤트 및 팀의 live 이벤트를 Skype 모임 브로드캐스트에 비교 하는 방법에 대 한 자세한 내용은 [팀 live 이벤트 및 Skype 모임 브로드캐스트](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc43e-188">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

## <a name="storage"></a><span data-ttu-id="bc43e-189">용량</span><span class="sxs-lookup"><span data-stu-id="bc43e-189">Storage</span></span>

<span data-ttu-id="bc43e-190">Microsoft 팀의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 채널은 기본 팀 사이트 문서 라이브러리 내에서 폴더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-190">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="bc43e-191">대화 내에서 공유 된 파일은 문서 라이브러리에 자동으로 추가 되며 SharePoint에 설정 된 사용 권한 및 파일 보안 옵션은 팀 내에 자동으로 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-191">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="bc43e-192">테 넌 트에서 SharePoint Online이 활성화 되어 있지 않은 경우 Microsoft 팀 사용자는 팀에서 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-192">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="bc43e-193">비즈니스용 OneDrive (SharePoint 라이선스에 연결 됨)가 해당 기능에 필요 하므로 개인 채팅의 사용자도 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-193">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="bc43e-194">SharePoint Online 문서 라이브러리 및 비즈니스용 OneDrive에 파일을 저장 하면 테 넌 트 수준에서 구성 된 모든 준수 규칙이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-194">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="bc43e-195">자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive For Microsoft 팀과의 상호 작용](sharepoint-onedrive-interact.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc43e-195">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="bc43e-196">팀은 파일 공유를 위해 SharePoint Online 백 엔드에서 실행 되므로 SharePoint 제한은 팀 내의 Files 섹션에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-196">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="bc43e-197">SharePoint Online에 적용 가능한 저장소 제한 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-197">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="bc43e-198">요소</span><span class="sxs-lookup"><span data-stu-id="bc43e-198">Feature</span></span>                 |<span data-ttu-id="bc43e-199">Office 365 비즈니스 주요 기능</span><span class="sxs-lookup"><span data-stu-id="bc43e-199">Office 365 Business Essentials</span></span>  |<span data-ttu-id="bc43e-200">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="bc43e-200">Office 365 Business Premium</span></span>   |<span data-ttu-id="bc43e-201">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="bc43e-201">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="bc43e-202">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="bc43e-202">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="bc43e-203">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="bc43e-203">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="bc43e-204">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="bc43e-204">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="bc43e-205">용량</span><span class="sxs-lookup"><span data-stu-id="bc43e-205">Storage</span></span>                 |<span data-ttu-id="bc43e-206">조직 당 1TB 및 구입한 라이선스 당 10gb</span><span class="sxs-lookup"><span data-stu-id="bc43e-206">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="bc43e-207">조직 당 1TB 및 구입한 라이선스 당 10gb</span><span class="sxs-lookup"><span data-stu-id="bc43e-207">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="bc43e-208">조직 당 1TB 및 구입한 라이선스 당 10gb</span><span class="sxs-lookup"><span data-stu-id="bc43e-208">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="bc43e-209">조직 당 1TB 및 구입한 라이선스 당 10gb</span><span class="sxs-lookup"><span data-stu-id="bc43e-209">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="bc43e-210">조직 당 1TB 및 구입한 라이선스 당 10gb</span><span class="sxs-lookup"><span data-stu-id="bc43e-210">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="bc43e-211">조직 당 1TB</span><span class="sxs-lookup"><span data-stu-id="bc43e-211">1 TB per organization</span></span>           |
|<span data-ttu-id="bc43e-212">팀 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="bc43e-212">Storage for Teams Files</span></span> |<span data-ttu-id="bc43e-213">사이트 모음 또는 그룹 당 최대 25 TB</span><span class="sxs-lookup"><span data-stu-id="bc43e-213">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="bc43e-214">사이트 모음 또는 그룹 당 최대 25 TB</span><span class="sxs-lookup"><span data-stu-id="bc43e-214">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="bc43e-215">사이트 모음 또는 그룹 당 최대 25 TB</span><span class="sxs-lookup"><span data-stu-id="bc43e-215">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="bc43e-216">사이트 모음 또는 그룹 당 최대 25 TB</span><span class="sxs-lookup"><span data-stu-id="bc43e-216">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="bc43e-217">사이트 모음 또는 그룹 당 최대 25 TB</span><span class="sxs-lookup"><span data-stu-id="bc43e-217">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="bc43e-218">사이트 모음 또는 그룹 당 최대 25 TB</span><span class="sxs-lookup"><span data-stu-id="bc43e-218">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="bc43e-219">파일 업로드 제한 (파일당)</span><span class="sxs-lookup"><span data-stu-id="bc43e-219">File upload limit  (per file)</span></span>    |<span data-ttu-id="bc43e-220">15 GB</span><span class="sxs-lookup"><span data-stu-id="bc43e-220">15 GB</span></span>    |<span data-ttu-id="bc43e-221">15 GB</span><span class="sxs-lookup"><span data-stu-id="bc43e-221">15 GB</span></span>    |<span data-ttu-id="bc43e-222">15 GB</span><span class="sxs-lookup"><span data-stu-id="bc43e-222">15 GB</span></span>    |<span data-ttu-id="bc43e-223">15 GB</span><span class="sxs-lookup"><span data-stu-id="bc43e-223">15 GB</span></span>    |<span data-ttu-id="bc43e-224">15 GB</span><span class="sxs-lookup"><span data-stu-id="bc43e-224">15 GB</span></span>    |<span data-ttu-id="bc43e-225">15 GB</span><span class="sxs-lookup"><span data-stu-id="bc43e-225">15 GB</span></span>    |

<span data-ttu-id="bc43e-226">채널은 팀에 대해 만든 SharePoint Online 사이트 모음 내의 폴더에 따라 지원 되므로 채널 내의 파일 탭은 자신이 속한 팀의 저장 용량 제한을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-226">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="bc43e-227">자세한 내용은 [SharePoint Online 제한을](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc43e-227">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="contacts"></a><span data-ttu-id="bc43e-228">상대가</span><span class="sxs-lookup"><span data-stu-id="bc43e-228">Contacts</span></span>

<span data-ttu-id="bc43e-229">팀은 다음 연락처를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-229">Teams uses these contacts:</span></span>

- <span data-ttu-id="bc43e-230">조직의 Active Directory에 있는 연락처</span><span class="sxs-lookup"><span data-stu-id="bc43e-230">Contacts in your organization's Active Directory</span></span>
- <span data-ttu-id="bc43e-231">사용자의 Outlook 기본 폴더에 추가 된 연락처</span><span class="sxs-lookup"><span data-stu-id="bc43e-231">Contacts added to the user's Outlook default folder</span></span>

<span data-ttu-id="bc43e-232">팀 사용자는 조직의 active directory에 있는 모든 사람과 통신할 수 있으며 조직의 active directory에 있는 사용자를 연락처 및 연락처 목록에 추가 하 여**대화 상대** 에 게 **채팅** > 하거나 전화를 **걸**  >  수 있습니다. **연락처**.</span><span class="sxs-lookup"><span data-stu-id="bc43e-232">Teams users can communicate with anyone in your organization's Active Directory and can add anyone in your organization's Active Directory as a contact and to their contact lists by going to **Chat** > **Contacts** or **Calls** > **Contacts**.</span></span>

<span data-ttu-id="bc43e-233">팀 사용자는**연락처**를 **호출** > 하 여 조직의 Active Directory에 없는 사람을 연락처로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc43e-233">Teams users can also add a person who isn't in your organization's Active Directory as a contact by going to **Calls** > **Contacts**.</span></span>

## <a name="browsers"></a><span data-ttu-id="bc43e-234">브라우저인</span><span class="sxs-lookup"><span data-stu-id="bc43e-234">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="bc43e-235">운영 체제</span><span class="sxs-lookup"><span data-stu-id="bc43e-235">Operating systems</span></span>

<span data-ttu-id="bc43e-236">운영 체제 요구 사항에 대 한 자세한 내용은 [Microsoft 팀 용 클라이언트 가져오기를](get-clients.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc43e-236">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
