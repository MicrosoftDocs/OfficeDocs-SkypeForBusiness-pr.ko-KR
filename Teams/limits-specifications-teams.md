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
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecd31a243da999704b7d466b3dc93dd66fb7ac25
ms.sourcegitcommit: 9053c0d5ddb6be3ce3da85dffcde3f45dbc0ab7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "36407995"
---
# <a name="limits-and-specifications-for-microsoft-teams"></a><span data-ttu-id="066ef-103">Microsoft 팀의 제한 사항 및 사양</span><span class="sxs-lookup"><span data-stu-id="066ef-103">Limits and specifications for Microsoft Teams</span></span>

<span data-ttu-id="066ef-104">이 문서에서는 팀에 적용 되는 몇 가지 제한 사항, 사양 및 기타 요구 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-104">This article describes some of the limits, specifications, and other requirements that apply to Teams.</span></span>

## <a name="teams-and-channels"></a><span data-ttu-id="066ef-105">팀 및 채널</span><span class="sxs-lookup"><span data-stu-id="066ef-105">Teams and channels</span></span> 

|<span data-ttu-id="066ef-106">요소</span><span class="sxs-lookup"><span data-stu-id="066ef-106">Feature</span></span>    | <span data-ttu-id="066ef-107">최대 한도</span><span class="sxs-lookup"><span data-stu-id="066ef-107">Maximum limit</span></span> |
|-----------|---------------|
|<span data-ttu-id="066ef-108">사용자가 만들 수 있는 팀 수</span><span class="sxs-lookup"><span data-stu-id="066ef-108">Number of teams a user can create</span></span> | <span data-ttu-id="066ef-109">250 개체&제한에 따라 sup1.</span><span class="sxs-lookup"><span data-stu-id="066ef-109">Subject to a 250 object limit&sup1;</span></span>         |
|<span data-ttu-id="066ef-110">팀의 구성원 수</span><span class="sxs-lookup"><span data-stu-id="066ef-110">Number of members in a team</span></span> | <span data-ttu-id="066ef-111">5000</span><span class="sxs-lookup"><span data-stu-id="066ef-111">5,000</span></span>       |
|<span data-ttu-id="066ef-112">테 넌 트에서 허용 되는 조직 차원의 팀 수</span><span class="sxs-lookup"><span data-stu-id="066ef-112">Number of org-wide teams allowed in a tenant</span></span> | <span data-ttu-id="066ef-113">5mb</span><span class="sxs-lookup"><span data-stu-id="066ef-113">5</span></span>     |
|<span data-ttu-id="066ef-114">[조직 차원의 팀](create-an-org-wide-team.md) 구성원 수</span><span class="sxs-lookup"><span data-stu-id="066ef-114">Number of members in an [org-wide team](create-an-org-wide-team.md)</span></span> | <span data-ttu-id="066ef-115">5000</span><span class="sxs-lookup"><span data-stu-id="066ef-115">5,000</span></span>       |
|<span data-ttu-id="066ef-116">전역 관리자가 만들 수 있는 팀 수</span><span class="sxs-lookup"><span data-stu-id="066ef-116">Number of teams a global admin can create</span></span>        |  <span data-ttu-id="066ef-117">50만</span><span class="sxs-lookup"><span data-stu-id="066ef-117">500,000</span></span>   |
|<span data-ttu-id="066ef-118">Office 365 테 넌 트가 가질 수 있는 팀 수</span><span class="sxs-lookup"><span data-stu-id="066ef-118">Number of teams an Office 365 tenant can have</span></span>    | <span data-ttu-id="066ef-119">50만&sup2</span><span class="sxs-lookup"><span data-stu-id="066ef-119">500,000&sup2;</span></span>     |
|<span data-ttu-id="066ef-120">팀 당 채널 수</span><span class="sxs-lookup"><span data-stu-id="066ef-120">Number of channels per team</span></span>    | <span data-ttu-id="066ef-121">200 (삭제 된 채널 포함) &sup3</span><span class="sxs-lookup"><span data-stu-id="066ef-121">200 (includes deleted channels)&sup3;</span></span>         |

