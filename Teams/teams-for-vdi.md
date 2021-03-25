---
title: VDI(Virtualized Desktop Infrastructure)용 Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: VDI(Virtualized Desktop Infrastructure) 환경에서 Microsoft Teams를 실행하는 방법에 대해 자세히 알아보고
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 020ed67b695c10e54d43891d78a77783ab61ee81
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119197"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="0405f-103">VDI(Virtualized Desktop Infrastructure)용 Teams</span><span class="sxs-lookup"><span data-stu-id="0405f-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="0405f-104">이 문서에서는 가상화된 환경에서 Microsoft Teams 사용에 대한 요구 사항 및 제한 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="0405f-105">VDI란?</span><span class="sxs-lookup"><span data-stu-id="0405f-105">What is VDI?</span></span>

<span data-ttu-id="0405f-106">VDI(Virtual Desktop Infrastructure)는 데이터 센터의 중앙 집중식 서버에 데스크톱 운영 체제 및 애플리케이션을 호스트하는 가상화 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="0405f-107">이렇게 하면 완전히 보호된 규정을 준수하는 중앙 집중식 원본을 사용하여 사용자에게 완전히 개인 설정된 데스크톱 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span>

<span data-ttu-id="0405f-108">가상화된 환경에서 Microsoft Teams는 채팅 및 공동 작업을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-108">Microsoft Teams in a virtualized environment supports chat and collaboration.</span></span> <span data-ttu-id="0405f-109">또한 Windows Virtual Desktop, Citrix 및 VMware 플랫폼을 사용하여 호출 및 모임 기능도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-109">And with the Windows Virtual Desktop, Citrix, and VMware platforms, calling and meeting functionality is also supported.</span></span>

<span data-ttu-id="0405f-110">가상화된 환경의 팀은 여러 구성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-110">Teams in a virtualized environment supports multiple configurations.</span></span> <span data-ttu-id="0405f-111">여기에는 VDI, 전용, 공유, 영구 및 비 영구 모드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-111">These include VDI, dedicated, shared, persistent, and non-persistent modes.</span></span> <span data-ttu-id="0405f-112">기능은 지속적인 개발에 있으며 정기적으로 추가되고, 기능은 다음 달과 몇 년 동안 확장될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-112">Features are in continuous development and are added on a regular basis, and functionality will expand in the coming months and years.</span></span>

<span data-ttu-id="0405f-113">가상화된 환경에서 Teams를 사용하는 것이 가상화된 환경의 Teams 사용과 다소 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-113">Using Teams in a virtualized environment might be somewhat different from using Teams in a non-virtualized environment.</span></span> <span data-ttu-id="0405f-114">예를 들어 가상화된 환경에서 일부 고급 기능을 사용할 수 없는 경우 비디오 해상도가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-114">For example, some advanced features might not be available in a virtualized environment, and video resolution might differ.</span></span>

<span data-ttu-id="0405f-115">최적의 사용자 환경을 보장하기 위해 이 문서의 지침을 따르하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-115">To ensure an optimal user experience, follow the guidance in this article.</span></span>

> [!Note]
> <span data-ttu-id="0405f-116">다른 플랫폼에서 Teams VDI에 대한 자세한 내용은 플랫폼에 따라 [Teams 기능을 참조하세요.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)</span><span class="sxs-lookup"><span data-stu-id="0405f-116">For details about Teams VDI on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="teams-on-vdi-components"></a><span data-ttu-id="0405f-117">VDI 구성 요소의 팀</span><span class="sxs-lookup"><span data-stu-id="0405f-117">Teams on VDI components</span></span>

<span data-ttu-id="0405f-118">가상화된 환경에서 Teams를 사용하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-118">Using Teams in a virtualized environment requires the following components.</span></span>

- <span data-ttu-id="0405f-119">**가상화 브로커**: Azure와 같은 가상화 공급자에 대한 리소스 및 연결 관리자</span><span class="sxs-lookup"><span data-stu-id="0405f-119">**Virtualization broker**: The resource and connection manager to the virtualization provider, such as Azure</span></span>
- <span data-ttu-id="0405f-120">**가상 데스크톱**: Microsoft Teams를 실행하는 VM(Virtual Machine) 스택</span><span class="sxs-lookup"><span data-stu-id="0405f-120">**Virtual desktop**: The Virtual Machine (VM) stack that runs Microsoft Teams</span></span>
- <span data-ttu-id="0405f-121">**씬 클라이언트**: 사용자가 물리적으로 인터페이스하는 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="0405f-121">**Thin client**: The endpoint that the user physically interfaces with</span></span>
- <span data-ttu-id="0405f-122">**Teams 데스크톱 앱**: Teams 데스크톱 클라이언트 앱</span><span class="sxs-lookup"><span data-stu-id="0405f-122">**Teams desktop app**: The Teams desktop client app</span></span>

## <a name="teams-on-vdi-requirements"></a><span data-ttu-id="0405f-123">VDI 요구 사항에 대한 팀</span><span class="sxs-lookup"><span data-stu-id="0405f-123">Teams on VDI requirements</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="0405f-124">가상화 공급자 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0405f-124">Virtualization provider requirements</span></span>

<span data-ttu-id="0405f-125">Teams 데스크톱 앱은 주요 가상화 솔루션 공급자를 사용하여 유효성을 검사했습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-125">The Teams desktop app was validated with leading virtualization solution providers.</span></span> <span data-ttu-id="0405f-126">여러 시장 공급자를 사용하는 경우 최소 요구 사항을 충족하도록 가상화 솔루션 공급자를 문의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-126">With multiple market providers, we recommend that you consult your virtualization solution provider to ensure that you meet the minimum requirements.</span></span>
  
<span data-ttu-id="0405f-127">현재 AV(오디오/비디오) 최적화가 있는 VDI의 Teams는 Windows Virtual Desktop, Citrix 및 VMware를 통해 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-127">Currently, Teams on VDI with audio/video (AV) optimization is certified with Windows Virtual Desktop, Citrix, and VMware.</span></span> <span data-ttu-id="0405f-128">이 섹션의 정보를 검토하여 적절한 기능에 대한 모든 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-128">Review the information in this section to ensure that you meet all requirements for proper functionality.</span></span>

### <a name="platforms-certified-for-teams"></a><span data-ttu-id="0405f-129">Teams에 대해 인증된 플랫폼</span><span class="sxs-lookup"><span data-stu-id="0405f-129">Platforms certified for Teams</span></span>

<span data-ttu-id="0405f-130">다음 플랫폼에는 Teams용 가상 데스크톱 인프라 솔루션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-130">The following platforms have virtual desktop infrastructure solutions for Teams.</span></span>

|<span data-ttu-id="0405f-131">플랫폼</span><span class="sxs-lookup"><span data-stu-id="0405f-131">Platform</span></span>|<span data-ttu-id="0405f-132">솔루션</span><span class="sxs-lookup"><span data-stu-id="0405f-132">Solution</span></span>|
|----|---|
|![Microsoft를 나타내는 로고](media/microsoft-logo.png)| <span data-ttu-id="0405f-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span><span class="sxs-lookup"><span data-stu-id="0405f-134"><a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Windows Virtual Desktop</a></span></span> |
|![Citrix를 나타내는 로고](media/citrix-logo.png)| <span data-ttu-id="0405f-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps 및 Desktops</a></span><span class="sxs-lookup"><span data-stu-id="0405f-136"><a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a></span></span> |
|![VMware를 나타내는 로고](media/vmware-logo.png)| <span data-ttu-id="0405f-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span><span class="sxs-lookup"><span data-stu-id="0405f-138"><a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a></span></span> |

### <a name="windows-virtual-desktop"></a><span data-ttu-id="0405f-139">Windows Virtual Desktop</span><span class="sxs-lookup"><span data-stu-id="0405f-139">Windows Virtual Desktop</span></span>

<span data-ttu-id="0405f-140">Windows Virtual Desktop은 VDI의 Teams에 대한 AV 최적화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-140">Windows Virtual Desktop provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="0405f-141">자세한 사항 및 요구 사항 및 설치는 [Windows Virtual Desktop에서 Teams 사용을 참조하세요.](/azure/virtual-desktop/teams-on-wvd)</span><span class="sxs-lookup"><span data-stu-id="0405f-141">To learn more and requirements and installation, see [Use Teams on Windows Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).</span></span>

### <a name="citrix-virtual-apps-and-desktops-requirements"></a><span data-ttu-id="0405f-142">Citrix Virtual Apps 및 Desktops 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0405f-142">Citrix Virtual Apps and Desktops requirements</span></span>

