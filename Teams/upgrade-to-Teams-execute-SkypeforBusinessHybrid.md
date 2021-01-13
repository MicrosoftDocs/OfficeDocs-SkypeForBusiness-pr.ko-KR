---
title: 비즈니스용 Skype 하이브리드 배포를 Teams로 업그레이드
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype 하이브리드 배포에서 Microsoft Teams로 조직을 업그레이드하는 방법을 배워보는 것이 좋습니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802348"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="4a0b8-103">비즈니스용 Skype 하이브리드 배포에서 Teams로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="4a0b8-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="4a0b8-104">![배포 및 구현 단계에 강조를 두는 업그레이드 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 강조를 두는 업그레이드 단계")</span><span class="sxs-lookup"><span data-stu-id="4a0b8-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="4a0b8-105">이 문서는 업그레이드 여정의 배포 및 구현 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="4a0b8-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="4a0b8-106">계속하기 전에 다음 활동을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0b8-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="4a0b8-107">프로젝트 관련자에 참여</span><span class="sxs-lookup"><span data-stu-id="4a0b8-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="4a0b8-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="4a0b8-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="4a0b8-109">비즈니스용 Skype 및 Teams의 공존 및 상호 연동성 이해</span><span class="sxs-lookup"><span data-stu-id="4a0b8-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="4a0b8-110">업그레이드 여정 선택</span><span class="sxs-lookup"><span data-stu-id="4a0b8-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="4a0b8-111">환경 준비</span><span class="sxs-lookup"><span data-stu-id="4a0b8-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="4a0b8-112">조직 준비</span><span class="sxs-lookup"><span data-stu-id="4a0b8-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="4a0b8-113">파일럿 수행</span><span class="sxs-lookup"><span data-stu-id="4a0b8-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="4a0b8-114">비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포하고 Microsoft 365 또는 Office 365 조직과의 하이브리드 배포에서 구성한 경우 조직에서 여러 공존 모드 또는 모든 기능을 사용하여 선택적으로 Teams로 업그레이드하려는 경우 이 문서의 지침을 따르하세요.</span><span class="sxs-lookup"><span data-stu-id="4a0b8-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="4a0b8-115">업그레이드 여정의 경우 사용자를 비즈니스용 Skype Online(아직 온라인에 없는 경우)으로 이동한 다음 적절한 공존 및 업그레이드 모드를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0b8-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="4a0b8-116">1단계: 비즈니스용 Skype Online으로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="4a0b8-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="4a0b8-117">이 단계는 현재 홈이 있는 On-프레미스 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0b8-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="4a0b8-118">이러한 사용자를 비즈니스용 Skype Online으로 이동하는 자세한 내용은 사용자를 -프레미스에서 비즈니스용 [Skype Online으로 이동을 참조하세요.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="4a0b8-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="4a0b8-119">2단계: 공존 및 업그레이드 모드 할당</span><span class="sxs-lookup"><span data-stu-id="4a0b8-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="4a0b8-120">사용자를 비즈니스용 Skype Online으로 이동한 후 조직에서 선택한 업그레이드 여정에 따라 적절한 공존 모드를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0b8-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="4a0b8-121">자세한 내용은 마이그레이션 [](https://aka.ms/SkypeToTeams-SetCoexistence) 및 공존 관리와 같은 공존 및 업그레이드 설정 및 [TeamsUpgradePolicy 설정을 참조하세요.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="4a0b8-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4a0b8-122">비즈니스용 Skype Server 2019 및 향후 비즈니스용 Skype Server 2015 누적 업데이트를 사용하면 1단계(사용자를 비즈니스용 Skype Online으로 이동) 및 2단계(사용자를 Teams로 업그레이드)를 한 단계로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0b8-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="4a0b8-123">비즈니스용 Skype Server 2019가 출시된 후 자세한 정보가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0b8-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="4a0b8-124">전화 시스템 및 Teams 업그레이드</span><span class="sxs-lookup"><span data-stu-id="4a0b8-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="4a0b8-125">비즈니스용 Skype 하이브리드 배포를 통화 요금제로 전화 시스템으로 전환하고 Microsoft는 PSTN(공용 전화망) 공급자가 되며 전화 번호 포터링을 완료했다고 생각하면 사용자를 Teams로 업그레이드하면 자동으로 인바운드 PSTN 통화가 Teams로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0b8-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="4a0b8-126">통화 계획을 사용할 수 없는 경우 또는 기존 PSTN 연결 공급자를 사용하려는 경우 엔터프라이즈 음성 배포 또는 기존 On-프레미스 배포 또는 Cloud Connector Edition을 사용하는 하이브리드 음성 배포를 Microsoft Phone System 직접 라우팅으로 전환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0b8-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="4a0b8-127">사용자를 Teams로 업그레이드하려면 전화 시스템 직접 라우팅에 대한 추가 고려 [사항을 참조합니다.](2-envision-make-my-service-decisions-direct-routing.md)</span><span class="sxs-lookup"><span data-stu-id="4a0b8-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
