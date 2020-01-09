---
title: StaffHub PowerShell 모듈 설치
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub PowerShell 모듈을 설치 하 고 연결 하는 방법을 알아봅니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 122a704df184619591f121f088162a045733cf4b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992133"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell 모듈 설치

> [!IMPORTANT]
> 2019 년 12 월 31 일에 효력을 StaffHub Microsoft는 곧 만료 됩니다. Microsoft 팀에 StaffHub 접근 권한 값을 구축 하 고 있습니다. 현재 팀에는 일정 관리를 위해 교대 근무 앱이 포함 되어 있으며 추가 기능이 시간에 따라 롤아웃 됩니다. StaffHub는 2019 년 12 월 31 일에 모든 사용자의 작동이 중지 됩니다. StaffHub를 열려고 하는 모든 사용자에 게 팀을 다운로드 하도록 지시 하는 메시지가 표시 됩니다. 자세한 내용은 [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)을 사용 중지 하세요.  

이 문서의 단계를 사용 하 여 Microsoft StaffHub PowerShell 모듈을 설치 하 고 연결 합니다. [StaffHub 팀을 팀으로 이동](move-staffhub-teams-to-shifts-in-teams.md)하려면이이 필요 합니다.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell 모듈 설치

1. [StaffHub PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftStaffHub)을 다운로드 합니다.
2. Windows PowerShell 3.0 이상을 관리자로 엽니다. 이렇게 하려면 **시작**을 클릭 하 고 **windows powershell**을 입력 한 다음 **windows powershell**을 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 선택 합니다.
    > [!NOTE]
    > 최신 버전의 Windows PowerShell을 얻으려면 [Windows Powershell 설치](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)를 참조 하세요.
3. 다음을 실행 합니다.

    ```PowerShell
    $ENV:PSModulePath
    ```
4. 출력에서 폴더 경로를 확인 하 고 다음 단계로 이동 하기 전에 경로의 모든 폴더가 컴퓨터에 있는지 확인 합니다. 폴더가 없는 경우 폴더를 만듭니다.
5. StaffHub PowerShell 모듈을 설치할 수 있도록 하려면 다음을 실행 합니다.

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. 다음을 실행 합니다. &lt;여기서&gt; path는 3 단계의 출력에서 경로입니다. 예를 들어 경로는 C:\Users\User1\Documents\WindowsPowerShell\Modules. 처럼 표시 될 것입니다.

    각 명령을 개별적으로 실행 해야 합니다.

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. Windows PowerShell을 종료 합니다.
8. Windows PowerShell 3.0 이상을 전역 관리자로 연 후 다음을 실행 합니다.

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell 모듈에 연결

1. 다음을 실행 합니다.

    ```PowerShell
    Connect-StaffHub
    ```

2. 메시지가 표시 되 면 전역 관리자로 로그인 합니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft StaffHub PowerShell 참조](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [Teams에서 Microsoft StaffHub 팀을 교대로 이동](move-staffhub-teams-to-shifts-in-teams.md)
