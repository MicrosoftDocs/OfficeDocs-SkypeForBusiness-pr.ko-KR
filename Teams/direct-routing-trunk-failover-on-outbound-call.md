---
title: 발신 전화에 대한 트렁크 장애 조치
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
description: 이 항목을 읽고 Teams에서 SBC(세션 테두리 컨트롤러)로의 아웃바운드 호출에서 트렁크 장애 조치(failover)를 처리하는 방법을 배워야 합니다.
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836180"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="43454-103">발신 전화에 대한 트렁크 장애 조치</span><span class="sxs-lookup"><span data-stu-id="43454-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="43454-104">이 항목에서는 Teams에서 SBC(세션 테두리 컨트롤러)로의 아웃바운드 호출에서 트렁크 장애 조치(failover)를 방지하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43454-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="43454-105">네트워크 오류에 대한 장애 조치</span><span class="sxs-lookup"><span data-stu-id="43454-105">Failover on network errors</span></span>

<span data-ttu-id="43454-106">어떤 이유로든 트렁크를 연결할 수 없는 경우 다른 Microsoft 데이터 센터에서 동일한 트렁크에 대한 연결을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="43454-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="43454-107">트렁크가 연결되지 않을 수 있습니다. 예를 들어 연결이 거부되거나 TLS 시간 제한이 있는 경우 또는 다른 네트워크 수준 문제가 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="43454-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="43454-108">예를 들어 관리자가 잘 알려진 IP 주소에서만 SBC에 대한 액세스를 제한하지만 모든 Microsoft 직접 라우팅 데이터 센터의 IP 주소를 SBC의 ACL(액세스 제어 목록)에 넣지 못하면 연결이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43454-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="43454-109">SBC(세션 테두리 컨트롤러)에서 받은 특정 SIP 코드의 장애 조치(failover)</span><span class="sxs-lookup"><span data-stu-id="43454-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="43454-110">직접 라우팅이 발신 초대에 대한 응답으로 4xx 또는 6xx SIP 오류 코드를 수신하는 경우 호출은 기본적으로 완료된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="43454-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="43454-111">발신은 Teams 클라이언트에서 PSTN(공용 전환 전화 네트워크)으로의 통화를 의미하고, Teams 클라이언트 -> 직접 라우팅 -> SBC -> Telephony 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="43454-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="43454-112">SIP 코드 목록은 [SIP(세션 시작 프로토콜) RFC에서 찾을 수 있습니다.](https://tools.ietf.org/html/rfc3261)</span><span class="sxs-lookup"><span data-stu-id="43454-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="43454-113">SBC가 들어오는 초대에 "408 요청 시간 제한: 서버가 적절한 시간 내에 응답을 생성하지 못했습니다(예: 시간 내에 사용자의 위치를 확인할 수 없는 경우).</span><span class="sxs-lookup"><span data-stu-id="43454-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="43454-114">클라이언트는 나중에 수정하지 않고 요청을 반복할 수 있습니다."</span><span class="sxs-lookup"><span data-stu-id="43454-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="43454-115">이 특정 SBC는 네트워크 구성 오류 또는 기타 오류로 인하여 호출자에 연결하는 데 어려움이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43454-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="43454-116">그러나 경로에 발신자에 도달할 수 있는 SBC가 하나 더 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43454-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="43454-117">다음 다이어그램에서는 사용자가 전화 번호로 전화를 걸 때 이 호출을 배달할 수 있는 경로에 두 개의 SBC가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43454-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="43454-118">처음에는 SBC1.contoso.com 선택되지만 네트워크 SBC1.contoso.com 문제로 인해 PTSN 네트워크에 도달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43454-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="43454-119">기본적으로 이 순간에는 호출이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="43454-119">By default, the call will be completed at this moment.</span></span> 
 
![네트워크 문제로 인해 SBC가 PSTN에 도달할 수 없는 경우를 보여주는 다이어그램](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="43454-121">하지만 경로에 호출을 배달할 수 있는 SBC가 하나 더 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43454-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="43454-122">매개 변수를 구성하는 경우 다음 다이어그램에서 두 `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` 번째 SBC가 SBC2.contoso.com 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="43454-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![두 번째 SBC로의 라우팅을 보여주는 다이어그램](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="43454-124">매개 변수 -FailoverResponseCodes를 설정하고 코드를 지정하면 라우팅을 미세 조정하고 SBC가 네트워크 또는 기타 문제로 인해 호출을 할 수 없는 경우 잠재적인 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43454-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="43454-125">기본값: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="43454-125">Default values:  408, 503, 504</span></span>

