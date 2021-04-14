---
title: Azure Sentinel 및 Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: IT 관리자를 위한 Sentinel을 사용하여 Teams에서 발생할 수 있는 위협을 모니터링하고 헌팅하는 데 대한 보안 자문과 학습입니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3b2c37f7f3731b34abb5337bf954250e0c3564d
ms.sourcegitcommit: 046b020cee8af00a1d0e5f5866f847d42e8ad9a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51712770"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="5f026-103">Azure Sentinel 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5f026-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f026-104">이제 Azure Sentinel에 통합 커넥터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="5f026-105">자세한 내용은 [Azure Sentinel 365 로그 연결](/azure/sentinel/connect-office-365)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f026-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="5f026-106">이 경로는 이러한 로그를 수집하는 데 권장되는 경로로 아래 설명된 컬렉션 방법을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="5f026-107">Teams은 Microsoft 365 클라우드에서 통신 및 데이터 공유의 중심 역할을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-107">Teams serves a central role in communication and data-sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="5f026-108">Teams은 클라우드에서 매우 많은 기술을 활용하기 때문에 인적, 자동화된 분석을 통해 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-108">Since Teams touches on so many technologies in the Cloud, it can benefit from human and automated analysis.</span></span> <span data-ttu-id="5f026-109">이는 *로그 검색* 및 *모임 실시간 모니터링* 에 모두 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-109">This applies to both *hunting in logs*, and *real-time monitoring of meetings*.</span></span> <span data-ttu-id="5f026-110">Azure Sentinel은 관리자에게 이러한 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-110">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="5f026-111">Azure Sentinel에 대한 복습이 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="5f026-111">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="5f026-112">[이 문서](/azure/sentinel/overview)를 참고하시면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-112">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="5f026-113">Azure Sentinel 및 Microsoft Teams 활동 로그</span><span class="sxs-lookup"><span data-stu-id="5f026-113">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="5f026-114">이 문서에서는 Azure Sentinel에서 Teams의 활동 로그 수집에 초점을 두고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-114">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span>

<span data-ttu-id="5f026-115">Sentinel을 통해 관리자는 한 위치에서 보안 관리를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-115">Sentinel lets administrators do security management in one location.</span></span> <span data-ttu-id="5f026-116">여기에는 다음 관리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-116">This includes managing:</span></span>

- <span data-ttu-id="5f026-117">타사 장치</span><span class="sxs-lookup"><span data-stu-id="5f026-117">Third-party devices</span></span>
- <span data-ttu-id="5f026-118">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="5f026-118">Microsoft Threat Protection</span></span>
- <span data-ttu-id="5f026-119">Microsoft 365 Workloads</span><span class="sxs-lookup"><span data-stu-id="5f026-119">Microsoft 365 Workloads</span></span>

<span data-ttu-id="5f026-120">Sentinel 통합 문서와 실행 문서는 보안 모니터링을 *체계적* 으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-120">Sentinel workbooks and runbooks can make security monitoring *systematic*.</span></span> <span data-ttu-id="5f026-121">이 프로세스의 좋은 첫 번째 단계는 분석에 필요한 로그를 수집하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-121">A good first step in this process is collecting the logs needed analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="5f026-122">Azure Sentinel의 동일한 인스턴스에서 둘 이상의 Microsoft 365 구독을 노출시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-122">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="5f026-123">이는 기록 로그 파일 s에서 위협에 대한 [실시간 모니터링](/azure/sentinel/livestream)과 헌팅을 할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-123">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log files.</span></span> <span data-ttu-id="5f026-124">관리자는 단일 리소스 그룹 내에서, 여러 리소스 그룹에서 또는 다른 구독에서 [교차 리소스 쿼리](/azure/azure-monitor/log-query/cross-workspace-query)를 사용하여 헌팅을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-124">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="5f026-125">1단계: Teams 로그 수집: Microsoft 365에서 감사 로그 사용</span><span class="sxs-lookup"><span data-stu-id="5f026-125">Step 1: Collect Teams logs: Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="5f026-126">Teams은 Microsoft 365를 통해 작업을 기록하므로 감사 로그는 기본적으로 수집되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-126">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="5f026-127">[이러한 단계](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)를 통해 이 기능을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-127">Turn on this feature with [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span> <span data-ttu-id="5f026-128">Teams 데이터는 *Audit.General* 의 Microsoft 365 감사에서 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-128">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a><span data-ttu-id="5f026-129">2단계: Azure Sentinel 365 로그 연결</span><span class="sxs-lookup"><span data-stu-id="5f026-129">Step 2: Connect Office 365 logs to Azure Sentinel</span></span>

