---
title: VDI 환경의 비즈니스용 Skype 계획
author: cichur
ms.author: v-cichur
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 이 항목에서는 원격 가상 데스크톱에 연결하는 동안 비즈니스용 Skype를 사용할 계획 고려 사항을 논의합니다.
ms.openlocfilehash: 66fe9dd0be2dd079597837b8d25c29b3f047b0c6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816108"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a><span data-ttu-id="4e31b-103">VDI 환경의 비즈니스용 Skype 계획</span><span class="sxs-lookup"><span data-stu-id="4e31b-103">Plan for Skype for Business in VDI environments</span></span>
 
<span data-ttu-id="4e31b-104">이 항목에서는 원격 가상 데스크톱에 연결하는 동안 비즈니스용 Skype를 사용할 계획 고려 사항을 논의합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-104">This topic discusses planning considerations for using Skype for Business while connecting to a remote virtual desktop.</span></span> 
  
<span data-ttu-id="4e31b-105">보안 및 규정 준수 문제가 특히 중요한 일부 조직에서는 VDI(가상 데스크톱 인프라) 환경이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-105">A Virtual Desktop Infrastructure (VDI) environment is used in some organizations where security and compliance issues are especially sensitive.</span></span> <span data-ttu-id="4e31b-106">사용자는 원격 데스크톱 서비스 또는 유사한 원격 연결을 사용하여 모든 데스크톱 응용 프로그램 및 파일을 사용하여 가상 데스크톱에서 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-106">Their users do their work on a virtual desktop with all their desktop applications and files using Remote Desktop Services or a similar remote connection.</span></span> <span data-ttu-id="4e31b-107">가상 데스크톱에 있는 클라이언트에서 오디오 및 비디오 처리를 많이 필요로 하는 경우와 같이 연결에서 전체 오디오 및 비디오와 함께 비즈니스용 Skype를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4e31b-107">Using Skype for Business with full audio and video on a connection like that requires heavy loads of audio and video processing on the client homed on a virtual desktop.</span></span> <span data-ttu-id="4e31b-108">추가 VDI 플러그 인 소프트웨어를 사용하여 최종 사용자의 로컬 컴퓨터로 처리를 오프로드하고 가상 데스크톱의 부하를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-108">Additional VDI plug-in software is available that offloads that processing to the end user's local machine, and reduces the load on the virtual desktop.</span></span>
  
<span data-ttu-id="4e31b-109">Microsoft, Citrix 또는 VMWare에서 제공하는 VDI 플러그 인 구성 요소에 사용할 수 있는 세 가지 솔루션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-109">There are three solutions available for the VDI plug-in component, offered by Microsoft, Citrix, or VMWare.</span></span> <span data-ttu-id="4e31b-110">새 배포의 경우 Citrix HDX RealTime Optimization Pack 솔루션 또는 VMWare Horizon 가상화 팩을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-110">For new deployments, Microsoft recommends using either the Citrix HDX RealTime Optimization Pack solution or the VMWare Horizon Virtualization Pack.</span></span> <span data-ttu-id="4e31b-111">원래 Lync VDI 플러그 인은 나머지 수명 주기 동안 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-111">The original Lync VDI Plug-in is still supported for the remainder of its lifecycle.</span></span>
  
