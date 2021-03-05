---
title: 게스트 액세스 및 외부 액세스를 사용하여 조직 외부 사용자와 공동 작업
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Priority
description: 외부 액세스(페더레이션) 및 게스트 액세스를 사용하여 Microsoft Teams에서 외부 조직의 사용자와 통화, 채팅, 검색 및 추가하는 방법을 알아봅니다.
ms.openlocfilehash: 10ce0e7f89872a7fda842871d17f8bd06481193f
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461048"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a><span data-ttu-id="d0b59-103">게스트 액세스 및 외부 액세스를 사용하여 조직 외부 사용자와 공동 작업</span><span class="sxs-lookup"><span data-stu-id="d0b59-103">Use guest access and external access to collaborate with people outside your organization</span></span>

<span data-ttu-id="d0b59-104">조직 외부의 사용자와 의사 소통 및 공동 작업을 해야 하는 경우 Microsoft Teams에서는 다음 두 가지 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-104">When you need to communicate and collaborate with people outside your organization, Microsoft Teams has two options:</span></span>

- <span data-ttu-id="d0b59-105">**외부 액세스** - 다른 조직의 사용자를 찾고, 통화하고, 채팅할 수 있는 페더레이션 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-105">**External access** - A type of federation that allows users to find, call, and chat with people in other organizations.</span></span> <span data-ttu-id="d0b59-106">이러한 사용자는 게스트로 초대되지 않는 한 팀에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-106">These people cannot be added to teams unless they are invited as guests.</span></span>
- <span data-ttu-id="d0b59-107">**게스트 액세스** - 게스트 액세스를 통해 조직 외부의 사용자를 팀에 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-107">**Guest access** - Guest access allows you to invite people from outside your organization to join a team.</span></span> <span data-ttu-id="d0b59-108">초대된 사용자는 Azure Active Directory에서 게스트 계정을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-108">Invited people get a guest account in Azure Active Directory.</span></span>

<span data-ttu-id="d0b59-109">Teams를 사용하면 조직 외부의 사용자들을 모임에 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-109">Note that Teams allows you to invite people outside your organization to meetings.</span></span> <span data-ttu-id="d0b59-110">이 경우 외부 또는 게스트 액세스를 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-110">This does not require external or guest access to be configured.</span></span>

## <a name="external-access-federation"></a><span data-ttu-id="d0b59-111">외부 액세스(페더레이션)</span><span class="sxs-lookup"><span data-stu-id="d0b59-111">External access (federation)</span></span>

<span data-ttu-id="d0b59-112">Teams, 비즈니스용 Skype(온라인 또는온-프레미스) 또는 Skype를 사용하는 조직 외부 사용자와의 모임을 검색, 통화, 채팅, 설정해야 하는 경우 외부 액세스를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="d0b59-112">Set up external access if you need to find, call, chat, and set up meetings with people outside your organization who use Teams, Skype for Business (online or on premises) or Skype.</span></span> 

<span data-ttu-id="d0b59-113">기본적으로 Outlook 액세스는 모든 도메인에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-113">By default, external access is enabled for all domains.</span></span> <span data-ttu-id="d0b59-114">특정 도메인을 허용 또는 차단하거나 해제하여 외부 액세스를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-114">You can restrict external access by allowing or blocking specific domains or by turning it off.</span></span>

![외부 액세스 설정 스크린샷](media/external-access-federation-settings.png)

