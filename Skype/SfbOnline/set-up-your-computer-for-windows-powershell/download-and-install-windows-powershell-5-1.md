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
description: Windows PowerShell 5.1을 다운로드, 설치 및 사용하여 비즈니스용 Skype Online에 연결하는 원격 PowerShell 세션을 만들 수 있습니다.
ms.openlocfilehash: 64d1ed1b3e3031f5186a09289ab6e1d9088840cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029099"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="9a088-103">Windows PowerShell 5.1 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="9a088-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="9a088-104">Windows 10 1주년 업데이트 또는 Windows Server 2016을 사용하는 경우 이미 5.1을 Windows PowerShell 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="9a088-105">이 애플리케이션은 해당 운영 체제에 미리 설치하기 때문에 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="9a088-106">사용 하는 Microsoft PowerShelll 버전을 확인하려면 Windows 7 또는 Windows Server 2008 R2 또는 Windows Server 2012 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="9a088-107">시작을 클릭하고 모든 프로그램을 클릭하고 **보조** 프로그램을 클릭한 다음 Windows PowerShell 클릭한 다음 **Windows PowerShell.**  </span><span class="sxs-lookup"><span data-stu-id="9a088-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="9a088-108">PowerShell 콘솔에서 다음 명령을 입력한 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="9a088-109">그런 다음 콘솔 창에 다음과 유사한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="9a088-110">반환된 버전 번호가 5.1이면 5.1에서 Windows PowerShell 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="9a088-111">반환된 버전 번호가 5.1이 아닌 경우 5.1을 Windows PowerShell 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="9a088-112">Microsoft Windows Management Framework 센터에서 Windows PowerShell 5.1을 포함하는 5.1을 [다운로드할 수 있습니다.](https://www.microsoft.com/download/details.aspx?id=54616)</span><span class="sxs-lookup"><span data-stu-id="9a088-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="9a088-113">5.1 Windows PowerShell 설치를 확인한 후 PowerShell이 원격 스크립트를 실행하도록 구성되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="9a088-114">이를 위해 관리자 권한으로 PowerShell을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="9a088-115">Windows 7, Windows Server 2008 R2, Windows Server 2012 또는 Windows Server 2012 R2에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="9a088-116">시작을 클릭하고 모든 프로그램을 클릭하고 **보조** 프로그램을 클릭하고 Windows PowerShell **클릭한** 다음 Windows PowerShell 관리자 권한으로  **실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9a088-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="9a088-117">사용자 계정 **컨트롤** 대화 상자가 나타나면 [예]를 클릭하여 관리자 자격 증명으로 PowerShell을 실행할지 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="9a088-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="9a088-118">Windows 8을 실행하는 경우 다음 절차를 대신 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="9a088-119">참 표시줄에 액세스하고 검색을 클릭한 다음 마우스 오른쪽 **단추로** Windows PowerShell. </span><span class="sxs-lookup"><span data-stu-id="9a088-119">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="9a088-120">Windows 키를 누르고 C 키를 눌러 Windows 8 컴퓨터(터치 스크린 또는 비 터치 스크린)에서 참 표시줄에 빠르게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-120">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="9a088-121">화면 아래쪽의 도구 모음에서 관리자 권한으로 **실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9a088-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="9a088-122">사용자 계정 **컨트롤** 대화 상자가 나타나면 [예]를 클릭하여 관리자 자격 증명으로 PowerShell을 실행할지 확인할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="9a088-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="9a088-123">PowerShell이 실행된 후 원격 스크립트 실행을 허용하도록 실행 정책을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-123">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="9a088-124">PowerShell 콘솔에서 다음 명령을 입력한 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-124">In the PowerShell console, type the following command and then press ENTER:</span></span>
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="9a088-125">이전 명령을 실행하면 다음 오류 메시지가 표시될 수 있습니다. > *Set-ExecutionPolicy: 레지스트리 키의 HKEY_LOCAL_MACHINE \\ SOFTWARE \\ Microsoft \\ PowerShell \\ 1 \\ ShellIds \\ Micrsoft.PowerShell'이 거부됩니다.*</span><span class="sxs-lookup"><span data-stu-id="9a088-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="9a088-126">이 오류 메시지는 일반적으로 관리자 자격 증명으로 PowerShell을 실행하지 않는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="9a088-127">PowerShell 세션을 닫고 관리자 권한으로 새 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="9a088-128">실행 정책이 올바르게 구성됐는지 확인하려면 PowerShell 프롬프트에서 다음을 입력하고 Enter를 누르기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-ExecutionPolicy
```

<span data-ttu-id="9a088-129">다음 값을 다시 얻게 된 경우 모든 것이 올바르게 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="9a088-130">현재 Windows PowerShell 5.1을 실행하고 있지 않은 경우 Microsoft 다운로드 센터에서 Windows Management Framework 5.1을 다운로드하여 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="9a088-131">5.1 및 WinRM(Windows 원격 Windows PowerShell) 3.0을 포함하는 설치 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="9a088-132">예를 들어 Windows 7 SP1을 실행 중일 때 아직 5.1 버전으로 업데이트되지 않은 경우 이 설치 패키지가 Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="9a088-133">Windows Server 2016 또는 Windows 10 1주년 업데이트를 실행하는 경우 5.1에서 Windows PowerShell 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="9a088-134">Windows PowerShell 5.1은 해당 운영 체제에 미리 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="9a088-135">5.1 Windows Management Framework 설치하기 전에:</span><span class="sxs-lookup"><span data-stu-id="9a088-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="9a088-136">올바른 버전의 설치 패키지를 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="9a088-137">64비트 버전의 Windows 7 SP1을 실행하는 경우 파일을 다운로드하여 Win7AndW2K8R2-KB3191566-x64.ZIP.</span><span class="sxs-lookup"><span data-stu-id="9a088-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="9a088-138">32비트 버전의 Windows 7을 실행하는 경우 파일을 다운로드하여 Win7-KB3191566-x86.ZIP.</span><span class="sxs-lookup"><span data-stu-id="9a088-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="9a088-139">컴퓨터에서 Windows 7을 실행하는 경우 Windows 7 서비스 팩 1을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="9a088-140">실행 중인 Windows 버전을 잘 모르겠거나 Windows 7 서비스 팩 1을 설치한 경우 시작을 클릭하고 **컴퓨터를** 마우스 오른쪽 단추로 클릭한 다음 **속성을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-140">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="9a088-141">이 정보는 시스템 대화 상자에 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-141">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="9a088-142">Windows Management Framework 5.1을 설치하려면 [WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure)설치 및 구성 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure).</span></span>
  
<span data-ttu-id="9a088-143">컴퓨터가 다시 시작된 후 Windows PowerShell 수 있으며 관리 자격 증명으로 애플리케이션을 실행할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-143">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="9a088-144">이 작업을 위해:</span><span class="sxs-lookup"><span data-stu-id="9a088-144">To do this:</span></span>
  
1. <span data-ttu-id="9a088-145">시작을 **클릭하고** 모든 프로그램을 클릭하고 **보조** 프로그램을 클릭하고 Windows PowerShell  **클릭한** 다음 Windows PowerShell 관리자 권한으로 **실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9a088-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="9a088-146">사용자 계정 컨트롤 대화 상자가  나타나면 [예]를 클릭하여 관리자 자격 증명으로 PowerShell을 실행할지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="9a088-147">PowerShell 콘솔이 나타나면 WinRM 서비스가 실행되고 있으며 올바르게 구성됐는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-147">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="9a088-148">서비스가 실행 중인지 확인을 위해 PowerShell 프롬프트에서 다음 명령을 입력한 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-148">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-Service winrm
```

<span data-ttu-id="9a088-149">그러면 WinRM 서비스에 대한 정보가 화면에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="9a088-150">서비스 상태가 "실행 중"과 같지 않은 경우 다음 명령을 입력한 다음 Enter를 눌러 WinRM 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```PowerShell
Start-Service winrm
```

<span data-ttu-id="9a088-151">서비스가 시작된 후 다음 명령을 실행하여 WinRM이 기본 인증을 사용하고 있는지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="9a088-152">다음과 유사한 정보가 화면에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="9a088-153">기본 인증이 true로 설정된 경우 PowerShell을 사용하여 비즈니스용 Skype Online에 연결할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9a088-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="9a088-154">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9a088-154">Related topics</span></span>
[<span data-ttu-id="9a088-155">Windows PowerShell용 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="9a088-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
