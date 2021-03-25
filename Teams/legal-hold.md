---
title: 법적 보류에 Microsoft Teams 사용자 또는 팀을 추가합니다.
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
description: 보안 준수 센터를 사용하여 Microsoft Teams 사용자 또는 팀을 법적 보류에 & 데이터 요구 사항에 따라 법적 보류가 필요한 사항에 대해 알아보는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f2f269d75a7bf8bd97165329d2ae6b006b940f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112304"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="ddcf3-103">법적 보류에 Microsoft Teams 사용자 또는 팀을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="ddcf3-104">소송에 대한 합리적인 기대가 있는 경우 조직은 사건과 관련된 Teams 채팅 메시지를 포함하여 ESI(전자적으로 저장된 정보)를 보존해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-104">When a reasonable expectation of litigation exists, organizations are required to preserve electronically stored information (ESI), including Teams chat messages that are relevant to the case.</span></span> <span data-ttu-id="ddcf3-105">조직은 특정 토픽 또는 특정 개인과 관련된 모든 메시지를 보존해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-105">Organizations may need to preserve all messages related to a specific topic or for certain individuals.</span></span> <span data-ttu-id="ddcf3-106">이 문서에서는 Microsoft Teams의 법적 보류(M365 공간에서 구현 보류를 해결하기 위해 [eDiscovery 사례 관리:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)콘텐츠 위치 보류를 검토하세요.)에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-106">This article will cover legal hold in Microsoft Teams (To address hold implementation across the M365 space, please review [Manage eDiscovery cases: Place content locations on hold](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).).</span></span>

