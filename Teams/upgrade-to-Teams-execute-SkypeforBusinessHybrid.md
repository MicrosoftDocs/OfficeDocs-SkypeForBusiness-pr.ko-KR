---
title: 비즈니스용 Skype 하이브리드 배포를 Microsoft 팀으로 업그레이드 | PSTN
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 비즈니스용 Skype 하이브리드 배포에서 팀으로 업그레이드 하기 위한 고려 사항
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54a9f75e6f9e1d0465af56b49df86010697edbd3
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837078"
---
<span data-ttu-id="dc921-103">![배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계")</span><span class="sxs-lookup"><span data-stu-id="dc921-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="dc921-104">이 문서는 업그레이드 여행 배포 및 구현 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="dc921-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="dc921-105">계속 하기 전에 다음 활동을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc921-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="dc921-106">프로젝트 이해 관계자 참여</span><span class="sxs-lookup"><span data-stu-id="dc921-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="dc921-107">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="dc921-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="dc921-108">비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해</span><span class="sxs-lookup"><span data-stu-id="dc921-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="dc921-109">업그레이드 여행 선택</span><span class="sxs-lookup"><span data-stu-id="dc921-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="dc921-110">환경 준비</span><span class="sxs-lookup"><span data-stu-id="dc921-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="dc921-111">조직 준비</span><span class="sxs-lookup"><span data-stu-id="dc921-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="dc921-112">파일럿 수행</span><span class="sxs-lookup"><span data-stu-id="dc921-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="dc921-113">비즈니스용 Skype 하이브리드 배포에서 팀으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="dc921-113">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="dc921-114">비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포 하 고 Office 365 테 넌 트와 함께 하이브리드 배포에 구성한 경우이 문서의 지침을 따르고, 조직에서 여러 개의 앱을 사용 하 여 팀으로 업그레이드 하려고 합니다. 공존 모드 (또는 모두).</span><span class="sxs-lookup"><span data-stu-id="dc921-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="dc921-115">업그레이드 여행 중에는 사용자를 비즈니스용 Skype Online으로 이동 (아직 온라인 상태가 되지 않은 경우) 한 다음 적절 한 공존 및 업그레이드 모드를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc921-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren’t already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="dc921-116">1 단계: 비즈니스용 Skype Online으로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="dc921-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="dc921-117">이 단계는 현재 온-프레미스 상태인 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc921-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="dc921-118">이러한 사용자를 비즈니스용 Skype Online으로 이동 하는 방법에 대 한 자세한 내용은 온 [-프레미스에서 비즈니스용 Skype online으로 사용자 이동을](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc921-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="dc921-119">2 단계: 공존 및 업그레이드 모드 할당</span><span class="sxs-lookup"><span data-stu-id="dc921-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="dc921-120">사용자를 비즈니스용 Skype Online으로 이동한 후에는 조직이 선택한 업그레이드의 여행에 따라 적절 한 공존 모드를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc921-120">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="dc921-121">자세한 내용은 [공존 및 업그레이드 설정](https://aka.ms/SkypeToTeams-SetCoexistence) 및 TeamsUpgradePolicy 설정 ( [마이그레이션 및 공존 관리](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc921-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="dc921-122">비즈니스용 skype 서버 2019 및 향후 비즈니스용 Skype Server 2015의 누적 업데이트는 1 단계 (비즈니스용 Skype Online으로 사용자 이동)와 2 단계 (사용자를 팀으로 업그레이드)를 수행 하 여 한 번에 수행할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc921-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="dc921-123">자세한 내용은 비즈니스용 Skype 서버 2019이 출시 된 후에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc921-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="dc921-124">전화 시스템 및 팀 업그레이드</span><span class="sxs-lookup"><span data-stu-id="dc921-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="dc921-125">Skype for Business 하이브리드 배포를 통화 요금제를 사용 하는 전화 시스템으로 전환 하는 경우, Microsoft는 전화 번호 포팅를 완료 했다고 가정 하 고, 사용자를 업그레이드 하는 경우 팀은 인바운드 PSTN 통화를 팀으로 자동 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc921-125">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="dc921-126">통화 요금제를 사용할 수 없거나 기존 PSTN 연결 공급자를 사용 하려는 경우 엔터프라이즈 음성 배포 또는 기존 온-프레미스 배포 또는 클라우드 커넥터 에디션을 사용 하는 하이브리드 음성 배포로 전환 해야 합니다. Microsoft 전화 시스템 다이렉트 라우팅.</span><span class="sxs-lookup"><span data-stu-id="dc921-126">If Calling Plans isn’t available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="dc921-127">사용자를 팀으로 업그레이드 하려면 [전화 시스템 다이렉트 라우팅에 대 한 추가 고려 사항을](2-envision-make-my-service-decisions-direct-routing.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc921-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
