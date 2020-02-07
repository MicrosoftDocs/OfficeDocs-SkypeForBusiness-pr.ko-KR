---
title: Microsoft Endpoint Configuration Manager를 사용 하 여 Microsoft 팀 대화방 배포
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: 대규모 배포에서 Microsoft 팀 회의실을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
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
ms.openlocfilehash: eb1e4337f97f16df6d7ef039bf4ba095ed692995
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827926"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="1d8bb-103">Microsoft Endpoint Configuration Manager를 사용 하 여 Microsoft 팀 대화방 배포</span><span class="sxs-lookup"><span data-stu-id="1d8bb-103">Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="1d8bb-104">이 문서에서는 Microsoft 끝점 구성 관리자를 사용 하 여 Microsoft 팀 회의실 배포를 만드는 데 필요한 모든 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-104">This article gives you all the necessary information to create your Microsoft Teams Rooms deployments by using Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="1d8bb-105">구성 관리자가 제공 하는 사용 하기 쉬운 메서드를 사용 하 여 운영 체제 및 기타 응용 프로그램을 여러 대상 장치에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-105">With the easy-to-use methods provided by Configuration Manager, you can deploy the operating system and other applications to multiple target devices.</span></span>

<span data-ttu-id="1d8bb-106">아래 설명 된 방법을 사용 하 여 Configuration Manager 구성을 안내 하 고 조직에 필요한 경우이 가이드에서 제공 하는 샘플 패키지 및 스크립트를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-106">Use the approach illustrated below to guide you through your Configuration Manager configuration, and customize the sample packages and scripts provided throughout this guidance as needed for your organization.</span></span>

