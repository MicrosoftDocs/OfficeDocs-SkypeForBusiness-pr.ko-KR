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
ms.openlocfilehash: 227023d5c86b99a66ecdbdabd3b2973d0383a534
ms.sourcegitcommit: ac922addbc1422b5c41273a2e03196efb2ed7770
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41831157"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="1e819-103">Windows PowerShell 5.1 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="1e819-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="1e819-104">Windows 10 기념 업데이트 또는 Windows Server 2016를 사용 하는 경우 Windows PowerShell 5.1이 이미 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="1e819-105">이 응용 프로그램은 해당 운영 체제에 사전 설치 되어 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="1e819-106">사용 중인 Microsoft PowerShelll 버전을 확인 하려면 Windows 7 또는 Windows Server 2008 R2 또는 Windows Server 2012 컴퓨터에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="1e819-107">**시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **보조 프로그램**, **windows powershell**, **windows powershell**을 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="1e819-108">PowerShell 콘솔에 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="1e819-109">다음과 유사한 정보가 콘솔 창에 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="1e819-110">반환 되는 버전 번호가 5.1 이면 Windows PowerShell 5.1을 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="1e819-111">반환 되는 버전 번호가 5.1이 아닌 경우 Windows PowerShell 5.1을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="1e819-112">[Microsoft 다운로드 센터](https://www.microsoft.com/en-us/download/details.aspx?id=54616)에서 windows PowerShell 5.1을 포함 하는 Windows Management 프레임 워크 5.1을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="1e819-113">Windows PowerShell 5.1이 설치 되어 있는지 확인 한 후에는 원격 스크립트 실행을 위해 PowerShell이 구성 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="1e819-114">이렇게 하려면 관리자로 PowerShell을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="1e819-115">Windows 7, Windows Server 2008 R2, Windows Server 2012 또는 Windows Server 2012 R2에서는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="1e819-116">**시작**, **모든 프로그램**, **액세서리**, **Windows PowerShell**을 차례로 클릭 하 고 **windows powershell**을 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="1e819-117">**사용자 계정 컨트롤** 대화 상자가 표시 되는 경우 **예** 를 클릭 하 여 관리자 자격 증명에서 PowerShell을 실행 하도록 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="1e819-118">Windows 8을 실행 하는 경우 대신 다음 절차를 완료 하세요.</span><span class="sxs-lookup"><span data-stu-id="1e819-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="1e819-119">참 메뉴 표시줄에 액세스 하 고 **검색**을 클릭 한 다음 **Windows PowerShell**을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-119">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="1e819-120">Windows 키를 누른 채 C를 눌러 Windows 8 컴퓨터 (터치 스크린 또는 터치 못 함 화면)의 참 메뉴 표시줄에 빠르게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-120">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="1e819-121">화면 아래쪽에 있는 도구 모음에서 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="1e819-122">**사용자 계정 컨트롤** 대화 상자가 표시 되는 경우 **예** 를 클릭 하 여 관리자 자격 증명에서 PowerShell을 실행 하도록 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="1e819-123">PowerShell을 실행 한 후에는 원격 스크립트 실행을 허용 하도록 실행 정책을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-123">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="1e819-124">PowerShell 콘솔에 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-124">In the PowerShell console, type the following command and then press ENTER:</span></span>
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="1e819-125">앞의 명령을 실행 하면 다음과 같은 오류 메시지가 표시 될 수 있습니다. > *Set-ExecutionPolicy: 레지스트리 키에 대 한 액세스 권한 '\\HKEY_LOCAL_MACHINE\\소프트웨어\\Microsoft\\PowerShell\\1\\ShellIds Micrsoft. PowerShell '이 (가) 거부 되었습니다.*</span><span class="sxs-lookup"><span data-stu-id="1e819-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="1e819-126">이 오류 메시지는 일반적으로 관리자 자격 증명으로 PowerShell을 실행 하지 않는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="1e819-127">PowerShell 세션을 닫고 관리자로 새 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="1e819-128">실행 정책이 올바르게 구성 되었는지 확인 하려면 PowerShell 프롬프트에서 다음을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-ExecutionPolicy
```

<span data-ttu-id="1e819-129">다음 값을 다시 가져오면 모든 항목이 올바르게 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="1e819-130">현재 Windows PowerShell 5.1을 실행 하 고 있지 않은 경우 Microsoft 다운로드 센터에서 Windows 관리 프레임 워크 5.1을 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="1e819-131">Windows PowerShell 5.1 및 WinRM (Windows Remote Management) 3.0을 포함 하는 설치 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="1e819-132">예를 들어 Windows 7 SP1을 실행 중이 고 아직 Windows PowerShell 5.1을 업데이트 하지 않은 경우이 설치 패키지가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="1e819-133">Windows Server 2016 또는 Windows 10 기념 업데이트를 실행 하는 경우 Windows PowerShell 5.1을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="1e819-134">Windows PowerShell 5.1은 이러한 운영 체제에 사전 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="1e819-135">Windows 관리 프레임 워크 5.1을 설치 하기 전에 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="1e819-136">올바른 버전의 설치 패키지를 다운로드 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="1e819-137">64 비트 버전의 Windows 7 SP1을 실행 하는 경우 Win7AndW2K8R2-KB3191566-x64 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="1e819-138">32 비트 버전의 Windows 7을 실행 하는 경우 Win7-KB3191566-x86 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="1e819-139">컴퓨터에서 Windows 7을 실행 하는 경우 Windows 7 서비스 팩 1을 설치 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="1e819-140">실행 중인 Windows 버전을 잘 모르거나 Windows 7 서비스 팩 1을 설치 했는지 확실 하지 않은 경우 **시작**을 클릭 하 고 **컴퓨터**를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-140">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="1e819-141">이 정보는 시스템 대화 상자에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-141">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="1e819-142">Windows 관리 프레임 워크 5.1를 설치 하려면 [WMF 5.1 설치 및 구성](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure)의 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure).</span></span>
  
<span data-ttu-id="1e819-143">컴퓨터를 다시 부팅 한 후에는 Windows PowerShell이 시작 될 수 있고 관리 자격 증명으로 응용 프로그램을 실행할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-143">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="1e819-144">실행할 작업:</span><span class="sxs-lookup"><span data-stu-id="1e819-144">To do this:</span></span>
  
1. <span data-ttu-id="1e819-145">**시작**, **모든 프로그램**, **보조 프로그램**, **Windows PowerShell**을 차례로 클릭 하 고 **windows powershell** 을 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="1e819-146">사용자 계정 컨트롤 대화 상자가 표시 되는 경우 **예** 를 클릭 하 여 관리자 자격 증명에서 PowerShell을 실행 하도록 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="1e819-147">PowerShell 콘솔이 나타나면 WinRM 서비스가 실행 중이 고 올바르게 구성 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-147">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="1e819-148">서비스가 실행 중인지 확인 하려면 PowerShell 프롬프트에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-148">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-Service winrm
```

<span data-ttu-id="1e819-149">WinRM 서비스에 대 한 정보가 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="1e819-150">서비스 상태가 "실행 중"이 아니면 다음 명령을 입력 하 고 ENTER 키를 눌러 WinRM 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```PowerShell
Start-Service winrm
```

<span data-ttu-id="1e819-151">서비스가 시작 되 면 다음 명령을 실행 하 여 WinRM이 기본 인증을 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="1e819-152">다음과 유사한 정보가 화면에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="1e819-153">기본 인증이 true로 설정 되어 있으면 PowerShell을 사용 하 여 비즈니스용 Skype Online에 연결할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1e819-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="1e819-154">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1e819-154">Related topics</span></span>
[<span data-ttu-id="1e819-155">Windows PowerShell용 컴퓨터 설정</span><span class="sxs-lookup"><span data-stu-id="1e819-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
