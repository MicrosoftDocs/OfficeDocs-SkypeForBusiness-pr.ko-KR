---
title: 오디오 회의 브리지에서 전화 번호 변경
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 사용자에 대한 적용 범위를 확장하기 위해 전화 회의 브리지에 새 서비스 전화 번호를 할당하는 데 필요한 단계를 알아봅니다.
ms.openlocfilehash: 0433577334dca5f84854ba1cdc14b81e4ec37e63
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674780"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>오디오 회의 브리지에서 전화 번호 변경

**오디오 회의** 라이선스를 구입하면 Microsoft에서 조직의 오디오 회의 브리지를 호스팅합니다. 오디오 회의 브리지는 모임 이끌이와 참가자가 전화를 사용하여 비즈니스용 Skype 참가하거나 Microsoft Teams 모임에 참가할 수 있도록 여러 위치에서 전화 접속 전화 번호를 제공합니다.

회의 브리지에 이미 할당된 전화 번호 외에도 다른 위치에서 [추가 서비스 번호](./getting-service-phone-numbers.md) (오디오 회의에 사용되는 유료 및 무료 번호)를 받고 회의 브리지에 할당하여 사용자에 대한 적용 범위를 확장할 수 있습니다.

> [!NOTE]
> 회의 브리지의 전화 번호를 할당하거나 할당 해제하려면 전화 번호가 '*서비스*' 번호여야 합니다. Microsoft Teams 관리 센터에서 **Voice** > **전화 숫자** 로 이동하고 **숫자 유형** 열을 확인하여 숫자 유형을 확인할 수 있습니다. 사용자가 무료 번호로 브리지에 전화하려면 먼저 Microsoft 365 또는 Office 365 Communications 크레딧을 설정해야 합니다.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>전화 회의 브리지에 새 서비스 전화 번호를 할당하는 단계

> [!NOTE]
> 그렇지 않으면 호출되는 경우를 제외하고 Microsoft Teams 관리 센터에서 이러한 모든 단계를 수행해야 합니다.

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>1단계 - 오디오 회의 브리지에 새 전화 번호 할당

1. 왼쪽 탐색 창에서 **Voice** > **전화 숫자** 로 이동합니다.

2. 목록에서 전화 번호를 선택하고 **편집** 을 클릭합니다.

3. **편집** 페이지의 **할당** 대상에서 드롭다운을 확장한 다음 **회의 브리지** > **적용** 을 선택합니다.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>2단계 - 컨퍼런스 브리지의 기본 전화 번호 변경(선택 사항)

회의 브리지의 기본 전화 번호는 모임 내에서 참가자 또는 이끌이가 아웃바운드 통화를 할 때 사용할 발신자 ID를 정의합니다.

서비스 통행료 번호만 회의 브리지의 기본 번호로 설정할 수 있습니다. **서비스 무료 번호는 회의 브리지의 기본 번호로 설정할 수 없습니다**. 서비스 요금 번호를 할당하고 오디오 회의 브리지의 새 기본 번호로 설정하려는 경우 다음 단계를 수행합니다.

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지** 로 이동합니다.

2. 기본값으로 구성하려는 서비스 통행료 번호를 강조 표시합니다.

3. **기본값으로 설정을** 선택합니다.

### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>3단계 - 사용자의 모임 초대에 포함된 기본 전화 번호 변경(선택 사항)

[Microsoft Teams 초대에 포함된 전화 번호 설정을](set-the-phone-numbers-included-on-invites-in-teams.md) 참조하세요.

> [!NOTE]
> *TeamsAudioconferencingpolicy* 에 전화 번호를 추가하고 사용자에게 정책을 할당하여 전화 번호를 설정할 수도 있습니다. 정책에 추가된 수신자 및 무료 전화 번호는 오디오 회의 설정 창을 통해 사용자에게 개별적으로 설정된 전화 번호보다 우선합니다. *Teamsaudioconferencingpolicy* 에 전화 번호가 추가되지 않으면 오디오 회의 설정 창을 통해 사용자에 대해 개별적으로 설정된 전화 번호가 Microsoft Teams 모임 요청에 표시됩니다. [유료 및 무료 번호에 대한 오디오 회의 정책 설정에는](audio-conferencing-toll-free-numbers-policy.md) 자세한 정보가 있습니다.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>4단계 - 모임 마이그레이션 서비스를 사용하여 사용자의 기존 모임 초대 업데이트(선택 사항)

다음 두 단계에서는 Windows PowerShell 시작해야 합니다.

일부 또는 모든 사용자의 모임 초대에 포함된 기본 전화 번호를 업데이트한 경우 필요에 따라 모임 마이그레이션 서비스를 사용하여 기본 전화 번호가 변경되기 전에 조직의 사용자에게 이미 전송된 모임 초대를 업데이트할 수 있습니다. 자세한 내용은 [MMS(모임 마이그레이션 서비스) 설정을](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) 참조하세요.

- 2단계에서 기본 전화 번호가 변경된 사용자에 대해 MMS(모임 마이그레이션 서비스)를 실행합니다. 이렇게 하려면 다음 명령을 실행합니다.

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 모임 마이그레이션 상태를 볼 수도 있습니다. *보류 중* 또는 *진행 중* 상태인 작업이 없으면 모든 모임의 일정이 조정됩니다.

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>회의 브리지에 대한 서비스 전화 번호를 할당 해제하는 단계

회의 브리지에서 전화 번호를 할당 해제하면 사용자는 더 이상 해당 전화 번호를 사용하여 모임에 참가할 수 없습니다. 전화 번호가 변경되기 때문에 전화 번호를 기본 번호(있는 경우)로 사용할 수 있는 모든 사용자를 업데이트하고 오디오 회의 브리지에서 전화 번호를 할당 해제하기 전에 기존 모임 초대를 업데이트하는 것이 중요합니다.

