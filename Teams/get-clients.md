---
title: Microsoft 팀 용 클라이언트 가져오기
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 사용할 수 있는 다양 한 클라이언트 (웹, 데스크톱 (Windows 및 Mac) 및 모바일 (Android 및 iOS)를 사용 하는 방법에 대해 알아봅니다.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3332f25366ea79d69bb95727f01651cb158de53
ms.sourcegitcommit: c2e315d0fcec742d2e1ba5ad90dffd1a1157a466
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/13/2019
ms.locfileid: "40002242"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="f191e-103">Microsoft 팀 용 클라이언트 가져오기</span><span class="sxs-lookup"><span data-stu-id="f191e-103">Get clients for Microsoft Teams</span></span> 


<span data-ttu-id="f191e-104">Microsoft 팀은 데스크톱 (Windows, Mac, Linux), 웹, 모바일 (Android 및 iOS)에 사용할 수 있는 클라이언트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="f191e-105">이러한 클라이언트는 모두 활성 인터넷 연결이 필요 하며 오프 라인 모드를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="f191e-106">2018 년 11 월 29 일부 터 Microsoft Store에서 제공 되는 Windows 10 S 용 Microsoft 팀 (Preview) 앱을 더 이상 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="f191e-107">대신 Windows 10 S 모드를 실행 하는 장치에 팀 데스크톱 클라이언트를 다운로드 하 여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="f191e-108">데스크톱 클라이언트를 다운로드 하려면으로 이동 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="f191e-109">Windows 10 S 모드를 실행 하는 장치에서 팀 데스크톱 클라이언트의 MSI 빌드를 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="f191e-110">Windows 10 S 모드에 대 한 자세한 내용은 [S 모드에서 Windows 10 소개](https://www.microsoft.com/windows/s-mode)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f191e-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="f191e-111">데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="f191e-111">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="f191e-112">Windows 데스크톱 클라이언트의 이점과이를 위해 계획 하는 방법 및 배포 하는 방법에 대 한 자세한 내용을 보려면 다음 세션을 시청 하세요. [팀 Windows 데스크톱 클라이언트](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="f191e-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="f191e-113">Microsoft 팀 데스크톱 클라이언트는 독립 실행형 응용 프로그램이 며 [Office 365 ProPlus 에서도 사용할 수 있습니다](https://docs.microsoft.com/deployoffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="f191e-113">The Microsoft Teams desktop client is a standalone application and is also [available in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="f191e-114">팀은 Windows (7 +), 32 비트 및 64 비트 버전, macOS (10.10 +), Linux (in `.deb` 및 `.rpm` formats)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-114">Teams is available for Windows (7+), both 32-bit and 64-bit versions, macOS (10.10+), and Linux (in `.deb` and `.rpm` formats.).</span></span> <span data-ttu-id="f191e-115">Windows에서 팀에는 .NET Framework 4.5 이상이 필요 합니다. 팀 설치 관리자가 없는 경우 설치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="f191e-116">Linux에서 apt 및 yum과 같은 패키지 관리자는 모든 요구 사항을 설치 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-116">On Linux, package managers such as apt and yum will try to install any requirements for you.</span></span> <span data-ttu-id="f191e-117">그러나이 경우에는 Linux에 팀을 설치 하기 전에 보고 된 요구 사항을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-117">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="f191e-118">데스크톱 클라이언트는 실시간 통신 지원 (오디오, 비디오 및 콘텐츠 공유)을 제공 하 여 팀 모임, 그룹 통화, 개인 일대일 통화를 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-118">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="f191e-119">데스크톱 클라이언트는 최종 사용자가 적절 한 로컬 권한을 갖고 있는 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) 경우 직접 다운로드 및 설치할 수 있습니다 (관리자 권한은 PC에 팀 클라이언트를 설치 하는 데는 필요 하지 않지만 Mac에는 필요 하지 않음).</span><span class="sxs-lookup"><span data-stu-id="f191e-119">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="f191e-120">IT 관리자는 조직의 컴퓨터에 설치 파일을 배포 하는 데 선호 하는 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-120">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="f191e-121">몇 가지 예로는 System Center Configuration Manager (Windows) 또는 Jamf Pro (macOS)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-121">Some examples include System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="f191e-122">Windows 배포용 MSI 패키지를 가져오려면 [msi를 사용 하 여 Microsoft 팀 설치](msi-deployment.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f191e-122">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="f191e-123">이러한 메커니즘을 통해 클라이언트를 배포 하는 것은 향후 업데이트에 대 한 것이 아니라 Microsoft 팀 클라이언트의 초기 설치에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-123">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="f191e-124">창을</span><span class="sxs-lookup"><span data-stu-id="f191e-124">Windows</span></span>

<span data-ttu-id="f191e-125">Windows 용 Microsoft 팀 설치는 32 비트 및 64 비트 아키텍처에서 다운로드 가능한 설치 관리자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-125">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="f191e-126">Microsoft 팀의 아키텍처 (32 비트 대 64 비트)는 설치 되어 있는 Windows 및 Office의 아키텍처와 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-126">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="f191e-127">Windows 클라이언트는 사용자 프로필에 있는 AppData 폴더에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-127">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="f191e-128">사용자의 로컬 프로필에 배포 하면 관리자 권한이 필요 하지 않고 클라이언트가 설치 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-128">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="f191e-129">Windows 클라이언트는 다음 위치를 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-129">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="f191e-130">% LocalAppData%\\Microsoft\\팀</span><span class="sxs-lookup"><span data-stu-id="f191e-130">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="f191e-131">% LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="f191e-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="f191e-132">% AppData%\\Microsoft\\팀</span><span class="sxs-lookup"><span data-stu-id="f191e-132">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="f191e-133">% LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="f191e-133">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="f191e-134">사용자가 처음 Microsoft 팀 클라이언트를 사용 하 여 전화를 시작 하면 사용자에 게 통신을 허용 하도록 요청 하는 Windows 방화벽 설정에 대 한 경고가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-134">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="f191e-135">경고가 해제 된 경우에도 호출이 작동 하기 때문에 사용자가이 메시지를 무시 하도록 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-135">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Windows 보안 알림 대화 상자 스크린샷.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="f191e-137">Windows 방화벽 구성은 "취소"를 선택 하 여 메시지가 해제 되는 경우에도 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-137">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="f191e-138">TCP 및 UDP 프로토콜에 대 한 Block 동작을 사용 하 여 cluster.exe에 대 한 두 개의 인바운드 규칙이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-138">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="f191e-139">Ac</span><span class="sxs-lookup"><span data-stu-id="f191e-139">Mac</span></span>

<span data-ttu-id="f191e-140">Mac 사용자는 macOS 컴퓨터에 INSTALLER.PKG 설치 파일을 사용 하 여 팀을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-140">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="f191e-141">Mac 클라이언트를 설치 하려면 관리자 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-141">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="f191e-142">MacOS 클라이언트는/Applications 폴더에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-142">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="f191e-143">INSTALLER.PKG 파일을 사용 하 여 팀 설치</span><span class="sxs-lookup"><span data-stu-id="f191e-143">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="f191e-144">[팀 다운로드 페이지](https://teams.microsoft.com/downloads)의 **Mac**에서 **다운로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-144">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="f191e-145">INSTALLER.PKG 파일을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-145">Double click the PKG file.</span></span>
3. <span data-ttu-id="f191e-146">설치 마법사의 지시에 따라 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-146">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="f191e-147">팀이/Applications 폴더에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-147">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="f191e-148">시스템 전체에 설치 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-148">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="f191e-149">설치 하는 동안 INSTALLER.PKG에서 관리자 자격 증명을 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-149">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="f191e-150">사용자가 관리자 인지 여부에 관계 없이 관리자 자격 증명을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-150">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="f191e-151">사용자가 현재 팀의 DMG 설치를 보유 하 고 INSTALLER.PKG 설치로 대체 하려는 경우 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-151">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="f191e-152">팀 앱을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-152">Exit the Teams app.</span></span>
2. <span data-ttu-id="f191e-153">팀 앱을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-153">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="f191e-154">INSTALLER.PKG 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-154">Install the PKG file.</span></span>

<span data-ttu-id="f191e-155">IT 관리자는 팀의 관리 되는 배포를 사용 하 여 Jamf Pro와 같은 조직의 모든 Mac에 설치 파일을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-155">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="f191e-156">INSTALLER.PKG를 설치 하는 중 문제가 발생 하면 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="f191e-156">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="f191e-157">이 문서의 끝부분에 있는 **피드백** 섹션에서 **제품 피드백**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-157">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="f191e-158">Linux</span><span class="sxs-lookup"><span data-stu-id="f191e-158">Linux</span></span>

<span data-ttu-id="f191e-159">사용자는 및 `.deb` `.rpm` 형식으로 네이티브 Linux 패키지를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-159">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="f191e-160">DEB 또는 RPM 패키지를 설치 하면 패키지 리포지토리가 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-160">Installing the DEB or RPM package will automatically install the package repository</span></span>
- <span data-ttu-id="f191e-161">DEB 다운로드`https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="f191e-161">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="f191e-162">RPM`https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="f191e-162">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="f191e-163">시스템의 패키지 관리자를 사용 하 여 자동 업데이트를 사용 하도록 설정 하는 서명 키가 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-163">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="f191e-164">그러나 다음https://packages.microsoft.com/keys/microsoft.asc)위치에서 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-164">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="f191e-165">Microsoft 팀은 매달 제공 되 고 리포지토리가 올바르게 설치 된 경우 시스템의 다른 패키지와 같은 방식으로 시스템 패키지 관리자가 자동 업데이트를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-165">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="f191e-166">버그를 찾았으면 클라이언트 내에서이를 사용 `Report a Problem` 하 여 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-166">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="f191e-167">알려진 문제는 [알려진 문제점](Known-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f191e-167">For known issues, see [Known Issues](Known-issues.md).</span></span>
> <span data-ttu-id="f191e-168">Linux 용 팀 지원이 필요한 경우 [Microsoft Q&A의 Linux 포럼 지원 채널](https://docs.microsoft.com/answers/topics/teams.html)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-168">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span></span> <span data-ttu-id="f191e-169">질문을 게시할 때 태그 `teams-linux` 를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-169">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="f191e-170">DEB 패키지를 사용 하 여 팀 설치</span><span class="sxs-lookup"><span data-stu-id="f191e-170">Install Teams using DEB package</span></span>

1. <span data-ttu-id="f191e-171">에서 https://aka.ms/getteams패키지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-171">Download the package from https://aka.ms/getteams.</span></span> <span data-ttu-id="f191e-172">(Linux 클라이언트는 제한 된 미리 보기 상태 이며 곧 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-172">(The Linux client is in limited preview and will launch soon.</span></span> <span data-ttu-id="f191e-173">다운로드 페이지에 Linux 클라이언트가 표시 되지 않으면 아직 시작 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-173">If you don't see the Linux client on the downloads page then it has not launched yet.)</span></span>
2. <span data-ttu-id="f191e-174">다음 중 하나를 사용 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-174">Install using one of the following:</span></span>  
    - <span data-ttu-id="f191e-175">관련 패키지 관리 도구를 열고 셀프 기반 Linux 앱 설치 프로세스를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-175">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="f191e-176">또는 터미널을 선호 하는 경우 다음을 입력 합니다.`sudo apt install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="f191e-176">Or if you love Terminal, type: `sudo apt install **teams download file**`</span></span>

<span data-ttu-id="f191e-177">를 입력 `Teams`하 여 작업을 통해서나 터미널을 통해 팀을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-177">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="f191e-178">RPM 패키지를 사용 하 여 팀 설치</span><span class="sxs-lookup"><span data-stu-id="f191e-178">Install Teams using RPM package</span></span>

1. <span data-ttu-id="f191e-179">에서 https://aka.ms/getteams패키지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-179">Download the package from https://aka.ms/getteams.</span></span> <span data-ttu-id="f191e-180">(Linux 클라이언트는 제한 된 미리 보기 상태 이며 곧 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-180">(The Linux client is in limited preview and will launch soon.</span></span> <span data-ttu-id="f191e-181">다운로드 페이지에 Linux 클라이언트가 표시 되지 않으면 아직 시작 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-181">If you don't see the Linux client on the downloads page then it has not launched yet.)</span></span>
2. <span data-ttu-id="f191e-182">다음 중 하나를 사용 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-182">Install using one of the following:</span></span>
    - <span data-ttu-id="f191e-183">관련 패키지 관리 도구를 열고 셀프 기반 Linux 앱 설치 프로세스를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-183">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="f191e-184">또는 터미널을 선호 하는 경우 다음을 입력 합니다.`sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="f191e-184">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="f191e-185">를 입력 `Teams`하 여 작업을 통해서나 터미널을 통해 팀을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-185">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span>

## <a name="web-client"></a><span data-ttu-id="f191e-186">웹 클라이언트</span><span class="sxs-lookup"><span data-stu-id="f191e-186">Web client</span></span> 

<span data-ttu-id="f191e-187">웹 클라이언트 ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753))는 다양 한 브라우저에서 사용할 수 있는 완전 한 기능적 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-187">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="f191e-188">웹 클라이언트는 webRTC를 사용 하 여 통화 및 모임을 지원 하므로 웹 브라우저에서 팀을 실행 하는 데 필요한 플러그 인 또는 다운로드가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-188">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="f191e-189">타사 쿠키를 허용 하도록 브라우저를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-189">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="f191e-190">웹 클라이언트는 연결 시 브라우저 버전 검색을 [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-190">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="f191e-191">지원 되지 않는 브라우저 버전이 발견 되 면 웹 인터페이스에 대 한 액세스를 차단 하 고 사용자가 데스크톱 클라이언트 또는 모바일 앱을 다운로드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-191">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="f191e-192">모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="f191e-192">Mobile clients</span></span>

<span data-ttu-id="f191e-193">Microsoft 팀 모바일 앱은 Android 및 iOS에서 사용할 수 있으며 채팅 기반 대화에 참여 하는 사용자에 게 전달 되며 피어 투 피어 오디오 통화를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-193">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="f191e-194">모바일 앱의 경우 관련 모바일 스토어 Google Play 및 Apple App Store로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-194">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="f191e-195">Windows Phone 앱은 2018 년 7 월 20 일에 만료 되었으며 더 이상 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-195">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="f191e-196">Microsoft 팀을 위한 지원 되는 모바일 플랫폼 모바일 앱은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-196">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="f191e-197">**Android**: 5.0 이상</span><span class="sxs-lookup"><span data-stu-id="f191e-197">**Android**: 5.0 or later</span></span>

-   <span data-ttu-id="f191e-198">**iOS**: 10.0 이상</span><span class="sxs-lookup"><span data-stu-id="f191e-198">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="f191e-199">팀이 예상 대로 작동 하도록 하려면 모바일 버전을 공용에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-199">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="f191e-200">모바일 앱은 해당 모바일 플랫폼의 앱 스토어를 통해 배포 되 고 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-200">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="f191e-201">MDM 또는 사이드 로딩을 통해 모바일 앱을 배포 하는 것은 Microsoft에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-201">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="f191e-202">모바일 앱이 지원 되는 모바일 플랫폼에 설치 된 후에는 버전이 현재 릴리스의 3 개월 이내에 제공 되는 경우 팀 모바일 앱이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-202">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![결정 지점을 가리키는 아이콘](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="f191e-204">판단 요점</span><span class="sxs-lookup"><span data-stu-id="f191e-204">Decision Point</span></span>         |<span data-ttu-id="f191e-205">사용자가 장치에 적절 한 Microsoft 팀 클라이언트를 설치 하는 것을 막는 제한 사항이 있나요?</span><span class="sxs-lookup"><span data-stu-id="f191e-205">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![다음 단계를 묘사하는 아이콘](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="f191e-207">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f191e-207">Next Steps</span></span>         |<span data-ttu-id="f191e-208">조직이 소프트웨어 설치를 제한 하는 경우 해당 프로세스가 Microsoft 팀과 호환 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-208">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="f191e-209">참고: PC 클라이언트 설치에는 관리자 권한이 필요 하지 않지만 Mac에 설치 하는 데는 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-209">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="f191e-210">클라이언트 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="f191e-210">Client update management</span></span>

<span data-ttu-id="f191e-211">클라이언트가 현재 Microsoft 팀 서비스에 의해 자동으로 업데이트 되므로 IT 관리자의 개입 없이도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-211">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="f191e-212">업데이트를 사용할 수 있는 경우 클라이언트는 업데이트를 자동으로 다운로드 하 고 앱에 특정 기간 동안 idled가 있는 경우 업데이트 프로세스가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-212">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="f191e-213">클라이언트측 구성</span><span class="sxs-lookup"><span data-stu-id="f191e-213">Client-side configurations</span></span>

<span data-ttu-id="f191e-214">현재 테 넌 트 관리자, PowerShell, 그룹 정책 개체 또는 레지스트리를 통해 클라이언트를 구성 하는 데 사용할 수 있는 지원 되는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-214">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="f191e-215">알림 설정</span><span class="sxs-lookup"><span data-stu-id="f191e-215">Notification settings</span></span>

<span data-ttu-id="f191e-216">현재 IT 관리자가 클라이언트 쪽 알림 설정을 구성할 수 있는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-216">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="f191e-217">모든 알림 옵션은 사용자가 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-217">All notification options are set by the user.</span></span> <span data-ttu-id="f191e-218">아래 그림에서는 기본 클라이언트 설정을 간략하게 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-218">The figure below outlines the default client settings.</span></span>

![알림 설정 스크린샷.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a><span data-ttu-id="f191e-220">샘플 PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="f191e-220">Sample PowerShell Script</span></span>

<span data-ttu-id="f191e-221">관리자 권한 administrator 계정의 컨텍스트에서 클라이언트 컴퓨터에 실행 해야 하는이 예제 스크립트는 c:\users.에 있는 각 사용자 폴더에 대 한 새 인바운드 방화벽 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-221">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="f191e-222">팀에서이 규칙을 발견 하면 팀 응용 프로그램에서 사용자가 팀 으로부터 처음 통화를 할 때 방화벽 규칙을 만들지 못하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f191e-222">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
