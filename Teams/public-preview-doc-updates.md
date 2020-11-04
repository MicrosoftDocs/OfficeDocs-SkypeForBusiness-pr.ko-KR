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
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft Teams의 공개 미리 보기에 대해 자세히 알아보세요. 새로운 기능을 사용해 보시고 피드백을 제공해 주십시오.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: a2b06c58396db0e8fdb976037696b7a782d581cd
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852189"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="58fba-104">Microsoft Teams 공개 미리 보기</span><span class="sxs-lookup"><span data-stu-id="58fba-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="58fba-105">미리 보기에 포함된 기능은 완전하지 않을 수 있으며, 일반에 정식으로 공개되기 전에 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-105">Features included in preview might not be complete, and might undergo changes before becoming available in the public release.</span></span> <span data-ttu-id="58fba-106">단지 평가 및 탐색 용도로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-106">They're provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="58fba-107">Microsoft Teams의 공개 미리 보기는 Teams에서 릴리스되지 않은 기능에 대한 조기 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-107">Public Preview for Microsoft Teams provides early access to unreleased features in Teams.</span></span> <span data-ttu-id="58fba-108">미리 보기를 사용하여 예정된 기능을 탐색하고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-108">Previews allow you to explore and test upcoming features.</span></span> <span data-ttu-id="58fba-109">당사는 또한 공개 미리 보기의 모든 기능에 대한 피드백을 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-109">We also welcome feedback on any feature in public previews.</span></span> <span data-ttu-id="58fba-110">모든 Teams 사용자에 대해 공개 미리 보기를 사용하도록 설정했으므로 전체 조직에 영향을 미칠 걱정을 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-110">Public preview is enabled each Teams user, so you don't need to worry about affecting your entire organization.</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="58fba-111">업데이트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="58fba-111">Set the Update policy</span></span>

 <span data-ttu-id="58fba-112">각 사용자에 대해 공개 미리 보기를 사용하도록 설정하였고 공개 미리 보기를 설정하는 옵션은 관리자 정책에서 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-112">Public preview is enabled for each user, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="58fba-113">업데이트 정책은 Teams 앱의 시험판 또는 미리 보기 기능을 볼 수 있는 Teams 및 Office 미리 보기 사용자를 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-113">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="58fba-114">전역(전제 조직의 기본) 정책을 사용하여 사용자 지정하거나 사용자에게 하나 이상의 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-114">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span>

1. <span data-ttu-id="58fba-115">관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-115">Sign in to the admin center.</span></span>
2. <span data-ttu-id="58fba-116">**Teams**>**업데이트 정책** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-116">Select **Teams**>**Update policies**.</span></span>

   ![정책 업데이트 옵션 선택](media/updatePolicies.png)

3. <span data-ttu-id="58fba-118">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-118">Select **Add**.</span></span>
4. <span data-ttu-id="58fba-119">업데이트 정책에 이름을 지정하고, 설명을 추가하고, **미리 보기 기능 표시** 를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-119">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="58fba-120">공개 미리 보기 사용</span><span class="sxs-lookup"><span data-stu-id="58fba-120">Enable public preview</span></span>

<span data-ttu-id="58fba-121">데스크톱 혹은 웹 클라이언트에서 공개 미리 보기를 사용하도록 설정하려면 다음 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-121">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="58fba-122">프로필을 선택하여 Teams 메뉴를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-122">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="58fba-123">**정보** → **개발자 미리 보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-123">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="58fba-124">**개발자 미리 보기로 전환** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="58fba-124">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="58fba-125">관련 항목</span><span class="sxs-lookup"><span data-stu-id="58fba-125">Related topics</span></span>

[<span data-ttu-id="58fba-126">공개 개발자 미리 보기</span><span class="sxs-lookup"><span data-stu-id="58fba-126">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)
