---
title: 프레미스 Teams 배포에서 비즈니스용 Skype 도구
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype 업그레이드를 위한 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5465267309966ccaa4806db094e70eb02f8c5aebd9e72e4ea9de00610bac1417
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319651"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>IT 관리자를 위해 Teams &mdash; 도구

이 문서에서는 이 문서에서 Teams 업그레이드하기 위한 비즈니스용 Skype. 

업그레이드를 시작하기 전에 Microsoft는 중요한 업그레이드 개념 및 공존 동작을 설명하는 다음 문서를 권장합니다.

- [Teams 및 비즈니스용 Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>업그레이드를 관리하는 도구

어떤 업그레이드 방법을 선택하든 온라인에 이미 비즈니스용 Skype 있는 사용자의 경우 [TeamsUpgradePolicy를 사용하여 TeamsOnly로의](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)전환을 관리합니다. 이는 사용자의 공존 모드를 제어합니다. 에 있는 프레미스 계정이 있는 비즈니스용 Skype 서버 클라우드로 이동하는 `Move-CsUser` [데도 사용할 수 있습니다.](/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  각 모드에 대한 자세한 내용은 공존 모드 [를 참조하세요.](migration-interop-guidance-for-teams-with-skype.md)

> [!NOTE]
> 현재 온라인 커넥터를 사용하여 비즈니스용 Skype 서비스를 관리하는 경우 PowerShell 모듈로 이동하여 Teams PowerShell 스크립트를 업데이트해야 합니다. 자세한 내용은 비즈니스용 Skype 온라인 커넥터에서 Teams [PowerShell 모듈로](teams-powershell-move-from-sfbo.md) 이동을 참조하세요.

기본 비즈니스용 Skype 모드를 사용하여 선택 기능 전환을 수행하거나 기본 섬 구성에서 TeamsOnly 모드로 업그레이드하는 경우 TeamsUpgradePolicy는 기본 도구입니다. 다른 정책과 Teams TeamsUpgradePolicy를 사용자에게 직접 할당할 수 있습니다. 정책을 테넌트 전체 기본값으로 설정할 수도 있습니다. 사용자에 대한 할당은 테넌트 기본 설정보다 우선합니다.  관리 콘솔 및 PowerShell에서 Teams 관리할 수 있습니다.

TeamsOnly 모드를 제외한 TeamsUpgradePolicy의 모든 모드를 모든 비즈니스용 Skype 있습니다. 반대로 클라우드에 있는 사용자는 TeamsOnly 모드만 할당할 수 있습니다. **TeamsOnly** 모드는 사용자가 온라인 온라인에 비즈니스용 Skype 비즈니스용 Skype 경우만 가능하기 때문에 클라우드에 이미 비즈니스용 Skype 사용자에게만 할당할 수 Microsoft 365 전화 시스템 있습니다.  또한 **온-프레미스** 배포가 있는 경우 TeamsOnly 모드를 테넌트 전체 기본값으로 할당할 수 비즈니스용 Skype(lyncdiscover DNS 레코드가 있는 경우 다른 위치를 지정하는 것으로 Office 365. 자세한 내용은 하이브리드 구성을 사용하지 않도록 설정하여 에서만 으로 [마이그레이션을 Teams 참조합니다.](/SkypeForBusiness/hybrid/cloud-consolidation-disabling-hybrid)

온라인 비즈니스용 Skype 계정이 있는 사용자는 온라인에서 Teams Move-CsUser 도구 비즈니스용 Skype 전용 모드로 이동해야 합니다. [](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

다른 정책과 달리, 여러 정책에서 TeamsUpgradePolicy의 새 인스턴스를 만들 수 Microsoft 365 Office 365. 모든 기존 인스턴스는 서비스에 기본 제공됩니다.  (모드는 정책 인스턴스의 이름이 아닌 TeamsUpgradePolicy 내의 속성입니다.) 일부에서는 그렇지만 모든 경우에서는 정책 인스턴스의 이름이 모드와 동일합니다. 특히 TeamsOnly 모드를 사용자에게 할당하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 해당 사용자에게 부여합니다. 모든 인스턴스 목록을 표시하기 위해 다음 명령을 실행할 수 있습니다.

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

온라인 사용자를 TeamsOnly 모드로 업그레이드하려면 "UpgradeToTeams" 인스턴스를 할당합니다. 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

프레미스 비즈니스용 Skype TeamsOnly 모드로 업그레이드하려면 Move-CsUser 도구를 사용합니다.

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -credential $cred
```

테넌트의 모든 사용자에 대한 모드를 변경하기 위해 사용자당 명시적 부여(우선 순위)가 있는 사용자를 제외하고는 다음 명령을 실행합니다.

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>모든 사용자가 비즈니스용 Skype 있는 경우 테넌트 수준에서 TeamsOnly 모드를 할당할 수 없습니다. Move-CsUser를 사용하여 이러한 Teams 전용 모드로 개별적으로 이동해야 합니다.


## <a name="using-notifications-in-skype-for-business-clients"></a>클라이언트에서 알림 비즈니스용 Skype 사용

관리자는 다음 다이어그램에 표시된 비즈니스용 Skype 클라이언트에서 최종 사용자 알림을 제공하여 사용자에게 곧 Teams 알릴 수 있습니다. 예를 들어 관리자가 사용자 그룹을 TeamsOnly 모드로 업그레이드하기 일주일 전에 관리자는 해당 사용자 그룹에 대한 이러한 알림을 켜야 할 수 있습니다. 이러한 알림은 NotificationSfbUsers=true와 TeamsUpgradePolicy의 인스턴스를 사용하여 사용하도록 설정됩니다.  TeamsOnly를 다른 모든 모드의 경우, 실제로는 NotifySfbUsers의 두 값에 해당하는 모드당 두 개의 인스턴스가 있습니다.  TeamsOnly를 다른 모든 모드의 경우, 실제로는 NotifySfbUsers의 두 값에 해당하는 모드당 두 개의 인스턴스가 있습니다. 

![알림을 보여주는 다이어그램](media/teams-upgrade-sfb-with-notifications.png)

사용자가 온라인에 비즈니스용 Skype 경우 사용자와 동일한 모드가 있지만 NotifySfbUsers=true인 정책 인스턴스를 할당하기만 합니다. 

사용자가 비즈니스용 Skype 서버 프레미스에 있는 경우, 2015년에는 2019 또는 CU8을 비즈니스용 Skype 서버 2019 또는 CU8을 비즈니스용 Skype 서버 있습니다. 프레미스 비즈니스용 Skype 서버 있는 사용자의 경우 TeamsUpgradePolicy의 온라인 인스턴스의 모드 속성은 존중되지만, NotifySfbUsers 속성은 그렇지 않습니다. 알림이 필요한 경우 클라이언트 동작을 제어하려면 TeamsUpgradePolicy의 프레미스 인스턴스를 만들어야 합니다. 

On-Premises PowerShell 창에서 NotifySfbUsers=true를 사용하여 TeamsUpgradePolicy의 새 인스턴스를 만드십시오.

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

그런 다음 동일한 On-Premises PowerShell 창을 사용하여 원하는 사용자에게 해당 새 정책을 할당합니다.

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>모임 마이그레이션

사용자가 TeamsOnly 모드로 마이그레이션되는 경우 기본적으로 구성한 기존 비즈니스용 Skype 모임이 기본적으로 Teams. 사용자에게 TeamsOnly 모드를 할당할 때 기본 동작을 선택적으로 사용하지 않도록 설정할 수 있습니다. 사용자를온-프레미스에서 이동하는 경우 모임을 클라우드로 마이그레이션하여 온라인 사용자 계정으로 작동해야 하지만 -MoveToTeams를 지정하지 않으면 모임을 비즈니스용 Skype 모임으로 마이그레이션되지 않고 Teams. 

테넌트 수준에서 TeamsOnly 모드를 할당하는 경우 모든 사용자에 대해 모임 마이그레이션이 트리거되지 않습니다. 테넌트 수준에서 TeamsOnly 모드를 할당하고 모임을 마이그레이션하려는 경우 PowerShell을 사용하여 테넌트의 사용자 목록을(예: 필요한 필터와 함께 Get-CsOnlineUser 사용) 각 사용자를 반복하여 Start-CsExMeetingMigration을 사용하여 모임 마이그레이션을 트리거할 수 있습니다. 자세한 내용은 [MMS(모임 마이그레이션 서비스) 사용을 참조합니다.](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>관련 링크

[공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버 및 Microsoft 365 Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