<span data-ttu-id="0405f-143">Citrix Virtual Apps 및 Desktops(이전의 XenApp 및 XenDesktop)는 VDI의 Teams에 대한 AV 최적화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-143">Citrix Virtual Apps and Desktops (formerly known as XenApp and XenDesktop) provides AV optimization for Teams on VDI.</span></span> <span data-ttu-id="0405f-144">Citrix Virtual Apps 및 Desktops를 사용하여 VDI의 Teams는 채팅 및 공동 작업 외에도 통화 및 모임 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-144">With Citrix Virtual Apps and Desktops, Teams on VDI supports calling and meeting functionality in addition to chat and collaboration.</span></span>

<span data-ttu-id="0405f-145">Citrix 다운로드 사이트에서 최신 버전의 Citrix Virtual Apps 및 [데스크톱을 다운로드할 수 있습니다.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/)</span><span class="sxs-lookup"><span data-stu-id="0405f-145">You can download the latest version of Citrix Virtual Apps and Desktops at [the Citrix downloads site](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/).</span></span> <span data-ttu-id="0405f-146">(먼저 로그인해야 합니다.) 필요한 구성 요소는 기본적으로 [CWA(Citrix 작업](https://www.citrix.com/downloads/workspace-app/) 영역 앱) 및 VDA(Virtual Delivery Agent)에 번들로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-146">(You'll need to sign in first.) The necessary components are bundled into the [Citrix Workspace app (CWA)](https://www.citrix.com/downloads/workspace-app/) and Virtual Delivery Agent (VDA) by default.</span></span> <span data-ttu-id="0405f-147">CWA 또는 VDA에 추가 구성 요소 또는 플러그 인을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-147">You don't need to install any additional components or plugins on CWA or the VDA.</span></span>

<span data-ttu-id="0405f-148">최신 서버 및 클라이언트 요구 사항은 [이 Citrix 웹 사이트](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-148">For the latest server and client requirements, see [this Citrix website](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).</span></span>

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a><span data-ttu-id="0405f-149">VMware Horizon 작업 영역 및 데스크톱 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0405f-149">VMware Horizon Workspace and Desktop requirements</span></span>

<span data-ttu-id="0405f-150">VMware Horizon은 하이브리드 클라우드에서 가상 데스크톱 및 앱을 안전하게 배달하기 위한 최신 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-150">VMware Horizon is a modern platform for secure delivery of virtual desktops and apps across the hybrid cloud.</span></span> <span data-ttu-id="0405f-151">훌륭한 최종 사용자 환경을 제공하도록 VMware Horizon은 Teams에 대한 미디어 최적화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-151">To offer a great end-user experience, VMware Horizon provides media optimization for Teams.</span></span> <span data-ttu-id="0405f-152">이 최적화는 가상 데스크톱 및 앱 전체의 전반적인 생산성을 향상하고 Teams를 사용하여 통화 및 모임 시 사용자 환경을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-152">This optimization improves overall productivity across virtual desktops and apps, and enhances user experience when calling and meeting using Teams.</span></span>

<span data-ttu-id="0405f-153">VMware 다운로드 페이지에서 [최신 버전의 VMware](https://my.vmware.com/web/vmware/downloads/#all_products) Horizon을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-153">You can download the latest version of VMware Horizon from the [VMware Downloads](https://my.vmware.com/web/vmware/downloads/#all_products) page.</span></span> <span data-ttu-id="0405f-154">필수 미디어 최적화 구성 요소는 기본적으로 Horizon 에이전트 및 Horizon 클라이언트의 일부로, Teams에 대한 최적화 기능을 사용하기 위해 추가 플러그 인을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-154">The required media optimization components are part of the Horizon Agent and Horizon Client by default and there's no need to install any additional plug-in to use the optimization feature for Teams.</span></span>

<span data-ttu-id="0405f-155">Teams에 대한 미디어 최적화를 구성하는 방법에 대한 최신 요구 사항 및 지침을 얻었다면 이 [VMware 웹 사이트 를 참조하세요.](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)</span><span class="sxs-lookup"><span data-stu-id="0405f-155">To get the latest requirements and instructions on how to configure media optimization for Teams, see [this VMware website](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).</span></span>

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a><span data-ttu-id="0405f-156">VDI에서 Teams 데스크톱 앱 설치 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="0405f-156">Install or update the Teams desktop app on VDI</span></span>

<span data-ttu-id="0405f-157">MSI 패키지를 사용하여 컴퓨터당 설치 또는 사용자당 설치를 사용하여 VDI용 Teams 데스크톱 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-157">You can deploy the Teams desktop app for VDI using a per-machine installation or per-user installation using the MSI package.</span></span> <span data-ttu-id="0405f-158">사용할 방법을 결정하려면 영구적 또는 비영구적 설정을 사용할지 여부와 조직의 관련 기능 요구에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-158">Deciding on which approach to use depends on whether you use a persistent or non-persistent setup and the associated functionality needs of your organization.</span></span>

<span data-ttu-id="0405f-159">전용 영구 설정의 경우 두 방법 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-159">For a dedicated persistent setup, either approach would work.</span></span> <span data-ttu-id="0405f-160">그러나 비영구적 설치의 경우 Teams는 효율적으로 작동하려면 컴퓨터당 설치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-160">However, for a non-persistent setup, Teams requires a per-machine installation in order to work efficiently.</span></span> <span data-ttu-id="0405f-161">영구적이지 않은 설정 [섹션을 참조하세요.](#non-persistent-setup)</span><span class="sxs-lookup"><span data-stu-id="0405f-161">See the [Non-persistent setup](#non-persistent-setup) section.</span></span>

<span data-ttu-id="0405f-162">컴퓨터당 설치를 통해 자동 업데이트를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-162">With per-machine installation, automatic updates is disabled.</span></span> <span data-ttu-id="0405f-163">즉, Teams 앱을 업데이트하려면 최신 버전으로 업데이트하려면 현재 버전을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-163">This means that to update the Teams app, you must uninstall the current version to update to a newer version.</span></span> <span data-ttu-id="0405f-164">사용자당 설치를 사용하면 자동 업데이트가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-164">With per-user installation, automatic updates is enabled.</span></span> <span data-ttu-id="0405f-165">대부분의 VDI 배포의 경우 컴퓨터당 설치를 사용하여 Teams를 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-165">For most VDI deployments, we recommend you deploy Teams using per-machine installation.</span></span>

<span data-ttu-id="0405f-166">최신 Teams 버전으로 업데이트하기 위해 제거 프로시저부터 시작하고 최신 Teams 버전 배포를 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-166">To update to the latest Teams version, start with the uninstall procedure followed by latest Teams version deployment.</span></span>

<span data-ttu-id="0405f-167">VDI 환경에서 Teams AV 최적화가 제대로 작동하려면 씬 클라이언트 엔드포인트가 인터넷에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-167">For Teams AV optimization in VDI environments to work properly, the thin client endpoint must have access to the internet.</span></span> <span data-ttu-id="0405f-168">씬 클라이언트 엔드포인트에서 인터넷 액세스를 사용할 수 없는 경우 최적화 시작이 성공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-168">If internet access isn't available at the thin client endpoint, optimization startup won't be successful.</span></span> <span data-ttu-id="0405f-169">즉, 사용자가 최적화되지 않은 미디어 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-169">This means that the user is in a non-optimized media state.</span></span>

#### <a name="dedicated-persistent-setup"></a><span data-ttu-id="0405f-170">전용 영구 설정</span><span class="sxs-lookup"><span data-stu-id="0405f-170">Dedicated persistent setup</span></span>

<span data-ttu-id="0405f-171">전용 영구 설정에서 사용자의 로컬 운영 체제 변경 내용은 사용자가 로그오프한 후에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-171">In a dedicated persistent setup, users' local operating system changes are retained after users log off.</span></span> <span data-ttu-id="0405f-172">영구 설치의 경우 Teams는 사용자당 및 컴퓨터당 설치를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-172">For persistent setup, Teams supports both per-user and per-machine installation.</span></span>

<span data-ttu-id="0405f-173">권장되는 최소 VM 구성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-173">The following is the recommended minimum VM configuration.</span></span>

|<span data-ttu-id="0405f-174">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0405f-174">Parameter</span></span>  |<span data-ttu-id="0405f-175">Workstation 운영 체제</span><span class="sxs-lookup"><span data-stu-id="0405f-175">Workstation operating system</span></span>  |<span data-ttu-id="0405f-176">서버 운영 체제</span><span class="sxs-lookup"><span data-stu-id="0405f-176">Server operating system</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="0405f-177">vCPU</span><span class="sxs-lookup"><span data-stu-id="0405f-177">vCPU</span></span>   |    <span data-ttu-id="0405f-178">코어 2개</span><span class="sxs-lookup"><span data-stu-id="0405f-178">2 cores</span></span>     |  <span data-ttu-id="0405f-179">4,6 또는 8</span><span class="sxs-lookup"><span data-stu-id="0405f-179">4,6, or 8</span></span><br><span data-ttu-id="0405f-180">기본 NUMA(비 균일하지 않은 메모리 액세스) 구성을 이해하고 이에 따라 VM을 구성하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-180">It's important to understand the underlying non-uniform memory access (NUMA) configuration and configure your VMs accordingly.</span></span>     |
|<span data-ttu-id="0405f-181">RAM</span><span class="sxs-lookup"><span data-stu-id="0405f-181">RAM</span></span>     |   <span data-ttu-id="0405f-182">4GB</span><span class="sxs-lookup"><span data-stu-id="0405f-182">4 GB</span></span>      | <span data-ttu-id="0405f-183">사용자당 512~1024MB</span><span class="sxs-lookup"><span data-stu-id="0405f-183">512 to 1024 MB per user</span></span>        |
|<span data-ttu-id="0405f-184">저장소</span><span class="sxs-lookup"><span data-stu-id="0405f-184">Storage</span></span>    | <span data-ttu-id="0405f-185">8GB</span><span class="sxs-lookup"><span data-stu-id="0405f-185">8 GB</span></span>        | <span data-ttu-id="0405f-186">40~60GB</span><span class="sxs-lookup"><span data-stu-id="0405f-186">40 to 60 GB</span></span>        |

#### <a name="non-persistent-setup"></a><span data-ttu-id="0405f-187">영구적이지 않은 설정</span><span class="sxs-lookup"><span data-stu-id="0405f-187">Non-persistent setup</span></span>

<span data-ttu-id="0405f-188">영구적이지 않은 설정에서 사용자의 로컬 운영 체제 변경 내용은 사용자가 로그오프한 후에 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-188">In a non-persistent setup, users' local operating system changes are not retained after users log off.</span></span> <span data-ttu-id="0405f-189">이러한 설정은 일반적으로 공유 다중 사용자 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-189">Such setups are commonly shared multi-user sessions.</span></span> <span data-ttu-id="0405f-190">VM 구성은 사용자 수 및 사용 가능한 물리적 상자 리소스에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-190">VM configuration varies based on the number of users and available physical box resources.</span></span>

<span data-ttu-id="0405f-191">영구적이지 않은 설정의 경우 Teams 데스크톱 앱을 황금 이미지에 컴퓨터당 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-191">For a non-persistent setup, the Teams desktop app must be installed per-machine to the golden image.</span></span> <span data-ttu-id="0405f-192">(자세한 내용은 [VDI에서 Teams 데스크톱](#install-or-update-the-teams-desktop-app-on-vdi) 앱 설치 또는 업데이트 섹션을 참조하세요.) 이렇게 하면 사용자 세션 중에 Teams 앱을 효율적으로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-192">(To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.) This ensures an efficient launch of the Teams app during a user session.</span></span>

<span data-ttu-id="0405f-193">비영구적 설정에서 Teams를 사용하려면 효율적인 Teams 런타임 데이터 동기화를 위해 프로필 캐싱 관리자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-193">Using Teams in a non-persistent setup also requires a profile-caching manager, for efficient Teams runtime data synchronization.</span></span> <span data-ttu-id="0405f-194">효율적인 데이터 동기화를 통해 사용자의 세션 중에 적절한 사용자별 정보(예: 사용자의 데이터, 프로필 또는 설정)가 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-194">Efficient data synchronization ensures that the appropriate user-specific information (such as a user's data, profile, or settings) is cached during the user's session.</span></span> <span data-ttu-id="0405f-195">다음 두 폴더의 데이터가 동기화된지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-195">Make sure data in these two folders are synched:</span></span><br>
- <span data-ttu-id="0405f-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache(%localAppdata%\Microsoft\IdentityCache)</span><span class="sxs-lookup"><span data-stu-id="0405f-196">C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)</span></span>
- <span data-ttu-id="0405f-197">C:\Users\username\AppData\Roaming\Microsoft\Teams(%appdata%\Microsoft\Teams)</span><span class="sxs-lookup"><span data-stu-id="0405f-197">C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)</span></span>

> [!NOTE]
> <span data-ttu-id="0405f-198">로밍 폴더(또는 폴더 리디렉션을 사용하는 경우 캐싱 관리자)는 Teams 앱에 애플리케이션을 실행하는 데 필요한 런타임 데이터 및 파일이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-198">A roaming folder (or, if you are using folder redirection, a caching manager) is required to ensure that the Teams app has the runtime data and files required to run the application.</span></span> <span data-ttu-id="0405f-199">이 문제는 네트워크 대기 시간 문제 또는 네트워크 문제의 완화를 위해 필요하며, 그렇지 않으면 애플리케이션 오류 및 사용할 수 없는 데이터 및 파일로 인해 환경이 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-199">This is necessary to mitigate network latency issues or network glitches, which would otherwise cause application errors and a slow experience due to unavailable data and files.</span></span>

<span data-ttu-id="0405f-200">다양한 캐싱 관리자 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-200">There are a variety of caching manager solutions available.</span></span> <span data-ttu-id="0405f-201">예를 들어 [FSLogix](/fslogix/overview).</span><span class="sxs-lookup"><span data-stu-id="0405f-201">For example, [FSLogix](/fslogix/overview).</span></span> <span data-ttu-id="0405f-202">특정 구성 지침은 캐싱 관리자 공급자에게 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-202">Consult your caching manager provider for specific configuration instructions.</span></span>

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a><span data-ttu-id="0405f-203">영구적이지 않은 설정에 대해 팀 캐시된 콘텐츠 제외 목록</span><span class="sxs-lookup"><span data-stu-id="0405f-203">Teams cached content exclusion list for non-persistent setup</span></span>

<span data-ttu-id="0405f-204">Teams 캐싱 폴더, %appdata%/Microsoft/Teams에서 다음을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-204">Exclude the following from the Teams caching folder, %appdata%/Microsoft/Teams.</span></span> <span data-ttu-id="0405f-205">이러한 항목을 제외하면 사용자 캐싱 크기를 줄여 비영구적 설정을 더욱 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-205">Excluding these items helps reduce the user caching size to further optimize your non-persistent setup.</span></span>

- <span data-ttu-id="0405f-206">.txt 파일</span><span class="sxs-lookup"><span data-stu-id="0405f-206">.txt files</span></span>
- <span data-ttu-id="0405f-207">미디어 스택 폴더</span><span class="sxs-lookup"><span data-stu-id="0405f-207">Media-stack folder</span></span>
- <span data-ttu-id="0405f-208">meeting-addin\Cache(%appdata%\Microsoft\Teams\meeting-addin\Cache)</span><span class="sxs-lookup"><span data-stu-id="0405f-208">meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)</span></span>

### <a name="microsoft-365-apps-for-enterprise-considerations"></a><span data-ttu-id="0405f-209">Microsoft 365 엔터프라이즈 고려 사항용 앱</span><span class="sxs-lookup"><span data-stu-id="0405f-209">Microsoft 365 Apps for enterprise considerations</span></span>

<span data-ttu-id="0405f-210">VDI에서 엔터프라이즈용 Microsoft 365 Apps를 사용하여 Teams를 배포할 때 다음을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-210">Consider the following when you deploy Teams with Microsoft 365 Apps for enterprise on VDI.</span></span>

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="0405f-211">엔터프라이즈용 Microsoft 365 Apps를 통해 Teams의 새 배포</span><span class="sxs-lookup"><span data-stu-id="0405f-211">New deployments of Teams through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="0405f-212">엔터프라이즈용 Microsoft 365 Apps를 통해 Teams를 배포하기 전에 먼저 컴퓨터당 설치를 사용하여 배포된 기존 Teams 앱을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-212">Before you deploy Teams through Microsoft 365 Apps for enterprise, you must first uninstall any pre-existing Teams apps if they were deployed using per-machine installation.</span></span>

<span data-ttu-id="0405f-213">엔터프라이즈용 Microsoft 365 Apps를 통한 팀은 사용자당 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-213">Teams through Microsoft 365 Apps for enterprise is installed per-user.</span></span> <span data-ttu-id="0405f-214">자세한 내용은 [VDI에서 Teams 데스크톱](#install-or-update-the-teams-desktop-app-on-vdi) 앱 설치 또는 업데이트 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-214">To learn more, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a><span data-ttu-id="0405f-215">엔터프라이즈 업데이트를 위한 Microsoft 365 Apps를 통한 팀 배포</span><span class="sxs-lookup"><span data-stu-id="0405f-215">Teams deployments through Microsoft 365 Apps for enterprise updates</span></span>

<span data-ttu-id="0405f-216">또한 Teams는 엔터프라이즈용 Microsoft 365 Apps의 기존 설치에도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-216">Teams is also being added to existing installations of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="0405f-217">엔터프라이즈용 Microsoft 365 Apps는 사용자당 Teams만 설치하기 때문에 [VDI에 Teams 데스크톱](#install-or-update-the-teams-desktop-app-on-vdi) 앱 설치 또는 업데이트 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-217">Since Microsoft 365 Apps for enterprise installs Teams per-user only, see the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span>

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="0405f-218">컴퓨터당 설치 및 엔터프라이즈용 Microsoft 365 Apps를 사용하는 Teams 사용</span><span class="sxs-lookup"><span data-stu-id="0405f-218">Using Teams with per-machine installation and Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="0405f-219">엔터프라이즈용 Microsoft 365 Apps는 Teams의 컴퓨터당 설치를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-219">Microsoft 365 Apps for enterprise doesn't support per-machine installations of Teams.</span></span> <span data-ttu-id="0405f-220">컴퓨터당 설치를 사용하려면 엔터프라이즈용 Microsoft 365 Apps에서 Teams를 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-220">To use per-machine installation, you must exclude Teams from Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="0405f-221">[VM에 Teams](#deploy-the-teams-desktop-app-to-the-vm) 데스크톱 앱 배포 및 [엔터프라이즈용 Microsoft 365 Apps](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) 섹션을 통해 Teams 배포를 제외하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-221">See the [Deploy the Teams desktop app to the VM](#deploy-the-teams-desktop-app-to-the-vm) and [How to exclude Teams deployment through Microsoft 365 Apps for enterprise](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.</span></span>

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="0405f-222">엔터프라이즈용 Microsoft 365 Apps를 통해 Teams 배포를 제외하는 방법</span><span class="sxs-lookup"><span data-stu-id="0405f-222">How to exclude Teams deployment through Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="0405f-223">Teams 및 Microsoft 365 Enterprise용 앱에 대한 자세한 내용은 [엔터프라이즈용 Microsoft 365 Apps의](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) 새 설치에서 Teams를 제외하는 방법 및 그룹 정책을 사용하여 Teams 설치를 [제어하는 방법을 참조하세요.](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="0405f-223">To learn more about Teams and Microsoft 365 Apps for enterprise, see [How to exclude Teams from new installations of Microsoft 365 Apps for enterprise](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) and [Use Group Policy to control the installation of Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).</span></span>

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a><span data-ttu-id="0405f-224">VM에 Teams 데스크톱 앱 배포</span><span class="sxs-lookup"><span data-stu-id="0405f-224">Deploy the Teams desktop app to the VM</span></span>

1. <span data-ttu-id="0405f-225">다음 링크 중 하나를 사용하여 VDI VM 운영 체제와 일치하는 Teams MSI 패키지를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-225">Download the Teams MSI package that matches your VDI VM operating system using one of the following links:</span></span>

    - [<span data-ttu-id="0405f-226">32비트 버전</span><span class="sxs-lookup"><span data-stu-id="0405f-226">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [<span data-ttu-id="0405f-227">64비트 버전</span><span class="sxs-lookup"><span data-stu-id="0405f-227">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > <span data-ttu-id="0405f-228">정부 클라우드의 경우 MSI 파일에 대한 다운로드 링크에 [대해 Microsoft 엔드포인트 구성 관리자를](msi-deployment.md) 사용하여 Microsoft Teams 설치를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-228">For government clouds, see [Install Microsoft Teams using Microsoft Endpoint Configuration Manager](msi-deployment.md) for the download links to the MSI files.</span></span>

    <span data-ttu-id="0405f-229">필요한 Teams 데스크톱 앱의 최소 버전은 버전 1.3.00.4461입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-229">The minimum version of the Teams desktop app that's required is version 1.3.00.4461.</span></span> <span data-ttu-id="0405f-230">(이전 버전에서는 PSTN 보류가 지원되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="0405f-230">(PSTN hold isn't supported in earlier versions.)</span></span>

2. <span data-ttu-id="0405f-231">다음 명령 중 하나를 실행하여 VDI VM에 MSI를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-231">Install the MSI to the VDI VM by running one of the following commands:</span></span>

    - <span data-ttu-id="0405f-232">사용자당 설치(기본값)</span><span class="sxs-lookup"><span data-stu-id="0405f-232">Per-user installation (default)</span></span>
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        <span data-ttu-id="0405f-233">이 프로세스는 %AppData% 사용자 폴더에 Teams를 설치하는 기본 설치입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-233">This process is the default installation, which installs Teams to the %AppData% user folder.</span></span> <span data-ttu-id="0405f-234">이 시점에서 골든 이미지 설정이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-234">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="0405f-235">팀이 비영구적 설치에서 사용자당 설치로 제대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-235">Teams won't work properly with per-user installation on a non-persistent setup.</span></span>

    - <span data-ttu-id="0405f-236">컴퓨터당 설치</span><span class="sxs-lookup"><span data-stu-id="0405f-236">Per-machine installation</span></span>

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        <span data-ttu-id="0405f-237">이 프로세스는 64비트 운영 체제의 프로그램 파일(x86) 폴더 및 32비트 운영 체제의 프로그램 파일 폴더에 Teams를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-237">This process installs Teams to the Program Files (x86) folder on a 64-bit operating system and to the Program Files folder on a 32-bit operating system.</span></span> <span data-ttu-id="0405f-238">이 시점에서 골든 이미지 설정이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-238">At this point, the golden image setup is complete.</span></span> <span data-ttu-id="0405f-239">비영구적 설정에 대해 컴퓨터당 Teams를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-239">Installing Teams per-machine is required for non-persistent setups.</span></span>

        <span data-ttu-id="0405f-240">다음 대화형 로그온 세션은 Teams를 시작하고 자격 증명을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-240">The next interactive logon session starts Teams and asks for credentials.</span></span>

        > [!NOTE]
        > <span data-ttu-id="0405f-241">또한 이러한 예제에서는 **ALLUSERS=1 매개 변수를** 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-241">These examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="0405f-242">이 매개 변수를 설정하면 Teams Machine-Wide 설치 관리자가 제어판의 프로그램 및 기능 및 앱에 & 모든 사용자에 대한 Windows 설정의 기능에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-242">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="0405f-243">그러면 모든 사용자가 관리자 자격 증명이 있는 경우 Teams를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-243">All users can then uninstall Teams if they have admin credentials.</span></span>
        <span data-ttu-id="0405f-244">**ALLUSERS=1과 ALLUSER=1의** **차이점을** 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-244">It's important to understand the difference between **ALLUSERS=1** and **ALLUSER=1**.</span></span> <span data-ttu-id="0405f-245">**ALLUSERS=1** 매개 변수는 VDI가 아닌 VDI 환경에서 사용할 수 **있으며, ALLUSER=1** 매개 변수는 VDI 환경에서만 사용하여 컴퓨터당 설치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-245">The **ALLUSERS=1** parameter can be used in non-VDI and VDI environments, while the **ALLUSER=1** parameter is used only in VDI environments to specify a per-machine installation.</span></span>

3. <span data-ttu-id="0405f-246">VDI VM에서 MSI를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-246">Uninstall the MSI from the VDI VM.</span></span> <span data-ttu-id="0405f-247">Teams를 제거하는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-247">There are two ways to uninstall Teams.</span></span>

    - <span data-ttu-id="0405f-248">PowerShell 스크립트: 이 [PowerShell](scripts/powershell-script-deployment-cleanup.md) 스크립트를 사용하여 Teams를 제거하고 사용자에 대한 Teams 폴더를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-248">PowerShell script: You can use [this PowerShell script](scripts/powershell-script-deployment-cleanup.md) to uninstall Teams and remove the Teams folder for a user.</span></span> <span data-ttu-id="0405f-249">Teams가 컴퓨터에 설치된 각 사용자 프로필에 대한 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-249">Run the script for each user profile in which Teams was installed on the computer.</span></span>
    - <span data-ttu-id="0405f-250">명령줄: 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-250">Command line: Run the following command.</span></span>
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      <span data-ttu-id="0405f-251">이 프로세스는 운영 체제 환경에 따라 프로그램 파일(x86) 폴더 또는 프로그램 파일 폴더에서 Teams를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-251">This process uninstalls Teams from the Program Files (x86) folder or Program Files folder, depending on the operating system environment.</span></span>

## <a name="teams-on-vdi-performance-considerations"></a><span data-ttu-id="0405f-252">VDI 성능 고려 사항의 팀</span><span class="sxs-lookup"><span data-stu-id="0405f-252">Teams on VDI performance considerations</span></span>

<span data-ttu-id="0405f-253">다양한 가상화된 설정 구성이 있습니다. 각각 최적화에 대한 포커스가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-253">There are a variety of virtualized setup configurations, each with a different focus for optimization.</span></span> <span data-ttu-id="0405f-254">예를 들어 구성은 사용자 밀도에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-254">For example, a configuration might focus on user density.</span></span> <span data-ttu-id="0405f-255">계획할 때 조직의 워크로드 요구에 따라 설정을 최적화하는 데 도움이 되는 다음을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-255">When planning, consider the following to help optimize your setup based on your organization's workload needs.</span></span>

- <span data-ttu-id="0405f-256">최소 요구 사항: 일부 워크로드에는 최소 요구 사항 이상인 리소스를 사용하여 설정이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-256">Minimum requirement: Some workloads might require a setup using resources that are above the minimum requirements.</span></span> <span data-ttu-id="0405f-257">예를 들어 더 많은 컴퓨팅 리소스를 요구하는 애플리케이션을 사용하는 개발자를 위한 워크로드입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-257">For example, workloads for developers who use applications that demand more computing resources.</span></span>
- <span data-ttu-id="0405f-258">종속성: Teams 데스크톱 앱 외부의 인프라, 워크로드 및 기타 환경 고려 사항에 대한 종속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-258">Dependencies: These include dependencies on infrastructure, workload, and other environmental considerations outside the Teams desktop app.</span></span>
- <span data-ttu-id="0405f-259">VDI에서 비활성화된 기능: Teams는 일시적인 CPU 사용률을 개선하는 데 도움이 될 수 있는 VDI에 대한 GPU 집약적 기능을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-259">Disabled features on VDI: Teams disables GPU-intensive features for VDI, which can help improve transient CPU utilization.</span></span> <span data-ttu-id="0405f-260">다음 기능은 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-260">The following features are disabled:</span></span>
    - <span data-ttu-id="0405f-261">Teams CSS 애니메이션</span><span class="sxs-lookup"><span data-stu-id="0405f-261">Teams CSS animation</span></span>
    - <span data-ttu-id="0405f-262">Giphy 자동 시작</span><span class="sxs-lookup"><span data-stu-id="0405f-262">Giphy auto-start</span></span>

## <a name="teams-on-vdi-with-calling-and-meetings"></a><span data-ttu-id="0405f-263">호출 및 모임이 있는 VDI의 팀</span><span class="sxs-lookup"><span data-stu-id="0405f-263">Teams on VDI with calling and meetings</span></span>

<span data-ttu-id="0405f-264">채팅 및 공동 작업 외에도 지원되는 가상화 공급자 플랫폼에서 호출 및 모임이 있는 VDI의 Teams를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-264">In addition to chat and collaboration, Teams on VDI with calling and meetings is available with supported virtualization provider platforms.</span></span> <span data-ttu-id="0405f-265">지원되는 기능은 WebRTC 미디어 스택 및 가상화 공급자 구현을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-265">Supported features are based on the WebRTC media stack and virtualization provider implementation.</span></span> <span data-ttu-id="0405f-266">다음 다이어그램에서는 아키텍처에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-266">The following diagram provides an overview of the architecture.</span></span>

![VDI 아키텍처의 Teams를 보여주는 다이어그램](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> <span data-ttu-id="0405f-268">현재 VDI에서 AV 최적화 없이 Teams를 실행하고 최적화를 위해 아직 지원되지 않는 기능을 사용하는 경우(예: 앱 공유 시 제공 및 제어) 가상화 공급자 정책을 설정하여 Teams 리디렉션을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-268">If you currently run Teams without AV optimization in VDI and you use features that are not supported yet for optimization (such as Give and take control when app sharing), you have to set virtualization provider policies to turn off Teams redirection.</span></span> <span data-ttu-id="0405f-269">즉, Teams 미디어 세션이 최적화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-269">This means that Teams media sessions won't be optimized.</span></span> <span data-ttu-id="0405f-270">Teams 리디렉션을 해제하는 정책을 설정하는 방법에 대한 단계는 가상화 공급자에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-270">For steps on how to set policies to turn off Teams redirection, contact your virtualization provider.</span></span>

### <a name="network-requirements"></a><span data-ttu-id="0405f-271">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0405f-271">Network requirements</span></span>

<span data-ttu-id="0405f-272">환경을 평가하여 전체 클라우드 음성 및 비디오 배포에 영향을 줄 수 있는 위험 및 요구 사항을 식별하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-272">We recommend that you evaluate your environment to identify any risks and requirements that can influence your overall cloud voice and video deployment.</span></span> <span data-ttu-id="0405f-273">비즈니스용 [Skype 네트워크 평가](https://www.microsoft.com/download/details.aspx?id=53885) 도구를 사용하여 네트워크가 Teams에 대한 준비가 됐는지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-273">Use the [Skype for Business Network Assessment Tool](https://www.microsoft.com/download/details.aspx?id=53885) to test whether your network is ready for Teams.</span></span>

<span data-ttu-id="0405f-274">Teams용 네트워크를 준비하는 방법에 대한 자세한 내용은 Teams에 대한 조직의 [네트워크 준비를 참조합니다.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="0405f-274">To learn more about how to prepare your network for Teams, see [Prepare your organization's network for Teams](prepare-network.md).</span></span>

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a><span data-ttu-id="0405f-275">VDI의 비즈니스용 Skype에서 VDI의 Teams로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="0405f-275">Migrate from Skype for Business on VDI to Teams on VDI</span></span>

<span data-ttu-id="0405f-276">VDI의 비즈니스용 Skype에서 VDI의 Teams로 마이그레이션하는 경우 두 애플리케이션 간의 차이점 외에도 VDI가 구현될 때 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-276">If you're migrating from Skype for Business on VDI to Teams on VDI, besides the differences between the two applications, there are some differences when VDI is also implemented.</span></span> <span data-ttu-id="0405f-277">비즈니스용 Skype VDI에 있는 Teams VDI에서 현재 지원되지 않는 일부 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-277">Some capabilities that aren't currently supported in Teams VDI that are in Skype for Business VDI are as follows:</span></span>

- <span data-ttu-id="0405f-278">VDI에서 일부 AV 기능을 사용하지 않도록 설정하는 플랫폼당 정책</span><span class="sxs-lookup"><span data-stu-id="0405f-278">Per-platform policy to disable some AV features in VDI</span></span>
- <span data-ttu-id="0405f-279">앱 공유 시 제어권 제공 및 제어</span><span class="sxs-lookup"><span data-stu-id="0405f-279">Give and take control when app sharing</span></span>
- <span data-ttu-id="0405f-280">오디오가 없는 채팅에서 화면 공유</span><span class="sxs-lookup"><span data-stu-id="0405f-280">Screen share from chat without audio</span></span>
- <span data-ttu-id="0405f-281">동시 비디오 및 화면 공유 보내기 및 수신</span><span class="sxs-lookup"><span data-stu-id="0405f-281">Simultaneous video and screen sharing send and receive</span></span>

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a><span data-ttu-id="0405f-282">VDI용 Teams 데스크톱 앱과 Chrome 브라우저의 팀</span><span class="sxs-lookup"><span data-stu-id="0405f-282">Teams on Chrome browser versus Teams desktop app for VDI</span></span>

<span data-ttu-id="0405f-283">Chrome 브라우저의 팀은 AV 최적화를 사용하여 VDI용 Teams 데스크톱 앱에 대한 대체를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-283">Teams on Chrome browser doesn't provide a replacement for the Teams desktop app for VDI with AV optimization.</span></span> <span data-ttu-id="0405f-284">채팅 및 공동 작업 환경은 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-284">The chat and collaboration experience works as expected.</span></span> <span data-ttu-id="0405f-285">미디어가 필요한 경우 Chrome 브라우저에서 사용자 기대를 충족하지 않을 수 있는 몇 가지 환경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-285">When media is needed, there are some experiences that might not meet user expectations on the Chrome browser:</span></span>

- <span data-ttu-id="0405f-286">오디오 및 비디오 스트리밍 환경이 최적화되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-286">The audio and video streaming experience might not be optimal.</span></span> <span data-ttu-id="0405f-287">사용자가 지연되거나 품질이 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-287">Users might experiences delays or reduced quality.</span></span>
- <span data-ttu-id="0405f-288">브라우저 설정에서 디바이스 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-288">Device settings aren't available in browser settings.</span></span>
- <span data-ttu-id="0405f-289">디바이스 관리는 브라우저를 통해 처리하며 브라우저 사이트 설정에서 여러 설정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-289">Device management is handled through the browser and requires multiple settings in browser site settings.</span></span>
- <span data-ttu-id="0405f-290">Windows 디바이스 관리에서 디바이스 설정을 설정해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-290">Device settings might also need to be set in Windows device management.</span></span>

## <a name="teams-on-vdi-with-chat-and-collaboration"></a><span data-ttu-id="0405f-291">채팅 및 공동 작업을 통해 VDI의 팀</span><span class="sxs-lookup"><span data-stu-id="0405f-291">Teams on VDI with chat and collaboration</span></span>

<span data-ttu-id="0405f-292">조직에서 Teams에서 채팅 및 공동 작업 기능만 사용하려는 경우 Teams에서 통화 및 모임 기능을 해제하도록 사용자 수준 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-292">If your organization wants to only use chat and collaboration features in Teams, you can set user-level policies to turn off calling and meeting functionality in Teams.</span></span> 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a><span data-ttu-id="0405f-293">통화 및 모임 기능을 해제하기 위한 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0405f-293">Set policies to turn off calling and meeting functionality</span></span>

<span data-ttu-id="0405f-294">Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-294">You can set policies by using the Microsoft Teams admin center or PowerShell.</span></span> <span data-ttu-id="0405f-295">정책 변경이 전파하는 데 몇 시간(몇 시간)이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-295">It might take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="0405f-296">특정 계정에 대한 변경 내용이 즉시 표시되지 않는 경우 몇 시간 후에 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-296">If you don't see changes for a given account immediately, try again in a few hours.</span></span>

<span data-ttu-id="0405f-297">[**호출 경찰:**](teams-calling-policy.md)Teams에는 모든 호출 기능이 해제된 기본 제공 DisallowCalling 호출 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-297">[**Calling polices**](teams-calling-policy.md): Teams includes the built-in DisallowCalling calling policy, in which all calling features are turned off.</span></span> <span data-ttu-id="0405f-298">가상화된 환경에서 Teams를 사용하는 조직의 모든 사용자에게 DisallowCalling 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-298">Assign the DisallowCalling policy to all users in your organization who use Teams in a virtualized environment.</span></span>

<span data-ttu-id="0405f-299">[**모임 정책**](meeting-policies-in-teams.md): Teams에는 모든 모임 기능이 해제된 기본 제공 AllOff 모임 정책이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-299">[**Meeting policies**](meeting-policies-in-teams.md): Teams includes the built-in AllOff meeting policy, in which all meeting features are turned off.</span></span> <span data-ttu-id="0405f-300">가상화된 환경에서 Teams를 사용하는 조직의 모든 사용자에게 AllOff 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-300">Assign the AllOff policy to all users in your organization who use Teams in a virtualized environment.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0405f-301">Microsoft Teams 관리 센터를 사용하여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="0405f-301">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="0405f-302">DisallowCalling 호출 정책 및 AllOff 모임 정책을 사용자에게 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="0405f-302">To assign the DisallowCalling calling policy and the AllOff meeting policy to a user:</span></span>

1. <span data-ttu-id="0405f-303">Microsoft Teams 관리 센터의 왼쪽 탐색에서 사용자로 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-303">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="0405f-304">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-304">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="0405f-305">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-305">Do the following:</span></span>
    1.  <span data-ttu-id="0405f-306">통화 **정책에서** **를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-306">Under **Calling policy**, click **DisallowCalling**.</span></span>
    2.  <span data-ttu-id="0405f-307">모임 **정책에서** **AllOff 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-307">Under **Meeting policy**, click **AllOff**.</span></span>
4. <span data-ttu-id="0405f-308">적용 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-308">Click **Apply**.</span></span>

<span data-ttu-id="0405f-309">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-309">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="0405f-310">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-310">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="0405f-311">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-311">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="0405f-312">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-312">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="0405f-313">**설정 편집** 을 클릭하고 원하는 대로 변경한 다음, **적용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-313">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="0405f-314">또는 다음을 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-314">Or, you can also do the following:</span></span>

1. <span data-ttu-id="0405f-315">Microsoft Teams 관리 센터의 왼쪽 탐색에서 할당할 정책으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-315">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="0405f-316">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-316">For example:</span></span>
    - <span data-ttu-id="0405f-317">음성 통화  >  **정책으로 이동한** **다음, DisallowCalling 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-317">Go to **Voice** > **Calling policies**, and then click **DisallowCalling**.</span></span>
    - <span data-ttu-id="0405f-318">모임 모임 **정책으로**  >  이동한 다음 **AllOff 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-318">Go to **Meetings** > **Meeting policies**, and then click **AllOff**.</span></span>
2. <span data-ttu-id="0405f-319">**사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-319">Select **Manage users**.</span></span>
3. <span data-ttu-id="0405f-320">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-320">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="0405f-321">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-321">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="0405f-322">사용자 추가가 완료되면 저장 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-322">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="0405f-323">PowerShell을 사용하여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="0405f-323">Assign policies using PowerShell</span></span>

<span data-ttu-id="0405f-324">다음 예제에서는 [Grant-CsTeamsCallingPolicy를](/powershell/module/skype/grant-csteamscallingpolicy) 사용하여 사용자에게 DisallowCalling 호출 정책을 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-324">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the DisallowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

<span data-ttu-id="0405f-325">PowerShell을 사용하여 통화 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-325">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="0405f-326">다음 예제에서는 [Grant-CsTeamsMeetingPolicy를](/powershell/module/skype/grant-csteamsmeetingpolicy) 사용하여 AllOff 모임 정책을 사용자에게 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-326">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOff meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

<span data-ttu-id="0405f-327">PowerShell을 사용하여 모임 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-327">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a><span data-ttu-id="0405f-328">채팅 및 공동 작업으로 VDI의 Teams 마이그레이션을 통해 호출 및 모임을 사용하여 Teams를 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-328">Migrate Teams on VDI with chat and collaboration to optimize Teams with calling and meetings</span></span>

<span data-ttu-id="0405f-329">채팅 및 공동 작업을 사용하여 VDI에 Teams를 구현한 경우 사용자 수준 정책을 설정하여 통화 및 모임 기능을 해제하고 AV 최적화를 사용하여 Teams로 마이그레이션하는 경우 VDI 사용자에 대한 해당 Teams에 대한 호출 및 모임 기능을 켜기 위한 정책을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-329">If you have an existing implementation of Teams on VDI with chat and collaboration in which you had set user-level policies to turn off calling and meeting functionality, and you're migrating to Teams with AV optimization, you must set policies to turn on calling and meeting functionality for those Teams on VDI users.</span></span>

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a><span data-ttu-id="0405f-330">통화 및 모임 기능을 켜기 위한 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0405f-330">Set policies to turn on calling and meeting functionality</span></span>

<span data-ttu-id="0405f-331">Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 사용자에게 통화 및 모임 정책을 설정하고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-331">You can use the Microsoft Teams admin center or PowerShell to set and assign calling and meeting policies to your users.</span></span> <span data-ttu-id="0405f-332">정책 변경이 전파하는 데 다소 시간이 걸릴 수 있습니다(몇 시간).</span><span class="sxs-lookup"><span data-stu-id="0405f-332">It can take some time (a few hours) for policy changes to propagate.</span></span> <span data-ttu-id="0405f-333">특정 계정에 대한 변경 내용이 즉시 표시되지 않는 경우 몇 시간 후에 다시 시도하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-333">If you don't see changes for a given account immediately, try again after a few hours.</span></span>

<span data-ttu-id="0405f-334">[**호출 경찰**](teams-calling-policy.md): Teams의 통화 정책은 사용자가 사용할 수 있는 호출 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-334">[**Calling polices**](teams-calling-policy.md): Calling policies in Teams control which calling features are available to users.</span></span> <span data-ttu-id="0405f-335">팀에는 모든 호출 기능이 켜져 있는 기본 제공 AllowCalling 호출 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-335">Teams includes the built-in AllowCalling calling policy, in which all calling features are turned on.</span></span> <span data-ttu-id="0405f-336">모든 호출 기능을 켜기 위해 AllowCalling 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-336">To turn on all calling features, assign the AllowCalling policy.</span></span> <span data-ttu-id="0405f-337">또는 사용자 지정 호출 정책을 만들어 원하는 호출 기능을 켜고 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-337">Or, create a custom calling policy to turn on the calling features that you want and assign it to users.</span></span> 

<span data-ttu-id="0405f-338">[**모임 정책**](meeting-policies-in-teams.md): Teams의 모임 정책은 사용자가 만들 수 있는 모임 유형과 조직의 사용자가 예약한 모임 참가자에 사용할 수 있는 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-338">[**Meeting policies**](meeting-policies-in-teams.md): Meeting policies in Teams control the types of meetings that users can create and the features that are available to meeting participants that are scheduled by users in your organization.</span></span> <span data-ttu-id="0405f-339">팀에는 모든 모임 기능이 켜져 있는 기본 제공 AllOn 모임 정책이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-339">Teams includes the built-in AllOn meeting policy, in which all meeting features are turned on.</span></span> <span data-ttu-id="0405f-340">모든 모임 기능을 켜기 위해 AllOn 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-340">To turn on all meeting features, assign the AllOn policy.</span></span> <span data-ttu-id="0405f-341">또는 사용자 지정 모임 정책을 만들어 원하는 모임 기능을 켜고 사용자를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-341">Or, create a custom meeting policy to turn on the meeting features that you want and assign it users.</span></span>

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0405f-342">Microsoft Teams 관리 센터를 사용하여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="0405f-342">Assign policies using the Microsoft Teams admin center</span></span>

<span data-ttu-id="0405f-343">AllowCalling 호출 정책 및 AllOn 모임 정책을 사용자에게 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="0405f-343">To assign the AllowCalling calling policy and the AllOn meeting policy to a user:</span></span>

1. <span data-ttu-id="0405f-344">Microsoft Teams 관리 센터의 왼쪽 탐색에서 사용자로 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-344">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="0405f-345">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-345">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="0405f-346">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-346">Do the following:</span></span>
    1.  <span data-ttu-id="0405f-347">통화 **정책에서** 허용 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-347">Under **Calling policy**, click **AllowCalling**.</span></span>
    2.  <span data-ttu-id="0405f-348">모임 **정책에서** **AllOn 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-348">Under **Meeting policy**, click **AllOn**.</span></span>
4. <span data-ttu-id="0405f-349">적용 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-349">Click **Apply**.</span></span>

<span data-ttu-id="0405f-350">한 번에 여러 사용자에게 정책을 할당하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-350">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="0405f-351">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자** 로 이동한 다음, 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-351">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="0405f-352">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-352">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="0405f-353">모든 사용자를 선택하려면 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-353">To select all users, click the **&#x2713;** (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="0405f-354">**설정 편집** 을 클릭하고 원하는 대로 변경한 다음, **적용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-354">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="0405f-355">또는 다음을 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-355">Or, you can also do the following:</span></span>

1. <span data-ttu-id="0405f-356">Microsoft Teams 관리 센터의 왼쪽 탐색에서 할당할 정책으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="0405f-356">In the left navigation of the Microsoft Teams admin center, go to the policy you want to assign.</span></span> <span data-ttu-id="0405f-357">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-357">For example:</span></span>
    - <span data-ttu-id="0405f-358">음성 통화  >  **정책으로 이동한** 다음 **허용 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-358">Go to **Voice** > **Calling policies**, and then click **AllowCalling**.</span></span>
    - <span data-ttu-id="0405f-359">모임 **모임 정책으로**  >  이동한 다음 **AllOn 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-359">Go to **Meetings** > **Meeting policies**, and then click **AllOn**.</span></span>
2. <span data-ttu-id="0405f-360">**사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-360">Select **Manage users**.</span></span>
3. <span data-ttu-id="0405f-361">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-361">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="0405f-362">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-362">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="0405f-363">사용자 추가가 완료되면 저장 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-363">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-policies-using-powershell"></a><span data-ttu-id="0405f-364">PowerShell을 사용하여 정책 할당</span><span class="sxs-lookup"><span data-stu-id="0405f-364">Assign policies using PowerShell</span></span>

<span data-ttu-id="0405f-365">다음 예제에서는 [Grant-CsTeamsCallingPolicy를](/powershell/module/skype/grant-csteamscallingpolicy) 사용하여 사용자에게 AllowCalling 호출 정책을 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-365">The following example shows how to use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) to assign the AllowCalling calling policy to a user.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

<span data-ttu-id="0405f-366">PowerShell을 사용하여 통화 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-366">To learn more about using PowerShell to manage calling policies, see [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).</span></span>

<span data-ttu-id="0405f-367">다음 예제에서는 [Grant-CsTeamsMeetingPolicy를](/powershell/module/skype/grant-csteamsmeetingpolicy) 사용하여 AllOn 모임 정책을 사용자에게 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-367">The following example shows how to use the [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) to assign the AllOn meeting policy to a user.</span></span>

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

<span data-ttu-id="0405f-368">PowerShell을 사용하여 모임 정책을 관리하는 데 대한 자세한 내용은 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-368">To learn more about using PowerShell to manage meeting policies, see [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

## <a name="control-fallback-mode-in-teams"></a><span data-ttu-id="0405f-369">Teams에서 폴백 모드 제어</span><span class="sxs-lookup"><span data-stu-id="0405f-369">Control fallback mode in Teams</span></span>

<span data-ttu-id="0405f-370">지원되지 않는 엔드포인트에서 사용자가 연결하면 사용자가 AV가 최적화되지 않은 폴백 모드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-370">When users connect from an unsupported endpoint, the users are in fallback mode, in which AV isn't optimized.</span></span> <span data-ttu-id="0405f-371">다음 레지스트리 DWORD 값 중 하나를 설정하여 폴백 모드를 사용하지 않도록 설정하거나 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-371">You can disable or enable fallback mode by setting one of the following registry DWORD values:</span></span>

- <span data-ttu-id="0405f-372">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="0405f-372">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback</span></span>
- <span data-ttu-id="0405f-373">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span><span class="sxs-lookup"><span data-stu-id="0405f-373">HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback</span></span>

<span data-ttu-id="0405f-374">폴백 모드를 사용하지 않도록 설정하고 값을 **1로 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-374">To disable fallback mode, set the value to **1**.</span></span> <span data-ttu-id="0405f-375">오디오만 사용하도록 설정하려면 값을 **2로 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="0405f-375">To enable audio only, set the value to **2**.</span></span> <span data-ttu-id="0405f-376">값이 존재하지 않는 경우 또는 **0(0)으로** 설정되어 있는 경우 폴백 모드가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-376">If the value isn't present or is set to **0** (zero), fallback mode is enabled.</span></span>

<span data-ttu-id="0405f-377">이 기능은 Teams 버전 1.3.00.13565 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-377">This feature is available in Teams version 1.3.00.13565 and later.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="0405f-378">알려진 문제 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="0405f-378">Known issues and limitations</span></span>

### <a name="client-deployment-installation-and-setup"></a><span data-ttu-id="0405f-379">클라이언트 배포, 설치 및 설치</span><span class="sxs-lookup"><span data-stu-id="0405f-379">Client deployment, installation, and setup</span></span>

- <span data-ttu-id="0405f-380">컴퓨터당 설치를 통해 VDI의 Teams는 비 VDI Teams 클라이언트가 있는 방식으로 자동으로 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-380">With per-machine installation, Teams on VDI isn't automatically updated in the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="0405f-381">VDI의 Teams 데스크톱 앱 설치 또는 업데이트 섹션에 설명된 바와 같이 [새 MSI를](#install-or-update-the-teams-desktop-app-on-vdi) 설치하여 VM 이미지를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-381">You have to update the VM image by installing a new MSI as described in the [Install or update the Teams desktop app on VDI](#install-or-update-the-teams-desktop-app-on-vdi) section.</span></span> <span data-ttu-id="0405f-382">최신 버전으로 업데이트하려면 현재 버전을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-382">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="0405f-383">팀은 사용자당 또는 컴퓨터당 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-383">Teams should be deployed either per user or per machine.</span></span> <span data-ttu-id="0405f-384">사용자당 및 컴퓨터당 동시에 대한 Teams 배포는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-384">Deployment of Teams for concurrent per user and per machine is not supported.</span></span> <span data-ttu-id="0405f-385">컴퓨터당 또는 사용자당을 이러한 모드 중 하나로 마이그레이션하려면 제거 프로시저를 따라 두 모드로 다시 재배포합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-385">To migrate from either per machine or per user to one of these modes, follow the uninstall procedure and redeploy to either mode.</span></span>
- <span data-ttu-id="0405f-386">Windows Virtual Desktop 및 VMware는 현재 MacOS 및 Linux 기반 클라이언트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-386">Windows Virtual Desktop and VMware don't support MacOS and Linux-based clients at this time.</span></span>
- <span data-ttu-id="0405f-387">Citrix는 현재 MacOs 클라이언트를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-387">Citrix doesn't support MacOs clients at this time.</span></span>
- <span data-ttu-id="0405f-388">Citrix는 엔드포인트에 정의된 명시적 HTTP proxies 사용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-388">Citrix doesn't support the use of explicit HTTP proxies defined on an endpoint.</span></span>

### <a name="calling-and-meetings"></a><span data-ttu-id="0405f-389">통화 및 모임</span><span class="sxs-lookup"><span data-stu-id="0405f-389">Calling and meetings</span></span>

<span data-ttu-id="0405f-390">다음 호출 및 모임 기능은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-390">The following calling and meeting features are not supported:</span></span>

- <span data-ttu-id="0405f-391">새 모임 환경 또는 새 모임 환경과 함께 제공된 기능과 같은 모든 다중 창 기능</span><span class="sxs-lookup"><span data-stu-id="0405f-391">Any multi-window functionality like the new meeting experiences or any functionality that comes with the new meeting experience</span></span>
- <span data-ttu-id="0405f-392">향상된 응급 서비스</span><span class="sxs-lookup"><span data-stu-id="0405f-392">Enhanced emergency services</span></span>
- <span data-ttu-id="0405f-393">Teams 앱과 디바이스 간의 HID 단추 및 LED 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0405f-393">HID buttons and LED controls between the Teams app and devices</span></span>
- <span data-ttu-id="0405f-394">배경 흐림 및 효과</span><span class="sxs-lookup"><span data-stu-id="0405f-394">Background blur and effects</span></span>
- <span data-ttu-id="0405f-395">브로드캐스트 및 라이브 이벤트 생산자 및 발표자 역할</span><span class="sxs-lookup"><span data-stu-id="0405f-395">Broadcast and live event producer and presenter roles</span></span>
- <span data-ttu-id="0405f-396">Location-Based(LBR)</span><span class="sxs-lookup"><span data-stu-id="0405f-396">Location-Based Routing (LBR)</span></span>
- <span data-ttu-id="0405f-397">통화 공원</span><span class="sxs-lookup"><span data-stu-id="0405f-397">Call park</span></span>
- <span data-ttu-id="0405f-398">통화 큐</span><span class="sxs-lookup"><span data-stu-id="0405f-398">Call queue</span></span>
- <span data-ttu-id="0405f-399">공유 시스템 오디오/컴퓨터 소리</span><span class="sxs-lookup"><span data-stu-id="0405f-399">Shared system audio/computer sound</span></span>
- <span data-ttu-id="0405f-400">직접 라우팅을 위한 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="0405f-400">Media bypass for Direct Routing</span></span>

> [!NOTE]
> <span data-ttu-id="0405f-401">현재 VDI가 아닌 환경에서만 사용할 수 있는 호출 및 모임 기능을 추가하는 작업을 진행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-401">We're working on adding calling and meeting features that are currently only available in non-VDI environments.</span></span> <span data-ttu-id="0405f-402">여기에는 품질에 대한 더 많은 관리 제어, 추가 화면 공유 시나리오 및 최근에 Teams에 추가된 고급 기능이 포함되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-402">These might include more admin control over quality, additional screen sharing scenarios, and advanced features recently added to Teams.</span></span> <span data-ttu-id="0405f-403">예정된 기능에 대한 자세한 내용은 Teams 담당자에게 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-403">Contact your Teams representative to learn more about upcoming features.</span></span>

<span data-ttu-id="0405f-404">다음은 호출 및 모임에 대한 알려진 문제 및 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-404">The following are known issues and limitations for calling and meetings:</span></span>

- <span data-ttu-id="0405f-405">비즈니스용 Skype와의 상호 연동성은 오디오 통화로 제한됩니다. 비디오 모달리티가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-405">Interoperability with Skype for Business is limited to audio calls; there is no video modality.</span></span>
- <span data-ttu-id="0405f-406">모임 또는 그룹 통화에서 들어오는 단일 비디오 스트림만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-406">Only a single incoming video stream is supported in meetings or group calls.</span></span> <span data-ttu-id="0405f-407">여러 사용자가 비디오를 보낼 때 주된 스피커의 비디오만 주어진 시간으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-407">When multiple people send video, only the dominant speaker's video is shown at any given time.</span></span>
- <span data-ttu-id="0405f-408">수신 및 발신 비디오 스트림 해상도는 720p 해상도로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-408">Incoming and outgoing video stream resolution is limited to 720p resolution.</span></span> <span data-ttu-id="0405f-409">WebRTC 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-409">This is a WebRTC limitation.</span></span>
- <span data-ttu-id="0405f-410">들어오는 카메라 또는 화면 공유 스트림에서 하나의 비디오 스트림만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-410">Only one video stream from an incoming camera or screen share stream is supported.</span></span> <span data-ttu-id="0405f-411">들어오는 화면 공유가 있는 경우 주된 스피커의 비디오 대신 화면 공유가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-411">When there's an incoming screen share, that screen share is shown, instead of the video of the dominant speaker.</span></span>
- <span data-ttu-id="0405f-412">팀은 사용자가 선택한 마지막 오디오 디바이스(디바이스 연결이 끊어진 경우)를 사용하도록 전환하지 않은 다음 다시 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-412">Teams doesn't switch to use the last audio device that a user selected, if the device is disconnected, and then reconnected.</span></span>
- <span data-ttu-id="0405f-413">외출 화면 공유:</span><span class="sxs-lookup"><span data-stu-id="0405f-413">Outgoing screen sharing:</span></span>
    - <span data-ttu-id="0405f-414">애플리케이션 공유는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-414">Application sharing is not supported.</span></span>
- <span data-ttu-id="0405f-415">제어권 및 제어권:</span><span class="sxs-lookup"><span data-stu-id="0405f-415">Give control and take control:</span></span>
    - <span data-ttu-id="0405f-416">화면 공유 또는 애플리케이션 공유 세션 중에 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-416">Not supported during a screen sharing or application sharing session.</span></span>
    - <span data-ttu-id="0405f-417">PowerPoint 공유 세션 중에 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-417">Supported during a PowerPoint sharing session.</span></span>
- <span data-ttu-id="0405f-418">Citrix 전용 제한 사항</span><span class="sxs-lookup"><span data-stu-id="0405f-418">Citrix-only limitations</span></span>
    - <span data-ttu-id="0405f-419">다중 모니터 설정에서 화면 공유 시 주 모니터만 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-419">When screen sharing in a multi-monitor setup, only the main monitor is shared.</span></span>
    - <span data-ttu-id="0405f-420">CWA의 높은 DPI 크기 조정은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-420">High DPI scaling on CWA is not supported.</span></span>

<span data-ttu-id="0405f-421">VDI와 관련이 없는 Teams 알려진 문제의 경우 조직의 [지원 팀 을 참조합니다.](/MicrosoftTeams/troubleshoot/teams-welcome)</span><span class="sxs-lookup"><span data-stu-id="0405f-421">For Teams known issues that aren't related to VDI, see [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0405f-422">문제 해결</span><span class="sxs-lookup"><span data-stu-id="0405f-422">Troubleshooting</span></span>

### <a name="troubleshoot-citrix-components"></a><span data-ttu-id="0405f-423">Citrix 구성 요소 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0405f-423">Troubleshoot Citrix components</span></span>

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a><span data-ttu-id="0405f-424">팀이 충돌하거나 Teams 로그인 화면이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-424">Teams crashes or the Teams sign in screen is blank</span></span>

<span data-ttu-id="0405f-425">Citrix VDA 버전 1906 및 1909에 알려진 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-425">This is a known issue with Citrix VDA versions 1906 and 1909.</span></span> <span data-ttu-id="0405f-426">이 문제를 해결하기 위해 다음 레지스트리 DWORD 값을 추가하고 204(hexadecimal)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-426">To work around this issue, add the following registry DWORD value, and set it to 204 (hexadecimal).</span></span>

<span data-ttu-id="0405f-427">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span><span class="sxs-lookup"><span data-stu-id="0405f-427">HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe</span></span>

<span data-ttu-id="0405f-428">그런 다음 VDA를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0405f-428">Then, restart VDA.</span></span> <span data-ttu-id="0405f-429">자세한 내용은 Teams에 대한 HDX 최적화 문제 해결 이 Citrix 지원 문서를 [참조하세요.](https://support.citrix.com/article/CTX253754)</span><span class="sxs-lookup"><span data-stu-id="0405f-429">To learn more, see this Citrix support article, [Troubleshooting HDX optimization for Teams](https://support.citrix.com/article/CTX253754).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0405f-430">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0405f-430">Related topics</span></span>

- [<span data-ttu-id="0405f-431">MSI를 사용하여 Microsoft Teams 설치</span><span class="sxs-lookup"><span data-stu-id="0405f-431">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
- [<span data-ttu-id="0405f-432">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="0405f-432">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="0405f-433">Windows Virtual Desktop에서 Microsoft Teams 사용</span><span class="sxs-lookup"><span data-stu-id="0405f-433">Use Microsoft Teams on Windows Virtual desktop</span></span>](/azure/virtual-desktop/teams-on-wvd)