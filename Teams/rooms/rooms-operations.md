---
title: Microsoft Teams 룸 유지 관리 및 작업
ms.author: dstrome
author: dstrome
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
description: 이 항목에서 이 항목의 관리에 대해 Microsoft Teams 룸.
ms.openlocfilehash: be5f183e593ca1723383b6834c9ff5cad387b42f
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2022
ms.locfileid: "62298993"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams 룸 유지 관리 및 작업
 
이 항목에서 이 항목의 관리에 대해 Microsoft Teams 룸.
  
Microsoft Teams 룸 회의실을 풍부하고 공동 작업 환경으로 변환하도록 설계된 Microsoft의 회의 솔루션입니다. 사용자는 친숙한 인터페이스 또는 Microsoft Teams 비즈니스용 Skype 즐길 수 있으며 IT 관리자는 쉽게 배포되고 관리되는 앱에 Windows 10 Teams 룸 있습니다. Microsoft Teams 룸 설치가 용이하도록 기존 장비를 활용하여 회의실에 Microsoft Teams 비즈니스용 Skype 수 있도록 디자인되었습니다.
    
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>로그를 수집하는 Microsoft Teams 룸
<a name="Logs"> </a>

관리 센터에서 Teams 로그를 수집하려면 Teams > Teams 룸 **Windows**. 로그를 사용할 디바이스의 표시 이름을 선택합니다. 위쪽 패널에서 "디바이스 로그 다운로드"를 선택합니다. 확인하면 몇 분 후에 기록 탭에서 로그를 다운로드할 준비가 됩니다.

PowerShell을 사용하여 로그를 수집할 수도 있습니다. 앱과 함께 배송되는 로그 컬렉션 스크립트를 Microsoft Teams 룸 합니다. 관리자 [모드에서](rooms-operations.md) 상승된 명령 프롬프트를 시작하고 다음 명령을 실행합니다.
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

로그는 c:\rigel의 ZIP 파일로 출력됩니다.
  
## <a name="front-of-room-display-settings"></a>룸 디스플레이 설정
<a name="Display"> </a>

CEC(Consumer Electronics Control)를 지원하거나 PC 모드를 사용하도록 설정하기 위해 전면 디스플레이의 설정을 구성합니다.
  
대기 모드에서 깨어나면 전면 디스플레이가 자동으로 대기 모드로 Teams 룸 경우 특정 조건이 충족되어야 합니다. 이 기능은 선택 사항이지만 기본 Microsoft Teams 룸 소프트웨어에서 지원됩니다. 기본 하드웨어가 기능을 지원합니다. 전면 디스플레이로 사용되는 소비자 TV는 HDMI의 CEC(소비자 전자 제어) 기능을 지원해야 합니다.  선택한 도크 또는 콘솔(CEC를 지원하지 않을 수 있는 제조업체 지원 설명서 참조)에 따라 Crestron의 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 또는 [Extron의 Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) 과 같은 컨트롤러가 필요한 경우 원하는 동작을 사용하도록 설정할 수 있습니다.

### <a name="change-scale-and-resolution"></a>크기 및 해상도 변경

전면 디스플레이의 글꼴 크기가 너무 크거나 작을 경우 화면의 해상도를 조정해야 합니다. 