<span data-ttu-id="d0b59-116">외부 액세스를 구성하는 경우 [외부 액세스 관리](manage-external-access.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0b59-116">To configure external access, see [Manage external access](manage-external-access.md).</span></span> 

>[!NOTE]
><span data-ttu-id="d0b59-117">Microsoft Teams 무료 라이선스는 외부 액세스를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-117">Microsoft Teams free licenses do not support external access.</span></span>

## <a name="guest-access"></a><span data-ttu-id="d0b59-118">게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="d0b59-118">Guest access</span></span>

<span data-ttu-id="d0b59-119">게스트 액세스를 사용하여 조직 외부의 사람을 팀에 추가하여 채팅, 통화, 미팅, 파일 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-119">Use guest access to add a person from outside your organization to a team, where they can chat, call, meet, and collaborate on files.</span></span> <span data-ttu-id="d0b59-120">게스트는 기본 팀 구성원과 거의 동일한 모든 Teams 기능을 제공받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-120">A guest can be given nearly all the same Teams capabilities as a native team member.</span></span>

<span data-ttu-id="d0b59-121">게스트는 조직의 Azure Active Directory에 B2B 사용자로 추가되며 게스트 계정을 사용하여 Teams에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-121">Guests are added to your organization's Azure Active Directory as B2B users and must sign in to Teams using their guest account.</span></span> <span data-ttu-id="d0b59-122">즉, 조직에 로그인하기 위해 자신의 조직에서 로그아웃해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-122">This means that they may have to sign out of their own organization to sign in to your organization.</span></span>

<span data-ttu-id="d0b59-123">Teams에서 게스트 액세스를 구성하려면 [팀에서 게스트와 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0b59-123">To configure guest access for Teams, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="compare-external-and-guest-access"></a><span data-ttu-id="d0b59-124">외부 및 게스트 액세스 비교</span><span class="sxs-lookup"><span data-stu-id="d0b59-124">Compare external and guest access</span></span>

<span data-ttu-id="d0b59-125">다음 표에서는 외부 액세스(페더레이션) 사용과 게스트 사용 간의 차이점을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-125">The following tables show the differences between using external access (federation) and guests.</span></span> <span data-ttu-id="d0b59-126">두 경우 모두 조직 외부 사용자는 외부에 있는 사용자로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-126">In both cases, people outside your organization are identified to your users as being external.</span></span>

### <a name="things-your-users-can-do"></a><span data-ttu-id="d0b59-127">사용자가 할 수 있는 일</span><span class="sxs-lookup"><span data-stu-id="d0b59-127">Things your users can do</span></span>

| <span data-ttu-id="d0b59-128">사용자가 할 수 있음</span><span class="sxs-lookup"><span data-stu-id="d0b59-128">Users can</span></span> | <span data-ttu-id="d0b59-129">외부 액세스 사용자</span><span class="sxs-lookup"><span data-stu-id="d0b59-129">External access users</span></span> | <span data-ttu-id="d0b59-130">게스트</span><span class="sxs-lookup"><span data-stu-id="d0b59-130">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="d0b59-131">다른 조직에서 다른 사용자와 채팅</span><span class="sxs-lookup"><span data-stu-id="d0b59-131">Chat with someone in another organization</span></span> | <span data-ttu-id="d0b59-132">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-132">Yes</span></span> | <span data-ttu-id="d0b59-133">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-133">Yes</span></span> |
| <span data-ttu-id="d0b59-134">다른 조직에서 다른 사용자와 통화</span><span class="sxs-lookup"><span data-stu-id="d0b59-134">Call someone in another organization</span></span> | <span data-ttu-id="d0b59-135">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-135">Yes</span></span> | <span data-ttu-id="d0b59-136">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-136">Yes</span></span> |
| <span data-ttu-id="d0b59-137">다른 조직의 다른 사용자가 전화 또는 채팅을 할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d0b59-137">See if someone from another organization is available for call or chat</span></span> | <span data-ttu-id="d0b59-138">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-138">Yes</span></span> | <span data-ttu-id="d0b59-139">예<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-139">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="d0b59-140">다른 조직의 사용자 검색</span><span class="sxs-lookup"><span data-stu-id="d0b59-140">Search for people in other organizations</span></span> | <span data-ttu-id="d0b59-141">예<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-141">Yes<sup>2</sup></span></span> | <span data-ttu-id="d0b59-142">아니요</span><span class="sxs-lookup"><span data-stu-id="d0b59-142">No</span></span> |
| <span data-ttu-id="d0b59-143">파일 공유</span><span class="sxs-lookup"><span data-stu-id="d0b59-143">Share files</span></span> | <span data-ttu-id="d0b59-144">아니요</span><span class="sxs-lookup"><span data-stu-id="d0b59-144">No</span></span> | <span data-ttu-id="d0b59-145">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-145">Yes</span></span> |
| <span data-ttu-id="d0b59-146">다른 조직의 사용자 부재 중 메시지 보기</span><span class="sxs-lookup"><span data-stu-id="d0b59-146">See the out-of-office message of someone in another organization</span></span> | <span data-ttu-id="d0b59-147">아니요</span><span class="sxs-lookup"><span data-stu-id="d0b59-147">No</span></span> | <span data-ttu-id="d0b59-148">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-148">Yes</span></span> |
| <span data-ttu-id="d0b59-149">다른 조직의 사용자 차단</span><span class="sxs-lookup"><span data-stu-id="d0b59-149">Block someone in another organization</span></span>  | <span data-ttu-id="d0b59-150">아니요</span><span class="sxs-lookup"><span data-stu-id="d0b59-150">No</span></span> | <span data-ttu-id="d0b59-151">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-151">Yes</span></span> |
| <span data-ttu-id="d0b59-152">@멘션 사용</span><span class="sxs-lookup"><span data-stu-id="d0b59-152">Use @mentions</span></span> | <span data-ttu-id="d0b59-153">예<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-153">Yes<sup>3</sup></span></span> | <span data-ttu-id="d0b59-154">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-154">Yes</span></span> |

### <a name="things-people-outside-your-organization-can-do"></a><span data-ttu-id="d0b59-155">조직 외부 사용자가 할 수 있는 일</span><span class="sxs-lookup"><span data-stu-id="d0b59-155">Things people outside your organization can do</span></span>

| <span data-ttu-id="d0b59-156">조직 외부 사용자가 할 수 있음</span><span class="sxs-lookup"><span data-stu-id="d0b59-156">People outside your organization can</span></span> | <span data-ttu-id="d0b59-157">외부 액세스 사용자</span><span class="sxs-lookup"><span data-stu-id="d0b59-157">External access users</span></span> | <span data-ttu-id="d0b59-158">게스트</span><span class="sxs-lookup"><span data-stu-id="d0b59-158">Guests</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="d0b59-159">Teams 리소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="d0b59-159">Access Teams resources</span></span> | <span data-ttu-id="d0b59-160">아니요</span><span class="sxs-lookup"><span data-stu-id="d0b59-160">No</span></span> | <span data-ttu-id="d0b59-161">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-161">Yes</span></span> |
| <span data-ttu-id="d0b59-162">그룹 채팅에 추가하기</span><span class="sxs-lookup"><span data-stu-id="d0b59-162">Be added to a group chat</span></span> | <span data-ttu-id="d0b59-163">아니요</span><span class="sxs-lookup"><span data-stu-id="d0b59-163">No</span></span> | <span data-ttu-id="d0b59-164">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-164">Yes</span></span> |
| <span data-ttu-id="d0b59-165">모임에 초대하기</span><span class="sxs-lookup"><span data-stu-id="d0b59-165">Be invited to a meeting</span></span> | <span data-ttu-id="d0b59-166">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-166">Yes</span></span> | <span data-ttu-id="d0b59-167">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-167">Yes</span></span> |
| <span data-ttu-id="d0b59-168">개인 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="d0b59-168">Make private calls</span></span> | <span data-ttu-id="d0b59-169">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-169">Yes</span></span> | <span data-ttu-id="d0b59-170">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-170">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="d0b59-171">전화 접속 모임 참가자의 전화 번호 보기</span><span class="sxs-lookup"><span data-stu-id="d0b59-171">View the phone number for dial-in meeting participants</span></span> | <span data-ttu-id="d0b59-172">아니요<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-172">No<sup>4</sup></span></span> | <span data-ttu-id="d0b59-173">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-173">Yes</span></span> |
| <span data-ttu-id="d0b59-174">IP 비디오 사용</span><span class="sxs-lookup"><span data-stu-id="d0b59-174">Use IP video</span></span> | <span data-ttu-id="d0b59-175">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-175">Yes</span></span> | <span data-ttu-id="d0b59-176">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-176">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="d0b59-177">화면 공유 사용</span><span class="sxs-lookup"><span data-stu-id="d0b59-177">Use screen sharing</span></span> | <span data-ttu-id="d0b59-178">예<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-178">Yes<sup>3</sup></span></span> | <span data-ttu-id="d0b59-179">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-179">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="d0b59-180">모임 시작 사용</span><span class="sxs-lookup"><span data-stu-id="d0b59-180">Use meet now</span></span> | <span data-ttu-id="d0b59-181">아니요</span><span class="sxs-lookup"><span data-stu-id="d0b59-181">No</span></span> | <span data-ttu-id="d0b59-182">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-182">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="d0b59-183">보낸 메시지 편집</span><span class="sxs-lookup"><span data-stu-id="d0b59-183">Edit sent messages</span></span> | <span data-ttu-id="d0b59-184">예<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-184">Yes<sup>3</sup></span></span> | <span data-ttu-id="d0b59-185">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-185">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="d0b59-186">보낸 메시지 삭제</span><span class="sxs-lookup"><span data-stu-id="d0b59-186">Delete sent messages</span></span> | <span data-ttu-id="d0b59-187">예<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-187">Yes<sup>3</sup></span></span> | <span data-ttu-id="d0b59-188">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-188">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="d0b59-189">대화에서 Giphy 사용</span><span class="sxs-lookup"><span data-stu-id="d0b59-189">Use Giphy in conversation</span></span> | <span data-ttu-id="d0b59-190">예<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-190">Yes<sup>3</sup></span></span> | <span data-ttu-id="d0b59-191">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-191">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="d0b59-192">대화에서 밈 사용</span><span class="sxs-lookup"><span data-stu-id="d0b59-192">Use memes in conversation</span></span> | <span data-ttu-id="d0b59-193">예<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-193">Yes<sup>3</sup></span></span> | <span data-ttu-id="d0b59-194">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-194">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="d0b59-195">대화에서 스티커 사용</span><span class="sxs-lookup"><span data-stu-id="d0b59-195">Use stickers in conversation</span></span> | <span data-ttu-id="d0b59-196">예<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-196">Yes<sup>3</sup></span></span> | <span data-ttu-id="d0b59-197">예<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-197">Yes<sup>5</sup></span></span> |
| <span data-ttu-id="d0b59-198">현재 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-198">Presence is displayed</span></span> | <span data-ttu-id="d0b59-199">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-199">Yes</span></span> | <span data-ttu-id="d0b59-200">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-200">Yes</span></span> |
| <span data-ttu-id="d0b59-201">@멘션 사용</span><span class="sxs-lookup"><span data-stu-id="d0b59-201">Use @mentions</span></span> | <span data-ttu-id="d0b59-202">예<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="d0b59-202">Yes<sup>3</sup></span></span> | <span data-ttu-id="d0b59-203">예</span><span class="sxs-lookup"><span data-stu-id="d0b59-203">Yes</span></span> |

<br>

<span data-ttu-id="d0b59-204"><sup>1</sup> 사용자가 게스트로 추가되어 있고 게스트 계정으로 로그인되어 있는 경우 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-204"><sup>1</sup> Provided that the user has been added as a guest and is signed with the guest account.</span></span><br>
<span data-ttu-id="d0b59-205"><sup>2</sup> 전자 메일 또는 SIP(Session Initiation Protocol) 주소만 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-205"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="d0b59-206"><sup>3</sup> 서로 다른 두 조직의 Teams 전용 사용자에게 Teams 전용 1:1 채팅이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-206"><sup>3</sup> Supported for 1:1 chat for Teams Only to Teams Only users from two different organizations.</span></span> <br>
<span data-ttu-id="d0b59-207"><sup>4</sup> 기본적으로 외부 참가자는 전화 접속 참가자의 전화 번호를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0b59-207"><sup>4</sup> By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="d0b59-208">이러한 전화 번호의 프라이버시를 유지하려면 **입장/종료** **알림** 유형에 대해 톤을 선택하십시오(이로 인해 Teams가 번호를 읽을 수 없음).</span><span class="sxs-lookup"><span data-stu-id="d0b59-208">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span> <span data-ttu-id="d0b59-209">자세한 내용은 [Microsoft Teams에서 모임에 대한 입장 및 퇴장 알림 켜기 혹은 끄기](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="d0b59-209">To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md).</span></span> <br>
<span data-ttu-id="d0b59-210"><sup>5</sup> 기본적으로 허용되지만 Teams 관리자가 해제할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="d0b59-210"><sup>5</sup> Allowed by default, but can be turned off by the Teams admin</span></span>

## <a name="related-topics"></a><span data-ttu-id="d0b59-211">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d0b59-211">Related topics</span></span>

[<span data-ttu-id="d0b59-212">Teams의 외부 액세스</span><span class="sxs-lookup"><span data-stu-id="d0b59-212">External access in Teams</span></span>](manage-external-access.md)

[<span data-ttu-id="d0b59-213">Teams의 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="d0b59-213">Guest access in Teams</span></span>](guest-access.md)

