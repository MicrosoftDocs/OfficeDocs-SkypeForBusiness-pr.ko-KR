---
title: 비즈니스용 Skype Online 커넥터의 연결 문제 진단
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 가져오기 모듈, 동시 셸, 라이브 ID 및 권한 오류를 포함하여 비즈니스용 Skype Online에 연결하는 원격 PowerShell 세션 만들기 문제를 해결합니다.
ms.openlocfilehash: c2092da0324a147b182ce7715e757f1ed039aa65
ms.sourcegitcommit: 1ac37cc27d4ccb3e1dae20ca1929214e17be2075
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2022
ms.locfileid: "65913396"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>비즈니스용 Skype Online 커넥터의 연결 문제 진단

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

이 항목에서는 비즈니스용 Skype Online에 연결하는 원격 Microsoft PowerShell 세션을 만들 때 발생할 수 있는 문제를 진단하고 해결하는 데 도움이 되는 정보를 제공합니다. 다음 섹션을 참조하세요.
  
- [Windows PowerShell 실행 정책으로 인한 가져오기-모듈 오류](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [잘못된 버전의 Windows PowerShell로 인한 가져오기-모듈 오류](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [WinRM 기본 인증을 사용하지 않도록 설정한 경우 최신 인증 실패](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [라이브 ID 서버에 연결하지 못했습니다.](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
      
- [사용자에 대한 로그인 실패](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [사용자에게 이 테넌트 관리 권한이 없습니다.](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [비즈니스용 Skype Online에서 테넌트에 연결하는 기능이 비활성화되었습니다.](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [비즈니스용 Skype Online에서 이 사용자의 최대 동시 셸 수를 초과했습니다.](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [비즈니스용 Skype Online에서 이 테넌트의 최대 동시 셸 수를 초과했습니다.](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Windows PowerShell 실행 정책으로 인한 Import-Module 오류
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 실행 정책은 PowerShell 콘솔에 로드할 수 있는 구성 파일과 사용자가 해당 콘솔에서 실행할 수 있는 스크립트를 결정하는 데 도움이 됩니다. 실행 정책이 RemoteSigned로 설정되지 않은 경우 최소한 비즈니스용 Skype Online 커넥터 모듈을 가져올 수 없습니다. 모듈이 없는 경우 모듈을 가져오려고 할 때 다음 오류 메시지가 표시됩니다.
  
- **오류**: <em>가져오기-모듈: 파일 C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1은 이 시스템에서 스크립트를 실행할 수 없으므로 로드할 수 없습니다. 자세한 내용은 about_Execution_Policies 참조하세요 https://go.microsoft.com/fwlink/?LinkID=135170.</em>

- **해상도** 이 문제를 해결하려면 관리자 권한으로 PowerShell을 시작한 다음, 다음 명령을 실행합니다.
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    실행 정책에 대한 자세한 내용은 [실행 정책 정보를](/powershell/module/microsoft.powershell.core/about/about_execution_policies) 참조하세요.
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>잘못된 버전의 Windows PowerShell로 인한 Import-Module 오류
<a name="BKMKIncorrectVersion"> </a>

비즈니스용 Skype Online 커넥터 모듈은 Windows PowerShell 3.0에서만 실행할 수 있습니다. 이전 버전의 PowerShell에서 모듈을 가져오려고 하면 이 메시지와 유사한 오류 메시지와 함께 가져오기 프로세스가 실패합니다.
  
  - **오류**: *Import-Module: 로드된 PowerShell의 버전은 '2.0'입니다. 'D:\\Program Files Common Files\\\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector LyncOnlineConnector.psd1\\' 모듈을 실행하려면 최소 '3.0' PowerShell 버전이 필요합니다. PowerShell 설치를 확인하고 다시 시도하세요.*

- **해결 방법**: 이 문제를 해결하는 유일한 방법은 Microsoft 다운로드 센터에서 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595)사용할 수 있는 Windows PowerShell 3.0을 설치하는 것입니다.
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>WinRM 기본 인증을 사용하지 않도록 설정한 경우 최신 인증 실패
<a name="BKMKWinRMBasicAuth"> </a>

최신 버전의 비즈니스용 Skype Online 커넥터 모듈은 최신 인증을 사용하지만 기본 WinRM(Windows 원격 관리) 클라이언트는 기본 인증을 허용하도록 구성해야 합니다.  최신 인증은 일반적으로 *Authorization: Bearer* 헤더에 전달되는 전달자 토큰을 사용합니다. 비즈니스용 Skype PowerShell이 빌드된 Windows PowerShell은 이 헤더를 조작할 수 없습니다.  대신 비즈니스용 Skype PowerShell은 *권한 부여: 기본* 헤더를 사용하여 전달자 토큰을 전달합니다.

기본 인증을 위해 WinRM을 사용하도록 설정하는 방법에 대한 지침은 [Windows PowerShell 다운로드 및 설치](./download-and-install-windows-powershell-5-1.md) 를 참조하세요.

## <a name="failed-to-connect-to-live-id-server"></a>라이브 ID 서버에 연결하지 못했습니다.
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> 비즈니스용 Skype 온라인 커넥터의 경우 라이브 ID 인증이 더 이상 사용되지 않습니다. Teams PowerShell 모듈을 사용하여 온라인 테넌트 관리 하이브리드 환경을 관리할 때 최신 누적 업데이트로 업그레이드하거나 oAuth 인증을 사용합니다.

일반적으로 다음 오류 메시지와 함께 연결 시도가 실패할 수 있는 세 가지 이유가 있습니다.

  - **오류**: *Get-CsWebTicket: 라이브 ID 서버를 연결하지 못했습니다. 프록시가 활성화되어 있는지 또는 컴퓨터에 라이브 ID 서버에 대한 네트워크 연결이 있는지 확인합니다.*

- **해결 방법**: 이 오류는 종종 Microsoft Online Services 로그인 도우미가 실행되고 있지 않음을 의미합니다. PowerShell 프롬프트에서 다음 명령을 실행하여 이 서비스의 상태를 확인할 수 있습니다. 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    서비스가 실행되고 있지 않으면 다음 명령을 사용하여 서비스를 시작합니다.
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    서비스가 실행 중인 경우 컴퓨터와 Microsoft Live ID 인증 서버 간의 네트워크 연결에 문제가 발생할 수 있습니다. 이를 확인하려면 Internet Explorer를 열고 .로 이동합니다 [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) 여기에서 Microsoft 365 또는 Office 365에 로그온해 보세요. 이 오류가 발생하면 네트워크 연결 문제가 발생할 수 있습니다.
  
    일반적으로 Microsoft Live ID 인증 서버에 대한 연결 URI가 잘못된 값으로 구성되었을 수 있습니다. Sign-In Assistant가 실행 중이고 네트워크 연결 문제가 발생하지 않는다고 이미 결정한 경우 이 문제가 발생할 수 있습니다. 이 경우 Microsoft 지원에 문의하세요.
  
## <a name="logon-failed-for-the-user"></a>사용자에 대한 로그온 실패
<a name="BKMKLogonFailed"> </a>

비즈니스용 Skype Online에 원격으로 연결하려는 경우 유효한 비즈니스용 Skype Online 사용자 계정의 사용자 이름과 암호를 제공해야 합니다. 그렇지 않으면 이 메시지와 유사한 오류 메시지와 함께 로그온이 실패합니다.

- **오류**: *Get-CsWebTicket: 'kenmyer@litwareinc.com' 사용자에 대해 로그온하지 못했습니다. 새 PSCredential 개체를 만들어 올바른 사용자 이름과 암호를 사용했는지 확인합니다.*

- **해결 방법**: 유효한 사용자 계정을 사용하고 있고 올바른 암호를 가지고 있다고 생각되면 다시 로그온해 보세요. 실패하면 동일한 자격 증명을 사용하고 .에서 [https://login.microsoftonline.com/](https://login.microsoftonline.com/)로그인을 시도합니다. 로그인할 수 없는 경우 Microsoft 지원에 문의하세요. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>사용자에게 이 테넌트 관리 권한이 없습니다.
<a name="BKMKUserPermission"> </a>

테넌트 관리자 그룹의 구성원이 아니면 비즈니스용Skype Online에 원격 PowerShell 연결을 설정할 수 없습니다. 그렇지 않으면 연결 시도가 실패하고 다음 오류 메시지가 표시됩니다.

- **오류**: *New-PSSession: [admin.vdomain.com] 원격 서버에서 데이터를 처리하지 admin.vdomain.com 오류 메시지와 함께 실패했습니다. 'user@foo.com' 사용자에게는 이 테넌트 관리 권한이 없습니다. 적절한 RBAC 역할에 사용자를 할당하여 권한을 부여할 수 있습니다. 자세한 내용은 [원격 문제 해결](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )을 참조하세요.*

- **해결 방법**: 테넌트 관리자 그룹의 구성원이거나 구성원이어야 한다고 생각되는 경우 Microsoft 지원에 문의해야 합니다.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 테넌트에 연결하는 기능이 비활성화되었습니다.
<a name="BKMKAbilityConnect"> </a>

PowerShell을 사용하여 비즈니스용 Skype Online을 관리하려면 테넌트 PowerShell 정책의 EnableRemotePowerShellAccess 속성을 다음으로  `True`설정해야 합니다. 그렇지 않으면 연결이 실패하고 다음 오류 메시지가 표시됩니다.

- **오류**: *New-PSSession: [admin.vdomain.com] 원격 서버에서 데이터를 처리하지 admin.vdomain.com 다음 오류 메시지와 함께 실패했습니다. 원격 PowerShell 세션을 사용하여 이 테넌트에 연결하는 기능이 비활성화되었습니다. 이 테넌트에 대한 테넌트 PowerShell 정책을 확인하려면 Lync 도움말에 문의하세요. 자세한 내용은 [원격 문제 해결](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )을 참조하세요.*

- **해결 방법**: 이 오류 메시지가 표시되면 Microsoft 지원에 문의하고 원격 PowerShell 액세스를 사용하도록 설정해야 합니다.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>비즈니스용 Skype Online에서 이 사용자의 최대 동시 셸 수를 초과했습니다.
<a name="BKMKMaxNumberShellsUser"> </a>

각 관리자는 비즈니스용 Skype Online에 대해 최대 3개의 동시 원격 연결을 허용합니다. 3개의 원격 PowerShell 연결이 실행되고 있는 경우 다음 오류 메시지와 함께 네 번째 동시 연결을 시도하면 실패합니다. 

- **오류**: *New-PSSession: [admin.vdomain.com] 원격 서버에 연결하지 admin.vdomain.com 다음 오류 메시지와 함께 실패했습니다. WS-Management 서비스에서 요청을 처리할 수 없습니다. 이 사용자의 최대 동시 셸 수를 초과했습니다. 기존 셸을 닫거나 이 사용자의 할당량을 높입니다. 자세한 내용은 [원격 문제 해결](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )을 참조하세요.*

- **해결 방법**: 이 문제를 해결하는 유일한 방법은 이전 연결 중 하나 이상을 닫는 것입니다. 비즈니스용 Skype Online 세션을 마치면 **Remove-PSSession** cmdlet을 사용하여 세션을 종료하는 것이 좋습니다. 이렇게 하면 이 문제를 방지하는 데 도움이 됩니다.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>비즈니스용 Skype Online에서 이 테넌트의 최대 동시 셸 수를 초과했습니다.
<a name="BKMKMaxNumberShellsTenant"> </a>

각 관리자는 비즈니스용 Skype Online 테넌트에 대해 최대 3개의 동시 연결을 사용할 수 있지만 단일 테넌트에는 20개 이상의 동시 연결이 허용되지 않습니다. 예를 들어 6명의 관리자가 각각 3개의 열린 세션을 가질 수 있습니다. 네 번째 관리자가 두 개 이상의 연결을 시도하면(총 21개의 동시 연결이 발생함) 다음 오류 메시지와 함께 이 시도가 실패합니다.
  
- **오류**: *New-PSSession: [admin.vdomain.com] 원격 서버에 연결하지 admin.vdomain.com 다음 오류 메시지와 함께 실패했습니다. WS-Management 서비스에서 요청을 처리할 수 없습니다. 이 테넌트의 최대 동시 셸 수를 초과했습니다. 기존 셸을 닫거나 이 테넌트에 대한 할당량을 높입니다. 자세한 내용은 [원격 문제 해결](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )을 참조하세요.*

- **해결 방법**: 이 문제를 해결하는 유일한 방법은 이전 연결 중 하나 이상을 닫는 것입니다. 비즈니스용 Skype Online 세션을 마치면 **Remove-PSSession** cmdlet을 사용하여 해당 세션을 종료하는 것이 좋습니다. 이렇게 하면 이 문제를 방지하는 데 도움이 됩니다.  
 
## <a name="related-topics"></a>관련 항목
[Windows PowerShell을 사용하여 비즈니스용 Skype 온라인 관리를 위한 컴퓨터 설정](set-up-your-computer-for-windows-powershell.md)

  
