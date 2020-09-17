---
title: 비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드-Microsoft 팀
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7156c02dff45e170efde9314c15b5688fd43058
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940678"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="1cc84-103">비즈니스용 Skype Server 온-프레미스를 사용 하는 조직에 대 한 업그레이드 고려 사항 &mdash; IT 관리자 용</span><span class="sxs-lookup"><span data-stu-id="1cc84-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="1cc84-104">이 문서에서는 비즈니스용 Skype Server 온-프레미스를 사용 하는 조직에 대 한 추가 고려 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="1cc84-105">이 문서는 IT 관리자의 업그레이드 개념 및 구현을 설명 하는 여러 가지 항목 중 네 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="1cc84-106">개요</span><span class="sxs-lookup"><span data-stu-id="1cc84-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="1cc84-107">업그레이드 방법</span><span class="sxs-lookup"><span data-stu-id="1cc84-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="1cc84-108">업그레이드 관리 도구</span><span class="sxs-lookup"><span data-stu-id="1cc84-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="1cc84-109">**비즈니스용 Skype 온-프레미스를 사용 하는 조직에 대 한 추가 고려 사항** (이 문서)</span><span class="sxs-lookup"><span data-stu-id="1cc84-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="1cc84-110">업그레이드 구현</span><span class="sxs-lookup"><span data-stu-id="1cc84-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="1cc84-111">PSTN (공개 통신 네트워크) 고려 사항</span><span class="sxs-lookup"><span data-stu-id="1cc84-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="1cc84-112">또한 다음 문서에서는 중요 한 업그레이드 개념 및 공존 동작에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="1cc84-113">팀과 비즈니스용 Skype의 공존</span><span class="sxs-lookup"><span data-stu-id="1cc84-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="1cc84-114">공존 모드-참조</span><span class="sxs-lookup"><span data-stu-id="1cc84-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="1cc84-115">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="1cc84-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="1cc84-116">비즈니스용 Skype Server 온-프레미스를 사용 하는 조직에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="1cc84-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="1cc84-117">비즈니스용 Skype 하이브리드을 설정 하는 것은 팀 전용 모드로 마이그레이션하는 필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="1cc84-118">통합 없이 아일랜드 모드에서 팀을 사용할 수 있지만, 사용자가 비즈니스용 Skype 온-프레미스에서 비즈니스용 Skype Online ( [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)사용)으로 이동할 때 까지는 TeamsOnly 모드 전환 기능을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="1cc84-119">자세한 내용은 [하이브리드 연결 구성을](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1cc84-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="1cc84-120">조직에 비즈니스용 Skype 서버가 있고 하이브리드 연결을 구성 하지 않은 상태에서 팀을 사용 하 여 팀의 기능을 관리 하려면 onmicrosoft.com 도메인이 있는 관리자 계정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="1cc84-121">비즈니스용 Skype 계정이 있는 (즉, 이동-CsUser를 사용 하 여 클라우드로 아직 이동 하지 않은) 팀 사용자는 비즈니스용 Skype 사용자와 상호 운용할 수 없으며 외부 사용자와 페더레이션 할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="1cc84-122">이 기능은 사용자를 클라우드로 이동한 후에만 사용할 수 있습니다 (예를 들어, 아일랜드 모드에서 또는 Team사용자만 해당).</span><span class="sxs-lookup"><span data-stu-id="1cc84-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="1cc84-123">비즈니스용 Skype 계정을 보유 하 고 있는 사용자가 있는 경우, 온-프레미스 Skype 계정으로 모든 사용자에 게 다른 모드를 명시적으로 할당 하지 않는 한, 테 넌 트 수준에서 TeamsOnly 모드를 할당 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-123">If you have any users with Skype for Business accounts on-premises, you must not assign TeamsOnly mode at the tenant level, unless you explicitly assign some other mode to all users with on-premises Skype for Business accounts.</span></span> 

- <span data-ttu-id="1cc84-124">올바른 비즈니스용 Skype 특성을 사용 하 여 사용자가 Azure AD로 적절 하 게 동기화 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-124">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="1cc84-125">이러한 특성은 모두 "msRTCSIP"이 포함 된 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-125">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="1cc84-126">사용자가 Azure AD에 올바르게 동기화 되지 않은 경우 팀의 관리 도구에서 이러한 사용자를 관리할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-126">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="1cc84-127">예를 들어 이러한 특성을 적절 하 게 동기화 하지 않는 한 온-프레미스 사용자에 게 팀 정책을 할당할 수 없게 됩니다. 자세한 내용은 [팀 및 비즈니스용 Skype에 대 한 AZURE AD Connect 구성을](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1cc84-127">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="1cc84-128">하이브리드 조직에서 새 팀 또는 비즈니스용 Skype Online 사용자를 만들려면 *먼저 비즈니스용 Skype Server 온-프레미스에서 사용자를 사용 하도록 설정*하 고 사용자를 이동-csuser를 사용 하 여 온-프레미스에서 클라우드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-128">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="1cc84-129">온-프레미스에서 사용자를 만들면 남아 있는 나머지 온-프레미스 비즈니스용 Skype 사용자가 새로 만든 사용자에 게 경로를 지정할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-129">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="1cc84-130">모든 사용자가 온라인으로 이동한 후에는 온-프레미스에서 사용자를 활성화 하는 데 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-130">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="1cc84-131">사용자가 온-프레미스에서 클라우드로 이동 하는 경우, 해당 사용자가 구성한 모임은 비즈니스용 Skype Online 또는 팀으로 마이그레이션됩니다--MoveToTeams 스위치가 지정 되었는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-131">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="1cc84-132">온-프레미스 사용자 용 Skype for Business 클라이언트에 알림을 표시 하려는 경우 온-프레미스 도구 모음에서 TeamsUpgradePolicy를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-132">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="1cc84-133">NotifySfbUsers 매개 변수만 온-프레미스 사용자와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-133">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="1cc84-134">온-프레미스 사용자는 TeamsUpgradePolicy의 온라인 인스턴스에서 자신의 모드를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-134">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="1cc84-135">[허용-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)의 메모를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1cc84-135">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="1cc84-136">2 월 3 일 이후에 만들어진 모든 새 테 넌 트는 조직에 비즈니스용 Skype 서버에 대 한 온-프레미스 배포가 이미 있는 경우 2019를 제외 하 고는 TeamsOnly 넌 트로만 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-136">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="1cc84-137">Microsoft는 DNS 레코드를 사용 하 여 온-프레미스 비즈니스용 Skype 서버 조직을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-137">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="1cc84-138">조직에서 공용 DNS 항목이 없는 온-프레미스 비즈니스용 Skype 서버를 사용 하는 경우 Microsoft 지원에 전화를 걸어 새 테 넌 트가 다운 그레이드 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc84-138">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 



















## <a name="related-links"></a><span data-ttu-id="1cc84-139">관련 링크</span><span class="sxs-lookup"><span data-stu-id="1cc84-139">Related links</span></span>

[<span data-ttu-id="1cc84-140">비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="1cc84-140">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="1cc84-141">비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="1cc84-141">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="1cc84-142">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="1cc84-142">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="1cc84-143">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="1cc84-143">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="1cc84-144">부여-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="1cc84-144">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="1cc84-145">MMS (모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="1cc84-145">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

