---
title: Windows PowerShell 5.1 다운로드 및 설치
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Windows PowerShell 5.1을 다운로드 하 여 설치한 다음 비즈니스용 Skype Online에 연결 하는 원격 PowerShell 세션을 만듭니다.
ms.openlocfilehash: 64d1ed1b3e3031f5186a09289ab6e1d9088840cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029099"
---
# <a name="download-and-install-windows-powershell-51"></a>Windows PowerShell 5.1 다운로드 및 설치

Windows 10 기념 업데이트 또는 Windows Server 2016를 사용 하는 경우 Windows PowerShell 5.1이 이미 설치 되어 있어야 합니다. 이 응용 프로그램은 해당 운영 체제에 사전 설치 되어 있기 때문입니다.
  
사용 중인 Microsoft PowerShelll 버전을 확인 하려면 Windows 7 또는 Windows Server 2008 R2 또는 Windows Server 2012 컴퓨터에서 다음을 실행 합니다.
  
1. **시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **보조 프로그램**, **windows powershell**, **windows powershell**을 차례로 클릭 합니다.
    
2. PowerShell 콘솔에 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. 다음과 유사한 정보가 콘솔 창에 표시 되어야 합니다.
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    반환 되는 버전 번호가 5.1 이면 Windows PowerShell 5.1을 실행 하는 것입니다. 반환 되는 버전 번호가 5.1이 아닌 경우 Windows PowerShell 5.1을 설치 해야 합니다. [Microsoft 다운로드 센터](https://www.microsoft.com/download/details.aspx?id=54616)에서 windows PowerShell 5.1을 포함 하는 Windows Management 프레임 워크 5.1을 다운로드할 수 있습니다.
  
Windows PowerShell 5.1이 설치 되어 있는지 확인 한 후에는 원격 스크립트 실행을 위해 PowerShell이 구성 되어 있는지 확인 해야 합니다. 이렇게 하려면 관리자로 PowerShell을 시작 합니다. Windows 7, Windows Server 2008 R2, Windows Server 2012 또는 Windows Server 2012 R2에서는 다음을 수행 합니다.
  
1. **시작**, **모든 프로그램**, **액세서리**, **Windows PowerShell**을 차례로 클릭 하 고 **windows powershell**을 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.
    
2. **사용자 계정 컨트롤** 대화 상자가 표시 되는 경우 **예** 를 클릭 하 여 관리자 자격 증명에서 PowerShell을 실행 하도록 확인 합니다.
    
Windows 8을 실행 하는 경우 대신 다음 절차를 완료 하세요.
  
1. 참 메뉴 표시줄에 액세스 하 고 **검색**을 클릭 한 다음 **Windows PowerShell**을 마우스 오른쪽 단추로 클릭 합니다. Windows 키를 누른 채 C를 눌러 Windows 8 컴퓨터 (터치 스크린 또는 터치 못 함 화면)의 참 메뉴 표시줄에 빠르게 액세스할 수 있습니다.
    
2. 화면 아래쪽에 있는 도구 모음에서 **관리자 권한으로 실행**을 클릭 합니다.
    
3. **사용자 계정 컨트롤** 대화 상자가 표시 되는 경우 **예** 를 클릭 하 여 관리자 자격 증명에서 PowerShell을 실행 하도록 확인 합니다.
    
PowerShell을 실행 한 후에는 원격 스크립트 실행을 허용 하도록 실행 정책을 변경 해야 합니다. PowerShell 콘솔에 다음 명령을 입력 하 고 enter 키를 누릅니다.
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> 앞의 명령을 실행 하면 다음과 같은 오류 메시지가 표시 될 수 있습니다. > *Set-ExecutionPolicy: 레지스트리 키에 대 한 액세스 권한 '\\HKEY_LOCAL_MACHINE\\소프트웨어\\Microsoft\\PowerShell\\1\\ShellIds Micrsoft. PowerShell '이 (가) 거부 되었습니다.* 이 오류 메시지는 일반적으로 관리자 자격 증명으로 PowerShell을 실행 하지 않는 경우에 발생 합니다. PowerShell 세션을 닫고 관리자로 새 세션을 시작 합니다.
 
실행 정책이 올바르게 구성 되었는지 확인 하려면 PowerShell 프롬프트에서 다음을 입력 하 고 enter 키를 누릅니다.
  
```PowerShell
Get-ExecutionPolicy
```

다음 값을 다시 가져오면 모든 항목이 올바르게 구성 되었습니다.
  
`RemoteSigned`

현재 Windows PowerShell 5.1을 실행 하 고 있지 않은 경우 Microsoft 다운로드 센터에서 Windows 관리 프레임 워크 5.1을 다운로드 하 여 설치 해야 합니다. Windows PowerShell 5.1 및 WinRM (Windows Remote Management) 3.0을 포함 하는 설치 패키지입니다. 예를 들어 Windows 7 SP1을 실행 중이 고 아직 Windows PowerShell 5.1을 업데이트 하지 않은 경우이 설치 패키지가 필요할 수 있습니다. Windows Server 2016 또는 Windows 10 기념 업데이트를 실행 하는 경우 Windows PowerShell 5.1을 설치할 필요가 없습니다. Windows PowerShell 5.1은 이러한 운영 체제에 사전 설치 되어 있습니다.
  
Windows 관리 프레임 워크 5.1을 설치 하기 전에 다음을 수행 합니다.
  
- 올바른 버전의 설치 패키지를 다운로드 했는지 확인 합니다. 64 비트 버전의 Windows 7 SP1을 실행 하는 경우 Win7AndW2K8R2-KB3191566-x64 파일을 다운로드 합니다. 32 비트 버전의 Windows 7을 실행 하는 경우 Win7-KB3191566-x86 파일을 다운로드 합니다.
    
- 컴퓨터에서 Windows 7을 실행 하는 경우 Windows 7 서비스 팩 1을 설치 했는지 확인 합니다.

실행 중인 Windows 버전을 잘 모르거나 Windows 7 서비스 팩 1을 설치 했는지 확실 하지 않은 경우 **시작**을 클릭 하 고 **컴퓨터**를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다. 이 정보는 시스템 대화 상자에 보고 됩니다.
  
Windows 관리 프레임 워크 5.1를 설치 하려면 [WMF 5.1 설치 및 구성](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure)의 절차를 완료 합니다.
  
컴퓨터를 다시 부팅 한 후에는 Windows PowerShell이 시작 될 수 있고 관리 자격 증명으로 응용 프로그램을 실행할 수 있는지 확인 합니다. 실행할 작업:
  
1. **시작**, **모든 프로그램**, **보조 프로그램**, **Windows PowerShell**을 차례로 클릭 하 고 **windows powershell** 을 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.
    
2. 사용자 계정 컨트롤 대화 상자가 표시 되는 경우 **예** 를 클릭 하 여 관리자 자격 증명에서 PowerShell을 실행 하도록 확인 합니다.
    
PowerShell 콘솔이 나타나면 WinRM 서비스가 실행 중이 고 올바르게 구성 되어 있는지 확인 해야 합니다. 서비스가 실행 중인지 확인 하려면 PowerShell 프롬프트에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
  
```PowerShell
Get-Service winrm
```

WinRM 서비스에 대 한 정보가 화면에 표시 됩니다.
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

서비스 상태가 "실행 중"이 아니면 다음 명령을 입력 하 고 ENTER 키를 눌러 WinRM 서비스를 시작 합니다.
  
```PowerShell
Start-Service winrm
```

서비스가 시작 되 면 다음 명령을 실행 하 여 WinRM이 기본 인증을 사용 하 고 있는지 확인 합니다.
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

다음과 유사한 정보가 화면에 표시 됩니다.
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

기본 인증이 true로 설정 되어 있으면 PowerShell을 사용 하 여 비즈니스용 Skype Online에 연결할 준비가 된 것입니다.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>관련 항목
[Windows PowerShell용 컴퓨터 설정](set-up-your-computer-for-windows-powershell.md) 

  
 
