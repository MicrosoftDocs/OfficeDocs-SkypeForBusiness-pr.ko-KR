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
description: 다운로드, 설치 및 Windows PowerShell 5.1을 사용하여 온라인에 연결하는 원격 PowerShell 세션을 비즈니스용 Skype 있습니다.
ms.openlocfilehash: af3d4346b699c6511b17b0cce0e881c91ceb927cb4a9e5cba57674fb96751b77
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308039"
---
# <a name="download-and-install-windows-powershell-51"></a>Windows PowerShell 5.1 다운로드 및 설치

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Windows 10 업데이트 또는 Windows Server 2016 사용 중이면 이미 5.1 Windows PowerShell 있습니다. 이 애플리케이션은 해당 운영 체제와 함께 사전 설치됩니다.
  
사용하는 Microsoft PowerShelll 버전을 확인하려면 서버 2008 R2 또는 Windows 7 또는 Windows 컴퓨터에서 다음을 Windows Server 2012 합니다.
  
1. **시작을** 클릭하고 모든 프로그램을 **클릭하고** 액세서리를 **클릭하고** Windows PowerShell **클릭한** 다음 을 **Windows PowerShell.**
    
2. PowerShell 콘솔에서 다음 명령을 입력한 다음 ENTER를 누를 수 있습니다.
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. 그런 다음 콘솔 창에 다음과 유사한 정보를 표시해야 합니다.
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    반환된 버전 번호가 5.1이면 5.1 Windows PowerShell 실행됩니다. 반환된 버전 번호가 5.1이 아닌 경우 5.1 Windows PowerShell 설치해야 합니다. Microsoft 다운로드 센터에서 Windows Management Framework 5.1을 포함하는 Windows PowerShell 5.1을 [다운로드할 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=54616)
  
5.1이 Windows PowerShell 확인한 후 PowerShell이 원격 스크립트를 실행하도록 구성되어 있는지 확인해야 합니다. 이를 위해 관리자 권한으로 PowerShell을 시작합니다. Windows 7에서는 Windows 서버 2008 R2, Windows Server 2012 또는 Windows Server 2012 R2에서 다음을 실행합니다.
  
1. **시작,** 모든 프로그램 **클릭,** 액세서리 **클릭,** Windows PowerShell **클릭,** Windows PowerShell 마우스 오른쪽 단추로 **클릭한** 다음 관리자로 **실행을 클릭합니다.**
    
2. 사용자 계정 **제어** 대화 상자가 나타나면 **예를** 클릭하여 관리자 자격 증명에서 PowerShell을 실행할지 여부를 확인할 수 있습니다.
    
실행 중인 Windows 8 대신 이 절차를 완료합니다.
  
1. 참 표시줄에 액세스하고 **검색을** 클릭한 다음 을 마우스 **오른쪽 단추로 Windows PowerShell.** 모든 컴퓨터(터치 스크린 또는 Windows 8 터치 스크린)에서 참스 표시줄에 빠르게 액세스할 수 Windows 키를 누를 수 있습니다.
    
2. 화면 아래쪽의 도구 모음에서 관리자 **권한으로 실행을 클릭합니다.**
    
3. 사용자 계정 **제어** 대화 상자가 나타나면 **예를** 클릭하여 관리자 자격 증명에서 PowerShell을 실행할지 여부를 확인할 수 있습니다.
    
PowerShell이 실행되고 나면 원격 스크립트를 실행하도록 실행 정책을 변경해야 합니다. PowerShell 콘솔에서 다음 명령을 입력한 다음 ENTER를 누를 수 있습니다.
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> 위의 명령을 실행하면 다음 오류 메시지가 표시될 수 있습니다. > Set-ExecutionPolicy : 레지스트리 키의 HKEY_LOCAL_MACHINE *\\ SOFTWARE Microsoft \\ \\ PowerShell \\ 1 \\ ShellIds \\ Micrsoft.PowerShell'에 대한 액세스가* 거부될 수 있습니다. 이 오류 메시지는 일반적으로 관리자 자격 증명 아래에서 PowerShell을 실행하지 않는 경우 발생합니다. PowerShell 세션을 닫고 관리자로 새 세션을 시작합니다.
 
