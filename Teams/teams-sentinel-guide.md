---
title: Azure Sentinel 및 Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: serdars
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
ms.openlocfilehash: a59609404e51287be02dafc961561bd03e9efb9b
ms.sourcegitcommit: 8b172e9a0d0626c9a88998600d4b17c6c8cdadd2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761486"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel 및 Microsoft Teams

Teams는 Microsoft 365 클라우드의 커뮤니케이션 및 데이터 공유 모두에서 중심 역할을 수행합니다. Teams 서비스는 클라우드에서 많은 기반 기술을 사용하므로 *로그에서 헌팅*을 하는 경우 외에 *모임의 실시간 모니터링*에도 사용자와 자동화된 분석을 활용할 수 있습니다. Azure Sentinel은 관리자에게 이러한 솔루션을 제공합니다.

> [!NOTE]
> Azure Sentinel에 대한 복습이 필요한가요? [이 문서](https://docs.microsoft.com/azure/sentinel/overview)를 참고하시면 됩니다.

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Azure Sentinel 및 Microsoft Teams 활동 로그

이 문서에서는 Azure Sentinel에서 Teams의 활동 로그 수집에 초점을 두고 있습니다. 관리자가 보안 관리를 하나의 창에(모든 타사 장치, Microsoft Threat Protection 및 기타 Microsoft 365 워크로드) 두는 것 외에, 센티널 통합 문서와 runbook은 보안 모니터링을 체계적으로 수행할 수 있습니다. 이 프로세스에서 바람직한 첫 번째 단계는 분석에 필요한 로그를 수집하는 것입니다.

> [!NOTE]
> 두 개 이상의 Microsoft 365 구독이 동일한 Azure Sentinel 인스턴스에서 노출될 수 있습니다. 이는 기록 로그 파일 s에서 위협에 대한 [실시간 모니터링](https://docs.microsoft.com/azure/sentinel/livestream)과 헌팅을 할 수 있도록 해줍니다. 관리자는 단일 리소스 그룹 내에서, 여러 리소스 그룹에서 또는 다른 구독에서 [교차 리소스 쿼리](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query)를 사용하여 헌팅을 할 수 있습니다.

## <a name="step-1-collect-teams-logs"></a>1단계: Teams 로그 수집

이 섹션에는 세 가지 부분이 있습니다.

1. **Microsoft 365**(M365)에서 감사 로그를 사용합니다.
2. **Microsoft Azure**에서 앱을 등록하여 로그 수집에 대한 인증 및 권한을 허용합니다. 
3. **PowerShell**을 통해 M365 API를 통해 로그 수집을 허용하는 API 구독을 등록합니다.

### <a name="enable-audit-logs-in-m365"></a>M365에서 감사 로그 사용

Teams가 M365를 통해 활동을 기록하기 때문에 감사 로그가 기본적으로 수집되지 않습니다. [이러한 단계](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)를 통해 이 기능을 설정합니다. Teams 데이터는 *Audit.General*의 M365 감사에서 수집됩니다.

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a>M로그 수집을 위해 Microsoft Azure에서 앱 등록

> [!TIP]
> 시작하기 전에 **응용 프로그램 ID/클라이언트 ID**와 **테넌트 ID**를 나중에 사용할 수 있도록 기록해야 합니다. 아래에서 앱 등록 단계를 안내하는 단계를 수행하면서 이러한 정보를 반드시 캡처하세요. 두 ID가 모두 표시됩니다.
>- 앱을 만든 후 빠른 실행 사이드바에서 앱 등록 > 새 앱의 표시 이름 찾기 > 응용 프로그램(클라이언트) ID 복사를 클릭합니다.
>- 빠른 실행 사이드바에서 개요 > 디렉터리(테넌트) ID 복사를 클릭합니다.

API에서 로그 데이터를 수집하기 위해 Azure AD(Active Directory) 앱을 인증하고 권한을 부여합니다.

1. Azure Portal에서 *Azure AD* 블레이드로 이동합니다.
2. 빠른 실행 사이드바에서 *앱 등록*을 클릭합니다.
3. *새 등록*을 선택합니다.
4. Teams 로그 수집 앱 이름을 지정하고 *등록*을 클릭합니다.
5. 다음 경로를 클릭합니다. *API 사용 권한* > *사용 권한 추가* > *Office 365 관리 API* > *응용 프로그램 사용 권한*을 클릭합니다.
6. 활동 피드를 확장하고 *ActivityFeed.Read*를 확인합니다.
7. 여기서 *그랜드 관리자 동의*를 선택합니다. 정말로 선택하기를 원하는지 묻는 메시지가 나타나면 예를 클릭합니다.
8. 사이드바에서 *인증서와 암호* > *새 클라이언트 암호* 단추를 클릭합니다.
9. 새 클라이언트 암호 창에서 새 클라이언트 암호에 대한 설명을 입력하고, 만료는 '안 함'을 선택하고 *추가*를 클릭합니다.

> [!IMPORTANT]
> 새 클라이언트 암호를 새로 만든 앱의 이름 아래에 있는 암호 관리자 항목에 복사하는 것은 매우 **중요**합니다. Azure 블레이드를 닫은 후에는(*블레이드*는 창에 대한 Azure 용어) 이 암호를 확인하러 돌아갈 수 없습니다. 

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a>Teams 로그 수집을 위해 PowerShell에 API 등록

설치의 마지막 단계는 로그 데이터를 수집할 수 있도록 API 구독을 수집하고 등록하는 것입니다. M365 관리 활동 API에 대한 PowerShell REST 호출을 통해 이 작업을 수행할 수 있습니다.

아래 PowerShell cmdlet에서 **응용 프로그램(클라이언트) ID**, 새 **클라이언트 암호**, **M365에 다한 URL 도메인**, 그리고 **디렉터리(테넌트) ID** 값을 제공할 준비를 합니다.

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a>2단계: Teams 로그를 수집하기 위해 Sentinel 플레이북 배포

Azure Sentinel 플레이북(논리 앱이라고도 함)은 Azure을 통해 수집한 Teams 데이터를 수집하도록 합니다. 논리 앱은 Office 365를 쿼리하여 Azure Sentinel 작업 영역에 쓰는 감사 데이터를 찾습니다.

[이](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM 템플릿을 이용하여 Sentinel 플레이북을 배포합니다.

주의 사항은 다음과 같습니다.

1. ARM 템플릿을 거쳐 특정 값을 사용자 고유의 환경에 맞는 값으로 바꿔야 합니다.
2. Azure Sentinel에서 로그 수집 및 결과 확인 작업 사이에 시간을 두어야 합니다.

   지난 5분 내에 데이터가 없는 경우 오류 메시지가 표시됨을 알고 5~10분 정도 기다립니다. 감사 로그를 확인하고 Teams 정보가 Teams 로그 보다 많은 정보를 수집하는 Audit.General 이벤트에 있기 때문에 사용 중인 시스템에서 5 ~ 10분 이내에 결과과 표시됨을 염두에 둡니다. 텍스트 환경을 사용하는 경우에는 로깅을 생성하는 데 반드시 Teams를 사용합니다.

![논리 앱 클래스를 보여주는 그래픽](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> 그래픽의 작업에 대한 설명: 
  </summary>

  • 되풀이는 워크플로를 매시간 실행하도록 하는 논리 앱 트리거입니다.
  <p>
• 현재 시간 작업은 매우 기본적인 항목으로 단지 현재 시간을 가져옵니다.
  <p>
• 변수 초기화는 NextPage라는 변수를 만들고 이를 1로 설정합니다. 이는 나중에 O365 API에서 페이지 매김을 처리하는 데 사용됩니다.
  <p>
• 변수 2 초기화는 시작 시간이라는 빈 변수를 만듭니다.
  <p>
• 쿼리 실행 및 결과 나열은 논리 앱에서 입력한 마지막 O365 로그에 대한 작업 영역을 쿼리하는 Azure Monitor 동작입니다.
  <p>
• 조건 4는 쿼리 실행 및 결과 나열 쿼리가 반환한 데이터가 있는지를 확인하는 데 사용됩니다. 이 작업은 논리 앱이 최초로 사용되는 경우인지 확인하기 위해 수행됩니다. 데이터가 반환되지 않는 경우 StartTime 변수는 Now(24 시간)로 설정됩니다. 데이터가 반환되면 StartTime이 마지막 레코드(TimeGenerated)로 설정됩니다. 이는 쿼리가 O365 API를 대상으로 하는 폴링에서 마지막 항목에서 현재까지의 데이터를 가져올 수 있도록 하기 위해 수행됩니다(이번이 최초 실행인 경우 마지막 24시간 이내).
  <p>
• 변수 3 초기화는 AvailableUri라는 변수를 만듭니다. 시작 시간과 종료 시간으로 StartTime과 CurrentTime를 각각 사용하여 빌드한 URL이 있는 문자열입니다.
  <p>
• Until 조건은 논리 앱에서 계속해서 API를 폴링하여 데이터가 더 있는지 확인할 수 있는 루프입니다(페이지 매김). NextPage 변수가 1인 한 루프가 계속 진행됩니다. 나중에 더 이상 검색할 페이지가 없으면 이 변수가 업데이트됩니다.
  <p>
• Until 루프 내에 첫 번째 HTTP 단계가 AvailableURI에 연결됩니다. 이 URI는 사용 가능한 콘텐츠 목록과 각 콘텐츠 URI를 반환합니다. 이 URL에서 이 작업이 수행되는 방법에 대한 자세한 내용은 https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content를 참조하세요.
  <p>
• 다음으로 검사를 실행하여 데이터가 반환되는지 확인합니다. 이 조건은 본문의 길이가 0인지 확인합니다. 0인 경우 로그 분석에 쓸 데이터가 없습니다. 값이 0보다 크면 처리할 데이터가 있습니다.
  <p>
• 데이터가 검색되면 다음에 처리해야 합니다. JSON 구문 분석은 반환된 데이터의 스키마를 정의합니다. 이는 이후의 단계에 논리 앱에서 구문 분석된 데이터를 동적 콘텐츠로 사용할 수 있도록 합니다.
  <p>
• 반환되는 사용 가능한 데이터 목록이 배열이므로 For Each 동작은 사용 가능한 콘텐츠 목록에서 루프를 수행하는 데 사용됩니다.
  <p>
• 다음은 콘텐츠 가져오기입니다.  검색할 데이터의 URL인 contentUri(구문 분석 JSON에서 만든 동적 속성)를 가져오는 데 HTTP가 다시 사용됩니다.
  <p>
• 구문 분석 JSON은 반환된 데이터를 구문 분석하는 데도 사용됩니다. 다음 URL에서 일부 샘플 콘텐츠를 찾을 수 있습니다.https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content
  <p>
• 반환되는 데이터 또한 배열입니다. 여기에서도 For Each 루프를 사용할 수 있습니다. 이 루프에서는 워크플로가 현재 데이터 항목을 받고 데이터 보내기 동작을 사용하여 데이터를 Log Analytics에 씁니다.
  <p>
• 사용 가능한 콘텐츠 페이지가 여러 개 있을 수 있으므로 조건은 NextPageUri가 NULL이 아닌지 확인합니다. NULL이거나 비어있는 경우 NextPage가 0으로 설정되면 Until 루프를 종료합니다. URL이 포함되어 있는 경우 AvaibleUri 변수는 해당 URL로 업데이트됩니다. 이러한 방식으로 다음에 Until 루프를 실행할 때 시작 URL이 아닌 다음 사용 가능한 URL이 사용됩니다.

  </details>

> [!TIP]
> 이러한 로그를 수집하기 위해 대신 *Azure 함수*를 사용하도록 선택할 수 있고, 선택하는 경우의 배포 방법에 대한 정보는 기본 설정에 따라 [여기](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data) 혹은 [여기](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp)에 있습니다.

(사용자가 위에서 선택한 옵션에 상관없이) 커넥터를 실행하는 경우, Azure Sentinel 작업 영역에 O365API_CL이라는 사용자 지정 표가 표시됩니다. 여기에 Teams 로그가 보관됩니다.

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a>3 단계: Sentinel을 사용하여 Microsoft Teams 모니터링

ID는 Microsoft Teams와 관련된 경우, 모니터링할 중요한 공격 벡터입니다. Azure AD(Active Directory)는 Teams를 포함하는 Microsoft 365의 디렉터리의 기반이기에, 인증과 관련된 Azure AD 로그에서 위협을 수집하고 헌팅함은 ID에 대한 의심이 가는 동작을 캡처하는 데 유용합니다. 기본 제공 커넥터를 사용하여 Azure Sentinel로 Azure AD 데이터를 가져오고 이러한 [검색](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) 및 [헌팅](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) 쿼리를 사용하여 문제를 찾을 수 있습니다.

Microsoft Teams와 관련된 공격, 데이터에 대한 위협과 관련하여, 예를 들어 Azure Sentinel 또한 그들을 모니터링하고 헌팅하는 수단이 있습니다.

### <a name="create-a-parser-for-your-data"></a>데이터에 대한 파서 만들기

수집된 대규모 데이터 집합이 제대로 작성되려면 먼저 수행해야 하는 작업은 구문 분석을 통해 의미를 부여하는 것입니다. 이 작업은 데이터를 더 쉽게 사용할 수 있도록 하는 KQL(Kusto 쿼리 언어) 함수를 사용하여 수행합니다.

> [!NOTE]
> KQL 함수는 '함수'라는 데이터 형식으로 저장된 KQL 쿼리입니다. KQL 함수는 Sentinel의 쿼리 상자에 입력하여 쿼리를 신속하게 다시 실행할 수 있는 별칭이 있습니다. KQL 함수 및 파서 함수를 빌드하는 방법에 대한 자세한 내용은 [이 기술 커뮤니티 문서](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381)를 읽어보세요.
 
 아래 파서는 *Teams*와 관련된 Office 365 관리 API 필드의 하위 집합을 선택할 목적의 사용자 지정이 가능한 예시입니다. 또한 제안된 파서 [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt)가 있지만 아래의 파서는 다양 한 요구 사항 및 기본 설정에 맞게 수정할 수 있습니다.

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 TeamsData의 별칭을 사용하여 이 파서를 KQL 함수로 저장합니다. 따를 쿼리에 사용됩니다. KQL 함수를 구문으로 구성하고 사용하는 방법에 대한 자세한 내용은 이 [기술 커뮤니티 문서](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381)를 참조하세요.

## <a name="helfpul-hunting-kql-queries"></a>유용한 헌팅 KQL 쿼리

이 쿼리를 사용하여 Teams 데이터와 Teams 환경에 익숙해지도록 합니다. 환경의 모양과 작동 방식을 아는 것은 의심스러운 활동을 인식하는 데 바람직한 첫 단계입니다. 여기서 위협 헌팅으로 분기할 수 있습니다.

#### <a name="federated-external-users-query"></a>페더레이션된 외부 사용자 쿼리

페더레이션된 외부 사용자가 있는 Teams 사이트 목록을 가져옵니다. 이들 사용자는 조직에서 소유하지 *않는* 도메인 이름/UPN 접미사를 갖게됩니다. 이 예제 쿼리에서는 조직이 contoso.com를 소유합니다.

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> Teams의 외부 및 게스트 액세스 유형에 대한 자세한 내용은 [이 문서](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations) 또는 [Teams 보안 가이드](https://docs.microsoft.com/microsoftteams/teams-security-guide)의 *참가자 유형* 섹션을 참조하세요.

#### <a name="who-recently-joined--whose-role-changed"></a>최근 참가한 사용자/역할이 변경된 사용자

특정 사용자를 쿼리하여 최근 7일 또는 일주일 이내에 Teams 채널에 추가되었는지 확인합니다.

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

최근 7일 이내에 Teams에 대한 사용자의 역할이 변경되었습니다.

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a>알 수 없는 조직이나 새 조직의 외부 사용자

Teams에서 사용자 환경이나 채널에 외부 사용자를 추가할 수 있습니다. 조직은 종종 제한된 수의 주요 파트너 관계를 가지고 있으며, 이러한 파트너 들 사이에서 사용자를 추가합니다. 이 KQL는 이전에 보이거나 추가되지 않은 조직에서 온 팀에 추가된 외부 사용자를 살펴봅니다.

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a>추가된 후 제거된 외부 사용자

기존의 어느 정도의 액세스 권한이 있는 공격자는 Teams에 새 외부 계정을 추가하여 데이터에 액세스하고 데이터를 빼낼 수 있습니다. 또한 액세스한 사실을 숨기기 위해 해당 사용자를 신속히 제거할 수도 있습니다. 이 쿼리는 Teams에 추가되고 신속히 제거되는 외부 계정을 헌팅하여 의심스러운 동작을 식별하는 데 도움을 줍니다.

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a>새 봇 또는 응용 프로그램이 추가됨

Teams는 팀에 앱 또는 봇을 포함하여 기능 집합을 확장할 수 있습니다. 여기에는 사용자 지정 앱과 봇이 포함됩니다. 경우에 따라 앱 또는 봇을 사용하여 사용자 계정이 없어도 Teams에 지속성을 설정하고 파일 및 기타 데이터에 액세스할 수 있습니다. 이 쿼리는 Teams에 새로운 앱이나 봇을 헌팅합니다.

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>다수의 Teams의 소유자인 사용자 계정

자신의 권한을 승격하려는 공격자는 일반적으로 사용자가 특정 항목에 대한 소수의 Teams를 만들고 소유하는 경우, 다수의 다양한 Teams의 소유자 권한을 자신에게 할당할 수 있습니다. 이 KQL 쿼리는 의심스러운 동작을 검색합니다.

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a>단일 사용자에 의한 다수의 팀 삭제

공격자는 여러 팀을 삭제하여 프로젝트와 데이터의 분열을 유발하고 위태롭게 할 수 있습니다. 팀은 일반적으로 개별 소유자에 의해 삭제되기 때문에 많은 팀에 대한 중앙 집중식 삭제는 문제의 징후일 수 있습니다. 이 KQL은 여러 팀을 삭제하는 단일 사용자를 검색합니다.

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a>스레드 헌팅 기회 확장하기

Azure AD(Azure Active Directory) 또는 기타 Office 365 워크로드와 같은 리소스의 쿼리를 Teams 쿼리와 결합하여 헌팅을 확장할 수 있습니다. 한가지 예로는 Teams 소유자를 헌팅하는 동안 Azure AD SigninLogs에서 의심스러운 패턴의 검색과 이러한 정보의 사용을 결합하는 것입니다.

```kusto
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
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

또한 다음을 사용하여 Teams 기반 로그인에 대해서만 필터를 추가하여 Teams와 관련된 SigninLogs를 검색할 수 있습니다.

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

`where AppDisplayName starts with "Microsoft Teams"`의 사용을 더욱 상세히 설명하고자 다음의 KQL는 한 IP 주소에서 다양한 IP 주소에서 오류가 발생했지만 Teams 로그인에만 범위가 지정되는 성공적인 로그온을 보여줍니다.

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
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

**콘텐츠 공동 작업에 감사드립니다. Pete Bryan, Nicholas DiCola, Matthew Lowe.** Pete Bryan씨와 공동 작업을 하는 사용자들은 검색 및 헌팅 쿼리를 계속해서 개발할 것이므로 이 [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) 리포지토리를 계속 사용하여 업데이트를 확인하세요.  이 문서에서 사용되는 [파서](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) 및 [논리 앱](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data)에 대한 업데이트를 모니터링하세요. 또한 [Azure Sentinel 커뮤니티](https://github.com/Azure/Azure-Sentinel/wiki)에 참가하고 기여할 수도 있습니다. 감사합니다! 즐거운 헌팅을 하세요.

[Azure AD에서 응용 프로그램을 등록하기](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[감사 로그 검색 켜기 또는 끄기](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[Azure Sentinel이란 무엇인가요?](https://docs.microsoft.com/azure/sentinel/overview)