---
title: 다이렉트 라우팅으로 미디어 바이패스 계획
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 이 항목에서는 전화 시스템 다이렉트 라우팅과 함께 미디어 바이패스를 계획 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 70d0b5ea61d0d7a8001bb1dbfabda2c45274e521
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271449"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a><span data-ttu-id="bef6f-103">다이렉트 라우팅으로 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="bef6f-103">Plan for media bypass with Direct Routing</span></span>

## <a name="about-media-bypass-with-direct-routing"></a><span data-ttu-id="bef6f-104">다이렉트 라우팅으로 미디어 바이패스 정보</span><span class="sxs-lookup"><span data-stu-id="bef6f-104">About media bypass with Direct Routing</span></span>

<span data-ttu-id="bef6f-105">미디어 바이패스를 통해 미디어 트래픽 경로를 줄이고, 더 나은 성능을 위해 전송 하는 홉 수를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-105">Media bypass enables you to shorten the path of media traffic and reduce the number of hops in transit for better performance.</span></span> <span data-ttu-id="bef6f-106">미디어 바이패스를 사용 하 여 미디어는 Microsoft 전화 시스템을 통해 전송 되는 대신 SBC (세션 경계 컨트롤러)와 클라이언트 간에 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-106">With media bypass, media is kept between the Session Border Controller (SBC) and the client instead of sending it via the Microsoft Phone System.</span></span> <span data-ttu-id="bef6f-107">미디어 바이패스를 구성 하려면 SBC 및 클라이언트가 같은 위치 또는 네트워크에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-107">To configure media bypass, the SBC and the client must be in the same location or network.</span></span>

<span data-ttu-id="bef6f-108">**-MediaBypass** 매개 변수가 true 또는 false로 설정 된 **set-CSOnlinePSTNGateway** 명령을 사용 하 여 각 SBC에 대 한 미디어 바이패스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-108">You can control media bypass for each SBC by using the **Set-CSOnlinePSTNGateway** command with the **-MediaBypass** parameter set to true or false.</span></span> <span data-ttu-id="bef6f-109">미디어 바이패스를 사용 하도록 설정 하면 모든 미디어 트래픽이 회사 네트워크 내에 유지 된다는 의미는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-109">If you enable media bypass, this does not mean that all media traffic will stay within the corporate network.</span></span> <span data-ttu-id="bef6f-110">이 문서에서는 다양 한 시나리오의 통화 흐름에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-110">This article describes the call flow in different scenarios.</span></span>    

<span data-ttu-id="bef6f-111">아래 다이어그램은 미디어 바이패스와 함께 통화 흐름의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-111">The diagrams below illustrate the difference in call flow with and without media bypass.</span></span>

<span data-ttu-id="bef6f-112">미디어 바이패스 없이 클라이언트가 다음 다이어그램과 같이 SBC, Microsoft 전화 시스템, 팀 클라이언트 간의 신호 및 미디어 흐름을 모두 호출 하거나 수신할 때 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-112">Without media bypass, when a client makes or receives a call, both signaling and media flow between the SBC, the Microsoft Phone System, and the Teams client, as shown in the following diagram:</span></span>

![미디어 바이패스 없이 신호 및 미디어 흐름 표시](media/direct-routing-media-bypass-1.png)


<span data-ttu-id="bef6f-114">사용자가 SBC와 같은 건물이 나 네트워크상에 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-114">But let's assume that a user is in the same building or network as the SBC.</span></span> <span data-ttu-id="bef6f-115">예를 들어 Frankfurt에서 빌드하는 사용자가 PSTN 사용자에 게 전화를 거는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-115">For example, assume a user who is in a building in Frankfurt makes a call to a PSTN user:</span></span> 

- <span data-ttu-id="bef6f-116">**미디어를 우회 하지 않으면**미디어는 암스테르담 또는 더블린 (Microsoft 데이터 센터가 배포 된 위치)를 통해 FRANKFURT의 SBC로 다시 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-116">**Without media bypass**, media will flow via either Amsterdam or Dublin (where Microsoft datacenters are deployed) and back to the SBC in Frankfurt.</span></span> 

  <span data-ttu-id="bef6f-117">이 SBC는 유럽에 있으며, Microsoft는 SBC에 가장 가까운 데이터 센터를 사용 하므로 유럽의 데이터 센터가 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-117">The datacenter in Europe is selected because the SBC is in Europe, and Microsoft uses the datacenter closest to the SBC.</span></span> <span data-ttu-id="bef6f-118">이 접근 방식은 대부분의 지역에서 Microsoft 네트워크 내의 트래픽 흐름 최적화로 인해 통화 품질에 영향을 주지는 않지만 소통량이 불필요 한 루프를가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-118">While this approach does not affect call quality due to optimization of traffic flow within Microsoft networks in most geographies, the traffic has an unnecessary loop.</span></span>     

- <span data-ttu-id="bef6f-119">**미디어 바이패스를 사용**하는 경우 미디어는 다음 다이어그램에 표시 된 대로 팀 사용자와 SBC 간에 직접 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-119">**With media bypass**, the media is kept directly between the Teams user and the SBC as shown in the following diagram:</span></span>

![미디어 우회를 사용 하 여 신호 및 미디어 흐름 표시](media/direct-routing-media-bypass-2.png)

<span data-ttu-id="bef6f-121">미디어 바이패스는 팀 클라이언트 및 SBC의 ICE lite에 있는 ICE (대화형 연결 설정) 프로토콜을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-121">Media bypass leverages protocols called Interactive Connectivity Establishment (ICE) on the Teams client and ICE lite on the SBC.</span></span> <span data-ttu-id="bef6f-122">이러한 프로토콜은 최적의 음질을 위해 직접 라우팅이 가장 직접적인 미디어 경로를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-122">These protocols enable Direct Routing to use the most direct media path for optimal quality.</span></span> <span data-ttu-id="bef6f-123">ICE 및 얼음 Lite는 WebRTC 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-123">ICE and ICE Lite are WebRTC standards.</span></span> <span data-ttu-id="bef6f-124">이러한 프로토콜에 대 한 자세한 내용은 RFC 5245을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bef6f-124">For detailed information about these protocols, see RFC 5245.</span></span>


## <a name="call-flow-and-firewall-planning"></a><span data-ttu-id="bef6f-125">통화 흐름 및 방화벽 계획</span><span class="sxs-lookup"><span data-stu-id="bef6f-125">Call flow and firewall planning</span></span>

<span data-ttu-id="bef6f-126">통화 흐름 및 방화벽 계획은 사용자가 SBC의 공용 IP 주소에 직접 액세스 했는지 여부와 네트워크 내부 또는 외부에 있는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-126">Call flow and firewall planning depends on whether the user has direct access to the public IP address of the SBC, and whether the user is inside or outside of the network.</span></span>

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="bef6f-127">사용자가 SBC의 공용 IP 주소에 직접 액세스 하는 경우의 호출 흐름</span><span class="sxs-lookup"><span data-stu-id="bef6f-127">Call flow if the user has direct access to the public IP address of the SBC</span></span>

<span data-ttu-id="bef6f-128">사용자가 SBC의 공용 IP 주소에 직접 액세스 하는 경우 통화 흐름은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-128">If the user has direct access to the public IP address of the SBC, the call flow is as follows:</span></span>

- <span data-ttu-id="bef6f-129">미디어 바이패스의 경우 팀 클라이언트는 내부 네트워크 에서도 SBC의 공용 IP 주소에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-129">For media bypass, the Teams client must have access to the public IP address of the SBC even from an internal network.</span></span> <span data-ttu-id="bef6f-130">직접 미디어를 원하지 않는 경우에는 전송 릴레이를 통해 미디어를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-130">If direct media is not desired, the media can flow via Transport Relays.</span></span>

