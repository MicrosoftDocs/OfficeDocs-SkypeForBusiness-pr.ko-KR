---
title: 비즈니스용 Skype 서버에 대 한 사용 중 옵션 설치 및 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: 비즈니스용 Skype 서버에서 약속 있음 옵션을 설치 하 고 구성 하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: 45779af0410dcadd1b5fe8e3988905e88acd9213
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002518"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a><span data-ttu-id="45463-103">비즈니스용 Skype 서버에 대 한 사용 중 옵션 설치 및 구성</span><span class="sxs-lookup"><span data-stu-id="45463-103">Install and configure Busy Options for Skype for Business Server</span></span>

<span data-ttu-id="45463-104">비즈니스용 Skype 서버에서 약속 있음 옵션을 설치 하 고 구성 하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="45463-104">Read about how to install and configure Busy Options in Skype for Business Server.</span></span>

<span data-ttu-id="45463-105">약속 있음 옵션은 사용자가 이미 통화 중이거나 회의에 있거나 통화 대기 상태에 있을 때 수신 통화가 처리 되는 방식을 구성할 수 있는 7 월 2016 누적 업데이트에 도입 된 새로운 음성 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="45463-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="45463-106">약속 있음/없음 신호를 사용 하 여 신규 또는 수신 전화를 거부 하거나 음성 메일로 착신 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45463-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span>

<span data-ttu-id="45463-107">조직에 대 한 약속 있음 옵션을 사용 하는 경우 엔터프라이즈의 모든 사용자, enterprise Voice 사용자가 아닌 경우에는 다음 구성 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45463-107">If Busy Options is enabled for the organization, all users at the Enterprise, both Enterprise Voice and non-Enterprise Voice users, can use the following configuration options:</span></span>

- <span data-ttu-id="45463-108">다른 용무 중입니다-사용자가 통화 중인 경우 새로운 수신 통화가 통화 중 이라는 신호를 사용 하 여 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45463-108">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>

- <span data-ttu-id="45463-109">사용자가 바쁜 경우 새로운 수신 통화가 음성 메일로 착신 전환 되는 동안 보이스 메일을 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="45463-109">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>

<span data-ttu-id="45463-110">약속 있음/없음 옵션이 구성 되는 방식에 관계 없이, 통화 또는 컨퍼런스 사용자 또는 통화 중 통화가 포함 된 경우에는 새 통화 또는 회의가 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45463-110">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span>