<span data-ttu-id="5f026-130">Azure Sentinel은 다른 Office 365 데이터와 함께 Teams 데이터를 Azure Sentinel로 수집할 수 있도록 Office 365 로그를 위한 내장 커넥터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-130">Azure Sentinel provides a built-in connector for Office 365 logs, which enables you to ingest Teams data into Azure Sentinel together with other Office 365 data.</span></span>
 
<span data-ttu-id="5f026-131">Azure Sentinel에서 Office 365 데이터 커넥터를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-131">In Azure Sentinel, enable the Office 365 data connector.</span></span> <span data-ttu-id="5f026-132">자세한 내용은 [Azure Sentinel 설명서](/azure/sentinel/connect-office-365)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f026-132">For more information, see the [Azure Sentinel documentation](/azure/sentinel/connect-office-365).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="5f026-133">유용한 헌팅 KQL 쿼리</span><span class="sxs-lookup"><span data-stu-id="5f026-133">Helpful hunting KQL queries</span></span>

<span data-ttu-id="5f026-134">이 쿼리를 사용하여 Teams 데이터와 Teams 환경에 익숙해지도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-134">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="5f026-135">환경의 모양과 작동 방식을 아는 것은 의심스러운 활동을 인식하는 데 바람직한 첫 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-135">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="5f026-136">여기서 위협 헌팅으로 분기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-136">From there, you can branch out into threat hunting.</span></span>

### <a name="federated-external-users-query"></a><span data-ttu-id="5f026-137">페더레이션된 외부 사용자 쿼리</span><span class="sxs-lookup"><span data-stu-id="5f026-137">Federated external users query</span></span>

<span data-ttu-id="5f026-138">페더레이션된 외부 사용자가 있는 Teams 사이트 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-138">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="5f026-139">이러한 사용자는 조직에서 소유하지 않은 도메인 이름 및/또는 UPN 접미사를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-139">These users have a domain name and/or a UPN suffix that isn't owned by your organization.</span></span>

