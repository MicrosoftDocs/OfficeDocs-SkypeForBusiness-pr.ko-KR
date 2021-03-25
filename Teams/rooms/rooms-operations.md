---
title: Microsoft Teams Rooms 유지 관리 및 작업
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
localization_priority: Normal
description: 다음 세대 Skype Room Systems인 Microsoft Teams Rooms의 관리에 대해 알아보시고 이 항목을 참조하세요.
ms.openlocfilehash: 52234f72c380c4f5af8f47fff51998fa8c3d1459
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117436"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft Teams Rooms 유지 관리 및 작업 
 
다음 세대 Skype Room Systems인 Microsoft Teams Rooms의 관리에 대해 알아보시고 이 항목을 참조하세요.
  
Microsoft Teams Room은 Microsoft의 최신 회의 솔루션으로 회의실을 풍부하고 공동 작업 환경으로 변환할 수 있습니다. 사용자는 친숙한 Microsoft Teams 또는 비즈니스용 Skype 인터페이스를 즐길 수 있으며 IT 관리자는 쉽게 배포되고 관리되는 Windows 10 Skype 모임 앱을 감사하게 됩니다. Microsoft Teams Room은 설치가 용이하도록 LCD 패널과 같은 기존 장비를 활용하여 Microsoft Teams 또는 비즈니스용 Skype를 회의실로 가져오기 위해 디자인되었습니다.
  
추가 구성을 통해 Azure Monitor를 사용하여 Microsoft Teams Rooms 관리 계획, [Azure Monitor를](azure-monitor-plan.md)사용하여 [Microsoft Teams Rooms](azure-monitor-deploy.md)관리 배포, Azure [Monitor를](azure-monitor-deploy.md)사용하여 Microsoft Teams Rooms 디바이스 관리에 설명된 바와 같이 Microsoft Azure Monitor를 사용하여 원격 관리가 가능합니다. 또한 사용자 지정 표시 테마 적용을 포함하는 XML 구성 파일을 사용하여 [원격으로 Microsoft Teams Rooms](xml-config-file.md)콘솔 설정을 관리할 수 있습니다. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Microsoft Teams Rooms에서 로그 수집
<a name="Logs"> </a>

로그를 수집하려면 Microsoft Teams Rooms 앱과 함께 배송하는 로그 컬렉션 스크립트를 호출해야 합니다. 관리자 모드에서 상승된 명령 프롬프트를 시작하고 다음 명령을 실행합니다.
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

로그는 c:\rigel의 ZIP 파일로 출력됩니다.
  
## <a name="front-of-room-display-settings"></a>룸 디스플레이 설정 전면
<a name="Display"> </a>

전면 디스플레이를 확장 모드로 구성합니다. 이렇게 하면 디스플레이에서 전원을 순환할 때 콘솔 UI가 해당 디스플레이에 중복되지 않도록 합니다.
  
