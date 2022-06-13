---
title: Microsoft Teams 일선 근로자를 위한 대규모 팀 배포
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 최전방 작업자를 위해 대규모로 팀을 배포하는 방법을 알아봅니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 561eaf310201b99ada9cce4dde49746d58d77088
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046027"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Microsoft Teams 일선 근로자를 위한 대규모 팀 배포

> [!NOTE]
> 이 기능은 현재 프라이빗 미리 보기로 제공됩니다. 프라이빗 미리 보기에 참여하려면 [dscale@microsoft.com](mailto:dscale@microsoft.com) 문의하세요.

## <a name="overview"></a>개요
 
조직에는 다양한 매장, 위치 및 역할에 걸쳐 분산된 일선 인력 간의 커뮤니케이션 및 협업을 촉진하는 데 사용하는 팀이 많을 수 있습니다. 현재 이러한 팀과 사용자를 대규모로 배포, 설정 및 관리하는 쉬운 솔루션은 없습니다.

관리자가 대규모로 팀을 배포하고 관리할 수 있는 솔루션을 빌드하고 있습니다.

다음은 현재 많은 수의 팀을 한 번에 만들고 관리하는 데 사용할 수 있는 기능과 가까운 미래를 위해 계획하고 있는 기능에 대한 개요입니다.

||현재 사용 가능 |2022년 말  |
|---------|---------|---------|
|**일괄 처리당 만들 수 있는 팀 수**|최대 100 |최대 500|
|**팀당 추가할 수 있는 사용자 수**|최대 25개|최대 25개|

대규모로 팀을 배포하면 다음을 수행할 수 있습니다.

- 미리 빌드된 템플릿 또는 사용자 지정 템플릿을 사용하여 팀을 만듭니다.
- 소유자 또는 구성원으로 팀에 사용자를 추가합니다.
- 기존 팀에서 사용자를 추가하거나 제거하여 대규모로 팀을 관리합니다.
- 완료, 상태 및 오류(있는 경우)를 포함하여 전자 메일을 통해 알림을 받습니다. 배포하는 팀의 각 배치 상태에 대해 최대 5명까지 알릴 수 있습니다. 팀 소유자와 구성원은 팀에 추가될 때 자동으로 알림을 받습니다.

## <a name="how-to-deploy-teams-at-scale"></a>대규모로 팀을 배포하는 방법

> [!NOTE]
> 팀을 배포하기 전에 모든 팀 소유자에게 Teams 라이선스가 있는지 확인합니다.

다음 단계에 따라 한 번에 많은 수의 팀을 배포합니다.

### <a name="step-1-prepare-your-csv-files"></a>1단계: CSV 파일 준비

배포하는 팀의 각 배치에 대해 두 개의 CSV 파일을 만들어야 합니다.

- **만드는 팀을 정의하는 CSV 파일입니다**. 이 파일에는 첫 번째 열부터 시작하여 다음 순서로 이러한 필수 열이 포함되어야 합니다.

    |열 이름  |설명  |
    |---------|---------|
    |**팀 이름**|팀의 이름입니다.|
    |**기존 팀 ID**|기존 팀에서 사용자를 추가하거나 제거하는 경우 팀의 팀 ID를 지정합니다.|
    |**가시성**|팀이 공개(조직의 모든 사용자가 참가할 수 있음) 또는 비공개(사용자가 참가하려면 팀 소유자의 승인이 필요)인지 여부입니다. 옵션은 **공용** 및 **비공개** 입니다.|
    |**팀 템플릿 ID**|미리 빌드된 템플릿 또는 사용자 지정 템플릿에서 팀을 만드는 경우 팀 템플릿 ID를 지정합니다. 미리 빌드된 [팀 템플릿 및 ID 목록은 Teams 관리 센터에서](get-started-with-teams-templates-in-the-admin-console.md) 팀 템플릿으로 시작 참조하세요. 표준 기본 팀 템플릿을 사용하려면 비워 둡니다.|

- **각 팀에 추가하는 사용자를 매핑하는 CSV 파일** 입니다. 이 파일에는 첫 번째 열부터 시작하여 다음 순서로 이러한 필수 열이 포함되어야 합니다.

    |열 이름  |설명  |
    |---------|---------|
    |**사용자 전체 이름**|사용자의 표시 이름입니다.|
    |**사용자 UPN 또는 ID**|UPN(사용자 계정 이름) 또는 사용자의 ID입니다. 예를 들어 averyh@contoso.com.|
    |**팀 이름**|팀의 이름입니다.|
    |**ActionType**|팀에서 사용자를 추가하거나 제거하는지 여부입니다. 옵션은 **AddMember** 및 **RemoveMember입니다**.|
    |**소유자 또는 구성원**|사용자가 팀 소유자인지 또는 팀 구성원인지 여부입니다. 옵션은 **소유자** 및 **멤버입니다**.|

#### <a name="examples"></a>예제

다음 예제를 사용하여 CSV 파일을 만들 수 있습니다. 여기서는 파일, Teams.csv 및 Users.csv 이름을 지정했습니다.

**Teams.csv**

