---
title: PowerShell에서 Teams 관리 Microsoft Teams 관리
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell을 사용하여 Microsoft Teams 관리 Teams 방법을 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71f68c813a1379c29cf64ad732eb5da1ffe4d188
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238974"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>PowerShell에서 Teams 관리 Microsoft Teams 관리

이 문서에서는 PowerShell을 사용하여 Microsoft Teams 및 데이터 Teams 방법을 비즈니스용 Skype. 

이 지침은 Microsoft Teams [cmdlet](/powershell/teams/?view=teams-ps) 참조 및 비즈니스용 Skype 참조와 함께 [사용하세요.](/powershell/skype/intro?view=skype-ps)

## <a name="create-and-manage-teams-using-powershell"></a>PowerShell을 사용하여 팀 만들기 및 관리

팀을 만들고 관리하기 위한 [cmdlet은 PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Microsoft Teams 있습니다.

Teams 그룹에서 Office 365 팀을 만들 때 그룹을 만들 수 있습니다. 팀의 채널을 관리하기 위한 ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` cmdlet뿐만 ``new-teamchannel`` 아니라 핵심 팀 및 해당 설정(, , ) 관리 팀 사용자(, ) 에서 작동하기 위해 제공되는 cmdlet 집합이 ``remove-teamchannel`` 있습니다. 이러한 모든 cmdlet은 최종 사용자로 실행할 수 있지만 사용자가 소유하거나 구성원인 팀에서만 작동하게 됩니다. 전역 관리자 또는 Teams 관리자인 경우 조직의 모든 팀에서 행동할 수 있습니다.

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> **PowerShell** 모듈 cmdlet에 Microsoft Teams GroupId는 PowerShell 모듈에서 반환된 **ID** ``Get-UnifiedGroup`` Exchange 동일합니다.

## <a name="manage-policies-via-powershell"></a>PowerShell을 통해 정책 관리

> [!NOTE]
> - 비즈니스용 Skype 온라인 커넥터가 PowerShell에 Teams 있습니다. 현재 공개 미리 보기에서 사용할 수 있습니다. 시간이 비즈니스용 Skype PowerShell 모듈에서 기본적으로 Teams 온라인 cmdlet을 Teams 수 있습니다. 설치 단계는 [PowerShell](teams-powershell-install.md) 설치 문서에서 Teams 있습니다.
>
> - 온라인에 연결하면 powerShell 세션에서 cmdlet을 사용할 비즈니스용 Skype 있습니다. 자세한 내용은 [PowerShell을](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)사용하여 비즈니스용 Skype 온라인 Office 365 참조하세요.

비즈니스용 Skype cmdlet 모듈에서 정책을 관리하기 [위한 cmdlet을 찾을 수 있습니다.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

정책은 개별 사용자에게 세분화하여 적용할 수 있는 설정 그룹입니다. 각 정책 유형에는 정책을 만들고, 보고, 삭제하고, 업데이트한 다음 사용자에게 해당 정책을 할당하기 위한 자체 cmdlet 집합이 있습니다. 일반적인 구조는:

- **GET** 명령(예: ): 조직에서 할당할 수 있는 정책 문서를 반환합니다( Microsoft에서 만든 정책 및 만든 사용자 지정 정책 ``Get-CsTeamsMeetingPolicy`` 포함).
   - 조직에서 만든 사용자 지정 정책만 찾으면 ``-Filter "tag:*"`` 를 사용 합니다.

- **NEW** 명령(예: ): 조직의 사용자에게 할당할 조직에 대한 새 정책을 ``New-CsTeamsMeetingPolicy`` 만듭니다. 모든 정책이 사용자 지정 정책 만들기를 지원하지는 않습니다. 조직에서 사용하는 정책에 지원되는 설정 조합이 되도록 하는 경우가 종종 있습니다.

- **SET** 명령(예: ): 특정 정책에서 ``Set-CsTeamsMeetingPolicy`` 특정 값을 설정합니다. 일부 정책에는 SET 명령을 사용할 수 없는 경우 또는 정책에서 사용자 지정할 수 없는 매개 변수가 포함되어 있습니다. PowerShell 설명에서는 사용자 지정할 수 없는 매개 변수를 알 수 있습니다. 
   - 사용자 지정 정책이 할당되지 않은 조직의 사용자에게 기본적으로 할당될 정책을 편집하려면 ``Set-Cs<PolicyName> -Identity Global`` 을 실행합니다.

- **REMOVE** 명령(예: ): 테넌트에서 만든 사용자 지정 정책을 ``Remove-CsTeamsMeetingPolicy`` 삭제합니다. 조직에서 하나 이상의 사용자에게 할당된 사용자 지정 정책을 삭제하면 해당 사용자가 전역 정책으로 돌아가게 됩니다.
   - 조직의 전역 정책을 실제로 제거할 수 없지만 조직의 전역 정책을 Microsoft에서 제공한 기본 설정으로 다시 설정하려면 을 ``Remove-Cs<PolicyName> -Identity Global`` 실행합니다.

- **GRANT** 명령(예: ): 특정 사용자에게 정책을 ``Grant-CsTeamsMeetingPolicy`` 할당합니다.
   - 사용자 지정 정책 할당을 제거하고 사용자가 조직의 기본 정책으로 돌아가게하려면 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 을 실행합니다.

> [!TIP]
> 모든 정책이 사용자 지정 정책을 만들 수 있는 것은 아니며, 일부 정책에는 사용자 지정할 수 없는 설정이 있습니다(따라서 설정을 볼 수 있지만 및 동안에는 사용자 지정 값을 설정할 수 ``set-`` ``new-`` 없습니다). 각 cmdlet에 대한 설명서는 고객이 매개 변수를 사용할 수 있는지 여부를 호출합니다.

일반적인 매개 변수:

- **ID**: 의 경우 , 및 의 경우 ID 매개 변수는 항상 특정 정책 ``Get-`` ``Set-`` ``New-`` ``Remove-`` 인스턴스를 참조합니다.  의 경우 ID 매개 변수는 정책이 적용되는 특정 사용자 개체를 ``Grant`` 참조합니다. 

## <a name="manage-configurations-via-powershell"></a>PowerShell을 통해 구성 관리

비즈니스용 Skype cmdlet 모듈에서 [구성을 관리하기 위한 cmdlet을 찾아야 합니다.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)

구성은 사용자 수준에서 지정할 수 없는 서비스에서 유지 관리되는 설정의 버킷입니다. 설정 항상 전체 조직에 적용됩니다. 전역 구성은 조직에서 유일한 효과적인 구성입니다. 각 구성 유형에는 두 개의 기본 cmdlet이 함께 있습니다.

- ``Get-Cs<ConfigurationName>`` (예: ``Get-CsTeamsClientConfiguration`` ):

- SET 명령(예: ): 해당 형식의 구성에서 속성을 ``Set-CsTeamsClientConfiguration`` 설정합니다. 수정할 매개 변수를 지정합니다.
   > 을 지정하거나 를 실행하여 두 가지 방법 중 하나에서 수정하는 구성을 참조할 수 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 있습니다.

## <a name="what-can-each-admin-role-do"></a>각 관리자 역할은 무엇을 할 수 있나요?

관리자 [Microsoft Teams](using-admin-roles.md) 사용하여 관리 Teams 각 PowerShell cmdlet을 실행할 수 있는 관리자 역할을 이해합니다.

## <a name="related-topics"></a>관련 주제

[PowerShell Teams 설치](teams-powershell-install.md)

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Teams cmdlet 참조](/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](/powershell/skype/intro?view=skype-ps)

[Teams 관리자 역할을 사용하여 Teams를 관리](using-admin-roles.md)