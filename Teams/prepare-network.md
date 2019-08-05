---
title: Microsoft 팀을 위한 조직의 네트워크 준비
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: Microsoft 팀 네트워크를 준비 하 고 관리 하는 방법을 알아보세요. 정보에는 네트워크 요구 사항, 대역폭 요구 사항, 추가 고려 사항 등이 포함 됩니다.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d203aefa4ba6991fbe6cf6a2ac463f4649f2aaa9
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2019
ms.locfileid: "36184238"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="84da3-104">Microsoft 팀을 위한 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="84da3-104">Prepare your organization's network for Microsoft Teams</span></span>


<span data-ttu-id="84da3-105">팀은 다음 세 가지 트래픽 형태를 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-105">Teams combines three forms of traffic:</span></span>

-   <span data-ttu-id="84da3-106">Office 365 온라인 환경과 팀 클라이언트 간의 데이터 트래픽 (신호, 현재 상태, 채팅, 파일 업로드 및 다운로드, OneNote 동기화).</span><span class="sxs-lookup"><span data-stu-id="84da3-106">Data traffic between the Office 365 online environment and the Teams client (signaling, presence, chat, file upload and download, OneNote synchronization).</span></span>

-   <span data-ttu-id="84da3-107">피어 투 피어 실시간 통신 트래픽 (오디오, 비디오, 데스크톱 공유).</span><span class="sxs-lookup"><span data-stu-id="84da3-107">Peer-to-peer real-time communications traffic (audio, video, desktop sharing).</span></span>

-   <span data-ttu-id="84da3-108">회의 실시간 통신 트래픽 (오디오, 비디오, 데스크톱 공유).</span><span class="sxs-lookup"><span data-stu-id="84da3-108">Conferencing real-time communications traffic (audio, video, desktop sharing).</span></span>

<span data-ttu-id="84da3-109">이는 두 가지 수준의 네트워크에 영향을 주고 피어 투 피어 시나리오에 대 한 트래픽이 Microsoft 팀 클라이언트 간에 직접 전달 되며, 트래픽은 Office 365 환경과 모임 시나리오에 대 한 Microsoft 팀 클라이언트 간에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-109">This impacts the network on two levels: traffic will flow between the Microsoft Teams clients directly for peer-to-peer scenarios, and traffic will flow between the Office 365 environment and the Microsoft Teams clients for meeting scenarios.</span></span> <span data-ttu-id="84da3-110">트래픽 흐름을 최적화 하려면 내부 네트워크 세그먼트 (예: WAN을 통해 사이트 간)와 네트워크 사이트와 Office 365 사이에 모두 흐름을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-110">To ensure optimal traffic flow, traffic must be allowed to flow both between the internal network segments (for example, between sites over the WAN) as well as between the network sites and Office 365.</span></span> <span data-ttu-id="84da3-111">올바른 포트를 열지 않거나 특정 포트를 능동적으로 차단 하면 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-111">Not opening the correct ports or actively blocking specific ports will lead to a degraded experience.</span></span>

> [!NOTE]
> <span data-ttu-id="84da3-112">IOS 및 Android 모바일 장치에서 모임이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-112">Meetings are supported on iOS and Android mobile devices.</span></span> 

<span data-ttu-id="84da3-113">Microsoft 팀 내에서 실시간 미디어를 사용 하 여 최적의 환경을 얻으려면 네트워크가 Office 365의 네트워킹 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-113">To get an optimal experience with real time media within Microsoft Teams, your network must meet the networking requirements for Office 365.</span></span> <span data-ttu-id="84da3-114">자세한 내용은 [비즈니스용 Skype Online의 미디어 품질과 네트워크 연결 성능을](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84da3-114">For more information, see [Media Quality and Network Connectivity Performance for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).</span></span>

<span data-ttu-id="84da3-115">두 가지 네트워크 세그먼트 (클라이언트에서 Microsoft edge 및 고객에 게 Microsoft Edge에 대 한)를 정의 하려면 다음 권장 사항을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="84da3-115">For the two defining network segments (Client to Microsoft Edge and Customer Edge to Microsoft Edge), consider the following recommendations.</span></span>