- <span data-ttu-id="bef6f-131">사용자가 SBC와 동일한 건물 및/또는 네트워크에 있는 경우 미디어 경로에서 Microsoft 클라우드 구성 요소를 제거 하는 것이 권장 되는 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-131">This is the recommended solution when a user is in the same building and/or network as the SBC – remove Microsoft Cloud components from the media path.</span></span>

- <span data-ttu-id="bef6f-132">신호는 항상 Microsoft 클라우드를 통해 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-132">Signaling always flows via the Microsoft cloud.</span></span>

<span data-ttu-id="bef6f-133">다음 다이어그램에서는 미디어 바이패스를 사용 하도록 설정 하 고 클라이언트는 내부 이며 클라이언트는 SBC의 공용 IP 주소 (직접 미디어)에 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-133">The following diagram shows call flow when media bypass is enabled, the client is internal, and the client can reach the public IP address of the SBC (direct media):</span></span> 

- <span data-ttu-id="bef6f-134">경로의 화살표 및 숫자 값은 [Microsoft 팀의 통화 흐름](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) 문서에 따라 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-134">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="bef6f-135">SIP 신호는 항상 경로 4 및 4를 받습니다 (트래픽 방향에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="bef6f-135">The SIP signaling always takes paths 4 and 4’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="bef6f-136">미디어는 로컬에서 유지 되 고 경로 5b를 차지 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-136">Media stays local and takes path 5b.</span></span>

