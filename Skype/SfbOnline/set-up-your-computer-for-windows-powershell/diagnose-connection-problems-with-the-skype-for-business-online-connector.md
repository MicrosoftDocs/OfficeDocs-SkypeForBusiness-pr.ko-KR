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
description: 가져오기-모듈, 동시 셸, Live ID 및 사용 권한 오류를 포함 하 여 비즈니스용 Skype Online에 연결 하는 데 필요한 원격 PowerShell 세션을 만드는 문제를 해결 합니다.
ms.openlocfilehash: be3500ea5573dab6daa3d8ff72a8de4f60566ee2
ms.sourcegitcommit: a4fd238de09366d6ed33d72c908faff812da11a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42637135"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>비즈니스용 Skype Online 커넥터의 연결 문제 진단

이 항목에서는 비즈니스용 Skype Online에 연결 하는 원격 Microsoft PowerShell 세션을 만들려고 할 때 발생할 수 있는 문제를 진단 하 고 해결 하는 데 도움이 되는 정보를 제공 합니다. 다음 섹션을 참조 하세요.
  
- [Windows PowerShell 실행 정책으로 인해 발생 하는 가져오기 모듈 오류](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [잘못 된 버전의 Windows PowerShell로 인해 발생 하는 가져오기 모듈 오류](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Live ID 서버에 연결 하지 못했습니다.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [라이브 ID 모듈을 로드 하지 못했습니다.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [사용자에 대 한 로그온 실패](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [사용자에 게이 테 넌 트를 관리할 수 있는 권한이 없습니다.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [비즈니스용 Skype Online에서 테 넌 트 연결 기능을 사용 하지 않도록 설정 했습니다.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [비즈니스용 Skype Online에서이 사용자에 대 한 최대 동시 셸 수가 초과 되었습니다.](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [비즈니스용 Skype Online에서이 테 넌 트에 대 한 최대 동시 셸 수가 초과 되었습니다.](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Windows PowerShell 실행 정책으로 인해 발생 하는 가져오기 모듈 오류
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 실행 정책은 PowerShell 콘솔로 로드할 수 있는 구성 파일 및 해당 콘솔에서 실행할 수 있는 스크립트를 결정 하는 데 도움이 됩니다. 적어도 비즈니스용 Skype Online Connector 모듈은 실행 정책이 RemoteSigned로 설정 되지 않은 경우에만 가져올 수 있습니다. 그렇지 않은 경우 모듈을 가져오려고 할 때 다음과 같은 오류 메시지가 표시 됩니다.
  
- **오류**: <em>가져오기-모듈: 파일 C:\\프로그램 파일\\공통 파일\\시스템에서 스크립트를\\실행\\하\\는 기능이 비활성화 되어 있으므로 Microsoft Lync Server 2013 모듈 LyncOnlineConnector LyncOnlineConnectorStartup을 로드할 수 없습니다. 자세한 내용은의 about_Execution_Policies를 참조 하세요 https://go.microsoft.com/fwlink/?LinkID=135170.</em>

- **해결**방법:이 문제를 해결 하려면 관리자로 PowerShell을 시작 하 고 다음 명령을 실행 합니다.
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    실행 정책에 대 한 자세한 내용은 [실행 정책 정보](https://go.microsoft.com/fwlink/?LinkID=135170)를 참조 하세요.
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>잘못 된 버전의 Windows PowerShell로 인해 발생 하는 가져오기 모듈 오류
<a name="BKMKIncorrectVersion"> </a>

비즈니스용 Skype Online Connector 모듈은 Windows PowerShell 3.0 에서만 실행할 수 있습니다. 이전 버전의 PowerShell에서 모듈을 가져오려고 하면 다음과 같은 오류 메시지와 함께 가져오기 프로세스가 실패 합니다.
  
  - **오류**: *가져오기-모듈: 로드 된 PowerShell의 버전은 ' 2.0 '입니다. 모듈 d\\: 프로그램 파일\\일반적인 파일\\Microsoft Lync Server 2013\\module\\LyncOnlineConnector\\LyncOnlineConnector를 실행 하려면 최소 PowerShell 버전 ' 3.0 '이 필요 합니다. PowerShell 설치를 확인 한 후 다시 시도 하세요.*

- **해결**방법:이 문제를 해결 하는 유일한 방법은 Microsoft 다운로드 센터에서 제공 하는 Windows PowerShell 3.0을 설치 하는 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595)것입니다.
  
## <a name="failed-to-connect-to-live-id-server"></a>Live ID 서버에 연결 하지 못했습니다.
<a name="BKMKFailedConnect"> </a>

일반적으로 다음 오류 메시지와 함께 연결 시도가 실패할 수 있는 세 가지 이유가 있습니다.

  - **오류**: *가져오기-cswebticket: live id 서버에 연결 하지 못했습니다. 프록시를 사용 하도록 설정 하거나 컴퓨터에 live id 서버에 대 한 네트워크 연결이 있는지 확인 합니다.*

- **해결**:이 오류는 종종 Microsoft Online Services 로그인 도우미가 실행 되 고 있지 않음을 의미 합니다. PowerShell 프롬프트에서 다음 명령을 실행 하 여이 서비스의 상태를 확인할 수 있습니다. 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    서비스가 실행 되 고 있지 않은 경우에는 다음 명령을 사용 하 여 서비스를 시작 합니다.
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    서비스가 실행 되 고 있는 경우 컴퓨터와 Microsoft Live ID 인증 서버 간의 네트워크 연결에 문제가 발생할 수 있습니다. 이를 확인 하려면 Internet Explorer를 열고으로 [ https://login.microsoftonline.com/이동 합니다.](https://login.microsoftonline.com/.) 여기에서 Office 365에 로그온 해 보세요. 이 문제가 발생 하는 경우 네트워크 연결 문제가 발생 했을 수 있습니다.
  
    덜 일반적으로 Microsoft Live ID 인증 서버의 연결 URI가 잘못 된 값으로 구성 되었을 수 있습니다. 이미 로그인 도우미가 실행 중이 고 네트워크 연결 문제가 발생 하지 않은 것으로 확인 된 경우이 문제가 발생할 수 있습니다. 이 경우 Office 365 지원에 문의 하세요.
  
## <a name="failed-to-load-live-id-module"></a>라이브 ID 모듈을 로드 하지 못했습니다.
<a name="BKMKFailedLoad"> </a>

PowerShell을 사용 하 여 비즈니스용 Skype Online을 관리 하기 위한 필수 구성 요소 중 하나는 Microsoft Online Services 로그인 도우미를 설치 하는 것입니다. 로그인 도우미가 설치 되어 있지 않은 경우 비즈니스용 Skype Online을 사용 하 여 원격 세션을 설정 하려고 하면 다음과 같은 오류 메시지가 나타납니다.

- **오류**: *Get-Cswebticket: Live Id 모듈을 로드할 수 없습니다. 올바른 버전의 Live Id 로그인 도우미가 설치 되어 있는지 확인 합니다.*

- **해결**방법: Microsoft Online Services 로그인 도우미는 [IT 전문가를 위한 Microsoft Online services 로그인 도우미](https://www.microsoft.com/download/details.aspx?id=28177) 의 microsoft 다운로드 센터에서 사용할 수 있습니다. rtw

## <a name="logon-failed-for-the-user"></a>사용자에 대 한 로그온 실패
<a name="BKMKLogonFailed"> </a>

비즈니스용 Skype Online으로 원격 연결을 시도 하는 경우 유효한 비즈니스용 Skype Online 사용자 계정에 대 한 사용자 이름 및 암호를 제공 해야 합니다. 그렇지 않으면 다음과 유사한 오류 메시지와 함께 logon에 실패 합니다.

- **오류**: *get-help webticket: 사용자 ' kenmyer@litwareinc.com '에 대 한 로그온에 실패 했습니다. 올바른 사용자 이름 및 암호를 사용 하 고 있는지 확인 하 여 새 PSCredential 개체를 만들어 주십시오.*

- **해결**방법: 유효한 사용자 계정을 사용 하 고 있고 올바른 암호를가지고 있다고 생각 되는 경우 다시 로그온 해 보세요. 이 문제가 발생 하면 같은 자격 증명을 사용 하 여에 [https://login.microsoftonline.com/](https://login.microsoftonline.com/)로그온 합니다. 로그인 할 수 없는 경우에는 Office 365 지원에 문의 하세요. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>사용자에 게이 테 넌 트를 관리할 수 있는 권한이 없습니다.
<a name="BKMKUserPermission"> </a>

테 넌 트 관리자 그룹의 구성원이 아닌 경우에는 원격 PowerShell 연결을 비즈니스용 Skype Online으로 설정할 수 없습니다. 그렇지 않으면 연결 시도가 실패 하 고 다음 오류 메시지가 표시 됩니다.

- **오류**: *다음 오류 메시지 때문에 원격 서버 admin.vdomain.com에서 데이터를 처리 하는 동안 새 PSSession: [admin.vdomain.com]이 (가) 실패 했습니다. 사용자 ' user@foo.com '에 게이 테 넌 트를 관리할 수 있는 권한이 없습니다. 사용자를 적절 한 RBAC 역할에 할당 하 여 사용 권한을 부여할 수 있습니다. 자세한 내용은 [원격 문제 해결](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)을 참조 하세요.*

- **해결**방법: 테 넌 트 관리자 그룹의 구성원 이거나이를 대상으로 생각 하는 경우 Office 365 지원에 문의 해야 합니다.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 테 넌 트 연결 기능을 사용 하지 않도록 설정 했습니다.
<a name="BKMKAbilityConnect"> </a>

PowerShell을 사용 하 여 비즈니스용 Skype Online을 관리 하려면 테 넌 트 PowerShell 정책의 EnableRemotePowerShellAccess 속성을 (으) `True`로 설정 해야 합니다. 그렇지 않으면 연결에 실패 하 고 다음 오류 메시지가 표시 됩니다.

- **오류**: *다음 오류 메시지 때문에 원격 서버 admin.vdomain.com에서 데이터를 처리 하는 동안 새 PSSession: [admin.vdomain.com]에서 실패 했습니다. 원격 PowerShell 세션을 사용 하 여이 테 넌 트에 연결 하는 기능이 비활성화 되었습니다. Lync 도움말에 문의 하 여이 테 넌 트의 테 넌 트 Powershell 정책을 확인 하세요. 자세한 내용은 [원격 문제 해결](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)을 참조 하세요.*

- **해결**방법:이 오류 메시지가 표시 되는 경우 Office 365 지원에 문의 하 여 원격 PowerShell 액세스를 사용 하도록 설정 해야 합니다.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>비즈니스용 Skype Online에서이 사용자에 대 한 최대 동시 셸 수가 초과 되었습니다.
<a name="BKMKMaxNumberShellsUser"> </a>

각 관리자는 비즈니스용 Skype Online에 대해 최대 세 개의 동시 원격 연결을 허용 합니다. 세 개의 원격 PowerShell 연결이 있고 실행 중인 경우에는 네 번째 동시 연결 시도에 실패 하 고 다음 오류 메시지가 표시 됩니다.

- **오류**: *다음 오류 메시지 때문에 원격 서버 admin.vdomain.com에 대 한 새 PSSession: [Admin.vdomain.com]에 연결 하지 못했습니다. ws-management 서비스가 요청을 처리할 수 없습니다. 이 사용자에 대 한 최대 동시 셸 수가 초과 되었습니다. 기존 셸을 닫거나이 사용자의 할당량을 높이십시오. 자세한 내용은 [원격 문제 해결]을 참조 하세요 (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **해결**방법:이 문제를 해결 하는 유일한 방법은 이전 연결을 하나 이상 닫는 것입니다. 비즈니스용 Skype Online 세션을 마치면 **제거-PSSession** cmdlet을 사용 하 여 세션을 종료 하는 것이 좋습니다. 이는이 문제를 방지 하는 데 도움이 됩니다.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>비즈니스용 Skype Online에서이 테 넌 트에 대 한 최대 동시 셸 수가 초과 되었습니다.
<a name="BKMKMaxNumberShellsTenant"> </a>

각 관리자는 비즈니스용 Skype Online 테 넌 트에 세 개 이상의 동시 연결이 허용 되지만 단일 테 넌 트는 20 개 이상의 동시 연결을 허용 하지 않습니다. 예를 들어 6 대의 관리자는 각각 세 개의 열린 세션을 가질 수 있습니다. 일곱 번째 관리자가 두 개 이상의 연결을 열려고 하는 경우 (총 21 개의 동시 연결), 다음 오류 메시지와 함께이 시도가 실패 합니다.
  
- **오류**: *다음 오류 메시지 때문에 원격 서버 admin.vdomain.com에 대 한 새 PSSession: [Admin.vdomain.com]에 연결 하지 못했습니다. ws-management 서비스가 요청을 처리할 수 없습니다. 이 테 넌 트에 대 한 최대 동시 셸 수가 초과 되었습니다. 기존 셸을 닫거나이 테 넌 트의 할당량을 높이십시오. 자세한 내용은 [원격 문제 해결]을 참조 하세요 (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **해결**방법:이 문제를 해결 하는 유일한 방법은 이전 연결을 하나 이상 닫는 것입니다. 비즈니스용 Skype Online 세션을 마치면 **제거-PSSession** cmdlet을 사용 하 여 해당 세션을 종료 하는 것이 좋습니다. 이는이 문제를 방지 하는 데 도움이 됩니다.  
 
## <a name="related-topics"></a>관련 항목
[Windows PowerShell을 사용 하 여 비즈니스용 skype online 관리를 위한 컴퓨터 설정](set-up-your-computer-for-windows-powershell.md)

  
 
