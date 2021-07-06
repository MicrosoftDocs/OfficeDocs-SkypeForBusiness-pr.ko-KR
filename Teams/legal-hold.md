---
title: 법적 Microsoft Teams 사용자 또는 팀을 법적 보류에 두기
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: 보안 Microsoft Teams 준수 센터를 사용하여 & 사용자 또는 팀을 법적 보류에 추가하고 데이터 요구 사항에 따라 법적 보류가 필요한 사항에 대해 알아보는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b78fba2a85cd45c07183ebc9df8016f16036dce5
ms.sourcegitcommit: e023c3023f49e196315e176ce346f0dc5825fa56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53275667"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="f4b73-103">법적 Microsoft Teams 사용자 또는 팀을 법적 보류에 두기</span><span class="sxs-lookup"><span data-stu-id="f4b73-103">Place a Microsoft Teams user or team on legal hold</span></span>

<span data-ttu-id="f4b73-104">소송에 대한 합리적인 기대가 있는 경우 조직은 사례와 관련된 채팅 메시지를 포함하여 ESI(전자 Teams 저장)를 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-104">When a reasonable expectation of litigation exists, organizations are required to preserve electronically stored information (ESI), including Teams chat messages that are relevant to the case.</span></span> <span data-ttu-id="f4b73-105">조직은 특정 토픽 또는 특정 개인과 관련된 모든 메시지를 보존해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-105">Organizations may need to preserve all messages related to a specific topic or for certain individuals.</span></span> <span data-ttu-id="f4b73-106">이 문서에서는 법적 보류를 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f4b73-106">This article will cover legal hold in Microsoft Teams.</span></span> <span data-ttu-id="f4b73-107">전체 콘텐츠에 Microsoft 365 [eDiscovery 보류](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds)만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4b73-107">To hold content across Microsoft 365, see [Create an eDiscovery hold](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds).</span></span>

> [!NOTE]
> <span data-ttu-id="f4b73-108">2020년 2월에는 개인 채널에 대한 법적 보류를 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-108">In February 2020, we turned on legal hold for private channels.</span></span> <span data-ttu-id="f4b73-109">개인 채널 채팅은 사용자 사서함에 저장되고 일반 채널 채팅은 사용자의 그룹 Teams 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-109">Private channel chats are stored in user mailboxes, while normal channel chats are stored in the Teams’ group mailbox.</span></span> <span data-ttu-id="f4b73-110">사용자 사서함에 대한 법적 보류가 이미 있는 경우 보류 정책은 이제 해당 사서함에 저장된 개인 채널 메시지에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-110">If there is already a legal hold in place for a user mailbox, the hold policy will now automatically apply to private channel messages stored in that mailbox.</span></span> <span data-ttu-id="f4b73-111">관리자가 이 기능을 켜는 데 필요한 추가 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-111">There is no further action needed for an admin to turn this on.</span></span> <span data-ttu-id="f4b73-112">개인 채널에서 공유되는 파일의 법적 보류도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-112">Legal hold of files shared in private channels is also supported.</span></span>

<span data-ttu-id="f4b73-113">이 Microsoft Teams 전체 팀 또는 선택 사용자를 법적 보류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-113">Within Microsoft Teams, an entire team or select users can be put on legal hold.</span></span> <span data-ttu-id="f4b73-114">이렇게 하면 해당 팀에서 교환된 모든 메시지(개인 채널 포함) 또는 해당 개인이 교환한 메시지는 조직의 규정 준수 관리자 또는 관리자에게 검색할 수 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-114">Doing that will make sure that all messages that were exchanged in those teams (including private channels) or messages exchanged by those individuals are discoverable by the organization's compliance managers or Teams Admins.</span></span>

> [!NOTE]
> <span data-ttu-id="f4b73-115">사용자를 보류 중이면 그룹이 자동으로 보류되거나 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-115">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>
> <span data-ttu-id="f4b73-116">활동 피드로 전송된 알림은 보류 중일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-116">Notifications sent in activity feed can't be placed on hold.</span></span>

<span data-ttu-id="f4b73-117">Core eDiscovery 사례에서 사용자 또는 팀을 법적으로 보류하는 경우:</span><span class="sxs-lookup"><span data-stu-id="f4b73-117">To put a user or a team on legal hold in a Core eDiscovery case:</span></span>

