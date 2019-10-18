---
title: 아웃 바운드 통화에 대 한 트렁크 장애 조치
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
description: 팀에서 SBC (세션 경계 컨트롤러)로의 아웃 바운드 호출에서 트렁크 장애 조치를 처리 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: a5462de971fed32a0618800b257b9c6e37b462af
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572127"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="c9575-103">아웃 바운드 통화에 대 한 트렁크 장애 조치</span><span class="sxs-lookup"><span data-stu-id="c9575-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="c9575-104">이 항목에서는 팀에서 세션 경계 컨트롤러 (SBC)로 나가는 호출에 대 한 트렁크 장애 조치를 방지 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="c9575-105">네트워크 오류에 대 한 장애 조치</span><span class="sxs-lookup"><span data-stu-id="c9575-105">Failover on network errors</span></span>

<span data-ttu-id="c9575-106">트렁크를 어떤 이유로 든 연결할 수 없는 경우 같은 트렁크에 대 한 연결이 다른 Microsoft Datacenter에서 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="c9575-107">연결이 거부 되었거나, TLS 시간이 초과 되거나, 기타 네트워크 수준 문제가 있는 경우 트렁크가 연결 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="c9575-108">예를 들어 관리자가 잘 알려진 IP 주소 에서만 SBC에 대 한 액세스를 제한 하는 경우 연결이 실패할 수 있지만 SBC의 ACL (액세스 제어 목록)에 모든 Microsoft 직접 라우팅 데이터 센터의 IP 주소를 넣지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="c9575-109">SBC (세션 경계 컨트롤러)에서 받은 특정 SIP 코드의 장애 조치</span><span class="sxs-lookup"><span data-stu-id="c9575-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="c9575-110">송신 초대에 대 한 응답으로 직접 라우팅이 4xx 또는 6xx SIP 오류 코드를 수신 하는 경우에는 통화가 기본적으로 완료 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="c9575-111">발신은 팀 클라이언트에서 다음 트래픽 흐름을 통해 PSTN (공개 교환 전화 네트워크)로 전화를 거는 것을 의미 합니다. 팀 클라이언트 > 직접 라우팅-> SBC-> 전화 통신 네트워크.</span><span class="sxs-lookup"><span data-stu-id="c9575-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="c9575-112">SIP 코드 목록은 [sip (세션 시작 프로토콜) RFC](https://tools.ietf.org/html/rfc3261)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="c9575-113">SBC에서 코드 "408 요청 시간 초과: 사용자의 위치를 확인할 수 없는 경우와 같이 적절 한 시간 내에 서버에서 응답을 생성할 수 없는 상황이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="c9575-114">나중에 수정 하지 않고 클라이언트가 요청을 반복할 수 있습니다. "</span><span class="sxs-lookup"><span data-stu-id="c9575-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="c9575-115">이 특정 SBC는 네트워크를 잘못 구성 했거나 기타 오류로 인해 호출 수신자에 게 연결 하는 데 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="c9575-116">그러나 경로에는 호출 수신자에 도달할 수 있는 SBC 하나가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="c9575-117">다음 다이어그램에서 사용자가 전화 번호를 호출 하면 경로에 두 개의 SBCs가 있어이 통화를 잠재적으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="c9575-118">처음에는 통화를 위해 SBC1.contoso.com가 선택 되지만 SBC1.contoso.com는 네트워크 문제로 인해 PTSN 네트워크에 접속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="c9575-119">기본적으로이 통화는 현재 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-119">By default, the call will be completed at this moment.</span></span> 
 
![네트워크 문제로 인해 SBC에 연결할 수 없음 SBC을 보여 주는 다이어그램](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="c9575-121">그러나 경로에는 통화를 전달할 수 있는 SBC가 하나 더 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="c9575-122">매개 변수 `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`를 구성 하는 경우 두 번째 SBC는 다음 다이어그램에서 SBC2.contoso.com 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![두 번째 SBC에 대 한 라우팅을 보여 주는 다이어그램](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="c9575-124">FailoverResponseCodes 매개 변수를 설정 하 고 코드를 지정 하면 네트워크 또는 기타 문제로 인해 SBC에서 전화를 걸 수 없을 때 경로를 세부적으로 조정 하 고 잠재적인 문제를 방지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9575-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="c9575-125">기본값: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="c9575-125">Default values:  408, 503, 504</span></span>

