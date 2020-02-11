---
title: 비즈니스용 Skype 서버 2019에서 팀으로 사용자 이동
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
description: '요약: 사용자 설정을 마이그레이션하고 사용자를 팀으로 이동 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: af5281faffa9bd9439e045dc40f67283bb740cb5
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888777"
---
# <a name="move-users-from-on-premises-to-teams"></a>온-프레미스에서 팀으로 사용자 이동

사용자가 온-프레미스에서 팀 전용으로 이동 하는 경우, 사용자의 비즈니스용 Skype 홈은 온-프레미스에서 온라인으로 이동 되며 사용자에 게는 mode = TeamsOnly TeamsUpgradePolicy가 할당 됩니다.  사용자가 온-프레미스에서 TeamsOnly 모드로 이동한 후에는 다음을 수행 합니다.

- 비즈니스용 Skype에서 보내는 모든 수신 전화 및 다른 사용자의 채팅은 사용자의 팀 클라이언트에 배치 됩니다.
- 사용자는 비즈니스용 Skype (온라인 또는 온-프레미스)를 사용 하는 다른 사용자와 상호 작용할 수 있습니다.
- 사용자가 페더레이션 조직의 사용자와 통신할 수 있습니다.
- 해당 사용자가 예약한 새 모임은 팀 모임입니다.
- 사용자는 여전히 비즈니스용 Skype 모임에 참가할 수 있습니다.
- 앞으로 예약 된 사용자의 기존 모임은 온-프레미스에서 팀으로 마이그레이션됩니다.
- 온-프레미스에 있던 연락처는 사용자가 처음으로 로그온 한 후에 팀에서 즉시 사용할 수 있습니다.
- 사용자는 비즈니스용 skype에서 통화 또는 채팅을 시작할 수 없으며 비즈니스용 Skype에서 새 모임을 예약할 수 없습니다. 비즈니스용 Skype 클라이언트를 열려고 하면 아래에 표시 된 것 처럼 팀 사용으로 리디렉션됩니다. 팀 클라이언트가 설치 되어 있지 않으면 브라우저를 사용 하 여 팀의 웹 버전으로 연결 됩니다.<br><br>
    ![팀에 게 사용자를 리디렉션하는 메시지](../media/go-to-teams-page.png)

