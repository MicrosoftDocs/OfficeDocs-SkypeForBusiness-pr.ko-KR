---
title: SCCM을 통해 MSI를 사용 하 여 Microsoft 팀 설치
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 관리자는 팀 MSI를 사용 하 여 Microsoft 팀을 대량 배포 하 여 사용자 또는 컴퓨터를 선택할 수 있습니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd934c601b45258dd7a2e2c15ef49f19ffee9201
ms.sourcegitcommit: 416a2d404a2ea15b484cd7579035e7f2282ac2cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233277"
---
# <a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="13292-103">MSI를 사용 하 여 Microsoft 팀 설치</span><span class="sxs-lookup"><span data-stu-id="13292-103">Install Microsoft Teams using MSI</span></span>

> [!Tip]
> <span data-ttu-id="13292-104">Windows 데스크톱 클라이언트의 이점,이를 위해 계획 하는 방법 및 배포 하는 방법에 대해 알아보려면 다음 세션을 시청 하세요. [팀 Windows 데스크톱 클라이언트](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="13292-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="13292-105">System Center Configuration Manager 또는 그룹 정책 또는 광범위 한 배포에 대 한 타사 배포 메커니즘을 사용 하기 위해 Microsoft는 관리자가 사용자 또는 컴퓨터를 선택 하기 위해 팀을 대량으로 배포 하는 데 사용할 수 있는 MSI 파일 (32 비트 및 64 비트)을 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="13292-106">관리자는 이러한 파일을 사용 하 여 사용자가 팀 앱을 수동으로 다운로드할 필요가 없도록 팀을 원격으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="13292-107">배포 되는 경우 해당 컴퓨터에 로그인 하는 모든 사용자에 대해 팀이 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13292-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="13292-108">(앱을 설치한 후 자동 시작을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="13292-109">[아래를 참조](#disable-auto-launch-for-the-msi-installer)하세요.) 컴퓨터에 패키지를 배포 하는 것이 좋으며,이는 컴퓨터의 모든 새 사용자도이 배포를 활용할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="13292-110">MSI 파일에 대 한 링크는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="13292-111">엔터티만</span><span class="sxs-lookup"><span data-stu-id="13292-111">Entity</span></span>  |<span data-ttu-id="13292-112">32 비트</span><span class="sxs-lookup"><span data-stu-id="13292-112">32 bit</span></span>      |<span data-ttu-id="13292-113">64 비트</span><span class="sxs-lookup"><span data-stu-id="13292-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="13292-114">상업성</span><span class="sxs-lookup"><span data-stu-id="13292-114">Commercial</span></span>     | [<span data-ttu-id="13292-115">32 비트</span><span class="sxs-lookup"><span data-stu-id="13292-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="13292-116">64 비트</span><span class="sxs-lookup"><span data-stu-id="13292-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="13292-117">미국 정부의 GCC</span><span class="sxs-lookup"><span data-stu-id="13292-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="13292-118">32 비트</span><span class="sxs-lookup"><span data-stu-id="13292-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="13292-119">64 비트</span><span class="sxs-lookup"><span data-stu-id="13292-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="13292-120">미국 정부-GCC 최고</span><span class="sxs-lookup"><span data-stu-id="13292-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="13292-121">32 비트</span><span class="sxs-lookup"><span data-stu-id="13292-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="13292-122">64 비트</span><span class="sxs-lookup"><span data-stu-id="13292-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="13292-123">연방 정부-DoD</span><span class="sxs-lookup"><span data-stu-id="13292-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="13292-124">32 비트</span><span class="sxs-lookup"><span data-stu-id="13292-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="13292-125">64 비트</span><span class="sxs-lookup"><span data-stu-id="13292-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="13292-126">팀은 Office 365 ProPlus 배포에도 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="13292-127">자세한 내용은 [Office 365 ProPlus를 사용 하 여 Microsoft 팀 배포](https://docs.microsoft.com/deployoffice/teams-install)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13292-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="13292-128">SCCM에 대해 자세히 알아보려면 [System Center Configuration Manager 소개](https://docs.microsoft.com/sccm/core/understand/introduction)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13292-128">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="13292-129">배포 절차 (권장)</span><span class="sxs-lookup"><span data-stu-id="13292-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="13292-130">최신 패키지를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="13292-131">MSI에서 미리 채워 온 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="13292-132">가능 하면 컴퓨터에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="13292-133">Microsoft 팀 MSI 패키지가 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="13292-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="13292-134">PC 설치</span><span class="sxs-lookup"><span data-stu-id="13292-134">PC installation</span></span>

<span data-ttu-id="13292-135">팀 MSI는 프로그램 파일에 설치 관리자를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="13292-136">사용자가 새 Windows 사용자 프로필에 로그인 할 때마다 설치 프로그램이 시작 되 고 팀 앱의 복사본이 해당 사용자의 appdata 폴더에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13292-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="13292-137">Appdata 폴더에 팀 앱이 이미 설치 되어 있는 경우 MSI 설치 관리자가 해당 사용자에 대 한 프로세스를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="13292-137">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="13292-138">MSI를 사용 하 여 업데이트를 배포 하는 경우 클라이언트는 서비스에서 새 버전이 제공 될 때 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13292-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="13292-139">최신 설치 관리자를 다시 배포 하려면 아래 설명 된 MSI 재배포 프로세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="13292-140">이전 버전의 MSI 패키지를 배포 하는 경우 클라이언트는 사용자에 대해 가능 하면 VDI 환경에서 제외 하 고 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13292-140"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="13292-141">오래 된 버전이 배포 되는 경우 MSI는 사용자가 팀을 사용할 수 있도록 앱 업데이트를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="13292-142">기본 설치 위치를 변경 하는 것은 업데이트 흐름이 중단 될 수 있으므로 권장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="13292-143">오래 된 버전을 보유 하면 결국 사용자가 서비스에 액세스 하지 못하도록 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13292-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="13292-144">대상 컴퓨터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="13292-144">Target computer requirements</span></span>

- <span data-ttu-id="13292-145">.NET framework 4.5 이상</span><span class="sxs-lookup"><span data-stu-id="13292-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="13292-146">Windows 7 이상</span><span class="sxs-lookup"><span data-stu-id="13292-146">Windows 7 or later</span></span>
- <span data-ttu-id="13292-147">Windows Server 2012 R2 이상</span><span class="sxs-lookup"><span data-stu-id="13292-147">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="13292-148">각 사용자 프로필에 대해 3gb의 디스크 공간 (권장)</span><span class="sxs-lookup"><span data-stu-id="13292-148">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="13292-149">VDI 설치</span><span class="sxs-lookup"><span data-stu-id="13292-149">VDI installation</span></span>

<span data-ttu-id="13292-150">VDI에서 팀 데스크톱 앱을 배포 하는 방법에 대 한 자세한 지침은 [가상화 된 데스크톱 인프라 팀](teams-for-vdi.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13292-150">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="13292-151">정리 및 다시 배포 절차</span><span class="sxs-lookup"><span data-stu-id="13292-151">Clean up and redeployment procedure</span></span>

<span data-ttu-id="13292-152">사용자가 사용자 프로필에서 팀을 제거 하는 경우 MSI 설치 관리자는 사용자가 팀 앱을 제거 하 고 더 이상 해당 사용자 프로필에 대 한 팀을 설치 하지 않은 것을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-152">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="13292-153">제거 된 특정 컴퓨터에서이 사용자의 팀을 다시 배포 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-153">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="13292-154">모든 사용자 프로필에 대해 팀 앱을 설치 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-154">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="13292-155">제거 후%localappdata%\Microsoft\Teams\.에서 디렉터리를 재귀적으로 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-155">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="13292-156">해당 특정 컴퓨터에 MSI 패키지를 다시 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-156">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="13292-157">[Microsoft 팀 배포 정리](scripts/powershell-script-teams-deployment-clean-up.md) 스크립트를 사용 하 여 SCCM을 통해 1 단계 및 2 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-157">You can use our [Microsoft Teams deployment clean up](scripts/powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="13292-158">설치 후 팀이 자동으로 시작 되지 않도록 방지</span><span class="sxs-lookup"><span data-stu-id="13292-158">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="13292-159">MSI의 기본 동작은 사용자가 로그인 하는 즉시 팀 앱을 설치한 다음 팀을 자동으로 시작 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="13292-159">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="13292-160">사용자가 설치 된 후 팀이 자동으로 시작 되지 않도록 하려면 그룹 정책을 사용 하 여 정책 설정을 설정 하거나 MSI 설치 관리자에 대 한 자동 시작을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-160">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

#### <a name="use-group-policy-recommended"></a><span data-ttu-id="13292-161">그룹 정책 사용 (권장)</span><span class="sxs-lookup"><span data-stu-id="13292-161">Use Group Policy (recommended)</span></span>

<span data-ttu-id="13292-162">**설치 후 Microsoft 팀이 자동으로 시작 되지 않도록** 설정 그룹 정책 설정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-162">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="13292-163">사용자 Configuration\Policies\Administrative Templates\Microsoft 팀에서이 정책 설정을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-163">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="13292-164">조직의 요구 사항에 따라 정책 설정을 끄거나 켤 수 있으므로이 방법을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-164">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="13292-165">팀을 설치 하기 전에이 정책 설정을 사용 하면 사용자가 Windows에 로그인 할 때 팀이 자동으로 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-165">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="13292-166">사용자가 처음으로 팀에 로그인 한 후에는 다음에 사용자가 로그인 할 때 팀이 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13292-166">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="13292-167">자세한 내용은 그룹 정책 사용을 참조 하 여 [팀이 설치 후 자동으로 시작 되지 않도록](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-167">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="13292-168">이미 팀을 배포 했으며 팀 자동 시작을 사용 하지 않도록 설정 하려는 경우 먼저 그룹 정책 설정을 원하는 값으로 설정한 다음 팀에서 사용자 기준으로 자동 시작 스크립트를 [다시](scripts/powershell-script-teams-reset-autostart.md) 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-168">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="13292-169">MSI 설치 관리자에 대 한 자동 시작 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="13292-169">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="13292-170">다음과 같이 **옵션 = "noAutoStart 시작 = true"** 매개 변수를 사용 하 여 MSI 설치 관리자에 대 한 자동 실행을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-170">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="13292-171">32 비트 버전</span><span class="sxs-lookup"><span data-stu-id="13292-171">For the 32-bit version</span></span>
```PowerShell
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="13292-172">64 비트 버전</span><span class="sxs-lookup"><span data-stu-id="13292-172">For the 64-bit version</span></span>
```PowerShell
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

<span data-ttu-id="13292-173">사용자가 Windows에 로그인 하면 팀이 MSI와 함께 설치 되 고 팀 시작에 대 한 바로 가기가 사용자의 데스크톱에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13292-173">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="13292-174">팀은 사용자가 수동으로 팀을 시작할 때까지 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13292-174">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="13292-175">사용자가 수동으로 팀을 시작 하면 사용자가 로그인 할 때마다 팀이 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13292-175">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

> [!Note]
> <span data-ttu-id="13292-176">MSI를 수동으로 실행 하는 경우 관리자 권한으로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13292-176">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="13292-177">관리자 권한으로 실행 하는 경우에도 권한 상승으로이를 실행 하지 않으면 설치 관리자가 자동 시작을 사용 하지 않도록 설정 하는 옵션을 구성할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13292-177">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
