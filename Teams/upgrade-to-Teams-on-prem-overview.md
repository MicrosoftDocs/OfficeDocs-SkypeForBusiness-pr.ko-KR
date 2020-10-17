---
title: 비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드-Microsoft 팀
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 528dcfd975616d213b8a9fbd2499dc5d798708b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533585"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="341a5-103">비즈니스용 Skype에서 IT 관리자를 위한 팀으로 업그레이드 &mdash;</span><span class="sxs-lookup"><span data-stu-id="341a5-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="341a5-104">개요</span><span class="sxs-lookup"><span data-stu-id="341a5-104">Overview</span></span>

<span data-ttu-id="341a5-105">비즈니스용 Skype에서 팀으로 업그레이드할 때 일부 조직에서는 IT 부서가 계획 하 고 관리 하는 점진적 롤아웃을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="341a5-106">이 섹션의 문서는 주로 대규모 조직의 IT 관리자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="341a5-107">이러한 조직은 일반적으로 온-프레미스 이며, 대규모 비즈니스용 Skype Online 조 직 일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="341a5-108">이 문서를 읽기 전에 먼저 [팀 업그레이드](upgrade-start-here.md) 와 [업그레이드 프레임 워크에 대 한 자세한](upgrade-framework.md)내용을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="341a5-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="341a5-109">조직의 업그레이드 프로세스를 안내 하는 문서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="341a5-110">업그레이드 방법</span><span class="sxs-lookup"><span data-stu-id="341a5-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="341a5-111">업그레이드 관리 도구</span><span class="sxs-lookup"><span data-stu-id="341a5-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="341a5-112">비즈니스용 Skype 온-프레미스를 사용 하는 조직에 대 한 추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="341a5-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="341a5-113">업그레이드 수행</span><span class="sxs-lookup"><span data-stu-id="341a5-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="341a5-114">PSTN (공개 통신 네트워크) 고려 사항</span><span class="sxs-lookup"><span data-stu-id="341a5-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="341a5-115">또한 다음 문서에서는 중요 한 업그레이드 개념 및 공존 동작에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="341a5-116">팀과 비즈니스용 Skype의 공존</span><span class="sxs-lookup"><span data-stu-id="341a5-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="341a5-117">공존 모드-참조</span><span class="sxs-lookup"><span data-stu-id="341a5-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="341a5-118">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="341a5-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="341a5-119">이 문서는 비즈니스용 Skype Online, 비즈니스용 Skype Server 온-프레미스, 비즈니스용 Skype를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="341a5-120">후자의 용어는 온라인 및 온-프레미스 버전을 모두 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="341a5-121">시작 하기 전에, 팀으로 마이그레이션한 사용자가 비즈니스용 Skype에서 호스트 된 모임에 참가 하는 것 외에는 비즈니스 클라이언트를 더 이상 사용 하지 않는다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="341a5-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="341a5-122">발신자가 팀과 비즈니스용 Skype를 사용 하는지 여부에 관계 없이 사용자의 팀 클라이언트에 있는 모든 수신 채팅 및 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="341a5-123">마이그레이션된 사용자가 구성한 모든 새 모임은 팀 모임으로 예약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="341a5-124">사용자가 비즈니스용 Skype 클라이언트를 사용 하려고 시도 하는 경우 채팅 및 통화에 대 한 시작이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="341a5-125">그러나 사용자는 비즈니스용 Skype 클라이언트를 사용 하 여 초대 받은 비즈니스용 Skype 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="341a5-126">(2017 이전에 출시 된 이전 비즈니스용 Skype 클라이언트는 TeamsUpgradePolicy를 준수 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="341a5-127">최신 비즈니스용 Skype 클라이언트를 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="341a5-128">[TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)의 속성인 [mode](migration-interop-guidance-for-teams-with-skype.md)개념을 사용 하 여 팀으로 사용자의 전환을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="341a5-129">위에 설명 된 대로 팀으로 마이그레이션한 사용자는 "TeamsOnly" 모드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="341a5-130">팀으로 마이그레이션하는 조직의 경우 궁극적인 목표는 모든 사용자를 TeamsOnly 모드로 이동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

>[!NOTE]
><span data-ttu-id="341a5-131">비즈니스용 Skype 온-프레미스 계정이 있는 사용자는 TeamsOnly 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-131">Users who have a Skype for Business on-premises account cannot be TeamsOnly.</span></span> <span data-ttu-id="341a5-132">이러한 사용자는 [아일랜드 모드에서 팀을 사용할](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)수 있지만,이는 TeamsOnly 모드에서 사용할 수 있는 전체 팀 기능 집합을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-132">Although these users can [use Teams in Islands mode](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), this does not provide the full set of Teams functionality that is available in TeamsOnly mode.</span></span> <span data-ttu-id="341a5-133">이러한 사용자를 팀에 게만 자신 있게 하려면 온 `Move-CsUser` -프레미스 비즈니스용 Skype 서버 도구를 사용 하 여 클라우드로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-133">To make these users TeamsOnly, they must be moved to the cloud using `Move-CsUser` in the on-premises Skype for Business Server tools.</span></span>

<span data-ttu-id="341a5-134">그래.</span><span class="sxs-lookup"><span data-stu-id="341a5-134">OK.</span></span> <span data-ttu-id="341a5-135">시작 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-135">Let's get started.</span></span>  <span data-ttu-id="341a5-136">첫 번째 단계는 [사용할 수 있는 업그레이드 방법을 이해 하](upgrade-to-teams-on-prem-upgrade-methods.md)는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="341a5-136">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="341a5-137">관련 링크</span><span class="sxs-lookup"><span data-stu-id="341a5-137">Related links</span></span>

[<span data-ttu-id="341a5-138">비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="341a5-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="341a5-139">비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="341a5-139">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="341a5-140">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="341a5-140">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="341a5-141">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="341a5-141">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="341a5-142">부여-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="341a5-142">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="341a5-143">MMS (모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="341a5-143">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

