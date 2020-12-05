---
title: Microsoft Teams를 위한 IT 직원 준비
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Microsoft Teams를 배포하고 지원하기 위해 조직의 IT 직원을 준비하는 방법에 대해 자세히 배워야 합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 680106618d610d0adc3f93658e3a522d63850e24
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578461"
---
# <a name="prepare-your-it-staff-for-microsoft-teams"></a><span data-ttu-id="729cd-103">Microsoft Teams를 위한 IT 직원 준비</span><span class="sxs-lookup"><span data-stu-id="729cd-103">Prepare your IT staff for Microsoft Teams</span></span>

<span data-ttu-id="729cd-104">![기술 준비 단계 강조를 표시하는 업그레이드 여정 다이어그램](media/upgrade-banner-tech-readiness.png "기술 준비 단계에 강조를 두는 업그레이드 단계")</span><span class="sxs-lookup"><span data-stu-id="729cd-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="729cd-105">이 문서는 사용자 준비 단계와 병렬로 완료하는 작업인 업그레이드 여정의 기술 준비 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="729cd-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="729cd-106">계속하기 전에 이전 단계에서 이러한 활동을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="729cd-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="729cd-107">프로젝트 관련자에 참여</span><span class="sxs-lookup"><span data-stu-id="729cd-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="729cd-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="729cd-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="729cd-109">비즈니스용 Skype 및 Teams의 공존 및 상호 연동성 이해</span><span class="sxs-lookup"><span data-stu-id="729cd-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="729cd-110">업그레이드 여정 선택</span><span class="sxs-lookup"><span data-stu-id="729cd-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="729cd-111">Microsoft 365 또는 Office 365 조직 관리자, 기술 책임자 및 지원 센터는 고품질 사용자 환경을 구동하는 데 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729cd-111">Your Microsoft 365 or Office 365 organization admins, technical leads, and support desk are accountable for driving a high-quality user experience.</span></span> <span data-ttu-id="729cd-112">여기에는 네트워크가 Teams를 지원할 준비가 됐는지, 사용자를 위한 Teams를 구성하고, 발생할 수 있는 문제를 효과적으로 해결하고 해결할 수 있는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="729cd-112">This includes ensuring that your network is ready to support Teams, configuring Teams for your users, and being able to effectively troubleshoot and resolve issues that might arise.</span></span>

<span data-ttu-id="729cd-113">IT 직원 구성원과 다음 리소스를 공유하고 Teams로 업그레이드하기 전에 사용자를 지원할 준비가 됐는지 확인</span><span class="sxs-lookup"><span data-stu-id="729cd-113">Share the following resources with your IT staff members, and confirm that they're ready to support users before you begin your upgrade to Teams:</span></span>

- [<span data-ttu-id="729cd-114">Microsoft Teams에 대한 관리자 교육</span><span class="sxs-lookup"><span data-stu-id="729cd-114">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)
- [<span data-ttu-id="729cd-115">비즈니스용 제품에 대한 고객 지원 센터 - 관리자 도움말</span><span class="sxs-lookup"><span data-stu-id="729cd-115">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [<span data-ttu-id="729cd-116">Microsoft Teams 클라이언트의 연결 문제 해결</span><span class="sxs-lookup"><span data-stu-id="729cd-116">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>](connectivity-issues.md)
- [<span data-ttu-id="729cd-117">Microsoft Teams 문제 해결에 로그 파일 사용</span><span class="sxs-lookup"><span data-stu-id="729cd-117">Use log files in troubleshooting Microsoft Teams</span></span>](log-files.md)



| | |
|---|---|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="729cd-119">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="729cd-119">Decision points</span></span>|<ul><li><span data-ttu-id="729cd-120">Teams 배포 및 지원에 관여할 가능성이 있는 모든 지원 직원을 참여시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="729cd-120">Have you involved all support staff who are likely to be involved in deploying and supporting Teams?</span></span></li><li><span data-ttu-id="729cd-121">업그레이드가 진행될 때 추가 직원을 온보드하기 위한 교육 계획을 개발한 경우</span><span class="sxs-lookup"><span data-stu-id="729cd-121">Have you developed a training plan for onboarding additional staff as your upgrade progresses?</span></span></li></ul> |
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/><span data-ttu-id="729cd-123">다음 단계</span><span class="sxs-lookup"><span data-stu-id="729cd-123">Next steps</span></span>|<ul><li><span data-ttu-id="729cd-124">IT 직원에게 필요한 정보가 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="729cd-124">Verify that IT staff has the information they need.</span></span></li><li><span data-ttu-id="729cd-125">새 기능이 릴리스될 때 학습 및 준비 계획을 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="729cd-125">Revisit your training and preparation plans as new features are released.</span></span></li></ul>|

<span data-ttu-id="729cd-126">Teams에 대한 IT 직원을 준비한 후 환경이 모든 요건을 충족하는지 [확인해야 합니다.](upgrade-plan-journey-prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="729cd-126">After you've prepared your IT staff for Teams, verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md).</span></span>
