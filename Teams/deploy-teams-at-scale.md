---
title: Microsoft Teams에서 최전방 작업자를 위한 대규모 팀 배포
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
ms.openlocfilehash: 655e79e70945419c446dab3d721334a1a70b0e9e
ms.sourcegitcommit: d54217d3c339fe02f83d86efe50dabe67528a14c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2022
ms.locfileid: "65947235"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Microsoft Teams에서 최전방 작업자를 위한 대규모 팀 배포

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
- 완료, 상태 및 오류(있는 경우)를 포함하여 전자 메일을 통해 알림을 받습니다. 팀 소유자 및 구성원에게 알림이 표시됩니다.

## <a name="how-to-deploy-teams-at-scale"></a>대규모로 팀을 배포하는 방법

> [!NOTE]
> 팀을 배포하기 전에 모든 팀 소유자에게 Teams 라이선스가 있는지 확인합니다.

다음 단계에 따라 한 번에 많은 수의 팀을 배포합니다.

cmdlet을 ```New-CsBatchTeamsDeployment``` 사용하여 만들 팀의 일괄 처리를 제출합니다. 오케스트레이션 ID는 각 일괄 처리에 대해 생성됩니다. 그런 다음 cmdlet을 ```Get-CsBatchTeamsDeployment``` 사용하여 각 일괄 처리의 진행률 및 상태를 추적할 수 있습니다.

1. PowerShell 버전 7 이상을 설치합니다. 단계별 지침은 [Windows에 PowerShell 설치를 참조하세요](/powershell/scripting/install/installing-powershell-on-windows).
1. 관리자 모드에서 PowerShell을 실행합니다.
1. 다음을 실행하여 이전에 설치된 Teams PowerShell 모듈을 제거합니다.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    오류 메시지가 표시되면 이미 설정되어 있습니다. 다음 단계로 이동합니다.
1. [최신 버전의 Teams PowerShell 모듈을](https://www.powershellgallery.com/packages/MicrosoftTeams) 다운로드하여 설치합니다.

1. 다음을 실행하여 Teams에 연결합니다.

    ```powershell
    Connect-MicrosoftTeams
    ```

    메시지가 표시되면 관리자 자격 증명을 사용하여 로그인합니다.

1. 다음을 실행하여 Teams PowerShell 모듈의 명령 목록을 가져옵니다.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    확인하여 ```New-CsBatchTeamsDeployment``` ```Get-CsBatchTeamsDeployment``` 나열합니다.

1. 다음을 실행하여 팀 배치를 배포합니다. **UsersToNotify** 매개 변수에 최대 5개의 전자 메일 주소를 입력할 수 있습니다.

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "*Your file path*" -UsersFilePath "*Your file path*" -UsersToNotify *Email addresses* 
    ```

1. 다음을 실행하여 제출한 일괄 처리의 상태를 확인합니다.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>사용자 의견 보내기

여러분의 의견을 소중히 생각합니다. 유용성, 안정성, 성능&mdash;모두 환영합니다!

[dscale@microsoft.com 이메일을](mailto:dscale@microsoft.com) 보내 오케스트레이션 ID 및 오류 파일을 포함합니다(있는 경우).

## <a name="related-articles"></a>관련 기사

- [Teams PowerShell 개요](teams-powershell-overview.md)
