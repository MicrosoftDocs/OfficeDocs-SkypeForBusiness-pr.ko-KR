---
title: Microsoft 팀 회의실 유지 관리 및 운영
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: 이 항목에서는 차세대 Skype 대화방 시스템인 Microsoft 팀 회의실 관리에 대해 자세히 알아보세요.
ms.openlocfilehash: 0eb68e74368a9ae4463ab5f6a9721a844b151152
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628664"
---
# <a name="microsoft-teams-rooms-maintenance-and-operations"></a><span data-ttu-id="3b52a-103">Microsoft 팀 회의실 유지 관리 및 운영</span><span class="sxs-lookup"><span data-stu-id="3b52a-103">Microsoft Teams Rooms maintenance and operations</span></span> 
 
<span data-ttu-id="3b52a-104">이 항목에서는 차세대 Skype 대화방 시스템인 Microsoft 팀 회의실 관리에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3b52a-104">Read this topic to learn about management of Microsoft Teams Rooms, the next generation of Skype Room Systems.</span></span>
  
<span data-ttu-id="3b52a-105">Microsoft 팀 대화방은 회의실을 다양 한 공동 작업 환경으로 변환 하도록 설계 된 Microsoft의 최신 회의 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-105">Microsoft Teams Rooms is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative experience.</span></span> <span data-ttu-id="3b52a-106">사용자는 친숙 한 Microsoft 팀 또는 비즈니스용 Skype 인터페이스를 즐길 수 있으며 IT 관리자가 Windows 10 Skype 모임 앱을 쉽게 배포 하 고 관리 하는 데 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-106">Users will enjoy its familiar Microsoft Teams or Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="3b52a-107">Microsoft 팀 공간은 설치 하기 쉽도록 LCD 패널과 같은 기존 장비를 이용 하 여 Microsoft 팀 또는 비즈니스용 Skype를 회의실에 제공할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-107">Microsoft Teams Rooms is designed to leverage existing equipment like LCD panels for ease of installation to bring Microsoft Teams or Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="3b52a-108">추가 구성을 사용 하는 경우 azure monitor를 사용 하 여 [Microsoft 팀 공간 관리 계획](azure-monitor-plan.md), Azure [모니터로 microsoft 팀 대화방 관리 배포](azure-monitor-deploy.md), [azure Monitor를 사용 하 여 microsoft 팀 회의실 장치 관리](azure-monitor-deploy.md)에 설명 된 microsoft Azure Monitor를 사용 하 여 원격 관리를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-108">With additional configuration, remote management is possible using Microsoft Azure Monitor as described in [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md), [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-deploy.md).</span></span> <span data-ttu-id="3b52a-109">사용자 지정 표시 테마 적용을 포함 하 여 [XML 구성 파일을 사용 하 여 원격으로 Microsoft 팀 공간 콘솔 설정을 관리할](xml-config-file.md)수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-109">You may also [Manage Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md), which includes applying a Custom display theme.</span></span> 
  
## <a name="collecting-logs-on-microsoft-teams-rooms"></a><span data-ttu-id="3b52a-110">Microsoft 팀 방에 대 한 로그 수집</span><span class="sxs-lookup"><span data-stu-id="3b52a-110">Collecting logs on Microsoft Teams Rooms</span></span>
<span data-ttu-id="3b52a-111"><a name="Logs"> </a></span><span class="sxs-lookup"><span data-stu-id="3b52a-111"><a name="Logs"> </a></span></span>

<span data-ttu-id="3b52a-112">로그를 수집 하려면 Microsoft 팀 대화방 앱과 함께 제공 되는 로그 수집 스크립트를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-112">To collect logs, you must invoke the log collection script that ships with the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="3b52a-113">관리 모드에서 관리자 권한 명령 프롬프트를 시작 하 고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-113">In Admin mode, start an elevated command prompt, and issue the following command:</span></span>
  
```PowerShell
powershell -ExecutionPolicy unrestricted c:\rigel\x64\scripts\provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
```

<span data-ttu-id="3b52a-114">로그는 c:\rigel.에서 ZIP 파일로 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-114">The logs will be output as a ZIP file in c:\rigel.</span></span>
  
## <a name="front-of-room-display-settings"></a><span data-ttu-id="3b52a-115">회의실 디스플레이 설정 전면</span><span class="sxs-lookup"><span data-stu-id="3b52a-115">Front of Room Display Settings</span></span>
<span data-ttu-id="3b52a-116"><a name="Display"> </a></span><span class="sxs-lookup"><span data-stu-id="3b52a-116"><a name="Display"> </a></span></span>

