---
title: 직접 라우팅을 위한 미디어 바이패스 계획
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 직접 라우팅을 사용하여 미디어 전화 시스템 계획하는 방법을 알아보고 미디어 트래픽 경로를 단축하고 성능을 향상시킬 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d60513dbcf1128d303102f494600a67335b366d
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075401"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="5d84a-103">직접 라우팅을 위한 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="5d84a-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="5d84a-104">직접 라우팅을 통해 미디어 우회에 대해</span><span class="sxs-lookup"><span data-stu-id="5d84a-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="5d84a-105">미디어 우회를 사용하면 미디어 트래픽 경로를 단축하고 더 나은 성능을 위해 전송되는 홉 수를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="5d84a-106">미디어 우회를 통해 미디어는 SBC(세션 테두리 컨트롤러)와 클라이언트 간에 유지되는 대신 Microsoft 전화 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="5d84a-107">미디어 우회를 구성하려면 SBC와 클라이언트가 동일한 위치 또는 네트워크에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="5d84a-108">**-MediaBypass** 매개 변수가 true 또는 false로 설정된 **Set-CSOnlinePSTNGateway** 명령을 사용하여 각 SBC에 대한 미디어 우회를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="5d84a-109">미디어 우회를 사용하도록 설정하는 경우 모든 미디어 트래픽이 회사 네트워크 내에 유지되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="5d84a-110">이 문서에서는 다양한 시나리오에서 호출 흐름을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-110">This article describes the call flow in different scenarios.</span></span>

<span data-ttu-id="5d84a-111">아래 다이어그램은 미디어 우회와 없는 호출 흐름의 차이를 보여 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="5d84a-112">미디어 우회 없이 클라이언트가 호출을 만들거나 받을 때 다음 다이어그램과 같이 SBC, Microsoft 전화 시스템 및 Teams 클라이언트 간에 신호 및 미디어 흐름이 모두 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5d84a-113">![미디어 우회 없이 신호 및 미디어 흐름 표시](media/direct-routing-media-bypass-1.png)</span><span class="sxs-lookup"><span data-stu-id="5d84a-113">![Shows signaling and media flow without media bypass](media/direct-routing-media-bypass-1.png)</span></span>


<span data-ttu-id="5d84a-114">그러나 사용자가 SBC와 동일한 건물 또는 네트워크에 있는 것으로 가정해 가정해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="5d84a-115">예를 들어 프랑크푸르트의 건물에 있는 사용자가 PSTN 사용자에게 전화를 걸었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="5d84a-116">**미디어 우회** 없이는 미디어가 암스테르담 또는 더블린(Microsoft 데이터 센터가 배포되는 곳)을 통해 다시 프랑크푸르트의 SBC로 흐르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="5d84a-117">유럽의 데이터 센터는 SBC가 유럽에 있으며 Microsoft는 SBC에 가장 가까운 데이터 센터를 사용하기 때문에 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="5d84a-118">이 접근 방식은 대부분의 지리에서 Microsoft 네트워크 내의 트래픽 흐름 최적화로 인해 통화 품질에 영향을 주지는 하지만 트래픽에는 불필요한 루프가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="5d84a-119">**미디어 우회를** 사용하면 다음 다이어그램에 표시된 Teams 사용자와 SBC 간에 미디어가 직접 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="5d84a-120">![미디어 우회를 통해 신호 및 미디어 흐름 표시](media/direct-routing-media-bypass-2.png)</span><span class="sxs-lookup"><span data-stu-id="5d84a-120">![Shows signaling and media flow with media bypass](media/direct-routing-media-bypass-2.png)</span></span>

<span data-ttu-id="5d84a-121">미디어 우회는 SBC의 클라이언트 및 ICE 라이트의 Teams ICE(Interactive Connectivity Establishment)라는 프로토콜을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="5d84a-122">이러한 프로토콜을 사용하면 직접 라우팅이 최적의 품질을 위해 가장 직접적인 미디어 경로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="5d84a-123">ICE 및 ICE Lite는 WebRTC 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="5d84a-124">이러한 프로토콜에 대한 자세한 내용은 RFC 5245를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d84a-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="5d84a-125">통화 흐름 및 방화벽 계획</span><span class="sxs-lookup"><span data-stu-id="5d84a-125">Call flow and firewall planning</span></span>

<span data-ttu-id="5d84a-126">통화 흐름 및 방화벽 계획은 사용자가 SBC의 공용 IP 주소에 직접 액세스할 수 있는지 여부와 사용자가 네트워크 내부 또는 외부에 있는지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="5d84a-127">사용자가 SBC의 공용 IP 주소에 직접 액세스하는 경우 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="5d84a-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="5d84a-128">사용자가 SBC의 공용 IP 주소에 직접 액세스할 수 있는 경우 호출 흐름은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="5d84a-129">미디어 우회의 경우 Teams 클라이언트는 내부 네트워크에서도 SBC의 공용 IP 주소에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="5d84a-130">직접 미디어를 원하지 않는 경우 미디어는 전송 릴레이를 통해 흐를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="5d84a-131">이 솔루션은 사용자가 SBC와 동일한 건물 및/또는 네트워크에 있는 경우 권장되는 솔루션입니다. 미디어 경로에서 Microsoft Cloud 구성 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="5d84a-132">신호는 항상 Microsoft 클라우드를 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="5d84a-133">다음 다이어그램은 미디어 우회를 사용하도록 설정하고 클라이언트가 내부 상태일 때 호출 흐름을 보여 주며, 클라이언트가 SBC(직접 미디어)의 공용 IP 주소에 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="5d84a-134">경로의 화살표 및 숫자 값은 호출 흐름에 [Microsoft Teams 있습니다.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="5d84a-134">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="5d84a-135">SIP 신호는 항상 경로 4 및 4'(트래픽 방향에 따라 다를 수 있습니다)를 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-135">The SIP signaling always takes paths 4 and 4' (depending on the direction of the traffic).</span></span> <span data-ttu-id="5d84a-136">미디어는 로컬로 유지하며 경로 5b를 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-136">Media stays local and takes path 5b.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5d84a-137">![Media Bypass를 사용하도록 설정한 통화 흐름 표시, 클라이언트가 내부](media/direct-routing-media-bypass-3.png)</span><span class="sxs-lookup"><span data-stu-id="5d84a-137">![Shows Call flow with Media Bypass enabled, client is internal](media/direct-routing-media-bypass-3.png)</span></span>


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="5d84a-138">사용자가 SBC의 공용 IP 주소에 액세스할 수 없는 경우 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="5d84a-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="5d84a-139">다음에서는 사용자가 SBC의 공용 IP 주소에 액세스할 수 없는 경우 호출 흐름을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="5d84a-140">예를 들어 사용자가 외부인 것으로 가정하고 테넌트 관리자는 인터넷의 모든 사용자에게 SBC의 공용 IP 주소를 열지 말고 Microsoft Cloud에만 열지로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="5d84a-141">트래픽의 내부 구성 요소는 전송 릴레이를 통해 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="5d84a-142">다음과 같은 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-142">Consider the following:</span></span>