|팀 이름|기존 팀 ID|가시성|팀 템플릿 ID|
|---------|---------|---------|---------|
|Contoso Microsoft Store 1||공용|com.microsoft.teams.template.retailStore|
|Contoso Microsoft Store 2||공용|com.microsoft.teams.template.retailStore|
|Contoso Microsoft Store 3||공용|com.microsoft.teams.template.retailStore|
|Contoso Microsoft Store 4||공용|com.microsoft.teams.template.retailStore|
|Contoso Microsoft Store 5||공용|com.microsoft.teams.template.ManageAProject|
|Contoso Microsoft Store 6||공용|com.microsoft.teams.template.ManageAProject|
|Contoso Microsoft Store 7||공용||
|Contoso Microsoft Store 8||개인|com.microsoft.teams.template.OnboardEmployees|
|Contoso Microsoft Store 9||개인|com.microsoft.teams.template.OnboardEmployees|
|Contoso Microsoft Store 10||개인|com.microsoft.teams.template.OnboardEmployees|

**Users.csv**

|사용자 전체 이름 |사용자 UPN 또는 ID|팀 이름|ActionType|소유자 또는 구성원|
|---------|---------|---------|---------|---------|
|에이버리 하워드|averyh@contoso.com|Contoso Microsoft Store 1|AddMember|소유자|
|케이시 젠슨|caseyj@contoso.com|Contoso Microsoft Store 2|AddMember|소유자|
|제시 어윈|jessiei@contoso.com|Contoso Microsoft Store 3|AddMember|소유자|
|만지트 바티아|manjeetb@contoso.com|Contoso Microsoft Store 4|AddMember|소유자|
|미카엘라 리|mikaelal@contoso.com|Contoso Microsoft Store 5|AddMember|소유자|
|모건 코너스|morganc@contoso.com|Contoso Microsoft Store 6|AddMember|멤버|
|오스카 워드|oscarw@contoso.com|Contoso Microsoft Store 7|AddMember|멤버|
|르네 펠레티에|renep@contoso.com|Contoso Microsoft Store 8|AddMember|멤버|
|시드니 마토스|sydneym@contoso.com|Contoso Microsoft Store 9|AddMember|멤버|
|바이올렛 마르티네즈|violetm@contoso.com|Contoso Microsoft Store 10|AddMember|멤버|

### <a name="step-2-deploy-your-teams"></a>2단계: 팀 배포

이제 CSV 파일을 만들었으므로 환경을 설정하고 팀을 배포할 준비가 되었습니다.

cmdlet을 ```New-CsBatchTeamsDeployment``` 사용하여 만들 팀의 일괄 처리를 제출합니다. 오케스트레이션 ID는 각 일괄 처리에 대해 생성됩니다. 그런 다음 cmdlet을 ```Get-CsBatchTeamsDeployment``` 사용하여 각 일괄 처리의 진행률 및 상태를 추적할 수 있습니다.

1. PowerShell 버전 7 이상을 설치합니다. 단계별 지침은 [Windows PowerShell 설치를](/powershell/scripting/install/installing-powershell-on-windows) 참조하세요.
1. 관리자 모드에서 PowerShell을 실행합니다.
1. 다음을 실행하여 이전에 설치된 Teams PowerShell 모듈을 제거합니다.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    오류 메시지가 표시되면 이미 설정되어 있습니다. 다음 단계로 이동합니다.
1. [최신 버전의 Teams PowerShell 모듈을](https://www.powershellgallery.com/packages/MicrosoftTeams) 다운로드하여 설치합니다.

1. 다음을 실행하여 Teams 연결합니다.

    ```powershell
    Connect-MicrosoftTeams
    ```

    메시지가 표시되면 관리자 자격 증명을 사용하여 로그인합니다.

1. 다음을 실행하여 Teams PowerShell 모듈의 명령 목록을 가져옵니다.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    확인하여 ```New-CsBatchTeamsDeployment``` ```Get-CsBatchTeamsDeployment``` 나열합니다.

1. 다음을 실행하여 팀 배치를 배포합니다. 이 명령에서는 CSV 파일의 경로와 최대 5명의 받는 사람의 이메일 주소를 지정하여 이 배포에 대해 알립니다.

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "Your CSV file path" -UsersFilePath "Your CSV file path" -UsersToNotify "Email addresses" 
    ```

    예를 들면 다음과 같습니다.

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "C:\dscale\Teams.csv" -UsersFilePath "C:\dscale\Users.csv" -UsersToNotify "adminteams@contoso.com,adelev@contoso.com"
    ```

    받는 사람은 배포 상태에 대한 이메일 알림을 받게 됩니다. 전자 메일에는 제출한 일괄 처리에 대한 오케스트레이션 ID와 발생할 수 있는 모든 오류가 포함됩니다.

1. 다음을 실행하여 제출한 일괄 처리의 상태를 확인합니다.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>사용자 의견 보내기

여러분의 의견을 소중히 생각합니다. 유용성, 안정성, 성능&mdash;모두 환영합니다!

[dscale@microsoft.com 이메일을](mailto:dscale@microsoft.com) 보내 오케스트레이션 ID 및 오류 파일을 포함합니다(있는 경우).

## <a name="related-articles"></a>관련 기사

- [Teams PowerShell 개요](teams-powershell-overview.md)
