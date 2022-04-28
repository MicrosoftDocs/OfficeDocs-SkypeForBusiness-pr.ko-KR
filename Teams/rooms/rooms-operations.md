---
title: Microsoft Teams 룸 유지 관리 및 운영
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Microsoft Teams 룸 관리에 대해 알아봅니다.
ms.openlocfilehash: e214d0b438ea7dd9b710a7aba8597de6c5b76bdf
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106263"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams 룸 유지 관리 및 운영
 
 
Microsoft Teams 룸 회의실을 풍부하고 공동 작업적인 환경으로 변환하도록 설계된 Microsoft의 회의 솔루션입니다. 사용자는 친숙한 Microsoft Teams 또는 비즈니스용 Skype 인터페이스를 즐길 수 있으며 IT 관리자는 쉽게 배포되고 관리되는 Windows 10 Teams 룸 앱을 감상할 수 있습니다. Microsoft Teams 룸 설치 용이성을 위해 기존 장비를 활용하여 Microsoft Teams 또는 비즈니스용 Skype 회의실로 가져오도록 설계되었습니다.
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Microsoft Teams 룸 로그 수집
<a name="Logs"> </a>

Teams 관리 센터에서 로그를 수집하려면 **Windows > Teams 룸 Teams 디바이스로** 이동합니다. 로그를 사용할 디바이스의 표시 이름을 선택합니다. 위쪽 패널에서 "디바이스 로그 다운로드"를 선택합니다. 확인되면 몇 분 후에 기록 탭에서 로그를 다운로드할 준비가 됩니다.

PowerShell을 사용하여 로그를 수집할 수도 있습니다. Microsoft Teams 룸 앱과 함께 제공되는 로그 수집 스크립트를 호출해야 합니다. [관리자 모드](rooms-operations.md)에서 관리자 권한 명령 프롬프트를 시작하고 다음 명령을 실행합니다.
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

로그는 c:\rigel에서 ZIP 파일로 출력됩니다.
  
## <a name="front-of-room-display-settings"></a>방 전면 디스플레이 설정
<a name="Display"> </a>

CEC(Consumer Electronics Control)를 지원하거나 PC 모드를 사용하도록 실내 전면 디스플레이 설정을 구성합니다.
  
대기 모드에서 해제될 때 방 앞 디스플레이가 자동으로 Teams 룸 전환되도록 하려면 특정 조건을 충족해야 합니다. 이 기능은 선택 사항이지만 기본 하드웨어에서 이 기능을 지원하는 경우 Microsoft Teams 룸 소프트웨어에서 지원됩니다. 전면 디스플레이로 사용되는 소비자 TV는 HDMI의 CEC(소비자 가전 제어) 기능을 지원해야 합니다.  선택한 도크 또는 콘솔(CEC를 지원하지 않을 수 있음, 제조업체 지원 설명서 참조)에 따라 원하는 동작을 사용하도록 설정하려면 Crestron의 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 또는 [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) 과 같은 컨트롤러가 필요할 수 있습니다.

### <a name="scale-and-resolution"></a>크기 조정 및 해상도

Teams 룸 디자인된 환경을 얻으려면 회의실 전면 디스플레이가 해상도 및 크기 조정 요구 사항을 충족해야 합니다.

