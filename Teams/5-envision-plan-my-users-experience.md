---
title: 사용자 경험 계획 Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 클라이언트 Teams 선택하고 엔드포인트 품질을 계획하고, 엔드포인트를 배포하고 오디오 Wi-Fi 권장 사항을 얻습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d20d914ab6ceca1d264a23662c9c8a067798a82
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094736"
---
# <a name="plan-my-users-experience"></a><span data-ttu-id="a4797-103">사용자 환경 계획</span><span class="sxs-lookup"><span data-stu-id="a4797-103">Plan my users’ experience</span></span>

<span data-ttu-id="a4797-104">이 문서에서는 사용자 경험에 직접적인 영향을 주는 클라우드 음성 서비스 배포의 요소를 올바르게 식별하기 위한 요구 사항에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-104">This article gives an overview of the requirements for properly identifying the elements of your cloud voice services deployment that directly affect your users’ experience.</span></span> <span data-ttu-id="a4797-105">배포 전에 이러한 항목을 준비하면 사용자에게 고품질의 신뢰할 수 있는 환경을 성공적으로 제공할 가능성이 높아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-105">By preparing for these items before deployment, you’ll increase your chances of successfully delivering a high-quality, reliable experience for users.</span></span> 

## <a name="client-deployment"></a><span data-ttu-id="a4797-106">클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="a4797-106">Client deployment</span></span>

<span data-ttu-id="a4797-107">Microsoft Teams 웹, 데스크톱(Windows 및 Mac), 모바일(Android 및 iOS)에 사용할 수 있는 클라이언트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-107">Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android and iOS).</span></span> <span data-ttu-id="a4797-108">데스크톱(Windows 및 Mac) 및 모바일 클라이언트가 설치되는 방법에 대한 자세한 내용은 에 대한 클라이언트 [Microsoft Teams.](./get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="a4797-108">For additional details about how the desktop (Windows and Mac) and mobile clients are installed, see [Get clients for Microsoft Teams](./get-clients.md).</span></span>

## <a name="client-updates"></a><span data-ttu-id="a4797-109">클라이언트 업데이트</span><span class="sxs-lookup"><span data-stu-id="a4797-109">Client updates</span></span>

<span data-ttu-id="a4797-110">클라이언트가 Teams 주요 이점 중 하나는 클라이언트가 자동으로 최신으로 유지되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-110">One of the key benefits of Teams is that the client is kept up to date automatically.</span></span> <span data-ttu-id="a4797-111">PC 및 Mac의 클라이언트는 새 빌드를 확인하고 앱이 유휴일 때 새 클라이언트를 다운로드하는 백그라운드 프로세스를 사용하여 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-111">The clients on the PC and Mac are updated by using a background process that checks for new builds and downloads the new client when the app is idle.</span></span>

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a><span data-ttu-id="a4797-112">엔드포인트 품질 계획</span><span class="sxs-lookup"><span data-stu-id="a4797-112">Plan for endpoint quality</span></span>

<span data-ttu-id="a4797-113">아래 다이어그램에서 볼 수 있 처럼 엔드포인트는 사용자에게 품질 환경을 제공하는 데 중요한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-113">As you can see from the diagram below, endpoints are an important building block in providing a quality experience for users.</span></span>

<span data-ttu-id="a4797-114">![품질의 세 가지 구성 요소를 설명하는 다이어그램](media/plan-my-users-experience-image1.png "품질의 세 가지 구성 요소와 서비스 관리가 세 구성 요소를 모두 겹치는 방법을 설명하는 다이어그램입니다. 엔드포인트에 포커스가 있습니다.")</span><span class="sxs-lookup"><span data-stu-id="a4797-114">![Diagram describing the three components of quality](media/plan-my-users-experience-image1.png "Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on endpoints.")</span></span>