사용자와 모임을 업데이트하지 않고 전화 번호가 제거되면 기존 모임 초대에 모임 참가에 작동하지 않는 전화 번호가 포함될 수 있습니다.

처음 세 단계에서는 Windows PowerShell 시작해야 합니다. 이 작업을 수행하는 방법을 보려면 [Windows PowerShell 사용하여 관리하는 방법을 알고 싶으신가요?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>1단계 - 기본 번호 중 하나로 할당되지 않은 전화 번호가 있는 사용자 업데이트

번호를 기본 번호로 할당하지 않은 모든 사용자의 기본 통행료 또는 무료 번호를 바꾸고 모임 일정을 조정하는 프로세스를 시작합니다. 이렇게 하려면 다음 명령을 실행합니다.

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

 > [!IMPORTANT]
 >Microsoft Teams 관리 센터에서 기본 통행료 또는 무료 사용자 수를 변경할 수도 있습니다. 그러나 모임 일정을 자동으로 조정하지는 않습니다.

 자세한 내용은 [Microsoft Teams 초대에 포함된 전화 번호 설정 또는 비즈니스용 Skype](set-the-phone-numbers-included-on-invites-in-teams.md) [Online의 초대에 포함된 전화 번호 설정을 참조하세요](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites).

  > [!NOTE]
  > 조직의 크기에 따라 완료하는 데 다소 시간이 걸릴 수 있습니다.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>2단계 - Windows PowerShell 사용하여 모임 마이그레이션 상태 보기

*보류 중* 또는 *진행 중* 상태인 작업이 없으면 모든 모임의 일정이 조정됩니다.

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

모임 마이그레이션 서비스에 대한 자세한 내용은 [MMS(모임 마이그레이션 서비스) 설정을](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms) 참조하세요.

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>3단계 - 오디오 회의 브리지에서 이전 전화 번호 할당 해제

Unregister-CsOnlineDialInConferencingServiceNumber cmdlet을 사용하여 회의 브리지에서 수신자 또는 무료 번호 등록 취소

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```

참고: 컨퍼런스 브리지 ID를 찾으려면 다음 PowerShell: Get-CsOnlineDialInConferencingBridge를 실행합니다.

   > [!IMPORTANT]
   > 오디오 회의 브리지에서 전화 번호를 할당 해제하면 사용자가 새 모임이나 기존 모임에 참가할 수 있는 전화 번호가 더 이상 제공되지 않습니다.

### <a name="save-time-and-automate"></a>시간 절약 및 자동화

이 프로세스를 자동화하여 시간을 절약하려면 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) 또는 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용할 수 있습니다.

- [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet을 사용하여 특정 사용자의 기본 통행료 또는 무료 번호를 변경합니다.

  - 사용자의 기본 무료 번호를 변경하려면 다음을 실행합니다.

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용하여 원래 기본 번호 또는 해당 위치에 따라 기본 요금 또는 무료 사용자 수를 변경합니다.

    > [!NOTE]
    > BridgeID를 찾으려면 **Get-CsOnlineDialInConferencingBridge** 를 사용합니다.

  - 8005551234 없는 모든 사용자에 대한 기본 무료 번호를 설정하려면 다음을 실행합니다.

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 8005551234 기본 무료 번호로 8005551239 자동으로 모임 일정을 조정하는 모든 사용자의 기본 무료 번호를 변경하려면 다음을 실행합니다.

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 미국에 있는 모든 사용자의 기본 무료 번호를 8005551234 자동으로 모임 일정을 조정하도록 설정하려면 다음을 실행합니다.

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 위에서 사용되는 위치는 Microsoft 365 관리 센터 설정된 사용자의 연락처 정보와 일치해야 합니다.

## <a name="troubleshooting"></a>문제 해결

### <a name="the-unassign-button-isnt-available"></a>할당 해제 단추를 사용할 수 없음

숫자를 할당 취소하려고 하지만 단추를 사용할 수 없으며, 단추를 마우스로 가리키면 "기본 또는 공유 번호를 브리지에서 할당 해제할 수 없습니다. 전용 통행료 번호를 할당 취소하려면 지원에 문의하세요.".

브리지에 대한 자세한 정보를 얻으려면 다음 Powershell을 실행합니다.

```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

ID, 이름 및 지역과 같은 다른 정보를 제외하고 결과에는 DefaultServiceNumber도 포함되어야 합니다.

**예를** 들어 할당을 취소하려면 DefaultServiceNumber "8005551234"

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234
```

## <a name="about-windows-powershell"></a>Windows PowerShell 정보

Windows PowerShell 사용하여 사용자와 사용자가 수행할 수 있는 작업 또는 허용되지 않는 작업을 관리할 수 있습니다. Windows PowerShell 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 관리하고 비즈니스용 Skype Online을 관리하는 데 도움이 될 수 있습니다. Windows PowerShell 시작하려면 다음 항목을 참조하세요.

- [Windows PowerShell 및 비즈니스용 Skype Online 소개](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell 한 번에 많은 사용자에 대해 설정을 변경하는 경우와 같이 Microsoft 365 관리 센터 사용하는 것에 비해 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아봅니다.

- [Windows PowerShell 사용하여 Microsoft 365 또는 Office 365 관리하는 가장 좋은 방법](/previous-versions//dn568025(v=technet.10))

- [Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [Windows PowerShell 사용하여 일반적인 비즈니스용 Skype Online 관리 작업 수행](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>관련 항목

[오디오 회의 브리지의 설정 변경](change-the-settings-for-an-audio-conferencing-bridge.md)
