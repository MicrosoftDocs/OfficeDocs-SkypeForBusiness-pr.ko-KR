---
title: Microsoft 팀의 사용자 환경 계획
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 팀 클라이언트 앱을 선택 하 고, 끝점 품질을 계획 하 고, Wi-fi 끝점을 배포 하기 위한 권장 사항을 얻고, 오디오 장치를 선택 합니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f12b80fa1914166d48860b15cda7a928ca94ece
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069199"
---
# <a name="plan-my-users-experience"></a><span data-ttu-id="3936b-103">내 사용자 환경 계획</span><span class="sxs-lookup"><span data-stu-id="3936b-103">Plan my users’ experience</span></span>

<span data-ttu-id="3936b-104">이 문서에서는 사용자 환경에 직접적인 영향을 주는 클라우드 음성 서비스 배포 요소를 적절 하 게 식별 하는 데 필요한 요구 사항에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-104">This article gives an overview of the requirements for properly identifying the elements of your cloud voice services deployment that directly affect your users’ experience.</span></span> <span data-ttu-id="3936b-105">배포 하기 전에 이러한 항목을 준비 하면 고품질의 사용자를 위한 안정적인 환경을 제공 하는 데 성공할 확률이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-105">By preparing for these items before deployment, you’ll increase your chances of successfully delivering a high-quality, reliable experience for users.</span></span> 

## <a name="client-deployment"></a><span data-ttu-id="3936b-106">클라이언트 배포</span><span class="sxs-lookup"><span data-stu-id="3936b-106">Client deployment</span></span>

<span data-ttu-id="3936b-107">Microsoft 팀에는 웹, 데스크톱 (Windows 및 Mac) 및 모바일 (Android 및 iOS)에 사용할 수 있는 클라이언트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-107">Microsoft Teams has clients available for web, desktop (Windows and Mac), and mobile (Android and iOS).</span></span> <span data-ttu-id="3936b-108">데스크톱 (Windows 및 Mac)과 모바일 클라이언트를 설치 하는 방법에 대 한 자세한 내용은 [Microsoft 팀 용 클라이언트 가져오기를](https://docs.microsoft.com/microsoftteams/get-clients)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3936b-108">For additional details about how the desktop (Windows and Mac) and mobile clients are installed, see [Get clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).</span></span>

## <a name="client-updates"></a><span data-ttu-id="3936b-109">클라이언트 업데이트</span><span class="sxs-lookup"><span data-stu-id="3936b-109">Client updates</span></span>

<span data-ttu-id="3936b-110">팀의 주요 이점 중 하나는 클라이언트가 자동으로 최신 상태로 유지 된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-110">One of the key benefits of Teams is that the client is kept up to date automatically.</span></span> <span data-ttu-id="3936b-111">PC 및 Mac의 클라이언트는 새 빌드를 확인 하는 백그라운드 프로세스를 사용 하 여 업데이트 되며 앱이 유휴 상태일 때 새 클라이언트를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-111">The clients on the PC and Mac are updated by using a background process that checks for new builds and downloads the new client when the app is idle.</span></span>

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a><span data-ttu-id="3936b-112">끝점 품질 계획</span><span class="sxs-lookup"><span data-stu-id="3936b-112">Plan for endpoint quality</span></span>

<span data-ttu-id="3936b-113">아래 다이어그램에서 볼 수 있듯이 끝점은 사용자에 게 품질 경험을 제공 하기 위한 중요 한 빌딩 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-113">As you can see from the diagram below, endpoints are an important building block in providing a quality experience for users.</span></span>

<span data-ttu-id="3936b-114">![품질의 세 가지 구성 요소를 설명 하는 다이어그램](media/plan-my-users-experience-image1.png "품질의 세 가지 구성 요소와 서비스 관리가 세 구성 요소를 모두 겹치는 방법을 설명 하는 다이어그램입니다. 끝점에 포커스를 둔 상태")</span><span class="sxs-lookup"><span data-stu-id="3936b-114">![Diagram describing the three components of quality](media/plan-my-users-experience-image1.png "Diagram describing the three components of quality, and how service management overlaps all three components. With a focus on endpoints.")</span></span>