1. 관리자 [모드로 전환](#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)

2. 시작 아이콘을 선택합니다. 그런 **설정 > 시스템 > 디스플레이**

3. 크기 조정 **및 레이아웃으로 이동** 한 다음 텍스트 **,** 앱 및 기타 항목의 크기를 변경하고 크기 조정을 100%로 설정합니다.

4. 디스플레이 해상도를 1080p로 설정합니다. 듀얼 모니터가 있는 경우 두 화면의 크기 및 해상도를 설정합니다.

5. 다음으로 시작 아이콘을 선택하고 **명령 프롬프트를 입력합니다**. 관리자 **권한으로 실행을 선택합니다**.

6. 다음 명령을 실행합니다.

```cmdlet
 Powershell -ExecutionPolicy Unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentDisplayScaling.ps1 
```
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams 룸 재설정(팩터리 복원)
<a name="Reset"> </a>

Microsoft Teams 룸 작동하지 않는 경우 팩터리 재설정을 수행하는 것이 도움이 될 수 있습니다. 이렇게하려면 Microsoft Teams [룸](recovery-tool.md) 복구 도구를 사용하여 팩터리 복원 지침을 따릅니다.

> [!NOTE]
> 내 파일 Microsoft Teams 룸 **유지 -** 앱 및 설정을 제거하지만 다시 설정 프로세스 중에 개인 파일 옵션이 선택되어 있는 경우 Windows 문제가 있습니다. 이 *옵션을* 사용하지 않습니다.
  
## <a name="supported-remote-options"></a>지원되는 원격 옵션
<a name="RemoteOptions"> </a>

다음 표에서는 가능한 원격 작업과 이를 수행하기 위해 사용할 수 있는 방법을 요약합니다.
  

|작업대|도메인에 가입되지 않은 경우|도메인에 가입된|
|:-----|:-----|:-----|
|다시 시작  <br/> |Teams 관리 센터  <br/> 원격 데스크톱  <br/> 원격 PowerShell  <br/> | <br/>원격 데스크톱(추가 구성 필요)  <br/> 원격 PowerShell(추가 구성 필요)  <br/> 구성 관리자  <br/> |
|OS 업데이트  <br/> |Windows 업데이트  <br/> |Windows 업데이트  <br/> WSUS  <br/> |
|앱 업데이트  <br/> |Windows 스토어  <br/> |Windows 스토어  <br/> 구성 관리자  <br/> |
|계정 구성  <br/> |Teams 관리 센터  <br/> |Teams 관리 센터  <br/> |
|액세스 로그  <br/> |Teams 관리 센터  <br/> PowerShell  <br/> |Teams 관리 센터 <br/> PowerShell  <br/>  |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>사용자에 대한 그룹 Microsoft Teams 룸
<a name="GroupPolicy"> </a>

이 섹션에서는 제대로 작동하기 위해 Microsoft Teams 룸 시스템 설정에 대해 설명합니다. 

Active Directory Teams 룸 도메인에 가입하면 다음과 같은 이점이 있습니다.

- 도메인 가입 Teams 룸 도메인 사용자 및 그룹 관리 권한을 부여할 수 있습니다. 이렇게 하면 로컬 컴퓨터 수준 관리자 계정 암호를 기억할 수 없습니다.

- 서비스 품질 Windows 배포할 수 Teams 룸.

- 비즈니스용 Skype 경우 도메인에 Teams 룸 조직의 개인 루트 인증서 체인 가져오기가 자동화됩니다.

도메인에 Teams 룸 모든 개체가 상주하는 OU에 GPO(그룹 정책 개체) 제외를 제공할 수 있도록 별도의 OU(조직 단위)를 Teams 룸 필요합니다. 지원되지 않는 그룹 정책 설정이 지원되지 않도록 모든 GPO 상속을 Teams 룸. 도메인에 Teams 룸 OU에서 컴퓨터 개체를 만들어 기본 컴퓨터 OU에 적용된 그룹 정책이 적용되지 않습니다.

> [!NOTE]
> 별도의 OU를 만들고 상속을 차단하는 경우에도 일부 그룹 정책이 있습니다. 이 정책이 다시 설정되지 않았다면 문제가 발생할 수 있습니다. OU가 없음 집합이 있는 그룹 정책은 블록 정책 상속 집합을 통해 OU를 꺾습니다.

많은 조직에는 다음과 같은 GPOS가 있습니다. 이로 인하여 기능에 Teams 룸 있습니다. 이러한 상속을 다시 받거나 차단해야 합니다.

  - 로그온 세션의 시간 제한(자동 잠금)
  - Power Management 관련 정책
  - 추가 인증 단계 필요
  - 로컬 드라이브에 대한 액세스 거부
  - 느린 네트워크 연결에 대한 사용자에게 묻는 메시지
  - 로그온에서 특정 프로그램 시작
  - 도메인에 가입된 모든 머신에서 다른 도메인 사용자 계정을 만들 수 있습니다.
  - 업데이트 Windows 푸시합니다Teams 룸

도메인에 Microsoft Teams 룸 그룹 정책이 다음 표의 설정을 오버라이드하지 않도록 합니다.

|설정|허용|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |부팅 Microsoft Teams 룸 수 있습니다.  <br/> |
|Power Management -\> AC에서 10분 후에 화면 끄기  <br/> Power Management -\> AC에서 시스템을 절전에 놓지 않습니다.  <br/> |연결된 Microsoft Teams 룸 해제하고 자동으로 절전 모드 해제할 수 있습니다.  <br/> |
|net 계정 /maxpwage:unlimited  <br/> 또는 로컬 계정에서 암호 만료를 사용할 수 없습니다. 이렇게 하지 못하면 로그온이 Skype 로그온에 실패하게 됩니다. 이로 인해 컴퓨터의 모든 로컬 계정에 영향을 미치기 때문에 이를 설정하지 못하면 상자의 관리 계정도 결국 만료됩니다.  <br/> |계정 Skype 항상 로그인할 수 있습니다.  <br/> |

> [!NOTE]
> Microsoft Teams 룸 OS의 다음 버전과 호환되는 Windows 10 경우 Teams 룸 업데이트를 통해 Windows 업데이트합니다. Microsoft Teams 룸 WUFB(비즈니스용 업데이트) Windows 10 Windows (WUFB) 그룹 정책 "수신하려는 업데이트에 대한 Windows 준비 수준을 선택" 및 "미리 보기 빌드 및 기능 업데이트가 GPO를 통해 수신될 때 선택"을 사용하도록 설정하여 다음 릴리스로 업그레이드하면 안 됩니다. Teams 룸 이러한 그룹 정책을 사용하는 경우 OS 업데이트에 문제가 Windows 10 것으로 알려져 있습니다.

## <a name="remote-management-using-powershell"></a>PowerShell을 사용하여 원격 관리
<a name="RemotePS"> </a>

PowerShell을 사용하여 원격으로 다음 관리 작업을 수행할 수 있습니다(스크립트 샘플에 대한 아래 표 참조).
  
- 연결된 디바이스를 얻다
- 앱 상태 다운로드
- 시스템 정보 보기
- 시스템 재부팅
- 로그 검색
- 파일 전송(도메인에 가입된 Microsoft Teams 룸)
    
> [!NOTE]
> 이 기능은 기본적으로 꺼집니다. 아래 작업을 수행하려면 Microsoft Teams 룸 환경에 대해 원격 PowerShell을 사용하도록 설정해야 합니다. 원격 PowerShell을 사용하도록 설정하는 방법에 대한 자세한 내용은 **[Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting)** 의 설명서를 참조하세요.
  
예를 들어 다음과 같이 원격 PowerShell을 사용하도록 설정할 수 있습니다.
  
1. 디바이스에서 관리자로 Microsoft Teams 룸.
2. 상승된 PowerShell 명령 프롬프트를  실행합니다.
3. 다음 명령을 입력합니다. `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. 로컬 보안 정책을 열  >  고 관리자 보안 그룹을  보안 설정 **Local PolicyUser** >  **권한 할당** > **Accesss 네트워크에서 이 컴퓨터를 추가합니다**.

관리 작업을 수행하기 위해:
  
1. 디바이스에서 PowerShell 명령을 실행할 수 있는 권한이 있는 계정 자격 증명을 사용하여 PC에 Microsoft Teams 룸.
2. PC에서 일반 PowerShell 명령 프롬프트를  실행합니다.
3. 아래 표에서 명령 텍스트를 복사하고 프롬프트에 붙여넣습니다.
4. 필드  `<Device fqdn>` 를 환경에 적합한 FQDN 값으로 바 대체합니다.
5. 마스터  *\<path\>*  의 파일 이름 및 로컬 경로로 SkypeSettings.xml 구성 파일(또는 테마 이미지)으로 바 대체합니다.
    
연결된 디바이스를 사용
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

앱 상태 다운로드
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

시스템 정보 보기
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

시스템 재부팅
  
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

XML 구성 파일 푸시(또는 테마 그래픽)
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>소프트웨어 업데이트
<a name="SWupdate"> </a>

기본적으로 Microsoft Teams 룸 최신 버전의 소프트웨어를 Windows 저장소에 Microsoft Teams 룸 시도합니다. 따라서 Teams 룸 인터넷에 정기적으로 액세스해야 합니다. Microsoft에 지원 문제를 문의하기 전에 Microsoft Teams 룸 최신 버전의 앱으로 로드해야 합니다.
  
Microsoft Teams 룸 업데이트에 Windows 운영 체제 및 주변 장치 펌웨어 업데이트를 검색합니다. Teams 2:00AM 로컬 시간부터 설치하도록 구성됩니다.
  
저장소에 액세스하는 데 제한이 Windows 수동으로 업데이트를 관리해야 하므로 오프라인 앱 배포에 대한 일반적인 절차를 비즈니스용 Microsoft Store 수 없는 경우 배포 키트에서 적절한 APPX 파일 [및](https://businessstore.microsoft.com/store) 종속[](/microsoft-store/distribute-offline-apps)성(지침에서 구성)을 획득할 수 있습니다.[](https://go.microsoft.com/fwlink/?linkid=851168) [ Microsoft Teams 룸)](console.md) 구성 관리자와 함께 사용할 수 있습니다. 배포 키트 릴리스는 저장소 릴리스 뒤로 까다로우기 때문에 항상 사용 가능한 최신 빌드와 일치하지 않을 수 있습니다.
  
### <a name="to-update-using-powershell"></a>PowerShell을 사용하여 업데이트

1. 설치 [MSI](https://go.microsoft.com/fwlink/?linkid=851168) 에서 디바이스가 액세스할 수 있는 공유로 패키지를 추출합니다.
2. 디바이스를 대상으로 하는 Microsoft Teams 룸 스크립트를 실행하여 디바이스 \<share\> 공유를 적절하게 변경합니다.
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>관리자 모드 및 디바이스 관리
<a name="AdminMode"> </a>

개인 CA 인증서를 수동으로 설치하는 등 일부 관리 함수는 관리자 Teams 룸 배치해야 합니다. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>앱 실행 시 관리 모드로 Microsoft Teams 룸 전환

1. 지속적인 통화를 중단하고 홈 화면으로 돌아온다.
2. 기어 아이콘을 선택하고 메뉴를 시작합니다(옵션은 **설정, 접근****성 및 디바이스 다시** **시작).**
3. **설정.**
4. 관리자 암호를 입력합니다. 설정 화면이 나타납니다.  디바이스가 도메인에 가입되지 않은 경우 로컬 관리 계정(사용자 이름 "관리자")이 기본적으로 사용됩니다. 이 계정의 기본 암호는 'sfb'입니다. 가능한 한 빨리 이 암호를 변경합니다. 머신이 도메인에 가입된 경우 적절한 권한 있는 도메인 계정으로 로그인할 수 있습니다.
5. 왼쪽 **Windows 설정** 열에서 Windows 설정 선택합니다.
6. 관리 자격 증명을 사용하여 데스크톱에 로그인합니다. 디바이스를 관리하는 데 필요한 권한이 있습니다.
7. 필요한 관리 작업을 수행합니다.
8.  완료되면 컴퓨터를 다시 시작합니다.
    
이제 콘솔이 정상 작동 모드로 돌아갑니다. 다음 절차에서는 키보드가 아직 연결되지 않은 경우 디바이스에 키보드를 연결해야 합니다. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>앱 충돌 시 관리 모드로 Microsoft Teams 룸 전환

1. 연속으로 Windows 키를 5번 누르고 있습니다. 이렇게 하면 로그온 Windows 표시됩니다. 
2. 관리 자격 증명을 사용하여 데스크톱에 로그인합니다.
3. 필요한 관리 작업을 수행합니다.
4. 완료되면 컴퓨터를 다시 시작합니다.

    > [!NOTE]
    > 이 메서드는 사용자 Skype 로그오프하거나 앱을 은혜적으로 종료하지 않지만 앱이 응답하지 않는 경우 다른 메서드를 사용할 수 없는 경우 이 메서드를 사용합니다. 

   콘솔이 정상 작동 모드로 다시 시작되어 Microsoft Teams 룸 실행됩니다. 이 절차를 완료하기 위해 키보드를 연결한 경우 키보드를 제거할 수 있습니다.
   ## <a name="troubleshooting-tips"></a>문제 해결 팁
   <a name="TS"> </a>

- 도메인 경계(예: 두 회사 간)를 통해 전송될 때 모임 초대가 나타나지 않을 수 있습니다. 이러한 경우 IT 관리자는 외부 사용자가 모임을 예약할 수 있도록 허용할지 여부를 결정해야 합니다. Exchange PowerShell cmdlet [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing), 특히 'ProcessExternalMeetingMessages' 매개 변수에 대한 문서를 참조하세요.
- Microsoft Teams 룸 2010을 통해 자동 Exchange 리디렉션을 지원하지 Exchange 없습니다.
- 일반적으로 IT 관리자는 사용하지 않는 오디오 엔드포인트를 사용하지 않도록 설정하는 것이 좋습니다.
- 미러 이미지가 룸 미리 보기에 표시되는 경우 IT 관리자는 카메라 전원을 순환하거나 카메라 설정을 사용하여 이미지 방향을 뒤집어 수정할 수 있습니다.
- 콘솔 터치 스크린 액세스의 손실이 발생하는 것으로 알려져 있습니다. 이러한 경우 문제를 다시 시작하여 Teams 룸.
- 유선 인제스트를 통해 PC를 콘솔에 연결할 때 로컬 오디오 손실이 발생하는 것으로 알려져 있습니다. 이러한 경우 PC를 다시 시작하면 로컬 오디오 재생 문제가 해결될 수 있습니다.
