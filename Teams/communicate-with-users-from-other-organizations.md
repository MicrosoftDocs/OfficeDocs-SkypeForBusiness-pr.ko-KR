---
title: 다른 조직의 사용자와 통화하고 채팅
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 외부 액세스 (페더레이션) 및 게스트 액세스를 사용하여 Microsoft Teams에서 외부 조직의 사용자와 통화, 채팅, 검색 및 추가하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 401b63aad667d355516486deb6f056e0995dbe26
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031814"
---
<a name="call-and-chat-with-users-from-other-organizations-in-microsoft-teams"></a><span data-ttu-id="a8414-103">Microsoft Teams에서 다른 조직의 사용자와 통화 및 채팅</span><span class="sxs-lookup"><span data-stu-id="a8414-103">Call and chat with users from other organizations in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="a8414-p101">조직 외부의 사용자와 통신하고 공동 작업을 해야 하는 경우 Microsoft Teams에서 이 작업을 수행하는 두 가지 방법을 제공합니다. 첫째로는 **외부 액세스**(페더레이션)를 통해 다른 도메인의 사용자를 찾고, 사용자와 통화하고, 채팅할 수 있습니다. 두 번째로는 **게스트 액세스** 를 통해 개인들을 그들의 전자 메일 주소를 사용하여 게스트로 팀에 추가할 수 있습니다. 조직의 다른 사용자와 마찬가지로 게스트와 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-p101">When you need to communicate and collaborate with people outside your organization, Microsoft Teams gives you two different ways to make that happen. The first – **external access** (federation) – lets  you find, call, and chat with users in other domains (for example, contoso.com). The second – **guest access** – lets you add individuals to your teams, as guests, using their email address. You can collaborate with guests as you would with any other users in your organization.</span></span>

<span data-ttu-id="a8414-108">원하는 경우에는 외부 액세스와 게스트 액세스를 모두 사용할 수 있습니다. 이들은 서로 방해되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-108">You can use both external access and guest access if you want - one doesn't preclude the other.</span></span>

