---
title: 업그레이드를 위한 전제적 구성요소 및 환경 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 이 지침을 사용하여 조직에서 배포를 위한 전제요구 및 환경적 종속성에 대해 Teams
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
ms.openlocfilehash: e9924c24f19da3cf17f8e8a124a03acc294c24b4
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282165"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="30f05-103">Teams</span><span class="sxs-lookup"><span data-stu-id="30f05-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="30f05-104">![기술 준비 단계 강조하는 업그레이드 여정 다이어그램](media/upgrade-banner-tech-readiness.png "기술 준비 단계가 강조된 업그레이드 여정의 단계")</span><span class="sxs-lookup"><span data-stu-id="30f05-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="30f05-105">이 문서는 사용자 준비 단계와 병렬로 완료한 작업인 업그레이드 여정의 기술 준비 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="30f05-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="30f05-106">계속하기 전에 이전 단계에서 이러한 작업을 완료한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="30f05-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="30f05-107">프로젝트 관계자 인리스트</span><span class="sxs-lookup"><span data-stu-id="30f05-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="30f05-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="30f05-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="30f05-109">비즈니스용 Skype 및 상호운용성을 Teams</span><span class="sxs-lookup"><span data-stu-id="30f05-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="30f05-110">업그레이드 여정을 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="30f05-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="30f05-111">Teams 여러 Microsoft 365 Office 365 서비스를 결합하므로 이러한 서비스의 올바른 구현 및 작업에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="30f05-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="30f05-112">이러한 서비스에는 온라인, SharePoint, Exchange Online 및 비즈니스용 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="30f05-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="30f05-113">모든 서비스가 필요한 것은 아니지만 모든 서비스를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="30f05-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="30f05-114">특정 서비스를 구현하지 않을 경우 조직에 제공할 수 있는 기능에 Teams 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30f05-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="30f05-115">예를 들어 온라인에서 SharePoint 구현할 Teams 그룹 대화에서 파일 공유와 같은 특정 기능에 SharePoint 온라인에서만 사용할 수 있으므로 이 서비스를 구현하지 않을 경우 클라이언트를 통해 제공되는 기능이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="30f05-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="30f05-116">다음 문서를 참조하여 전제 사항 및 다른 기술과 상호 작용하는 Teams 알아보는 방법을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="30f05-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="30f05-117">조직에서 워크로드 또는 워크로드를 배포하지 않은 Microsoft 365 Office 365 시작을 [참조합니다.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span><span class="sxs-lookup"><span data-stu-id="30f05-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="30f05-118">조직에서 인증된 도메인을 추가하거나 구성하지 않은 경우 Microsoft 365 Office 365 [FAQ를 참조합니다.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)</span><span class="sxs-lookup"><span data-stu-id="30f05-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="30f05-119">조직에서 동기화할 ID가 없는 Azure Active Directory 에서 ID 모델 및 [인증을 Microsoft Teams.](identify-models-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="30f05-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="30f05-120">조직에 Exchange Online이 없는 경우 [Exchange와 Microsoft Teams의 상호 작용 방법](Exchange-Teams-interact.md)을 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="30f05-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="30f05-121">조직에 SharePoint Online이 없는 경우 [SharePoint Online 및 비즈니스용 OneDrive가 Microsoft Teams와 상호 작용하는 방법](SharePoint-OneDrive-interact.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30f05-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="30f05-122">그룹 및 Microsoft 365 [상호 작용하는 Microsoft Teams 알아보는 방법](Office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="30f05-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="30f05-123">조직이 교육 기관인 경우 학생 정보 시스템을 사용하는 경우 배포하기 전에 [Microsoft](/schooldatasync) 학교 데이터 동기화 시작을 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="30f05-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="30f05-124">조직에서 PSTN(공용 전환 전화 네트워크) 통화 옵션을 고려하는 경우 Voice - 전화 시스템 [및 PSTN](cloud-voice-landing-page.md)연결 [,](calling-plan-landing-page.md)어떤 통화 계획이 적합한지, 직접 라우팅을 전화 시스템 [참조하세요.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="30f05-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="30f05-125">를 롤아웃하기 전에 모든 네트워크 요구 사항을 충족하는지 확인 Teams 에 대한 조직의 네트워크 [준비를 Microsoft Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="30f05-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

- <span data-ttu-id="30f05-126">현재 온라인 커넥터를 사용하여 비즈니스용 Skype 서비스를 관리하는 경우 PowerShell 모듈로 이동하여 Teams PowerShell 스크립트를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30f05-126">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="30f05-127">자세한 내용은 비즈니스용 Skype 온라인 커넥터에서 Teams [PowerShell 모듈로](teams-powershell-move-from-sfbo.md) 이동을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30f05-127">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="30f05-128">환경이 적용 가능한 모든 요구 사항을 충족하는지 확인한 후 에 대한 현재 환경을 [Teams.](upgrade-plan-journey-evaluate-environment.md)</span><span class="sxs-lookup"><span data-stu-id="30f05-128">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>