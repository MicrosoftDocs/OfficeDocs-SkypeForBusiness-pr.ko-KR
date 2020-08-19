---
title: VDI(Virtualized Desktop Infrastructure)용 Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: VDI (가상화 데스크톱 인프라) 환경에서 Microsoft 팀을 실행 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e286611823ddfd12b43abd3a8ff385885fd02a38
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803998"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="a4e61-103">VDI(Virtualized Desktop Infrastructure)용 Teams</span><span class="sxs-lookup"><span data-stu-id="a4e61-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="a4e61-104">이 문서에서는 가상화 된 환경에서 Microsoft 팀을 사용 하는 데 필요한 요구 사항과 제한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="a4e61-105">VDI 란?</span><span class="sxs-lookup"><span data-stu-id="a4e61-105">What is VDI?</span></span>

<span data-ttu-id="a4e61-106">VDI (가상 데스크톱 인프라)는 데스크톱 운영 체제 및 응용 프로그램을 데이터 센터의 중앙 집중식 서버에 호스팅하는 가상화 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="a4e61-107">이렇게 하면 완전히 안전한 중앙 집중화 된 원본을 사용 하 여 사용자에 게 개인 설정 된 데스크톱 환경이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="a4e61-108">가상화 된 환경에서 Microsoft 팀은 채팅 및 공동 작업을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="a4e61-109">또한 Windows 가상 데스크톱, Citrix 및 VMware 플랫폼을 사용 하 여 통화 및 모임 기능도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="a4e61-110">가상화 된 환경의 팀은 여러 구성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="a4e61-111">여기에는 VDI, 전용, 공유, 영구, 비 영구적인 모드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="a4e61-112">기능은 지속적으로 개발 되 고 있으며 정기적으로 추가 되며, 제공 되는 개월 단위와 몇 년 동안 기능이 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="a4e61-113">가상화 된 환경에서 팀을 사용 하는 것은 가상화 되지 않은 환경에서 팀을 사용 하는 것과 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="a4e61-114">예를 들어 가상화 된 환경에서는 일부 고급 기능을 사용할 수 없으며 비디오 해상도가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="a4e61-115">최적의 사용자 환경을 보장 하려면이 문서의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="a4e61-116">VDI 구성 요소의 팀</span><span class="sxs-lookup"><span data-stu-id="a4e61-116">Teams on VDI components</span></span>

<span data-ttu-id="a4e61-117">가상화 된 환경에서 팀을 사용 하려면 다음 구성 요소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-117">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="a4e61-118">**가상화 브로커**: Azure와 같은 가상화 공급자에 대 한 리소스 및 연결 관리자</span><span class="sxs-lookup"><span data-stu-id="a4e61-118">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="a4e61-119">**가상 데스크톱**: Microsoft 팀을 실행 하는 VM (가상 컴퓨터) 스택</span><span class="sxs-lookup"><span data-stu-id="a4e61-119">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="a4e61-120">**씬 클라이언트**: 사용자가 실제 인터페이스를 사용 하는 끝점</span><span class="sxs-lookup"><span data-stu-id="a4e61-120">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="a4e61-121">**팀 데스크톱 앱**: 팀 데스크톱 클라이언트 앱</span><span class="sxs-lookup"><span data-stu-id="a4e61-121">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="a4e61-122">VDI 요구 사항 팀</span><span class="sxs-lookup"><span data-stu-id="a4e61-122">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="a4e61-123">가상화 공급자 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4e61-123">Virtualization provider requirements</span></span>

<span data-ttu-id="a4e61-124">팀 데스크톱 앱의 유효성을 주요 가상화 솔루션 공급자로 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-124">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="a4e61-125">여러 시장 공급자를 사용 하는 경우 가상화 솔루션 공급자에 게 문의 하 여 최소 요구 사항을 충족 하는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-125">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="a4e61-126">현재, AV (오디오/비디오)가 최적화 된 VDI의 팀은 Windows 가상 데스크톱, Citrix 및 VMware를 통해 인증 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-126">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="a4e61-127">이 섹션의 정보를 검토 하 여 적절 한 기능에 대 한 모든 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-127">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="a4e61-128">팀에 대해 인증 된 플랫폼</span><span class="sxs-lookup"><span data-stu-id="a4e61-128">Platforms certified for Teams</span></span>

<span data-ttu-id="a4e61-129">다음 플랫폼에는 팀을 위한 가상 데스크톱 인프라 솔루션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-129">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="a4e61-130">플랫폼</span><span class="sxs-lookup"><span data-stu-id="a4e61-130">Platform</span></span>|<span data-ttu-id="a4e61-131">솔루션</span><span class="sxs-lookup"><span data-stu-id="a4e61-131">Solution</span></span>|
|----|---|
|![Microsoft를 나타내는 로고](media/microsoft-logo.png)| <span data-ttu-id="a4e61-133"><a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows 가상 데스크톱</a></span><span class="sxs-lookup"><span data-stu-id="a4e61-133"><a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![Citrix를 나타내는 로고](media/citrix-logo.png)| <span data-ttu-id="a4e61-135"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 가상 앱 및 데스크톱</a></span><span class="sxs-lookup"><span data-stu-id="a4e61-135"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![VMware를 나타내는 로고](media/vmware-logo.png)| <span data-ttu-id="a4e61-137"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware 구간</a></span><span class="sxs-lookup"><span data-stu-id="a4e61-137"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="a4e61-138">Windows 가상 데스크톱</span><span class="sxs-lookup"><span data-stu-id="a4e61-138">Windows Virtual Desktop</span></span>