<span data-ttu-id="a8414-109">높은 수준에서 선택하는 방법 (자세한 비교를 위해 [외부 및 게스트 액세스 비교](#compare-external-and-guest-access)로 이동하세요):</span><span class="sxs-lookup"><span data-stu-id="a8414-109">At a high level, here’s how to choose (for a detailed comparison, jump down to [Compare external and guest access](#compare-external-and-guest-access)):</span></span>

## <a name="external-access"></a><span data-ttu-id="a8414-110">외부 액세스</span><span class="sxs-lookup"><span data-stu-id="a8414-110">External access</span></span>

<span data-ttu-id="a8414-p102">다른 도메인의 외부 사용자가 찾기, 통화, 채팅 및 모임을 설정할 수 있도록 하는 솔루션이 필요한 경우, **외부 액세스**(페더레이션)를 사용합니다. 외부 사용자는 조직의 팀 또는 팀 리소스에 액세스할 수 없습니다. 아직 비즈니스용 Skype(온라인 또는 온-프레미스)나 Skype(2020년 초 제공 예정)를 계속 사용하고 있는 조직 외부의 사용자와 통신하려는 경우 외부 액세스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-p102">Use **external access** (federation) when you need a solution that lets external users in other domains find, call, chat, and set up meetings with you. External users have no access to your organization's teams or team resources. Choose external access when you want to communicate with users outside your organization who are still on Skype for Business (online or on premises) or Skype (coming in early 2020).</span></span> 

<span data-ttu-id="a8414-p103">외부 액세스는 Teams에서 기본적으로 사용하도록 설정되어 있습니다. 즉, 조직에서 모든 외부 도메인과 통신할 수 있습니다. Teams 관리자는 이 기능을 해제하거나 포함할(또는 제외할) 도메인을 지정할 수 있습니다. 자세한 내용은 [외부 액세스 관리](manage-external-access.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8414-p103">External access is turned on by default in Teams, which means your org can communicate with all external domains. The Teams admin can turn it off or specify which domains to include (or exclude). To learn more, read [Manage external access](manage-external-access.md).</span></span> 

<span data-ttu-id="a8414-117">외부 사용자가 팀과 채널에 액세스할 수 있도록 하려면 [게스트 액세스](#guest-access)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-117">If you want external users to have access to teams and channels, [guest access](#guest-access) might be a better way to go.</span></span> 


## <a name="guest-access"></a><span data-ttu-id="a8414-118">게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="a8414-118">Guest access</span></span>

<span data-ttu-id="a8414-p104">**게스트 액세스** 를 사용하여 개인 사용자(도메인에 상관없이)를 팀에 추가할 수 있으며, 팀에서 Microsoft 365나 Office 365 앱(예: Word, Excel 또는 PowerPoint)을 사용하여 채팅, 통화, 모임 및 조직 파일을(SharePoint 또는 비즈니스용 OneDrive에 저장된) 공동 작업할 수 있습니다. 게스트 사용자에게는 기본 팀 구성원과 거의 동일한 Teams의 모든 기능이 제공될 수 있습니다. 자세한 내용은 [Teams의 게스트 액세스](guest-access.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8414-p104">Use **guest access** to add an individual user (regardless of domain) to a team, where they can chat, call, meet, and collaborate on organization files (stored in SharePoint or OneDrive for Business), using Microsoft 365 or Office 365 apps such as Word, Excel, or PowerPoint. A guest user can be given nearly all the same Teams capabilities as a native team member. To learn more, read [Guest access in Teams](guest-access.md).</span></span>

- <span data-ttu-id="a8414-122">게스트는 조직의 Active Directory에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-122">Guests are added to your organization’s Active Directory.</span></span>
- <span data-ttu-id="a8414-p105">게스트와 통신하려면 게스트는 게스트 계정을 사용하여 Teams에 로그인해야 합니다. 즉, 게스트는 자신의 Teams 계정에서 로그아웃하고 귀하의 Teams 계정에 로그인하거나, 계정이 동일한 경우 조직을 전환해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-p105">To communicate with a guest, the guest has to be signed in to Teams using their guest account. This means that a guest may have to sign out of their own Teams account to sign in to your Teams account, or switch organizations if it's the same account.</span></span>
- <span data-ttu-id="a8414-125">게스트 사용자는 외부 액세스 (페더레이션) 사용자 보다 Teams에서 더 많은 리소스 (예: 파일, 팀 및 채널)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-125">Guest users have access to more resources in Teams - such as files, teams, and channels - than external-access (federated) users.</span></span>
- <span data-ttu-id="a8414-p106">Teams 관리자는 Teams 관리 센터에서 게스트가 수행할 수 있는(혹은 없는) 모든 것을 제어합니다. 자세한 내용은 [게스트 액세스 관리](manage-guests.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8414-p106">The Teams admin controls everything that a guest can (or can’t) do in the Teams admin center. To learn more, read [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="a8414-128">조직에서 게스트 액세스를 설정할 준비가 되었으면 [팀에서 게스트와 협력](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-128">If you're ready to turn on guest access in your organization, start with the [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>


## <a name="compare-external-and-guest-access"></a><span data-ttu-id="a8414-129">외부 및 게스트 액세스 비교</span><span class="sxs-lookup"><span data-stu-id="a8414-129">Compare external and guest access</span></span>

| <span data-ttu-id="a8414-130">기능</span><span class="sxs-lookup"><span data-stu-id="a8414-130">Feature</span></span> | <span data-ttu-id="a8414-131">외부 액세스 사용자</span><span class="sxs-lookup"><span data-stu-id="a8414-131">External access users</span></span> | <span data-ttu-id="a8414-132">게스트 액세스 사용자</span><span class="sxs-lookup"><span data-stu-id="a8414-132">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="a8414-133">사용자는 다른 회사의 사용자와 채팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-133">User can chat with someone in another company</span></span> | <span data-ttu-id="a8414-134">예</span><span class="sxs-lookup"><span data-stu-id="a8414-134">Yes</span></span> |<span data-ttu-id="a8414-135">예</span><span class="sxs-lookup"><span data-stu-id="a8414-135">Yes</span></span> |
| <span data-ttu-id="a8414-136">사용자는 다른 회사의 사용자와 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-136">User can call someone in another company</span></span> | <span data-ttu-id="a8414-137">예</span><span class="sxs-lookup"><span data-stu-id="a8414-137">Yes</span></span> | <span data-ttu-id="a8414-138">예</span><span class="sxs-lookup"><span data-stu-id="a8414-138">Yes</span></span> |
| <span data-ttu-id="a8414-139">사용자는 다른 회사의 다른 사용자가 전화를 하거나 채팅을 할 수 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-139">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="a8414-140">예</span><span class="sxs-lookup"><span data-stu-id="a8414-140">Yes</span></span> | <span data-ttu-id="a8414-141">예<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a8414-141">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="a8414-142">사용자가 외부 테넌트에서 사용자를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-142">User can search for users across external tenants</span></span> | <span data-ttu-id="a8414-143">예<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a8414-143">Yes<sup>2</sup></span></span> | <span data-ttu-id="a8414-144">아니요</span><span class="sxs-lookup"><span data-stu-id="a8414-144">No</span></span> |
| <span data-ttu-id="a8414-145">사용자는 파일을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-145">User can share files</span></span> | <span data-ttu-id="a8414-146">아니요</span><span class="sxs-lookup"><span data-stu-id="a8414-146">No</span></span> | <span data-ttu-id="a8414-147">예</span><span class="sxs-lookup"><span data-stu-id="a8414-147">Yes</span></span> |
| <span data-ttu-id="a8414-148">사용자는 Teams 자원에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-148">User can access Teams resources</span></span> | <span data-ttu-id="a8414-149">아니요</span><span class="sxs-lookup"><span data-stu-id="a8414-149">No</span></span> | <span data-ttu-id="a8414-150">예</span><span class="sxs-lookup"><span data-stu-id="a8414-150">Yes</span></span> |
| <span data-ttu-id="a8414-151">그룹 채팅에 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-151">User can be added to a group chat</span></span> | <span data-ttu-id="a8414-152">아니요</span><span class="sxs-lookup"><span data-stu-id="a8414-152">No</span></span> | <span data-ttu-id="a8414-153">예</span><span class="sxs-lookup"><span data-stu-id="a8414-153">Yes</span></span> |
| <span data-ttu-id="a8414-154">사용자를 모임에 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-154">User can be invited to a meeting</span></span> | <span data-ttu-id="a8414-155">예</span><span class="sxs-lookup"><span data-stu-id="a8414-155">Yes</span></span> | <span data-ttu-id="a8414-156">예</span><span class="sxs-lookup"><span data-stu-id="a8414-156">Yes</span></span> |
| <span data-ttu-id="a8414-157">외부 사용자와의 채팅에 다른 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-157">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="a8414-158">아니요<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a8414-158">No<sup>3</sup></span></span> | <span data-ttu-id="a8414-159">해당 없음</span><span class="sxs-lookup"><span data-stu-id="a8414-159">N/A</span></span> |
| <span data-ttu-id="a8414-160">사용자는 외부 대상으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-160">User is identified as an external party</span></span> | <span data-ttu-id="a8414-161">예</span><span class="sxs-lookup"><span data-stu-id="a8414-161">Yes</span></span> | <span data-ttu-id="a8414-162">예</span><span class="sxs-lookup"><span data-stu-id="a8414-162">Yes</span></span> |
| <span data-ttu-id="a8414-163">현재 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-163">Presence is displayed</span></span> | <span data-ttu-id="a8414-164">예</span><span class="sxs-lookup"><span data-stu-id="a8414-164">Yes</span></span> | <span data-ttu-id="a8414-165">예</span><span class="sxs-lookup"><span data-stu-id="a8414-165">Yes</span></span> |
| <span data-ttu-id="a8414-166">부재 중 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-166">Out of office message is shown</span></span> | <span data-ttu-id="a8414-167">아니요</span><span class="sxs-lookup"><span data-stu-id="a8414-167">No</span></span> | <span data-ttu-id="a8414-168">예</span><span class="sxs-lookup"><span data-stu-id="a8414-168">Yes</span></span> |
| <span data-ttu-id="a8414-169">개별 사용자를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-169">Individual user can be blocked</span></span> | <span data-ttu-id="a8414-170">아니요</span><span class="sxs-lookup"><span data-stu-id="a8414-170">No</span></span> | <span data-ttu-id="a8414-171">예</span><span class="sxs-lookup"><span data-stu-id="a8414-171">Yes</span></span> |
| <span data-ttu-id="a8414-172">@멘션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-172">@mentions are supported</span></span> | <span data-ttu-id="a8414-173">예<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a8414-173">Yes<sup>4</sup></span></span> | <span data-ttu-id="a8414-174">예</span><span class="sxs-lookup"><span data-stu-id="a8414-174">Yes</span></span> |
| <span data-ttu-id="a8414-175">개인 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="a8414-175">Make private calls</span></span> | <span data-ttu-id="a8414-176">예</span><span class="sxs-lookup"><span data-stu-id="a8414-176">Yes</span></span> | <span data-ttu-id="a8414-177">예</span><span class="sxs-lookup"><span data-stu-id="a8414-177">Yes</span></span> |
| <span data-ttu-id="a8414-178">전화 접속 모임 참가자의 전화 번호 보기</span><span class="sxs-lookup"><span data-stu-id="a8414-178">View the phone number for dial-in meeting participants</span></span> | <span data-ttu-id="a8414-179">아니요<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="a8414-179">No<sup>5</sup></span></span> | <span data-ttu-id="a8414-180">예</span><span class="sxs-lookup"><span data-stu-id="a8414-180">Yes</span></span> |
| <span data-ttu-id="a8414-181">IP 비디오 허용</span><span class="sxs-lookup"><span data-stu-id="a8414-181">Allow IP video</span></span> | <span data-ttu-id="a8414-182">예</span><span class="sxs-lookup"><span data-stu-id="a8414-182">Yes</span></span> | <span data-ttu-id="a8414-183">예</span><span class="sxs-lookup"><span data-stu-id="a8414-183">Yes</span></span> |
| <span data-ttu-id="a8414-184">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="a8414-184">Screen sharing mode</span></span> | <span data-ttu-id="a8414-185">예<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a8414-185">Yes<sup>4</sup></span></span> | <span data-ttu-id="a8414-186">예</span><span class="sxs-lookup"><span data-stu-id="a8414-186">Yes</span></span> |
| <span data-ttu-id="a8414-187">모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="a8414-187">Allow meet now</span></span> | <span data-ttu-id="a8414-188">아니요</span><span class="sxs-lookup"><span data-stu-id="a8414-188">No</span></span> | <span data-ttu-id="a8414-189">예</span><span class="sxs-lookup"><span data-stu-id="a8414-189">Yes</span></span> |
| <span data-ttu-id="a8414-190">보낸 메시지 편집</span><span class="sxs-lookup"><span data-stu-id="a8414-190">Edit sent messages</span></span> | <span data-ttu-id="a8414-191">예<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a8414-191">Yes<sup>4</sup></span></span> | <span data-ttu-id="a8414-192">예</span><span class="sxs-lookup"><span data-stu-id="a8414-192">Yes</span></span> |
| <span data-ttu-id="a8414-193">보낸 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-193">Can delete sent messages</span></span> | <span data-ttu-id="a8414-194">예<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a8414-194">Yes<sup>4</sup></span></span> | <span data-ttu-id="a8414-195">예</span><span class="sxs-lookup"><span data-stu-id="a8414-195">Yes</span></span> |
| <span data-ttu-id="a8414-196">대화에서 Giphy 사용</span><span class="sxs-lookup"><span data-stu-id="a8414-196">Use Giphy in conversation</span></span> | <span data-ttu-id="a8414-197">예<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a8414-197">Yes<sup>4</sup></span></span> | <span data-ttu-id="a8414-198">예</span><span class="sxs-lookup"><span data-stu-id="a8414-198">Yes</span></span> |
| <span data-ttu-id="a8414-199">대화에서 밈 사용</span><span class="sxs-lookup"><span data-stu-id="a8414-199">Use memes in conversation</span></span> | <span data-ttu-id="a8414-200">예<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a8414-200">Yes<sup>4</sup></span></span> | <span data-ttu-id="a8414-201">예</span><span class="sxs-lookup"><span data-stu-id="a8414-201">Yes</span></span> |
| <span data-ttu-id="a8414-202">대화에서 스티커 사용</span><span class="sxs-lookup"><span data-stu-id="a8414-202">Use stickers in conversation</span></span> | <span data-ttu-id="a8414-203">예<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a8414-203">Yes<sup>4</sup></span></span> | <span data-ttu-id="a8414-204">예</span><span class="sxs-lookup"><span data-stu-id="a8414-204">Yes</span></span> |
||||

<span data-ttu-id="a8414-205"><sup>1</sup> 사용자가 게스트로 추가되어 있고 게스트 테넌트에 게스트로 로그인되어 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="a8414-205"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="a8414-206"><sup>2</sup> 전자 메일 또는 SIP(Session Initiation Protocol) 주소만 해당.</span><span class="sxs-lookup"><span data-stu-id="a8414-206"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="a8414-207"><sup>3</sup> 외부 (페더레이션) 채팅은 1:1만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-207"><sup>3</sup> External (federated) chat is 1:1 only.</span></span><br>
<span data-ttu-id="a8414-208"><sup>4</sup> Teams의 1:1 채팅은 Teams에서만, 다른 두 조직의 사용자만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8414-208"><sup>4</sup> Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations.</span></span> <br>
<span data-ttu-id="a8414-p107"><sup>5</sup> 기본적으로 외부 참가자는 전화 접속 참가자의 전화 번호를 볼 수 없습니다. 이러한 전화 번호에 대한 개인 정보 보호를 유지하려면 **입장/나가기 알림 유형** 에 대한 **톤** 을 선택합니다(이러한 경우 Teams에서 해당 숫자가 읽혀지지 않도록 방지). 자세한 내용은 [Microsoft Teams에서 모임에 대한 입장 및 퇴장 알림 공지 설정 및 해제](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a8414-p107"><sup>5</sup> By default, external participants can't see the phone numbers of dialed-in participants. If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams). To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a8414-212">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a8414-212">Related topics</span></span>

[<span data-ttu-id="a8414-213">Teams의 외부 액세스</span><span class="sxs-lookup"><span data-stu-id="a8414-213">External access in Teams</span></span>](manage-external-access.md)

[<span data-ttu-id="a8414-214">Teams의 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="a8414-214">Guest access in Teams</span></span>](guest-access.md)

