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
ms.openlocfilehash: 55307637e18f81775229bb46db51a6f5738cce7c
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587047"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel 및 Microsoft Teams

> [!IMPORTANT]
> 이제 Azure Sentinel에 통합 커넥터가 있습니다. 자세한 내용은 [Azure Sentinel 365 로그 연결](/azure/sentinel/connect-office-365)을 참조하세요. 이 경로는 이러한 로그를 수집하는 데 권장되는 경로로 아래 설명된 컬렉션 방법을 대체합니다.

Teams은 Microsoft 365 클라우드에서 통신 및 데이터 공유의 중심 역할을 수행합니다. Teams은 클라우드에서 매우 많은 기술을 활용하기 때문에 인적, 자동화된 분석을 통해 이점을 얻을 수 있습니다. 이는 *로그 검색* 및 *모임 실시간 모니터링* 에 모두 적용됩니다. Azure Sentinel은 관리자에게 이러한 솔루션을 제공합니다.

> [!NOTE]
> Azure Sentinel에 대한 복습이 필요한가요? [이 문서](/azure/sentinel/overview)를 참고하시면 됩니다.

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Azure Sentinel 및 Microsoft Teams 활동 로그

이 문서에서는 Azure Sentinel에서 Teams의 활동 로그 수집에 초점을 두고 있습니다.

Sentinel을 통해 관리자는 한 위치에서 보안 관리를 수행할 수 있습니다. 여기에는 다음 항목에 대한 관리가 포함됩니다.

- 타사 장치
- Microsoft Threat Protection
- Microsoft 365 Workloads

Sentinel 통합 문서와 실행 문서는 보안 모니터링을 *체계적* 으로 만들 수 있습니다. 이 프로세스의 좋은 첫 번째 단계는 분석에 필요한 로그를 수집하는 것입니다.

> [!NOTE]
> Azure Sentinel의 동일한 인스턴스에서 둘 이상의 Microsoft 365 구독을 노출시킬 수 있습니다. 이는 기록 로그 파일 s에서 위협에 대한 [실시간 모니터링](/azure/sentinel/livestream)과 헌팅을 할 수 있도록 해줍니다. 관리자는 단일 리소스 그룹 내에서, 여러 리소스 그룹에서 또는 다른 구독에서 [교차 리소스 쿼리](/azure/azure-monitor/log-query/cross-workspace-query)를 사용하여 헌팅을 할 수 있습니다.

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a>1단계: Teams 로그 수집: Microsoft 365에서 감사 로그 사용

Teams은 Microsoft 365를 통해 작업을 기록하므로 감사 로그는 기본적으로 수집되지 않습니다. [이러한 단계](/microsoft-365/compliance/turn-audit-log-search-on-or-off)를 통해 이 기능을 설정합니다. Teams 데이터는 *Audit.General* 의 Microsoft 365 감사에서 수집됩니다.

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a>2단계: Azure Sentinel 365 로그 연결

Azure Sentinel은 다른 Office 365 데이터와 함께 Teams 데이터를 Azure Sentinel로 수집할 수 있도록 Office 365 로그를 위한 내장 커넥터를 제공합니다.
 
Azure Sentinel에서 Office 365 데이터 커넥터를 활성화합니다. 자세한 내용은 [Azure Sentinel 설명서](/azure/sentinel/connect-office-365)를 참조하세요.

## <a name="helpful-hunting-kql-queries"></a>유용한 헌팅 KQL 쿼리

이 쿼리를 사용하여 Teams 데이터와 Teams 환경에 익숙해지도록 합니다. 환경의 모양과 작동 방식을 아는 것은 의심스러운 활동을 인식하는 데 바람직한 첫 단계입니다. 여기서 위협 헌팅으로 분기할 수 있습니다.

### <a name="federated-external-users-query"></a>페더레이션된 외부 사용자 쿼리

페더레이션된 외부 사용자가 있는 Teams 사이트 목록을 가져옵니다. 이러한 사용자는 조직에서 소유하지 않은 도메인 이름 및/또는 UPN 접미사를 가집니다.

