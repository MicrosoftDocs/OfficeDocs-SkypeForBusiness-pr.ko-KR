---
title: Microsoft 팀 회의실 유지 관리 및 운영
ms.author: v-lanac
author: lanachin
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
description: 이 항목에서는 차세대 Skype 대화방 시스템인 Microsoft 팀 회의실 관리에 대해 자세히 알아보세요.
ms.openlocfilehash: 1fecf852c11e7ab89e0cdc7dc6caf615182e7d5f
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "43157763"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a>Microsoft 팀 회의실 유지 관리 및 운영 
 
이 항목에서는 차세대 Skype 대화방 시스템인 Microsoft 팀 회의실 관리에 대해 자세히 알아보세요.
  
Microsoft 팀 대화방은 회의실을 다양 한 공동 작업 환경으로 변환 하도록 설계 된 Microsoft의 최신 회의 솔루션입니다. 사용자는 친숙 한 Microsoft 팀 또는 비즈니스용 Skype 인터페이스를 즐길 수 있으며 IT 관리자가 Windows 10 Skype 모임 앱을 쉽게 배포 하 고 관리 하는 데 감사 합니다. Microsoft 팀 공간은 설치 하기 쉽도록 LCD 패널과 같은 기존 장비를 이용 하 여 Microsoft 팀 또는 비즈니스용 Skype를 회의실에 제공할 수 있도록 설계 되었습니다.
  
추가 구성을 사용 하는 경우 azure monitor를 사용 하 여 [Microsoft 팀 공간 관리 계획](azure-monitor-plan.md), Azure [모니터로 microsoft 팀 대화방 관리 배포](azure-monitor-deploy.md), [azure Monitor를 사용 하 여 microsoft 팀 회의실 장치 관리](azure-monitor-deploy.md)에 설명 된 microsoft Azure Monitor를 사용 하 여 원격 관리를 할 수 있습니다. 사용자 지정 표시 테마 적용을 포함 하 여 [XML 구성 파일을 사용 하 여 원격으로 Microsoft 팀 공간 콘솔 설정을 관리할](xml-config-file.md)수도 있습니다. 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a>Microsoft 팀 방에 대 한 로그 수집
<a name="Logs"> </a>

로그를 수집 하려면 Microsoft 팀 대화방 앱과 함께 제공 되는 로그 수집 스크립트를 호출 해야 합니다. 관리 모드에서 관리자 권한 PowerShell 프롬프트를 시작 하 고 다음 명령을 실행 합니다.
  
```PowerShell
c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1 -ExecutionPolicy unrestricted
```

로그는 c:\rigel.에서 ZIP 파일로 출력 됩니다.
  
## <a name="front-of-room-display-settings"></a>회의실 디스플레이 설정 전면
<a name="Display"> </a>

확장 모드로 방 디스플레이를 구성 합니다. 이렇게 하면 디스플레이 전원을 켤 때 콘솔 UI가 해당 디스플레이에 복제 되지 않습니다.
  
