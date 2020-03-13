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
ms.openlocfilehash: 4e009ccfb70e307e4a67f8331deabce51e229c0f
ms.sourcegitcommit: 511238a3550ad0ff8d4bbd4600a252651ab6a654
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42615370"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="8cbbe-103">VDI(Virtualized Desktop Infrastructure)용 Teams</span><span class="sxs-lookup"><span data-stu-id="8cbbe-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="8cbbe-104">이 문서에서는 가상화 된 환경에서 Microsoft 팀을 사용 하는 데 필요한 요구 사항과 제한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="8cbbe-105">VDI 란?</span><span class="sxs-lookup"><span data-stu-id="8cbbe-105">What is VDI?</span></span>

<span data-ttu-id="8cbbe-106">VDI (가상 데스크톱 인프라)는 데스크톱 운영 체제 및 응용 프로그램을 데이터 센터의 중앙 집중식 서버에 호스팅하는 가상화 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="8cbbe-107">이렇게 하면 완전히 안전한 중앙 집중화 된 원본을 사용 하 여 사용자에 게 개인 설정 된 데스크톱 환경이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>
 
<span data-ttu-id="8cbbe-108">가상화 된 환경에서 Microsoft 팀은 채팅 및 공동 작업을 지원 하며 Citrix 플랫폼 에서도 통화와 모임 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-108">Microsoft Teams in a virtualized environment supports chat and collaboration, and with the Citrix platform, calling and meeting functionality are also supported.</span></span>

<span data-ttu-id="8cbbe-109">가상화 된 환경의 팀은 여러 구성을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-109">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="8cbbe-110">여기에는 VDI, 전용, 공유, 영구 및 비영구 모드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-110">These include VDI, dedicated, shared, persistent and non-persistent modes.</span></span> <span data-ttu-id="8cbbe-111">기능은 지속적으로 개발 되 고 있으며 정기적으로 추가 되며, 제공 되는 개월 단위와 몇 년 동안 기능이 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-111">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>
 
<span data-ttu-id="8cbbe-112">가상화 된 환경에서 팀을 사용 하는 것은 가상화 되지 않은 환경에서 팀을 사용 하는 것과 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-112">Using Teams in a virtualized environment may be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="8cbbe-113">예를 들어 가상화 된 환경에서 일부 고급 기능을 사용 하지 못할 수 있으며 비디오 해상도가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-113">For example, some advanced features may not be available in a virtualized environment and video resolution may differ.</span></span> <span data-ttu-id="8cbbe-114">최적의 사용자 환경을 보장 하려면이 문서의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-114">To ensure an optimal user experience, follow the guidance in this article.</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="8cbbe-115">VDI 구성 요소의 팀</span><span class="sxs-lookup"><span data-stu-id="8cbbe-115">Teams on VDI components</span></span>

<span data-ttu-id="8cbbe-116">가상화 된 환경에서 팀을 사용 하려면 다음 구성 요소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-116">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="8cbbe-117">**가상화 브로커**: Azure와 같은 가상화 공급자에 대 한 리소스 및 연결 관리자</span><span class="sxs-lookup"><span data-stu-id="8cbbe-117">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="8cbbe-118">**가상 데스크톱**: Microsoft 팀을 실행 하는 VM (가상 컴퓨터) 스택</span><span class="sxs-lookup"><span data-stu-id="8cbbe-118">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="8cbbe-119">**씬 클라이언트**: 사용자가 실제 인터페이스를 사용 하는 끝점</span><span class="sxs-lookup"><span data-stu-id="8cbbe-119">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="8cbbe-120">**팀 데스크톱 앱**: 팀 데스크톱 클라이언트 앱입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-120">**Teams desktop app**: This is the Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="8cbbe-121">VDI 요구 사항 팀</span><span class="sxs-lookup"><span data-stu-id="8cbbe-121">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="8cbbe-122">가상화 공급자 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8cbbe-122">Virtualization provider requirements</span></span>

<span data-ttu-id="8cbbe-123">팀 데스크톱 앱의 유효성을 주요 가상화 솔루션 공급자로 확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-123">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="8cbbe-124">여러 시장 공급자를 사용 하는 경우 가상화 솔루션 공급자에 게 문의 하 여 최소 요구 사항을 충족 하는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-124">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure minimum requirements are met.</span></span>
  
<span data-ttu-id="8cbbe-125">현재, AV (오디오/비디오) 최적화를 사용 하는 VDI의 팀은 Citrix로 인증 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-125">Currently, Teams on VDI with audio/video (AV) optimization is certified with Citrix.</span></span> <span data-ttu-id="8cbbe-126">이 섹션의 정보를 검토 하 여 적절 한 기능에 대 한 Citrix와 팀 요구 사항이 모두 충족 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-126">Review the information in this section to ensure both Citrix and Teams requirements are met for proper functionality.</span></span>

### <a name="partners-certified-for-teams"></a><span data-ttu-id="8cbbe-127">팀에 대해 인증 된 파트너</span><span class="sxs-lookup"><span data-stu-id="8cbbe-127">Partners certified for Teams</span></span>

