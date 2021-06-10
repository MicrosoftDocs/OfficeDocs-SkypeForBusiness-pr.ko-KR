---
title: Teams Contoso 사례 연구
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams 기업에 대한 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0da56bc0da083654a0cd694bd5983f2fe4fe515
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093728"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="e7506-103">Contoso 사례 연구: Teams 계획</span><span class="sxs-lookup"><span data-stu-id="e7506-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="e7506-104">Contoso는 최종 사용자에게 비즈니스용 Skype Teams 전환 환경을 제공하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7506-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="e7506-105">모든 사용자를 동시에 Teams 대신 하이브리드 연결을 설정하고 겹치는 기능 메서드를 사용하여 사용자를 다른 사용자로 Teams.</span><span class="sxs-lookup"><span data-stu-id="e7506-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="e7506-106">이렇게 하면 사용자가 Teams 및 비즈니스용 Skype 현재 상태 공유 및 통신을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7506-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="e7506-107">사용자가 파일럿을 전화 시스템 전용 모드로 Teams 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="e7506-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="e7506-108">업그레이드, 메서드 및 모드에 대한 기본 개념을 이해하려면 Contoso는 다음 문서를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e7506-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="e7506-109">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="e7506-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="e7506-110">IT 관리자를 위한 업그레이드 전략</span><span class="sxs-lookup"><span data-stu-id="e7506-110">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md) 
- [<span data-ttu-id="e7506-111">마이그레이션 및 상호 실행성 지침</span><span class="sxs-lookup"><span data-stu-id="e7506-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="e7506-112">Contoso는 또한 Ignite 2019 세션에 참석하여 비즈니스용 Skype 에서 [Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="e7506-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="e7506-113">Contoso는 다음에 대해 배웠다.</span><span class="sxs-lookup"><span data-stu-id="e7506-113">Contoso learned about:</span></span>

- <span data-ttu-id="e7506-114">상호 운영성, 페더리게이트 및 업그레이드 동작과 같은 기본 개념</span><span class="sxs-lookup"><span data-stu-id="e7506-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="e7506-115">TeamsUpgradePolicy를 기반으로 하는 공존 모드 및 관리</span><span class="sxs-lookup"><span data-stu-id="e7506-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="e7506-116">다음에 대한 최종 사용자 환경:</span><span class="sxs-lookup"><span data-stu-id="e7506-116">End user experience for:</span></span> 

  - <span data-ttu-id="e7506-117">채팅 및 통화</span><span class="sxs-lookup"><span data-stu-id="e7506-117">Chat and Calling</span></span> 

  - <span data-ttu-id="e7506-118">모임일정</span><span class="sxs-lookup"><span data-stu-id="e7506-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="e7506-119">클라이언트에서 공동 작업 Teams 가용성</span><span class="sxs-lookup"><span data-stu-id="e7506-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="e7506-120">하이브리드 연결을 계획하고 구성하기 위해, 프레미스 환경의 클라우드로 이동하는 [](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) 첫 번째 단계인 Contoso는 하이브리드 연결 계획 및 하이브리드 연결 구성을 읽고 다음 방법을 이해합니다. [](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="e7506-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="e7506-121">프레미스 환경 서비스를 구성하여 Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7506-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="e7506-122">공유 SIP 주소 공간을 신뢰하고 Office 365 공유 SIP 주소 공간을 사용하도록 프레미스 Office 365</span><span class="sxs-lookup"><span data-stu-id="e7506-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="e7506-123">공유 SIP 주소 공간을 테넌트에서 Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7506-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="e7506-124">기술 파일럿 중에 섬 모드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7506-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="e7506-125">사용자가 활성화되면 TeamsOnly 모드로 사용자를 전화 시스템.</span><span class="sxs-lookup"><span data-stu-id="e7506-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="e7506-126">TeamsOnly 모드는 통화 계획 및 직접 라우팅에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e7506-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span>