사용자를 이동 하기 전에 [필수 구성 요소](move-users-between-on-premises-and-cloud.md#prerequisites) 를 검토 하 여 클라우드로 사용자를 이동 해야 합니다. 또한 [팀을 비즈니스용 Skype와 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침도](/microsoftteams/migration-interop-guidance-for-teams-with-skype)검토 해야 합니다.


> [!NOTE]
> 연락처를 팀으로 이동 하려면 온-프레미스 SfB 계정에서 통합 연락처 저장소를 사용 하지 않도록 설정 해야 합니다.


온-프레미스에서 팀으로 사용자를 이동 하는 방법에는 다음 두 가지가 있습니다.

- 비즈니스용 Skype 서버 2015 않았습니다 이전 버전을 사용 하는 경우에는 다음 두 단계가 필요 합니다 (필요한 경우 한 단계로 함께 수행 되도록 스크립팅할 수 있음).
  - 비즈니스용 skype [서버에서 온-프레미스로 사용자를 비즈니스용 Skype Online으로 이동](move-users-from-on-premises-to-skype-for-business-online.md)합니다.
  - 사용자가 비즈니스용 Skype Online에 있으면 사용자에 게 TeamsUpgradePolicy 모드 = TeamsOnly를 할당 합니다. TeamsOnly 모드를 부여 하려면 비즈니스용 Skype Online PowerShell 창에서 다음 cmdlet을 실행 합니다.`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- 비즈니스용 Skype 서버 2015 않았습니다 이상에서 관리 도구를 사용 하는 경우에는 위의 방법을 사용할 수도 있고, 아래 설명 된 것 처럼 한 단계로 이동할 수도 있습니다. 또한 필요한 경우 비즈니스용 Skype 클라이언트 내에 알림을 제공할 수 있을 뿐만 아니라 필요한 경우 비즈니스용 skype 클라이언트에서 팀 클라이언트를 자동으로 다운로드 하도록 할 수도 있습니다.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>비즈니스용 Skype에서 직접 사용자를 팀으로 이동

비즈니스용 skype 서버 2015의 온-프레미스 관리 도구 및 비즈니스용 skype 서버 2019을 사용 하 여 PowerShell 또는 비즈니스용 Skype의 Move-CsUser cmdlet을 사용 하 여 한 번에 사용자를 온-프레미스 전용 모드로 이동할 수 있습니다. 아래 설명 된 것 처럼 rver 제어판

### <a name="move-to-teams-using-move-csuser"></a>Move-CsUser를 사용 하 여 팀으로 이동

이동-CsUser는 온-프레미스 비즈니스용 Skype 관리 셸 PowerShell 창에서 사용할 수 있습니다. 아래 단계 및 필요한 사용 권한은 사용자를 비즈니스용 Skype Online으로 이동 하는 것과 동일 하지만, MoveToTeams 스위치를 지정 해야 하 고 사용자에 게 팀에 대 한 라이선스도 부여 되었는지 확인 해야 합니다 (비즈니스용 Skype 추가). 온라인)

[필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 온-프레미스 환경과 Office 365 테 넌 트 둘 다에 충분 한 권한이 있어야 합니다. 두 환경 모두에서 권한이 있는 단일 계정을 사용 하거나 온-프레미스 자격 증명을 사용 하 여 온-프레미스 비즈니스용 Skype 서버 관리 셸 창을 시작 하 고 `-Credential` 매개 변수를 사용 하 여 필요한 office 365 관리 역할이 있는 office 365 계정에 대 한 자격 증명을 지정할 수 있습니다.

이동-CsUser를 사용 하 여 사용자를 팀 전용 모드로 이동 하려면 다음을 수행 합니다.

- 매개 변수를 `Identity` 사용 하 여 이동할 사용자를 지정 합니다.
- -Target 매개 변수를 "sipfed.online.lync.com>" 값과 함께 지정 합니다. <span>com "입니다.
- 스위치를 `MoveToTeams` 지정 합니다.
- 온-프레미스 및 Office 365 모두에 충분 한 사용 권한이 있는 계정이 없는 경우에는 `-credential` 매개 변수를 사용 하 여 Office 365에서 충분 한 사용 권한을 가진 계정을 제공 합니다.
- Office 365에서 사용 권한이 있는 계정이 "onmicrosoft"로 끝나지 않는 경우 <span>com "에서는 `-HostedMigrationOverrideUrl` [필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 올바른 값을 사용 하 여 매개 변수를 지정 해야 합니다.

다음 cmdlet 시퀀스를 사용 하 여 사용자를 TeamsOnly로 이동할 수 있으며, Office 365 자격 증명이 별도의 계정이 고 자격 증명 확인을 위한 입력으로 제공 된다고 가정 합니다.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용 하 여 팀으로 이동

1. 비즈니스용 Skype 서버 제어판 앱을 엽니다.
2. 왼쪽 탐색 영역에서 **사용자**를 선택 합니다.
3. **찾기를** 사용 하 여 팀으로 이동할 사용자를 찾습니다.
4. 사용자를 선택 하 고 목록 위의 **작업** 드롭다운에서 **선택한 사용자를 팀으로 이동을**선택 합니다.
5. 마법사에서 **다음**을 클릭합니다.
6. 메시지가 표시 되 면 onmicrosoft.com로 끝나고 충분 한 사용 권한이 있는 계정을 사용 하 여 Office 365에 로그인 합니다.
7. **다음**을 클릭 하 고 **다음으로 한 번** 더 사용자를 이동 합니다.
8. 성공 또는 실패와 관련 된 상태 메시지는 마법사가 아니라 주 제어판 앱의 위쪽에 제공 됩니다.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>예정 된 팀 구성원에 대 한 비즈니스용 Skype 온-프레미스 사용자에 게 알림

비즈니스용 skype 서버 2015의 온-프레미스 관리 도구와 않았습니다를 사용 하는 비즈니스용 skype 서버 2019에서는 온-프레미스 비즈니스용 Skype 사용자에 게 팀에 게 알릴 수 있습니다. 이러한 알림을 사용 하도록 설정 하면 사용자는 아래와 같이 비즈니스용 Skype 클라이언트 (Win32, Mac, 웹 및 모바일)에 알림을 표시 합니다. 사용자가 **Try it** 단추를 클릭 하면 팀 클라이언트가 설치 되어 있으면 시작 되 고, 그렇지 않으면 실행 됩니다. 그렇지 않으면 사용자가 브라우저에서 팀의 웹 버전으로 이동 됩니다. 기본적으로 알림을 사용 하도록 설정 하면 Win32 비즈니스용 Skype 클라이언트에서 팀 클라이언트를 자동으로 다운로드 하 여 사용자를 팀 전용 모드로 이동 하기 전에 리치 클라이언트를 사용할 수 있도록 합니다. 그러나이 동작을 사용 하지 않도록 설정할 수도 있습니다.  알림은 온-프레미스 버전 `TeamsUpgradePolicy`을 사용 하 여 구성 되 고 Win32 클라이언트에 대 한 자동 다운로드는 온-프레미스 `TeamsUpgradeConfiguration` cmdlet을 통해 제어 됩니다.

> [!TIP]
> 않았습니다을 사용 하 여 비즈니스용 Skype 2015에서이 작업을 수행 하려면 일부 서버를 다시 부팅 해야 할 수 있습니다.

![팀에 게 예정 된 이후 이동 알림](../media/teams-upgrade-notification.png)

온-프레미스 사용자에 게 곧 팀으로 업그레이드할 예정 임을 알리려면 NotifySfBUsers = true를 사용 하 여 TeamsUpgradePolicy의 새 인스턴스를 만듭니다. 그런 다음 정책을 사용자에 게 직접 할당 하거나 사이트, 풀 또는 전역 수준에서 정책을 설정 하 여 알림을 받을 사용자에 게 해당 정책을 할당 합니다. 다음 cmdlet은 사용자 수준 정책을 만들고 부여 합니다.

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

비즈니스용 Skype Win32 클라이언트를 통한 팀의 자동 다운로드는 DownloadTeams 매개 변수를 사용 하 여 온-프레미스 TeamsUpgradeConfiguration cmdlet을 통해 제어 됩니다. 이 구성은 전역, 사이트 및 풀 수준에서 만듭니다. 예를 들어 다음 명령은 사이트 Redmond1에 대 한 구성을 만듭니다.

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

기본적으로 DownloadTeams의 값은 True입니다. 그러나 지정 된 사용자에 대해 NotifySfbUser = True 인 경우에 *만* 이 속성이 허용 됩니다.

## <a name="see-also"></a>참고 항목

[CsUser 이동](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Team를 비즈니스용 Skype와 함께 사용하는 조직에 대한 마이그레이션 및 상호 운용성 가이드](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[비즈니스용 Skype와 동시 사용](/microsoftteams/coexistence-chat-calls-presence)
