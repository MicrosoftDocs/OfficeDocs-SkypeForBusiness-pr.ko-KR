---
title: 기본 업그레이드 PowerShell| Microsoft Teams| 업그레이드 Interop 정책 부여
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 관리 센터가 테넌트에서 켜지 않은 경우 Microsoft Teams로 업그레이드하기 위한 중지gap에 대해 자세히 배워야 합니다.
localization_priority: Normal
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
ms.openlocfilehash: adb9a0854268df25ebb8dc0337db22f792834b36
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809098"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>비즈니스용 Skype Online에서 Microsoft Teams로 사용자 업그레이드

> [!Note]
> 이 문서에 설명된 명령은 업그레이드 기본 검사 목록의 일부로 사용할 [수](https://aka.ms/UpgradeBasic) 있도록 디자인되어 있습니다.

업그레이드의 기술 마이그레이션 측면은 사용자에게 비즈니스용 Skype가 Teams로 업그레이드했다가 Teams 전용 모드로 전환된다고 **알리는 것입니다.** 이러한 단계는 비즈니스용 Skype 원격 Windows PowerShell 세션 또는 Microsoft Teams 관리 센터를 통해 수행할 수 있습니다.

[Microsoft](manage-teams-skypeforbusiness-admin-center.md)Teams 관리 센터에서 업그레이드 도구를 적극적으로 출시하고 있으며 테넌트에서 곧 사용할 수 있습니다. 사용 가능한 즉시 공존 및 업그레이드 설정 설정에서 사용자 마이그레이션에 대한 정보를 [찾을 수 있습니다.](https://aka.ms/SkypeToTeams-SetCoexistence)

지금 업그레이드할 준비가 된 경우 다음 표에 나열된 [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 명령을 사용할 수 있습니다.

| 기본 단계 업그레이드 # | 모드 | PowerShell 명령 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + 비즈니스용 Skype 사용자에게 알림<br>(사용자가 현재 제도 모드(기본값)에 있는 경우 이 명령을 사용  | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(예: $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | 비즈니스용 Skype만 + 비즈니스용 Skype 사용자에게 알림 <br>(사용자가 현재 비즈니스용 Skype 전용 모드인 경우 이 **명령을** 사용하세요.) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams만 해당 | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
