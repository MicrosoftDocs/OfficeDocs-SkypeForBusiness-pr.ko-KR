---
title: Microsoft Teams Rooms 유지 관리 및 작업
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 다음 세대 Skype Room Systems인 Microsoft Teams Rooms의 관리에 대해 알아보시고 이 항목을 참조하세요.
ms.openlocfilehash: 56468ad85b20b25d6e9310a20638ae35e941db73
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875148"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="bab74-103">Microsoft Teams Rooms 유지 관리 및 작업</span><span class="sxs-lookup"><span data-stu-id="bab74-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="bab74-104">다음 세대 Skype Room Systems인 Microsoft Teams Rooms의 관리에 대해 알아보시고 이 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bab74-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="bab74-105">Microsoft Teams Room은 Microsoft의 최신 회의 솔루션으로 회의실을 풍부하고 공동 작업 환경으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="bab74-106">사용자는 친숙한 Microsoft Teams 또는 비즈니스용 Skype 인터페이스를 즐길 수 있으며 IT 관리자는 쉽게 배포되고 관리되는 Windows 10 Skype 모임 앱을 감사하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="bab74-107">Microsoft Teams Room은 설치가 용이하도록 LCD 패널과 같은 기존 장비를 활용하여 Microsoft Teams 또는 비즈니스용 Skype를 회의실로 가져오기 위해 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="bab74-108">추가 구성을 통해 Azure Monitor를 사용하여 Microsoft Teams Rooms 관리 계획, [Azure Monitor를](azure-monitor-plan.md)사용하여 [Microsoft Teams Rooms](azure-monitor-deploy.md)관리 배포, Azure [Monitor를](azure-monitor-deploy.md)사용하여 Microsoft Teams Rooms 디바이스 관리에 설명된 바와 같이 Microsoft Azure Monitor를 사용하여 원격 관리가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="bab74-109">또한 사용자 지정 표시 테마 적용을 포함하는 XML 구성 파일을 사용하여 [원격으로 Microsoft Teams Rooms](xml-config-file.md)콘솔 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="bab74-110">Microsoft Teams Rooms에서 로그 수집</span><span class="sxs-lookup"><span data-stu-id="bab74-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="bab74-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="bab74-111"><a name="Logs"> </a></span></span>

<span data-ttu-id="bab74-112">로그를 수집하려면 Microsoft Teams Rooms 앱과 함께 배송하는 로그 컬렉션 스크립트를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="bab74-113">관리자 모드에서 상승된 명령 프롬프트를 시작하고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="bab74-114">로그는 c:\rigel의 ZIP 파일로 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="bab74-115">룸 디스플레이 설정 전면</span><span class="sxs-lookup"><span data-stu-id="bab74-115">Front of Room Display Settings</span></span>
<span data-ttu-id="bab74-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="bab74-116"><a name="Display"> </a></span></span>