<span data-ttu-id="a4797-115">Teams 엔드포인트는 PC, Mac, 태블릿 및 모바일 디바이스를 비롯한 여러 장치에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-115">Teams endpoints can run on many devices, including PCs, Macs, tablets, and mobile devices.</span></span> <span data-ttu-id="a4797-116">환경의 일부에는 디바이스뿐만 아니라 사용자가 디바이스에 연결하는 방식(예: 디바이스의 기본 제공 마이크/스피커, 이어버드 또는 최적화된 헤드셋 사용)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-116">Part of the experience not only encompasses the device, but how a user connects to the device—for example, using the device’s built-in mic/speaker, earbuds, or an optimized headset.</span></span> <span data-ttu-id="a4797-117">최적화된 헤드셋을 사용하면 전체 사용자 환경을 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-117">Using an optimized headset can enrich the overall user experience.</span></span>

<span data-ttu-id="a4797-118">엔드포인트 계획에 대한 다음 지침은 조직에서 성공적인 온보더링 환경을 보장하는 데 도움이 Teams.</span><span class="sxs-lookup"><span data-stu-id="a4797-118">The following guidance on endpoint planning will help you ensure your organization has a successful onboarding experience with Teams.</span></span>

## <a name="endpoint-capability"></a><span data-ttu-id="a4797-119">엔드포인트 기능</span><span class="sxs-lookup"><span data-stu-id="a4797-119">Endpoint capability</span></span>

<span data-ttu-id="a4797-120">계획의 첫 번째 부분은 조직의 모든 PC 및 기타 디바이스에서 실행될 수 있도록 Teams.</span><span class="sxs-lookup"><span data-stu-id="a4797-120">The first part of planning is to ensure all the PCs and other devices in your organization can run Teams.</span></span> <span data-ttu-id="a4797-121">이는 하드웨어 요구 사항을 보는 것만이 아니라 PC가 백그라운드에서 무엇을 하는지 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-121">This involves not just looking at the hardware requirements, but also understanding what else the PC is doing in the background.</span></span> <span data-ttu-id="a4797-122">많은 조직에서 디바이스의 기본 성능에 영향을 줄 수 있는 침입 감지 시스템 및 맬웨어 방지 소프트웨어를 포함하여 다른 소프트웨어를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-122">Many organizations run other software, including intrusion detection systems and antimalware software, which can affect the base performance of a device.</span></span>

