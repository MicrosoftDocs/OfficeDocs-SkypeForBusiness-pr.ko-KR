---
title: Teams 음성 Contoso 사례 연구
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
description: 다국적 기업에 대한 Teams 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786091"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="7b404-103">Contoso 사례 연구: Teams 업그레이드 계획</span><span class="sxs-lookup"><span data-stu-id="7b404-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="7b404-104">비즈니스용 Skype에서 Teams로 마이그레이션하기로 결정한 Contoso는 최종 사용자에게 간편한 전환 환경을 제공하기를 원했습니다.</span><span class="sxs-lookup"><span data-stu-id="7b404-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="7b404-105">모든 사용자를 Teams로 동시에 전환하는 대신 하이브리드 연결을 설정하고 겹치는 기능 방법을 사용하여 사용자를 Teams로 이동하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="7b404-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="7b404-106">이렇게 하면 Teams 및 비즈니스용 Skype의 사용자가 현재 상태와 통신을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b404-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="7b404-107">사용자가 전화 시스템 파일럿에 들어가면 Teams 전용 모드로 이동했습니다.</span><span class="sxs-lookup"><span data-stu-id="7b404-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="7b404-108">업그레이드, 메서드 및 모드에 대한 기본 개념을 이해하려면 Contoso에서 다음 문서를 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="7b404-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="7b404-109">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="7b404-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="7b404-110">비즈니스용 Skype에서 Teams로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7b404-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="7b404-111">마이그레이션 및 상호 연동성 지침</span><span class="sxs-lookup"><span data-stu-id="7b404-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="7b404-112">또한 Contoso는 비즈니스용 Skype에서 Teams로의 경로를 디자인하는 Ignite 2019 [세션에 참석했습니다.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="7b404-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="7b404-113">Contoso는 다음에 대해 알아보았다.</span><span class="sxs-lookup"><span data-stu-id="7b404-113">Contoso learned about:</span></span>

- <span data-ttu-id="7b404-114">상호 운영성, 페더전 및 업그레이드 동작과 같은 기본 개념</span><span class="sxs-lookup"><span data-stu-id="7b404-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="7b404-115">TeamsUpgradePolicy 기반의 공존 모드 및 관리</span><span class="sxs-lookup"><span data-stu-id="7b404-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="7b404-116">다음에 대한 최종 사용자 환경:</span><span class="sxs-lookup"><span data-stu-id="7b404-116">End user experience for:</span></span> 

  - <span data-ttu-id="7b404-117">채팅 및 통화</span><span class="sxs-lookup"><span data-stu-id="7b404-117">Chat and Calling</span></span> 

  - <span data-ttu-id="7b404-118">모임일정</span><span class="sxs-lookup"><span data-stu-id="7b404-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="7b404-119">Teams 클라이언트의 공동 작업 기능 가용성</span><span class="sxs-lookup"><span data-stu-id="7b404-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="7b404-120">하이브리드 연결을 계획하고 구성하기 위해, Contoso는 클라우드로 자신의 On-프레미스 환경을 [](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 이동하는 첫 번째 단계인 하이브리드 연결을 읽고 하이브리드 연결을 구성하여 다음 방법을 이해합니다. [](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="7b404-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="7b404-121">Office 365와 페더해지도록 자신의 On-프레미스 환경 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7b404-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="7b404-122">Office 365를 신뢰하고 Office 365에서 공유 SIP 주소 공간을 사용하도록 자신의 On-프레미스 환경 구성</span><span class="sxs-lookup"><span data-stu-id="7b404-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="7b404-123">Office 365 테넌트에서 공유 SIP 주소 공간을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="7b404-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="7b404-124">기술 파일럿 중에 제도 모드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b404-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="7b404-125">사용자가 전화 시스템에 사용하도록 설정되면 사용자를 TeamsOnly 모드로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="7b404-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="7b404-126">TeamsOnly 모드는 통화 계획 및 직접 라우팅에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7b404-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