> [!NOTE]
> <span data-ttu-id="ddcf3-107">2020년 2월에는 개인 채널에 법적 보류 또는 사례 보관을 사용하도록 설정했습니다(개인 채널 채팅은 사용자 사서함에 저장되고, 일반 채널 채팅은 팀의 그룹 사서함에 저장됩니다).</span><span class="sxs-lookup"><span data-stu-id="ddcf3-107">In February 2020, we enabled legal hold or case hold on private channels (private channel chats are stored in user mailboxes, normal channel chats are stored in a Team's group mailbox).</span></span> <span data-ttu-id="ddcf3-108">사용자 사서함에 대한 법적 보류가 이미 있는 경우 보류 정책은 이제 해당 사서함에 저장된 개인 채널 메시지에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-108">If there is already a legal hold in place for a user mailbox, the hold policy will now automatically apply to private channel messages stored in that mailbox.</span></span> <span data-ttu-id="ddcf3-109">관리자가 이 기능을 켜는 데 필요한 추가 작업이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-109">There is no further action needed for an admin to turn this on.</span></span> <span data-ttu-id="ddcf3-110">개인 채널에서 공유되는 파일의 법적 보류도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-110">Legal hold of files shared in private channels is also supported.</span></span>

<span data-ttu-id="ddcf3-111">Microsoft Teams 내에서 전체 팀 또는 선택 사용자를 보류하거나 법적 보류를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-111">Within Microsoft Teams, an entire team or select users can be put on hold or legal hold.</span></span> <span data-ttu-id="ddcf3-112">이렇게 하면 해당 팀에서 교환된 모든 메시지(개인 채널 포함) 또는 해당 개인이 교환한 메시지는 조직의 규정 준수 관리자 또는 Teams 관리자가 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-112">Doing that will make sure that all messages that were exchanged in those teams (including private channels) or messages exchanged by those individuals are discoverable by the organization’s compliance managers or Teams Admins.</span></span>

> [!NOTE]
> <span data-ttu-id="ddcf3-113">사용자를 보류 중이면 그룹이 자동으로 보류되거나 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-113">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

<span data-ttu-id="ddcf3-114">사용자 또는 팀을 법적 보류로 설정하는 경우:</span><span class="sxs-lookup"><span data-stu-id="ddcf3-114">To put a user or a team on legal hold:</span></span>

1. <span data-ttu-id="ddcf3-115">보안 & [준수 센터로 이동합니다.](https://go.microsoft.com/fwlink/?linkid=854628)</span><span class="sxs-lookup"><span data-stu-id="ddcf3-115">Navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628).</span></span> <span data-ttu-id="ddcf3-116">새 사례를 만들 때 사서함 또는 사이트를 보류할 수 있는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-116">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

2. <span data-ttu-id="ddcf3-117">eDiscovery 또는 Advanced eDiscovery로 이동하고 "사례 만들기"를 클릭하여 사례를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-117">Go to eDiscovery or Advanced eDiscovery and create a case by clicking "Create a case".</span></span> <span data-ttu-id="ddcf3-118">사례가 만들어지면 을 를 를 를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-118">Once the case is created, open it.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ddcf3-119">![Microsoft Teams eDiscovery 탭이 선택되어 사례 만들기 단추가 표시됩니다.](media/LegalHold1.png)</span><span class="sxs-lookup"><span data-stu-id="ddcf3-119">![Microsoft Teams eDiscovery tab is selected, showing the Create a case button.](media/LegalHold1.png)</span></span>

3. <span data-ttu-id="ddcf3-120">위쪽 메뉴에서 "보류" 섹션으로 이동하고 "+ 만들기"를 클릭하여 보류를 만드세요.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-120">Go to the "Holds" section from the top menu and click "+ Create" to create a hold.</span></span> <span data-ttu-id="ddcf3-121">사용자 또는 팀을 보류하면 해당 사용자 또는 메시지에 의해 교환된 모든 메시지가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-121">Putting a user or a team on hold saves all the messages exchanged by those users or messages.</span></span> <span data-ttu-id="ddcf3-122">새 사례를 만들 때 사서함 또는 사이트를 보류할 수 있는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-122">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ddcf3-123">![선택된 보류 탭과 아래 만들기 단추를 보여주는 이미지입니다.](media/LegalHold2.png)</span><span class="sxs-lookup"><span data-stu-id="ddcf3-123">![An image showing the Holds tab selected, and the Create button underneath.](media/LegalHold2.png)</span></span>

   1. <span data-ttu-id="ddcf3-124">**보류의 이름을 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="ddcf3-124">**Name your hold**.</span></span> <span data-ttu-id="ddcf3-125">만들 보류에 대한 설명이 있는 고유한 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-125">Select a descriptive and unique name for the hold you are going to create.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="ddcf3-126">![이 스크린샷은 보류 탭의 이름과 만드는 보류에 대한 설명과 이름에 입력할 수 있는 이름을 보여줍니다.](media/LegalHold3.png)</span><span class="sxs-lookup"><span data-stu-id="ddcf3-126">![This screenshot shows the Name your hold tab, where you can enter in a name and description for the hold you are creating.](media/LegalHold3.png)</span></span>

    2. <span data-ttu-id="ddcf3-127">**위치를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="ddcf3-127">**Choose location**.</span></span> <span data-ttu-id="ddcf3-128">사용자 또는 전체 팀에 보류를 적용할지 여부를 선택하세요(현재는 개별 채널에 보류를 적용할 수 없습니다).</span><span class="sxs-lookup"><span data-stu-id="ddcf3-128">Choose whether you want the hold to be applied on a user or on an entire Team (hold cannot be applied on individual channels for now).</span></span> <span data-ttu-id="ddcf3-129">참고: 사용자가 보류 중이면 1:1 채팅, 1:다 또는 그룹 채팅 또는 채널 대화(개인 채널 포함)에서 보낸 메시지를 포함하여 모든 메시지가 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-129">Note: if a user is on hold, all their messages would be on hold, including whatever they sent in a 1:1 chat, 1:many or group chat, or a channel conversation (including private channels).</span></span>
  
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="ddcf3-130">![여기에 새 보류 만들기의 위치 선택 섹션이 있습니다. 여기서 Microsoft Teams를 비롯한 어떤 M365 옵션에 대해 결정을 내릴 수 있습니다. 보류가 적용될 수 있습니다.](media/LegalHold4.png)</span><span class="sxs-lookup"><span data-stu-id="ddcf3-130">![Here we have the Choose locations section of Create a new hold, where you can make decisions on what M365 options, including Microsoft Teams, you wish the hold to apply to.](media/LegalHold4.png)</span></span>

    3. <span data-ttu-id="ddcf3-131">**쿼리 만들기** 입니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-131">**Create Query**.</span></span> <span data-ttu-id="ddcf3-132">보류 정책에서 더 세분화하려는 경우 보류를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-132">You can customize the hold if you want more granularity in the hold policy.</span></span> <span data-ttu-id="ddcf3-133">예를 들어 검색할 키워드를 지정하거나 보류가 적용될 때 만족해야 하는 조건을 더 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-133">For example, you can specify keywords to look for, or you can add more conditions, that would need to be satisfied for the hold to take effect.</span></span>
    
    4. <span data-ttu-id="ddcf3-134">**조직에 게시하기** 전에 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-134">**Review your settings** before publishing it to your organization.</span></span>

<span data-ttu-id="ddcf3-135">법적 보류가 설정된 후 [Teams eDiscovery](eDiscovery-investigation.md) 문서 다음의 보류 정책에 의해 보존된 모든 콘텐츠를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-135">After the legal hold has been set, you can discover all the content retained by any hold policy following the [Teams eDiscovery](eDiscovery-investigation.md) article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddcf3-136">사용자 또는 그룹이 보류 중이면 모든 메시지 복사본이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-136">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="ddcf3-137">예를 들어 사용자가 채널에 메시지를 게시한 다음 메시지를 수정한 경우 보류 시나리오에서 두 메시지 복사본이 모두 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-137">For example, if a user posted a message in a channel and then modified the message, in a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="ddcf3-138">법적 보존이 없는 경우 최신 메시지만 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-138">Without the legal hold in-place, only the latest message is retained.</span></span>

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a><span data-ttu-id="ddcf3-139">Teams 콘텐츠를 보존하기 위해 법적 보존을 위해 게시할 콘텐츠 위치</span><span class="sxs-lookup"><span data-stu-id="ddcf3-139">Content locations to place on legal hold to preserve Teams content</span></span>

<span data-ttu-id="ddcf3-140">유용한 가이드로 다음 표를 사용하여 다양한 유형의 Teams 콘텐츠를 보존하기 위해 법적 보존을 위해 어떤 콘텐츠 위치(예: 사서함 또는 사이트)를 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-140">As a helpful guide, you can use the following table to understand what content location (such as a mailbox or site) to place on legal hold to preserve different types of Teams content.</span></span>

|<span data-ttu-id="ddcf3-141">시나리오</span><span class="sxs-lookup"><span data-stu-id="ddcf3-141">Scenario</span></span>  |<span data-ttu-id="ddcf3-142">콘텐츠 위치</span><span class="sxs-lookup"><span data-stu-id="ddcf3-142">Content location</span></span>  |
|---------|---------|
|<span data-ttu-id="ddcf3-143">사용자에 대한 Teams 채팅(예: 1:1 채팅, 1:N 그룹 채팅 및 개인 채널 대화)</span><span class="sxs-lookup"><span data-stu-id="ddcf3-143">Teams chats for a user (for example, 1:1 chats, 1:N group chats, and private channel conversations)</span></span>     |<span data-ttu-id="ddcf3-144">사용자 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-144">User mailbox.</span></span>         |
|<span data-ttu-id="ddcf3-145">Teams 채널 채팅(개인 채널 제외)</span><span class="sxs-lookup"><span data-stu-id="ddcf3-145">Teams channel chats (excluding private channels)</span></span>    |<span data-ttu-id="ddcf3-146">팀에 사용되는 그룹 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-146">Group mailbox used for the team.</span></span>         |
|<span data-ttu-id="ddcf3-147">Teams 파일 콘텐츠(예: Wiki 콘텐츠 및 파일)</span><span class="sxs-lookup"><span data-stu-id="ddcf3-147">Teams file content (for example, Wiki content and files)</span></span>     |<span data-ttu-id="ddcf3-148">팀에서 사용하는 SharePoint 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-148">SharePoint site used by the team.</span></span>         |
|<span data-ttu-id="ddcf3-149">Teams 개인 채널 파일</span><span class="sxs-lookup"><span data-stu-id="ddcf3-149">Teams private channel files</span></span>     |<span data-ttu-id="ddcf3-150">개인 채널에 대한 전용 SharePoint 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-150">Dedicated SharePoint site for private channels.</span></span>     |
|<span data-ttu-id="ddcf3-151">사용자의 개인 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="ddcf3-151">User's private content</span></span>     |<span data-ttu-id="ddcf3-152">사용자의 비즈니스용 OneDrive 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-152">The user's OneDrive for Business account.</span></span>         |
|<span data-ttu-id="ddcf3-153">채팅의 카드 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="ddcf3-153">Card content in chats</span></span>|<span data-ttu-id="ddcf3-154">1:1 채팅, 1:N 그룹 채팅 및 개인 채널 대화 또는 채널 메시지의 카드 콘텐츠에 대한 그룹 사서함에 대한 사용자 사서함입니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-154">User mailbox for 1:1 chats, 1:N group chats, and private channel conversations or group mailbox for card content in channel messages.</span></span> <span data-ttu-id="ddcf3-155">자세한 내용은 [eDiscovery](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)보류 만들기의 "카드 콘텐츠 보존" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-155">For more information, see the "Preserve card content" section in [Create an eDiscovery hold](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).</span></span>
||||

> [!NOTE]
> <span data-ttu-id="ddcf3-156">개인 채널에서 통신을 유지하려면 사용자 사서함(개인 채널 사용자)을 보류하고 eDiscovery 도구를 사용하여 검색할 때 해당 사용자의 사서함에서 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-156">To retain communication in private channels, you need to put the user mailboxes ( Private channel users) on hold and when using eDiscovery tool to search, you should search in that user’s mailbox.</span></span> <span data-ttu-id="ddcf3-157">앞에서 말한 대로 개인 채널 채팅은 팀의 그룹 사서함이 아닌 사용자 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-157">As was stated earlier, private channel chats are stored in user mailboxes, not in group mailbox of a Team.</span></span>

<span data-ttu-id="ddcf3-158">Microsoft 365의 팀이 아닌 영역에 대한 이 항목에서 자세히 읽으면 [eDiscovery 사례 관리:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)콘텐츠 위치 보류 를 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddcf3-158">If you want to read further on this topic for non-Teams areas in Microsoft 365, you should review [Manage eDiscovery cases: Place content locations on hold](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).</span></span>