- <span data-ttu-id="5d84a-143">Teams 전송 릴레이가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-143">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="5d84a-144">미디어 우회의 경우 Microsoft는 전송 릴레이와 SBC 간에 포트 50 000에서 59 999 포트를 여는 데 필요한 전송 릴레이 버전을 Teams(향후 3478-3481 포트가 필요한 버전으로 이동할 계획).</span><span class="sxs-lookup"><span data-stu-id="5d84a-144">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires 3478-3481 ports).</span></span>


<span data-ttu-id="5d84a-145">다음 다이어그램은 미디어 우회를 사용하도록 설정하고 클라이언트가 외부 상태일 때 호출 흐름을 보여 주며, 클라이언트가 세션 테두리 컨트롤러의 공용 IP 주소에 도달할 수 없는 경우(미디어는 전송 Teams 릴레이로 릴레이됩니다).</span><span class="sxs-lookup"><span data-stu-id="5d84a-145">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="5d84a-146">경로의 화살표 및 숫자 값은 호출 흐름에 [Microsoft Teams 있습니다.](./microsoft-teams-online-call-flows.md)</span><span class="sxs-lookup"><span data-stu-id="5d84a-146">The arrows and numeric values of the paths are in accordance with [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md).</span></span>

- <span data-ttu-id="5d84a-147">미디어는 경로 3, 3', 4 및 4'를 통해 릴레이됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-147">Media is relayed via paths 3, 3', 4 and 4'</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5d84a-148">![사용자가 SBC의 공용 IP에 액세스할 수 없는 경우 통화 흐름 표시](media/direct-routing-media-bypass-4.png)</span><span class="sxs-lookup"><span data-stu-id="5d84a-148">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-4.png)</span></span>


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="5d84a-149">사용자가 네트워크 외부에 있으며 SBC의 공용 IP에 대한 액세스 권한이 있는 경우 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="5d84a-149">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="5d84a-150">전송 릴레이를 활용하지 못하기 때문에 권장되는 Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-150">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="5d84a-151">대신 사용자가 SBC의 공용 IP 주소에 액세스할 수 없는 이전 시나리오를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-151">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="5d84a-152">다음 다이어그램은 미디어 우회를 사용하도록 설정하고, 클라이언트가 외부에 있으며, 클라이언트가 SBC(직접 미디어)의 공용 IP 주소에 도달할 수 있는 호출 흐름을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-152">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="5d84a-153">경로의 화살표 및 숫자 값은 호출 흐름 문서의 Microsoft Teams [따라야](./microsoft-teams-online-call-flows.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-153">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](./microsoft-teams-online-call-flows.md) article.</span></span>

- <span data-ttu-id="5d84a-154">SIP 신호는 항상 경로 3 및 3'(트래픽 방향에 따라 다를 수 있습니다.)을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-154">The SIP signaling always takes paths 3 and 3' (depending on the direction of the traffic).</span></span> <span data-ttu-id="5d84a-155">경로 2를 사용하여 미디어 흐름입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-155">Media flows using path 2.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5d84a-156">![사용자가 SBC의 공용 IP에 액세스할 수 없는 경우 통화 흐름 표시](media/direct-routing-media-bypass-5.png)</span><span class="sxs-lookup"><span data-stu-id="5d84a-156">![Shows Call flow if user does not have access to public IP of the SBC](media/direct-routing-media-bypass-5.png)</span></span>


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="5d84a-157">미디어 프로세서 및 전송 릴레이 사용</span><span class="sxs-lookup"><span data-stu-id="5d84a-157">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="5d84a-158">Microsoft Cloud에는 미디어 트래픽 경로에 있는 미디어 프로세서 및 전송 릴레이의 두 가지 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-158">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="5d84a-159">Media Processor는 비우회 사례에서 미디어를 처리하고 음성 애플리케이션용 미디어를 처리하는 공용 직면 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-159">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="5d84a-160">미디어 프로세서는 항상 최종 사용자가 우회되지 않은 호출에 대한 경로에 있지만, 우회 호출 경로에는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-160">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="5d84a-161">Media Processor는 호출 공원, 조직 자동 전화 교환 큐와 같은 모든 음성 애플리케이션에 대해 항상 경로에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-161">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="5d84a-162">전송 릴레이는 가장 가까운 전송 서비스에 연결하여 실시간 트래픽을 전송하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-162">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="5d84a-163">전송 릴레이는 사용자가 어디에 있는지, 네트워크가 구성되는 방식에 따라 우회 호출 경로에 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-163">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="5d84a-164">다음 다이어그램은 미디어 우회를 사용하도록 설정한 호출 흐름과 미디어 우회를 사용하지 않도록 설정한 두 번째 호출 흐름을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-164">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span>

> [!NOTE]
> <span data-ttu-id="5d84a-165">다이어그램은 종단 사용자 또는 종단 사용자로부터 시작된 트래픽만 보여 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-165">The diagram only illustrates traffic originating from--or destined to--end users.</span></span>  

- <span data-ttu-id="5d84a-166">Media Controller는 미디어 프로세서를 할당하고 SDP(세션 설명 프로토콜) 제안을 만드는 Azure의 마이크로 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-166">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="5d84a-167">SIP 프록시는 SIP에 사용되는 HTTP REST 신호를 SIP로 Teams 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-167">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5d84a-168">![Media Bypass를 사용하도록 설정하고 사용하지 않도록 설정한 통화 흐름 표시](media/direct-routing-media-bypass-6.png)</span><span class="sxs-lookup"><span data-stu-id="5d84a-168">![Shows call flows with Media Bypass enabled and disabled](media/direct-routing-media-bypass-6.png)</span></span>


<span data-ttu-id="5d84a-169">아래 표에서는 Media Processor와 전송 릴레이의 차이점을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-169">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="5d84a-170">미디어 프로세서</span><span class="sxs-lookup"><span data-stu-id="5d84a-170">Media Processors</span></span> | <span data-ttu-id="5d84a-171">전송 릴레이</span><span class="sxs-lookup"><span data-stu-id="5d84a-171">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="5d84a-172">최종 사용자의 비우회 호출에 대한 미디어 경로에서</span><span class="sxs-lookup"><span data-stu-id="5d84a-172">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="5d84a-173">항상</span><span class="sxs-lookup"><span data-stu-id="5d84a-173">Always</span></span> | <span data-ttu-id="5d84a-174">클라이언트가 Media Processor에 직접 도달할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="5d84a-174">If client cannot reach the Media Processor directly</span></span> | 
<span data-ttu-id="5d84a-175">최종 사용자의 우회 호출에 대한 미디어 경로에서</span><span class="sxs-lookup"><span data-stu-id="5d84a-175">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="5d84a-176">절대로 안</span><span class="sxs-lookup"><span data-stu-id="5d84a-176">Never</span></span> | <span data-ttu-id="5d84a-177">클라이언트가 공용 IP 주소에서 SBC에 도달할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="5d84a-177">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="5d84a-178">음성 애플리케이션의 미디어 경로에서</span><span class="sxs-lookup"><span data-stu-id="5d84a-178">In media path for voice applications</span></span> | <span data-ttu-id="5d84a-179">항상</span><span class="sxs-lookup"><span data-stu-id="5d84a-179">Always</span></span> | <span data-ttu-id="5d84a-180">절대로 안</span><span class="sxs-lookup"><span data-stu-id="5d84a-180">Never</span></span> | 
<span data-ttu-id="5d84a-181">트랜스코드를 할 수 있습니다(B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="5d84a-181">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="5d84a-182">예</span><span class="sxs-lookup"><span data-stu-id="5d84a-182">Yes</span></span> | <span data-ttu-id="5d84a-183">아니요, 엔드포인트 간에 오디오만 릴레이</span><span class="sxs-lookup"><span data-stu-id="5d84a-183">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="5d84a-184">전 세계 인스턴스 수 및 위치</span><span class="sxs-lookup"><span data-stu-id="5d84a-184">Number of instances worldwide and location</span></span> | <span data-ttu-id="5d84a-185">총 10개: 미국 동부 및 서부에서 2개; 암스테르담 및 더블린에서 2개; 홍콩 및 싱가포르에서 2개; 일본에서 2; 오스트레일리아 동부 및 남동부의 2</span><span class="sxs-lookup"><span data-stu-id="5d84a-185">10 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan ; 2 in Australia East and Southeast</span></span> | <span data-ttu-id="5d84a-186">다중</span><span class="sxs-lookup"><span data-stu-id="5d84a-186">Multiple</span></span>

<span data-ttu-id="5d84a-187">IP 범위는:</span><span class="sxs-lookup"><span data-stu-id="5d84a-187">The IP ranges are:</span></span>
- <span data-ttu-id="5d84a-188">52.112.0.0/14(52.112.0.1에서 52.115.255.254까지의 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="5d84a-188">52.112.0.0/14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>
- <span data-ttu-id="5d84a-189">52.120.0.0/14(52.120.0.1에서 52.123.255.254까지의 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="5d84a-189">52.120.0.0/14 (IP addresses from 52.120.0.1 to 52.123.255.254)</span></span>

<span data-ttu-id="5d84a-190">\* 트랜스코드 설명:</span><span class="sxs-lookup"><span data-stu-id="5d84a-190">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="5d84a-191">Media Processor는 B2BUA로 코덱을 변경할 수 있습니다(예: SILK를 클라이언트에서 MP로Teams MP와 SBC 간에 G.711로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-191">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="5d84a-192">전송 릴레이는 B2BUA가 아니기 때문에 릴레이를 통해 트래픽이 흐르는 경우에도 클라이언트와 SBC 간에 코덱이 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-192">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="5d84a-193">미디어 Teams 트렁크를 구성하는 경우 미디어 프로세서 사용</span><span class="sxs-lookup"><span data-stu-id="5d84a-193">Use of Teams Media Processors if trunk is configured for media bypass</span></span>

<span data-ttu-id="5d84a-194">Teams 미디어 프로세서는 항상 다음 시나리오의 미디어 경로에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-194">Teams Media Processors are always inserted in the media path in the following scenarios:</span></span>

- <span data-ttu-id="5d84a-195">통화가 1:1에서 그룹 호출로 에스컬레이터됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-195">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="5d84a-196">페더리드된 사용자에 Teams 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-196">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="5d84a-197">통화가 다른 사용자에게 전달되거나 비즈니스용 Skype 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-197">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="5d84a-198">아래 설명된 바와 같이 SBC에서 Media Processor 및 전송 릴레이 범위에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-198">Ensure your SBC has access to the Media Processors and Transport Relays ranges as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="5d84a-199">SIP 신호: FQDNS</span><span class="sxs-lookup"><span data-stu-id="5d84a-199">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="5d84a-200">SIP 신호의 경우 FQDN 및 방화벽 요구 사항은 우회되지 않은 경우와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-200">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="5d84a-201">직접 라우팅은 다음 환경에서 Microsoft 365 Office 365 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-201">Direct Routing is offered in the following Microsoft 365 or Office 365 environments:</span></span>
- <span data-ttu-id="5d84a-202">Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="5d84a-202">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="5d84a-203">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="5d84a-203">Office 365 GCC</span></span>
- <span data-ttu-id="5d84a-204">Office 365 GCC 높음</span><span class="sxs-lookup"><span data-stu-id="5d84a-204">Office 365 GCC High</span></span>
- <span data-ttu-id="5d84a-205">Office 365 DoD는 Office 365, GCC, GCC 및 DoD와 같은 미국 정부 환경에 대해 자세히 알아보십시오. [](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government)</span><span class="sxs-lookup"><span data-stu-id="5d84a-205">Office 365 DoD Learn more about [Office 365 and US Government environments](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="5d84a-206">Microsoft 365, Office 365 및 Office 365 GCC 환경</span><span class="sxs-lookup"><span data-stu-id="5d84a-206">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

<span data-ttu-id="5d84a-207">직접 라우팅의 연결 지점은 다음 세 가지 FQDNS입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-207">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="5d84a-208">**sip.pstnhub.microsoft.com** FQDN - 먼저 시도해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-208">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="5d84a-209">SBC에서 이 이름을 확인하기 위한 요청을 보내면 SBC에 Microsoft Azure 기본 Azure 데이터 센터를 지적하는 IP 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-209">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="5d84a-210">할당은 데이터 센터의 성능 메트릭 및 SBC에 대한 지리적 근접성을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-210">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="5d84a-211">반환된 IP 주소는 기본 FQDN에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-211">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="5d84a-212">**sip2.pstnhub.microsoft.com** - 보조 FQDN – 지리적으로 두 번째 우선 순위 지역에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-212">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="5d84a-213">**sip3.pstnhub.microsoft.com** - Tertiary FQDN – 지리적으로 세 번째 우선 순위 지역에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-213">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="5d84a-214">다음을 위해 다음 세 개의 FQDNS를 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-214">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="5d84a-215">최적의 환경을 제공합니다(로드가 적고 첫 번째 FQDN을 쿼리하여 할당된 SBC 데이터 센터에 가장 가깝습니다).</span><span class="sxs-lookup"><span data-stu-id="5d84a-215">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="5d84a-216">일시적인 문제가 발생하는 데이터 센터에 SBC의 연결이 설정되면 장애 조치(failover)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-216">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="5d84a-217">자세한 내용은 아래 장애 조치 메커니즘을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d84a-217">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="5d84a-218">FQDNs **sip.pstnhub.microsoft.com** **,** sip2.pstnhub.microsoft.com 및 sip3.pstnhub.microsoft.com  다음 서브넷의 IP 주소로 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-218">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to IP addresses from the following subnets:</span></span>
- <span data-ttu-id="5d84a-219">52.112.0.0/14</span><span class="sxs-lookup"><span data-stu-id="5d84a-219">52.112.0.0/14</span></span>
- <span data-ttu-id="5d84a-220">52.120.0.0/14</span><span class="sxs-lookup"><span data-stu-id="5d84a-220">52.120.0.0/14</span></span>

<span data-ttu-id="5d84a-221">신호에 대한 주소와 수신 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 범위에 대한 포트를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-221">You need to open ports for all these IP ranges in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="5d84a-222">방화벽이 DNS 이름을 지원하는 경우 FQDN  sip-all.pstnhub.microsoft.com 모든 IP 서브넷으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-222">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP subnets.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="5d84a-223">Office 365 GCC DoD 환경</span><span class="sxs-lookup"><span data-stu-id="5d84a-223">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="5d84a-224">직접 라우팅의 연결 지점은 다음 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-224">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="5d84a-225">**sip.pstnhub.dod.teams.microsoft.us** - 글로벌 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-225">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="5d84a-226">DoD Office 365 미국 데이터 센터에만 존재하기 때문에 보조 및 세로 FQDNS가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-226">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="5d84a-227">FQDN sip.pstnhub.dod.teams.microsoft.us 다음 서브넷의 IP 주소로 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-227">The FQDN sip.pstnhub.dod.teams.microsoft.us will be resolved to an IP address from the following subnet:</span></span>

- <span data-ttu-id="5d84a-228">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="5d84a-228">52.127.64.0/21</span></span>

<span data-ttu-id="5d84a-229">신호에 대한 주소와 수신 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 범위에 대한 포트를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-229">You need to open ports for all these IP ranges in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="5d84a-230">방화벽이 DNS 이름을 지원하는 경우 FQDN sip.pstnhub.dod.teams.microsoft.us 모든 IP 서브넷으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-230">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP subnets.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="5d84a-231">Office 365 GCC 환경</span><span class="sxs-lookup"><span data-stu-id="5d84a-231">Office 365 GCC High environment</span></span>

<span data-ttu-id="5d84a-232">직접 라우팅의 연결 지점은 다음 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-232">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="5d84a-233">**sip.pstnhub.gov.teams.microsoft.us** – 글로벌 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-233">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="5d84a-234">높은 GCC 미국 데이터 센터에만 존재하기 때문에 보조 및 세로 FQDNS가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-234">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="5d84a-235">FQDN sip.pstnhub.gov.teams.microsoft.us 다음 서브넷의 IP 주소로 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-235">The FQDN sip.pstnhub.gov.teams.microsoft.us will be resolved to an IP address from the following subnet:</span></span>

- <span data-ttu-id="5d84a-236">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="5d84a-236">52.127.64.0/21</span></span>

<span data-ttu-id="5d84a-237">신호에 대한 주소와 수신 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 범위에 대한 포트를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-237">You need to open ports for all these IP ranges in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="5d84a-238">방화벽이 DNS 이름을 지원하는 경우 FQDN sip.pstnhub.gov.teams.microsoft.us 모든 IP 서브넷으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-238">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP subnets.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="5d84a-239">SIP 신호: 포트</span><span class="sxs-lookup"><span data-stu-id="5d84a-239">SIP Signaling: Ports</span></span>

<span data-ttu-id="5d84a-240">포트 요구 사항은 직접 라우팅이 제공되는 Office 365 모든 환경에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-240">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="5d84a-241">Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="5d84a-241">Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="5d84a-242">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="5d84a-242">Office 365 GCC</span></span>
- <span data-ttu-id="5d84a-243">Office 365 GCC 높음</span><span class="sxs-lookup"><span data-stu-id="5d84a-243">Office 365 GCC High</span></span>
- <span data-ttu-id="5d84a-244">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="5d84a-244">Office 365 DoD</span></span>

<span data-ttu-id="5d84a-245">다음 포트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-245">You must use the following ports:</span></span>

| <span data-ttu-id="5d84a-246">트래픽</span><span class="sxs-lookup"><span data-stu-id="5d84a-246">Traffic</span></span> | <span data-ttu-id="5d84a-247">보낸 사람</span><span class="sxs-lookup"><span data-stu-id="5d84a-247">From</span></span> | <span data-ttu-id="5d84a-248">받는 사람</span><span class="sxs-lookup"><span data-stu-id="5d84a-248">To</span></span> | <span data-ttu-id="5d84a-249">원본 포트</span><span class="sxs-lookup"><span data-stu-id="5d84a-249">Source port</span></span> | <span data-ttu-id="5d84a-250">대상 포트</span><span class="sxs-lookup"><span data-stu-id="5d84a-250">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5d84a-251">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="5d84a-251">SIP/TLS</span></span>| <span data-ttu-id="5d84a-252">SIP 프록시</span><span class="sxs-lookup"><span data-stu-id="5d84a-252">SIP Proxy</span></span> | <span data-ttu-id="5d84a-253">SBC</span><span class="sxs-lookup"><span data-stu-id="5d84a-253">SBC</span></span> | <span data-ttu-id="5d84a-254">1024 - 65535</span><span class="sxs-lookup"><span data-stu-id="5d84a-254">1024 - 65535</span></span> | <span data-ttu-id="5d84a-255">SBC에 정의</span><span class="sxs-lookup"><span data-stu-id="5d84a-255">Defined on the SBC</span></span> |
| <span data-ttu-id="5d84a-256">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="5d84a-256">SIP/TLS</span></span> | <span data-ttu-id="5d84a-257">SBC</span><span class="sxs-lookup"><span data-stu-id="5d84a-257">SBC</span></span> | <span data-ttu-id="5d84a-258">SIP 프록시</span><span class="sxs-lookup"><span data-stu-id="5d84a-258">SIP Proxy</span></span> | <span data-ttu-id="5d84a-259">SBC에 정의</span><span class="sxs-lookup"><span data-stu-id="5d84a-259">Defined on the SBC</span></span> | <span data-ttu-id="5d84a-260">5061</span><span class="sxs-lookup"><span data-stu-id="5d84a-260">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="5d84a-261">미디어 트래픽: IP 및 포트 범위</span><span class="sxs-lookup"><span data-stu-id="5d84a-261">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="5d84a-262">직접 연결을 사용할 수 Teams 경우 또는 클라이언트가 공용 IP 주소를 사용하여 SBC에 도달할 수 없는 경우 Teams 전송 릴레이를 통해 SBC와 클라이언트 간에 미디어 트래픽이 흐르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-262">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="5d84a-263">직접 미디어 트래픽에 대한 요구 사항(Teams 클라이언트와 SBC 간의)</span><span class="sxs-lookup"><span data-stu-id="5d84a-263">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="5d84a-264">클라이언트는 SBC의 공용 IP 주소에서 지정된 포트(표 참조)에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-264">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

> [!NOTE]
> <span data-ttu-id="5d84a-265">클라이언트가 내부 네트워크에 있는 경우 미디어는 SBC의 공용 IP 주소로 흐르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-265">If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="5d84a-266">트래픽이 엔터프라이즈 네트워크 장비에서 나가지 않을 수 있도록 NAT 디바이스에 머리 고정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-266">You can configure hair pinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="5d84a-267">트래픽</span><span class="sxs-lookup"><span data-stu-id="5d84a-267">Traffic</span></span> | <span data-ttu-id="5d84a-268">보낸 사람</span><span class="sxs-lookup"><span data-stu-id="5d84a-268">From</span></span> | <span data-ttu-id="5d84a-269">받는 사람</span><span class="sxs-lookup"><span data-stu-id="5d84a-269">To</span></span> | <span data-ttu-id="5d84a-270">원본 포트</span><span class="sxs-lookup"><span data-stu-id="5d84a-270">Source port</span></span> | <span data-ttu-id="5d84a-271">대상 포트</span><span class="sxs-lookup"><span data-stu-id="5d84a-271">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5d84a-272">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5d84a-272">UDP/SRTP</span></span> | <span data-ttu-id="5d84a-273">클라이언트</span><span class="sxs-lookup"><span data-stu-id="5d84a-273">Client</span></span> | <span data-ttu-id="5d84a-274">SBC</span><span class="sxs-lookup"><span data-stu-id="5d84a-274">SBC</span></span> | <span data-ttu-id="5d84a-275">3478-3481 및 49152 - 53247</span><span class="sxs-lookup"><span data-stu-id="5d84a-275">3478-3481 and 49152 – 53247</span></span>| <span data-ttu-id="5d84a-276">SBC에 정의</span><span class="sxs-lookup"><span data-stu-id="5d84a-276">Defined on the SBC</span></span> |
| <span data-ttu-id="5d84a-277">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5d84a-277">UDP/SRTP</span></span> | <span data-ttu-id="5d84a-278">SBC</span><span class="sxs-lookup"><span data-stu-id="5d84a-278">SBC</span></span> | <span data-ttu-id="5d84a-279">클라이언트</span><span class="sxs-lookup"><span data-stu-id="5d84a-279">Client</span></span> | <span data-ttu-id="5d84a-280">SBC에 정의</span><span class="sxs-lookup"><span data-stu-id="5d84a-280">Defined on the SBC</span></span> | <span data-ttu-id="5d84a-281">3478-3481 및 49152 - 53247</span><span class="sxs-lookup"><span data-stu-id="5d84a-281">3478-3481 and 49152 – 53247</span></span>  |


> [!NOTE]
> <span data-ttu-id="5d84a-282">클라이언트의 원본 포트를 변환하는 네트워크 장치가 있는 경우 네트워크 장비와 SBC 간에 번역된 포트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-282">If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="5d84a-283">전송 릴레이 사용에 대한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d84a-283">Requirements for using Transport Relays</span></span>

<span data-ttu-id="5d84a-284">전송 릴레이는 Media Processor와 동일한 범위에 있습니다(비 우회 사례의 경우).</span><span class="sxs-lookup"><span data-stu-id="5d84a-284">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a><span data-ttu-id="5d84a-285">Microsoft 365, Office 365 및 Office 365 GCC 환경</span><span class="sxs-lookup"><span data-stu-id="5d84a-285">Microsoft 365, Office 365, and Office 365 GCC environments</span></span>

- <span data-ttu-id="5d84a-286">52.112.0.0 /14(52.112.0.1에서 52.115.255.254까지의 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="5d84a-286">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="5d84a-287">Office 365 GCC DoD 환경</span><span class="sxs-lookup"><span data-stu-id="5d84a-287">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="5d84a-288">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="5d84a-288">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="5d84a-289">Office 365 GCC 환경</span><span class="sxs-lookup"><span data-stu-id="5d84a-289">Office 365 GCC High environment</span></span>

- <span data-ttu-id="5d84a-290">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="5d84a-290">52.127.88.0/21</span></span>


<span data-ttu-id="5d84a-291">전송 릴레이의 Teams(모든 환경에 적용 가능)의 포트 범위는 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-291">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="5d84a-292">트래픽</span><span class="sxs-lookup"><span data-stu-id="5d84a-292">Traffic</span></span> | <span data-ttu-id="5d84a-293">보낸 사람</span><span class="sxs-lookup"><span data-stu-id="5d84a-293">From</span></span> | <span data-ttu-id="5d84a-294">받는 사람</span><span class="sxs-lookup"><span data-stu-id="5d84a-294">To</span></span> | <span data-ttu-id="5d84a-295">원본 포트</span><span class="sxs-lookup"><span data-stu-id="5d84a-295">Source port</span></span> | <span data-ttu-id="5d84a-296">대상 포트</span><span class="sxs-lookup"><span data-stu-id="5d84a-296">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5d84a-297">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5d84a-297">UDP/SRTP</span></span> | <span data-ttu-id="5d84a-298">전송 릴레이</span><span class="sxs-lookup"><span data-stu-id="5d84a-298">Transport Relay</span></span> | <span data-ttu-id="5d84a-299">SBC</span><span class="sxs-lookup"><span data-stu-id="5d84a-299">SBC</span></span> | <span data-ttu-id="5d84a-300">50 000 -59 999</span><span class="sxs-lookup"><span data-stu-id="5d84a-300">50 000 -59 999</span></span>    | <span data-ttu-id="5d84a-301">SBC에 정의</span><span class="sxs-lookup"><span data-stu-id="5d84a-301">Defined on the SBC</span></span> |
| <span data-ttu-id="5d84a-302">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5d84a-302">UDP/SRTP</span></span> | <span data-ttu-id="5d84a-303">SBC</span><span class="sxs-lookup"><span data-stu-id="5d84a-303">SBC</span></span> | <span data-ttu-id="5d84a-304">전송 릴레이</span><span class="sxs-lookup"><span data-stu-id="5d84a-304">Transport Relay</span></span> | <span data-ttu-id="5d84a-305">SBC에 정의</span><span class="sxs-lookup"><span data-stu-id="5d84a-305">Defined on the SBC</span></span> | <span data-ttu-id="5d84a-306">50 000 – 59 999, 3478-3481</span><span class="sxs-lookup"><span data-stu-id="5d84a-306">50 000 – 59 999, 3478-3481</span></span>     |


> [!NOTE]
> <span data-ttu-id="5d84a-307">Microsoft는 SBC에서 동시 호출당 두 개 이상의 포트를 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-307">Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="5d84a-308">Microsoft에는 전송 릴레이의 두 가지 버전이 있기 때문에 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-308">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>
> 
> - <span data-ttu-id="5d84a-309">v4, 포트 범위 50 000에서 59 999로만 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-309">v4, which can only work with port range 50 000 to 59 999</span></span>
> 
> - <span data-ttu-id="5d84a-310">포트 3478-3481과 함께 작동하는 v6</span><span class="sxs-lookup"><span data-stu-id="5d84a-310">v6, which works with ports 3478-3481</span></span>

<span data-ttu-id="5d84a-311">현재 미디어 우회는 v4 버전의 전송 릴레이만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-311">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="5d84a-312">향후 v6의 지원을 소개하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-312">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="5d84a-313">전환을 위해 포트 3478-3481을 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-313">You need to open ports 3478-3481 for transitioning.</span></span> <span data-ttu-id="5d84a-314">Microsoft에서 Media Bypass를 통해 v6 전송 릴레이에 대한 지원을 소개하는 경우 네트워크 장비 또는 SBC를 다시 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-314">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="5d84a-315">미디어 프로세서 사용에 대한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d84a-315">Requirements for using media processors</span></span>

<span data-ttu-id="5d84a-316">미디어 프로세서는 항상 음성 애플리케이션 및 웹 클라이언트의 미디어 경로에 있습니다(예: edge 또는 Google Chrome의 Teams 클라이언트).</span><span class="sxs-lookup"><span data-stu-id="5d84a-316">Media Processors are always in the media path for voice applications and for Web clients (for example, Teams clients in Edge or Google Chrome).</span></span> <span data-ttu-id="5d84a-317">요구 사항은 비우회 구성과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-317">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="5d84a-318">미디어 트래픽의 IP 범위는</span><span class="sxs-lookup"><span data-stu-id="5d84a-318">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="5d84a-319">Office 365 및 Office 365 GCC 환경</span><span class="sxs-lookup"><span data-stu-id="5d84a-319">Office 365 and Office 365 GCC environments</span></span>

- <span data-ttu-id="5d84a-320">52.112.0.0 /14(52.112.0.1에서 52.115.255.254까지의 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="5d84a-320">52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="5d84a-321">Office 365 GCC DoD 환경</span><span class="sxs-lookup"><span data-stu-id="5d84a-321">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="5d84a-322">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="5d84a-322">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="5d84a-323">Office 365 GCC 환경</span><span class="sxs-lookup"><span data-stu-id="5d84a-323">Office 365 GCC High environment</span></span>

- <span data-ttu-id="5d84a-324">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="5d84a-324">52.127.88.0/21</span></span>

<span data-ttu-id="5d84a-325">Media Processor의 포트 범위(모든 환경에 적용 가능)는 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-325">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="5d84a-326">트래픽</span><span class="sxs-lookup"><span data-stu-id="5d84a-326">Traffic</span></span> | <span data-ttu-id="5d84a-327">보낸 사람</span><span class="sxs-lookup"><span data-stu-id="5d84a-327">From</span></span> | <span data-ttu-id="5d84a-328">받는 사람</span><span class="sxs-lookup"><span data-stu-id="5d84a-328">To</span></span> | <span data-ttu-id="5d84a-329">원본 포트</span><span class="sxs-lookup"><span data-stu-id="5d84a-329">Source port</span></span> | <span data-ttu-id="5d84a-330">대상 포트</span><span class="sxs-lookup"><span data-stu-id="5d84a-330">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="5d84a-331">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5d84a-331">UDP/SRTP</span></span> | <span data-ttu-id="5d84a-332">미디어 프로세서</span><span class="sxs-lookup"><span data-stu-id="5d84a-332">Media Processor</span></span> | <span data-ttu-id="5d84a-333">SBC</span><span class="sxs-lookup"><span data-stu-id="5d84a-333">SBC</span></span> | <span data-ttu-id="5d84a-334">3478-3481 및 49 152 - 53 247</span><span class="sxs-lookup"><span data-stu-id="5d84a-334">3478-3481 and 49 152 – 53 247</span></span>    | <span data-ttu-id="5d84a-335">SBC에 정의</span><span class="sxs-lookup"><span data-stu-id="5d84a-335">Defined on the SBC</span></span> |
| <span data-ttu-id="5d84a-336">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="5d84a-336">UDP/SRTP</span></span> | <span data-ttu-id="5d84a-337">SBC</span><span class="sxs-lookup"><span data-stu-id="5d84a-337">SBC</span></span> | <span data-ttu-id="5d84a-338">미디어 프로세서</span><span class="sxs-lookup"><span data-stu-id="5d84a-338">Media Processor</span></span> | <span data-ttu-id="5d84a-339">SBC에 정의</span><span class="sxs-lookup"><span data-stu-id="5d84a-339">Defined on the SBC</span></span> | <span data-ttu-id="5d84a-340">3478-3481 및 49 152 - 53 247</span><span class="sxs-lookup"><span data-stu-id="5d84a-340">3478-3481 and 49 152 – 53 247</span></span>     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a><span data-ttu-id="5d84a-341">미디어 우회 및 비미디어 우회에 대한 별도의 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="5d84a-341">Configure separate trunks for media bypass and non-media bypass</span></span>  

<span data-ttu-id="5d84a-342">비미디어 우회에서 미디어 우회로로 마이그레이션하고 모든 사용량을 미디어 우회로로 마이그레이션하기 전에 기능을 확인하려는 경우 별도의 트렁크 및 별도의 온라인 음성 라우팅 정책을 만들어 미디어 우회 트렁크로 라우팅하고 특정 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-342">If you are migrating to media bypass from non-media bypass and want to confirm functionality before migrating all usage to media bypass, you can create a separate trunk and separate Online Voice Routing policy to route to the media bypass trunk and assign to specific users.</span></span> 

<span data-ttu-id="5d84a-343">고급 구성 단계:</span><span class="sxs-lookup"><span data-stu-id="5d84a-343">High-level configuration steps:</span></span>

- <span data-ttu-id="5d84a-344">미디어 우회를 테스트할 사용자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-344">Identify users to test media bypass.</span></span>

- <span data-ttu-id="5d84a-345">서로 다른 FQDNS를 사용하여 두 개의 별도의 트렁크를 만들 수 있습니다. 미디어 우회에 사용하도록 설정되어 있습니다. 다른 것은 안 습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-345">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="5d84a-346">두 트렁크는 모두 동일한 SBC를 지적합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-346">Both trunks point to the same SBC.</span></span> <span data-ttu-id="5d84a-347">TLS SIP 신호에 대한 포트는 다를 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-347">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="5d84a-348">미디어의 포트는 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-348">The ports for media must be the same.</span></span>

- <span data-ttu-id="5d84a-349">새 온라인 음성 라우팅 정책을 만들고 이 정책에 대한 PSTN 사용과 관련된 해당 경로에 미디어 우회 트렁크를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-349">Create a new Online Voice Routing policy and assign the media bypass trunk to the corresponding routes associated with the PSTN usage for this policy.</span></span>

- <span data-ttu-id="5d84a-350">미디어 우회를 테스트하기 위해 식별한 사용자에게 새 온라인 음성 라우팅 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-350">Assign the new Online Voice Routing policy to users you have identified to test media bypass.</span></span>

<span data-ttu-id="5d84a-351">아래 예제에서는 이 논리를 보여 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-351">The example below illustrates this logic.</span></span>

| <span data-ttu-id="5d84a-352">사용자 집합</span><span class="sxs-lookup"><span data-stu-id="5d84a-352">Set of users</span></span> | <span data-ttu-id="5d84a-353">사용자 수</span><span class="sxs-lookup"><span data-stu-id="5d84a-353">Number of users</span></span> | <span data-ttu-id="5d84a-354">OVRP에 할당된 트렁크 FQDN</span><span class="sxs-lookup"><span data-stu-id="5d84a-354">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="5d84a-355">미디어 우회 사용</span><span class="sxs-lookup"><span data-stu-id="5d84a-355">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="5d84a-356">미디어가 아닌 우회 트렁크가 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="5d84a-356">Users with non-media bypass trunk</span></span> | <span data-ttu-id="5d84a-357">980</span><span class="sxs-lookup"><span data-stu-id="5d84a-357">980</span></span> | <span data-ttu-id="5d84a-358">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="5d84a-358">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="5d84a-359">false</span><span class="sxs-lookup"><span data-stu-id="5d84a-359">false</span></span> |
<span data-ttu-id="5d84a-360">미디어 우회 트렁크가 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="5d84a-360">Users with media bypass trunk</span></span> | <span data-ttu-id="5d84a-361">20</span><span class="sxs-lookup"><span data-stu-id="5d84a-361">20</span></span> | <span data-ttu-id="5d84a-362">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="5d84a-362">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="5d84a-363">true</span><span class="sxs-lookup"><span data-stu-id="5d84a-363">true</span></span> | 

<span data-ttu-id="5d84a-364">두 트렁크 모두 동일한 공용 IP 주소가 있는 동일한 SBC를 지적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-364">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="5d84a-365">SBC의 TLS 신호 포트는 다음 다이어그램과 같이 다를 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-365">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="5d84a-366">인증서가 두 트렁크를 모두 지원하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-366">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="5d84a-367">SAN에서 두 개의 이름(sbc1.contoso.com 및 **sbc2.contoso.com)** 또는 와일드카드 인증서가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-367">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5d84a-368">![두 트렁크가 동일한 공용 IP를 사용하여 동일한 SBC를 지적할 수 있는 표시](media/direct-routing-media-bypass-7.png)</span><span class="sxs-lookup"><span data-stu-id="5d84a-368">![Shows both trunks can point to the same SBC with the same public IP](media/direct-routing-media-bypass-7.png)</span></span>

<span data-ttu-id="5d84a-369">동일한 SBC에서 두 개의 트렁크를 구성하는 방법에 대한 자세한 내용은 SBC 공급업체에서 제공하는 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d84a-369">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="5d84a-370">AudioCodes 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="5d84a-370">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="5d84a-371">Oracle 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="5d84a-371">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="5d84a-372">리본 통신 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="5d84a-372">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="5d84a-373">TE-Systems(anynode) 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="5d84a-373">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="5d84a-374">미디어 우회로 지원되는 클라이언트 엔드포인트</span><span class="sxs-lookup"><span data-stu-id="5d84a-374">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="5d84a-375">미디어 우회는 데스크톱 클라이언트, Android 및 iOS Teams 모든 독립 실행형 Teams 전화 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-375">Media bypass is supported with all standalone Teams Desktop clients, Android and iOS clients and Teams Phone Devices.</span></span> 

<span data-ttu-id="5d84a-376">미디어 우회를 지원하지 않는 다른 모든 엔드포인트의 경우 우회 호출로 시작된 경우에도 호출을 비우회로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-376">For all other endpoints that do not support media bypass, we will convert the call to non-bypass even if it started as a bypass call.</span></span> <span data-ttu-id="5d84a-377">이 작업은 자동으로 수행되며 관리자의 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-377">This happens automatically and does not require any actions from the administrator.</span></span> <span data-ttu-id="5d84a-378">여기에는 비즈니스용 Skype 3PIP 휴대폰 및 직접 라우팅 호출을 Teams 웹 클라이언트(웹RTC 기반 클라이언트, Google Chrome, 모질라 파이어 폭스에서 실행되는 웹RTC 기반 클라이언트)가 Microsoft Edge 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-378">This includes Skype for Business 3PIP Phones, and Teams Web Clients that support Direct Routing calling (WebRTC based clients running on Microsoft Edge, Google Chrome, Mozilla Firefox).</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="5d84a-379">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d84a-379">See also</span></span>

[<span data-ttu-id="5d84a-380">직접 라우팅을 위한 미디어 바이패스 구성</span><span class="sxs-lookup"><span data-stu-id="5d84a-380">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)
