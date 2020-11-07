---
title: Microsoft 팀 PowerShell 릴리스 정보
ms.reviewer: brandber
author: BrandBer
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 팀 PowerShell의 최신 변경 사항에 대해 알아보세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41aa6cdf05901756bb2bcd13dbb8b9ad2cedabf6
ms.sourcegitcommit: a6c7a0cdbedf6cf32213d7636da52db71b4bac3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2020
ms.locfileid: "48937747"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft 팀 PowerShell 릴리스 정보

이 페이지에서는 일반 사용 가능성 및 공용 미리 보기 릴리스 모두에 대 한 최신 팀 PowerShell 변경 로그를 제공 합니다.

## <a name="release-notes"></a>릴리스 정보

> [!NOTE]
> -아래 버전 열의 **미리 보기** 는 팀 PowerShell 공개 미리 보기의 업데이트를 나타냅니다.

| 시작일 | 버전 | 업데이트 |
|------- | -------------------- | ------------------------------ |
| 2020 년 11 월 | [1.1.7-미리 보기](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>인증 & 승인에 MSAL 사용</li><li>정책 패키지 cmdlet을 리팩터링 하 고 그룹 패키지 할당을 추가 합니다.</li><li>비동기 모델을 사용 하도록 대상 계층 구조 업로드 명령 리팩터링</li> <li>사용자는-credential 매개 변수를 사용 하지 않을 때 초기 인증 중에 두 번 메시지가 표시 됩니다. 사용자는-credential 매개 변수를 사용 하 여 자격 증명을 전달 하 여 중복 메시지를 피할 수 있습니다. 이 동작은 다음 릴리스에서 해결 될 것입니다.</li> |
| 2020 년 9 월 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>비즈니스용 Skype Online 커넥터 통합</li> |
| 2020 년 9 월 | [1.1.5-미리 보기](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>비즈니스용 Skype Online 커넥터 통합</li> |
| 2020 년 7 월 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>[그룹 정책 할당 cmdlet](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group) 이 추가 됨</li> |
| 2020 년 6 월 | [1.1.3-미리 보기](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>비즈니스용 Skype Online 커넥터 통합<li>Get-Team 최적화<li>향상 된 안정성</li> |
| 2020 년 6 월 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Cmdlet 미리 로드 추가 됨<li>.Net Framework 최적화</li>   |
| 2020 년 4 월 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode 및 어셈블리 서명<li>Get-CsPolicyPackage 추가 됨<li>Get-CsUserPolicyPackage 추가 됨<li>Get-CsUserPolicyPackageRecommendation 추가 됨<li>Grant-CsUserPolicyPackage 추가 됨<li>New-CsBatchPolicyPackageAssignmentOperation 추가 됨<li>Set-TeamArchivedState 추가 됨<li>Set-TeamPicture 추가 됨<li>Get-TeamHelp 제거 됨</li>  |
| 2020 년 3 월 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>New-CsBatchPolicyAssignmentOperation 추가 됨</li> |
| 2020 년 2 월 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team 최적화</li>  |

### <a name="cmdlet-availability"></a>Cmdlet 가용성

> [!NOTE]
> 아래 표의 목록에는 팀 PowerShell 모듈에 기본적으로 포함 된 cmdlet만 포함 되어 있습니다. S[Kype For 비즈니스용 온라인 커넥터 모듈](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) 의 팀 cmdlet이 표시 되지 않습니다. 그러나 이러한 cmdlet은 기본적으로 팀 PowerShell로 마이그레이션 되므로이 테이블에 추가 됩니다.

| 은 | 공개 미리 보기에서 사용 가능 | GA에서 사용 가능 |
| -| -- | --|
| [TeamChannelUser 추가](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | 예 | **아니요** |
| [팀 추가 사용자](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | 예 | 예 |
| [추가-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | 예 | **아니요**|
| [연결-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | 예 | 예 |
| [연결 해제-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | 예 | 예 |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | 예 | 예 |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | 예 | **아니요** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | 예 | 예 |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | 예 | 예 |
| [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | 예 | 예 |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | 예 | 예 |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | 예 | 예 |
| [가져오기-팀](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | 예 | 예 |
| [팀에서 채널을 가져옵니다.](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | 예 | 예|
| [내려받기-팀 Channeluser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | 예 | **아니요** |
| [팀 구매 사용자](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | 예 | 예 |
| [내려받기 – TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | 예 | 예 |
| [Get-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | 예 | **아니요** |
| [부여-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | 예 | 예 |
| [새로운 CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | 예 | 예 |
| [새-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | 예 | 예 |
| [새로운 CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | 예 | 예 |
| [새로운 CsOnlineSession](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | 예 | 예 |
| [신규-팀](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | 예 | 예 |
| [새 팀 채널](https://docs.microsoft.com/powershell/module/teams/new-channel?view=teams-ps) | 예 | 예 |
| [새 팀 앱](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | 예 | 예 |
| [-CsGroupPolicyAssignment 제거](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | 예 | 예 |
| [팀 제거](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | 예 | 예 |
| [팀 제거 채널](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | 예 | 예 |
| [-TeamChannelUser 제거](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | 예 | **아니요** |
| [-TeamsApp 제거](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | 예 | 예 |
| [제거-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | 예 | **아니요** |
| [제거-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/remove-teamtargetinghierarchy?view=teams-ps) | 예 | **아니요**|
| [-팀 사용자 제거](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | 예 | 예 |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | 예 | **아니요** |
| [집합-팀](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | 예 | 예 |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | 예 | 예 |
| [TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | 예 | 예 |
| [팀 사진](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | 예 | 예 |
| [집합-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | 예 | 예 |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | 예 | **아니요** |
| [업데이트-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | 예 | **아니요** |

## <a name="related-topics"></a>관련 항목

[팀 PowerShell 개요](teams-powershell-overview.md)

[팀 PowerShell 설치](teams-powershell-install.md)

[팀을 사용 하 여 팀 관리 PowerShell](teams-powershell-managing-teams.md)

[Microsoft 팀 cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