<span data-ttu-id="5f026-140">이 예제 쿼리에서는 조직이 contoso.com를 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-140">In this example query, the organization owns contoso.com.</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
```

> [!TIP]
> <span data-ttu-id="5f026-141">Teams의 외부 및 게스트 액세스 유형에 대한 자세한 내용은 [다른 조직의 사용자](communicate-with-users-from-other-organizations.md)와 통신 또는 Teams 보안 가이드의 [참가자 유형](teams-security-guide.md#participant-types) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f026-141">To learn more about External and Guest access types in Teams see [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md), or the [Participant Types](teams-security-guide.md#participant-types) section in the Teams Security Guide.</span></span>

### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="5f026-142">최근에 가입한 사람 / 역할이 변경된 사람</span><span class="sxs-lookup"><span data-stu-id="5f026-142">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="5f026-143">특정 사용자를 쿼리하여 최근 7일 또는 일주일 이내에 Teams 채널에 추가되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-143">Query a specific user to check if they were added to a Teams channel in the last seven days, or within a week:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

<span data-ttu-id="5f026-144">지난 7일 동안 Teams에 대한 사용자 역할이 변경되었는지 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-144">Query whether a user's role changed for a Team in the last seven days:</span></span>

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="5f026-145">알 수 없는 조직이나 새 조직의 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="5f026-145">External users from unknown or new organizations</span></span>

<span data-ttu-id="5f026-146">Teams에서 사용자 환경이나 채널에 외부 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-146">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="5f026-147">조직은 종종 제한된 수의 주요 파트너 관계를 가지고 있으며, 이러한 파트너 들 사이에서 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-147">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="5f026-148">이 KQL는 이전에 보이거나 추가되지 않은 조직에서 온 팀에 추가된 외부 사용자를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-148">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

<span data-ttu-id="5f026-149">자세한 내용은 [Azure Sentinel 커뮤니티 Git 허브](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml)에서 쿼리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f026-149">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml).</span></span>

### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="5f026-150">추가된 후 제거된 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="5f026-150">External users who were added and then removed</span></span>

<span data-ttu-id="5f026-151">기존의 어느 정도의 액세스 권한이 있는 공격자는 Teams에 새 외부 계정을 추가하여 데이터에 액세스하고 데이터를 빼낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-151">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="5f026-152">또한 액세스한 사실을 숨기기 위해 해당 사용자를 신속히 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-152">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="5f026-153">이 쿼리는 Teams에 추가되고 신속히 제거되는 외부 계정을 헌팅하여 의심스러운 동작을 식별하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-153">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

<span data-ttu-id="5f026-154">자세한 내용은 [Azure Sentinel 커뮤니티 Git 허브](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml)에서 쿼리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f026-154">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml).</span></span>

### <a name="new-bot-or-application-added"></a><span data-ttu-id="5f026-155">새 봇 또는 애플리케이션이 추가됨</span><span class="sxs-lookup"><span data-stu-id="5f026-155">New bot or application added</span></span>

<span data-ttu-id="5f026-156">Teams은 기능 세트(사용자 지정 앱 및 봇 포함)를 확장하기 위해 Teams에 앱 또는 봇을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-156">Teams can include apps or bots in a Team to extend the feature set (including custom apps and bots).</span></span> <span data-ttu-id="5f026-157">사용자 계정이 없어도 Teams의 *지속성* 에 앱이나 봇을 사용할 수 있고 파일 및 기타 데이터에 액세스할 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-157">In some cases, an app or bot can be used for *persistence* in Teams without needing a user account, and can access files and other data.</span></span> <span data-ttu-id="5f026-158">이 쿼리는 Teams이 처음 사용하는 앱 또는 봇을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-158">This query hunts for apps or bots that are new to Teams.</span></span>

<span data-ttu-id="5f026-159">자세한 내용은 [Azure Sentinel 커뮤니티 Git 허브](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml)에서 쿼리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f026-159">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml).</span></span>

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="5f026-160">다수의 Teams 소유자인 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="5f026-160">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="5f026-161">자신의 권한을 높이려는 공격자는 많은 다양한 Teams의 소유자 권한을 자신에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-161">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams.</span></span> <span data-ttu-id="5f026-162">*일반적으로* 사용자는 특정 주제에 대해 몇 개의 Teams을 만들고 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-162">*Usually*, users create and own a few teams around specific topics.</span></span> <span data-ttu-id="5f026-163">이 KQL 쿼리는 의심스러운 동작을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-163">This KQL query looks for suspicious behavior.</span></span>

<span data-ttu-id="5f026-164">자세한 내용은 [Azure Sentinel 커뮤니티 Git 허브](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml)에서 쿼리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f026-164">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml).</span></span>

### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="5f026-165">단일 사용자에 의한 다수의 팀 삭제</span><span class="sxs-lookup"><span data-stu-id="5f026-165">Many Team deletions by a single user</span></span>

<span data-ttu-id="5f026-166">공격자는 여러 팀을 삭제하여 프로젝트와 데이터의 분열을 유발하고 위태롭게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-166">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="5f026-167">팀은 일반적으로 개별 소유자에 의해 삭제되기 때문에 많은 팀에 대한 중앙 집중식 삭제는 문제의 징후일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-167">Since teams are usually deleted by individual Owners, central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="5f026-168">이 KQL은 여러 Teams을 삭제하는 단일 사용자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-168">This KQL looks for single users who delete multiple teams.</span></span>

<span data-ttu-id="5f026-169">자세한 내용은 [Azure Sentinel 커뮤니티 Git 허브](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml)에서 쿼리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5f026-169">For more information, see the query in the [Azure Sentinel community git hub](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml).</span></span>

### <a name="expanding-your-threat-hunting-opportunities"></a><span data-ttu-id="5f026-170">위협 헌팅 기회 확장하기</span><span class="sxs-lookup"><span data-stu-id="5f026-170">Expanding your threat hunting opportunities</span></span>

<span data-ttu-id="5f026-171">Azure AD(Azure Active Directory) 또는 다른 Office 365 작업과 같은 리소스의 쿼리를 Teams 쿼리에 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-171">Combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads can be used with Teams queries.</span></span> <span data-ttu-id="5f026-172">예를 들어 Azure AD SigninLogs에서 의심스러운 패턴의 검색을 결합하고 해당 출력을 사용하여 Teams 소유자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-172">For example, combine the detection of suspicious patterns in Azure AD SigninLogs, and use that output while hunting for Team Owners.</span></span>

```Kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
OfficeActivity
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '2'
| where Members in (failed_signins)
```

<span data-ttu-id="5f026-173">또한 다음을 사용하여 Teams 기반 로고에 대한 필터를 추가하여 SigninLogs에서 Teams와 관련한 검색을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-173">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based logons by using:</span></span>

```Kusto
| where AppDisplayName has 'Teams'
```

<span data-ttu-id="5f026-174">*AppDisplayName에 Teams가 있는 위치* 를 더 자세히 설명하기 위해 아래에 표시된 KQL은 다른 IP 주소에서 실패했지만 Teams 로그인으로 *만* 범위가 지정된 한 IP 주소에서 성공적인 로그온을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-174">To help explain using *where AppDisplayName has Teams* further, the KQL you see below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped to *only* Teams sign-ins:</span></span>

```Kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName has "Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a><span data-ttu-id="5f026-175">중요 정보 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="5f026-175">Important information and updates</span></span>

