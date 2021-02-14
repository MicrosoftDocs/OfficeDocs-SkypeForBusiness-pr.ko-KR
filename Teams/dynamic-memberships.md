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
description: Microsoft Teams에서 동적 멤버 자격을 사용하여 Microsoft 365 그룹과 연결된 팀을 지원하는 방법에 대해 자세히 알아보습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75bd058d79b1f54a40ad0e42207178c9c29d08cd
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583927"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="b9ac3-103">팀의 동적 구성원 개요</span><span class="sxs-lookup"><span data-stu-id="b9ac3-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="b9ac3-104">Microsoft Teams는 동적 멤버 자격을 사용하여 Microsoft 365 그룹과 연결된 *팀을 지원합니다.*</span><span class="sxs-lookup"><span data-stu-id="b9ac3-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="b9ac3-105">동적 멤버 자격을 사용하면 Azure AD(Azure Active Directory)에서 특정 사용자 특성을 검사하는 하나 이상의 규칙으로 팀 멤버 자격을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b9ac3-106">사용자 특성이 변경되거나 사용자가 테넌트에 가입하고 나가면 사용자가 올바른 팀에 자동으로 추가되거나 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="b9ac3-107">동적 멤버 자격을 사용하면 조직의 특정 코호트에 대한 팀을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="b9ac3-108">가능한 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-108">Possible scenarios include:</span></span>
- <span data-ttu-id="b9ac3-109">병원은 간호사, 의사 및 외과의사와 통신을 브로드캐스트할 수 있는 고유한 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="b9ac3-110">이 방법은 병원에서 임시 직원을 고용하는 경우 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="b9ac3-111">대학은 자주 변경되는 부재 중 교직원을 포함하여 특정 대학 내의 모든 교직원을 위한 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="b9ac3-112">항공사는 각 플라이트에 대한 팀을 만들고(예: 화요일 오후 시카고에서 애틀랜타로의 출발이 아닌 화요일 오후) 자주 변경되는 플라이트 승무원을 자동으로 할당하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="b9ac3-113">이 기능을 사용하면 특정 팀의 구성원이 멤버 자격을 수동으로 관리하는 대신 특정 조건 집합에 따라 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="b9ac3-114">이렇게 하려면 테넌트 및 관리자 계정이 [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) 있는 경우 테넌트 관리자가 Azure AD Premium P1 라이선스 및 팀 멤버 자격을 사용자의 Azure AD 속성에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="b9ac3-115">Microsoft Teams는 팀의 Microsoft 365 그룹에 적용된 동적 멤버 자격 변경 내용을 반영하는 데 몇 분에서 최대 2시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="b9ac3-116">규칙은 팀 소유자가 아닌 팀 구성원을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="b9ac3-117">팀 및 채널 크기에 대한 현재 제한은 [Microsoft Teams의](limits-specifications-teams.md) 제한 및 사양을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="b9ac3-118">구성원은 동적 그룹 규칙에 의해 정의되어 팀의 구성원으로 사용자를 추가하거나 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> -    <span data-ttu-id="b9ac3-119">구성원은 동적 그룹에서 팀을 떠날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-119">Members will not be able to leave teams backed by dynamic groups.</span></span>

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a><span data-ttu-id="b9ac3-120">동적 멤버 자격을 통해 Microsoft 365 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="b9ac3-120">Creating and managing a Microsoft 365 group with dynamic membership</span></span>

<span data-ttu-id="b9ac3-121">테넌트 관리자로 로그인하는 동안 동적 그룹 만들기의 지침을 따르고 [상태를 검사합니다.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)</span><span class="sxs-lookup"><span data-stu-id="b9ac3-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="b9ac3-122">필요한 경우 Azure Active Directory의 그룹에 대한 동적 [멤버 자격 규칙을 참조하세요.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)</span><span class="sxs-lookup"><span data-stu-id="b9ac3-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-microsoft-365-group"></a><span data-ttu-id="b9ac3-123">Microsoft 365 그룹을 사용하여 새 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="b9ac3-123">Create a new team with your Microsoft 365 group</span></span>

<span data-ttu-id="b9ac3-124">이제 멤버 자격 변경이 적용될 시간을 허용하고 기존 그룹에서 팀 만들기에 설명된 새 [팀을 만들 수 있습니다.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="b9ac3-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Create a team from an existing group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="b9ac3-125">기존 팀에 동적 멤버 자격 적용</span><span class="sxs-lookup"><span data-stu-id="b9ac3-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="b9ac3-126">Azure Active Directory에서 정적 그룹 멤버 자격 변경에 설명된 바와 같이 기존 팀을 사용하여 동적 멤버 자격을 가지게 변경할 [수도 있습니다.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)</span><span class="sxs-lookup"><span data-stu-id="b9ac3-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="b9ac3-127">클라이언트 동작의 변경 내용</span><span class="sxs-lookup"><span data-stu-id="b9ac3-127">Changes in client behavior</span></span>

<span data-ttu-id="b9ac3-128">팀에 대해 동적 멤버 자격을 사용하도록 설정하면 Teams 클라이언트는 더 이상 팀에 대한 구성원 관리를 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="b9ac3-129">구성원을 추가하고, 구성원 역할을 편집하고, 참가 요청을 보내고 승인하고, 팀에서 나가는 옵션은 모두 숨겨져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ac3-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
