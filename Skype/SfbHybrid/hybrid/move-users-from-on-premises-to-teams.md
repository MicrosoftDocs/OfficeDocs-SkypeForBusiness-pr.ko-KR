---
title: 비즈니스용 Skype 서버에서 Teams로 사용자 이동
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
description: '요약: 사용자 설정을 마이그레이션하고 사용자를 Teams로 이동하는 방법을 학습합니다.'
ms.openlocfilehash: 49763d7674946eb179188554326863f4860252c3
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130649"
---
# <a name="move-users-from-on-premises-to-teams"></a>사용자를 온-프레미스에서 Teams로 이동

사용자가 프레미스에서 Teams 전용으로 이동하면 사용자의 비즈니스용 Skype 홈이 온라인에서 온라인으로 이동하고 mode=TeamsOnly를 통해 TeamsUpgradePolicy가 할당됩니다.  사용자가온-프레미스에서 TeamsOnly 모드로 이동된 후:

- 다른 사용자의 모든 수신 전화 및 채팅(비즈니스용 Skype 또는 Teams에서 전송)이 사용자의 Teams 클라이언트에 연결됩니다.
- 사용자는 비즈니스용 Skype(온라인 또는 프레미스에 관계 없이)를 사용하는 다른 사용자와 상호 협력할 수 있습니다.
- 사용자는 페더러 조직의 사용자와 통신할 수 있습니다.
- 해당 사용자가 예약한 새 모임이 Teams 모임입니다.
- 사용자는 여전히 비즈니스용 Skype 모임에 참가할 수 있습니다.
- 앞으로 예정된 사용자의 기존 모임이온-프레미스에서 Teams로 마이그레이션됩니다.
- 사용자가 처음으로 로그온한 직후에는 Teams에서 현재 존재하는 연락처를 사용할 수 있습니다.
- 사용자는 비즈니스용 Skype에서 통화 또는 채팅을 시작할 수 없으며 비즈니스용 Skype에서 새 모임을 예약할 수 없습니다. 비즈니스용 Skype 클라이언트를 열려고 하면 아래와 같이 Teams를 사용으로 리디렉션됩니다. Teams 클라이언트가 설치되어 있지 않은 경우 해당 브라우저를 사용하여 웹 버전의 Teams로 연결됩니다.<br><br>
    ![사용자를 Teams로 리디렉션하는 메시지](../media/go-to-teams-page.png)

