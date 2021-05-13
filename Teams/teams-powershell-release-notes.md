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
description: PowerShell의 최신 변경 Teams 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 601783d5c0b3b84470e79abbc705c4c22244581b
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469640"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell 릴리스 정보

이 페이지에서는 일반 Teams 공개 미리 보기 릴리스에 대한 최신 PowerShell 변경 로그를 제공합니다.

## <a name="release-notes"></a>릴리스 정보

> [!NOTE]
> 아래 버전 열의 **-preview는** PowerShell 공개 미리 보기에 대한 Teams 표시됩니다.

| 날짜 | 버전 | 업데이트 |
|------- | -------------------- | ------------------------------ |
| 2021년 5월 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>에서 업데이트합니다. NETCore 2.1~3.1</li><li>사용자 및 그룹에 대한 다중 지역 지역을 얻을 수 있는 cmdlet이 추가되었습니다.</li><li>-AccountId를 사용하여 통합된 windows 인증에 대한 Connect-MicrosoftTeams</li><li>TeamsCallHoldPolicy cmdlet을 사용할 수 있습니다.</li><li>여러 명령의 입력 매개 변수 및 출력 형식 업데이트</li><li>명령을 리모트하는 동안 대기 시간 문제가 해결됩니다.</li><li>GA 사용자 지정 패키지 기능</li>|
| 2021년 4월 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>-accountId를 Windows-MicrosoftTeams와 함께 -accountId를 사용하는 통합 커넥트 수정합니다.</li><li>사용자에게 보낼 수 있는 전체 변경 알림 이벤트에 대한 세부 정보를 얻을 수 있는 cmdlet이 추가되었습니다.</li><li>사용자 및 그룹에 대한 다중 지역 지역을 얻을 수 있도록 cmdlet을 추가했습니다.</li><li>TeamsEnvironment 이름에 전달된 값의 처리는 대소문자 구분이 중요했습니다. 이 수정되었습니다.</li><li>단위 테스트를 용이하게 하기 위해 모듈 내의 원격 세션 관리의 주요 리포터입니다. 테넌트 관리자에 대한 기능 변경은 없습니다.</li>|
| 2021년 4월 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>기존 cmdlet의 서식이 수정되었습니다(예: Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy 등).</li><li>정책 관리 cmdlet의 업데이트된 매개 변수 목록입니다.</li>|
| 2021년 3월 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>인증 권한 부여에 MSAL & 사용</li> <li>Connect-MicrosoftTeams 모든 cmdlet의 진입점입니다.</li><li>New-csOnlineSession을 더 이상 사용할 수 없습니다. 이 는 커넥트-MicrosoftTeams로 대체됩니다.</li><li>Enable-csonlinesessionforreconnection은 더 이상 필요하지 않습니다. 이 기능은 기본적으로 PowerShell 모듈에서 Teams 구현됩니다.</li> <li>리포터된 정책 패키지 cmdlet 및 그룹 패키지 할당 추가</li><li>cmdlet에 대한 Get-Team 향상된 기능</li> <li>기존 cmdlet에 대한 향상된 로깅 및 디버깅 옵션 </li> <li>템플릿 관리 cmdlet 추가</li> <li>New-CsOnlineSession</li>|
| 2021년 2월 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>템플릿 관리 cmdlet 추가</li><li>cmdlet에 대한 Mezzo 및 일괄 처리 Get-Team 향상</li> <li>기존 cmdlet에 대한 향상된 로깅 및 디버깅 옵션 </li> <li>리포터된 정책 패키지 cmdlet</li>|
| 2020년 12월 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>재시도 및 절전 기간이 증가한 New-team cmdlet 업데이트</li>|
| 2020년 12월 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>온라인 비즈니스용 Skype 업데이트</li><li>중복 프롬프트에 대한 Connect-Microsoft Teams</li>|
| 2020년 11월 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>사용자 지정 정책 패키지 cmdlet 추가</li><li>대상 계층 구조 업로드 명령에 대한 수정</li>|
| 2020년 11월 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>인증 권한 부여에 MSAL & 사용</li><li>리포터된 정책 패키지 cmdlet 및 그룹 패키지 할당 추가</li><li>비동기 모델을 사용하기 위해 리포터링된 대상 지정 계층 구조 업로드 명령</li> <li>초기 인증 중에 -credential 매개 변수를 사용하지 않는 경우 사용자에게 두 번 메시지가 표시됩니다. 사용자는 중복 프롬프트를 방지하기 위해 -credential 매개 변수를 사용하여 자격 증명을 전달할 수 있습니다. 이 동작은 다음 릴리스에서 해결됩니다.</li> |
| 2020년 9월 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>비즈니스용 Skype 온라인 커넥터 통합</li> |
| 2020년 9월 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>비즈니스용 Skype 온라인 커넥터 통합</li> |
| 2020년 7월 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>그룹 [정책 할당 cmdlet 추가](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| 2020년 6월 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>비즈니스용 Skype 온라인 커넥터 통합<li>Get-Team 최적화<li>향상된 안정성</li> |
| 2020년 6월 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Cmdlet 미리 로드 추가<li>.Net Framework 최적화</li>   |
| 2020년 4월 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode 및 어셈블리 서명<li>추가된 Get-CsPolicyPackage<li>추가된 Get-CsUserPolicyPackage<li>추가된 Get-CsUserPolicyPackageRecommendation<li>추가된 Grant-CsUserPolicyPackage<li>추가된 New-CsBatchPolicyPackageAssignmentOperation<li>추가된 Set-TeamArchivedState<li>추가된 Set-TeamPicture<li>제거된 Get-TeamHelp</li>  |
| 2020년 3월 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>추가된 New-CsBatchPolicyAssignmentOperation</li> |
| 2020년 2월 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team 최적화</li>  |

## <a name="related-topics"></a>관련 항목

[Teams PowerShell 개요](teams-powershell-overview.md)

[PowerShell Teams 설치](teams-powershell-install.md)

[PowerShell을 Teams Teams 관리](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 참조](/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](/powershell/skype/intro?view=skype-ps)