![Microsoft 팀 대화방 배포 프로세스 구성 관리자 사용](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> <span data-ttu-id="1d8bb-108">이 솔루션은 Surface Pro 기반 배포 에서만 테스트를 거쳤습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-108">This solution has only been tested with Surface Pro–based deployments.</span></span> <span data-ttu-id="1d8bb-109">Surface Pro를 기반으로 하지 않는 구성에 대 한 제조업체의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-109">Follow the manufacturer’s guidelines for configurations that aren’t based on Surface Pro.</span></span>

## <a name="validate-prerequisites"></a><span data-ttu-id="1d8bb-110">필수 조건 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="1d8bb-110">Validate prerequisites</span></span>

<span data-ttu-id="1d8bb-111">Configuration Manager를 사용 하 여 Microsoft 팀 회의실을 배포 하려면 다음 필수 구성 요소 및 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-111">To deploy Microsoft Teams Rooms with Configuration Manager, ensure that you meet the following prerequisites and requirements.</span></span>

### <a name="microsoft-endpoint-configuration-manager-requirements"></a><span data-ttu-id="1d8bb-112">Microsoft Endpoint Configuration Manager 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d8bb-112">Microsoft Endpoint Configuration Manager requirements</span></span>

-   <span data-ttu-id="1d8bb-113">Microsoft Endpoint Configuration Manager 버전은 1706 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-113">Microsoft Endpoint Configuration Manager version must be at least 1706 or above.</span></span> <span data-ttu-id="1d8bb-114">1710 이상을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-114">We recommend using 1710 or later.</span></span> <span data-ttu-id="1d8bb-115">Configuration manager [에서 windows 10](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) 을 지 원하는 windows 10 버전에 대 한 자세한 내용은 configuration manager에서 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-115">Check out [Support for Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) to learn about the Windows 10 versions that Configuration Manager supports.</span></span>

-   <span data-ttu-id="1d8bb-116">Windows 10 용 지원 되는 버전의 Windows ADK (평가 및 배포 키트)가 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-116">A supported version of Windows Assessment and Deployment Kit (ADK) for Windows 10 must be installed.</span></span> <span data-ttu-id="1d8bb-117">여러 버전의 Configuration Manager에서 사용할 수 있는 [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) 버전을 참조 하 고 배포에 올바른 버전이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-117">See the versions of the [Windows 10 ADK](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) that you can use with different versions of Configuration Manager, and ensure that your deployment includes the correct version.</span></span>

-   <span data-ttu-id="1d8bb-118">사이트 시스템 서버에 배포 지점의 역할이 할당 되어 있어야 하며 네트워크에서 시작 된 배포를 사용 하려면 [PXE (부팅 전 실행 환경) 지원](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) 에 부팅 이미지를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-118">The site system servers must have been assigned the distribution point role, and the boot images should be enabled for [preboot execution environment (PXE) support](https://docs.microsoft.com/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) to enable network-initiated deployments.</span></span> <span data-ttu-id="1d8bb-119">PXE 지원이 사용 되지 않는 경우에는 배포에 [부팅 가능한 미디어](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-119">If PXE support isn’t enabled, you can use [bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments.</span></span>

-   <span data-ttu-id="1d8bb-120">네트워크 액세스 계정은 새 컴퓨터 (완전 한 금속) 배포 시나리오를 지원 하도록 구성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-120">A network access account must be configured to support new computer (bare metal) deployment scenarios.</span></span> <span data-ttu-id="1d8bb-121">네트워크 액세스 계정의 구성에 대 한 자세한 내용은 [구성 관리자에 사용 되는 계정을](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-121">To learn more about the configuration of a network access account, see [Accounts used in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

-   <span data-ttu-id="1d8bb-122">동일한 Microsoft 팀 대화방 이미지를 동시에 여러 장치에 배포 하는 경우 [멀티 캐스트 지원을](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-122">We recommend that you enable [multicast support](https://docs.microsoft.com/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), if you’re likely to deploy the same Microsoft Teams Rooms image to multiple units at the same time.</span></span>

### <a name="networking-requirements"></a><span data-ttu-id="1d8bb-123">네트워킹 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d8bb-123">Networking requirements</span></span>

-   <span data-ttu-id="1d8bb-124">네트워크에는 Microsoft 팀 대화방 유닛이 배포 되는 서브넷에 대 한 자동 IP 주소 배포용으로 구성 된 DHCP (동적 호스트 구성 프로토콜) 서버가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-124">Your network should have a Dynamic Host Configuration Protocol (DHCP) server, configured for automatic IP address distribution to the subnets where Microsoft Teams Rooms units will be deployed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d8bb-125">DHCP 임대 기간은 이미지 배포 기간 보다 긴 값으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-125">DHCP lease duration must be set to a value longer than the image deployment duration.</span></span> <span data-ttu-id="1d8bb-126">그렇지 않으면 배포가 실패할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-126">Otherwise, the deployment might fail.</span></span>

-   <span data-ttu-id="1d8bb-127">스위치 및 Vlan을 비롯 한 네트워크는 PXE를 지원 하도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-127">Your network, including switches and virtual LANs (VLANs), should be configured to support PXE.</span></span> <span data-ttu-id="1d8bb-128">IP 도우미 및 PXE 구성에 대 한 자세한 내용은 네트워크 공급 업체에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-128">Refer to your network vendor for more information about IP Helper and PXE configuration.</span></span> <span data-ttu-id="1d8bb-129">또는 PXE 지원이 사용 되지 않는 경우 배포에 대해 [부팅 가능한 미디어](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-129">Alternatively, you can use [bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) for your deployments, if PXE support isn’t enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d8bb-130">Surface Pro 장치의 경우 네트워크 (PXE 부팅)의 부팅은 이더넷 어댑터 또는 Microsoft의 도킹 스테이션을 사용 하는 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-130">For Surface Pro devices, booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="1d8bb-131">타사 이더넷 어댑터는 Surface Pro를 사용 하 여 PXE 부팅을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-131">Third-party Ethernet adapters don’t support PXE boot with Surface Pro.</span></span> <span data-ttu-id="1d8bb-132">자세한 내용은 [이더넷 어댑터 및 Surface 배포](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-132">See [Ethernet adapters and Surface deployment](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) for more information.</span></span>

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a><span data-ttu-id="1d8bb-133">운영 체제 배포용 Microsoft Endpoint Configuration Manager 구성</span><span class="sxs-lookup"><span data-stu-id="1d8bb-133">Configure Microsoft Endpoint Configuration Manager for operating system deployment</span></span>

<span data-ttu-id="1d8bb-134">이 문서에서는 이미 올바른 구성 관리자 배포를 보유 하 고 있는 것으로 가정 하 고 구성 관리자를 처음부터 배포 하 고 구성 하는 데 필요한 모든 단계를 자세히 설명 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-134">This article assumes you already have a healthy Configuration Manager deployment, and doesn’t detail all the steps required to deploy and configure Configuration Manager from scratch.</span></span> <span data-ttu-id="1d8bb-135">Microsoft 끝점 구성 관리자의 [설명서와 구성 지침은](https://docs.microsoft.com/configmgr/) 훌륭한 리소스입니다. 아직 구성 관리자를 배포 하지 않은 경우 이러한 리소스부터 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-135">The [documentation and the configuration guidance](https://docs.microsoft.com/configmgr/) on the Microsoft Endpoint Configuration Manager is a great resource; we recommend you start with these resources if you haven’t yet deployed Configuration Manager.</span></span>

<span data-ttu-id="1d8bb-136">다음 지침을 사용 하 여 OSD (운영 체제 배포) 기능이 올바르게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-136">Use the following instructions to verify that the operating system deployment (OSD) features are configured properly.</span></span>

### <a name="validate-and-upgrade-configuration-manager"></a><span data-ttu-id="1d8bb-137">구성 관리자 유효성 검사 및 업그레이드</span><span class="sxs-lookup"><span data-stu-id="1d8bb-137">Validate and upgrade Configuration Manager</span></span>

1.  <span data-ttu-id="1d8bb-138">Configuration Manager 콘솔에서 **관리** \> **업데이트 및 서비스**를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-138">In the Configuration Manager console, go to **Administration** \> **Updates and Servicing**.</span></span>

2.  <span data-ttu-id="1d8bb-139">설치 된 빌드 및 아직 설치 되지 않은 적용 가능한 업데이트를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-139">Check the installed build and applicable updates that haven’t been installed yet.</span></span>

3.  <span data-ttu-id="1d8bb-140">[구성 관리자에서 Windows 10에 대 한 지원을 검토 합니다](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client). 배포를 업그레이드 해야 하는 경우 설치할 업데이트를 선택한 다음 **다운로드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-140">Review [Support for Windows 10 in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); if you need to upgrade your deployment, select the update you want to install, and then select **Download**.</span></span>

4.  <span data-ttu-id="1d8bb-141">다운로드가 완료 되 면 업데이트를 선택 하 고 **업데이트 팩 설치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-141">After the download is complete, select the update, and then select **Install Update Pack**.</span></span>

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a><span data-ttu-id="1d8bb-142">PXE 및 멀티 캐스트를 지원 하도록 배포 지점 구성</span><span class="sxs-lookup"><span data-stu-id="1d8bb-142">Configure distribution points to support PXE and multicast</span></span>

1.  <span data-ttu-id="1d8bb-143">Configuration Manager 콘솔에서 **관리** \> **배포 지점**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-143">In the Configuration Manager console, go to **Administration** \> **Distribution Points**.</span></span>

2.  <span data-ttu-id="1d8bb-144">Microsoft 팀 대화방 배포를 서비스할 배포 지점의 서버를 선택한 다음 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-144">Select the distribution point server that will serve the Microsoft Teams Rooms deployment, and then select **Properties**.</span></span>

3.  <span data-ttu-id="1d8bb-145">**PXE** 탭을 선택 하 고 다음 설정을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-145">Select the **PXE** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="1d8bb-146">클라이언트에 대해 PXE 지원 사용</span><span class="sxs-lookup"><span data-stu-id="1d8bb-146">Enable PXE support for clients</span></span>
    -   <span data-ttu-id="1d8bb-147">이 배포 지점이 들어오는 PXE 요청에 응답할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="1d8bb-147">Allow this distribution point to respond to incoming PXE requests</span></span>
    -   <span data-ttu-id="1d8bb-148">알 수 없는 컴퓨터 지원 사용</span><span class="sxs-lookup"><span data-stu-id="1d8bb-148">Enable unknown computer support</span></span>

4.  <span data-ttu-id="1d8bb-149">*선택 사항:* 멀티 캐스트 지원을 사용 하도록 설정 하려면 **멀티 캐스트** 탭을 선택 하 고 다음 설정을 사용할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-149">*Optional:* To enable multicast support, select the **Multicast** tab, and ensure that the following settings are enabled:</span></span>
    -   <span data-ttu-id="1d8bb-150">멀티 캐스트를 사용 하 여 여러 클라이언트에 동시에 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="1d8bb-150">Enable multicast to simultaneously send data to multiple clients</span></span>
    -   <span data-ttu-id="1d8bb-151">네트워크 팀의 권장 사항에 따라 UDP 포트 범위 구성</span><span class="sxs-lookup"><span data-stu-id="1d8bb-151">Configure the UDP port range as per your network team’s recommendation</span></span>

### <a name="configure-the-network-access-account"></a><span data-ttu-id="1d8bb-152">네트워크 액세스 계정 구성</span><span class="sxs-lookup"><span data-stu-id="1d8bb-152">Configure the Network Access Account</span></span>

1.  <span data-ttu-id="1d8bb-153">Configuration Manager 콘솔에서 **관리** \> **사이트 구성** \> **사이트로**이동한 다음 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-153">In the Configuration Manager console, go to **Administration** \> **Site Configuration** \> **Sites**, and then select the site.</span></span>

2.  <span data-ttu-id="1d8bb-154">**설정** 그룹에서 **사이트 구성 요소** \> **소프트웨어 배포**구성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-154">In the **Settings** group, select **Configure Site Components** \> **Software Distribution**.</span></span>

3.  <span data-ttu-id="1d8bb-155">**네트워크 액세스 계정** 탭을 선택 합니다. 하나 이상의 계정을 설정한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-155">Select the **Network Access Account** tab. Set up one or more accounts, and then select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="1d8bb-156">계정에는 배포 지점의 서버에서 해당 **네트워크에서이 컴퓨터 액세스** 권한을 제외한 특별 한 권한이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-156">The accounts don’t need any special rights, except for the **Access this computer from the network** right on the distribution point server.</span></span> <span data-ttu-id="1d8bb-157">일반 도메인 사용자 계정이 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-157">A generic domain user account will be appropriate.</span></span> <span data-ttu-id="1d8bb-158">자세한 내용은 [구성 관리자에 사용 되는 계정을](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-158">For more information, see [Accounts used in Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).</span></span>

### <a name="configure-a-boot-image"></a><span data-ttu-id="1d8bb-159">부팅 이미지 구성</span><span class="sxs-lookup"><span data-stu-id="1d8bb-159">Configure a boot image</span></span>

1.  <span data-ttu-id="1d8bb-160">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> 의 **운영 체제** \> **부팅 이미지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-160">In the Configuration Manager console, go to **Software Library** \> **Operating System** \> **Boot Images**.</span></span>

2.  <span data-ttu-id="1d8bb-161">**부팅 이미지 (x64)** 를 선택한 다음 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-161">Select **Boot image (x64)**, and then select **Properties**.</span></span>

3.  <span data-ttu-id="1d8bb-162">**데이터 원본** 탭을 선택 하 고 **PXE 사용 배포 지점의이 부팅 이미지 배포**를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-162">Select the **Data Source** tab, and enable **Deploy this boot image from the PXE-enabled distribution point**.</span></span>

4.  <span data-ttu-id="1d8bb-163">**선택적 구성 요소** 탭을 선택 하 여 필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-163">Select the **Optional Components** tab to install required components:</span></span>

    1.  <span data-ttu-id="1d8bb-164">별모양 아이콘을 선택 하 고 **HTML (WinPE-HTA)** 을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-164">Select the star icon, and search for **HTML (WinPE-HTA)**</span></span>

    2.  <span data-ttu-id="1d8bb-165">**확인** 을 선택 하 여 HTML 응용 프로그램 지원 기능을 부팅 이미지에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-165">Select **OK** to add HTML application support in to the boot image.</span></span>

5.  <span data-ttu-id="1d8bb-166">*선택 사항:* 배포 환경을 사용자 지정 하려면 **사용자 지정** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-166">*Optional:* To customize the deployment experience, select the **Customization** tab.</span></span>
    -   <span data-ttu-id="1d8bb-167">배포 중에 명령 프롬프트에 대 한 액세스 권한을 부여 하려면 **명령 지원 (테스트만 해당)** 을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-167">Enable **command support (testing only)** if you want to have access to a command prompt during the deployment.</span></span> <span data-ttu-id="1d8bb-168">이 기능을 사용 하도록 설정 하면 배포 중에 언제 든 지 **F8** 키를 선택 하 여 명령 프롬프트를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-168">When this is enabled, you can start a command prompt by selecting **F8** at any time during the deployment.</span></span>
    -   <span data-ttu-id="1d8bb-169">배포 중에 표시할 사용자 지정 배경 이미지를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-169">You can also specify a custom background image to be displayed during the deployment.</span></span> <span data-ttu-id="1d8bb-170">이미지를 설정 하려면 **사용자 지정 배경 이미지 파일 (UNC 경로) 지정** 을 사용 하도록 설정한 다음 배경을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-170">To set an image, enable **Specify the custom background image file (UNC path** and select your background.</span></span>

6.  <span data-ttu-id="1d8bb-171">메시지가 표시 되 면 **예** 를 선택 하 고 업데이트 된 부팅 이미지를 배포 지점에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-171">When asked, select **Yes** and distribute the updated boot image to your distribution points.</span></span>

<span data-ttu-id="1d8bb-172">자세한 내용은 [Configuration Manager를 사용 하 여 부팅 이미지 관리](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-172">For more information, see [Manage boot images with Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-boot-images).</span></span>

> [!NOTE]
> <span data-ttu-id="1d8bb-173">PXE 지원이 없는 환경에 대 한 Configuration Manager 작업 순서 기반 배포를 시작 하기 위해 부팅 가능 USB 미디어를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-173">You can create a bootable USB media to initiate Configuration Manager task sequence–based deployments for environments that have no PXE support.</span></span> <span data-ttu-id="1d8bb-174">부팅 가능 미디어에는 Windows PE로 부팅 하 고 나머지 배포 프로세스에 대해 구성 관리자에 연결 하는 데 사용할 부트 이미지, 선택적으로 제공 되는 명령 및 필요한 파일 및 구성 관리자 바이너리가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-174">The bootable media contains only the boot image, optional prestart commands and their required files, and Configuration Manager binaries to support booting into Windows PE and connecting to Configuration Manager for the rest of the deployment process.</span></span> <span data-ttu-id="1d8bb-175">자세한 내용은 [부팅 가능 미디어 만들기](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-175">For more information, see [Create bootable media](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).</span></span>

## <a name="create-configuration-manager-packages"></a><span data-ttu-id="1d8bb-176">Configuration Manager 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="1d8bb-176">Create Configuration Manager packages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d8bb-177">모든 MSI 릴리스의 각 SRS installer 버전에 대해 필요한 운영 체제 버전이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-177">The required operating system version for each SRS installer version changes with every MSI release.</span></span> <span data-ttu-id="1d8bb-178">지정 된 MSI에 가장 적합 한 운영 체제 버전을 확인 하려면 콘솔 설치 스크립트를 한 번 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-178">To determine the best operating system version for a given MSI, run the console setup script once.</span></span> <span data-ttu-id="1d8bb-179">자세한 내용은 [Microsoft 끝점 구성 관리자를 사용 하 여 Microsoft 팀 대화방 배포](rooms-scale.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-179">To learn more, see [Deploy Microsoft Teams Rooms by using Microsoft Endpoint Configuration Manager](rooms-scale.md).</span></span>

<span data-ttu-id="1d8bb-180">Configuration Manager에서 Microsoft 팀 대화방 단위를 배포 하 고 구성 하려면 여러 패키지가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-180">Configuration Manager requires a number of packages to deploy and configure the Microsoft Teams Rooms units.</span></span>

<span data-ttu-id="1d8bb-181">다음 패키지를 만들고 구성한 다음 배포 지점의 서버 역할이 지정 된 Configuration Manager 사이트 시스템에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-181">You need to create and configure the following packages, and then distribute them to the Configuration Manager site systems that have been assigned the distribution point server role.</span></span>

| <span data-ttu-id="1d8bb-182">**패키지 이름**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-182">**Package name**</span></span>                     | <span data-ttu-id="1d8bb-183">**유형**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-183">**Type**</span></span>               | <span data-ttu-id="1d8bb-184">**설명**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-184">**Description**</span></span>                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| <span data-ttu-id="1d8bb-185">SRS v2-SRS 응용 프로그램 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-185">SRS v2 - SRS Application Package</span></span>     | <span data-ttu-id="1d8bb-186">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-186">Software package</span></span>       | <span data-ttu-id="1d8bb-187">Microsoft 팀 대화방 배포 키트 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-187">Package for the Microsoft Teams Rooms deployment kit</span></span>                                      |
| <span data-ttu-id="1d8bb-188">SRS v2-Sysprep 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-188">SRS v2 - Sysprep Package</span></span>             | <span data-ttu-id="1d8bb-189">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-189">Software package</span></span>       | <span data-ttu-id="1d8bb-190">Microsoft 팀 대화방 단위를 구성 하는 사용자 지정 무인 .xml 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-190">Package for the custom Unattended.xml to configure Microsoft Teams Rooms units</span></span>            |
| <span data-ttu-id="1d8bb-191">SRS v2-집합-SRSComputerName 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-191">SRS v2 - Set-SRSComputerName Package</span></span> | <span data-ttu-id="1d8bb-192">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-192">Software package</span></span>       | <span data-ttu-id="1d8bb-193">배포 중 컴퓨터 이름을 할당 하는 HTA (HTML application) 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-193">Package for the HTML application (HTA) to assign a computer name during the deployment</span></span>    |
| <span data-ttu-id="1d8bb-194">SRS v2-SRS 설정 구성</span><span class="sxs-lookup"><span data-stu-id="1d8bb-194">SRS v2 - Configure SRS Setup</span></span>         | <span data-ttu-id="1d8bb-195">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-195">Software package</span></span>       | <span data-ttu-id="1d8bb-196">Microsoft 팀 대화방 앱 배포를 구성 하기 위한 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-196">Package to configure deployment of the Microsoft Teams Rooms app</span></span>                          |
| <span data-ttu-id="1d8bb-197">SRS v2-OS 업데이트 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-197">SRS v2 - OS Updates Package</span></span>          | <span data-ttu-id="1d8bb-198">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-198">Software package</span></span>       | <span data-ttu-id="1d8bb-199">필수 운영 체제 업데이트를 배포 하기 위한 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-199">Package to deploy mandatory operating system updates</span></span>                                      |
| <span data-ttu-id="1d8bb-200">SRS v2-루트 인증서 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-200">SRS v2 - Root Certificate Package</span></span>    | <span data-ttu-id="1d8bb-201">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-201">Software package</span></span>       | <span data-ttu-id="1d8bb-202">선택-루트 인증서를 배포 하기 위한 패키지 (도메인 가입 된 장치에 필요 하지 않음)</span><span class="sxs-lookup"><span data-stu-id="1d8bb-202">Optional - Package to deploy the root certificate (not required for domain-joined units)</span></span>  |
| <span data-ttu-id="1d8bb-203">SRS v2-Microsoft Monitoring Agent 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-203">SRS v2 - Microsoft Monitoring Agent Package</span></span> | <span data-ttu-id="1d8bb-204">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-204">Software package</span></span>       | <span data-ttu-id="1d8bb-205">선택-Microsoft Operations Management Suite 에이전트를 배포 하 고 구성 하는 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-205">Optional - Package to deploy and configure the Microsoft Operations Management Suite agent</span></span>|
| <span data-ttu-id="1d8bb-206">SRS v2-WinPE 백그라운드 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-206">SRS v2 - WinPE Background Package</span></span>    | <span data-ttu-id="1d8bb-207">소프트웨어 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-207">Software package</span></span>       | <span data-ttu-id="1d8bb-208">부팅 이미지와 함께 사용할 사용자 지정 배경 이미지를 위한 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-208">Package for the custom background image to use with boot images</span></span>                           |
| <span data-ttu-id="1d8bb-209">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1d8bb-209">Windows 10 Enterprise</span></span>                | <span data-ttu-id="1d8bb-210">운영 체제 이미지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-210">Operating system image</span></span> | <span data-ttu-id="1d8bb-211">운영 체제 설치 파일 (.wim)에 대 한 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-211">Package for the operating system installation file (install.wim)</span></span>                          |
| <span data-ttu-id="1d8bb-212">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="1d8bb-212">Surface Pro</span></span>                          | <span data-ttu-id="1d8bb-213">드라이버 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-213">Driver package</span></span>         | <span data-ttu-id="1d8bb-214">Microsoft Surface Pro 용 장치 드라이버 및 펌웨어의 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-214">Package for the device drivers and firmware for Microsoft Surface Pro</span></span>                     |
| <span data-ttu-id="1d8bb-215">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="1d8bb-215">Surface Pro 4</span></span>                        | <span data-ttu-id="1d8bb-216">드라이버 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-216">Driver package</span></span>         | <span data-ttu-id="1d8bb-217">Microsoft Surface Pro 4 용 장치 드라이버 및 펌웨어의 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-217">Package for the device drivers and firmware for Microsoft Surface Pro 4</span></span>                   |

<span data-ttu-id="1d8bb-218">자세한 내용은 [Configuration Manager에서 패키지 및 프로그램](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-218">For more information, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>

### <a name="create-folders-for-the-package-source-files"></a><span data-ttu-id="1d8bb-219">패키지 원본 파일에 대 한 폴더 만들기</span><span class="sxs-lookup"><span data-stu-id="1d8bb-219">Create folders for the package source files</span></span>

<span data-ttu-id="1d8bb-220">구성 관리자를 사용 하려면 패키지 원본 파일이 처음 만들어지고 업데이트 될 때 특정 폴더 구조에 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-220">Configuration Manager requires package source files to be organized in a specific folder structure when they’re first created and when they’re updated.</span></span>

<span data-ttu-id="1d8bb-221">Microsoft Endpoint Configuration Manager 중앙 관리 사이트 또는 기본 사이트 또는 패키지 원본 파일을 호스트 하는 데 사용 중인 서버 공유에 다음 폴더 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-221">Create the following folder structure on the Microsoft Endpoint Configuration Manager central administration site or primary site, or on a server share you’re using to host package source files:</span></span>

-   <span data-ttu-id="1d8bb-222">SRS v2-Microsoft Monitoring Agent 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-222">SRS v2 - Microsoft Monitoring Agent Package</span></span>
-   <span data-ttu-id="1d8bb-223">SRS v2-OS 업데이트 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-223">SRS v2 - OS Updates Package</span></span>
-   <span data-ttu-id="1d8bb-224">SRS v2-루트 인증서 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-224">SRS v2 - Root Certificate Package</span></span>
-   <span data-ttu-id="1d8bb-225">SRS v2-집합-SRSComputerName 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-225">SRS v2 - Set-SRSComputerName Package</span></span>
-   <span data-ttu-id="1d8bb-226">SRS v2-SRS 응용 프로그램 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-226">SRS v2 - SRS Application Package</span></span>
-   <span data-ttu-id="1d8bb-227">SRS v2-SRS 설정 구성</span><span class="sxs-lookup"><span data-stu-id="1d8bb-227">SRS v2 - Configure SRS Setup</span></span>
-   <span data-ttu-id="1d8bb-228">SRS v2-Sysprep 패키지</span><span class="sxs-lookup"><span data-stu-id="1d8bb-228">SRS v2 - Sysprep Package</span></span>
-   <span data-ttu-id="1d8bb-229">드라이버</span><span class="sxs-lookup"><span data-stu-id="1d8bb-229">Drivers</span></span>
    -   <span data-ttu-id="1d8bb-230">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="1d8bb-230">Surface Pro</span></span>
    -   <span data-ttu-id="1d8bb-231">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="1d8bb-231">Surface Pro 4</span></span>
-   <span data-ttu-id="1d8bb-232">운영 체제</span><span class="sxs-lookup"><span data-stu-id="1d8bb-232">Operating Systems</span></span>
    -   <span data-ttu-id="1d8bb-233">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1d8bb-233">Windows 10 Enterprise</span></span>

> [!TIP]
> <span data-ttu-id="1d8bb-234">패키지의 폴더 구조, 사용 해야 하는 스크립트, 가져오는 데 필요한 작업 순서 템플릿을 포함 하는 zip 파일을 [다운로드](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) 하 여 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-234">You may also [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) and use the zip file that includes the folder structure for the packages, the scripts that you need to use, and the task sequence template, that you need to import.</span></span>

### <a name="create-the-monitoring-agent-package"></a><span data-ttu-id="1d8bb-235">모니터링 에이전트 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="1d8bb-235">Create the Monitoring agent package</span></span>

1. <span data-ttu-id="1d8bb-236">에서 <https://go.microsoft.com/fwlink/?LinkId=828603>모니터링 에이전트를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-236">Download the Monitoring agent from <https://go.microsoft.com/fwlink/?LinkId=828603>.</span></span>

2. <span data-ttu-id="1d8bb-237">명령 프롬프트 창을 열고 **MMASetup-AMD64/c:** 명령 프롬프트에서 다음을 입력 하 여 **SRS V2-Microsoft Monitoring Agent 패키지** 폴더로 패키지를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-237">Extract the package into the **SRS v2 - Microsoft Monitoring Agent Package** folder by opening a Command Prompt window and entering **MMASetup-AMD64.exe /C:**     at the command prompt.</span></span>

3. <span data-ttu-id="1d8bb-238">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-238">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="1d8bb-239">패키지를 만들려면 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-239">Enter the following information to create the package:</span></span>

   - <span data-ttu-id="1d8bb-240">이름<strong>: SRS v2-Microsoft Monitoring Agent 패키지</strong></span><span class="sxs-lookup"><span data-stu-id="1d8bb-240">Name<strong>: SRS v2 - Microsoft Monitoring Agent Package</strong></span></span>

   - <span data-ttu-id="1d8bb-241">제조 업체<strong>: Microsoft Corporation</strong></span><span class="sxs-lookup"><span data-stu-id="1d8bb-241">Manufacturer<strong>: Microsoft Corporation</strong></span></span>

   - <span data-ttu-id="1d8bb-242">버전<strong>: 8.1.11081.0</strong> (다운로드 한 설치 파일의 버전을 입력 하십시오.)</span><span class="sxs-lookup"><span data-stu-id="1d8bb-242">Version<strong>: 8.1.11081.0</strong> (enter the version of the downloaded installation file)</span></span>

   - <span data-ttu-id="1d8bb-243">**이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2-Microsoft Monitoring Agent 패키지** 폴더 경로를 입력 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-243">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Microsoft Monitoring Agent Package** folder, and then select **Next**.</span></span>

5. <span data-ttu-id="1d8bb-244">**프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-244">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="1d8bb-245">**설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-245">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="1d8bb-246">**닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-246">Select **Close**.</span></span>

### <a name="create-the-operating-system-updates-package"></a><span data-ttu-id="1d8bb-247">운영 체제 업데이트 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="1d8bb-247">Create the operating system updates package</span></span>

1. <span data-ttu-id="1d8bb-248">**SRS v2-OS 업데이트 패키지** 폴더에서 **Install-SRSv2-OS-Updates**이라는 새 PowerShell 스크립트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-248">In the **SRS v2 - OS Updates Package** folder, create a new PowerShell script named **Install-SRSv2-OS-Updates.ps1**.</span></span>

2. <span data-ttu-id="1d8bb-249">아래 스크립트를 **Install-SRSv2-OS-Updates** 스크립트에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-249">Copy the script below into the **Install-SRSv2-OS-Updates.ps1** script.</span></span> <span data-ttu-id="1d8bb-250">또는 [여기](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)에서 Install-SRSv2-OS-Updates 스크립트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-250">Alternatively, you can download the Install-SRSv2-OS-Updates.ps1 script from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="1d8bb-251">동일한 폴더에 필수 Windows 업데이트 패키지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-251">Download the mandatory Windows Update packages into the same folder.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1d8bb-252">이 문서를 게시 한 시점에는 [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) 만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-252">At the time this article was published, only [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) was required.</span></span> <span data-ttu-id="1d8bb-253">[Microsoft 팀 대화방 콘솔 구성을](console.md)확인 하 여 다른 업데이트가 필요한 지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-253">Check [Configure a Microsoft Teams Rooms console](console.md), to see whether any other updates are required.</span></span>

4. <span data-ttu-id="1d8bb-254">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-254">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

5. <span data-ttu-id="1d8bb-255">패키지를 만들려면 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-255">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="1d8bb-256">이름: **SRS v2-OS 업데이트 패키지**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-256">Name: **SRS v2 – OS Updates Package**</span></span>
   -   <span data-ttu-id="1d8bb-257">제조 업체: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-257">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="1d8bb-258">버전: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-258">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="1d8bb-259">**이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2-OS 업데이트 패키지** 폴더 경로를 입력 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-259">Select the **This package contains source files** check box, enter the path to the **SRS v2 - OS Updates Package** folder, and then select **Next**.</span></span>

6. <span data-ttu-id="1d8bb-260">**프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-260">Select **Do not create a program**, and then select **Next**.</span></span>

7. <span data-ttu-id="1d8bb-261">**설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-261">Review the **Confirm the settings** page, and then select **Next**.</span></span>

8. <span data-ttu-id="1d8bb-262">**닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-262">Select **Close**.</span></span>

### <a name="create-the-root-certificate-package-optional"></a><span data-ttu-id="1d8bb-263">루트 인증서 패키지 만들기 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="1d8bb-263">Create the root certificate package (optional)</span></span>

<span data-ttu-id="1d8bb-264">Active Directory 도메인에 가입 되지 않은 디바이스에 대 한 루트 인증서를 배포 하기 위해이 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-264">You create this package to distribute the root certificate for devices that won’t be joined to an Active Directory domain.</span></span> <span data-ttu-id="1d8bb-265">다음 두 조건이 모두 적용 되는 경우에만이 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-265">Create this package only if both the following conditions apply:</span></span>
-   <span data-ttu-id="1d8bb-266">배포에 온-프레미스 Lync 또는 비즈니스용 Skype Server가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-266">Your deployment includes on-premises Lync or Skype for Business Server.</span></span>
-   <span data-ttu-id="1d8bb-267">Microsoft 팀 대화방 단위는 도메인 구성원이 아닌 작업 그룹에서 작동 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-267">Microsoft Teams Rooms units are configured to work in a workgroup instead of a domain member.</span></span>

1.  <span data-ttu-id="1d8bb-268">루트 인증서를 **SRS v2-루트 인증서 패키지** 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-268">Copy the root certificate into the **SRS v2 – Root Certificate Package** folder.</span></span>

2.  <span data-ttu-id="1d8bb-269">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-269">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

3.  <span data-ttu-id="1d8bb-270">패키지를 만들려면 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-270">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="1d8bb-271">이름: **SRS v2 – 루트 인증서 패키지**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-271">Name: **SRS v2 – Root Certificate Package**</span></span>
    -   <span data-ttu-id="1d8bb-272">제조업체: *조직의 이름*</span><span class="sxs-lookup"><span data-stu-id="1d8bb-272">Manufacturer: *Your organization’s name*</span></span>
    -   <span data-ttu-id="1d8bb-273">버전: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-273">Version: **1.0.0**</span></span>
    -   <span data-ttu-id="1d8bb-274">**이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2-루트 인증서 패키지** 폴더의 경로를 입력 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-274">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Root Certificate Package** folder, and then select **Next**.</span></span>

4.  <span data-ttu-id="1d8bb-275">**프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-275">Select **Do not create a program**, and then select **Next**.</span></span>

5.  <span data-ttu-id="1d8bb-276">**설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-276">Review the **Confirm the settings** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="1d8bb-277">**닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-277">Select **Close**.</span></span>

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a><span data-ttu-id="1d8bb-278">Microsoft 팀 대화방 배포 키트 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="1d8bb-278">Create the Microsoft Teams Rooms deployment kit package</span></span>

1.  <span data-ttu-id="1d8bb-279">의 **Microsoft 팀 공간 배포 키트** 최신 버전 <https://go.microsoft.com/fwlink/?linkid=851168>을 다운로드 하 여 워크스테이션에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-279">Download the latest version of the **Microsoft Teams Rooms deployment kit** from <https://go.microsoft.com/fwlink/?linkid=851168>, and install it to a workstation.</span></span>

2.  <span data-ttu-id="1d8bb-280">**C:\\Program Files (x86)\\Skype 회의실 시스템 배포 키트** 의 콘텐츠를 **SRS v2-srs 응용 프로그램 패키지** 폴더로 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-280">Copy the content from **C:\\Program Files (x86)\\Skype Room System Deployment Kit** to the **SRS v2 - SRS Application Package** folder.</span></span>

3.  <span data-ttu-id="1d8bb-281">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-281">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="1d8bb-282">패키지를 만들려면 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-282">Enter the following information to create the package:</span></span>
    -   <span data-ttu-id="1d8bb-283">이름: **srs v2-Srs 응용 프로그램 패키지**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-283">Name: **SRS v2 – SRS Application Package**</span></span>
    -   <span data-ttu-id="1d8bb-284">제조 업체: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-284">Manufacturer: **Microsoft Corporation**</span></span>
    -   <span data-ttu-id="1d8bb-285">버전: **3.1.104.0** (다운로드 한 설치 파일의 버전을 입력 하십시오.)</span><span class="sxs-lookup"><span data-stu-id="1d8bb-285">Version: **3.1.104.0** (enter the version of the downloaded installation file)</span></span>
    -   <span data-ttu-id="1d8bb-286">**이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2-Srs 응용 프로그램 패키지** 폴더 경로를 입력 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-286">Select the **This package contains source files** check box, enter the path to the **SRS v2 – SRS Application Package** folder, and then select **Next**.</span></span>
5.  <span data-ttu-id="1d8bb-287">**프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-287">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="1d8bb-288">**설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-288">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="1d8bb-289">**닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-289">Select **Close**.</span></span>

### <a name="create-the-computer-name-assignment-package"></a><span data-ttu-id="1d8bb-290">컴퓨터 이름 할당 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="1d8bb-290">Create the computer name assignment package</span></span>

1.  <span data-ttu-id="1d8bb-291">**SRS V2 Set-SRSComputerName 패키지** 폴더에서 **SET-SRSCOMPUTERNAME** 이라는 새 HTML 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-291">In the **SRS v2 - Set-SRSComputerName Package** folder, create a new HTML application named **Set-SRSComputerName.hta** .</span></span>

2.  <span data-ttu-id="1d8bb-292">**Set-SRSComputerName** 파일에 다음 스크립트를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-292">Copy the following script into the **Set-SRSComputerName.hta** file.</span></span> <span data-ttu-id="1d8bb-293">또는 [여기](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)에서 Set-SRSComputerName 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-293">Alternatively, you can download the Set-SRSComputerName.hta file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3.  <span data-ttu-id="1d8bb-294">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-294">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4.  <span data-ttu-id="1d8bb-295">패키지를 만들려면 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-295">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="1d8bb-296">Name: **SRS V2 Set-SRSComputerName 패키지**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-296">Name: **SRS v2 - Set-SRSComputerName Package**</span></span>

    -   <span data-ttu-id="1d8bb-297">제조 업체: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-297">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="1d8bb-298">버전: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-298">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="1d8bb-299">**이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2 집합-Srscomputername 패키지** 폴더 경로를 입력 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-299">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Set-SRSComputerName Package** folder, and then select **Next**.</span></span>

5.  <span data-ttu-id="1d8bb-300">**프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-300">Select **Do not create a program**, and then select **Next**.</span></span>

6.  <span data-ttu-id="1d8bb-301">**설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-301">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7.  <span data-ttu-id="1d8bb-302">**닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-302">Select **Close**.</span></span>

### <a name="create-the-sysprep-package"></a><span data-ttu-id="1d8bb-303">Sysprep 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="1d8bb-303">Create the Sysprep package</span></span>

1. <span data-ttu-id="1d8bb-304">**SRS v2-Sysprep 패키지** 폴더에서 **UNATTEND.XML** 이라는 새 XML 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-304">In the **SRS v2 – Sysprep Package** folder, create a new XML file named **Unattend.xml** .</span></span>

2. <span data-ttu-id="1d8bb-305">다음 텍스트를 **Unattend .xml** 파일에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-305">Copy the following text into the **Unattend.xml** file.</span></span> <span data-ttu-id="1d8bb-306">또는 [여기](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)에서 unattend.xml 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-306">Alternatively, you can download the Unattend.xml file from [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true).</span></span>
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
3. <span data-ttu-id="1d8bb-307">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-307">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

4. <span data-ttu-id="1d8bb-308">패키지를 만들려면 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-308">Enter the following information to create the package:</span></span>
   -   <span data-ttu-id="1d8bb-309">이름: **SRS v2-Sysprep 패키지**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-309">Name: **SRS v2 - Sysprep Package**</span></span>
   -   <span data-ttu-id="1d8bb-310">제조 업체: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-310">Manufacturer: **Microsoft Corporation**</span></span>
   -   <span data-ttu-id="1d8bb-311">버전: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-311">Version: **1.0.0**</span></span>
   -   <span data-ttu-id="1d8bb-312">**이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2-Sysprep 패키지** 폴더 경로를 입력 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-312">Select the **This package contains source files** check box, enter the path to the **SRS v2 – Sysprep Package** folder, and then select **Next**.</span></span>
5. <span data-ttu-id="1d8bb-313">**프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-313">Select **Do not create a program**, and then select **Next**.</span></span>

6. <span data-ttu-id="1d8bb-314">**설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-314">Review the **Confirm the settings** page, and then select **Next**.</span></span>

7. <span data-ttu-id="1d8bb-315">**닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-315">Select **Close**.</span></span>

### <a name="create-the-windows-10-enterprise-package"></a><span data-ttu-id="1d8bb-316">Windows 10 Enterprise 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="1d8bb-316">Create the Windows 10 Enterprise package</span></span>

1.  <span data-ttu-id="1d8bb-317">Windows 10 Enterprise x64 미디어를 구하여 **설치 .wim** 파일을 **운영 체제\\Windows 10 enterprise** 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-317">Obtain a Windows 10 Enterprise x64 media, and copy the **install.wim** file to the **Operating Systems\\Windows 10 Enterprise** folder.</span></span>

2.  <span data-ttu-id="1d8bb-318">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **운영** \> **체제로 이동한**다음 운영 체제 이미지 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-318">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**, and then select **Add Operating System Image**.</span></span>

3.  <span data-ttu-id="1d8bb-319">방금 복사한 **설치 .wim** 파일의 경로를 지정 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-319">Specify the path to the **install.wim** file you just copied, and then select **Next**.</span></span>

4.  <span data-ttu-id="1d8bb-320">Windows 10 Enterprise 이미지의 빌드 번호와 일치 하도록 **Version** 필드를 업데이트 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-320">Update the **Version** field to match the build number of the Windows 10 Enterprise image, and then select **Next**.</span></span>

5.  <span data-ttu-id="1d8bb-321">**세부 정보** 페이지를 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-321">Review the **Details** page, and then select **Next**.</span></span>

6.  <span data-ttu-id="1d8bb-322">**닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-322">Select **Close**.</span></span>

<span data-ttu-id="1d8bb-323">자세한 내용은 [Configuration Manager를 사용 하 여 OS 이미지 관리](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-323">For more information, see [Manage OS images with Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-operating-system-images).</span></span>

### <a name="create-surface-pro-device-driver-packages"></a><span data-ttu-id="1d8bb-324">Surface Pro 장치 드라이버 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="1d8bb-324">Create Surface Pro device driver packages</span></span>

<span data-ttu-id="1d8bb-325">Microsoft 팀 대화방은 Surface Pro 및 Surface Pro 4에서 모두 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-325">Microsoft Teams Rooms is supported for both Surface Pro and Surface Pro 4.</span></span> <span data-ttu-id="1d8bb-326">환경에 있는 각 Surface Pro 모델에 대 한 드라이버 패키지를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-326">You need to create a driver package for each Surface Pro model you have in your environment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d8bb-327">드라이버는 Windows 10 Enterprise 빌드 및 Microsoft 팀 대화방 배포 키트 버전과 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-327">The drivers must be compatible with the Windows 10 Enterprise build and the Microsoft Teams Rooms deployment kit version.</span></span> <span data-ttu-id="1d8bb-328">자세한 내용은 [Surface 장치에 대 한 최신 펌웨어 및 드라이버 다운로드](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) 및 [콘솔 구성을](console.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-328">For more information, see [Download the latest firmware and drivers for Surface devices](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) and [Configure a console](console.md).</span></span>

1.  <span data-ttu-id="1d8bb-329">최신 드라이버 및 펌웨어를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-329">Download the latest drivers and firmware.</span></span>
    -   <span data-ttu-id="1d8bb-330">Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484></span><span class="sxs-lookup"><span data-stu-id="1d8bb-330">For Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484></span></span>
    -   <span data-ttu-id="1d8bb-331">Surface Pro 4의 경우:<https://www.microsoft.com/download/details.aspx?id=49498></span><span class="sxs-lookup"><span data-stu-id="1d8bb-331">For Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498></span></span>

2.  <span data-ttu-id="1d8bb-332">다운로드 한 드라이버와 펌웨어를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-332">Extract the downloaded driver and firmware.</span></span> <span data-ttu-id="1d8bb-333">명령 프롬프트 창을 열고 명령 프롬프트에서 다음 명령 중 하나를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-333">Open a Command Prompt window and at the command prompt, enter one of the following commands:</span></span>
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  <span data-ttu-id="1d8bb-334">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **운영 체제** \> **드라이버로**이동한 다음 **드라이버 가져오기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-334">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Drivers**, and then select **Import Driver**.</span></span>

4.  <span data-ttu-id="1d8bb-335">**다음 네트워크 경로 (UNC)에서 모든 드라이버 가져오기를**선택 하 고 원본 폴더 (예: C\\: _Sources\\drivers\\Surface Pro)를 선택한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-335">Select **Import all drivers in the following network path (UNC)**, select the source folder (for example, C:\\_Sources\\Drivers\\Surface Pro), and then select **Next**.</span></span>

5.  <span data-ttu-id="1d8bb-336">**가져온 드라이버에 대 한 세부 정보 지정** 페이지에서 나열 된 모든 드라이버를 선택 하 고 **다음 드라이버 사용 및 컴퓨터에서 설치 하도록 허용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-336">On the **Specify the details for the imported drivers** page, select all the listed drivers, and then select **Enable these drivers and allow computers to install them**.</span></span>

6.  <span data-ttu-id="1d8bb-337">**범주**를 선택 하 고, 표면 모델과 일치 하는 새 범주를 만들고, **확인**을 선택한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-337">Select **Categories**, create a new category that matches the Surface model, select **OK**, and then select **Next**.</span></span>

7.  <span data-ttu-id="1d8bb-338">**새 패키지**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-338">Select **New Package**.</span></span>

8.  <span data-ttu-id="1d8bb-339">Surface Pro 모델과 일치 하는 패키지 이름을 지정 하 고, 드라이버 패키지 파일을 저장할 폴더 경로를 입력 하 고, **확인**을 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-339">Specify the package name that matches the Surface Pro model, enter a folder path to store the driver package files in, select **OK**, and then select **Next**.</span></span>

9.  <span data-ttu-id="1d8bb-340">**부팅 이미지** 페이지에서 부팅 이미지가 선택 되어 있지 않은지 확인 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-340">On the **boot images** page, ensure that no boot images are selected, and then select **Next**.</span></span>

10. <span data-ttu-id="1d8bb-341">**닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-341">Select **Close**.</span></span>

11. <span data-ttu-id="1d8bb-342">**소프트웨어 라이브러리** \> **운영 체제** \> **드라이버로**이동 하 고 **폴더 \> 만들기**를 선택한 다음 방금 드라이버를 가져온 Surface Pro 모델과 일치 하는 폴더 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-342">Go to **Software Library** \> **Operating Systems** \> **Drivers**, select **Folder \> Create Folder**, and enter a folder name that matches the Surface Pro model that you just imported the drivers for.</span></span>

12. <span data-ttu-id="1d8bb-343">가져온 모든 드라이버를 새로 만든 폴더로 이동 하 여 탐색 및 작업을 더 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-343">Move all the imported drivers to the newly created folder for easier navigation and operation.</span></span>

> [!NOTE]
> <span data-ttu-id="1d8bb-344">사용할 수 있는 다른 Surface Pro 모델에 대해 같은 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-344">Repeat the same steps for other Surface Pro models you might have.</span></span> <span data-ttu-id="1d8bb-345">자세한 내용은 [구성 관리자에서 드라이버 관리](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-345">For more information, see [Manage drivers in Configuration Manager](https://docs.microsoft.com/configmgr/osd/get-started/manage-drivers).</span></span>

### <a name="create-microsoft-teams-rooms-configuration-package"></a><span data-ttu-id="1d8bb-346">Microsoft 팀 대화방 구성 패키지 만들기</span><span class="sxs-lookup"><span data-stu-id="1d8bb-346">Create Microsoft Teams Rooms Configuration Package</span></span>

1.  <span data-ttu-id="1d8bb-347">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동한 다음 **패키지 만들기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-347">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**, and then select **Create Package**.</span></span>

2.  <span data-ttu-id="1d8bb-348">패키지를 만들려면 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-348">Enter the following information to create the package:</span></span>

    -   <span data-ttu-id="1d8bb-349">이름: **srs v2-Srs 설치 패키지 구성**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-349">Name: **SRS v2 - Configure SRS Setup Package**</span></span>

    -   <span data-ttu-id="1d8bb-350">제조 업체: **Microsoft Corporation**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-350">Manufacturer: **Microsoft Corporation**</span></span>

    -   <span data-ttu-id="1d8bb-351">버전: **1.0.0**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-351">Version: **1.0.0**</span></span>

    -   <span data-ttu-id="1d8bb-352">**이 패키지에 원본 파일 포함** 확인란을 선택 하 고 **SRS V2-srs 구성 설정** 폴더 경로를 입력 한 후 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-352">Select the **This package contains source files** check box, enter the path to the **SRS v2 - Configure SRS Setup** folder, and then select **Next**.</span></span>

3.  <span data-ttu-id="1d8bb-353">**프로그램 만들지 않음을**선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-353">Select **Do not create a program**, and then select **Next**.</span></span>

4.  <span data-ttu-id="1d8bb-354">**설정 확인** 페이지를 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-354">Review the **Confirm the settings** page, and then select **Next**.</span></span>

5.  <span data-ttu-id="1d8bb-355">**닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-355">Select **Close**.</span></span>



## <a name="distribute-configuration-manager-packages"></a><span data-ttu-id="1d8bb-356">Configuration Manager 패키지 배포</span><span class="sxs-lookup"><span data-stu-id="1d8bb-356">Distribute Configuration Manager packages</span></span>

<span data-ttu-id="1d8bb-357">모든 패키지는 Configuration Manager 계층 구조에서 배포 지점이 역할을 할당 한 서버에 배포 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-357">All the packages must be distributed to the servers that have been assigned the distribution point role in the Configuration Manager hierarchy.</span></span> <span data-ttu-id="1d8bb-358">패키지 배포를 시작 하려면 아래 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-358">Follow the instructions below to initiate package distribution.</span></span>

1.  <span data-ttu-id="1d8bb-359">소프트웨어 패키지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-359">Distribute software packages.</span></span>

    1.  <span data-ttu-id="1d8bb-360">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **응용 프로그램 관리** \> **패키지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-360">In the Configuration Manager console, go to **Software Library** \> **Application Management** \> **Packages**.</span></span> <span data-ttu-id="1d8bb-361">배포 하려는 소프트웨어 패키지를 모두 선택 하 고 **콘텐츠 배포**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-361">Select all the software packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="1d8bb-362">패키지 목록을 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-362">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="1d8bb-363">모든 배포 지점의 서버 (또는 Configuration Manager 계층 구조에 따라 배포 지점의 그룹)를 목록에 추가 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-363">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="1d8bb-364">**다음**을 선택 하 고 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-364">Select **Next**, and then select **Close**.</span></span>

2.  <span data-ttu-id="1d8bb-365">드라이버 패키지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-365">Distribute driver packages.</span></span>

    1.  <span data-ttu-id="1d8bb-366">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> 의 **운영 체제** \> **드라이버 패키지로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-366">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Driver Packages**.</span></span> <span data-ttu-id="1d8bb-367">배포 하려는 모든 드라이버 패키지를 선택 하 고 **콘텐츠 배포**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-367">Select all the driver packages you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="1d8bb-368">패키지 목록을 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-368">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="1d8bb-369">모든 배포 지점의 서버 (또는 Configuration Manager 계층 구조에 따라 배포 지점의 그룹)를 목록에 추가 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-369">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="1d8bb-370">**다음**을 선택 하 고 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-370">Select **Next**, and then select **Close**.</span></span>

3.  <span data-ttu-id="1d8bb-371">운영 체제 패키지를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-371">Distribute operating system packages.</span></span>

    1.  <span data-ttu-id="1d8bb-372">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **운영** \> 체제 ( **운영 시스템 이미지**)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-372">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Operating System Images**.</span></span> <span data-ttu-id="1d8bb-373">배포 하려는 모든 운영 체제 이미지를 선택한 다음 **콘텐츠 배포**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-373">Select all the operating system images you want to distribute, and then select **Distribute Content**.</span></span>

    2.  <span data-ttu-id="1d8bb-374">패키지 목록을 검토 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-374">Review the list of packages, and then select **Next**.</span></span>

    3.  <span data-ttu-id="1d8bb-375">모든 배포 지점의 서버 (또는 Configuration Manager 계층 구조에 따라 배포 지점의 그룹)를 목록에 추가 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-375">Add all the distribution point servers (or distribution point groups, depending on your Configuration Manager hierarchy) to the list, and then select **Next**.</span></span>

    4.  <span data-ttu-id="1d8bb-376">**다음**을 선택 하 고 **닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-376">Select **Next**, and then select **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="1d8bb-377">패키지 배포에는 패키지 크기, 구성 관리자 계층 구조, 배포 지점의 서버 수, 네트워크에서 사용할 수 있는 대역폭에 따라 약간의 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-377">Package distribution might take some time, depending on the package size, Configuration Manager hierarchy, number of distribution point servers, and the bandwidth available in your network.</span></span>
> 
> <span data-ttu-id="1d8bb-378">Microsoft 팀 회의실 단위 배포를 시작 하려면 먼저 모든 패키지를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-378">All the packages must be distributed before you can start deploying a Microsoft Teams Rooms unit.</span></span>
> 
> <span data-ttu-id="1d8bb-379">\*\*\*\* \> **배포** 상태 \> **콘텐츠 상태**모니터링으로 진행 하 여 Configuration Manager 콘솔에서 패키지 배포의 상태를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-379">You can review the status of your package distribution in the Configuration Manager console by going to **Monitoring** \> **Distribution Status** \> **Content Status**.</span></span>

## <a name="configuration-manager-task-sequences"></a><span data-ttu-id="1d8bb-380">Configuration Manager 작업 순서</span><span class="sxs-lookup"><span data-stu-id="1d8bb-380">Configuration Manager task sequences</span></span>

<span data-ttu-id="1d8bb-381">작업 순서를 구성 관리자와 함께 사용 하 여 운영 체제 이미지를 대상 컴퓨터에 배포 하는 단계를 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-381">You use task sequences with Configuration Manager to automate the steps for deploying an operating system image to a destination computer.</span></span> <span data-ttu-id="1d8bb-382">Microsoft 팀 회의실 단위를 자동화 된 방식으로 배포 하려면 대상 Microsoft 팀 공간 컴퓨터를 시작 하는 데 사용 되는 부팅 이미지, 설치할 Windows 10 Enterprise 운영 체제 이미지, 모든 작업 순서를 만듭니다. 다른 응용 프로그램 또는 소프트웨어 업데이트와 같은 기타 추가 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="1d8bb-382">To deploy a Microsoft Teams Rooms unit in an automated fashion, you create a task sequence that references the boot image used to start the destination Microsoft Teams Rooms computer, the Windows 10 Enterprise operating system image that you want to install, and any other additional content, such as other applications or software updates.</span></span>

### <a name="import-the-sample-task-sequence"></a><span data-ttu-id="1d8bb-383">샘플 작업 순서 가져오기</span><span class="sxs-lookup"><span data-stu-id="1d8bb-383">Import the sample task sequence</span></span>

<span data-ttu-id="1d8bb-384">샘플 작업 순서를 다운로드 하 여 쉽게 가져와 필요에 맞게 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-384">You can download and easily import a sample task sequence and customize it to meet your needs.</span></span>

1.  <span data-ttu-id="1d8bb-385">예제 작업 순서를 [**다운로드**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) 하 고 다운로드 한 zip 파일을 공유 위치에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-385">[**Download**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) the sample task sequence, and copy the downloaded zip file to a shared location.</span></span>
2.  <span data-ttu-id="1d8bb-386">Configuration Manager 콘솔에서 **소프트웨어 라이브러리** \> **운영 체제** \> **작업 시퀀스로**이동한 다음 **작업 순서 가져오기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-386">In the Configuration Manager console, go to **Software Library** \> **Operating Systems** \> **Task Sequences**, and then select **Import Task Sequence**.</span></span>

3.  <span data-ttu-id="1d8bb-387">**찾아보기를**선택 하 고 1 단계에서 사용한 공유 폴더 위치로 이동한 다음 **Microsoft 팀 대화방 배포 (en-us) .zip** 파일을 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-387">Select **Browse**, go to the shared folder location you used in step 1, select the **Microsoft Teams Rooms Deployment (EN-US).zip** file, and then select **Next**.</span></span>

4.  <span data-ttu-id="1d8bb-388">**새로 만들기** **작업** 을 설정 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-388">Set **Action** to **Create New**, and then select **Next**.</span></span>

5.  <span data-ttu-id="1d8bb-389">설정을 확인 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-389">Confirm the settings, and then select **Next**.</span></span>

6.  <span data-ttu-id="1d8bb-390">**닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-390">Select **Close**.</span></span>

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a><span data-ttu-id="1d8bb-391">참조 패키지가 각 작업 순서 단계에 제대로 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-391">Validate that the reference packages are correctly linked to each task sequence step.</span></span>

1. <span data-ttu-id="1d8bb-392">가져온 작업 순서를 선택 하 고 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-392">Select the imported task sequence, and then select **Edit**.</span></span>

    <span data-ttu-id="1d8bb-393">작업 순서 편집기가 열리고 Microsoft 팀 대화방 단위를 배포 하 고 구성 하는 데 필요한 각 순차적 단계가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-393">The Task Sequence Editor opens and displays each sequential step that you need to deploy and configure a Microsoft Teams Rooms unit.</span></span>

2. <span data-ttu-id="1d8bb-394">각 단계를 살펴보고 권장 업데이트를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-394">Walk through each step and complete the recommended updates:</span></span>

   1. <span data-ttu-id="1d8bb-395">**WINDOWS PE에서 다시 시작**:이 단계는 컴퓨터를 다시 시작 하 고 Windows PXE로 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-395">**Restart in Windows PE**: This step restarts and then boots the computer into Windows PXE.</span></span> <span data-ttu-id="1d8bb-396">이 단계에서는 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-396">No changes are required for this step.</span></span>

   2. <span data-ttu-id="1d8bb-397">**파티션 디스크 0 – UEFI**:이 단계에서는 디스크 구성을 닦아내기 하 고 구성 된 설정을 기반으로 파티션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-397">**Partition Disk 0 – UEFI**: This step wipes the disk configuration and creates partitions based on the configured settings.</span></span> <span data-ttu-id="1d8bb-398">이 단계는 변경 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-398">We recommend that you not make any changes to this step.</span></span>

   3. <span data-ttu-id="1d8bb-399">**SRS 컴퓨터 이름 설정**:이 단계에는 배포 중 Microsoft 팀 공간 단위에 대 한 컴퓨터 이름을 설정 하는 UI를 제공 하는 HTML 응용 프로그램이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-399">**Set SRS Computer Name**: This step includes an HTML application to provide a UI to set a computer name for the Microsoft Teams Rooms unit during the deployment.</span></span>
      -  <span data-ttu-id="1d8bb-400">이 단계는 선택 사항 이지만 대체 프로세스를 통해 컴퓨터 명명을 관리 하려는 경우에만 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-400">This is an optional step, but it can only be disabled if you want to manage computer naming through an alternate process.</span></span>
      -  <span data-ttu-id="1d8bb-401">**SRS V2 Set-SRSComputerName** 패키지를 선택 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-401">Verify that the **SRS v2 - Set-SRSComputerName** package is selected.</span></span> <span data-ttu-id="1d8bb-402">그렇지 않으면 패키지를 찾아 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-402">If it isn’t, browse to the package and select it.</span></span>

   4. <span data-ttu-id="1d8bb-403">**운영 체제 적용**:이 단계에서는 배포할 운영 체제 이미지와 무인 Sysprep 응답 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-403">**Apply Operating System**: This step specifies the operating system image to be deployed and the unattended Sysprep answer file to use.</span></span>
      -  <span data-ttu-id="1d8bb-404">올바른 Windows 10 Enterprise 운영 체제 이미지 파일이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-404">Verify that the correct Windows 10 Enterprise operating system image file is selected.</span></span>
      -  <span data-ttu-id="1d8bb-405">**사용자 지정 설치에 무인 또는 sysprep 응답 파일을 사용** 하도록 설정 되어 있는지 확인 하 고 **SRS V2-Sysprep 패키지** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-405">Verify that **Use an unattended or Sysprep answer file for a custom installation** is enabled, and the **SRS v2 - Sysprep Package** is selected.</span></span> <span data-ttu-id="1d8bb-406">또한 **파일 이름이** **unattend.xml**으로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-406">Also ensure that **File Name** is set to **unattend.xml**.</span></span>

   5. <span data-ttu-id="1d8bb-407">**Windows 설정 적용**:이 단계에서는 windows 설치에 대 한 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-407">**Apply Windows Settings**: This step gathers information about the Windows installation.</span></span>
      -  <span data-ttu-id="1d8bb-408">제품 키, 로컬 관리자 계정 암호, 표준 시간대 (필요에 따라 다름)를 포함 하 여 라이선스 및 등록 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-408">Provide licensing and registration information including the product key, local administrator account password, and time zone (depending on your needs).</span></span>

   6. <span data-ttu-id="1d8bb-409">**네트워크 설정 적용**:이 단계에서는 작업 그룹 또는 Active Directory 도메인 이름 및 조직 구성 단위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-409">**Apply Network Settings**: This step allows you to specify a workgroup or Active Directory domain name and organizational unit.</span></span>
      > [!NOTE]
      > <span data-ttu-id="1d8bb-410">Microsoft 팀 대화방 단위를 Actve 디렉터리 도메인의 구성원으로 배포 하는 데 필요한 권장 작업에 대 한 [Skype 대화방 시스템 도메인 참가 고려 사항을](domain-joining-considerations.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-410">See [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.</span></span>
   7. <span data-ttu-id="1d8bb-411">**드라이버 적용:** 이 단계 및 해당 하위 단계는 보유 하 고 있는 Surface Pro 모델을 기반으로 적용 가능한 디바이스 드라이버와 펌웨어를 배포 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-411">**Apply Drivers:** This step and its sub-steps are used to deploy applicable device drivers and firmware based on the Surface Pro model you have.</span></span> <span data-ttu-id="1d8bb-412">각 단계를 업데이트 하 여이 배포와 연결 된 관련 드라이버 패키지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-412">Update each step to specify the relevant driver package associated with this deployment.</span></span>
      -   <span data-ttu-id="1d8bb-413">각 드라이버 패키지는 Surface Pro 만들기 및 모델을 기반으로 관련 드라이버와 펌웨어를 배포 하기 위해 WMI (Windows Management Instrumentation) 필터를 활용 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-413">Each driver package is configured to leverage Windows Management Instrumentation (WMI) filters to deploy relevant drivers and firmware based on the Surface Pro make and model.</span></span>
      -   <span data-ttu-id="1d8bb-414">이러한 드라이버의 구성은 변경 하지 않는 것이 좋으며, 그렇지 않은 경우에는 배포가 실패할 것을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-414">We highly recommend that you not alter the configuration of these drivers, otherwise deployment might fail.</span></span>

   8. <span data-ttu-id="1d8bb-415">**Windows 및 구성 관리자 설정**:이 단계에서는 Configuration manager 클라이언트를 배포 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-415">**Set up Windows and Configuration Manager**: This step deploys and configures the Configuration Manager client.</span></span> <span data-ttu-id="1d8bb-416">이 단계를 업데이트 하 여 기본 제공 Configuration Manager 클라이언트 패키지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-416">Update this step to specify the built-in Configuration Manager Client Package.</span></span>

   9. <span data-ttu-id="1d8bb-417">**루트 인증서 설치**:이 단계는 도메인에 연결 되지 않은 디바이스에 대 한 루트 인증서를 배포 하므로 기본적으로 선택 및 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-417">**Install Root Certificate**: This step distributes the root certificate for non–domain-joined devices, and therefore is optional and disabled by default.</span></span>
      -   <span data-ttu-id="1d8bb-418">Microsoft 팀 회의실 단위에 루트 인증서를 배포 해야 하는 경우이 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-418">Enable this step if you need to deploy a root certificate to the Microsoft Teams Rooms units.</span></span>
      -   <span data-ttu-id="1d8bb-419">이 단계를 수행 해야 하는 경우 **SRS v2-루트 인증서 패키지** 및 **사용 안 함 64 비트 파일 시스템 리디렉션이** 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-419">If you do need to perform this step, verify that the **SRS v2 – Root Certificate Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   10. <span data-ttu-id="1d8bb-420">**모니터링 에이전트 설치 및 구성**:이 단계에서는 64 비트 버전의 Microsoft Azure 모니터 에이전트를 설치 하 고 에이전트를 로그 분석 작업 영역에 연결 하도록 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-420">**Install and Configure Monitoring Agent**: This step installs the 64-bit version of the Microsoft Azure Monitor agent and configures the agent to connect to your Log Analytics workspace.</span></span>
       -   <span data-ttu-id="1d8bb-421">이 단계는 기본적으로 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-421">This step is disabled by default.</span></span> <span data-ttu-id="1d8bb-422">모니터링 에이전트를 사용 하 여 Microsoft 팀 회의실의 상태를 모니터링 하는 경우에만이 단계를 사용 하도록 설정 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-422">Enable this step only if you’re going to use the Monitoring Agent to monitor the health of your Microsoft Teams Rooms units.</span></span>
       -   <span data-ttu-id="1d8bb-423">이 단계를 편집 하 고 명령줄 매개 변수를 업데이트 하 여 **작업 영역 ID** 와 **작업 영역 키**를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-423">Edit this step and update the command-line parameters to specify your **Workspace ID** and **Workspace Key**.</span></span>
       -   <span data-ttu-id="1d8bb-424">Operations Management Suite 작업 영역 ID 및 기본 키를 가져오는 방법에 대 한 자세한 내용은 [Azure 모니터링에 대 한 테스트 장치 구성을](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-424">See [Configure test devices for Azure Monitoring](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) for more information about obtaining the Operations Management Suite Workspace ID and the primary key.</span></span>
       -   <span data-ttu-id="1d8bb-425">**SRS v2-Microsoft Monitoring Agent 패키지** 및 **사용 안 함 64 비트 파일 시스템 리디렉션이** 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-425">Verify that the **SRS v2 – Microsoft Monitoring Agent Package** and **Disable 64-bit file system redirection** are selected.</span></span>
       -   <span data-ttu-id="1d8bb-426">Microsoft 팀 대화방 배포의 상태를 모니터링 하는 방법에 대 한 자세한 내용은 azure [모니터로 Microsoft 팀 대화방 관리 계획](azure-monitor-plan.md), Azure 모니터로 [microsoft 팀 대화방 관리 배포](azure-monitor-deploy.md) 및 [azure Monitor를 사용 하 여 microsoft 팀 공간 장치 관리](azure-monitor-manage.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-426">For more information about monitoring the health of your Microsoft Teams Rooms deployment, see [Plan Microsoft Teams Rooms management with Azure Monitor](azure-monitor-plan.md), [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md) and [Manage Microsoft Teams Rooms devices with Azure Monitor](azure-monitor-manage.md).</span></span>

   11. <span data-ttu-id="1d8bb-427">**SRS V2 구성 파일 복사**:이 단계에서는 Microsoft 팀 대화방 배포 키트의 필수 설정 파일과 구성 파일을 로컬 하드 드라이브에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-427">**Copy SRS v2 Configuration Files**: This step copies the required setup and configuration files from the Microsoft Teams Rooms deployment kit to the local hard drive.</span></span> <span data-ttu-id="1d8bb-428">이 단계에서는 사용자 지정이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-428">No customization is required for this step.</span></span>
       -   <span data-ttu-id="1d8bb-429">**Srs v2-Srs 응용 프로그램 패키지** 및 **사용 안 함 64 비트 파일 시스템 리디렉션이** 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-429">Verify that the **SRS v2 – SRS Application Package** and **Disable 64-bit file system redirection** are selected.</span></span>

   12. <span data-ttu-id="1d8bb-430">**설치-SRSv2-OS-업데이트**:이 단계는 Microsoft 팀 대화방 배포에 필요한 필수 운영 체제 업데이트를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-430">**Install-SRSv2-OS-Updates**: This step deploys any mandatory operating system updates required with the Microsoft Teams Rooms deployment.</span></span> <span data-ttu-id="1d8bb-431">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-431">Do the following:</span></span>
       -   <span data-ttu-id="1d8bb-432">[Microsoft 팀 대화방 콘솔 구성을](console.md) 선택 하 여 필요한 업데이트를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-432">Check [Configure a Microsoft Teams Rooms console](console.md) to see which updates are required.</span></span>
       -   <span data-ttu-id="1d8bb-433">**SRS v2-OS 업데이트 패키지** 에 필수 업데이트가 모두 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-433">Verify that your **SRS v2 – OS Updates Package** includes all the required updates.</span></span>
       -   <span data-ttu-id="1d8bb-434">**SRS v2-OS 업데이트 패키지가** 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-434">Verify that the **SRS v2 – OS Updates Package** is selected.</span></span>
       -   <span data-ttu-id="1d8bb-435">PowerShell 실행 정책이 **Bypass**으로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-435">Verify that the PowerShell execution policy is set to **Bypass**.</span></span>

   13. <span data-ttu-id="1d8bb-436">**컴퓨터 다시 시작**:이 단계에서는 필수 운영 체제 업데이트가 설치 된 후 컴퓨터를 재부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-436">**Restart Computer**: This step reboots the computer after the mandatory operating system updates are installed.</span></span> <span data-ttu-id="1d8bb-437">이 단계에서는 사용자 지정이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-437">No customization is required for this step.</span></span>

   14. <span data-ttu-id="1d8bb-438">**Windows 구성 요소 구성**:이 단계에서는 필요한 Windows 기능을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-438">**Configure Windows Components**: This step configures the required Windows features.</span></span> <span data-ttu-id="1d8bb-439">이 단계에서는 사용자 지정이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-439">No customization is required for this step.</span></span>

   15. <span data-ttu-id="1d8bb-440">**컴퓨터 다시 시작**:이 단계는 Windows 기능을 구성한 후 컴퓨터를 재부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-440">**Restart Computer**: This step reboots the computer after the Windows features are configured.</span></span> <span data-ttu-id="1d8bb-441">이 단계에서는 사용자 지정이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-441">No customization is required for this step.</span></span>

   16. <span data-ttu-id="1d8bb-442">**로컬 Skype 사용자 추가**:이 단계는 Windows에 자동으로 로그인 하 여 Microsoft 팀 회의실 응용 프로그램을 시작 하는 데 사용 되는 로컬 Skype 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-442">**Add Local Skype User**: This step creates the local Skype account used to automatically sign in to Windows and start the Microsoft Teams Rooms application.</span></span> <span data-ttu-id="1d8bb-443">이 단계에는 연결 된 소프트웨어 패키지가 없으며 사용자 지정이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-443">This step doesn’t have any software package associated with it, and no customization is required for it.</span></span>

   17. <span data-ttu-id="1d8bb-444">**SRS 응용 프로그램 설정 및 구성**:이 단계에서는 다음 운영 체제 부팅을 위해 Microsoft 팀 대화방 응용 프로그램 설치를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-444">**Set up and configure SRS application**: This step configures the Microsoft Teams Rooms application installation for the next boot of the operating system.</span></span>
       -   <span data-ttu-id="1d8bb-445">**Srs v2-Srs 설치 패키지 구성** 및 **64 비트 파일 시스템 리디렉션 사용 안 함** 이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-445">Verify that the **SRS v2 – Configure SRS Setup Package** and **Disable 64-bit file system redirection** are selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d8bb-446">작업 순서 단계는 제공 되는 순서 대로 진행 되어야 한다는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-446">It is very important that the task sequence steps must be in the provided order.</span></span> <span data-ttu-id="1d8bb-447">단계의 순서를 수정 하거나 추가 단계를 구성 하면 배포가 중단 될 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-447">Modifying the order of steps, or configuring additional steps might break the deployment.</span></span>
>
> <span data-ttu-id="1d8bb-448">**SRS 응용 프로그램 설정 및 구성** 단계는 작업 순서의 마지막 단계 여야 하며 그렇지 않으면 배포가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-448">**Set up and configure SRS application** step must be the last step in the task sequence, otherwise the deployment might fail.</span></span>

### <a name="create-deployment-for-the-task-sequence"></a><span data-ttu-id="1d8bb-449">작업 순서에 대 한 배포 만들기</span><span class="sxs-lookup"><span data-stu-id="1d8bb-449">Create deployment for the task sequence</span></span>

1. <span data-ttu-id="1d8bb-450">작업 순서를 선택 하 고 **배포**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-450">Select the task sequence, and then select **Deploy**.</span></span>

2. <span data-ttu-id="1d8bb-451">**찾아보기를** 선택 하 여 배포용 대상 모음을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-451">Select **Browse** to select target collection for deployment.</span></span>

3. <span data-ttu-id="1d8bb-452">**알 수 없는 모든 컴퓨터** 를 선택 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-452">Select **All Unknown Computers** and then select **OK**.</span></span>

4. <span data-ttu-id="1d8bb-453">**다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-453">Select **Next**.</span></span>

5. <span data-ttu-id="1d8bb-454">**용도** 드롭다운 목록에서 **사용 가능** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-454">Select **Available** on the **Purpose** drop down list.</span></span>

6. <span data-ttu-id="1d8bb-455">**다음을 사용 하 여 설정** 목록에서 **미디어 및 PXE만** 을 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-455">Select **Only Media and PXE** in the **Make available to the following** list, and then select **Next**.</span></span>
   > [!WARNING]
   > <span data-ttu-id="1d8bb-456">**용도가** **사용 가능**으로 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-456">It is very important that **Purpose** is set to **Available**.</span></span> <span data-ttu-id="1d8bb-457">**용도가** **필수**로 설정 **되지** 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-457">Make sure that the **Purpose** is **NOT** set to **Required**.</span></span> <span data-ttu-id="1d8bb-458">또한 **다음에 사용할 수 있도록 설정**에서 **미디어 및 PXE만** 선택 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-458">Also make sure that you select **Only Media and PXE** in the **Make available to the following**.</span></span>
   >
   > <span data-ttu-id="1d8bb-459">이러한 값을 다른 항목으로 설정 하면 모든 컴퓨터에서 부팅할 때 Microsoft 팀 공간 배포 이미지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-459">Setting these values to something else might cause all computers to get the Microsoft Teams Rooms deployment image when booted.</span></span>
7. <span data-ttu-id="1d8bb-460">일정을 지정 하지 않고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-460">Do not specify any schedule and select **Next**.</span></span>

8. <span data-ttu-id="1d8bb-461">**사용자 환경** 섹션 내에서 아무것도 변경 하지 말고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-461">Do not change anything within the **User Experience** section and select **Next**.</span></span>

9. <span data-ttu-id="1d8bb-462">**알림** 섹션 내에서 아무것도 변경 하지 말고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-462">Do not change anything within the **Alerts** section and select **Next**.</span></span>

10. <span data-ttu-id="1d8bb-463">**배포 지점** 섹션 내에서 아무것도 변경 하지 말고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-463">Do not change anything within the **Distribution Points** section and select **Next**.</span></span>

11. <span data-ttu-id="1d8bb-464">설정을 확인 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-464">Confirm the settings and then select **Next**.</span></span>

12. <span data-ttu-id="1d8bb-465">**닫기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-465">Select **Close**.</span></span>

<a name="validate-and-troubleshoot-the-solution"></a><span data-ttu-id="1d8bb-466">해결 방법 유효성 검사 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1d8bb-466">Validate and troubleshoot the solution</span></span>
--------------------------------------

<span data-ttu-id="1d8bb-467">Microsoft 끝점 구성 관리자 작업 시퀀스를 완료 한 후에는 작업 순서가 Microsoft 팀 대화방 단위를 배포 하 고 구성할 수 있는지 확인 하기 위해 테스트 실행을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-467">After you’ve completed the Microsoft Endpoint Configuration Manager task sequences, you’ll need to perform a test run to validate that the task sequence can deploy and configure Microsoft Teams Rooms units.</span></span>

1.  <span data-ttu-id="1d8bb-468">지원 되는 이더넷 어댑터 중 하나를 사용 하거나 Surface dock를 사용 하 여 테스트 장치를 유선 네트워크에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-468">Connect the test device to the wired network by using one of the supported Ethernet adapters or using the Surface dock.</span></span> <span data-ttu-id="1d8bb-469">PXE 부팅 기능이 환경에 맞게 구성 되지 [않은 경우 이전에 만든](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) usb 플래시 드라이브의 부팅 이미지를 사용 하 여 usb에서 부팅 하 고 구성 관리자에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-469">If PXE boot functionality hasn’t been configured for your environment, you can use the boot image on the USB flash drive [that you created earlier](https://docs.microsoft.com/configmgr/osd/deploy-use/create-bootable-media) to boot from USB and connect to Configuration Manager.</span></span>

2.  <span data-ttu-id="1d8bb-470">펌웨어에 액세스 하 고 PXE 부팅 시작:</span><span class="sxs-lookup"><span data-stu-id="1d8bb-470">Access the firmware and initiate PXE boot:</span></span>

    1.  <span data-ttu-id="1d8bb-471">Surface 디바이스의 전원이 꺼져 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-471">Ensure the Surface device is powered off.</span></span>

    2.  <span data-ttu-id="1d8bb-472">**볼륨 크게** 단추를 길게 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-472">Press and hold the **Volume Up** button.</span></span>

    3.  <span data-ttu-id="1d8bb-473">**전원** 단추를 눌렀다가 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-473">Press and release the **Power** button.</span></span>

    4.  <span data-ttu-id="1d8bb-474">장치가 부팅 되기 시작한 후 **볼륨을 위로** 단추를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-474">After the device begins to boot, release the **Volume Up** button.</span></span>

    5.  <span data-ttu-id="1d8bb-475">**부팅 구성을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-475">Select **Boot configuration**.</span></span>

    6.  <span data-ttu-id="1d8bb-476">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-476">Do one of the following:</span></span>

        -   <span data-ttu-id="1d8bb-477">**PXE 부팅**을 선택 하 고 목록 맨 위로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-477">Select **PXE boot**, and drag it to the top of the list.</span></span> <span data-ttu-id="1d8bb-478">또는 네트워크 어댑터에서 왼쪽으로 살짝 밀어 장치에 바로 부팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-478">Alternatively, you can swipe left on the network adapter to boot to the device immediately.</span></span> <span data-ttu-id="1d8bb-479">이는 부팅 순서에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-479">This won’t affect the boot order.</span></span>
        -   <span data-ttu-id="1d8bb-480">부팅 미디어를 보유 하는 USB 플래시 드라이브를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-480">Select the USB flash drive that holds the boot media.</span></span>

3.  <span data-ttu-id="1d8bb-481">**끝내기**를 선택 하 고 **지금 다시 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-481">Select **Exit**, and then select **Restart Now**.</span></span>

4.  <span data-ttu-id="1d8bb-482">메시지가 표시 되 면 네트워크 부팅 서비스에 대해 **Enter** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-482">When prompted, select **Enter** for network boot service.</span></span>

5.  <span data-ttu-id="1d8bb-483">Windows PE가 메모리에 로드 되 고 작업 순서 마법사가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-483">Windows PE will load into memory, and the Task Sequence Wizard will start.</span></span> <span data-ttu-id="1d8bb-484">**Next (다음** )를 선택 하 여 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-484">Select **Next** to continue.</span></span>

6.  <span data-ttu-id="1d8bb-485">이전에 가져온 작업 순서를 선택 하 고 **다음**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-485">Select the task sequence that you imported earlier, and then select **Next**.</span></span>

7.  <span data-ttu-id="1d8bb-486">디스크 구성이 적용 된 후 장치에 대 한 컴퓨터 이름을 지정 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-486">After the disk configuration is applied, you’ll be prompted to specify a computer name for the device.</span></span> <span data-ttu-id="1d8bb-487">사용자 인터페이스에는 Surface Pro 디바이스의 일련 번호를 기준으로 권장 컴퓨터 이름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-487">The user interface will display a recommended computer name based on the serial number of the Surface Pro device.</span></span> <span data-ttu-id="1d8bb-488">제안 된 이름을 그대로 사용 하거나 새로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-488">You can either accept the proposed name or specify a new one.</span></span> <span data-ttu-id="1d8bb-489">컴퓨터 이름 할당 화면의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-489">Follow the instructions on the computer name assignment screen.</span></span> <span data-ttu-id="1d8bb-490">**수락**을 선택 하면 배포가 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-490">When you select **Accept**, the deployment begins.</span></span>

8.  <span data-ttu-id="1d8bb-491">나머지 배포 프로세스는 자동으로 진행 되며 사용자 입력을 더 이상 요구 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-491">The rest of the deployment process is automatic and doesn’t ask for any more user input.</span></span>

9.  <span data-ttu-id="1d8bb-492">배포 작업 순서에 따라 디바이스 구성이 완료 되 면 Microsoft 팀 대화방 응용 프로그램 설정을 구성 하 라는 다음 구성 화면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-492">After the deployment task sequence finishes configuring the device, you’ll see the following configuration screen that asks you to configure the Microsoft Teams Rooms application settings.</span></span>

    ![Microsoft 팀 대화방 응용 프로그램의 초기 설정 화면](../media/room-systems-scale-image2.png)

10.  <span data-ttu-id="1d8bb-494">Surface Pro를 Microsoft 팀 공간 콘솔에 연결 하 고 응용 프로그램 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-494">Plug the Surface Pro into the Microsoft Teams Rooms console, and configure the application settings.</span></span>

11.  <span data-ttu-id="1d8bb-495">[Microsoft 팀 대화방](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) 에 나열 된 기능이 배포 된 장치에서 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-495">Validate that the capabilities listed in [Microsoft Teams Rooms help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) are working on the deployed device.</span></span>


<span data-ttu-id="1d8bb-496">실패 한 설치 문제를 해결 하려면 Configuration Manager 작업 순서에서 실행 되는 모든 단계를 기록 하는 **Smsts .log** 파일을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-496">To troubleshoot a failed installation, check the **SMSTS.log** file, which logs all the steps executed in a Configuration Manager task sequence.</span></span>

<span data-ttu-id="1d8bb-497">SMSTS .log 파일은 빌드 프로세스의 단계에 따라 여러 경로 중 하나에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-497">The SMSTS.log file is stored on one of a number of paths, depending on the stage of the build process.</span></span> <span data-ttu-id="1d8bb-498">다음 표를 참조 하 여 SMSTS .log 파일의 경로를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-498">Check the following table to identify the path to the SMSTS.log file.</span></span>


| <span data-ttu-id="1d8bb-499">**배포 단계**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-499">**Deployment phase**</span></span>                                                            | <span data-ttu-id="1d8bb-500">**작업 순서 로그 경로**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-500">**Task sequence log path**</span></span>                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| <span data-ttu-id="1d8bb-501">WinPE, HDD 형식 앞</span><span class="sxs-lookup"><span data-stu-id="1d8bb-501">WinPE, before HDD format</span></span>                                                        | <span data-ttu-id="1d8bb-502">X:\\Windows\\\temp\\smstslog\\smsts. 로그</span><span class="sxs-lookup"><span data-stu-id="1d8bb-502">X:\\Windows\\Temp\\smstslog\\smsts.log</span></span>             |
| <span data-ttu-id="1d8bb-503">HDD 형식 이후 WinPE</span><span class="sxs-lookup"><span data-stu-id="1d8bb-503">WinPE, after HDD format</span></span>                                                         | <span data-ttu-id="1d8bb-504">C:\\_SMSTaskSequence\\로그\\Smstslog\\smsts .log</span><span class="sxs-lookup"><span data-stu-id="1d8bb-504">C:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="1d8bb-505">구성 관리자 에이전트를 설치 하기 전에 배포 되는 운영 체제</span><span class="sxs-lookup"><span data-stu-id="1d8bb-505">Operating system deployed, before the Configuration Manager agent was installed</span></span> | <span data-ttu-id="1d8bb-506">c:\\_SMSTaskSequence\\로그\\Smstslog\\smsts .log</span><span class="sxs-lookup"><span data-stu-id="1d8bb-506">c:\\_SMSTaskSequence\\Logs\\Smstslog\\smsts.log</span></span>    |
| <span data-ttu-id="1d8bb-507">운영 체제 및 구성 관리자 에이전트 배포 됨</span><span class="sxs-lookup"><span data-stu-id="1d8bb-507">Operating system and the Configuration Manager agent deployed</span></span>                   | <span data-ttu-id="1d8bb-508">% windir%\\System32\\ccm\\\\Smstslog\\smsts. i i 로그</span><span class="sxs-lookup"><span data-stu-id="1d8bb-508">%windir%\\System32\\ccm\\logs\\Smstslog\\smsts.log</span></span> |
| <span data-ttu-id="1d8bb-509">작업 순서 실행 완료</span><span class="sxs-lookup"><span data-stu-id="1d8bb-509">Task sequence execution complete</span></span>                                                | <span data-ttu-id="1d8bb-510">% windir%\\System32\\ccm\\은\\smsts .log를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-510">%windir%\\System32\\ccm\\logs\\smsts.log</span></span>           |

> [!TIP]
> <span data-ttu-id="1d8bb-511">작업 순서 중 언제 든 지 **F8** 키를 선택 하 여 명령 콘솔을 연 다음 smsts. i f f f f f f f f f f f f f f f f f f f f</span><span class="sxs-lookup"><span data-stu-id="1d8bb-511">You can select **F8** at any time during the task sequence to open a command console, and then get access to the SMSTS.log file.</span></span>

<span data-ttu-id="1d8bb-512">PXE 부팅 문제를 해결 하려면 Configuration Manager 서버의 PXE 동작과 관련 된 두 로그 파일을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-512">To troubleshoot PXE boot issues, check the two log files on the Configuration Manager server that are specific to PXE actions:</span></span>

-   <span data-ttu-id="1d8bb-513">Configuration Manager 설치 로그 디렉터리에 있는 **Pxecontrol .log**</span><span class="sxs-lookup"><span data-stu-id="1d8bb-513">**Pxecontrol.log**, located in the Configuration Manager installation logs directory</span></span>

-   <span data-ttu-id="1d8bb-514">**Smspxe .log**(Configuration Manager 관리 위치 (MP) 로그 디렉터리에 있음)</span><span class="sxs-lookup"><span data-stu-id="1d8bb-514">**Smspxe.log**, located in Configuration Manager Management Point (MP) logs directory</span></span>

<span data-ttu-id="1d8bb-515">Configuration Manager 설치 문제를 해결 하는 데 사용할 수 있는 전체 로그 파일 목록은 Microsoft Endpoint Configuration Manager [로그 파일 참조](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1d8bb-515">For a complete list of the log files that you can use to further troubleshoot your Configuration Manager installation, see the Microsoft Endpoint Configuration Manager [Log file reference](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/log-files).</span></span>