> [!NOTE]
> 대기 모드에서 해제할 때 룸 전면 디스플레이가 활성 비디오 원본(예: MTR 콘솔)으로 자동으로 전환하려면 특정 조건을 충족해야 합니다. 이 기능은 선택 사항이지만 기본 하드웨어가 기능을 지원하는 Microsoft Teams Rooms 소프트웨어에서 지원됩니다. 전면 디스플레이로 사용되는 소비자 TV는 HDMI의 CEC(소비자 전자 제어) 기능을 지원해야 합니다.  선택한 도크 또는 콘솔(CEC를 지원하지 않을 수 있는 제조업체 지원 설명서 참조)에 따라 Crestron의 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 또는 [Extron의 Extron HD CTL 100과](https://www.extron.com/article/hdctl100ad) 같은 컨트롤러가 필요한 경우 원하는 동작을 사용하도록 설정할 수 있습니다. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft Teams Rooms 재설정(팩터리 복원)
<a name="Reset"> </a>

Microsoft Teams Rooms가 잘 실행되지 않는 경우 팩터리 재설정을 수행하는 것이 도움이 될 수 있습니다. 이렇게하려면 [Microsoft Teams Room 복구](recovery-tool.md) 도구를 사용하여 팩터리 복원 지침을 따릅니다.

> [!NOTE]
> 내 파일 유지 **-** 앱 및 설정을 제거하지만 Windows 재설정 프로세스 중에 개인 파일 옵션이 선택되어 있는 경우 Microsoft Teams Rooms를 사용할 수 없는 문제가 있습니다. 이 *옵션을* 사용하지 않습니다.
  
## <a name="supported-remote-options"></a>지원되는 원격 옵션
<a name="RemoteOptions"> </a>

다음 표에서는 가능한 원격 작업과 이를 수행하기 위해 사용할 수 있는 방법을 요약합니다.
  

|작업대|도메인에 가입되지 않은 경우|도메인에 가입된|
|:-----|:-----|:-----|
|다시 시작  <br/> |Teams 관리 센터  <br/> 원격 데스크톱  <br/> 원격 Powershell  <br/> | <br/>원격 데스크톱(추가 구성 필요)  <br/> 원격 Powershell(추가 구성 필요)  <br/> 구성 관리자  <br/> |
|OS 업데이트  <br/> |Windows 업데이트  <br/> |Windows 업데이트  <br/> WSUS  <br/> |
|앱 업데이트  <br/> |Windows 스토어  <br/> |Windows 스토어  <br/> 구성 관리자  <br/> |
|계정 구성  <br/> |Teams 관리 센터  <br/> |Teams 관리 센터  <br/> |
|액세스 로그  <br/> |Teams 관리 센터  <br/> |Teams 관리 센터 <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Microsoft Teams Rooms에 대한 그룹 정책 구성
<a name="GroupPolicy"> </a>

이 섹션에서는 Microsoft Teams Rooms가 올바르게 작동하기 위해 종속되는 시스템 설정을 다 설명합니다. Microsoft Teams Rooms를 도메인에 조인할 때 그룹 정책이 다음 표의 설정을 오버라이드하지 않도록 합니다.
  

|설정|허용|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Microsoft Teams Rooms를 부팅할 수 있습니다.  <br/> |
|Power Management - \> AC에서 10분 후에 화면 끄기  <br/> Power Management - \> AC에서 시스템을 절전에 놓지 않습니다.  <br/> |Microsoft Teams Rooms에서 연결된 디스플레이를 끄고 자동으로 절전 모드 해제할 수 있습니다.  <br/> |
|net 계정 /maxpwage:unlimited  <br/> 또는 로컬 계정에서 암호 만료를 사용할 수 없습니다. 이 작업을 실패하면 결국 Skype 계정이 만료된 암호에 대해 불평하는 로그온에 실패하게 됩니다. 이로 인해 컴퓨터의 모든 로컬 계정에 영향을 미치기 때문에 이를 설정하지 못하면 상자의 관리 계정도 결국 만료됩니다.  <br/> |Skype 계정이 항상 로그인할 수 있습니다.  <br/> |
   
그룹 정책을 사용하여 파일 전송은 파일 항목 구성 [에서 설명됩니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))

> [!NOTE]
> Microsoft Teams Rooms 디바이스가 Windows 10 OS의 다음 버전과 호환되는 경우 디바이스는 Windows 업데이트를 통해 자동으로 다음 버전으로 업데이트됩니다. Microsoft Teams Rooms 디바이스는 Windows 10의 다음 릴리스로 수동으로 업그레이드하거나 WUFB(Windows Update for Business) 그룹 정책을 사용하도록 설정하여 "받을 업데이트에 대한 Windows 준비 수준을 선택"하고 GPO를 통해 "미리 보기 빌드 및 기능 업데이트가 수신될 때 선택"으로 업그레이드하면 안 됩니다. 이러한 그룹 정책을 사용하도록 설정된 디바이스는 Microsoft Teams Rooms 앱에서 Windows 10 OS 업데이트에 문제가 있는 것으로 알려져 있습니다.

## <a name="remote-management-using-powershell"></a>PowerShell을 사용하여 원격 관리
<a name="RemotePS"> </a>

PowerShell을 사용하여 원격으로 다음 관리 작업을 수행할 수 있습니다(스크립트 샘플에 대한 아래 표 참조).
  
- 연결된 디바이스를 얻다
- 앱 상태 다운로드
- 시스템 정보 보기
- 시스템 재부팅
- 로그 검색
- 파일 전송(도메인에 가입된 Microsoft Teams Rooms 필요)
    