- <span data-ttu-id="4e31b-112">**Lync VDI** 플러그 인은 Lync 2013을 위해 개발되고 가상 데스크톱에서 실행되는 Lync 2013 또는 비즈니스용 Skype 2015 클라이언트와 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-112">The **Lync VDI plug-in** was developed for Lync 2013 and is compatible with either the Lync 2013 or Skype for Business 2015 client running on a virtual desktop.</span></span> <span data-ttu-id="4e31b-113">로컬 컴퓨터에 설치되는 독립 실행형 응용 프로그램으로, 가상 데스크톱의 클라이언트에서 로컬 오디오 및 비디오 장치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-113">It's a stand-alone application that installs on the local computer and allows the use of local audio and video devices with a client on a virtual desktop.</span></span> <span data-ttu-id="4e31b-114">이 플러그 인을 사용하려면 로컬 컴퓨터 또는 씬 클라이언트에 비즈니스용 Skype 클라이언트를 설치할 필요가 없습니다. 이 클라이언트는 Windows 7, Windows 8 또는 Windows Server 2008 운영 체제를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-114">The plug-in does not require a Skype for Business client to be installed on the local computer or thin client, which must run Windows 7, Windows 8, or Windows Server 2008 operating systems.</span></span> <span data-ttu-id="4e31b-115">이러한 운영 체제를 사용하며 Microsoft에서 지원하는 씬 클라이언트 디바이스에는 Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 및 HP t5740e가 포함됩니다. 이 플러그 인은 계속 지원되지만 향후 업데이트는 계획되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-115">(Thin client devices using these operating systems and supported by Microsoft include: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 and HP t5740e.) This plug-in is still supported, but no future updates are planned.</span></span> <span data-ttu-id="4e31b-116">Citrix 기반 가상 환경의 경우 Citrix 실시간 최적화 팩을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-116">For Citrix-based virtual environments, the Citrix RealTime Optimization Pack is recommended.</span></span>
    