<span data-ttu-id="45463-111">다른 용무 중 옵션 기능에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 약속 있음 옵션 계획](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45463-111">For more information about the Busy Options feature, see [Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md).</span></span>

## <a name="install"></a><span data-ttu-id="45463-112">설치</span><span class="sxs-lookup"><span data-stu-id="45463-112">Install</span></span>

<span data-ttu-id="45463-113">최신 버전의 비즈니스용 Skype Server가 설치 되어 있고 최신 패치를 설치 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-113">Make sure you have the latest version of Skype for Business Server installed and that you have installed the most recent patch.</span></span> <span data-ttu-id="45463-114">이렇게 하려면 먼저 모든 서비스를 중지 하 고 다음과 같이 비즈니스용 Skype 서버 업데이트 설치 관리자를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-114">To do this, first stop all services, and then run the Skype for Business Server update installer as follows:</span></span>

1. <span data-ttu-id="45463-115">CsWindowsService 명령 중지를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-115">Run the Stop-CsWindowsService command.</span></span>

2. <span data-ttu-id="45463-116">풀의 각 프런트 엔드 서버에서 SkypeServerUpdateInstaller 설치 관리자를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-116">Run the SkypeServerUpdateInstaller.exe installer on each Front End server in a pool.</span></span>

3. <span data-ttu-id="45463-117">SBS에서 장애 조치 (failover)에 대 한 지원을 확인 하려면 각 SBS (Survivable Branch Server)에서 SkypeServerUpdateInstaller 설치 관리자를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-117">Run the SkypeServerUpdateInstaller.exe installer on each Survivable Branch Server (SBS), if you want to ensure support for failover on SBS.</span></span>

<span data-ttu-id="45463-118">설치 관리자가 최신 버전의 사용 옵션 응용 프로그램을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-118">The installer will deploy the latest version of the Busy Options application.</span></span> <span data-ttu-id="45463-119">그러나 응용 프로그램은 기본적으로 활성화 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45463-119">However, the application is not enabled by default.</span></span> <span data-ttu-id="45463-120">응용 프로그램을 사용 하도록 설정 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-120">To enable the application, perform the following steps:</span></span>

1. <span data-ttu-id="45463-121">다음 예제에 표시 된 대로 전역 작업을 사용 하도록 [설정 하려면 CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-121">Run the [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet to globally enable Busy Options as shown in the following example:</span></span>

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. <span data-ttu-id="45463-122">다음으로, 사이트에 음성 정책이 있는 경우 다음과 같이 음성 정책에 대 한 사용 옵션을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-122">Next, if the site has a voice policy is place, you must enable Busy Options for the voice policy as follows:</span></span>

    <span data-ttu-id="45463-123">먼저 [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) 를 실행 하 여 사이트의 이름을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-123">First, run [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) to retrieve the name of the site:</span></span>

   ```powershell
   Get-CsSite
   ```

    <span data-ttu-id="45463-124">다음과 같이 사이트의 음성 정책을 검색 하려면 Get-CsSite에서 Id 값 (예: Site: Redmond1)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-124">Use the Identity value (for example: Site:Redmond1) retrieved from Get-CsSite to retrieve the voice policy of the site as follows:</span></span>

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    <span data-ttu-id="45463-125">사이트에 대 한 음성 정책이 있는 경우 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-125">If a voice policy exists for the site, run the following command:</span></span>

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. <span data-ttu-id="45463-126">다음 예제와 같이 [새 CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet을 실행 하 여 사용 중 옵션을 서버 응용 프로그램 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-126">Next, run the [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet to add Busy Options to the list of server applications as shown in the following example:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > <span data-ttu-id="45463-127">% FQDN%을 특정 풀의 정규화 된 도메인 이름으로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-127">You must replace %FQDN% with the fully-qualified domain name of a specific pool.</span></span>

4. <span data-ttu-id="45463-128">다음 예제에 표시 된 대로 [업데이트-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet을 실행 하 여 Busy 옵션 cmdlet에 대 한 RBAC (역할 기반 액세스 제어) 역할을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-128">Next, run the [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet to update the Role-based access control (RBAC) roles for the Busy Options cmdlets as shown in the following example:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

5. <span data-ttu-id="45463-129">마지막으로, 다른 용무 중 옵션이 설치 되어 있고 사용 하도록 설정 된 모든 풀의 모든 프런트 엔드 서버에서 비즈니스용 Skype 서버 Windows 서비스를 시작 합니다 ( [시작-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) ) 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-129">Finally, start the Skype for Business Server Windows services on all the Front End servers in all the pools where Busy Options was installed and enabled by running the [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) command:</span></span>

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a><span data-ttu-id="45463-130">구성할</span><span class="sxs-lookup"><span data-stu-id="45463-130">Configure</span></span>

<span data-ttu-id="45463-131">다른 용무 중 옵션을 구성 하려면 [CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-131">To configure Busy Options, use the [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet.</span></span>

<span data-ttu-id="45463-132">예를 들어 다음 명령은 사용자 ": 진구 Myer"에 대 한 사용 중 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-132">For example, the following command configures busy options for the user "Ken Myer".</span></span> <span data-ttu-id="45463-133">이 구성에서 ": 진구 Myer"로 거는 호출은 이미 통화 중일 때 통화 중 신호를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-133">In this configuration, any call to "Ken Myer" will return a busy signal when he is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

<span data-ttu-id="45463-134">다음 예제에서 명령은 사용자 "Chrystal Velasquez"에 대 한 사용 중 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-134">In the next example, the command configures busy options for the user "Chrystal Velasquez".</span></span> <span data-ttu-id="45463-135">이 구성에서 "Chrystal Velasquez"에 대 한 새로운 수신 전화는 이미 통화 중에 음성 메일로 착신 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45463-135">In this configuration, new incoming calls to "Chrystal Velasquez" will be forwarded to voice mail when she is already in a call:</span></span>

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

<span data-ttu-id="45463-136">[CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet을 사용 하 여 다른 용무 중 옵션에 대 한 구성 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45463-136">You can retrieve configuration information about Busy Options by using the [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet.</span></span> <span data-ttu-id="45463-137">다음 예에서는 "KenMyer@Contoso.com"에 대 한 사용 중 옵션 설정을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-137">The following example returns the Busy Options setting for "KenMyer@Contoso.com":</span></span>

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

<span data-ttu-id="45463-138">[CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet을 사용 하 여 약속 있음/없음 옵션을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45463-138">You can remove Busy Options by using the [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet.</span></span> <span data-ttu-id="45463-139">다음 명령은 ": 진구 Myer"의 약속 있음/없음 옵션을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-139">The following command removes Busy Options for "Ken Myer":</span></span>

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

<span data-ttu-id="45463-140">다른 용무 중 옵션을 구성 하는 데 사용 하는 cmdlet에 대 한 자세한 내용은 [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)및 [Remove](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)에 대 한 기술 참조 콘텐츠를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="45463-140">For detailed information about the cmdlets you use to configure Busy Options, see the technical reference content for [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx), [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx), and [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx).</span></span>

## <a name="enable-logging"></a><span data-ttu-id="45463-141">로깅 사용</span><span class="sxs-lookup"><span data-stu-id="45463-141">Enable logging</span></span>

<span data-ttu-id="45463-142">중앙 로깅 서비스를 사용 하 여 통화 중 옵션의 로깅을 사용 하도록 설정 하려면 다음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-142">To enable logging for Busy Options by using the Centralized Logging Service, specify the following:</span></span>

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a><span data-ttu-id="45463-143">확인 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="45463-143">Verify and troubleshoot</span></span>

<span data-ttu-id="45463-144">다른 용무 중 옵션을 설치한 후에는 [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet을 사용 하 여 서버 응용 프로그램 목록을 검색 하 여 성공적으로 설치 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45463-144">After installing Busy Options, you can verify that the installation was successful by using the [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet to retrieve the list of server applications.</span></span> <span data-ttu-id="45463-145">약속 있음/없음 옵션이 제대로 설치 되어 있는 경우 cmdlet의 출력에는 사용 중인 옵션 구성이 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45463-145">If Busy Options is installed properly, the output of the cmdlet should show the Busy Options configuration as follows:</span></span>

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

<span data-ttu-id="45463-146">Windows 이벤트 뷰어를 사용 하 여 다른 용무 중 옵션이 성공적으로 설치 되었는지 확인 하 고 비즈니스용 Skype 서버가 사용 중 옵션을 성공적으로 로드 했는지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45463-146">You can also use Windows Event Viewer to verify that the Busy Options installation was successful and that Skype for Business Server successfully loaded Busy Options.</span></span> <span data-ttu-id="45463-147">약속 있음 옵션을 확인 하려면 **이벤트 뷰어-\> 응용 프로그램 및 서비스 로그\> -Skype (또는 Lync) 서버** 를 열고 이벤트 ID = 30253를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="45463-147">To verify Busy Options, open **Event Viewer -\> Application and Services Logs -\> Skype (or Lync) Server** and search for Event ID = 30253.</span></span>