<span data-ttu-id="8cbbe-128">다음 파트너는 팀에 대 한 가상 데스크톱 인프라 솔루션을 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-128">The following partners have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="8cbbe-129">Partner</span><span class="sxs-lookup"><span data-stu-id="8cbbe-129">Partner</span></span>|<span data-ttu-id="8cbbe-130">파트너 솔루션</span><span class="sxs-lookup"><span data-stu-id="8cbbe-130">Partner solution</span></span>|
|----|---|
|![Citrix를 나타내는 로고](media/citrix.png)| <span data-ttu-id="8cbbe-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix 가상 앱 및 데스크톱</a></span><span class="sxs-lookup"><span data-stu-id="8cbbe-132"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="8cbbe-133">Citrix 가상 앱 및 데스크톱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8cbbe-133">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="8cbbe-134">Citrix 가상 앱 및 데스크톱 (이전의 XenApp 및 XenDesktop)은 VDI의 팀에 대 한 AV 최적화 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-134">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="8cbbe-135">Citrix 가상 앱 및 데스크톱을 사용 하는 경우 VDI의 팀은 채팅 및 공동 작업 외에도 통화와 모임 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-135">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="8cbbe-136">[여기](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)에서 최신 버전의 Citrix 가상 앱 및 데스크톱을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-136">You can download the latest version of Citrix Virtual Apps and Desktops [here](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="8cbbe-137">(먼저 로그인 해야 합니다.) 필수 구성 요소는 기본적으로 [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) 및 가상 배달 에이전트 (VDA)에 번들 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-137">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="8cbbe-138">CWA 또는 VDA에 추가 구성 요소 또는 플러그인을 설치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-138">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="8cbbe-139">최신 서버 및 클라이언트 요구 사항은 [이 Citrix 웹 사이트](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-139">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="8cbbe-140">VDI에서 팀 데스크톱 앱 설치 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="8cbbe-140">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="8cbbe-141">MSI 패키지를 사용 하 여 컴퓨터별 설치 또는 사용자 단위 설치를 사용 하 여 VDI 용 팀 데스크톱 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-141">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="8cbbe-142">사용할 접근 방식을 결정 하는 것은 영구적이 든 비영구 설정을 사용 하 고 조직의 관련 기능 필요 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-142">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>
<span data-ttu-id="8cbbe-143">전용 영구적 설정의 경우 두 접근 방법이 모두 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-143">For a dedicated persistent setup, either approach would work.</span></span>  <span data-ttu-id="8cbbe-144">그러나 비영구 설치의 경우 팀이 효율적으로 작업 하려면 컴퓨터 단위 설치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-144">However, for a non-persistent setup, per-machine installation is required for Teams to work efficiently.</span></span> <span data-ttu-id="8cbbe-145">[비 영구적인 설정](#non-persistent-setup) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-145">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="8cbbe-146">컴퓨터 단위 설치의 경우 자동 업데이트를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-146">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="8cbbe-147">즉, 팀 앱을 업데이트 하려면 최신 버전으로 업데이트 하기 위해 현재 버전을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-147">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="8cbbe-148">사용자 단위 설치의 경우 자동 업데이트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-148">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="8cbbe-149">대부분의 VDI 배포의 경우 시스템 단위 설치를 사용 하 여 팀을 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-149">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="8cbbe-150">최신 팀 버전으로 업데이트 하려면 제거 절차와 최신 팀 버전 배포를 차례로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-150">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="8cbbe-151">VDI 환경에서 팀의 AV 최적화가 올바르게 작동 하려면 씬 클라이언트 끝점이 인터넷에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-151">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="8cbbe-152">씬 클라이언트 끝점에서 인터넷 액세스를 사용할 수 없는 경우에는 최적화가 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-152">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="8cbbe-153">이는 사용자가 최적화 되지 않은 미디어 상태에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-153">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="8cbbe-154">전용 영구적 설정</span><span class="sxs-lookup"><span data-stu-id="8cbbe-154">Dedicated persistent setup</span></span>

<span data-ttu-id="8cbbe-155">전용 영구적 설정에서는 사용자가 로그 아웃 한 후 사용자의 로컬 운영 체제 변경 내용이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-155">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span>  <span data-ttu-id="8cbbe-156">영구 설치의 경우 팀은 사용자 단위 및 컴퓨터 단위 설치를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-156">For persistent setup, Teams support both per-user and per-machine installation.</span></span>

<span data-ttu-id="8cbbe-157">다음은 권장 되는 최소 VM 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-157">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="8cbbe-158">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8cbbe-158">Parameter</span></span>  |<span data-ttu-id="8cbbe-159">Workstation 운영 체제</span><span class="sxs-lookup"><span data-stu-id="8cbbe-159">Workstation operating system</span></span>  |<span data-ttu-id="8cbbe-160">서버 운영 체제</span><span class="sxs-lookup"><span data-stu-id="8cbbe-160">Server operation system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="8cbbe-161">vCPU</span><span class="sxs-lookup"><span data-stu-id="8cbbe-161">vCPU</span></span>   |    <span data-ttu-id="8cbbe-162">2 코어</span><span class="sxs-lookup"><span data-stu-id="8cbbe-162">2 cores</span></span>     |  <span data-ttu-id="8cbbe-163">4, 6 또는 8</span><span class="sxs-lookup"><span data-stu-id="8cbbe-163">4,6, or 8</span></span><br><span data-ttu-id="8cbbe-164">기본 비 유니폼 메모리 액세스 (NUMA) 구성을 이해 하 고 그에 따라 Vm을 구성 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-164">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="8cbbe-165">할당할</span><span class="sxs-lookup"><span data-stu-id="8cbbe-165">RAM</span></span>     |   <span data-ttu-id="8cbbe-166">4GB</span><span class="sxs-lookup"><span data-stu-id="8cbbe-166">4 GB</span></span>      | <span data-ttu-id="8cbbe-167">사용자 당 512 ~ 1024 MB</span><span class="sxs-lookup"><span data-stu-id="8cbbe-167">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="8cbbe-168">저장소</span><span class="sxs-lookup"><span data-stu-id="8cbbe-168">Storage</span></span>    | <span data-ttu-id="8cbbe-169">8gb</span><span class="sxs-lookup"><span data-stu-id="8cbbe-169">8 GB</span></span>        | <span data-ttu-id="8cbbe-170">40 ~ 60 GB</span><span class="sxs-lookup"><span data-stu-id="8cbbe-170">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="8cbbe-171">비 영구적인 설정</span><span class="sxs-lookup"><span data-stu-id="8cbbe-171">Non-persistent setup</span></span>

<span data-ttu-id="8cbbe-172">비 영구적인 설정에서는 사용자가 로그 아웃 한 후 사용자의 로컬 운영 체제 변경 내용이 보존 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-172">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="8cbbe-173">이러한 설정은 일반적으로 공유 다중 사용자 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-173">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="8cbbe-174">VM 구성은 사용자 수와 사용 가능한 실제 box 리소스에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-174">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="8cbbe-175">비 영구적인 설정의 경우 팀 데스크톱 앱은 골든 이미지에 컴퓨터별 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-175">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="8cbbe-176">자세히 알아보려면 [VDI에서 팀 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션을 참조 하세요. 이렇게 하면 사용자 세션 중에 팀 앱을 효율적으로 실행할 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-176">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span> <span data-ttu-id="8cbbe-177">비 영구적인 설정으로 팀을 사용 하려면 효율적인 팀 런타임 데이터 동기화를 위한 프로필 캐싱 관리자도 필요 합니다. 이렇게 하면 사용자 데이터, 프로필 및 설정 등의 적절 한 사용자 관련 정보를 사용 하는 동안 해당 정보가 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-177">Using Teams with a non-persistent setup also requires a profile caching manager for efficient Teams runtime data sync. This ensures that the appropriate user-specific information (for example, user data, profile, and settings) are cached during the user session.</span></span>  <span data-ttu-id="8cbbe-178">다양 한 캐싱 관리자 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-178">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="8cbbe-179">예를 들어 [Fslogix](https://docs.microsoft.com/fslogix/overview)를 사용할 경우</span><span class="sxs-lookup"><span data-stu-id="8cbbe-179">For example, [FSLogix](https://docs.microsoft.com/fslogix/overview).</span></span> <span data-ttu-id="8cbbe-180">특정 구성 지침은 캐싱 관리자 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-180">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="8cbbe-181">비 영구적인 설정에 대 한 팀 캐시 된 콘텐츠 제외 목록</span><span class="sxs-lookup"><span data-stu-id="8cbbe-181">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="8cbbe-182">팀 캐싱 폴더에서 다음을 제외 합니다 (% appdata%/Microsoft/Teams.).</span><span class="sxs-lookup"><span data-stu-id="8cbbe-182">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span>  <span data-ttu-id="8cbbe-183">이를 제외 하면 사용자 캐싱 크기를 줄여 비영구 설정을 더 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-183">Excluding these help reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="8cbbe-184">.txt 파일</span><span class="sxs-lookup"><span data-stu-id="8cbbe-184">.txt files</span></span>
- <span data-ttu-id="8cbbe-185">미디어 스택 폴더</span><span class="sxs-lookup"><span data-stu-id="8cbbe-185">Media-stack folder</span></span>

### <a name="office-365-proplus-considerations"></a><span data-ttu-id="8cbbe-186">Office 365 ProPlus 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8cbbe-186">Office 365 ProPlus considerations</span></span>

<span data-ttu-id="8cbbe-187">VDI에서 Office 365 ProPlus를 사용 하 여 팀을 배포 하는 경우 다음 사항을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-187">Consider the following when you deploy Teams with Office 365 ProPlus on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-office-365-proplus"></a><span data-ttu-id="8cbbe-188">Office 365 ProPlus를 통한 팀의 새로운 배포</span><span class="sxs-lookup"><span data-stu-id="8cbbe-188">New deployments of Teams through Office 365 ProPlus</span></span>

<span data-ttu-id="8cbbe-189">Office 365 ProPlus를 통해 팀을 배포 하기 전에 먼저 컴퓨터별 설치를 사용 하 여 배포 된 기존 팀 앱을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-189">Before you deploy Teams through Office 365 ProPlus, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="8cbbe-190">Office 365 ProPlus 팀은 사용자 단위로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-190">Teams through Office 365 ProPlus is installed per-user.</span></span> <span data-ttu-id="8cbbe-191">자세히 알아보려면 [VDI에서 팀 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-191">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-office-365-proplus-updates"></a><span data-ttu-id="8cbbe-192">Office 365 ProPlus 업데이트를 통한 팀 배포</span><span class="sxs-lookup"><span data-stu-id="8cbbe-192">Teams deployments through Office 365 ProPlus updates</span></span>

<span data-ttu-id="8cbbe-193">또한 팀은 Office 365 ProPlus의 기존 설치에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-193">Teams is also being added to existing installations of Office 365 ProPlus.</span></span> <span data-ttu-id="8cbbe-194">Office 365 ProPlus는 팀을 사용자별로 설치 하므로 [VDI에서 팀 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-194">Since Office 365 ProPlus installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-office-365-proplus"></a><span data-ttu-id="8cbbe-195">시스템 단위 설치 및 Office 365 ProPlus와 함께 팀 사용</span><span class="sxs-lookup"><span data-stu-id="8cbbe-195">Using Teams with per-machine installation and Office 365 ProPlus</span></span>

<span data-ttu-id="8cbbe-196">Office 365 ProPlus는 팀의 컴퓨터 단위 설치를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-196">Office 365 ProPlus doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="8cbbe-197">컴퓨터 단위 설치를 사용 하려면 Office 365 ProPlus에서 팀을 제외 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-197">To use per-machine installation, you must exclude Teams from Office 365 ProPlus.</span></span> <span data-ttu-id="8cbbe-198">[VM에 팀 데스크톱 앱 배포](#deploy-the-teams-desktop-app-to-the-vm) 를 참조 하 고 [Office 365 ProPlus 섹션을 통해 팀 배포를 제외 하는 방법에 대해](#how-to-exclude-teams-deployment-through-office-365-proplus) 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-198">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Office 365 ProPlus](#how-to-exclude-teams-deployment-through-office-365-proplus) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-office-365-proplus"></a><span data-ttu-id="8cbbe-199">Office 365 ProPlus를 통해 팀 배포를 제외 하는 방법</span><span class="sxs-lookup"><span data-stu-id="8cbbe-199">How to exclude Teams deployment through Office 365 ProPlus</span></span>

<span data-ttu-id="8cbbe-200">팀 및 Office 365 ProPlus에 대 한 자세한 내용은 [Office 365 ProPlus의 새 설치에서 팀을 제외](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) 하 고 [그룹 정책을 사용 하 여 팀 설치를 제어](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-200">To learn more about Teams and Office 365 ProPlus, see [How to exclude Teams from new installations of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="8cbbe-201">VM에 팀 데스크톱 앱 배포</span><span class="sxs-lookup"><span data-stu-id="8cbbe-201">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="8cbbe-202">다음 링크 중 하나를 사용 하 여 VDI VM 운영 체제와 일치 하는 팀 MSI 패키지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-202">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="8cbbe-203">32 비트 버전</span><span class="sxs-lookup"><span data-stu-id="8cbbe-203">32-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows/1.3.00.4461/Teams_windows.msi)
    - [<span data-ttu-id="8cbbe-204">64 비트 버전</span><span class="sxs-lookup"><span data-stu-id="8cbbe-204">64-bit version</span></span>](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.4461/Teams_windows_x64.msi)

    <span data-ttu-id="8cbbe-205">필요한 팀 데스크톱 앱의 최소 버전은 버전 1.2.00.31357입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-205">The minimum version of the Teams desktop app that's required is version 1.2.00.31357.</span></span> <span data-ttu-id="8cbbe-206">(PSTN 보류가 이전 버전에서 지원 되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="8cbbe-206">(PSTN hold is not supported in earlier versions.)</span></span>

2. <span data-ttu-id="8cbbe-207">다음 명령 중 하나를 실행 하 여이 MSI를 VDI VM에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-207">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="8cbbe-208">사용자별 설치 (기본값)</span><span class="sxs-lookup"><span data-stu-id="8cbbe-208">Per-user installation  (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name>
        ```
    
        <span data-ttu-id="8cbbe-209">% AppData% user 폴더에 팀을 설치 하는 기본 설치입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-209">This is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="8cbbe-210">이 시점에서 골든 이미지 설정이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-210">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="8cbbe-211">비 영구적인 설정에서 사용자 단위 설치와 함께 팀이 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-211">Teams will not work properly with per-user installation on a non-persistent setup.</span></span>
    
    - <span data-ttu-id="8cbbe-212">컴퓨터 단위 설치</span><span class="sxs-lookup"><span data-stu-id="8cbbe-212">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
        ```

        <span data-ttu-id="8cbbe-213">이렇게 하면 팀이 64 비트 운영 체제의 x86 (프로그램 파일) 폴더와 32 비트 운영 체제의 Program Files 폴더에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-213">This installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="8cbbe-214">이 시점에서 골든 이미지 설정이 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-214">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="8cbbe-215">비 영구적인 설치에는 컴퓨터별 팀이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-215">Installing Teams per-machine is required for non-persistent setups.</span></span>
 
        <span data-ttu-id="8cbbe-216">다음 대화형 로그온 세션에서 팀을 시작 하 고 자격 증명을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-216">The next interactive logon session starts Teams and asks for credentials.</span></span>

3. <span data-ttu-id="8cbbe-217">VDI VM에서 MSI를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-217">Uninstall the MSI from the VDI VM.</span></span> 

    <span data-ttu-id="8cbbe-218">팀을 제거 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-218">There are two ways to uninstall Teams:</span></span>  
  
    - <span data-ttu-id="8cbbe-219">PowerShell 스크립트 (권장)</span><span class="sxs-lookup"><span data-stu-id="8cbbe-219">PowerShell script (recommended)</span></span>
    
    - <span data-ttu-id="8cbbe-220">명령줄:이 방법은 팀을 제거 하지만 팀을 다시 설치 하는 것을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-220">Command line: This approach removes Teams, yet prevents re-installation of Teams.</span></span> <span data-ttu-id="8cbbe-221">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-221">Run the following command:</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      <span data-ttu-id="8cbbe-222">이렇게 하면 운영 체제 환경에 따라 x86 (프로그램 파일) 폴더 또는 프로그램 파일 폴더에서 팀이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-222">This uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="8cbbe-223">VDI 성능 고려 사항에 대 한 팀</span><span class="sxs-lookup"><span data-stu-id="8cbbe-223">Teams on VDI performance considerations</span></span>

<span data-ttu-id="8cbbe-224">가상화 된 설치 구성에는 각각 최적화를 위해 서로 다른 포커스를 갖는 여러 가지 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-224">There are variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="8cbbe-225">예를 들어 사용자 밀도를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-225">For example, user density.</span></span> <span data-ttu-id="8cbbe-226">계획을 수립할 때 조직의 작업 부하 요구 사항에 따라 설정을 최적화 하는 데 도움이 되는 다음 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-226">When planning, consider the following to help optimize your setup based on the workload needs of your organization:</span></span>

- <span data-ttu-id="8cbbe-227">최소 요구 사항: 일부 작업의 경우 최소 요구 사항을 충족 하는 리소스를 사용 하 여 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-227">Minimum requirement: Some workloads may require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="8cbbe-228">예를 들어 추가 컴퓨팅 리소스를 요구 하는 응용 프로그램을 사용 하는 개발자를 위한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-228">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="8cbbe-229">종속성: 여기에는 팀 데스크톱 앱 외부의 인프라, 작업 부하 및 기타 환경 고려 사항에 대 한 종속성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-229">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="8cbbe-230">VDI에서 사용할 수 없는 기능: 팀에서 VDI에 대 한 GPU 집약적 기능을 사용 하지 않도록 설정 하 여 일시적인 CPU 이용률을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-230">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="8cbbe-231">다음 기능은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-231">The following features are disabled:</span></span>
    - <span data-ttu-id="8cbbe-232">팀 CSS 애니메이션</span><span class="sxs-lookup"><span data-stu-id="8cbbe-232">Teams CSS animation</span></span>
    - <span data-ttu-id="8cbbe-233">Giphy 자동 시작</span><span class="sxs-lookup"><span data-stu-id="8cbbe-233">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="8cbbe-234">통화 및 모임으로 VDI의 팀</span><span class="sxs-lookup"><span data-stu-id="8cbbe-234">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="8cbbe-235">채팅 및 공동 작업 외에도, 통화 및 모임 지원이 포함 된 VDI 팀은 Citrix 기반 플랫폼에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-235">In addition to chat and collaboration, Teams on VDI with calling and meeting support is available with Citrix-based platforms.</span></span> <span data-ttu-id="8cbbe-236">지원 되는 기능은 WebRTC 미디어 스택과 Citrix 관련 구현을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-236">Supported features are based on the WebRTC media stack and Citrix-specific implementation.</span></span> <span data-ttu-id="8cbbe-237">다음 다이어그램은 아키텍처에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-237">The following diagram provides an overview of the architecture.</span></span>

![VDI 아키텍처의 팀을 보여 주는 다이어그램](media/teams-on-vdi-architecture.png)

<span data-ttu-id="8cbbe-239">이러한 통화 및 모임 기능은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-239">These calling and meeting features are not supported:</span></span>

- <span data-ttu-id="8cbbe-240">향상 된 응급 서비스</span><span class="sxs-lookup"><span data-stu-id="8cbbe-240">Enhanced emergency services</span></span>
- <span data-ttu-id="8cbbe-241">팀 앱과 장치 간의 HID 단추 및 LED 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8cbbe-241">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="8cbbe-242">백그라운드 흐림 및 효과</span><span class="sxs-lookup"><span data-stu-id="8cbbe-242">Background blur and effects</span></span>
- <span data-ttu-id="8cbbe-243">브로드캐스트/라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="8cbbe-243">Broadcast/live events</span></span>
- <span data-ttu-id="8cbbe-244">LBR (위치 기반 라우팅)</span><span class="sxs-lookup"><span data-stu-id="8cbbe-244">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="8cbbe-245">통화 공원</span><span class="sxs-lookup"><span data-stu-id="8cbbe-245">Call park</span></span>
- <span data-ttu-id="8cbbe-246">통화 대기열</span><span class="sxs-lookup"><span data-stu-id="8cbbe-246">Call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8cbbe-247">현재 VDI에서 AV 최적화를 사용 하지 않고 팀을 실행 중 이며 최적화를 위해 아직 지원 되지 않는 기능 (예: 앱 공유 시 제어 권한 부여 및 적용)을 사용할 경우, 팀 리디렉션을 끄려면 Citrix 정책을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-247">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set Citrix policies to turn off Teams redirection.</span></span> <span data-ttu-id="8cbbe-248">즉, 팀 미디어 세션이 최적화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-248">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="8cbbe-249">팀 리디렉션을 해제 하도록 정책을 설정 하는 방법에 대 한 단계는이 [Citrix 웹 사이트](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-249">For steps on how to set policies to turn off Teams redirection, see this [Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).</span></span>

<span data-ttu-id="8cbbe-250">현재는 비 VDI 환경 에서만 사용할 수 있는 통화 및 모임 기능을 추가 하는 작업을 진행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-250">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="8cbbe-251">여기에는 품질, 추가 화면 공유 시나리오, 최근에 팀에 추가 된 고급 기능에 대 한 더 많은 관리 제어가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-251">These may include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="8cbbe-252">예정 된 기능에 대해 자세히 알아보려면 팀 담당자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-252">Contact your Teams representative to learn more about upcoming features.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="8cbbe-253">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8cbbe-253">Network requirements</span></span>

<span data-ttu-id="8cbbe-254">전체 클라우드 음성 및 비디오 배포에 영향을 줄 수 있는 위험 및 요구 사항을 식별 하는 환경을 평가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-254">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="8cbbe-255">[비즈니스용 Skype 네트워크 평가 도구](https://www.microsoft.com/download/details.aspx?id=53885) 를 사용 하 여 네트워크가 팀에 게 준비 되었는지 여부를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-255">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="8cbbe-256">팀을 위해 네트워크를 준비 하는 방법에 대 한 자세한 내용은 [팀에 대 한 조직의 네트워크 준비](prepare-network.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-256">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for  Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="8cbbe-257">VDI의 비즈니스용 Skype에서 vdi의 팀으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8cbbe-257">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="8cbbe-258">Vdi의 비즈니스용 Skype에서 vdi의 팀으로 마이그레이션하는 경우, 두 응용 프로그램 간의 차이 외에 VDI도 구현 된 경우 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-258">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="8cbbe-259">비즈니스용 Skype VDI에 있는 팀 VDI에서 현재 지원 되지 않는 일부 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-259">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="8cbbe-260">미디어 비트 전송률 제한 정책으로 VDI 호출 환경 제어</span><span class="sxs-lookup"><span data-stu-id="8cbbe-260">Control of VDI calling experiences with policies for limiting media bitrate</span></span>
- <span data-ttu-id="8cbbe-261">VDI에서 일부 AV 기능을 사용 하지 않도록 설정 하는 플랫폼 단위 정책</span><span class="sxs-lookup"><span data-stu-id="8cbbe-261">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="8cbbe-262">앱 공유 시기 지정 및 관리</span><span class="sxs-lookup"><span data-stu-id="8cbbe-262">Give and take control when app sharing</span></span>
- <span data-ttu-id="8cbbe-263">오디오 없이 채팅에서 화면 공유</span><span class="sxs-lookup"><span data-stu-id="8cbbe-263">Screen share from chat without audio</span></span>
- <span data-ttu-id="8cbbe-264">동시 비디오 및 화면 공유 보내기 및 받기</span><span class="sxs-lookup"><span data-stu-id="8cbbe-264">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="8cbbe-265">Chrome 브라우저의 팀과 VDI 용 팀 데스크톱 앱 비교</span><span class="sxs-lookup"><span data-stu-id="8cbbe-265">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="8cbbe-266">Chrome 브라우저의 팀은 AV 최적화를 사용 하는 VDI 용 팀 데스크톱 앱의 대체 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-266">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="8cbbe-267">채팅 및 공동 작업 환경은 예상 대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-267">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="8cbbe-268">미디어를 사용 해야 하는 경우 Chrome 브라우저에서 사용자 기대치를 충족 하지 못하는 몇 가지 환경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-268">When media is needed, there are some experiences that may not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="8cbbe-269">오디오 및 비디오 스트리밍 환경이 최적이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-269">The audio and video streaming experience may not be optimal.</span></span> <span data-ttu-id="8cbbe-270">사용자에 게 지연 또는 품질이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-270">Users may experiences delays or reduced quality.</span></span>
- <span data-ttu-id="8cbbe-271">브라우저 설정에서는 장치 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-271">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="8cbbe-272">장치 관리는 브라우저를 통해 처리 되며 브라우저 사이트 설정에서 여러 설정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-272">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="8cbbe-273">Windows 장치 관리에서 장치 설정을 설정 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-273">Device settings may also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="8cbbe-274">채팅 및 공동 작업을 통해 VDI의 팀</span><span class="sxs-lookup"><span data-stu-id="8cbbe-274">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="8cbbe-275">조직에서 팀의 채팅 및 공동 작업 기능만 사용 하려는 경우 팀의 통화 및 모임 기능을 해제 하도록 사용자 수준 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-275">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> <span data-ttu-id="8cbbe-276">이 기능 수준에는 Citrix 가상 앱 및 데스크톱이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-276">This feature level doesn't require Citrix Virtual Apps and Desktops.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="8cbbe-277">정책을 설정 하 여 통화 및 모임 기능을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-277">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="8cbbe-278">Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-278">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="8cbbe-279">정책 변경 내용을 전파 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-279">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="8cbbe-280">지정 된 계정에 대 한 변경 내용이 즉시 표시 되지 않으면 몇 시간 후에 다시 시도 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-280">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="8cbbe-281">[**호출 정책**](teams-calling-policy.md): 팀에는 모든 통화 기능을 사용 하지 않도록 설정 된 기본 제공 DisallowCalling 호출 정책이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-281">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="8cbbe-282">DisallowCalling 정책을 가상화 된 환경에서 팀을 사용 하는 조직의 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-282">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="8cbbe-283">[**모임 정책**](meeting-policies-in-teams.md): 팀에는 모든 모임 기능이 해제 되어 있는 기본 제공 AllOff 모임 정책이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-283">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="8cbbe-284">AllOff 정책을 가상화 된 환경에서 팀을 사용 하는 조직의 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-284">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8cbbe-285">Microsoft 팀 관리 센터를 사용 하 여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="8cbbe-285">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="8cbbe-286">DisallowCalling 호출 정책 및 AllOff 모임 정책을 사용자에 게 할당 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-286">To assign the DisallowCalling calling policy and the AllOff meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="8cbbe-287">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-287">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="8cbbe-288">사용자 이름 왼쪽의을 클릭 하 여 사용자를 선택 하 고 **설정 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-288">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="8cbbe-289">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-289">Do the following:</span></span>
    1.  <span data-ttu-id="8cbbe-290">**호출 정책**에서 **DisallowCalling**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-290">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="8cbbe-291">**모임 정책**에서 **AllOff**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-291">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="8cbbe-292">**적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-292">Click **Apply**.</span></span>

<span data-ttu-id="8cbbe-293">한 번에 여러 사용자에 게 정책을 할당 하려면 [팀 사용자 설정을 일괄적으로 편집](edit-user-settings-in-bulk.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-293">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="8cbbe-294">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-294">Or, you can also do the following:</span></span>

1. <span data-ttu-id="8cbbe-295">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 할당 하려는 정책으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-295">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="8cbbe-296">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-296">For example:</span></span>
    - <span data-ttu-id="8cbbe-297">**음성** > **통화 정책**으로 이동한 다음 **DisallowCalling**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-297">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="8cbbe-298">**모임** > **모임 정책**으로 이동한 다음 **AllOff**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-298">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
3. <span data-ttu-id="8cbbe-299">**사용자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-299">Select **Manage users**.</span></span>
4. <span data-ttu-id="8cbbe-300">**사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-300">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="8cbbe-301">추가 하려는 각 사용자에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-301">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="8cbbe-302">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-302">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="8cbbe-303">PowerShell을 사용 하 여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="8cbbe-303">Assign policies using PowerShell</span></span>

<span data-ttu-id="8cbbe-304">다음 예제에서는 [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) 를 사용 하 여 DisallowCalling 호출 정책을 사용자에 게 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-304">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="8cbbe-305">PowerShell을 사용 하 여 호출 정책을 관리 하는 방법에 대해 자세히 알아보려면 [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-305">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="8cbbe-306">다음 예제에서는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) 를 사용 하 여 AllOff 모임 정책을 사용자에 게 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-306">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="8cbbe-307">PowerShell을 사용 하 여 모임 정책을 관리 하는 방법에 대해 자세히 알아보려면 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-307">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a><span data-ttu-id="8cbbe-308">통화 및 모임으로 채팅 및 공동 작업을 사용 하 여 VDI에서 팀 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8cbbe-308">Migrate Teams on VDI with chat and collaboration to Citrix with calling and meetings</span></span>

<span data-ttu-id="8cbbe-309">사용자 수준 정책을 설정 하 여 통화 및 모임 기능을 해제 하 고 AV 최적화를 사용 하 여 Citrix로 마이그레이션하는 경우 VDI에 팀의 기존 구현이 있는 경우 정책을 설정 하 여 전화를 켜고 VDI 사용자의 해당 팀에 대 한 모임 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-309">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Citrix with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="8cbbe-310">통화 및 모임 기능을 켜려면 정책 설정</span><span class="sxs-lookup"><span data-stu-id="8cbbe-310">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="8cbbe-311">Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 통화 및 모임 정책을 설정 하 고 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-311">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="8cbbe-312">정책 변경 내용을 전파 하는 데 몇 시간 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-312">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="8cbbe-313">지정 된 계정에 대 한 변경 내용이 즉시 표시 되지 않으면 몇 시간 후에 다시 시도 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-313">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="8cbbe-314">[**호출**](teams-calling-policy.md)정책: 팀에서 정책에 대 한 호출은 사용자가 사용할 수 있는 통화 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-314">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="8cbbe-315">팀에는 모든 통화 기능이 설정 되어 있는 기본 제공 AllowCalling 호출 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-315">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="8cbbe-316">모든 통화 기능을 설정 하려면 AllowCalling 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-316">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="8cbbe-317">또는 사용자 지정 호출 정책을 만들어 원하는 호출 기능을 설정 하 고 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-317">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="8cbbe-318">[**모임 정책**](meeting-policies-in-teams.md): 팀의 모임 정책은 사용자가 만들 수 있는 모임 유형과 조직의 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-318">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="8cbbe-319">팀에는 모든 모임 기능이 설정 되어 있는 기본 제공 된 AllOn 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-319">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="8cbbe-320">모든 모임 기능을 설정 하려면 AllOn를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-320">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="8cbbe-321">또는 사용자 지정 모임 정책을 만들어 원하는 모임 기능을 설정 하 고 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-321">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8cbbe-322">Microsoft 팀 관리 센터를 사용 하 여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="8cbbe-322">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="8cbbe-323">AllowCalling 호출 정책 및 AllOn meeting policy를 사용자에 게 할당 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-323">To assign the AllowCalling calling policy and the AllOn meeting policy to users, follow these steps:</span></span>

1. <span data-ttu-id="8cbbe-324">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-324">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="8cbbe-325">사용자 이름 왼쪽의을 클릭 하 여 사용자를 선택 하 고 **설정 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-325">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="8cbbe-326">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-326">Do the following:</span></span>
    1.  <span data-ttu-id="8cbbe-327">**호출 정책**에서 **allowcalling**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-327">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="8cbbe-328">**모임 정책**에서 **allon**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-328">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="8cbbe-329">**적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-329">Click **Apply**.</span></span>

<span data-ttu-id="8cbbe-330">한 번에 여러 사용자에 게 정책을 할당 하려면 [팀 사용자 설정을 일괄적으로 편집](edit-user-settings-in-bulk.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-330">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="8cbbe-331">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-331">Or, you can also do the following:</span></span>

1. <span data-ttu-id="8cbbe-332">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 할당 하려는 정책으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-332">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="8cbbe-333">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-333">For example:</span></span>
    - <span data-ttu-id="8cbbe-334">**음성** > **통화 정책**으로 이동한 다음 **allowcalling**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-334">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="8cbbe-335">**모임** > **모임 정책**으로 이동한 다음, **allon**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-335">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
3. <span data-ttu-id="8cbbe-336">**사용자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-336">Select **Manage users**.</span></span>
4. <span data-ttu-id="8cbbe-337">**사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-337">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="8cbbe-338">추가 하려는 각 사용자에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-338">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="8cbbe-339">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-339">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="8cbbe-340">PowerShell을 사용 하 여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="8cbbe-340">Assign policies using PowerShell</span></span>

<span data-ttu-id="8cbbe-341">다음 예제에서는 [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) 를 사용 하 여 allowcalling 호출 정책을 사용자에 게 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-341">The following example shows how to use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="8cbbe-342">PowerShell을 사용 하 여 호출 정책을 관리 하는 방법에 대해 자세히 알아보려면 [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-342">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="8cbbe-343">다음 예제에서는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) 를 사용 하 여 사용자에 게 allon 정책을 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-343">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="8cbbe-344">PowerShell을 사용 하 여 모임 정책을 관리 하는 방법에 대해 자세히 알아보려면 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-344">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="8cbbe-345">알려진 문제점 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="8cbbe-345">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="8cbbe-346">클라이언트 배포, 설치 및 설정</span><span class="sxs-lookup"><span data-stu-id="8cbbe-346">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="8cbbe-347">컴퓨터별 설치의 경우 vdi의 팀이 비 VDI 팀 클라이언트의 방식으로 자동으로 업데이트 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-347">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="8cbbe-348">[VDI에서 팀 데스크톱 앱 설치 또는 업데이트](#install-or-update-the-teams-desktop-app-on-vdi) 섹션에 설명 된 대로 새 MSI를 설치 하 여 VM 이미지를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-348">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="8cbbe-349">최신 버전으로 업데이트 하려면 현재 버전을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-349">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="8cbbe-350">팀은 사용자 또는 컴퓨터 별로 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-350">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="8cbbe-351">사용자 당 동시 및 컴퓨터 별로 팀을 배포 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-351">Deployment of Teams for concurrent per user and per machine is not supported.</span></span>  <span data-ttu-id="8cbbe-352">컴퓨터 또는 사용자 별로 이러한 모드 중 하나로 마이그레이션하려면 제거 절차에 따라 두 모드에 다시 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-352">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="8cbbe-353">MacOs 및 Linux 기반 클라이언트는 현재 Citrix에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-353">MacOs and Linux-based clients are not supported by Citrix at this time.</span></span>
- <span data-ttu-id="8cbbe-354">Citrix는 끝점에 정의 된 명시적 HTTP 프록시 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-354">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span> 

### <a name="calling-and-meetings"></a><span data-ttu-id="8cbbe-355">통화 및 모임</span><span class="sxs-lookup"><span data-stu-id="8cbbe-355">Calling and meetings</span></span>

- <span data-ttu-id="8cbbe-356">비즈니스용 Skype와의 상호 운용성은 오디오 통화로 제한 되며 영상 형식이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-356">Interoperability with Skype for Business is limited to audio calls, no video modality.</span></span>
- <span data-ttu-id="8cbbe-357">이중 톤 다중 주파수 (DTMF) 전화 통신 시스템과의 상호 작용은 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-357">Dual Tone Multi Frequency (DTMF) interaction with telephony systems  is currently not supported.</span></span>
- <span data-ttu-id="8cbbe-358">익명 사용자로 팀 회의에 참가 하면 AV는 최적화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-358">Joining Teams meetings as an anonymous user isn't AV-optimized.</span></span> <span data-ttu-id="8cbbe-359">사용자가 모임에 참가할 수 있으며 최적화 되지 않은 환경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-359">The user can join the meeting and have a non-optimized experience.</span></span>
- <span data-ttu-id="8cbbe-360">모임 또는 그룹 통화에서는 하나의 수신 비디오 스트림만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-360">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="8cbbe-361">여러 사용자가 비디오를 보내면 주어진 시간에 주요 스피커 비디오만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-361">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>  
- <span data-ttu-id="8cbbe-362">수신 및 발신 비디오 스트림 해상도는 720p 해상도로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-362">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="8cbbe-363">이것은 WebRTC 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-363">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="8cbbe-364">들어오는 카메라 또는 화면 공유 스트림의 비디오 스트림은 하나만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-364">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="8cbbe-365">들어오는 화면 공유가 있는 경우 해당 화면 공유는 주요 스피커의 비디오 대신 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-365">When there's an incoming screen share, that screen share is shown it instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="8cbbe-366">보내는 화면 공유:</span><span class="sxs-lookup"><span data-stu-id="8cbbe-366">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="8cbbe-367">응용 프로그램 공유가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-367">Application sharing is not supported.</span></span>
- <span data-ttu-id="8cbbe-368">제어권을 부여 하 고 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-368">Give control and take control:</span></span>  
    - <span data-ttu-id="8cbbe-369">화면 공유 또는 응용 프로그램 공유 세션 중에 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-369">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="8cbbe-370">PowerPoint 공유 세션 중에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-370">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="8cbbe-371">다중 모니터 설정에서 화면 공유 시 메인 모니터만 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-371">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
- <span data-ttu-id="8cbbe-372">CWA에서 높은 DPI 조정이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-372">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="8cbbe-373">VDI와 관련 되지 않은 팀의 알려진 문제점은 [팀에 대해 알려진 문제점](Known-issues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-373">For Teams known issues that aren't related to VDI, see [Known issues for Teams](Known-issues.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8cbbe-374">해결사</span><span class="sxs-lookup"><span data-stu-id="8cbbe-374">Troubleshooting</span></span>

#### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="8cbbe-375">Citrix 구성 요소 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8cbbe-375">Troubleshoot Citrix components</span></span>

<span data-ttu-id="8cbbe-376">VDA 및 CWA 문제를 해결 하는 방법에 대 한 자세한 내용은 [이 Citrix 웹 사이트](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8cbbe-376">For information on how to troubleshoot VDA and CWA issues, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8cbbe-377">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8cbbe-377">Related topics</span></span>

- [<span data-ttu-id="8cbbe-378">MSI를 사용 하 여 Microsoft 팀 설치</span><span class="sxs-lookup"><span data-stu-id="8cbbe-378">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="8cbbe-379">팀 PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="8cbbe-379">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
