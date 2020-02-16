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
ms.openlocfilehash: e86ec24e47bf6e8ea8d3e6b4ea66ab9da89457fd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010631"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="5faf2-103">비즈니스용 Skype Online 커넥터의 연결 문제 진단</span><span class="sxs-lookup"><span data-stu-id="5faf2-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="5faf2-104">이 항목에서는 비즈니스용 Skype Online에 연결 하는 원격 Microsoft PowerShell 세션을 만들려고 할 때 발생할 수 있는 문제를 진단 하 고 해결 하는 데 도움이 되는 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="5faf2-105">다음 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5faf2-105">See the following sections:</span></span>
  
- [<span data-ttu-id="5faf2-106">Windows PowerShell 실행 정책으로 인해 발생 하는 가져오기 모듈 오류</span><span class="sxs-lookup"><span data-stu-id="5faf2-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="5faf2-107">잘못 된 버전의 Windows PowerShell로 인해 발생 하는 가져오기 모듈 오류</span><span class="sxs-lookup"><span data-stu-id="5faf2-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="5faf2-108">WinRM 기본 인증을 사용 하지 않도록 설정한 경우 최신 인증이 실패 함</span><span class="sxs-lookup"><span data-stu-id="5faf2-108">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [<span data-ttu-id="5faf2-109">Live ID 서버에 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-109">Failed to connect to Live ID Server</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="5faf2-110">라이브 ID 모듈을 로드 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-110">Failed to load Live ID module</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="5faf2-111">사용자에 대 한 로그온 실패</span><span class="sxs-lookup"><span data-stu-id="5faf2-111">Logon failed for the user</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="5faf2-112">사용자에 게이 테 넌 트를 관리할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-112">The user does not have permission to manage this tenant</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="5faf2-113">비즈니스용 Skype Online에서 테 넌 트 연결 기능을 사용 하지 않도록 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-113">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="5faf2-114">비즈니스용 Skype Online에서이 사용자에 대 한 최대 동시 셸 수가 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-114">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="5faf2-115">비즈니스용 Skype Online에서이 테 넌 트에 대 한 최대 동시 셸 수가 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-115">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> <span data-ttu-id="5faf2-116">기본적으로 PowerShell 세션은 60 분 후에 시간 초과 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-116">By default, PowerShell sessions time out after sixty minutes.</span></span> <span data-ttu-id="5faf2-117">다시 연결 하려면 세션을 닫고 새 PowerShell 세션을 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-117">To reconnect, you have to close the session and launch a new PowerShell session.</span></span> <span data-ttu-id="5faf2-118">새 버전의 비즈니스용 [Skype Online, Windows PowerShell 모듈 (2046.123-게시 10/2/2019)](https://www.microsoft.com/download/details.aspx?id=39366)은 최근에 실행 되었으며 60 분 시간 초과 문제를 완화 하는 **Enable-CsOnlineSessionForReconnection** 이라는 새 cmdlet이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-118">A new version of [Skype for Business Online, Windows PowerShell Module (2046.123 - Published 10/2/2019)](https://www.microsoft.com/download/details.aspx?id=39366), has been launched recently which includes a new cmdlet called **Enable-CsOnlineSessionForReconnection** that mitigates the 60 minutes time-out issue.</span></span>
> <span data-ttu-id="5faf2-119">PowerShell 세션은 다시 연결 하 고 인증 하며, 새 인스턴스를 다시 시작 하지 않고도 다시 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-119">The PowerShell session reconnects and authenticates, allowing it to be re-used without having to launch a new instance to reconnect.</span></span>



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="5faf2-120">Windows PowerShell 실행 정책으로 인해 발생 하는 가져오기 모듈 오류</span><span class="sxs-lookup"><span data-stu-id="5faf2-120">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="5faf2-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="5faf2-121"><a name="BKMKPowerShellExecutionPolicy"> </a></span></span>

<span data-ttu-id="5faf2-122">PowerShell 실행 정책은 PowerShell 콘솔로 로드할 수 있는 구성 파일 및 해당 콘솔에서 실행할 수 있는 스크립트를 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-122">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="5faf2-123">적어도 비즈니스용 Skype Online Connector 모듈은 실행 정책이 RemoteSigned로 설정 되지 않은 경우에만 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-123">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="5faf2-124">그렇지 않은 경우 모듈을 가져오려고 할 때 다음과 같은 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-124">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="5faf2-125">**오류**: <em>가져오기-모듈: 파일 C:\\프로그램 파일\\공통 파일\\시스템에서 스크립트를\\실행\\하\\는 기능이 비활성화 되어 있으므로 Microsoft Lync Server 2013 모듈 LyncOnlineConnector LyncOnlineConnectorStartup을 로드할 수 없습니다. 자세한 내용은의 about_Execution_Policies를 참조 하세요 https://go.microsoft.com/fwlink/?LinkID=135170.</em></span><span class="sxs-lookup"><span data-stu-id="5faf2-125">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="5faf2-126">**해결 방법** 이 문제를 해결 하려면 관리자로 PowerShell을 시작 하 고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-126">**Resolution** To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="5faf2-127">실행 정책에 대 한 자세한 내용은 [실행 정책 정보](https://go.microsoft.com/fwlink/?LinkID=135170)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5faf2-127">For details about execution policy, see [About Execution Policies](https://go.microsoft.com/fwlink/?LinkID=135170).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="5faf2-128">잘못 된 버전의 Windows PowerShell로 인해 발생 하는 가져오기 모듈 오류</span><span class="sxs-lookup"><span data-stu-id="5faf2-128">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="5faf2-129"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="5faf2-129"><a name="BKMKIncorrectVersion"> </a></span></span>

<span data-ttu-id="5faf2-130">비즈니스용 Skype Online Connector 모듈은 Windows PowerShell 3.0 에서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-130">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="5faf2-131">이전 버전의 PowerShell에서 모듈을 가져오려고 하면 다음과 같은 오류 메시지와 함께 가져오기 프로세스가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-131">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="5faf2-132">**오류**: *가져오기-모듈: 로드 된 PowerShell의 버전은 ' 2.0 '입니다. 모듈 d\\: 프로그램 파일\\일반적인 파일\\Microsoft Lync Server 2013\\module\\LyncOnlineConnector\\LyncOnlineConnector를 실행 하려면 최소 PowerShell 버전 ' 3.0 '이 필요 합니다. PowerShell 설치를 확인 한 후 다시 시도 하세요.*</span><span class="sxs-lookup"><span data-stu-id="5faf2-132">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="5faf2-133">**해결**방법:이 문제를 해결 하는 유일한 방법은 Microsoft 다운로드 센터에서 제공 하는 Windows PowerShell 3.0을 설치 하는 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595)것입니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-133">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).</span></span>
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a><span data-ttu-id="5faf2-134">WinRM 기본 인증을 사용 하지 않도록 설정한 경우 최신 인증이 실패 함</span><span class="sxs-lookup"><span data-stu-id="5faf2-134">Modern authentication fails when WinRM Basic authentication has been disabled</span></span>
<span data-ttu-id="5faf2-135"><a name="BKMKWinRMBasicAuth"> </a></span><span class="sxs-lookup"><span data-stu-id="5faf2-135"><a name="BKMKWinRMBasicAuth"> </a></span></span>

<span data-ttu-id="5faf2-136">최신 버전의 비즈니스용 Skype Online Connector 모듈은 최신 인증을 사용 하지만 기본 인증을 허용 하도록 기본 WinRM (Windows Remote Management) 클라이언트를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-136">The latest version of the Skype for Business Online Connector module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span>  <span data-ttu-id="5faf2-137">최신 인증은 일반적으로 *권한 부여: 전달자* 헤더에 전달 되는 전달자 토큰을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-137">Modern authentication uses bearer tokens which are usually passed in the *Authorization: Bearer* header.</span></span> <span data-ttu-id="5faf2-138">비즈니스용 Skype PowerShell이 빌드되는 Windows PowerShell에서는이 헤더를 조작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-138">Windows PowerShell, upon which Skype for Business PowerShell is built, does not allow for manipulation of this header.</span></span>  <span data-ttu-id="5faf2-139">대신 비즈니스용 Skype PowerShell에서는 *권한 부여: 기본* 헤더를 사용 하 여 전달자 토큰을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-139">Instead, Skype for Business PowerShell uses the *Authorization: Basic* header to pass the bearer token.</span></span>

<span data-ttu-id="5faf2-140">기본 인증을 위해 WinRM을 사용 하는 방법에 대 한 지침은 [Windows PowerShell 다운로드 및 설치](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5faf2-140">See [Download and install Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="5faf2-141">Live ID 서버에 연결 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-141">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="5faf2-142"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="5faf2-142"><a name="BKMKFailedConnect"> </a></span></span>

<span data-ttu-id="5faf2-143">일반적으로 다음 오류 메시지와 함께 연결 시도가 실패할 수 있는 세 가지 이유가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-143">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="5faf2-144">**오류**: *가져오기-cswebticket: live id 서버에 연결 하지 못했습니다. 프록시를 사용 하도록 설정 하거나 컴퓨터에 live id 서버에 대 한 네트워크 연결이 있는지 확인 합니다.*</span><span class="sxs-lookup"><span data-stu-id="5faf2-144">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="5faf2-145">**해결**:이 오류는 종종 Microsoft Online Services 로그인 도우미가 실행 되 고 있지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-145">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="5faf2-146">PowerShell 프롬프트에서 다음 명령을 실행 하 여이 서비스의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-146">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="5faf2-147">서비스가 실행 되 고 있지 않은 경우에는 다음 명령을 사용 하 여 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-147">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="5faf2-148">서비스가 실행 되 고 있는 경우 컴퓨터와 Microsoft Live ID 인증 서버 간의 네트워크 연결에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-148">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="5faf2-149">이를 확인 하려면 Internet Explorer를 열고으로 [ https://login.microsoftonline.com/이동 합니다.](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="5faf2-149">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="5faf2-150">여기에서 Office 365에 로그온 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5faf2-150">Try logging on to Office 365 from there.</span></span> <span data-ttu-id="5faf2-151">이 문제가 발생 하는 경우 네트워크 연결 문제가 발생 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-151">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="5faf2-152">덜 일반적으로 Microsoft Live ID 인증 서버의 연결 URI가 잘못 된 값으로 구성 되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-152">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="5faf2-153">이미 로그인 도우미가 실행 중이 고 네트워크 연결 문제가 발생 하지 않은 것으로 확인 된 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-153">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="5faf2-154">이 경우 Office 365 지원에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="5faf2-154">In this case, contact Office 365 Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="5faf2-155">라이브 ID 모듈을 로드 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-155">Failed to load Live ID module</span></span>
<span data-ttu-id="5faf2-156"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="5faf2-156"><a name="BKMKFailedLoad"> </a></span></span>

<span data-ttu-id="5faf2-157">PowerShell을 사용 하 여 비즈니스용 Skype Online을 관리 하기 위한 필수 구성 요소 중 하나는 Microsoft Online Services 로그인 도우미를 설치 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-157">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="5faf2-158">로그인 도우미가 설치 되어 있지 않은 경우 비즈니스용 Skype Online을 사용 하 여 원격 세션을 설정 하려고 하면 다음과 같은 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-158">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="5faf2-159">**오류**: *Get-Cswebticket: Live Id 모듈을 로드할 수 없습니다. 올바른 버전의 Live Id 로그인 도우미가 설치 되어 있는지 확인 합니다.*</span><span class="sxs-lookup"><span data-stu-id="5faf2-159">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="5faf2-160">**해결**방법: Microsoft Online Services 로그인 도우미는 [IT 전문가를 위한 Microsoft Online services 로그인 도우미](https://www.microsoft.com/download/details.aspx?id=28177) 의 microsoft 다운로드 센터에서 사용할 수 있습니다. rtw</span><span class="sxs-lookup"><span data-stu-id="5faf2-160">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="5faf2-161">사용자에 대 한 로그온 실패</span><span class="sxs-lookup"><span data-stu-id="5faf2-161">Logon failed for the user</span></span>
<span data-ttu-id="5faf2-162"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="5faf2-162"><a name="BKMKLogonFailed"> </a></span></span>

<span data-ttu-id="5faf2-163">비즈니스용 Skype Online으로 원격 연결을 시도 하는 경우 유효한 비즈니스용 Skype Online 사용자 계정에 대 한 사용자 이름 및 암호를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-163">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="5faf2-164">그렇지 않으면 다음과 유사한 오류 메시지와 함께 logon에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-164">If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="5faf2-165">**오류**: *get-help webticket: 사용자 ' kenmyer@litwareinc.com '에 대 한 로그온에 실패 했습니다. 올바른 사용자 이름 및 암호를 사용 하 고 있는지 확인 하 여 새 PSCredential 개체를 만들어 주십시오.*</span><span class="sxs-lookup"><span data-stu-id="5faf2-165">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="5faf2-166">**해결**방법: 유효한 사용자 계정을 사용 하 고 있고 올바른 암호를가지고 있다고 생각 되는 경우 다시 로그온 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5faf2-166">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="5faf2-167">이 문제가 발생 하면 같은 자격 증명을 사용 하 여에 [https://login.microsoftonline.com/](https://login.microsoftonline.com/)로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-167">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="5faf2-168">로그인 할 수 없는 경우에는 Office 365 지원에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="5faf2-168">If you are unable to log on there, contact Office 365 Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="5faf2-169">사용자에 게이 테 넌 트를 관리할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-169">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="5faf2-170"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="5faf2-170"><a name="BKMKUserPermission"> </a></span></span>

<span data-ttu-id="5faf2-171">테 넌 트 관리자 그룹의 구성원이 아닌 경우에는 원격 PowerShell 연결을 비즈니스용 Skype Online으로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-171">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="5faf2-172">그렇지 않으면 연결 시도가 실패 하 고 다음 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-172">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="5faf2-173">**오류**: *다음 오류 메시지 때문에 원격 서버 admin.vdomain.com에서 데이터를 처리 하는 동안 새 PSSession: [admin.vdomain.com]이 (가) 실패 했습니다. 사용자 ' user@foo.com '에 게이 테 넌 트를 관리할 수 있는 권한이 없습니다. 사용자를 적절 한 RBAC 역할에 할당 하 여 사용 권한을 부여할 수 있습니다. 자세한 내용은 [원격 문제 해결](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)을 참조 하세요.*</span><span class="sxs-lookup"><span data-stu-id="5faf2-173">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="5faf2-174">**해결**방법: 테 넌 트 관리자 그룹의 구성원 이거나이를 대상으로 생각 하는 경우 Office 365 지원에 문의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-174">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Office 365 Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="5faf2-175">비즈니스용 Skype Online에서 테 넌 트 연결 기능을 사용 하지 않도록 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-175">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="5faf2-176"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="5faf2-176"><a name="BKMKAbilityConnect"> </a></span></span>

<span data-ttu-id="5faf2-177">PowerShell을 사용 하 여 비즈니스용 Skype Online을 관리 하려면 테 넌 트 PowerShell 정책의 EnableRemotePowerShellAccess 속성을 (으) `True`로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-177">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="5faf2-178">그렇지 않으면 연결에 실패 하 고 다음 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-178">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="5faf2-179">**오류**: *다음 오류 메시지 때문에 원격 서버 admin.vdomain.com에서 데이터를 처리 하는 동안 새 PSSession: [admin.vdomain.com]에서 실패 했습니다. 원격 PowerShell 세션을 사용 하 여이 테 넌 트에 연결 하는 기능이 비활성화 되었습니다. Lync 도움말에 문의 하 여이 테 넌 트의 테 넌 트 Powershell 정책을 확인 하세요. 자세한 내용은 [원격 문제 해결](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)을 참조 하세요.*</span><span class="sxs-lookup"><span data-stu-id="5faf2-179">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="5faf2-180">**해결**방법:이 오류 메시지가 표시 되는 경우 Office 365 지원에 문의 하 여 원격 PowerShell 액세스를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-180">**Resolution**: If you see this error message, you'll need to contact Office 365 Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="5faf2-181">비즈니스용 Skype Online에서이 사용자에 대 한 최대 동시 셸 수가 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-181">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="5faf2-182"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="5faf2-182"><a name="BKMKMaxNumberShellsUser"> </a></span></span>

<span data-ttu-id="5faf2-183">각 관리자는 비즈니스용 Skype Online에 대해 최대 세 개의 동시 원격 연결을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-183">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="5faf2-184">세 개의 원격 PowerShell 연결이 있고 실행 중인 경우에는 네 번째 동시 연결 시도에 실패 하 고 다음 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-184">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="5faf2-185">**오류**: \*다음 오류 메시지 때문에 원격 서버 admin.vdomain.com에 대 한 새 PSSession: [Admin.vdomain.com]에 연결 하지 못했습니다. ws-management 서비스가 요청을 처리할 수 없습니다. 이 사용자에 대 한 최대 동시 셸 수가 초과 되었습니다. 기존 셸을 닫거나이 사용자의 할당량을 높이십시오. 자세한 내용은 [원격 문제 해결]을 참조 하세요 (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 \*</span><span class="sxs-lookup"><span data-stu-id="5faf2-185">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="5faf2-186">**해결**방법:이 문제를 해결 하는 유일한 방법은 이전 연결을 하나 이상 닫는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-186">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="5faf2-187">비즈니스용 Skype Online 세션을 마치면 **제거-PSSession** cmdlet을 사용 하 여 세션을 종료 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-187">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="5faf2-188">이는이 문제를 방지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-188">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="5faf2-189">비즈니스용 Skype Online에서이 테 넌 트에 대 한 최대 동시 셸 수가 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-189">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="5faf2-190"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="5faf2-190"><a name="BKMKMaxNumberShellsTenant"> </a></span></span>

<span data-ttu-id="5faf2-191">각 관리자는 비즈니스용 Skype Online 테 넌 트에 세 개의 동시 연결을 사용할 수 있지만, 단일 테 넌 트가 20 개 이상 동시 연결을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-191">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than 20 simultaneous connections.</span></span> <span data-ttu-id="5faf2-192">예를 들어 6 대의 관리자는 각각 세 개의 열린 세션을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-192">For example, six administrators might each have three open sessions.</span></span> <span data-ttu-id="5faf2-193">네 번째 관리자가 2 개 이상의 연결을 시도 하면 (총 21 개의 동시 연결을 초래 함), 다음 오류 메시지와 함께이 시도가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-193">If a fourth administrator tries to make more than 2 connections (resulting in a total of 21 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="5faf2-194">**오류**: \*다음 오류 메시지 때문에 원격 서버 admin.vdomain.com에 대 한 새 PSSession: [Admin.vdomain.com]에 연결 하지 못했습니다. ws-management 서비스가 요청을 처리할 수 없습니다. 이 테 넌 트에 대 한 최대 동시 셸 수가 초과 되었습니다. 기존 셸을 닫거나이 테 넌 트의 할당량을 높이십시오. 자세한 내용은 [원격 문제 해결]을 참조 하세요 (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 \*</span><span class="sxs-lookup"><span data-stu-id="5faf2-194">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="5faf2-195">**해결**방법:이 문제를 해결 하는 유일한 방법은 이전 연결을 하나 이상 닫는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-195">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="5faf2-196">비즈니스용 Skype Online 세션을 마치면 **제거-PSSession** cmdlet을 사용 하 여 해당 세션을 종료 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-196">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="5faf2-197">이는이 문제를 방지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5faf2-197">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="5faf2-198">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5faf2-198">Related topics</span></span>
[<span data-ttu-id="5faf2-199">Windows PowerShell을 사용 하 여 비즈니스용 skype online 관리를 위한 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="5faf2-199">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
