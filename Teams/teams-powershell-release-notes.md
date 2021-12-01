---
title: Microsoft Teams PowerShell 릴리스 정보
ms.reviewer: gothambi
author: BrandBer
ms.author: gothambi
manager: naanur
ms.date: 11/30/2021
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: PowerShell의 최신 변경 Teams 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebaa5a3f5da4371da7fc2e6362a099756fabcda8
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257309"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams PowerShell 릴리스 정보

이 페이지에서는 일반 Teams 공개 미리 보기 릴리스에 대한 최신 PowerShell 변경 로그를 제공합니다.

## <a name="release-notes"></a>릴리스 정보

> [!NOTE]
> 아래 버전 열의 **-preview는** PowerShell 공개 미리 보기에 대한 Teams 표시됩니다.

| 날짜 | 버전 | 업데이트 |
|------- | -------------------- | ------------------------------ |
| 2021년 11월 | [3.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0) |<li>곧 Microsoft Teams 3.x.x 시리즈의 PowerShell 모듈 버전이 지원되는 유일한 버전이 됩니다. 이전 버전은 모두 사용되지 않습니다.</li><li> [BREAKING CHANGE] Get-CsOnlineUser 및 Get-CsOnlineVoiceUser: TeamsOnly 테넌트에 다음과 같은 변경 사항이 적용됩니다.<ul><li>이러한 cmdlet은 이제 이전 구현에서 새 API로 마이그레이션됩니다.</li><li>(-Identity 매개 변수 사용): 더 이상 관련이 없는 특성은 teamsOnly Teams 사용되지 않습니다. 일부 특성의 이름도 변경/대체됩니다. [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser?view=skype-ps) 및 [Get-CsOnlineVoiceUser 를 참조합니다.](/powershell/module/skype/get-csonlinevoiceuser?view=skype-ps)</li><li>Get-CsOnlineUser (-Filter 매개 변수): 할당된Plans 및 EnterpriseVoice를 기반으로 필터링하기 위한 서식이 수정되었습니다. 필터링 가능한 특성도 TeamsOnly 사용자에 대해 일시적으로 제한(사용량에 따라)되어 있습니다. [Get-CsOnlineVoiceUser 를 참조합니다.](/powershell/module/skype/get-csonlinevoiceuser?view=skype-ps)</li><li>이러한 cmdlet은 점진적으로 롤아웃될 것이고 일부 테넌트는 CY21이 끝날 때까지 이러한 변경 내용을 경험하지 않습니다.</ul></li><li>[중단된 변경] Get-CsTenant: Teams 세계에서 더 이상 관련이 없는 특성이 TeamsOnly 테넌트에 사용되지 않습니다. [Get-CsTenant](/powershell/module/skype/get-cstenant?view=skype-ps)를 참조합니다.</li><li> 모든 75+ Grant-Cs Policy cmdlet(모든 매개 변수 집합)의 \<Name\> 현대화된 버전을 릴리스합니다. 이러한 작업은 해당 리모팅과 유사하게 작동할 것으로 예상됩니다. 최신 버전은 점진적으로 롤아웃되어 일부 테넌트는 이전 리모트 버전(롤아웃이 완료될 때까지)을 볼 수 있습니다.</li><li> 모든 75+ Remove-Cs \<Name\> Policy cmdlet의 현대화된 버전을 릴리스합니다. 이러한 작업은 해당 리모팅과 유사하게 작동할 것으로 예상됩니다. 최신 버전은 점진적으로 롤아웃되어 일부 테넌트는 이전 리모트 버전(롤아웃이 완료될 때까지)을 볼 수 있습니다.</li><li> [제거 \| 설정]-CsPhoneNumberAssignment cmdlet을 릴리스합니다. 이러한 cmdlet은 점진적으로 롤아웃될 수 있으므로 일부 테넌트는 (롤아웃이 완료될 때까지) 사용할 수 있는 기존 cmdlet을 참조하는 오류 메시지가 표시됩니다.</li><li> [새로 \| 설정]-CsTeamsEmergencyCallingPolicy cmdlet에 대한 새 매개 변수 EnhancedEmergencyServiceDisclaimer를 릴리스합니다.<li> 릴리스 [제거 \| \| 추가]-TeamChannelUser cmdlet.</li><li> cmdlet Export-CsOnlineAudioFile 릴리스합니다.</li><li> [가져오기 제거 \| \| 가져오기]-CsOnlineAudioFile cmdlet에 대한 오류 처리를 수정합니다.</li><li>오류 처리에 Get-Team 수정합니다. 팀 데이터를 페치하는 데 실패하면 오류 메시지를 출력합니다.</li><li>Connect-MicrosoftTeams 수정 - AccessTokens 만료 시간의 차이가 증가합니다.</li>
| 2021년 11월 | [2.6.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.2-preview) |<li>모든 75+ Grant-Cs Policy cmdlet(모든 매개 변수 집합)의 \<Name\> 현대화된 버전을 릴리스합니다. 이러한 리모트는 해당 리모트와 유사하게 작동할 것으로 예상됩니다. 최신 버전은 점진적으로 롤아웃됩니다. 플라이트되지 않은 테넌트는 이전 리모트 버전을 볼 수 있습니다.</li><li>모든 75+ Remove-Cs \<Name\> Policy cmdlet의 현대화된 버전을 릴리스합니다. 이러한 리모트는 해당 리모트와 유사하게 작동할 것으로 예상됩니다. 최신 버전은 점진적으로 롤아웃됩니다. 플라이트되지 않은 테넌트는 이전 리모트 버전을 볼 수 있습니다.</li><li>cmdlet Set-CsUserCallingSettings 릴리스합니다. 이 cmdlet은 결국 GA 모듈에서 릴리스됩니다. 미리 보기 모듈에서 평가판 버전을 릴리스합니다.</li><li>cmdlet Export-CsOnlineAudioFile 릴리스합니다.</li><li>[가져오기 제거 \| \| 가져오기]-CsOnlineAudioFile cmdlet에 대한 오류 처리를 수정합니다.</li>
| 2021년 10월 | [2.6.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.1-preview) |<li>[제거 \| 설정]-CsPhoneNumberAssignment cmdlet을 릴리스합니다. 이러한 cmdlet은 점진적으로 롤아웃됩니다. 따라서 일부 테넌트는 사용할 수 있는 기존 cmdlet을 참조하는 오류 메시지가 표시됩니다(롤아웃이 완료될 때까지).</li><li>릴리스 Get-CsOnlineTelephoneNumberCountry 및 Get-CsOnlineTelephoneNumberType cmdlet입니다.</li><li>[새로 \| 설정]-CsTeamsEmergencyCallingPolicy cmdlet에 대한 새 매개 변수 EnhancedEmergencyServiceDisclaimer를 릴리스합니다.</li><li>cmdlet Get-CsUserCallingSettings 릴리스합니다. 이 cmdlet은 결국 GA 모듈에서 릴리스됩니다. 미리 보기 모듈에서 평가판 버전을 릴리스합니다.</li>
| 2021년 9월 | [2.6.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.6.0) |<li>다른 사용자 지정 PowerShell 모듈의 중첩된 모듈을 만든 경우 MicrosoftTeams 모듈 보기가 실패한 버그를 수정합니다. 이제 다른 모듈의 중첩된 모듈인 경우에도 MicrosoftTeams cmdlet을 사용할 수 있습니다.</li><li>릴리스 \| [새 전체 지우기]-CsOnlineTelephoneNumberOrder \| \| cmdlet.</li><li>릴리스 Get-CsOnlineTelephoneNumberCountry 및 Get-CsOnlineTelephoneNumberType cmdlet입니다.</li><li>이러한 cmdlet에 대한 새 매개 변수를 릴리스합니다. Get-CsOnlineApplicationInstance, New-CsExternalAccessPolicy, New-CsTeamsAppSetupPolicy, New-CsTeamsCallParkPolicy, New-CsTeamsMessagingPolicy, Set-CsTeamsAppSetupPolicy, Set-CsTeamsCallParkPolicy, Set-CsTeamsGuestMessagingConfiguration, Set-CsTeamsMeetingPolicy, Set-CsExternalAccessPolicy, Set-CsTeamsCallingPolicy.</li><li>잘못된 로그인 시도 후 Connect-MicrosoftTeams 로그인을 다시 시도할 때 발생한 오류를 수정합니다.</li><li>각 새 버전에 대해 PowerShell 갤러리에서 모듈의 릴리스 정보를 사용할 수 있도록 업데이트합니다.</li>
| 2021년 9월 | [2.5.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.2-preview) |<li>참고: 이 버전부터는 릴리스 정보의 가용성 지연을 줄이기 위해 모듈 자체와 함께 PowerShell 갤러리에도 릴리스 노트가 게시됩니다.</li><li>릴리스 [새 제거 부여 \| \| \| \| 시작]-CsTeamsEnhancedEncryptionPolicy cmdlet.</li><li>[새 제거 \| \| \| 설정]-CsTenantBlockedNumberExceptionPattern cmdlet을 제거합니다.</li><li>다른 사용자 지정 PowerShell Microsoft Teams 중첩된 모듈을 만든 경우 Microsoft Teams 모듈 보기가 실패한 버그를 수정합니다. 이제 Microsoft Teams 모듈의 중첩된 모듈인 경우에도 cmdlet을 사용할 수 있습니다.</li><li>릴리스 \| [새 전체 지우기]-CsOnlineTelephoneNumberOrder \| \| cmdlet.</li><li>릴리스 Get-CsOnlineTelephoneNumberCountry 및 Get-CsOnlineTelephoneNumberType cmdlet입니다.</li><li>잘못된 로그인 시도 후에 Connect-MicrosoftTeams 다시 시도할 때 발생한 오류를 수정합니다.</li><li>개인 Add-TeamChannelUser Remove-TeamChannelUser 장애 조치(fail)를 수정합니다.</li>
| 2021년 8월 | [2.5.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.1) |<li>이제 액세스 토큰 Connect-MicrosoftTeams 각 리소스별 토큰에 대한 별도의 매개 변수 대신 통합 토큰 배열을 사용합니다. 자세한 내용은 여기에서 찾을 [수 있습니다. 커넥트-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams).</li><li>Cloudshell에서 Connect-MicrosoftTeams 대화형 로그인 오류가 해결되었습니다. 이제 다시 인증하라는 메시지를 표시하는 대신 사용자의 로그인 ID를 사용하는 것이 기본값입니다.</li><li>TeamsUnasignedNumberTreatment cmdlet을 사용할 수 있습니다.</li><li>Get-CsOnlineDialInConferencingBridge 및 Set-CsOnlineDialInConferencingBridge cmdlet이 이전 구현에서 새 API로 마이그레이션됩니다.</li><li>최신 버전의 Get-CsTenant 및 Get-CsOnlineUser (-identity 매개 변수만 사용)가 릴리스되었습니다. 더 이상 사용 안 하게 된 속성을 내보 내지 못하고 리모트하는 속성과 비교하여 서식이 변경되었습니다.</li><li>참고: New-Team 업데이트가 2.5.0에서 되버렸다가 이전 버전이 제공되어 변경 내용이 중단되지 않도록 합니다.</li>|
| 2021년 7월 | [2.4.1-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.1-preview) |<li>이제 사용 가능한 cmdlet 변경을 부여합니다.</li><li>새 음성 관련 cmdlet이 릴리스됩니다.</li><li>-Cs* cmdlet에 대한 인증서 지문 인증 제거.</li><li>모든 cmdlet의 파일 로깅에 대한 로깅 수정.</li><li>*TeamChannelUser cmdlet에 대한 문제를 해결합니다.</li>|
| 2021년 6월 | [2.4.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) |<li>Get-CsTenant의 최신 버전만 미리 Get-CsOnlineUser(-identity 매개 변수만 사용), Get-CsOnlineDialInConferencingLanguagesSupported 및 Import-CsOnlineAudioFile.</li><li>최신 버전의 Get-CsOnlineDialInConferencingLanguagesSupported 및 Import-CsOnlineAudioFile 리모팅 버전과 유사/동일하게 작동할 것으로 예상됩니다.</li><li>최신 버전의 Get-CsTenant 및 Get-CsOnlineUser (-identity 매개 변수를 사용하여 실행할 때) 사용되지 않는 속성을 내보냅니다.</li><li>최신 버전의 Get-CsTenant 및 Get-CsOnlineUser (-identity 매개 변수를 사용하여 실행할 때) 리모트 카운터 파트와 비교할 때 서식이 일부 변경됩니다.</li><li>릴리스 [새 제거 부여 \| \| \| \| 시작]-CsTeamsAudioConferencingPolicy cmdlet.</li><li>릴리스 Get-CsOnlineAudioFile 및 Remove-CsOnlineAudioFile cmdlet입니다.</li><li>Set-TeamTargetingHierarchy, Remove-TeamTargetingHierarchy, Get-TeamTargetingHierarchyStatus 고객에 GCC 있습니다.</li><li>명령에서 호출한 엔드포인트를 Get-TeamTargetingHierarchyStatus 수정합니다.</li>|
| 2021년 5월 | [2.3.2-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>커넥트-MicrosoftTeams에서 AccessToken 로그인을 지원합니다. 토큰 배열을 허용하는 -AccessTokens 매개 변수가 추가되었습니다. AccessTokens 매개 변수를 Teams MSGraph 및 Teams 리소스 토큰이 필요합니다.</li><li>AadAccessToken 및 MsAccessToken 매개 변수를 제거했습니다.</li>|
| 2021년 5월 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>에서 업데이트합니다. NETCore 2.1~3.1</li><li>사용자 및 그룹에 대한 다중 지역 지역을 얻을 수 있는 cmdlet이 추가되었습니다.</li><li>-AccountId를 사용하여 통합된 windows 인증에 대한 Connect-MicrosoftTeams</li><li>TeamsCallHoldPolicy cmdlet을 사용할 수 있습니다.</li><li>여러 명령의 입력 매개 변수 및 출력 형식 업데이트</li><li>명령을 리모트하는 동안 대기 시간 문제가 해결됩니다.</li><li>GA 사용자 지정 패키지 기능</li>|
| 2021년 4월 | [2.2.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>-accountId를 Windows-MicrosoftTeams와 함께 -accountId를 사용하는 통합 커넥트 수정합니다.</li><li>사용자에게 보낼 수 있는 전체 변경 알림 이벤트에 대한 세부 정보를 얻을 수 있는 cmdlet이 추가되었습니다.</li><li>사용자 및 그룹에 대한 다중 지역 지역을 얻을 수 있도록 cmdlet을 추가했습니다.</li><li>TeamsEnvironment 이름에 전달된 값의 처리는 대소문자 구분이 중요했습니다. 이 수정되었습니다.</li><li>단위 테스트를 용이하게 하기 위해 모듈 내의 원격 세션 관리의 주요 리포터입니다. 테넌트 관리자에 대한 기능 변경은 없습니다.</li>|
| 2021년 4월 | [2.1.0-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>일부 리모트 cmdlet의 출력 서식이 수정되었습니다(예: Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMessagingPolicy 등).</li><li>정책 관리 cmdlet의 업데이트된 매개 변수 목록입니다.</li>|
| 2021년 3월 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>인증 권한 부여에 MSAL & 사용</li> <li>Connect-MicrosoftTeams 모든 cmdlet의 진입점입니다.</li><li>New-csOnlineSession을 더 이상 사용할 수 없습니다. 이 는 커넥트-MicrosoftTeams로 대체됩니다.</li><li>Enable-csonlinesessionforreconnection은 더 이상 필요하지 않습니다. 이 기능은 기본적으로 PowerShell 모듈에서 Teams 구현됩니다.</li> <li>리포터된 정책 패키지 cmdlet 및 그룹 패키지 할당 추가</li><li>cmdlet에 대한 Get-Team 향상된 기능</li> <li>기존 cmdlet에 대한 향상된 로깅 및 디버깅 옵션 </li> <li>템플릿 관리 cmdlet 추가</li> <li>New-CsOnlineSession</li>|
| 2021년 2월 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>템플릿 관리 cmdlet 추가</li><li>cmdlet에 대한 Mezzo 및 일괄 처리 Get-Team 향상</li> <li>기존 cmdlet에 대한 향상된 로깅 및 디버깅 옵션 </li> <li>리포터된 정책 패키지 cmdlet</li>|
| 2020년 12월 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>재시도 및 절전 기간이 증가한 New-team cmdlet 업데이트</li>|
| 2020년 12월 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>온라인 비즈니스용 Skype 업데이트</li><li>중복 프롬프트에 대한 Connect-Microsoft Teams</li>|
| 2020년 11월 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>사용자 지정 정책 패키지 cmdlet 추가</li><li>대상 계층 구조 업로드 명령에 대한 수정</li>|
| 2020년 11월 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>인증 권한 부여에 MSAL & 사용</li><li>리포터된 정책 패키지 cmdlet 및 그룹 패키지 할당 추가</li><li>비동기 모델을 사용하기 위해 리포터링된 대상 지정 계층 구조 업로드 명령</li> <li>초기 인증 중에 -credential 매개 변수를 사용하지 않는 경우 사용자에게 두 번 메시지가 표시됩니다. 사용자는 중복 프롬프트를 방지하기 위해 -credential 매개 변수를 사용하여 자격 증명을 전달할 수 있습니다. 이 동작은 다음 릴리스에서 해결됩니다.</li> |
| 2020년 9월 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>비즈니스용 Skype 커넥터 통합</li> |
| 2020년 9월 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>비즈니스용 Skype 커넥터 통합</li> |
| 2020년 7월 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>그룹 [정책 할당 cmdlet 추가](./assign-policies-users-and-groups.md#assign-a-policy-to-a-group)</li> |
| 2020년 6월 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>비즈니스용 Skype 커넥터 통합<li>Get-Team 최적화<li>향상된 안정성</li> |
| 2020년 6월 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Cmdlet 미리 로드 추가<li>.NET Framework 최적화</li>   |
| 2020년 4월 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode 및 어셈블리 서명<li>추가된 Get-CsPolicyPackage<li>추가된 Get-CsUserPolicyPackage<li>추가된 Get-CsUserPolicyPackageRecommendation<li>추가된 Grant-CsUserPolicyPackage<li>추가된 New-CsBatchPolicyPackageAssignmentOperation<li>추가된 Set-TeamArchivedState<li>추가된 Set-TeamPicture<li>제거된 Get-TeamHelp</li>  |
| 2020년 3월 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>추가된 New-CsBatchPolicyAssignmentOperation</li> |
| 2020년 2월 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team 최적화</li>  |

## <a name="related-topics"></a>관련 항목

[Teams PowerShell 개요](teams-powershell-overview.md)

[PowerShell Teams 설치](teams-powershell-install.md)

[PowerShell을 Teams Teams 관리](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 참조](/powershell/teams/)

[비즈니스용 Skype cmdlet 참조](/powershell/skype/intro)