<span data-ttu-id="3936b-115">팀 끝점은 Pc, Mac, 태블릿, 모바일 장치를 비롯 한 다양 한 장치에서 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-115">Teams endpoints can run on many devices, including PCs, Macs, tablets, and mobile devices.</span></span> <span data-ttu-id="3936b-116">장치의 기본 제공 마이크/스피커, 이어폰 또는 최적화 된 헤드셋을 사용 하는 것과 같이 장치를 포괄 하는 방법과 사용자가 디바이스에 연결 하는 방법을 경험해 보세요.</span><span class="sxs-lookup"><span data-stu-id="3936b-116">Part of the experience not only encompasses the device, but how a user connects to the device—for example, using the device’s built-in mic/speaker, earbuds, or an optimized headset.</span></span> <span data-ttu-id="3936b-117">최적화 된 헤드셋을 사용 하면 전체적인 사용자 환경이 보강 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-117">Using an optimized headset can enrich the overall user experience.</span></span>

<span data-ttu-id="3936b-118">끝점 계획에 대 한 다음 지침을 통해 조직에서 팀과 성공적으로 온 보 딩 환경을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-118">The following guidance on endpoint planning will help you ensure your organization has a successful onboarding experience with Teams.</span></span>

## <a name="endpoint-capability"></a><span data-ttu-id="3936b-119">끝점 기능</span><span class="sxs-lookup"><span data-stu-id="3936b-119">Endpoint capability</span></span>

<span data-ttu-id="3936b-120">계획의 첫 번째 부분은 조직의 모든 Pc와 다른 장치에서 팀을 실행할 수 있는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-120">The first part of planning is to ensure all the PCs and other devices in your organization can run Teams.</span></span> <span data-ttu-id="3936b-121">여기에는 하드웨어 요구 사항이 아닌 PC가 백그라운드에서 수행 하는 작업을 이해 하는 것이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-121">This involves not just looking at the hardware requirements, but also understanding what else the PC is doing in the background.</span></span> <span data-ttu-id="3936b-122">많은 조직이 침입 감지 시스템 및 맬웨어 방지 소프트웨어를 포함 하 여 다른 소프트웨어를 실행 하 여 디바이스의 기본 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-122">Many organizations run other software, including intrusion detection systems and antimalware software, which can affect the base performance of a device.</span></span>

