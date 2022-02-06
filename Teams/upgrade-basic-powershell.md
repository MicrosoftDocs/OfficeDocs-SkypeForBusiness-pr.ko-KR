---
title: 기본 업그레이드 PowerShell| Microsoft Teams| 업그레이드 Interop 정책 부여
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 관리 센터가 테넌트에 켜지 않은 경우 Microsoft Teams 업그레이드에 대한 중지gap에 대해 자세히 알아보습니다.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
  - CSH
ms.custom:
  - Teams-upgrade-guidance
  - seo-marvel-apr2020
ms.collection:
  - Teams_ITAdmin_JourneyFromSfB
  - M365-collaboration
appliesto:
  - Microsoft Teams
---

# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>사용자를 온라인에서 비즈니스용 Skype 업그레이드로 Microsoft Teams

> [!Note]
> 이 문서에 설명된 명령은 업그레이드 기본 검사 목록의 일부로 [사용할 수 있도록](./upgrade-start-here.md) 디자인되어 있습니다.

업그레이드의 기술 마이그레이션 측면은 사용자에 비즈니스용 Skype 업그레이드할 Teams 다음 사용자 전용 모드로 Teams **수** 있습니다. 이러한 단계는 원격 원격 비즈니스용 Skype 또는 Windows PowerShell 관리 센터를 통해 Microsoft Teams 수 있습니다.

관리 센터에서 업그레이드 도구를 적극적으로 Microsoft Teams 테넌트에서 곧 사용할 [](manage-teams-skypeforbusiness-admin-center.md)수 있습니다. 사용 가능한 즉시 공존 및 업그레이드 설정 설정에서 사용자 마이그레이션에 대한 정보를 [찾을 수 있습니다](./setting-your-coexistence-and-upgrade-settings.md).

오늘 업그레이드할 준비가 된 경우 다음 표에 나열된 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 명령을 사용할 수 있습니다.

| 기본 단계 업그레이드 # | 모드 | PowerShell 명령 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + 비즈니스용 Skype 사용자에게 알리기<br>(사용자가 현재 **Islands** 모드(기본값)에 있는 경우 이 명령을 사용) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(예: $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | 비즈니스용 Skype + 사용자에 비즈니스용 Skype 알림 <br>(사용자가 현재 전용 모드인 비즈니스용 Skype **이 명령을** 사용) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams 전용 | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |