---
title: 팀 정책 관리 Microsoft Teams
author: cichur
ms.author: v-cichur
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: 조직에서 팀 정책을 사용 및 관리하여 사용자가 팀 및 채널에서 할 수 있는 작업을 제어하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 81541c08ac963f0bcef18ba589b2341915c20d5d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094208"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="339bb-103">팀 정책 관리 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="339bb-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="339bb-104">관리자는 조직의 팀 정책을 사용하여 Microsoft Teams 및 채널에서 조직의 사용자가 할 수 있는 작업을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="339bb-105">예를 들어 사용자가 개인 채널을 만들 수 있는지 여부를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-105">For example, you can set whether users are allowed to create private channels.</span></span>

<span data-ttu-id="339bb-106">관리 센터에서 Teams Teams 관리 Microsoft Teams  >   관리합니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="339bb-107">전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="339bb-108">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="339bb-109">전역 정책을 편집하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="339bb-110">전역 정책을 편집하거나 정책을 할당한 후 변경 내용이 적용될 수 있는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="339bb-111">사용자 지정 팀 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="339bb-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="339bb-112">관리 센터의 왼쪽 탐색에서 Microsoft Teams 정책 Teams  >  **Teams 로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="339bb-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="339bb-113">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-113">Click **Add**.</span></span>
3. <span data-ttu-id="339bb-114">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-114">Enter a name and description for the policy.</span></span>

    ![팀 정책 설정 스크린샷](media/teams-policies.png)
4. <span data-ttu-id="339bb-116">사용자가 개인 채널을  <a name="createchannels"></a> 만들 수 있도록 허용할지 여부에 따라 개인 채널 만들기를 켜거나 끄습니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-116">Turn on or turn off **Create private channels**, <a name="createchannels"> </a> depending on whether you want to allow users to create private channels.</span></span>

5. <span data-ttu-id="339bb-117">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-117">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="339bb-118">팀 정책 편집</span><span class="sxs-lookup"><span data-stu-id="339bb-118">Edit a teams policy</span></span>

<span data-ttu-id="339bb-119">전역 정책 또는 만든 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-119">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="339bb-120">관리 센터의 왼쪽 탐색에서 Microsoft Teams 정책 Teams  >  **Teams 로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="339bb-120">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="339bb-121">정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="339bb-121">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="339bb-122">원하는 설정을 켜거나 끄고 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="339bb-122">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="339bb-123">사용자에게 사용자 지정 팀 정책 할당</span><span class="sxs-lookup"><span data-stu-id="339bb-123">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="339bb-124">관련 항목</span><span class="sxs-lookup"><span data-stu-id="339bb-124">Related topics</span></span>

[<span data-ttu-id="339bb-125">Teams</span><span class="sxs-lookup"><span data-stu-id="339bb-125">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="339bb-126">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="339bb-126">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="339bb-127">New-CsTeamsChannelsPolicy</span><span class="sxs-lookup"><span data-stu-id="339bb-127">New-CsTeamsChannelsPolicy</span></span>](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)