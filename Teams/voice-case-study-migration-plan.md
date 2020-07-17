---
title: 팀 음성 Contoso 사례 연구
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
description: 여러 국가의 기업에 대 한 팀 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786091"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="ff5c4-103">Contoso 사례 연구: 팀 업그레이드 계획</span><span class="sxs-lookup"><span data-stu-id="ff5c4-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="ff5c4-104">비즈니스용 Skype에서 팀으로 마이그레이션을 할 때 Contoso는 최종 사용자에 게 쉬운 전환 환경을 제공 하고자 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="ff5c4-105">동시에 모든 사람을 팀으로 전환 하는 대신 하이브리드 연결을 설정 하 고 겹치는 기능 방법을 사용 하 여 사용자를 팀으로 이동 하기로 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="ff5c4-106">이 허용 된 사용자는 팀 및 비즈니스용 Skype 온-프레미스에서 현재 상태를 공유 하 고 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="ff5c4-107">사용자가 전화 시스템의 파일럿을 입력 하면 팀 전용 모드로 옮겨졌습니다.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="ff5c4-108">업그레이드, 메서드 및 모드에 대 한 기본 개념을 이해 하기 위해 Contoso는 다음 문서를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="ff5c4-109">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="ff5c4-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="ff5c4-110">비즈니스용 Skype에서 Teams로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="ff5c4-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="ff5c4-111">마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="ff5c4-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="ff5c4-112">Contoso는 비즈니스용 [Skype에서 팀으로 경로를 디자인](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)하는 Ignite 2019 세션에도 참가 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="ff5c4-113">Contoso는 다음 정보를 얻었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-113">Contoso learned about:</span></span>

- <span data-ttu-id="ff5c4-114">상호 운용성, 페더레이션, 업그레이드 동작 등의 기본 개념</span><span class="sxs-lookup"><span data-stu-id="ff5c4-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="ff5c4-115">TeamsUpgradePolicy 기반 공존 모드 및 관리</span><span class="sxs-lookup"><span data-stu-id="ff5c4-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="ff5c4-116">최종 사용자 환경:</span><span class="sxs-lookup"><span data-stu-id="ff5c4-116">End user experience for:</span></span> 

  - <span data-ttu-id="ff5c4-117">채팅 및 통화</span><span class="sxs-lookup"><span data-stu-id="ff5c4-117">Chat and Calling</span></span> 

  - <span data-ttu-id="ff5c4-118">모임 예약</span><span class="sxs-lookup"><span data-stu-id="ff5c4-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="ff5c4-119">팀 클라이언트의 공동 작업 기능 가용성</span><span class="sxs-lookup"><span data-stu-id="ff5c4-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="ff5c4-120">하이브리드 연결을 계획 하 고 구성 하려면 (온-프레미스 환경을 클라우드로 이동 하는 첫 번째 단계), Contoso는 [하이브리드 연결 계획](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) 및 [하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="ff5c4-121">Office 365와 페더레이션 하도록 온-프레미스 환경 서비스를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="ff5c4-122">Office 365을 신뢰 하도록 온-프레미스 환경을 구성 하 고 Office 365에서 공유 SIP 주소 공간 사용</span><span class="sxs-lookup"><span data-stu-id="ff5c4-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="ff5c4-123">Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="ff5c4-124">기술 시험 운용 중에 아일랜드 모드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="ff5c4-125">사용자가 전화 시스템을 사용할 수 있게 되 면 사용자를 TeamsOnly 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="ff5c4-126">팀 전용 모드는 호출 계획 및 직접 라우팅에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff5c4-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
