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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 가져오기 모듈, 비즈니스용 Skype 셸, 라이브 ID 및 사용 권한 오류를 포함하여 온라인에 연결하기 위해 원격 PowerShell 세션을 만드는 문제를 해결합니다.
ms.openlocfilehash: f4bcb9c758d1660cafd7a6bd3f57c95d6bf3b546
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238909"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>비즈니스용 Skype Online 커넥터의 연결 문제 진단

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

이 항목에서는 온라인에 연결하는 원격 Microsoft PowerShell 세션을 만들 때 발생할 수 있는 문제를 진단하고 해결하는 비즈니스용 Skype 제공합니다. 다음 섹션을 참조하세요.
  
- [실행 정책에 Windows PowerShell 가져오기 모듈 오류](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [잘못된 버전으로 인해 발생하는 가져오기 모듈 Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Live ID 서버에 연결하지 못했습니다.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Live ID 모듈을 로드하지 못했습니다.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [사용자에게 로그온이 실패했습니다.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [사용자에게 이 테넌트 관리 권한이 없습니다.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [온라인에서 테넌트에 연결하는 비즈니스용 Skype 사용되지 않습니다.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [온라인에서 이 사용자에 대한 동시 셸의 비즈니스용 Skype 수를 초과했습니다.](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [온라인에서 이 테넌트에 대한 동시 셸의 비즈니스용 Skype 수를 초과했습니다.](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Import-Module 실행 정책으로 Windows PowerShell 오류 발생
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 실행 정책은 PowerShell 콘솔에 로드할 수 있는 구성 파일 및 사용자가 해당 콘솔에서 실행할 수 있는 스크립트를 결정하는 데 도움이 됩니다. 실행 정책이 RemoteSigned로 비즈니스용 Skype 경우 최소 온라인 커넥터 모듈을 가져올 수 없습니다. 그렇지 않은 경우 모듈을 가져오는 경우 다음 오류 메시지가 표시됩니다.
  
- **오류**: 가져오기 모듈 : 파일 C: 프로그램 파일 일반 파일 <em> \\ Microsoft \\ \\ Lync Server 2013 \\ 모듈 \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1은 이 시스템에서 스크립트를 실행하지 않도록 설정되어 있기 때문에 로드할 수 없습니다. 자세한 내용은 에서 about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170 참조하세요.</em>

- **해결**: 이 문제를 해결하기 위해 PowerShell을 관리자 권한으로 시작한 다음 다음 명령을 실행합니다.
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    실행 정책에 대한 자세한 내용은 실행 정책 [정보를 참조합니다.](/powershell/module/microsoft.powershell.core/about/about_execution_policies)
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module 버전이 잘못되어 발생하는 오류 Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

온라인 비즈니스용 Skype 모듈은 3.0에서만 Windows PowerShell 수 있습니다. 이전 버전의 PowerShell에서 모듈을 가져오려고 하면 가져오기 프로세스가 이와 유사한 오류 메시지로 실패합니다.
  
  - **오류**: *Import-Module : 로드된 PowerShell의 버전은 '2.0'입니다. 'D: \\ Program Files Common Files Microsoft \\ \\ Lync Server 2013 \\ Modules \\ LyncOnlineConnectorLyncOnlineConnector.psd1' 모듈은 \\ '3.0'의 최소 PowerShell 버전을 실행해야 합니다. PowerShell의* 설치를 확인하고 다시 시도하세요.

- **해결** 방법 : 이 문제를 해결하는 유일한 방법은 의 Microsoft 다운로드 센터에서 Windows PowerShell 3.0을 설치하는 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) 것입니다.
  
## <a name="failed-to-connect-to-live-id-server"></a>Live ID 서버에 연결하지 못했습니다.
<a name="BKMKFailedConnect"> </a>

일반적으로 다음 오류 메시지로 연결 시도가 실패할 수 있는 세 가지 이유가 있습니다.

  - **오류**: *Get-CsWebTicket : 라이브 ID 서버를 연결하지 못했습니다. 프록시를 사용하도록 설정하거나 머신에* 라이브 ID 서버에 대한 네트워크 연결이 있는지 확인합니다.

- **해결:** 종종 이 오류는 로그인 Microsoft Online Services 실행되지 않는 경우를 의미합니다. PowerShell 프롬프트에서 다음 명령을 실행하여 이 서비스의 상태를 확인할 수 있습니다. 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    서비스가 실행되지 않는 경우 다음 명령을 사용하여 서비스를 시작합니다.
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    서비스가 실행 중인 경우 컴퓨터와 Microsoft Live ID 인증 서버 간의 네트워크 연결에 문제가 발생할 수 있습니다. 이 확인을 확인 Internet Explorer 을 열고 [ https://login.microsoftonline.com/ 로 이동합니다.](https://login.microsoftonline.com/.) 로그온하여 Microsoft 365 Office 365 시도합니다. 이 오류가 발생하면 네트워크 연결 문제가 발생하는 것일 수 있습니다.
  
    일반적으로 Microsoft Live ID 인증 서버의 연결 URI가 잘못된 값으로 구성된 것일 수 있습니다. 지원 도우미가 Sign-In 네트워크 연결 문제가 발생하지 않았다고 이미 판단한 경우 이 문제가 될 수 있습니다. 이 경우 Microsoft 지원에 문의합니다.
  
## <a name="failed-to-load-live-id-module"></a>Live ID 모듈을 로드하지 못했습니다.
<a name="BKMKFailedLoad"> </a>

PowerShell을 사용하여 온라인 비즈니스용 Skype 관리하기 위한 Microsoft Online Services 구성하는 것입니다. 로그인 도우미가 설치되어 있지 않은 경우 온라인에서 원격 세션을 설정하려고 할 때 다음 오류 메시지가 비즈니스용 Skype 있습니다.

- **오류**: *Get-CsWebTicket : Live Id 모듈을 로드할 수 없습니다. 올바른 버전의 Live Id 로그인* 도우미가 설치되어 있는지 확인합니다.

- **해결:** Microsoft Online Services 로그인 도우미는 IT 전문가 [RTW용](https://www.microsoft.com/download/details.aspx?id=28177) Microsoft Microsoft Online Services Sign-In 다운로드 센터에서 사용할 수 있습니다.

## <a name="logon-failed-for-the-user"></a>사용자에게 로그온이 실패했습니다.
<a name="BKMKLogonFailed"> </a>

온라인에 원격 연결을 시도하는 비즈니스용 Skype 유효한 온라인 사용자 계정의 사용자 이름과 비즈니스용 Skype 제공해야 합니다. 그렇지 않은 경우 로그온은 이와 유사한 오류 메시지와 함께 실패합니다.

- **오류**: *Get-CsWebTicket : Logon이 'kenmyer@litwareinc.com'에 실패했습니다. 올바른 사용자* 이름과 암호를 사용한지 확인하여 새 PSCredential 개체를 만들어 주세요.

- **해결**: 유효한 사용자 계정을 사용하고 있으며 올바른 암호가 있는 것으로 생각되는 경우 다시 로그온해 하세요. 이 오류가 발생하면 동일한 자격 증명을 사용하여 에서 로그온해 를 [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 시도합니다. 로그온할 수 없는 경우 Microsoft 지원에 문의합니다. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>사용자에게 이 테넌트 관리 권한이 없습니다.
<a name="BKMKUserPermission"> </a>

테넌트 관리자 그룹의 구성원이면 비즈니스용 온라인용Skype에 원격 PowerShell 연결을 만들 수 없습니다. 그렇지 않은 경우 연결 시도가 실패하고 다음 오류 메시지가 표시됩니다.

- **오류**: New-PSSession : [admin.vdomain.com] 원격 서버 admin.vdomain.com 데이터 처리에 *실패했습니다. 사용자 'user@foo.com'는 이 테넌트 관리 권한이 없습니다. 적절한 RBAC 역할에 사용자를 할당하여 권한을 부여할 수 있습니다. 자세한 내용은 원격 문제 [해결 을 참조하세요.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **해결:** 테넌트 관리자 그룹의 구성원인 경우 Microsoft 지원에 문의해야 합니다.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>온라인에서 테넌트에 연결하는 비즈니스용 Skype 사용되지 않습니다.
<a name="BKMKAbilityConnect"> </a>

PowerShell을 사용하여 온라인 비즈니스용 Skype 관리하려면 테넌트 PowerShell 정책의 EnableRemotePowerShellAccesss 속성을 으로 설정해야 `True` 합니다. 그렇지 않은 경우 연결이 실패하고 다음 오류 메시지가 표시됩니다.

- **오류**: New-PSSession : [admin.vdomain.com] 원격 서버의 데이터 admin.vdomain.com 오류 메시지로 실패했습니다. 원격 PowerShell 세션을 사용하여 이 테넌트에 연결하는 기능을 사용하지 않도록 *설정했습니다. 이 테넌트의 테넌트 Powershell 정책을 확인하기 위해 Lync 도움말에 문의하시기 바랍니다. 자세한 내용은 원격 문제 [해결 을 참조하세요.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **해결:** 이 오류 메시지가 표시되면 Microsoft 지원에 문의하고 원격 PowerShell 액세스를 사용하도록 설정해야 합니다.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>온라인에서 이 사용자에 대한 동시 셸의 비즈니스용 Skype 수를 초과했습니다.
<a name="BKMKMaxNumberShellsUser"> </a>

각 관리자는 온라인에서 최대 3개의 동시 원격 비즈니스용 Skype 허용됩니다. 세 개의 원격 PowerShell 연결이 실행되는 경우 다음 오류 메시지와 함께 네 번째 동시 연결을 시도하는 시도가 실패합니다.

- **오류**: New-PSSession : [admin.vdomain.com] 다음 오류 메시지로 admin.vdomain.com 서버에 연결하지 못했습니다. WS-Management 서비스에서 요청을 처리하지 *못했습니다. 이 사용자에 대한 동시 셸의 최대 수가 초과됩니다. 기존 셸을 닫거나 이 사용자에 대한 할당량도 올렸다. 자세한 내용은 [원격 문제 해결]을 참조하세요. https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*

- **해결** 방법 : 이 문제를 해결하는 유일한 방법은 이전 연결을 하나 이상 닫는 것입니다. 온라인 세션을 비즈니스용 Skype 완료하면 **Remove-PSSession** cmdlet을 사용하여 세션을 종료하는 것이 좋습니다. 이렇게 하면 이 문제를 방지하는 데 도움이 될 수 있습니다.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>온라인에서 이 테넌트에 대한 동시 셸의 비즈니스용 Skype 수를 초과했습니다.
<a name="BKMKMaxNumberShellsTenant"> </a>

각 관리자는 온라인 테넌트에 최대 3개의 동시 연결을 허용할 수 비즈니스용 Skype 테넌트 하나에 20개 이상의 동시 연결을 허용하지 않습니다. 예를 들어 관리자 6명은 각각 3개의 열려 있는 세션을 사용할 수 있습니다. 7번째 관리자는 두 개 이상의 연결을 열고(총 21개의 동시 연결로 인해) 실패합니다. 다음 오류 메시지와 함께 이 시도는 실패합니다.
  
- **오류**: New-PSSession : [admin.vdomain.com] 다음 오류 메시지로 admin.vdomain.com 서버에 연결하지 못했습니다. WS-Management 서비스에서 요청을 처리하지 *못했습니다. 이 테넌트에 대한 동시 셸의 최대 수가 초과됩니다. 기존 셸을 닫거나 이 테넌트에 대한 할당량은 올 입니다. 자세한 내용은 [원격 문제 해결]을 참조하세요. https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*

- **해결** 방법 : 이 문제를 해결하는 유일한 방법은 이전 연결을 하나 이상 닫는 것입니다. 온라인 세션을 비즈니스용 Skype 경우 **Remove-PSSession** cmdlet을 사용하여 해당 세션을 종료하는 것이 좋습니다. 이렇게 하면 이 문제를 방지하는 데 도움이 될 수 있습니다.  
 
## <a name="related-topics"></a>관련 항목
[비즈니스용 Skype 온라인 관리용 컴퓨터를 Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