사용자를 이동하기 전에 사용자를 클라우드로 이동하기 위한 선행 준비를 검토해야 합니다. [](move-users-between-on-premises-and-cloud.md#prerequisites) 또한 Teams를 비즈니스용 Skype와 함께 사용하는 조직에 대한 마이그레이션 및 상호 관리 지침을 [검토해야 합니다.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)


> [!NOTE]
> 연락처를 Teams로 이동하려면 통합 연락처 저장소를 프레미스 SfB 계정에서 사용하지 않도록 설정해야 합니다.


사용자를 프레미스에서 Teams로 이동하는 방법에는 다음 두 가지가 있습니다.

- 비즈니스용 Skype 서버 2015 CU8 이전 버전을 사용하는 경우 이동에는 두 단계가 필요합니다(필요한 경우 한 단계로 함께 스크립팅할 수 있습니다).
  - [사용자를 비즈니스용 Skype 서버(프레미스)에서](move-users-from-on-premises-to-skype-for-business-online.md)비즈니스용 Skype Online으로 이동
  - 사용자가 비즈니스용 Skype Online에 있는 경우 사용자 TeamsUpgradePolicy와 mode= TeamsOnly를 할당합니다. TeamsOnly 모드를 부여하기 위해 비즈니스용 Skype Online PowerShell 창에서 다음 cmdlet을 실행합니다. `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below. 또한 선택적으로 비즈니스용 Skype 클라이언트 내에서 알림을 Teams로 이동하기 전에 알림을 제공할 수 있습니다. 또한 선택적으로 비즈니스용 Skype 클라이언트에서 Teams 클라이언트를 자동으로 다운로드할 수도 있습니다.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>비즈니스용 Skype에서 Teams 전용으로 직접 사용자 이동

비즈니스용 Skype 서버 2015 및 비즈니스용 Skype 서버 2019의 비즈니스용 Skype 서버 2015의 프레미스 관리 도구를 사용하면 아래 설명된 바와 같이 PowerShell의 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용하여 단일 단계에서 사용자를 프레미스에서 Teams 전용 모드로 이동할 수 있습니다.

### <a name="move-to-teams-using-move-csuser"></a>다음을 사용하여 Teams로 Move-CsUser

Move-CsUser 프레미스 비즈니스용 Skype 관리 셸 PowerShell 창에서 사용할 수 있습니다. 아래 단계와 필요한 사용 권한은 사용자를 비즈니스용 Skype Online으로 이동하는 작업과 동일합니다. 단, MoveToTeams 스위치도 지정해야 하며 사용자에게 비즈니스용 Skype Online 외에 Teams에 대한 라이선스도 부여해야 합니다.

필수 관리 자격 증명에 설명된 바와 같이, 클라우드 서비스(Microsoft 365 또는 Office 365)와의 충분한 권한이 있어야 [합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) 두 환경 모두에서 권한이 있는 단일 계정을 사용할 수도 있습니다. 또는 비즈니스용 Skype 서버 관리 셸 창을 시작하고, 이 매개 변수를 사용하여 필요한 관리 역할이 있는 `-Credential` Microsoft 365 또는 Office 365 계정에 대한 자격 증명을 지정할 수 있습니다.

Move-CsUser를 사용하여 사용자를 Teams 전용 모드로 이동:

- 매개 변수를 사용하여 이동할 사용자를 `Identity` 지정합니다.
- -Target 매개 변수의 값을 "sipfed.online.lync"로 지정합니다. <span> com".
- 스위치를 `MoveToTeams` 지정합니다.
- 모든 클라우드 서비스(Microsoft 365 또는 Office 365)에 대해 충분한 사용 권한이 있는 계정이 하나도 없는 경우 이 매개 변수를 사용하여 Office 365에서 충분한 사용 권한을 계정에 `-credential` 제공합니다.
- Microsoft 365 또는 Office 365에서 사용 권한이 있는 계정이 "onmicrosoft"로 끝나지 않는 경우 <span> com", 필수 관리 자격 증명에 설명된 올바른 값을 사용하여 매개 `-HostedMigrationOverrideUrl` [변수를 지정해야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

다음 cmdlet 시퀀스를 사용하여 사용자를 TeamsOnly로 이동할 수 있으며 Microsoft 365 또는 Office 365 자격 증명이 별도의 계정으로 사용되어 Get-Credential 프롬프트에 대한 입력으로 제공됩니다.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 Teams로 이동

1. 비즈니스용 Skype 서버 제어판 앱을 열 수 있습니다.
2. 왼쪽 탐색에서 사용자를 **선택 합니다.**
3. **찾기를** 사용하여 Teams로 이동할 사용자를 찾습니다.
4. 사용자를 선택한 다음 목록 위의 작업  드롭다운에서 선택한 사용자를 **Teams로 이동을 선택합니다.**
5. 마법사에서 **다음** 을 클릭합니다.
6. 메시지가 표시될 경우 .onmicrosoft.com 계정으로 Microsoft 365 또는 Office 365에 로그인합니다.
7. **다음을** 클릭하고 **다음에** 한 번 더 사용자를 이동합니다.
8. 성공 또는 실패와 관련한 상태 메시지는 마법사가 아니라 주 제어판 앱의 맨 위에 제공됩니다.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>비즈니스용 Skype의 On-premises 사용자에게 Teams로의 예정된 이동을 알릴 수 있습니다.

CU8을 사용하는 비즈니스용 Skype 서버 2015의 프레미스 관리 도구와 비즈니스용 Skype 서버 2019에서는 예정된 비즈니스용 Skype 사용자에게 Teams로의 예정된 이동을 알릴 수 있습니다. 이러한 알림을 사용하도록 설정하면 사용자에게 아래 표시된 비즈니스용 Skype 클라이언트(Win32, Mac, 웹 및 모바일)에서 알림이 표시됩니다. 사용자가 시도  단추를 클릭하면 Teams 클라이언트가 설치된 경우 실행됩니다. 그렇지 않으면 사용자가 브라우저에서 Teams의 웹 버전으로 이동합니다. 기본적으로 알림을 사용하도록 설정하면 Win32 비즈니스용 Skype 클라이언트는 사용자를 Teams 전용 모드로 이동하기 전에 풍부한 클라이언트를 사용할 수 있도록 Teams 클라이언트를 자동으로 다운로드합니다. 그러나 이 동작을 사용하지 않도록 설정할 수도 있습니다.  알림은 프레미스 버전의 On-premises를 사용하여 구성하며, Win32 클라이언트에 대한 자동 다운로드는 `TeamsUpgradePolicy` On-premises `TeamsUpgradeConfiguration` cmdlet을 통해 제어됩니다.

> [!TIP]
> 일부 서버는 CU8을 통해 비즈니스용 Skype 2015에서 작동하기 위해 다시 시작해야 할 수 있습니다.

![Teams로 예정된 이동 알림](../media/teams-upgrade-notification.png)

모든 사용자가 곧 Teams로 업그레이드될 것임에 알리기 위해 NotifySfBUsers=true를 사용하여 TeamsUpgradePolicy의 새 인스턴스를 만드시다. 그런 다음 사용자에게 직접 정책을 할당하거나 사이트, 풀 또는 전역 수준에서 정책을 설정하여 알림을 제공하려는 사용자에게 해당 정책을 할당합니다. 다음 cmdlet은 사용자 수준 정책을 만들고 부여합니다.

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

비즈니스용 Skype Win32 클라이언트를 통해 Teams의 자동 다운로드는 DownloadTeams 매개 변수를 사용하여 온라인 TeamsUpgradeConfiguration cmdlet을 통해 제어됩니다. 이 구성은 전역, 사이트 및 풀 수준에서 만들 수 있습니다. 예를 들어 다음 명령은 Redmond1 사이트에 대한 구성을 만듭니다.

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

기본적으로 DownloadTeams의 값은 True입니다. 그러나 특정 *사용자에* 대해 NotifySfbUser = True인 경우만 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Team를 비즈니스용 Skype와 함께 사용하는 조직에 대한 마이그레이션 및 상호 운용성 가이드](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[비즈니스용 Skype와 공존](/microsoftteams/coexistence-chat-calls-presence)