|<span data-ttu-id="84da3-116">값</span><span class="sxs-lookup"><span data-stu-id="84da3-116">Value</span></span>  |<span data-ttu-id="84da3-117">클라이언트에서 Microsoft Edge로</span><span class="sxs-lookup"><span data-stu-id="84da3-117">Client to Microsoft Edge</span></span>  |<span data-ttu-id="84da3-118">고객 Edge에서 Microsoft Edge로</span><span class="sxs-lookup"><span data-stu-id="84da3-118">Customer Edge to Microsoft Edge</span></span>  |
|:--- |:--- |:--- |
|<span data-ttu-id="84da3-119">**대기 시간 (단방향)**\*</span><span class="sxs-lookup"><span data-stu-id="84da3-119">**Latency (one way)** \*</span></span>  |<span data-ttu-id="84da3-120">< 50ms</span><span class="sxs-lookup"><span data-stu-id="84da3-120">< 50ms</span></span>          |<span data-ttu-id="84da3-121">< 30ms</span><span class="sxs-lookup"><span data-stu-id="84da3-121">< 30ms</span></span>         |
|<span data-ttu-id="84da3-122">**지연 (RTT 또는 왕복 시간)**\*</span><span class="sxs-lookup"><span data-stu-id="84da3-122">**Latency (RTT or Round-trip Time)** \*</span></span> |<span data-ttu-id="84da3-123">< 100ms</span><span class="sxs-lookup"><span data-stu-id="84da3-123">< 100ms</span></span>   |<span data-ttu-id="84da3-124">< 60ms</span><span class="sxs-lookup"><span data-stu-id="84da3-124">< 60ms</span></span> |
|<span data-ttu-id="84da3-125">**버스트 패킷 손실**</span><span class="sxs-lookup"><span data-stu-id="84da3-125">**Burst packet loss**</span></span>    |<span data-ttu-id="84da3-126">200ms 간격 중 10% <</span><span class="sxs-lookup"><span data-stu-id="84da3-126"><10% during any 200ms interval</span></span>         |<span data-ttu-id="84da3-127">200ms interval 동안 1% <</span><span class="sxs-lookup"><span data-stu-id="84da3-127"><1% during any 200ms interval</span></span>         |
|<span data-ttu-id="84da3-128">**패킷 손실**</span><span class="sxs-lookup"><span data-stu-id="84da3-128">**Packet loss**</span></span>     |<span data-ttu-id="84da3-129">15s 간격 중 1% <</span><span class="sxs-lookup"><span data-stu-id="84da3-129"><1% during any 15s interval</span></span>          |<span data-ttu-id="84da3-130">15s 기간 동안 0.1% <</span><span class="sxs-lookup"><span data-stu-id="84da3-130"><0.1% during any 15s interval</span></span>         |
|<span data-ttu-id="84da3-131">**패킷 간 도착 지터**</span><span class="sxs-lookup"><span data-stu-id="84da3-131">**Packet inter-arrival Jitter**</span></span>    |<span data-ttu-id="84da3-132">15s 간격 중 30ms <</span><span class="sxs-lookup"><span data-stu-id="84da3-132"><30ms during any 15s interval</span></span>         |<span data-ttu-id="84da3-133">모든 15s 기간 동안 15ms <</span><span class="sxs-lookup"><span data-stu-id="84da3-133"><15ms during any 15s interval</span></span>         |
|<span data-ttu-id="84da3-134">**패킷 순서 다시 매기기**</span><span class="sxs-lookup"><span data-stu-id="84da3-134">**Packet reorder**</span></span>    |<span data-ttu-id="84da3-135"><0.05% 주문 종료 패킷</span><span class="sxs-lookup"><span data-stu-id="84da3-135"><0.05% out-of-order packets</span></span>         |<span data-ttu-id="84da3-136"><0.01% 주문 종료 패킷</span><span class="sxs-lookup"><span data-stu-id="84da3-136"><0.01% out-of-order packets</span></span>         |

<span data-ttu-id="84da3-137">\*대기 시간 메트릭 대상은 회사 사이트 또는 사이트를 가정 하 고 Microsoft의 경계는 동일한 대륙에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-137">\* The latency metric targets assume your company site or sites and the Microsoft edges are on the same continent.</span></span>

<span data-ttu-id="84da3-138">Microsoft 네트워크에 지에 대 한 회사 사이트 연결에는 WiFi 또는 다른 무선 기술인 첫 번째 홉 네트워크 액세스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-138">Your company site connection to the Microsoft network edge includes first hop network access, which can be WiFi or another wireless technology.</span></span>

<span data-ttu-id="84da3-139">네트워크 성능 대상은 적절 한 대역폭과/또는 [QoS 계획](QoS-in-Teams.md)을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-139">The network performance targets assume proper bandwidth and/or [QoS planning](QoS-in-Teams.md).</span></span> <span data-ttu-id="84da3-140">즉, 네트워크 연결이 최대 부하에 도달 했을 때 요구 사항이 팀의 실시간 미디어 트래픽에 직접적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-140">In other words, the requirements apply directly to Teams real-time media traffic when the network connection is under a peak load.</span></span>

