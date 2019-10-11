---
title: 팀 PowerShell 개요
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: PowerShell 컨트롤을 사용 하 여 Microsoft 팀을 관리 하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75bb6a982db4ab3986a423cf958ad8e81105380c
ms.sourcegitcommit: a71ad6762e18267faaaac09533bac80a181102af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2019
ms.locfileid: "37439586"
---
# <a name="teams-powershell-overview"></a>팀 PowerShell 개요

Microsoft 팀에는 Microsoft 팀 관리 센터, PowerShell 컨트롤, 그래프 Api를 통해 제품을 관리 하기 위한 다양 한 도구 집합이 있습니다. 이 가이드에서는 IT 관리자를 위해 PowerShell cmdlet을 사용 하도록 구조화 하는 방법에 대해 설명 하 고 추가 설명서에 대 한 포인터를 제공 합니다. 여러 팀 관리자 역할이 서로 다른 cmdlet에 액세스할 수 있다는 점에 유의 하세요. 자세한 내용은 [Microsoft 팀 관리 역할을 사용 하 여 팀 관리를](using-admin-roles.md)참조 하세요.

## <a name="which-modules-do-you-need-to-use"></a>어떤 모듈을 사용 해야 하나요?

팀 관리를 위한 PowerShell 컨트롤은 두 가지 다른 PowerShell 모듈에 있습니다. 
- [Microsoft 팀 powershell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams/) : 팀 powershell 모듈에는 팀을 만들고 관리 하는 데 필요한 모든 cmdlet이 포함 되어 있습니다.  
- 비즈니스용 [Skype powershell 모듈](https://www.microsoft.com/en-us/download/details.aspx?id=39366): 비즈니스용 skype powershell 모듈에는 정책, 구성, 기타 팀 도구를 관리 하는 cmdlet이 포함 되어 있습니다. 

PowerShell 컨트롤에 대 한 참조 설명서에서는 조사 하는 cmdlet을 포함 하는 모듈을 확인할 수 있습니다. (최종적으로 두 모듈을 결합 하는 것입니다.)

## <a name="what-can-each-admin-role-do"></a>각 관리자 역할이 수행할 수 있는 작업

[Microsoft 팀 관리자 역할을 사용 하 여 팀을 관리 하](using-admin-roles.md) 고 다른 관리자 역할이 활용할 수 있는 PowerShell cmdlet을 파악 합니다.

## <a name="creating-and-managing-teams-via-powershell"></a>PowerShell을 통해 팀 만들기 및 관리

팀을 만들고 관리 하는 cmdlet은 [Microsoft 팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams/)에서 사용할 수 있습니다. 

팀은 O365 그룹에 의해 지원 되므로 팀을 만들 때 그룹을 만듭니다. 핵심 팀과 해당 설정 (``new-team``, ``get-team``, ``set-team``)에 대 한 작동을 위해 제공 되는 cmdlet 집합과 팀 사용자 관리 (``add-teamuser``() ``remove-teamuser``) 뿐만 아니라 팀 (``new-teamchannel``, ``remove-teamchannel``) 채널을 관리 하는 cmdlet도 포함 되어 있습니다. 이러한 모든 cmdlet은 최종 사용자로 실행할 수 있지만 사용자가 소유 하거나 구성원 인 팀 에서만 작동 합니다. 전역 관리자 또는 팀 서비스 관리자는 조직의 모든 팀에 대해 작업을 수행할 수 있습니다.

> Microsoft 팀 PowerShell 모듈 cmdlet에 사용 되는 **GroupId** 는 Exchange powershell 모듈 ``Get-UnifiedGroup`` 에서 반환 되는 **Identity** 속성과 같습니다.

### <a name="differences-between-preview-and-generally-available-microsoft-teams-powershell-module"></a>미리 보기와 일반적으로 사용할 수 있는 Microsoft 팀 PowerShell 모듈의 차이점

일반적으로 사용 가능한 PowerShell 모듈 버전을 릴리스할 때 아래 표에 설명 된 대로 몇 가지 cmdlet이 베타 전용 모듈에 남아 있습니다.

| 은 | 미리 보기에서 사용 가능 | 1.0에서 사용 가능 |
|------- | -------------------- | ------------------------------ |
| 팀 추가 사용자 | ' | ' |
| 연결-MicrosoftTeams | ' | ' |
| 연결 해제-MicrosoftTeams | ' | ' |
| 가져오기-팀 | ' | ' |
| 팀에서 채널을 가져옵니다. | ' | ' |
| Get-TeamFunSettings | 1.0 릴리스 전용 이전 | 아니요 |
| Get-TeamGuestSettings | 1.0 릴리스 전용 이전 | 아니요 |
| 내려받기-팀 도움말 | ' | ' |
| 가져오기-팀 구성원 설정 | 1.0 릴리스 전용 이전 | 아니요 |
| 가져오기-팀 Messagingsettings | 1.0 릴리스 전용 이전 | 아니요 |
| 팀 구매 사용자 | ' | ' |
| 신규-팀 | ' | ' |
| 새 팀 채널 | ' | ' |
| 팀 제거 | ' | ' |
| 팀 제거 채널 | ' | ' |
| -팀 사용자 제거 | ' | ' |
| 집합-팀 | ' | ' |
| TeamChannel | ' | ' |
| Set-TeamFunSettings | 1.0 릴리스 전용 이전 | 아니요 |
| Set-TeamGuestSettings | 1.0 릴리스 전용 이전 | 아니요 |
| 집합-TeamMemberSettings | 1.0 릴리스 전용 이전 | 아니요 |
| 설정-팀 Messagingsettings | 1.0 릴리스 전용 이전 | 아니요 |
| 팀 사진 | ' | 아니요, 계획 됨 |


## <a name="managing-policies-via-powershell"></a>PowerShell을 통해 정책 관리

정책을 관리 하는 cmdlet은 [비즈니스용 Skype cmdlet 모듈](https://www.microsoft.com/en-us/download/details.aspx?id=39366)에 있습니다.

> [!NOTE]
> 비즈니스용 Skype Online에 연결 되 면 PowerShell 세션에서 cmdlet을 사용할 수 있습니다. 자세한 내용은 [Office 365 PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)를 참조 하세요. 

정책은 개인 사용자에 게 granularly 적용할 수 있는 설정 그룹입니다. 각 정책 형식에는 정책 자체를 만들고, 보고, 삭제 하 고, 업데이트 하 고, 해당 정책을 사용자에 게 할당할 수 있는 고유한 cmdlet 집합이 있습니다. 일반적인 구조는 다음과 같습니다.

- 명령 가져오기 (예를 ``Get-CsTeamsMeetingPolicy``들어): 조직에서 할당할 수 있는 정책 문서, Microsoft에서 만든 정책, 만든 사용자 지정 정책을 반환 합니다.
   > 조직에서 만든 사용자 지정 정책만 찾으려는 경우을 사용할 ``-Filter "tag:*"``수 있습니다.

- 새로운 명령 (예를 ``New-CsTeamsMeetingPolicy``들어): 조직에 대 한 새 정책을 만들어 조직의 사용자에 게 배정할 수 있도록 합니다. 모든 정책이 사용자 지정 정책 만들기를 지원 하지는 않습니다. 조직에서 사용 하는 정책에 지원 되는 설정 조합이 있는지 확인 하는 것이 일반적입니다.

- 명령 설정 (예를 ``Set-CsTeamsMeetingPolicy``들어): 지정 된 정책에서 특정 값을 설정할 수 있습니다. 일부 정책에 사용할 수 있는 set 명령이 없거나 정책에서 사용자 지정할 수 없는 매개 변수가 포함 되어 있지 않습니다. 각 PowerShell 설명은 사용자 지정할 수 없는 매개 변수를 호출 합니다. 
   > 사용자 지정 정책이 할당 되지 않은 조직의 사용자에 게 기본적으로 할당 되는 정책을 편집 하려면를 실행 ``Set-Cs<PolicyName> -Identity Global``합니다.

- 명령 제거 (예: ``Remove-CsTeamsMeetingPolicy``) 다음을 수행 합니다 .이 cmdlet을 사용 하 여 테 넌 트에서 만든 사용자 지정 정책을 삭제할 수 있습니다. 조직에서 하나 이상의 사용자에 게 할당 된 사용자 지정 정책을 삭제 하는 경우 해당 사용자는 전역 정책으로 대체 됩니다.
   > 조직에서 글로벌 정책을 실제로 제거할 수는 없지만 조직의 전역 정책을 Microsoft에서 제공 하는 기본 설정으로 다시 설정 하려는 경우에는를 실행할 ``Remove-Cs<PolicyName> -Identity Global``수 있습니다.

- 허용 명령 (예를 ``Grant-CsTeamsMeetingPolicy``들어): 정책을 특정 사용자에 게 할당할 수 있습니다.
   > 사용자 지정 정책 할당을 제거 하 고 사용자가 조직의 기본 정책으로 돌아갈 수 있도록 설정 하려면를 실행 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``합니다.

> [!TIP]
> 모든 정책에서 사용자 지정 정책을 만들 수 있는 것은 아니지만 일부 정책에는 사용자 지정할 수 없는 설정이 포함 되어 있으므로 설정을 볼 수 있지만 및 ``set-`` ``new-``중에 사용자 지정 값을 설정할 수는 없습니다. 특정 cmdlet의 설명서는 고객이 매개 변수를 사용할 수 없는 경우에 호출 됩니다.

공통 매개 변수:

- **Id**: ``Get-`` ``Set-``,, ``New-``, 및 ``Remove-``에서 **id** 매개 변수는 항상 특정 정책 인스턴스를 참조 합니다. 의 ``Grant``경우 **Identity** 매개 변수는 정책이 적용 되는 특정 사용자 개체를 참조 합니다.

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>PowerShell을 통한 구성 관리

구성을 관리 하는 cmdlet은 [비즈니스용 Skype cmdlet 모듈](https://www.microsoft.com/en-us/download/details.aspx?id=39366)에 있습니다.

구성은 사용자 수준에서 지정할 수 없는 서비스에서 유지 관리 되는 설정의 버킷을 말합니다. 설정은 항상 전체 조직에서 적용 됩니다. 글로벌 구성은 조직의 유일한 유효 구성입니다. 각 구성 유형에는 두 가지 기본 cmdlet이 포함 됩니다.

- ``Get-Cs<ConfigurationName>``(예를 들어 ``Get-CsTeamsClientConfiguration``) 다음을 수행 합니다. 

- 명령 (예: ``Set-CsTeamsClientConfiguration``)을 설정 합니다. 해당 형식의 구성에서 속성을 설정 합니다. 수정 하려는 매개 변수를 지정 합니다.
   > **Id 전역**을 지정 하거나를 실행 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``하 여 두 가지 방법 중 하나로 수정 하는 구성을 참조할 수 있습니다.

## <a name="other-powershell-tools"></a>다른 PowerShell 도구

각 정책의 설정에 대 한 자세한 설명과 [Microsoft 팀 cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps) 및 [skype for Business를 비롯 하 여 모든 PowerShell 컨트롤을 사용 하 여 Microsoft 팀과 비즈니스용 skype를 관리 하는 방법에 대 한 자세한 지침을 확인할 수 있습니다. 비즈니스 cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="learn-more"></a>더 알아보세요

- [Microsoft 팀 cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [비즈니스용 Skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [Microsoft 팀 관리자 역할을 사용 하 여 팀 관리](using-admin-roles.md)
