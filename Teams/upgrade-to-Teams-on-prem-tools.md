---
title: 비즈니스용 Skype-프레미스 배포에서 Teams로 업그레이드 - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드 - 업그레이드 도구
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 952214d615b62d0175841e2c7b24b45f1ae2d2b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533575"
---
# <a name="tools-for-upgrading-to-teams-mdash-for-it-administrators"></a>IT 관리자용 Teams로 &mdash; 업그레이드하기 위한 도구

이 문서에서는 Teams로 업그레이드하기 위한 도구를 설명하고 있습니다. 이 문서는 IT 관리자를 위한 업그레이드 개념 및 구현을 설명하는 세 번째 문서입니다.  

- [개요](upgrade-to-teams-on-prem-overview.md)
- [업그레이드 방법](upgrade-to-teams-on-prem-upgrade-methods.md)
- **업그레이드를 관리하기 위한 도구(이**   문서)
- [비즈니스용 Skype가 있는 조직에 대한 추가 고려 사항](upgrade-to-teams-on-prem-considerations.md)
- [업그레이드 수행](upgrade-to-teams-on-prem-implement.md)
- [PSTN(공용 전환 전화 네트워크) 고려 사항](upgrade-to-teams-on-prem-pstn-considerations.md)

또한 다음 문서에서는 중요한 업그레이드 개념 및 공존 동작을 설명하고 있습니다.

