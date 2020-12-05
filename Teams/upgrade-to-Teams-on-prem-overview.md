---
title: 비즈니스용 Skype-프레미스 배포에서 Teams로 업그레이드 - Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
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
ms.openlocfilehash: 0fe5bb56979b9b4b430076602e76ece595b8661f
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578401"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="b0d08-103">비즈니스용 Skype에서 IT 관리자용 &mdash; Teams로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="b0d08-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="b0d08-104">개요</span><span class="sxs-lookup"><span data-stu-id="b0d08-104">Overview</span></span>

<span data-ttu-id="b0d08-105">비즈니스용 Skype에서 Teams로 업그레이드할 때 일부 조직에는 IT 부서에서 계획하고 관리하는 점진적 롤아웃이 필요하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="b0d08-106">이 섹션의 문서는 주로 대규모 조직의 IT 관리자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="b0d08-107">이러한 조직은 일반적으로온-프레미스이지만 대규모 비즈니스용 Skype Online 조직일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="b0d08-108">이러한 문서를 읽기 전에 Teams 업그레이드 및 [업그레이드](upgrade-start-here.md) 프레임워크 시작을 [읽어야 합니다.](upgrade-framework.md)</span><span class="sxs-lookup"><span data-stu-id="b0d08-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="b0d08-109">다음 문서에서는 조직의 업그레이드 프로세스를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="b0d08-110">업그레이드 방법</span><span class="sxs-lookup"><span data-stu-id="b0d08-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="b0d08-111">업그레이드를 관리하기 위한 도구</span><span class="sxs-lookup"><span data-stu-id="b0d08-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="b0d08-112">비즈니스용 Skype가 있는 조직에 대한 추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b0d08-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="b0d08-113">업그레이드 수행</span><span class="sxs-lookup"><span data-stu-id="b0d08-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="b0d08-114">PSTN(공용 전환 전화 네트워크) 고려 사항</span><span class="sxs-lookup"><span data-stu-id="b0d08-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="b0d08-115">또한 다음 문서에서는 중요한 업그레이드 개념 및 공존 동작을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="b0d08-116">Teams 및 비즈니스용 Skype의 공존</span><span class="sxs-lookup"><span data-stu-id="b0d08-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="b0d08-117">공존 모드 - 참조</span><span class="sxs-lookup"><span data-stu-id="b0d08-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="b0d08-118">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="b0d08-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="b0d08-119">이 문서에서는 비즈니스용 Skype Online, 비즈니스용 Skype 서버의 온라인 및 비즈니스용 Skype를 사용하는 용어를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="b0d08-120">후자의 용어는 온라인 버전과온-프레미스 버전을 모두 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="b0d08-121">시작하기 전에 Teams로 마이그레이션된 사용자는 비즈니스용 Skype에서 호스트된 모임에 참가하는 것 외에는 더 이상 비즈니스용 Skype 클라이언트를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="b0d08-122">받는 모든 채팅 및 통화는 보낸 사람이 Teams 또는 비즈니스용 Skype를 사용하는지 여부에 관계없이 사용자의 Teams 클라이언트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="b0d08-123">마이그레이션된 사용자가 구성한 모든 새 모임은 Teams 모임으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="b0d08-124">사용자가 비즈니스용 Skype 클라이언트를 사용하려고 시도하면 채팅 및 통화 시작이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="b0d08-125">그러나 사용자는 여전히 비즈니스용 Skype 클라이언트를 사용하여 초대된 비즈니스용 Skype 모임에 참가할 수 있습니다(및 반드시).</span><span class="sxs-lookup"><span data-stu-id="b0d08-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="b0d08-126">(2017년 전에 제공된 이전의 비즈니스용 Skype 클라이언트는 TeamsUpgradePolicy를 존중하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="b0d08-127">최신 비즈니스용 Skype 클라이언트를 사용하고 있는지 확인)</span><span class="sxs-lookup"><span data-stu-id="b0d08-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="b0d08-128">[TeamsUpgradePolicy의](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)속성인 모드 [mode](migration-interop-guidance-for-teams-with-skype.md)개념을 사용하여 사용자의 Teams 전환을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="b0d08-129">위에서 설명한 대로 Teams로 마이그레이션된 사용자는 "TeamsOnly" 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="b0d08-130">Teams로 마이그레이션하는 조직의 경우 궁극적인 목표는 모든 사용자를 TeamsOnly 모드로 이동하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

>[!NOTE]
><span data-ttu-id="b0d08-131">비즈니스용 Skype-프레미스 계정이 있는 사용자는 TeamsOnly가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-131">Users who have a Skype for Business on-premises account cannot be TeamsOnly.</span></span> <span data-ttu-id="b0d08-132">이러한 사용자는 제도 모드에서 [Teams를](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)사용할 수 있습니다. 하지만 TeamsOnly 모드에서 사용할 수 있는 전체 Teams 기능은 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-132">Although these users can [use Teams in Islands mode](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype), this does not provide the full set of Teams functionality that is available in TeamsOnly mode.</span></span> <span data-ttu-id="b0d08-133">이러한 사용자를 TeamsOnly로 만들 수 있도록 하기 위해 해당 사용자를 비즈니스용 Skype 서버 도구에서 사용하여 클라우드로 `Move-CsUser` 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d08-133">To make these users TeamsOnly, they must be moved to the cloud using `Move-CsUser` in the on-premises Skype for Business Server tools.</span></span>

<span data-ttu-id="b0d08-134">그래.</span><span class="sxs-lookup"><span data-stu-id="b0d08-134">OK.</span></span> <span data-ttu-id="b0d08-135">시작해보죠.</span><span class="sxs-lookup"><span data-stu-id="b0d08-135">Let's get started.</span></span>  <span data-ttu-id="b0d08-136">첫 번째 단계는 사용할 수 있는 [업그레이드 방법을 이해하는 것입니다.](upgrade-to-teams-on-prem-upgrade-methods.md)</span><span class="sxs-lookup"><span data-stu-id="b0d08-136">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="b0d08-137">관련 링크</span><span class="sxs-lookup"><span data-stu-id="b0d08-137">Related links</span></span>

[<span data-ttu-id="b0d08-138">비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침</span><span class="sxs-lookup"><span data-stu-id="b0d08-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="b0d08-139">비즈니스용 Skype Server와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="b0d08-139">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="b0d08-140">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="b0d08-140">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="b0d08-141">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="b0d08-141">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="b0d08-142">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="b0d08-142">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="b0d08-143">MMS(모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="b0d08-143">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

