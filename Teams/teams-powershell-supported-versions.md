---
title: Teams PowerShell 모듈 - 지원되는 버전
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 관리에 사용되는 Teams PowerShell 모듈에서 지원되는 버전에 대해 Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e292e3ea5659920bca6fe6f663afc53164da5b49
ms.sourcegitcommit: e3a4df81721abe83886714a7c3c798e4c0888c35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2022
ms.locfileid: "64617709"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell 모듈 - 지원되는 버전

Microsoft Teams 4.x.x 시리즈 이상의 TPM(PowerShell Module) 버전은 앞으로 지원되는 유일한 버전입니다. 이전 버전은 모두 사용 중지 경로에 있습니다. PowerShell 모듈을 최신 Teams 업데이트하는 것이 좋습니다.



## <a name="new-organizations"></a>새 조직

새로 온보드하는 Teams 4.x.x 시리즈 Teams PowerShell 모듈을 2022년 4월 1일부터만 사용할 수 있습니다.



## <a name="current-organizations-non-tpm-active"></a>현재 조직(TPM 활성이 아닌 조직)

지난 Teams PowerShell 모듈을 사용하지 않은 조직은 2022년 4월 1일부터 4.x.x 시리즈 이상에서 Teams PowerShell 모듈만 사용할 수 있습니다.



## <a name="current-organizations-tpm-active"></a>현재 조직(TPM 활성)

지난 Teams PowerShell 모듈을 사용한 조직은 2022년 6월 15일부터 4.x.x 시리즈 이상에서 Teams PowerShell 모듈만 사용할 수 있습니다. 참조용 메시지 센터 게시물 - MC350371. 



## <a name="important-notes"></a>중요 노트

- 모든 PowerShell 모듈 Teams 릴리스 노트는 [PowerShell](teams-powershell-release-notes.md) 릴리스 Teams 있습니다.

- PowerShell 모듈을 업데이트하려면 모듈을 설치하는 데 사용되는 동일한 방법을 사용해야 합니다. 예를 들어 처음 설치 모듈을 사용했다면 [Update-Module](/powershell/module/powershellget/update-module) 을 사용하여 최신 버전을 제공해야 합니다.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   PowerShell 모듈 Teams 버전 1.1.6에서 업데이트하는 경우 `Connect-MicrosoftTeams` 대신 스크립트를 업데이트합니다`New-CsOnlineSession`.

-   업데이트하는 동안 3.0.0보다 오래된 버전과 함께 TPM 4.x.x/3.x.x를 사용하지 않는 것이 권장됩니다. 예를 들어 동일한 조직의 다른 관리자 작업에 대해 4.x.x & 2.6.0 버전을 함께 사용하는 것은 권장되지 않습니다. 

- 관련 변경 내용
  * TPM 3.x.x 이상에서 업데이트 - [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) & (메시지 센터 게시물 – MC340774)의 자세한 내용을 참조하세요. Get-CsOnlineUser & Get-CsOnlineVoiceUser[](/powershell/module/skype/get-csonlinevoiceuser)

  * 번호 할당에 전화 변경 - [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) & (메시지 센터 게시물 – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)

  * 사용 Get-CsOnlineDirectoryTenant - [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant) (메시지 센터 게시물 – MC346902)의 자세한 정보입니다.



## <a name="related-topics"></a>관련 항목

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[PowerShell Microsoft Teams 설치](teams-powershell-install.md)

[PowerShell Teams 사용하여 Teams 관리](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 참조](/powershell/module/teams) 

[비즈니스용 Skype cmdlet 참조](/powershell/module/skype) 