1. <span data-ttu-id="f4b73-118">를 [Microsoft 365 규정 준수 센터.](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="f4b73-118">Go to the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span> <span data-ttu-id="f4b73-119">새 사례를 만들 때 사서함 또는 사이트를 보류할 수 있는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-119">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

2. <span data-ttu-id="f4b73-120">**eDiscovery**  >  **Core로** 이동하여 사례 만들기 를 클릭하여 **사례를 만들 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f4b73-120">Go to **eDiscovery** > **Core** and create a case by clicking **Create a case**.</span></span> <span data-ttu-id="f4b73-121">대소문자 생성 후 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-121">After the case is created, open it.</span></span>
  
   ![Microsoft Teams eDiscovery 탭이 선택되어 사례 만들기 단추가 표시됩니다.](media/LegalHold1.png)

   > [!NOTE]
   > <span data-ttu-id="f4b73-123">또한 사용자 대소문자와 연결된 보류에 사용자를 Advanced eDiscovery 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-123">You can also place a user on a hold that's associated with an Advanced eDiscovery case.</span></span> <span data-ttu-id="f4b73-124">자세한 내용은 에서 보류 [Advanced eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/managing-holds)</span><span class="sxs-lookup"><span data-stu-id="f4b73-124">For more information, see [Manage holds in Advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).</span></span>

3. <span data-ttu-id="f4b73-125">위쪽 **메뉴의** 보류 탭으로 이동하고 만들기를 클릭하여 보류를 만드세요. </span><span class="sxs-lookup"><span data-stu-id="f4b73-125">Go to the **Holds** tab on the top menu and click **Create** to create a hold.</span></span> <span data-ttu-id="f4b73-126">사용자 또는 팀을 보류 중으로 배치하면 해당 사용자 또는 메시지에서 교환한 모든 메시지가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-126">Placing a user or a team on hold preserves all the messages exchanged by those users or messages.</span></span> <span data-ttu-id="f4b73-127">새 사례를 만들 때 사서함 또는 사이트를 보류할 수 있는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-127">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

   ![선택된 보류 탭과 아래 만들기 단추를 보여주는 이미지입니다.](media/LegalHold2.png)
    
    1. <span data-ttu-id="f4b73-129">**보류의 이름을 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="f4b73-129">**Name your hold**.</span></span> <span data-ttu-id="f4b73-130">만들 보류에 대한 설명이 있는 고유한 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-130">Select a descriptive and unique name for the hold you are going to create.</span></span>
  
       ![이 스크린샷은 보류 탭의 이름과 만드는 보류에 대한 설명과 이름에 입력할 수 있는 이름을 보여줍니다.](media/LegalHold3.png)

    1. <span data-ttu-id="f4b73-132">**위치를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="f4b73-132">**Choose location**.</span></span> <span data-ttu-id="f4b73-133">사용자 또는 전체 팀에 보류를 적용할지 여부를 선택하세요(현재는 개별 채널에 보류를 적용할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="f4b73-133">Choose whether you want the hold to be applied on a user or on an entire Team (hold cannot be applied on individual channels for now).</span></span> <span data-ttu-id="f4b73-134">참고: 사용자가 보류 중이면 1:1 채팅, 1:다 또는 그룹 채팅 또는 채널 대화(개인 채널 포함)에서 보낸 메시지를 포함하여 모든 메시지가 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-134">Note: if a user is on hold, all their messages would be on hold, including whatever they sent in a 1:1 chat, 1:many or group chat, or a channel conversation (including private channels).</span></span>
    <span data-ttu-id="f4b73-135">![여기에 새 보류 만들기의 위치 선택 섹션이 있습니다. 여기서 보류를 포함하여 M365 옵션을 Microsoft Teams 적용하기를 원합니다.](media/LegalHold4.png)</span><span class="sxs-lookup"><span data-stu-id="f4b73-135">![Here we have the Choose locations section of Create a new hold, where you can make decisions on what M365 options, including Microsoft Teams, you wish the hold to apply to.](media/LegalHold4.png)</span></span>

    2. <span data-ttu-id="f4b73-136">**쿼리 만들기** 입니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-136">**Create query**.</span></span> <span data-ttu-id="f4b73-137">보류 정책에서 더 세분화하려는 경우 보류를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-137">You can customize the hold if you want more granularity in the hold policy.</span></span> <span data-ttu-id="f4b73-138">예를 들어 검색할 키워드를 지정하거나 보류가 적용될 때 만족해야 하는 조건을 더 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-138">For example, you can specify keywords to look for, or you can add more conditions, that would need to be satisfied for the hold to take effect.</span></span>
    
    3. <span data-ttu-id="f4b73-139">**보류를 만들기** 전에 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-139">**Review your settings** before creating the hold.</span></span>

<span data-ttu-id="f4b73-140">법적 보류를 만든 후 보류 정책에 의해 보존된 콘텐츠를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-140">After the legal hold has been created, you can search the content retained by any hold policy.</span></span> <span data-ttu-id="f4b73-141">자세한 내용은 에서 [eDiscovery 조사 수행을 Teams.](eDiscovery-investigation.md)</span><span class="sxs-lookup"><span data-stu-id="f4b73-141">For more information, see [Conduct an eDiscovery investigation in Teams](eDiscovery-investigation.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4b73-142">사용자 또는 그룹이 보류 중이면 모든 메시지 복사본이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-142">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="f4b73-143">예를 들어 사용자가 채널에 메시지를 게시한 다음 메시지를 수정한 경우 보류 시나리오에서 두 메시지 복사본이 모두 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-143">For example, if a user posted a message in a channel and then modified the message, in a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="f4b73-144">법적 보존이 없는 경우 최신 메시지만 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-144">Without the legal hold in-place, only the latest message is retained.</span></span>

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a><span data-ttu-id="f4b73-145">콘텐츠 콘텐츠를 보존하기 위해 법적 보존에 Teams 위치</span><span class="sxs-lookup"><span data-stu-id="f4b73-145">Content locations to place on legal hold to preserve Teams content</span></span>

<span data-ttu-id="f4b73-146">유용한 가이드로 다음 표를 사용하여 다양한 유형의 콘텐츠를 보존하기 위해 법적 보존을 위해 어떤 콘텐츠 위치(예: 사서함 또는 사이트)를 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-146">As a helpful guide, you can use the following table to understand what content location (such as a mailbox or site) to place on legal hold to preserve different types of Teams content.</span></span>

|<span data-ttu-id="f4b73-147">시나리오</span><span class="sxs-lookup"><span data-stu-id="f4b73-147">Scenario</span></span>  |<span data-ttu-id="f4b73-148">콘텐츠 위치</span><span class="sxs-lookup"><span data-stu-id="f4b73-148">Content location</span></span>  |
|---------|---------|
|<span data-ttu-id="f4b73-149">Teams 채팅(예: 1:1 채팅, 1:N 그룹 채팅 및 개인 채널 대화)</span><span class="sxs-lookup"><span data-stu-id="f4b73-149">Teams chats for a user (for example, 1:1 chats, 1:N group chats, and private channel conversations)</span></span>     |<span data-ttu-id="f4b73-150">사용자 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-150">User mailbox.</span></span>         |
|<span data-ttu-id="f4b73-151">Teams 채팅(개인 채널 제외)</span><span class="sxs-lookup"><span data-stu-id="f4b73-151">Teams channel chats (excluding private channels)</span></span>    |<span data-ttu-id="f4b73-152">팀에 사용되는 그룹 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-152">Group mailbox used for the team.</span></span>         |
|<span data-ttu-id="f4b73-153">Teams 콘텐츠(예: Wiki 콘텐츠 및 파일)</span><span class="sxs-lookup"><span data-stu-id="f4b73-153">Teams file content (for example, Wiki content and files)</span></span>     |<span data-ttu-id="f4b73-154">SharePoint 사용하는 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-154">SharePoint site used by the team.</span></span>         |
|<span data-ttu-id="f4b73-155">Teams 채널 파일 저장</span><span class="sxs-lookup"><span data-stu-id="f4b73-155">Teams private channel files</span></span>     |<span data-ttu-id="f4b73-156">개인 SharePoint 전용 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-156">Dedicated SharePoint site for private channels.</span></span>     |
|<span data-ttu-id="f4b73-157">사용자의 개인 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="f4b73-157">User's private content</span></span>     |<span data-ttu-id="f4b73-158">사용자의 비즈니스용 OneDrive 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-158">The user's OneDrive for Business account.</span></span>         |
|<span data-ttu-id="f4b73-159">채팅의 카드 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="f4b73-159">Card content in chats</span></span>|<span data-ttu-id="f4b73-160">1:1 채팅, 1:N 그룹 채팅 및 개인 채널 대화 또는 채널 메시지의 카드 콘텐츠에 대한 그룹 사서함에 대한 사용자 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-160">User mailbox for 1:1 chats, 1:N group chats, and private channel conversations or group mailbox for card content in channel messages.</span></span> <span data-ttu-id="f4b73-161">자세한 내용은 [eDiscovery](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)보류 만들기의 "카드 콘텐츠 보존" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4b73-161">For more information, see the "Preserve card content" section in [Create an eDiscovery hold](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).</span></span>
||||

> [!NOTE]
> <span data-ttu-id="f4b73-162">개인 채널에서 통신을 유지하려면 사용자 사서함(개인 채널 사용자)을 보류하고 eDiscovery 도구를 사용하여 검색할 때 해당 사용자의 사서함에서 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-162">To retain communication in private channels, you need to put the user mailboxes ( Private channel users) on hold and when using eDiscovery tool to search, you should search in that user’s mailbox.</span></span> <span data-ttu-id="f4b73-163">앞에서 말한 대로 개인 채널 채팅은 팀의 그룹 사서함이 아닌 사용자 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-163">As was stated earlier, private channel chats are stored in user mailboxes, not in group mailbox of a Team.</span></span>

<span data-ttu-id="f4b73-164">이 항목에서 비영리 영역에 대한 자세한 내용을 Teams Microsoft 365 [eDiscovery 사례 관리:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)콘텐츠 위치 보류 를 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4b73-164">If you want to read further on this topic for non-Teams areas in Microsoft 365, you should review [Manage eDiscovery cases: Place content locations on hold](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).</span></span>
