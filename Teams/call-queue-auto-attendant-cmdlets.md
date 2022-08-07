---
title: 자동 전화 교환 및 통화 큐에 대한 PowerShell cmdlet 참조
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Phone System
- seo-marvel-apr2020
description: Microsoft Teams에서 자동 전화 교환 및 통화 큐를 만들고 관리하려면 PowerShell cmdlet에 대한 이 문서를 참조하세요.
ms.openlocfilehash: 7970a3c8199060d73d68e5f94c28dfe836688189
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269411"
---
# <a name="powershell-cmdlet-reference-for-auto-attendants-and-call-queues"></a>자동 전화 교환 및 통화 큐에 대한 PowerShell cmdlet 참조

다음 cmdlet 참조는 Microsoft Teams 자동 전화 교환 및 통화 큐에 대한 것입니다.

## <a name="auto-attendant-cmdlets"></a>자동 전화 교환 cmdlet

다음 cmdlet을 사용하면 자동 전화 교환을 관리할 수 있습니다.

- [New-CsAutoAttendant](/powershell/module/skype/new-csautoattendant)  
- [Get-CsAutoAttendant](/powershell/module/skype/get-csautoattendant)
- [Set-CsAutoAttendant](/powershell/module/skype/set-csautoattendant)
- [Update-CsAutoAttendant](/powershell/module/skype/update-csautoattendant)
- [Remove-CsAutoAttendant](/powershell/module/skype/remove-csautoattendant)
- [New-CsOnlineTimeRange](/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantHolidays](/powershell/module/skype/get-csautoattendantholidays)
- [Import-CsAutoAttendantHolidays](/powershell/module/skype/import-csautoattendantholidays)
- [Export-CsAutoAttendantHolidays](/powershell/module/skype/export-csautoattendantholidays)
- [New-CsAutoAttendantDialScope](/powershell/module/skype/New-CsAutoAttendantDialScope)
- [New-CsAutoAttendantPrompt](/powershell/module/skype/New-CsAutoAttendantPrompt)
- [New-CsAutoAttendantCallableEntity](/powershell/module/skype/New-CsAutoAttendantCallableEntity)
- [New-CsAutoAttendantMenuOption](/powershell/module/skype/New-CsAutoAttendantMenuOption)
- [New-CsAutoAttendantMenu](/powershell/module/skype/new-csautoattendantmenu)
- [New-CsAutoAttendantCallFlow](/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [New-CsAutoAttendantCallHandlingAssociation](/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantStatus](/powershell/module/skype/Get-CsAutoAttendantStatus)
- [Get-CsAutoAttendantTenantInformation](/powershell/module/skype/Get-CsAutoAttendantTenantInformation)

PowerShell을 사용하여 자동 전화 교환을 만드는 단계별 가이드는 [PowerShell cmdlet을 사용하여 자동 전화 교환 만들기를 참조하세요.](create-a-phone-system-auto-attendant-via-cmdlets.md)

## <a name="call-queue-cmdlets"></a>통화 큐 cmdlets

다음 cmdlet을 사용하면 통화 큐를 관리할 수 있습니다.

- [New-CsCallQueue](/powershell/module/skype/New-CsCallQueue)
- [Get-CsCallQueue](/powershell/module/skype/Get-CsCallQueue)
- [Set-CsCallQueue](/powershell/module/skype/Set-CsCallQueue)
- [Remove-CsCallQueue](/powershell/module/skype/Remove-CsCallQueue)

PowerShell을 사용하여 통화 큐를 만드는 단계별 가이드는 [PowerShell cmdlet을 사용하여 통화 큐 만들기를 참조하세요.](create-a-phone-system-call-queue-via-cmdlets.md)

## <a name="common-cmdlets-used-by-both-auto-attendants-and-call-queues"></a>자동 전화 교환 및 통화 큐에서 사용되는 일반적인 cmdlet

다음 cmdlet은 자동 전화 교환에 사용할 사용자, 리소스 계정, Microsoft Teams 전화 라이선스, 전화 번호, 오디오 파일 및 지원되는 언어를 관리하는 데도 필요합니다.

### <a name="users-and-teams"></a>사용자 및 팀

- 사용자
  - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- 팀:
  - [Get-Team](/powershell/module/teams/Get-Team)
  - [Get-TeamChannel](/powershell/module/teams/Get-TeamChannel)

### <a name="resource-accounts"></a>리소스 계정

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

### <a name="teams-phone-resource-account-licenses"></a>Teams 전화 리소스 계정 라이선스

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

### <a name="phone-number-assignment"></a>전화 번호 할당

- [Get-CsPhoneNumberAssignment](/powershell/module/teams/Get-CsPhoneNumberAssignment)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-CsPhoneNumberAssignment)

### <a name="audio-files"></a>오디오 파일

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

### <a name="support-languages-and-time-zones"></a>지원 언어 및 표준 시간대

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Get-CsAutoAttendantSupportedTimeZone](/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