<span data-ttu-id="a4797-123">각 플랫폼(웹Teams 데스크톱 및 모바일)의 클라이언트에 대한 소프트웨어 요구 사항에 대한 자세한 내용은 에 대한 클라이언트 [Microsoft Teams.](./get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="a4797-123">For information about the software requirements for Teams clients on each platform (web, desktop, and mobile), see [Get clients for Microsoft Teams](./get-clients.md).</span></span>

## <a name="endpoint-firewalls"></a><span data-ttu-id="a4797-124">엔드포인트 방화벽</span><span class="sxs-lookup"><span data-stu-id="a4797-124">Endpoint firewalls</span></span>

<span data-ttu-id="a4797-125">클라이언트 쪽 방화벽은 사용자 환경에 상당한 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-125">Client-side firewalls can have a significant impact on the user experience.</span></span>
<span data-ttu-id="a4797-126">클라이언트 쪽 방화벽은 통화가 설정되지 않도록 할 뿐만 아니라 통화 품질에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-126">Client-side firewalls can affect call quality in addition to preventing a call from being established.</span></span> <span data-ttu-id="a4797-127">URL 및 IP 주소 범위의 Microsoft 365 Office 365 클라이언트 방화벽에서 적절한 제외를 [구성합니다.](/microsoft-365/enterprise/urls-and-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="a4797-127">Configure the appropriate exclusions on the client firewall based on the information in [Microsoft 365 or Office 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="a4797-128">타사 공급업체는 제외를 만드는 방법에 대한 특정 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-128">Your third-party vendor will have specific guidance on how to create the exclusions.</span></span>

>[!NOTE]
> <span data-ttu-id="a4797-129">Microsoft Teams 방화벽을 Windows 방화벽을 자동으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-129">Microsoft Teams will automatically update the Windows Firewall with an appropriate firewall configuration.</span></span>

## <a name="wi-fi-recommendations-for-endpoints"></a><span data-ttu-id="a4797-130">Wi-Fi 권장 사항</span><span class="sxs-lookup"><span data-stu-id="a4797-130">Wi-Fi recommendations for endpoints</span></span>

<span data-ttu-id="a4797-131">최적화된 네트워크 배포를 Wi-Fi 실시간 워크로드를 지원하기 위해 상당한 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a4797-131">It takes significant planning to deploy an optimized Wi-Fi network to support real-time workloads in Microsoft Teams.</span></span> <span data-ttu-id="a4797-132">다음 섹션에서는 엔드포인트를 계획할 때 일반적인 문제를 방지하는 데 도움이 되는 몇 가지 일반적인 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-132">The following sections provide some general guidance that can help you avoid common pitfalls when planning for endpoints.</span></span>

### <a name="wi-fi-drivers"></a><span data-ttu-id="a4797-133">Wi-Fi 드라이버</span><span class="sxs-lookup"><span data-stu-id="a4797-133">Wi-Fi drivers</span></span>

<span data-ttu-id="a4797-134">일부 Wi-Fi 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-134">Some Wi-Fi drivers can be problematic.</span></span> <span data-ttu-id="a4797-135">예를 들어 드라이버는 액세스 지점 간에 매우 공격적인 로밍 동작이 발생하여 통화 품질이 좋지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-135">As an example, a driver might have very aggressive roaming behaviors between access points, causing poor call quality.</span></span>
<span data-ttu-id="a4797-136">일반적으로 발생하는 것은 아니지만 배포하기 전에 PC의 Wi-Fi 드라이버를 업데이트하고 테스트하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-136">This isn’t a common occurrence, but it’s important to ensure that Wi-Fi drivers on the PC have been updated and tested prior to deployment.</span></span>

### <a name="wi-fi-bands"></a><span data-ttu-id="a4797-137">Wi-Fi 밴드</span><span class="sxs-lookup"><span data-stu-id="a4797-137">Wi-Fi bands</span></span>

<span data-ttu-id="a4797-138">현재는 2.4GHz 및 5.0GHz의 Wi-Fi 장비에 사용되는 두 가지 유형의 대역이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-138">There are primarily two types of bands used in Wi-Fi equipment today, 2.4 GHz and 5.0 GHz.</span></span> <span data-ttu-id="a4797-139">조직에서 두 대역을 모두 제공하는 경우 5.0GHz 대역을 선호하도록 드라이버 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-139">If your organization provides both bands, you should configure your driver settings to prefer the 5.0 GHz band.</span></span> <span data-ttu-id="a4797-140">이 대역은 매우 밀도가 높고 2.4GHz 대역에서 볼 수 있는 간섭의 영향을 덜 받는다.</span><span class="sxs-lookup"><span data-stu-id="a4797-140">This band is much denser in terms of throughput and is less affected by the interference seen in the 2.4 GHz band.</span></span>
<span data-ttu-id="a4797-141">이 권장은 5.0GHz 네트워크 대역을 적절하게 최적화했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-141">This recommendation assumes that you’ve properly optimized the 5.0 GHz network band.</span></span>

### <a name="wi-fi-radio-type"></a><span data-ttu-id="a4797-142">Wi-Fi 라디오 유형</span><span class="sxs-lookup"><span data-stu-id="a4797-142">Wi-Fi radio type</span></span>

<span data-ttu-id="a4797-143">새로운 무선 형식을 지원하는 Wi-Fi 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-143">Plan for devices that support the newer Wi-Fi radio types.</span></span> <span data-ttu-id="a4797-144">프로비전하는 디바이스에서 802.11ac 또는 최신 Wi-Fi 활용하면 매우 좋은 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-144">You can get very good Wi-Fi performance if you leverage 802.11ac or newer on the devices you provision.</span></span>

### <a name="wireless-avoidance"></a><span data-ttu-id="a4797-145">무선 회피</span><span class="sxs-lookup"><span data-stu-id="a4797-145">Wireless avoidance</span></span>

<span data-ttu-id="a4797-146">일부 조직에서는 이러한 문제를 Wi-Fi 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-146">Some organizations prefer to avoid Wi-Fi altogether.</span></span> <span data-ttu-id="a4797-147">경우에 따라 이 지침은 유선 네트워크에 직접 연결하기 위한 사용자에게 권장을 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-147">Sometimes this guidance is provided through a recommendation to users to connect directly to a wired network.</span></span> <span data-ttu-id="a4797-148">경우에 따라 네트워크 바인딩 순서에 무선 연결이 선호되고 PC가 유선 연결에 연결되어 있는 경우에도 이 연결을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-148">In some cases, the network binding order might have the wireless connection preferred and continue to use that connection even though the PC is connected to the wired connection.</span></span> <span data-ttu-id="a4797-149">의도하지 않은 동작을 방지하기 위해 이 시나리오를 피하기 위해 바인딩 순서를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-149">To avoid this unintended behavior, configure the binding order to avoid this scenario.</span></span>

### <a name="80211-power-save-protocol"></a><span data-ttu-id="a4797-150">802.11 Power Save 프로토콜</span><span class="sxs-lookup"><span data-stu-id="a4797-150">802.11 Power Save protocol</span></span>

<span data-ttu-id="a4797-151">조직에서 802.11 Power Save 프로토콜을 지원하지 않는 무선 액세스 지점 또는 라우터를 사용하는 경우 디바이스에서 실행되는 장치에서 호출이 떨어지거나 통화 품질이 Microsoft Teams Windows 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-151">If your organization uses wireless access points or routers that don’t support the 802.11 Power Save protocol, you might experience dropped calls or poor call quality in Microsoft Teams running on Windows devices.</span></span> <span data-ttu-id="a4797-152">무선 액세스 지점 또는 라우터를 업그레이드할 수 없는 경우 배터리 전원에서 실행되는 Windows 전원 요금제 설정을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-152">If it’s not possible to upgrade your wireless access point or routers, you should update Windows Power Plan settings on devices that run on battery power.</span></span> <span data-ttu-id="a4797-153">자세한 내용 및 구성 지침은 다음 지원 문서 [에 제공됩니다.](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)</span><span class="sxs-lookup"><span data-stu-id="a4797-153">Further detail and configuration guidance is provided in the following [support article](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="a4797-154">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="a4797-154">Decision points</span></span></td><td><ul><li><span data-ttu-id="a4797-155">조직에 Teams 어떤 클라이언트가 배포될까요?</span><span class="sxs-lookup"><span data-stu-id="a4797-155">What Teams clients will be deployed in your organization?</span></span></li><li><span data-ttu-id="a4797-156">클라이언트를 처음에 Teams 어떻게 배포하나요?</span><span class="sxs-lookup"><span data-stu-id="a4797-156">How will you initially deploy Teams clients to your users?</span></span></li><li><span data-ttu-id="a4797-157">Who 요구 사항을 충족하는지 검사하기 위해 엔드포인트 및 디바이스를 Teams 책임이 있나요?</span><span class="sxs-lookup"><span data-stu-id="a4797-157">Who is responsible for evaluating endpoints and devices to validate they meet Teams requirements for a quality experience?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="a4797-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a4797-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="a4797-159">클라이언트를 배포하기 위해 수행될 프로세스를 Teams 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-159">Document the process that will be followed to deploy Teams clients.</span></span></li><li><span data-ttu-id="a4797-160">엔드포인트 및 디바이스를 평가하고 필요한 수행 및 수정을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-160">Evaluate endpoints and devices and perform and remediation required.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a><span data-ttu-id="a4797-161">Teams</span><span class="sxs-lookup"><span data-stu-id="a4797-161">Devices for Teams</span></span>

<span data-ttu-id="a4797-162">Microsoft Teams 또는 전화 시스템으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-162">Microsoft Teams can be used for meetings or as a phone system.</span></span> <span data-ttu-id="a4797-163">이러한 기능을 사용하는 경우 사용자 경험에서 Teams 인터페이스 디바이스가 중요한 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-163">When using these features, the interface device that is used for Teams plays an important role in the user experience.</span></span>

<span data-ttu-id="a4797-164">기본 제공 PC 스피커와 마이크를 사용하는 경우 해당 구성이 있는 사용자에게는 허용되는 소리가 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-164">Using a built-in PC speaker and microphone might sound acceptable to the user who has that configuration.</span></span> <span data-ttu-id="a4797-165">그러나 일반적으로 이러한 디바이스는 노이즈 취소에 최적화되지 않습니다. 모든 유형의 주변 소음이 호출에 다른 사용자에 다운스트림 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-165">But typically, those devices aren’t optimized for noise cancellation, and any type of ambient noise can have a downstream impact on others on the call.</span></span> <span data-ttu-id="a4797-166">이러한 시나리오에 최적화된 디바이스를 활용하면 고품질 환경을 보장하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-166">Leveraging devices optimized for these scenarios will help ensure a high-quality experience.</span></span>

<span data-ttu-id="a4797-167">각 디바이스는 사용자의 요구를 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-167">Each device needs to meet the needs of your users.</span></span> <span data-ttu-id="a4797-168">조직의 다른 사용자 및 사용 사례에 대한 헤드셋과 같은 디바이스를 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-168">You’ll need to tailor devices such as headsets for the different personas and use cases in your organization.</span></span>
<span data-ttu-id="a4797-169">가상 장치 매핑 연습은 계획 프로세스의 일부로 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-169">A persona-to-device mapping exercise should be completed as part of the planning process.</span></span>

<span data-ttu-id="a4797-170">디바이스를 선택한 후 최종 유효성 검사를 위한 파일럿 테스트 계획에 해당 디바이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-170">After you’ve selected the devices, include them in the pilot test plan for final validation.</span></span> <span data-ttu-id="a4797-171">파일럿 중에 설문 조사를 활용하여 피드백을 수집하여 디바이스 전략이 최적의지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-171">Leverage surveys during the pilot to collect feedback to ensure your device strategy is optimal.</span></span>

> [!NOTE]
> <span data-ttu-id="a4797-172">현재 인증 프로그램을 통해 인증된 오디오 비즈니스용 Skype 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-172">At this time, we recommend using audio devices that were certified through the Skype for Business Certification program.</span></span> <span data-ttu-id="a4797-173">이 프로그램 아래에서 인증된 디바이스를 [찾으신](https://products.office.com/microsoft-teams/across-devices/devices) 경우 디바이스 및 USB Microsoft Teams 및 비디오 디바이스를 [참조합니다.](/SkypeForBusiness/certification/devices-usb-devices)</span><span class="sxs-lookup"><span data-stu-id="a4797-173">To find devices certified under this program, see the [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices/devices) and [USB audio and video devices](/SkypeForBusiness/certification/devices-usb-devices).</span></span>



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="a4797-174">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="a4797-174">Decision points</span></span></td><td><ul><li><span data-ttu-id="a4797-175">사용자 및 회의실 환경을 위한 조직의 전체 디바이스 전략을 결정하세요.</span><span class="sxs-lookup"><span data-stu-id="a4797-175">Decide on your organization’s overall device strategy for user and meeting room experiences.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="a4797-176">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a4797-176">Next steps</span></span></td><td><ul><li><span data-ttu-id="a4797-177">조직의 가상 장치 매핑 연습을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-177">Complete a persona-to-device mapping exercise for your organization.</span></span></li><li><span data-ttu-id="a4797-178">사용자 및 회의실에 대한 디바이스를 얻기 위한 프로세스를 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-178">Document the process for obtaining devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="a4797-179">사용자 및 회의실에 대한 디바이스 배포 및 구성 프로세스를 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-179">Document the process for deploying and configuration devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="a4797-180">배포를 시작할 초기 디바이스를 조달합니다.</span><span class="sxs-lookup"><span data-stu-id="a4797-180">Procure initial devices to begin your deployment.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->