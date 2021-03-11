---
title: Microsoft 엔드포인트 구성 관리자를 사용하여 Teams 설치
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: Microsoft 엔드포인트 구성 관리자를 사용하여 Microsoft Teams를 대량 배포하여 사용자 또는 컴퓨터를 선택합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cde5b2f04936afdd16eb7d0ff13a03840e6fa49
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50614954"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="66966-103">Microsoft 엔드포인트 구성 관리자를 사용하여 Microsoft Teams 설치</span><span class="sxs-lookup"><span data-stu-id="66966-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="66966-104">다음 세션을 통해 Windows 데스크톱 클라이언트의 이점, 이를 계획하는 방법 및 배포 방법: Teams Windows Desktop Client 에 대해 [자세히 알아보는 세션을 시청합니다.](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="66966-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients).</span></span>

<span data-ttu-id="66966-105">Microsoft 엔드포인트 구성 관리자 또는 그룹 정책 또는 타사 배포 메커니즘을 광범위하게 배포하기 위해 Microsoft는 관리자가 Teams의 대량 배포에 사용할 수 있는 MSI 파일(32비트 및 64비트)을 제공하여 사용자 또는 컴퓨터를 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="66966-106">관리자는 이러한 파일을 사용하여 사용자가 Teams 앱을 수동으로 다운로드할 수 있도록 Teams를 원격으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="66966-107">배포되면 해당 머신에 로그인한 모든 사용자에 대해 Teams가 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="66966-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="66966-108">(앱을 설치한 후 자동 시작을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="66966-109">[아래를 참조하세요.](#disable-auto-launch-for-the-msi-installer) 컴퓨터에 패키지를 배포하는 것이 좋습니다. 따라서 컴퓨터의 모든 새 사용자도 이 배포의 혜택을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="66966-110">다음은 MSI 파일에 대한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="66966-110">These are the links to the MSI files:</span></span>

|<span data-ttu-id="66966-111">엔터티</span><span class="sxs-lookup"><span data-stu-id="66966-111">Entity</span></span>  |<span data-ttu-id="66966-112">32비트</span><span class="sxs-lookup"><span data-stu-id="66966-112">32-bit</span></span>      |<span data-ttu-id="66966-113">64비트</span><span class="sxs-lookup"><span data-stu-id="66966-113">64-bit</span></span>      | <span data-ttu-id="66966-114">ARM64</span><span class="sxs-lookup"><span data-stu-id="66966-114">ARM64</span></span> |
|---------|---------|---------|-----------|
|<span data-ttu-id="66966-115">상업용</span><span class="sxs-lookup"><span data-stu-id="66966-115">Commercial</span></span>     | [<span data-ttu-id="66966-116">32비트</span><span class="sxs-lookup"><span data-stu-id="66966-116">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="66966-117">64비트</span><span class="sxs-lookup"><span data-stu-id="66966-117">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [<span data-ttu-id="66966-118">ARM64</span><span class="sxs-lookup"><span data-stu-id="66966-118">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|<span data-ttu-id="66966-119">미국 정부 - GCC</span><span class="sxs-lookup"><span data-stu-id="66966-119">U.S. Government - GCC</span></span>     | [<span data-ttu-id="66966-120">32비트</span><span class="sxs-lookup"><span data-stu-id="66966-120">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="66966-121">64비트</span><span class="sxs-lookup"><span data-stu-id="66966-121">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[<span data-ttu-id="66966-122">ARM64</span><span class="sxs-lookup"><span data-stu-id="66966-122">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|<span data-ttu-id="66966-123">미국 정부 - GCC High</span><span class="sxs-lookup"><span data-stu-id="66966-123">U.S. Government - GCC High</span></span>    | [<span data-ttu-id="66966-124">32비트</span><span class="sxs-lookup"><span data-stu-id="66966-124">32-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="66966-125">64비트</span><span class="sxs-lookup"><span data-stu-id="66966-125">64-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[<span data-ttu-id="66966-126">ARM64</span><span class="sxs-lookup"><span data-stu-id="66966-126">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|<span data-ttu-id="66966-127">미국 정부 - DoD</span><span class="sxs-lookup"><span data-stu-id="66966-127">U.S. Government - DoD</span></span>     | [<span data-ttu-id="66966-128">32비트</span><span class="sxs-lookup"><span data-stu-id="66966-128">32-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="66966-129">64비트</span><span class="sxs-lookup"><span data-stu-id="66966-129">64-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [<span data-ttu-id="66966-130">ARM64</span><span class="sxs-lookup"><span data-stu-id="66966-130">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

<span data-ttu-id="66966-131">**성공적인 배포를 보장하기 위해 다음을 유의해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="66966-131">**To ensure a successful deployment, be aware of the following:**</span></span>

- <span data-ttu-id="66966-132">64비트 운영 체제에 64비트 버전의 Teams를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-132">Install the 64-bit version of Teams on 64-bit operating systems.</span></span> <span data-ttu-id="66966-133">32비트 운영 체제에 64비트 버전의 Teams를 설치하려고 하는 경우 설치가 성공하지 못하고 현재 오류 메시지가 수신되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-133">If you try to install the 64-bit version of Teams on a 32-bit operating system, the installation won't be successful and currently you won't receive an error message.</span></span>

- <span data-ttu-id="66966-134">고객 테넌트가 GCCH 또는 DoD 클라우드에 있는 경우 고객은 레지스트리의 키에 **CloudType** 값을 추가하여 레지스트리의 **초기 엔드포인트를** HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-134">If the customer tenant is on the GCCH or DoD clouds, the customer should set the initial endpoint in the registry by adding the **CloudType** value to the **HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams** key in the registry.</span></span> <span data-ttu-id="66966-135">**CloudType의** 형식은 **DWORD이고** 값은 (0 = Unset, 1 = commercial, 2 = GCC, 3 = GCCH, 4 = DOD)입니다.</span><span class="sxs-lookup"><span data-stu-id="66966-135">The type for **CloudType** is **DWORD** and values are (0 = Unset, 1 = commercial, 2 = GCC, 3 = GCCH, 4 = DOD).</span></span> <span data-ttu-id="66966-136">레지스트리 키로 엔드포인트를 설정하면 Teams가 Teams와의 사전 로그인 연결을 위해 올바른 클라우드 엔드포인트에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-136">Setting the endpoint with the registry key restricts Teams to connecting to the correct cloud endpoint for pre-sign-in connectivity with Teams.</span></span>

- <span data-ttu-id="66966-137">Teams는 엔터프라이즈용 Microsoft 365 Apps 배포에도 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-137">Teams can also be included with a deployment of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="66966-138">자세한 내용은 엔터프라이즈용 [Microsoft 365 Apps를 사용하여 Microsoft Teams 배포를 참조하세요.](https://docs.microsoft.com/deployoffice/teams-install)</span><span class="sxs-lookup"><span data-stu-id="66966-138">For more information, see [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

- <span data-ttu-id="66966-139">Microsoft 엔드포인트 구성 관리자에 대한 자세한 내용은 [구성 관리자란?을 참조하세요.](https://docs.microsoft.com/configmgr/core/understand/introduction)</span><span class="sxs-lookup"><span data-stu-id="66966-139">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction)</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="66966-140">배포 절차(권장)</span><span class="sxs-lookup"><span data-stu-id="66966-140">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="66966-141">최신 패키지를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-141">Retrieve the latest package.</span></span>
2. <span data-ttu-id="66966-142">MSI에서 미리 채우는 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-142">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="66966-143">가능한 경우 컴퓨터에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-143">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="66966-144">Microsoft Teams MSI 패키지의 작동 방식</span><span class="sxs-lookup"><span data-stu-id="66966-144">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="66966-145">PC 설치</span><span class="sxs-lookup"><span data-stu-id="66966-145">PC installation</span></span>

<span data-ttu-id="66966-146">Teams MSI는 프로그램 파일에 설치 관리자를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-146">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="66966-147">사용자가 새 Windows 사용자 프로필에 로그인할 때마다 설치 관리자를 시작하고 Teams 앱의 복사본이 해당 사용자의 폴더에 `AppData` 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="66966-147">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's `AppData` folder.</span></span> <span data-ttu-id="66966-148">사용자가 폴더에 Teams 앱이 이미 설치되어 있는 경우 MSI 설치 관리자에서 해당 사용자에 대한 프로세스를 `AppData` 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-148">If a user already has the Teams app installed in the `AppData` folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="66966-149">클라이언트가 서비스에서 새 버전을 사용할 수 있는 경우 클라이언트가 자동으로 업데이트하기 때문에 MSI를 사용하여 업데이트를 배포하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-149">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="66966-150">최신 설치 관리자를 다시 배포하려면 아래 설명된 MSI를 다시 배포하는 프로세스를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="66966-150">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="66966-151">이전 버전의 MSI 패키지를 배포하는 경우 클라이언트는 가능한 경우 자동으로 업데이트됩니다(VDI 환경 제외).</span><span class="sxs-lookup"><span data-stu-id="66966-151">If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="66966-152">매우 오래된 버전이 배포되면 사용자가 Teams를 사용하기 전에 MSI에서 앱 업데이트를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-152">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66966-153">기본 위치는 64비트 운영 체제의 C:\Program Files(x86)\Teams 설치 관리자 및 32비트 운영 체제의 C:\Program Files\Teams 설치 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="66966-153">The default location is C:\Program Files (x86)\Teams Installer on 64-bit operating systems and C:\Program Files\Teams Installer on 32-bit operating systems.</span></span>
> <span data-ttu-id="66966-154">업데이트 흐름이 중단될 수 있습니다. 기본 설치 위치를 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-154">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="66966-155">버전이 너무 오래된 경우 결국 사용자가 서비스에 액세스하지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66966-155">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="66966-156">대상 컴퓨터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="66966-156">Target computer requirements</span></span>

- <span data-ttu-id="66966-157">.NET Framework 4.5 이상</span><span class="sxs-lookup"><span data-stu-id="66966-157">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="66966-158">Windows 8.1 이상</span><span class="sxs-lookup"><span data-stu-id="66966-158">Windows 8.1 or later</span></span>
- <span data-ttu-id="66966-159">Windows Server 2012 R2 이상</span><span class="sxs-lookup"><span data-stu-id="66966-159">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="66966-160">각 사용자 프로필에 대한 디스크 공간 3GB(권장)</span><span class="sxs-lookup"><span data-stu-id="66966-160">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="66966-161">VDI 설치</span><span class="sxs-lookup"><span data-stu-id="66966-161">VDI installation</span></span>

<span data-ttu-id="66966-162">VDI에서 Teams 데스크톱 앱을 배포하는 방법에 대한 전체 지침은 가상화된 데스크톱 인프라용 [Teams 를 참조하세요.](teams-for-vdi.md)</span><span class="sxs-lookup"><span data-stu-id="66966-162">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="66966-163">정리 및 재배포 절차</span><span class="sxs-lookup"><span data-stu-id="66966-163">Clean up and redeployment procedure</span></span>

<span data-ttu-id="66966-164">사용자가 사용자 프로필에서 Teams를 제거하면 MSI 설치 관리자에서 사용자가 Teams 앱을 제거하고 해당 사용자 프로필에 대한 Teams를 더 이상 설치하지 않은지 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-164">If a user uninstalls Teams from their user profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that user profile.</span></span> <span data-ttu-id="66966-165">제거된 특정 컴퓨터에서 이 사용자에 대한 Teams를 다시 재배포하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-165">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66966-166">다음 단계에서는 레지스트리를 수정하는 방법에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-166">The next steps contain information about how to modify the registry.</span></span> <span data-ttu-id="66966-167">레지스트리를 수정하기 전에 레지스트리를 백업하고 문제가 발생하는 경우 레지스트리를 복원하는 방법을 알고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-167">Make sure that you back up the registry before you modify it and that you know how to restore the registry if a problem occurs.</span></span> <span data-ttu-id="66966-168">레지스트리를 백업, 복원 및 수정하는 방법에 대한 자세한 내용은 [고급 사용자에 대한 Windows 레지스트리 정보를 참조하세요.](https://support.microsoft.com/help/256986)</span><span class="sxs-lookup"><span data-stu-id="66966-168">For more information about how to back up, restore, and modify the registry, see [Windows registry information for advanced users](https://support.microsoft.com/help/256986).</span></span>

1. <span data-ttu-id="66966-169">모든 사용자 프로필에 대해 설치된 Teams 앱을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-169">Uninstall the Teams app installed for every user profile.</span></span> <span data-ttu-id="66966-170">자세한 내용은 [Microsoft Teams 제거를 참조하세요.](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)</span><span class="sxs-lookup"><span data-stu-id="66966-170">For more information, see [Uninstall Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).</span></span>
2. <span data-ttu-id="66966-171">에서 디렉터리를 다시 `%localappdata%\Microsoft\Teams\` 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-171">Delete the directory recursively under `%localappdata%\Microsoft\Teams\`.</span></span>
3. <span data-ttu-id="66966-172">레지스트리 `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` 값을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-172">Delete the `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` registry value.</span></span>
4. <span data-ttu-id="66966-173">MSI 패키지를 해당 특정 컴퓨터에 다시 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-173">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="66966-174">Teams 배포 정리 [](scripts/powershell-script-deployment-cleanup.md) 스크립트를 사용하여 1단계 및 2단계를 완료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-174">You can also use our [Teams deployment clean up script](scripts/powershell-script-deployment-cleanup.md) to complete steps 1 and 2.</span></span>  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="66966-175">설치 후 Teams가 자동으로 시작되지 않도록 방지</span><span class="sxs-lookup"><span data-stu-id="66966-175">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="66966-176">MSI의 기본 동작은 사용자가 로그인하는 즉시 Teams 앱을 설치한 다음 자동으로 Teams를 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66966-176">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="66966-177">Teams가 설치된 후에 사용자를 위해 자동으로 시작하지 않도록 하는 경우 그룹 정책을 사용하여 MSI 설치 관리자에 대한 정책 설정을 설정하거나 자동 시작을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-177">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

### <a name="use-group-policy-recommended"></a><span data-ttu-id="66966-178">그룹 정책 사용(권장)</span><span class="sxs-lookup"><span data-stu-id="66966-178">Use Group Policy (recommended)</span></span>

<span data-ttu-id="66966-179">설치 그룹 정책 설정 후 **Microsoft Teams가** 자동으로 시작되지 않도록 방지를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-179">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="66966-180">사용자 구성\Policy\Administrative Templates\Microsoft Teams에서 이 정책 설정을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-180">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="66966-181">조직의 요구에 따라 정책 설정을 해제하거나 설정할 수 있기 때문에 권장되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="66966-181">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="66966-182">Teams가 설치되기 전에 이 정책 설정을 사용하도록 설정하면 사용자가 Windows에 로그인할 때 Teams가 자동으로 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-182">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="66966-183">사용자가 Teams에 처음으로 로그인하면 다음에 사용자가 로그인할 때 Teams가 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="66966-183">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="66966-184">자세한 내용은 그룹 정책 사용을 참조하여 설치 후 Teams가 자동으로 시작되지 [않도록 합니다.](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)</span><span class="sxs-lookup"><span data-stu-id="66966-184">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="66966-185">Teams를 이미 배포하고 Teams 자동 시작을 사용하지 않도록 설정하려는 경우 먼저 그룹 정책 설정을 원하는 값으로 설정한 다음, [사용자당 Teams](scripts/powershell-script-teams-reset-autostart.md) 자동 시작 재설정 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-185">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="66966-186">MSI 설치 관리자에 대한 자동 시작 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="66966-186">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="66966-187">다음과 같이 **OPTIONS="noAutoStart=true"** 매개 변수를 사용하여 MSI 설치 관리자에 대한 자동 시작을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-187">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="66966-188">32비트 버전의 경우:</span><span class="sxs-lookup"><span data-stu-id="66966-188">For the 32-bit version:</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="66966-189">64비트 버전의 경우:</span><span class="sxs-lookup"><span data-stu-id="66966-189">For the 64-bit version:</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="66966-190">사용자가 Windows에 로그인하면 Teams가 MSI를 사용하여 설치하고 Teams를 시작하는 바로 가기가 사용자의 데스크톱에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="66966-190">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="66966-191">사용자가 Teams를 수동으로 시작할 때까지 팀은 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-191">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="66966-192">사용자가 Teams를 수동으로 시작하면 사용자가 로그인할 때마다 Teams가 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="66966-192">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

<span data-ttu-id="66966-193">이러한 예제에서는 **ALLUSERS=1 매개 변수도** 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-193">Note that these examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="66966-194">이 매개 변수를 설정하면 Teams Machine-Wide 설치 관리자가 제어판의 프로그램 및 기능 및 앱에 & 모든 사용자에 대한 Windows 설정의 기능에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="66966-194">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="66966-195">그러면 모든 사용자가 컴퓨터에 관리자 자격 증명이 있는 경우 Teams를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-195">All users can then uninstall Teams if they have admin credentials on the computer.</span></span>

> [!Note]
> <span data-ttu-id="66966-196">MSI를 수동으로 실행하는 경우 권한 상승을 통해 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66966-196">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="66966-197">관리자 권한으로 실행하는 경우에도 권한 상승으로 실행하지 않고도 설치 관리자는 자동 시작을 사용하지 않도록 설정하는 옵션을 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66966-197">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
