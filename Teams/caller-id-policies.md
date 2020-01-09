---
title: Microsoft 팀의 발신자 ID 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1keywords: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 발신자 ID 정책을 사용 하 고 관리 하 여 조직에서 팀 사용자의 발신자 ID를 변경 하거나 차단 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: aed6e3cbe2053ddc16b049608247f56705626249
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992888"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Microsoft 팀의 발신자 ID 정책 관리

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

관리자는 Microsoft 팀의 발신자 ID 정책을 사용 하 여 발신자 ID (전화 라인 ID 라고도 함)를 변경 하거나 차단할 수 있습니다. 기본적으로 팀 사용자는 PSTN 휴대폰으로 전화를 걸거나 PSTN 발신자의 전화 번호를 볼 수 있으며,이 경우 팀에 게 전화를 걸 때 볼 수 있습니다. 발신자 ID 정책을 사용 하 여 조직의 팀 사용자에 대 한 대체 전화 번호를 표시 하거나 수신 번호를 표시 되지 않도록 차단할 수 있습니다.

예를 들어 사용자가 전화를 거는 경우 발신자 ID를 변경 하 여 사용자의 전화 번호 대신 조직의 기본 전화 번호를 표시할 수 있습니다.

Microsoft 팀 관리 센터에서 **음성** > **발신자 id 정책** 으로 이동해 서 발신자 id 정책을 관리할 수 있습니다. 전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 정책을 만들어 사용자에 게 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당 하지 않으면 조직의 사용자가 자동으로 전역 정책을 받습니다.

전역 정책을 편집 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다. 사용자가 사용자 지정 정책을 할당 한 경우 해당 정책이 사용자에 게 적용 됩니다. 사용자가 사용자 지정 정책을 할당 하지 않으면 전역 정책이 사용자에 게 적용 됩니다.

## <a name="create-a-custom-caller-id-policy"></a>사용자 지정 발신자 ID 정책 만들기

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **발신자 ID 정책**으로 이동 합니다.
2. **추가**를 클릭 합니다.
![관리 센터의 새 발신자 ID 정책 페이지 스크린샷](media/caller-id-policies-add-policy.png)
3. 정책의 이름 및 설명을 입력 합니다.
4. 여기에서 원하는 설정을 선택 합니다.

    - **들어오는 발신자 Id 차단**:이 설정을 사용 하면 들어오는 전화의 발신자 id가 표시 되지 않도록 차단할 수 있습니다.
    - **사용자는 발신자 ID 정책을 무시할 수 있습니다**.이 설정을 사용 하면 사용자가 번호를 피호출자에 표시 하는 것과 관련 하 여 정책의 설정을 재정의할 수 있습니다. 즉, 사용자가 자신의 발신자 ID를 표시할지 여부를 선택할 수 있습니다.
    - **발신자 Id 바꾸기**: 다음 중 하나를 선택 하 여 사용자에 게 표시할 발신자 id를 설정 합니다.

        - **사용자의 번호**: 사용자의 번호를 표시 합니다. 
        - **서비스 번호**: 발신자 ID로 표시할 서비스 전화 번호를 설정할 수 있습니다.
        - **익명**: 발신자 ID를 익명으로 표시 합니다.

    - **발신자 id를 바꾸는 데 사용할 서비스 번호**: 사용자의 발신자 id를 바꿀 서비스 번호를 선택 합니다. 이 옵션은 **발신자 ID**에서 **서비스 번호** 를 선택한 경우에만 사용할 수 있습니다.

5. **저장**을 클릭 합니다.

## <a name="edit-a-caller-id-policy"></a>발신자 ID 정책 편집

만든 전역 정책 또는 사용자 지정 정책을 편집할 수 있습니다. 

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **발신자 ID 정책**으로 이동 합니다.
2. 정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.
3. 원하는 설정을 변경한 다음 **저장**을 클릭 합니다.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>사용자에 게 사용자 지정 발신자 ID 정책 할당

Microsoft 팀 관리 센터를 사용 하 여 한 명 이상의 사용자 또는 비즈니스용 Skype PowerShell 모듈에 사용자 지정 정책을 할당 하 여 보안 그룹 또는 메일 그룹과 같은 사용자 그룹에 사용자 지정 정책을 할당할 수 있습니다.

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a>사용자에 게 사용자 지정 발신자 줄 ID 정책 할당

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 다음 사용자를 클릭 합니다.
2. **정책을**클릭 한 다음 **할당 된 정책**옆에 있는 **편집**을 클릭 합니다.
3. **발신자 ID 정책**에서 할당할 정책을 선택한 다음 **저장**을 선택 합니다.

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a>사용자 지정 전화 회선 ID 정책을 한 번에 여러 사용자에 게 할당

사용자 지정 전화 회선 Id 정책을 한 번에 여러 사용자에 게 할당 하려면 [팀 사용자 설정을 일괄적으로 편집](edit-user-settings-in-bulk.md)을 참조 하세요.

또는 다음을 수행할 수도 있습니다.

1. **Microsoft 팀 관리 센터** > **음성** > **발신자 ID 정책**으로 이동 합니다.
2. 정책 이름 왼쪽에 있는을 클릭 하 여 정책을 선택 합니다.
3. **사용자 관리**를 선택 합니다.
4. **사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 선택 합니다. 추가 하려는 각 사용자에 대해이 단계를 반복 합니다.
5. 사용자 추가를 마쳤으면 **저장**을 선택 합니다.

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a>그룹의 사용자에 게 사용자 지정 발신자 ID 정책 할당

이미 식별 한 여러 사용자에 게 사용자 지정 정책을 할당 하려고 할 수 있습니다. 예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다. 그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여이 작업을 수행할 수 있습니다. PowerShell을 사용 하 여 팀을 관리 하는 방법에 대 한 자세한 내용은 [팀 Powershell 개요](teams-powershell-overview.md)를 참조 하세요.

이 예제에서는 사용자 지정 호출자 덮개 정책을 Contoso 지원 그룹의 모든 사용자에 게 할당 합니다.  

> [!NOTE]
> 먼저 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)의 단계를 따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.

특정 그룹의 GroupObjectId를 가져옵니다.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
지정 된 그룹의 구성원을 가져옵니다.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
그룹의 모든 사용자를 특정 발신자 ID 정책에 할당 합니다. 이 예제에서는 발신자 ID 정책을 지원 합니다.
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.

 ## <a name="related-topics"></a>관련 항목

- [새로운 CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

