---
title: 팀에서 관리 계획-Microsoft 팀
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 이 문서에서는 팀에서 관리 기능을 구현 하기 위해 계획 하는 방법에 대해 설명 합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a196dfee988a41a5d8145d9b6256d1df6e714133
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905830"
---
# <a name="plan-for-governance-in-teams"></a><span data-ttu-id="d54fe-103">Teams에서 거버넌스 계획</span><span class="sxs-lookup"><span data-stu-id="d54fe-103">Plan for governance in Teams</span></span>

<span data-ttu-id="d54fe-104">팀은 조직에서 요구할 수 있는 모든 관리 기능을 구현 하는 다양 한 도구 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-104">Teams provides a rich set of tools to implement any governance capabilities your organization might require.</span></span> <span data-ttu-id="d54fe-105">이 문서에서는 IT 전문가에 게 관리 요구 사항 및이를 충족 하는 방법에 대 한 질문을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-105">This article guides IT pros to ask the right questions to determine their requirements for governance, and how to meet them.</span></span> 

> [!Tip] 
> <span data-ttu-id="d54fe-106">Microsoft 팀의 경영진에 대 한 자세한 정보를 알아보려면 [Microsoft 팀의 지배 구조, 관리, 수명](https://aka.ms/teams-governance) 등 세션을 시청 하세요.</span><span class="sxs-lookup"><span data-stu-id="d54fe-106">Watch the following session to learn about more about Governance in Microsoft Teams: [Governance, management and lifecycle in Microsoft Teams](https://aka.ms/teams-governance)</span></span>

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a><span data-ttu-id="d54fe-107">그룹 및 팀 만들기, 이름 지정, 분류, 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="d54fe-107">Group and team creation, naming, classification, and guest access</span></span>

<span data-ttu-id="d54fe-108">조직에서 팀의 이름을 지정 하 고 분류 하는 방법, 게스트를 팀 구성원으로 추가할 수 있는지 여부, 그리고 팀을 만들 수 있는 사람에 게 엄격한 컨트롤을 구현 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-108">Your organization might require that you implement strict controls on how teams are named and classified, whether guests can be added as team members, and who can create teams.</span></span> <span data-ttu-id="d54fe-109">Azure AD (Active Directory)를 사용 하 여 이러한 영역을 각각 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-109">You can configure each of these areas by using Azure Active Directory (Azure AD).</span></span> 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |<span data-ttu-id="d54fe-110">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="d54fe-110">Decision points</span></span>|<ul><li><span data-ttu-id="d54fe-111">조직에 팀의 특정 명명 규칙이 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="d54fe-111">Does your organization require a specific naming convention for teams?</span></span></li><li><span data-ttu-id="d54fe-112">팀 작성자에 게 조직 고유의 분류를 팀에 할당할 수 있는 기능이 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="d54fe-112">Do team creators need the ability to assign organization-specific classifications to teams?</span></span></li><li><span data-ttu-id="d54fe-113">팀에 게 게스트를 추가 하는 기능에 대 한 권한을 제한 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d54fe-113">Do you need to restrict the ability to add guests to teams on a per-team basis?</span></span></li><li><span data-ttu-id="d54fe-114">조직에서 팀을 만들 수 있는 사람을 제한 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d54fe-114">Does your organization require limiting who can create teams?</span></span></li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|<span data-ttu-id="d54fe-115">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d54fe-115">Next steps</span></span>|<ul><li><span data-ttu-id="d54fe-116">조직의 팀 만들기, 이름 지정, 분류 및 게스트 액세스에 대 한 요구 사항을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-116">Document your organization’s requirements for team creation, naming, classification, and guest access.</span></span></li><li><span data-ttu-id="d54fe-117">이러한 요구 사항을 팀의 일부로 구현 하는 계획을 세워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-117">Plan to implement these requirements as a part of your Teams rollout.</span></span></li><li><span data-ttu-id="d54fe-118">팀 사용자에 게 예상할 수 있는 동작을 알리기 위해 정책을 전달 하 고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-118">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="d54fe-119">조직의 요구 사항을 캡처하려면 다음 표를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-119">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="d54fe-120">기능</span><span class="sxs-lookup"><span data-stu-id="d54fe-120">Capability</span></span> |<span data-ttu-id="d54fe-121">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d54fe-121">Details</span></span> |<span data-ttu-id="d54fe-122">Azure AD Premium</span><span class="sxs-lookup"><span data-stu-id="d54fe-122">Azure AD Premium</span></span> <br> <span data-ttu-id="d54fe-123">라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="d54fe-123">license required</span></span> |<span data-ttu-id="d54fe-124">덕분</span><span class="sxs-lookup"><span data-stu-id="d54fe-124">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="d54fe-125">팀 이름 지정 정책</span><span class="sxs-lookup"><span data-stu-id="d54fe-125">Team naming policy</span></span> | <span data-ttu-id="d54fe-126">접두사-접미사 기반, 사용자 지정 차단 된 단어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-126">Use Prefix-Suffix–based, Custom Blocked Words.</span></span> |<span data-ttu-id="d54fe-127">P1</span><span class="sxs-lookup"><span data-stu-id="d54fe-127">P1</span></span> |<span data-ttu-id="d54fe-128">TBD</span><span class="sxs-lookup"><span data-stu-id="d54fe-128">TBD</span></span> |
|<span data-ttu-id="d54fe-129">팀 분류</span><span class="sxs-lookup"><span data-stu-id="d54fe-129">Team classification</span></span> |<span data-ttu-id="d54fe-130">팀에 분류를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-130">Assign classifications to teams.</span></span> |<span data-ttu-id="d54fe-131">P1</span><span class="sxs-lookup"><span data-stu-id="d54fe-131">P1</span></span> |<span data-ttu-id="d54fe-132">TBD</span><span class="sxs-lookup"><span data-stu-id="d54fe-132">TBD</span></span> |
|<span data-ttu-id="d54fe-133">팀 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="d54fe-133">Team guest access</span></span> |<span data-ttu-id="d54fe-134">팀에 게스트를 추가 하는 것을 허용 하거나 금지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-134">Allow or prevent guests from being added to teams.</span></span> |<span data-ttu-id="d54fe-135">아니요</span><span class="sxs-lookup"><span data-stu-id="d54fe-135">No</span></span> |<span data-ttu-id="d54fe-136">TBD</span><span class="sxs-lookup"><span data-stu-id="d54fe-136">TBD</span></span> |
|<span data-ttu-id="d54fe-137">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="d54fe-137">Team creation</span></span> |<span data-ttu-id="d54fe-138">팀 만들기를 관리자로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-138">Limit team creation to administrators.</span></span> |<span data-ttu-id="d54fe-139">아니요</span><span class="sxs-lookup"><span data-stu-id="d54fe-139">No</span></span> |<span data-ttu-id="d54fe-140">TBD</span><span class="sxs-lookup"><span data-stu-id="d54fe-140">TBD</span></span>|
|<span data-ttu-id="d54fe-141">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="d54fe-141">Team creation</span></span> |<span data-ttu-id="d54fe-142">팀 만들기를 보안 그룹 구성원으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-142">Limit team creation to security group members.</span></span> |<span data-ttu-id="d54fe-143">P1</span><span class="sxs-lookup"><span data-stu-id="d54fe-143">P1</span></span> |<span data-ttu-id="d54fe-144">TBD</span><span class="sxs-lookup"><span data-stu-id="d54fe-144">TBD</span></span>|

> [!NOTE]
> <span data-ttu-id="d54fe-145">미리 계획 하는 데 도움이 되도록 [이러한 정책 설정 및 필요한 라이선스에 대해 자세히 알아보세요](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span><span class="sxs-lookup"><span data-stu-id="d54fe-145">To help you plan ahead, [learn more about setting these policies and what licenses they require](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings).</span></span>
> 
> [!NOTE]
> <span data-ttu-id="d54fe-146">그룹 및 팀 만들기를 제한 하면 많은 Office 365 서비스에서 서비스 기능을 위해 그룹을 만들어야 하기 때문에 사용자 생산성을 느리게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-146">Limiting group and team creation can slow your users’ productivity, because many Office 365 services require that groups be created for the service to function.</span></span> <span data-ttu-id="d54fe-147">추가 정보를 보려면 [Microsoft 365 그룹을 만드는 사용자를 제어 하는 이유](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)를 찾아 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-147">For additional information, navigate to and expand [Why control who creates Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why).</span></span>


#### <a name="additional-information"></a><span data-ttu-id="d54fe-148">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d54fe-148">Additional information</span></span>

<span data-ttu-id="d54fe-149">요구 사항을 결정 한 후에는 Azure AD 컨트롤을 사용 하 여이를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-149">After you’ve determined your requirements, you can implement them by using Azure AD controls.</span></span> <span data-ttu-id="d54fe-150">이러한 설정을 구현 하는 방법에 대 한 기술 지침은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d54fe-150">For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="d54fe-151">[그룹 설정 구성을 위한 Azure Active Directory cmdlet](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="d54fe-151">[Azure Active Directory cmdlets for configuring group settings](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).</span></span>

- <span data-ttu-id="d54fe-152">[Azure Active Directory에서 Microsoft 365 그룹에 대 한 이름 지정 정책을 적용](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-152">[Enforce a naming policy for Microsoft 365 groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>

- <span data-ttu-id="d54fe-153">[Microsoft 365 그룹 이름 지정 정책](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)</span><span class="sxs-lookup"><span data-stu-id="d54fe-153">[Microsoft 365 Groups naming policy](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>


## <a name="group-and-team-expiration-retention-and-archiving"></a><span data-ttu-id="d54fe-154">그룹 및 팀 만료, 보존 및 보관</span><span class="sxs-lookup"><span data-stu-id="d54fe-154">Group and team expiration, retention, and archiving</span></span>

<span data-ttu-id="d54fe-155">조직에 만료, 보존 및 보관 팀과 팀 데이터 (채널 메시지 및 채널 파일)에 대 한 정책을 설정 하는 데 필요한 추가 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-155">Your organization might have additional requirements for setting policies for expiration, retention, and archiving teams and teams data (channel messages and channel files).</span></span> <span data-ttu-id="d54fe-156">필요에 따라 정보를 보존 하거나 삭제 하기 위해 그룹 및 보존 정책의 수명 주기를 자동으로 관리 하 고 팀을 읽기 전용 모드로 설정 하 여 더 이상 활성 상태가 아닌 팀의 특정 시점 보기를 유지 하도록 그룹 만료 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-156">You can configure group expiration policies to automatically manage the lifecycle of the group and retention policies to preserve or delete information as needed, and you can archive teams (set them to read-only mode) to preserve a point-in-time view of a team that’s no longer active.</span></span>

|           |            |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d54fe-158">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="d54fe-158">Decision points</span></span>|<ul><li><span data-ttu-id="d54fe-159">조직에서 팀에 대해 만료 날짜를 지정 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d54fe-159">Does your organization require specifying an expiration date for teams?</span></span></li><li><span data-ttu-id="d54fe-160">조직의 특정 데이터 보존 정책을 팀에 적용 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d54fe-160">Does your organization require specific data retention policies be applied to teams?</span></span></li><li><span data-ttu-id="d54fe-161">조직에서 비활성 팀을 보관 하 여 콘텐츠를 읽기 전용 상태로 유지 하는 기능이 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="d54fe-161">Does your organization expect to require the ability to archive inactive teams to preserve the content in a read-only state?</span></span></li></ul>|
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/><span data-ttu-id="d54fe-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d54fe-163">Next steps</span></span>|<ul><li><span data-ttu-id="d54fe-164">조직의 팀 만료, 데이터 보존 및 보관에 대 한 요구 사항을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-164">Document your organization’s requirements for team expiration, data retention, and archiving.</span></span></li><li><span data-ttu-id="d54fe-165">이러한 요구 사항을 팀의 일부로 구현할 계획을 수립 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-165">Plan to implement these requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="d54fe-166">팀 사용자에 게 예상할 수 있는 동작을 알리기 위해 정책을 전달 하 고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-166">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

> [!TIP]
> <span data-ttu-id="d54fe-167">조직의 요구 사항을 캡처하려면 다음 표를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-167">Use the following table to capture your organization’s requirements.</span></span>

|<span data-ttu-id="d54fe-168">기능</span><span class="sxs-lookup"><span data-stu-id="d54fe-168">Capability</span></span> |<span data-ttu-id="d54fe-169">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d54fe-169">Details</span></span> |<span data-ttu-id="d54fe-170">Azure AD Premium 라이선스 필요</span><span class="sxs-lookup"><span data-stu-id="d54fe-170">Azure AD Premium license required</span></span> |<span data-ttu-id="d54fe-171">덕분</span><span class="sxs-lookup"><span data-stu-id="d54fe-171">Decision</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="d54fe-172">만료 정책</span><span class="sxs-lookup"><span data-stu-id="d54fe-172">Expiration policy</span></span> |<span data-ttu-id="d54fe-173">만료 정책을 설정 하 여 Microsoft 365 그룹의 수명 주기를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-173">Manage the lifecycle of Microsoft 365 groups by setting an expiration policy.</span></span> |<span data-ttu-id="d54fe-174">P1</span><span class="sxs-lookup"><span data-stu-id="d54fe-174">P1</span></span> |<span data-ttu-id="d54fe-175">TBD</span><span class="sxs-lookup"><span data-stu-id="d54fe-175">TBD</span></span>|
|<span data-ttu-id="d54fe-176">보존 정책</span><span class="sxs-lookup"><span data-stu-id="d54fe-176">Retention policy</span></span> |<span data-ttu-id="d54fe-177">보안 & 준수 센터에서 팀에 대 한 보존 정책을 설정 하 여 특정 기간에 대 한 데이터를 보존 하거나 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-177">Retain or delete data for a specific time period by setting retention policies for Teams in the Security & compliance center.</span></span> <span data-ttu-id="d54fe-178">**참고**:이 기능을 사용 하려면 Office 365 Enterprise E3 이상 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-178">**Note**: Using this feature requires licensing of Office 365 Enterprise E3 or above.</span></span> |<span data-ttu-id="d54fe-179">아니요</span><span class="sxs-lookup"><span data-stu-id="d54fe-179">No</span></span> |<span data-ttu-id="d54fe-180">TBD</span><span class="sxs-lookup"><span data-stu-id="d54fe-180">TBD</span></span> |
|<span data-ttu-id="d54fe-181">보관 및 복원</span><span class="sxs-lookup"><span data-stu-id="d54fe-181">Archive and restore</span></span> |<span data-ttu-id="d54fe-182">더 이상 활성 상태가 아닌 팀을 보관 하 되 참조를 위해 유지 하거나 나중에 다시 활성화 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="d54fe-182">Archive a team when it’s no longer active but you want to keep it around for reference or to reactivate in the future.</span></span> |<span data-ttu-id="d54fe-183">아니요</span><span class="sxs-lookup"><span data-stu-id="d54fe-183">No</span></span> |<span data-ttu-id="d54fe-184">TBD</span><span class="sxs-lookup"><span data-stu-id="d54fe-184">TBD</span></span> |

> [!Note]
> <span data-ttu-id="d54fe-185">그룹 만료는 Azure AD Premium 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-185">Group expiration is an Azure AD Premium feature.</span></span> <span data-ttu-id="d54fe-186">이 기능을 사용 하려면 테 넌 트에 설정 및 영향을 받는 그룹의 구성원을 구성 하는 관리자에 대 한 Azure AD Premium 및 라이선스 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-186">For this feature to be available, your tenant must have a subscription to Azure AD Premium and licenses for the administrator who configures the settings and the members of the affected groups.</span></span>

#### <a name="additional-information"></a><span data-ttu-id="d54fe-187">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d54fe-187">Additional information</span></span>

<span data-ttu-id="d54fe-188">이러한 설정을 구현 하는 방법에 대 한 기술 지침은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d54fe-188">For technical guidance on how to implement these settings, see:</span></span>

- <span data-ttu-id="d54fe-189">[Microsoft 365 그룹 만료를 설정](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-189">[Set up Microsoft 365 groups expiration](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle).</span></span>

- <span data-ttu-id="d54fe-190">[팀 보존 정책을 설정](retention-policies.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-190">[Set up Teams retention policies](retention-policies.md).</span></span>

- <span data-ttu-id="d54fe-191">[팀을 보관 하거나 복원](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-191">[Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>


## <a name="teams-feature-management"></a><span data-ttu-id="d54fe-192">팀 기능 관리</span><span class="sxs-lookup"><span data-stu-id="d54fe-192">Teams feature management</span></span>

<span data-ttu-id="d54fe-193">팀에 대 한 관리 및 수명 주기 관리의 또 다른 중요 한 측면은 사용자가 액세스할 수 있는 기능을 제어 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-193">Another important aspect of governance and lifecycle management for Teams is the ability to control what features your users will have access to.</span></span> <span data-ttu-id="d54fe-194">Office 365 조직 수준 또는 사용자 기준으로 메시징, 모임, 통화 기능을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-194">You can manage messaging, meeting, and calling features, either at the Office 365 organization level or per-user.</span></span> 


|         |         |
|---------|---------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="d54fe-196">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="d54fe-196">Decision points</span></span>|<ul><li><span data-ttu-id="d54fe-197">조직에서 전체 테 넌 트에 대 한 팀의 기능을 제한 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d54fe-197">Does your organization require limiting Teams features for your entire tenant?</span></span></li><li><span data-ttu-id="d54fe-198">조직에서 특정 사용자를 위해 팀의 기능을 제한 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d54fe-198">Does your organization require limiting Teams features for specific users?</span></span></li></ul>|
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/><span data-ttu-id="d54fe-200">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d54fe-200">Next steps</span></span>|<ul><li><span data-ttu-id="d54fe-201">테 넌 트 및 사용자 수준에서 팀 기능을 제한 하기 위한 조직의 요구 사항을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-201">Document your organization’s requirements for limiting Teams features at the tenant and user level.</span></span></li><li><span data-ttu-id="d54fe-202">팀의 일환으로 특정 요구 사항을 구현할 계획을 수립 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-202">Plan to implement your specific requirements as part of your Teams rollout.</span></span></li><li><span data-ttu-id="d54fe-203">팀 사용자에 게 예상할 수 있는 동작을 알리기 위해 정책을 전달 하 고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-203">Communicate and publish your policies to inform Teams users of the behavior they can expect.</span></span></li></ul>|

### <a name="teams-feature-management-focus-areas"></a><span data-ttu-id="d54fe-204">팀 기능 관리 포커스 영역</span><span class="sxs-lookup"><span data-stu-id="d54fe-204">Teams feature management focus areas</span></span>

<span data-ttu-id="d54fe-205">팀은 정책에 의해 메시징, 모임, 통화, 라이브 이벤트 기능 등을 제어 하는 세부적인 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-205">Teams provides granular capabilities for controlling messaging, meeting, calling, and live event features and more, via policies.</span></span> <span data-ttu-id="d54fe-206">기본적으로 또는 조직에 필요한 경우 사용자 기준으로 모든 사용자에 게 다른 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-206">Different policies can be applied to all users by default or per user as required by your organization.</span></span> 

<span data-ttu-id="d54fe-207">조직에 맞게 구현 하는 방법에 대 한 기술 지침을 포함 하 여 모든 설정에 대 한 자세한 목록은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d54fe-207">For detailed lists of all settings, including technical guidance on how to implement them for your organization, see the following articles:</span></span>

- [<span data-ttu-id="d54fe-208">조직에서 Microsoft Teams 설정 관리</span><span class="sxs-lookup"><span data-stu-id="d54fe-208">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)
- [<span data-ttu-id="d54fe-209">새 Microsoft Teams 관리 센터로 전환하는 동안 팀 관리</span><span class="sxs-lookup"><span data-stu-id="d54fe-209">Manage Teams during the transition to the new Microsoft Teams admin center</span></span>](manage-teams-skypeforbusiness-admin-center.md)
- [<span data-ttu-id="d54fe-210">팀에서 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="d54fe-210">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="d54fe-211">팀에서 메시징 정책 관리</span><span class="sxs-lookup"><span data-stu-id="d54fe-211">Manage messaging policies in Teams</span></span>](messaging-policies-in-teams.md)

<span data-ttu-id="d54fe-212">또한 채널에 대 한 중재를 설정 하 고 특정 사용자에 게 블로그 게시물을 만들고 응답할 수 있는 사람을 제어할 수 있도록 중재자 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-212">Additionally, you can set up moderation for a channel and give moderator capabilities to certain users so that they can control who can create channel posts and respond to them.</span></span> <span data-ttu-id="d54fe-213">자세한 내용은 [Microsoft 팀에서 채널 중재 설정 및 관리](manage-channel-moderation-in-teams.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d54fe-213">See [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md) for more information.</span></span>

## <a name="security-and-compliance"></a><span data-ttu-id="d54fe-214">보안 및 규정 준수</span><span class="sxs-lookup"><span data-stu-id="d54fe-214">Security and compliance</span></span>

<span data-ttu-id="d54fe-215">팀은 Office 365의 고급 보안 및 규정 준수 기능에 기반을 둠으로써 감사 및 보고, 준수 콘텐츠 검색, e-검색, 법적 보류, 보존 정책을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d54fe-215">Teams is built on the advanced security and compliance capabilities of Office 365 and supports auditing and reporting, compliance content search, e-discovery, Legal Hold, and retention policies.</span></span> 

> [!Important]
> <span data-ttu-id="d54fe-216">조직에 준수 및 보안 요구 사항이 있는 경우 [Microsoft 팀의 보안 및 준수에](security-compliance-overview.md)대 한 개요 문서에서 해당 항목에 대해 제공 되는 심층적인 콘텐츠를 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="d54fe-216">If your organization has compliance and security requirements, review the in-depth content provided about this topic in the article [Overview of security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d54fe-217">관련 주제</span><span class="sxs-lookup"><span data-stu-id="d54fe-217">Related topics</span></span>

[<span data-ttu-id="d54fe-218">Teams에 대한 거버넌스 빠른 시작</span><span class="sxs-lookup"><span data-stu-id="d54fe-218">Governance quick start for Teams</span></span>](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
