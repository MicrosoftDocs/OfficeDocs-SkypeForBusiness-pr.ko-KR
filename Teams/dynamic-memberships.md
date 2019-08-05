---
title: 팀의 동적 멤버 자격 개요
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
description: AAD를 기반으로 하는 동적 팀 구성원 자격에 대해 알아보세요.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f48309b5816c61668d240087c1f2815fc94ebe4
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184343"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="11ade-103">팀의 동적 멤버 자격 개요</span><span class="sxs-lookup"><span data-stu-id="11ade-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="11ade-104">Microsoft 팀은 *동적 구성원*을 사용 하 여 Office 365 그룹과 연결 된 팀을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-104">Microsoft Teams supports teams associated with Office 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="11ade-105">동적 멤버 자격을 사용 하면 Azure Active Directory (Azure AD)의 특정 사용자 특성을 확인 하는 하나 이상의 규칙으로 팀 구성원을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="11ade-106">사용자 특성이 변경 되거나 사용자가 테 넌 트에 가입 하 고 나갈 때 사용자가 자동으로 올바른 팀에 추가 또는 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="11ade-107">동적 구성원 자격을 통해 조직의 특정 cohorts 사용자에 대 한 팀을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="11ade-108">사용할 수 있는 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-108">Possible scenarios include:</span></span>
- <span data-ttu-id="11ade-109">병원은 nurses, doctors 및 surgeons에 대 한 고유한 팀을 만들어 브로드캐스트 통신을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="11ade-110">이는 병원이 임시 직원을 사용 하는 경우 특히 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="11ade-111">대학은 자주 변경 되는 adjunct 교직원을 포함 하 여 특정 대학 내의 모든 교직원을 위한 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="11ade-112">비행기는 각 비행에 대 한 팀 (예: 시카고에서 애틀랜타 까지의 화요일)을 만들고 필요에 따라 자주 변경 되는 비행 crew을 자동으로 할당 하거나 제거 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="11ade-113">이 기능을 사용 하면 지정 된 팀의 구성원이 멤버 자격을 수동으로 관리 하는 대신 특정 조건 집합에 따라 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="11ade-114">이 작업을 수행 하려면 Azure AD Premium P1 라이선스와 팀 구성원 자격을 테 넌 트 관리자가 사용자의 모든 Azure AD 속성에 [할당할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="11ade-115">Microsoft 팀은 팀의 Office 365 그룹에 영향을 미치는 경우 동적 구성원 변경을 반영 하는 데 몇 분에서 최대 2 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="11ade-116">규칙은 팀 구성원 인 사용자가 아닌 팀 소유자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="11ade-117">팀 및 채널 크기에 대 한 현재 제한에 대 한 [Microsoft 팀의 제한 및 사양을](limits-specifications-teams.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="11ade-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="11ade-118">멤버가 동적 그룹 규칙으로 정의 되므로 소유자는 팀 구성원으로 사용자를 추가 하거나 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> - <span data-ttu-id="11ade-119">구성원은 동적 그룹으로 지원 되는 팀에서 나갈 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-119">Members will not be able to leave teams backed by dynamic groups.</span></span>


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="11ade-120">동적 구성원 자격을 사용 하 여 Office 365 그룹 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="11ade-120">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="11ade-121">테 넌 트 관리자로 로그인 한 [후 동적 그룹 만들기](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)의 지침에 따라 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="11ade-122">필요에 따라 [Azure Active Directory의 그룹에 대 한 동적 구성원 규칙](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="11ade-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="11ade-123">O365 그룹을 사용 하 여 새 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="11ade-123">Create a new team with your O365 group</span></span>

<span data-ttu-id="11ade-124">이제 구성원 변경 내용이 적용 되는 시간을 허용 하 고 [Microsoft 팀과 기존 Office 365 그룹 향상](enhance-office-365-groups.md)에 설명 된 대로 새 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="11ade-125">기존 팀에 동적 구성원 자격 적용</span><span class="sxs-lookup"><span data-stu-id="11ade-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="11ade-126">또한 기존 팀을 가져와 [정적 그룹 구성원을 Azure Active Directory에서 동적으로 변경](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)하는 방법에 설명 된 것 처럼 동적인 구성원을 포함 하도록 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="11ade-127">클라이언트 동작 변경</span><span class="sxs-lookup"><span data-stu-id="11ade-127">Changes in client behavior</span></span>

<span data-ttu-id="11ade-128">팀에 대 한 동적 구성원 자격이 활성화 되 면 팀 클라이언트는 더 이상 구성원에 대 한 멤버 관리를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="11ade-129">구성원을 추가 하 고, 구성원 역할을 편집 하 고, 참가 요청을 보내고 승인 하며, 팀을 모두 숨길 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="11ade-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
