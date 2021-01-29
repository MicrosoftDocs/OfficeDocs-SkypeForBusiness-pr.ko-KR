---
title: Microsoft Teams의 공개 미리 보기
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft Teams의 공개 미리 보기에 대해 자세히 알아보세요. 새로운 기능을 사용해 보고 피드백을 제공해 주십시오.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 6a8d677b4acd56e6de5681d40a1e1aa69008a1ad
ms.sourcegitcommit: 6262deaede6f25b17624d7468eff7a2863eeacf7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50043962"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="c299b-104">Microsoft Teams 공개 미리 보기</span><span class="sxs-lookup"><span data-stu-id="c299b-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="c299b-p102">미리 보기에 포함된 기능은 완전하지 않을 수 있으며, 일반에 정식으로 공개되기 전에 변경될 수 있습니다. 단지 평가 및 탐색 용도로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="c299b-p103">Microsoft Teams의 공개 미리 보기는 Teams에서 릴리스되지 않은 기능에 대한 조기 액세스를 제공합니다. 미리 보기를 사용하여 예정된 기능을 탐색하고 테스트할 수 있습니다. 당사는 또한 공개 미리 보기의 모든 기능에 대한 피드백을 환영합니다. Teams 사용자별로 공개 미리 보기를 사용하도록 설정했으므로 전체 조직에 영향을 미칠 걱정을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.</span></span>

<span data-ttu-id="c299b-111">Teams 공개 미리 보기에서 사용할 수 있는 항목의 목록은 [Office 현재 채널(미리 보기) 릴리스 정보](https://docs.microsoft.com/officeupdates/current-channel-preview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c299b-111">For a list of what's available in the Teams public preview, visit [Release Notes for Office Current Channel (Preview)](https://docs.microsoft.com/officeupdates/current-channel-preview).</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="c299b-112">업데이트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="c299b-112">Set the Update policy</span></span>

<span data-ttu-id="c299b-113">사용자별로 공개 미리 보기를 사용하도록 설정하였고 공개 미리 보기를 설정하는 옵션은 관리자 정책에서 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-113">Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="c299b-114">업데이트 정책은 Teams 앱의 시험판 또는 미리 보기 기능을 볼 수 있는 Teams 및 Office 미리 보기 사용자를 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-114">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="c299b-115">전역(조직 전체의 기본값) 정책을 사용하고 사용자 지정하거나 특정 지역 사용자를 위한 맞춤 정책을 하나 이상 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-115">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="c299b-116">정책은 전역 정책을 덮어쓰지 않으므로 특정 사용자에게 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-116">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="c299b-117">관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-117">Sign in to the admin center.</span></span>
2. <span data-ttu-id="c299b-118">**Teams**>**업데이트 정책** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-118">Select **Teams**>**Update policies**.</span></span>

   ![정책 업데이트 옵션 선택](media/updatePolicies.png)

3. <span data-ttu-id="c299b-120">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-120">Select **Add**.</span></span>
4. <span data-ttu-id="c299b-121">업데이트 정책에 이름을 지정하고, 설명을 추가하고, **미리 보기 기능 표시** 를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-121">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="c299b-122">`CsTeamsUpdateManagementPolicy` cmdlet을 사용하는 PowerShell을 사용하여 정책을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-122">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="c299b-123">공개 미리 보기 사용</span><span class="sxs-lookup"><span data-stu-id="c299b-123">Enable public preview</span></span>

<span data-ttu-id="c299b-124">데스크톱 혹은 웹 클라이언트에서 공개 미리 보기를 사용하도록 설정하려면 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-124">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="c299b-125">프로필을 선택하여 Teams 메뉴를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-125">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="c299b-126">**정보** → **개발자 미리 보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-126">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="c299b-127">**개발자 미리 보기로 전환** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c299b-127">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c299b-128">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c299b-128">Related topics</span></span>

[<span data-ttu-id="c299b-129">공개 개발자 미리 보기</span><span class="sxs-lookup"><span data-stu-id="c299b-129">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)