> [!NOTE]
> 원본에서 대기 모드를 해제할 때 자동으로 활성 비디오 원본 (예: MTR 콘솔)으로 전환 하려면 특정 조건이 충족 되어야 합니다. 이 기능은 선택 사항 이지만 Microsoft 팀 공간 소프트웨어에서 지원 되며, 기본 하드웨어에서 기능을 지 원하는 경우 제공 됩니다. 채팅방 표시로 사용 되는 소비자 TV는 HDMI의 CEC (소비자 전자 컨트롤) 기능을 지원 해야 합니다.  선택 된 dock 또는 console (CEC를 지원 하지 않을 수 있음, 제조업체 지원 문서 참조)에 따라, 원하는 동작을 사용 하도록 설정 하려면 hd [-RX-201-C-](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) [100](https://www.extron.com/article/hdctl100ad) E와 같은 컨트롤러가 필요할 수 있습니다. 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a>Microsoft 팀 대화방 재설정 (출하 시 복원)
<a name="Reset"> </a>

Microsoft 팀 채팅방이 제대로 실행 되 고 있지 않은 경우 공장 초기화를 수행 하는 데 도움이 될 수 있습니다. 이렇게 하려면 [Microsoft 팀 대화방 복구 도구](recovery-tool.md) 를 사용 하 여 공장 복원 지침을 따르세요.

> [!NOTE]
> Microsoft 팀 대화방을 사용할 수 없게 되는 알려진 문제가 있습니다. **내 파일 유지-앱과 설정을 제거 하지만,** Windows 재설정 프로세스 중에 개인 파일 옵션 유지 옵션이 선택 되어 있습니다. 이 옵션을 사용 *하지* 마세요.
  
## <a name="supported-remote-options"></a>지원 되는 원격 옵션
<a name="RemoteOptions"> </a>

다음 표에서는 가능한 원격 작업 및이를 수행 하는 데 사용할 수 있는 메서드를 요약 하 여 설명 합니다.
  

|작업 그룹|도메인에 가입 되어 있지 않음|도메인 가입 됨|
|:-----|:-----|:-----|
|했다가  <br/> |원격 데스크톱  <br/> 원격 Powershell  <br/> |원격 데스크톱 (추가 구성 필요)  <br/> 원격 Powershell (추가 구성 필요)  <br/> 구성 관리자  <br/> |
|OS 업데이트  <br/> |Windows 업데이트  <br/> |Windows 업데이트  <br/> WSUS  <br/> |
|앱 업데이트  <br/> |Windows 스토어  <br/> |Windows 스토어  <br/> 구성 관리자  <br/> |
|Skype 계정 구성  <br/> |현재 지원 되지 않음  <br/> |현재 지원 되지 않음  <br/> |
|Access 로그  <br/> |현재 지원 되지 않음  <br/> |현재 지원 되지 않음  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a>Microsoft 팀 대화방에 대 한 그룹 정책 구성
<a name="GroupPolicy"> </a>

이 섹션에서는 Microsoft 팀 대화방에서 제대로 작동 하는 데 의존 하는 시스템 설정을 다룹니다. Microsoft 팀 대화방을 도메인에 참가 하는 경우 그룹 정책이 다음 표의 설정을 재정의 하지 않는지 확인 합니다.
  

|설정|가능|
|:-----|:-----|
|HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1  <br/> |Microsoft 팀 회의실을 부팅할 수 있도록 설정  <br/> |
|전원 관리-\> AC, 10 분 후 화면 끄기  <br/> 전원 관리-\> AC, 시스템을 절전 모드로 전환 안 함  <br/> |Microsoft 팀 대화방에서 연결 된 디스플레이를 끄고 자동으로 절전 모드 해제 하도록 설정  <br/> |
|네트 계정/maxpwage: 무제한  <br/> 또는 동등한 방법으로 로컬 계정에서 암호 만료를 비활성화 합니다. 이 작업을 수행 하지 않으면 결국 Skype 계정에 만료 된 비밀 번호에 대 한 로그온 complaining 실패 하 게 됩니다. 이로 인해 컴퓨터의 모든 로컬 계정에 영향을 줄 수 있으므로이를 설정 하지 않으면 상자의 관리 계정도 결국 만료 됩니다.  <br/> |Skype 계정이 항상 로그인 할 수 있도록 합니다.  <br/> |
   
그룹 정책을 사용 하 여 파일을 전송 하는 방법에 대해서는 [파일 항목 구성을](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)설명 합니다.

> [!NOTE]
> Microsoft 팀 대화방 장치가 Windows 10 OS의 다음 버전과 호환 되는 경우이 장치는 자동으로 Windows Update를 통해 다음 버전으로 업데이트 됩니다. Microsoft 팀 공간 장치를 수동으로 또는 windows 10의 다음 릴리스로 업그레이드할 수 없습니다 (WUFB). 그룹 정책 "받을 업데이트에 대 한 Windows 준비 수준 수준을 선택" 및 "Preview 빌드 및 기능 업데이트가 수신 되는 경우"를 통해 GPO를 사용 하 여 선택 합니다. 이러한 그룹 정책을 사용 하는 디바이스는 Microsoft 팀 대화방 앱에서 Windows 10 OS 업데이트 문제를 발생 하는 것으로 알려져 있습니다.

## <a name="remote-management-using-powershell"></a>PowerShell을 사용 하 여 원격 관리
<a name="RemotePS"> </a>

PowerShell을 사용 하 여 원격으로 다음 관리 작업을 수행할 수 있습니다 (스크립트 샘플은 아래 표 참조).
  
- 연결 된 장치 가져오기
- 앱 상태 가져오기
- 시스템 정보 가져오기
- 시스템 다시 부팅
- 로그 검색
- 파일 전송 (도메인에 가입 된 Microsoft 팀 대화방 필요)
    
> [!NOTE]
> 이 기능은 기본적으로 해제 되어 있습니다. 아래 작업을 수행 하려면 Microsoft 팀 대화방 시스템에서 환경에 대 한 원격 PowerShell을 사용 하도록 설정 해야 합니다. 원격 PowerShell을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 **[enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** 의 설명서를 참조 하세요.
  
예를 들어 다음과 같이 원격 PowerShell을 설정할 수 있습니다.
  
1. Microsoft 팀 대화방 장치에서 관리자로 로그인 합니다.
2. 관리자 권한 PowerShell 명령 프롬프트를 엽니다.
3. Enable-PSRemoting-force 명령을 입력 합니다.

관리 작업을 수행 하려면 다음을 실행 합니다.
  
1. Microsoft 팀 회의실 장치에서 PowerShell 명령을 실행할 권한이 있는 계정 자격 증명으로 PC에 로그인 합니다.
2. PC에서 일반 PowerShell 명령 프롬프트를 엽니다.
3. 아래 표의 명령 텍스트를 복사 하 고 프롬프트에 붙여 넣습니다.
4. 필드 `<Device fqdn>` 를 사용자 환경에 적합 한 FQDN 값으로 바꿉니다.
5. * \<경로\> * 를 마스터 SkypeSettings 구성 파일 (또는 테마 이미지)의 파일 이름 및 로컬 경로로 바꿉니다.
    
연결 된 장치를 얻으려면
  
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

XML 구성 파일 (또는 테마 그래픽) 푸시
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a>소프트웨어 업데이트
<a name="SWupdate"> </a>

기본적으로 Microsoft 팀 대화방에서 최신 버전의 Microsoft 팀 공간 소프트웨어를 다운로드 하기 위해 Windows 스토어에 연결 하려고 시도 하므로 장치에 일반 인터넷 액세스가 필요 합니다. Microsoft에서 지원 문제를 해결 하기 전에 Microsoft 팀 대화방 장치가 최신 버전의 앱을 사용 하 여 로드 되어 있는지 확인 합니다.
  
기본적으로 Microsoft 팀 대화방은 Windows Update에 연결 하 여 운영 체제 및 USB 주변 장치 펌웨어 업데이트를 검색 하 고, 구성 된 업무 시간 외에 설치 합니다. 관리자 계정에 로그인 하 고 설정 앱을 실행 하 여 업무 시간을 구성할 수 있습니다.
  
업데이트를 수동으로 관리 하 고 [Microsoft Store For Business](https://businessstore.microsoft.com/store) online에서 [오프 라인 앱을 배포](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)하는 것을 수행할 수 없는 경우에는 구성 관리자와 함께 사용할 수 있는 [배포 키트](https://go.microsoft.com/fwlink/?linkid=851168) ( [microsoft 팀 대화방 콘솔 구성](console.md)지침 참조)에서 적절 한 APPX 파일과 종속성을 얻을 수 있습니다. 배포 키트 릴리스는 스토어 릴리스에서 지연 되므로 사용 가능한 최신 빌드와 항상 일치 하지 않을 수 있습니다.
  
### <a name="to-update-using-powershell"></a>Powershell을 사용 하 여 업데이트 하려면

1. 설치 [MSI](https://go.microsoft.com/fwlink/?linkid=851168) 에서 장치에 액세스할 수 있는 공유로 패키지를 추출 합니다.
2. Microsoft 팀 회의실 장치를 대상으로 하는 다음 스크립트를 \<실행\> 하 고 장치 공유에 대 한 공유를 적절 하 게 변경 합니다.
    
```PowerShell
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a>관리 모드 및 장치 관리
<a name="AdminMode"> </a>

개인 CA 인증서를 수동으로 설치 하는 등의 일부 관리 기능은 Surface Pro 장치를 관리 모드로 전환 해야 합니다. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a>Microsoft 팀 대화방 앱이 실행 중일 때 관리 모드로 전환 및 돌아가기

1. 진행 중인 통화를 모두 끊고 홈 화면으로 돌아갑니다.
2. 기어 아이콘을 선택 하 고 메뉴를 표시 합니다 ( **설정**, **접근성**및 **장치 다시 시작** 옵션).
3. **설정을**선택 합니다.
4. 관리자 암호를 입력 합니다. 설정 화면이 표시 됩니다.  디바이스가 도메인에 가입 되어 있지 않으면 기본적으로 로컬 관리 계정 (사용자 이름 "관리자")을 사용 합니다. 이 계정의 기본 암호는 ' sfb ' 이며, 최대한 빨리 암호를 변경 합니다. 컴퓨터가 도메인에 가입 되어 있는 경우 적절 한 권한 도메인 계정으로 로그인 할 수 있습니다. 
5. 왼쪽 열에서 **Windows 설정을** 선택 합니다.
6. **관리자 로그인으로 이동을**선택 합니다.
7. 관리자 암호를 입력 합니다. 이렇게 하면 앱이 적절 하 게 로그 오프 되 고 Windows 로그인 화면으로 이동 합니다. 
8. 관리 자격 증명을 사용 하 여 데스크톱에 로그인 합니다. 장치를 관리 하는 데 필요한 권한이 있습니다.
9. 필요한 관리 작업을 수행 합니다.
10. 관리자 계정에서 로그 아웃 합니다.
11. 화면 왼쪽 끝에 있는 사용자 계정 아이콘을 선택한 다음 **Skype**를 선택 하 여 Microsoft 팀 대화방으로 돌아갑니다.
    
    **Skype** 사용자가 목록에 없는 경우 **다른 사용자** 를 선택 하 고 사용자 이름으로 **.\skype** 를 입력 한 후 로그인 해야 할 수 있습니다.
    
이제 콘솔이 정상 작동 모드로 돌아갑니다. 다음 절차에서는 키보드가 아직 연결 되어 있지 않은 경우 장치에 연결 해야 합니다. 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a>Microsoft 팀 대화방 앱이 충돌 하는 경우 관리 모드로 전환 및 돌아가기

1. Windows 키를 다섯 번 빠르게 연속적으로 누릅니다. Windows 로그온 화면이 표시 됩니다. 
2. 관리 자격 증명을 사용 하 여 데스크톱에 로그인 합니다.
3. 필요한 관리 작업을 수행 합니다.
4. 완료 되 면 컴퓨터를 다시 시작 합니다.

    > [!NOTE]
    > 이 방법은 Skype 사용자를 끄거나 앱을 정상적으로 종료 하지는 않지만 앱이 응답 하지 않고 다른 방법을 사용할 수 없는 경우에도 사용 합니다. 

   콘솔이 정상 작동 모드로 다시 시작 되어 Microsoft 팀 회의실 앱을 실행 합니다. 이 절차를 수행할 수 있도록 연결 된 경우 키보드를 제거할 수 있습니다.
   ## <a name="troubleshooting-tips"></a>문제 해결 팁
   <a name="TS"> </a>

- 도메인 경계를 넘어 전송 되는 경우 모임 초대가 표시 되지 않을 수 있습니다 (예: 두 회사 간). 이러한 경우 IT 관리자는 외부 사용자가 모임을 예약할 수 있도록 허용할지 여부를 결정 해야 합니다.
- Microsoft 팀 대화방은 Exchange 2010를 통해 Exchange 자동 검색 리디렉션을 지원 하지 않습니다.
- 일반적으로 IT 관리자는 사용 하지 않으려는 오디오 끝점을 비활성화 하는 것이 좋습니다.
- 룸 미리 보기에 미러 이미지가 표시 되는 경우, IT 관리자는 카메라 전원을 순환 하거나 카메라 리모컨을 사용 하 여 이미지 방향을 대칭 이동 하 여 수정할 수 있습니다.
- 콘솔 터치 스크린의 손실에 대 한 액세스가 발생 하는 것으로 알려졌습니다. 이러한 경우에는 Microsoft 팀 대화방 시스템을 다시 시작 하 여 문제가 해결 되기도 합니다.
- 유선 수집을 통해 PC를 콘솔에 연결할 때 로컬 오디오 손실이 발생 하는 것으로 알려져 있습니다. 이러한 경우 PC를 다시 시작 하면 로컬 오디오 재생 문제를 해결할 수 있습니다.
    
