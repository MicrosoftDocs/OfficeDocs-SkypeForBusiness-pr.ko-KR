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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464668"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell 모듈 설치

> [!IMPORTANT]
> 2019 년 10 월 1 일에 유효 합니다. Microsoft StaffHub는 곧 종료 됩니다. Microsoft 팀에 StaffHub 접근 권한 값을 구축 하 고 있습니다. 현재 팀에는 일정 관리를 위해 교대 근무 앱이 포함 되어 있으며 추가 기능이 시간에 따라 롤아웃 됩니다. StaffHub는 2019 년 10 월 1 일에 모든 사용자의 작동이 중지 됩니다. StaffHub를 열려고 하는 모든 사용자에 게 팀을 다운로드 하도록 지시 하는 메시지가 표시 됩니다. 자세한 내용은 [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)을 사용 중지 하세요.  

이 문서의 단계를 사용 하 여 Microsoft StaffHub PowerShell 모듈을 설치 하 고 연결 합니다. PowerShell을 사용 하 여 StaffHub를 관리 하 고 StaffHub 팀을 Microsoft 팀으로 이동 하려면이이 필요 합니다.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell 모듈 설치

1. Windows PowerShell 3.0 이상을 관리자로 엽니다. 이렇게 하려면 **시작**을 클릭 하 고 **windows powershell**을 입력 한 다음 **windows powershell**을 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 선택 합니다.
    > [!NOTE]
    > 최신 버전의 Windows PowerShell을 얻으려면 [Windows Powershell 설치](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)를 참조 하세요. 
2. 다음을 실행 하 여 현재 안정적인 버전의 StaffHub PowerShell 모듈을 설치 합니다.

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    최신 버전을 설치 해야 하는 경우에만이 명령을 실행할 수 있는데,이는 현재 안정적인 버전 보다 더 instabilities 수 있습니다.`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`

     > [!NOTE]
     > 최신 버전을 더 instabilities 설치 하는 동안 오류가 표시 되는 경우 다음을 실행할 수 있습니다.`Install-Module PowershellGet -Force`

3. 다음과 같은 경고 메시지가 표시 될 수 있습니다.

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

을 `Y` 입력 하 `Enter`고을 클릭 합니다.
 
4. Windows PowerShell을 종료 합니다.

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Microsoft StaffHub PowerShell 모듈에 연결

1. 다음을 실행 합니다.

    ```
    Connect-StaffHub
    ```

2. 메시지가 표시 되 면 전역 관리자로 로그인 합니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft StaffHub PowerShell 참조](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [팀에서 Microsoft StaffHub 팀을 교대으로 옮기기](move-staffhub-teams-to-shifts-in-teams.md)