이 예제 쿼리에서는 조직이 contoso.com를 소유합니다.

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
> Teams의 외부 및 게스트 액세스 유형에 대한 자세한 내용은 [다른 조직의 사용자](communicate-with-users-from-other-organizations.md)와 통신 또는 Teams 보안 가이드의 [참가자 유형](teams-security-guide.md#participant-types) 섹션을 참조하세요.

### <a name="who-recently-joined--whose-role-changed"></a>최근에 가입한 사람 / 역할이 변경된 사람

특정 사용자를 쿼리하여 최근 7일 또는 일주일 이내에 Teams 채널에 추가되었는지 확인합니다.

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

지난 7일 동안 Teams에 대한 사용자 역할이 변경되었는지 쿼리합니다.

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a>알 수 없는 조직이나 새 조직의 외부 사용자

Teams에서 사용자 환경이나 채널에 외부 사용자를 추가할 수 있습니다. 조직은 종종 제한된 수의 주요 파트너 관계를 가지고 있으며, 이러한 파트너 들 사이에서 사용자를 추가합니다. 이 KQL는 이전에 보이거나 추가되지 않은 조직에서 온 팀에 추가된 외부 사용자를 살펴봅니다.

자세한 내용은 [Azure Sentinel 커뮤니티 Git 허브](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml)에서 쿼리를 참조하세요.

### <a name="external-users-who-were-added-and-then-removed"></a>추가된 후 제거된 외부 사용자

기존의 어느 정도의 액세스 권한이 있는 공격자는 Teams에 새 외부 계정을 추가하여 데이터에 액세스하고 데이터를 빼낼 수 있습니다. 또한 액세스한 사실을 숨기기 위해 해당 사용자를 신속히 제거할 수도 있습니다. 이 쿼리는 Teams에 추가되고 신속히 제거되는 외부 계정을 헌팅하여 의심스러운 동작을 식별하는 데 도움을 줍니다.

자세한 내용은 [Azure Sentinel 커뮤니티 Git 허브](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml)에서 쿼리를 참조하세요.

### <a name="new-bot-or-application-added"></a>새 봇 또는 애플리케이션이 추가됨

Teams은 기능 세트(사용자 지정 앱 및 봇 포함)를 확장하기 위해 Teams에 앱 또는 봇을 포함할 수 있습니다. 사용자 계정이 없어도 Teams의 *지속성* 에 앱이나 봇을 사용할 수 있고 파일 및 기타 데이터에 액세스할 수 있는 경우도 있습니다. 이 쿼리는 Teams이 처음 사용하는 앱 또는 봇을 검색합니다.

자세한 내용은 [Azure Sentinel 커뮤니티 Git 허브](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml)에서 쿼리를 참조하세요.

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>다수의 Teams 소유자인 사용자 계정

자신의 권한을 높이려는 공격자는 많은 다양한 Teams의 소유자 권한을 자신에게 할당할 수 있습니다. *일반적으로* 사용자는 특정 주제에 대해 몇 개의 Teams을 만들고 소유합니다. 이 KQL 쿼리는 의심스러운 동작을 검색합니다.

자세한 내용은 [Azure Sentinel 커뮤니티 Git 허브](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml)에서 쿼리를 참조하세요.

### <a name="many-team-deletions-by-a-single-user"></a>단일 사용자에 의한 다수의 팀 삭제

공격자는 여러 팀을 삭제하여 프로젝트와 데이터의 분열을 유발하고 위태롭게 할 수 있습니다. 팀은 일반적으로 개별 소유자에 의해 삭제되기 때문에 많은 팀에 대한 중앙 집중식 삭제는 문제의 징후일 수 있습니다. 이 KQL은 여러 Teams을 삭제하는 단일 사용자를 검색합니다.

자세한 내용은 [Azure Sentinel 커뮤니티 Git 허브](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml)에서 쿼리를 참조하세요.

### <a name="expanding-your-threat-hunting-opportunities"></a>위협 헌팅 기회 확장하기

Azure AD(Azure Active Directory) 또는 다른 Office 365 작업과 같은 리소스의 쿼리를 Teams 쿼리에 결합할 수 있습니다. 예를 들어 Azure AD SigninLogs에서 의심스러운 패턴의 검색을 결합하고 해당 출력을 사용하여 Teams 소유자를 검색합니다.

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

또한 다음을 사용하여 Teams 기반 로고에 대한 필터를 추가하여 SigninLogs에서 Teams와 관련한 검색을 할 수 있습니다.

```Kusto
| where AppDisplayName has 'Teams'
```

*AppDisplayName에 Teams가 있는 위치* 를 더 자세히 설명하기 위해 아래에 표시된 KQL은 다른 IP 주소에서 실패했지만 Teams 로그인으로 *만* 범위가 지정된 한 IP 주소에서 성공적인 로그온을 보여줍니다.

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

## <a name="important-information-and-updates"></a>중요 정보 및 업데이트

**콘텐츠 공동 작업에 감사드립니다. Pete Bryan, Nicholas DiCola, Matthew Lowe.** Pete Bryan과 그와 협력하는 사람들은 Teams을 위한 탐지 및 쿼리 헌팅을 계속 개발하고 있습니다.

업데이트를 위해 이 [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) 저장소를 계속 확인하세요.

이 문서에서 사용되는 [파서](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) 및 [논리 앱](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)에 대한 업데이트를 지켜보세요.

또한 [Azure Sentinel 커뮤니티](https://github.com/Azure/Azure-Sentinel/wiki)에 참가하고 기여해야 합니다. 이 기사에 대한 피드백을 적극적으로 찾고 있으므로 아래의 피드백 옵션을 사용하세요. 감사합니다. 헌팅을 즐기세요.

[Azure AD에서 응용 프로그램을 등록하기](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[감사 로그 검색 켜기 또는 끄기](/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[Azure Sentinel이란?](/azure/sentinel/overview)
