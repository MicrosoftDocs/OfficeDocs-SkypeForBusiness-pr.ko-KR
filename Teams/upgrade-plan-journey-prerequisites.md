---
title: Teams로 업그레이드하기 위한 전제 구성성 및 환경 종속성
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 이 지침을 사용하여 조직에서 Teams를 배포하기 위한 전제 구성성 및 환경 종속성에 대해 자세히 알아보기
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
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578281"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="29929-103">Teams에 대한 전제 구성성 및 환경 종속성</span><span class="sxs-lookup"><span data-stu-id="29929-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="29929-104">![기술 준비 단계 강조를 표시하는 업그레이드 여정 다이어그램](media/upgrade-banner-tech-readiness.png "기술 준비 단계에 강조를 두는 업그레이드 단계")</span><span class="sxs-lookup"><span data-stu-id="29929-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="29929-105">이 문서는 사용자 준비 단계와 병렬로 완료하는 작업인 업그레이드 여정의 기술 준비 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="29929-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="29929-106">계속하기 전에 이전 단계에서 이러한 활동을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29929-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="29929-107">프로젝트 관련자에 참여</span><span class="sxs-lookup"><span data-stu-id="29929-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="29929-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="29929-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="29929-109">비즈니스용 Skype 및 Teams의 공존 및 상호 연동성 이해</span><span class="sxs-lookup"><span data-stu-id="29929-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="29929-110">업그레이드 여정 선택</span><span class="sxs-lookup"><span data-stu-id="29929-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="29929-111">Teams는 여러 Microsoft 365 및 Office 365 서비스를 결합하므로 이러한 서비스의 올바른 구현 및 작업에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="29929-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="29929-112">이러한 서비스에는 SharePoint Online, Exchange Online 및 비즈니스용 OneDrive가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="29929-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="29929-113">모든 서비스가 필요한 것은 아니지만 모든 서비스를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="29929-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="29929-114">특정 서비스를 구현하지 않을 경우 Teams에서 조직에 제공할 수 있는 기능에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29929-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="29929-115">예를 들어 SharePoint Online을 구현할 수 없는 경우 Teams는 그룹 대화에서 파일 공유와 같은 특정 기능에 대해 SharePoint Online을 사용하게 되어 이 서비스를 구현하지 않는 경우 클라이언트를 통해 제공되는 기능이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="29929-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="29929-116">다음 문서를 참조하여 전제 사항 및 Teams가 다른 기술과 상호 작용하는 방법에 대해 자세히 알아보는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="29929-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="29929-117">조직에서 Microsoft 365 또는 Office 365 워크로드를 배포하지 않은 경우 [시작을 참조합니다.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span><span class="sxs-lookup"><span data-stu-id="29929-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="29929-118">조직에서 Microsoft 365 또는 Office 365에 대해 확인된 도메인을 추가하거나 구성하지 않은 경우 도메인 [FAQ를 참조합니다.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)</span><span class="sxs-lookup"><span data-stu-id="29929-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="29929-119">조직에서 Azure Active Directory에 ID를 동기화하지 않은 경우 Microsoft Teams에서 ID 모델 및 [인증을 참조하세요.](identify-models-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="29929-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="29929-120">조직에 Exchange Online이 없는 경우 Exchange 및 Microsoft Teams가 상호 작용하는 방법 [이해를 참조하세요.](Exchange-Teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="29929-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="29929-121">조직에 SharePoint Online이 없는 경우 SharePoint Online 및 [비즈니스용 OneDrive가 Microsoft Teams와](SharePoint-OneDrive-interact.md)상호 작용하는 방식 이해를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29929-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="29929-122">[Microsoft 365](Office-365-groups.md)그룹 및 Microsoft Teams가 상호 작용하는 방법을 알아보는 방법</span><span class="sxs-lookup"><span data-stu-id="29929-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="29929-123">조직이 교육 기관인 경우 학생 정보 시스템을 사용하는 경우 Microsoft Teams를 배포하기 전에 [Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) 시작을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29929-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="29929-124">조직에서 PSTN(Public Switched Telephone Network) 통화 옵션을 고려하는 경우 음성 - 전화 시스템 및 [PSTN](cloud-voice-landing-page.md) [연결,](calling-plan-landing-page.md)적합한 통화 요금제 및 전화 시스템 직접 라우팅을 참조하세요. [Phone System Direct Routing](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="29929-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="29929-125">Teams를 배포하기 전에 모든 네트워크 요구 사항이 충족되도록 하기 위해 Microsoft Teams에 대한 조직의 네트워크 [준비를 참조하세요.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="29929-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

<span data-ttu-id="29929-126">환경이 적용 가능한 모든 요구 사항을 충족하는지 확인한 후 Teams에 대한 현재 [환경을 평가합니다.](upgrade-plan-journey-evaluate-environment.md)</span><span class="sxs-lookup"><span data-stu-id="29929-126">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
