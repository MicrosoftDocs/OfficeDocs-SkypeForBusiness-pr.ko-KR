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
description: 가져오기 모듈, 동시 셸, 라이브 ID 및 권한 오류를 포함하여 비즈니스용 Skype Online에 연결하는 원격 PowerShell 세션을 만드는 문제를 해결합니다.
ms.openlocfilehash: d27e40c7db423b0ef364a9d23eb956ba7059b03b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097284"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="50ebd-103">비즈니스용 Skype Online 커넥터의 연결 문제 진단</span><span class="sxs-lookup"><span data-stu-id="50ebd-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="50ebd-104">이 항목에서는 비즈니스용 Skype Online에 연결하는 원격 Microsoft PowerShell 세션을 만들 때 발생할 수 있는 문제를 진단하고 해결하는 데 도움이 되는 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="50ebd-105">다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50ebd-105">See the following sections:</span></span>
  
- [<span data-ttu-id="50ebd-106">실행 정책에 Windows PowerShell 가져오기 모듈 오류</span><span class="sxs-lookup"><span data-stu-id="50ebd-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="50ebd-107">잘못된 버전으로 인해 발생하는 가져오기 모듈 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="50ebd-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="50ebd-108">Live ID 서버에 연결하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-108">Failed to connect to Live ID Server</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="50ebd-109">Live ID 모듈을 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-109">Failed to load Live ID module</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="50ebd-110">사용자에게 로그온이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-110">Logon failed for the user</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="50ebd-111">사용자에게 이 테넌트 관리 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-111">The user does not have permission to manage this tenant</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="50ebd-112">비즈니스용 Skype Online에서 테넌트에 연결하는 기능을 사용하지 않도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-112">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [<span data-ttu-id="50ebd-113">비즈니스용 Skype Online에서 이 사용자의 최대 동시 셸 수가 초과된 경우</span><span class="sxs-lookup"><span data-stu-id="50ebd-113">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="50ebd-114">비즈니스용 Skype Online에서 이 테넌트의 최대 동시 셸 수가 초과된 경우</span><span class="sxs-lookup"><span data-stu-id="50ebd-114">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="50ebd-115">Import-Module 실행 정책으로 Windows PowerShell 오류 발생</span><span class="sxs-lookup"><span data-stu-id="50ebd-115">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="50ebd-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="50ebd-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span></span>

<span data-ttu-id="50ebd-117">PowerShell 실행 정책은 PowerShell 콘솔에 로드할 수 있는 구성 파일 및 사용자가 해당 콘솔에서 실행할 수 있는 스크립트를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-117">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="50ebd-118">실행 정책을 RemoteSigned로 설정하지 않는 한 비즈니스용 Skype Online 커넥터 모듈을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-118">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="50ebd-119">그렇지 않은 경우 모듈을 가져오는 경우 다음 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-119">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="50ebd-120">**오류**: 가져오기 모듈 : 파일 C: 프로그램 파일 일반 파일 <em> \\ Microsoft \\ \\ Lync Server 2013 \\ 모듈 \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1은 이 시스템에서 스크립트를 실행하지 않도록 설정되어 있기 때문에 로드할 수 없습니다. 자세한 내용은 에서 about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170 참조하세요.</em></span><span class="sxs-lookup"><span data-stu-id="50ebd-120">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="50ebd-121">**해결**: 이 문제를 해결하기 위해 PowerShell을 관리자 권한으로 시작한 다음 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-121">**Resolution**: To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="50ebd-122">실행 정책에 대한 자세한 내용은 실행 정책 [정보를 참조합니다.](/powershell/module/microsoft.powershell.core/about/about_execution_policies)</span><span class="sxs-lookup"><span data-stu-id="50ebd-122">For details about execution policy, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="50ebd-123">Import-Module 잘못된 버전으로 인해 발생하는 오류 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="50ebd-123">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="50ebd-124"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="50ebd-124"><a name="BKMKIncorrectVersion"> </a></span></span>

<span data-ttu-id="50ebd-125">비즈니스용 Skype Online 커넥터 모듈은 3.0에서만 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-125">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="50ebd-126">이전 버전의 PowerShell에서 모듈을 가져오려고 하면 가져오기 프로세스가 이와 유사한 오류 메시지로 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-126">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="50ebd-127">**오류**: *Import-Module : 로드된 PowerShell의 버전은 '2.0'입니다. 'D: \\ Program Files Common Files Microsoft \\ \\ Lync Server 2013 \\ Modules \\ LyncOnlineConnectorLyncOnlineConnector.psd1' 모듈은 \\ '3.0'의 최소 PowerShell 버전을 실행해야 합니다. PowerShell의* 설치를 확인하고 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="50ebd-127">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="50ebd-128">**해결** 방법 : 이 문제를 해결하는 유일한 방법은 Windows PowerShell 의 Microsoft 다운로드 센터에서 사용할 수 있는 3.0을 설치하는 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-128">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).</span></span>
  
## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="50ebd-129">Live ID 서버에 연결하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-129">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="50ebd-130"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="50ebd-130"><a name="BKMKFailedConnect"> </a></span></span>

<span data-ttu-id="50ebd-131">일반적으로 다음 오류 메시지로 연결 시도가 실패할 수 있는 세 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-131">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="50ebd-132">**오류**: *Get-CsWebTicket : 라이브 ID 서버를 연결하지 못했습니다. 프록시를 사용하도록 설정하거나 머신에* 라이브 ID 서버에 대한 네트워크 연결이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-132">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="50ebd-133">**해결:** 종종 이 오류는 로그인 Microsoft Online Services 실행되지 않는 경우를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-133">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="50ebd-134">PowerShell 프롬프트에서 다음 명령을 실행하여 이 서비스의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-134">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="50ebd-135">서비스가 실행되지 않는 경우 다음 명령을 사용하여 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-135">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="50ebd-136">서비스가 실행 중인 경우 컴퓨터와 Microsoft Live ID 인증 서버 간의 네트워크 연결에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-136">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="50ebd-137">이 확인을 확인 Internet Explorer 을 열고 [ https://login.microsoftonline.com/ 로 이동합니다.](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="50ebd-137">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="50ebd-138">Microsoft 365 또는 Office 365에 로그온해 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-138">Try logging on to Microsoft 365 or Office 365 from there.</span></span> <span data-ttu-id="50ebd-139">이 오류가 발생하면 네트워크 연결 문제가 발생하는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-139">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="50ebd-140">일반적으로 Microsoft Live ID 인증 서버의 연결 URI가 잘못된 값으로 구성된 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-140">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="50ebd-141">지원 도우미가 Sign-In 네트워크 연결 문제가 발생하지 않았다고 이미 판단한 경우 이 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-141">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="50ebd-142">이 경우 Microsoft 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-142">In this case, contact Microsoft Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="50ebd-143">Live ID 모듈을 로드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-143">Failed to load Live ID module</span></span>
<span data-ttu-id="50ebd-144"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="50ebd-144"><a name="BKMKFailedLoad"> </a></span></span>

<span data-ttu-id="50ebd-145">PowerShell을 사용하여 비즈니스용 Skype Online을 관리하기 위한 필요한 Microsoft Online Services 로그인 도우미를 설치하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-145">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="50ebd-146">로그인 도우미가 설치되어 있지 않은 경우 비즈니스용 Skype Online을 사용하여 원격 세션을 설정하려고 하면 다음 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-146">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="50ebd-147">**오류**: *Get-CsWebTicket : Live Id 모듈을 로드할 수 없습니다. 올바른 버전의 Live Id 로그인* 도우미가 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-147">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="50ebd-148">**해결:** Microsoft Online Services 로그인 도우미는 IT 전문가 [RTW용](https://www.microsoft.com/download/details.aspx?id=28177) Microsoft Microsoft Online Services Sign-In 다운로드 센터에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-148">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="50ebd-149">사용자에게 로그온이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-149">Logon failed for the user</span></span>
<span data-ttu-id="50ebd-150"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="50ebd-150"><a name="BKMKLogonFailed"> </a></span></span>

<span data-ttu-id="50ebd-151">비즈니스용 Skype Online에 원격 연결을 시도하는 경우 유효한 비즈니스용 Skype Online 사용자 계정의 사용자 이름과 암호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-151">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="50ebd-152">그렇지 않은 경우 로그온은 이와 유사한 오류 메시지와 함께 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-152">If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="50ebd-153">**오류**: *Get-CsWebTicket : Logon이 'kenmyer@litwareinc.com'에 실패했습니다. 올바른 사용자* 이름과 암호를 사용한지 확인하여 새 PSCredential 개체를 만들어 주세요.</span><span class="sxs-lookup"><span data-stu-id="50ebd-153">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="50ebd-154">**해결**: 유효한 사용자 계정을 사용하고 있으며 올바른 암호가 있는 것으로 생각되는 경우 다시 로그온해 하세요.</span><span class="sxs-lookup"><span data-stu-id="50ebd-154">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="50ebd-155">이 오류가 발생하면 동일한 자격 증명을 사용하여 에서 로그온해 를 [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-155">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="50ebd-156">로그온할 수 없는 경우 Microsoft 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-156">If you are unable to log on there, contact Microsoft Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="50ebd-157">사용자에게 이 테넌트 관리 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-157">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="50ebd-158"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="50ebd-158"><a name="BKMKUserPermission"> </a></span></span>

<span data-ttu-id="50ebd-159">테넌트 관리자 그룹의 구성원이면 비즈니스용 온라인용Skype에 원격 PowerShell 연결을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-159">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="50ebd-160">그렇지 않은 경우 연결 시도가 실패하고 다음 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-160">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="50ebd-161">**오류**: New-PSSession : [admin.vdomain.com] 원격 서버 admin.vdomain.com 데이터 처리에 *실패했습니다. 사용자 'user@foo.com'는 이 테넌트 관리 권한이 없습니다. 적절한 RBAC 역할에 사용자를 할당하여 권한을 부여할 수 있습니다. 자세한 내용은 원격 문제 [해결 을 참조하세요.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*</span><span class="sxs-lookup"><span data-stu-id="50ebd-161">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="50ebd-162">**해결:** 테넌트 관리자 그룹의 구성원인 경우 Microsoft 지원에 문의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-162">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Microsoft Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="50ebd-163">비즈니스용 Skype Online에서 테넌트에 연결하는 기능을 사용하지 않도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-163">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="50ebd-164"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="50ebd-164"><a name="BKMKAbilityConnect"> </a></span></span>

<span data-ttu-id="50ebd-165">PowerShell을 사용하여 비즈니스용 Skype Online을 관리하려면 테넌트 PowerShell 정책의 EnableRemotePowerShellAccess 속성을 로 설정해야  `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-165">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="50ebd-166">그렇지 않은 경우 연결이 실패하고 다음 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-166">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="50ebd-167">**오류**: New-PSSession : [admin.vdomain.com] 원격 서버의 데이터 admin.vdomain.com 오류 메시지로 실패했습니다. 원격 PowerShell 세션을 사용하여 이 테넌트에 연결하는 기능을 사용하지 않도록 *설정했습니다. 이 테넌트의 테넌트 Powershell 정책을 확인하기 위해 Lync 도움말에 문의하시기 바랍니다. 자세한 내용은 원격 문제 [해결 을 참조하세요.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*</span><span class="sxs-lookup"><span data-stu-id="50ebd-167">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="50ebd-168">**해결:** 이 오류 메시지가 표시되면 Microsoft 지원에 문의하고 원격 PowerShell 액세스를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-168">**Resolution**: If you see this error message, you'll need to contact Microsoft Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="50ebd-169">비즈니스용 Skype Online에서 이 사용자의 최대 동시 셸 수가 초과된 경우</span><span class="sxs-lookup"><span data-stu-id="50ebd-169">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="50ebd-170"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="50ebd-170"><a name="BKMKMaxNumberShellsUser"> </a></span></span>

<span data-ttu-id="50ebd-171">각 관리자는 비즈니스용 Skype Online에 최대 3개의 동시 원격 연결을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-171">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="50ebd-172">세 개의 원격 PowerShell 연결이 실행되는 경우 다음 오류 메시지와 함께 네 번째 동시 연결을 시도하는 시도가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-172">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="50ebd-173">**오류**: New-PSSession : [admin.vdomain.com] 다음 오류 메시지로 admin.vdomain.com 서버에 연결하지 못했습니다. WS-Management 서비스에서 요청을 처리하지 *못했습니다. 이 사용자에 대한 동시 셸의 최대 수가 초과됩니다. 기존 셸을 닫거나 이 사용자에 대한 할당량도 올렸다. 자세한 내용은 [원격 문제 해결]을 참조하세요. https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span><span class="sxs-lookup"><span data-stu-id="50ebd-173">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="50ebd-174">**해결** 방법 : 이 문제를 해결하는 유일한 방법은 이전 연결을 하나 이상 닫는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-174">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="50ebd-175">비즈니스용 Skype Online 세션이 완료되면 **Remove-PSSession** cmdlet을 사용하여 세션을 종료하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-175">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="50ebd-176">이렇게 하면 이 문제를 방지하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-176">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="50ebd-177">비즈니스용 Skype Online에서 이 테넌트의 최대 동시 셸 수가 초과된 경우</span><span class="sxs-lookup"><span data-stu-id="50ebd-177">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="50ebd-178"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="50ebd-178"><a name="BKMKMaxNumberShellsTenant"> </a></span></span>

<span data-ttu-id="50ebd-179">각 관리자는 비즈니스용 Skype Online 테넌트에 최대 3개의 동시 연결을 허용할 수 있습니다. 단일 테넌트는 20개 이상의 동시 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-179">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than twenty simultaneous connections.</span></span> <span data-ttu-id="50ebd-180">예를 들어 관리자 6명은 각각 3개의 열려 있는 세션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-180">For example, six administrators might each have three open sessions.</span></span> <span data-ttu-id="50ebd-181">7번째 관리자는 두 개 이상의 연결을 열고(총 21개의 동시 연결로 인해) 실패합니다. 다음 오류 메시지와 함께 이 시도는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-181">If a seventh administrator tries to open more than two connections (resulting in a total of 21 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="50ebd-182">**오류**: New-PSSession : [admin.vdomain.com] 다음 오류 메시지로 admin.vdomain.com 서버에 연결하지 못했습니다. WS-Management 서비스에서 요청을 처리하지 *못했습니다. 이 테넌트에 대한 동시 셸의 최대 수가 초과됩니다. 기존 셸을 닫거나 이 테넌트에 대한 할당량은 올 입니다. 자세한 내용은 [원격 문제 해결]을 참조하세요. https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span><span class="sxs-lookup"><span data-stu-id="50ebd-182">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="50ebd-183">**해결** 방법 : 이 문제를 해결하는 유일한 방법은 이전 연결을 하나 이상 닫는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-183">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="50ebd-184">비즈니스용 Skype Online 세션이 완료되면 **Remove-PSSession** cmdlet을 사용하여 해당 세션을 종료하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-184">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="50ebd-185">이렇게 하면 이 문제를 방지하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50ebd-185">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="50ebd-186">관련 항목</span><span class="sxs-lookup"><span data-stu-id="50ebd-186">Related topics</span></span>
[<span data-ttu-id="50ebd-187">비즈니스용 Skype 온라인 관리용 컴퓨터를 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="50ebd-187">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
