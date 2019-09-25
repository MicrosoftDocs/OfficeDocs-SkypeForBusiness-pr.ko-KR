---
title: Microsoft 팀에서 StaffHub 팀을 교대으로 이동
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft 팀에서 Microsoft StaffHub 팀 및 일정 데이터를 이동 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bf9776dbf5a5992354f542436b4904d53d58508
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142048"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Microsoft 팀에서 Microsoft StaffHub 팀을 교대으로 옮기기

> [!IMPORTANT]
> 2019 년 10 월 1 일에 유효 합니다. Microsoft StaffHub는 곧 종료 됩니다. Microsoft 팀에 StaffHub 접근 권한 값을 구축 하 고 있습니다. 현재 팀에는 일정 관리를 위해 교대 근무 앱이 포함 되어 있으며 추가 기능이 시간에 따라 롤아웃 됩니다. StaffHub는 2019 년 10 월 1 일에 모든 사용자의 작동이 중지 됩니다. StaffHub를 열려고 하는 모든 사용자에 게 팀을 다운로드 하도록 지시 하는 메시지가 표시 됩니다. 자세한 내용은 [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)을 사용 중지 하세요.

팀에서 교대 근무 앱은 일정을 관리 하는 간단한 방법과 매일 수행 되는 교대 전환 및 취소의 일정 한 흐름을 제공 합니다. 팀 구성원은 일정에 액세스 하 고, 앱 및 장치에서 직접 정보를 이동 하 여 기본 설정을 지정 하 고, 일정을 관리 하 고, 휴가를 요청할 수 있습니다.

이 문서에서는 팀에서 조직의 StaffHub 팀 및 일정 데이터를 이동 하는 방법을 안내 합니다. 설명 합니다.

