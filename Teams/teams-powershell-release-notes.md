---
title: Microsoft Teams PowerShell 릴리스 정보
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
description: Teams PowerShell의 최신 변경 내용에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 159e73ff9f499538f830da6dd57c8ff7584e49cd
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874738"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell 릴리스 정보

이 페이지에서는 일반 공급 및 공개 미리 보기 릴리스 모두에 대한 최신 Teams PowerShell 변경 로그를 제공합니다.

## <a name="release-notes"></a>릴리스 정보

> [!NOTE]
> 아래 버전 열의 **-preview는** Teams PowerShell 공개 미리 보기에 대한 업데이트를 나타내는 것입니다.

| 날짜 | 버전 | 업데이트 |
|------- | -------------------- | ------------------------------ |
| 2021년 3월 | [2.0](https://www.powershellgallery.com/packages/MicrosoftTeams/) | <li>Connect-MicrosoftTeams 모든 cmdlet의 진입점입니다.</li><li>New-csOnlineSession은 더 이상 사용 가능하지 않습니다. 이는 Connect-MicrosoftTeams로 대체됩니다.</li><li>Enable-csonlinesessionforreconnection은 더 이상 필요하지 않습니다. 이 기능은 Teams PowerShell 모듈에서 기본적으로 구현됩니다.</li>|
| 2020년 11월 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>버그 수정 및 개선</li>|
| 2020년 11월 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>버그 수정 및 개선</li>|
| 2021년 3월 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>인증 권한 부여에 MSAL & 사용</li><li>리포터된 정책 패키지 cmdlet 및 그룹 패키지 할당 추가</li><li>cmdlet에 대한 Get-Team 향상된 기능</li> <li>기존 cmdlet에 대한 향상된 로깅 및 디버깅 옵션 </li> <li>템플릿 관리 cmdlet 추가</li> <li>New-CsOnlineSession</li>|
| 2021년 2월 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>템플릿 관리 cmdlet 추가</li><li>cmdlet에 대한 Mezzo 및 일괄 처리 Get-Team 향상</li> <li>기존 cmdlet에 대한 향상된 로깅 및 디버깅 옵션 </li> <li>리포터된 정책 패키지 cmdlet</li>|
| 2020년 12월 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>재시도 및 절전 기간이 증가한 New-team cmdlet 업데이트</li>|
| 2020년 12월 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>비즈니스용 Skype 온라인 통합에 대한 업데이트</li><li>팀과 중복 프롬프트에 Connect-Microsoft 수정</li>|
| 2020년 11월 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>사용자 지정 정책 패키지 cmdlet 추가</li><li>대상 계층 구조 업로드 명령에 대한 수정</li>|
| 2020년 11월 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>인증 권한 부여에 MSAL & 사용</li><li>리포터된 정책 패키지 cmdlet 및 그룹 패키지 할당 추가</li><li>비동기 모델을 사용하기 위해 리포터링된 대상 지정 계층 구조 업로드 명령</li> <li>초기 인증 중에 -credential 매개 변수를 사용하지 않는 경우 사용자에게 두 번 메시지가 표시됩니다. 사용자는 중복 프롬프트를 방지하기 위해 -credential 매개 변수를 사용하여 자격 증명을 전달할 수 있습니다. 이 동작은 다음 릴리스에서 해결됩니다.</li> |
| 2020년 9월 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>비즈니스용 Skype Online 커넥터 통합</li> |
| 2020년 9월 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>비즈니스용 Skype Online 커넥터 통합</li> |
| 2020년 7월 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>그룹 [정책 할당 cmdlet 추가](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| 2020년 6월 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>비즈니스용 Skype Online 커넥터 통합<li>Get-Team 최적화<li>향상된 안정성</li> |
| 2020년 6월 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Cmdlet 미리 로드 추가<li>.Net Framework 최적화</li>   |
| 2020년 4월 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode 및 어셈블리 서명<li>추가된 Get-CsPolicyPackage<li>추가된 Get-CsUserPolicyPackage<li>추가된 Get-CsUserPolicyPackageRecommendation<li>추가된 Grant-CsUserPolicyPackage<li>추가된 New-CsBatchPolicyPackageAssignmentOperation<li>추가된 Set-TeamArchivedState<li>추가된 Set-TeamPicture<li>제거된 Get-TeamHelp</li>  |
| 2020년 3월 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>추가된 New-CsBatchPolicyAssignmentOperation</li> |
| 2020년 2월 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team 최적화</li>  |

### <a name="cmdlet-availability"></a>Cmdlet 가용성

> [!NOTE]
> 아래 표의 목록에는 Teams PowerShell 모듈의 기본 부분인 cmdlet만 포함됩니다. 비즈니스용 S[kype Online 커넥터](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) 모듈의 Teams cmdlet은 표시되지 않습니다. 그러나 이러한 cmdlet이 Teams PowerShell으로 기본적으로 마이그레이션될 때 이 테이블에 추가합니다.

| Cmdlet | 공개 미리 보기에서 사용할 수 있습니다. | GA에서 사용할 수 있습니다. |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | 예 | **아니요** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | 예 | 예 |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | 예 | **아니요**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | 예 | 예 |
| [연결 끊기-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | 예 | 예 |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | 예 | 예 |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment?view=teams-ps) | 예 | **아니요** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint?view=skype-ps) | 예 | 예 |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | 예 | 예 |
| [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | 예 | 예 |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | 예 | 예 |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | 예 | 예 |
| [Get-Team](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | 예 | 예 |
| [Get-TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | 예 | 예|
| [Get-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | 예 | **아니요** |
| [Get-TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | 예 | 예 |
| [Get-TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | 예 | 예 |
| [Get-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | 예 | **아니요** |
| [Grant-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | 예 | 예 |
| [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | 예 | 예 |
| [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | 예 | 예 |
| [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | 예 | 예 |
| [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession?view=skype-ps) | 예 | 예 |
| [New-Team](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | 예 | 예 |
| [New-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-teamchannel?view=teams-ps) | 예 | 예 |
| [New-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | 예 | 예 |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | 예 | 예 |
| [Remove-Team](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | 예 | 예 |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | 예 | 예 |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | 예 | **아니요** |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | 예 | 예 |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | 예 | **아니요** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy#remove-your-hierarchy) | 예 | **아니요**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | 예 | 예 |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | 예 | **아니요** |
| [Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | 예 | 예 |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | 예 | 예 |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | 예 | 예 |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | 예 | 예 |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | 예 | 예 |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | 예 | **아니요** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | 예 | **아니요** |
| [Enable-CsOnlineSessionForReconnection](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/diagnose-problems-with-the-skype-for-business-online-connector) | **아니요** | **아니요** |


## <a name="related-topics"></a>관련 주제

[Teams PowerShell 개요](teams-powershell-overview.md)

[Teams PowerShell 설치](teams-powershell-install.md)

[Teams PowerShell을 통해 Teams 관리](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
