---
title: 2019년 비즈니스용 Skype 서버 사용자 이동 Teams
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
description: '요약: 사용자 설정을 마이그레이션하고 사용자를 마이그레이션하도록 이동하는 Teams.'
ms.openlocfilehash: 1df8c617d40b88813074319d7eb041995ff71ca5
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2021
ms.locfileid: "53509779"
---
# <a name="move-users-from-on-premises-to-teams"></a>사용자를 온-프레미스에서 Teams로 이동

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

사용자가 프레미스에서 Teams 전용으로 이동하면 사용자의 비즈니스용 Skype 홈이 사내에서 온라인으로 이동하고 사용자에게 mode=TeamsOnly를 통해 TeamsUpgradePolicy가 할당됩니다.  사용자가 사내에서 TeamsOnly 모드로 이동된 후:

- 다른 사용자의 모든 수신 전화 및 채팅(비즈니스용 Skype 또는 Teams)은 사용자의 Teams 클라이언트에 연결됩니다.
- 사용자는 다른 사용자(온라인 또는 프레미스에 관계 없이)를 사용하는 다른 비즈니스용 Skype 수 있습니다.
- 사용자는 페더러 조직의 사용자와 통신할 수 있습니다.
- 해당 사용자가 예약한 새 모임이 Teams 있습니다.
- 사용자는 여전히 모든 모임에 참가할 비즈니스용 Skype 있습니다.
- 향후 예약된 사용자의 기존 모임은 사내에서 기존 모임으로 Teams.
- 사용자가 처음으로 로그온한 직후에는 Teams 연락처를 사용할 수 있습니다.
- 사용자는 사용자로부터 통화 또는 채팅을 시작할 수 비즈니스용 Skype 모임을 예약할 수 비즈니스용 Skype. 사용자가 비즈니스용 Skype 클라이언트를 열려고 하면 아래 표시된 Teams 사용으로 리디렉션됩니다. Teams 클라이언트가 설치되어 있지 않은 경우 브라우저를 사용하여 웹 버전의 클라이언트로 Teams 됩니다.<br><br>
    ![사용자를 사용자로 리디렉션하는 Teams](../media/go-to-teams-page.png)

