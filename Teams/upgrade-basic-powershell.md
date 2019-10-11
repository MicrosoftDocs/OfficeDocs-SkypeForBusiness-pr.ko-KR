---
title: 기본 업그레이드 PowerShell | Microsoft 팀 | 업그레이드 Interop 정책 부여
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 관리자 센터가 테 넌 트에서 켜져 있지 않은 경우 팀으로 업그레이드 하기 Stopgap
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 397cabcbba35c153d234bc4355d12e4eb44b5c57
ms.sourcegitcommit: de7e0afbd40bbe52994ab99d85cf9e95ecbc4a6c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435092"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>비즈니스용 Skype Online에서 Microsoft 팀으로 사용자 업그레이드

> [!Note]
> 이 문서에서 설명 하는 명령은 [업그레이드 기본](https://aka.ms/UpgradeBasic) 검사 목록의 일부로 사용할 수 있도록 디자인 되었습니다.

업그레이드의 기술적 마이그레이션 측면은 비즈니스용 Skype가 팀으로 업그레이드 되는 것을 사용자에 게 알리고 **팀 전용** 모드로 전환 하는 것입니다. 이러한 단계는 비즈니스용 Skype 원격 Windows PowerShell 세션 또는 Microsoft 팀 관리 센터를 통해 수행할 수 있습니다.

[Microsoft 팀 관리 센터](manage-teams-skypeforbusiness-admin-center.md)에서 업그레이드 도구를 적극적으로 배포 하 고 있으며, 테 넌 트에서 곧 사용할 수 있어야 합니다. 사용할 수 있게 되 면 사용자를 마이그레이션하는 방법에 대 한 자세한 내용을 확인 하 [고 공존 및 업그레이드 설정을 설정할](https://aka.ms/SkypeToTeams-SetCoexistence)수 있습니다.

지금 업그레이드할 준비가 되었으면 다음 표에 나열 된 [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 명령을 사용할 수 있습니다.

| 기본 업그레이드 단계 # | 모드 | PowerShell 명령 |
|---|---|---|
| [5mb](upgrade-basic.md#step-5) | Islands + 비즈니스용 Skype 사용자에 게 알림<br>(사용자가 현재 **제도** 모드에 있는 경우 (기본값)이 명령을 사용 합니다.) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(예: $SipAddress = ' TestUser@contoso.com ')* |
| [5mb](upgrade-basic.md#step-5) | 비즈니스용 skype 전용 + 비즈니스용 Skype 사용자에 게 알림 <br>(사용자가 현재 **비즈니스용 Skype 전용** 모드일 때이 명령 사용) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | 팀만 | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