<span data-ttu-id="84da3-141">두 네트워크 세그먼트를 모두 테스트 하려면 [네트워크 평가 도구](https://go.microsoft.com/fwlink/?linkid=855799)를 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-141">To test both network segments, you can use the [Network Assessment Tool](https://go.microsoft.com/fwlink/?linkid=855799).</span></span> <span data-ttu-id="84da3-142">이 도구는 고객 네트워크에 지에 연결 된 PC와 직접 클라이언트 PC에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-142">This tool can be deployed on both the client PC directly and on a PC connected to the Customer Network Edge.</span></span> <span data-ttu-id="84da3-143">이 도구에는 제한 된 설명서가 포함 되어 있지만,이 도구를 사용 하는 방법에 대 한 더 깊은 문서는 [네트워크 준비 상태 평가](https://go.microsoft.com/fwlink/?linkid=855800)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-143">The tool includes limited documentation, but a deeper documentation around the usage of the tool can be found here: [Network Readiness Assessment](https://go.microsoft.com/fwlink/?linkid=855800).</span></span> <span data-ttu-id="84da3-144">이 네트워크 준비 평가를 실행 하 여 네트워크의 준비 상태를 확인 하 여 Microsoft 팀과 같은 실시간 미디어 응용 프로그램을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-144">By running this Network Readiness Assessment, you can validate your network’s readiness to run real-time media applications, such as Microsoft Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="84da3-145">이는 비즈니스용 Skype를 성공적으로 배포 하려는 고객을 위해 실행 하는 것과 동일한 네트워크 준비 평가입니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-145">This is the same Network Readiness Assessment that is recommended to be run for customers who are looking to successfully deploy Skype for Business.</span></span>


## <a name="bandwidth-requirements"></a><span data-ttu-id="84da3-146">대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="84da3-146">Bandwidth requirements</span></span>
<span data-ttu-id="84da3-147">Microsoft 팀은 네트워크 상태에 관계 없이 최상의 오디오, 비디오 및 콘텐츠 공유 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-147">Microsoft Teams gives you the best audio, video and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="84da3-148">변수 코덱에는 최소한의 영향으로 제한 된 대역폭 환경에서 미디어를 협상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-148">With variable codecs, media can be negotiated in limited bandwidth environments with minimal impact.</span></span> <span data-ttu-id="84da3-149">그러나 대역폭이 문제가 되지 않는 경우에는 최대 1080p 비디오 해상도, 최대 30fps, 콘텐츠의 경우 15fps, 고화질 오디오 등의 품질에 대해 경험을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-149">But where bandwidth is not a concern, experiences can be optimized for quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span>

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a><span data-ttu-id="84da3-150">추가 네트워크 고려 사항</span><span class="sxs-lookup"><span data-stu-id="84da3-150">Additional network considerations</span></span>
---------------

#### <a name="external-name-resolution"></a><span data-ttu-id="84da3-151">외부 이름 확인</span><span class="sxs-lookup"><span data-stu-id="84da3-151">External Name Resolution</span></span>

<span data-ttu-id="84da3-152">팀 클라이언트를 실행 하는 모든 클라이언트 컴퓨터가 Office 365에서 제공 하는 서비스를 검색 하기 위해 외부 DNS 쿼리를 확인할 수 있으며 방화벽이 액세스를 차단 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-152">Ensure that all the client computers running Teams client can resolve external DNS queries to discover the services provided by Office 365, and that your firewalls are not preventing access.</span></span> <span data-ttu-id="84da3-153">방화벽 포트를 구성 하는 방법에 대 한 자세한 내용은 [Office 365 url 및 IP 범위로](office-365-urls-ip-address-ranges.md)이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="84da3-153">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

#### <a name="nat-pool-size"></a><span data-ttu-id="84da3-154">NAT 풀 크기</span><span class="sxs-lookup"><span data-stu-id="84da3-154">NAT Pool Size</span></span>

<span data-ttu-id="84da3-155">여러 사용자/장치가 NAT (Network Address Translation) 또는 PAT (Port Address Translation)를 사용 하 여 Office 365에 액세스 하는 경우, 각 공용 라우팅 가능 IP 주소 뒤에 숨겨진 장치가 지원 되는 번호를 초과 하지 않는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-155">When multiple users/devices access Office 365 using Network Address Translation (NAT) or Port Address Translation (PAT), you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span>

<span data-ttu-id="84da3-156">이 위험을 줄이려면 포트 소모를 방지 하기 위해 적절 한 공용 IP 주소가 NAT 풀에 할당 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-156">To mitigate this risk, ensure adequate Public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="84da3-157">포트 소모를 통해 Office 365 서비스에 연결할 때 내부 최종 사용자 및 장치가 문제를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-157">Port exhaustion will cause internal end users and devices to face issues when connecting to the Office 365 services.</span></span> <span data-ttu-id="84da3-158">자세한 내용은 [Office 365의 NAT 지원을](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84da3-158">For more information, see [NAT support with Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).</span></span>

#### <a name="intrusion-detection-and-prevention-guidance"></a><span data-ttu-id="84da3-159">**침입 감지 및 예방 지침**</span><span class="sxs-lookup"><span data-stu-id="84da3-159">**Intrusion Detection and Prevention Guidance**</span></span>

<span data-ttu-id="84da3-160">아웃 바운드 연결에 대 한 추가 보안 계층에 대 한 침입 감지 및/또는 방지 시스템 (ID/i p)이 환경에 있는 경우 목적지에서 Office 365 Url을 사용 하는 모든 트래픽이 허용 목록 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-160">If your environment has an Intrusion Detection and/or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, ensure that any traffic with destination to Office 365 URLs is whitelisted.</span></span>

<a name="network-health-determination"></a><span data-ttu-id="84da3-161">네트워크 상태 결정</span><span class="sxs-lookup"><span data-stu-id="84da3-161">Network health determination</span></span>
-----------------

<span data-ttu-id="84da3-162">네트워크 내에서 Microsoft 팀을 구현 하는 경우 필요한 대역폭을 확보 하 고, 필요한 모든 IP 주소와 열려 있는 올바른 포트를 액세스 하 고, 실시간 미디어에 대 한 성능 요구 사항을 만족 하 고 있는지 확인 해야 합니다. .</span><span class="sxs-lookup"><span data-stu-id="84da3-162">When planning on the implementation of Microsoft Teams within your network, you must ensure you have the required bandwidth, you have access to all required IP addresses, the correct ports opened, and you are meeting the performance requirements for real-time media.</span></span>

<span data-ttu-id="84da3-163">이러한 조건을 충족 하지 못하는 경우에는 최종 사용자가 통화와 모임 중 품질이 좋지 않아 팀에서 최적의 환경을 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-163">If you know you will not meet these criteria, your end users will not get an optimal experience from Teams due to bad quality during calls and meetings.</span></span>

<span data-ttu-id="84da3-164">이러한 조건을 충족 하지 않으면 계속 하기 전에 기준에 맞는지 프로젝트를 일시 중지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-164">Should you not meet these criteria, this is the time to consider pausing the project to ensure you meet the criteria before continuing.</span></span>


|  |  |  |
|---------|---------|---------|
|![결정 지점을 나타내는 아이콘](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |<span data-ttu-id="84da3-166">판단 요점</span><span class="sxs-lookup"><span data-stu-id="84da3-166">Decision Point</span></span>         |<span data-ttu-id="84da3-167">실시간 미디어 지원에 대 한 네트워크 기능을 평가 했습니까?</span><span class="sxs-lookup"><span data-stu-id="84da3-167">Have you evaluated your network capabilities for supporting real time media?</span></span><br></br><span data-ttu-id="84da3-168">네트워크가 제대로 평가 되지 않았거나 리얼 시간 미디어를 지원 하지 않는 경우에는 네트워크 영향과 낮은 팀 환경을 줄이기 위해 영상 및 화면 공유 기능을 사용 하지 않도록 설정 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="84da3-168">If your network has not been properly assessed, or you know it will not support real time media, will you disable video and screen sharing capabilities to reduce network impact and poor Teams experiences?</span></span>         |
|![다음 단계를 나타내는 아이콘](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |<span data-ttu-id="84da3-170">다음 단계</span><span class="sxs-lookup"><span data-stu-id="84da3-170">Next Steps</span></span>         |<span data-ttu-id="84da3-171">알 수 없는 네트워크 품질: 네트워크가 실시간 미디어에 대 한 준비가 되었는지 확인 하기 위해 네트워크 준비 평가를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-171">Network Quality Unknown: Perform a Network Readiness Assessment to determine if your network is ready for Real Time Media.</span></span><br></br><span data-ttu-id="84da3-172">네트워크 품질 저하: 네트워크 재구성 단계를 수행 하 여 고품질 실시간 미디어에 적합 한 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-172">Network Quality Poor: Perform network remediation steps to provide a proper environment for high quality Real Time Media.</span></span><br></br><span data-ttu-id="84da3-173">네트워크 만족: 모든 IP 주소 및 포트에 대 한 액세스가 적절 한지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="84da3-173">Network Satisfactory: Ensure all IP addresses and ports are properly accessible.</span></span>           |

## <a name="related-topics"></a><span data-ttu-id="84da3-174">관련 항목</span><span class="sxs-lookup"><span data-stu-id="84da3-174">Related Topics</span></span>

[<span data-ttu-id="84da3-175">비디오: 네트워크 계획</span><span class="sxs-lookup"><span data-stu-id="84da3-175">Video: Network Planning</span></span>](https://aka.ms/teams-networking)
