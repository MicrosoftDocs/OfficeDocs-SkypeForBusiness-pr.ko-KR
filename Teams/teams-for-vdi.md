---
title: VDI(Virtualized Desktop Infrastructure)용 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: VDI(Virtualized Desktop Infrastructure) Microsoft Teams 환경에서 실행되는 방법에 대해 자세히 알아보고
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d498f66241de3edc46a86ae884b615384508b84
ms.sourcegitcommit: 4d2e1328dee2b6c60ba0022976da8dfe5efba2ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53203627"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="75d2e-103">VDI(Virtualized Desktop Infrastructure)용 Teams</span><span class="sxs-lookup"><span data-stu-id="75d2e-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="75d2e-104">이 문서에서는 가상화된 환경에서 Microsoft Teams 요구 사항 및 제한 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="75d2e-105">VDI란?</span><span class="sxs-lookup"><span data-stu-id="75d2e-105">What is VDI?</span></span>

<span data-ttu-id="75d2e-106">VDI(Virtual Desktop Infrastructure)는 데이터 센터의 중앙 집중식 서버에 데스크톱 운영 체제 및 애플리케이션을 호스트하는 가상화 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="75d2e-107">이렇게 하면 완전히 보호된 규정을 준수하는 중앙 집중식 원본을 사용하여 사용자에게 완전히 개인 설정된 데스크톱 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="75d2e-108">Microsoft Teams 환경에서는 채팅 및 공동 작업을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="75d2e-109">또한 가상 데스크톱Windows Citrix 및 VMware 플랫폼을 사용하여 호출 및 모임 기능도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="75d2e-110">Teams 환경에서는 여러 구성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="75d2e-111">여기에는 VDI, 전용, 공유, 영구 및 비 영구 모드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="75d2e-112">기능은 지속적인 개발에 있으며 정기적으로 추가되고, 기능은 다음 달과 몇 년 동안 확장될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="75d2e-113">가상 Teams 환경에서 사용은 가상화되지 않은 환경에서 Teams 다소 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="75d2e-114">예를 들어 가상화된 환경에서 일부 고급 기능을 사용할 수 없는 경우 비디오 해상도가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="75d2e-115">최적의 사용자 환경을 보장하기 위해 이 문서의 지침을 따르하세요.</span><span class="sxs-lookup"><span data-stu-id="75d2e-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

