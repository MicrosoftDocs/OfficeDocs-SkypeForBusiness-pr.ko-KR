---
title: 긴급 전화 라우팅 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 긴급 전화 번호를 설정 하 고 긴급 전화의 라우팅 방법을 지정 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b573543483d41219d2795043f47042789bc855ba
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539525"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a>Microsoft 팀에서 긴급 통화 라우팅 정책 관리

조직에 [직접 전화 시스템 라우팅을](direct-routing-landing-page.md) 배포한 경우 Microsoft 팀에서 비상 전화 라우팅 정책을 사용 하 여 비상 전화 번호를 설정 하 고 긴급 통화의 라우팅 방식을 지정할 수 있습니다. 긴급 통화 라우팅 정책은 정책에 할당 된 사용자에 게 향상 된 응급 서비스를 사용할 수 있는지 여부, 비상 서비스를 호출 하는 데 사용 되는 번호 (예: 미국 내 911), 그리고 비상 서비스에 대 한 통화가 라우팅되는 방법을 결정 합니다.

**Voice**  >  Microsoft 팀 관리 센터에서 또는 Windows PowerShell을 사용 하 여 음성**응급 정책** 으로 이동해 서 긴급 통화 라우팅 정책을 관리할 수 있습니다. 사용자 및 [네트워크 사이트](cloud-voice-network-settings.md)에 정책을 할당할 수 있습니다.

사용자의 경우 전역 (조직 차원의 기본값) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만들고 지정 하지 않으면 사용자가 자동으로 전역 정책을 가져옵니다. 전역 정책의 설정은 편집할 수 있지만 이름을 바꾸거나 삭제할 수 없다는 점에 유의 하세요. 네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당 합니다.

네트워크 사이트에 대 한 긴급 통화 라우팅 정책을 할당 하 고 사용자에 게 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당 된 정책이 사용자에 게 할당 된 정책 보다 우선 합니다.

## <a name="create-a-custom-emergency-call-routing-policy"></a>사용자 지정 긴급 통화 라우팅 정책 만들기

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **응급 정책**으로 이동한 다음 **전화 라우팅 정책** 탭을 클릭 합니다.
2. **추가**를 클릭 합니다.
3. 정책의 이름과 설명을 입력합니다.
4. 동적 비상 전화를 사용 하려면 **동적인 비상 전화**를 켜십시오. 동적 긴급 통화를 사용 하도록 설정 하면 팀에서 서비스의 정책 및 위치 정보를 검색 하 고 긴급 통화의 일부로 해당 정보를 포함 합니다.
5. 하나 이상의 긴급 전화 번호를 정의 합니다. 이렇게 하려면 **비상 번호**에서 **추가**를 클릭 하 고 다음을 수행 합니다.
    1. **비상 다이얼 문자열**: 비상 다이얼 문자열을 입력 합니다. 이 다이얼 문자열은 통화가 비상 통화로 표시 됨을 나타냅니다.
        > [!NOTE]
        > 직접 라우팅의 경우 긴급 전화 다이얼 문자열 앞에 "+"를 사용 하 여 긴급 전화를 보내는 팀 클라이언트에서 멀리 전환 하 고 있습니다. 전환이 완료 될 때까지 긴급 전화 접속 문자열과 일치 하는 음성 경로 패턴은 911 및 + 911와 같이 앞에 "+"가 없는 문자열에 대해 일치가 수행 되도록 해야 합니다. 예를 들어 ^ \\ +? 911 또는. *를 선택 합니다.
    2. **응급 전화 접속 마스크**: 각 비상 전화 번호에 대해 0 개 이상의 비상 다이얼 마스크를 지정할 수 있습니다. 다이얼 마스크는 비상 다이얼 문자열의 값으로 번역 하려는 번호입니다. 이렇게 하면 대체 비상 번호를 사용 하 여 전화를 걸고 통화에도 비상 서비스를 받을 수 있습니다. <br>예를 들어 112을 긴급 전화 접속 마스크 (대부분 유럽의 비상 서비스 번호)로 추가 하 고 비상 다이얼 문자열로 911을 추가할 수 있습니다. 방문 하는 유럽 지역의 팀 사용자는 911이 미국에서 긴급 번호 라는 것을 알지 못할 수 있으며, 112가 전화를 거는 경우 911에 통화가 이루어집니다. 여러 다이얼 마스크를 정의 하려면 각 값을 세미콜론으로 구분 합니다. 예를 들어 112; 212.
    3. **Pstn 사용 레코드**: Pstn (공개 교환 전화 네트워크) 사용 레코드를 선택 합니다. PSTN 사용 레코드는 사용 하도록 승인 된 사용자 로부터 비상 통화를 라우팅하는 데 사용 되는 경로를 결정 하는 데 사용 됩니다. 이 사용과 연결 된 경로는 비상 전화 전용 SIP (세션 초기화 프로토콜) 트렁크 또는 가까운 공공 안전 응답 시점 (PSAP)으로 긴급 통화를 라우팅하는 비상 위치 Id 번호 (ELIN) 게이트웨이를 가리켜야 합니다.

    > [!NOTE]
    > 다이얼 문자열과 다이얼 마스크는 정책 내에서 고유 해야 합니다. 즉, 정책의 경우 여러 응급 번호를 정의할 수 있으며, 다이얼 문자열에 여러 개의 다이얼 마스크를 설정할 수 있지만 각 다이얼 문자열 및 다이얼 마스크는 한 번만 사용 해야 합니다.

