---
title: 비즈니스용 Skype 서버의 다른 업무용 옵션 설치 및 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: 비즈니스용 Skype 서버에서 다른용 Skype 옵션을 설치 및 구성하는 방법을 읽어 보십시오.
ms.openlocfilehash: 04690e9f2c7fbf16b67432526fe5c8fd6e5b95af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106314"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="9019d-103">비즈니스용 Skype 서버의 다른 업무용 옵션 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="9019d-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="9019d-104">비즈니스용 Skype 서버에서 다른용 Skype 옵션을 설치 및 구성하는 방법을 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="9019d-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="9019d-105">다른 사용자 옵션 2016년 7월 누적 업데이트에 도입된 새로운 음성 정책으로, 사용자가 이미 통화 또는 회의에 참석 중이거나 통화를 보류한 경우 수신 전화가 처리되는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="9019d-106">통화 중 신호로 새 전화나 수신 전화를 거부하거나 음성 메일로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="9019d-107">조직에서 다른 사용자 옵션을 사용하도록 설정한 경우 엔터프라이즈의 모든 사용자는 Enterprise Voice 및 비영리 Enterprise Voice 다음 구성 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="9019d-108">다른 사용 중 - 사용자가 통화 중일 때 새 수신 전화가 통화 중 신호로 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="9019d-109">통화 중 음성 메일 - 사용자가 통화 중일 때 새 수신 전화가 음성 메일로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="9019d-110">통화 중 옵션의 구성 방식에 관계없이 통화 또는 회의의 사용자 또는 통화가 보류된 사용자는 새 통화 또는 회의를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="9019d-111">다른 업무용 옵션 기능에 대한 자세한 내용은 [Plan for Busy Options for Skype for Business Server을 참조하십시오.](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)</span><span class="sxs-lookup"><span data-stu-id="9019d-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="9019d-112">설치</span><span class="sxs-lookup"><span data-stu-id="9019d-112">Install</span></span>

<span data-ttu-id="9019d-113">최신 버전의 비즈니스용 Skype 서버가 설치되어 있으며 최신 패치를 설치한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="9019d-114">이렇게하려면 먼저 모든 서비스를 중지한 다음 다음과 같이 비즈니스용 Skype 서버 업데이트 설치 관리자를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="9019d-115">명령 Stop-CsWindowsService 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="9019d-116">풀의 SkypeServerUpdateInstaller.exe 프런트 엔드 서버에서 설치 관리자를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="9019d-117">SBS의 장애 조치(failover)를 지원하려면 SkypeServerUpdateInstaller.exe SBS(Survivable Branch Server)에서 설치 관리자를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="9019d-118">설치 프로그램은 최신 버전의 Busy Options 응용 프로그램을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="9019d-119">그러나 응용 프로그램은 기본적으로 사용하도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="9019d-120">응용 프로그램을 사용하도록 설정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="9019d-121">[Set-CsVoicePolicy](/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet을 실행하여 다음 예와 같이 다른용 옵션을 전역으로 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-121">Run the [Set-CsVoicePolicy](/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="9019d-122">다음으로 사이트에 음성 정책이 있는 경우 다음과 같이 음성 정책에 대해 다른용 옵션을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="9019d-123">먼저 [Get-CsSite를](/powershell/module/skype/get-cssite?view=skype-ps) 실행하여 사이트 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-123">First, run [Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="9019d-124">사이트로부터 검색된 Identity 값(예: site:Redmond1Get-CsSite을 사용하여 사이트의 음성 정책을 다음과 같이 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="9019d-125">사이트에 음성 정책이 있는 경우 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="9019d-126">다음으로, [New-CsServerApplication](/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet을 실행하여 다음 예와 같이 서버 응용 프로그램 목록에 다른 사용자 옵션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-126">Next, run the [New-CsServerApplication](/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="9019d-127">%FQDN%을 특정 풀의 정식 도메인 이름으로 바꾸야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="9019d-128">다음으로, [Update-CsAdminRole](/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet을 실행하여 다음 예와 같이 다른 사용 중 옵션 cmdlet에 대한 RBAC(역할 기반 액세스 제어) 역할을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-128">Next, run the [Update-CsAdminRole](/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="9019d-129">마지막으로 [Start-CsWindowsService](/powershell/module/skype/start-cswindowsservice?view=skype-ps) 명령을 실행하여 다른용 옵션이 설치되고 사용하도록 설정된 모든 풀의 모든 프런트 엔드 서버에서 비즈니스용 Skype 서버 Windows 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="9019d-130">구성</span><span class="sxs-lookup"><span data-stu-id="9019d-130">Configure</span></span>

<span data-ttu-id="9019d-131">사용 중 옵션을 구성하기 위해 [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9019d-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="9019d-132">예를 들어 다음 명령은 사용자 "Ken Myer"에 대한 사용 중 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="9019d-133">이 구성에서 "Ken Myer"를 호출하면 이미 통화 중일 때 통화 중 신호가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="9019d-134">다음 예제에서는 "Chrystal Velasquez" 사용자에 대한 사용 중 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="9019d-135">이 구성에서는 "Chrystal Velasquez"에 대한 새 수신 전화가 이미 통화 중일 때 음성 메일로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="9019d-136">[Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet을 사용하여 다른 작업 중 옵션에 대한 구성 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="9019d-137">다음은 "KenMyer@Contoso.com"를 반환하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="9019d-138">[Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet을 사용하여 다른용 옵션을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="9019d-139">다음 명령은 "Ken Myer"에 대한 다른용 옵션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="9019d-140">다른 사용자 옵션을 구성하는 데 사용하는 cmdlet에 대한 자세한 내용은 [Set-CsBusyOptions, Get-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)및 [Remove-CsBusyOptions에](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)대한 기술 참조 콘텐츠를 참조하십시오. [](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)</span><span class="sxs-lookup"><span data-stu-id="9019d-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="9019d-141">로깅 사용</span><span class="sxs-lookup"><span data-stu-id="9019d-141">Enable logging</span></span>

<span data-ttu-id="9019d-142">중앙 로깅 서비스를 사용하여 다른 작업 중 옵션에 대해 로깅을 사용하도록 설정하려면 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="9019d-143">확인 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9019d-143">Verify and troubleshoot</span></span>

<span data-ttu-id="9019d-144">다른 작업 중 옵션을 설치한 후 [Get-CsServerApplication](/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet을 사용하여 서버 응용 프로그램 목록을 검색하여 설치가 성공적으로 완료된지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="9019d-145">다른 작업 중 옵션이 제대로 설치되어 있는 경우 cmdlet 출력에 다음과 같이 다른 작업 중 옵션 구성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="9019d-146">Windows 이벤트 뷰어를 사용하여 사용 중 옵션 설치가 성공적이고 비즈니스용 Skype 서버가 통화 중 옵션을 성공적으로 로드하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="9019d-147">사용 중 옵션을 확인하려면 이벤트 뷰어 - 응용 프로그램 및 서비스 로그 **\> - \> Skype(또는 Lync) 서버를 열고** 이벤트 ID = 30253을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="9019d-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>