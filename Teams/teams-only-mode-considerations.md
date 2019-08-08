---
title: 팀 전용 모드 고려 사항
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: Microsoft 팀 전용 모드로 업그레이드 준비
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords: ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1a6d27dc2e01d433f36196394f7d3b98871c597
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244780"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="70e58-103">팀 전용 모드 고려 사항</span><span class="sxs-lookup"><span data-stu-id="70e58-103">Teams Only mode considerations</span></span>

<span data-ttu-id="70e58-104">Office 365 테 넌 트의 관리자는 Microsoft 팀 관리 센터에서 팀 전용 모드로 업그레이드 하는 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-104">If you are an administrator on your Office 365 tenant, you will now see the option to upgrade to Teams Only mode in the Microsoft Teams admin center.</span></span> <span data-ttu-id="70e58-105">이 기능을 사용 하 여 개별 사용자 또는 전체 테 넌 트 중 하나를 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-105">With this functionality you can upgrade either individual users, or alternatively, the entire tenant.</span></span>  

<span data-ttu-id="70e58-106">팀 전용 모드로 업그레이드 하는 경우 단일 클라이언트 환경을 통해 Office 365의 팀워크에 대 한 허브 인 Microsoft 팀의 모든 혜택을 제공 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-106">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Office 365, via a single client experience.</span></span> <span data-ttu-id="70e58-107">또한 팀 전용 모드의 사용자는 보낸 사람이 비즈니스용 Skype를 사용 하 고 있는지 여부에 관계 없이 팀의 모든 통화와 채팅을 받게 되며 interop 및 페더레이션 지원의 혜택을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-107">Additionally, users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="70e58-108">수천 명의 고객이 Microsoft 팀으로 업그레이드 한 후 조직의 업그레이드 시간 표시 막대와 사용자 환경에 영향을 미칠 수 있는 고려 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-108">While thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization’s upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="70e58-109">특히, 업그레이드 옵션이 반드시 조직이이 변경에 대 한 것을 의미 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-109">In particular, having the option to upgrade doesn’t necessarily mean your organization is ready for this change.</span></span> <span data-ttu-id="70e58-110">최상의 사용자 환경을 위해서는 팀이 공동 작업 및 통신 요구 사항을 충족 하는지 확인 하 고, 사용자를 팀으로 업그레이드 하기 전에 네트워크가 팀을 지원할 준비가 되었는지 확인 하 고 사용자 준비 계획을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-110">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="70e58-111">업그레이드 계획을 시작 하는 경우에는 전체 업그레이드 지침 및 계획 리소스를 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-111">If you are just starting your upgrade planning, be sure to review our full upgrade guidance and planning resources.</span></span> <span data-ttu-id="70e58-112">[여기서 시작](upgrade-start-here.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="70e58-112">[Start here](upgrade-start-here.md).</span></span> 

<span data-ttu-id="70e58-113">**공존 고려 사항**: 이미 비즈니스용 skype Online 및/또는 비즈니스용 skype 서버를 사용 하는 조직은 사용자의 요구에 맞는 속도로 팀을 환경에 도입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-113">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="70e58-114">조직에서는 필요에 따라 팀을 원하는 사용자 집합에 점진적으로 롤아웃할 수 있으며, 팀을 사용 하는 사용자는 비즈니스용 Skype를 사용 하는 사용자와 통신할 수 있으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-114">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="70e58-115">이러한 경험을 관리 하기 위해 관리자는 최종 사용자 클라이언트 경험, 들어오는 채팅 및 통화의 라우팅 동작, 팀에서 새 모임을 예약 했는지 여부, 그리고 비즈니스용 Skype를 사용 하는 등을 정의 하는 공존 모드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-115">To manage this experience, administrators use coexistence modes, which define the end user client experience, the routing behavior of incoming chats and calls, as well as whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="70e58-116">사용자가 **팀**으로 업그레이드 한 경우 다른 조직의 사용자와 페더레이션 할 수 있습니다. 그러나 두 사용자가 모두 팀을 사용 하는 경우 최상의 환경이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-116">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="70e58-117">팀으로 업그레이드 한 사용자는 비즈니스용 Skype 모임에 계속 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-117">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!NOTE]
> <span data-ttu-id="70e58-118">팀으로 업그레이드 한 사용자는 소비자 용 Skype를 사용 하는 사용자와 통신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-118">Users who are upgraded to Teams Only cannot communicate with users who are using Skype for Consumer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="70e58-119">공존에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70e58-119">For more detailed information about coexistence please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> 

<span data-ttu-id="70e58-120">**테 넌 트 전체 고려 사항**: 다음 환경에서 팀을 사용 하도록 설정할 수 있습니다. 그러나 지금은 비즈니스용 Skype 테 넌 트가 다음 환경 중 하나에서 호스팅되는 경우 관리자는 조직의 모든 사용자를 업그레이드 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-120">**Tenant-wide considerations**: We are working on enabling Teams in the following environments; however, for now, administrators shouldn't upgrade any users in their organization if their Skype for Business tenant is hosted in one of the following environments:</span></span>

 - <span data-ttu-id="70e58-121">정부 커뮤니티 구름 높음</span><span class="sxs-lookup"><span data-stu-id="70e58-121">Government Community Cloud High</span></span>
 - <span data-ttu-id="70e58-122">정부 커뮤니티 클라우드 DoD</span><span class="sxs-lookup"><span data-stu-id="70e58-122">Government Community Cloud DoD</span></span>
 - <span data-ttu-id="70e58-123">21Vianet에서 운영 하는 Office 365</span><span class="sxs-lookup"><span data-stu-id="70e58-123">Office 365 operated by 21Vianet</span></span>
 - <span data-ttu-id="70e58-124">Office 365 독일</span><span class="sxs-lookup"><span data-stu-id="70e58-124">Office 365 Germany</span></span>
 - <span data-ttu-id="70e58-125">비즈니스용 Skype 테 넌 트가 대한민국에서 호스팅되며 조직 \*\*\*\* 에는 대한민국에 저장 되는 팀 데이터가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-125">Skype for Business tenant is hosted in South Korea **and** the organization requires Teams data to be stored in South Korea.</span></span> <span data-ttu-id="70e58-126">현재 대한민국에 저장 된 비즈니스용 Skype 데이터를 보유 하 고 있는 조직에서 팀으로 업그레이드 하면 해당 팀 데이터가 동남 한국 데이터 센터 지역에 저장 되지 않고 아시아 데이터 센터 지역에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-126">Currently, organizations with Skype for Business data stored in South Korea that upgrade to Teams will have their Teams data stored in the Asia datacenter region, not in the South Korea datacenter region.</span></span>

<span data-ttu-id="70e58-127">**사용자 관련 고려 사항**: 일부 사용자 시나리오는 계속 진화 하 고 있으며, 관리자는 조직의 다른 사용자를 업그레이드 하면서 특정 사용자의 업그레이드를 일시적으로 연기 하도록 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-127">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="70e58-128">저희는 이러한 시나리오를 해결 하는 것으로 진행 중입니다. [Office 365 로드맵](https://www.microsoft.com/en-us/microsoft-365/roadmap) 사이트에서 공지 사항을 모니터링 하세요.</span><span class="sxs-lookup"><span data-stu-id="70e58-128">We are working on addressing these scenarios; please monitor the [Office 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap) site for announcements.</span></span>

> [!NOTE]
> <span data-ttu-id="70e58-129">팀 전용 모드로 이동 하기 전에 팀을 지원 하지 않는 장치를 바꾸거나 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-129">Before you move to Teams Only mode you need to replace or update devices that don’t support Teams.</span></span> 

| <span data-ttu-id="70e58-130">시나리오</span><span class="sxs-lookup"><span data-stu-id="70e58-130">Scenario</span></span> | <span data-ttu-id="70e58-131">상속자</span><span class="sxs-lookup"><span data-stu-id="70e58-131">Notes</span></span> |
|----------|-------|
|<span data-ttu-id="70e58-132">사용자의 기본 회사 장치는 Mac 이며 사용자는 Outlook에서 동료의 사용 가능 여부를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-132">User’s primary work device is a Mac, and user needs to see colleagues' availability in Outlook.</span></span> | <span data-ttu-id="70e58-133">팀의 Outlook 현재 상태는 Mac 장치에 대해 아직 완전히 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-133">Outlook presence in Teams is not yet fully supported for Mac devices.</span></span> |
| <span data-ttu-id="70e58-134">사용자가 다양 한 국가별 지역에서 고객 또는 외부 파트너와의 모임을 정기적으로 수행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-134">User is regularly conducting meetings with customers or external partners in different international regions.</span></span> | <span data-ttu-id="70e58-135">테 넌 트가 다른 지리적 위치에 있는 외부 참석자는 **페더레이션된** 모임 중에 메신저 대화가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-135">External attendees whose tenant resides in a different geo-location don’t see IM chat while in a **federated** meeting.</span></span> <span data-ttu-id="70e58-136">참가자는 여전히 익명 사용자로 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-136">Participants can still join the meeting as anonymous users.</span></span> |
| <span data-ttu-id="70e58-137">사용자가 비즈니스용 Skype 브로드캐스트 모임을 수행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-137">User is conducting Skype for Business Broadcast meetings.</span></span> |  <span data-ttu-id="70e58-138">팀 live 이벤트 (Skype 브로드캐스트 교체)는 이미 공개 미리 보기 상태에 있으며,이 사용자는 팀의 일반 사용이 가능 해질 때까지 Skype for Business를 유지 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-138">While Teams live events (replacing Skype Broadcast) is already in public preview, this user may need to stay on Skype for Business until general availability of Teams live events.</span></span>
| <span data-ttu-id="70e58-139">사용자의 기본 장치는 VDI 기반입니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-139">User’s primary device is VDI-based.</span></span> | |
|||

> [!IMPORTANT]
> <span data-ttu-id="70e58-140">팀으로 이동 하는 것은 기술적 마이그레이션 보다 더 **주의할**사항입니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-140">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="70e58-141">성공적인 업그레이드는 기술 준비 및 최종 사용자 준비를 모두 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="70e58-141">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="70e58-142">팀으로 업그레이드를 구현 하는 방법을 계획 하는 방법에 대 한 자세한 내용은 팀의 비즈니스용 Skype [업그레이드 지침](upgrade-framework.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70e58-142">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
