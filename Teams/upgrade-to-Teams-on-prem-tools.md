---
title: 비즈니스용 Skype-프레미스 배포에서 Teams로 업그레이드하기 위한 도구
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드하기 위한 도구
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8c272cdd6eac98b8847b6f915d59b62444d16c97
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460438"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>IT 관리자를 위한 &mdash; Teams로 업그레이드하기 위한 도구

이 문서에서는 비즈니스용 Skype에서 Teams로 업그레이드하는 도구를 설명합니다. 

업그레이드를 시작하기 전에 Microsoft는 중요한 업그레이드 개념 및 공존 동작을 설명하는 다음 문서를 권장합니다.

- [Teams 및 비즈니스용 Skype의 공존](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="tools-for-managing-the-upgrade"></a>업그레이드를 관리하는 도구

선택한 업그레이드 방법 중 비즈니스용 Skype Online이 이미 있는 사용자의 경우 [TeamsUpgradePolicy를 사용하여 TeamsOnly로의](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)전환을 관리합니다. 이는 사용자의 공존 모드를 제어합니다. 비즈니스용 Skype Server에서 프레미스 계정이 있는 사용자의 경우 클라우드로 이동하는 `Move-CsUser` [데도 사용할 수 있습니다.](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  각 모드에 대한 자세한 내용은 공존 모드 [를 참조하세요.](migration-interop-guidance-for-teams-with-skype.md)

> [!NOTE]
> 현재 비즈니스용 Skype Online 커넥터를 사용하여 서비스를 관리하는 경우 Teams PowerShell 모듈로 이동하고 기존 PowerShell 스크립트를 업데이트해야 합니다. 자세한 [내용은 비즈니스용 Skype Online 커넥터에서 Teams PowerShell](teams-powershell-move-from-sfbo.md) 모듈로 이동을 참조하세요.

비즈니스용 Skype 모드를 사용하여 선택 기능 전환을 수행하거나 기본 아일랜드 구성에서 TeamsOnly 모드로 업그레이드하는 경우 TeamsUpgradePolicy는 이미 비즈니스용 Skype Online이 있는 사용자를 위한 기본 도구입니다. Teams의 다른 정책과 마찬가지로 TeamsUpgradePolicy를 사용자에게 직접 할당할 수 있습니다. 정책을 테넌트 전체 기본값으로 설정할 수도 있습니다. 사용자에 대한 할당은 테넌트 기본 설정보다 우선합니다.  Teams 관리 콘솔 및 PowerShell에서 정책을 관리할 수 있습니다.

TeamsOnly 모드를 제외한 TeamsUpgradePolicy의 모든 모드를 비즈니스용 Skype온-프레미스에 있는 사용자에게 할당할 수도 있습니다. **TeamsOnly 모드는** 비즈니스용 Skype Online에 이미 있는 사용자에게만 할당할 수 있습니다. 비즈니스용 Skype 사용자 및 페더전화 및 Microsoft 365 Phone System 기능과 상호 운영할 수 있기 때문에 사용자가 비즈니스용 Skype Online에 있는 경우만 가능합니다. 또한 비즈니스용 Skype 온-프레미스 배포가 있는 경우 **TeamsOnly** 모드를 테넌트 전체 기본값으로 할당할 수 없습니다(Office 365가외의 위치를 지정하는 lyncdiscover DNS 레코드가 있는 경우 감지).

비즈니스용 Skype 계정이 있는 사용자는 [](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 비즈니스용 Skype온-프레미스 도구 Move-CsUser 사용하여 온라인으로 이동해야 합니다. 이러한 사용자는 1 또는 2단계에서 TeamsOnly로 이동할 수 있습니다.

-   1단계: Move-CsUser에서 -MoveToTeams 스위치를 지정합니다. 이렇게 하려면 비즈니스용 Skype Server 2019 또는 CU8 이상이 있는 비즈니스용 Skype Server 2015가 필요합니다.

-   2단계: Move-CsUser를 실행한 후 TeamsUpgradePolicy를 사용하여 사용자에게 TeamsOnly 모드를 부여합니다.

다른 정책과 달리 Microsoft 365 또는 Office 365에서 TeamsUpgradePolicy의 새 인스턴스를 만들 수 없습니다. 모든 기존 인스턴스는 서비스에 기본 제공됩니다.  (모드는 정책 인스턴스의 이름이 아닌 TeamsUpgradePolicy 내의 속성입니다.) 일부에서는 그렇지만 모든 경우에서는 정책 인스턴스의 이름이 모드와 동일합니다. 특히 TeamsOnly 모드를 사용자에게 할당하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 해당 사용자에게 부여합니다. 모든 인스턴스 목록을 표시하기 위해 다음 명령을 실행할 수 있습니다.

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

온라인 사용자를 TeamsOnly 모드로 업그레이드하려면 "UpgradeToTeams" 인스턴스를 할당합니다. 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

비즈니스용 Skype 사용자를 TeamsOnly 모드로 업그레이드하려면 Move-CsUser 도구세트에서 다음을 사용합니다.

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

테넌트의 모든 사용자에 대한 모드를 변경하기 위해 사용자당 명시적 부여(우선 순위)가 있는 사용자를 제외하고는 다음 명령을 실행합니다.

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>비즈니스용 Skype 계정이 있는 사용자가 있는 경우 테넌트 수준에서 TeamsOnly 모드를 할당할 수 없습니다. Move-CsUser를 사용하여 이러한 사용자를 클라우드로 개별적으로 이동해야 합니다.


## <a name="using-notifications-in-skype-for-business-clients"></a>비즈니스용 Skype 클라이언트에서 알림 사용

관리자는 비즈니스용 Skype 클라이언트에서 최종 사용자 알림을 제공하여 사용자에게 다음 다이어그램과 같이 곧 Teams로 업그레이드될 것 을 알릴 수 있습니다. 예를 들어 관리자가 사용자 그룹을 TeamsOnly 모드로 업그레이드하기 일주일 전에 관리자는 해당 사용자 그룹에 대한 이러한 알림을 켜야 할 수 있습니다. 이러한 알림은 NotificationSfbUsers=true와 TeamsUpgradePolicy의 인스턴스를 사용하여 사용하도록 설정됩니다.  TeamsOnly를 다른 모든 모드의 경우, 실제로는 NotifySfbUsers의 두 값에 해당하는 모드당 두 개의 인스턴스가 있습니다.  TeamsOnly를 다른 모든 모드의 경우, 실제로는 NotifySfbUsers의 두 값에 해당하는 모드당 두 개의 인스턴스가 있습니다. 

![알림을 보여주는 다이어그램](media/teams-upgrade-sfb-with-notifications.png)

사용자가 비즈니스용 Skype Online에 있는 경우 사용자와 동일한 모드가 있지만 NotifySfbUsers=true인 정책 인스턴스를 할당하기만 합니다. 

사용자가 비즈니스용 Skype 서버 온라인 프레미스에 있는 경우, 비즈니스용 Skype 서버 2019 또는 비즈니스용 Skype Server 2015용 CU8을 사용해야 합니다. 비즈니스용 Skype Server온-프레미스에 있는 사용자의 경우 TeamsUpgradePolicy의 온라인 인스턴스의 모드 속성은 존중되지만, NotifySfbUsers 속성은 그렇지 않습니다. 알림이 필요한 경우 클라이언트 동작을 제어하려면 TeamsUpgradePolicy의 프레미스 인스턴스를 만들어야 합니다. 

On-Premises PowerShell 창에서 NotifySfbUsers=true를 사용하여 TeamsUpgradePolicy의 새 인스턴스를 만드십시오.

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

그런 다음 동일한 On-Premises PowerShell 창을 사용하여 원하는 사용자에게 해당 새 정책을 할당합니다.

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>모임 마이그레이션

사용자가 TeamsOnly 모드로 마이그레이션되는 경우 기본적으로 사용자가 구성한 기존 비즈니스용 Skype 모임이 Teams로 변환됩니다. 사용자에게 TeamsOnly 모드를 할당할 때 기본 동작을 선택적으로 사용하지 않도록 설정할 수 있습니다. 사용자를온-프레미스에서 이동하는 경우 모임을 클라우드로 마이그레이션하여 온라인 사용자 계정으로 작동해야 하지만 -MoveToTeams를 지정하지 않으면 모임이 Teams로 변환되지 않고 비즈니스용 Skype 모임으로 마이그레이션됩니다. 

테넌트 수준에서 TeamsOnly 모드를 할당하는 경우 모든 사용자에 대해 모임 마이그레이션이 트리거되지 않습니다. 테넌트 수준에서 TeamsOnly 모드를 할당하고 모임을 마이그레이션하려는 경우 PowerShell을 사용하여 테넌트의 사용자 목록을(예: 필요한 필터와 함께 Get-CsOnlineUser 사용) 각 사용자를 반복하여 Start-CsExMeetingMigration을 사용하여 모임 마이그레이션을 트리거할 수 있습니다. 자세한 내용은 [MMS(모임 마이그레이션 서비스) 사용을 참조합니다.](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>관련 링크

[공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간에 하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