<span data-ttu-id="066ef-122">&sup1 Azure Active Directory의 모든 디렉터리 개체는이 제한에 대해 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-122">&sup1;Any directory object in Azure Active Directory counts towards this limit.</span></span> <span data-ttu-id="066ef-123">전역 관리자는 [응용 프로그램 사용 권한을](https://docs.microsoft.com/graph/permissions-reference)사용 하 여 Microsoft Graph를 호출 하는 앱 처럼이 제한에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-123">Global admins are exempt from this limit, as are apps calling Microsoft Graph using [application permissions](https://docs.microsoft.com/graph/permissions-reference).</span></span>

<span data-ttu-id="066ef-124">&sup2 이 제한에는 보관 된 팀이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-124">&sup2;This limit includes archived teams.</span></span>

<span data-ttu-id="066ef-125">&sup3; 30 일 이내에 삭제 된 채널을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-125">&sup3;Deleted channels can be restored within 30 days.</span></span> <span data-ttu-id="066ef-126">30 일 이내에 삭제 된 채널은 팀 제한에 따라 200 채널에 계속 해 서 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-126">During these 30 days, a deleted channel continues to be counted towards the 200 channel per team limit.</span></span> <span data-ttu-id="066ef-127">30 일이 지난 후 삭제 된 채널과 해당 콘텐츠는 영구적으로 삭제 되며 채널은 더 이상 팀 제한에 따라 200 채널에 대해 카운트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-127">After 30 days, a deleted channel and its content are permanently deleted and the channel no longer counts towards the 200 channels per team limit.</span></span>

## <a name="channel-names"></a><span data-ttu-id="066ef-128">채널 이름</span><span class="sxs-lookup"><span data-stu-id="066ef-128">Channel names</span></span>

<span data-ttu-id="066ef-129">채널 이름에는 다음 문자 또는 단어를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-129">Channel names can't contain the following characters or words.</span></span>

|||
|---------|---------|
|<span data-ttu-id="066ef-130">자로</span><span class="sxs-lookup"><span data-stu-id="066ef-130">Characters</span></span>     | <span data-ttu-id="066ef-131">~ #% & \* {} +/\:  < > ?</span><span class="sxs-lookup"><span data-stu-id="066ef-131">~ # % & \* { } + / \ : < > ?</span></span> <span data-ttu-id="066ef-132">&#124; ' "..</span><span class="sxs-lookup"><span data-stu-id="066ef-132">&#124; ' " ..</span></span>        |
|<span data-ttu-id="066ef-133">이 범위의 문자</span><span class="sxs-lookup"><span data-stu-id="066ef-133">Characters in these ranges</span></span>    | <span data-ttu-id="066ef-134">0 ~ 1F</span><span class="sxs-lookup"><span data-stu-id="066ef-134">0 to 1F</span></span><br><span data-ttu-id="066ef-135">80-9F</span><span class="sxs-lookup"><span data-stu-id="066ef-135">80 to 9F</span></span>        |
|<span data-ttu-id="066ef-136">단어</span><span class="sxs-lookup"><span data-stu-id="066ef-136">Words</span></span>     | <span data-ttu-id="066ef-137">forms, CON, CONIN $, $ OUT $, PRN, AUX, NUL, COM1 to COM9, LPT1 ~ 사용할, desktop.ini, &#95;vti&#95;</span><span class="sxs-lookup"><span data-stu-id="066ef-137">forms, CON, CONIN$, CONOUT$, PRN, AUX, NUL, COM1 to COM9, LPT1 to LPT9, desktop.ini,  &#95;vti&#95;</span></span>|

<span data-ttu-id="066ef-138">또한 채널 이름은 밑줄 (_) 또는 마침표 (.)로 시작 하거나 마침표 (.)로 끝날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-138">Channel names also can't start with an underscore (_) or period (.), or end with a period (.).</span></span>

## <a name="meetings-and-calls"></a><span data-ttu-id="066ef-139">모임 및 통화</span><span class="sxs-lookup"><span data-stu-id="066ef-139">Meetings and calls</span></span>

|<span data-ttu-id="066ef-140">요소</span><span class="sxs-lookup"><span data-stu-id="066ef-140">Feature</span></span>     | <span data-ttu-id="066ef-141">최대 한도</span><span class="sxs-lookup"><span data-stu-id="066ef-141">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="066ef-142">모임에 참가 한 사용자 수</span><span class="sxs-lookup"><span data-stu-id="066ef-142">Number of people in a meeting</span></span>  | <span data-ttu-id="066ef-143">250</span><span class="sxs-lookup"><span data-stu-id="066ef-143">250</span></span>    |

## <a name="teams-live-events"></a><span data-ttu-id="066ef-144">팀 라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="066ef-144">Teams live events</span></span>

|<span data-ttu-id="066ef-145">요소</span><span class="sxs-lookup"><span data-stu-id="066ef-145">Feature</span></span>     | <span data-ttu-id="066ef-146">최대 한도</span><span class="sxs-lookup"><span data-stu-id="066ef-146">Maximum limit</span></span> |
|------------|---------------|
|<span data-ttu-id="066ef-147">청중 크기</span><span class="sxs-lookup"><span data-stu-id="066ef-147">Audience size</span></span> | <span data-ttu-id="066ef-148">1만 참석자</span><span class="sxs-lookup"><span data-stu-id="066ef-148">10,000 attendees</span></span> |
|<span data-ttu-id="066ef-149">이벤트 기간</span><span class="sxs-lookup"><span data-stu-id="066ef-149">Duration of event</span></span> | <span data-ttu-id="066ef-150">4 시간</span><span class="sxs-lookup"><span data-stu-id="066ef-150">4 hours</span></span> |
|<span data-ttu-id="066ef-151">1</span><span class="sxs-lookup"><span data-stu-id="066ef-151">Column1</span></span>  |<span data-ttu-id="066ef-152">Column2 등</span><span class="sxs-lookup"><span data-stu-id="066ef-152">Column2</span></span>  |
|---------|---------|
|<span data-ttu-id="066ef-153">Row1</span><span class="sxs-lookup"><span data-stu-id="066ef-153">Row1</span></span>     |         |
|<span data-ttu-id="066ef-154">Row2</span><span class="sxs-lookup"><span data-stu-id="066ef-154">Row2</span></span>     |         |

<span data-ttu-id="066ef-155">| Office 365 테 넌 트의 동시 라이브 이벤트 | 15 |</span><span class="sxs-lookup"><span data-stu-id="066ef-155">|Concurrent live events in an Office 365 tenant | 15 |</span></span>

<span data-ttu-id="066ef-156">Live 이벤트 및 팀의 live 이벤트를 Skype 모임 브로드캐스트에 비교 하는 방법에 대 한 자세한 내용은 [팀 live 이벤트 및 Skype 모임 브로드캐스트](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="066ef-156">For more information about live events and a comparison of Teams live events to Skype Meeting Broadcast, go to [Teams live events and Skype Meeting Broadcast](teams-live-events/plan-for-teams-live-events.md#teams-live-events-and-skype-meeting-broadcast).</span></span>

## <a name="storage"></a><span data-ttu-id="066ef-157">용량</span><span class="sxs-lookup"><span data-stu-id="066ef-157">Storage</span></span>

<span data-ttu-id="066ef-158">Microsoft 팀의 각 팀은 SharePoint Online에 팀 사이트가 있으며, 팀의 각 채널은 기본 팀 사이트 문서 라이브러리 내에서 폴더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-158">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="066ef-159">대화 내에서 공유 된 파일은 문서 라이브러리에 자동으로 추가 되며 SharePoint에 설정 된 사용 권한 및 파일 보안 옵션은 팀 내에 자동으로 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-159">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="066ef-160">테 넌 트에서 SharePoint Online이 활성화 되어 있지 않은 경우 Microsoft 팀 사용자는 팀에서 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-160">If you don't have SharePoint Online enabled in your tenant, Microsoft Teams users cannot always share files in teams.</span></span> <span data-ttu-id="066ef-161">비즈니스용 OneDrive (SharePoint 라이선스에 연결 됨)가 해당 기능에 필요 하므로 개인 채팅의 사용자도 파일을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-161">Users in private chat also cannot share files because OneDrive for Business (which is tied to the SharePoint license) is required for that functionality.</span></span>

<span data-ttu-id="066ef-162">SharePoint Online 문서 라이브러리 및 비즈니스용 OneDrive에 파일을 저장 하면 테 넌 트 수준에서 구성 된 모든 준수 규칙이 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-162">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> <span data-ttu-id="066ef-163">자세한 내용은 [SharePoint Online 및 비즈니스용 OneDrive For Microsoft 팀과의 상호 작용](sharepoint-onedrive-interact.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="066ef-163">(For more, see [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).)</span></span>

<span data-ttu-id="066ef-164">팀은 파일 공유를 위해 SharePoint Online 백 엔드에서 실행 되므로 SharePoint 제한은 팀 내의 Files 섹션에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-164">Because Teams runs on a SharePoint Online backend for file sharing, SharePoint limitations apply to the Files section within a Team.</span></span> <span data-ttu-id="066ef-165">SharePoint Online에 적용 가능한 저장소 제한 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-165">Here are the applicable storage limits for SharePoint Online.</span></span>

|<span data-ttu-id="066ef-166">요소</span><span class="sxs-lookup"><span data-stu-id="066ef-166">Feature</span></span>                 |<span data-ttu-id="066ef-167">Office 365 비즈니스 주요 기능</span><span class="sxs-lookup"><span data-stu-id="066ef-167">Office 365 Business Essentials</span></span>  |<span data-ttu-id="066ef-168">Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="066ef-168">Office 365 Business Premium</span></span>   |<span data-ttu-id="066ef-169">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="066ef-169">Office 365 Enterprise E1</span></span>  |<span data-ttu-id="066ef-170">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="066ef-170">Office 365 Enterprise E3</span></span>  |<span data-ttu-id="066ef-171">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="066ef-171">Office 365 Enterprise E5</span></span>  |<span data-ttu-id="066ef-172">Office 365 Enterprise F1</span><span class="sxs-lookup"><span data-stu-id="066ef-172">Office 365 Enterprise F1</span></span>  |
|------------------------|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="066ef-173">용량</span><span class="sxs-lookup"><span data-stu-id="066ef-173">Storage</span></span>                 |<span data-ttu-id="066ef-174">조직 당 1TB 및 구입한 라이선스 당 10gb</span><span class="sxs-lookup"><span data-stu-id="066ef-174">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="066ef-175">조직 당 1TB 및 구입한 라이선스 당 10gb</span><span class="sxs-lookup"><span data-stu-id="066ef-175">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="066ef-176">조직 당 1TB 및 구입한 라이선스 당 10gb</span><span class="sxs-lookup"><span data-stu-id="066ef-176">1 TB per organization plus 10 GB per license purchased</span></span>   |<span data-ttu-id="066ef-177">조직 당 1TB 및 구입한 라이선스 당 10gb</span><span class="sxs-lookup"><span data-stu-id="066ef-177">1 TB per organization plus 10 GB per license purchased</span></span> |<span data-ttu-id="066ef-178">조직 당 1TB 및 구입한 라이선스 당 10gb</span><span class="sxs-lookup"><span data-stu-id="066ef-178">1 TB per organization plus 10 GB per license purchased</span></span>  |<span data-ttu-id="066ef-179">조직 당 1TB</span><span class="sxs-lookup"><span data-stu-id="066ef-179">1 TB per organization</span></span>           |
|<span data-ttu-id="066ef-180">팀 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="066ef-180">Storage for Teams Files</span></span> |<span data-ttu-id="066ef-181">사이트 모음 또는 그룹 당 최대 25 TB</span><span class="sxs-lookup"><span data-stu-id="066ef-181">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="066ef-182">사이트 모음 또는 그룹 당 최대 25 TB</span><span class="sxs-lookup"><span data-stu-id="066ef-182">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="066ef-183">사이트 모음 또는 그룹 당 최대 25 TB</span><span class="sxs-lookup"><span data-stu-id="066ef-183">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="066ef-184">사이트 모음 또는 그룹 당 최대 25 TB</span><span class="sxs-lookup"><span data-stu-id="066ef-184">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="066ef-185">사이트 모음 또는 그룹 당 최대 25 TB</span><span class="sxs-lookup"><span data-stu-id="066ef-185">Up to 25 TB per site collection or group</span></span> |<span data-ttu-id="066ef-186">사이트 모음 또는 그룹 당 최대 25 TB</span><span class="sxs-lookup"><span data-stu-id="066ef-186">Up to 25 TB per site collection or group</span></span> |
|<span data-ttu-id="066ef-187">파일 업로드 제한 (파일당)</span><span class="sxs-lookup"><span data-stu-id="066ef-187">File upload limit  (per file)</span></span>    |<span data-ttu-id="066ef-188">15 GB</span><span class="sxs-lookup"><span data-stu-id="066ef-188">15 GB</span></span>    |<span data-ttu-id="066ef-189">15 GB</span><span class="sxs-lookup"><span data-stu-id="066ef-189">15 GB</span></span>    |<span data-ttu-id="066ef-190">15 GB</span><span class="sxs-lookup"><span data-stu-id="066ef-190">15 GB</span></span>    |<span data-ttu-id="066ef-191">15 GB</span><span class="sxs-lookup"><span data-stu-id="066ef-191">15 GB</span></span>    |<span data-ttu-id="066ef-192">15 GB</span><span class="sxs-lookup"><span data-stu-id="066ef-192">15 GB</span></span>    |<span data-ttu-id="066ef-193">15 GB</span><span class="sxs-lookup"><span data-stu-id="066ef-193">15 GB</span></span>    |

<span data-ttu-id="066ef-194">채널은 팀에 대해 만든 SharePoint Online 사이트 모음 내의 폴더에 따라 지원 되므로 채널 내의 파일 탭은 자신이 속한 팀의 저장 용량 제한을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-194">Channels are backed by folders within the SharePoint Online site collection created for the team, so file tabs within Channels share the storage limits of the team they belong to.</span></span>

<span data-ttu-id="066ef-195">자세한 내용은 [SharePoint Online 제한을](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="066ef-195">For more information, see [SharePoint Online limits](https://support.office.com/article/SharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span>

## <a name="messaging"></a><span data-ttu-id="066ef-196">메시지</span><span class="sxs-lookup"><span data-stu-id="066ef-196">Messaging</span></span>

<span data-ttu-id="066ef-197">Microsoft 팀에서 채팅 목록의 일부인 대화에 참여 하는 사용자는 관리자를 위해 Exchange Online (클라우드 기반) 사서함이 있어야 채팅 대화를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-197">Users who participate in conversations that are part of the Chat list in Microsoft Teams must have an Exchange Online (cloud-based) mailbox for an admin to search chat conversations.</span></span> <span data-ttu-id="066ef-198">채팅 목록의 일부인 대화는 채팅 참가자의 클라우드 기반 사서함에 저장 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-198">That's because conversations that are part of the Chat list are stored in the cloud-based mailboxes of the chat participants.</span></span> <span data-ttu-id="066ef-199">채팅 참가자에 게 Exchange Online 사서함이 없는 경우 관리자는 채팅을 통해 대화를 검색 하거나 보류할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-199">If a chat participant doesn't have an Exchange Online mailbox, the admin won't be able to search or place a hold on chat conversations.</span></span> <span data-ttu-id="066ef-200">예를 들어 Exchange 하이브리드 배포에서 온-프레미스 사서함을 사용 하는 사용자는 Microsoft 팀의 채팅 목록에 속하는 대화에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-200">For example, in an Exchange hybrid deployment, users with on-premises mailboxes might be able to participate in conversations that are part of the Chat list in Microsoft Teams.</span></span> <span data-ttu-id="066ef-201">그러나이 경우 사용자에 게 클라우드 기반 사서함이 없기 때문에 이러한 대화의 콘텐츠를 검색할 수 없으며 보류 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-201">However, in this case, content from these conversations isn't searchable and can't be placed on hold because the users don't have cloud-based mailboxes.</span></span> <span data-ttu-id="066ef-202">자세한 내용은 [Exchange 및 Microsoft 팀의 상호 작용 방식을](exchange-teams-interact.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="066ef-202">(For more, see [How Exchange and Microsoft Teams interact](exchange-teams-interact.md).)</span></span>

<span data-ttu-id="066ef-203">Microsoft Exchange 백 엔드에서 microsoft 팀 채팅 기능이 작동 하므로 Microsoft 팀 내에서 채팅 기능에 Exchange 메시징 제한을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-203">Microsoft Teams chat function works on a Microsoft Exchange backend, so you can apply the Exchange messaging limits to the chat function within Microsoft Teams.</span></span> <span data-ttu-id="066ef-204">사용자가 팀의 채널에 전자 메일을 보내려고 하는 경우 채널 전자 메일 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-204">If users want to send an email to a channel in Teams, they use the channel email address.</span></span> <span data-ttu-id="066ef-205">전자 메일이 채널의 일부인 경우 누구나 회신 하 여 대화를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-205">Once an email is part of a channel, anyone can reply to it to start a conversation.</span></span> <span data-ttu-id="066ef-206">다음은 채널에 전자 메일을 보낼 때 적용 되는 몇 가지 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-206">Here are some of the applicable limits for sending email to a channel.</span></span> 

|<span data-ttu-id="066ef-207">요소</span><span class="sxs-lookup"><span data-stu-id="066ef-207">Feature</span></span>  | <span data-ttu-id="066ef-208">최대 한도</span><span class="sxs-lookup"><span data-stu-id="066ef-208">Maximum limit</span></span>  |
|---------|---------|
|<span data-ttu-id="066ef-209">개인 채팅의 사용자 수</span><span class="sxs-lookup"><span data-stu-id="066ef-209">Number of people in a private chat</span></span>  | <span data-ttu-id="066ef-210">100</span><span class="sxs-lookup"><span data-stu-id="066ef-210">100</span></span>    |
|<span data-ttu-id="066ef-211">메시지 크기&dagger;</span><span class="sxs-lookup"><span data-stu-id="066ef-211">Message size &dagger;</span></span>  |<span data-ttu-id="066ef-212">25kb</span><span class="sxs-lookup"><span data-stu-id="066ef-212">25 KB</span></span>   |
|<span data-ttu-id="066ef-213">첨부 파일 수&Dagger;</span><span class="sxs-lookup"><span data-stu-id="066ef-213">Number of file attachments &Dagger;</span></span>  |<span data-ttu-id="066ef-214">1천만</span><span class="sxs-lookup"><span data-stu-id="066ef-214">10</span></span>     |
|<span data-ttu-id="066ef-215">인라인 이미지 수&Dagger;</span><span class="sxs-lookup"><span data-stu-id="066ef-215">Number of inline images &Dagger;</span></span> |<span data-ttu-id="066ef-216">50</span><span class="sxs-lookup"><span data-stu-id="066ef-216">50</span></span>   |

<span data-ttu-id="066ef-217">&dagger;메시지가이 제한을 초과 하는 경우 미리 보기 메시지가 생성 되 고 사용자에 게 제공 된 링크에서 원래 전자 메일을 보거나 다운로드 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-217">&dagger; If the message exceeds this limit, a preview message is generated and the user is asked to view/download the original email from the link provided.</span></span>

<span data-ttu-id="066ef-218">&Dagger;첨부 파일 또는 이미지 수가이 한도를 초과 하는 경우 메시지가 처리 되지 않으며, NDR 전자 메일을 보낸 사람에 게 다시 보내 오류를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-218">&Dagger; If the number of attachments or images exceeds this limit, the message will not be processed and an NDR email will be sent back to the sender notifying them of the error.</span></span>

> [!NOTE]
> <span data-ttu-id="066ef-219">메시지 크기, 첨부 파일 및 인라인 이미지 제한은 모든 Office 365 라이선스에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="066ef-219">The message size, file attachments, and inline images limits are the same across all Office 365 licenses.</span></span>

<span data-ttu-id="066ef-220">자세한 내용은 [Exchange Online 제한을](https://technet.microsoft.com/library/exchange-online-limits.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="066ef-220">For more information, see [Exchange Online limits](https://technet.microsoft.com/library/exchange-online-limits.aspx).</span></span>

## <a name="browsers"></a><span data-ttu-id="066ef-221">브라우저인</span><span class="sxs-lookup"><span data-stu-id="066ef-221">Browsers</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

## <a name="operating-systems"></a><span data-ttu-id="066ef-222">운영 체제</span><span class="sxs-lookup"><span data-stu-id="066ef-222">Operating systems</span></span>

<span data-ttu-id="066ef-223">운영 체제 요구 사항에 대 한 자세한 내용은 [Microsoft 팀 용 클라이언트 가져오기를](get-clients.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="066ef-223">For information about operating system requirements, see [Get clients for Microsoft Teams](get-clients.md).</span></span>