![미디어 바이패스를 사용 하도록 설정 하 고 클라이언트가 내부 인 통화 흐름 표시](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a><span data-ttu-id="bef6f-138">사용자에 게 SBC의 공용 IP 주소에 대 한 액세스 권한이 없는 경우의 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="bef6f-138">Call flow if the user does not have access to the public IP address of the SBC</span></span>

<span data-ttu-id="bef6f-139">다음은 사용자에 게 SBC의 공용 IP 주소에 대 한 액세스 권한이 없는 경우의 호출 흐름에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-139">The following describes call flow if the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="bef6f-140">예를 들어 사용자가 외부에 있고 테 넌 트 관리자가 인터넷의 모든 사용자에 게 SBC의 공용 IP 주소를 열지 않기로 결정 한 경우에만 Microsoft Cloud로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-140">For example, assume the user is external, and the tenant administrator decided not to open the public IP address of the SBC to everyone in the Internet, but only to the Microsoft Cloud.</span></span> <span data-ttu-id="bef6f-141">트래픽 내부 구성 요소는 팀 전송 릴레이를 통해 흐를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-141">The internal components of traffic can flow via the Teams Transport Relays.</span></span> <span data-ttu-id="bef6f-142">회사 네트워크 외부의 사용자에 게 권장 되는 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-142">This is the recommended configuration for users outside of the corporate network.</span></span> <span data-ttu-id="bef6f-143">다음을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="bef6f-143">Consider the following:</span></span>

- <span data-ttu-id="bef6f-144">팀 전송 릴레이를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-144">Teams Transport Relays are used.</span></span>

- <span data-ttu-id="bef6f-145">미디어 바이패스의 경우 Microsoft는 팀 전송 릴레이와 SBC 간에 포트 50 000을 59 999으로 열어야 하는 전송 릴레이 버전을 사용 합니다 (앞으로는 3478 및 3479 포트만 필요로 하는 버전으로 이동 하려고 함).</span><span class="sxs-lookup"><span data-stu-id="bef6f-145">For media bypass, Microsoft uses a version of Transport Relays that requires opening ports 50 000 to 59 999 between the Teams Transport Relays and the SBC (in the future we plan to move to the version which requires only 3478 and 3479 ports).</span></span>

- <span data-ttu-id="bef6f-146">미디어 최적화를 위해 Microsoft는 SBC의 공용 IP 주소를 팀의 전송 릴레이로만 열 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-146">For media optimization purposes, Microsoft recommends opening the public IP address of the SBC only to Teams Transport Relays.</span></span> <span data-ttu-id="bef6f-147">회사 네트워크 외부의 클라이언트의 경우 Microsoft는 SBC의 공용 IP 주소에 직접 도달 하는 대신 전송 릴레이를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-147">For clients outside of the corporate network, Microsoft recommends using Transport Relays instead of reaching the public IP address of the SBC directly.</span></span>

<span data-ttu-id="bef6f-148">다음 다이어그램에서는 미디어 바이패스를 사용 하도록 설정 하 고 클라이언트는 외부에 있으며 클라이언트가 세션 경계 컨트롤러의 공용 IP 주소에 연결할 수 없습니다 (미디어가 팀 전송 릴레이에 의해 릴레이 됨).</span><span class="sxs-lookup"><span data-stu-id="bef6f-148">The following diagram shows call flow when media bypass is enabled, the client is external, and the client cannot reach the public IP address of the Session Border Controller (media is relayed by Teams Transport Relay).</span></span>

- <span data-ttu-id="bef6f-149">경로의 화살표 및 숫자 값은 [Microsoft 팀의 통화 흐름](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) 문서에 따라 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-149">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="bef6f-150">미디어는 경로 3, 3, 4, 4를 통해 릴레이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-150">Media is relayed via paths 3, 3', 4 and 4'</span></span>

![사용자가 SBC의 공용 IP에 액세스할 수 없는 경우 통화 흐름 표시](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a><span data-ttu-id="bef6f-152">사용자가 네트워크 외부에 있고 SBC의 공용 IP에 대 한 액세스 권한이 있는 경우의 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="bef6f-152">Call flow if a user is outside the network and has access to the public IP of the SBC</span></span>

> [!NOTE]
> <span data-ttu-id="bef6f-153">이 구성은 팀 전송 릴레이를 이용 하지 않으므로 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-153">This is not a recommended configuration because it does not take advantage of Teams Transport Relays.</span></span> <span data-ttu-id="bef6f-154">대신 사용자에 게 SBC의 공용 IP 주소에 대 한 액세스 권한이 없는 이전 시나리오를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-154">Instead, you should consider the previous scenario where the user does not have access to the public IP address of the SBC.</span></span> 

<span data-ttu-id="bef6f-155">다음 다이어그램은 미디어 바이패스를 사용 하도록 설정 하 고 클라이언트가 외부에 있는 경우 클라이언트는 SBC의 공용 IP 주소 (직접 미디어)에 도달할 수 있는 경우의 통화 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-155">The following diagram shows call flow when media bypass is enabled, the client is external, and the client can reach the public IP address of the SBC (direct media).</span></span>

- <span data-ttu-id="bef6f-156">경로의 화살표 및 숫자 값은 [Microsoft 팀의 통화 흐름](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) 문서에 따라 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-156">The arrows and numeric values of the paths are in accordance with the [Microsoft Teams call flows](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) article.</span></span>

- <span data-ttu-id="bef6f-157">SIP 신호는 항상 경로 3 및 3을 받습니다 (트래픽 방향에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="bef6f-157">The SIP signaling always takes paths 3 and 3’ (depending on the direction of the traffic).</span></span> <span data-ttu-id="bef6f-158">경로 2를 사용 하는 미디어 흐름</span><span class="sxs-lookup"><span data-stu-id="bef6f-158">Media flows using path 2.</span></span>

![사용자가 SBC의 공용 IP에 액세스할 수 없는 경우 통화 흐름 표시](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a><span data-ttu-id="bef6f-160">미디어 프로세서 및 전송 릴레이 사용</span><span class="sxs-lookup"><span data-stu-id="bef6f-160">Use of Media Processors and Transport Relays</span></span>

<span data-ttu-id="bef6f-161">미디어 트래픽 경로에 있을 수 있는 Microsoft 클라우드의 두 가지 구성 요소 (미디어 프로세서와 전송 릴레이)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-161">There are two components in the Microsoft Cloud that can be in the path of media traffic: Media Processors and Transport Relays.</span></span> 

- <span data-ttu-id="bef6f-162">미디어 프로세서는 비 바이패스 케이스에서 미디어를 처리 하 고 음성 응용 프로그램의 미디어를 처리 하는 공용 지향 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-162">The Media Processor is a public facing component that handles media in non-bypass cases and handles media for voice applications.</span></span>

   <span data-ttu-id="bef6f-163">미디어 프로세서는 항상 최종 사용자가 무시할 수 없는 호출에 대 한 경로에 있지만 건너뛸 때는이 경로에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-163">Media Processors are always in the path for end user non-bypassed calls, but never in the path for bypassed calls.</span></span> <span data-ttu-id="bef6f-164">미디어 프로세서는 항상 통화 공원, 조직 자동 전화 교환, 통화 대기열 등의 모든 음성 응용 프로그램에 대 한 경로에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-164">Media Processors are always in the path for all voice applications such as Call Park, Organizational Auto Attendant, and Call Queues.</span></span>

- <span data-ttu-id="bef6f-165">전송 릴레이는 실시간 트래픽을 보내기 위해 가장 가까운 전송 서비스에 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-165">The Transport Relay is used to connect to the closest Transport Service to send real time traffic.</span></span>

   <span data-ttu-id="bef6f-166">전송 릴레이는 사용자가 어디에 있고 네트워크를 구성 하는 방법에 따라, 최종 사용자가 시작 하거나 대상으로 하는 호출 경로에 있을 수도 있고 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-166">Transport Relays might or might not be in the path for bypassed calls--originating from or destined to end users--depending on where the user is and how the network is configured .</span></span>

<span data-ttu-id="bef6f-167">다음 다이어그램은 미디어 바이패스를 사용 하도록 설정 하 고 두 번째는 미디어 바이패스를 사용 하지 않는 두 가지 호출 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-167">The following diagram shows two call flows – one with media bypass enabled and the second with media bypass disabled.</span></span> <span data-ttu-id="bef6f-168">참고 다이어그램은--또는로 보내는 사용자의 트래픽만 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-168">Note the diagram only illustrates traffic originating from--or destined to--end users.</span></span>  
- <span data-ttu-id="bef6f-169">미디어 컨트롤러는 미디어 프로세서를 할당 하 고 SDP (세션 설명 프로토콜) 제공을 만드는 Azure의 microservice입니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-169">The Media Controller is a microservice in Azure that assigns Media Processors and creates Session Description Protocol (SDP) offers.</span></span>

- <span data-ttu-id="bef6f-170">SIP 프록시는 팀에서 사용 되는 HTTP REST 신호를 SIP로 변환 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-170">The SIP Proxy is a component that translates HTTP REST signaling used in Teams to SIP.</span></span>    

![미디어 바이패스 사용 및 사용 안 함이 설정 된 통화 흐름 표시](media/direct-routing-media-bypass-6.png)


<span data-ttu-id="bef6f-172">아래 표에는 미디어 프로세서와 전송 릴레이의 차이점에 대 한 요약이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-172">The table below summarizes the difference between Media Processors and Transport Relays.</span></span>

|    | <span data-ttu-id="bef6f-173">미디어 프로세서</span><span class="sxs-lookup"><span data-stu-id="bef6f-173">Media Processors</span></span> | <span data-ttu-id="bef6f-174">전송 릴레이</span><span class="sxs-lookup"><span data-stu-id="bef6f-174">Transport Relays</span></span>|
| :--------------|:---------------|:------------|
<span data-ttu-id="bef6f-175">최종 사용자에 대 한 무시할 수 없는 통화에 대 한 미디어 경로</span><span class="sxs-lookup"><span data-stu-id="bef6f-175">In media path for non-bypassed calls for end users</span></span> | <span data-ttu-id="bef6f-176">Always</span><span class="sxs-lookup"><span data-stu-id="bef6f-176">Always</span></span> | <span data-ttu-id="bef6f-177">열리지</span><span class="sxs-lookup"><span data-stu-id="bef6f-177">Never</span></span> | 
<span data-ttu-id="bef6f-178">최종 사용자에 대 한 바이패스 전화의 미디어 경로</span><span class="sxs-lookup"><span data-stu-id="bef6f-178">In media path for bypassed calls for end users</span></span> | <span data-ttu-id="bef6f-179">열리지</span><span class="sxs-lookup"><span data-stu-id="bef6f-179">Never</span></span> | <span data-ttu-id="bef6f-180">클라이언트가 공용 IP 주소의 SBC에 연결할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="bef6f-180">If client cannot reach the SBC on the public IP address</span></span> | 
<span data-ttu-id="bef6f-181">음성 응용 프로그램용 미디어 경로</span><span class="sxs-lookup"><span data-stu-id="bef6f-181">In media path for voice applications</span></span> | <span data-ttu-id="bef6f-182">Always</span><span class="sxs-lookup"><span data-stu-id="bef6f-182">Always</span></span> | <span data-ttu-id="bef6f-183">열리지</span><span class="sxs-lookup"><span data-stu-id="bef6f-183">Never</span></span> | 
<span data-ttu-id="bef6f-184">코드 변환 가능 (B2BUA)\*</span><span class="sxs-lookup"><span data-stu-id="bef6f-184">Can do transcoding (B2BUA)\*</span></span> | <span data-ttu-id="bef6f-185">'</span><span class="sxs-lookup"><span data-stu-id="bef6f-185">Yes</span></span> | <span data-ttu-id="bef6f-186">아니요, 끝점 간 오디오만 릴레이 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-186">No, only relays audio between endpoints</span></span> | 
<span data-ttu-id="bef6f-187">전세계 인스턴스 수 및 위치</span><span class="sxs-lookup"><span data-stu-id="bef6f-187">Number of instances worldwide and location</span></span> | <span data-ttu-id="bef6f-188">총 8: 미국 동부와 서쪽에 2 개 # 암스테르담 및 더블린의 경우 2 홍콩 및 싱가포르의 2 일본의 2 (Q1CY2019에서 추가 됨)</span><span class="sxs-lookup"><span data-stu-id="bef6f-188">8 total: 2 in US East and West; 2 in Amsterdam and Dublin; 2 in Hong Kong and Singapore; 2 in Japan (being added in Q1CY2019)</span></span>  | <span data-ttu-id="bef6f-189">개인</span><span class="sxs-lookup"><span data-stu-id="bef6f-189">Multiple</span></span>

<span data-ttu-id="bef6f-190">IP 범위는 52.112.0.0/14입니다 (IP 주소는 52.112.0.1에서 52.115.255.254)입니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-190">The IP range is 52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254).</span></span> 

<span data-ttu-id="bef6f-191">\*코드 변환 설명:</span><span class="sxs-lookup"><span data-stu-id="bef6f-191">\* Transcoding explanation:</span></span> 

- <span data-ttu-id="bef6f-192">미디어 프로세서는 B2BUA, 즉, 코덱 (예: 팀 클라이언트에서 MP 및 SILK에 대 한 711 간)을 변경할 수 있다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-192">Media Processor is B2BUA, which means it can change a codecs (for example, SILK from Teams client to MP and G.711 between MP and SBC).</span></span>

- <span data-ttu-id="bef6f-193">전송 릴레이는 B2BUA 되지 않으므로 클라이언트와 SBC 간에 코덱이 변경 되지 않음을 의미 합니다--릴레이를 통해 트래픽이 흐름을 진행 하는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-193">Transport Relays are not B2BUA, which means the codec is never changed between the client and the SBC--even if traffic flows via relays.</span></span>

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a><span data-ttu-id="bef6f-194">미디어 바이패스를 위해 트렁크가 구성 된 경우 에스컬레이션 시나리오에서 팀의 전송 릴레이를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-194">Use of Teams Transport Relays in escalation scenarios if trunk is configured for media bypass</span></span>

<span data-ttu-id="bef6f-195">팀 전송 릴레이는 항상 다음과 같은 시나리오에서 미디어 경로에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-195">Teams Transport Relays are always in the media path in the following scenarios:</span></span>

- <span data-ttu-id="bef6f-196">1:1에서 그룹 통화로 통화 에스컬레이션</span><span class="sxs-lookup"><span data-stu-id="bef6f-196">Call is escalated from 1:1 to a group call</span></span>
- <span data-ttu-id="bef6f-197">연결이 페더레이션된 팀 사용자에 게 방문</span><span class="sxs-lookup"><span data-stu-id="bef6f-197">Call is going to a federated Teams user</span></span>
- <span data-ttu-id="bef6f-198">비즈니스용 Skype 사용자에 게 착신 전환 또는 전송</span><span class="sxs-lookup"><span data-stu-id="bef6f-198">Call is forwarded or transferred to a Skype for Business user</span></span>

<span data-ttu-id="bef6f-199">SBC에 아래 설명 된 대로 전송 중계에 대 한 액세스 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-199">Ensure your SBC has access to the Transport Relays as described below.</span></span>    


## <a name="sip-signaling-fqdns"></a><span data-ttu-id="bef6f-200">SIP 신호: Fqdn</span><span class="sxs-lookup"><span data-stu-id="bef6f-200">SIP Signaling: FQDNs</span></span>

<span data-ttu-id="bef6f-201">SIP 신호를 위해 FQDN 및 방화벽 요구 사항은 무시할 수 없는 경우와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-201">For SIP signaling, the FQDN and firewall requirements are the same as for non-bypassed cases.</span></span> 

<span data-ttu-id="bef6f-202">직접 라우팅은 다음과 같은 Office 365 환경에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-202">Direct Routing is offered in the following Office 365 environments:</span></span>
- <span data-ttu-id="bef6f-203">Office 365</span><span class="sxs-lookup"><span data-stu-id="bef6f-203">Office 365</span></span>
- <span data-ttu-id="bef6f-204">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="bef6f-204">Office 365 GCC</span></span>
- <span data-ttu-id="bef6f-205">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="bef6f-205">Office 365 GCC High</span></span>
- <span data-ttu-id="bef6f-206">Office 365 DoD, gcc, GCC High, DoD 등의 [office 365 및 US 정부 환경](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="bef6f-206">Office 365 DoD Learn more about [Office 365 and US Government environments](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) such as GCC, GCC High, and DoD.</span></span>

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="bef6f-207">Office 365 및 Office 365 GCC 환경</span><span class="sxs-lookup"><span data-stu-id="bef6f-207">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="bef6f-208">직접 라우팅의 연결 지점은 다음 세 가지 Fqdn입니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-208">The connection points for Direct Routing are the following three FQDNs:</span></span>

- <span data-ttu-id="bef6f-209">**sip.pstnhub.microsoft.com** – 전역 FQDN – 먼저 시도해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-209">**sip.pstnhub.microsoft.com** – Global FQDN – must be tried first.</span></span> <span data-ttu-id="bef6f-210">SBC에서이 이름을 확인 하는 요청을 보낼 때 Microsoft Azure DNS 서버는 SBC에 할당 된 기본 Azure 데이터 센터를 가리키는 IP 주소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-210">When the SBC sends a request to resolve this name, the Microsoft Azure DNS servers return an IP address pointing to the primary Azure datacenter assigned to the SBC.</span></span> <span data-ttu-id="bef6f-211">과제는 데이터 센터의 성과 메트릭과 SBC에 대 한 지리적 근접성을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-211">The assignment is based on performance metrics of the datacenters and geographical proximity to the SBC.</span></span> <span data-ttu-id="bef6f-212">반환 되는 IP 주소는 기본 FQDN에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-212">The IP address returned corresponds to the primary FQDN.</span></span>

- <span data-ttu-id="bef6f-213">**sip2.pstnhub.microsoft.com** – 보조 FQDN – 지리적으로 두 번째 우선 순위 영역으로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-213">**sip2.pstnhub.microsoft.com** – Secondary FQDN – geographically maps to the second priority region.</span></span>

- <span data-ttu-id="bef6f-214">**sip3.pstnhub.microsoft.com** – 세 번째 FQDN – 지리적으로 세번째 우선 순위 영역을 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-214">**sip3.pstnhub.microsoft.com** – Tertiary FQDN – geographically maps to the third priority region.</span></span>

<span data-ttu-id="bef6f-215">다음을 수행 하려면 이러한 세 가지 Fqdn을 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-215">You must place these three FQDNs in order to:</span></span>

- <span data-ttu-id="bef6f-216">최적의 환경을 제공 합니다 (첫 번째 FQDN을 쿼리하면 지정 된 SBC 데이터 센터에 가장 가깝습니다).</span><span class="sxs-lookup"><span data-stu-id="bef6f-216">Provide optimal experience (less loaded and closest to the SBC datacenter assigned by querying the first FQDN).</span></span>

- <span data-ttu-id="bef6f-217">일시적인 문제가 발생 하는 데이터 센터에 SBC의 연결이 설정 된 경우 장애 조치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-217">Provide failover when a connection from an SBC is established to a datacenter that is experiencing a temporary issue.</span></span> <span data-ttu-id="bef6f-218">자세한 내용은 아래의 장애 조치 메커니즘을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bef6f-218">For more information, see Failover mechanism below.</span></span>


<span data-ttu-id="bef6f-219">Fqdn **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**및 **sip3.pstnhub.microsoft.com** 는 다음 IP 주소 중 하나로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-219">The FQDNs **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**, and **sip3.pstnhub.microsoft.com** will be resolved to one of the following IP addresses:</span></span>
- <span data-ttu-id="bef6f-220">52.114.148.0</span><span class="sxs-lookup"><span data-stu-id="bef6f-220">52.114.148.0</span></span>
- <span data-ttu-id="bef6f-221">52.114.132.46</span><span class="sxs-lookup"><span data-stu-id="bef6f-221">52.114.132.46</span></span>
- <span data-ttu-id="bef6f-222">52.114.75.24</span><span class="sxs-lookup"><span data-stu-id="bef6f-222">52.114.75.24</span></span>
- <span data-ttu-id="bef6f-223">52.114.76.76</span><span class="sxs-lookup"><span data-stu-id="bef6f-223">52.114.76.76</span></span>
- <span data-ttu-id="bef6f-224">52.114.7.24</span><span class="sxs-lookup"><span data-stu-id="bef6f-224">52.114.7.24</span></span>
- <span data-ttu-id="bef6f-225">52.114.14.70</span><span class="sxs-lookup"><span data-stu-id="bef6f-225">52.114.14.70</span></span>

<span data-ttu-id="bef6f-226">수신 및 송신 트래픽을 주소에서 주고 받을 수 있도록 방화벽에서 이러한 모든 IP 주소에 대해 포트를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-226">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span> <span data-ttu-id="bef6f-227">방화벽이 DNS 이름을 지 원하는 경우 FQDN **sip-all.pstnhub.microsoft.com** 이러한 모든 IP 주소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-227">If your firewall supports DNS names, the FQDN **sip-all.pstnhub.microsoft.com** resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="bef6f-228">Office 365 GCC DoD 환경</span><span class="sxs-lookup"><span data-stu-id="bef6f-228">Office 365 GCC DoD environment</span></span>

<span data-ttu-id="bef6f-229">직접 라우팅의 연결 지점은 다음 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-229">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="bef6f-230">**sip.pstnhub.dod.teams.microsoft.us** – 전역 FQDN.</span><span class="sxs-lookup"><span data-stu-id="bef6f-230">**sip.pstnhub.dod.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="bef6f-231">Office 365 DoD 환경은 미국 데이터 센터에만 있으므로 2 차 및 3 차 Fqdn이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-231">As the Office 365 DoD environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="bef6f-232">Fqdn – sip.pstnhub.dod.teams.microsoft.us는 다음 IP 주소 중 하나로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-232">The FQDNs – sip.pstnhub.dod.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="bef6f-233">52.127.64.33</span><span class="sxs-lookup"><span data-stu-id="bef6f-233">52.127.64.33</span></span>
- <span data-ttu-id="bef6f-234">52.127.68.34</span><span class="sxs-lookup"><span data-stu-id="bef6f-234">52.127.68.34</span></span>

<span data-ttu-id="bef6f-235">수신 및 송신 트래픽을 주소에서 주고 받을 수 있도록 방화벽에서 이러한 모든 IP 주소에 대해 포트를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-235">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="bef6f-236">방화벽이 DNS 이름을 지 원하는 경우 FQDN sip.pstnhub.dod.teams.microsoft.us 이러한 모든 IP 주소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-236">If your firewall supports DNS names, the FQDN  sip.pstnhub.dod.teams.microsoft.us resolves to all these IP addresses.</span></span> 

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="bef6f-237">Office 365 GCC High 환경</span><span class="sxs-lookup"><span data-stu-id="bef6f-237">Office 365 GCC High environment</span></span>

<span data-ttu-id="bef6f-238">직접 라우팅의 연결 지점은 다음 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-238">The connection point for Direct Routing is the following FQDN:</span></span>

<span data-ttu-id="bef6f-239">**sip.pstnhub.gov.teams.microsoft.us** – 전역 FQDN.</span><span class="sxs-lookup"><span data-stu-id="bef6f-239">**sip.pstnhub.gov.teams.microsoft.us** – Global FQDN.</span></span> <span data-ttu-id="bef6f-240">GCC High 환경은 US 데이터 센터에만 존재 하므로 2 차 및 3 차 Fqdn이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-240">As the GCC High environment exists only in the US data centers, there is no secondary and tertiary FQDNs.</span></span>

<span data-ttu-id="bef6f-241">Fqdn – sip.pstnhub.gov.teams.microsoft.us는 다음 IP 주소 중 하나로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-241">The FQDNs – sip.pstnhub.gov.teams.microsoft.us will be resolved to one of the following IP addresses:</span></span>

- <span data-ttu-id="bef6f-242">52.127.88.59</span><span class="sxs-lookup"><span data-stu-id="bef6f-242">52.127.88.59</span></span>
- <span data-ttu-id="bef6f-243">52.127.92.64</span><span class="sxs-lookup"><span data-stu-id="bef6f-243">52.127.92.64</span></span>

<span data-ttu-id="bef6f-244">수신 및 송신 트래픽을 주소에서 주고 받을 수 있도록 방화벽에서 이러한 모든 IP 주소에 대해 포트를 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-244">You need to open ports for all these IP addresses in your firewall to allow incoming and outgoing traffic to and from the addresses for signaling.</span></span>  <span data-ttu-id="bef6f-245">방화벽이 DNS 이름을 지 원하는 경우 FQDN sip.pstnhub.gov.teams.microsoft.us 이러한 모든 IP 주소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-245">If your firewall supports DNS names, the FQDN  sip.pstnhub.gov.teams.microsoft.us resolves to all these IP addresses.</span></span> 

## <a name="sip-signaling-ports"></a><span data-ttu-id="bef6f-246">SIP 신호: 포트</span><span class="sxs-lookup"><span data-stu-id="bef6f-246">SIP Signaling: Ports</span></span>

<span data-ttu-id="bef6f-247">포트 요구 사항은 직접 라우팅이 제공 되는 모든 Office 365 환경에 대해 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-247">Port requirements are the same for all Office 365 environments where Direct Routing is offered:</span></span>
- <span data-ttu-id="bef6f-248">Office 365</span><span class="sxs-lookup"><span data-stu-id="bef6f-248">Office 365</span></span>
- <span data-ttu-id="bef6f-249">Office 365 GCC</span><span class="sxs-lookup"><span data-stu-id="bef6f-249">Office 365 GCC</span></span>
- <span data-ttu-id="bef6f-250">Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="bef6f-250">Office 365 GCC High</span></span>
- <span data-ttu-id="bef6f-251">Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="bef6f-251">Office 365 DoD</span></span>

<span data-ttu-id="bef6f-252">다음 포트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-252">You must use the following ports:</span></span>

| <span data-ttu-id="bef6f-253">통신량</span><span class="sxs-lookup"><span data-stu-id="bef6f-253">Traffic</span></span> | <span data-ttu-id="bef6f-254">보낸 사람</span><span class="sxs-lookup"><span data-stu-id="bef6f-254">From</span></span> | <span data-ttu-id="bef6f-255">받는 사람</span><span class="sxs-lookup"><span data-stu-id="bef6f-255">To</span></span> | <span data-ttu-id="bef6f-256">원본 포트</span><span class="sxs-lookup"><span data-stu-id="bef6f-256">Source port</span></span> | <span data-ttu-id="bef6f-257">대상 포트</span><span class="sxs-lookup"><span data-stu-id="bef6f-257">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="bef6f-258">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="bef6f-258">SIP/TLS</span></span>| <span data-ttu-id="bef6f-259">SIP 프록시</span><span class="sxs-lookup"><span data-stu-id="bef6f-259">SIP Proxy</span></span> | <span data-ttu-id="bef6f-260">하더라도</span><span class="sxs-lookup"><span data-stu-id="bef6f-260">SBC</span></span> | <span data-ttu-id="bef6f-261">1024-65535</span><span class="sxs-lookup"><span data-stu-id="bef6f-261">1024 - 65535</span></span> | <span data-ttu-id="bef6f-262">SBC에 정의 됨</span><span class="sxs-lookup"><span data-stu-id="bef6f-262">Defined on the SBC</span></span> |
| <span data-ttu-id="bef6f-263">SIP/TLS</span><span class="sxs-lookup"><span data-stu-id="bef6f-263">SIP/TLS</span></span> | <span data-ttu-id="bef6f-264">하더라도</span><span class="sxs-lookup"><span data-stu-id="bef6f-264">SBC</span></span> | <span data-ttu-id="bef6f-265">SIP 프록시</span><span class="sxs-lookup"><span data-stu-id="bef6f-265">SIP Proxy</span></span> | <span data-ttu-id="bef6f-266">SBC에 정의 됨</span><span class="sxs-lookup"><span data-stu-id="bef6f-266">Defined on the SBC</span></span> | <span data-ttu-id="bef6f-267">5061</span><span class="sxs-lookup"><span data-stu-id="bef6f-267">5061</span></span> |


## <a name="media-traffic-ip-and-port-ranges"></a><span data-ttu-id="bef6f-268">미디어 트래픽: IP 및 포트 범위</span><span class="sxs-lookup"><span data-stu-id="bef6f-268">Media traffic: IP and Port ranges</span></span>

<span data-ttu-id="bef6f-269">클라이언트가 공용 IP 주소를 사용 하 여 SBC에 연결할 수 없는 경우 직접 연결을 사용할 수 있거나 팀을 통해 전송 되는 경우에는 SBC 및 팀 클라이언트 간 미디어 소통량이 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-269">Media traffic flows between the SBC and Teams client if direct connectivity is available or via Teams Transport Relays if the client cannot reach the SBC using the public IP address.</span></span>

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a><span data-ttu-id="bef6f-270">직접 미디어 트래픽 (팀 클라이언트와 SBC 간)에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bef6f-270">Requirements for direct media traffic (between the Teams client and the SBC)</span></span> 

<span data-ttu-id="bef6f-271">클라이언트는 SBC의 공용 IP 주소에 지정 된 포트 (표 참조)에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-271">The client must have access to the specified ports (see table) on the public IP address of the SBC.</span></span> 

<span data-ttu-id="bef6f-272">참고: 클라이언트가 내부 네트워크에 있는 경우 미디어는 SBC의 공용 IP 주소로 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-272">Note: If the client is in an internal network, the media flows to the public IP address of the SBC.</span></span> <span data-ttu-id="bef6f-273">NAT 장치에서 hairpinning를 구성 하 여 트래픽이 엔터프라이즈 네트워크 장비를 떠나는 일을 받지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-273">You can configure hairpinning on your NAT device so traffic never leaves the enterprise network equipment.</span></span>

| <span data-ttu-id="bef6f-274">통신량</span><span class="sxs-lookup"><span data-stu-id="bef6f-274">Traffic</span></span> | <span data-ttu-id="bef6f-275">보낸 사람</span><span class="sxs-lookup"><span data-stu-id="bef6f-275">From</span></span> | <span data-ttu-id="bef6f-276">받는 사람</span><span class="sxs-lookup"><span data-stu-id="bef6f-276">To</span></span> | <span data-ttu-id="bef6f-277">원본 포트</span><span class="sxs-lookup"><span data-stu-id="bef6f-277">Source port</span></span> | <span data-ttu-id="bef6f-278">대상 포트</span><span class="sxs-lookup"><span data-stu-id="bef6f-278">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="bef6f-279">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="bef6f-279">UDP/SRTP</span></span> | <span data-ttu-id="bef6f-280">클라이언트측</span><span class="sxs-lookup"><span data-stu-id="bef6f-280">Client</span></span> | <span data-ttu-id="bef6f-281">하더라도</span><span class="sxs-lookup"><span data-stu-id="bef6f-281">SBC</span></span> | <span data-ttu-id="bef6f-282">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="bef6f-282">50 000 – 50 019</span></span>  | <span data-ttu-id="bef6f-283">SBC에 정의 됨</span><span class="sxs-lookup"><span data-stu-id="bef6f-283">Defined on the SBC</span></span> |
| <span data-ttu-id="bef6f-284">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="bef6f-284">UDP/SRTP</span></span> | <span data-ttu-id="bef6f-285">하더라도</span><span class="sxs-lookup"><span data-stu-id="bef6f-285">SBC</span></span> | <span data-ttu-id="bef6f-286">클라이언트측</span><span class="sxs-lookup"><span data-stu-id="bef6f-286">Client</span></span> | <span data-ttu-id="bef6f-287">SBC에 정의 됨</span><span class="sxs-lookup"><span data-stu-id="bef6f-287">Defined on the SBC</span></span> | <span data-ttu-id="bef6f-288">50 000 – 50 019</span><span class="sxs-lookup"><span data-stu-id="bef6f-288">50 000 – 50 019</span></span>  |


<span data-ttu-id="bef6f-289">참고: 클라이언트의 원본 포트를 변환 하는 네트워크 장치가 있는 경우 네트워크 장비와 SBC 사이에 변환 된 포트가 열려 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="bef6f-289">Note: If you have a network device that translates the client's source ports, please make sure that translated ports are opened between the network equipment and the SBC.</span></span> 

### <a name="requirements-for-using-transport-relays"></a><span data-ttu-id="bef6f-290">전송 릴레이를 사용 하기 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bef6f-290">Requirements for using Transport Relays</span></span>

<span data-ttu-id="bef6f-291">전송 릴레이는 미디어 프로세서와 같은 범위에 있습니다 (바이패스 이외의 경우).</span><span class="sxs-lookup"><span data-stu-id="bef6f-291">Transport Relays are in the same range as Media Processors (for non-bypass cases):</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="bef6f-292">Office 365 및 Office 365 GCC 환경</span><span class="sxs-lookup"><span data-stu-id="bef6f-292">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="bef6f-293">-52.112.0.0/14 (52.112.0.1에서 52.115.255.254 까지의 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="bef6f-293">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="bef6f-294">Office 365 GCC DoD 환경</span><span class="sxs-lookup"><span data-stu-id="bef6f-294">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="bef6f-295">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="bef6f-295">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="bef6f-296">Office 365 GCC High 환경</span><span class="sxs-lookup"><span data-stu-id="bef6f-296">Office 365 GCC High environment</span></span>

- <span data-ttu-id="bef6f-297">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="bef6f-297">52.127.88.0/21</span></span>


<span data-ttu-id="bef6f-298">모든 환경에 적용 되는 팀 전송 릴레이의 포트 범위는 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-298">The port range of the Teams Transport Relays (applicable to all environments) is shown in the following table:</span></span>


| <span data-ttu-id="bef6f-299">통신량</span><span class="sxs-lookup"><span data-stu-id="bef6f-299">Traffic</span></span> | <span data-ttu-id="bef6f-300">보낸 사람</span><span class="sxs-lookup"><span data-stu-id="bef6f-300">From</span></span> | <span data-ttu-id="bef6f-301">받는 사람</span><span class="sxs-lookup"><span data-stu-id="bef6f-301">To</span></span> | <span data-ttu-id="bef6f-302">원본 포트</span><span class="sxs-lookup"><span data-stu-id="bef6f-302">Source port</span></span> | <span data-ttu-id="bef6f-303">대상 포트</span><span class="sxs-lookup"><span data-stu-id="bef6f-303">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="bef6f-304">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="bef6f-304">UDP/SRTP</span></span> | <span data-ttu-id="bef6f-305">전송 릴레이</span><span class="sxs-lookup"><span data-stu-id="bef6f-305">Transport Relay</span></span> | <span data-ttu-id="bef6f-306">하더라도</span><span class="sxs-lookup"><span data-stu-id="bef6f-306">SBC</span></span> | <span data-ttu-id="bef6f-307">50 000-59 999</span><span class="sxs-lookup"><span data-stu-id="bef6f-307">50 000 -59 999</span></span>    | <span data-ttu-id="bef6f-308">SBC에 정의 됨</span><span class="sxs-lookup"><span data-stu-id="bef6f-308">Defined on the SBC</span></span> |
| <span data-ttu-id="bef6f-309">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="bef6f-309">UDP/SRTP</span></span> | <span data-ttu-id="bef6f-310">하더라도</span><span class="sxs-lookup"><span data-stu-id="bef6f-310">SBC</span></span> | <span data-ttu-id="bef6f-311">전송 릴레이</span><span class="sxs-lookup"><span data-stu-id="bef6f-311">Transport Relay</span></span> | <span data-ttu-id="bef6f-312">SBC에 정의 됨</span><span class="sxs-lookup"><span data-stu-id="bef6f-312">Defined on the SBC</span></span> | <span data-ttu-id="bef6f-313">50 000-59 999, 3478, 3479</span><span class="sxs-lookup"><span data-stu-id="bef6f-313">50 000 – 59 999, 3478, 3479</span></span>     |


<span data-ttu-id="bef6f-314">참고: Microsoft에서는 SBC에 대 한 동시 호출 당 포트를 두 개 이상 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-314">Note: Microsoft recommends at least two ports per concurrent call on the SBC.</span></span> <span data-ttu-id="bef6f-315">Microsoft에는 두 가지 버전의 전송 중계이 있기 때문에 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-315">Because Microsoft has two versions of Transport Relays, the following are required:</span></span>

- <span data-ttu-id="bef6f-316">v4-포트 범위 50 000 ~ 59 999에만 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-316">v4, which can only work with port range 50 000 to 59 999</span></span>

- <span data-ttu-id="bef6f-317">포트 3478, 3479에서 작동 하는 v6</span><span class="sxs-lookup"><span data-stu-id="bef6f-317">v6, which works with ports 3478, 3479</span></span>

<span data-ttu-id="bef6f-318">현재 미디어 바이패스는 v4 버전의 전송 릴레이만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-318">At this time, media bypass only supports v4 version of Transport Relays.</span></span> <span data-ttu-id="bef6f-319">앞으로 v6에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-319">We will introduce support of v6 in the future.</span></span> 

<span data-ttu-id="bef6f-320">전환을 위해 포트 3478 및 3479을 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-320">You need to open ports 3478 and 3479 for transitioning.</span></span> <span data-ttu-id="bef6f-321">Microsoft에서 미디어 바이패스를 사용 하 여 v6 전송 릴레이에 대 한 지원을 도입 하는 경우 네트워크 장비 또는 SBCs를 다시 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-321">When Microsoft introduces support for v6 Transport Relays with Media Bypass, you will not need to reconfigure your network equipment or SBCs.</span></span> 

### <a name="requirements-for-using-media-processors"></a><span data-ttu-id="bef6f-322">미디어 프로세서 사용에 대 한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bef6f-322">Requirements for using media processors</span></span>

<span data-ttu-id="bef6f-323">미디어 프로세서는 항상 음성 응용 프로그램 및 웹 cleints 미디어 경로에 있습니다 (exampe의 경우 팀 cleint Edge 또는 Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="bef6f-323">Media Processors are always in the media path for voice applications and for Web cleints (for exampe, Teams cleint in Edge or Google Chrome).</span></span> <span data-ttu-id="bef6f-324">요구 사항은 비 바이패스 구성의 경우와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-324">The requirements are the same as for non-bypass configuration.</span></span>


<span data-ttu-id="bef6f-325">미디어 트래픽 IP 범위는</span><span class="sxs-lookup"><span data-stu-id="bef6f-325">The IP range for media traffic is</span></span> 

### <a name="office-365-and-office-365-gcc-environments"></a><span data-ttu-id="bef6f-326">Office 365 및 Office 365 GCC 환경</span><span class="sxs-lookup"><span data-stu-id="bef6f-326">Office 365 and Office 365 GCC environments</span></span>

<span data-ttu-id="bef6f-327">-52.112.0.0/14 (52.112.0.1에서 52.115.255.254 까지의 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="bef6f-327">-52.112.0.0 /14 (IP addresses from 52.112.0.1 to 52.115.255.254)</span></span>

## <a name="office-365-gcc-dod-environment"></a><span data-ttu-id="bef6f-328">Office 365 GCC DoD 환경</span><span class="sxs-lookup"><span data-stu-id="bef6f-328">Office 365 GCC DoD environment</span></span>

- <span data-ttu-id="bef6f-329">52.127.64.0/21</span><span class="sxs-lookup"><span data-stu-id="bef6f-329">52.127.64.0/21</span></span>

### <a name="office-365-gcc-high-environment"></a><span data-ttu-id="bef6f-330">Office 365 GCC High 환경</span><span class="sxs-lookup"><span data-stu-id="bef6f-330">Office 365 GCC High environment</span></span>

- <span data-ttu-id="bef6f-331">52.127.88.0/21</span><span class="sxs-lookup"><span data-stu-id="bef6f-331">52.127.88.0/21</span></span>

<span data-ttu-id="bef6f-332">모든 환경에 적용 되는 미디어 프로세서의 포트 범위는 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-332">The port range of the Media Processors (applicable to all environments) is shown in the following table:</span></span>

| <span data-ttu-id="bef6f-333">통신량</span><span class="sxs-lookup"><span data-stu-id="bef6f-333">Traffic</span></span> | <span data-ttu-id="bef6f-334">보낸 사람</span><span class="sxs-lookup"><span data-stu-id="bef6f-334">From</span></span> | <span data-ttu-id="bef6f-335">받는 사람</span><span class="sxs-lookup"><span data-stu-id="bef6f-335">To</span></span> | <span data-ttu-id="bef6f-336">원본 포트</span><span class="sxs-lookup"><span data-stu-id="bef6f-336">Source port</span></span> | <span data-ttu-id="bef6f-337">대상 포트</span><span class="sxs-lookup"><span data-stu-id="bef6f-337">Destination port</span></span>|
| :-------- | :-------- |:-----------|:--------|:---------|
<span data-ttu-id="bef6f-338">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="bef6f-338">UDP/SRTP</span></span> | <span data-ttu-id="bef6f-339">미디어 프로세서</span><span class="sxs-lookup"><span data-stu-id="bef6f-339">Media Processor</span></span> | <span data-ttu-id="bef6f-340">하더라도</span><span class="sxs-lookup"><span data-stu-id="bef6f-340">SBC</span></span> | <span data-ttu-id="bef6f-341">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="bef6f-341">49 152 – 53 247</span></span>    | <span data-ttu-id="bef6f-342">SBC에 정의 됨</span><span class="sxs-lookup"><span data-stu-id="bef6f-342">Defined on the SBC</span></span> |
| <span data-ttu-id="bef6f-343">UDP/SRTP</span><span class="sxs-lookup"><span data-stu-id="bef6f-343">UDP/SRTP</span></span> | <span data-ttu-id="bef6f-344">하더라도</span><span class="sxs-lookup"><span data-stu-id="bef6f-344">SBC</span></span> | <span data-ttu-id="bef6f-345">미디어 프로세서</span><span class="sxs-lookup"><span data-stu-id="bef6f-345">Media Processor</span></span> | <span data-ttu-id="bef6f-346">SBC에 정의 됨</span><span class="sxs-lookup"><span data-stu-id="bef6f-346">Defined on the SBC</span></span> | <span data-ttu-id="bef6f-347">49 152 – 53 247</span><span class="sxs-lookup"><span data-stu-id="bef6f-347">49 152 – 53 247</span></span>     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a><span data-ttu-id="bef6f-348">네트워크에 비즈니스용 Skype 전화를 사용 하는 경우의 고려 사항</span><span class="sxs-lookup"><span data-stu-id="bef6f-348">Considerations if you have Skype for Business phones in your network</span></span>  

<span data-ttu-id="bef6f-349">네트워크에 직접 라우팅을 사용 하는 비즈니스용 Skype 끝점이 있는 경우 (예: 비즈니스용 Skype 클라이언트를 기반으로 한 팀 사용자는 3PIP 휴대폰을 사용할 수 있음), 이러한 사용자를 위해 제공 하는 트렁크의 미디어 바이패스는 꺼야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-349">If you have any Skype for Business end points in your network that are using Direct Routing--for example, a Teams user can have a 3PIP phone that is based on Skype for Business client--the media bypass on the trunk that serves these users must be turned off.</span></span>

<span data-ttu-id="bef6f-350">이러한 사용자를 위해 별도의 트렁크를 만들고 온라인 음성 라우팅 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-350">You can create a separate trunk for these users and assign it an Online Voice Routing policy.</span></span>

<span data-ttu-id="bef6f-351">상위 수준 구성 단계:</span><span class="sxs-lookup"><span data-stu-id="bef6f-351">High-level configuration steps:</span></span>

- <span data-ttu-id="bef6f-352">사용자에 게 3PIP 휴대폰이 있는지 여부에 따라 유형별로 사용자를 분할 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-352">Split users by type – depending on whether the user has a 3PIP phone or not.</span></span>

- <span data-ttu-id="bef6f-353">다른 Fqdn을 사용 하 여 별도의 trunks를 만듭니다 (미디어 바이패스에 사용 가능). 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-353">Create two separate trunks with different FQDNs: one enabled for media bypass; the other not.</span></span> 

  <span data-ttu-id="bef6f-354">두 trunks 모두 동일한 SBC를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-354">Both trunks point to the same SBC.</span></span> <span data-ttu-id="bef6f-355">TLS SIP 신호에 대 한 포트는 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-355">The ports for TLS SIP signaling must be different.</span></span> <span data-ttu-id="bef6f-356">미디어의 포트는 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-356">The ports for media must be the same.</span></span>

- <span data-ttu-id="bef6f-357">온라인 음성 라우팅 정책에서 사용자의 유형에 따라 올바른 트렁크를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-357">Assign the correct trunk depending on the type of the user in the Online Voice Routing policy.</span></span>

<span data-ttu-id="bef6f-358">아래 예제에서는이 논리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-358">The example below illustrates this logic.</span></span>

| <span data-ttu-id="bef6f-359">사용자 집합</span><span class="sxs-lookup"><span data-stu-id="bef6f-359">Set of users</span></span> | <span data-ttu-id="bef6f-360">사용자 수</span><span class="sxs-lookup"><span data-stu-id="bef6f-360">Number of users</span></span> | <span data-ttu-id="bef6f-361">OVRP에 할당 된 트렁크 FQDN</span><span class="sxs-lookup"><span data-stu-id="bef6f-361">Trunk FQDN assigned in OVRP</span></span> | <span data-ttu-id="bef6f-362">미디어 바이패스 사용</span><span class="sxs-lookup"><span data-stu-id="bef6f-362">Media bypass enabled</span></span> |
| :------------ |:----------------- |:--------------|:--------------|
<span data-ttu-id="bef6f-363">팀 클라이언트 및 3PIP 휴대폰을 사용 하는 사용자</span><span class="sxs-lookup"><span data-stu-id="bef6f-363">Users with Teams clients and 3PIP phones</span></span> | <span data-ttu-id="bef6f-364">명</span><span class="sxs-lookup"><span data-stu-id="bef6f-364">20</span></span> | <span data-ttu-id="bef6f-365">sbc1.contoso.com:5061</span><span class="sxs-lookup"><span data-stu-id="bef6f-365">sbc1.contoso.com:5061</span></span> | <span data-ttu-id="bef6f-366">해제</span><span class="sxs-lookup"><span data-stu-id="bef6f-366">false</span></span> | 
<span data-ttu-id="bef6f-367">팀 종단점만 있는 사용자 (팀에 대해 인증 된 새 전화 포함)</span><span class="sxs-lookup"><span data-stu-id="bef6f-367">Users with only Teams end points (including new phones certified for Teams)</span></span> | <span data-ttu-id="bef6f-368">980</span><span class="sxs-lookup"><span data-stu-id="bef6f-368">980</span></span> | <span data-ttu-id="bef6f-369">sbc2.contoso.com:5060</span><span class="sxs-lookup"><span data-stu-id="bef6f-369">sbc2.contoso.com:5060</span></span> | <span data-ttu-id="bef6f-370">false</span><span class="sxs-lookup"><span data-stu-id="bef6f-370">true</span></span>

<span data-ttu-id="bef6f-371">두 trunks 모두 동일한 공용 IP 주소를 사용 하 여 동일한 SBC를 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-371">Both trunks can point to the same SBC with the same public IP address.</span></span> <span data-ttu-id="bef6f-372">SBC의 TLS 신호 포트는 다음 다이어그램에 표시 된 것과 같이 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-372">The TLS signaling ports on the SBC must be different, as shown in the following diagram.</span></span> <span data-ttu-id="bef6f-373">참고 인증서가 두 trunks를 모두 지원 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-373">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="bef6f-374">SAN에는 두 개의 이름 (**sbc1.contoso.com** 및 **sbc2.contoso.com**)이 있거나 와일드 카드 인증서가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-374">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>


![두 trunks 모두 동일한 공용 IP를 사용 하 여 동일한 SBC를 가리킬 수 있는지 표시 합니다.](media/direct-routing-media-bypass-7.png)

<span data-ttu-id="bef6f-376">동일한 SBC에서 두 개의 trunks를 구성 하는 방법에 대 한 자세한 내용은 SBC 공급 업체에서 제공 하는 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bef6f-376">For information about how to configure two trunks on the same SBC, see the documentation provided by your SBC vendor:</span></span>

 - [<span data-ttu-id="bef6f-377">오디오 코드 배포 설명서</span><span class="sxs-lookup"><span data-stu-id="bef6f-377">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="bef6f-378">Oracle 배포 문서</span><span class="sxs-lookup"><span data-stu-id="bef6f-378">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="bef6f-379">리본 커뮤니케이션 배포 문서</span><span class="sxs-lookup"><span data-stu-id="bef6f-379">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="bef6f-380">TE-시스템 (anynode) 배포 문서</span><span class="sxs-lookup"><span data-stu-id="bef6f-380">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a><span data-ttu-id="bef6f-381">미디어 바이패스에서 지원 되는 클라이언트 끝점</span><span class="sxs-lookup"><span data-stu-id="bef6f-381">Client endpoints supported with media bypass</span></span>

<span data-ttu-id="bef6f-382">미디어 건너뛰기는 모든 팀 끝점에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-382">Media bypass is supported with all Teams endpoints.</span></span>

<span data-ttu-id="bef6f-383">참고 webcleints (Microsoft Edge의 팀 웹 앱, Google Chrome 또는 Mozilla Firefox)의 경우에는 호출이 우회로 시작 되는 경우에도이를 우회 되지 않은 것으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-383">Note for webcleints (Teams Web app in Microsoft Edge, Google Chrome or Mozilla Firefox) we will covert the call to non-bypass even of it started as a bypass call.</span></span> <span data-ttu-id="bef6f-384">이는 자동으로 수행 되며 관리자가 수행할 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bef6f-384">This happens automatically and does not require any actions on the administrator.</span></span> 
 
## <a name="see-also"></a><span data-ttu-id="bef6f-385">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bef6f-385">See also</span></span>

[<span data-ttu-id="bef6f-386">직접 라우팅으로 미디어 우회 구성</span><span class="sxs-lookup"><span data-stu-id="bef6f-386">Configure media bypass with Direct Routing</span></span>](direct-routing-configure-media-bypass.md)