사용자를 이동하기 전에 사용자를 클라우드로 이동하기 위한 선행 준비를 검토해야 합니다. [](move-users-between-on-premises-and-cloud.md#prerequisites) 또한 마이그레이션 및 상호 관리 지침과 함께 Teams [조직에 대한](/microsoftteams/migration-interop-guidance-for-teams-with-skype)비즈니스용 Skype.


> [!NOTE]
> 연락처를 프레미스 SfB 계정으로 이동하려면 통합 연락처 저장소를 사용하지 않도록 설정해야 Teams.

> [!IMPORTANT]
>Move-CsUser를 사용하여 사용자를 사내에서 클라우드로 이동하면 이제 사용자에게 TeamsOnly 모드가 자동으로 할당되고, 전환이 실제로 지정되어 있는지 여부에 관계없이 해당 모임이 Teams 모임으로 자동 `-MoveToTeams` 변환됩니다. 여기에는 전환이 없는 Lync Server 2013의 마이그레이션이 `-MoveToTeams` 포함됩니다.  이전에는 이 스위치를 지정하지 않은 경우 사용자가 비즈니스용 Skype 서버 프레미스에서 비즈니스용 Skype Online으로 전환한 모드는 변경되지 않았습니다. 이는 최근에 온라인에서 서비스 중지를 준비하는 비즈니스용 Skype 변경된 것입니다.


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>사용자를 비즈니스용 Skype 프레미스에서 Teams 전용으로 이동

비즈니스용 Skype 서버 및 Lync Server 2013의 온-프레미스 관리 도구를 사용하면 아래 설명된 바와 같이 PowerShell의 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용하여 단일 단계에서 온-프레미스에서 TeamsOnly 모드로 사용자를 이동할 수 있습니다. 더 이상 스위치를 지정할 필요는 없습니다. 온-프레미스에서 Teams 서버로 직접 이동하는 동작은 이제 비즈니스용 Skype 서버 또는 Lync Server 버전에 관계없이 `-MoveToTeams` 자동입니다. 

필수 관리 자격 증명 에 설명된 바와 같이 사내 환경과 클라우드 서비스(Microsoft 365 또는 Office 365 둘 다에 충분한 권한이 있어야 [합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) 두 환경 모두에서 권한이 있는 단일 계정을 사용할 수도 있습니다. 또는 비즈니스용 Skype 서버 자격 증명으로 사내 관리 셸 창을 시작하고 매개 변수를 사용하여 필요한 관리 역할로 Microsoft 365 자격 증명을 지정할 수 `-Credential` 있습니다.

또한 사용자에게 Teams(비즈니스용 Skype 외에도) 라이선스가 부여되어 있어야 합니다. 온라인 라이선스를 사용하지 비즈니스용 Skype 않습니다.

### <a name="move-to-teams-using-move-csuser"></a>다음을 사용하여 Teams 이동 Move-CsUser

Move-CsUser 온-프레미스 관리 셸 PowerShell 비즈니스용 Skype 서버 Lync Server 관리 셸 PowerShell 창에서 사용할 수 있습니다. Move-CsUser를 사용하여 사용자를 TeamsOnly 모드로 이동하는 경우:
- 매개 변수를 사용하여 이동할 사용자를 `Identity` 지정합니다.
- `-Target`"sipfed.online.lync" 값으로 매개 변수를 지정합니다. <span> com".
- 사내 및 클라우드 서비스(Microsoft 365)에서 충분한 사용 권한이 있는 계정이 하나도 없는 경우 이 매개 변수를 사용하여 `-credential` Microsoft 365.
- 권한이 있는 계정이 Microsoft 365 "onmicrosoft"로 끝나지 않는 경우. <span> com", 필수 관리 자격 증명에 설명된 올바른 값을 사용하여 매개 `-HostedMigrationOverrideUrl` [변수를 지정해야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

다음 cmdlet 시퀀스를 사용하여 사용자를 TeamsOnly로 이동하고 Microsoft 365 자격 증명이 별도의 계정으로 제공된 것으로 가정하고 Get-Credential 프롬프트에 대한 입력으로 제공됩니다. 스위치를 지정하는지 `-MoveToTeams` 여부에 따라 동작이 동일합니다.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> 서로 다른 매개 변수가 필요한 상황에 따라 대부분의 경우 기본 명령은 다음을 나타냅니다.

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>제어판을 Teams 비즈니스용 Skype 서버 이동

1. 제어판 비즈니스용 Skype 서버 를 니다.
2. 왼쪽 탐색에서 사용자 를 **선택 합니다.**
3. **Find를** 사용하여 이동하고자 하는 사용자를 Teams.
4. 사용자를 선택하고 목록 위의 작업 드롭다운에서 선택한 사용자를 Teams  온라인으로 이동을 비즈니스용 Skype **선택합니다.**    이제 두 옵션 모두 사용자를 TeamsOnly로 직접 이동합니다.
5. 마법사에서 **다음** 을 클릭합니다.
6. 메시지가 표시될 경우 .Microsoft 365 계정으로 로그인하여 onmicrosoft.com 권한이 있습니다.
7. **다음을** 클릭하고 **다음을** 한 번 더 클릭하여 사용자를 이동합니다.
8. 성공 또는 실패와 관련한 상태 메시지는 마법사가 아니라 주 제어판 앱의 맨 위에 제공됩니다.
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>비즈니스용 Skype 사용자에 대한 예정된 이동을 Teams

cu8과 비즈니스용 Skype 서버 2019의 비즈니스용 Skype 서버 2015의 프레미스 관리 도구를 사용하여 비즈니스용 Skype 예정된 사용자에 대한 서비스로의 이동을 알릴 수 Teams. 이러한 알림을 사용하도록 설정하면 사용자에게 아래 표시된 비즈니스용 Skype 클라이언트(Win32, Mac, 웹 및 모바일)에 알림이 표시됩니다. 사용자가 시도 **단추를** 클릭하면 Teams 클라이언트가 설치되면 실행됩니다. 그렇지 않으면 사용자가 브라우저에서 웹 버전의 Teams 탐색됩니다. 기본적으로 알림을 사용하도록 설정하면 Win32 비즈니스용 Skype 클라이언트가 사용자를 TeamsOnly 모드로 이동하기 전에 리치 클라이언트를 사용할 수 있도록 Teams 클라이언트를 자동으로 다운로드합니다. 그러나 이 동작을 사용하지 않도록 설정할 수도 있습니다.  알림은 의 On-프레미스 버전을 사용하여 구성하며, Win32 클라이언트에 대한 자동 다운로드는 `TeamsUpgradePolicy` 사내 `TeamsUpgradeConfiguration` cmdlet을 통해 제어됩니다.

> [!TIP]
> 일부 서버는 CU8이 있는 2015에서 작동하려면 비즈니스용 Skype 다시 시작해야 할 수 있습니다.

![사용자로의 예정된 이동 Teams](../media/teams-upgrade-notification.png)

프레미스 사용자에게 곧 업그레이드될 것 Teams NotifySfBUsers=true를 사용하여 TeamsUpgradePolicy의 새 인스턴스를 만드시다. 그런 다음 사용자에게 직접 정책을 할당하거나 사이트, 풀 또는 전역 수준에서 정책을 설정하여 알림을 하려는 사용자에게 해당 정책을 할당합니다. 다음 cmdlet은 사용자 수준 정책을 만들고 부여합니다.

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Teams Win32 클라이언트를 통해 비즈니스용 Skype 다운로드는 DownloadTeams 매개 변수를 사용하여 사내 TeamsUpgradeConfiguration cmdlet을 통해 제어됩니다. 전역, 사이트 및 풀 수준에서 이 구성을 만들 수 있습니다. 예를 들어 다음 명령은 Redmond1 사이트에 대한 구성을 만듭니다.

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

기본적으로 DownloadTeams 값은 True입니다. 그러나 특정 *사용자에* 대해 NotifySfbUser = True인 경우만 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Team를 비즈니스용 Skype와 함께 사용하는 조직에 대한 마이그레이션 및 상호 운용성 가이드](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[비즈니스용 Skype와 공존](/microsoftteams/coexistence-chat-calls-presence)