<span data-ttu-id="a4e61-139">Windows 가상 데스크톱은 VDI의 팀에 대해 AV 최적화 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-139">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="a4e61-140">자세한 내용 및 요구 사항과 설치에 대 한 자세한 내용은 [Windows 가상 데스크톱에서 팀 사용](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-140">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="a4e61-141">Citrix 가상 앱 및 데스크톱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4e61-141">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="a4e61-142">Citrix 가상 앱 및 데스크톱 (이전의 XenApp 및 XenDesktop)은 VDI의 팀에 대 한 AV 최적화 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-142">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="a4e61-143">Citrix 가상 앱 및 데스크톱을 사용 하는 경우 VDI의 팀은 채팅 및 공동 작업 외에도 통화와 모임 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-143">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="a4e61-144">[Citrix 다운로드 사이트](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)에서 최신 버전의 Citrix 가상 앱 및 데스크톱을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-144">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="a4e61-145">(먼저 로그인 해야 합니다.) 필수 구성 요소는 기본적으로 [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) 및 가상 배달 에이전트 (VDA)에 번들 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-145">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="a4e61-146">CWA 또는 VDA에 추가 구성 요소 또는 플러그인을 설치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-146">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="a4e61-147">최신 서버 및 클라이언트 요구 사항은 [이 Citrix 웹 사이트](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-147">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="a4e61-148">VMware 수평 작업 공간 및 데스크톱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4e61-148">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="a4e61-149">VMware 수평은 가상 데스크톱 전반의 생산성 향상을 위해 VDI의 팀에 최적화 된 AV 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-149">VMware Horizon provides optimized AV support for Teams on VDI for improved productivity across virtual desktops.</span></span> <span data-ttu-id="a4e61-150">[Vmware 다운로드](https://my.vmware.com/web/vmware/downloads/#all_products) 페이지에서 최신 버전의 vmware 구간을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-150">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="a4e61-151">VDI에서 팀 데스크톱 앱 설치 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="a4e61-151">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="a4e61-152">MSI 패키지를 사용 하 여 컴퓨터별 설치 또는 사용자 단위 설치를 사용 하 여 VDI 용 팀 데스크톱 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-152">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="a4e61-153">사용할 접근 방식을 결정 하는 것은 영구적이 든 비영구 설정을 사용 하 고 조직의 관련 기능 필요 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-153">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="a4e61-154">전용 영구적 설정의 경우 두 접근 방법이 모두 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-154">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="a4e61-155">그러나 비영구 설정의 경우 팀에서 효율적으로 작업 하기 위해 컴퓨터별 설치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-155">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="a4e61-156">[비 영구적인 설정](#non-persistent-setup) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-156">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="a4e61-157">컴퓨터 단위 설치의 경우 자동 업데이트를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-157">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="a4e61-158">즉, 팀 앱을 업데이트 하려면 최신 버전으로 업데이트 하기 위해 현재 버전을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-158">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="a4e61-159">사용자 단위 설치의 경우 자동 업데이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-159">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="a4e61-160">대부분의 VDI 배포의 경우 시스템 단위 설치를 사용 하 여 팀을 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-160">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="a4e61-161">최신 팀 버전으로 업데이트 하려면 제거 절차와 최신 팀 버전 배포를 차례로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-161">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="a4e61-162">VDI 환경에서 팀의 AV 최적화가 올바르게 작동 하려면 씬 클라이언트 끝점이 인터넷에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-162">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="a4e61-163">씬 클라이언트 끝점에서 인터넷 액세스를 사용할 수 없는 경우에는 최적화가 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-163">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="a4e61-164">이는 사용자가 최적화 되지 않은 미디어 상태에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-164">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="a4e61-165">전용 영구적 설정</span><span class="sxs-lookup"><span data-stu-id="a4e61-165">Dedicated persistent setup</span></span>

<span data-ttu-id="a4e61-166">전용 영구적 설정에서는 사용자가 로그 아웃 한 후 사용자의 로컬 운영 체제 변경 내용이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-166">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="a4e61-167">영구 설치의 경우 팀은 사용자 단위 및 컴퓨터 단위 설치를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-167">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="a4e61-168">다음은 권장 되는 최소 VM 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-168">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="a4e61-169">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4e61-169">Parameter</span></span>  |<span data-ttu-id="a4e61-170">Workstation 운영 체제</span><span class="sxs-lookup"><span data-stu-id="a4e61-170">Workstation operating system</span></span>  |<span data-ttu-id="a4e61-171">서버 운영 체제</span><span class="sxs-lookup"><span data-stu-id="a4e61-171">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="a4e61-172">vCPU</span><span class="sxs-lookup"><span data-stu-id="a4e61-172">vCPU</span></span>   |    <span data-ttu-id="a4e61-173">2 코어</span><span class="sxs-lookup"><span data-stu-id="a4e61-173">2 cores</span></span>     |  <span data-ttu-id="a4e61-174">4, 6 또는 8</span><span class="sxs-lookup"><span data-stu-id="a4e61-174">4,6, or 8</span></span><br><span data-ttu-id="a4e61-175">기본 비 유니폼 메모리 액세스 (NUMA) 구성을 이해 하 고 그에 따라 Vm을 구성 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-175">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="a4e61-176">RAM</span><span class="sxs-lookup"><span data-stu-id="a4e61-176">RAM</span></span>     |   <span data-ttu-id="a4e61-177">4GB</span><span class="sxs-lookup"><span data-stu-id="a4e61-177">4 GB</span></span>      | <span data-ttu-id="a4e61-178">사용자 당 512 ~ 1024 MB</span><span class="sxs-lookup"><span data-stu-id="a4e61-178">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="a4e61-179">저장소</span><span class="sxs-lookup"><span data-stu-id="a4e61-179">Storage</span></span>    | <span data-ttu-id="a4e61-180">8GB</span><span class="sxs-lookup"><span data-stu-id="a4e61-180">8 GB</span></span>        | <span data-ttu-id="a4e61-181">40 ~ 60 GB</span><span class="sxs-lookup"><span data-stu-id="a4e61-181">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="a4e61-182">비 영구적인 설정</span><span class="sxs-lookup"><span data-stu-id="a4e61-182">Non-persistent setup</span></span>

<span data-ttu-id="a4e61-183">비 영구적인 설정에서는 사용자가 로그 아웃 한 후 사용자의 로컬 운영 체제 변경 내용이 보존 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-183">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="a4e61-184">이러한 설정은 일반적으로 공유 다중 사용자 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-184">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="a4e61-185">VM 구성은 사용자 수와 사용 가능한 실제 box 리소스에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-185">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="a4e61-186">비 영구적인 설정의 경우 팀 데스크톱 앱은 골든 이미지에 컴퓨터별 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-186">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="a4e61-187">자세히 알아보려면 [VDI에서 팀 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션을 참조 하세요. 이렇게 하면 사용자 세션 중에 팀 앱을 효율적으로 실행할 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-187">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="a4e61-188">비 영구적인 설정으로 팀을 사용 하려면 효율적인 팀 런타임 데이터 동기화를 위한 프로필 캐싱 관리자도 필요 합니다. 이렇게 하면 사용자의 사용자 정보 (예: 사용자 데이터, 프로필 및 설정)가 사용자 세션 중에 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-188">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) is cached during the user session.</span></span> <span data-ttu-id="a4e61-189">이 두 폴더의 데이터가 동기화 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-189">Make sure data in these two folders are synced.</span></span>  

- <span data-ttu-id="a4e61-190">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span><span class="sxs-lookup"><span data-stu-id="a4e61-190">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="a4e61-191">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span><span class="sxs-lookup"><span data-stu-id="a4e61-191">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

<span data-ttu-id="a4e61-192">다양 한 캐싱 관리자 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-192">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="a4e61-193">예를 들어 [Fslogix](https://docs.microsoft.com/fslogix/overview)를 사용할 경우</span><span class="sxs-lookup"><span data-stu-id="a4e61-193">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="a4e61-194">특정 구성 지침은 캐싱 관리자 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-194">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="a4e61-195">비 영구적인 설정에 대 한 팀 캐시 된 콘텐츠 제외 목록</span><span class="sxs-lookup"><span data-stu-id="a4e61-195">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="a4e61-196">팀 캐싱 폴더에서 다음을 제외 합니다 (% appdata%/Microsoft/Teams.).</span><span class="sxs-lookup"><span data-stu-id="a4e61-196">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="a4e61-197">이러한 항목을 제외 하면 사용자 캐싱 크기를 줄여 비영구 설정을 보다 최적화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-197">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="a4e61-198">.txt 파일</span><span class="sxs-lookup"><span data-stu-id="a4e61-198">.txt files</span></span>
- <span data-ttu-id="a4e61-199">미디어 스택 폴더</span><span class="sxs-lookup"><span data-stu-id="a4e61-199">Media-stack folder</span></span>
- <span data-ttu-id="a4e61-200">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span><span class="sxs-lookup"><span data-stu-id="a4e61-200">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="a4e61-201">엔터프라이즈 고려 사항에 대 한 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="a4e61-201">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="a4e61-202">VDI에서 엔터프라이즈 용 Microsoft 365 앱을 배포 하는 경우 다음 사항을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-202">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="a4e61-203">엔터프라이즈 용 Microsoft 365 앱을 통한 팀의 새 배포</span><span class="sxs-lookup"><span data-stu-id="a4e61-203">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="a4e61-204">엔터프라이즈 용 Microsoft 365 앱을 통해 팀을 배포 하기 전에 먼저 컴퓨터별 설치를 사용 하 여 배포 된 기존 팀 앱을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-204">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="a4e61-205">엔터프라이즈 용 Microsoft 365 앱을 통한 팀은 사용자 단위로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-205">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="a4e61-206">자세히 알아보려면 [VDI에서 팀 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-206">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="a4e61-207">엔터프라이즈 업데이트에 대 한 Microsoft 365 앱을 통한 팀 배포</span><span class="sxs-lookup"><span data-stu-id="a4e61-207">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="a4e61-208">또한 enterprise 용 Microsoft 365 앱의 기존 설치에 팀이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-208">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="a4e61-209">Enterprise 용 Microsoft 365 앱은 사용자별로 팀을 설치 하므로 [VDI에서 팀 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-209">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="a4e61-210">시스템 단위 설치 및 엔터프라이즈 용 Microsoft 365 앱을 사용 하는 팀</span><span class="sxs-lookup"><span data-stu-id="a4e61-210">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="a4e61-211">엔터프라이즈 용 Microsoft 365 앱이 팀 컴퓨터별 설치를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-211">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="a4e61-212">컴퓨터 단위 설치를 사용 하려면 enterprise 용 Microsoft 365 앱에서 팀을 제외 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-212">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="a4e61-213">[팀 데스크톱 앱을 VM에 배포](#deploy-the-teams-desktop-app-to-the-vm) 하는 [방법과 엔터프라이즈 섹션에 대 한 Microsoft 365 앱을 통해 팀 배포를 제외 하는 방법을](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-213">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="a4e61-214">엔터프라이즈 용 Microsoft 365 앱을 통해 팀 배포를 제외 하는 방법</span><span class="sxs-lookup"><span data-stu-id="a4e61-214">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="a4e61-215">Enterprise 용 microsoft 365 앱에 대 한 자세한 내용은 [엔터프라이즈의 새 365 설치에서 팀을 제외](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) 하 고 [그룹 정책을 사용 하 여 팀 설치를 제어](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-215">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="a4e61-216">VM에 팀 데스크톱 앱 배포</span><span class="sxs-lookup"><span data-stu-id="a4e61-216">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="a4e61-217">다음 링크 중 하나를 사용 하 여 VDI VM 운영 체제와 일치 하는 팀 MSI 패키지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-217">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="a4e61-218">32 비트 버전</span><span class="sxs-lookup"><span data-stu-id="a4e61-218">32-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows/1.3.00.21759/Teams_windows.msi)
    - [<span data-ttu-id="a4e61-219">64 비트 버전</span><span class="sxs-lookup"><span data-stu-id="a4e61-219">64-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.21759/Teams_windows_x64.msi)

    <span data-ttu-id="a4e61-220">필요한 팀 데스크톱 앱의 최소 버전은 버전 1.3.00.4461입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-220">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="a4e61-221">(PSTN 보류가 이전 버전에서 지원 되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="a4e61-221">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="a4e61-222">다음 명령 중 하나를 실행 하 여이 MSI를 VDI VM에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-222">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="a4e61-223">사용자별 설치 (기본값)</span><span class="sxs-lookup"><span data-stu-id="a4e61-223">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="a4e61-224">이 프로세스는 '% AppData% 사용자 폴더에 팀을 설치 하는 기본 설치입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-224">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="a4e61-225">이 시점에서 골든 이미지 설정이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-225">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="a4e61-226">비 영구적인 설정의 사용자 단위 설치에서는 팀이 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-226">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="a4e61-227">컴퓨터 단위 설치</span><span class="sxs-lookup"><span data-stu-id="a4e61-227">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="a4e61-228">이 프로세스는 팀을 64 비트 운영 체제의 x86 (프로그램 파일) 폴더 및 32 비트 운영 체제의 Program Files 폴더에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-228">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="a4e61-229">이 시점에서 골든 이미지 설정이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-229">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="a4e61-230">비 영구적인 설치에는 컴퓨터별 팀이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-230">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="a4e61-231">다음 대화형 로그온 세션에서 팀을 시작 하 고 자격 증명을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-231">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="a4e61-232">이 예제에서는 또한 **ALLUSERS = 1** 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-232">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="a4e61-233">이 매개 변수를 설정 하면 제어판의 프로그램 및 기능 및 컴퓨터의 모든 사용자에 대 한 Windows 설정의 앱 & 기능에 팀 컴퓨터 전체의 설치 관리자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-233">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="a4e61-234">모든 사용자가 관리자 자격 증명을 사용 하는 경우 팀을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-234">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="a4e61-235">**ALLUSERS = 1** 과 **alluser = 1**간의 차이를 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-235">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="a4e61-236">비 VDI 및 VDI 환경에는 **ALLUSERS = 1** 매개 변수를 사용할 수 있지만 **alluser = 1** 매개 변수는 vdi 환경 에서만 사용 하 여 컴퓨터별 설치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-236">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="a4e61-237">VDI VM에서 MSI를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-237">Uninstall the MSI from the VDI VM.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="a4e61-238">이 프로세스는 운영 체제 환경에 따라 x86 (프로그램 파일) 폴더 또는 프로그램 파일 폴더에서 팀을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-238">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="a4e61-239">VDI 성능 고려 사항에 대 한 팀</span><span class="sxs-lookup"><span data-stu-id="a4e61-239">Teams on VDI performance considerations</span></span>

<span data-ttu-id="a4e61-240">최적화 된 다양 한 설치 구성을 사용할 수 있으며, 여기에는 각각 다른 가상화의 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-240">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="a4e61-241">예를 들어, 구성은 사용자 밀도에 중점을 둘 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-241">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="a4e61-242">계획을 수립할 때 다음 사항을 고려 하 여 조직의 작업량 요구 사항에 따라 설정을 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-242">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="a4e61-243">최소 요구 사항: 일부 작업의 경우 최소 요구 사항을 충족 하는 리소스를 사용 하 여 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-243">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="a4e61-244">예를 들어 추가 컴퓨팅 리소스를 요구 하는 응용 프로그램을 사용 하는 개발자를 위한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-244">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="a4e61-245">종속성: 여기에는 팀 데스크톱 앱 외부의 인프라, 작업 부하 및 기타 환경 고려 사항에 대 한 종속성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-245">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="a4e61-246">VDI에서 사용할 수 없는 기능: 팀에서 VDI에 대 한 GPU 집약적 기능을 사용 하지 않도록 설정 하 여 일시적인 CPU 이용률을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-246">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="a4e61-247">다음 기능은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-247">The following features are disabled:</span></span>
    - <span data-ttu-id="a4e61-248">팀 CSS 애니메이션</span><span class="sxs-lookup"><span data-stu-id="a4e61-248">Teams CSS animation</span></span>
    - <span data-ttu-id="a4e61-249">Giphy 자동 시작</span><span class="sxs-lookup"><span data-stu-id="a4e61-249">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="a4e61-250">통화 및 모임으로 VDI의 팀</span><span class="sxs-lookup"><span data-stu-id="a4e61-250">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="a4e61-251">채팅 및 공동 작업 외에도, 통화와 모임이 포함 된 VDI 팀은 지원 되는 가상화 공급자 플랫폼에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-251">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="a4e61-252">지원 되는 기능은 WebRTC 미디어 스택과 가상화 공급자 구현에 기반을 둔 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-252">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="a4e61-253">다음 다이어그램은 아키텍처에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-253">The following diagram provides an overview of the architecture.</span></span>

![VDI 아키텍처의 팀을 보여 주는 다이어그램](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="a4e61-255">현재 VDI에서 AV 최적화를 사용 하지 않고 팀을 실행 중 이며 최적화를 위해 아직 지원 되지 않는 기능 (예: 앱 공유 시 제어 권한 부여 및 적용)을 사용할 경우에는 팀 리디렉션을 해제 하도록 가상화 공급자 정책을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-255">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="a4e61-256">즉, 팀 미디어 세션이 최적화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-256">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="a4e61-257">팀 리디렉션을 끄려면 정책을 설정 하는 방법에 대 한 단계는 가상화 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-257">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="a4e61-258">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4e61-258">Network requirements</span></span>

<span data-ttu-id="a4e61-259">전체 클라우드 음성 및 비디오 배포에 영향을 줄 수 있는 위험 및 요구 사항을 식별 하는 환경을 평가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-259">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="a4e61-260">[비즈니스용 Skype 네트워크 평가 도구](https://www.microsoft.com/download/details.aspx?id=53885) 를 사용 하 여 네트워크가 팀에 게 준비 되었는지 여부를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-260">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="a4e61-261">팀을 위해 네트워크를 준비 하는 방법에 대 한 자세한 내용은 [팀에 대 한 조직의 네트워크 준비](prepare-network.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-261">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="a4e61-262">VDI의 비즈니스용 Skype에서 vdi의 팀으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="a4e61-262">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="a4e61-263">Vdi의 비즈니스용 Skype에서 vdi의 팀으로 마이그레이션하는 경우, 두 응용 프로그램 간의 차이 외에 VDI도 구현 된 경우 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-263">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="a4e61-264">비즈니스용 Skype VDI에 있는 팀 VDI에서 현재 지원 되지 않는 일부 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-264">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="a4e61-265">미디어 비트 전송률 제한 정책으로 VDI 호출 환경 제어</span><span class="sxs-lookup"><span data-stu-id="a4e61-265">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="a4e61-266">VDI에서 일부 AV 기능을 사용 하지 않도록 설정 하는 플랫폼 단위 정책</span><span class="sxs-lookup"><span data-stu-id="a4e61-266">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="a4e61-267">앱 공유 시기 지정 및 관리</span><span class="sxs-lookup"><span data-stu-id="a4e61-267">Give and take control when app sharing</span></span>
- <span data-ttu-id="a4e61-268">오디오 없이 채팅에서 화면 공유</span><span class="sxs-lookup"><span data-stu-id="a4e61-268">Screen share from chat without audio</span></span>
- <span data-ttu-id="a4e61-269">동시 비디오 및 화면 공유 보내기 및 받기</span><span class="sxs-lookup"><span data-stu-id="a4e61-269">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="a4e61-270">Chrome 브라우저의 팀과 VDI 용 팀 데스크톱 앱 비교</span><span class="sxs-lookup"><span data-stu-id="a4e61-270">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="a4e61-271">Chrome 브라우저의 팀은 AV 최적화를 사용 하는 VDI 용 팀 데스크톱 앱의 대체 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-271">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="a4e61-272">채팅 및 공동 작업 환경은 예상 대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-272">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="a4e61-273">미디어를 사용 해야 하는 경우 Chrome 브라우저에서 사용자 기대치를 충족 하지 못하는 몇 가지 환경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-273">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="a4e61-274">오디오 및 비디오 스트리밍 환경이 최적이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-274">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="a4e61-275">사용자에 게 지연 또는 품질이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-275">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="a4e61-276">브라우저 설정에서는 장치 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-276">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="a4e61-277">장치 관리는 브라우저를 통해 처리 되며 브라우저 사이트 설정에서 여러 설정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-277">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="a4e61-278">Windows 장치 관리에서 장치 설정을 설정 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-278">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="a4e61-279">채팅 및 공동 작업을 통해 VDI의 팀</span><span class="sxs-lookup"><span data-stu-id="a4e61-279">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="a4e61-280">조직에서 팀의 채팅 및 공동 작업 기능만 사용 하려는 경우 팀의 통화 및 모임 기능을 해제 하도록 사용자 수준 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-280">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="a4e61-281">정책을 설정 하 여 통화 및 모임 기능을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-281">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="a4e61-282">Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-282">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="a4e61-283">정책 변경 내용을 전파 하는 데 시간이 걸릴 수 있습니다 (몇 시간).</span><span class="sxs-lookup"><span data-stu-id="a4e61-283">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="a4e61-284">지정 된 계정에 대 한 변경 내용이 즉시 표시 되지 않으면 몇 시간 후에 다시 시도 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-284">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="a4e61-285">[**호출 정책**](teams-calling-policy.md): 팀에는 모든 통화 기능을 사용 하지 않도록 설정 된 기본 제공 DisallowCalling 호출 정책이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-285">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="a4e61-286">DisallowCalling 정책을 가상화 된 환경에서 팀을 사용 하는 조직의 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-286">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="a4e61-287">[**모임 정책**](meeting-policies-in-teams.md): 팀에는 모든 모임 기능이 해제 되어 있는 기본 제공 AllOff 모임 정책이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-287">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="a4e61-288">AllOff 정책을 가상화 된 환경에서 팀을 사용 하는 조직의 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-288">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a4e61-289">Microsoft 팀 관리 센터를 사용 하 여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a4e61-289">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="a4e61-290">DisallowCalling 호출 정책 및 AllOff 모임 정책을 사용자에 게 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-290">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="a4e61-291">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-291">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="a4e61-292">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-292">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="a4e61-293">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-293">Do the following:</span></span>
    1.  <span data-ttu-id="a4e61-294">**호출 정책**에서 **DisallowCalling**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-294">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="a4e61-295">**모임 정책**에서 **AllOff**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-295">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="a4e61-296">**적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-296">Click **Apply**.</span></span>

<span data-ttu-id="a4e61-297">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-297">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="a4e61-298">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-298">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="a4e61-299">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-299">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="a4e61-300">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-300">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="a4e61-301">**설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-301">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="a4e61-302">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-302">Or, you can also do the following:</span></span>

1. <span data-ttu-id="a4e61-303">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 할당 하려는 정책으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-303">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="a4e61-304">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-304">For example:</span></span>
    - <span data-ttu-id="a4e61-305">**음성**  >  **통화 정책**으로 이동한 다음 **DisallowCalling**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-305">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="a4e61-306">**모임**  >  **모임 정책**으로 이동한 다음 **AllOff**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-306">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
2. <span data-ttu-id="a4e61-307">**사용자 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-307">Select **Manage users**.</span></span>
3. <span data-ttu-id="a4e61-308">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-308">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="a4e61-309">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-309">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="a4e61-310">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-310">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="a4e61-311">PowerShell을 사용 하 여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a4e61-311">Assign policies using PowerShell</span></span>

<span data-ttu-id="a4e61-312">다음 예제에서는 [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) 를 사용 하 여 DisallowCalling 호출 정책을 사용자에 게 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-312">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="a4e61-313">PowerShell을 사용 하 여 호출 정책을 관리 하는 방법에 대해 자세히 알아보려면 [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-313">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="a4e61-314">다음 예제에서는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) 를 사용 하 여 AllOff 모임 정책을 사용자에 게 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-314">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="a4e61-315">PowerShell을 사용 하 여 모임 정책을 관리 하는 방법에 대해 자세히 알아보려면 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-315">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="a4e61-316">통화 및 모임으로 팀을 최적화 하기 위해 채팅 및 공동 작업을 통해 VDI에서 팀 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="a4e61-316">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="a4e61-317">사용자 수준 정책을 설정 하 여 통화 및 모임 기능을 해제 하 고 AV 최적화를 사용 하 여 팀으로 마이그레이션하는 경우 VDI에 팀의 기존 구현이 있는 경우 VDI 사용자에 게 해당 팀에 대 한 통화 및 모임 기능을 설정 하도록 정책을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-317">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="a4e61-318">통화 및 모임 기능을 켜려면 정책 설정</span><span class="sxs-lookup"><span data-stu-id="a4e61-318">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="a4e61-319">Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 통화 및 모임 정책을 설정 하 고 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-319">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="a4e61-320">정책 변경 내용을 전파 하는 데 몇 시간 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-320">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="a4e61-321">지정 된 계정에 대 한 변경 내용이 즉시 표시 되지 않으면 몇 시간 후에 다시 시도 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-321">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="a4e61-322">[**호출**](teams-calling-policy.md)정책: 팀에서 정책에 대 한 호출은 사용자가 사용할 수 있는 통화 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-322">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="a4e61-323">팀에는 모든 통화 기능이 설정 되어 있는 기본 제공 AllowCalling 호출 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-323">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="a4e61-324">모든 통화 기능을 설정 하려면 AllowCalling 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-324">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="a4e61-325">또는 사용자 지정 호출 정책을 만들어 원하는 호출 기능을 설정 하 고 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-325">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="a4e61-326">[**모임 정책**](meeting-policies-in-teams.md): 팀의 모임 정책은 사용자가 만들 수 있는 모임 유형과 조직의 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-326">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="a4e61-327">팀에는 모든 모임 기능이 설정 되어 있는 기본 제공 된 AllOn 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-327">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="a4e61-328">모든 모임 기능을 설정 하려면 AllOn를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-328">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="a4e61-329">또는 사용자 지정 모임 정책을 만들어 원하는 모임 기능을 설정 하 고 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-329">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="a4e61-330">Microsoft 팀 관리 센터를 사용 하 여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a4e61-330">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="a4e61-331">AllowCalling 호출 정책 및 AllOn meeting policy를 사용자에 게 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-331">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="a4e61-332">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-332">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="a4e61-333">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-333">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="a4e61-334">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-334">Do the following:</span></span>
    1.  <span data-ttu-id="a4e61-335">**호출 정책**에서 **allowcalling**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-335">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="a4e61-336">**모임 정책**에서 **allon**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-336">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="a4e61-337">**적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-337">Click **Apply**.</span></span>

<span data-ttu-id="a4e61-338">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-338">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="a4e61-339">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자**로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-339">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="a4e61-340">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-340">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="a4e61-341">모든 사용자를 선택 하려면 표 맨 위에 있는 **&#x2713;** (확인 표시)을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-341">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="a4e61-342">**설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-342">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="a4e61-343">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-343">Or, you can also do the following:</span></span>

1. <span data-ttu-id="a4e61-344">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 할당 하려는 정책으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-344">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="a4e61-345">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-345">For example:</span></span>
    - <span data-ttu-id="a4e61-346">**음성**  >  **통화 정책**으로 이동한 다음 **allowcalling**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-346">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="a4e61-347">**모임**  >  **모임 정책**으로 이동한 다음, **allon**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-347">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
2. <span data-ttu-id="a4e61-348">**사용자 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-348">Select **Manage users**.</span></span>
3. <span data-ttu-id="a4e61-349">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-349">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="a4e61-350">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-350">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="a4e61-351">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-351">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="a4e61-352">PowerShell을 사용 하 여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a4e61-352">Assign policies using PowerShell</span></span>

<span data-ttu-id="a4e61-353">다음 예제에서는 [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) 를 사용 하 여 allowcalling 호출 정책을 사용자에 게 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-353">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="a4e61-354">PowerShell을 사용 하 여 호출 정책을 관리 하는 방법에 대해 자세히 알아보려면 [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-354">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="a4e61-355">다음 예제에서는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) 를 사용 하 여 사용자에 게 allon 정책을 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-355">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="a4e61-356">PowerShell을 사용 하 여 모임 정책을 관리 하는 방법에 대해 자세히 알아보려면 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-356">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="a4e61-357">팀의 대체 모드 제어</span><span class="sxs-lookup"><span data-stu-id="a4e61-357">Control fallback mode in Teams</span></span>

<span data-ttu-id="a4e61-358">사용자가 지원 되지 않는 끝점에서 연결 하는 경우 사용자는 AV에 최적화 되지 않은 대체 모드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-358">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="a4e61-359">다음 레지스트리 DWORD 값 중 하나를 설정 하 여 fallback 모드를 사용 하지 않도록 설정 하거나 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-359">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="a4e61-360">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="a4e61-360">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="a4e61-361">HKEY_CURRENT_USER \SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="a4e61-361">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="a4e61-362">Fallback 모드를 사용 하지 않도록 설정 하려면 값을 **1**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-362">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="a4e61-363">오디오만 활성화 하려면 값을 **2**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-363">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="a4e61-364">값이 없거나 **0** (영)으로 설정 되어 있으면 fallback 모드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-364">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="a4e61-365">이 기능은 팀 버전 1.3.00.13565 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-365">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="a4e61-366">알려진 문제점 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="a4e61-366">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="a4e61-367">클라이언트 배포, 설치 및 설정</span><span class="sxs-lookup"><span data-stu-id="a4e61-367">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="a4e61-368">컴퓨터별 설치의 경우 vdi의 팀이 비 VDI 팀 클라이언트의 방식으로 자동으로 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-368">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="a4e61-369">[VDI에서 팀 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션에 설명 된 대로 새 MSI를 설치 하 여 VM 이미지를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-369">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="a4e61-370">최신 버전으로 업데이트 하려면 현재 버전을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-370">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="a4e61-371">팀은 사용자 또는 컴퓨터 별로 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-371">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="a4e61-372">사용자 당 동시 및 컴퓨터 별로 팀을 배포 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-372">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="a4e61-373">컴퓨터 또는 사용자 별로 이러한 모드 중 하나로 마이그레이션하려면 제거 절차에 따라 두 모드에 다시 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-373">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="a4e61-374">Windows 가상 데스크톱 및 VMware는 현재 MacOS 및 Linux 기반 클라이언트를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-374">Windows Virtual Desktop and VMware don't support MacOS and Linux-based clients at this time.</span></span>
- <span data-ttu-id="a4e61-375">지금은 Citrix가 MacOs 클라이언트를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-375">Citrix doesn't support MacOs clients at this time.</span></span>
- <span data-ttu-id="a4e61-376">Citrix는 끝점에 정의 된 명시적 HTTP 프록시 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-376">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="a4e61-377">통화 및 모임</span><span class="sxs-lookup"><span data-stu-id="a4e61-377">Calling and meetings</span></span>

<span data-ttu-id="a4e61-378">다음 통화 및 모임 기능은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-378">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="a4e61-379">향상 된 응급 서비스</span><span class="sxs-lookup"><span data-stu-id="a4e61-379">Enhanced emergency services</span></span>
- <span data-ttu-id="a4e61-380">팀 앱과 장치 간의 HID 단추 및 LED 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a4e61-380">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="a4e61-381">백그라운드 흐림 및 효과</span><span class="sxs-lookup"><span data-stu-id="a4e61-381">Background blur and effects</span></span>
- <span data-ttu-id="a4e61-382">브로드캐스트/라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="a4e61-382">Broadcast/live events</span></span>
- <span data-ttu-id="a4e61-383">LBR (위치 기반 라우팅)</span><span class="sxs-lookup"><span data-stu-id="a4e61-383">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="a4e61-384">통화 공원</span><span class="sxs-lookup"><span data-stu-id="a4e61-384">Call park</span></span>
- <span data-ttu-id="a4e61-385">통화 대기열</span><span class="sxs-lookup"><span data-stu-id="a4e61-385">Call queue</span></span>

> [!NOTE]
> <span data-ttu-id="a4e61-386">현재는 비 VDI 환경 에서만 사용할 수 있는 통화 및 모임 기능을 추가 하는 작업을 진행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-386">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="a4e61-387">여기에는 품질, 추가 화면 공유 시나리오, 최근에 팀에 추가 된 고급 기능에 대 한 더 많은 관리 제어가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-387">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="a4e61-388">예정 된 기능에 대해 자세히 알아보려면 팀 담당자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-388">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="a4e61-389">다음은 통화 및 모임에 대 한 알려진 문제점 및 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-389">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="a4e61-390">비즈니스용 Skype와의 상호 운용성은 음성 통화로 제한 됩니다. 영상 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-390">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="a4e61-391">모임 또는 그룹 통화에서는 하나의 수신 비디오 스트림만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-391">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="a4e61-392">여러 사용자가 비디오를 보내면 주어진 시간에 주요 스피커 비디오만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-392">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>
- <span data-ttu-id="a4e61-393">수신 및 발신 비디오 스트림 해상도는 720p 해상도로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-393">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="a4e61-394">이것은 WebRTC 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-394">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="a4e61-395">들어오는 카메라 또는 화면 공유 스트림의 비디오 스트림은 하나만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-395">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="a4e61-396">들어오는 화면 공유가 있는 경우 기준 스피커의 비디오 대신 해당 화면 공유가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-396">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="a4e61-397">보내는 화면 공유:</span><span class="sxs-lookup"><span data-stu-id="a4e61-397">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="a4e61-398">응용 프로그램 공유가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-398">Application sharing is not supported.</span></span>
- <span data-ttu-id="a4e61-399">제어권을 부여 하 고 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-399">Give control and take control:</span></span>
    - <span data-ttu-id="a4e61-400">화면 공유 또는 응용 프로그램 공유 세션 중에 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-400">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="a4e61-401">PowerPoint 공유 세션 중에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-401">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="a4e61-402">Citrix 전용 제한</span><span class="sxs-lookup"><span data-stu-id="a4e61-402">Citrix-only limitations</span></span>
    - <span data-ttu-id="a4e61-403">이중 톤 다중 주파수 (DTMF) 전화 통신 시스템과의 상호 작용은 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-403">Dual Tone Multi Frequency (DTMF) interaction with telephony systems is currently not supported.</span></span>
    - <span data-ttu-id="a4e61-404">다중 모니터 설정에서 화면 공유 시 메인 모니터만 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-404">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="a4e61-405">CWA에서 높은 DPI 조정이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e61-405">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="a4e61-406">VDI와 관련 되지 않은 팀의 알려진 문제점은 [조직의 지원 팀](Known-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-406">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a4e61-407">문제 해결</span><span class="sxs-lookup"><span data-stu-id="a4e61-407">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="a4e61-408">Citrix 구성 요소 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a4e61-408">Troubleshoot Citrix components</span></span>

<span data-ttu-id="a4e61-409">VDA 및 CWA 문제를 해결 하는 방법에 대 한 자세한 내용은 [이 Citrix 웹 사이트](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4e61-409">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a4e61-410">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a4e61-410">Related topics</span></span>

- [<span data-ttu-id="a4e61-411">MSI를 사용 하 여 Microsoft 팀 설치</span><span class="sxs-lookup"><span data-stu-id="a4e61-411">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="a4e61-412">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="a4e61-412">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="a4e61-413">Windows 가상 데스크톱에서 Microsoft 팀 사용</span><span class="sxs-lookup"><span data-stu-id="a4e61-413">Use Microsoft Teams on Windows Virtual desktop</span></span>](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
