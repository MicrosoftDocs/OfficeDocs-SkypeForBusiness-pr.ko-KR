---
title: 법적 보류를 위해 Microsoft Teams 사용자 또는 팀에 추가
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
description: Security & 준수 센터를 사용하여 Microsoft Teams 사용자 또는 팀을 법적 보류에 추가하고 데이터 요구 사항에 따라 법적 보류가 필요한 사항을 알아보는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63d862cbdf8d31fc00a48849c85994bd878f0bbc
ms.sourcegitcommit: b6aeaa3d98c29bdc120db8ccfcb7ff2c11d246af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570837"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="73daf-103">법적 보류를 위해 Microsoft Teams 사용자 또는 팀에 추가</span><span class="sxs-lookup"><span data-stu-id="73daf-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="73daf-104">소송에 대한 합리적 기대가 있는 경우 조직은 사례와 관련된 Teams 채팅 메시지를 포함하여 ESI(전자적으로 저장된 정보)를 보존해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-104">When a reasonable expectation of litigation exists, organizations are required to preserve electronically stored information (ESI), including Teams chat messages that are relevant to the case.</span></span> <span data-ttu-id="73daf-105">조직은 특정 토픽 또는 특정 개인과 관련된 모든 메시지를 유지해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-105">Organizations may need to preserve all messages related to a specific topic or for certain individuals.</span></span> <span data-ttu-id="73daf-106">이 문서에서는 Microsoft Teams의 법적 보류에 대해 설명합니다(M365 공간에서 구현을 보류하기 위해 [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)사례 관리 검토: 콘텐츠 위치 보류.).</span><span class="sxs-lookup"><span data-stu-id="73daf-106">This article will cover legal hold in Microsoft Teams (To address hold implementation across the M365 space, please review [Manage eDiscovery cases: Place content locations on hold](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).).</span></span>

> [!NOTE]
> <span data-ttu-id="73daf-107">2020년 2월에 비공개 채널에서 법적 보류 또는 사례 보류를 설정했습니다(개인 채널 채팅은 사용자 사서함에 저장되고 일반 채널 채팅은 해당 Teams의 그룹 사서함에 저장).</span><span class="sxs-lookup"><span data-stu-id="73daf-107">In Feb 2020, we turned on legal hold or case hold on private channels (private channel chats are stored in user mailboxes, normal channel chats are stored in that Teams’ group mailboxes).</span></span> <span data-ttu-id="73daf-108">사용자 사서함에 대한 법적 보류가 이미 있는 경우 이제 해당 사서함에 저장된 개인 채널 메시지에 보류 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-108">If there is already a legal hold in place for a user mailbox, the hold policy will now automatically apply to private channel messages stored in that mailbox.</span></span> <span data-ttu-id="73daf-109">관리자가 이 기능을 설정하는 데 필요한 추가 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-109">There is no further action needed for an admin to turn this on.</span></span> <span data-ttu-id="73daf-110">비공개 채널에서 공유되는 파일의 법적 보유도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-110">Legal hold of files shared in private channels is also supported.</span></span>

<span data-ttu-id="73daf-111">Microsoft Teams 내에서 전체 팀 또는 선택 사용자가 보류 또는 법적 보류를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-111">Within Microsoft Teams, an entire team or select users can be put on hold or legal hold.</span></span> <span data-ttu-id="73daf-112">이렇게 하면 해당 팀에서 교환된 모든 메시지(비공개 채널 포함) 또는 해당 개인이 교환한 메시지를 조직의 규정 준수 관리자 또는 Teams 관리자가 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-112">Doing that will make sure that all messages that were exchanged in those teams (including private channels) or messages exchanged by those individuals are discoverable by the organization’s compliance managers or Teams Admins.</span></span>

> [!NOTE]
> <span data-ttu-id="73daf-113">사용자를 보류로 설정하면 그룹이 자동으로 보류되거나 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-113">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

<span data-ttu-id="73daf-114">사용자 또는 팀을 법적 보류에 추가하는 경우:</span><span class="sxs-lookup"><span data-stu-id="73daf-114">To put a user or a team on Legal Hold:</span></span>

