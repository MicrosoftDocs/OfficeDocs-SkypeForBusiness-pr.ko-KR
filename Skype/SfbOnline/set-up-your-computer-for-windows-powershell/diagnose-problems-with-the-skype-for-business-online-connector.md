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
ms.openlocfilehash: d220fbbf9df22964833aa42bcd29c5ecaaa6eaa5
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856067"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="3b493-103">비즈니스용 Skype Online 커넥터의 연결 문제 진단</span><span class="sxs-lookup"><span data-stu-id="3b493-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="3b493-104">이 항목에서는 온라인에 연결하는 원격 Microsoft PowerShell 세션을 만들 때 발생할 수 있는 문제를 진단하고 해결하는 비즈니스용 Skype 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="3b493-105">다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b493-105">See the following sections:</span></span>
  
- [<span data-ttu-id="3b493-106">실행 정책에 Windows PowerShell 가져오기 모듈 오류</span><span class="sxs-lookup"><span data-stu-id="3b493-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="3b493-107">잘못된 버전으로 인해 발생하는 가져오기 모듈 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b493-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="3b493-108">WinRM Basic 인증을 사용하지 않도록 설정한 경우 최신 인증이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-108">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [<span data-ttu-id="3b493-109">Live ID 서버에 연결하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-109">Failed to connect to Live ID Server</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="3b493-110">Live ID 모듈을 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-110">Failed to load Live ID module</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="3b493-111">사용자에 대한 로그인 실패</span><span class="sxs-lookup"><span data-stu-id="3b493-111">Sign in failed for the user</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="3b493-112">사용자에게 이 테넌트 관리 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-112">The user does not have permission to manage this tenant</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="3b493-113">온라인에서 테넌트에 연결하는 비즈니스용 Skype 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-113">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="3b493-114">온라인에서 이 사용자에 대한 동시 셸의 비즈니스용 Skype 수를 초과했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-114">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="3b493-115">온라인에서 이 테넌트에 대한 동시 셸의 비즈니스용 Skype 수를 초과했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-115">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> <span data-ttu-id="3b493-116">기본적으로 PowerShell 세션은 60분 후에 시간제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-116">By default, PowerShell sessions time out after sixty minutes.</span></span> <span data-ttu-id="3b493-117">다시 연결하기 위해 세션을 닫고 새 PowerShell 세션을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-117">To reconnect, you have to close the session and launch a new PowerShell session.</span></span> <span data-ttu-id="3b493-118">새 버전의 비즈니스용 Skype 온라인, Windows PowerShell [모듈(2046.123 - 게시된 10/2/2/2019)은](https://www.microsoft.com/download/details.aspx?id=39366)60분의 시간 시간 문제를 완화하는 **Enable-CsOnlineSessionForReconnection이라는** 새 cmdlet을 포함하는 최근에 출시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-118">A new version of [Skype for Business Online, Windows PowerShell Module (2046.123 - Published 10/2/2019)](https://www.microsoft.com/download/details.aspx?id=39366), has been launched recently which includes a new cmdlet called **Enable-CsOnlineSessionForReconnection** that mitigates the 60 minutes time-out issue.</span></span>
> <span data-ttu-id="3b493-119">PowerShell 세션은 다시 연결하고 인증하므로 다시 연결하기 위해 새 인스턴스를 시작하지 않고도 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-119">The PowerShell session reconnects and authenticates, allowing it to be re-used without having to launch a new instance to reconnect.</span></span>



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="3b493-120">Import-Module 실행 정책으로 Windows PowerShell 오류 발생</span><span class="sxs-lookup"><span data-stu-id="3b493-120">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="3b493-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="3b493-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span></span>

<span data-ttu-id="3b493-122">PowerShell 실행 정책은 PowerShell 콘솔에 로드할 수 있는 구성 파일 및 사용자가 해당 콘솔에서 실행할 수 있는 스크립트를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-122">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="3b493-123">실행 정책이 RemoteSigned로 비즈니스용 Skype 경우 최소 온라인 커넥터 모듈을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-123">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="3b493-124">그렇지 않은 경우 모듈을 가져오는 경우 다음 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-124">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="3b493-125">**오류**: 가져오기 모듈 : 파일 C: 프로그램 파일 일반 파일 <em> \\ Microsoft \\ \\ Lync Server 2013 \\ 모듈 \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1은 이 시스템에서 스크립트를 실행하지 않도록 설정되어 있기 때문에 로드할 수 없습니다. 자세한 내용은 에서 about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170 참조하세요.</em></span><span class="sxs-lookup"><span data-stu-id="3b493-125">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="3b493-126">**해결** 이 문제를 해결하기 위해 관리자 권한으로 PowerShell을 시작한 다음 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-126">**Resolution** To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="3b493-127">실행 정책에 대한 자세한 내용은 실행 정책 [정보를 참조합니다.](/powershell/module/microsoft.powershell.core/about/about_execution_policies)</span><span class="sxs-lookup"><span data-stu-id="3b493-127">For details about execution policy, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="3b493-128">Import-Module 버전이 잘못되어 발생하는 오류 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b493-128">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="3b493-129"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="3b493-129"><a name="BKMKIncorrectVersion"> </a></span></span>

<span data-ttu-id="3b493-130">온라인 비즈니스용 Skype 모듈은 3.0에서만 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-130">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="3b493-131">이전 버전의 PowerShell에서 모듈을 가져오려고 하면 이 메시지와 유사한 오류 메시지로 가져오기 프로세스가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-131">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this message:</span></span>
  
  - <span data-ttu-id="3b493-132">**오류**: *Import-Module : 로드된 PowerShell의 버전은 '2.0'입니다. 'D: \\ Program Files Common Files Microsoft \\ \\ Lync Server 2013 \\ Modules \\ LyncOnlineConnectorLyncOnlineConnector.psd1' 모듈은 \\ '3.0'의 최소 PowerShell 버전을 실행해야 합니다. PowerShell의* 설치를 확인하고 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="3b493-132">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="3b493-133">**해결** 방법 : 이 문제를 해결하는 유일한 방법은 의 Microsoft 다운로드 센터에서 Windows PowerShell 3.0을 설치하는 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-133">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).</span></span>
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a><span data-ttu-id="3b493-134">WinRM Basic 인증을 사용하지 않도록 설정한 경우 최신 인증이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-134">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>
<span data-ttu-id="3b493-135"><a name="BKMKWinRMBasicAuth"> </a></span><span class="sxs-lookup"><span data-stu-id="3b493-135"><a name="BKMKWinRMBasicAuth"> </a></span></span>

<span data-ttu-id="3b493-136">최신 버전의 비즈니스용 Skype 온라인 커넥터 모듈은 최신 인증을 사용하지만 기본 인증을 허용하도록 기본 Windows WinRM(원격 관리) 클라이언트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-136">The latest version of the Skype for Business Online Connector module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span>  <span data-ttu-id="3b493-137">최신 인증은 일반적으로 권한 *부여: Bearer* 헤더에 전달되는 전달자 토큰을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-137">Modern authentication uses bearer tokens, which are usually passed in the *Authorization: Bearer* header.</span></span> <span data-ttu-id="3b493-138">Windows PowerShell PowerShell이 비즈니스용 Skype 경우 이 헤더를 조작할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="3b493-138">Windows PowerShell, upon which Skype for Business PowerShell is built, does not allow for manipulation of this header.</span></span>  <span data-ttu-id="3b493-139">대신 비즈니스용 Skype PowerShell에서 권한 *부여:* 기본 헤더를 사용하여 전달자 토큰을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-139">Instead, Skype for Business PowerShell uses the *Authorization: Basic* header to pass the bearer token.</span></span>

<span data-ttu-id="3b493-140">기본 [인증을 위해 WinRM을](./download-and-install-windows-powershell-5-1.md) Windows PowerShell 방법에 대한 지침은 다운로드 및 설치를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b493-140">See [Download and install Windows PowerShell](./download-and-install-windows-powershell-5-1.md) for instructions on how to enable WinRM for Basic authentication.</span></span>

## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="3b493-141">Live ID 서버에 연결하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-141">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="3b493-142"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="3b493-142"><a name="BKMKFailedConnect"> </a></span></span>

> [!WARNING] 
> <span data-ttu-id="3b493-143">비즈니스용 온라인 커넥터에서 라이브 ID Skype 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-143">Live ID authentication has been deprecated for Skype For Business online Connector.</span></span> <span data-ttu-id="3b493-144">온라인 Teams 관리하기 위해 PowerShell 모듈을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-144">Use the Teams PowerShell Module to manage the online tenant.</span></span> <span data-ttu-id="3b493-145">하이브리드 환경을 관리할 때 최신 누적 업데이트로 업그레이드하거나 oAuth 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-145">When managing hybrid environments, upgrade to latest cumulative update or use oAuth authentication.</span></span>

<span data-ttu-id="3b493-146">일반적으로 다음 오류 메시지로 연결 시도가 실패할 수 있는 세 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-146">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="3b493-147">**오류**: *Get-CsWebTicket : 라이브 ID 서버를 연결하지 못했습니다. 프록시를 사용하도록 설정하거나 머신에* 라이브 ID 서버에 대한 네트워크 연결이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-147">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live ID servers.*</span></span>

- <span data-ttu-id="3b493-148">**해결:** 종종 이 오류는 로그인 Microsoft Online Services 실행되지 않는 경우를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-148">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="3b493-149">PowerShell 프롬프트에서 다음 명령을 실행하여 이 서비스의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-149">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="3b493-150">서비스가 실행되지 않는 경우 다음 명령을 사용하여 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-150">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="3b493-151">서비스가 실행 중인 경우 컴퓨터와 Microsoft Live ID 인증 서버 간의 네트워크 연결에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-151">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="3b493-152">이 확인을 확인 Internet Explorer 을 열고 [ https://login.microsoftonline.com/ 로 이동합니다.](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="3b493-152">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="3b493-153">로그온하여 Microsoft 365 Office 365 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-153">Try logging on to Microsoft 365 or Office 365 from there.</span></span> <span data-ttu-id="3b493-154">이 오류가 발생하면 네트워크 연결 문제가 발생하는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-154">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="3b493-155">일반적으로 Microsoft Live ID 인증 서버의 연결 URI가 잘못된 값으로 구성된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-155">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="3b493-156">지원 도우미가 Sign-In 네트워크 연결 문제가 발생하지 않았다고 이미 판단한 경우 이 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-156">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="3b493-157">이 경우 Microsoft 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-157">In this case, contact Microsoft Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="3b493-158">Live ID 모듈을 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-158">Failed to load Live ID module</span></span>
<span data-ttu-id="3b493-159"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="3b493-159"><a name="BKMKFailedLoad"> </a></span></span>

<span data-ttu-id="3b493-160">PowerShell을 사용하여 온라인 비즈니스용 Skype 관리하기 위한 Microsoft Online Services 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-160">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="3b493-161">로그인 도우미가 설치되어 있지 않은 경우 온라인에서 원격 세션을 설정하려고 할 때 다음 오류 메시지가 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-161">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="3b493-162">**오류**: *Get-CsWebTicket : Live ID 모듈을 로드할 수 없습니다. 올바른 버전의 Live Id 로그인* 도우미가 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-162">**Error**: *Get-CsWebTicket : Can't load Live ID module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="3b493-163">**해결:** Microsoft Online Services 로그인 도우미는 IT 전문가 [RTW용](https://www.microsoft.com/download/details.aspx?id=28177) Microsoft Microsoft Online Services Sign-In 다운로드 센터에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-163">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="3b493-164">사용자에게 로그온이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-164">Logon failed for the user</span></span>
<span data-ttu-id="3b493-165"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="3b493-165"><a name="BKMKLogonFailed"> </a></span></span>

<span data-ttu-id="3b493-166">온라인에 원격 연결을 시도하는 비즈니스용 Skype 유효한 온라인 사용자 계정의 사용자 이름과 비즈니스용 Skype 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-166">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="3b493-167">그렇지 않은 경우 로그온이 이 메시지와 유사한 오류 메시지와 함께 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-167">If you do not, logon will fail along with an error message similar to this message:</span></span>

- <span data-ttu-id="3b493-168">**오류**: *Get-CsWebTicket : Logon이 'kenmyer@litwareinc.com'에 실패했습니다. 올바른 사용자* 이름 및 암호를 사용한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-168">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="3b493-169">**해결**: 유효한 사용자 계정을 사용하고 있으며 올바른 암호가 있는 것으로 생각되는 경우 다시 로그온해 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b493-169">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="3b493-170">이 오류가 발생하면 동일한 자격 증명을 사용하여 에 로그인해 를 [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-170">If that fails, use the same credentials and try to sign in at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="3b493-171">로그인할 수 없는 경우 Microsoft 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-171">If you're unable to sign in there, contact Microsoft Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="3b493-172">사용자에게 이 테넌트 관리 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-172">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="3b493-173"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="3b493-173"><a name="BKMKUserPermission"> </a></span></span>

<span data-ttu-id="3b493-174">테넌트 관리자 그룹의 구성원이면 비즈니스용 온라인용Skype에 원격 PowerShell 연결을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-174">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="3b493-175">그렇지 않은 경우 연결 시도가 실패하고 다음 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-175">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="3b493-176">**오류**: New-PSSession : [admin.vdomain.com] 원격 서버 admin.vdomain.com 데이터 처리에 *실패했습니다. 사용자 'user@foo.com'는 이 테넌트 관리 권한이 없습니다. 적절한 RBAC 역할에 사용자를 할당하여 권한을 부여할 수 있습니다. 자세한 내용은 원격 문제 [해결 을 참조하세요.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*</span><span class="sxs-lookup"><span data-stu-id="3b493-176">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="3b493-177">**해결:** 테넌트 관리자 그룹의 구성원인 경우 Microsoft 지원에 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-177">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Microsoft Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="3b493-178">온라인에서 테넌트에 연결하는 비즈니스용 Skype 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-178">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="3b493-179"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="3b493-179"><a name="BKMKAbilityConnect"> </a></span></span>

<span data-ttu-id="3b493-180">PowerShell을 사용하여 온라인 비즈니스용 Skype 관리하려면 테넌트 PowerShell 정책의 EnableRemotePowerShellAccesss 속성을 으로 설정해야 `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-180">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="3b493-181">그렇지 않은 경우 연결이 실패하고 다음 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-181">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="3b493-182">**오류**: New-PSSession : [admin.vdomain.com] 원격 서버의 데이터 admin.vdomain.com 오류 메시지로 실패했습니다. 원격 PowerShell 세션을 사용하여 이 테넌트에 연결하는 기능을 사용하지 않도록 *설정했습니다. Lync 도움말에 문의하여 이 테넌트의 테넌트 Powershell 정책을 검사합니다. 자세한 내용은 원격 문제 [해결 을 참조하세요.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*</span><span class="sxs-lookup"><span data-stu-id="3b493-182">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="3b493-183">**해결:** 이 오류 메시지가 표시되면 Microsoft 지원에 문의하고 원격 PowerShell 액세스를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-183">**Resolution**: If you see this error message, you'll need to contact Microsoft Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="3b493-184">온라인에서 이 사용자에 대한 동시 셸의 비즈니스용 Skype 수를 초과했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-184">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="3b493-185"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="3b493-185"><a name="BKMKMaxNumberShellsUser"> </a></span></span>

<span data-ttu-id="3b493-186">각 관리자는 온라인에서 최대 3개의 동시 원격 비즈니스용 Skype 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-186">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="3b493-187">세 개의 원격 PowerShell 연결이 실행되는 경우 다음 오류 메시지와 함께 네 번째 동시 연결을 시도하는 시도가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-187">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="3b493-188">**오류**: New-PSSession : [admin.vdomain.com] 다음 오류 메시지로 admin.vdomain.com 서버에 연결하지 못했습니다. WS-Management 서비스에서 요청을 처리하지 *못했습니다. 이 사용자에 대한 동시 셸의 최대 수가 초과됩니다. 기존 셸을 닫거나 이 사용자에 대한 할당량도 올렸다. 자세한 내용은 [원격 문제 해결](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="3b493-188">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="3b493-189">**해결** 방법 : 이 문제를 해결하는 유일한 방법은 이전 연결을 하나 이상 닫는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-189">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="3b493-190">온라인 세션을 비즈니스용 Skype 완료하면 **Remove-PSSession** cmdlet을 사용하여 세션을 종료하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-190">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="3b493-191">이렇게 하면 이 문제를 방지하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-191">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="3b493-192">온라인에서 이 테넌트에 대한 동시 셸의 비즈니스용 Skype 수를 초과했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-192">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="3b493-193"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="3b493-193"><a name="BKMKMaxNumberShellsTenant"> </a></span></span>

<span data-ttu-id="3b493-194">각 관리자는 온라인 테넌트에 최대 3개의 동시 연결을 허용할 수 비즈니스용 Skype 테넌트 하나만 20개 이상의 동시 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-194">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than 20 simultaneous connections.</span></span> <span data-ttu-id="3b493-195">예를 들어 관리자 6명은 각각 3개의 열려 있는 세션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-195">For example, six administrators might each have three open sessions.</span></span> <span data-ttu-id="3b493-196">네 번째 관리자가 두 개 이상의 연결(총 21개의 동시 연결)을 시도하는 경우 다음 오류 메시지와 함께 이 시도가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-196">If a fourth administrator tries to make more than two connections (resulting in a total of 21 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="3b493-197">**오류**: New-PSSession : [admin.vdomain.com] admin.vdomain.com 오류 메시지로 원격 서버에 연결하지 못했습니다. WS-Management 서비스에서 요청을 처리하지 *못했습니다. 이 테넌트에 대한 동시 셸의 최대 수가 초과됩니다. 기존 셸을 닫거나 이 테넌트에 대한 할당량은 올 입니다. 자세한 내용은 [원격 문제 해결](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1을 참조하세요.*</span><span class="sxs-lookup"><span data-stu-id="3b493-197">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message: The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="3b493-198">**해결** 방법 : 이 문제를 해결하는 유일한 방법은 이전 연결을 하나 이상 닫는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-198">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="3b493-199">온라인 세션을 비즈니스용 Skype 경우 **Remove-PSSession** cmdlet을 사용하여 해당 세션을 종료하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-199">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="3b493-200">이렇게 하면 이 문제를 방지하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b493-200">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="3b493-201">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3b493-201">Related topics</span></span>
[<span data-ttu-id="3b493-202">비즈니스용 Skype 온라인 관리용 컴퓨터를 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b493-202">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