<span data-ttu-id="3b52a-117">확장 모드로 방 디스플레이를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-117">Configure the Front of Room display to Extended mode.</span></span> <span data-ttu-id="3b52a-118">이렇게 하면 디스플레이 전원을 켤 때 콘솔 UI가 해당 디스플레이에 복제 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-118">Doing so will ensure that the console UI is not duplicated on that display when you cycle power on the display.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b52a-119">원본에서 대기 모드를 해제할 때 자동으로 활성 비디오 원본 (예: MTR 콘솔)으로 전환 하려면 특정 조건이 충족 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-119">If you desire a front of room display to automatically switch to an active video source (such as an MTR console) when the source wakes from standby mode, certain conditions must be met.</span></span> <span data-ttu-id="3b52a-120">이 기능은 선택 사항 이지만 Microsoft 팀 공간 소프트웨어에서 지원 되며, 기본 하드웨어에서 기능을 지 원하는 경우 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-120">This feature is optional but supported by Microsoft Teams Rooms software, provided underlying hardware supports the feature.</span></span> <span data-ttu-id="3b52a-121">채팅방 표시로 사용 되는 소비자 TV는 HDMI의 CEC (소비자 전자 컨트롤) 기능을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-121">A consumer TV used as a front of room display needs to support the Consumer Electronics Control (CEC) feature of HDMI.</span></span>  <span data-ttu-id="3b52a-122">선택 된 dock 또는 console (CEC를 지원 하지 않을 수 있음, 제조업체 지원 문서 참조)에 따라, 원하는 동작을 사용 하도록 설정 하려면 hd [-RX-201-C-](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) [100](https://www.extron.com/article/hdctl100ad) E와 같은 컨트롤러가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-122">Depending on the dock or console selected (which might not support CEC, refer to manufacturer support documentation), a controller such as an [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) from Crestron or [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) from Extron may be needed to enable the desired behavior.</span></span> 
  
## <a name="microsoft-teams-rooms-reset-factory-restore"></a><span data-ttu-id="3b52a-123">Microsoft 팀 대화방 재설정 (출하 시 복원)</span><span class="sxs-lookup"><span data-stu-id="3b52a-123">Microsoft Teams Rooms Reset (Factory Restore)</span></span>
<span data-ttu-id="3b52a-124"><a name="Reset"> </a></span><span class="sxs-lookup"><span data-stu-id="3b52a-124"><a name="Reset"> </a></span></span>

<span data-ttu-id="3b52a-125">Microsoft 팀 채팅방이 제대로 실행 되 고 있지 않은 경우 공장 초기화를 수행 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-125">If Microsoft Teams Rooms isn't running well, performing a factory reset might help.</span></span> <span data-ttu-id="3b52a-126">이렇게 하려면 [Microsoft 팀 대화방 복구 도구](recovery-tool.md) 를 사용 하 여 공장 복원 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="3b52a-126">To do this, use the [Microsoft Teams Room recovery tool](recovery-tool.md) and follow the factory restore instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="3b52a-127">Microsoft 팀 대화방을 사용할 수 없게 되는 알려진 문제가 있습니다. **내 파일 유지-앱과 설정을 제거 하지만,** Windows 재설정 프로세스 중에 개인 파일 옵션 유지 옵션이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-127">There is a known issue where the Microsoft Teams Rooms can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="3b52a-128">이 옵션을 사용 *하지* 마세요.</span><span class="sxs-lookup"><span data-stu-id="3b52a-128">Do *not* use this option.</span></span>
  
## <a name="supported-remote-options"></a><span data-ttu-id="3b52a-129">지원 되는 원격 옵션</span><span class="sxs-lookup"><span data-stu-id="3b52a-129">Supported Remote Options</span></span>
<span data-ttu-id="3b52a-130"><a name="RemoteOptions"> </a></span><span class="sxs-lookup"><span data-stu-id="3b52a-130"><a name="RemoteOptions"> </a></span></span>

<span data-ttu-id="3b52a-131">다음 표에서는 가능한 원격 작업 및이를 수행 하는 데 사용할 수 있는 메서드를 요약 하 여 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-131">The following table summarizes the possible remote operations and the methods you can use to accomplish them.</span></span>
  

|<span data-ttu-id="3b52a-132">작업 그룹</span><span class="sxs-lookup"><span data-stu-id="3b52a-132">Workgroup</span></span>|<span data-ttu-id="3b52a-133">도메인에 가입 되어 있지 않음</span><span class="sxs-lookup"><span data-stu-id="3b52a-133">Not domain joined</span></span>|<span data-ttu-id="3b52a-134">도메인 가입 됨</span><span class="sxs-lookup"><span data-stu-id="3b52a-134">Domain joined</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b52a-135">했다가</span><span class="sxs-lookup"><span data-stu-id="3b52a-135">Restart</span></span>  <br/> |<span data-ttu-id="3b52a-136">원격 데스크톱</span><span class="sxs-lookup"><span data-stu-id="3b52a-136">Remote desktop</span></span>  <br/> <span data-ttu-id="3b52a-137">원격 Powershell</span><span class="sxs-lookup"><span data-stu-id="3b52a-137">Remote Powershell</span></span>  <br/> |<span data-ttu-id="3b52a-138">원격 데스크톱 (추가 구성 필요)</span><span class="sxs-lookup"><span data-stu-id="3b52a-138">Remote desktop (requires further configuration)</span></span>  <br/> <span data-ttu-id="3b52a-139">원격 Powershell (추가 구성 필요)</span><span class="sxs-lookup"><span data-stu-id="3b52a-139">Remote Powershell (requires further configuration)</span></span>  <br/> <span data-ttu-id="3b52a-140">구성 관리자</span><span class="sxs-lookup"><span data-stu-id="3b52a-140">Configuration Manager</span></span>  <br/> |
|<span data-ttu-id="3b52a-141">OS 업데이트</span><span class="sxs-lookup"><span data-stu-id="3b52a-141">Update OS</span></span>  <br/> |<span data-ttu-id="3b52a-142">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="3b52a-142">Windows Update</span></span>  <br/> |<span data-ttu-id="3b52a-143">Windows 업데이트</span><span class="sxs-lookup"><span data-stu-id="3b52a-143">Windows Update</span></span>  <br/> <span data-ttu-id="3b52a-144">WSUS</span><span class="sxs-lookup"><span data-stu-id="3b52a-144">WSUS</span></span>  <br/> |
|<span data-ttu-id="3b52a-145">앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="3b52a-145">App update</span></span>  <br/> |<span data-ttu-id="3b52a-146">Windows 스토어</span><span class="sxs-lookup"><span data-stu-id="3b52a-146">Windows Store</span></span>  <br/> |<span data-ttu-id="3b52a-147">Windows 스토어</span><span class="sxs-lookup"><span data-stu-id="3b52a-147">Windows Store</span></span>  <br/> <span data-ttu-id="3b52a-148">구성 관리자</span><span class="sxs-lookup"><span data-stu-id="3b52a-148">Configuration Manager</span></span>  <br/> |
|<span data-ttu-id="3b52a-149">Skype 계정 구성</span><span class="sxs-lookup"><span data-stu-id="3b52a-149">Skype Account Config</span></span>  <br/> |<span data-ttu-id="3b52a-150">현재 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="3b52a-150">Not currently supported</span></span>  <br/> |<span data-ttu-id="3b52a-151">현재 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="3b52a-151">Not currently supported</span></span>  <br/> |
|<span data-ttu-id="3b52a-152">Access 로그</span><span class="sxs-lookup"><span data-stu-id="3b52a-152">Access logs</span></span>  <br/> |<span data-ttu-id="3b52a-153">현재 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="3b52a-153">Not currently supported</span></span>  <br/> |<span data-ttu-id="3b52a-154">현재 지원 되지 않음</span><span class="sxs-lookup"><span data-stu-id="3b52a-154">Not currently supported</span></span>  <br/> |
   
## <a name="configuring-group-policy-for-microsoft-teams-rooms"></a><span data-ttu-id="3b52a-155">Microsoft 팀 대화방에 대 한 그룹 정책 구성</span><span class="sxs-lookup"><span data-stu-id="3b52a-155">Configuring Group Policy for Microsoft Teams Rooms</span></span>
<span data-ttu-id="3b52a-156"><a name="GroupPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="3b52a-156"><a name="GroupPolicy"> </a></span></span>

<span data-ttu-id="3b52a-157">이 섹션에서는 Microsoft 팀 대화방에서 제대로 작동 하는 데 의존 하는 시스템 설정을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-157">This section covers system settings that Microsoft Teams Rooms depends on to function properly.</span></span> <span data-ttu-id="3b52a-158">Microsoft 팀 대화방을 도메인에 참가 하는 경우 그룹 정책이 다음 표의 설정을 재정의 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-158">When joining Microsoft Teams Rooms to a domain, ensure that your group policy doesn't override the settings in the following table.</span></span>
  

|<span data-ttu-id="3b52a-159">설정</span><span class="sxs-lookup"><span data-stu-id="3b52a-159">Setting</span></span>|<span data-ttu-id="3b52a-160">가능</span><span class="sxs-lookup"><span data-stu-id="3b52a-160">Allows</span></span>|
|:-----|:-----|
|<span data-ttu-id="3b52a-161">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span><span class="sxs-lookup"><span data-stu-id="3b52a-161">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (REG_SZ) 1</span></span>  <br/> |<span data-ttu-id="3b52a-162">Microsoft 팀 회의실을 부팅할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="3b52a-162">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="3b52a-163">전원 관리-\> AC, 10 분 후 화면 끄기</span><span class="sxs-lookup"><span data-stu-id="3b52a-163">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="3b52a-164">전원 관리-\> AC, 시스템을 절전 모드로 전환 안 함</span><span class="sxs-lookup"><span data-stu-id="3b52a-164">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="3b52a-165">Microsoft 팀 대화방에서 연결 된 디스플레이를 끄고 자동으로 절전 모드 해제 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="3b52a-165">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="3b52a-166">네트 계정/maxpwage: 무제한</span><span class="sxs-lookup"><span data-stu-id="3b52a-166">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="3b52a-167">또는 동등한 방법으로 로컬 계정에서 암호 만료를 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-167">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="3b52a-168">이 작업을 수행 하지 않으면 결국 Skype 계정에 만료 된 비밀 번호에 대 한 로그온 complaining 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-168">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="3b52a-169">이로 인해 컴퓨터의 모든 로컬 계정에 영향을 줄 수 있으므로이를 설정 하지 않으면 상자의 관리 계정도 결국 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-169">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="3b52a-170">Skype 계정이 항상 로그인 할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-170">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="3b52a-171">그룹 정책을 사용 하 여 파일을 전송 하는 방법에 대해서는 [파일 항목 구성을](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-171">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="3b52a-172">Microsoft 팀 대화방 장치가 Windows 10 OS의 다음 버전과 호환 되는 경우이 장치는 자동으로 Windows Update를 통해 다음 버전으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-172">When Microsoft Teams Rooms device is compatible with the next version of Windows 10 OS, the device automatically updates to the next version through Windows Update.</span></span> <span data-ttu-id="3b52a-173">Microsoft 팀 공간 장치를 수동으로 또는 windows 10의 다음 릴리스로 업그레이드 (WUFB) 할 수 없습니다. "받을 업데이트에 대 한 Windows 준비 수준 설정" 및 "Preview 빌드를 선택 하 고 "To GPO"를 통해 기능 업데이트를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-173">Microsoft Teams Rooms device should not be upgraded to next release of Windows 10 manually or via enabling Windows Update for Business (WUFB) group policies “Select the Windows readiness level for the updates you want to receive” and "Select when Preview Builds and Feature Updates are received" through GPO.</span></span> <span data-ttu-id="3b52a-174">이러한 그룹 정책을 사용 하는 디바이스는 Microsoft 팀 대화방 앱에서 Windows 10 OS 업데이트 문제를 발생 하는 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-174">A device with these group policies enabled is known to run into issues with Windows 10 OS update by Microsoft Teams Rooms app.</span></span>

## <a name="remote-management-using-powershell"></a><span data-ttu-id="3b52a-175">PowerShell을 사용 하 여 원격 관리</span><span class="sxs-lookup"><span data-stu-id="3b52a-175">Remote Management using PowerShell</span></span>
<span data-ttu-id="3b52a-176"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="3b52a-176"><a name="RemotePS"> </a></span></span>

<span data-ttu-id="3b52a-177">PowerShell을 사용 하 여 원격으로 다음 관리 작업을 수행할 수 있습니다 (스크립트 샘플은 아래 표 참조).</span><span class="sxs-lookup"><span data-stu-id="3b52a-177">You can perform the following management operations remotely by using PowerShell (see the table below for script samples):</span></span>
  
- <span data-ttu-id="3b52a-178">연결 된 장치 가져오기</span><span class="sxs-lookup"><span data-stu-id="3b52a-178">Get attached devices</span></span>
- <span data-ttu-id="3b52a-179">앱 상태 가져오기</span><span class="sxs-lookup"><span data-stu-id="3b52a-179">Get app status</span></span>
- <span data-ttu-id="3b52a-180">시스템 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="3b52a-180">Get system info</span></span>
- <span data-ttu-id="3b52a-181">시스템 다시 부팅</span><span class="sxs-lookup"><span data-stu-id="3b52a-181">Reboot system</span></span>
- <span data-ttu-id="3b52a-182">로그 검색</span><span class="sxs-lookup"><span data-stu-id="3b52a-182">Retrieve logs</span></span>
- <span data-ttu-id="3b52a-183">파일 전송 (도메인에 가입 된 Microsoft 팀 대화방 필요)</span><span class="sxs-lookup"><span data-stu-id="3b52a-183">Transfer files (requires a domain-joined Microsoft Teams Rooms)</span></span>
    
> [!NOTE]
> <span data-ttu-id="3b52a-184">이 기능은 기본적으로 해제 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-184">This functionality is off by default.</span></span> <span data-ttu-id="3b52a-185">아래 작업을 수행 하려면 Microsoft 팀 대화방 시스템에서 환경에 대 한 원격 PowerShell을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-185">You need to enable remote PowerShell for your environment on the Microsoft Teams Rooms system to perform the operations below.</span></span> <span data-ttu-id="3b52a-186">원격 PowerShell을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 **[enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** 의 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b52a-186">Refer to the documentation on **[Enable-PSRemoting](https://technet.microsoft.com/library/hh849694.aspx)** for information about how to enable remote PowerShell.</span></span>
  
<span data-ttu-id="3b52a-187">예를 들어 다음과 같이 원격 PowerShell을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-187">For example, you can enable Remote PowerShell as follows:</span></span>
  
1. <span data-ttu-id="3b52a-188">Microsoft 팀 대화방 장치에서 관리자로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-188">Sign in as Admin on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="3b52a-189">관리자 권한 PowerShell 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-189">Open an elevated PowerShell command prompt.</span></span>
3. <span data-ttu-id="3b52a-190">Enable-PSRemoting-force 명령을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-190">Enter the following command: Enable-PSRemoting -force</span></span>

<span data-ttu-id="3b52a-191">관리 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-191">To perform a management operation:</span></span>
  
1. <span data-ttu-id="3b52a-192">Microsoft 팀 회의실 장치에서 PowerShell 명령을 실행할 권한이 있는 계정 자격 증명으로 PC에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-192">Sign in to a PC with account credentials that have permission to run PowerShell commands on a Microsoft Teams Rooms device.</span></span>
2. <span data-ttu-id="3b52a-193">PC에서 일반 PowerShell 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-193">Open a regular PowerShell command prompt on the PC.</span></span>
3. <span data-ttu-id="3b52a-194">아래 표의 명령 텍스트를 복사 하 고 프롬프트에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-194">Copy the command text from the table below and paste it at the prompt.</span></span>
4. <span data-ttu-id="3b52a-195">필드 `<Device fqdn>` 를 사용자 환경에 적합 한 FQDN 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-195">Replace  `<Device fqdn>` fields with FQDN values appropriate to your environment.</span></span>
5. <span data-ttu-id="3b52a-196">\* \<경로\> \* 를 마스터 SkypeSettings 구성 파일 (또는 테마 이미지)의 파일 이름 및 로컬 경로로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-196">Replace  *\<path\>*  with the file name and local path of the master SkypeSettings.xml configuration file (or Theme image).</span></span>
    
<span data-ttu-id="3b52a-197">연결 된 장치를 얻으려면</span><span class="sxs-lookup"><span data-stu-id="3b52a-197">To Get Attached Devices</span></span>
  
```PowerShell
invoke-command {Write-Host "VIDEO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Image"} | Format-Table Name,Status,Present; Write-Host "AUDIO DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Media"} | Format-Table Name,Status,Present; Write-Host "DISPLAY DEVICES:" 
gwmi -Class Win32_PnPEntity | where {$_.PNPClass -eq "Monitor"} | Format-Table Name,Status,Present} -ComputerName <Device fqdn>
```

<span data-ttu-id="3b52a-198">앱 상태 가져오기</span><span class="sxs-lookup"><span data-stu-id="3b52a-198">Get App Status</span></span>
  
```PowerShell
invoke-command { $package = get-appxpackage -User Skype -Name Microsoft.SkypeRoomSystem; if ($package -eq $null) {Write-host "SkypeRoomSystems not installed."} else {write-host "SkypeRoomSystem Version : " $package.Version}; $process = Get-Process -Name "Microsoft.SkypeRoomSystem" -ErrorAction SilentlyContinue; if ($process -eq $null) {write-host "App not running."} else {$process | format-list StartTime,Responding}}  -ComputerName <Device fqdn>
```

<span data-ttu-id="3b52a-199">시스템 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="3b52a-199">Get System Info</span></span>
  
```PowerShell
invoke-command {gwmi -Class Win32_ComputerSystem | Format-List PartOfDomain,Domain,Workgroup,Manufacturer,Model
gwmi -Class Win32_Bios | Format-List SerialNumber,SMBIOSBIOSVersion} -ComputerName <Device fqdn>
```

<span data-ttu-id="3b52a-200">시스템 다시 부팅</span><span class="sxs-lookup"><span data-stu-id="3b52a-200">Reboot System</span></span>
  
```PowerShell
invoke-command { Shutdown /r /t 0 } -ComputerName <Device fqdn>
```

<span data-ttu-id="3b52a-201">로그 검색</span><span class="sxs-lookup"><span data-stu-id="3b52a-201">Retrieve Logs</span></span>
  
```PowerShell
$targetDevice = "<Device fqdn> "
$logFile = invoke-command {$output = Powershell.exe -ExecutionPolicy Bypass -File C:\Rigel\x64\Scripts\Provisioning\ScriptLaunch.ps1 CollectSrsV2Logs.ps1
Get-ChildItem -Path C:\Rigel\*.zip | Sort-Object -Descending -Property LastWriteTime | Select-Object -First 1} -ComputerName $targetDevice
$session = new-pssession -ComputerName $targetDevice
Copy-Item -Path $logFile.FullName -Destination .\ -FromSession $session; invoke-command {remove-item -force C:\Rigel\*.zip} -ComputerName $targetDevice
```

<span data-ttu-id="3b52a-202">XML 구성 파일 (또는 테마 그래픽) 푸시</span><span class="sxs-lookup"><span data-stu-id="3b52a-202">Push an XML configuration file (or theme graphic)</span></span>
  
```XML
$movefile = "<path>";
$targetDevice = "\\<Device fqdn> \Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState\SkypeSettings.xml"; 
Copy-Item $movefile $targetDevice 
```

## <a name="software-updates"></a><span data-ttu-id="3b52a-203">소프트웨어 업데이트</span><span class="sxs-lookup"><span data-stu-id="3b52a-203">Software updates</span></span>
<span data-ttu-id="3b52a-204"><a name="SWupdate"> </a></span><span class="sxs-lookup"><span data-stu-id="3b52a-204"><a name="SWupdate"> </a></span></span>

<span data-ttu-id="3b52a-205">기본적으로 Microsoft 팀 대화방에서 최신 버전의 Microsoft 팀 공간 소프트웨어를 다운로드 하기 위해 Windows 스토어에 연결 하려고 시도 하므로 장치에 일반 인터넷 액세스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-205">By default, Microsoft Teams Rooms attempts to connect to the Windows Store to get the latest version of Microsoft Teams Rooms software, so the device will require regular internet access.</span></span> <span data-ttu-id="3b52a-206">Microsoft에서 지원 문제를 해결 하기 전에 Microsoft 팀 대화방 장치가 최신 버전의 앱을 사용 하 여 로드 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-206">Before contacting Microsoft with support issues, be sure the Microsoft Teams Rooms device is loaded with the latest version of the app.</span></span>
  
<span data-ttu-id="3b52a-207">기본적으로 Microsoft 팀 대화방은 Windows Update에 연결 하 여 운영 체제 및 USB 주변 장치 펌웨어 업데이트를 검색 하 고, 구성 된 업무 시간 외에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-207">By default, Microsoft Teams Rooms connects to Windows Update to retrieve operating system and USB peripheral device firmware updates, and installs them outside of configured business hours.</span></span> <span data-ttu-id="3b52a-208">관리자 계정에 로그인 하 고 설정 앱을 실행 하 여 업무 시간을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-208">You can configure business hours by signing into the administrator account and running the Settings app.</span></span>
  
<span data-ttu-id="3b52a-209">업데이트를 수동으로 관리 하 고 [Microsoft Store For Business](https://businessstore.microsoft.com/store) online에서 [오프 라인 앱을 배포](https://docs.microsoft.com/microsoft-store/distribute-offline-apps)하는 것을 수행할 수 없는 경우에는 구성 관리자와 함께 사용할 수 있는 [배포 키트](https://go.microsoft.com/fwlink/?linkid=851168) ( [microsoft 팀 대화방 콘솔 구성](console.md)지침 참조)에서 적절 한 APPX 파일과 종속성을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-209">If you want to manage updates manually, and are unable to follow the normal procedure for [Microsoft Store for Business](https://businessstore.microsoft.com/store) to [Distribute offline apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps), you can acquire the appropriate APPX file and dependencies from the [deployment kit](https://go.microsoft.com/fwlink/?linkid=851168) (from the instructions to [Configure a Microsoft Teams Rooms console](console.md)) that can be used with Configuration Manager.</span></span> <span data-ttu-id="3b52a-210">배포 키트 릴리스는 스토어 릴리스에서 지연 되므로 사용 가능한 최신 빌드와 항상 일치 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-210">The deployment kit release lags behind the store release, so it might not always match the latest available build.</span></span>
  
### <a name="to-update-using-powershell"></a><span data-ttu-id="3b52a-211">Powershell을 사용 하 여 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="3b52a-211">To update using Powershell</span></span>

1. <span data-ttu-id="3b52a-212">설치 [MSI](https://go.microsoft.com/fwlink/?linkid=851168) 에서 장치에 액세스할 수 있는 공유로 패키지를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-212">Extract the package from the installation [MSI](https://go.microsoft.com/fwlink/?linkid=851168) to a share the device can access.</span></span>
2. <span data-ttu-id="3b52a-213">Microsoft 팀 회의실 장치를 대상으로 하는 다음 스크립트를 \<실행\> 하 고 장치 공유에 대 한 공유를 적절 하 게 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-213">Run the following script targeting the Microsoft Teams Rooms devices, changing \<share\> to the device share as appropriate:</span></span>
    
```PowerShell
Add-AppxPackage -Update -ForceApplicationShutdown -Path '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\*.appx' -DependencyPath (Get-ChildItem '\\<share>\$oem$\$1\Rigel\x64\Ship\AppPackages\*\Dependencies\x64\*.appx' | Foreach-Object {$_.FullName})
```

## <a name="admin-mode-and-device-management"></a><span data-ttu-id="3b52a-214">관리 모드 및 장치 관리</span><span class="sxs-lookup"><span data-stu-id="3b52a-214">Admin mode and device management</span></span>
<span data-ttu-id="3b52a-215"><a name="AdminMode"> </a></span><span class="sxs-lookup"><span data-stu-id="3b52a-215"><a name="AdminMode"> </a></span></span>

<span data-ttu-id="3b52a-216">개인 CA 인증서를 수동으로 설치 하는 등의 일부 관리 기능은 Surface Pro 장치를 관리 모드로 전환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-216">Some management functions, like manually installing a private CA certificate, require placing the Surface Pro device in Admin mode.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running"></a><span data-ttu-id="3b52a-217">Microsoft 팀 대화방 앱이 실행 중일 때 관리 모드로 전환 및 돌아가기</span><span class="sxs-lookup"><span data-stu-id="3b52a-217">Switching to Admin Mode and back when the Microsoft Teams Rooms app is running</span></span>

1. <span data-ttu-id="3b52a-218">진행 중인 통화를 모두 끊고 홈 화면으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-218">Hang up any ongoing calls, and return to the home screen.</span></span>
2. <span data-ttu-id="3b52a-219">기어 아이콘을 선택 하 고 메뉴를 표시 합니다 ( **설정**, **접근성**및 **장치 다시 시작** 옵션).</span><span class="sxs-lookup"><span data-stu-id="3b52a-219">Select the Gear icon and bring up the menu (options are **Settings**, **Accessibility**, and **Restart Device** ).</span></span>
3. <span data-ttu-id="3b52a-220">**설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-220">Select **Settings**.</span></span>
4. <span data-ttu-id="3b52a-221">관리자 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-221">Enter the Administrator Password.</span></span> <span data-ttu-id="3b52a-222">설정 화면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-222">The Setup screen will appear.</span></span>  <span data-ttu-id="3b52a-223">디바이스가 도메인에 가입 되어 있지 않으면 기본적으로 로컬 관리 계정 (사용자 이름 "관리자")을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-223">If the device isn't domain-joined, the local administrative account (username "Admin") will be used by default.</span></span> <span data-ttu-id="3b52a-224">이 계정의 기본 암호는 ' sfb ' 이며, 최대한 빨리 암호를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-224">The default password for this account is 'sfb', change the password as soon as possible.</span></span> <span data-ttu-id="3b52a-225">컴퓨터가 도메인에 가입 되어 있는 경우 적절 한 권한 도메인 계정으로 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-225">If the machine is domain-joined, you can sign in with an appropriately privileged domain account.</span></span> 
5. <span data-ttu-id="3b52a-226">왼쪽 열에서 **Windows 설정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-226">Select **Windows Settings** in the left column.</span></span>
6. <span data-ttu-id="3b52a-227">**관리자 로그인으로 이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-227">Choose **Go to Admin Sign-in**.</span></span>
7. <span data-ttu-id="3b52a-228">관리자 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-228">Enter the Administrator Password.</span></span> <span data-ttu-id="3b52a-229">이렇게 하면 앱이 적절 하 게 로그 오프 되 고 Windows 로그인 화면으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-229">This will gracefully log off the app and take you to the Windows login screen.</span></span> 
8. <span data-ttu-id="3b52a-230">관리 자격 증명을 사용 하 여 데스크톱에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-230">Log in to the desktop with your administrative credentials.</span></span> <span data-ttu-id="3b52a-231">장치를 관리 하는 데 필요한 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-231">You'll have the necessary privileges to manage the device.</span></span>
9. <span data-ttu-id="3b52a-232">필요한 관리 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-232">Perform the necessary administrative tasks.</span></span>
10. <span data-ttu-id="3b52a-233">관리자 계정에서 로그 아웃 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-233">Sign out from the Admin account.</span></span>
11. <span data-ttu-id="3b52a-234">화면 왼쪽 끝에 있는 사용자 계정 아이콘을 선택한 다음 **Skype**를 선택 하 여 Microsoft 팀 대화방으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-234">Return to Microsoft Teams Rooms by selecting the user account icon on the far left side of the screen and then selecting **Skype**.</span></span>
    
    <span data-ttu-id="3b52a-235">**Skype** 사용자가 목록에 없는 경우 **다른 사용자** 를 선택 하 고 사용자 이름으로 **.\skype** 를 입력 한 후 로그인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-235">If the **Skype** user is not listed, you might have to select **other user** and enter **.\skype** as the user name, and sign in.</span></span>
    
<span data-ttu-id="3b52a-236">이제 콘솔이 정상 작동 모드로 돌아갑니다. 다음 절차에서는 키보드가 아직 연결 되어 있지 않은 경우 장치에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-236">The console is now back in its normal operation mode.The following procedure requires you to attach a keyboard to the device if one is not already attached.</span></span> 
  
### <a name="switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes"></a><span data-ttu-id="3b52a-237">Microsoft 팀 대화방 앱이 충돌 하는 경우 관리 모드로 전환 및 돌아가기</span><span class="sxs-lookup"><span data-stu-id="3b52a-237">Switching to Admin Mode and back when the Microsoft Teams Rooms app crashes</span></span>

1. <span data-ttu-id="3b52a-238">Windows 키를 다섯 번 빠르게 연속적으로 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-238">Press the Windows key five times in rapid succession.</span></span> <span data-ttu-id="3b52a-239">Windows 로그온 화면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-239">This will bring you to the Windows logon screen.</span></span> 
2. <span data-ttu-id="3b52a-240">관리 자격 증명을 사용 하 여 데스크톱에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-240">Log in to the desktop with your administrative credentials.</span></span>
3. <span data-ttu-id="3b52a-241">필요한 관리 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-241">Perform the necessary administrative tasks.</span></span>
4. <span data-ttu-id="3b52a-242">완료 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-242">Restart the machine when you're finished.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b52a-243">이 방법은 Skype 사용자를 끄거나 앱을 정상적으로 종료 하지는 않지만 앱이 응답 하지 않고 다른 방법을 사용할 수 없는 경우에도 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-243">This method doesn't log the Skype user off or gracefully terminate the app, but you'd use it if the app wasn't responding and the other method wasn't available.</span></span> 

   <span data-ttu-id="3b52a-244">콘솔이 정상 작동 모드로 다시 시작 되어 Microsoft 팀 회의실 앱을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-244">The console restarts into its normal operation mode, running the Microsoft Teams Rooms app.</span></span> <span data-ttu-id="3b52a-245">이 절차를 수행할 수 있도록 연결 된 경우 키보드를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-245">You can remove the keyboard, if it was attached to allow you to perform this procedure.</span></span>
   ## <a name="troubleshooting-tips"></a><span data-ttu-id="3b52a-246">문제 해결 팁</span><span class="sxs-lookup"><span data-stu-id="3b52a-246">Troubleshooting tips</span></span>
   <span data-ttu-id="3b52a-247"><a name="TS"> </a></span><span class="sxs-lookup"><span data-stu-id="3b52a-247"><a name="TS"> </a></span></span>

- <span data-ttu-id="3b52a-248">도메인 경계를 넘어 전송 되는 경우 모임 초대가 표시 되지 않을 수 있습니다 (예: 두 회사 간).</span><span class="sxs-lookup"><span data-stu-id="3b52a-248">Meeting invitations might not appear when sent across domain boundaries (for example, between two companies).</span></span> <span data-ttu-id="3b52a-249">이러한 경우 IT 관리자는 외부 사용자가 모임을 예약할 수 있도록 허용할지 여부를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-249">In such cases, IT admins should decide whether to allow external users to schedule a meeting.</span></span>
- <span data-ttu-id="3b52a-250">Microsoft 팀 대화방은 Exchange 2010를 통해 Exchange 자동 검색 리디렉션을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-250">Microsoft Teams Rooms doesn't support Exchange AutoDiscover redirects via Exchange 2010.</span></span>
- <span data-ttu-id="3b52a-251">일반적으로 IT 관리자는 사용 하지 않으려는 오디오 끝점을 비활성화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-251">In general, it's a good practice for IT admins to disable any audio endpoints they don't intend to use.</span></span>
- <span data-ttu-id="3b52a-252">룸 미리 보기에 미러 이미지가 표시 되는 경우, IT 관리자는 카메라 전원을 순환 하거나 카메라 리모컨을 사용 하 여 이미지 방향을 대칭 이동 하 여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-252">In the event that a mirror image is displayed in room preview, the IT admin can correct by cycling camera power or flipping the image orientation using the camera remote control.</span></span>
- <span data-ttu-id="3b52a-253">콘솔 터치 스크린의 손실에 대 한 액세스가 발생 하는 것으로 알려졌습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-253">Loss of console touchscreen access has been known to occur.</span></span> <span data-ttu-id="3b52a-254">이러한 경우에는 Microsoft 팀 대화방 시스템을 다시 시작 하 여 문제가 해결 되기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-254">In such cases, the issue is sometimes resolved by restarting the Microsoft Teams Rooms system.</span></span>
- <span data-ttu-id="3b52a-255">유선 수집을 통해 PC를 콘솔에 연결할 때 로컬 오디오 손실이 발생 하는 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-255">Loss of local audio when connecting a PC to console via wired ingest has been known to occur.</span></span> <span data-ttu-id="3b52a-256">이러한 경우 PC를 다시 시작 하면 로컬 오디오 재생 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b52a-256">In such cases, restarting the PC can resolve the local audio playback issue.</span></span>
    
