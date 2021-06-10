---
title: Teams 모드 고려 사항만
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 관리자는 관리 센터의 Microsoft Teams 전용 모드로 업그레이드를 준비하는 Microsoft Teams 수 있습니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b2232d4774a31f3b081b2410371a5903debe9123
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239015"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="21ef4-103">Teams 모드 고려 사항만</span><span class="sxs-lookup"><span data-stu-id="21ef4-103">Teams Only mode considerations</span></span>

<span data-ttu-id="21ef4-104">조직 또는 Microsoft 365 Office 365 관리자는 개별 사용자 또는 전체 테넌트 중 하나를 전용 모드로 업그레이드할 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ef4-104">Administrators of Microsoft 365 or Office 365 organizations can upgrade either individual users or the entire tenant to Teams Only mode.</span></span>  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="21ef4-105">단일 Teams 전용 모드로 업그레이드하면 단일 클라이언트 환경을 통해 Microsoft Teams 팀워크의 허브인 Microsoft 365 Office 365 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21ef4-105">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="21ef4-106">Teams 전용 모드의 사용자는 보낸 사람이 Teams 사용 여부에 관계없이 모든 통화 및 채팅을 비즈니스용 Skype Teams 및 페더전 지원의 혜택을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ef4-106">Users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="21ef4-107">수천 명의 고객이 성공적으로 업그레이드 Microsoft Teams 조직의 업그레이드 타임라인 및 사용자 경험에 영향을 줄 수 있는 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ef4-107">Although thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="21ef4-108">최상의 사용자 환경을 위해서는 Teams가 공동 작업 및 커뮤니케이션 요구 사항을 충족하는지와 네트워크가 Teams를 지원할 준비가 되었는지를 확인하고 사용자를 Teams에 업그레이드하기 전에 사용자 준비를 위한 계획을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ef4-108">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="21ef4-109">업그레이드 계획을 시작하고 있는 경우 업그레이드 시작 가이드를 Microsoft Teams [검토하세요.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="21ef4-109">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="21ef4-110">**공존** 고려 사항: 비즈니스용 Skype 온라인 및/또는 비즈니스용 Skype 서버 조직은 요구에 Teams 속도로 환경에 Teams 도입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ef4-110">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="21ef4-111">조직은 필요한 Teams 사용자 집합으로 증분 롤아웃할 수 있으며, 조직을 사용하는 Teams 사용자와 통신할 수 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ef4-111">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="21ef4-112">이 환경을 관리하기 위해 관리자는 최종 사용자 클라이언트 환경, 들어오는 채팅 및 통화의 라우팅 동작 및 새 모임이 Teams 또는 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="21ef4-112">To manage this experience, administrators use coexistence modes, which define the end-user client experience, the routing behavior of incoming chats and calls, and whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="21ef4-113">사용자가 사용자 전용으로 업그레이드된 경우 다른 조직의 사용자와 페더 Teams **수 있습니다.** 그러나 두 사용자가 모두 사용 하는 경우 최상의 환경이 Teams.</span><span class="sxs-lookup"><span data-stu-id="21ef4-113">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="21ef4-114">업그레이드된 사용자만 Teams 모임에 비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ef4-114">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="21ef4-115">공존에 대한 자세한 내용은 공존성 및 상호 Microsoft Teams 비즈니스용 Skype 이해를 [참조하세요.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="21ef4-115">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="21ef4-116">Teams 및 Skype(소비자)에 대한 자세한 내용은 Teams Skype [참조하세요.](teams-skype-interop.md)</span><span class="sxs-lookup"><span data-stu-id="21ef4-116">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>


<span data-ttu-id="21ef4-117">**사용자별** 고려 사항: 일부 사용자 시나리오는 계속 진화하고 있으며 관리자는 조직의 다른 사용자를 업그레이드하는 동안 특정 사용자의 업그레이드를 일시적으로 연기하기로 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ef4-117">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="21ef4-118">특히 기본 디바이스가 VDI 기반인 사용자에 대한 해결 시나리오를 계속 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ef4-118">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="21ef4-119">사이트 공지의 경우 [로드맵 Microsoft 365 모니터링합니다.](https://www.microsoft.com/microsoft-365/roadmap)</span><span class="sxs-lookup"><span data-stu-id="21ef4-119">For site announcements, monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

> [!NOTE]
> <span data-ttu-id="21ef4-120">Teams 전용 모드로 이동하기 전에 지원되지 않는 디바이스를 교체하거나 업데이트해야 Teams.</span><span class="sxs-lookup"><span data-stu-id="21ef4-120">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="21ef4-121">**기억:** Teams 이동은 기술 마이그레이션 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="21ef4-121">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="21ef4-122">성공적인 업그레이드는 기술 준비와 최종 사용자 준비를 모두 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="21ef4-122">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="21ef4-123">업그레이드 비즈니스용 Skype Teams 계획에 [](upgrade-framework.md) 대한 자세한 내용은 업그레이드 지침을 검토하여 Teams.</span><span class="sxs-lookup"><span data-stu-id="21ef4-123">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
