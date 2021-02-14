---
title: Microsoft Teams PowerShell을 사용하여 Teams 관리
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
description: Teams PowerShell을 사용하여 Microsoft Teams를 관리하는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 09d11b2c697ba57ea161d0ce961cf5ba73794617
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852179"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Microsoft Teams PowerShell을 사용하여 Teams 관리

이 문서에서는 Microsoft Teams PowerShell을 사용하여 Teams 및 비즈니스용 Skype를 관리하는 방법을 보여줍니다. 

이 지침은 Microsoft [Teams cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps) 및 [비즈니스용 Skype cmdlet 참조와 함께 사용하세요.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

## <a name="create-and-manage-teams-using-powershell"></a>PowerShell을 사용하여 팀 만들기 및 관리

팀을 만들고 관리하기 위한 cmdlet은 [Microsoft Teams PowerShell 모듈에 있습니다.](https://www.powershellgallery.com/packages/MicrosoftTeams/)

Teams는 Office 365 그룹에서 백업됩니다. 따라서 팀을 만들 때 그룹을 만들 수 있습니다. 핵심 팀 및 해당 설정(, , 팀 사용자 관리), 팀 사용자 관리( 및 팀 채널 관리)를 위해 제공되는 ``new-team`` ``get-team``  ``set-team`` cmdlet 집합이 ``add-teamuser`` ``remove-teamuser`` ``new-teamchannel`` ``remove-teamchannel`` 있습니다. 이러한 cmdlet은 모두 최종 사용자로 실행할 수 있지만 사용자가 소유하거나 구성원인 팀에서만 작업합니다. 전역 관리자 또는 Teams 서비스 관리자인 경우 조직의 모든 팀에서 행동할 수 있습니다.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> Microsoft Teams PowerShell 모듈 cmdlet에 사용되는 **GroupId는** Exchange PowerShell 모듈에서 반환된 **ID** 속성과 ``Get-UnifiedGroup`` 동일합니다.

## <a name="manage-policies-via-powershell"></a>PowerShell을 통해 정책 관리

> [!NOTE]
> - 비즈니스용 Skype Online Connector가 Teams PowerShell에 통합되고 있습니다. 현재 공개 미리 보기로 제공됩니다. Teams에 적용되는 비즈니스용 Skype Online cmdlet은 Teams PowerShell 모듈에서 기본적으로 사용할 수 있습니다. 설치 단계는 Teams [PowerShell 설치 문서에서 사용할 수](teams-powershell-install.md) 있습니다.
>
> - 비즈니스용 Skype Online에 연결하면 PowerShell 세션에서 cmdlet을 사용할 수 있습니다. 자세한 내용은 Office [365 PowerShell을](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)사용하여 비즈니스용 Skype Online 관리를 참조하세요.

비즈니스용 Skype cmdlet 모듈에서 정책을 관리하기 위한 [cmdlet을 찾을 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=39366)

정책은 개별 사용자에게 세분화하여 적용할 수 있는 설정 그룹입니다. 각 정책 유형에는 정책 자체를 만들고, 보고, 삭제하고, 업데이트한 다음, 사용자에게 해당 정책을 할당하기 위한 고유한 cmdlet 집합이 있습니다. 일반적인 구조는

- **GET** 명령(예: ): Microsoft에서 만든 정책 및 만든 사용자 지정 정책을 포함하여 조직에서 할당할 수 있는 정책 문서를 ``Get-CsTeamsMeetingPolicy`` 반환합니다.
   - 조직에서 만든 사용자 지정 정책만 찾으면 을(를) 사용 ``-Filter "tag:*"`` 합니다.

- **새** 명령(예: ): 조직의 사용자에게 할당할 새 ``New-CsTeamsMeetingPolicy`` 정책을 만듭니다. 모든 정책이 사용자 지정 정책 생성을 지원하지는 않습니다. 조직에서 사용하는 정책에 지원되는 설정 조합이 있도록 하는 경우가 종종 있습니다.

- **SET** 명령(예: ``Set-CsTeamsMeetingPolicy`` ): 주어진 정책에서 특정 값을 설정합니다. 일부 정책에는 SET 명령을 사용할 수 없는 경우도 있습니다. 또는 정책에서 사용자 지정할 수 없는 매개 변수가 포함되어 있습니다. PowerShell 설명은 사용자 지정할 수 없는 매개 변수를 나타냅니다. 
   - 사용자 지정 정책이 할당되지 않은 조직의 사용자에게 기본적으로 할당되는 정책을 편집하려면 다음을 ``Set-Cs<PolicyName> -Identity Global`` 실행합니다.

- **REMOVE** 명령(예: ): 테넌트에서 만든 사용자 지정 정책을 ``Remove-CsTeamsMeetingPolicy`` 삭제합니다. 조직에서 하나 이상의 사용자에게 할당된 사용자 지정 정책을 삭제하는 경우 해당 사용자는 전역 정책으로 되돌아가게 됩니다.
   - 조직에서 전역 정책을 실제로 제거할 수 없지만 조직의 전역 정책을 Microsoft에서 제공하는 기본 설정으로 다시 설정하려면 ``Remove-Cs<PolicyName> -Identity Global`` 실행합니다.

- **GRANT** 명령(예: ): 특정 사용자에게 정책을 ``Grant-CsTeamsMeetingPolicy`` 할당합니다.
   - 사용자 지정 정책 할당을 제거하고 사용자가 조직의 기본 정책으로 돌아오게하려면 다음을 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 실행합니다.

> [!TIP]
> 모든 정책에서 사용자 지정 정책을 만들 수 있는 것은 아니며, 일부 정책에는 사용자 지정할 수 없는 설정이 있습니다(설정을 볼 수 있지만 그 동안에는 사용자 지정 값을 설정할 수 ``set-`` ``new-`` 없습니다). 각 cmdlet에 대한 설명서는 고객이 매개 변수를 사용할 수 있는지 여부를 호출합니다.

일반적인 매개 변수:

- **ID:** ID 매개 변수의 경우, 및 ID 매개 변수는 항상 특정 정책 ``Get-`` ``Set-`` ``New-`` ``Remove-`` 인스턴스를 참조합니다.  이 경우 ID 매개 변수는 정책을 적용하는 특정 사용자 ``Grant`` 개체를 나타냅니다. 

## <a name="manage-configurations-via-powershell"></a>PowerShell을 통해 구성 관리

비즈니스용 Skype cmdlet 모듈에서 구성을 관리하기 위한 [cmdlet을 찾을 수 있습니다.](https://www.microsoft.com/en-us/download/details.aspx?id=39366)

구성은 사용자 수준에서 지정할 수 없는 서비스에서 유지 관리되는 설정의 버킷입니다. 설정은 항상 전체 조직에 적용됩니다. 전역 구성은 조직에서 유일하게 효과적인 구성입니다. 각 구성 유형에는 두 가지 기본 cmdlet이 함께 있습니다.

- ``Get-Cs<ConfigurationName>`` (예: ``Get-CsTeamsClientConfiguration`` ):

- SET 명령(예: ``Set-CsTeamsClientConfiguration`` ): 해당 형식의 구성에서 속성을 설정합니다. 수정하려는 매개 변수를 지정합니다.
   > ID 전역을 지정하거나 실행하여 두 가지 방법 중 하나에서 수정하는 **구성을** 참조할 수 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 있습니다.

## <a name="what-can-each-admin-role-do"></a>각 관리자 역할은 무엇을 할 수 있나요?

Microsoft Teams 관리자 [역할을 사용하여 Teams를](using-admin-roles.md) 관리하여 각 PowerShell cmdlet을 실행할 수 있는 관리자 역할을 이해합니다.

## <a name="related-topics"></a>관련 항목

[Teams PowerShell 설치](teams-powershell-install.md)

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Teams cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Teams 관리자 역할을 사용하여 Teams를 관리](using-admin-roles.md)
