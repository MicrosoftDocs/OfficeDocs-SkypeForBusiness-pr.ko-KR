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
description: 가져오기 모듈, 동시 셸, 라이브 ID 및 사용 권한 오류를 포함하여 비즈니스용 Skype Online에 연결하는 원격 PowerShell 세션을 만드는 문제를 해결합니다.
ms.openlocfilehash: 019ef023b325227be046aae1e855573449453864
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204879"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="1715c-103">비즈니스용 Skype Online 커넥터의 연결 문제 진단</span><span class="sxs-lookup"><span data-stu-id="1715c-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="1715c-104">이 항목에서는 비즈니스용 Skype Online에 연결하는 원격 Microsoft PowerShell 세션을 만들 때 발생할 수 있는 문제를 진단하고 해결하는 데 도움이 되는 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="1715c-105">다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1715c-105">See the following sections:</span></span>
  
- [<span data-ttu-id="1715c-106">실행 정책으로 인해 Windows PowerShell 모듈 오류</span><span class="sxs-lookup"><span data-stu-id="1715c-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="1715c-107">모듈의 잘못된 버전으로 인한 가져오기 모듈 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1715c-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="1715c-108">WinRM 기본 인증을 사용하지 않도록 설정한 경우 최신 인증이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-108">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [<span data-ttu-id="1715c-109">Live ID 서버에 연결하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-109">Failed to connect to Live ID Server</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="1715c-110">Live ID 모듈을 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-110">Failed to load Live ID module</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="1715c-111">사용자에 대한 로그온 실패</span><span class="sxs-lookup"><span data-stu-id="1715c-111">Logon failed for the user</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="1715c-112">사용자에게 이 테넌트 관리 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-112">The user does not have permission to manage this tenant</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="1715c-113">비즈니스용 Skype Online에서 테넌트에 연결하는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-113">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="1715c-114">비즈니스용 Skype Online에서 이 사용자의 최대 동시 셸 수를 초과했습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-114">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="1715c-115">비즈니스용 Skype Online에서 이 테넌트의 최대 동시 셸 수를 초과했습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-115">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> <span data-ttu-id="1715c-116">기본적으로 PowerShell 세션은 60분 후에 시간적이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-116">By default, PowerShell sessions time out after sixty minutes.</span></span> <span data-ttu-id="1715c-117">다시 연결하기 위해 세션을 닫고 새 PowerShell 세션을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-117">To reconnect, you have to close the session and launch a new PowerShell session.</span></span> <span data-ttu-id="1715c-118">60분의 시간 시간 문제를 완화하는 **Enable-CsOnlineSessionForReconnection이라는** 새 cmdlet을 포함하는 새로운 버전의 비즈니스용 [Skype Online Windows PowerShell Module(2046.123 - 게시 2019/10/2)이](https://www.microsoft.com/download/details.aspx?id=39366)최근에 출시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-118">A new version of [Skype for Business Online, Windows PowerShell Module (2046.123 - Published 10/2/2019)](https://www.microsoft.com/download/details.aspx?id=39366), has been launched recently which includes a new cmdlet called **Enable-CsOnlineSessionForReconnection** that mitigates the 60 minutes time-out issue.</span></span>
> <span data-ttu-id="1715c-119">PowerShell 세션은 다시 연결하고 인증하므로 다시 연결하기 위해 새 인스턴스를 시작하지 않고도 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-119">The PowerShell session reconnects and authenticates, allowing it to be re-used without having to launch a new instance to reconnect.</span></span>



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="1715c-120">Import-Module 정책으로 인해 Windows PowerShell 오류 발생</span><span class="sxs-lookup"><span data-stu-id="1715c-120">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="1715c-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="1715c-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span></span>

<span data-ttu-id="1715c-122">PowerShell 실행 정책은 PowerShell 콘솔에 로드할 수 있는 구성 파일과 사용자가 해당 콘솔에서 실행할 수 있는 스크립트를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-122">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="1715c-123">최소한 비즈니스용 Skype Online Connector 모듈은 실행 정책을 RemoteSigned로 설정하지 않는 한 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-123">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="1715c-124">그렇지 않은 경우 모듈을 가져오는 경우 다음과 같은 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-124">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="1715c-125">**오류**: Import-Module : 파일 C: 프로그램 파일 일반 파일 <em> \\ Microsoft \\ \\ Lync Server 2013 \\ 모듈 \\ LyncOnlineConnector \\ LyncOnlineConnector LyncOnlineConnectorStartup.psm1은 이 시스템에서 스크립트를 실행하지 않도록 설정되어 있기 때문에 로드할 수 없습니다. 자세한 내용은 다음 about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170 참조하세요.</em></span><span class="sxs-lookup"><span data-stu-id="1715c-125">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="1715c-126">**해결** 이 문제를 해결하기 위해 관리자 권한으로 PowerShell을 시작한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-126">**Resolution** To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="1715c-127">실행 정책에 대한 자세한 내용은 실행 정책 [정보를 참조합니다.](https://go.microsoft.com/fwlink/?LinkID=135170)</span><span class="sxs-lookup"><span data-stu-id="1715c-127">For details about execution policy, see [About Execution Policies](https://go.microsoft.com/fwlink/?LinkID=135170).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="1715c-128">Import-Module 버전이 잘못되어 발생하는 오류 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1715c-128">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="1715c-129"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="1715c-129"><a name="BKMKIncorrectVersion"> </a></span></span>

<span data-ttu-id="1715c-130">비즈니스용 Skype Online Connector 모듈은 3.0에서 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-130">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="1715c-131">이전 버전의 PowerShell에서 모듈을 가져오려고 하면 가져오기 프로세스가 실패하고 이와 유사한 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-131">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="1715c-132">**오류:** *Import-Module: 로드된 PowerShell의 버전은 '2.0'입니다. 'D: \\ Program Files Common Files Microsoft \\ \\ Lync Server 2013 \\ Modules \\ LyncOnlineConnectorLyncOnlineConnector.psd1' 모듈을 실행하려면 \\ 최소 PowerShell 버전 '3.0'이 필요합니다. PowerShell 설치를 확인하고 다시 시도하세요.*</span><span class="sxs-lookup"><span data-stu-id="1715c-132">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="1715c-133">**해결** 방법: 이 문제를 해결하는 유일한 방법은 microsoft 다운로드 센터에서 Windows PowerShell 3.0을 설치하는 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-133">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).</span></span>
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a><span data-ttu-id="1715c-134">WinRM 기본 인증을 사용하지 않도록 설정한 경우 최신 인증이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-134">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>
<span data-ttu-id="1715c-135"><a name="BKMKWinRMBasicAuth"> </a></span><span class="sxs-lookup"><span data-stu-id="1715c-135"><a name="BKMKWinRMBasicAuth"> </a></span></span>

<span data-ttu-id="1715c-136">최신 버전의 비즈니스용 Skype Online Connector 모듈은 최신 인증을 사용하지만 기본 인증을 허용하도록 기본 Windows 원격 관리(WinRM) 클라이언트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-136">The latest version of the Skype for Business Online Connector module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span>  <span data-ttu-id="1715c-137">최신 인증은 일반적으로 권한 부여: 전달자 헤더에 전달되는 *전달자 토큰을* 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-137">Modern authentication uses bearer tokens which are usually passed in the *Authorization: Bearer* header.</span></span> <span data-ttu-id="1715c-138">Windows PowerShell Skype PowerShell이 구축되는 경우 이 헤더를 조작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-138">Windows PowerShell, upon which Skype for Business PowerShell is built, does not allow for manipulation of this header.</span></span>  <span data-ttu-id="1715c-139">대신 비즈니스용 Skype PowerShell은 *권한 부여: 기본* 헤더를 사용하여 전달자 토큰을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-139">Instead, Skype for Business PowerShell uses the *Authorization: Basic* header to pass the bearer token.</span></span>

<span data-ttu-id="1715c-140">기본 [인증에 WinRM을 Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) 방법에 대한 지침은 다운로드 및 설치를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1715c-140">See [Download and install Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="1715c-141">Live ID 서버에 연결하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-141">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="1715c-142"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="1715c-142"><a name="BKMKFailedConnect"> </a></span></span>

<span data-ttu-id="1715c-143">일반적으로 다음 오류 메시지와 함께 연결 시도가 실패할 수 있는 세 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-143">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="1715c-144">**오류:** *Get-CsWebTicket: 라이브 ID 서버에 연결하지 못했습니다. 프록시가 활성화되어 있는지 또는 머신에* 라이브 ID 서버에 대한 네트워크 연결이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-144">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="1715c-145">**해결:** 종종 이 오류는 Microsoft Online Services 로그인 도우미가 실행되고 있지 않다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-145">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="1715c-146">PowerShell 프롬프트에서 다음 명령을 실행하여 이 서비스의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-146">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="1715c-147">서비스가 실행되고 있지 않은 경우 다음 명령을 사용하여 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-147">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="1715c-148">서비스가 실행 중인 경우 컴퓨터와 Microsoft Live ID 인증 서버 간의 네트워크 연결에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-148">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="1715c-149">이 확인을 위해 해당 Internet Explorer 을 열고 [ https://login.microsoftonline.com/ 으로 이동합니다.](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="1715c-149">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="1715c-150">거기에서 Microsoft 365 또는 Office 365에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-150">Try logging on to Microsoft 365 or Office 365 from there.</span></span> <span data-ttu-id="1715c-151">이 오류가 발생하면 네트워크 연결 문제가 발생하는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-151">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="1715c-152">일반적으로 Microsoft Live ID 인증 서버에 대한 연결 URI가 잘못된 값으로 구성된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-152">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="1715c-153">Sign-In 도우미가 실행되고 있으며 네트워크 연결 문제가 없다고 이미 판단한 경우 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-153">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="1715c-154">이 경우 Microsoft 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-154">In this case, contact Microsoft Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="1715c-155">Live ID 모듈을 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-155">Failed to load Live ID module</span></span>
<span data-ttu-id="1715c-156"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="1715c-156"><a name="BKMKFailedLoad"> </a></span></span>

<span data-ttu-id="1715c-157">PowerShell을 사용하여 비즈니스용 Skype Online을 관리하기 위한 전제 구성 Microsoft Online Services 로그인 도우미를 설치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-157">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="1715c-158">로그인 도우미가 설치되지 않은 경우 비즈니스용 Skype Online에서 원격 세션을 설정하려고 할 때 다음과 같은 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-158">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="1715c-159">**오류:** *Get-CsWebTicket: Live Id 모듈을 로드할 수 없습니다. 올바른 버전의 Live ID 로그인 도우미가 설치되어 있는지 확인합니다.*</span><span class="sxs-lookup"><span data-stu-id="1715c-159">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="1715c-160">**해결:** Microsoft Online Services 로그인 도우미는 IT 전문가를 위한 Microsoft Online Services Sign-In 도우미의 Microsoft 다운로드 센터에서 사용할 [수 있습니다.](https://www.microsoft.com/download/details.aspx?id=28177)</span><span class="sxs-lookup"><span data-stu-id="1715c-160">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="1715c-161">사용자에 대한 로그온 실패</span><span class="sxs-lookup"><span data-stu-id="1715c-161">Logon failed for the user</span></span>
<span data-ttu-id="1715c-162"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="1715c-162"><a name="BKMKLogonFailed"> </a></span></span>

<span data-ttu-id="1715c-163">비즈니스용 Skype Online에 원격 연결을 시도하는 경우 유효한 비즈니스용 Skype Online 사용자 계정의 사용자 이름과 암호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-163">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="1715c-164">그렇지 않은 경우 로그온은 이와 유사한 오류 메시지와 함께 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-164">If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="1715c-165">**오류:** *Get-CsWebTicket: 'kenmyer@litwareinc.com' 사용자에 대해 로그온에 실패했습니다. 올바른 사용자* 이름과 암호를 사용한지 확인하여 새 PSCredential 개체를 만들어 주세요.</span><span class="sxs-lookup"><span data-stu-id="1715c-165">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="1715c-166">**해결:** 유효한 사용자 계정을 사용하고 있으며 올바른 암호가 있는 것으로 생각되는 경우 다시 로그온해 하세요.</span><span class="sxs-lookup"><span data-stu-id="1715c-166">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="1715c-167">실패하는 경우 동일한 자격 증명을 사용하여 .에서 로그온을 [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-167">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="1715c-168">로그온할 수 없는 경우 Microsoft 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-168">If you are unable to log on there, contact Microsoft Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="1715c-169">사용자에게 이 테넌트 관리 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-169">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="1715c-170"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="1715c-170"><a name="BKMKUserPermission"> </a></span></span>

<span data-ttu-id="1715c-171">테넌트 관리자 그룹의 구성원이면 비즈니스용Skype Online에 대한 원격 PowerShell 연결을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-171">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="1715c-172">그렇지 않은 경우 연결 시도가 실패하고 다음과 같은 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-172">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="1715c-173">**오류**: New-PSSession : [admin.vdomain.com] 원격 서버의 데이터 admin.vdomain.com 다음 오류 메시지로 실패했습니다. 'user@foo.com' 사용자에게 이 테넌트 관리 권한이 *없습니다. 적절한 RBAC 역할에 사용자를 할당하여 권한을 부여할 수 있습니다. 자세한 내용은 원격 문제 [해결을 참조하세요.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*</span><span class="sxs-lookup"><span data-stu-id="1715c-173">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="1715c-174">**해결:** 테넌트 관리자 그룹의 구성원인 경우 Microsoft 지원에 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-174">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Microsoft Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="1715c-175">비즈니스용 Skype Online에서 테넌트에 연결하는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-175">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="1715c-176"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="1715c-176"><a name="BKMKAbilityConnect"> </a></span></span>

<span data-ttu-id="1715c-177">PowerShell을 사용하여 비즈니스용 Skype Online을 관리하려면 테넌트 PowerShell 정책의 EnableRemotePowerShellAccess 속성을 으로 설정해야  `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-177">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="1715c-178">그렇지 않은 경우 연결이 실패하고 다음과 같은 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-178">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="1715c-179">**오류**: New-PSSession : [admin.vdomain.com] 원격 admin.vdomain.com 서버에서 데이터를 처리하지 못했습니다. 원격 PowerShell 세션을 사용하여 이 테넌트에 연결하는 기능을 사용할 수 *없습니다. 이 테넌트의 테넌트 Powershell 정책을 확인하기 위해 Lync 도움말에 문의합니다. 자세한 내용은 원격 문제 [해결을 참조하세요.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*</span><span class="sxs-lookup"><span data-stu-id="1715c-179">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="1715c-180">**해결:** 이 오류 메시지가 표시되면 Microsoft 지원에 문의하고 원격 PowerShell 액세스를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-180">**Resolution**: If you see this error message, you'll need to contact Microsoft Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="1715c-181">비즈니스용 Skype Online에서 이 사용자의 최대 동시 셸 수를 초과했습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-181">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="1715c-182"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="1715c-182"><a name="BKMKMaxNumberShellsUser"> </a></span></span>

<span data-ttu-id="1715c-183">각 관리자는 비즈니스용 Skype Online에 최대 3개의 동시 원격 연결을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-183">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="1715c-184">원격 PowerShell 연결이 3개 실행 중인 경우 다음 오류 메시지와 함께 네 번째 동시 연결을 시도하면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-184">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="1715c-185">**오류**: New-PSSession : [admin.vdomain.com] 원격 서버 admin.vdomain.com 연결에 실패했습니다. WS-Management 서비스에서 요청을 처리하지 *못했습니다. 이 사용자에 대한 최대 동시 셸 수를 초과했습니다. 기존 셸을 닫거나 이 사용자에 대한 할당량도 높입니다. 자세한 내용은 [원격 문제 해결]( https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span><span class="sxs-lookup"><span data-stu-id="1715c-185">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="1715c-186">**해결** 방법: 이 문제를 해결하는 유일한 방법은 이전 연결 중 하나 이상을 닫는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-186">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="1715c-187">비즈니스용 Skype Online 세션이 완료되면 **Remove-PSSession** cmdlet을 사용하여 세션을 종료하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-187">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="1715c-188">이렇게 하면 이 문제를 방지하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-188">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="1715c-189">비즈니스용 Skype Online에서 이 테넌트의 최대 동시 셸 수를 초과했습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-189">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="1715c-190"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="1715c-190"><a name="BKMKMaxNumberShellsTenant"> </a></span></span>

<span data-ttu-id="1715c-191">각 관리자가 비즈니스용 Skype Online 테넌트에 대해 최대 3개의 동시 연결을 사용할 수 있도록 허용되는 경우 단일 테넌트는 20개 이상의 동시 연결을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-191">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than 20 simultaneous connections.</span></span> <span data-ttu-id="1715c-192">예를 들어 관리자 6명은 각각 3개의 열린 세션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-192">For example, six administrators might each have three open sessions.</span></span> <span data-ttu-id="1715c-193">네 번째 관리자가 2개 이상의 연결을 시도하면(총 21개 동시 연결이 발생) 다음 오류 메시지와 함께 이 시도가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-193">If a fourth administrator tries to make more than 2 connections (resulting in a total of 21 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="1715c-194">**오류**: New-PSSession : [admin.vdomain.com] 원격 서버 admin.vdomain.com 연결에 실패했습니다. WS-Management 서비스에서 요청을 처리하지 *못했습니다. 이 테넌트에 대한 최대 동시 셸 수를 초과했습니다. 기존 셸을 닫거나 이 테넌트에 대한 할당량도 높입니다. 자세한 내용은 [원격 문제 해결]( https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span><span class="sxs-lookup"><span data-stu-id="1715c-194">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="1715c-195">**해결** 방법: 이 문제를 해결하는 유일한 방법은 이전 연결 중 하나 이상을 닫는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-195">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="1715c-196">비즈니스용 Skype Online 세션이 완료되면 **Remove-PSSession** cmdlet을 사용하여 해당 세션을 종료하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-196">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="1715c-197">이렇게 하면 이 문제를 방지하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1715c-197">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="1715c-198">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1715c-198">Related topics</span></span>
[<span data-ttu-id="1715c-199">비즈니스용 Skype 온라인 관리를 위한 컴퓨터를 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1715c-199">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