<span data-ttu-id="5f026-176">**콘텐츠 공동 작업에 감사드립니다. Pete Bryan, Nicholas DiCola, Matthew Lowe.**</span><span class="sxs-lookup"><span data-stu-id="5f026-176">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="5f026-177">Pete Bryan과 그와 협력하는 사람들은 Teams을 위한 탐지 및 쿼리 헌팅을 계속 개발하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-177">Pete Bryan, and people he collaborates with, continue to develop detection and hunting queries for Teams.</span></span>

<span data-ttu-id="5f026-178">업데이트를 위해 이 [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) 저장소를 계속 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5f026-178">Stay in touch with this [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>

<span data-ttu-id="5f026-179">이 문서에서 사용되는 [파서](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) 및 [논리 앱](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)에 대한 업데이트를 지켜보세요.</span><span class="sxs-lookup"><span data-stu-id="5f026-179">Watch for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span>

<span data-ttu-id="5f026-180">또한 [Azure Sentinel 커뮤니티](https://github.com/Azure/Azure-Sentinel/wiki)에 참가하고 기여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f026-180">You should also join (and contribute to) the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="5f026-181">이 기사에 대한 피드백을 적극적으로 찾고 있으므로 아래의 피드백 옵션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5f026-181">We are actively looking for feedback on this article, so please use the feedback option below.</span></span> <span data-ttu-id="5f026-182">감사합니다. 헌팅을 즐기세요.</span><span class="sxs-lookup"><span data-stu-id="5f026-182">Thank you & Happy hunting.</span></span>

[<span data-ttu-id="5f026-183">Azure AD에서 응용 프로그램을 등록하기</span><span class="sxs-lookup"><span data-stu-id="5f026-183">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="5f026-184">감사 로그 검색 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="5f026-184">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[<span data-ttu-id="5f026-185">Azure Sentinel이란?</span><span class="sxs-lookup"><span data-stu-id="5f026-185">What is Azure Sentinel?</span></span>](/azure/sentinel/overview)