- <span data-ttu-id="4e31b-117">**Citrix 실시간** 최적화 팩은 Lync VDI 플러그 인을 빌드하고 가상 데스크톱의 Lync 2013 또는 비즈니스용 Skype 2016 클라이언트에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-117">The **Citrix RealTime Optimization Pack** builds on the Lync VDI plug-in and works with Lync 2013 or Skype for Business 2016 clients on a virtual desktop.</span></span> <span data-ttu-id="4e31b-118">원래 VDI 플러그 인을 개선하기 위해 Citrix와 Microsoft에서 공동 개발한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-118">It was co-developed by Citrix and Microsoft to improve upon the original VDI Plug-in.</span></span> <span data-ttu-id="4e31b-119">Windows 및 비 Windows 운영 체제(Windows 10, Mac 및 Linux 포함)가 있는 클라이언트에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-119">It can be installed on clients with Windows and non-Windows operating systems (including Windows 10, Mac and Linux).</span></span> <span data-ttu-id="4e31b-120">이 구성 요소는 RealTime Connector(가상 데스크톱에 설치) 및 RealTime Media Engine(최종 사용자의 로컬 컴퓨터에 설치)의 두 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-120">It consists of two components: the RealTime Connector (which is installed on the virtual desktop) and the RealTime Media Engine (which is installed on the end user's local machine).</span></span> <span data-ttu-id="4e31b-121">이 두 구성 요소를 사용하면 사용자의 로컬 컴퓨터에서 A/V 처리가 로컬 컴퓨터로 이동된 가상 데스크톱에서 실행되는 비즈니스용 Skype 클라이언트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-121">These two components allow the user's local computer to use the Skype for Business client running on the virtual desktop with the A/V processing moved to the local computer.</span></span> <span data-ttu-id="4e31b-122">Citrix 기반 가상 데스크톱 환경의 경우 Citrix 실시간 최적화 팩을 권장하며 추가 지원이 계획됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-122">For Citrix-based virtual desktop environments, the Citrix RealTime Optimization Pack is recommended, and further support is planned.</span></span>
    
- <span data-ttu-id="4e31b-123">VMWare와 공동으로 개발된 비즈니스용 **Skype용 VMWare Horizon 가상화** 팩을 사용하면 뛰어난 사용자 환경을 제공하는 동시에 가상 데스크톱에서 비즈니스용 Skype를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-123">The **VMWare Horizon Virtualization Pack** for Skype for Business, developed in collaboration with VMWare, allows you to deliver Skype for Business in a virtual desktop while delivering a great user experience.</span></span> <span data-ttu-id="4e31b-124">이 솔루션은 클라이언트의 미디어 엔진을 활용하여 최적화된 솔루션을 만들고 클라이언트 끝점은 오디오 및 비디오 통화에 대한 미디어 오프로드 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-124">The solution works by leveraging a media engine at the client to create an optimized solution, with the client endpoint providing media offload capabilities for audio and video calls.</span></span> <span data-ttu-id="4e31b-125">일대일 공동 작업을 위한 끝점 간에 직접 오디오 및 비디오를 전달하거나, 다중 회의 통화 또는 모임을 위해 중앙 MCU(Multipoint 제어 장치)로 오프로드할 수 있는 이 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-125">This solution that can deliver audio and video either directly between endpoints for one-on-one collaboration, or offload it to a central Multipoint Control Unit (MCU) for multiparty conference calls or meetings.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4e31b-126">비즈니스용 Skype Basic 클라이언트는 Citrix HDX RealTime Optimization Pack 또는 VMWare Horizon 가상화 팩에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-126">The Skype for Business Basic clients are not supported with the Citrix HDX RealTime Optimization Pack or the VMWare Horizon Virtualization Pack.</span></span> 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a><span data-ttu-id="4e31b-127">Citrix HDX 실시간 최적화 팩</span><span class="sxs-lookup"><span data-stu-id="4e31b-127">Citrix HDX RealTime Optimization Pack</span></span>
<span data-ttu-id="4e31b-128"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="4e31b-128"><a name="Citrix_RT"> </a></span></span>

<span data-ttu-id="4e31b-129">Citrix의 VDI 환경 플러그 인(XenApp 및 XenDesktop의 기능)은 Lync 2013 및 비즈니스용 Skype 2015 및 2016(모든 클릭으로 설치 관리자를 실행하거나 2017년 1월 PU 이후 릴리스된 MSI 설치 관리자)와 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-129">Citrix's VDI environment plugin (a feature of XenApp and XenDesktop) is compatible with Lync 2013 and Skype for Business 2015 and 2016 (Full clients using any click to run installer, or MSI installers released after January 2017 PU) clients installed on a virtual desktop.</span></span> <span data-ttu-id="4e31b-130">전체적인 기능은 Microsoft Lync VDI 플러그 인을 기반으로 하지만 Windows 10, Macintosh 및 Linux를 비롯한 다양한 클라이언트 운영 체제에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-130">Its overall functioning is based on the Microsoft Lync VDI plug-in, but works on a wider variety of client operating systems, including Windows 10, Macintosh, and Linux.</span></span>
  
<span data-ttu-id="4e31b-131">전체 기능 및 지원되는 기술 목록은 Citrix 웹 사이트에서 [Microsoft 비즈니스용 Skype를 XenApp 및 XenDesktop Users로 배달하는](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-131">A full list of features and supported technologies can be found on the Citrix website at [Delivering Microsoft Skype for Business to XenApp and XenDesktop Users](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).</span></span>
  
<span data-ttu-id="4e31b-132">자세한 내용은 다음 링크를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="4e31b-132">Review the following links for more information:</span></span>
  
- <span data-ttu-id="4e31b-133">Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)</span><span class="sxs-lookup"><span data-stu-id="4e31b-133">Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)</span></span>
    
