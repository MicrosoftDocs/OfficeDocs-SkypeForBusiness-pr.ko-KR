---
title: 기본 업그레이드 PowerShell| Microsoft Teams| 업그레이드 Interop 정책 부여
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 테넌트에서 관리 센터에 불이 켜지지 않은 경우 Microsoft Teams로 업그레이드하기 위한 중지에 대해 알아봅니다.
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
ms.openlocfilehash: 02ba32e5b498639e93bc10757c51429871f5683a
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606037"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>비즈니스용 Skype Online에서 Microsoft Teams로 사용자 업그레이드

> [!Note]
> 이 문서에 설명된 명령은 [기본 업그레이드](./upgrade-start-here.md) 검사 목록의 일부로 사용하도록 설계되었습니다.

업그레이드의 기술 마이그레이션 측면은 사용자에게 비즈니스용 Skype Teams로 업그레이드한 다음 **Teams 전용** 모드로 전환할 것임을 알리는 것을 수반합니다. 이러한 단계는 비즈니스용 Skype 원격 Windows PowerShell 세션 또는 Microsoft Teams 관리 센터를 통해 수행할 수 있습니다.

[Microsoft Teams 관리 센터에서](manage-teams-skypeforbusiness-admin-center.md) 업그레이드 도구를 적극적으로 배포하고 있으며 테넌트에서 곧 사용할 수 있습니다. 사용 가능한 즉시 [공존 설정 및 업그레이드 설정](./setting-your-coexistence-and-upgrade-settings.md)에서 사용자 마이그레이션에 대한 정보를 찾을 수 있습니다.

지금 업그레이드할 준비가 되면 다음 표에 나열된 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 명령을 사용할 수 있습니다.

| 기본 단계 업그레이드 # | 모드 | PowerShell 명령 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + 비즈니스용 Skype 사용자에게 알림<br>(사용자가 현재 **아일랜드** 모드(기본값)인 경우 이 명령을 사용합니다. | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(예: $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | 비즈니스용 Skype만 + 비즈니스용 Skype 사용자에게 알림 <br>(사용자가 현재 **비즈니스용 Skype 전용** 모드인 경우 이 명령을 사용합니다.) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams만 | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |