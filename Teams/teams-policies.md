---
title: Microsoft 팀에서 팀 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 조직에서 팀 정책을 사용 하 고 관리 하 여 팀과 채널에서 사용자가 수행할 수 있는 작업을 제어 하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 9ed0bd3aadcde76835bb3d435429785ceaf562a2
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938147"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="f3638-103">Microsoft 팀에서 팀 정책 관리</span><span class="sxs-lookup"><span data-stu-id="f3638-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="f3638-104">관리자는 Microsoft 팀에서 팀 정책을 사용 하 여 팀과 채널에서 조직의 사용자가 수행할 수 있는 작업을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="f3638-105">예를 들어 사용자가 검색 결과 및 팀 갤러리에서 비공개 팀을 검색 하도록 허용할지 여부와 사용자가 개인 채널을 만들 수 있도록 허용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="f3638-106">**Teams**  >  Microsoft 팀 관리 센터에서 팀**팀 정책** 으로 이동해 서 팀 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f3638-107">전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="f3638-108">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="f3638-109">전역 정책을 편집 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="f3638-110">전역 정책을 편집 하거나 정책을 할당 한 후 변경 내용을 적용 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="f3638-111">사용자 지정 팀 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f3638-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="f3638-112">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀**  >  **팀 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="f3638-113">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-113">Click **Add**.</span></span>
3. <span data-ttu-id="f3638-114">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-114">Enter a name and description for the policy.</span></span>

    ![팀 정책 설정 스크린샷](media/teams-policies.png)
4. <span data-ttu-id="f3638-116">원하는 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-116">Choose the settings that you want:</span></span>

- <span data-ttu-id="f3638-117">**비공개 팀 검색** (비공개 미리 보기):<a name="discoverteams"> </a> 사용자가 검색 결과 및 팀 갤러리에서 비공개 팀을 검색할 수 있도록 하려면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-117">**Discover private teams** (in private preview):<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="f3638-118">**개인 채널 만들기**: <a name="createchannels"> </a>이 설정을 사용 하면 사용자가 개인 채널을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-118">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="f3638-119">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-119">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="f3638-120">팀 정책 편집</span><span class="sxs-lookup"><span data-stu-id="f3638-120">Edit a teams policy</span></span>

<span data-ttu-id="f3638-121">만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-121">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="f3638-122">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀**  >  **팀 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-122">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="f3638-123">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-123">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="f3638-124">원하는 설정을 켜거나 끈 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3638-124">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="f3638-125">사용자에 게 사용자 지정 팀 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f3638-125">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="f3638-126">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f3638-126">Related topics</span></span>

[<span data-ttu-id="f3638-127">Teams에서 비공개 팀의 검색 관리</span><span class="sxs-lookup"><span data-stu-id="f3638-127">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)

[<span data-ttu-id="f3638-128">팀의 비공개 채널</span><span class="sxs-lookup"><span data-stu-id="f3638-128">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="f3638-129">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f3638-129">Assign policies to your users in Teams</span></span>](assign-policies.md)
