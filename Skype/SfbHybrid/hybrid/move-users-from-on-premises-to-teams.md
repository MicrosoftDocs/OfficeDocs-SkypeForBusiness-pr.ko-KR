---
title: 비즈니스용 Skype 서버 2019에서 Teams로 사용자 이동
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.custom: ''
description: '요약: 사용자 설정을 마이그레이션하고 사용자를 Teams로 이동하는 방법을 알아봅니다.'
ms.openlocfilehash: d29fa49e3521e93cb1818c70adb37cfb5019660b
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705847"
---
# <a name="move-users-from-on-premises-to-teams"></a>사용자를 온-프레미스에서 Teams로 이동

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

사용자가 온-프레미스에서 Teams만으로 이동하면 사용자의 비즈니스용 Skype 홈이 온-프레미스에서 온라인으로 이동되고 사용자에게 mode=TeamsOnly를 사용하여 TeamsUpgradePolicy가 할당됩니다.  사용자가 온-프레미스에서 TeamsOnly 모드로 이동된 후:

- 비즈니스용 Skype 또는 Teams에서 보낸 모든 수신 전화 및 채팅은 사용자의 Teams 클라이언트에 전달됩니다.
- 사용자는 비즈니스용 Skype를 사용하는 다른 사용자(온라인이든 온-프레미스이든)와 상호 운용할 수 있습니다.
- 사용자는 페더레이션된 조직의 사용자와 통신할 수 있습니다.
- 해당 사용자가 예약한 새 모임은 Teams 모임입니다.
- 사용자는 여전히 모든 비즈니스용 Skype 모임에 참가할 수 있습니다. 그러나 2022년 10월부터 하이브리드 조직의 TeamsOnly 사용자는 익명으로만 비즈니스용 Skype 모임에 참가할 수 있습니다. 자세한 내용은 [은퇴 후 예상되는 사항을](/microsoftteams/skype-for-business-online-retirement#what-to-expect-post-retirement) 참조하세요.
- 향후에 예정된 사용자의 기존 모임은 온-프레미스에서 Teams로 마이그레이션됩니다.
- 온-프레미스에 존재하는 연락처는 사용자가 처음으로 로그온한 직후 Teams에서 사용할 수 있습니다.
- 사용자는 비즈니스용 Skype 통화 또는 채팅을 시작할 수 없으며 비즈니스용 Skype 새 모임을 예약할 수도 없습니다. 비즈니스용 Skype 클라이언트를 열려고 하면 아래와 같이 Teams를 사용하도록 리디렉션됩니다. Teams 클라이언트가 설치되지 않은 경우 브라우저를 사용하여 웹 버전의 Teams로 전달됩니다.<br><br>
    ![사용자를 Teams로 리디렉션하는 메시지입니다.](../media/go-to-teams-page.png)

사용자를 이동하기 전에 사용자를 클라우드로 이동하기 위한 [필수 구성 요소를](move-users-between-on-premises-and-cloud.md#prerequisites) 검토해야 합니다. 또한 [비즈니스용 Skype 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 운용성 지침을](/microsoftteams/migration-interop-guidance-for-teams-with-skype) 검토해야 합니다.


> [!NOTE]
> 연락처를 Teams로 이동하려면 온-프레미스 SfB 계정에서 통합 연락처 저장소를 사용하지 않도록 설정해야 합니다.

> [!IMPORTANT]
>
> - Move-CsUser를 사용하여 사용자를 온-프레미스에서 클라우드로 이동하면 사용자에게 TeamsOnly 모드가 자동으로 할당되고, 스위치가 실제로 지정되었는지 여부에 `-MoveToTeams` 관계없이 온-프레미스에서의 모임이 Teams 모임으로 자동으로 변환됩니다. (여기에는 스위치가 없었던 Lync Server 2013의 마이그레이션이 `-MoveToTeams` 포함됩니다.)  이전에는 이 스위치를 지정하지 않은 경우 사용자가 비즈니스용 Skype 서버 온-프레미스에서 비즈니스용 Skype Online으로 전환되었으며 해당 모드는 변경되지 않았습니다. 이것은 비즈니스용 Skype Online의 은퇴를 준비하기 위해 변경되었습니다.
> - 이제 온-프레미스 배포와 Teams 간에 사용자를 이동하려면 비즈니스용 Skype Online 레거시 인프라에 더 이상 의존하지 않는 비즈니스용 Skype 서버 또는 Lync Server에서 온-프레미스 구성 요소의 업데이트된 최소 버전이 *필요합니다*. 자세한 내용은 [필수 구성 요소를 참조하세요](move-users-between-on-premises-and-cloud.md#prerequisites).

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>사용자를 비즈니스용 Skype 온-프레미스에서 Teams 전용으로 직접 이동

비즈니스용 Skype 서버 및 Lync Server 2013의 온-프레미스 관리 도구를 사용하면 아래 설명된 대로 PowerShell의 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판 사용하여 한 단계로 온-프레미스에서 TeamsOnly 모드로 사용자를 이동할 수 있습니다. 더 이상 스위치를 지정할 `-MoveToTeams` 필요가 없으며 온-프레미스에서 Teams로 직접 이동하는 동작은 이제 사용되는 비즈니스용 Skype 서버 또는 Lync Server 버전에 관계없이 자동입니다. 

[필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명된 대로 온-프레미스 환경과 클라우드 서비스(Microsoft 365 또는 Office 365) 모두에서 충분한 권한이 있어야 합니다. 두 환경 모두에서 권한이 있는 단일 계정을 사용하거나 온-프레미스 자격 증명을 사용하여 온-프레미스 비즈니스용 Skype 서버 관리 셸 창을 시작하고 매개 변수를 사용하여 `-Credential` 필요한 관리 역할로 Microsoft 365에 대한 자격 증명을 지정할 수 있습니다.

또한 사용자에게 Teams에 대한 라이선스가 부여되었는지 확인해야 합니다(비즈니스용 Skype Online 외에). 비즈니스용 Skype Online 라이선스를 사용하지 않도록 설정하지 마세요.

### <a name="move-to-teams-using-move-csuser"></a>Move-CsUser를 사용하여 Teams로 이동

Move-CsUser는 온-프레미스 비즈니스용 Skype 서버 관리 셸 PowerShell 창 또는 Lync Server 관리 셸 PowerShell 창에서 사용할 수 있습니다. Move-CsUser를 사용하여 사용자를 TeamsOnly 모드로 이동하려면:
- 매개 변수를 사용하여 이동할 사용자를 지정합니다 `Identity` .
- `-Target`"sipfed.online.lync" 값을 사용하여 매개 변수를 지정합니다.<span> com"(또는 테넌트가 정부 클라우드인 경우 유사한 값).
- 온-프레미스 및 클라우드 서비스(Microsoft 365)에 충분한 권한이 있는 계정이 없는 경우 이 매개 변수를 사용하여 `-credential` Microsoft 365에서 충분한 권한을 가진 계정을 제공합니다.
- Microsoft 365의 권한이 있는 계정이 "onmicrosoft<span>"로 끝나지 않는 경우 com", [필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 `-HostedMigrationOverrideUrl` 설명된 대로 올바른 값을 사용하여 매개 변수를 지정해야 합니다.
- 온-프레미스 관리 도구를 실행하는 컴퓨터가 비즈니스용 Skype 서버 또는 Lync Server 2013 버전에 최신 CU를 사용하고 있는지 확인하여 OAuth가 인증에 사용되는지 확인합니다. 

다음 cmdlet 시퀀스를 사용하여 사용자를 TeamsOnly로 이동할 수 있으며 Microsoft 365 자격 증명이 별도의 계정이며 Get-Credential 프롬프트에 대한 입력으로 제공된다고 가정합니다. 이 동작은 스위치가 지정되었는지 여부에 관계없이 `-MoveToTeams` 동일합니다.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> 다른 매개 변수가 필요한 상황이 다르기 때문에 대부분의 경우 기본 명령은 다음과 같습니다.

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 Teams로 이동

1. 비즈니스용 Skype 서버 제어판 앱을 엽니다.
2. 왼쪽 탐색 영역에서 **사용자를** 선택합니다.
3. **찾기** 를 사용하여 Teams로 이동하려는 사용자를 찾습니다.
4. 사용자를 선택한 다음 목록 위의 **작업** 드롭다운에서 **선택한 사용자를 Teams로 이동** 또는 **선택한 사용자를 비즈니스용 Skype Online으로 이동** 을 선택합니다.   이제 두 옵션 중 하나를 선택하면 사용자가 TeamsOnly로 직접 이동합니다.
5. 마법사에서 **다음** 을 클릭합니다.
6. 메시지가 표시되면 .onmicrosoft.com으로 끝나고 충분한 권한이 있는 계정으로 Microsoft 365에 로그인합니다.
7. **다음** 을 클릭한 후 **다음** 을 한 번 더 클릭하여 사용자를 이동합니다.
8. 성공 또는 실패에 대한 상태 메시지는 마법사가 아닌 기본 제어판 앱 상단에 제공됩니다.
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>비즈니스용 Skype 온-프레미스 사용자에게 Teams로의 향후 이동에 대해 알립니다.

2015년 비즈니스용 Skype 서버 CU8 및 비즈니스용 Skype 서버 2019의 온-프레미스 관리 도구를 사용하면 온-프레미스 비즈니스용 Skype 사용자에게 Teams로의 향후 이동에 대해 알릴 수 있습니다. 이러한 알림을 사용하도록 설정하면 아래와 같이 비즈니스용 Skype 클라이언트(Win32, Mac, 웹 및 모바일)에 알림이 표시됩니다. 사용자가 **시도** 단추를 클릭하면 Teams 클라이언트가 설치된 경우 시작됩니다. 그렇지 않으면 사용자는 브라우저에서 Teams의 웹 버전으로 이동됩니다. 기본적으로 알림을 사용하도록 설정하면 Win32 비즈니스용 Skype 클라이언트는 Teams 클라이언트를 자동으로 다운로드하여 사용자를 TeamsOnly 모드로 이동하기 전에 풍부한 클라이언트를 사용할 수 있도록 합니다. 그러나 이 동작을 사용하지 않도록 설정할 수도 있습니다.  알림은 온-프레미스 버전의 `TeamsUpgradePolicy`를 사용하여 구성되며 Win32 클라이언트에 대한 자동 다운로드는 온-프레미스 cmdlet을 통해 제어됩니다 `TeamsUpgradeConfiguration` .


![Teams로의 향후 이동 알림입니다.](../media/teams-upgrade-notification.png)

온-프레미스 사용자에게 Teams로 곧 업그레이드될 것임을 알리려면 NotifySfBUsers=true를 사용하여 TeamsUpgradePolicy의 새 인스턴스를 만듭니다. 그런 다음 사용자에게 직접 정책을 할당하거나 사이트, 풀 또는 전역 수준에서 정책을 설정하여 알리려는 사용자에게 해당 정책을 할당합니다. 다음 cmdlet은 사용자 수준 정책을 만들고 부여합니다.

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

비즈니스용 Skype Win32 클라이언트를 통한 Teams 자동 다운로드는 DownloadTeams 매개 변수를 사용하여 온-프레미스 TeamsUpgradeConfiguration cmdlet을 통해 제어됩니다. 전역, 사이트 및 풀 수준에서 이 구성을 만듭니다. 예를 들어 다음 명령은 Redmond1 사이트에 대한 구성을 만듭니다.

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

기본적으로 DownloadTeams의 값은 True입니다. 그러나 지정된 사용자에 대해 NotifySfbUser = True인 *경우에만* 적용됩니다.

## <a name="see-also"></a>참고 항목

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Team를 비즈니스용 Skype와 함께 사용하는 조직에 대한 마이그레이션 및 상호 운용성 가이드](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[비즈니스용 Skype와 공존](/microsoftteams/coexistence-chat-calls-presence)
