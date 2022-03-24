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
ms.openlocfilehash: ea8a755c75c5f91c5dbf3a4cd4dd749ac576557c
ms.sourcegitcommit: b878c57b8e822913b7aac8c105f476bc4ebfcd7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2022
ms.locfileid: "63762012"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell 모듈 - 지원되는 버전

Microsoft Teams PowerShell 모듈(TPM) 버전 4.0.0 이상은 앞으로 지원되는 유일한 버전입니다. 이전 버전은 모두 사용 중지 경로에 있습니다.



## <a name="new-organizations"></a>새 조직

새로 온보드하는 Teams PowerShell 모듈 4.0.0 Teams 2022년 4월 1일부터만 사용할 수 있습니다.



## <a name="current-organizations-non-tpm-active"></a>현재 조직(TPM 활성이 아닌 조직)

지난 3개월 동안 TPM을 사용하지 않은 조직(1월 22일 – 3월 22일)은 2022년 4월 1일부터 TPM 4.0.0 이상만 사용할 수 있습니다.



## <a name="current-organizations-tpm-active"></a>현재 조직(TPM 활성)

지난 3개월(1월 22일 – 3월 22일)에 TPM을 사용한 조직은 2022년 6월 15일부터 TPM 4.0.0 이상만 사용할 수 있습니다. PowerShell 모듈을 최신 Teams 업데이트하는 것이 좋습니다.


## <a name="important-notes"></a>중요 노트

- 모든 PowerShell 모듈 Teams 릴리스 노트는 [PowerShell](teams-powershell-release-notes.md) 릴리스 Teams 있습니다.

- PowerShell 모듈을 업데이트하려면 모듈을 설치하는 데 사용되는 동일한 방법을 사용해야 합니다. 예를 들어 처음 설치 모듈을 사용했다면 [Update-Module](/powershell/module/powershellget/update-module) 을 사용하여 최신 버전을 제공해야 합니다.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   PowerShell 모듈 Teams 버전 1.1.6에서 업데이트하는 경우 `Connect-MicrosoftTeams` 대신 스크립트를 업데이트합니다`New-CsOnlineSession`.

-   업데이트하는 동안 3.0.0보다 오래된 버전과 함께 TPM 4.x.x/3.x.x를 사용하지 않는 것이 권장됩니다. 예를 들어 동일한 조직의 다른 관리자 작업에 대해 버전 4.0.0 & 2.6.0을 함께 사용하는 것은 권장되지 않습니다. 

- 관련 변경 내용
  * TPM 3.0.0 이상에서 업데이트 - Get-CsOnlineUserGet-CsOnlineVoiceUser[](/powershell/module/skype/get-csonlineuser) & (메시지 센터 게시물 – MC340774)의 자세한 내용은 TPM 3.0.0 이상에서 업데이트됩니다. Get-CsOnlineUser & Get-CsOnlineVoiceUser[](/powershell/module/skype/get-csonlinevoiceuser)

  * 번호 할당에 전화 변경 - [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) & (메시지 센터 게시물 – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="related-topics"></a>관련 항목

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[PowerShell Microsoft Teams 설치](teams-powershell-install.md)

[PowerShell Teams 사용하여 Teams 관리](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 참조](/powershell/module/teams) 

[비즈니스용 Skype cmdlet 참조](/powershell/module/skype) 