> [!NOTE]
> 이 기능은 기본적으로 꺼집니다. 아래 작업을 수행하려면 Microsoft Teams Rooms 시스템에서 사용자 환경에 대해 원격 PowerShell을 사용하도록 설정해야 합니다. 원격 PowerShell을 사용하도록 설정하는 방법에 대한 자세한 내용은 **[Enable-PSRemoting의](/powershell/module/microsoft.powershell.core/enable-psremoting)** 설명서를 참조하세요.
  
예를 들어 다음과 같이 원격 PowerShell을 사용하도록 설정할 수 있습니다.
  
1. Microsoft Teams Rooms 디바이스에서 관리자로 로그인합니다.
2. 상승된 PowerShell 명령 프롬프트를 실행합니다.
3. 다음 명령을 입력합니다. `Enable-PSRemoting -SkipNetworkProfileCheck -Force`
4. 로컬 보안 정책을 열고  관리자 보안 그룹을 **보안 설정** 로컬 정책 사용자 권한 할당 네트워크에 있는 이  >    >    >  **컴퓨터에 추가합니다.**

관리 작업을 수행하기 위해:
  
1. Microsoft Teams Rooms 디바이스에서 PowerShell 명령을 실행할 수 있는 권한이 있는 계정 자격 증명을 사용하여 PC에 로그인합니다.
2. PC에서 일반 PowerShell 명령 프롬프트를 실행합니다.
3. 아래 표에서 명령 텍스트를 복사하고 프롬프트에 붙여넣습니다.
4. 필드를  `<Device fqdn>` 환경에 적합한 FQDN 값으로 바 대체합니다.
5. 마스터의 파일 이름 및 로컬 경로로 SkypeSettings.xml 구성  *\<path\>*  파일(또는 테마 이미지)으로 바 대체합니다.
    
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

기본적으로 Microsoft Teams Rooms는 Windows Store에 연결하여 최신 버전의 Microsoft Teams Rooms 소프트웨어를 얻게 하려고 시도하기 때문에 디바이스에 일반 인터넷 액세스가 필요합니다. 지원 문제에 대해 Microsoft에 문의하기 전에 Microsoft Teams Rooms 디바이스가 최신 버전의 앱으로 로드된지 확인합니다.
  
기본적으로 Microsoft Teams Rooms는 Windows Update에 연결하여 운영 체제 및 USB 주변 장치 펌웨어 업데이트를 검색하고, 구성된 업무 시간 외부에 설치합니다. 관리자 계정에 로그인하고 설정 앱을 실행하여 업무 시간을 구성할 수 있습니다.
  
