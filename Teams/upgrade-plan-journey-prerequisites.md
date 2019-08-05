---
title: Microsoft 팀 필수 구성 요소 | 종속성 채택 업그레이드
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 이 지침을 사용 하 여 조직에서 팀을 배포 하기 위한 필수 구성 요소 및 환경 종속성에 대해 알아보세요.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbdb59bc5239b8982e330972188ec15527312d22
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "36183905"
---
<span data-ttu-id="d77d4-103">![여행 다이어그램 업그레이드, 기술 준비 단계 강조] (media/upgrade-banner-tech-readiness.png "기술 준비 단계에 중점을 두어 업그레이드 여행 단계")</span><span class="sxs-lookup"><span data-stu-id="d77d4-103">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="d77d4-104">이 문서는 사용자 준비 단계와 병행 하 여 완료 한 활동 인 업그레이드 여행에 대 한 기술 준비 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="d77d4-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="d77d4-105">계속 하기 전에 이전 단계에서 다음 활동을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77d4-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

- [<span data-ttu-id="d77d4-106">프로젝트 이해 관계자 참여</span><span class="sxs-lookup"><span data-stu-id="d77d4-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="d77d4-107">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="d77d4-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="d77d4-108">비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해</span><span class="sxs-lookup"><span data-stu-id="d77d4-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="d77d4-109">업그레이드 여행 선택</span><span class="sxs-lookup"><span data-stu-id="d77d4-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="d77d4-110">팀에 대 한 전제 조건 및 환경 종속성</span><span class="sxs-lookup"><span data-stu-id="d77d4-110">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="d77d4-111">팀은 여러 개의 Office 365 서비스를 결합 하므로 이러한 서비스의 올바른 구현과 작동에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d77d4-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="d77d4-112">이러한 서비스에는 SharePoint Online, Exchange Online, 비즈니스용 OneDrive 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d77d4-112">These services include—but aren’t limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="d77d4-113">모든 서비스가 필요 하지는 않지만 모두 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d77d4-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="d77d4-114">특정 서비스를 구현 하지 않도록 선택 하는 경우 팀이 조직을 제공할 수 있는 기능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d77d4-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="d77d4-115">예를 들어 SharePoint Online을 구현할 필요가 없지만, 팀은 그룹 대화의 파일 공유와 같은 특정 기능에 대해 SharePoint Online을 사용 하므로이 서비스를 구현 하지 않으면 다음을 통해 제공 되는 기능이 감소 됩니다. 클라이언트측.</span><span class="sxs-lookup"><span data-stu-id="d77d4-115">For example, though you don’t have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="d77d4-116">다음 문서를 참조 하 여 필수 구성 요소와 팀이 다른 기술과 상호 작용 하는 방식에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d77d4-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="d77d4-117">조직에서 Office 365 작업을 배포 하지 않은 경우 [비즈니스용 office 365 시작](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d77d4-117">If your organization hasn’t deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="d77d4-118">조직이 Office 365에 대해 확인 된 도메인을 추가 하거나 구성 하지 않은 경우 [office 365 도메인 확인](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d77d4-118">If your organization hasn’t added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="d77d4-119">조직이 Azure Active Directory에 대 한 id를 동기화 하지 않은 경우 [Microsoft 팀의 id 모델 및 인증](identify-models-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d77d4-119">If your organization hasn’t synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="d77d4-120">조직에 Exchange Online이 포함 되어 있지 않은 경우 [exchange 및 Microsoft 팀의 상호 작용 방법 이해](Exchange-Teams-interact.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d77d4-120">If your organization doesn¹t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="d77d4-121">조직에 SharePoint Online이 없는 경우 [Sharepoint online 및 비즈니스용 OneDrive For Business가 Microsoft 팀과 어떻게 상호 작용 하는지 이해](SharePoint-OneDrive-interact.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d77d4-121">If your organization doesn’t have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="d77d4-122">[Office 365 그룹 및 Microsoft 팀의 상호 작용](Office-365-groups.md)방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="d77d4-122">Learn how [Office 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="d77d4-123">조직이 교육 기관이 고 학생 정보 시스템을 사용 하는 경우 Microsoft 팀을 배포 하기 전에 [School Data Sync를 배포](https://docs.microsoft.com/schooldatasync) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77d4-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="d77d4-124">해당 환경이 적용 가능한 모든 필수 구성 요소를 충족 하는지 확인 한 후 [팀에 대 한 현재 환경을 평가](upgrade-plan-journey-evaluate-environment.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d77d4-124">After you’ve verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
