---
title: 팀의 동적 구성원 개요
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: 동적 Microsoft Teams 사용하여 Microsoft 365 그룹과 연결된 팀을 지원하는 방법을 알아보습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74974f7b94a5d1bcadb340e132dae9e3b39a7704
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856327"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="00698-103">팀의 동적 구성원 개요</span><span class="sxs-lookup"><span data-stu-id="00698-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="00698-104">Microsoft Teams 멤버 자격을 사용하여 Microsoft 365 그룹과 연결된 *팀을 지원합니다.*</span><span class="sxs-lookup"><span data-stu-id="00698-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="00698-105">동적 멤버 자격을 사용하면 Azure AD(Azure AD)에서 특정 사용자 특성을 검사하는 하나 이상의 규칙에 Azure Active Directory 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00698-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="00698-106">사용자 특성이 변경되거나 사용자가 테넌트에 참가하고 나가면 사용자가 자동으로 추가되거나 올바른 팀에 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="00698-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="00698-107">동적 멤버 자격을 사용하면 조직의 특정 사용자 코호트에 대한 팀을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00698-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="00698-108">가능한 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00698-108">Possible scenarios include:</span></span>
- <span data-ttu-id="00698-109">병원은 통신을 브로드캐스트하기 위해 간호사, 의사 및 외과 의사를 위한 고유한 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00698-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="00698-110">이는 병원에서 임시 직원을 의존하는 경우 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="00698-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="00698-111">대학은 자주 변경되는 2학년 교직원을 포함하여 특정 대학 내의 모든 교직원에 대한 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00698-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="00698-112">항공사는 각 항공편(예: 시카고에서 애틀랜타로의 화요일 오후 논스톱)에 대한 팀을 만들고, 자주 변경되는 승무원이 필요한 경우 자동으로 할당되거나 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="00698-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="00698-113">이 기능을 사용하여 특정 팀의 구성원은 수동으로 멤버 자격을 관리하는 대신 특정 조건 집합에 따라 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="00698-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="00698-114">이렇게 하려면 테넌트 Premium 관리자 계정이 있는 경우 [](/azure/active-directory/users-groups-roles/groups-dynamic-membership) 테넌트 관리자가 Azure AD 속성에 대해 Azure AD Premium 팀 멤버 자격을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00698-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="00698-115">Microsoft Teams 팀의 그룹에서 적용된 동적 멤버 자격 변경 내용을 반영하기 위해 몇 분에서 최대 2시간까지 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00698-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

<span data-ttu-id="00698-116">동적 그룹으로 팀을 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="00698-116">When using teams with dynamic groups:</span></span>

- <span data-ttu-id="00698-117">규칙은 팀 구성원을 정의할 수 있지만 팀 소유자는 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00698-117">Rules can define who is a team member, but not who is a team owner.</span></span>
- <span data-ttu-id="00698-118">소유자는 구성원이 동적 그룹 규칙으로 정의되어 팀의 구성원으로 사용자를 추가하거나 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00698-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
- <span data-ttu-id="00698-119">Teams 클라이언트는 팀에 대한 구성원 관리를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00698-119">Teams clients don't allow member management for the team.</span></span> <span data-ttu-id="00698-120">멤버를 추가하고, 멤버 역할을 편집하고, 조인 요청을 보내고 승인하고, 팀을 떠나는 옵션은 모두 숨겨져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00698-120">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>

<span data-ttu-id="00698-121">동적 멤버 자격을 사용하는 팀을 만들 경우 동적 그룹 Microsoft 365 만든 다음 해당 [그룹에서](/azure/active-directory/users-groups-roles/groups-create-rule) 팀을 [만들어야 합니다.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="00698-121">To create a team that uses dynamic membership, start by [creating a dynamic Microsoft 365 group](/azure/active-directory/users-groups-roles/groups-create-rule) and then [create a team from that group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

<span data-ttu-id="00698-122">기존 팀을 동적 멤버 자격으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00698-122">You can change an existing team to have a dynamic membership.</span></span> <span data-ttu-id="00698-123">자세한 [내용은 정적](/azure/active-directory/users-groups-roles/groups-change-type) 그룹 멤버 자격을 Azure Active Directory 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="00698-123">See [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="00698-124">관련 항목</span><span class="sxs-lookup"><span data-stu-id="00698-124">Related topics</span></span>

[<span data-ttu-id="00698-125">Microsoft Teams의 제한 사항 및 사양</span><span class="sxs-lookup"><span data-stu-id="00698-125">Limits and specifications for Microsoft Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="00698-126">그룹의 동적 멤버 자격 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="00698-126">Dynamic membership rules for groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