실행 정책이 올바르게 구성되고 있는지 확인하려면 PowerShell 프롬프트에 다음을 입력한 다음 ENTER를 누를 수 있습니다.
  
```PowerShell
Get-ExecutionPolicy
```

다음 값을 되돌리면 모든 값이 올바르게 구성되었습니다.
  
`RemoteSigned`

현재 Windows PowerShell 5.1을 실행하지 않는 경우 Microsoft 다운로드 센터에서 Windows Management Framework 5.1을 다운로드하고 설치해야 합니다. 이 패키지는 WinRM(원격 관리) Windows PowerShell 5.1 및 Windows 3.0을 포함하는 설치 패키지입니다. 예를 들어 7 SP1을 실행하고 아직 5.1 버전으로 Windows 없는 경우 이 설치 패키지가 Windows PowerShell 수 있습니다. Windows Server 2016 또는 Windows 10 업데이트가 실행되는 경우 5.1 Windows PowerShell 필요가 없습니다. Windows PowerShell 5.1은 해당 운영 체제에 미리 설치됩니다.
  
5.1 Windows Management Framework 설치하기 전에:
  
- 올바른 버전의 설치 패키지를 다운로드한지 확인합니다. 64비트 버전의 7 SP1을 Windows 경우 파일을 Win7AndW2K8R2-KB3191566-x64.ZIP. 32비트 버전의 7을 실행하는 Windows 파일을 다운로드하면 Win7-KB3191566-x86.ZIP.
    
- 컴퓨터에서 Windows 7을 실행하는 경우 7 서비스 팩 1에 Windows 있는지 확인합니다.

실행 중인 Windows 버전이 확실하지 않은 경우 또는 7 서비스 팩 1을 설치한 Windows 확실하지 않은 경우 시작, 컴퓨터 마우스 오른쪽 단추로 클릭한 다음 속성을 **클릭합니다.** 이 정보는 시스템 대화 상자에 보고됩니다.
  
Windows Management Framework 5.1을 설치하려면 [WMF 5.1](/powershell/scripting/wmf/setup/install-configure)설치 및 구성에서 절차를 완료합니다.
  
컴퓨터가 다시 부팅된 후 Windows PowerShell 시작하고 애플리케이션을 관리 자격 증명에서 실행할 수 있는지 확인합니다. 이 작업을 위해:
  
1. **시작,** 모든 프로그램 클릭, 액세서리 **클릭,** Windows PowerShell **클릭,** Windows PowerShell 마우스 오른쪽 단추로 클릭한 다음 관리자 권한으로 **실행을 클릭합니다.**  
    
2. 사용자 계정 제어 대화 상자가 나타나면 **예를** 클릭하여 관리자 자격 증명에서 PowerShell을 실행할지 여부를 확인할 수 있습니다.
    
PowerShell 콘솔이 나타나면 WinRM 서비스가 실행 중이고 올바르게 구성된지 확인해야 합니다. 서비스가 실행 중이지 확인을 위해 PowerShell 프롬프트에 다음 명령을 입력한 다음 ENTER를 누를 수 있습니다.
  
```PowerShell
Get-Service winrm
```

그런 다음 WinRM 서비스에 대한 정보가 화면에 표시됩니다.
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

서비스 상태가 "실행 중"과 같지 않은 경우 다음 명령을 입력한 다음 ENTER를 눌러 WinRM 서비스를 시작합니다.
  
```PowerShell
Start-Service winrm
```

서비스가 시작된 후 다음 명령을 실행하여 WinRM이 기본 인증을 사용하고 있는지 확인합니다.
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

다음과 유사한 정보가 화면에 표시됩니다.
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

기본 인증이 true로 설정되어 있는 경우 PowerShell을 사용하여 온라인에 비즈니스용 Skype 있습니다.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>관련 항목
[Windows PowerShell용 컴퓨터 설정](set-up-your-computer-for-windows-powershell.md) 

  
