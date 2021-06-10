---
title: Microsoft Teams 룸 사용하여 Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: 대규모 배포에서 Microsoft Teams 룸 배포하는 방법을 Microsoft Endpoint Configuration Manager.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: 2348d0f3e9d94aed80494155fbaab8288ddd97a6
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410114"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="4ea50-103">Microsoft Teams 룸 사용하여 Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4ea50-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="4ea50-104">이 문서에서는 Microsoft Teams 룸 배포를 만드는 데 필요한 모든 정보를 Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="4ea50-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="4ea50-105">Configuration Manager에서 제공하는 사용하기 쉬운 방법을 사용하여 운영 체제 및 기타 애플리케이션을 여러 대상 디바이스에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="4ea50-106">아래 설명된 방법을 사용하여 Configuration Manager 구성을 안내하고 조직에 필요한 경우 이 지침 전체에 제공된 샘플 패키지 및 스크립트를 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Microsoft Teams 룸 사용하여 배포 프로세스 변경](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="4ea50-108">이 솔루션은 테스트 기반 배포에서 Surface Pro 테스트했습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="4ea50-109">표준을 기반으로 하지 않는 구성에 대한 제조업체의 지침을 Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="4ea50-109">Follow the manufacturer's guidelines for configurations that aren't based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="4ea50-110">전제요소 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="4ea50-110">Validate prerequisites</span></span>

<span data-ttu-id="4ea50-111">Configuration manager를 Microsoft Teams 룸 배포하려면 다음 요구 사항 및 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="4ea50-112">Microsoft Endpoint Configuration Manager 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ea50-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="4ea50-113">Microsoft Endpoint Configuration Manager 버전은 1706 이상이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="4ea50-114">1710 이상을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="4ea50-115">구성 [관리자에서](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) Windows 10 지원에 대해 알아보고 구성 관리자가 지원하는 Windows 10 버전에 대해 자세히 알아보고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-115">Check out [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="4ea50-116">지원되는 버전의 WINDOWS ADK(평가 및 배포 키트)를 Windows 10 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="4ea50-117">다양한 버전의 [Configuration Manager에서](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) 사용할 Windows 10 ADK 버전을 참조하고 배포에 올바른 버전이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-117">See the versions of the [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="4ea50-118">사이트 시스템 서버는 배포 지점 역할이 할당되어 있어야 합니다. 네트워크 시작 배포를 사용하도록 설정하려면 [PXE(Preboot 실행 환경)](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) 지원에 부트 이미지를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="4ea50-119">PXE 지원을 사용하도록 설정하지 않은 경우 배포에 [부팅 가능한](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 미디어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-119">If PXE support isn't enabled, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="4ea50-120">새 컴퓨터(베어 메탈) 배포 시나리오를 지원하도록 네트워크 액세스 계정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="4ea50-121">네트워크 액세스 계정 구성에 대한 자세한 내용은 Configuration Manager에서 사용되는 [계정을 참조하세요.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="4ea50-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="4ea50-122">동일한 이미지를 여러 [](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)단위에 동시에 배포할 가능성이 Microsoft Teams 룸 멀티캐스트 지원을 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-122">We recommend that you enable [multicast support](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you're likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="4ea50-123">네트워킹 요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ea50-123">Networking requirements</span></span>

-   <span data-ttu-id="4ea50-124">네트워크에는 DHCP(동적 호스트 구성 프로토콜) 서버가 구성되어 있습니다. 이 서버는 서브넷에 대한 자동 IP 주소 배포를 위해 Microsoft Teams 룸 단위가 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ea50-125">DHCP 임대 기간은 이미지 배포 기간보다 긴 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="4ea50-126">그렇지 않으면 배포가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="4ea50-127">스위치 및 VLA(가상 런)를 포함한 네트워크는 PXE를 지원하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="4ea50-128">IP 도우미 및 PXE 구성에 대한 자세한 내용은 네트워크 공급업체를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ea50-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="4ea50-129">또는 PXE [](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 지원을 사용하도록 설정하지 않은 경우 배포에 부팅 가능한 미디어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-129">Alternatively, you can use [bootable media](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn't enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ea50-130">Surface Pro 디바이스의 경우 네트워크에서 부팅(PXE 부팅)은 Microsoft의 이더넷 어댑터 또는 도킹 스테이션을 사용하는 경우만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="4ea50-131">타사 이더넷 어댑터는 PXE 부팅을 지원하지 Surface Pro.</span><span class="sxs-lookup"><span data-stu-id="4ea50-131">Third-party Ethernet adapters don't support PXE boot with Surface Pro.</span></span> <span data-ttu-id="4ea50-132">자세한 [내용은 이더넷 어댑터](/surface/ethernet-adapters-and-surface-device-deployment) 및 Surface 배포를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ea50-132">See [Ethernet adapters and Surface deployment](/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="4ea50-133">운영 Microsoft Endpoint Configuration Manager 배포를 위한 시스템 구성</span><span class="sxs-lookup"><span data-stu-id="4ea50-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="4ea50-134">이 문서에서는 구성 관리자 배포가 정상인 것으로 가정하고 구성 관리자를 처음부터 배포하고 구성하는 데 필요한 모든 단계를 자세히 설명하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn't detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="4ea50-135">문서 및 문서에 [대한](/configmgr/) 구성 지침은 Microsoft Endpoint Configuration Manager 리소스입니다. 아직 구성 관리자를 배포하지 않은 경우 이러한 리소스를 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-135">The [documentation and the configuration guidance](/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven't yet deployed Configuration Manager.</span></span>

<span data-ttu-id="4ea50-136">다음 지침을 사용하여 OSD(운영 체제 배포) 기능이 올바르게 구성되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="4ea50-137">구성 관리자 유효성 검사 및 업그레이드</span><span class="sxs-lookup"><span data-stu-id="4ea50-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="4ea50-138">Configuration Manager 콘솔에서 관리  업데이트 및 \> **서비스로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="4ea50-139">아직 설치되지 않은 설치된 빌드 및 적용 가능한 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-139">Check the installed build and applicable updates that haven't been installed yet.</span></span>

3.  <span data-ttu-id="4ea50-140">구성 [관리자에서 Windows 10 지원 검토;](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) 배포를 업그레이드해야 하는 경우 설치하려는 업데이트를 선택한 다음 **다운로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-140">Review [Support for Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="4ea50-141">다운로드가 완료되면 업데이트를 선택한 다음 업데이트 팩 **설치를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="4ea50-142">PXE 및 멀티캐스트를 지원하도록 배포 지점 구성</span><span class="sxs-lookup"><span data-stu-id="4ea50-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="4ea50-143">Configuration Manager 콘솔에서 관리 배포 **지점** \> **으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="4ea50-144">배포에 사용할 배포 지점 서버를 선택한 Microsoft Teams 룸 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="4ea50-145">**PXE 탭을 선택하고** 다음 설정을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="4ea50-146">클라이언트에 대한 PXE 지원 사용</span><span class="sxs-lookup"><span data-stu-id="4ea50-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="4ea50-147">이 배포 지점이 들어오는 PXE 요청에 응답하도록 허용</span><span class="sxs-lookup"><span data-stu-id="4ea50-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="4ea50-148">알 수 없는 컴퓨터 지원 사용</span><span class="sxs-lookup"><span data-stu-id="4ea50-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="4ea50-149">*선택 사항:* 멀티캐스트 지원을 사용하도록 설정하려면 **Multicast** 탭을 선택하고 다음 설정을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="4ea50-150">다중 캐스트를 사용하여 여러 클라이언트에 동시에 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="4ea50-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="4ea50-151">네트워크 팀의 권장에 따라 UDP 포트 범위 구성</span><span class="sxs-lookup"><span data-stu-id="4ea50-151">Configure the UDP port range as per your network team's recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="4ea50-152">네트워크 액세스 계정 구성</span><span class="sxs-lookup"><span data-stu-id="4ea50-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="4ea50-153">Configuration Manager 콘솔에서 관리  사이트 구성 \>  \> **사이트로 이동한** 다음 사이트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="4ea50-154">설정  그룹에서 사이트 구성 **요소** 소프트웨어 배포 구성 \> **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="4ea50-155">네트워크 **액세스 계정 탭을** 선택합니다. 하나 이상의 계정을 설정한 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="4ea50-156">계정은 배포 지점 서버의 네트워크에서  이 컴퓨터에 액세스하는 경우를 제외하고는 특별한 권한이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-156">The accounts don't need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="4ea50-157">일반 도메인 사용자 계정이 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="4ea50-158">자세한 내용은 [Configuration Manager 에 사용되는 계정을 참조하세요.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)</span><span class="sxs-lookup"><span data-stu-id="4ea50-158">For more information, see [Accounts used in Configuration Manager](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="4ea50-159">부팅 이미지 구성</span><span class="sxs-lookup"><span data-stu-id="4ea50-159">Configure a boot image</span></span>

1.  <span data-ttu-id="4ea50-160">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** 운영 체제 \> **부팅** \> **이미지로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="4ea50-161">부팅 **이미지(x64)를** 선택한 다음 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="4ea50-162">데이터 원본 **탭을 선택하고** PXE 사용 배포 지점에서 이 부팅 이미지 **배포를 사용하도록 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="4ea50-163">필수 구성 요소를 설치하려면 선택적 **구성** 요소 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="4ea50-164">별 아이콘을 선택하고 **HTML(WinPE-HTA)을 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="4ea50-165">확인을 **선택하여** 부팅 이미지에 HTML 애플리케이션 지원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="4ea50-166">*선택 사항:* 배포 환경을 사용자 지정하려면 사용자 지정 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="4ea50-167">배포 **중에** 명령 프롬프트에 대한 액세스 권한이 있는 경우 명령 지원(테스트 전용)을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="4ea50-168">이 기능을 사용하도록 설정하면 배포 중에 **F8을** 선택하여 명령 프롬프트를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="4ea50-169">배포 중에 표시할 사용자 지정 배경 이미지를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="4ea50-170">이미지를 설정하려면 사용자 지정 배경 이미지 파일 지정(UNC 경로)을 사용하도록 **설정하고** 배경을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="4ea50-171">묻는 질문이 있는 **경우 예를 선택하고** 업데이트된 부팅 이미지를 배포 지점에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="4ea50-172">자세한 내용은 Configuration Manager를 사용하여 [부팅 이미지 관리를 참조하세요.](/configmgr/osd/get-started/manage-boot-images)</span><span class="sxs-lookup"><span data-stu-id="4ea50-172">For more information, see [Manage boot images with Configuration Manager](/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="4ea50-173">부팅 가능한 USB 미디어를 만들어 PXE 지원이 없는 환경에 대한 Configuration Manager 작업 시퀀스 기반 배포를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="4ea50-174">부팅 가능한 미디어에는 부트 이미지, 선택적 미리 설정 명령 및 필요한 파일 및 구성 관리자 이진 파일만 포함되어 있으며, 나머지 배포 프로세스의 경우 Windows PE로 부팅하고 Configuration Manager에 연결하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="4ea50-175">자세한 내용은 부팅 가능한 [미디어 만들기 를 참조하세요.](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)</span><span class="sxs-lookup"><span data-stu-id="4ea50-175">For more information, see [Create bootable media](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="4ea50-176">Configuration Manager 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="4ea50-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ea50-177">각 SRS 설치 관리자 버전에 필요한 운영 체제 버전은 모든 MSI 릴리스에 따라 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="4ea50-178">특정 MSI에 대한 최상의 운영 체제 버전을 확인하려면 콘솔 설정 스크립트를 한 번 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="4ea50-179">자세한 내용은 을 사용하여 Microsoft Teams 룸 [배포를 Microsoft Endpoint Configuration Manager.](rooms-scale.md)</span><span class="sxs-lookup"><span data-stu-id="4ea50-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="4ea50-180">Configuration Manager는 여러 패키지를 배포하고 구성해야 Microsoft Teams 룸 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="4ea50-181">다음 패키지를 만들고 구성한 다음 배포 지점 서버 역할이 할당된 Configuration Manager 사이트 시스템에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="4ea50-182">**패키지 이름**</span><span class="sxs-lookup"><span data-stu-id="4ea50-182">**Package name**</span></span>                     | <span data-ttu-id="4ea50-183">**유형**</span><span class="sxs-lookup"><span data-stu-id="4ea50-183">**Type**</span></span>               | <span data-ttu-id="4ea50-184">**설명**</span><span class="sxs-lookup"><span data-stu-id="4ea50-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="4ea50-185">SRS v2 - SRS 애플리케이션 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="4ea50-186">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-186">Software package</span></span>       | <span data-ttu-id="4ea50-187">배포 키트에 Microsoft Teams 룸 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="4ea50-188">SRS v2 - Sysprep 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="4ea50-189">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-189">Software package</span></span>       | <span data-ttu-id="4ea50-190">사용자 지정 단위를 Unattended.xml 패키지 Microsoft Teams 룸 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="4ea50-191">SRS v2 - Set-SRSComputerName 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="4ea50-192">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-192">Software package</span></span>       | <span data-ttu-id="4ea50-193">배포 중에 컴퓨터 이름을 할당하는 HTA(HTML 애플리케이션)에 대한 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="4ea50-194">SRS v2 - SRS 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4ea50-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="4ea50-195">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-195">Software package</span></span>       | <span data-ttu-id="4ea50-196">앱의 배포를 Microsoft Teams 룸 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="4ea50-197">SRS v2 - OS 업데이트 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="4ea50-198">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-198">Software package</span></span>       | <span data-ttu-id="4ea50-199">필수 운영 체제 업데이트를 배포하는 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="4ea50-200">SRS v2 - 루트 인증서 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="4ea50-201">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-201">Software package</span></span>       | <span data-ttu-id="4ea50-202">선택 사항 - 루트 인증서를 배포하는 패키지(도메인에 가입된 단위에는 필요하지 않습니다)</span><span class="sxs-lookup"><span data-stu-id="4ea50-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="4ea50-203">SRS v2 - Microsoft Monitoring Agent 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="4ea50-204">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-204">Software package</span></span>       | <span data-ttu-id="4ea50-205">선택 사항 - Microsoft Operations Management Suite 에이전트를 배포하고 구성하는 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="4ea50-206">SRS v2 - WinPE 배경 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="4ea50-207">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-207">Software package</span></span>       | <span data-ttu-id="4ea50-208">부팅 이미지와 함께 사용할 사용자 지정 배경 이미지에 대한 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="4ea50-209">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4ea50-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="4ea50-210">운영 체제 이미지</span><span class="sxs-lookup"><span data-stu-id="4ea50-210">Operating system image</span></span> | <span data-ttu-id="4ea50-211">운영 체제 설치 파일의 패키지(install.wim)</span><span class="sxs-lookup"><span data-stu-id="4ea50-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="4ea50-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="4ea50-212">Surface Pro</span></span>                          | <span data-ttu-id="4ea50-213">드라이버 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-213">Driver package</span></span>         | <span data-ttu-id="4ea50-214">Microsoft용 디바이스 드라이버 및 펌웨어에 대한 Surface Pro</span><span class="sxs-lookup"><span data-stu-id="4ea50-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="4ea50-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="4ea50-215">Surface Pro 4</span></span>                        | <span data-ttu-id="4ea50-216">드라이버 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-216">Driver package</span></span>         | <span data-ttu-id="4ea50-217">Microsoft용 디바이스 드라이버 및 펌웨어에 대한 Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="4ea50-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="4ea50-218">자세한 내용은 Configuration Manager의 패키지 [및 프로그램을 참조하세요.](/configmgr/apps/deploy-use/packages-and-programs)</span><span class="sxs-lookup"><span data-stu-id="4ea50-218">For more information, see [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="4ea50-219">패키지 원본 파일에 대한 폴더 만들기</span><span class="sxs-lookup"><span data-stu-id="4ea50-219">Create folders for the package source files</span></span>

<span data-ttu-id="4ea50-220">Configuration Manager는 패키지 원본 파일을 처음 만들 때 및 업데이트할 때 특정 폴더 구조로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-220">Configuration Manager requires package source files to be organized in a specific folder structure when they're first created and when they're updated.</span></span>

<span data-ttu-id="4ea50-221">중앙 관리 사이트 또는 기본 Microsoft Endpoint Configuration Manager 또는 패키지 원본 파일을 호스트하는 데 사용하는 서버 공유에서 다음 폴더 구조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you're using to host package source files:</span></span>

-   <span data-ttu-id="4ea50-222">SRS v2 - Microsoft Monitoring Agent 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="4ea50-223">SRS v2 - OS 업데이트 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="4ea50-224">SRS v2 - 루트 인증서 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="4ea50-225">SRS v2 - Set-SRSComputerName 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="4ea50-226">SRS v2 - SRS 애플리케이션 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="4ea50-227">SRS v2 - SRS 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4ea50-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="4ea50-228">SRS v2 - Sysprep 패키지</span><span class="sxs-lookup"><span data-stu-id="4ea50-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="4ea50-229">드라이버</span><span class="sxs-lookup"><span data-stu-id="4ea50-229">Drivers</span></span>
    -   <span data-ttu-id="4ea50-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="4ea50-230">Surface Pro</span></span>
    -   <span data-ttu-id="4ea50-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="4ea50-231">Surface Pro 4</span></span>
-   <span data-ttu-id="4ea50-232">운영 체제</span><span class="sxs-lookup"><span data-stu-id="4ea50-232">Operating Systems</span></span>
    -   <span data-ttu-id="4ea50-233">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4ea50-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="4ea50-234">패키지의 [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) 폴더 구조, 사용해야 하는 스크립트 및 가져오기해야 하는 작업 시퀀스 템플릿을 포함하는 zip 파일을 다운로드하여 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="4ea50-235">모니터링 에이전트 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="4ea50-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="4ea50-236">에서 모니터링 에이전트를 <https://go.microsoft.com/fwlink/?LinkId=828603> 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="4ea50-237">명령 프롬프트 창을 열고 명령 프롬프트에 **Microsoft Monitoring Agent /C를** 입력하여 **패키지를 SRS v2 -** Microsoft Monitoring AgentMMASetup-AMD64.exe 패키지 폴더로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="4ea50-238">Configuration Manager 콘솔에서 **Software Library** 애플리케이션 \> **관리 패키지로 이동한** 다음 패키지 \>  **만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="4ea50-239">다음 정보를 입력하여 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="4ea50-240">이름<strong>: SRS v2 - Microsoft Monitoring Agent 패키지</strong></span><span class="sxs-lookup"><span data-stu-id="4ea50-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="4ea50-241">제조업체<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="4ea50-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="4ea50-242">버전<strong>: 8.1.11081.0(다운로드한</strong> 설치 파일의 버전을 입력합니다)</span><span class="sxs-lookup"><span data-stu-id="4ea50-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="4ea50-243">이 **패키지에** 원본 파일이 포함된 확인란을 선택하고 **SRS v2 -** Microsoft Monitoring Agent 패키지 폴더에 대한 경로를 입력한 다음 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="4ea50-244">프로그램 **만들기 안 를 선택한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="4ea50-245">설정 **확인 페이지를 검토한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="4ea50-246">닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="4ea50-247">운영 체제 업데이트 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="4ea50-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="4ea50-248">**SRS v2 - OS 업데이트** 패키지 폴더에서 새 PowerShell **스크립트를Install-SRSv2-OS-Updates.ps1.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="4ea50-249">아래 스크립트를Install-SRSv2-OS-Updates.ps1 **스크립트를** 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="4ea50-250">또는 여기에서 Install-SRSv2-OS-Updates.ps1 스크립트를 다운로드할 수 [있습니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="4ea50-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. <span data-ttu-id="4ea50-251">필수 업데이트 패키지를 Windows 폴더에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="4ea50-252">이 문서가 게시된 [당시에는 KB4056892만](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="4ea50-253">콘솔 [Microsoft Teams 룸](console.md)구성을 확인하여 다른 업데이트가 필요한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="4ea50-254">Configuration Manager 콘솔에서 **Software Library** 애플리케이션 \> **관리 패키지로 이동한** 다음 패키지 \>  **만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="4ea50-255">다음 정보를 입력하여 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="4ea50-256">이름: **SRS v2 – OS 업데이트 패키지**</span><span class="sxs-lookup"><span data-stu-id="4ea50-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="4ea50-257">제조업체: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="4ea50-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="4ea50-258">버전: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="4ea50-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="4ea50-259">원본 **파일이** 포함된 이 패키지를 선택하고 **SRS v2 - OS** 업데이트 패키지 폴더에 대한 경로를 입력한 다음 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="4ea50-260">프로그램 **만들기 안 를 선택한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="4ea50-261">설정 **확인 페이지를 검토한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="4ea50-262">닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="4ea50-263">루트 인증서 패키지 만들기(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="4ea50-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="4ea50-264">Active Directory 도메인에 조인되지 않는 디바이스에 대한 루트 인증서를 배포하기 위해 이 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-264">You create this package to distribute the root certificate for devices that won't be joined to an Active Directory domain.</span></span> <span data-ttu-id="4ea50-265">다음 조건이 모두 적용되는 경우만 이 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="4ea50-266">배포에는 온-프레미스 Lync 또는 비즈니스용 Skype 서버.</span><span class="sxs-lookup"><span data-stu-id="4ea50-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="4ea50-267">Microsoft Teams 룸 단위는 도메인 멤버 대신 작업에서 작동하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="4ea50-268">루트 인증서를 **SRS v2 – 루트 인증서 패키지 폴더에 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="4ea50-269">Configuration Manager 콘솔에서 **Software Library** 애플리케이션 \> **관리 패키지로 이동한** 다음 패키지 \>  **만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="4ea50-270">다음 정보를 입력하여 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="4ea50-271">이름: **SRS v2 – 루트 인증서 패키지**</span><span class="sxs-lookup"><span data-stu-id="4ea50-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="4ea50-272">제조업체: *조직의 이름*</span><span class="sxs-lookup"><span data-stu-id="4ea50-272">Manufacturer: *Your organization's name*</span></span>
    -   <span data-ttu-id="4ea50-273">버전: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="4ea50-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="4ea50-274">이 **패키지에** 원본 파일이 포함된 확인란을 선택하고 **SRS v2 – 루트** 인증서 패키지 폴더에 대한 경로를 입력한 다음 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="4ea50-275">프로그램 **만들기 안 를 선택한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="4ea50-276">설정 **확인 페이지를 검토한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="4ea50-277">닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="4ea50-278">배포 Microsoft Teams 룸 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="4ea50-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="4ea50-279">에서 최신 버전의 Microsoft Teams 룸 배포 **키트를** 다운로드하고, 이 키트를 <https://go.microsoft.com/fwlink/?linkid=851168> workstation에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="4ea50-280">C: 프로그램 **\\ 파일(x86) \\** Skype 룸 시스템 배포 키트에서 **SRS v2 - SRS 애플리케이션 패키지** 폴더에 콘텐츠를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="4ea50-281">Configuration Manager 콘솔에서 **Software Library** 애플리케이션 \> **관리 패키지로 이동한** 다음 패키지 \>  **만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="4ea50-282">다음 정보를 입력하여 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="4ea50-283">이름: **SRS v2 – SRS 애플리케이션 패키지**</span><span class="sxs-lookup"><span data-stu-id="4ea50-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="4ea50-284">제조업체: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="4ea50-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="4ea50-285">버전: **3.1.104.0(다운로드한** 설치 파일의 버전을 입력합니다)</span><span class="sxs-lookup"><span data-stu-id="4ea50-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="4ea50-286">이 **패키지에** 원본 파일이 포함된 확인란을 선택하고 **SRS v2 – SRS 애플리케이션 패키지** 폴더에 대한 경로를 입력한 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="4ea50-287">프로그램 **만들기 안 를 선택한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="4ea50-288">설정 **확인 페이지를 검토한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="4ea50-289">닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="4ea50-290">컴퓨터 이름 할당 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="4ea50-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="4ea50-291">**SRS v2 - Set-SRSComputerName** 패키지 폴더에서 **Set-SRSComputerName.hta라는** 새 HTML 애플리케이션을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="4ea50-292">**Set-SRSComputerName.hta** 파일에 다음 스크립트를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="4ea50-293">또는 여기에서 Set-SRSComputerName.hta 파일을 다운로드할 수 [있습니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="4ea50-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  <span data-ttu-id="4ea50-294">Configuration Manager 콘솔에서 **Software Library** 애플리케이션 \> **관리 패키지로 이동한** 다음 패키지 \>  **만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="4ea50-295">다음 정보를 입력하여 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="4ea50-296">이름: **SRS v2 - Set-SRSComputerName 패키지**</span><span class="sxs-lookup"><span data-stu-id="4ea50-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="4ea50-297">제조업체: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="4ea50-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="4ea50-298">버전: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="4ea50-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="4ea50-299">이 **패키지에** 원본 파일이 포함된 확인란을 선택하고 **SRS v2 -** Set-SRSComputerName 패키지 폴더에 대한 경로를 입력한 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="4ea50-300">프로그램 **만들기 안 를 선택한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="4ea50-301">설정 **확인 페이지를 검토한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="4ea50-302">닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="4ea50-303">Sysprep 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="4ea50-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="4ea50-304">**SRS v2 – Sysprep 패키지** 폴더에서 새 XML **파일을Unattend.xml.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="4ea50-305">다음 텍스트를Unattend.xml **복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="4ea50-306">또는 여기에서 Unattend.xml 파일을 다운로드할 수 [있습니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="4ea50-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. <span data-ttu-id="4ea50-307">Configuration Manager 콘솔에서 **Software Library** 애플리케이션 \> **관리 패키지로 이동한** 다음 패키지 \>  **만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="4ea50-308">다음 정보를 입력하여 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="4ea50-309">이름: **SRS v2 - Sysprep 패키지**</span><span class="sxs-lookup"><span data-stu-id="4ea50-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="4ea50-310">제조업체: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="4ea50-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="4ea50-311">버전: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="4ea50-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="4ea50-312">이 **패키지에** 원본 파일이 포함된 확인란을 선택하고 **SRS v2 – Sysprep 패키지** 폴더에 대한 경로를 입력한 다음 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="4ea50-313">프로그램 **만들기 안 를 선택한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="4ea50-314">설정 **확인 페이지를 검토한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="4ea50-315">닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="4ea50-316">패키지 Windows 10 Enterprise 만들기</span><span class="sxs-lookup"><span data-stu-id="4ea50-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="4ea50-317">x64 Windows 10 Enterprise 다운로드하고 **install.wim** 파일을 운영 체제 Windows 10 Enterprise 폴더에 **\\ 복사합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="4ea50-318">구성 관리자 콘솔에서 **소프트웨어** 라이브러리 운영 체제 운영 체제 이미지로 이동한 다음 운영 체제 이미지 \>  \>  **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="4ea50-319">방금 복사한 **install.wim** 파일의 경로를 지정한 다음 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="4ea50-320">버전 **필드를** 업데이트하여 이미지의 빌드 Windows 10 Enterprise 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="4ea50-321">세부 **정보 페이지를 검토한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="4ea50-322">닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-322">Select **Close**.</span></span>

<span data-ttu-id="4ea50-323">자세한 내용은 Configuration Manager를 사용하여 [OS 이미지 관리를 참조하세요.](/configmgr/osd/get-started/manage-operating-system-images)</span><span class="sxs-lookup"><span data-stu-id="4ea50-323">For more information, see [Manage OS images with Configuration Manager](/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="4ea50-324">디바이스 Surface Pro 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="4ea50-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="4ea50-325">Microsoft Teams 룸 및 Surface Pro 모두 Surface Pro 4.</span><span class="sxs-lookup"><span data-stu-id="4ea50-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="4ea50-326">환경에 있는 각 모델에 Surface Pro 드라이버 패키지를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ea50-327">드라이버는 빌드 및 Windows 10 Enterprise 배포 키트 버전과 Microsoft Teams 룸 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="4ea50-328">자세한 내용은 Surface 디바이스에 대한 최신 펌웨어 및 [드라이버](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) 다운로드 및 콘솔 [구성을 참조하세요.](console.md)</span><span class="sxs-lookup"><span data-stu-id="4ea50-328">For more information, see [Download the latest firmware and drivers for Surface devices](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="4ea50-329">최신 드라이버 및 펌웨어를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="4ea50-330">다음 Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="4ea50-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="4ea50-331">다음 Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="4ea50-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="4ea50-332">다운로드한 드라이버 및 펌웨어를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="4ea50-333">명령 프롬프트 창을 열고 명령 프롬프트에서 다음 명령 중 하나를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="4ea50-334">구성 관리자 콘솔에서 **소프트웨어** 라이브러리 운영 \> **체제** \> **드라이버로** 이동한 다음 드라이버 **가져오기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="4ea50-335">**다음 UNC(네트워크** 경로)에서 모든 드라이버 가져오기 를 선택하고 원본 폴더(예: C: _Sources \\ 드라이버 \\ Surface Pro)를 선택한 다음 \\ 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="4ea50-336">가져온  드라이버에 대한 세부 정보 지정 페이지에서 나열된 모든 드라이버를 선택한 다음 이러한 드라이버 사용 및 컴퓨터에 설치 허용 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="4ea50-337">범주를 **선택하고** Surface 모델과 일치하는 새 범주를 만들고 확인을 선택한 다음 다음 을 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="4ea50-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="4ea50-338">새 **패키지를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="4ea50-339">모델과 일치하는 패키지 이름을 Surface Pro 폴더 경로를 입력하여 드라이버 패키지 파일을 저장하고 확인을 선택한 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="4ea50-340">부팅 이미지 **페이지에서** 부팅 이미지가 선택되어 없는지 확인한 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="4ea50-341">닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-341">Select **Close**.</span></span>

11. <span data-ttu-id="4ea50-342">**소프트웨어** 라이브러리 운영 체제 드라이버로 이동하고 폴더 만들기 폴더를 선택하고 방금 드라이버를 가져온 Surface Pro 모델과 일치하는 폴더 이름을 \>  \> 입력합니다. **\>**</span><span class="sxs-lookup"><span data-stu-id="4ea50-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="4ea50-343">가져온 모든 드라이버를 새로 만든 폴더로 이동하여 탐색 및 작업을 쉽게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="4ea50-344">있을 수 있는 다른 Surface Pro 동일한 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="4ea50-345">자세한 내용은 [Configuration Manager에서 드라이버 관리를 참조하세요.](/configmgr/osd/get-started/manage-drivers)</span><span class="sxs-lookup"><span data-stu-id="4ea50-345">For more information, see [Manage drivers in Configuration Manager](/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="4ea50-346">구성 Microsoft Teams 룸 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="4ea50-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="4ea50-347">Configuration Manager 콘솔에서 **Software Library** 애플리케이션 \> **관리 패키지로 이동한** 다음 패키지 \>  **만들기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="4ea50-348">다음 정보를 입력하여 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="4ea50-349">이름: **SRS v2 - SRS 설정 패키지 구성**</span><span class="sxs-lookup"><span data-stu-id="4ea50-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="4ea50-350">제조업체: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="4ea50-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="4ea50-351">버전: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="4ea50-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="4ea50-352">이 **패키지에** 원본 파일이 포함된 확인란을 선택하고 **SRS v2 - SRS** 설정 폴더 구성에 대한 경로를 입력한 다음 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="4ea50-353">프로그램 **만들기 안 를 선택한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="4ea50-354">설정 **확인 페이지를 검토한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="4ea50-355">닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="4ea50-356">Configuration Manager 패키지 배포</span><span class="sxs-lookup"><span data-stu-id="4ea50-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="4ea50-357">모든 패키지는 Configuration Manager 계층 구조에서 배포 지점 역할이 할당된 서버에 배포되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="4ea50-358">아래 지침에 따라 패키지 배포를 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="4ea50-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="4ea50-359">소프트웨어 패키지를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="4ea50-360">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** 애플리케이션 \> **관리 패키지로** \> **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="4ea50-361">배포할 모든 소프트웨어 패키지를 선택한 다음 콘텐츠 배포를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="4ea50-362">패키지 목록을 검토한 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="4ea50-363">모든 배포 지점 서버(또는 구성 관리자 계층 구조에 따라 배포 지점 그룹)를 목록에 추가한 다음 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="4ea50-364">다음 **을** 선택한 다음 **닫기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="4ea50-365">드라이버 패키지를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="4ea50-366">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** 운영 체제 \> **드라이버** \> **패키지로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="4ea50-367">배포할 모든 드라이버 패키지를 선택한 다음 콘텐츠 **배포를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="4ea50-368">패키지 목록을 검토한 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="4ea50-369">모든 배포 지점 서버(또는 구성 관리자 계층 구조에 따라 배포 지점 그룹)를 목록에 추가한 다음 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="4ea50-370">다음 **을** 선택한 다음 **닫기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="4ea50-371">운영 체제 패키지를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="4ea50-372">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** 운영 체제 \>  \> **이미지로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="4ea50-373">배포할 모든 운영 체제 이미지를 선택한 다음 콘텐츠 **배포를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="4ea50-374">패키지 목록을 검토한 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="4ea50-375">모든 배포 지점 서버(또는 구성 관리자 계층 구조에 따라 배포 지점 그룹)를 목록에 추가한 다음 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="4ea50-376">다음 **을** 선택한 다음 **닫기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="4ea50-377">패키지 배포는 패키지 크기, Configuration Manager 계층 구조, 배포 지점 서버 수 및 네트워크에서 사용할 수 있는 대역폭에 따라 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="4ea50-378">패키지를 배포하기 전에 모든 패키지를 배포해야 Microsoft Teams 룸 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="4ea50-379">배포 상태 콘텐츠 상태 모니터링 으로 가면 Configuration  Manager 콘솔에서 패키지 배포 상태를 \> **검토할** \> **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="4ea50-380">Configuration Manager 작업 시퀀스</span><span class="sxs-lookup"><span data-stu-id="4ea50-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="4ea50-381">Configuration Manager를 사용하여 작업 시퀀스를 사용하여 대상 컴퓨터에 운영 체제 이미지를 배포하는 단계를 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="4ea50-382">자동화된 Microsoft Teams 룸 배포하려면 대상 컴퓨터, 설치하려는 Microsoft Teams 룸 운영 체제 이미지 및 기타 애플리케이션 또는 소프트웨어 업데이트와 같은 기타 추가 Microsoft Teams 룸 Windows 10 Enterprise 부팅 이미지를 참조하는 작업 시퀀스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="4ea50-383">샘플 작업 시퀀스 가져오기</span><span class="sxs-lookup"><span data-stu-id="4ea50-383">Import the sample task sequence</span></span>

<span data-ttu-id="4ea50-384">샘플 작업 시퀀스를 다운로드하고 쉽게 가져오고 필요에 맞게 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="4ea50-385">[**샘플**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) 작업 순서를 다운로드하고 다운로드한 zip 파일을 공유 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="4ea50-386">Configuration Manager 콘솔에서 **소프트웨어** 라이브러리 운영 체제 작업 시퀀스로 이동한 다음 작업 시퀀스 \>  \>  **가져오기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="4ea50-387">**찾아보기를** 선택하고 1단계에서 사용한 공유 폴더 위치로 이동하고, **EN-US(Microsoft Teams 룸).zip** 파일을 선택한 다음 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="4ea50-388">작업을 **새** 만들기로 **설정한** 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="4ea50-389">설정을 확인한 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="4ea50-390">닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="4ea50-391">참조 패키지가 각 작업 순서 단계에 올바르게 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="4ea50-392">가져온 작업 순서를 선택한 다음 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="4ea50-393">작업 시퀀스 편집기에서 단위를 배포하고 구성하는 데 필요한 각 순차적 Microsoft Teams 룸 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="4ea50-394">각 단계를 진행하고 권장되는 업데이트를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="4ea50-395">**PE에서 Windows 다시** 시작: 이 단계는 다시 시작한 다음, 컴퓨터를 Windows PXE로 부팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="4ea50-396">이 단계에서는 변경이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="4ea50-397">**파티션 디스크 0 – UEFI**: 이 단계는 디스크 구성을 지우고 구성된 설정에 따라 파티션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="4ea50-398">이 단계를 변경하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="4ea50-399">**SRS 컴퓨터** 이름 설정 : 이 단계에서는 배포 중에 Microsoft Teams 룸 컴퓨터 이름을 설정하는 UI를 제공하는 HTML 애플리케이션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="4ea50-400">이 단계는 선택적 단계이지만 대체 프로세스를 통해 컴퓨터 이름을 관리하려는 경우만 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="4ea50-401">**SRS v2 - Set-SRSComputerName 패키지가 선택되어** 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="4ea50-402">그렇지 않은 경우 패키지로 찾아가서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-402">If it isn't, browse to the package and select it.</span></span>

   4. <span data-ttu-id="4ea50-403">**운영 체제 적용**: 이 단계에서는 배포할 운영 체제 이미지와 사용할 무인 Sysprep 응답 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="4ea50-404">올바른 운영 체제 Windows 10 Enterprise 파일이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="4ea50-405">사용자 지정 설치에 무인 또는 **Sysprep** 응답 파일을 사용하도록 설정하고 **SRS v2 - Sysprep 패키지가** 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="4ea50-406">또한 파일 **이름이** 으로 **설정되어unattend.xml.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="4ea50-407">**적용 Windows 설정**: 이 단계에서는 설치에 대한 Windows 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="4ea50-408">제품 키, 로컬 관리자 계정 암호 및 표준 시간대를 포함한 라이선스 및 등록 정보를 제공합니다(요구에 따라 다를 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="4ea50-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="4ea50-409">**네트워크 설정** 적용 : 이 단계를 통해 작업 영역 또는 Active Directory 도메인 이름 및 조직 단위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="4ea50-410">Actve Directory [도메인의](domain-joining-considerations.md) 구성원으로 Skype 단위를 배포하는 데 Microsoft Teams 룸 권장 작업에 대한 룸 시스템 도메인 가입 고려 사항을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="4ea50-411">**드라이버 적용:** 이 단계 및 해당 하위 단계는 해당 모델에 따라 해당 디바이스 드라이버 및 펌웨어를 배포하는 데 Surface Pro 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="4ea50-412">각 단계를 업데이트하여 이 배포와 관련된 관련 드라이버 패키지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="4ea50-413">각 드라이버 패키지는 WMI(관리 Windows) 필터를 활용하여 관련 드라이버 및 펌웨어를 Surface Pro 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="4ea50-414">이러한 드라이버의 구성을 변경하지 않는 것이 좋습니다. 그렇지 않으면 배포가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="4ea50-415">**Windows 및** 구성 관리자 설정 : 이 단계는 Configuration Manager 클라이언트를 배포하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="4ea50-416">기본 제공 Configuration Manager 클라이언트 패키지를 지정하려면 이 단계를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="4ea50-417">**루트 인증서 설치**: 이 단계는 도메인에 가입되지 않은 디바이스에 대한 루트 인증서를 배포하므로 선택 사항이며 기본적으로 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="4ea50-418">루트 인증서를 배포해야 하는 경우 이 Microsoft Teams 룸 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="4ea50-419">이 단계를 수행해야 하는 경우 **SRS v2 – 루트** 인증서 패키지 및 **64비트** 파일 시스템 리디렉션 사용 안 을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="4ea50-420">**모니터링 에이전트** 설치 및 구성: 이 단계에서는 모니터링 에이전트의 64비트 버전을 Microsoft Azure 에이전트를 구성하여 Log Analytics 작업 영역으로 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="4ea50-421">이 단계는 기본적으로 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-421">This step is disabled by default.</span></span> <span data-ttu-id="4ea50-422">모니터링 에이전트를 사용하여 장치 단위의 Microsoft Teams 룸 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-422">Enable this step only if you're going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="4ea50-423">이 단계를 편집하고 명령줄 매개 변수를 업데이트하여 작업 영역 **ID** 및 작업 영역 키를 **지정합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="4ea50-424">Operations Management Suite 작업 영역 ID 및 기본 키 획득에 대한 자세한 내용은 [Azure Monitoring에](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) 대한 테스트 디바이스 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ea50-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="4ea50-425">**SRS v2 –** Microsoft Monitoring Agent 및 사용하지 않도록 설정 **64비트** 파일 시스템 리디렉션을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="4ea50-426">배포의 상태 모니터링에 대한 Microsoft Teams 룸 자세한 내용은 [Azure Monitor를](azure-monitor-plan.md)사용하여 Microsoft Teams 룸 관리 계획, Azure Monitor를 사용하여 Microsoft Teams 룸 관리 배포 및 Azure [Monitor를](azure-monitor-deploy.md) 사용하여 디바이스 Microsoft Teams 룸 관리 를 [참조하세요.](azure-monitor-manage.md)</span><span class="sxs-lookup"><span data-stu-id="4ea50-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="4ea50-427">**SRS v2** 구성 파일 복사 : 이 단계에서는 배포 키트에서 로컬 Microsoft Teams 룸 필요한 설정 및 구성 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="4ea50-428">이 단계에서는 사용자 지정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="4ea50-429">**SRS v2 – SRS 애플리케이션 패키지** 및 **64비트 파일** 시스템 리디렉션 사용 안 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ea50-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="4ea50-430">**Install-SRSv2-OS-Updates:** 이 단계에서는 배포에 필요한 모든 필수 운영 체제 업데이트를 Microsoft Teams 룸 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="4ea50-431">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-431">Do the following:</span></span>
       -   <span data-ttu-id="4ea50-432">필요한 [업데이트를](console.md) Microsoft Teams 룸 콘솔 구성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="4ea50-433">**SRS v2 – OS 업데이트 패키지에** 필요한 모든 업데이트가 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="4ea50-434">**SRS v2 – OS 업데이트 패키지가 선택되어 있는지** 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="4ea50-435">PowerShell 실행 정책이 **Bypass로 설정되어 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="4ea50-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="4ea50-436">**컴퓨터 다시 시작**: 이 단계는 필수 운영 체제 업데이트를 설치한 후 컴퓨터를 다시 부트합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="4ea50-437">이 단계에서는 사용자 지정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="4ea50-438">**구성 Windows 구성**: 이 단계에서는 필요한 Windows 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="4ea50-439">이 단계에서는 사용자 지정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="4ea50-440">**컴퓨터 다시 시작**: 이 단계는 Windows 구성한 후에 컴퓨터를 다시 부트합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="4ea50-441">이 단계에서는 사용자 지정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="4ea50-442">**로컬 Skype 사용자** 추가: 이 단계에서는 Skype 자동으로 로그인하고 애플리케이션에 Windows 데 사용되는 로컬 Microsoft Teams 룸 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="4ea50-443">이 단계에서는 연결된 소프트웨어 패키지가 없습니다. 이에 대한 사용자 지정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-443">This step doesn't have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="4ea50-444">**SRS 애플리케이션** 설정 및 구성 : 이 Microsoft Teams 룸 다음 부팅에 대한 애플리케이션 설치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="4ea50-445">**SRS v2 – SRS 설정** 패키지 구성 및 **64비트 파일** 시스템 리디렉션 사용 안 하도록 설정이 선택되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ea50-446">작업 순서 단계가 제공된 순서에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="4ea50-447">단계 순서를 수정하거나 추가 단계를 구성하면 배포가 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="4ea50-448">**SRS 애플리케이션** 단계 설정 및 구성은 작업 순서의 마지막 단계이 되어야 합니다. 그렇지 않으면 배포가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="4ea50-449">작업 시퀀스에 대한 배포 만들기</span><span class="sxs-lookup"><span data-stu-id="4ea50-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="4ea50-450">작업 순서를 선택한 다음 **배포를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="4ea50-451">**찾아보기를** 선택하여 배포 대상 컬렉션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="4ea50-452">알 **수 없는 모든 컴퓨터를 선택한** 다음 확인 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="4ea50-453">다음 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-453">Select **Next**.</span></span>

5. <span data-ttu-id="4ea50-454">목적 **드롭다운** **목록에서** 사용 가능을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="4ea50-455">다음 목록에 사용할 수 있도록  만들기에서 미디어 및 **PXE만** 선택한 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="4ea50-456">목적이 **사용** 가능으로 설정되어 있는 것이 **매우 중요합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="4ea50-457">목적이 **필수** 으로 **설정되어** 있지 **않은지 확인**</span><span class="sxs-lookup"><span data-stu-id="4ea50-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="4ea50-458">또한 다음 에서 사용할 수 있도록 만들기에서 미디어 및 **PXE만** **선택해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="4ea50-459">이러한 값을 다른 것으로 설정하면 모든 컴퓨터가 부팅 시 Microsoft Teams 룸 이미지를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="4ea50-460">일정을 지정하지 말고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="4ea50-461">사용자 환경 섹션 내의 아무 것도 **변경하지** 말고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="4ea50-462">경고 섹션 내에서 아무 것도 **변경하지** 말고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="4ea50-463">배포 지점 섹션 내에서 아무 것도 **변경하지** 말고 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="4ea50-464">설정을 확인한 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="4ea50-465">닫기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="4ea50-466">솔루션의 유효성 검사 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4ea50-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="4ea50-467">작업 시퀀스를 Microsoft Endpoint Configuration Manager 완료한 후 테스트 실행을 수행하여 작업 시퀀스가 단위를 배포하고 구성할 수 있는지 Microsoft Teams 룸 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-467">After you've completed the Microsoft Endpoint Configuration Manager task sequences, you'll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="4ea50-468">커넥트 이더넷 어댑터 중 하나를 사용하거나 Surface dock을 사용하여 테스트 디바이스를 유선 네트워크에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="4ea50-469">PXE 부팅 기능이 환경에 맞게 구성되지 않은 경우 앞에서 만든 USB 플래시 드라이브의 부팅 이미지를 사용하여 USB에서 부팅하고 Configuration Manager에 연결할 수 있습니다. [](/configmgr/osd/deploy-use/create-bootable-media)</span><span class="sxs-lookup"><span data-stu-id="4ea50-469">If PXE boot functionality hasn't been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="4ea50-470">펌웨어에 액세스하고 PXE 부팅을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="4ea50-471">Surface 디바이스가 전원을 끄고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="4ea50-472">볼륨 업 **단추를 누를 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="4ea50-473">전원 단추를 **누르고 해제합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="4ea50-474">디바이스가 부팅하기 시작하면 **볼륨 업 단추를 해제합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="4ea50-475">부팅 **구성을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="4ea50-476">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-476">Do one of the following:</span></span>

        -   <span data-ttu-id="4ea50-477">**PXE 부팅을 선택하고** 목록 맨 위로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="4ea50-478">또는 네트워크 어댑터에서 왼쪽으로 스와이프하여 디바이스로 즉시 부팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="4ea50-479">부팅 순서에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-479">This won't affect the boot order.</span></span>
        -   <span data-ttu-id="4ea50-480">부팅 미디어가 있는 USB 플래시 드라이브를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="4ea50-481">**종료를** 선택한 다음 지금 다시 **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="4ea50-482">메시지가 표시될 때 네트워크 부팅 **서비스에 대해 Enter를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="4ea50-483">Windows PE가 메모리에 로드됩니다. 작업 시퀀스 마법사가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="4ea50-484">**다음을** 선택하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="4ea50-485">앞에서 가져온 작업 순서를 선택한 다음 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="4ea50-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="4ea50-486">디스크 구성이 적용된 후 디바이스에 대한 컴퓨터 이름을 지정하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-486">After the disk configuration is applied, you'll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="4ea50-487">사용자 인터페이스는 디바이스의 일련 번호에 따라 권장되는 컴퓨터 Surface Pro 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="4ea50-488">제안된 이름을 수락하거나 새 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="4ea50-489">컴퓨터 이름 할당 화면의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="4ea50-490">**수락을 선택하면** 배포가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="4ea50-491">나머지 배포 프로세스는 자동으로 수행됩니다. 더 이상 사용자 입력을 요청하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-491">The rest of the deployment process is automatic and doesn't ask for any more user input.</span></span>

9.  <span data-ttu-id="4ea50-492">배포 작업 순서가 디바이스 구성을 완료하면 애플리케이션 설정을 구성하도록 요청하는 다음 구성 화면이 Microsoft Teams 룸 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-492">After the deployment task sequence finishes configuring the device, you'll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![애플리케이션에 대한 초기 Microsoft Teams 룸 화면](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="4ea50-494">Surface Pro 콘솔에 Microsoft Teams 룸 애플리케이션 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="4ea50-495">배포된 디바이스에서 Microsoft Teams 룸 [도움말에](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 나열된 기능의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="4ea50-496">실패한 설치 문제를 해결하려면 구성 관리자 작업 시퀀스에서 실행된 모든 단계를 기록하는 **SMSTS.log** 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="4ea50-497">SMSTS.log 파일은 빌드 프로세스의 단계에 따라 여러 경로 중 하나에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="4ea50-498">다음 표를 확인하여 SMSTS.log 파일의 경로를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="4ea50-499">**배포 단계**</span><span class="sxs-lookup"><span data-stu-id="4ea50-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="4ea50-500">**작업 시퀀스 로그 경로**</span><span class="sxs-lookup"><span data-stu-id="4ea50-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="4ea50-501">HDD 형식 이전의 WinPE</span><span class="sxs-lookup"><span data-stu-id="4ea50-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="4ea50-502">X: \\ Windows \\ \\ smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="4ea50-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="4ea50-503">WINPE( HDD 형식 이후)</span><span class="sxs-lookup"><span data-stu-id="4ea50-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="4ea50-504">C: \\ _SMSTaskSequence \\ \\ Logs Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="4ea50-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="4ea50-505">Configuration Manager 에이전트가 설치되기 전에 배포된 운영 체제</span><span class="sxs-lookup"><span data-stu-id="4ea50-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="4ea50-506">c: \\ _SMSTaskSequence \\ \\ Logs Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="4ea50-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="4ea50-507">운영 체제 및 배포된 Configuration Manager 에이전트</span><span class="sxs-lookup"><span data-stu-id="4ea50-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="4ea50-508">%windir% \\ System32 \\ ccm \\ logs \\ Smstslog \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="4ea50-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="4ea50-509">작업 시퀀스 실행 완료</span><span class="sxs-lookup"><span data-stu-id="4ea50-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="4ea50-510">%windir% \\ System32 \\ ccm \\ logs \\ smsts.log</span><span class="sxs-lookup"><span data-stu-id="4ea50-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="4ea50-511">작업 순서 중에 **F8을** 선택하여 명령 콘솔을 열고 SMSTS.log 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="4ea50-512">PXE 부팅 문제를 해결하려면 PXE 작업과 관련이 있는 Configuration Manager 서버의 두 로그 파일을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="4ea50-513">구성 관리자 설치 로그 디렉터리에 있는 **Pxecontrol.log**</span><span class="sxs-lookup"><span data-stu-id="4ea50-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="4ea50-514">**Smspxe.log**, 구성 관리자 관리 지점(MP) 로그 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ea50-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="4ea50-515">Configuration Manager 설치 문제를 추가로 해결하는 데 사용할 수 있는 로그 파일의 전체 목록은 로그 Microsoft Endpoint Configuration Manager [참조를 참조하세요.](/configmgr/core/plan-design/hierarchy/log-files)</span><span class="sxs-lookup"><span data-stu-id="4ea50-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](/configmgr/core/plan-design/hierarchy/log-files).</span></span>