> [!Note]
> <span data-ttu-id="75d2e-116">다양한 플랫폼에서 VDI Teams 대한 자세한 내용은 플랫폼 [Teams 기능을 참조하세요.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="75d2e-116">For details about Teams VDI on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="75d2e-117">Teams 구성 요소에 대한 구성 요소</span><span class="sxs-lookup"><span data-stu-id="75d2e-117">Teams on VDI components</span></span>

<span data-ttu-id="75d2e-118">가상 Teams 환경에서는 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-118">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="75d2e-119">**가상화 브로커**: Azure와 같은 가상화 공급자에 대한 리소스 및 연결 관리자</span><span class="sxs-lookup"><span data-stu-id="75d2e-119">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="75d2e-120">**가상 데스크톱:** VM(Virtual Machine) 스택에서 실행되는 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="75d2e-120">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="75d2e-121">**씬 클라이언트**: 사용자가 물리적으로 인터페이스하는 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="75d2e-121">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="75d2e-122">**Teams 데스크톱 앱**: Teams 데스크톱 클라이언트 앱</span><span class="sxs-lookup"><span data-stu-id="75d2e-122">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="75d2e-123">Teams 요구 사항에 대한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="75d2e-123">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="75d2e-124">가상화 공급자 요구 사항</span><span class="sxs-lookup"><span data-stu-id="75d2e-124">Virtualization provider requirements</span></span>

<span data-ttu-id="75d2e-125">Teams 데스크톱 앱은 선도적인 가상화 솔루션 공급자를 사용하여 유효성을 검사했습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-125">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="75d2e-126">여러 시장 공급자를 사용하는 경우 최소 요구 사항을 충족하도록 가상화 솔루션 공급자를 문의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-126">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="75d2e-127">현재 AV(오디오/비디오) 최적화를 Teams VDI에서 가상 데스크톱, Citrix 및 VMware에서 Windows 인증을 받은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-127">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="75d2e-128">이 섹션의 정보를 검토하여 적절한 기능에 대한 모든 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-128">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="75d2e-129">인증된 플랫폼 Teams</span><span class="sxs-lookup"><span data-stu-id="75d2e-129">Platforms certified for Teams</span></span>

<span data-ttu-id="75d2e-130">다음 플랫폼에는 가상 데스크톱 인프라 솔루션이 Teams.</span><span class="sxs-lookup"><span data-stu-id="75d2e-130">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="75d2e-131">플랫폼</span><span class="sxs-lookup"><span data-stu-id="75d2e-131">Platform</span></span>|<span data-ttu-id="75d2e-132">솔루션</span><span class="sxs-lookup"><span data-stu-id="75d2e-132">Solution</span></span>|
|----|---|
|![Microsoft를 나타내는 로고](media/microsoft-logo.png)| <span data-ttu-id="75d2e-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span><span class="sxs-lookup"><span data-stu-id="75d2e-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![Citrix를 나타내는 로고](media/citrix-logo.png)| <span data-ttu-id="75d2e-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps 및 Desktops</a></span><span class="sxs-lookup"><span data-stu-id="75d2e-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![VMware를 나타내는 로고](media/vmware-logo.png)| <span data-ttu-id="75d2e-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span><span class="sxs-lookup"><span data-stu-id="75d2e-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="75d2e-139">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="75d2e-139">Windows Virtual Desktop</span></span>

<span data-ttu-id="75d2e-140">Windows Virtual Desktop은 VDI에서 Teams AV 최적화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-140">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="75d2e-141">자세한 사항 및 요구 사항 및 설치는 Virtual Desktop에서 Teams [Windows 참조하세요.](/azure/virtual-desktop/teams-on-wvd)</span><span class="sxs-lookup"><span data-stu-id="75d2e-141">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="75d2e-142">Citrix Virtual Apps 및 Desktops 요구 사항</span><span class="sxs-lookup"><span data-stu-id="75d2e-142">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="75d2e-143">Citrix Virtual Apps 및 Desktops(이전의 XenApp 및 XenDesktop)는 VDI에 대한 AV 최적화를 Teams 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-143">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="75d2e-144">Citrix Virtual Apps 및 데스크톱을 사용하여 VDI에서 Teams 채팅 및 공동 작업 외에도 통화 및 모임 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-144">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="75d2e-145">Citrix 다운로드 사이트에서 최신 버전의 Citrix Virtual Apps 및 [데스크톱을 다운로드할 수 있습니다.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)</span><span class="sxs-lookup"><span data-stu-id="75d2e-145">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="75d2e-146">(먼저 로그인해야 합니다.) 필요한 구성 요소는 기본적으로 [CWA(Citrix 작업](https://www.citrix.com/downloads/workspace-app/) 영역 앱) 및 VDA(Virtual Delivery Agent)에 번들로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-146">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="75d2e-147">CWA 또는 VDA에 추가 구성 요소 또는 플러그 인을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-147">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="75d2e-148">최신 서버 및 클라이언트 요구 사항은 [이 Citrix 웹 사이트](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75d2e-148">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="75d2e-149">VMware Horizon 작업 영역 및 데스크톱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="75d2e-149">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="75d2e-150">VMware Horizon은 하이브리드 클라우드에서 가상 데스크톱 및 앱을 안전하게 배달하기 위한 최신 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-150">VMware Horizon is a modern platform for secure delivery of virtual desktops and apps across the hybrid cloud.</span></span> <span data-ttu-id="75d2e-151">훌륭한 최종 사용자 환경을 제공하도록 VMware Horizon은 사용자에 대한 미디어 최적화를 Teams.</span><span class="sxs-lookup"><span data-stu-id="75d2e-151">To offer a great end-user experience, VMware Horizon provides media optimization for Teams.</span></span> <span data-ttu-id="75d2e-152">이 최적화는 가상 데스크톱 및 앱 전반에 걸쳐 전반적인 생산성을 향상하고, 가상 데스크톱을 사용하여 전화를 걸고 모임할 때 사용자 환경을 Teams.</span><span class="sxs-lookup"><span data-stu-id="75d2e-152">This optimization improves overall productivity across virtual desktops and apps, and enhances user experience when calling and meeting using Teams.</span></span>

<span data-ttu-id="75d2e-153">VMware 다운로드 페이지에서 [최신 버전의 VMware](https://my.vmware.com/web/vmware/downloads/#all_products) Horizon을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-153">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span> <span data-ttu-id="75d2e-154">필수 미디어 최적화 구성 요소는 기본적으로 Horizon 에이전트 및 Horizon 클라이언트의 일부로, 추가 플러그 인을 설치할 필요가 Teams.</span><span class="sxs-lookup"><span data-stu-id="75d2e-154">The required media optimization components are part of the Horizon Agent and Horizon Client by default and there's no need to install any additional plug-in to use the optimization feature for Teams.</span></span>

<span data-ttu-id="75d2e-155">미디어 최적화를 구성하는 방법에 대한 최신 요구 사항 및 지침을 Teams VMware 웹 사이트 [를 참조하세요.](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)</span><span class="sxs-lookup"><span data-stu-id="75d2e-155">To get the latest requirements and instructions on how to configure media optimization for Teams, see [this VMware website](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="75d2e-156">VDI에 Teams 데스크톱 앱 설치 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="75d2e-156">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="75d2e-157">MSI 패키지를 사용하여 Teams 설치 또는 사용자당 설치를 사용하여 VDI용 데스크톱 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-157">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="75d2e-158">사용할 방법을 결정하려면 영구적 또는 비영구적 설정을 사용할지 여부와 조직의 관련 기능 요구에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-158">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="75d2e-159">전용 영구 설정의 경우 두 방법 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-159">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="75d2e-160">그러나 비영구적 설치의 경우 효율적으로 Teams 컴퓨터당 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-160">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="75d2e-161">영구적이지 않은 설정 [섹션을 참조하세요.](#non-persistent-setup)</span><span class="sxs-lookup"><span data-stu-id="75d2e-161">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="75d2e-162">컴퓨터당 설치를 통해 자동 업데이트를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-162">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="75d2e-163">즉, 앱을 Teams 최신 버전으로 업데이트하려면 현재 버전을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-163">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="75d2e-164">사용자당 설치를 사용하면 자동 업데이트가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-164">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="75d2e-165">대부분의 VDI 배포의 경우 컴퓨터당 설치를 사용하여 Teams 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-165">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="75d2e-166">최신 버전으로 Teams 제거 프로시저를 시작하고 최신 버전 배포를 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-166">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="75d2e-167">VDI Teams AV 최적화가 제대로 작동하려면 씬 클라이언트 엔드포인트가 인터넷에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-167">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="75d2e-168">씬 클라이언트 엔드포인트에서 인터넷 액세스를 사용할 수 없는 경우 최적화 시작이 성공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-168">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="75d2e-169">즉, 사용자가 최적화되지 않은 미디어 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-169">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="75d2e-170">전용 영구 설정</span><span class="sxs-lookup"><span data-stu-id="75d2e-170">Dedicated persistent setup</span></span>

<span data-ttu-id="75d2e-171">전용 영구 설정에서 사용자의 로컬 운영 체제 변경 내용은 사용자가 로그오프한 후에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-171">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="75d2e-172">영구 설치의 경우 Teams 사용자당 및 컴퓨터당 설치를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-172">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="75d2e-173">권장되는 최소 VM 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-173">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="75d2e-174">매개 변수</span><span class="sxs-lookup"><span data-stu-id="75d2e-174">Parameter</span></span>  |<span data-ttu-id="75d2e-175">Workstation 운영 체제</span><span class="sxs-lookup"><span data-stu-id="75d2e-175">Workstation operating system</span></span>  |<span data-ttu-id="75d2e-176">서버 운영 체제</span><span class="sxs-lookup"><span data-stu-id="75d2e-176">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="75d2e-177">vCPU</span><span class="sxs-lookup"><span data-stu-id="75d2e-177">vCPU</span></span>   |    <span data-ttu-id="75d2e-178">코어 2개</span><span class="sxs-lookup"><span data-stu-id="75d2e-178">2 cores</span></span>     |  <span data-ttu-id="75d2e-179">4,6 또는 8</span><span class="sxs-lookup"><span data-stu-id="75d2e-179">4,6, or 8</span></span><br><span data-ttu-id="75d2e-180">기본 NUMA(비 균일하지 않은 메모리 액세스) 구성을 이해하고 이에 따라 VM을 구성하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-180">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="75d2e-181">RAM</span><span class="sxs-lookup"><span data-stu-id="75d2e-181">RAM</span></span>     |   <span data-ttu-id="75d2e-182">4GB</span><span class="sxs-lookup"><span data-stu-id="75d2e-182">4 GB</span></span>      | <span data-ttu-id="75d2e-183">사용자당 512~1024MB</span><span class="sxs-lookup"><span data-stu-id="75d2e-183">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="75d2e-184">저장소</span><span class="sxs-lookup"><span data-stu-id="75d2e-184">Storage</span></span>    | <span data-ttu-id="75d2e-185">8GB</span><span class="sxs-lookup"><span data-stu-id="75d2e-185">8 GB</span></span>        | <span data-ttu-id="75d2e-186">40~60GB</span><span class="sxs-lookup"><span data-stu-id="75d2e-186">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="75d2e-187">영구적이지 않은 설정</span><span class="sxs-lookup"><span data-stu-id="75d2e-187">Non-persistent setup</span></span>

<span data-ttu-id="75d2e-188">영구적이지 않은 설정에서 사용자의 로컬 운영 체제 변경 내용은 사용자가 로그오프한 후에 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-188">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="75d2e-189">이러한 설정은 일반적으로 공유 다중 사용자 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-189">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="75d2e-190">VM 구성은 사용자 수 및 사용 가능한 물리적 상자 리소스에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-190">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="75d2e-191">영구적이지 않은 설정의 경우 Teams 데스크톱 앱을 골든 이미지에 컴퓨터당 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-191">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="75d2e-192">(자세한 내용은 [VDI에서](#install-or-update-the-teams-desktop-app-on-vdi) 데스크톱 앱 설치 또는 Teams 섹션을 참조하세요.) 이렇게 하면 사용자 세션 동안 Teams 앱을 효율적으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-192">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="75d2e-193">비 Teams 런타임 데이터 동기화를 위해 프로필 캐싱 관리자도 Teams 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-193">Using Teams in a non-persistent setup also requires a profile-caching manager, for efficient Teams runtime data synchronization.</span></span> <span data-ttu-id="75d2e-194">효율적인 데이터 동기화를 통해 사용자의 세션 중에 적절한 사용자별 정보(예: 사용자의 데이터, 프로필 또는 설정)가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-194">Efficient data synchronization ensures that the appropriate user-specific information (such as a user's data, profile, or settings) is cached during the user's session.</span></span> <span data-ttu-id="75d2e-195">다음 두 폴더의 데이터가 동기화된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-195">Make sure data in these two folders are synched:</span></span><br>

- <span data-ttu-id="75d2e-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache(%localAppdata%\Microsoft\IdentityCache)</span><span class="sxs-lookup"><span data-stu-id="75d2e-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="75d2e-197">C:\Users\username\AppData\Roaming\Microsoft\Teams(%appdata%\Microsoft\Teams)</span><span class="sxs-lookup"><span data-stu-id="75d2e-197">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

> [!NOTE]
> <span data-ttu-id="75d2e-198">로밍 폴더(또는 폴더 리디렉션을 사용하는 경우 캐싱 관리자)는 애플리케이션을 실행하기 위해 Teams 런타임 데이터와 파일이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-198">A roaming folder (or, if you are using folder redirection, a caching manager) is required to ensure that the Teams app has the runtime data and files required to run the application.</span></span> <span data-ttu-id="75d2e-199">이 문제는 네트워크 대기 시간 문제 또는 네트워크 문제의 완화를 위해 필요하며, 그렇지 않으면 애플리케이션 오류 및 사용할 수 없는 데이터 및 파일로 인해 환경이 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-199">This is necessary to mitigate network latency issues or network glitches, which would otherwise cause application errors and a slow experience due to unavailable data and files.</span></span>

<span data-ttu-id="75d2e-200">다양한 캐싱 관리자 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-200">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="75d2e-201">예를 들어 [FSLogix](/fslogix/overview).</span><span class="sxs-lookup"><span data-stu-id="75d2e-201">For example, [FSLogix](/fslogix/overview).</span></span> <span data-ttu-id="75d2e-202">특정 구성 지침은 캐싱 관리자 공급자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="75d2e-202">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="75d2e-203">Teams 설정에 대한 캐시된 콘텐츠 제외 목록</span><span class="sxs-lookup"><span data-stu-id="75d2e-203">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="75d2e-204">캐싱 폴더, %appdata%/Microsoft/Teams 폴더에서 다음을 Teams.</span><span class="sxs-lookup"><span data-stu-id="75d2e-204">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="75d2e-205">이러한 항목을 제외하면 사용자 캐싱 크기를 줄여 비영구적 설정을 더욱 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-205">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="75d2e-206">.txt 파일</span><span class="sxs-lookup"><span data-stu-id="75d2e-206">.txt files</span></span>
- <span data-ttu-id="75d2e-207">미디어 스택 폴더</span><span class="sxs-lookup"><span data-stu-id="75d2e-207">Media-stack folder</span></span>
- <span data-ttu-id="75d2e-208">meeting-addin\Cache(%appdata%\Microsoft\Teams\meeting-addin\Cache)</span><span class="sxs-lookup"><span data-stu-id="75d2e-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="75d2e-209">엔터프라이즈용 Microsoft 365 앱 고려 사항</span><span class="sxs-lookup"><span data-stu-id="75d2e-209">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="75d2e-210">VDI에서 Teams 배포할 엔터프라이즈용 Microsoft 365 앱 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-210">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="75d2e-211">새 배포 Teams 엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="75d2e-211">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="75d2e-212">Teams 엔터프라이즈용 Microsoft 365 앱 배포하기 전에 먼저 컴퓨터당 설치를 사용하여 배포된 Teams 기존 앱의 제거를 먼저 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-212">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="75d2e-213">Teams 엔터프라이즈용 Microsoft 365 앱 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-213">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="75d2e-214">자세한 내용은 [VDI에서](#install-or-update-the-teams-desktop-app-on-vdi) Teams 데스크톱 앱 설치 또는 업데이트 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75d2e-214">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="75d2e-215">Teams 업데이트를 통한 엔터프라이즈용 Microsoft 365 앱 배포</span><span class="sxs-lookup"><span data-stu-id="75d2e-215">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="75d2e-216">Teams 설치에 엔터프라이즈용 Microsoft 365 앱.</span><span class="sxs-lookup"><span data-stu-id="75d2e-216">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="75d2e-217">사용자 엔터프라이즈용 Microsoft 365 앱 Teams 설치하기 때문에 [VDI에](#install-or-update-the-teams-desktop-app-on-vdi) Teams 데스크톱 앱 설치 또는 업데이트 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75d2e-217">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="75d2e-218">컴퓨터 Teams 설치 및 엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="75d2e-218">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="75d2e-219">엔터프라이즈용 Microsoft 365 앱 컴퓨터당 설치를 지원하지 Teams.</span><span class="sxs-lookup"><span data-stu-id="75d2e-219">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="75d2e-220">컴퓨터당 설치를 사용하려면 시스템 Teams 제외해야 엔터프라이즈용 Microsoft 365 앱.</span><span class="sxs-lookup"><span data-stu-id="75d2e-220">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="75d2e-221">[VM에](#deploy-the-teams-desktop-app-to-the-vm) Teams 데스크톱 앱 배포 및 Teams 섹션을 통해 배포를 제외하는 [엔터프라이즈용 Microsoft 365 앱](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75d2e-221">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="75d2e-222">배포를 Teams 제외하는 엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="75d2e-222">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="75d2e-223">Teams 및 엔터프라이즈용 Microsoft 365 앱 방법에 대한 자세한 내용은 Teams [](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) 새 설치에서 제외하는 엔터프라이즈용 Microsoft 365 앱 및 그룹 정책 사용 을 참조하여 [Teams.](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="75d2e-223">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="75d2e-224">VM에 Teams 데스크톱 앱 배포</span><span class="sxs-lookup"><span data-stu-id="75d2e-224">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="75d2e-225">다음 링크 Teams VDI VM 운영 체제와 일치하는 MSI 패키지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-225">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="75d2e-226">32비트 버전</span><span class="sxs-lookup"><span data-stu-id="75d2e-226">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [<span data-ttu-id="75d2e-227">64비트 버전</span><span class="sxs-lookup"><span data-stu-id="75d2e-227">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > <span data-ttu-id="75d2e-228">정부 클라우드의 경우 [MSI](msi-deployment.md) Microsoft Teams Microsoft Endpoint Configuration Manager 다운로드 링크를 사용하여 Microsoft Endpoint Configuration Manager 설치를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75d2e-228">For government clouds, see [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md) for the download links to the MSI files.</span></span>

    <span data-ttu-id="75d2e-229">필요한 데스크톱 앱의 최소 Teams 버전은 버전 1.3.00.4461입니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-229">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="75d2e-230">(이전 버전에서는 PSTN 보류가 지원되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="75d2e-230">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="75d2e-231">다음 명령 중 하나를 실행하여 VDI VM에 MSI를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-231">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="75d2e-232">사용자당 설치(기본값)</span><span class="sxs-lookup"><span data-stu-id="75d2e-232">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="75d2e-233">이 프로세스는 %AppData% 사용자 폴더에 Teams 설치하는 기본 설치입니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-233">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="75d2e-234">이 시점에서 골든 이미지 설정이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-234">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="75d2e-235">Teams 설치 시 사용자당 설치가 제대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-235">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="75d2e-236">컴퓨터당 설치</span><span class="sxs-lookup"><span data-stu-id="75d2e-236">Per-machine installation</span></span>

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        <span data-ttu-id="75d2e-237">이 프로세스는 컴퓨터에 필요한 레지스트리 키를 추가하여 Teams 설치 관리자에게 VDI 인스턴스인지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-237">This process adds a required registry key to the machine that lets the Teams installer know it is a VDI instance.</span></span>  <span data-ttu-id="75d2e-238">이 설정이 없는 경우 설치 관리자가 오류가 발생하여 "설치가 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-238">Without it, the installer will error out, stating: "Installation has failed.</span></span>  <span data-ttu-id="75d2e-239">VDI 환경이 검색되지 않은 경우 모든 사용자에게 설치할 수 없습니다."</span><span class="sxs-lookup"><span data-stu-id="75d2e-239">Cannot install for all users when a VDI environment is not detected."</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="75d2e-240">이 프로세스는 Teams 64비트 운영 체제의 프로그램 파일(x86) 폴더 및 32비트 운영 체제의 프로그램 파일 폴더에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-240">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="75d2e-241">이 시점에서 골든 이미지 설정이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-241">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="75d2e-242">비 Teams 설정에 대해 컴퓨터당 Teams 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-242">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="75d2e-243">다음 대화형 로그온 세션은 Teams 시작하고 자격 증명을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-243">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="75d2e-244">또한 이러한 예제에서는 **ALLUSERS=1 매개 변수를** 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-244">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="75d2e-245">이 매개 변수를 설정하면 Teams Machine-Wide 프로그램의 프로그램 및 기능에 설치 관리자를 & 앱의 Windows 설정 모든 사용자에 대해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-245">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="75d2e-246">그런 다음 모든 사용자가 관리자 자격 증명이 있는 Teams 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-246">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="75d2e-247">**ALLUSERS=1과 ALLUSER=1의** **차이점을** 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-247">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="75d2e-248">**ALLUSERS=1** 매개 변수는 VDI가 아닌 VDI 환경에서 사용할 수 **있으며, ALLUSER=1** 매개 변수는 VDI 환경에서만 사용하여 컴퓨터당 설치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-248">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="75d2e-249">VDI VM에서 MSI를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-249">Uninstall the MSI from the VDI VM.</span></span> <span data-ttu-id="75d2e-250">두 가지 방법으로 Teams.</span><span class="sxs-lookup"><span data-stu-id="75d2e-250">There are two ways to uninstall Teams.</span></span>

    - <span data-ttu-id="75d2e-251">PowerShell 스크립트: 이 [PowerShell](scripts/powershell-script-deployment-cleanup.md) 스크립트를 사용하여 사용자에 대한 Teams 제거하고 Teams 폴더를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-251">PowerShell script: You can use [this PowerShell script](scripts/powershell-script-deployment-cleanup.md) to uninstall Teams and remove the Teams folder for a user.</span></span> <span data-ttu-id="75d2e-252">컴퓨터에 설치된 각 사용자 Teams 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-252">Run the script for each user profile in which Teams was installed on the computer.</span></span>
    - <span data-ttu-id="75d2e-253">명령줄: 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-253">Command line: Run the following command.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="75d2e-254">이 프로세스는 운영 체제 환경에 Teams 프로그램 파일(x86) 폴더 또는 프로그램 파일 폴더에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-254">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="75d2e-255">Teams 성능 고려 사항의 설명</span><span class="sxs-lookup"><span data-stu-id="75d2e-255">Teams on VDI performance considerations</span></span>

<span data-ttu-id="75d2e-256">다양한 가상화된 설정 구성이 있습니다. 각각 최적화에 대한 포커스가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-256">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="75d2e-257">예를 들어 구성은 사용자 밀도에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-257">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="75d2e-258">계획할 때 조직의 워크로드 요구에 따라 설정을 최적화하는 데 도움이 되는 다음을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-258">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="75d2e-259">최소 요구 사항: 일부 워크로드에는 최소 요구 사항 이상인 리소스를 사용하여 설정이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-259">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="75d2e-260">예를 들어 더 많은 컴퓨팅 리소스를 요구하는 애플리케이션을 사용하는 개발자를 위한 워크로드입니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-260">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="75d2e-261">종속성: 데스크톱 앱 외부의 인프라, 워크로드 및 기타 환경 고려 사항의 종속성 Teams 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-261">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="75d2e-262">VDI의 비활성화 기능: Teams GPU 집약적 기능을 사용하지 않도록 설정하여 일시적인 CPU 사용률을 개선하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-262">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="75d2e-263">다음 기능은 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-263">The following features are disabled:</span></span>
    - <span data-ttu-id="75d2e-264">Teams CSS 애니메이션</span><span class="sxs-lookup"><span data-stu-id="75d2e-264">Teams CSS animation</span></span>
    - <span data-ttu-id="75d2e-265">Giphy 자동 시작</span><span class="sxs-lookup"><span data-stu-id="75d2e-265">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="75d2e-266">Teams 및 모임을 통해 VDI에서 사용</span><span class="sxs-lookup"><span data-stu-id="75d2e-266">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="75d2e-267">채팅 및 공동 작업 외에도 Teams 및 모임을 통해 VDI에서 지원되는 가상화 공급자 플랫폼에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-267">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="75d2e-268">지원되는 기능은 WebRTC 미디어 스택 및 가상화 공급자 구현을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-268">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="75d2e-269">다음 다이어그램에서는 아키텍처에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-269">The following diagram provides an overview of the architecture.</span></span>

![VDI 아키텍처에 Teams 다이어그램](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="75d2e-271">현재 VDI에서 AV 최적화 없이 Teams 실행하고 최적화를 위해 아직 지원되지 않는 기능을 사용하는 경우(예: 앱 공유 시 제공 및 제어) 가상화 공급자 정책을 설정하여 Teams 리디렉션을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-271">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="75d2e-272">즉, Teams 미디어 세션이 최적화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-272">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="75d2e-273">리디렉션을 해제하는 정책을 설정하는 방법에 대한 Teams 가상화 공급자에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="75d2e-273">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="75d2e-274">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="75d2e-274">Network requirements</span></span>

<span data-ttu-id="75d2e-275">환경을 평가하여 전체 클라우드 음성 및 비디오 배포에 영향을 줄 수 있는 위험 및 요구 사항을 식별하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-275">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="75d2e-276">네트워크 [비즈니스용 Skype](https://www.microsoft.com/download/details.aspx?id=53885) 평가 도구를 사용하여 네트워크가 Teams.</span><span class="sxs-lookup"><span data-stu-id="75d2e-276">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="75d2e-277">네트워크 준비 방법에 대한 자세한 내용은 Teams 에 대한 조직의 네트워크 [준비를 Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="75d2e-277">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="75d2e-278">VDI의 비즈니스용 Skype VDI에서 VDI로 Teams 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="75d2e-278">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="75d2e-279">VDI의 비즈니스용 Skype VDI에서 VDI로 Teams 경우 두 애플리케이션 간의 차이점 외에도 VDI가 구현될 때 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-279">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="75d2e-280">VDI에 있는 VDI에서 현재 지원되지 Teams VDI에 비즈니스용 Skype 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-280">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="75d2e-281">VDI에서 일부 AV 기능을 사용하지 않도록 설정하는 플랫폼당 정책</span><span class="sxs-lookup"><span data-stu-id="75d2e-281">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="75d2e-282">앱 공유 시 제어권 제공 및 제어</span><span class="sxs-lookup"><span data-stu-id="75d2e-282">Give and take control when app sharing</span></span>
- <span data-ttu-id="75d2e-283">오디오가 없는 채팅에서 화면 공유</span><span class="sxs-lookup"><span data-stu-id="75d2e-283">Screen share from chat without audio</span></span>
- <span data-ttu-id="75d2e-284">동시 비디오 및 화면 공유 보내기 및 수신</span><span class="sxs-lookup"><span data-stu-id="75d2e-284">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="75d2e-285">Teams용 데스크톱 앱과 Chrome 브라우저에서 Teams 데스크톱 앱</span><span class="sxs-lookup"><span data-stu-id="75d2e-285">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="75d2e-286">Teams 브라우저에서 AV 최적화를 사용하여 VDI용 Teams 데스크톱 앱의 대체를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-286">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="75d2e-287">채팅 및 공동 작업 환경은 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-287">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="75d2e-288">미디어가 필요한 경우 Chrome 브라우저에서 사용자 기대를 충족하지 않을 수 있는 몇 가지 환경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-288">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="75d2e-289">오디오 및 비디오 스트리밍 환경이 최적화되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-289">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="75d2e-290">사용자가 지연되거나 품질이 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-290">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="75d2e-291">브라우저 설정에서 디바이스 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-291">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="75d2e-292">디바이스 관리는 브라우저를 통해 처리하며 브라우저 사이트 설정에서 여러 설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-292">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="75d2e-293">디바이스 설정은 디바이스 관리에서 Windows 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-293">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="75d2e-294">Teams 및 공동 작업을 통해 VDI에서 작업</span><span class="sxs-lookup"><span data-stu-id="75d2e-294">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="75d2e-295">조직에서 채팅 및 공동 작업 기능만 사용하려는 Teams 사용자 수준 정책을 설정하여 통화 및 모임 기능을 Teams.</span><span class="sxs-lookup"><span data-stu-id="75d2e-295">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="75d2e-296">통화 및 모임 기능을 해제하기 위한 정책 설정</span><span class="sxs-lookup"><span data-stu-id="75d2e-296">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="75d2e-297">관리자 센터 또는 PowerShell을 사용하여 정책을 Microsoft Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-297">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="75d2e-298">정책 변경이 전파하는 데 몇 시간(몇 시간)이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-298">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="75d2e-299">특정 계정에 대한 변경 내용이 즉시 표시되지 않는 경우 몇 시간 후에 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="75d2e-299">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="75d2e-300">[**호출 경찰**](teams-calling-policy.md): Teams 모든 호출 기능이 꺼져 있는 기본 제공 DisallowCalling 호출 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-300">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="75d2e-301">가상화된 환경에서 사용자를 사용하는 조직의 모든 Teams DisallowCalling 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-301">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="75d2e-302">[**모임 정책**](meeting-policies-in-teams.md): Teams 모든 모임 기능을 해제하는 기본 제공 AllOff 모임 정책이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-302">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="75d2e-303">가상화된 환경에서 모든 사용자를 사용하는 Teams AllOff 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-303">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="75d2e-304">관리 센터를 사용하여 Microsoft Teams 할당</span><span class="sxs-lookup"><span data-stu-id="75d2e-304">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="75d2e-305">DisallowCalling 호출 정책 및 AllOff 모임 정책을 사용자에게 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="75d2e-305">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="75d2e-306">관리 센터의 왼쪽 Microsoft Teams 사용자로 **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-306">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="75d2e-307">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-307">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="75d2e-308">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-308">Do the following:</span></span>
    1. <span data-ttu-id="75d2e-309">통화 **정책에서** **를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-309">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2. <span data-ttu-id="75d2e-310">모임 **정책에서** **AllOff 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-310">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="75d2e-311">적용 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-311">Click **Apply**.</span></span>

<span data-ttu-id="75d2e-312">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-312">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="75d2e-313">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-313">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="75d2e-314">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-314">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="75d2e-315">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-315">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="75d2e-316">**설정 편집** 을 클릭하고 원하는 대로 변경한 다음, **적용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-316">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="75d2e-317">또는 다음을 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-317">Or, you can also do the following:</span></span>

1. <span data-ttu-id="75d2e-318">관리 센터의 왼쪽 Microsoft Teams 할당할 정책으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="75d2e-318">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="75d2e-319">예제:</span><span class="sxs-lookup"><span data-stu-id="75d2e-319">For example:</span></span>
    - <span data-ttu-id="75d2e-320">음성 통화  >  **정책으로 이동한** **다음, DisallowCalling 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-320">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="75d2e-321">모임 모임 **정책으로**  >  이동한 다음 **AllOff 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-321">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
2. <span data-ttu-id="75d2e-322">**사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-322">Select **Manage users**.</span></span>
3. <span data-ttu-id="75d2e-323">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-323">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="75d2e-324">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-324">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="75d2e-325">사용자 추가가 완료되면 저장 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-325">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="75d2e-326">PowerShell을 사용하여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="75d2e-326">Assign policies using PowerShell</span></span>

<span data-ttu-id="75d2e-327">다음 예제에서는 [Grant-CsTeamsCallingPolicy를](/powershell/module/skype/grant-csteamscallingpolicy) 사용하여 사용자에게 DisallowCalling 호출 정책을 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-327">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="75d2e-328">PowerShell을 사용하여 통화 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-328">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="75d2e-329">다음 예제에서는 [Grant-CsTeamsMeetingPolicy를](/powershell/module/skype/grant-csteamsmeetingpolicy) 사용하여 AllOff 모임 정책을 사용자에게 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-329">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="75d2e-330">PowerShell을 사용하여 모임 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-330">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="75d2e-331">채팅 및 Teams VDI에서 마이그레이션하여 통화 및 Teams 최적화</span><span class="sxs-lookup"><span data-stu-id="75d2e-331">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="75d2e-332">채팅 및 Teams 및 공동 작업을 사용하여 VDI에 대한 기존 구현이 있는 경우 사용자 수준 정책을 설정하여 통화 및 모임 기능을 해제하고 AV 최적화를 사용하여 Teams VDI 사용자에 대한 호출 및 모임 기능을 설정하도록 정책을 Teams 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-332">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="75d2e-333">통화 및 모임 기능을 켜기 위한 정책 설정</span><span class="sxs-lookup"><span data-stu-id="75d2e-333">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="75d2e-334">관리자 센터 또는 Microsoft Teams PowerShell을 사용하여 사용자에게 통화 및 모임 정책을 설정하고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-334">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="75d2e-335">정책 변경이 전파하는 데 다소 시간이 걸릴 수 있습니다(몇 시간).</span><span class="sxs-lookup"><span data-stu-id="75d2e-335">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="75d2e-336">특정 계정에 대한 변경 내용이 즉시 표시되지 않는 경우 몇 시간 후에 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="75d2e-336">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="75d2e-337">[**호출 경찰**](teams-calling-policy.md): 사용자가 사용할 수 있는 Teams 제어하는 정책 호출 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-337">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="75d2e-338">Teams 모든 호출 기능이 켜져 있는 기본 제공 AllowCalling 호출 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-338">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="75d2e-339">모든 호출 기능을 켜기 위해 AllowCalling 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-339">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="75d2e-340">또는 사용자 지정 호출 정책을 만들어 원하는 호출 기능을 켜고 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-340">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span>

<span data-ttu-id="75d2e-341">[**모임 정책**](meeting-policies-in-teams.md): Teams 사용자가 만들 수 있는 모임 유형 및 조직의 사용자가 예약한 모임 참가자에 사용할 수 있는 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-341">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="75d2e-342">Teams 모든 모임 기능이 켜져 있는 기본 제공 AllOn 모임 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-342">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="75d2e-343">모든 모임 기능을 켜기 위해 AllOn 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-343">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="75d2e-344">또는 사용자 지정 모임 정책을 만들어 원하는 모임 기능을 켜고 사용자를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-344">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="75d2e-345">관리 센터를 사용하여 Microsoft Teams 할당</span><span class="sxs-lookup"><span data-stu-id="75d2e-345">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="75d2e-346">AllowCalling 호출 정책 및 AllOn 모임 정책을 사용자에게 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="75d2e-346">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="75d2e-347">관리 센터의 왼쪽 Microsoft Teams 사용자로 **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-347">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="75d2e-348">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-348">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="75d2e-349">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-349">Do the following:</span></span>
    1. <span data-ttu-id="75d2e-350">통화 **정책에서** 허용 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-350">Under **Calling policy**, click **AllowCalling**.</span></span>
    2. <span data-ttu-id="75d2e-351">모임 **정책에서** **AllOn 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-351">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="75d2e-352">적용 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-352">Click **Apply**.</span></span>

<span data-ttu-id="75d2e-353">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-353">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="75d2e-354">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-354">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="75d2e-355">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-355">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="75d2e-356">모든 사용자를 선택하려면 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-356">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="75d2e-357">**설정 편집** 을 클릭하고 원하는 대로 변경한 다음, **적용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-357">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="75d2e-358">또는 다음을 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-358">Or, you can also do the following:</span></span>

1. <span data-ttu-id="75d2e-359">관리 센터의 왼쪽 Microsoft Teams 할당할 정책으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="75d2e-359">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="75d2e-360">예제:</span><span class="sxs-lookup"><span data-stu-id="75d2e-360">For example:</span></span>
    - <span data-ttu-id="75d2e-361">음성 통화  >  **정책으로 이동한** 다음 **허용 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-361">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="75d2e-362">모임 **모임 정책으로**  >  이동한 다음 **AllOn 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-362">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
2. <span data-ttu-id="75d2e-363">**사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-363">Select **Manage users**.</span></span>
3. <span data-ttu-id="75d2e-364">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-364">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="75d2e-365">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-365">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="75d2e-366">사용자 추가가 완료되면 저장 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-366">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="75d2e-367">PowerShell을 사용하여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="75d2e-367">Assign policies using PowerShell</span></span>

<span data-ttu-id="75d2e-368">다음 예제에서는 [Grant-CsTeamsCallingPolicy를](/powershell/module/skype/grant-csteamscallingpolicy) 사용하여 사용자에게 AllowCalling 호출 정책을 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-368">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="75d2e-369">PowerShell을 사용하여 통화 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-369">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="75d2e-370">다음 예제에서는 [Grant-CsTeamsMeetingPolicy를](/powershell/module/skype/grant-csteamsmeetingpolicy) 사용하여 AllOn 모임 정책을 사용자에게 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-370">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="75d2e-371">PowerShell을 사용하여 모임 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-371">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="75d2e-372">제어 폴백 모드 Teams</span><span class="sxs-lookup"><span data-stu-id="75d2e-372">Control fallback mode in Teams</span></span>

<span data-ttu-id="75d2e-373">지원되지 않는 엔드포인트에서 사용자가 연결하면 사용자가 AV가 최적화되지 않은 폴백 모드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-373">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="75d2e-374">다음 레지스트리 DWORD 값 중 하나를 설정하여 폴백 모드를 사용하지 않도록 설정하거나 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-374">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="75d2e-375">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="75d2e-375">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="75d2e-376">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="75d2e-376">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="75d2e-377">폴백 모드를 사용하지 않도록 설정하고 값을 **1로 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-377">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="75d2e-378">오디오만 사용하도록 설정하려면 값을 **2로 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="75d2e-378">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="75d2e-379">값이 존재하지 않는 경우 또는 **0(0)으로** 설정되어 있는 경우 폴백 모드가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-379">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="75d2e-380">이 기능은 1.3.00.13565 Teams 버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-380">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="disable-audio-and-video-settings-for-vdi"></a><span data-ttu-id="75d2e-381">VDI에 대한 오디오 및 비디오 설정을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="75d2e-381">Disable audio and video settings for VDI</span></span>

<span data-ttu-id="75d2e-382">Teams VDI 정책은 Microsoft Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-382">Teams VDI policies are available in the Microsoft Teams module.</span></span> <span data-ttu-id="75d2e-383">이러한 정책은 최적화되지 않은 VDI 환경에서 활성화되어 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-383">These policies are active and enforced on non-optimized VDI environments.</span></span>

- <span data-ttu-id="75d2e-384">New-CsTeamsVdiPolicy</span><span class="sxs-lookup"><span data-stu-id="75d2e-384">New-CsTeamsVdiPolicy</span></span>  
- <span data-ttu-id="75d2e-385">Grant-CsTeamsVdiPolicy</span><span class="sxs-lookup"><span data-stu-id="75d2e-385">Grant-CsTeamsVdiPolicy</span></span>
- <span data-ttu-id="75d2e-386">Remove-CsTeamsVdiPolicy</span><span class="sxs-lookup"><span data-stu-id="75d2e-386">Remove-CsTeamsVdiPolicy</span></span>
- <span data-ttu-id="75d2e-387">Set-CsTeamsVdiPolicy</span><span class="sxs-lookup"><span data-stu-id="75d2e-387">Set-CsTeamsVdiPolicy</span></span>

> [!NOTE]
> <span data-ttu-id="75d2e-388">최적화되지 않은 환경에만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-388">This is only for non-optimized environments.</span></span>

### <a name="update-a-module-name"></a><span data-ttu-id="75d2e-389">모듈 이름 업데이트</span><span class="sxs-lookup"><span data-stu-id="75d2e-389">Update a module name</span></span>

<span data-ttu-id="75d2e-390">update-Module -Name MicrosoftTeams -AllowPrerelease</span><span class="sxs-lookup"><span data-stu-id="75d2e-390">update-Module -Name MicrosoftTeams -AllowPrerelease</span></span>

```PowerShell
<# Import and connect to online (CSOnline runs the policies) #>
Import-Module microsoftTeams
if( -not $sess){
    $session = New-CsOnlineSession
    $pss = Import-PSSession $session
}
<# Check out the commands #>
Get-Command -Noun *VDI*
<#
```

### <a name="set-policies-to-limit-calling-features"></a><span data-ttu-id="75d2e-391">통화 기능을 제한하기 위해 정책 설정</span><span class="sxs-lookup"><span data-stu-id="75d2e-391">Set policies to limit calling features</span></span>

<span data-ttu-id="75d2e-392">이 VDI 정책 설정 -DisableCallsAndMeetings를 $true VDI에 로그인하기 위해 Teams 사용자가 다음을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-392">When users with this VDI Policy setting -DisableCallsAndMeetings $true to sign in to Teams on VDI, they shouldn't be able to:</span></span>

- <span data-ttu-id="75d2e-393">전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-393">Make calls.</span></span>
- <span data-ttu-id="75d2e-394">모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-394">Join meetings.</span></span>
- <span data-ttu-id="75d2e-395">채팅에서 화면 공유를 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-395">Do a screen share from chat.</span></span>

<span data-ttu-id="75d2e-396">모든 유형의 호출을 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-396">All types of calling should be disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="75d2e-397">최적화되지 않은 환경에만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-397">This is only for non-optimized environments.</span></span>

```PowerShell
#>
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false
<# Assign Policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue
<# wait for some time until the policy is applied #>
get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
<#
Show all Policies  
#>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
<#
```

<span data-ttu-id="75d2e-398">VDI 정책 설정 -DisableAudioVideoInCallsAndMeetings를 사용하여 VDI에 $true 로그인할 Teams 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-398">When users with the VDI Policy setting -DisableAudioVideoInCallsAndMeetings $true sign in to Teams on VDI, they should be able to:</span></span>

- <span data-ttu-id="75d2e-399">채팅에서 화면 공유를 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-399">Do a screen share from chat.</span></span>
- <span data-ttu-id="75d2e-400">모임에 참가하고 화면을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-400">Join a meeting and share a screen.</span></span> <span data-ttu-id="75d2e-401">오디오를 휴대폰으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-401">Move their audio to a phone.</span></span>
- <span data-ttu-id="75d2e-402">사용자는 VDI에서 사람 대 사람 오디오 및 비디오 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-402">Users shouldn't be able to do a person-to-person audio and video call from VDI.</span></span>

> [!NOTE]
> <span data-ttu-id="75d2e-403">최적화되지 않은 환경에만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-403">This is only for non-optimized environments.</span></span>

```powershell
#>
$PolName = "DisableCallsAndMeetingsAV"
New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName
<# wait for some time until the policy is applied #>
get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
<# ## Cleanup afterwards #>
$cleanup = $false
if($cleanup){
    "Doing cleanup"
    # de-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*
    # remove Policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a><span data-ttu-id="75d2e-404">알려진 문제 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="75d2e-404">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="75d2e-405">클라이언트 배포, 설치 및 설치</span><span class="sxs-lookup"><span data-stu-id="75d2e-405">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="75d2e-406">컴퓨터당 설치를 Teams VDI가 아닌 클라이언트가 있는 방식으로 VDI의 Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-406">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="75d2e-407">[VDI의](#install-or-update-the-teams-desktop-app-on-vdi) 데스크톱 앱 설치 또는 업데이트 섹션에 설명된 Teams VM 이미지를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-407">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="75d2e-408">최신 버전으로 업데이트하려면 현재 버전을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-408">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="75d2e-409">Citrix 환경에서 사용자가 가상 머신을 Teams 경우 업데이트가 Teams 다시 연결할 때 사용자가 AV에 대해 최적화되지 않은 상태로 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-409">In Citrix environments, if the user disconnects from the Virtual Machine while Teams is running, Teams updates can result in the user to be in a non-optimized state for AV when they reconnect.</span></span> <span data-ttu-id="75d2e-410">이 시나리오를 피하기 위해 사용자가 Citrix Virtual Machine에서 Teams 전에 연결을 종료하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-410">We recommend that users quit Teams before they disconnect from Citrix Virtual Machine to avoid this scenario.</span></span>
- <span data-ttu-id="75d2e-411">Teams 사용자당 또는 컴퓨터당 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-411">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="75d2e-412">사용자 Teams 및 컴퓨터당 동시 배포는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-412">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="75d2e-413">컴퓨터당 또는 사용자당을 이러한 모드 중 하나로 마이그레이션하려면 제거 프로시저를 따라 두 모드로 다시 재배포합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-413">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="75d2e-414">Windows Virtual Desktop은 현재 macOS 및 Linux 기반 클라이언트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-414">Windows Virtual Desktop doesn't support macOS and Linux-based clients at this time.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="75d2e-415">통화 및 모임</span><span class="sxs-lookup"><span data-stu-id="75d2e-415">Calling and meetings</span></span>

<span data-ttu-id="75d2e-416">다음 호출 및 모임 기능은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-416">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="75d2e-417">새 모임 환경 또는 새 모임 환경과 함께 제공된 기능과 같은 모든 다중 창 기능</span><span class="sxs-lookup"><span data-stu-id="75d2e-417">Any multi-window functionality like the new meeting experiences or any functionality that comes with the new meeting experience</span></span>
- <span data-ttu-id="75d2e-418">향상된 응급 서비스</span><span class="sxs-lookup"><span data-stu-id="75d2e-418">Enhanced emergency services</span></span>
- <span data-ttu-id="75d2e-419">앱과 디바이스 간의 HID Teams LED 컨트롤</span><span class="sxs-lookup"><span data-stu-id="75d2e-419">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="75d2e-420">배경 흐림 및 효과</span><span class="sxs-lookup"><span data-stu-id="75d2e-420">Background blur and effects</span></span>
- <span data-ttu-id="75d2e-421">브로드캐스트 및 라이브 이벤트 생산자 및 발표자 역할</span><span class="sxs-lookup"><span data-stu-id="75d2e-421">Broadcast and live event producer and presenter roles</span></span>
- <span data-ttu-id="75d2e-422">Location-Based(LBR)</span><span class="sxs-lookup"><span data-stu-id="75d2e-422">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="75d2e-423">PSTN 콜링백 톤</span><span class="sxs-lookup"><span data-stu-id="75d2e-423">PSTN call ringback tone</span></span>
- <span data-ttu-id="75d2e-424">공유 시스템 오디오/컴퓨터 소리</span><span class="sxs-lookup"><span data-stu-id="75d2e-424">Shared system audio/computer sound</span></span>
- <span data-ttu-id="75d2e-425">직접 라우팅을 위한 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="75d2e-425">Media bypass for Direct Routing</span></span>
- <span data-ttu-id="75d2e-426">통화 공원</span><span class="sxs-lookup"><span data-stu-id="75d2e-426">Call park</span></span>
- <span data-ttu-id="75d2e-427">확대/축소 제어</span><span class="sxs-lookup"><span data-stu-id="75d2e-427">Zoom control</span></span>

> [!NOTE]
> <span data-ttu-id="75d2e-428">현재 VDI가 아닌 환경에서만 사용할 수 있는 호출 및 모임 기능을 추가하는 작업을 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-428">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="75d2e-429">여기에는 품질에 대한 더 많은 관리 제어, 추가 화면 공유 시나리오 및 최근에 추가된 고급 기능이 Teams.</span><span class="sxs-lookup"><span data-stu-id="75d2e-429">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="75d2e-430">다가오는 기능에 Teams 자세한 내용은 담당자에게 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-430">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="75d2e-431">다음은 호출 및 모임에 대한 알려진 문제 및 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-431">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="75d2e-432">비즈니스용 Skype 상호 연동성은 오디오 호출로 제한됩니다. 비디오 모달리티가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-432">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="75d2e-433">수신 및 발신 비디오 스트림 해상도는 720p 해상도로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-433">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span>
- <span data-ttu-id="75d2e-434">들어오는 카메라 또는 화면 공유 스트림에서 하나의 비디오 스트림만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-434">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="75d2e-435">들어오는 화면 공유가 있는 경우 주된 스피커의 비디오 대신 화면 공유가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-435">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="75d2e-436">Teams 연결이 끊어진 경우 사용자가 선택한 마지막 오디오 디바이스를 사용하도록 전환하지 않은 다음 다시 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-436">Teams doesn't switch to use the last audio device that a user selected, if the device is disconnected, and then reconnected.</span></span>
- <span data-ttu-id="75d2e-437">외출 화면 공유:</span><span class="sxs-lookup"><span data-stu-id="75d2e-437">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="75d2e-438">애플리케이션 공유는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-438">Application sharing is not supported.</span></span>
- <span data-ttu-id="75d2e-439">제어권 및 제어권:</span><span class="sxs-lookup"><span data-stu-id="75d2e-439">Give control and take control:</span></span>
    - <span data-ttu-id="75d2e-440">화면 공유 또는 애플리케이션 공유 세션 중에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-440">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="75d2e-441">공유 세션 동안 PowerPoint 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-441">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="75d2e-442">Citrix 전용 제한 사항</span><span class="sxs-lookup"><span data-stu-id="75d2e-442">Citrix-only limitations</span></span>
    - <span data-ttu-id="75d2e-443">다중 모니터 설정에서 화면 공유 시 주 모니터만 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-443">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="75d2e-444">CWA의 높은 DPI 크기 조정은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-444">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="75d2e-445">VDI와 Teams 알려진 문제에 대한 자세한 내용은 조직의 지원 Teams [를 참조합니다.](/MicrosoftTeams/troubleshoot/teams-welcome)</span><span class="sxs-lookup"><span data-stu-id="75d2e-445">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="75d2e-446">문제 해결</span><span class="sxs-lookup"><span data-stu-id="75d2e-446">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="75d2e-447">Citrix 구성 요소 문제 해결</span><span class="sxs-lookup"><span data-stu-id="75d2e-447">Troubleshoot Citrix components</span></span>

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a><span data-ttu-id="75d2e-448">Teams 또는 Teams 화면이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-448">Teams crashes or the Teams sign in screen is blank</span></span>

<span data-ttu-id="75d2e-449">Citrix VDA 버전 1906 및 1909에 알려진 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-449">This is a known issue with Citrix VDA versions 1906 and 1909.</span></span> <span data-ttu-id="75d2e-450">이 문제를 해결하기 위해 다음 레지스트리 DWORD 값을 추가하고 204(hexadecimal)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-450">To work around this issue, add the following registry DWORD value, and set it to 204 (hexadecimal).</span></span>

<span data-ttu-id="75d2e-451">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span><span class="sxs-lookup"><span data-stu-id="75d2e-451">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span></span>

<span data-ttu-id="75d2e-452">그런 다음 VDA를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="75d2e-452">Then, restart VDA.</span></span> <span data-ttu-id="75d2e-453">자세한 내용은 이 Citrix 지원 문서, 에 대한 [HDX 최적화 문제 해결 Teams.](https://support.citrix.com/article/CTX253754)</span><span class="sxs-lookup"><span data-stu-id="75d2e-453">To learn more, see this Citrix support article, [Troubleshooting HDX optimization for Teams](https://support.citrix.com/article/CTX253754).</span></span>

## <a name="related-topics"></a><span data-ttu-id="75d2e-454">관련 항목</span><span class="sxs-lookup"><span data-stu-id="75d2e-454">Related topics</span></span>

- [<span data-ttu-id="75d2e-455">MSI를 Microsoft Teams 설치</span><span class="sxs-lookup"><span data-stu-id="75d2e-455">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="75d2e-456">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="75d2e-456">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="75d2e-457">가상 Microsoft Teams 데스크톱에서 Windows 사용</span><span class="sxs-lookup"><span data-stu-id="75d2e-457">Use Microsoft Teams on Windows Virtual desktop</span></span>](/azure/virtual-desktop/teams-on-wvd)
