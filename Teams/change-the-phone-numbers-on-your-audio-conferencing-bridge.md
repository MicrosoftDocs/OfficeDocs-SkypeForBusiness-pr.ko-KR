---
title: 오디오 회의 브리지에서 전화 번호 변경
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 사용자의 범위를 확장하기 위해 전화 회의 브리지에 새 서비스 전화 번호를 할당하는 데 필요한 단계를 알아보십시오.
ms.openlocfilehash: 7f9efd4289f24b4248cddd732773d7c96e728f0c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918754"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>오디오 회의 브리지에서 전화 번호 변경

오디오 **회의** 라이선스를 구입하면 Microsoft에서 조직의 오디오 회의 브리지를 호스팅합니다. 오디오 회의 브리지는 모임 이끌이와 참가자가 전화기를 사용하여 비즈니스용 Skype 또는 Microsoft Teams 모임에 참가할 수 있도록 여러 위치에서 전화 접속 전화 번호를 제공합니다.
  
회의 브리지에 이미 할당된 전화 번호 외에도 다른 [](/microsoftteams/getting-service-phone-numbers) 위치에서 추가 서비스 번호(오디오 회의에 사용되는 무료 번호)를 확인한 다음 회의 브리지에 할당하여 사용자에 대한 적용 범위를 확장할 수 있습니다.
  
> [!NOTE]
> 회의 브리지의 전화 번호를 할당/할당을 해지하려면 전화 번호가 *'서비스'* 번호가 되어야 합니다. Microsoft Teams 관리 센터에서 음성 전화 번호로 찾아 번호 유형 열을 보고 번호 유형을 볼  >   **수** 있습니다. 사용자가 무료 번호로 브리지에 전화를 걸 수 있도록 Microsoft 365 또는 Office 365 통신 크레딧을 먼저 설정해야 합니다.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>전화 회의 브리지에 새 서비스 전화 번호를 할당하는 단계

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>1단계 - 오디오 회의 브리지에 새 전화 번호 할당

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **음성** 전화  >  **번호로 이동**

2. 목록에서 전화 번호를 선택하고 편집을 **클릭합니다.**

3. 편집 페이지의 **[할당]** 아래에서 드롭다운을 확장한 다음 회의 브리지    >  **적용을 선택합니다.**

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>2단계 - 전화 회의 브리지의 기본 전화 번호 변경(선택 사항)

전화 회의 브리지의 기본 전화 번호는 모임 내에서 참가자 또는 이끌이가 아웃바운드 통화를 걸 때 사용할 발신자 ID를 정의합니다.

서비스 에일리 번호만 회의 브리지의 기본 번호로 설정할 수 있습니다. **서비스 무료 번호는** 회의 브리지의 기본 번호로 설정할 수 없습니다. 서비스 LL 번호를 할당하고 오디오 회의 브리지의 새 기본 번호로 설정하는 경우 다음 단계를 수행합니다.

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 모임 회의  >  **브리지로 이동**

2. 기본값으로 구성하려는 서비스 에지 번호를 강조합니다.

3. 기본값으로 **설정 선택**
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>3단계 - 사용자의 모임 초대에 포함된 기본 전화 번호 변경(선택 사항)

사용자의 기본 전화 번호는 모임을 예약할 때 모임 초대에 포함된 전화 번호입니다. 새 사용자에 대해 기본 전화 번호가 할당되는 방법을 비롯한 자세한 내용은 [Microsoft Teams의](set-the-phone-numbers-included-on-invites-in-teams.md) 초대에 포함된 전화 번호 설정 또는 비즈니스용 [Skype Online의](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)초대에 포함된 전화 번호 설정을 참조하세요.

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 사용자로  이동하고 목록에서 원하는 사용자의 표시 이름을 클릭합니다.

2. 오디오 회의 옆에 **있는** 편집을 **클릭합니다.**

3. 무료 **전화** 번호 또는 무료 번호 아래의 드롭다운에서 번호를 선택하고 적용을 **클릭합니다.**

변경 내용이 적용된 후 다음에 새 모임을 예약할 때 이끌이의 모임 초대에 새 기본 전화 번호가 포함됩니다.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>4단계 - 모임 마이그레이션 서비스를 사용하여 사용자의 기존 모임 초대 업데이트(선택 사항)

다음 두 단계의 경우 다음 단계를 시작해야 Windows PowerShell.
  
일부 또는 전체 사용자의 모임 초대에 포함된 기본 전화 번호를 업데이트한 경우 모임 마이그레이션 서비스를 사용하여 기본 전화 번호가 변경되기 전에 조직의 사용자에게 이미 전송된 모임 초대를 선택적으로 업데이트할 수 있습니다. 자세한 내용은 [MMS(모임 마이그레이션 서비스) 설정을 참조하세요.](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
  
- 2단계에서 기본 전화 번호가 변경된 사용자에 대해 MMS(모임 마이그레이션 서비스)를 실행합니다. 이를 위해 다음 명령을 실행합니다.

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 모임 마이그레이션 상태를 볼 수도 있습니다. 보류 중 또는 진행 중 상태인 작업이 없는  경우 모든 모임이 다시 *예약됩니다.*

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>회의 브리지에 대한 서비스 전화 번호를 부재 중일 때의 단계


회의 브리지에서 전화 번호를 재할당을 해지하면 사용자는 더 이상 해당 전화 번호를 사용하여 모임에 참가할 수 없습니다. 전화 번호가 변경되기 때문에 전화 번호를 기본 번호(있는 경우)로 사용할 수 있는 모든 사용자를 업데이트하고 오디오 회의 브리지에서 전화 번호가 지정되지 않은 경우 기존 모임 초대를 업데이트해야 합니다.

사용자 및 해당 모임을 업데이트하지 않고 전화 번호가 제거되면 기존 모임 초대에 모임에 참가할 수 없는 전화 번호가 포함될 수 있습니다.

처음 세 단계의 경우 다음 단계를 시작해야 Windows PowerShell. 이 작업을 하는 방법을 보려면 다음을 사용하여 관리 방법을 알고 [Windows PowerShell.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>1단계 - 전화 번호를 지정하지 않은 사용자를 기본 번호 중 하나로 업데이트합니다.

번호가 지정되지 않은 모든 사용자의 기본 통행료 또는 무료 번호를 기본 번호로 바꾸고 모임을 다시 진행하는 프로세스를 시작하십시오. 이를 위해 다음 명령을 실행합니다.

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >Microsoft Teams 관리 센터에서 기본 무료 사용자 수를 변경할 수도 있습니다. 그러나 모임을 자동으로 다시 조정하지는 않습니다. 
 
 자세한 내용은 [Microsoft Teams의](set-the-phone-numbers-included-on-invites-in-teams.md) 초대에 포함된 전화 번호 설정 또는 비즈니스용 Skype Online의 초대에 포함된 전화 번호 [설정을 참조하세요.](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

  > [!NOTE]
  > 조직의 크기에 따라 완료하는 데 다소 시간이 걸릴 수 있습니다.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>2단계 - 다음을 사용하여 모임 마이그레이션 상태 Windows PowerShell

보류 중 또는 진행 중 상태인 작업이 없는  경우 모든 모임이 다시 *예약됩니다.*

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

모임 마이그레이션 서비스에 대한 자세한 내용은 [MMS(모임](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)마이그레이션 서비스) 설정을 참조하세요.
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>3단계 - 오디오 회의 브리지에서 이전 전화 번호의 이전 전화 번호의 재할당을 해지합니다.

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 모음에서 **음성** 전화  >  **번호로 이동**

2. 전화 번호가 무료 번호인 경우 목록에서 전화 번호를 선택하고 릴리스를 **클릭합니다.** 전화 번호가 통행료 번호인 경우 [Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) 지원에 문의하여 전화 번호를 미지정합니다.

3. 전화 번호가 무료 번호인 경우 확인 창에서 **예를** 클릭합니다.

   > [!IMPORTANT]
   > 오디오 회의 브리지에서 전화 번호가 부재 중이면 사용자가 새 모임이나 기존 모임에 참가할 수 없는 전화 번호가 더 이상 제공되지 않습니다.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>다음을 Windows PowerShell 준비가 됐는지 확인

 다음 단계에서는 버전 3.0 Windows PowerShell 실행 중인지 검사합니다.

1. 시작 **메뉴를**  >  **Windows PowerShell.**

2. 버전 확인을 위해  Windows PowerShell _Get-Host를_ 입력합니다.

3. 버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell. 버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다.
메시지가 표시될 때 컴퓨터를 다시 시작합니다.

4. 또한 비즈니스용 Skype Online에 Windows PowerShell 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online용 Windows PowerShell 모듈을 설치해야 합니다. 이 모듈은 64비트 컴퓨터에서만 지원하며 비즈니스용 Skype Online용 Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 [다운로드할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)
메시지가 표시될 경우 컴퓨터를 다시 시작합니다.

자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://technet.microsoft.com/library/dn568015.aspx)

### <a name="to-start-windows-powershell"></a>시작 Windows PowerShell

 **세션 Windows PowerShell 시작**

1. 시작 **메뉴에서**  >  **Windows PowerShell.**

2. 다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.

> [!NOTE]
> 비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.
>
> 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> 비즈니스용 Skype Online  모듈을 처음 사용하는 경우 모듈 가져오기 명령을 Windows PowerShell 합니다.
Windows PowerShell 시작하는 데 대한 자세한 내용은 단일 Windows PowerShell 창에서 모든 [Microsoft 365 또는 Office 365](https://technet.microsoft.com/library/dn568015.aspx) 서비스에 연결하거나 [Windows PowerShell.](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)

### <a name="save-time-and-automate"></a>시간 절약 및 자동화

이 프로세스를 자동화하여 시간을 절약하기 위해 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) 또는 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용할 수 있습니다.

- [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet을 사용하여 특정 사용자의 기본 무료 또는 무료 번호를 변경합니다.

  - 사용자의 기본 무료 번호를 변경하기 위해 다음을 실행합니다.

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용하여 원래 기본 번호 또는 해당 위치에 따라 기본 무료 사용자 수를 변경합니다.

    > [!NOTE]
    > BridgeID를 찾으면 **Get-CsOnlineDialInConferencingBridge를 사용 합니다.**

  - 8005551234로 설정하지 않은 모든 사용자의 기본 무료 번호를 설정하고 다음을 실행합니다.

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 기본 무료 번호로 8005551234가 있는 모든 사용자의 기본 무료 번호를 8005551239로 변경하고 모임을 자동으로 다시 조정하기 위해 다음을 실행합니다.

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 미국에 있는 모든 사용자의 기본 무료 수를 8005551234로 설정하고 모임을 자동으로 다시 조정하기 위해 다음을 실행합니다.

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 위에서 사용된 위치는 Microsoft 365 관리 센터에 설정된 사용자의 연락처 정보와 일치해야 합니다.

## <a name="troubleshooting"></a>문제 해결

**선택 안 하여 단추를 사용할 수 없습니다.**

번호의 배정을 해지하고 단추를 사용할 수 없습니다. 단추를 마우스로 이동하는 동안 지원에 "기본 또는 공유 번호는 브리지에서 지정을 해지할 수 _없습니다. 전용 통행료_ 번호를 부과하지 않는 경우 고객 지원에 문의하시기 바랍니다. ".

브리지에 대한 자세한 정보를 얻은 다음 Powershell을 실행합니다.
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

결과에는 ID, 이름 및 지역과 같은 다른 정보 외에도 DefaultServiceNumber가 포함되어야 합니다.

**예를** 들어, 지정을 해지하기 위해 DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>자세한 Windows PowerShell

이 Windows PowerShell 사용자 및 사용자가 할 수 있는 작업 또는 허용되지 않는 작업을 관리할 수 있습니다. Windows PowerShell 사용하면 특히 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.

  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.

  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>관련 항목
[오디오 회의 브리지의 설정 변경](change-the-settings-for-an-audio-conferencing-bridge.md)