- [<span data-ttu-id="4e31b-134">기술 개요</span><span class="sxs-lookup"><span data-stu-id="4e31b-134">Technical Overview</span></span>](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [<span data-ttu-id="4e31b-135">CTX200279 비즈니스용 Skype 기능 지원</span><span class="sxs-lookup"><span data-stu-id="4e31b-135">CTX200279 Skype for Business Feature Support</span></span>](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a><span data-ttu-id="4e31b-136">VMWare Horizon 가상화 팩</span><span class="sxs-lookup"><span data-stu-id="4e31b-136">VMWare Horizon Virtualization Pack</span></span>
<span data-ttu-id="4e31b-137"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="4e31b-137"><a name="Citrix_RT"> </a></span></span>

<span data-ttu-id="4e31b-138">VMWare의 VDI 환경 솔루션은 가상 데스크톱에 설치된 비즈니스용 Skype 2015 및 2016 전체 클라이언트와 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-138">VMWare's VDI environment solution is compatible with Skype for Business 2015 and 2016 Full clients installed on a virtual desktop.</span></span> <span data-ttu-id="4e31b-139">전체적인 기능은 Microsoft Lync VDI 플러그 인을 기반으로 하지만 Windows 10, Macintosh 및 Linux를 비롯한 다양한 클라이언트 운영 체제에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-139">Its overall functioning is based on the Microsoft Lync VDI plug-in, but works on a wider variety of client operating systems, including Windows 10, Macintosh, and Linux.</span></span> 
  
<span data-ttu-id="4e31b-140">기능 및 지원되는 기술에 대한 전체 설명은 다음 링크의 VMWare 웹 사이트에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-140">A full discussion of features and supported technologies can be found on the VMWare website at the following links:</span></span>
  
- [<span data-ttu-id="4e31b-141">VMware Horizon 7.4 &amp; Horizon Client 4.7의 새로운</span><span class="sxs-lookup"><span data-stu-id="4e31b-141">What's New in VMware Horizon 7.4 &amp; Horizon Client 4.7</span></span>](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [<span data-ttu-id="4e31b-142">비즈니스용 Skype용 Horizon 가상화 팩</span><span class="sxs-lookup"><span data-stu-id="4e31b-142">Horizon Virtualization Pack for Skype for Business</span></span>](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [<span data-ttu-id="4e31b-143">VMWare Horizon을 통해 비즈니스용 Microsoft Skype</span><span class="sxs-lookup"><span data-stu-id="4e31b-143">Microsoft Skype for Business With VMWare Horizon</span></span>](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a><span data-ttu-id="4e31b-144">Microsoft의 Lync VDI 플러그 인</span><span class="sxs-lookup"><span data-stu-id="4e31b-144">Microsoft's Lync VDI plug-in</span></span>
<span data-ttu-id="4e31b-145"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="4e31b-145"><a name="Citrix_RT"> </a></span></span>

<span data-ttu-id="4e31b-146">Microsoft Lync VDI 플러그 인 솔루션을 사용할 경우 사용자는 Windows 컴퓨터 또는 씬 클라이언트에 있으며 가상 데스크톱의 클라이언트에서 오디오/비디오 스트림을 처리하기 위해 Microsoft의 Lync VDI 플러그 인이 설치되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-146">With the Microsoft Lync VDI plug-in solution, the user has to be on a Windows computer or thin client and have Microsoft's Lync VDI plugin installed to handle audio/video streams from the client on the virtual desktop.</span></span> <span data-ttu-id="4e31b-147">사용자는 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-147">A user will:</span></span>
  
1. <span data-ttu-id="4e31b-148">오디오/비디오 장치(예: 헤드셋 또는 카메라)를 로컬 컴퓨터에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-148">Connect an audio/video device (like a headset or camera) to a local computer.</span></span>
    
2. <span data-ttu-id="4e31b-149">Lync 2013 또는 비즈니스용 Skype 2015 클라이언트를 사용하여 원격 가상 데스크톱에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-149">Connect to a remote virtual desktop with a Lync 2013 or Skype for Business 2015 client.</span></span>
    
3. <span data-ttu-id="4e31b-150">가상 데스크톱에서 비즈니스용 Skype 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-150">Enter credentials for Skype for Business on the virtual desktop.</span></span>
    
4. <span data-ttu-id="4e31b-151">로컬 Windows 컴퓨터 또는 씬 클라이언트에서 Lync VDI 플러그 인과 연결을 설정하려면 사용자 자격 증명을 다시 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-151">Re-enter user credentials to establish a connection with the Lync VDI plug-in on the local Windows computer or thin client.</span></span>
    
<span data-ttu-id="4e31b-152">연결이 설정되면 사용자는 오디오 및 비디오 통화를 걸고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-152">After a connection is established, the user is ready to make and receive audio and video calls.</span></span> <span data-ttu-id="4e31b-153">로컬 컴퓨터가 오디오/비디오 처리를 처리하기 때문에 네트워크의 트래픽과 가상 데스크톱의 부하가 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-153">Traffic on the network and the load on the virtual desktop are minimized, since the local computer handles the audio/video processing.</span></span>
  
<span data-ttu-id="4e31b-154">Microsoft의 Lync VDI 플러그 인은 특정 Windows 운영 체제에서만 지원하며 Lync 2013 또는 비즈니스용 Skype 2015 클라이언트만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-154">Microsoft's Lync VDI plug-in is only supported on certain Windows operating systems and only supports Lync 2013 or Skype for Business 2015 clients.</span></span> <span data-ttu-id="4e31b-155">지원되는 [기술](vdi-environments.md#Supported_virt) 및 제한에 대한 자세한 내용은 지원되는 가상화 기술 및 알려진 제한 사항을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-155">See [Supported virtualization technologies and known limitations](vdi-environments.md#Supported_virt) for more details on supported technologies and limitations.</span></span>
  
<span data-ttu-id="4e31b-156">자세한 내용은 다음 링크를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="4e31b-156">Review the following links for more information:</span></span>
  
- [<span data-ttu-id="4e31b-157">지원되는 가상화 기술 및 알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="4e31b-157">Supported virtualization technologies and known limitations</span></span>](vdi-environments.md#Supported_virt)
    
- [<span data-ttu-id="4e31b-158">Lync VDI 플러그 인 필요</span><span class="sxs-lookup"><span data-stu-id="4e31b-158">Lync VDI plug-in prerequisites</span></span>](vdi-environments.md#VDI_prereq)
    
- [<span data-ttu-id="4e31b-159">비즈니스용 Skype 서버를 통해 Lync VDI 플러그 인 배포</span><span class="sxs-lookup"><span data-stu-id="4e31b-159">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- <span data-ttu-id="4e31b-160">Citrix 기술 센터 문서 [CTX138408](https://support.citrix.com/article/CTX138408)</span><span class="sxs-lookup"><span data-stu-id="4e31b-160">Citrix Knowledge Center article [CTX138408](https://support.citrix.com/article/CTX138408)</span></span>
    
<span data-ttu-id="4e31b-161">Microsoft VDI 플러그 인은 [Microsoft Lync VDI 2013 플러그 인(32비트)](https://www.microsoft.com/download/details.aspx?id=35457) 또는 [Microsoft Lync VDI 2013 플러그 인(64비트)에서](https://www.microsoft.com/download/details.aspx?id=35454)사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-161">The Microsoft VDI plugin is available at [Microsoft Lync VDI 2013 plugin (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) or [Microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454).</span></span> <span data-ttu-id="4e31b-162">이 플러그 인은 이름에도 불구하고 비즈니스용 Skype 2015 클라이언트에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-162">This plugin is supported with the Skype for Business 2015 client, despite the name.</span></span>
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a><span data-ttu-id="4e31b-163">지원되는 가상화 기술 및 알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="4e31b-163">Supported virtualization technologies and known limitations</span></span>
<span data-ttu-id="4e31b-164"><a name="Supported_virt"> </a></span><span class="sxs-lookup"><span data-stu-id="4e31b-164"><a name="Supported_virt"> </a></span></span>

<span data-ttu-id="4e31b-165">Lync VDI 플러그 인을 사용하면 지원되는 가상화 기술에 대해 오디오 및 화상 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-165">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="4e31b-166">표준 전화 규정을 준수하는 E911 지원도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-166">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="4e31b-167">다음 섹션에서는 Lync VDI 플러그 인에서 지원하는 가상화 기술 및 알려진 기능 제한에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-167">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>
  
#### <a name="support-for-virtualization-technologies"></a><span data-ttu-id="4e31b-168">가상화 기술 지원</span><span class="sxs-lookup"><span data-stu-id="4e31b-168">Support for Virtualization Technologies</span></span>

<span data-ttu-id="4e31b-169">Lync VDI 플러그 인은 개인 가상 데스크톱 시나리오에서 전체 데스크톱 원격 세션을 지원하지만 원격 데스크톱 세션 시나리오에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-169">The Lync VDI plug-in supports full desktop remote sessions in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="4e31b-170">이러한 시나리오는 다음과 같이 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-170">These scenarios can be described as follows:</span></span>
  
- <span data-ttu-id="4e31b-171">**지원: 개인 설정된 가상 데스크톱 또는 VDI(가상 데스크톱 인프라)**</span><span class="sxs-lookup"><span data-stu-id="4e31b-171">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**</span></span> <span data-ttu-id="4e31b-172">이 시나리오에서 각 사용자는 사용자 지정 가능한 가상 데스크톱에 로그온하고 세션 전체에서 유지되는 데스크톱에 파일을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-172">In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="4e31b-173">Microsoft 원격 데스크톱 서비스 및 VMware Horizon 보기는 비즈니스용 Skype 2015에서 사용하기 위해 테스트된 구현의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-173">Microsoft Remote Desktop Services and VMware Horizon View are example implementations that have been tested for use with Skype for Business 2015.</span></span> <span data-ttu-id="4e31b-174">유효성 검사를 진행하는 다른 구현에는 Citrix XenDesktop이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-174">Other implementations undergoing validation include Citrix XenDesktop.</span></span> <span data-ttu-id="4e31b-175">Microsoft에서 테스트한 공급업체별 VDI 환경 및 클라이언트 하드웨어에 대한 자세한 내용은 Microsoft Lync에 대해 자격을 갖춘 [인프라를 참조하세요.](https://go.microsoft.com/fwlink/?LinkID=313435)</span><span class="sxs-lookup"><span data-stu-id="4e31b-175">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).</span></span>
    
- <span data-ttu-id="4e31b-176">**지원되지 않습니다. 원격 데스크톱 세션.**</span><span class="sxs-lookup"><span data-stu-id="4e31b-176">**Not supported: Remote Desktop Sessions.**</span></span> <span data-ttu-id="4e31b-177">이 시나리오에서는 각 사용자가 사용자 지정할 수 없는 일반 가상 데스크톱 세션에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-177">In this scenario, each user logs on to a generic virtual desktop session that can't be customized.</span></span> <span data-ttu-id="4e31b-178">예를 들어 Microsoft RDSH(원격 데스크톱 세션) 및 Citrix Receiver와 결합된 Citrix XenApp이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-178">Examples include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>
    
<span data-ttu-id="4e31b-179">Lync VDI 플러그 인은 전체 응용 프로그램을 로컬로 설치하지 않고도 응용 프로그램을 사용할 수 있는 응용 프로그램 가상화와 같은 다른 가상화 기술을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-179">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="4e31b-180">구현 예로는 Citrix XenApp 및 Microsoft App-V(Application Virtualization)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-180">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="4e31b-181">응용 프로그램 스트리밍, 응용 프로그램 원격 및 혼합 가상화 모드(예: 전체 데스크톱 원격의 응용 프로그램 원격)는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-181">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>
  
<span data-ttu-id="4e31b-182">Lync VDI 플러그 인은 DVC(동적 가상 채널)라는 플랫폼 독립적 API를 사용하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-182">The Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="4e31b-183">명시적으로 지원되지 않는 시나리오는 VDI 솔루션 공급자의 지원 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e31b-183">For scenarios that are not explicitly supported, refer to support statements from the VDI solution provider.</span></span>
  
#### <a name="lync-vdi-plug-in-prerequisites"></a><span data-ttu-id="4e31b-184">Lync VDI 플러그 인 필요</span><span class="sxs-lookup"><span data-stu-id="4e31b-184">Lync VDI plug-in prerequisites</span></span>
<span data-ttu-id="4e31b-185"><a name="VDI_prereq"> </a></span><span class="sxs-lookup"><span data-stu-id="4e31b-185"><a name="VDI_prereq"> </a></span></span>

<span data-ttu-id="4e31b-186">VDI 환경에서는 가상 컴퓨터와 사용자의 로컬 컴퓨터가 이 섹션에 설명된 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-186">In a VDI environment, the virtual machines and the user's local computer must meet the requirements outlined in this section.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="4e31b-187">가상화 솔루션 공급자는 해당 환경을 설치 및 배포하는 방법에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-187">Your virtualization solution provider can supply details about how to install and deploy their environment.</span></span> <span data-ttu-id="4e31b-188">Hyper-V 및 원격 데스크톱 서비스를 기반으로 가상화된 환경을 배포하는 데 대한 일반적인 정보는 Microsoft 라이브러리의 [Hyper-V,](https://go.microsoft.com/fwlink/p/?linkid=247514) [Windows Server 2008 R2의](https://go.microsoft.com/fwlink/p/?linkid=247513) 원격 데스크톱 서비스 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e31b-188">For general information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft Library: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Remote Desktop Services in Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513)</span></span> 
  
<span data-ttu-id="4e31b-189">가상 컴퓨터는 최신 서비스 팩을 통해 Windows 8, Windows 7 또는 Windows Server 2008 R2로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-189">Virtual machines must be configured with Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>
  
<span data-ttu-id="4e31b-190">사용자의 로컬 컴퓨터는 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-190">The user's local computer must meet the following requirements:</span></span>
  
- <span data-ttu-id="4e31b-191">사용자는 비즈니스용 Skype 서버 또는 Lync Server 2013에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-191">The user must be homed on Skype for Business Server or Lync Server 2013.</span></span>
    
- <span data-ttu-id="4e31b-192">로컬 컴퓨터에서 Windows Embedded Standard 7 SP1, Windows 7 SP1 또는 Windows 8을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-192">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, or Windows 8.</span></span>
    
- <span data-ttu-id="4e31b-193">원격 데스크톱 서비스를 사용하는 경우 로컬 컴퓨터의 운영 체제와 일치하게 32비트 또는 64비트 Lync VDI 플러그 인을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e31b-193">If you're using Remote Desktop Services, choose the 32-bit or 64-bit Lync VDI plug-in to match the local computer's operating system.</span></span> <span data-ttu-id="4e31b-194">로컬 컴퓨터와 가상 컴퓨터 모두 32비트 또는 64비트 운영 체제를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-194">It's not required for both the local computer and the virtual machine to have 32-bit or 64-bit operating systems.</span></span> <span data-ttu-id="4e31b-195">다른 가상화 솔루션 또는 플랫폼을 사용하는 경우 공급자의 요구 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e31b-195">If you're using another virtualization solution or platform, refer to your provider's requirements.</span></span>
    
- <span data-ttu-id="4e31b-196">로컬 컴퓨터에서 최신 버전의 원격 데스크톱 [클라이언트를 실행하고 있어야 합니다.](https://go.microsoft.com/fwlink/p/?LinkId=268032)</span><span class="sxs-lookup"><span data-stu-id="4e31b-196">The local computer must be running the [latest version of the remote desktop client](https://go.microsoft.com/fwlink/p/?LinkId=268032).</span></span> <span data-ttu-id="4e31b-197">Microsoft에서 제공하는 원격 데스크톱 서비스 클라이언트의 최신 업데이트를 설치하거나 가상화 솔루션 공급자가 제공하는 최신 원격 데스크톱 클라이언트 소프트웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-197">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> 
    
- <span data-ttu-id="4e31b-198">로컬 컴퓨터에서 오디오가 재생되고 원격 녹음을 사용할 수 없도록 원격 데스크톱 클라이언트 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-198">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="4e31b-199">Windows에서 원격 데스크톱 연결에 대한 이러한 설정을 구성하려면 다음 섹션인 "원격 데스크톱 연결 설정을 구성하려면"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e31b-199">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span> 
    
<span data-ttu-id="4e31b-200">Microsoft VDI 플러그 인은 [Microsoft Lync VDI 2013 플러그 인(32비트)](https://www.microsoft.com/download/details.aspx?id=35457) 또는 [Microsoft Lync VDI 2013 플러그 인(64비트)에서](https://www.microsoft.com/download/details.aspx?id=35454)사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-200">The Microsoft VDI plugin is available at [Microsoft Lync VDI 2013 plugin (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) or [Microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454).</span></span>
  
#### <a name="known-feature-limitations"></a><span data-ttu-id="4e31b-201">알려진 기능 제한 사항</span><span class="sxs-lookup"><span data-stu-id="4e31b-201">Known Feature Limitations</span></span>
<span data-ttu-id="4e31b-202"><a name="VDI_prereq"> </a></span><span class="sxs-lookup"><span data-stu-id="4e31b-202"><a name="VDI_prereq"> </a></span></span>

<span data-ttu-id="4e31b-203">다음은 VDI 환경에서 비즈니스용 Skype 2015 클라이언트를 사용할 때 알려진 제한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-203">The following are known limitations when you use the Skype for Business 2015 client in a VDI environment:</span></span>
  
<span data-ttu-id="4e31b-204">통화 위임 및 응답 그룹 에이전트의Onymization 기능에 대한 지원은 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-204">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>
  
<span data-ttu-id="4e31b-205">다음 기능은 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-205">There is no support for the following features:</span></span>
  
- <span data-ttu-id="4e31b-206">통합 오디오 장치 및 비디오 장치 조정 페이지</span><span class="sxs-lookup"><span data-stu-id="4e31b-206">Integrated Audio Device and Video Device tuning pages.</span></span>
    
- <span data-ttu-id="4e31b-207">다중 보기 비디오.</span><span class="sxs-lookup"><span data-stu-id="4e31b-207">Multiple-view video.</span></span>
    
- <span data-ttu-id="4e31b-208">대화 녹음/녹화.</span><span class="sxs-lookup"><span data-stu-id="4e31b-208">Recording of conversations.</span></span>
    
- <span data-ttu-id="4e31b-209">익명으로 모임 참가(즉, 조직과 페더링되지 않은 조직에서 호스팅하는 비즈니스용 Skype 모임에 참가)</span><span class="sxs-lookup"><span data-stu-id="4e31b-209">Joining meetings anonymously (that is, joining Skype for Business meetings hosted by an organization that does not federate with your organization).</span></span>
    
- <span data-ttu-id="4e31b-210">Lync Phone Edition 장치와 함께 Lync VDI 플러그 인 사용</span><span class="sxs-lookup"><span data-stu-id="4e31b-210">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
- <span data-ttu-id="4e31b-211">네트워크가 정전된 경우 통화 연속성</span><span class="sxs-lookup"><span data-stu-id="4e31b-211">Call continuity in case of a network outage.</span></span>
    
- <span data-ttu-id="4e31b-212">사용자 지정된 벨소리 및 보류 음악 기능</span><span class="sxs-lookup"><span data-stu-id="4e31b-212">Customized ringtones and music-on-hold features.</span></span>
    
<span data-ttu-id="4e31b-213">Lync VDI 플러그 인은 Microsoft 365 또는 Office 365 환경에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-213">The Lync VDI plug-in is not supported in Microsoft 365 or Office 365 environments.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4e31b-214">Citrix 실시간 최적화 팩은 Microsoft 365 및 Office 365를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4e31b-214">The Citrix RealTime Optimization Pack does support Microsoft 365 and Office 365.</span></span> <span data-ttu-id="4e31b-215">Citrix 기반 가상 환경의 경우 지원되는 [](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) 기능 및 버전 목록에 대한 Citrix의 기술 개요 설명서를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="4e31b-215">For Citrix-based virtual environments, review Citrix's [Technical Overview](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) documentation for the list of supported features and versions.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4e31b-216">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e31b-216">See also</span></span>
<span data-ttu-id="4e31b-217"><a name="Citrix_RT"> </a></span><span class="sxs-lookup"><span data-stu-id="4e31b-217"><a name="Citrix_RT"> </a></span></span>

[<span data-ttu-id="4e31b-218">비즈니스용 Skype 서버를 통해 Lync VDI 플러그 인 배포</span><span class="sxs-lookup"><span data-stu-id="4e31b-218">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

