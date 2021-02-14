---
title: 비즈니스용 Skype-프레미스 배포에서 Teams로 업그레이드 - Microsoft Teams
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
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533595"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="0a032-103">IT 관리자를 위해 비즈니스용 Skype Server가 있는 조직에 대한 업그레이드 고려 &mdash; 사항</span><span class="sxs-lookup"><span data-stu-id="0a032-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="0a032-104">이 문서에서는 비즈니스용 Skype 서버가 있는 조직에 대한 추가 고려 사항을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="0a032-105">이 문서는 IT 관리자를 위한 업그레이드 개념 및 구현을 설명하는 네 번째 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="0a032-106">개요</span><span class="sxs-lookup"><span data-stu-id="0a032-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="0a032-107">업그레이드 방법</span><span class="sxs-lookup"><span data-stu-id="0a032-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="0a032-108">업그레이드를 관리하기 위한 도구</span><span class="sxs-lookup"><span data-stu-id="0a032-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="0a032-109">**비즈니스용 Skype가 있는** 조직에 대한 추가 고려 사항(이 문서)</span><span class="sxs-lookup"><span data-stu-id="0a032-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="0a032-110">업그레이드 구현</span><span class="sxs-lookup"><span data-stu-id="0a032-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="0a032-111">PSTN(공용 전환 전화 네트워크) 고려 사항</span><span class="sxs-lookup"><span data-stu-id="0a032-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="0a032-112">또한 다음 문서에서는 중요한 업그레이드 개념 및 공존 동작을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="0a032-113">Teams 및 비즈니스용 Skype의 공존</span><span class="sxs-lookup"><span data-stu-id="0a032-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="0a032-114">공존 모드 - 참조</span><span class="sxs-lookup"><span data-stu-id="0a032-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="0a032-115">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="0a032-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="0a032-116">비즈니스용 Skype Server가 있는 조직에 대한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="0a032-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="0a032-117">TeamsOnly 모드로 마이그레이션하려면 비즈니스용 Skype 하이브리드를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="0a032-118">하이브리드 없이 제도 모드에서 Teams를 사용할 수 있는 반면 사용자가 비즈니스용 Skype On-프레미스에서 비즈니스용 Skype Online으로 전환될 때까지 TeamsOnly 모드로 전환할 수 [없습니다(Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)사용).</span><span class="sxs-lookup"><span data-stu-id="0a032-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="0a032-119">자세한 내용은 하이브리드 연결 [구성을 참조하세요.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="0a032-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="0a032-120">조직에 비즈니스용 Skype 서버가 있지만 하이브리드 연결을 구성하지 않은 경우 Teams 기능을 관리하려면 .onmicrosoft.com 도메인이 있는 관리 계정을 onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="0a032-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="0a032-121">비즈니스용 Skype 계정이 있는 팀 사용자(즉, Move-CsUser를 사용하여 클라우드로 아직 이동되지 않은 경우)는 비즈니스용 Skype 사용자와 상호 협력할 수 없으며 외부 사용자와 페더맹할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="0a032-122">이 기능은 사용자가 클라우드로 이동한 후(제도 모드 또는 TeamsOnly 사용자로) 한 번만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="0a032-123">비즈니스용 Skype 계정이 있는 사용자가 있는 경우 테넌트 수준에서 TeamsOnly 모드를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="0a032-124">먼저 클라우드로의 마이그레이션을 완료하려면 하이브리드를 사용하지 않도록 설정하여 비즈니스용 Skype 계정이 있는 모든 사용자를 클라우드로 이동해야 `Move-CsUser` [합니다.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)</span><span class="sxs-lookup"><span data-stu-id="0a032-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="0a032-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` lyncdiscover DNS 레코드가 Office 365가 아닌 다른 위치를 향하는 것으로 감지되면 테넌트 수준에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="0a032-126">사용자가 올바른 비즈니스용 Skype 특성을 사용하여 Azure AD에 올바르게 동기화되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="0a032-127">이러한 특성은 모두 "msRTCSIP-"가 있는 모든 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="0a032-128">사용자가 Azure AD에 제대로 동기화되지 않은 경우 Teams의 관리 도구에서 이러한 사용자를 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="0a032-129">(예를 들어 이러한 특성을 제대로 동기화하지 않으면 Teams 정책을 프레미스 사용자에게 할당할 수 없습니다.) 자세한 내용은 Teams 및 비즈니스용 [Skype에 대한 Azure AD Connect 구성을 참조하세요.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)</span><span class="sxs-lookup"><span data-stu-id="0a032-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="0a032-130">하이브리드 조직에서 새 TeamsOnly 또는 비즈니스용 Skype Online 사용자를 만들하려면 먼저 비즈니스용 *Skype Server의* 사용자를 사용하도록 설정한 다음, Move-CsUser를 사용하여 사용자를 클라우드로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="0a032-131">먼저 사용자를 프레미스에서 만들면 나머지 모든 나머지 비즈니스용 Skype 사용자가 새로 만든 사용자로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="0a032-132">모든 사용자가 온라인으로 이동된 후 더 이상 먼저 사용자가온-프레미스에서 사용하도록 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="0a032-133">사용자가 프레미스에서 클라우드로 이동하면 -MoveToTeams 스위치가 지정되어 있는지 여부에 따라 해당 사용자가 구성한 모임이 비즈니스용 Skype Online 또는 Teams로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="0a032-134">비즈니스용 Skype 클라이언트에서 알림을 프레미스 사용자에 대해 표시하려면, 이 도구에서 TeamsUpgradePolicy를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="0a032-135">NotifySfbUsers 매개 변수만이-프레미스 사용자와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="0a032-136">프레미스 사용자는 TeamsUpgradePolicy의 온라인 인스턴스에서 자신의 모드를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="0a032-137">[Grant-CsTeamsUpgradePolicy의 참고를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0a032-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="0a032-138">2019년 9월 3일 이후에 만든 모든 새 테넌트는 조직이 비즈니스용 Skype 서버의 이미 프레미스 배포를 하지 않는 한 TeamsOnly 테넌트로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="0a032-139">Microsoft는 DNS 레코드를 사용하여 비즈니스용 Skype 서버 조직을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="0a032-140">조직에 공용 DNS 항목이 없는 비즈니스용 Skype Server가 있는 경우 새 테넌트가 다운그레드되어 있도록 Microsoft 지원에 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a032-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="0a032-141">관련 링크</span><span class="sxs-lookup"><span data-stu-id="0a032-141">Related links</span></span>

[<span data-ttu-id="0a032-142">비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침</span><span class="sxs-lookup"><span data-stu-id="0a032-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="0a032-143">비즈니스용 Skype Server와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="0a032-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="0a032-144">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="0a032-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="0a032-145">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="0a032-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="0a032-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="0a032-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="0a032-147">MMS(모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="0a032-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