<span data-ttu-id="bab74-117">전면 디스플레이를 확장 모드로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="bab74-118">이렇게 하면 디스플레이에서 전원을 순환할 때 콘솔 UI가 해당 디스플레이에 중복되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bab74-119">대기 모드에서 해제할 때 룸 전면 디스플레이가 활성 비디오 원본(예: MTR 콘솔)으로 자동으로 전환하려면 특정 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-119">If you desire a front of room display to automatically switch to an active video source (such as an MTR console) when the source wakes from standby mode, certain conditions must be met.</span></span> <span data-ttu-id="bab74-120">이 기능은 선택 사항이지만 기본 하드웨어가 기능을 지원하는 Microsoft Teams Rooms 소프트웨어에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-120">This feature is optional but supported by Microsoft Teams Rooms software, provided underlying hardware supports the feature.</span></span> <span data-ttu-id="bab74-121">전면 디스플레이로 사용되는 소비자 TV는 HDMI의 CEC(소비자 전자 제어) 기능을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-121">A consumer TV used as a front of room display needs to support the Consumer Electronics Control (CEC) feature of HDMI.</span></span>  <span data-ttu-id="bab74-122">선택한 도크 또는 콘솔(CEC를 지원하지 않을 수 있는 제조업체 지원 설명서 참조)에 따라 Crestron의 [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) 또는 [Extron의 Extron HD CTL 100과](https://www.extron.com/article/hdctl100ad) 같은 컨트롤러가 필요한 경우 원하는 동작을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-122">Depending on the dock or console selected (which might not support CEC, refer to manufacturer support documentation), a controller such as an [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) from Crestron or [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) from Extron may be needed to enable the desired behavior.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="bab74-123">Microsoft Teams Rooms 재설정(팩터리 복원)</span><span class="sxs-lookup"><span data-stu-id="bab74-123">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="bab74-124"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="bab74-124"><a name="Reset"> </a></span></span>

<span data-ttu-id="bab74-125">Microsoft Teams Rooms가 잘 실행되지 않는 경우 팩터리 재설정을 수행하는 것이 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-125">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="bab74-126">이렇게하려면 [Microsoft Teams Room 복구](recovery-tool.md) 도구를 사용하여 팩터리 복원 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-126">To do this, use the [Microsoft Teams Room recovery tool](recovery-tool.md) and follow the factory restore instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="bab74-127">내 파일 유지 **-** 앱 및 설정을 제거하지만 Windows 재설정 프로세스 중에 개인 파일 옵션이 선택되어 있는 경우 Microsoft Teams Rooms를 사용할 수 없는 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-127">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="bab74-128">이 *옵션을* 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-128">Do *not* use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="bab74-129">지원되는 원격 옵션</span><span class="sxs-lookup"><span data-stu-id="bab74-129">Supported Remote Options</span></span>
<span data-ttu-id="bab74-130"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="bab74-130"><a name="RemoteOptions"> </a></span></span>

<span data-ttu-id="bab74-131">다음 표에서는 가능한 원격 작업과 이를 수행하기 위해 사용할 수 있는 방법을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-131">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="bab74-132">작업대</span><span class="sxs-lookup"><span data-stu-id="bab74-132">Workgroup</span></span>|<span data-ttu-id="bab74-133">도메인에 가입되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="bab74-133">Not domain joined</span></span>|<span data-ttu-id="bab74-134">도메인에 가입된</span><span class="sxs-lookup"><span data-stu-id="bab74-134">Domain joined</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bab74-135">다시 시작</span><span class="sxs-lookup"><span data-stu-id="bab74-135">Restart</span></span>  <br/> |<span data-ttu-id="bab74-136">Teams 관리 센터</span><span class="sxs-lookup"><span data-stu-id="bab74-136">Teams admin center</span></span>  <br/> <span data-ttu-id="bab74-137">원격 데스크톱</span><span class="sxs-lookup"><span data-stu-id="bab74-137">Remote desktop</span></span>  <br/> <span data-ttu-id="bab74-138">원격 Powershell</span><span class="sxs-lookup"><span data-stu-id="bab74-138">Remote Powershell</span></span>  <br/> | <br/><span data-ttu-id="bab74-139">원격 데스크톱(추가 구성 필요)</span><span class="sxs-lookup"><span data-stu-id="bab74-139">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="bab74-140">원격 Powershell(추가 구성 필요)</span><span class="sxs-lookup"><span data-stu-id="bab74-140">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="bab74-141">구성 관리자</span><span class="sxs-lookup"><span data-stu-id="bab74-141">Configuration Manager</span></span>  <br/> |
|<span data-ttu-id="bab74-142">OS 업데이트</span><span class="sxs-lookup"><span data-stu-id="bab74-142">Update OS</span></span>  <br/> |<span data-ttu-id="bab74-143">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="bab74-143">Windows Update</span></span>  <br/> |<span data-ttu-id="bab74-144">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="bab74-144">Windows Update</span></span>  <br/> <span data-ttu-id="bab74-145">WSUS</span><span class="sxs-lookup"><span data-stu-id="bab74-145">WSUS</span></span>  <br/> |
|<span data-ttu-id="bab74-146">앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="bab74-146">App update</span></span>  <br/> |<span data-ttu-id="bab74-147">Windows 스토어</span><span class="sxs-lookup"><span data-stu-id="bab74-147">Windows Store</span></span>  <br/> |<span data-ttu-id="bab74-148">Windows 스토어</span><span class="sxs-lookup"><span data-stu-id="bab74-148">Windows Store</span></span>  <br/> <span data-ttu-id="bab74-149">구성 관리자</span><span class="sxs-lookup"><span data-stu-id="bab74-149">Configuration Manager</span></span>  <br/> |
|<span data-ttu-id="bab74-150">계정 구성</span><span class="sxs-lookup"><span data-stu-id="bab74-150">Account Config</span></span>  <br/> |<span data-ttu-id="bab74-151">Teams 관리 센터</span><span class="sxs-lookup"><span data-stu-id="bab74-151">Teams admin center</span></span>  <br/> |<span data-ttu-id="bab74-152">Teams 관리 센터</span><span class="sxs-lookup"><span data-stu-id="bab74-152">Teams admin center</span></span>  <br/> |
|<span data-ttu-id="bab74-153">액세스 로그</span><span class="sxs-lookup"><span data-stu-id="bab74-153">Access logs</span></span>  <br/> |<span data-ttu-id="bab74-154">Teams 관리 센터</span><span class="sxs-lookup"><span data-stu-id="bab74-154">Teams admin center</span></span>  <br/> |<span data-ttu-id="bab74-155">Teams 관리 센터</span><span class="sxs-lookup"><span data-stu-id="bab74-155">Teams admin center</span></span> <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="bab74-156">Microsoft Teams Rooms에 대한 그룹 정책 구성</span><span class="sxs-lookup"><span data-stu-id="bab74-156">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="bab74-157"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="bab74-157"><a name="GroupPolicy"> </a></span></span>

<span data-ttu-id="bab74-158">이 섹션에서는 Microsoft Teams Rooms가 올바르게 작동하기 위해 종속되는 시스템 설정을 다 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-158">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="bab74-159">Microsoft Teams Rooms를 도메인에 조인할 때 그룹 정책이 다음 표의 설정을 오버라이드하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-159">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="bab74-160">설정</span><span class="sxs-lookup"><span data-stu-id="bab74-160">Setting</span></span>|<span data-ttu-id="bab74-161">허용</span><span class="sxs-lookup"><span data-stu-id="bab74-161">Allows</span></span>|
|:-----|:-----|
|<span data-ttu-id="bab74-162">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="bab74-162">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="bab74-163">Microsoft Teams Rooms를 부팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-163">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="bab74-164">Power Management - \> AC에서 10분 후에 화면 끄기</span><span class="sxs-lookup"><span data-stu-id="bab74-164">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="bab74-165">Power Management - \> AC에서 시스템을 절전에 놓지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-165">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="bab74-166">Microsoft Teams Rooms에서 연결된 디스플레이를 끄고 자동으로 절전 모드 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-166">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="bab74-167">net 계정 /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="bab74-167">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="bab74-168">또는 로컬 계정에서 암호 만료를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-168">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="bab74-169">이 작업을 실패하면 결국 Skype 계정이 만료된 암호에 대해 불평하는 로그온에 실패하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-169">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="bab74-170">이로 인해 컴퓨터의 모든 로컬 계정에 영향을 미치기 때문에 이를 설정하지 못하면 상자의 관리 계정도 결국 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-170">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="bab74-171">Skype 계정이 항상 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-171">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="bab74-172">그룹 정책을 사용하여 파일 전송은 파일 항목 구성 [에서 설명됩니다.](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bab74-172">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="bab74-173">Microsoft Teams Rooms 디바이스가 Windows 10 OS의 다음 버전과 호환되는 경우 디바이스는 Windows 업데이트를 통해 자동으로 다음 버전으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-173">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="bab74-174">Microsoft Teams Rooms 디바이스는 Windows 10의 다음 릴리스로 수동으로 업그레이드하거나 WUFB(Windows Update for Business) 그룹 정책을 사용하도록 설정하여 "받을 업데이트에 대한 Windows 준비 수준을 선택"하고 GPO를 통해 "미리 보기 빌드 및 기능 업데이트가 수신될 때 선택"으로 업그레이드하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-174">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="bab74-175">이러한 그룹 정책을 사용하도록 설정된 디바이스는 Microsoft Teams Rooms 앱에서 Windows 10 OS 업데이트에 문제가 있는 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-175">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="bab74-176">PowerShell을 사용하여 원격 관리</span><span class="sxs-lookup"><span data-stu-id="bab74-176">Remote Management using PowerShell</span></span>
<span data-ttu-id="bab74-177"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="bab74-177"><a name="RemotePS"> </a></span></span>

<span data-ttu-id="bab74-178">PowerShell을 사용하여 원격으로 다음 관리 작업을 수행할 수 있습니다(스크립트 샘플에 대한 아래 표 참조).</span><span class="sxs-lookup"><span data-stu-id="bab74-178">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="bab74-179">연결된 디바이스를 얻다</span><span class="sxs-lookup"><span data-stu-id="bab74-179">Get attached devices</span></span>
- <span data-ttu-id="bab74-180">앱 상태 다운로드</span><span class="sxs-lookup"><span data-stu-id="bab74-180">Get app status</span></span>
- <span data-ttu-id="bab74-181">시스템 정보 보기</span><span class="sxs-lookup"><span data-stu-id="bab74-181">Get system info</span></span>
- <span data-ttu-id="bab74-182">시스템 재부팅</span><span class="sxs-lookup"><span data-stu-id="bab74-182">Reboot system</span></span>
- <span data-ttu-id="bab74-183">로그 검색</span><span class="sxs-lookup"><span data-stu-id="bab74-183">Retrieve logs</span></span>
- <span data-ttu-id="bab74-184">파일 전송(도메인에 가입된 Microsoft Teams Rooms 필요)</span><span class="sxs-lookup"><span data-stu-id="bab74-184">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="bab74-185">이 기능은 기본적으로 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-185">This functionality is off by default.</span></span> <span data-ttu-id="bab74-186">아래 작업을 수행하려면 Microsoft Teams Rooms 시스템에서 사용자 환경에 대해 원격 PowerShell을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-186">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="bab74-187">원격 PowerShell을 사용하도록 설정하는 방법에 대한 자세한 내용은 **[Enable-PSRemoting의](https://technet.microsoft.com/library/hh849694.aspx)** 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bab74-187">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="bab74-188">예를 들어 다음과 같이 원격 PowerShell을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-188">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="bab74-189">Microsoft Teams Rooms 디바이스에서 관리자로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-189">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="bab74-190">상승된 PowerShell 명령 프롬프트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-190">Open an elevated PowerShell command prompt.</span></span>
3. <span data-ttu-id="bab74-191">다음 명령을 입력합니다. `Enable-PSRemoting -SkipNetworkProfileCheck -Force`</span><span class="sxs-lookup"><span data-stu-id="bab74-191">Enter the following command: `Enable-PSRemoting -SkipNetworkProfileCheck -Force`</span></span>
4. <span data-ttu-id="bab74-192">로컬 보안 정책을 열고  관리자 보안 그룹을 **보안 설정** 로컬 정책 사용자 권한 할당 네트워크에 있는 이  >    >    >  **컴퓨터에 추가합니다.**</span><span class="sxs-lookup"><span data-stu-id="bab74-192">Open the Local Security Policy and add the *Administrators* security group to **Security Settings** > **Local Policies** > **User Rights Assignment** > **Access this computer from the network**.</span></span>

<span data-ttu-id="bab74-193">관리 작업을 수행하기 위해:</span><span class="sxs-lookup"><span data-stu-id="bab74-193">To perform a management operation:</span></span>
  
1. <span data-ttu-id="bab74-194">Microsoft Teams Rooms 디바이스에서 PowerShell 명령을 실행할 수 있는 권한이 있는 계정 자격 증명을 사용하여 PC에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-194">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="bab74-195">PC에서 일반 PowerShell 명령 프롬프트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-195">Open a regular PowerShell command prompt on the PC.</span></span>
3. <span data-ttu-id="bab74-196">아래 표에서 명령 텍스트를 복사하고 프롬프트에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-196">Copy the command text from the table below and paste it at the prompt.</span></span>
4. <span data-ttu-id="bab74-197">필드를  `<Device fqdn>` 환경에 적합한 FQDN 값으로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-197">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
5. <span data-ttu-id="bab74-198">마스터의 파일 이름 및 로컬 경로로 SkypeSettings.xml 구성  *\<path\>*  파일(또는 테마 이미지)으로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-198">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="bab74-199">연결된 디바이스를 사용</span><span class="sxs-lookup"><span data-stu-id="bab74-199">To Get Attached Devices</span></span>
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="bab74-200">앱 상태 다운로드</span><span class="sxs-lookup"><span data-stu-id="bab74-200">Get App Status</span></span>
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="bab74-201">시스템 정보 보기</span><span class="sxs-lookup"><span data-stu-id="bab74-201">Get System Info</span></span>
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="bab74-202">시스템 재부팅</span><span class="sxs-lookup"><span data-stu-id="bab74-202">Reboot System</span></span>
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="bab74-203">로그 검색</span><span class="sxs-lookup"><span data-stu-id="bab74-203">Retrieve Logs</span></span>
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="bab74-204">XML 구성 파일 푸시(또는 테마 그래픽)</span><span class="sxs-lookup"><span data-stu-id="bab74-204">Push an XML configuration file (or theme graphic)</span></span>
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="bab74-205">소프트웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="bab74-205">Software updates</span></span>
<span data-ttu-id="bab74-206"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="bab74-206"><a name="SWupdate"> </a></span></span>

<span data-ttu-id="bab74-207">기본적으로 Microsoft Teams Rooms는 Windows Store에 연결하여 최신 버전의 Microsoft Teams Rooms 소프트웨어를 얻게 하려고 시도하기 때문에 디바이스에 일반 인터넷 액세스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-207">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="bab74-208">지원 문제에 대해 Microsoft에 문의하기 전에 Microsoft Teams Rooms 디바이스가 최신 버전의 앱으로 로드된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-208">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="bab74-209">기본적으로 Microsoft Teams Rooms는 Windows Update에 연결하여 운영 체제 및 USB 주변 장치 펌웨어 업데이트를 검색하고, 구성된 업무 시간 외부에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-209">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="bab74-210">관리자 계정에 로그인하고 설정 앱을 실행하여 업무 시간을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-210">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="bab74-211">업데이트를 수동으로 관리하려는 경우 [Microsoft Store for Business에서](https://businessstore.microsoft.com/store) 오프라인 앱 배포를 위한 일반적인 절차를 따를 수 없는 경우, 구성 [](https://go.microsoft.com/fwlink/?linkid=851168) 관리자와 함께 사용할 수 있는 배포 키트에서 적절한 APPX 파일 및 종속성(지침에서 Microsoft Teams [Rooms 콘솔](console.md)구성)을 획득할 수 있습니다. [](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)</span><span class="sxs-lookup"><span data-stu-id="bab74-211">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with Configuration Manager.</span></span> <span data-ttu-id="bab74-212">배포 키트 릴리스는 저장소 릴리스 뒤로 까다로우기 때문에 항상 사용 가능한 최신 빌드와 일치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-212">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="bab74-213">Powershell을 사용하여 업데이트</span><span class="sxs-lookup"><span data-stu-id="bab74-213">To update using Powershell</span></span>

1. <span data-ttu-id="bab74-214">설치 [MSI에서](https://go.microsoft.com/fwlink/?linkid=851168) 디바이스가 액세스할 수 있는 공유로 패키지를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-214">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
2. <span data-ttu-id="bab74-215">Microsoft Teams Rooms 디바이스를 대상으로 하는 다음 스크립트를 실행하여 적절하게 디바이스 \<share\> 공유로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-215">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
    ```PowerShell
    Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
    ```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="bab74-216">관리자 모드 및 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="bab74-216">Admin mode and device management</span></span>
<span data-ttu-id="bab74-217"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="bab74-217"><a name="AdminMode"> </a></span></span>

<span data-ttu-id="bab74-218">개인 CA 인증서를 수동으로 설치하는 등 일부 관리 함수는 Surface Pro 디바이스를 관리자 모드로 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-218">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="bab74-219">Microsoft Teams Rooms 앱이 실행 중일 때 관리자 모드로 전환하고 다시</span><span class="sxs-lookup"><span data-stu-id="bab74-219">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="bab74-220">지속적인 통화를 중단하고 홈 화면으로 돌아온다.</span><span class="sxs-lookup"><span data-stu-id="bab74-220">Hang up any ongoing calls, and return to the home screen.</span></span>
2. <span data-ttu-id="bab74-221">기어 아이콘을 선택하고 메뉴를 시작합니다(옵션은 **설정,** **접근성** 및 디바이스 다시 **시작입니다).**</span><span class="sxs-lookup"><span data-stu-id="bab74-221">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
3. <span data-ttu-id="bab74-222">설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bab74-222">Select **Settings**.</span></span>
4. <span data-ttu-id="bab74-223">관리자 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-223">Enter the Administrator Password.</span></span> <span data-ttu-id="bab74-224">설정 화면이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-224">The Setup screen will appear.</span></span>  <span data-ttu-id="bab74-225">디바이스가 도메인에 가입되지 않은 경우 로컬 관리 계정(사용자 이름 "관리자")이 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-225">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="bab74-226">이 계정의 기본 암호는 'sfb'입니다. 가능한 한 빨리 암호를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-226">The default password for this account is 'sfb', change the password as soon as possible.</span></span> <span data-ttu-id="bab74-227">머신이 도메인에 가입된 경우 적절한 권한 있는 도메인 계정으로 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-227">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
5. <span data-ttu-id="bab74-228">왼쪽 **열에서 Windows 설정을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-228">Select **Windows Settings** in the left column.</span></span>
6. <span data-ttu-id="bab74-229">관리자 **로그인으로 이동 을 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="bab74-229">Choose **Go to Admin Sign-in**.</span></span>
7. <span data-ttu-id="bab74-230">관리자 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-230">Enter the Administrator Password.</span></span> <span data-ttu-id="bab74-231">이렇게 하면 앱을 잘 로그오프하고 Windows 로그인 화면으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-231">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
8. <span data-ttu-id="bab74-232">관리 자격 증명을 사용하여 데스크톱에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-232">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="bab74-233">디바이스를 관리하는 데 필요한 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-233">You'll have the necessary privileges to manage the device.</span></span>
9. <span data-ttu-id="bab74-234">필요한 관리 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-234">Perform the necessary administrative tasks.</span></span>
10. <span data-ttu-id="bab74-235">관리자 계정에서 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-235">Sign out from the Admin account.</span></span>
11. <span data-ttu-id="bab74-236">화면의 왼쪽에 있는 사용자 계정 아이콘을 선택한 다음 Skype를 선택하여 Microsoft Teams Rooms로 **돌아온다.**</span><span class="sxs-lookup"><span data-stu-id="bab74-236">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="bab74-237">Skype **사용자가** 나열되지 않은 경우 다른  사용자를 선택하고 **.\skype를** 사용자 이름으로 입력하고 로그인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-237">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="bab74-238">이제 콘솔이 정상 작동 모드로 돌아갑니다. 다음 절차에서는 키보드가 아직 연결되지 않은 경우 디바이스에 키보드를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-238">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="bab74-239">Microsoft Teams Rooms 앱이 충돌할 때 관리자 모드로 전환</span><span class="sxs-lookup"><span data-stu-id="bab74-239">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="bab74-240">Windows 키를 5번 연속으로 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-240">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="bab74-241">이렇게 하면 Windows 로그온 화면이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-241">This will bring you to the Windows logon screen.</span></span> 
2. <span data-ttu-id="bab74-242">관리 자격 증명을 사용하여 데스크톱에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-242">Log in to the desktop with your administrative credentials.</span></span>
3. <span data-ttu-id="bab74-243">필요한 관리 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-243">Perform the necessary administrative tasks.</span></span>
4. <span data-ttu-id="bab74-244">완료되면 컴퓨터를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-244">Restart the machine when you're finished.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bab74-245">이 메서드는 Skype 사용자를 로그오프하거나 앱을 우호적으로 종료하지 않지만 앱이 응답하지 않는 경우 다른 메서드를 사용할 수 없는 경우 이 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-245">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 

   <span data-ttu-id="bab74-246">콘솔이 정상 작동 모드로 다시 시작되고 Microsoft Teams Rooms 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-246">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="bab74-247">이 절차를 수행할 수 있도록 연결된 경우 키보드를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-247">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="bab74-248">문제 해결 팁</span><span class="sxs-lookup"><span data-stu-id="bab74-248">Troubleshooting tips</span></span>
   <span data-ttu-id="bab74-249"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="bab74-249"><a name="TS"> </a></span></span>

- <span data-ttu-id="bab74-250">도메인 경계(예: 두 회사 간)를 통해 전송될 때 모임 초대가 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-250">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="bab74-251">이러한 경우 IT 관리자는 외부 사용자가 모임을 예약할 수 있도록 허용할지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-251">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
- <span data-ttu-id="bab74-252">Microsoft Teams Rooms는 Exchange 2010을 통해 Exchange AutoDiscover 리디렉션을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-252">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
- <span data-ttu-id="bab74-253">일반적으로 IT 관리자는 사용하지 않는 오디오 엔드포인트를 사용하지 않도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-253">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
- <span data-ttu-id="bab74-254">미러 이미지가 룸 미리 보기에 표시되는 경우 IT 관리자는 카메라 전원을 순환하거나 카메라 원격 제어를 사용하여 이미지 방향을 뒤집어 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-254">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
- <span data-ttu-id="bab74-255">콘솔 터치 스크린 액세스의 손실이 발생하는 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-255">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="bab74-256">이러한 경우 Microsoft Teams Rooms 시스템을 다시 시작하여 문제가 해결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-256">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
- <span data-ttu-id="bab74-257">유선 인제스트를 통해 PC를 콘솔에 연결할 때 로컬 오디오 손실이 발생하는 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-257">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="bab74-258">이러한 경우 PC를 다시 시작하면 로컬 오디오 재생 문제가 해결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bab74-258">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