<span data-ttu-id="3936b-123">각 플랫폼 (웹, 데스크톱, 모바일)의 팀 클라이언트에 대 한 소프트웨어 요구 사항에 대 한 자세한 내용은 [Microsoft 팀 용 클라이언트 가져오기를](https://docs.microsoft.com/microsoftteams/get-clients)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3936b-123">For information about the software requirements for Teams clients on each platform (web, desktop, and mobile), see [Get clients for Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).</span></span>

## <a name="endpoint-firewalls"></a><span data-ttu-id="3936b-124">끝점 방화벽</span><span class="sxs-lookup"><span data-stu-id="3936b-124">Endpoint firewalls</span></span>

<span data-ttu-id="3936b-125">클라이언트쪽 방화벽은 사용자 환경에 큰 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-125">Client-side firewalls can have a significant impact on the user experience.</span></span>
<span data-ttu-id="3936b-126">클라이언트 쪽 방화벽은 통화 설정 방지 외에도 통화 음질에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-126">Client-side firewalls can affect call quality in addition to preventing a call from being established.</span></span> <span data-ttu-id="3936b-127">[Office 365 url 및 IP 주소 범위](https://aka.ms/o365ips)에 대 한 정보를 기반으로 클라이언트 방화벽에서 적절 하지 않은 예외를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-127">Configure the appropriate exclusions on the client firewall based on the information in [Office 365 URLs and IP address ranges](https://aka.ms/o365ips).</span></span> <span data-ttu-id="3936b-128">타사 공급 업체는 제외를 만드는 방법에 대 한 특정 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-128">Your third-party vendor will have specific guidance on how to create the exclusions.</span></span>

>[!NOTE]
> <span data-ttu-id="3936b-129">Microsoft 팀은 적절 한 방화벽 구성을 사용 하 여 Windows 방화벽을 자동으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-129">Microsoft Teams will automatically update the Windows Firewall with an appropriate firewall configuration.</span></span>

## <a name="wi-fi-recommendations-for-endpoints"></a><span data-ttu-id="3936b-130">끝점에 대 한 wi-fi 권장 사항</span><span class="sxs-lookup"><span data-stu-id="3936b-130">Wi-Fi recommendations for endpoints</span></span>

<span data-ttu-id="3936b-131">Microsoft 팀에서 실시간 작업 부하를 지원 하기 위해 최적화 된 Wi-fi 네트워크를 배포 하는 계획은 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-131">It takes significant planning to deploy an optimized Wi-Fi network to support real-time workloads in Microsoft Teams.</span></span> <span data-ttu-id="3936b-132">다음 섹션에서는 끝점을 계획할 때 일반적인 문제를 방지 하는 데 도움이 될 수 있는 몇 가지 일반적인 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-132">The following sections provide some general guidance that can help you avoid common pitfalls when planning for endpoints.</span></span>

### <a name="wi-fi-drivers"></a><span data-ttu-id="3936b-133">Wi-fi 드라이버</span><span class="sxs-lookup"><span data-stu-id="3936b-133">Wi-Fi drivers</span></span>

<span data-ttu-id="3936b-134">일부 Wi-fi 드라이버에는 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-134">Some Wi-Fi drivers can be problematic.</span></span> <span data-ttu-id="3936b-135">예를 들어 드라이버는 액세스 지점 간에 매우 적극적인 로밍 동작을 사용 하 여 낮은 통화 품질을 유발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-135">As an example, a driver might have very aggressive roaming behaviors between access points, causing poor call quality.</span></span>
<span data-ttu-id="3936b-136">이는 일반적인 경우가 아니지만 PC의 Wi-fi 드라이버가 배포 전에 업데이트 되 고 테스트 되었는지 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-136">This isn’t a common occurrence, but it’s important to ensure that Wi-Fi drivers on the PC have been updated and tested prior to deployment.</span></span>

### <a name="wi-fi-bands"></a><span data-ttu-id="3936b-137">Wi-fi 밴드</span><span class="sxs-lookup"><span data-stu-id="3936b-137">Wi-Fi bands</span></span>

<span data-ttu-id="3936b-138">현재 Wi-fi 장비에 사용 되는 밴드에는 주로 2.4 GHz 및 5.0 GHz의 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-138">There are primarily two types of bands used in Wi-Fi equipment today, 2.4 GHz and 5.0 GHz.</span></span> <span data-ttu-id="3936b-139">조직에서 두 밴드를 모두 제공 하는 경우 5.0 GHz 밴드를 선호 하도록 드라이버 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-139">If your organization provides both bands, you should configure your driver settings to prefer the 5.0 GHz band.</span></span> <span data-ttu-id="3936b-140">이 밴드는 처리량 측면에서 훨씬 denser, 2.4 GHz 밴드에 표시 되는 간섭의 영향을 덜 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-140">This band is much denser in terms of throughput and is less affected by the interference seen in the 2.4 GHz band.</span></span>
<span data-ttu-id="3936b-141">이 권장 사항은 5.0 GHz 네트워크 대역을 적절 하 게 최적화 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-141">This recommendation assumes that you’ve properly optimized the 5.0 GHz network band.</span></span>

### <a name="wi-fi-radio-type"></a><span data-ttu-id="3936b-142">Wi-fi 송수신 장치 유형</span><span class="sxs-lookup"><span data-stu-id="3936b-142">Wi-Fi radio type</span></span>

<span data-ttu-id="3936b-143">최신 Wi-fi 라디오 형식을 지 원하는 장치에 대 한 계획</span><span class="sxs-lookup"><span data-stu-id="3936b-143">Plan for devices that support the newer Wi-Fi radio types.</span></span> <span data-ttu-id="3936b-144">프로 비전 하는 장치에서 802.11 ac 이상을 이용 하는 경우 Wi-fi 성능이 매우 우수한 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-144">You can get very good Wi-Fi performance if you leverage 802.11ac or newer on the devices you provision.</span></span>

### <a name="wireless-avoidance"></a><span data-ttu-id="3936b-145">무선 방지</span><span class="sxs-lookup"><span data-stu-id="3936b-145">Wireless avoidance</span></span>

<span data-ttu-id="3936b-146">일부 조직에서는 Wi-fi를 전혀 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-146">Some organizations prefer to avoid Wi-Fi altogether.</span></span> <span data-ttu-id="3936b-147">때로는 사용자에 게 유선 네트워크에 직접 연결 하는 권장 사항을 통해이 지침이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-147">Sometimes this guidance is provided through a recommendation to users to connect directly to a wired network.</span></span> <span data-ttu-id="3936b-148">경우에 따라 네트워크 바인딩 순서에 무선 연결이 기본 설정 되어 있는 경우 PC가 유선 연결에 연결 된 경우에도 해당 연결을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-148">In some cases, the network binding order might have the wireless connection preferred and continue to use that connection even though the PC is connected to the wired connection.</span></span> <span data-ttu-id="3936b-149">의도 하지 않은이 동작을 방지 하려면이 시나리오를 방지 하기 위해 바인딩 순서를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-149">To avoid this unintended behavior, configure the binding order to avoid this scenario.</span></span>

### <a name="80211-power-save-protocol"></a><span data-ttu-id="3936b-150">802.11 전원 절약 프로토콜</span><span class="sxs-lookup"><span data-stu-id="3936b-150">802.11 Power Save protocol</span></span>

<span data-ttu-id="3936b-151">조직에서 802.11 절전 프로토콜을 지원 하지 않는 무선 액세스 지점 또는 라우터를 사용 하는 경우 Windows 장치에서 실행 되는 Microsoft 팀에서 호출이 손실 되거나 잘못 된 통화 품질이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-151">If your organization uses wireless access points or routers that don’t support the 802.11 Power Save protocol, you might experience dropped calls or poor call quality in Microsoft Teams running on Windows devices.</span></span> <span data-ttu-id="3936b-152">무선 액세스 지점이 나 라우터를 업그레이드할 수 없는 경우 배터리 전원으로 실행 되는 장치에서 Windows 전원 관리 옵션 설정을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-152">If it’s not possible to upgrade your wireless access point or routers, you should update Windows Power Plan settings on devices that run on battery power.</span></span> <span data-ttu-id="3936b-153">자세한 내용 및 구성 지침은 다음 [지원 문서](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-153">Further detail and configuration guidance is provided in the following [support article](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="3936b-154">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="3936b-154">Decision points</span></span></td><td><ul><li><span data-ttu-id="3936b-155">조직에 배포할 팀 클라이언트는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="3936b-155">What Teams clients will be deployed in your organization?</span></span></li><li><span data-ttu-id="3936b-156">처음에 팀 클라이언트를 사용자에 게 배포 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="3936b-156">How will you initially deploy Teams clients to your users?</span></span></li><li><span data-ttu-id="3936b-157">끝점 및 장치를 평가 하 여 품질 경험을 위한 팀 요구 사항에 맞는지 확인 하는 책임은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="3936b-157">Who is responsible for evaluating endpoints and devices to validate they meet Teams requirements for a quality experience?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="3936b-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3936b-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="3936b-159">팀 클라이언트를 배포 하기 위해 팔 로우 하는 프로세스를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-159">Document the process that will be followed to deploy Teams clients.</span></span></li><li><span data-ttu-id="3936b-160">끝점 및 장치를 평가 하 고 필요한 경우 업데이트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-160">Evaluate endpoints and devices and perform and remediation required.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a><span data-ttu-id="3936b-161">팀 장치</span><span class="sxs-lookup"><span data-stu-id="3936b-161">Devices for Teams</span></span>

<span data-ttu-id="3936b-162">Microsoft 팀은 모임 또는 전화 시스템에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-162">Microsoft Teams can be used for meetings or as a phone system.</span></span> <span data-ttu-id="3936b-163">이러한 기능을 사용 하는 경우 팀에 사용 되는 인터페이스 디바이스는 사용자 환경에서 중요 한 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-163">When using these features, the interface device that is used for Teams plays an important role in the user experience.</span></span>

<span data-ttu-id="3936b-164">기본 제공 PC 스피커와 마이크를 사용 하는 것은 해당 구성을 가진 사용자가 수용할 수 있는 음질입니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-164">Using a built-in PC speaker and microphone might sound acceptable to the user who has that configuration.</span></span> <span data-ttu-id="3936b-165">그러나 일반적으로 이러한 장치는 노이즈 취소에 최적화 되지 않으며, 모든 유형의 앰비언트 노이즈는 통화 중에 다른 사용자에 게 다운스트림에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-165">But typically, those devices aren’t optimized for noise cancellation, and any type of ambient noise can have a downstream impact on others on the call.</span></span> <span data-ttu-id="3936b-166">이러한 시나리오에 최적화 된 장치를 활용 하면 고품질 환경을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-166">Leveraging devices optimized for these scenarios will help ensure a high-quality experience.</span></span>

<span data-ttu-id="3936b-167">각 장치는 사용자의 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-167">Each device needs to meet the needs of your users.</span></span> <span data-ttu-id="3936b-168">조직의 다른 가상 사용자 및 사용 사례에 대 한 헤드셋 등의 장치를 조직에 맞게 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-168">You’ll need to tailor devices such as headsets for the different personas and use cases in your organization.</span></span>
<span data-ttu-id="3936b-169">사용자 대 장치 매핑 연습은 계획 프로세스의 일부로 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-169">A persona-to-device mapping exercise should be completed as part of the planning process.</span></span>

<span data-ttu-id="3936b-170">장치를 선택한 후 파일럿 테스트 계획에 최종 유효성 검사에 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-170">After you’ve selected the devices, include them in the pilot test plan for final validation.</span></span> <span data-ttu-id="3936b-171">파일럿에서 설문 조사를 활용 하 여 피드백을 수집 하 여 디바이스 전략이 최적화 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-171">Leverage surveys during the pilot to collect feedback to ensure your device strategy is optimal.</span></span>

> [!NOTE]
> <span data-ttu-id="3936b-172">이번에는 비즈니스용 Skype 인증 프로그램을 통해 인증 된 오디오 장치를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-172">At this time, we recommend using audio devices that were certified through the Skype for Business Certification program.</span></span> <span data-ttu-id="3936b-173">이 프로그램에서 인증 된 장치를 찾으려면 [Microsoft 팀 디바이스](https://products.office.com/en-us/microsoft-teams/across-devices/devices) 및 [USB 오디오 및 비디오 장치](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3936b-173">To find devices certified under this program, see the [Microsoft Teams devices](https://products.office.com/en-us/microsoft-teams/across-devices/devices) and [USB audio and video devices](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices).</span></span>



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="3936b-174">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="3936b-174">Decision points</span></span></td><td><ul><li><span data-ttu-id="3936b-175">사용자 및 회의실 환경에 대 한 조직의 전반적인 디바이스 전략을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-175">Decide on your organization’s overall device strategy for user and meeting room experiences.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="3936b-176">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3936b-176">Next steps</span></span></td><td><ul><li><span data-ttu-id="3936b-177">조직에 대 한 가상 사용자 대 장치 매핑 연습을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-177">Complete a persona-to-device mapping exercise for your organization.</span></span></li><li><span data-ttu-id="3936b-178">사용자 및 회의실에 대 한 장치를 가져오기 위한 프로세스를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-178">Document the process for obtaining devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="3936b-179">사용자 및 회의실에 맞게 장치를 배포 하 고 구성 하는 프로세스를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="3936b-179">Document the process for deploying and configuration devices for users and meeting rooms.</span></span></li><li><span data-ttu-id="3936b-180">배포를 시작 하는 초기 장치를 조달 하세요.</span><span class="sxs-lookup"><span data-stu-id="3936b-180">Procure initial devices to begin your deployment.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