프런트 오브 룸의 크기 조정 및 해상도를 원격으로 설정하려면 [XML 구성 파일을 사용하여 원격으로 Microsoft Teams 룸 콘솔 설정 관리를](xml-config-file.md#set-front-of-room-scale-and-resolution) 참조하세요.

Teams Room 관리자 설정에서 크기 조정 및 해상도를 수동으로 설정하려면 다음을 수행합니다.

1. Teams 룸에서 [관리자 모드](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)로 전환

2. 시작 아이콘을 선택합니다. 그런 다음 **시스템 > 표시를 설정 >**

3. **크기 조정 및 레이아웃** 으로 이동한 다음 **텍스트, 앱 및 기타 항목의 크기를 변경하고** 크기 조정을 100%로 설정합니다.

4. 디스플레이 해상도를 1080p로 설정합니다. 이중 모니터가 있는 경우 두 화면의 크기 조정 및 해상도를 설정합니다.

5. 다음으로 시작 아이콘을 선택하고 **명령 프롬프트를 입력합니다**. **관리자 권한으로 실행을** 선택합니다.

6. 다음 명령을 실행합니다.

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```

7. 디바이스를 다시 시작합니다.
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams 룸 초기화(공장 복원)
<a name="Reset"> </a>

Microsoft Teams 룸 잘 실행되지 않는 경우 공장 재설정을 수행하는 것이 도움이 될 수 있습니다. 이렇게 하려면 [Microsoft Teams 룸 복구 도구를](recovery-tool.md) 사용하고 공장 복원 지침을 따릅니다.

> [!NOTE]
> **내 파일 보관 - 앱 및 설정을 제거하지만** Windows 다시 설정 프로세스 중에 개인 파일 옵션을 선택한 경우 Microsoft Teams 룸 사용할 수 없게 될 수 있는 알려진 문제가 있습니다. 이 옵션을 사용하지 *마세요* .
  
## <a name="supported-remote-options"></a>지원되는 원격 옵션
<a name="RemoteOptions"> </a>

다음 표에는 가능한 원격 작업 및 이를 수행하는 데 사용할 수 있는 메서드가 요약되어 있습니다.
  

|작업|도메인에 가입되지 않음|도메인에 가입됨|
|:-----|:-----|:-----|
|다시 시작할  <br/> |Teams 관리 센터  <br/> 원격 데스크톱  <br/> 원격 PowerShell  <br/> | <br/>원격 데스크톱(추가 구성 필요)  <br/> 원격 PowerShell(추가 구성 필요)  <br/> Configuration Manager  <br/> |
|OS 업데이트  <br/> |Windows 업데이트  <br/> |Windows 업데이트  <br/> WSUS  <br/> |
|앱 업데이트  <br/> |Windows 스토어  <br/> |Windows 스토어  <br/> Configuration Manager  <br/> |
|계정 구성  <br/> |Teams 관리 센터  <br/> |Teams 관리 센터  <br/> |
|액세스 로그  <br/> |Teams 관리 센터  <br/> Powershell  <br/> |Teams 관리 센터 <br/> Powershell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Microsoft Teams 룸 대한 그룹 정책 구성
<a name="GroupPolicy"> </a>

이 섹션에서는 Microsoft Teams 룸 제대로 작동하기 위해 의존하는 시스템 설정에 대해 설명합니다. 

Active Directory 도메인에 Teams 룸 가입하면 다음과 같은 이점이 제공됩니다.

- 도메인 가입 Teams 룸 도메인 사용자 및 그룹에 관리 권한을 부여할 수 있습니다. 이렇게 하면 로컬 컴퓨터 수준 관리자 계정 암호를 기억할 필요가 없습니다.

- Windows 서비스 품질 구성을 Teams 룸 배포할 수 있습니다.

- 비즈니스용 Skype 사용하는 경우 Teams 룸 도메인에 가입하면 조직의 프라이빗 루트 인증서 체인 가져오기가 자동화됩니다.

Teams 룸 도메인에 가입하는 경우 모든 Teams 룸 개체가 있는 OU에 GPO(그룹 정책 Object) 제외를 제공할 수 있도록 별도의 OU(조직 구성 단위)를 만들어야 합니다. 지원되지 않는 그룹 정책 설정이 Teams 룸 적용되지 않도록 모든 GPO 상속을 사용하지 않도록 설정합니다. 도메인에 Teams 룸 가입하기 전에 OU에서 컴퓨터 개체를 만들어 기본 컴퓨터 OU에 적용된 그룹 정책이 적용되지 않도록 합니다.

> [!NOTE]
> 별도의 OU를 만들고 상속을 차단하는 경우에도 재정의가 설정되지 않은 경우 문제가 발생할 수 있는 일부 그룹 정책이 있습니다. 재정의가 없는 그룹 정책 블록 정책 상속 집합이 있는 OU를 능가합니다.

많은 조직에는 Teams 룸 기능에 영향을 미치는 다음과 같은 GPO가 있습니다. 이러한 상속을 재정의하거나 차단해야 합니다.

  - 로그온 세션 시간 제한(자동 잠금)
  - 전원 관리 관련 정책
  - 추가 인증 단계 필요
  - 로컬 드라이브에 대한 액세스 거부
  - 사용자에게 느린 네트워크 연결에 대한 메시지 표시
  - 로그온 시 특정 프로그램 시작
  - 모든 도메인에 가입된 컴퓨터에서 다른 도메인 사용자 계정을 만듭니다.
  - Teams 룸 Windows 업데이트 푸시

도메인에 Microsoft Teams 룸 조인할 때 그룹 정책이 다음 표의 설정을 재정의하지 않는지 확인합니다.

|설정|허용|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Microsoft Teams 룸 부팅할 수 있습니다.  <br/> |
|전원 관리 -\> AC에서 10분 후 화면 끄기  <br/> 전원 관리 -\> AC에서 시스템을 절전 모드로 설정하지 마세요.  <br/> |Microsoft Teams 룸 연결된 디스플레이를 끄고 자동으로 절전 모드 해제할 수 있습니다.  <br/> |
|net accounts /maxpwage:unlimited  <br/> 또는 로컬 계정에서 암호 만료를 사용하지 않도록 설정하는 동등한 수단입니다. 이 작업을 수행하지 않으면 결국 Skype 계정이 만료된 암호에 대해 불평하는 로그온에 실패하게 됩니다. 이는 컴퓨터의 모든 로컬 계정에 영향을 주므로 이를 설정하지 않으면 상자의 관리 계정도 결국 만료됩니다.  <br/> |Skype 계정이 항상 로그인하도록 설정  <br/> |

> [!NOTE]
> Microsoft Teams 룸 다음 버전의 Windows 10 OS와 호환되는 경우 Teams 룸 Windows 업데이트 통해 자동으로 다음 버전으로 업데이트됩니다. Microsoft Teams 룸 수동으로 Windows 10 다음 릴리스로 업그레이드하거나 WUFB(비즈니스용 Windows 업데이트) 그룹 정책 "수신하려는 업데이트에 대한 Windows 준비 수준 선택" 및 GPO를 통해 "미리 보기 빌드 및 기능 업데이트를 받을 때 선택"을 통해 업그레이드해서는 안 됩니다. 이러한 그룹 정책을 사용하는 Teams 룸 Windows 10 OS 업데이트와 관련된 문제가 발생하는 것으로 알려져 있습니다.

## <a name="remote-management-using-powershell"></a>PowerShell을 사용한 원격 관리
<a name="RemotePS"> </a>

PowerShell을 사용하여 원격으로 다음 관리 작업을 수행할 수 있습니다(스크립트 샘플은 아래 표 참조).
  
- 연결된 디바이스 가져오기
- 앱 상태 가져오기
- 시스템 정보 가져오기
- 다시 부팅 시스템
- 로그 검색
- 파일 전송(도메인에 가입된 Microsoft Teams 룸 필요)
    
> [!NOTE]
> 이 기능은 기본적으로 꺼져 있습니다. 아래 작업을 수행하려면 Microsoft Teams 룸 시스템의 환경에 대해 원격 PowerShell을 사용하도록 설정해야 합니다. 원격 PowerShell을 사용하도록 설정하는 방법에 대한 자세한 내용은 **[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** 에 대한 설명서를 참조하세요.
  
예를 들어 다음과 같이 원격 PowerShell을 사용하도록 설정할 수 있습니다.
  
1. Microsoft Teams 룸 디바이스에서 관리자로 로그인합니다.
2. 관리자 권한 PowerShell 명령 프롬프트를 엽니다.
3. 다음 명령을 입력합니다. `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. 로컬 보안 정책을 열고 *보안* **설정** > **로컬 PoliciesUser** >  **권한 할당** > **에 관리자 보안 그룹을 네트워크에서 이 컴퓨터에 추가합니다**.

관리 작업을 수행하려면 다음을 수행합니다.
  
1. Microsoft Teams 룸 디바이스에서 PowerShell 명령을 실행할 수 있는 권한이 있는 계정 자격 증명을 사용하여 PC에 로그인합니다.
2. PC에서 일반 PowerShell 명령 프롬프트를 엽니다.
3. 아래 표에서 명령 텍스트를 복사하여 프롬프트에 붙여넣습니다.
4. 필드를 사용자 환경에 적합한 FQDN 값으로 바꿉  `<Device fqdn>` 있습니다.
5. 마스터 SkypeSettings.xml 구성 파일(또는 테마 이미지)의 파일 이름 및 로컬 경로로 바꿉  *\<path\>*  니다.
    
연결된 디바이스를 얻으려면
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

앱 상태 가져오기
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

시스템 정보 가져오기
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

시스템 다시 부팅
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

로그 검색
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

XML 구성 파일(또는 테마 그래픽) 푸시
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>소프트웨어 업데이트
<a name="SWupdate"> </a>

기본적으로 Microsoft Teams 룸 최신 버전의 Microsoft Teams 룸 소프트웨어를 얻기 위해 Windows Store에 연결하려고 시도합니다. 따라서 Teams 룸 일반 인터넷 액세스가 필요합니다. 지원 문제로 Microsoft에 문의하기 전에 Microsoft Teams 룸 최신 버전의 앱과 함께 로드되었는지 확인합니다.
  
Microsoft Teams 룸 Windows 업데이트 연결하여 운영 체제 및 주변 장치 펌웨어 업데이트를 검색합니다. 또한 Microsoft Store 연결하여 애플리케이션 업데이트를 검색합니다.

애플리케이션 업데이트를 수동으로 관리해야 하지만 [오프라인 앱을 배포](/microsoft-store/distribute-offline-apps)하는 [비즈니스용 Microsoft Store](https://businessstore.microsoft.com/store) 일반적인 절차를 따를 수 없는 경우 Teams 룸 업데이트 패키지를 획득하여 지원되는 운영 체제에서 앱 업데이트를 수행할 수 있습니다. 업데이트 릴리스는 스토어 릴리스보다 뒤쳐질 수 있으며 항상 사용 가능한 최신 빌드와 일치하지 않을 수 있습니다. 자세한 내용은 [Microsoft Teams 룸 디바이스 수동 업데이트를](manual-update.md) 참조하세요.

## <a name="admin-mode-and-device-management"></a>관리 모드 및 디바이스 관리
<a name="AdminMode"> </a>

개인 CA 인증서를 수동으로 설치하는 것과 같은 일부 관리 기능을 사용하려면 관리 모드에서 Teams 룸 배치해야 합니다. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Microsoft Teams 룸 앱이 실행 중일 때 관리자 모드로 전환 및 다시 전환

1. 진행 중인 전화를 끊고 홈 화면으로 돌아갑니다.
2. 기어 아이콘을 선택하고 메뉴를 표시합니다(옵션은 **설정**, **접근성** 및 **디바이스 다시 시작**).
3. **설정** 선택합니다.
4. 관리자 암호를 입력합니다. 설치 화면이 나타납니다.  디바이스가 도메인에 가입되지 않은 경우 로컬 관리 계정(사용자 이름 "관리자")이 기본적으로 사용됩니다. 이 계정의 기본 암호는 'sfb'입니다. 가능한 한 빨리 이 암호를 변경합니다. 컴퓨터가 도메인에 가입된 경우 적절한 권한의 도메인 계정으로 로그인할 수 있습니다.
5. 왼쪽 열에서 **Windows 설정** 선택합니다.
6. 관리자 자격 증명을 사용하여 데스크톱에 로그인합니다. 디바이스를 관리하는 데 필요한 권한이 있습니다.
7. 필요한 관리 작업을 수행합니다.
8.  완료되면 컴퓨터를 다시 시작합니다.
    
이제 콘솔이 정상 작동 모드로 돌아왔습니다. 다음 절차에서는 키보드가 아직 연결되지 않은 경우 디바이스에 키보드를 연결해야 합니다. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Microsoft Teams 룸 앱이 충돌할 때 관리자 모드로 전환 및 다시 전환

1. Windows 키를 5번 연속해서 누릅니다. 그러면 Windows 로그온 화면으로 연결됩니다. 
2. 관리자 자격 증명을 사용하여 데스크톱에 로그인합니다.
3. 필요한 관리 작업을 수행합니다.
4. 완료되면 컴퓨터를 다시 시작합니다.

    > [!NOTE]
    > 이 메서드는 Skype 사용자를 로그오프하거나 정상적으로 앱을 종료하지 않지만 앱이 응답하지 않고 다른 메서드를 사용할 수 없는 경우 이 메서드를 사용합니다. 

   콘솔이 정상 작동 모드로 다시 시작하여 Microsoft Teams 룸 앱을 실행합니다. 키보드를 연결한 경우 키보드를 제거하여 이 절차를 완료할 수 있습니다.
   ## <a name="troubleshooting-tips"></a>문제 해결 팁
   <a name="TS"> </a>

- 도메인 경계를 넘어 보낼 때 모임 초대가 표시되지 않을 수 있습니다(예: 두 회사 간). 이러한 경우 IT 관리자는 외부 사용자가 모임을 예약할 수 있도록 허용할지 여부를 결정해야 합니다. Exchange PowerShell cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing), 특히 'ProcessExternalMeetingMessages' 매개 변수에 대한 문서를 참조하세요.
- Microsoft Teams 룸 Exchange 2010을 통한 Exchange 자동 검색 리디렉션을 지원하지 않습니다.
- 일반적으로 IT 관리자는 사용하지 않으려는 오디오 엔드포인트를 사용하지 않도록 설정하는 것이 좋습니다.
- 미러 이미지가 회의실 미리 보기에 표시되는 경우 IT 관리자는 카메라 전원을 순환하거나 카메라 설정을 사용하여 이미지 방향을 대칭 이동하여 수정할 수 있습니다.
- 콘솔 터치 스크린 액세스 손실이 발생한 것으로 알려져 있습니다. 이러한 경우 Teams 룸 다시 시작하여 문제가 해결되는 경우가 있습니다.
- 유선 수집을 통해 PC를 콘솔에 연결할 때 로컬 오디오가 손실되는 것으로 알려져 있습니다. 이러한 경우 PC를 다시 시작하면 로컬 오디오 재생 문제가 해결될 수 있습니다.
