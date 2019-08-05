---
title: 비즈니스용 Skype 하이브리드 또는 온-프레미스 배포에서 팀으로 업그레이드-Microsoft 팀
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 비즈니스용 Skype 하이브리드 또는 온-프레미스 배포에서 팀으로 업그레이드 하기 위한 고려 사항
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 731a6b30fe2476d180198e88f83e80f24c8e8227
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "36185219"
---
<span data-ttu-id="e4993-103">![여행 다이어그램 업그레이드, 배포 및 구현 강조] (media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계")</span><span class="sxs-lookup"><span data-stu-id="e4993-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e4993-104">이 문서는 업그레이드 여행 배포 및 구현 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="e4993-105">계속 하기 전에 다음 활동을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="e4993-106">프로젝트 이해 관계자 참여</span><span class="sxs-lookup"><span data-stu-id="e4993-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="e4993-107">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="e4993-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="e4993-108">비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해</span><span class="sxs-lookup"><span data-stu-id="e4993-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="e4993-109">업그레이드 여행 선택</span><span class="sxs-lookup"><span data-stu-id="e4993-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="e4993-110">환경 준비</span><span class="sxs-lookup"><span data-stu-id="e4993-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="e4993-111">조직 준비</span><span class="sxs-lookup"><span data-stu-id="e4993-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="e4993-112">파일럿 수행</span><span class="sxs-lookup"><span data-stu-id="e4993-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a><span data-ttu-id="e4993-113">비즈니스용 Skype 하이브리드 또는 온-프레미스 배포에서 팀으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="e4993-113">Upgrade to Teams from a Skype for Business hybrid or on-premises deployment</span></span>

<span data-ttu-id="e4993-114">비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포 하 고 조직이 여러 공존 모드를 사용 하 여 선택적으로 팀으로 업그레이드 하려는 경우이 문서의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="e4993-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="e4993-115">첫 번째 단계는 Office 365 테 넌 트와 하이브리드 연결을 설정한 다음 사용자를 비즈니스용 Skype Online으로 이동 하 고 적절 한 공존 및 업그레이드 모드를 할당 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e4993-116">비즈니스용 Skype Online은 2021 년 7 월 31 일에 만료 되며, 그 이후에는 더 이상 접근성 또는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="e4993-117">조직의 혜택 실현을 최대화 하 고 업그레이드를 구현 하는 데 적절 한 시간을 확보 하려면 지금 Microsoft 팀으로 여행을 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="e4993-118">성공적으로 업그레이드 하면 기술 및 사용자의 준비가 정렬 되므로 Microsoft 팀으로 여행을 이동할 때이 가이드의 지침을 활용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="e4993-119">1 단계: 하이브리드 연결 배포</span><span class="sxs-lookup"><span data-stu-id="e4993-119">Step 1: Deploy hybrid connectivity</span></span> 

<span data-ttu-id="e4993-120">사용자를 팀으로 업그레이드 하기 위한 주요 전제 조건은 하이브리드 연결을 배포 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-120">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="e4993-121">여기에는 기존 비즈니스용 Skype 또는 Lync 배포에 새 외부 연결을 배포 하거나 Office 365 테 넌 트에서 하이브리드 관계를 구성 하는 작업이 포함 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-121">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span> 

<span data-ttu-id="e4993-122">자세한 내용은 비즈니스용 [Skype 서버와 비즈니스용 Skype Online 간 하이브리드 연결 배포](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e4993-122">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="e4993-123">2 단계: 비즈니스용 Skype Online으로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="e4993-123">Step 2: Move users to Skype for Business Online</span></span> 

<span data-ttu-id="e4993-124">하이브리드 설정을 완료 한 후에는 비즈니스용 Skype Online으로 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-124">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span> 

<span data-ttu-id="e4993-125">자세한 내용은 [온-프레미스에서 비즈니스용 Skype Online으로 사용자 이동을](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e4993-125">For more information, see [Move users from on premises to Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span> 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="e4993-126">3 단계: 공존 및 업그레이드 모드 지정</span><span class="sxs-lookup"><span data-stu-id="e4993-126">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="e4993-127">사용자를 비즈니스용 Skype Online으로 이동한 후에는 조직이 선택한 업그레이드의 여행에 따라 적절 한 공존 모드를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-127">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="e4993-128">자세한 내용은 [공존 및 업그레이드 설정](https://aka.ms/SkypeToTeams-SetCoexistence) 및 TeamsUpgradePolicy 설정 ( [마이그레이션 및 공존 관리](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e4993-128">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="e4993-129">비즈니스용 skype 서버 2019 및 향후 비즈니스용 Skype Server 2015의 누적 업데이트를 사용 하 여 2 단계 (비즈니스용 Skype Online으로 사용자 이동)와 3 단계 (사용자를 팀으로 업그레이드)를 한 번에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-129">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="e4993-130">자세한 내용은 비즈니스용 Skype 서버 2019이 출시 된 후에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-130">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="e4993-131">전화 시스템 및 팀 업그레이드</span><span class="sxs-lookup"><span data-stu-id="e4993-131">Phone System and Teams upgrade</span></span>

<span data-ttu-id="e4993-132">Skype for Business 하이브리드 배포를 통화 요금제를 사용 하는 전화 시스템으로 전환 하는 경우, Microsoft는 전화 번호 포팅를 완료 했다고 가정 하 고, 사용자를 업그레이드 하는 경우 팀은 인바운드 PSTN 통화를 팀으로 자동 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-132">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="e4993-133">통화 요금제를 사용할 수 없는 경우에는 엔터프라이즈 음성 배포를 Microsoft 전화 시스템 다이렉트 라우팅으로 전환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4993-133">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="e4993-134">사용자를 팀으로 업그레이드 하려면 [전화 시스템 다이렉트 라우팅에 대 한 추가 고려 사항을](2-envision-make-my-service-decisions-direct-routing.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e4993-134">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
