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
description: 사용자를 비즈니스용 Skype Online으로 이동하는 방법을 배워야 합니다.
ms.openlocfilehash: a9fb80046195580daca6dfc7f810b2e0c1877f1c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221118"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동

사용자를 비즈니스용 Skype Online으로 이동한 후 사용자는 해당 기능을 위해 비즈니스용 Skype Online과 상호 작용합니다. 모든 연락처는 비즈니스용 Skype Online에서 사용할 수 있으며, 사용자가 향후 구성한 모든 기존 모임이 비즈니스용 Skype Online을 지날 수 있도록 업데이트됩니다. 사용자가 오디오 회의를 사용할 수 있는 경우 모임에 전화 접속 좌표도 포함됩니다.  사용자를 프레미스 환경에서 비즈니스용 Skype Online으로 이동하기 위해 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용합니다. 이 두 cmdlet은 모두온-프레미스 도구입니다. 

사용자를 이동하기 전에 사용자를 클라우드로 이동하기 위한 선행 준비를 검토해야 합니다. [](move-users-between-on-premises-and-cloud.md#prerequisites)
 
## <a name="move-users-with-move-csuser"></a>사용자와 사용자 Move-CsUser 

Move-CsUser 프레미스 비즈니스용 Skype 관리 셸 PowerShell 창에서 사용할 수 있습니다. 필수 관리 자격 증명에 설명된 바와 같이 Microsoft 365/Office 365 조직뿐만 아니라, 모든 환경과 모든 환경에 충분한 권한이 [있어야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) 두 환경 모두에서 권한이 있는 단일 계정을 사용할 수도 있습니다. 또는 비즈니스용 Skype 서버 관리 셸 창을 시작하고, 이 매개 변수를 사용하여 필요한 관리 역할이 있는 `-Credential` Microsoft 365 또는 Office 365 계정에 대한 자격 증명을 지정할 수 있습니다.

Move-CsUser를 사용하여 사용자를 온라인으로 이동하는 경우:

- Identity 매개 변수를 사용하여 이동할 사용자를 지정합니다.
- -Target 매개 변수의 값을 "sipfed.online.lync"로 지정합니다. <span> com".
- On-premises 및 Office 365 둘 다에 충분한 사용 권한이 있는 계정이 하나도 없는 경우 -credential 매개 변수를 사용하여 Office 365에서 충분한 사용 권한이 있는 계정을 제공합니다.
- Office 365에서 사용 권한이 있는 계정이 ".onmicrosoft"로 끝나지 않는 경우 <span> com"을 선택한 다음 필수 관리 자격 증명에 설명된 올바른 값을 사용하여 -HostedMigrationOverrideUrl 매개 변수를 [지정해야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

다음 cmdlet 시퀀스를 사용하여 사용자를 비즈니스용 Skype Online으로 이동할 수 있습니다. 이 매크로에서는 Microsoft 365 또는 Office 365 자격 증명이 별도의 계정으로 가정하며 이 자격 증명 프롬프트의 입력으로 Get-Credential 가정합니다.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

관리자 계정이 MFA(Multi-Factor Authentication)를 사용하는 경우 -Credential 매개 변수를 지정하지 않습니다. 관리자에게 자격 증명을 입력하라는 메시지가 표시될 것입니다.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 사용자 이동 

1. 비즈니스용 Skype 서버 제어판 앱을 열 수 있습니다.
2. 왼쪽 탐색에서 사용자를 **선택 합니다.**
3. **찾기를** 사용하여 비즈니스용 Skype Online으로 이동할 사용자를 찾습니다.
4. 사용자를 선택한 다음 목록 위의 작업  드롭다운에서 선택한 사용자를 **비즈니스용 Skype Online으로 이동을 선택합니다.**
5. 마법사에서 **다음** 을 클릭합니다.
6. 메시지가 표시될 경우 .onmicrosoft.com 계정으로 Microsoft 365 또는 Office 365에 로그인합니다.
7. **다음을** 클릭하고 **다음에** 한 번 더 사용자를 이동합니다.
8. 성공 또는 실패와 관련한 상태 메시지는 마법사가 아니라 주 제어판 앱의 맨 위에 제공됩니다.

## <a name="see-also"></a>참고 항목

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
