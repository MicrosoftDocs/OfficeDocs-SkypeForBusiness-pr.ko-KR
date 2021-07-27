---
title: 사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 사용자를 온라인 또는 온라인으로 비즈니스용 Skype 방법을 배워야 합니다.
ms.openlocfilehash: fcb1d508230c4faa18da4a473d9e24d384b047a6
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2021
ms.locfileid: "53509949"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

사용자를 프레미스에서 비즈니스용 Skype Online으로 이동한 후 사용자는 기능을 위해 비즈니스용 Skype Online과 상호 작용합니다. 모든 연락처는 비즈니스용 Skype Online에서 사용할 수 있으며, 사용자가 향후에 구성한 기존 모임이 모두 업데이트되어 링크가 비즈니스용 Skype Online을 비즈니스용 Skype. 사용자가 오디오 회의를 사용할 수 있도록 설정된 경우 모임에는 전화 접속 좌표도 포함됩니다.  사용자를 프레미스 환경에서 비즈니스용 Skype Online으로 이동하기 위해 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용합니다. 이 두 cmdlet은 모두온-프레미스 도구입니다. 

사용자를 이동하기 전에 사용자를 클라우드로 이동하기 위한 선행 준비를 검토해야 합니다. [](move-users-between-on-premises-and-cloud.md#prerequisites)

> [!NOTE]
> Microsoft는 예정된 비즈니스용 Skype Online의 사용 중지를 준비하기 위해 조직이 온라인 서비스로 이동하는 Teams. 사용자를 사내에서 클라우드로 이동하면 이제 사용자에게 TeamsOnly 모드가 자동으로 할당되고, 스위치가 실제로 지정되어 있는지 여부에 관계없이 전환이 지정된 경우와 같은 Teams 모임이 자동으로 Teams 모임으로 `-MoveToTeams` 변환됩니다.  비즈니스용 Skype Online을 사용 중지하기 전에 사용자를 비즈니스용 Skype Online으로 이동해야 하는 조직은 사용자가 *TeamsOnly로* 이동된 후 사용자의 모드를 업데이트하여 두 단계로 이 단계를 수행할 수 있습니다. 그러나 조만히 클라우드에 있는 사용자에게 TeamsOnly 외의 모드를 할당할 수 없습니다.  
 
## <a name="move-users-with-move-csuser"></a>사용자 이동을 Move-CsUser 

Move-CsUser 관리 셸 PowerShell 창의 비즈니스용 Skype 사용할 수 있습니다. 필수 관리 자격 증명 에 설명된 바와 같이 조직뿐만 아니라 Microsoft 365 환경 둘 다에 충분한 권한이 [있어야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) 두 환경에서 모두 권한이 있는 단일 계정을 사용할 수도 있습니다. 또는 비즈니스용 Skype 서버 자격 증명을 사용하여 사내 비즈니스용 Skype 서버 관리 셸 창을 시작하고 이 매개 변수를 사용하여 필요한 관리 역할로 Microsoft 365 계정에 대한 자격 증명을 지정할 수 `-Credential` 있습니다.

Move-CsUser를 사용하여 사용자를 온라인으로 이동하는 경우:

- Identity 매개 변수를 사용하여 이동할 사용자를 지정합니다.
- -Target 매개 변수를 값 "sipfed.online.lync"로 지정합니다. <span> com".
- 사내 및 Microsoft 365 둘 다에 충분한 사용 권한이 있는 계정이 하나도 없는 경우 -credential 매개 변수를 사용하여 Microsoft 365.
- 권한이 있는 계정이 Microsoft 365 ".onmicrosoft"로 끝나지 않는 경우. <span> com"을 입력한 다음 필수 관리 자격 증명에 설명된 올바른 값으로 -HostedMigrationOverrideUrl 매개 변수를 [지정해야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

다음 cmdlet 시퀀스를 사용하여 사용자를 Online으로 비즈니스용 Skype 테넌트 기본 모드를 사용자에게 할당할 수 있습니다. 이 계정은 Microsoft 365 자격 증명이 별도의 계정으로 사용 프롬프트에 대한 입력으로 Get-Credential 가정합니다.

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

관리자 계정이 MFA(다단계 인증)를 사용하는 경우 -Credential 매개 변수를 지정하지 않습니다. 관리자에게 자격 증명을 입력하라는 메시지가 표시될 것입니다.

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a>제어판 및 비즈니스용 Skype 서버 센터를 사용하여 Teams 이동

1. 제어판 비즈니스용 Skype 서버 를 니다.
2. 왼쪽 탐색에서 사용자 를 **선택 합니다.**
3. **Find를** 사용하여 Online으로 이동할 사용자를 비즈니스용 Skype.
4. 사용자를 선택한 다음 목록 위의 작업  드롭다운에서 선택한 사용자를  온라인으로 비즈니스용 Skype 이동을 선택하거나 선택한 사용자를 으로 **Teams.** 두 옵션 모두 처음에는 사용자를 TeamsOnly 모드로 이동하지만 이동 후에 다른 모드를 할당할 수 있습니다. 
5. 마법사에서 **다음** 을 클릭합니다.
6. 메시지가 표시될 경우 .Microsoft 365 계정으로 로그인하여 onmicrosoft.com 권한이 있습니다.
7. **다음을** 클릭하고 **다음을** 한 번 더 클릭하여 사용자를 이동합니다.
8. 성공 또는 실패와 관련한 상태 메시지는 마법사가 아니라 주 제어판 앱의 맨 위에 제공됩니다.
9. Teams 관리 센터를 열고 왼쪽 탐색 창에서 "사용자"를 선택합니다. 
10. listview에서 원하는 사용자를 클릭합니다. 
11. 업그레이드 후 편집 **섹션에서** **편집을 Teams 클릭합니다.**
12. 오른쪽 플라이아웃에서 원하는 공존 모드를 선택하고 적용을 **클릭합니다.**
 

## <a name="see-also"></a>참고 항목

[Move-CsUser](/powershell/module/skype/move-csuser)