- [팀으로 이동 하는 방법에 대해 알아야 할 사항](#what-you-need-to-know-about-the-move-to-teams)
- [대비](#prepare)
- [파일럿 실시](#conduct-a-pilot) 
- [파일럿을 넘어서 모든 StaffHub 팀을 이동 하세요.](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [팀 사용량 모니터링](#monitor-teams-usage)
- [해결사](#troubleshooting)

하나 또는 두 개의 StaffHub 팀이 있는 중소기업이 고 수백 StaffHub 팀이 있는 대기업에 있든 관계 없이, 팀으로 전환 하는 데 도움이 되는 관리자 지침을 확인할 수 있습니다.

이 문서에 나와 있는 단계를 수행 하려면 전역 관리자 여야 합니다. 아직 수행 하지 않은 경우 [StaffHub 만료 FAQ](microsoft-staffhub-to-be-retired.md) 를 참조 하 여 질문에 대 한 답을 얻을 수 있습니다.

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>팀으로 이동 하는 방법에 대해 알아야 할 사항

### <a name="when-to-move-to-teams"></a>팀으로 이동 하는 경우

2019 년 10 월 1 일에 유효 하며, StaffHub가 만료 됩니다. 지금 팀 사용을 시작 하 고 조직의 팀과 사용자를 StaffHub에서 전환 하기 시작 하는 것이 좋습니다. StaffHub에서 가장 일반적으로 사용 되는 기능으로 일정 관리를 사용 하는 경우 팀에서 이동 앱을 진행 하는 것이 좋습니다.

### <a name="what-is-moved-to-teams"></a>팀으로 이동 하는 항목

StaffHub 팀을 이동 하면 팀 구성원, 사용자 세부 정보, 팀 일정 및 채팅 데이터가 팀으로 이동 됩니다. StaffHub 팀을 이동할 때 파일이 이동 되지 않습니다. StaffHub 팀에 팀으로 이동 하려는 파일이 포함 되어 있는 경우 별도의 단계로 파일을 이동 합니다.

모든 StaffHub 팀에는 해당 하는 Office 365 그룹이 필요 합니다. StaffHub 팀에 Office 365 그룹이 연결 되어 있지 않으면 전환을 지원할 수 있도록 자동으로 만들어집니다. 팀과 StaffHub 간의 팀 및 그룹 명명 차이로 인해 팀에 다른 팀 이름이 표시 될 수 있습니다.

StaffHub에서 팀으로 전환 하는 동안 사용자는 더 이상 StaffHub에서 해당 일정에 액세스할 수 없으며 팀에서 이동 하도록 리디렉션됩니다. 중단을 최소화 하 고 사용자가 팀을 채택 하 고 탐색 하도록 하는 것을 권장 하기 위해 조직에서이 변경 내용을 알릴 것을 권장 합니다. Azure AD Premium을 사용 하는 경우 [보고서를 실행](run-report-to-show-staffhub-usage.md) 하 여 조직의 StaffHub 사용자 중 해당 변경 사항에 대해 알고 있어야 하는 목록을 가져올 수 있습니다.  

StaffHub 팀을 팀으로 이동한 후에는 롤백 옵션이 없습니다.

### <a name="user-experience-when-you-move-a-team"></a>팀을 이동할 때의 사용자 환경

팀이 StaffHub에서 전환 되는 경우 사용자에 대 한 가동 중지 (가능한 경우 두 번째이 하)는 거의 없습니다. 사용자는 팀으로 이동이 완료 될 때까지 StaffHub를 계속 사용할 수 있습니다. 이동이 완료 되 면 팀 구성원은 팀 일정에 액세스 하기 위해 팀의 교대 근무를 사용 해야 한다는 것을 알리는 메시지를 볼 수 있습니다. 다음은 StaffHub 팀이 팀으로 이동한 후 사용자에 게 StaffHub에 표시 되는 메시지의 예입니다.

![사용자에 게 표시 되는 메시지의 예입니다.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "StaffHub 팀이 팀으로 이동한 후 사용자가 StaffHub에 표시 하는 메시지의 예")

## <a name="prepare"></a>대비

팀으로 이동 하기 위해 준비 하는 방법은 다음과 같습니다.

### <a name="check-that-prerequisites-are-met"></a>전제 조건이 충족 되는지 확인

StaffHub 팀을 팀으로 이동 하기 전에 다음을 확인 하세요.

- 로그인 한 사용자는 전역 관리자입니다.
- 팀은 테 넌 트의 모든 사용자에 대해 사용 하도록 설정 됩니다.
- 테 넌 트에서 Office 365 그룹 만들기를 사용 하도록 설정 합니다.
- StaffHub teamId가 유효 합니다.
- StaffHub 팀은 구성원을 포함 합니다.
- 모든 StaffHub 팀 구성원은 Azure AD 계정에 연결 됩니다.

이러한 선행 조건이 충족 되지 않으면 이동 요청이 실패 합니다.

### <a name="assign-teams-licenses"></a>팀 라이선스 할당

각 사용자는 [적격 요금제](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) 에서 활성 Microsoft 365 또는 Office 365 라이선스를 보유 하 고 있어야 하며 팀 라이선스를 할당 받아야 합니다. 사용자에 게 팀 라이선스를 할당 하면 팀에 액세스할 수 있습니다.

Microsoft 365 관리 센터에서 팀 라이선스를 관리 합니다. 자세히 알아보려면 [팀에 대 한 사용자 액세스 관리](../../user-access.md)를 참조 하세요.

> [!NOTE]
> 조직에서 비즈니스용 Skype를 사용 하는 경우 모든 사용자를 팀으로 이동할 준비가 되지 않은 경우, 팀을 비즈니스용 Skype와 함께 실행할 수 있는 Firstline Worker에 대 한 팀을 사용 하도록 설정할 수 있습니다. *아일랜드*라는이 공존 모드에서는 각 클라이언트 앱이 별도의 솔루션으로 작동 합니다. 자세한 내용은 [비즈니스용 Skype 공존 및 상호 운용성에 대해 팀 이해](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)를 참조 하세요.

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a>StaffHub PowerShell 모듈의 시험판 버전을 설치 합니다.

아직 설치 하지 않은 경우 [StaffHub PowerShell 모듈의 시험판 버전을 설치](install-the-staffhub-powershell-module.md)합니다. 

StaffHub 팀을 팀으로 이동 하려면 시험판 버전의 모듈을 설치 해야 합니다.

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a>StaffHub 팀 구성원에 대 한 Azure AD 계정 연결

각 StaffHub 팀 구성원은 Azure AD (Azure Active Directory) 계정에 연결 되어 있어야 합니다. 다음 시나리오 중 하나가 적용 되는 경우 조직의 사용자는 Azure AD 계정에 연결 되지 않습니다.

- 팀 소유자가 Azure AD 계정이 없는 사용자를 추가 했습니다.
- 팀 소유자가 사용자를 StaffHub 팀에 초대 했으며 해당 사용자가 초대를 수락 하지 않았습니다.

이러한 사용자에 대 한 Azure AD 계정을 연결할 수 있습니다.  방법은 다음과 같습니다.

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-linked-to-an-azure-ad-account"></a>Azure AD 계정에 연결 되지 않은 팀 구성원이 있는 StaffHub 팀의 모든 사용자 목록 가져오기

다음을 실행 합니다.
```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="link-the-account"></a>계정 연결

다음 중 하나를 수행 합니다.

- 계정을 변환 하 고 연결 합니다.

  StaffHub 팀 소유자 및 관리자는 사용자의 전자 메일 주소를 StaffHub 팀 설정 페이지에서 유효한 UPN으로 변경 하 여 비활성 계정을 변환 하 고 StaffHub의 Azure AD 계정에 연결할 수 있습니다.

- 연결 되지 않은 계정을 제거한 다음 UPN을 사용 하 여 계정을 다시 추가 합니다.
    1. [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) cmdlet을 실행 하 여 StaffHub 팀에서 프로 비전 되지 않은 계정을 제거 합니다.
    2. [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) cmdlet을 실행 하 여 UPN을 사용 하 여 StaffHub 팀에 계정을 다시 추가 합니다.

- 연결이 연결 되지 않은 사용자 계정을 제거 합니다. 사용자 계정이 더 이상 필요 하지 않은 경우이 옵션을 사용 합니다.

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>사용자에 게 FirstlineWorker 앱 설정 정책 할당

팀에는 조직의 Firstline 작업자에 게 가장 중요 한 앱을 강조 표시 하도록 팀을 사용자 지정 하는 데 사용할 수 있는 기본 제공 FirstlineWorker 앱 설정 정책이 포함 되어 있습니다. 이 정책을 사용자에 게 할당 하면, 정책의 앱이 팀의 앱 표시줄에 고정 되므로 빠르고 쉽게 액세스할 수 있습니다. 팀에 추가 된 다른 앱은 앱 표시줄에서 다음을 클릭 하 여 찾을 수 **있습니다. **팀 데스크톱 및 웹 클라이언트의 앱이 더 있고 팀 모바일 클라이언트에서 위로 살짝 밀어 보세요. 기본적으로 FirstlineWorker 앱 설정 정책에는 활동, 교대, 채팅 및 통화 앱이 포함 됩니다.

FirstlineWorker 앱 설치 정책을 사용자에 게 할당 하는 방법에 대 한 단계는 [FirstlineWorker 앱 설정 정책을 사용 하 여 팀에 고정](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)을 참조 하세요. 정책을 할당 하면 적용 되는 데 최대 24 시간이 걸릴 수 있습니다.

StaffHub 팀 이나 사용자를 팀으로 이동 하기 전에 적어도 일주일에이 단계를 완료 하는 것이 좋습니다. 팀에 속한 사용자는 교대 근무 앱을 보고 액세스할 수 있는지 확인 합니다.

사용자 지정 앱 설정 정책을 만들고 전역 앱 설정 정책에서 설정을 편집할 수도 있습니다. 자세한 내용은 [팀에서 앱 설치 정책 관리](../../teams-app-setup-policies.md)를 참고 하세요.

### <a name="onboard-users-to-teams"></a>팀에 대 한 온보드 사용자

온 보 딩 전략의 일부로 팀에 익숙해질 수 있도록 사용자에 게 교육 및 지침을 제공 합니다. 팀 클라이언트, 교육 및 지원을 받을 위치를 알 수 있도록 다음 리소스를 사용자와 공유 합니다.

- [팀 웹 클라이언트](https://teams.microsoft.com)
- [데스크톱 및 모바일 클라이언트 다운로드 링크](https://teams.microsoft.com/downloads)
- [팀 교육 비디오](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [팀 도움말 문서](https://support.office.com/teams)

팀 및 운전 팀 채택을 배포 하는 방법에 대 한 지침은 팀을 롤 포워드 하 고 [팀을 채택](../../adopt-microsoft-teams-landing-page.md)하 [는 방법을](../../How-to-roll-out-teams.md) 참조 하세요.

## <a name="conduct-a-pilot"></a>파일럿 실시

최초 사용자의 선택 그룹을 위해 2 개 또는 3 개의 StaffHub 팀부터 시작 하는 것이 좋습니다. 파일럿을 실행 하면 전환 계획을 개선 하 고 조직의 모든 StaffHub 팀을 팀으로 이동할 준비가 되어 있는지 확인할 수 있습니다. 또한 조직에서 채택을 간편 하 게 할 수 있는 챔피언 식별 합니다. 단계별 접근 방법이 필요 하지 않은 중소 기업 이라면이 섹션의 단계를 StaffHub에서 팀으로 전환 하는 것이 필요할 수 있습니다.

### <a name="identify-pilot-teams"></a>파일럿 팀 식별

2 명 또는 세 명의 파일럿 팀을 확인 하세요. 모든 팀 구성원은 팀의 교대 근무를 사용 하 여 일정을 관리 하 고 서로와 통신 하 고 공동 작업 해야 합니다.

### <a name="identify-team-champions"></a>팀 챔피언 확인

파일럿 팀에서 챔피언를 식별 하 고 참여 하 여 evangelize 교대 근무를 지원 합니다. 팀 챔피언 자신의 학습이을 공유 하 여 팀 구성원에 게 지원 및 지침을 제공 하는 것에 대해 열정. 팀 챔피언 팀 소유자 또는 관리자가 될 수 있습니다.

팀 챔피언 모든 사람이 [팀 클라이언트를 확보](../../get-clients.md)하 고, 팀에 로그인 하 고, 일정을 교대에서 확인 하 고, 서로 채팅을 시작 하도록 시간을 설정 하는 것을 보장 해야 합니다. 이미 StaffHub에 익숙한 사용자는 이동 중에 빠르게 실행 됩니다. 또한 [도움말](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) 을 가리키면 추가 도움말을 볼 수 있습니다.

### <a name="move-a-staffhub-team"></a>StaffHub 팀 이동

이 단계를 사용 하 여 한 번에 한 StaffHub 팀을 이동 합니다. 파일럿 팀에이 접근 방법을 권장 합니다. 나중에 조직의 모든 StaffHub 팀을 이동할 준비가 되 면 여러 팀을 한 번에 이동 하는 방법에 대 한 단계에 대해 [StaffHub 팀 이동을](#move-your-staffhub-teams) 참조 하세요.

다음을 실행 하 여 StaffHub 팀을 이동 합니다.

```
Move-StaffHubTeam -TeamId <String>
```
예

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

다음은 StaffHub 팀을 팀으로 이동 하는 요청을 제출할 때 표시 되는 응답의 예입니다.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

이동 요청의 상태를 확인 하려면 다음을 실행 합니다.

```
Get-TeamMigrationJobStatus <String>
```
예

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

다음은 이동을 진행 하는 동안 받은 응답의 예입니다.

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>StaffHub 팀에서 팀으로 파일 이동

이 단계는 팀으로 이동한 StaffHub 팀에 게 팀으로 이동 하려는 파일이 있는 경우에만 적용 됩니다. SharePoint Online 또는 PowerShell을 사용 하 여 파일을 직접 이동할 수 있습니다.

#### <a name="in-sharepoint-online"></a>SharePoint Online에서

[SharePoint Online에서 파일을 이동 하는 방법](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)에 대해 알아봅니다.

#### <a name="using-powershell"></a>PowerShell 사용

아직 없는 경우 [SharePoint Online 관리 셸을](https://www.microsoft.com/download/details.aspx?id=35588)다운로드 하 여 설치 합니다. 파일을 이동 하는 데 필요한 cmdlet이 포함 되어 있습니다.  

SharePoint Online 팀 사이트에 연결 하려면 [PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) cmdlet을 사용 합니다.

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

StaffHub에서 팀으로 이동 하려는 각 파일에 대해 [move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) cmdlet을 사용 하 여 파일을 이동 합니다.

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

여러 파일을 이동 하려면 파일을 순환 하면서 루프에서 두 번째 명령을 실행 합니다. 세션이 활성 상태를 유지 하는 경우 첫 번째 명령을 반복할 필요는 없습니다.

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>파일럿을 넘어서 모든 StaffHub 팀을 이동 하세요.

### <a name="raise-awareness"></a>인식 발생

파일럿 팀으로 이동 하 고 조직의 StaffHub 팀을 팀으로 이동할 준비가 되 면 먼저 조직 전반에 변경 내용을 전달 하는 것이 중요 합니다. 이동 및 팀으로 전환에 대 한 단어를 분산 하 여 인식, 흥미로운 생성, 드라이브 채택을 발생 시킵니다.

### <a name="move-your-staffhub-teams"></a>StaffHub 팀 이동

StaffHub 팀을 대량으로 이동 하려면 다음 단계를 사용 하세요. 조직의 StaffHub 팀을 모두 이동 하거나 특정 StaffHub 팀을 이동 하도록 선택할 수 있습니다. StaffHub 팀을 한 번에 하나씩 이동 하려면 [StaffHub 팀 이동을](#move-a-staffhub-team)참조 하세요.

#### <a name="move-all-staffhub-teams"></a>모든 StaffHub 팀 이동

다음을 실행 하 여 조직의 모든 StaffHub 팀 목록을 가져옵니다.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

모든 팀을 이동 하려면 다음을 실행 합니다.

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

다음은 응답의 예입니다.

이미 팀으로 이동 하거나 팀에 이미 있는 팀의 경우, 해당 팀을 이동 하기 위해 작업을 제출할 필요가 없으므로 jobId는 "null"이 됩니다.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>특정 StaffHub 팀 이동

조직의 모든 StaffHub 팀 Id 목록을 가져오려면 다음을 실행 합니다.

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

이전에 실행 한 `Get-StaffHubteamsForTenant` cmdlet에서 반환 된 결과에서 이동 하려는 팀 id를 선택한 다음 CSV (쉼표로 구분 된 값) 파일에 추가 합니다.

다음은 CSV 파일의 서식을 지정 하는 방법의 예입니다.

|I  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

CSV 파일을 만든 후 다음을 실행 하 여 CSV 파일에서 지정한 팀을 이동 합니다.

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>StaffHub 팀이 팀으로 이동 했는지 확인

다음을 실행 하 여 조직에서 모든 팀의 변화에 대 한 목록을 가져옵니다. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>StaffHub 팀에서 팀으로 파일 이동

이동한 StaffHub 팀에 팀으로 이동 하려는 파일이 포함 되어 있는 경우 [StaffHub 팀에서 팀으로 파일 이동을](#move-files-from-a-staffhub-team-to-teams)참조 하세요.

## <a name="monitor-teams-usage"></a>팀 사용량 모니터링

사용 현황 보고서를 통해 사용 패턴을 보다 잘 이해 하 고 조직의 교육 및 통신 작업에 대 한 우선 순위를 지정할 수 있습니다. 전체 팀 사용, 팀에서 사용자가 수행 하는 작업 유형, 사용자가 팀에 연결 하는 방법 등에 대 한 보고서를 실행할 수 있습니다. 자세한 내용은 [microsoft 365 관리 센터의](../../teams-activity-reports.md) [microsoft 팀 관리 센터](../../teams-analytics-and-reports/teams-reporting-reference.md) 및 팀 활동 보고서에서 팀 보고를 참조 하세요.

## <a name="troubleshooting"></a>해결사

**파일을 StaffHub에서 팀으로 이동 하려고 하면 "사용 권한 거부 됨" 오류 메시지가 표시 됩니다.**

구성원이 아닌 개인 Office 365 그룹의 파일을 이동 하려는 경우이 문제가 발생할 수 있습니다. 이 경우 [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) cmdlet을 사용 하 여 자신을 StaffHub 팀에 추가한 다음 파일을 이동 합니다. 파일을 이동한 후 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) cmdlet을 사용 하 여 팀에서 자신을 제거 합니다. 

**파일을 StaffHub에서 팀으로 이동 하려고 하면 일반 폴더가 없다는 오류 메시지가 나타납니다.**

다음 명령을 실행 하 여 SharePoint에 일반 폴더를 추가한 다음 다시 시도 합니다.

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>관련 항목
- [Microsoft 팀을 배포 하는 방법](../../How-to-roll-out-teams.md)
- [Microsoft StaffHub 사용 중지](microsoft-staffhub-to-be-retired.md)
- [Microsoft 팀에서 조직의 교대 근무 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub PowerShell 참조](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