- [Teams 및 비즈니스용 Skype의 공존](upgrade-to-teams-on-prem-coexistence.md)
- [공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="tools-for-managing-the-upgrade"></a>업그레이드를 관리하기 위한 도구

선택한 업그레이드 방법 중 비즈니스용 Skype Online이 이미 있는 사용자의 경우 사용자의 공존 모드를 제어하는 [TeamsUpgradePolicy를 사용하여 TeamsOnly로의](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)전환을 관리합니다. 비즈니스용 Skype Server에서 프레미스 계정이 있는 사용자의 경우 클라우드로 이동하는 `Move-CsUser` [데도 사용할 수 있습니다.](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)  각 모드에 대한 자세한 내용은 공존 모드를 [참조하세요.](migration-interop-guidance-for-teams-with-skype.md)  

비즈니스용 Skype 모드를 사용하여 선택 기능 전환을 수행하거나 기본 제도 구성에서 TeamsOnly 모드로 간단히 업그레이드하는 경우 TeamsUpgradePolicy는 이미 비즈니스용 Skype Online이 있는 사용자를 위한 기본 도구입니다. Teams의 다른 정책과 마찬가지로 TeamsUpgradePolicy를 사용자에게 직접 할당할 수 있습니다. 정책을 테넌트 전체 기본값으로 설정할 수도 있습니다. 사용자에 대한 할당은 테넌트 기본 설정보다 우선합니다.  Teams 관리 콘솔 및 PowerShell에서 정책을 관리할 수 있습니다.

TeamsOnly 모드를 제외한 TeamsUpgradePolicy의 모든 모드를 비즈니스용 Skype에 있는 사용자에게 할당할 수도 있습니다. **TeamsOnly 모드는** 이미 비즈니스용 Skype Online에 있는 사용자에게만 할당할 수 있습니다. 사용자가 비즈니스용 Skype Online에 있는 경우 비즈니스용 Skype 사용자 및 페더맹 및 Microsoft 365 전화 시스템 기능과의 상호 운영이 가능하기 때문에 가능합니다. 또한 비즈니스용 Skype 온-프레미스 배포가 있는 경우(Office 365가 아니라 다른 위치를 지정하는 lyncdiscover DNS 레코드가 있는 경우 감지되는 **경우) TeamsOnly** 모드를 테넌트 전체 기본값으로 할당할 수 없습니다.

비즈니스용 Skype 계정이 있는 사용자는 [](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 비즈니스용 Skype On-프레미스 도구 Move-CsUser 사용하여 온라인(비즈니스용 Skype Online 또는 Teams로 직접)으로 이동해야 합니다. 이러한 사용자는 1단계 또는 2단계에서 TeamsOnly로 이동할 수 있습니다.

-   1단계: Move-CsUser에서 -MoveToTeams 스위치를 지정합니다. 이렇게 하려면 비즈니스용 Skype Server 2019 또는 CU8 이상이 있는 비즈니스용 Skype Server 2015가 필요합니다.

-   2단계: Move-CsUser를 실행한 후 TeamsUpgradePolicy를 사용하여 사용자에게 TeamsOnly 모드를 부여합니다.

다른 정책과 달리 Microsoft 365 또는 Office 365에서 TeamsUpgradePolicy의 새 인스턴스를 만들 수 없습니다. 모든 기존 인스턴스가 서비스에 기본 제공됩니다.  (모드는 정책 인스턴스의 이름이 아닌 TeamsUpgradePolicy 내의 속성입니다.) 일부(모든 경우는 아는 것은 아는 경우)에서 정책 인스턴스의 이름은 모드와 동일합니다. 특히 사용자에게 TeamsOnly 모드를 할당하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 해당 사용자에게 부여합니다. 모든 인스턴스 목록을 표시하기 위해 다음 명령을 실행할 수 있습니다.

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

온라인 사용자를 TeamsOnly 모드로 업그레이드하려면 "UpgradeToTeams" 인스턴스를 할당합니다. 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

비즈니스용 Skype 사용자를 TeamsOnly 모드로 업그레이드하려면 Move-CsUser 도구 Move-CsUser 다음을 사용합니다.

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

테넌트의 모든 사용자에 대한 모드를 변경하기 위해 사용자당 명시적 권한 부여(우선 순위)가 있는 사용자를 제외하고는 다음 명령을 실행합니다.

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>비즈니스용 Skype 계정이 있는 사용자가 있는 경우 테넌트 수준에서 TeamsOnly 모드를 할당할 수 없습니다. Move-CsUser를 사용하여 이러한 사용자를 개별적으로 클라우드로 이동해야 합니다.


## <a name="using-notifications-in-skype-for-business-clients"></a>비즈니스용 Skype 클라이언트에서 알림 사용

관리자는 비즈니스용 Skype 클라이언트에서 최종 사용자 알림을 제공하여 사용자에게 다음 다이어그램과 같이 곧 Teams로 업그레이드될 것 같다는 알림을 제공할 수 있습니다. 예를 들어 관리자가 사용자 그룹을 TeamsOnly 모드로 업그레이드하기 1주일 전에 관리자는 해당 사용자 그룹에 대해 이러한 알림을 설정해야 할 수 있습니다. 이러한 알림은 NotifySfbUsers=true와 함께 TeamsUpgradePolicy의 인스턴스를 사용하여 활성화됩니다.  TeamsOnly 외의 모든 모드에는 NotifySfbUsers의 두 값에 해당하는 모드당 두 개의 인스턴스가 실제로 있습니다.  TeamsOnly 외의 모든 모드에는 NotifySfbUsers의 두 값에 해당하는 모드당 두 개의 인스턴스가 실제로 있습니다. 

![알림을 보여주는 다이어그램](media/teams-upgrade-sfb-with-notifications.png)

사용자가 비즈니스용 Skype Online에 있는 경우 사용자와 동일한 모드의 정책 인스턴스를 NotifySfbUsers=true로 할당하면 됩니다. 

사용자가 비즈니스용 Skype Server의 프레미스에 있는 경우, 비즈니스용 Skype Server 2019 또는 비즈니스용 Skype Server 2015용 CU8이 필요합니다. 비즈니스용 Skype Server에 있는 사용자의 경우 TeamsUpgradePolicy의 온라인 인스턴스에서 모드 속성이 사용되지만 NotifySfbUsers 속성은 사용할 수 없습니다. 알림이 필요한 경우 TeamsUpgradePolicy의 프레미스 인스턴스를 만들어 클라이언트 동작을 제어해야 합니다. 

On-premises PowerShell 창에서 NotifySfbUsers=true를 사용하여 TeamsUpgradePolicy의 새 인스턴스를 만드십시오.

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

그런 다음, 동일한 On-premises PowerShell 창을 사용하여 원하는 사용자에게 새 정책을 할당합니다.

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

## <a name="meeting-migration"></a>모임 마이그레이션

사용자가 TeamsOnly 모드로 마이그레이션된 경우 기본적으로 사용자가 구성한 기존 비즈니스용 Skype 모임은 Teams로 변환됩니다. 선택적으로 사용자에게 TeamsOnly 모드를 할당할 때 기본 동작을 사용하지 않도록 설정할 수 있습니다. 사용자를 프레미스에서 이동할 때 온라인 사용자 계정으로 작동하려면 모임을 클라우드로 마이그레이션해야 하지만 -MoveToTeams를 지정하지 않으면 모임이 Teams로 변환되는 대신 비즈니스용 Skype 모임으로 마이그레이션됩니다. 

테넌트 수준에서 TeamsOnly 모드를 할당할 때 사용자에 대해 모임 마이그레이션이 트리거되지 않습니다. 테넌트 수준에서 TeamsOnly 모드를 할당하고 모임을 마이그레이션하려는 경우 PowerShell을 사용하여 테넌트의 사용자 목록(예: 필요한 필터와 함께 Get-CsOnlineUser 사용)을 수행한 다음 이러한 각 사용자를 반복하여 Start-CsExMeetingMigration을 사용하여 모임 마이그레이션을 트리거할 수 있습니다. 자세한 내용은 [MMS(모임 마이그레이션 서비스) 사용을 참조합니다.](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)



## <a name="related-links"></a>관련 링크

[비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype Server와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

