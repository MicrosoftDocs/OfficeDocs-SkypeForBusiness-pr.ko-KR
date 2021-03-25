---
title: 기본 업그레이드 PowerShell| Microsoft Teams| 업그레이드 Interop 정책 부여
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 관리 센터가 테넌트에 켜지 않은 경우 Microsoft Teams로 업그레이드하기 위한 중지gap에 대해 자세히 알아보습니다.
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
ms.openlocfilehash: ef164ee5d93cb5491923ef3b319ae51134924cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120546"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>비즈니스용 Skype Online에서 Microsoft Teams로 사용자 업그레이드

> [!Note]
> 이 문서에 설명된 명령은 업그레이드 기본 검사 목록의 일부로 사용할 [수](./upgrade-start-here.md) 있도록 디자인되어 있습니다.

업그레이드의 기술 마이그레이션 측면에는 비즈니스용 Skype가 Teams로 업그레이드된 다음 팀 전용 모드로 전환할 것 을 사용자에게 **알릴 수** 있습니다. 이러한 단계는 비즈니스용 Skype 원격 Windows PowerShell 또는 Microsoft Teams 관리 센터를 통해 수행할 수 있습니다.

[Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)관리 센터에서 업그레이드 도구를 적극적으로 롤아웃하고 있으며 테넌트에서 곧 사용할 수 있습니다. 사용 가능한 즉시 공존 및 업그레이드 설정 설정에서 사용자를 마이그레이션하는 방법을 [찾을 수 있습니다.](./setting-your-coexistence-and-upgrade-settings.md)

오늘 업그레이드할 준비가 된 경우 다음 표에 나열된 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 명령을 사용할 수 있습니다.

| 기본 단계 업그레이드 # | 모드 | PowerShell 명령 |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands + 비즈니스용 Skype 사용자에게 알리기<br>(사용자가 현재 **Islands** 모드(기본값)에 있는 경우 이 명령을 사용) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(예: $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | 비즈니스용 Skype 전용 + 비즈니스용 Skype 사용자에게 알리기 <br>(사용자가 현재 **비즈니스용 Skype** 전용 모드인 경우 이 명령을 사용하세요. | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Only | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |