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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 오디오 회의 라이선스를 구입 하는 경우 Microsoft는 조직에 대 한 오디오 회의 브리지를 호스팅 하 고 있습니다. 오디오 회의 브리지는 다른 위치에서 전화 접속 전화 번호를 제공 하므로 모임 이끌이 및 참가자가 휴대폰을 사용 하 여 비즈니스용 Skype 또는 Microsoft 팀 모임에 참가 하는 데 사용할 수 있습니다.
ms.openlocfilehash: 9c4d16f3f68e190549b1e8a1d7b6f3f03e8a44c6
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516966"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>오디오 회의 브리지에서 전화 번호 변경

**오디오 회의** 라이선스를 구입 하는 경우 Microsoft는 조직에 대 한 오디오 회의 브리지를 호스팅 하 고 있습니다. 오디오 회의 브리지는 다른 위치에서 전화 접속 전화 번호를 제공 하 여 모임 이끌이 및 참가자가 휴대폰을 사용 하 여 비즈니스용 Skype 또는 Microsoft 팀 모임에 참가할 수 있도록 합니다.
  
이미 회의 브리지에 지정 된 전화번호 외에도 다른 위치에서 [추가 서비스 번호](/microsoftteams/getting-service-phone-numbers) (오디오 회의에 사용 되는 유료 및 무료 번호)를 가져온 다음이를 회의 브리지에 할당 하 여 다음을 수행할 수 있습니다. 사용자에 대 한 검사 범위를 확장 합니다.
  
> [!NOTE]
> 회의 브리지의 전화 번호를 할당/할당 취소 하려면 전화 번호가 '*서비스*' 번호 여야 합니다. 이전 포털에서 **음성** > **전화 번호로** 이동 하 여 **번호 형식** 열을 보면 번호 형식을 볼 수 있습니다. 사용자가 유료 번호를 사용 하 여 bridge로 전화를 걸려면 먼저 Office 365 통신 크레딧을 설정 해야 합니다.

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>회의 브리지에 새 서비스 전화 번호를 할당 하는 단계

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>1 단계-오디오 회의 브리지에 새 전화 번호를 할당 합니다.

1. 회사 계정으로 Office 365에 로그인 합니다.

2. **Microsoft 365 관리 센터** > **관리자** > **팀** > 으로 이동 하 여 Skype**레거시 포털** > **음성** > **전화 번호**를 &.

3. 목록에서 전화 번호를 선택 하 고 작업 창에서 **할당**을 클릭 합니다.

4. **배정** 페이지에서 **저장**을 클릭 합니다.

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>2 단계-회의 브리지의 기본 전화 번호 변경 (선택 사항)

전화 회의 브리지의 기본 전화 번호는 모임 내에서 참가자 또는 이끌이를 통해 아웃 바운드 통화를 할 때 사용 되는 발신자 ID를 정의 합니다.

회의 브리지의 기본 번호로 서비스 유료 번호를 설정할 수 있습니다. **서비스 무료 번호는 회의 브리지의 기본 번호로 설정할 수 없습니다**. 서비스 유료 전화 번호를 할당 하는 경우 오디오 회의 브리지에 대 한 새로운 기본 번호로 설정 하려면 다음 단계를 수행 하세요.

1. 회사 계정으로 Office 365에 로그인 합니다.

2. **Microsoft 365 관리 센터** > **** > **팀** > 으로 이동 하 여 Skype**모임** > **회의 브리지**를 & 합니다.

3. 기본값으로 구성 하려는 서비스 유료 전화 번호를 강조 표시 합니다.

4. **기본값으로 설정을**선택 합니다.
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>3 단계-사용자의 모임 초대에 포함 된 기본 전화 번호 변경 (선택 사항)

사용자의 기본 전화 번호는 모임 일정을 정할 때 모임 초대에 포함 됩니다. Defaul 전화 번호가 새 사용자에 게 할당 되는 방식을 비롯 한 자세한 내용은 [Microsoft 팀의 초대에 포함 된 전화 번호 설정](set-the-phone-numbers-included-on-invites-in-teams.md) 또는 비즈니스용 [Skype Online의 초대에 포함 된 전화 번호](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)설정을 참조 하세요.
  
1. 회사 또는 학교 계정으로 Office 365에 로그인 합니다.

2. **Microsoft 365 관리 센터** > **관리** > 센터**팀** > 으로 이동 하 여 Skype**레거시 포털** > **오디오 회의** > **사용자**를 & 하 고 목록에서 사용자를 선택 합니다.

3. 작업 창에서 **편집** 을 클릭 합니다.

4. **기본 유료 전화 번호** 또는 **기본 무료 유료 번호**에서 목록에 있는 번호를 선택 하 고 **저장**을 클릭 합니다.

변경 내용이 저장 되 면 다음에 새 모임을 예약할 때 새 기본 전화 번호가 이끌이의 모임 초대에 포함 됩니다.

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>4 단계-모임 마이그레이션 서비스를 사용 하 여 사용자의 기존 모임 초대 업데이트 (선택 사항)

다음 두 단계는 Windows PowerShell을 시작 해야 하는 경우입니다.
  
일부 또는 모든 사용자에 대 한 모임 초대에 사용 되는 기본 전화 번호를 업데이트 한 경우에는 조직의 사용자에 게 이미 보낸 모임 초대를 선택적으로 업데이트할 수 있으며,이 경우 해당 기본 전화 번호를 사용 하 여 변경 되었습니다. 모임 마이그레이션 서비스. 자세한 내용은 [MMS (모임 마이그레이션 서비스) 설정을](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)참조 하세요.
  
- 2 단계에서 기본 전화 번호를 변경한 사용자를 위해 MMS (모임 마이그레이션 서비스)를 실행 합니다. 이렇게 하려면 다음 명령을 실행 합니다.

```
    Start-CsExMeetingMigration user@contoso.com
```

- 모임 마이그레이션 상태를 볼 수도 있습니다. *보류* 중이거나 *진행* 중 상태인 작업이 없는 경우 모든 모임의 일정이 다시 조정 됩니다.

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>회의 브리지에 대 한 서비스 전화 번호의 할당을 취소 하는 단계


회의 브리지에서 전화 번호를 할당 취소 하면 사용자는 해당 전화 번호를 사용 하 여 모임에 더 이상 참가할 수 없게 됩니다. 전화 번호가 변경 되므로 전화 번호를 기본 번호 (있는 경우)로 사용 하는 모든 사용자를 업데이트 하 고 기존 모임 초대를 업데이트 하 여 전화 번호가 오디오 회의 브리지에서 할당 되지 않도록 하는 것이 중요 합니다.

사용자 및 해당 모임을 업데이트 하지 않고 전화 번호가 제거 되는 경우 기존 모임 초대에는 모임 참가에 사용할 수 없는 전화 번호가 포함 되어 있을 수 있습니다.

처음 세 단계는 Windows PowerShell을 시작 해야 하는 경우입니다. 이 작업을 수행 하는 방법을 알아보려면 [Windows PowerShell을 사용 하 여 관리 하는 방법을 알아보려면 원하는](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell) 을 클릭 하세요.

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>1 단계-전화 번호를 할당 하지 않은 사용자를 기본 번호 중 하나로 업데이트

기본 유료 또는 수신자 부담 전화 번호를 기본 번호로 지정할 수 없는 번호를 사용 하는 모든 사용자를 대체 하 고 모임의 일정을 재조정 하는 프로세스를 시작 합니다. 이렇게 하려면 다음 명령을 실행 합니다.

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >비즈니스용 Skype 관리 센터에서 기본 유료 또는 무료 사용자 수를 변경할 수도 있습니다. 그러나 모임 일정이 자동으로 재조정 되는 것은 아닙니다. 
 
 자세한 내용은 [Microsoft 팀의 초대에 포함 된 전화 번호 설정](set-the-phone-numbers-included-on-invites-in-teams.md) 또는 비즈니스용 [Skype Online의 초대에 포함 된 전화 번호](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)설정을 참조 하세요.

  > [!NOTE]
  > 조직의 규모에 따라 완료 하는 데 시간이 걸릴 수 있습니다.

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>2 단계-Windows PowerShell을 사용 하 여 모임 마이그레이션 상태 보기

*보류* 중이거나 *진행* 중 상태인 작업이 없는 경우 모든 모임의 일정이 다시 조정 됩니다.

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

모임 마이그레이션 서비스에 대 한 자세한 내용은 [MMS (모임 마이그레이션 서비스) 설정을](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)참조 하세요.
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>3 단계-오디오 회의 브리지에서 이전 전화 번호 할당 취소

1. 회사 또는 학교 계정으로 Office 365에 로그인 합니다.

2. **Microsoft 365 관리 센터** > **관리** > **팀**으로 이동 하 여 Skype > **레거시 포털** > **음성** > **전화 번호**를 &.

3. 전화 번호가 무료 번호 이면 목록에서 전화 번호를 선택 하 고 작업 창에서 **할당**취소를 클릭 합니다. 전화 번호가 유료 이면 [Microsoft 지원](https://go.microsoft.com/fwlink/?linkid=2091806) 에 문의 하 여 전화 번호를 지정 하지 않은 것으로 확인 하세요.

4. 전화 번호가 유료-fre 번호 이면 확인 창에서 **예** 를 클릭 합니다.

   > [!IMPORTANT]
   > 오디오 회의 브리지에서 전화 번호를 할당 하지 않은 후에는 더 이상 사용자가 전화 번호를 사용 하 여 새 모임이 나 기존 모임에 참가할 수 없습니다.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>Windows PowerShell을 사용할 준비가 되었는지 확인 하려면 다음을 실행 하세요.

 이 단계에서는 Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인 합니다.

1. **시작 메뉴** > **Windows PowerShell**을 입력 합니다.

2. **Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.

3. 버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다. Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.
메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.

4. 비즈니스용 Skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.

자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/library/dn568015.aspx)을 참조 하세요.

### <a name="to-start-windows-powershell"></a>Windows PowerShell을 시작 하려면

 **Windows PowerShell 세션 시작**

1. **시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.

2. **Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> 비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.
Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/library/dn568015.aspx) 또는 [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online에](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)연결을 참조 하세요.

### <a name="save-time-and-automate"></a>시간 절약 및 자동화

이 프로세스를 자동화 하 여 시간을 절약 하기 위해 [set-get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688) 또는 **CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용할 수 있습니다.

- [Get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet을 사용 하 여 특정 사용자의 기본 유료 또는 무료 전화 번호를 변경 합니다.

  - 사용자의 기본 무료 전화 번호를 변경 하려면 다음을 실행 합니다.

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- **CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용 하 여 기본 유료 또는 수신자의 사용자 수를 원래의 기본 숫자나 해당 위치에 따라 변경 합니다.

    > [!NOTE]
    > BridgeID를 찾으려면 **CsOnlineDialInConferencingBridge**를 사용 합니다.

  - 1 ~ 8005551234 없는 모든 사용자의 기본 무료 전화 번호를 설정 하려면 다음을 실행 합니다.

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 8005551234을 기본 무료 번호로 사용 하는 모든 사용자의 기본 무료 (수신자 부담 번호)를 8005551239로 변경 하 고 자동으로 모임 일정을 조정 하려면 다음을 실행 합니다.

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 미국에 거주 하는 모든 사용자의 기본 무료 무료 번호를 8005551234로 설정 하 고 자동으로 모임 일정을 재조정 하려면 다음을 실행 합니다.

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 위에서 사용 되는 위치는 Microsoft 365 관리 센터에서 설정한 사용자의 연락처 정보와 일치 해야 합니다.

## <a name="troubleshooting"></a>해결사

**할당 취소 단추가 회색으로 표시 됨**

숫자의 할당을 취소 했지만 단추가 회색으로 표시 되는 동안에는 다음 메시지가 표시 되 면 _"기본 또는 공유 번호를 브리지에서 할당 해제할 수 없었습니다" 라는 메시지와 함께 연락처에 대 한 지원이 리디렉션됩니다. 전용 유료 전화 번호를 할당 취소 하려면 고객 지원에 문의 하세요._"

브리지에 대 한 자세한 정보를 얻으려면 다음 Powershell을 실행 합니다.
```
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

그 결과, Id, 이름, 지역 등의 다른 정보는 함께 DefaultServiceNumber를 포함 해야 합니다.

**예**를 들어, DefaultServiceNumber "8005551234"을 할당 취소 하려면
```
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName “Conference Bridge” -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>Windows PowerShell 정보

Windows PowerShell을 사용 하 여 사용자를 관리 하 고, 수행할 수 있는 작업을 관리할 수 있습니다. Windows PowerShell을 사용 하면 작업을 수행 하는 데 많은 작업을 수행할 수 있는 단일 관리 지점을 통해 Office 365 및 비즈니스용 Skype Online을 손쉽게 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.

  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.

  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>관련 항목
[오디오 회의 브리지에 대 한 설정 변경](change-the-settings-for-an-audio-conferencing-bridge.md)