6. **저장**을 클릭합니다.

### <a name="using-powershell"></a>PowerShell 사용

[새로운 CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy)을 참조 하세요.

## <a name="edit-an-emergency-call-routing-policy"></a>긴급 통화 라우팅 정책 편집

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **응급 정책**으로 이동한 다음 **전화 라우팅 정책** 탭을 클릭 합니다.
2. 정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.
3. 원하는 변경 작업을 수행한 다음 **저장**을 클릭 합니다.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy)를 참조 하세요.

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a>사용자에 게 사용자 지정 긴급 전화 라우팅 정책 할당

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

한 사용자에 게 정책을 할당 하려면 다음을 수행 합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.
2. **정책을**클릭 한 다음 **할당 된 정책**옆에 있는 **편집**을 클릭 합니다.
3. **비상 전화 라우팅 정책**에서 할당할 정책을 선택한 다음 **저장**을 클릭 합니다.

한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.
2. **&#x2713;**(확인 표시) 열에서 사용자를 선택합니다. 모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.
3. **설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.  

또는 다음을 수행할 수도 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성**  >  **응급 정책**으로 이동한 다음 **전화 라우팅 정책** 탭을 클릭 합니다.
2. 정책 이름의 왼쪽을 클릭하여 정책을 선택합니다.
3. **사용자 관리**를 선택합니다.
4. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가**를 선택하세요. 추가할 각 사용자에 대해 이 단계를 반복합니다.
5. 사용자 추가를 마쳤으면 **저장**을 클릭 합니다.

### <a name="using-powershell"></a>PowerShell 사용

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a>사용자에 게 사용자 지정 긴급 통화 라우팅 정책 할당

[허용-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy)을 참조 하세요.

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a>그룹의 사용자에 게 사용자 지정 긴급 전화 라우팅 정책 할당

이미 확인 한 여러 사용자에 게 사용자 지정 긴급 전화 라우팅 정책을 할당 하려고 할 수 있습니다. 예를 들어 보안 또는 메일 그룹의 모든 사용자에 게 정책을 할당할 수 있습니다. 그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다.

이 예제에서는 Contoso HR 그룹의 모든 사용자에 게 HR 비상 통화 라우팅 정책 이라는 정책을 할당 합니다.  

> [!NOTE]
> 먼저 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)의 단계를 따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.

특정 그룹의 GroupObjectId를 가져옵니다.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
지정 된 그룹의 구성원을 가져옵니다.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
특정 팀 정책에 그룹의 모든 사용자를 할당 합니다. 이 예제에서는 HR 긴급 통화 라우팅 정책입니다.
```PowerShell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallRoutingPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.UserPrincipalName}
``` 
그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a>네트워크 사이트에 사용자 지정 긴급 전화 라우팅 정책 할당

[Set-Csten앤틸리스 site](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용 하 여 네트워크 사이트에 긴급 통화 라우팅 정책을 할당 합니다.

이 예제에서는 비상 통화 라우팅 정책 1 이라는 정책을 Site1 사이트에 할당 하는 방법을 보여 줍니다.

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a>관련 항목

- [팀에서 긴급 통화 정책 관리](manage-emergency-calling-policies.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)
- [팀에서 사용자에 게 정책 할당](assign-policies.md)
