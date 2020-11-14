---
title: Microsoft Endpoint Configuration Manager를 사용 하 여 팀 설치
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jhreddy
audience: admin
description: Microsoft Endpoint Configuration Manager를 사용 하 여 Microsoft 팀을 일괄적으로 배포 하 여 사용자 또는 컴퓨터를 선택 합니다.
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
ms.openlocfilehash: 61b55a8cd734d4f63db4e3d6e1379c0ed235c038
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030414"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="2ab82-103">Microsoft Endpoint Configuration Manager를 사용 하 여 Microsoft 팀 설치</span><span class="sxs-lookup"><span data-stu-id="2ab82-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="2ab82-104">Windows 데스크톱 클라이언트의 이점,이를 위해 계획 하는 방법 및 배포 하는 방법에 대해 알아보려면 다음 세션을 시청 하세요: [팀 Windows 데스크톱 클라이언트](https://aka.ms/teams-clients).</span><span class="sxs-lookup"><span data-stu-id="2ab82-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients).</span></span>

<span data-ttu-id="2ab82-105">Microsoft 끝점 구성 관리자 또는 그룹 정책 또는 광범위 한 배포에 대 한 타사 배포 메커니즘을 사용 하기 위해 Microsoft는 관리자가 사용자 또는 컴퓨터를 선택 하기 위해 팀을 대량으로 배포 하는 데 사용할 수 있는 MSI 파일 (32 비트 및 64 비트)을 제공 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="2ab82-106">관리자는 이러한 파일을 사용 하 여 사용자가 팀 앱을 수동으로 다운로드할 필요가 없도록 팀을 원격으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="2ab82-107">배포 되는 경우 해당 컴퓨터에 로그인 하는 모든 사용자에 대해 팀이 자동으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="2ab82-108">(앱을 설치한 후 자동 시작을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="2ab82-109">[아래를 참조](#disable-auto-launch-for-the-msi-installer)하세요.) 컴퓨터에 패키지를 배포 하는 것이 좋으며,이는 컴퓨터의 모든 새 사용자도이 배포를 활용할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="2ab82-110">MSI 파일에 대 한 링크는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-110">These are the links to the MSI files:</span></span>

|<span data-ttu-id="2ab82-111">엔터티만</span><span class="sxs-lookup"><span data-stu-id="2ab82-111">Entity</span></span>  |<span data-ttu-id="2ab82-112">32 비트</span><span class="sxs-lookup"><span data-stu-id="2ab82-112">32-bit</span></span>      |<span data-ttu-id="2ab82-113">64 비트</span><span class="sxs-lookup"><span data-stu-id="2ab82-113">64-bit</span></span>      | <span data-ttu-id="2ab82-114">ARM64</span><span class="sxs-lookup"><span data-stu-id="2ab82-114">ARM64</span></span> |
|---------|---------|---------|-----------|
|<span data-ttu-id="2ab82-115">상업성</span><span class="sxs-lookup"><span data-stu-id="2ab82-115">Commercial</span></span>     | [<span data-ttu-id="2ab82-116">32 비트</span><span class="sxs-lookup"><span data-stu-id="2ab82-116">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="2ab82-117">64 비트</span><span class="sxs-lookup"><span data-stu-id="2ab82-117">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [<span data-ttu-id="2ab82-118">ARM64</span><span class="sxs-lookup"><span data-stu-id="2ab82-118">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|<span data-ttu-id="2ab82-119">미국 정부의 GCC</span><span class="sxs-lookup"><span data-stu-id="2ab82-119">Federal Government - GCC</span></span>     | [<span data-ttu-id="2ab82-120">32 비트</span><span class="sxs-lookup"><span data-stu-id="2ab82-120">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="2ab82-121">64 비트</span><span class="sxs-lookup"><span data-stu-id="2ab82-121">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[<span data-ttu-id="2ab82-122">ARM64</span><span class="sxs-lookup"><span data-stu-id="2ab82-122">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|<span data-ttu-id="2ab82-123">미국 정부-GCC 최고</span><span class="sxs-lookup"><span data-stu-id="2ab82-123">Federal Government - GCC High</span></span>    | [<span data-ttu-id="2ab82-124">32 비트</span><span class="sxs-lookup"><span data-stu-id="2ab82-124">32-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="2ab82-125">64 비트</span><span class="sxs-lookup"><span data-stu-id="2ab82-125">64-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[<span data-ttu-id="2ab82-126">ARM64</span><span class="sxs-lookup"><span data-stu-id="2ab82-126">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|<span data-ttu-id="2ab82-127">연방 정부-DoD</span><span class="sxs-lookup"><span data-stu-id="2ab82-127">Federal Government - DoD</span></span>     | [<span data-ttu-id="2ab82-128">32 비트</span><span class="sxs-lookup"><span data-stu-id="2ab82-128">32-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="2ab82-129">64 비트</span><span class="sxs-lookup"><span data-stu-id="2ab82-129">64-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [<span data-ttu-id="2ab82-130">ARM64</span><span class="sxs-lookup"><span data-stu-id="2ab82-130">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

<span data-ttu-id="2ab82-131">**성공적인 배포를 위해서는 다음에 유의 해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2ab82-131">**To ensure a successful deployment, be aware of the following:**</span></span>

- <span data-ttu-id="2ab82-132">64 비트 버전의 팀을 64 비트 운영 체제에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-132">Install the 64-bit version of Teams on 64-bit operating systems.</span></span> <span data-ttu-id="2ab82-133">32 비트 운영 체제에서 64 비트 버전의 팀을 설치 하려고 하면 설치에 실패 하 고 현재 오류 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-133">If you try to install the 64-bit version of Teams on a 32-bit operating system, the installation won't be successful and currently you won't receive an error message.</span></span>

- <span data-ttu-id="2ab82-134">고객 테 넌 트가 GCCH 또는 DoD 클라우드에 있는 경우 고객은 레지스트리의 **HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams** 키에 **cloudtype** 값을 추가 하 여 레지스트리의 초기 끝점을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-134">If the customer tenant is on the GCCH or DoD clouds, the customer should set the initial endpoint in the registry by adding the **CloudType** value to the **HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams** key in the registry.</span></span> <span data-ttu-id="2ab82-135">**Cloudtype** 에 대 한 형식은 **DWORD** 이 고 값은 (0 = 설정 되지 않음, 1 = 상업용, 2 = GCC, 3 = GCCH, 4 = DOD)입니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-135">The type for **CloudType** is **DWORD** and values are (0 = Unset, 1 = commercial, 2 = GCC, 3 = GCCH, 4 = DOD).</span></span> <span data-ttu-id="2ab82-136">레지스트리 키를 사용 하 여 끝점을 설정 하면 팀에서 사전 로그인 연결을 위해 올바른 클라우드 끝점에 연결 하도록 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-136">Setting the endpoint with the registry key restricts Teams to connecting to the correct cloud endpoint for pre-sign-in connectivity with Teams.</span></span>

- <span data-ttu-id="2ab82-137">팀은 enterprise 용 Microsoft 365 앱 배포에도 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-137">Teams can also be included with a deployment of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="2ab82-138">자세한 내용은 microsoft [365 앱을 사용 하 여 엔터프라이즈에 대 한 Microsoft 팀 배포](https://docs.microsoft.com/deployoffice/teams-install)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab82-138">For more information, see [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

- <span data-ttu-id="2ab82-139">Microsoft 끝점 구성 관리자에 대 한 자세한 내용은 [구성 관리자 란?](https://docs.microsoft.com/configmgr/core/understand/introduction) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab82-139">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction)</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="2ab82-140">배포 절차 (권장)</span><span class="sxs-lookup"><span data-stu-id="2ab82-140">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="2ab82-141">최신 패키지를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-141">Retrieve the latest package.</span></span>
2. <span data-ttu-id="2ab82-142">MSI에서 미리 채워 온 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-142">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="2ab82-143">가능 하면 컴퓨터에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-143">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="2ab82-144">Microsoft 팀 MSI 패키지가 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="2ab82-144">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="2ab82-145">PC 설치</span><span class="sxs-lookup"><span data-stu-id="2ab82-145">PC installation</span></span>

<span data-ttu-id="2ab82-146">팀 MSI는 프로그램 파일에 설치 관리자를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-146">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="2ab82-147">사용자가 새 Windows 사용자 프로필에 로그인 할 때마다 설치 프로그램이 시작 되 고 팀 앱의 복사본이 해당 사용자의 폴더에 설치 됩니다 `AppData` .</span><span class="sxs-lookup"><span data-stu-id="2ab82-147">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's `AppData` folder.</span></span> <span data-ttu-id="2ab82-148">사용자가 폴더에 이미 팀 앱을 설치한 경우 `AppData` MSI 설치 관리자가 해당 사용자에 대 한 프로세스를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-148">If a user already has the Teams app installed in the `AppData` folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="2ab82-149">MSI를 사용 하 여 업데이트를 배포 하는 경우 클라이언트는 서비스에서 새 버전이 제공 될 때 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-149">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="2ab82-150">최신 설치 관리자를 다시 배포 하려면 아래 설명 된 MSI 재배포 프로세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-150">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="2ab82-151">이전 버전의 MSI 패키지를 배포 하는 경우 클라이언트는 사용자에 대해 가능 하면 VDI 환경에서 제외 하 고 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-151">If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="2ab82-152">오래 된 버전이 배포 되는 경우 MSI는 사용자가 팀을 사용할 수 있도록 앱 업데이트를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-152">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ab82-153">기본 위치는 64 비트 운영 체제 및 32 비트 운영 체제의 C:\Program Files\Teams Installer에 있는 C:\Program Files (x86) \Teams 설치 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-153">The default location is C:\Program Files (x86)\Teams Installer on 64-bit operating systems and C:\Program Files\Teams Installer on 32-bit operating systems.</span></span>
> <span data-ttu-id="2ab82-154">기본 설치 위치를 변경 하는 것은 업데이트 흐름이 중단 될 수 있으므로 권장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-154">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="2ab82-155">오래 된 버전을 보유 하면 결국 사용자가 서비스에 액세스 하지 못하도록 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-155">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="2ab82-156">대상 컴퓨터 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ab82-156">Target computer requirements</span></span>

- <span data-ttu-id="2ab82-157">.NET framework 4.5 이상</span><span class="sxs-lookup"><span data-stu-id="2ab82-157">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="2ab82-158">Windows 8.1 이상</span><span class="sxs-lookup"><span data-stu-id="2ab82-158">Windows 8.1 or later</span></span>
- <span data-ttu-id="2ab82-159">Windows Server 2012 R2 이상</span><span class="sxs-lookup"><span data-stu-id="2ab82-159">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="2ab82-160">각 사용자 프로필에 대해 3gb의 디스크 공간 (권장)</span><span class="sxs-lookup"><span data-stu-id="2ab82-160">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="2ab82-161">VDI 설치</span><span class="sxs-lookup"><span data-stu-id="2ab82-161">VDI installation</span></span>

<span data-ttu-id="2ab82-162">VDI에서 팀 데스크톱 앱을 배포 하는 방법에 대 한 자세한 지침은 [가상화 된 데스크톱 인프라 팀](teams-for-vdi.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab82-162">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="2ab82-163">정리 및 다시 배포 절차</span><span class="sxs-lookup"><span data-stu-id="2ab82-163">Clean up and redeployment procedure</span></span>

<span data-ttu-id="2ab82-164">사용자가 사용자 프로필에서 팀을 제거 하는 경우 MSI 설치 관리자는 사용자가 팀 앱을 제거 하 고 더 이상 해당 사용자 프로필에 대 한 팀을 설치 하지 않은 것을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-164">If a user uninstalls Teams from their user profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that user profile.</span></span> <span data-ttu-id="2ab82-165">제거 된 특정 컴퓨터에서이 사용자의 팀을 다시 배포 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-165">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ab82-166">다음 단계에는 레지스트리를 수정 하는 방법에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-166">The next steps contain information about how to modify the registry.</span></span> <span data-ttu-id="2ab82-167">레지스트리를 수정 하기 전에 백업 하 고 문제가 발생 하는 경우 레지스트리를 복원 하는 방법을 알고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-167">Make sure that you back up the registry before you modify it and that you know how to restore the registry if a problem occurs.</span></span> <span data-ttu-id="2ab82-168">레지스트리를 백업, 복원 및 수정 하는 방법에 대 한 자세한 내용은 [고급 사용자를 위한 Windows 레지스트리 정보](https://support.microsoft.com/help/256986)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab82-168">For more information about how to back up, restore, and modify the registry, see [Windows registry information for advanced users](https://support.microsoft.com/help/256986).</span></span>

1. <span data-ttu-id="2ab82-169">모든 사용자 프로필에 대해 설치 된 팀 앱을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-169">Uninstall the Teams app installed for every user profile.</span></span> <span data-ttu-id="2ab82-170">자세한 내용은 [Microsoft 팀 제거](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2ab82-170">For more information, see [Uninstall Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).</span></span>
2. <span data-ttu-id="2ab82-171">재귀적으로 디렉터리를 삭제 `%localappdata%\Microsoft\Teams\` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-171">Delete the directory recursively under `%localappdata%\Microsoft\Teams\`.</span></span>
3. <span data-ttu-id="2ab82-172">`HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi`레지스트리 값을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-172">Delete the `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` registry value.</span></span>
4. <span data-ttu-id="2ab82-173">해당 특정 컴퓨터에 MSI 패키지를 다시 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-173">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="2ab82-174">[팀 배포 정리 스크립트](scripts/powershell-script-deployment-cleanup.md) 를 사용 하 여 1 ~ 2 단계를 완료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-174">You can also use our [Teams deployment clean up script](scripts/powershell-script-deployment-cleanup.md) to complete steps 1 and 2.</span></span>  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="2ab82-175">설치 후 팀이 자동으로 시작 되지 않도록 방지</span><span class="sxs-lookup"><span data-stu-id="2ab82-175">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="2ab82-176">MSI의 기본 동작은 사용자가 로그인 하는 즉시 팀 앱을 설치한 다음 팀을 자동으로 시작 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-176">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="2ab82-177">사용자가 설치 된 후 팀이 자동으로 시작 되지 않도록 하려면 그룹 정책을 사용 하 여 정책 설정을 설정 하거나 MSI 설치 관리자에 대 한 자동 시작을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-177">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

### <a name="use-group-policy-recommended"></a><span data-ttu-id="2ab82-178">그룹 정책 사용 (권장)</span><span class="sxs-lookup"><span data-stu-id="2ab82-178">Use Group Policy (recommended)</span></span>

<span data-ttu-id="2ab82-179">**설치 후 Microsoft 팀이 자동으로 시작 되지 않도록** 설정 그룹 정책 설정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-179">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="2ab82-180">사용자 Configuration\Policies\Administrative Templates\Microsoft 팀에서이 정책 설정을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-180">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="2ab82-181">조직의 요구 사항에 따라 정책 설정을 끄거나 켤 수 있으므로이 방법을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-181">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="2ab82-182">팀을 설치 하기 전에이 정책 설정을 사용 하면 사용자가 Windows에 로그인 할 때 팀이 자동으로 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-182">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="2ab82-183">사용자가 처음으로 팀에 로그인 한 후에는 다음에 사용자가 로그인 할 때 팀이 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-183">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="2ab82-184">자세한 내용은 그룹 정책 사용을 참조 하 여 [팀이 설치 후 자동으로 시작 되지 않도록](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-184">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="2ab82-185">이미 팀을 배포 했으며 팀 자동 시작을 사용 하지 않도록 설정 하려는 경우 먼저 그룹 정책 설정을 원하는 값으로 설정한 다음 팀에서 사용자 기준으로 자동 시작 스크립트를 [다시](scripts/powershell-script-teams-reset-autostart.md) 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-185">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="2ab82-186">MSI 설치 관리자에 대 한 자동 시작 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="2ab82-186">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="2ab82-187">다음과 같이 **옵션 = "noAutoStart 시작 = true"** 매개 변수를 사용 하 여 MSI 설치 관리자에 대 한 자동 실행을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-187">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="2ab82-188">32 비트 버전의 경우:</span><span class="sxs-lookup"><span data-stu-id="2ab82-188">For the 32-bit version:</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="2ab82-189">64 비트 버전의 경우:</span><span class="sxs-lookup"><span data-stu-id="2ab82-189">For the 64-bit version:</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="2ab82-190">사용자가 Windows에 로그인 하면 팀이 MSI와 함께 설치 되 고 팀 시작에 대 한 바로 가기가 사용자의 데스크톱에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-190">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="2ab82-191">팀은 사용자가 수동으로 팀을 시작할 때까지 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-191">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="2ab82-192">사용자가 수동으로 팀을 시작 하면 사용자가 로그인 할 때마다 팀이 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-192">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

<span data-ttu-id="2ab82-193">이러한 예제에서는 **ALLUSERS = 1** 매개 변수도 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-193">Note that these examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="2ab82-194">이 매개 변수를 설정 하면 제어판의 프로그램 및 기능 및 컴퓨터의 모든 사용자에 대 한 Windows 설정의 앱 & 기능에 팀 Machine-Wide 설치 프로그램이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-194">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="2ab82-195">모든 사용자는 컴퓨터에 관리자 자격 증명이 있는 경우 팀을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-195">All users can then uninstall Teams if they have admin credentials on the computer.</span></span>

> [!Note]
> <span data-ttu-id="2ab82-196">MSI를 수동으로 실행 하는 경우 관리자 권한으로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-196">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="2ab82-197">관리자 권한으로 실행 하는 경우에도 권한 상승으로이를 실행 하지 않으면 설치 관리자가 자동 시작을 사용 하지 않도록 설정 하는 옵션을 구성할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ab82-197">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