업데이트를 수동으로 관리하려는 경우 [Microsoft Store for Business에서](https://businessstore.microsoft.com/store) 오프라인 앱 배포를 위한 일반적인 절차를 따를 수 없는 경우, 구성 [](https://go.microsoft.com/fwlink/?linkid=851168) 관리자와 함께 사용할 수 있는 배포 키트에서 적절한 APPX 파일 및 종속성(지침에서 Microsoft Teams [Rooms 콘솔](console.md)구성)을 획득할 수 있습니다. [](/microsoft-store/distribute-offline-apps) 배포 키트 릴리스는 저장소 릴리스 뒤로 까다로우기 때문에 항상 사용 가능한 최신 빌드와 일치하지 않을 수 있습니다.
  
### <a name="to-update-using-powershell"></a>Powershell을 사용하여 업데이트

1. 설치 [MSI에서](https://go.microsoft.com/fwlink/?linkid=851168) 디바이스가 액세스할 수 있는 공유로 패키지를 추출합니다.
2. Microsoft Teams Rooms 디바이스를 대상으로 하는 다음 스크립트를 실행하여 적절하게 디바이스 \<share\> 공유로 변경합니다.
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a>관리자 모드 및 디바이스 관리
<a name="AdminMode"> </a>

개인 CA 인증서를 수동으로 설치하는 등 일부 관리 함수는 Surface Pro 디바이스를 관리자 모드로 배치해야 합니다. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Microsoft Teams Rooms 앱이 실행 중일 때 관리자 모드로 전환하고 다시

1. 지속적인 통화를 중단하고 홈 화면으로 돌아온다.
2. 기어 아이콘을 선택하고 메뉴를 시작합니다(옵션은 **설정,** **접근성** 및 디바이스 다시 **시작입니다).**
3. 설정을 **선택합니다.**
4. 관리자 암호를 입력합니다. 설정 화면이 나타납니다.  디바이스가 도메인에 가입되지 않은 경우 로컬 관리 계정(사용자 이름 "관리자")이 기본적으로 사용됩니다. 이 계정의 기본 암호는 'sfb'입니다. 가능한 한 빨리 암호를 변경합니다. 머신이 도메인에 가입된 경우 적절한 권한 있는 도메인 계정으로 로그인할 수 있습니다. 
5. 왼쪽 **열에서 Windows 설정을** 선택합니다.
6. 관리자 **로그인으로 이동 을 선택하세요.**
7. 관리자 암호를 입력합니다. 이렇게 하면 앱을 잘 로그오프하고 Windows 로그인 화면으로 표시됩니다. 
8. 관리 자격 증명을 사용하여 데스크톱에 로그인합니다. 디바이스를 관리하는 데 필요한 권한이 있습니다.
9. 필요한 관리 작업을 수행합니다.
10. 관리자 계정에서 로그인합니다.
11. 화면의 왼쪽에 있는 사용자 계정 아이콘을 선택한 다음 Skype를 선택하여 Microsoft Teams Rooms로 **돌아온다.**
    
    Skype **사용자가** 나열되지 않은 경우 다른  사용자를 선택하고 **.\skype를** 사용자 이름으로 입력하고 로그인해야 할 수 있습니다.
    
이제 콘솔이 정상 작동 모드로 돌아갑니다. 다음 절차에서는 키보드가 아직 연결되지 않은 경우 디바이스에 키보드를 연결해야 합니다. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Microsoft Teams Rooms 앱이 충돌할 때 관리자 모드로 전환

1. Windows 키를 5번 연속으로 누를 수 있습니다. 이렇게 하면 Windows 로그온 화면이 표시됩니다. 
2. 관리 자격 증명을 사용하여 데스크톱에 로그인합니다.
3. 필요한 관리 작업을 수행합니다.
4. 완료되면 컴퓨터를 다시 시작합니다.

    > [!NOTE]
    > 이 메서드는 Skype 사용자를 로그오프하거나 앱을 우호적으로 종료하지 않지만 앱이 응답하지 않는 경우 다른 메서드를 사용할 수 없는 경우 이 메서드를 사용합니다. 

   콘솔이 정상 작동 모드로 다시 시작되고 Microsoft Teams Rooms 앱을 실행합니다. 이 절차를 수행할 수 있도록 연결된 경우 키보드를 제거할 수 있습니다.
   ## <a name="troubleshooting-tips"></a>문제 해결 팁
   <a name="TS"> </a>

- 도메인 경계(예: 두 회사 간)를 통해 전송될 때 모임 초대가 나타나지 않을 수 있습니다. 이러한 경우 IT 관리자는 외부 사용자가 모임을 예약할 수 있도록 허용할지 여부를 결정해야 합니다.
- Microsoft Teams Rooms는 Exchange 2010을 통해 Exchange AutoDiscover 리디렉션을 지원하지 않습니다.
- 일반적으로 IT 관리자는 사용하지 않는 오디오 엔드포인트를 사용하지 않도록 설정하는 것이 좋습니다.
- 미러 이미지가 룸 미리 보기에 표시되는 경우 IT 관리자는 카메라 전원을 순환하거나 카메라 원격 제어를 사용하여 이미지 방향을 뒤집어 수정할 수 있습니다.
- 콘솔 터치 스크린 액세스의 손실이 발생하는 것으로 알려져 있습니다. 이러한 경우 Microsoft Teams Rooms 시스템을 다시 시작하여 문제가 해결될 수 있습니다.
- 유선 인제스트를 통해 PC를 콘솔에 연결할 때 로컬 오디오 손실이 발생하는 것으로 알려져 있습니다. 이러한 경우 PC를 다시 시작하면 로컬 오디오 재생 문제가 해결될 수 있습니다.
