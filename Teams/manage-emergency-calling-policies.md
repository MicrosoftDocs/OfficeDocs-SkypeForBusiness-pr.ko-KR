---
title: Microsoft 팀에서 긴급 통화 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 긴급 통화 정책을 사용 하 고 관리 하는 방법에 대해 알아봅니다.
f1keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: d6dc6f58085fedadf25f80272bc55dcc7723db19
ms.sourcegitcommit: f2c7626dbef4ed250b9a937a9b56d46fe2e2039e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2019
ms.locfileid: "39998796"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Microsoft 팀에서 긴급 통화 정책 관리

조직에서 통화 계획 또는 배포 된 전화 시스템 직접 라우팅을 사용 하는 경우 Microsoft 팀에서 비상 전화 정책을 사용 하 여 조직의 팀 사용자가 긴급 통화를 할 때 수행 되는 작업을 정의할 수 있습니다. 정책을 할당할 사용자가 응급 서비스를 호출할 때 알릴 사람과 알림을 받을 방법을 설정할 수 있습니다. 예를 들어 조직의 보안 데스크에 자동으로 알리기 위해 정책 설정을 구성 하 고 긴급 전화를 수신 하도록 설정할 수 있습니다.  

Microsoft 팀 관리 센터에서 또는 Windows PowerShell을 사용 하 여 **음성** > **응급 정책** 으로 이동해 서 긴급 통화 정책을 관리할 수 있습니다. 사용자 및 [네트워크 사이트](cloud-voice-network-settings.md)에 정책을 할당할 수 있습니다.

사용자의 경우 전역 (조직 차원의 기본값) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자 지정 정책을 만들고 지정 하지 않으면 사용자가 자동으로 전역 정책을 가져옵니다. 전역 정책의 설정은 편집할 수 있지만 이름을 바꾸거나 삭제할 수 없다는 점에 유의 하세요. 네트워크 사이트의 경우 사용자 지정 정책을 만들고 할당 합니다.

긴급 통화 정책을 네트워크 사이트 및 사용자에 게 할당 하 고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당 된 정책이 사용자에 게 할당 된 정책 보다 우선 합니다.

## <a name="create-a-custom-emergency-calling-policy"></a>사용자 지정 비상 통화 정책 만들기

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터 사용

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **응급 정책**으로 이동한 다음, **통화 정책** 탭을 클릭 합니다.
2. **추가**를 클릭 합니다.
3. 정책의 이름 및 설명을 입력 합니다.
4. 긴급 통화가 이루어질 때 조직의 사용자에 게 일반적으로 보안 데스크에 알리는 방법을 설정 합니다. 이렇게 하려면 **알림 모드**에서 다음 중 하나를 선택 합니다.
    - **알림만**: 지정 된 사용자 및 그룹에 게 팀 채팅 메시지가 전송 됩니다.
    - **Conferenced에는 있지만 음소거 되어**있습니다. 지정 하는 사용자 및 그룹에 팀 채팅 메시지가 전송 되며, 호출자와 psap 연산자 간에 대화에 참여 하지 않고이를 수신할 수 있습니다.
5.  **Conferenced in (음소거 됨** 알림 모드)을 선택한 경우에는 **알림 전화 접속 번호** 상자에서 사용자 또는 그룹의 PSTN 전화 번호를 입력 하 여 비상 전화를 걸거나 받을 수 있습니다. 예를 들어 조직의 보안 데스크 번호를 입력 하 고, 긴급 통화를 할 때 전화를 받을 수 있으며, 전화를 걸거나이에 참가할 수 있습니다.
6. 조직의 보안 데스크와 같은 하나 이상의 사용자 또는 그룹을 검색 하 고 선택 하 여 긴급 통화가 발생 한 경우 알립니다.  알림은 사용자, 메일 그룹, 보안 그룹의 전자 메일 주소로 보낼 수 있습니다. 최대 50 명의 사용자에 게 알림을 보낼 수 있습니다.
7. **저장**을 클릭 합니다.

### <a name="using-powershell"></a>PowerShell 사용

[새로운 CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)을 참조 하세요.

## <a name="edit-an-emergency-calling-policy"></a>긴급 통화 정책 편집

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터 사용

만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **응급 정책**으로 이동한 다음, **통화 정책** 탭을 클릭 합니다.
2. 정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.
3. 원하는 변경 작업을 수행한 다음 **저장**을 클릭 합니다.

### <a name="using-powershell"></a>PowerShell 사용

[Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)를 참조 하세요.

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>사용자에 게 사용자 지정 긴급 통화 정책 할당

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터 사용

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 다음 사용자를 클릭 합니다.
2. **정책을**클릭 한 다음 **할당 된 정책**옆에 있는 **편집**을 클릭 합니다.
3. **비상 전화 정책**에서 할당 하려는 정책을 선택한 다음 **저장**을 클릭 합니다.

사용자 지정 팀 정책을 한 번에 여러 사용자에 게 할당 하려면 [팀 사용자 설정을 일괄적으로 편집](edit-user-settings-in-bulk.md)을 참조 하세요.

또는 다음을 수행할 수도 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **응급 정책**으로 이동한 다음, **통화 정책** 탭을 클릭 합니다.
2. 정책 이름 왼쪽에 있는을 클릭 하 여 정책을 선택 합니다.
3. **사용자 관리**를 선택 합니다.
4. **사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 선택 합니다. 추가 하려는 각 사용자에 대해이 단계를 반복 합니다.
5. 사용자 추가를 마쳤으면 **저장**을 클릭 합니다.

### <a name="using-powershell"></a>PowerShell 사용

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a>사용자에 게 사용자 지정 긴급 통화 정책 할당

[허용-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)을 참조 하세요.

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a>사용자 지정 긴급 통화 정책을 그룹의 사용자에 게 할당

이미 확인 한 여러 사용자에 게 사용자 지정 비상 전화 정책을 할당 하려고 할 수 있습니다. 예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다. 그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다.

이 예제에서는 운영 긴급 호출 정책 이라고 하는 정책을 Contoso Operations group의 모든 사용자에 게 할당 합니다.  

> [!NOTE]
> 먼저 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)의 단계를 따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.

특정 그룹의 GroupObjectId를 가져옵니다.
```
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
지정 된 그룹의 구성원을 가져옵니다.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
특정 팀 정책에 그룹의 모든 사용자를 할당 합니다. 이 예제에서는 운영 긴급 통화 라우팅 정책입니다.
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>네트워크 사이트에 사용자 지정 비상 통화 정책 지정

[Set-Csten앤틸리스 site](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용 하 여 네트워크 사이트에 비상 전화 정책을 할당 합니다.

다음 예제에서는 Site1 사이트에 Contoso 비상 통화 정책 1 이라는 정책을 할당 하는 방법을 보여 줍니다.

    ```
    Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
    ```

## <a name="related-topics"></a>관련 항목

- [팀에서 긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)
- [팀 PowerShell 개요](teams-powershell-overview.md)