1. <span data-ttu-id="73daf-115">Security & [준수 센터로 이동합니다.](https://go.microsoft.com/fwlink/?linkid=854628)</span><span class="sxs-lookup"><span data-stu-id="73daf-115">Navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628).</span></span> <span data-ttu-id="73daf-116">새 사례를 만들면 사서함 또는 사이트를 보류하는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-116">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

2. <span data-ttu-id="73daf-117">eDiscovery 또는 Advanced eDiscovery로 이동하고 "사례 만들기"를 클릭하여 사례를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-117">Go to eDiscovery or Advanced eDiscovery and create a case by clicking "Create a case".</span></span> <span data-ttu-id="73daf-118">사례가 만들어지면 열립니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-118">Once the case is created, open it.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="73daf-119">![Microsoft Teams eDiscovery 탭이 선택되어 사례 만들기 단추가 표시됩니다.](media/LegalHold1.png)</span><span class="sxs-lookup"><span data-stu-id="73daf-119">![Microsoft Teams eDiscovery tab is selected, showing the Create a case button.](media/LegalHold1.png)</span></span>

3. <span data-ttu-id="73daf-120">위쪽 메뉴에서 "보류" 섹션으로 이동하고 "+ 만들기"를 클릭하여 보류를 만드세요.</span><span class="sxs-lookup"><span data-stu-id="73daf-120">Go to the "Holds" section from the top menu and click "+ Create" to create a hold.</span></span> <span data-ttu-id="73daf-121">사용자 또는 팀을 보류하면 해당 사용자 또는 메시지에서 교환된 모든 메시지가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-121">Putting a user or a team on hold saves all the messages exchanged by those users or messages.</span></span> <span data-ttu-id="73daf-122">새 사례를 만들면 사서함 또는 사이트를 보류하는 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-122">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="73daf-123">![보류 탭이 선택된 이미지와 그 아래에 만들기 단추가 표시됩니다.](media/LegalHold2.png)</span><span class="sxs-lookup"><span data-stu-id="73daf-123">![An image showing the Holds tab selected, and the Create button underneath.](media/LegalHold2.png)</span></span>

   1. <span data-ttu-id="73daf-124">**보류 이름을 지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="73daf-124">**Name your hold**.</span></span> <span data-ttu-id="73daf-125">만들 보류에 대한 설명이 있는 고유한 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-125">Select a descriptive and unique name for the hold you are going to create.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="73daf-126">![이 스크린샷은 보류 탭의 이름과 생성 보류에 대한 설명을 입력할 수 있는 이름을 보여줍니다.](media/LegalHold3.png)</span><span class="sxs-lookup"><span data-stu-id="73daf-126">![This screenshot shows the Name your hold tab, where you can enter in a name and description for the hold you are creating.](media/LegalHold3.png)</span></span>

    2. <span data-ttu-id="73daf-127">**위치를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="73daf-127">**Choose location**.</span></span> <span data-ttu-id="73daf-128">사용자 또는 전체 팀에서 보류를 적용할지(현재는 개별 채널에 적용될 수 없습니다)를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="73daf-128">Choose whether you want the hold to be applied on a user or on an entire Team (hold cannot be applied on individual channels for now).</span></span> <span data-ttu-id="73daf-129">참고: 사용자가 보류 중이면 1:1 채팅, 1:다 또는 그룹 채팅 또는 채널 대화(개인 채널 포함)에서 보낸 모든 메시지를 포함하여 모든 메시지가 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-129">Note: if a user is on hold, all their messages would be on hold, including whatever they sent in a 1:1 chat, 1:many or group chat, or a channel conversation (including private channels).</span></span>
  
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="73daf-130">![여기서는 보류를 적용하고자 하는 Microsoft Teams를 비롯한 M365 옵션에 대해 결정을 내릴 수 있는 새 보류 만들기의 위치 선택 섹션이 있습니다.](media/LegalHold4.png)</span><span class="sxs-lookup"><span data-stu-id="73daf-130">![Here we have the Choose locations section of Create a new hold, where you can make decisions on what M365 options, including Microsoft Teams, you wish the hold to apply to.](media/LegalHold4.png)</span></span>

    3. <span data-ttu-id="73daf-131">**쿼리 만들기.**</span><span class="sxs-lookup"><span data-stu-id="73daf-131">**Create Query**.</span></span> <span data-ttu-id="73daf-132">보류 정책에서 더 세분화하려는 경우 보류를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-132">You can customize the hold if you want more granularity in the hold policy.</span></span> <span data-ttu-id="73daf-133">예를 들어 검색할 키워드를 지정하거나 보류가 적용될 때 충족해야 하는 조건을 더 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-133">For example, you can specify keywords to look for, or you can add more conditions, that would need to be satisfied for the hold to take effect.</span></span>
    
    4. <span data-ttu-id="73daf-134">**조직에 게시하기** 전에 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-134">**Review your settings** before publishing it to your organization.</span></span>

<span data-ttu-id="73daf-135">법적 보존이 설정되고 나면 [Teams eDiscovery](eDiscovery-investigation.md) 문서 다음에 보존 정책에 의해 보존되는 모든 콘텐츠를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-135">After the legal hold has been set, you can discover all the content retained by any hold policy following the [Teams eDiscovery](eDiscovery-investigation.md) article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73daf-136">사용자 또는 그룹이 보류된 경우 모든 메시지 복사본이 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-136">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="73daf-137">예를 들어 사용자가 채널에 메시지를 게시한 다음 메시지를 수정한 경우 보류 시나리오에서는 두 메시지 복사본이 모두 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-137">For example, if a user posted a message in a channel and then modified the message, in a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="73daf-138">법적 보존이 없는 경우 최신 메시지만 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-138">Without the legal hold in-place, only the latest message is retained.</span></span>

<span data-ttu-id="73daf-139">유용한 가이드로 아래 표를 사용하여 데이터 요구 사항에 따라 법적 보류에 배치해야 하는 사항을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-139">As a helpful guide, you can use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="73daf-140">시나리오</span><span class="sxs-lookup"><span data-stu-id="73daf-140">Scenario</span></span>  |<span data-ttu-id="73daf-141">보류할 것</span><span class="sxs-lookup"><span data-stu-id="73daf-141">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="73daf-142">**사용자에 의해 Microsoft Teams 채팅 콘텐츠(1:1 채팅, 1:다 또는 그룹 채팅, 비공개 채널 대화 등)**</span><span class="sxs-lookup"><span data-stu-id="73daf-142">**Microsoft Teams chat content by a user (on 1:1 chats, 1:many or group chats, private channel conversations, etc.)**</span></span>     |<span data-ttu-id="73daf-143">사용자 사서함</span><span class="sxs-lookup"><span data-stu-id="73daf-143">User mailbox</span></span>         |
|<span data-ttu-id="73daf-144">**Microsoft Teams 채널 채팅(비공개 채널 제외)**</span><span class="sxs-lookup"><span data-stu-id="73daf-144">**Microsoft Teams Channel chats (excluding private channels)**</span></span>    |<span data-ttu-id="73daf-145">팀에 사용되는 그룹 사서함</span><span class="sxs-lookup"><span data-stu-id="73daf-145">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="73daf-146">**Microsoft Teams 콘텐츠(예: Wiki, 파일)**</span><span class="sxs-lookup"><span data-stu-id="73daf-146">**Microsoft Teams content (for example, Wiki, Files)**</span></span>     |<span data-ttu-id="73daf-147">팀에서 사용하는 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="73daf-147">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="73daf-148">**Microsoft Teams 개인 채널 파일**</span><span class="sxs-lookup"><span data-stu-id="73daf-148">**Microsoft Teams Private Channel files**</span></span>     |<span data-ttu-id="73daf-149">비공개 전용 SharePoint 사이트</span><span class="sxs-lookup"><span data-stu-id="73daf-149">Dedicated SharePoint site for private</span></span>     |
|<span data-ttu-id="73daf-150">**사용자의 개인 콘텐츠**</span><span class="sxs-lookup"><span data-stu-id="73daf-150">**User's private content**</span></span>     |<span data-ttu-id="73daf-151">사용자의 비즈니스용 OneDrive 사이트</span><span class="sxs-lookup"><span data-stu-id="73daf-151">OneDrive for Business site of the user</span></span>         |
||||

> [!NOTE]
> <span data-ttu-id="73daf-152">개인 채널에서 통신을 유지하려면 사용자 사서함(개인 채널 사용자)을 보류하고 eDiscovery 도구를 사용하여 검색할 때 해당 사용자의 사서함에서 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-152">To retain communication in private channels, you need to put the user mailboxes ( Private channel users) on hold and when using eDiscovery tool to search, you should search in that user’s mailbox.</span></span> <span data-ttu-id="73daf-153">앞에서 말한 대로 비공개 채널 채팅은 팀의 그룹 사서함이 아닌 사용자 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-153">As was stated earlier, private channel chats are stored in user mailboxes, not in group mailbox of a Team.</span></span>

<span data-ttu-id="73daf-154">M365의 Teams가 아닌 영역에 대한 이 항목에 대해 자세히 읽으면 [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)사례 관리: 콘텐츠 위치 보류를 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73daf-154">If you want to read further on this topic for non-Teams areas in M365, you should review [Manage eDiscovery cases: Place content locations on hold](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).</span></span>
