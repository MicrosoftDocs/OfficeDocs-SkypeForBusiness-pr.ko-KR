---
title: 'Lync Server 2013: 영구 채팅 서버에 대 한 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c6bb3c7dcd8d03ffb0a57fb165fe1dba4ee933d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512805"
---
# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="426bf-102">Lync Server 2013의 영구 채팅 서버에 대 한 용량 계획</span><span class="sxs-lookup"><span data-stu-id="426bf-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="426bf-103">_**마지막으로 수정 된 항목:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="426bf-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="426bf-104">영구 채팅 서버는 향후 검색 및 검색을 위해 유지할 수 있는 여러 사용자 실시간 채팅을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="426bf-105">사용자의 사서함에 저장 되는 IM (인스턴트 메시징)과 달리 대화 기록이 구성 되 면 영구 채팅 서버 세션은 계속 해 서 열려 있는 상태로 유지 되며, 콘텐츠는 진행 중인 대화의 일부인 메시지, 파일, Url 및 기타 데이터와 함께 서버에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="426bf-106">영구 채팅 서버 배포를 준비 하는 데 있어 용량 계획은 중요 한 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="426bf-107">이 항목에서는 배포에 가장 적합 한 구성을 결정 하는 데 사용할 수 있는 지원 되는 영구 채팅 서버 토폴로지 및 용량 계획 표에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="426bf-108">또한 사용량이 가장 많은 시간에 더 많은 용량을 필요로 하는 영구 채팅 서버 배포를 최상으로 관리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="426bf-109">영구 채팅 서버를 다운로드 하려면에서 "Microsoft Lync Server 13영구 채팅 서버"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539) 하세요.</span><span class="sxs-lookup"><span data-stu-id="426bf-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="426bf-110">영구 채팅 서버를 설치 하는 방법에 대 한 자세한 내용은 배포 설명서의 lync [server 2013에서 영구 채팅 서버 설치](lync-server-2013-installing-persistent-chat-server.md) 및 [lync Server 2013의 영구 채팅 서버 구성을](lync-server-2013-configuring-persistent-chat-server.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="426bf-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="426bf-111">Lync Server 계획 도구와 같은 지원 도구를 사용 하면 용량을 계획 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="426bf-112">계획 도구에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013에 대 한 계획 프로세스 시작](lync-server-2013-beginning-the-planning-process.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="426bf-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="426bf-113">영구 채팅 서버 지원 토폴로지</span><span class="sxs-lookup"><span data-stu-id="426bf-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="426bf-114">단일 서버 또는 다중 서버 풀 및 단일 풀 또는 다중 풀 토폴로지에 영구 채팅 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="426bf-115">이제 새 Lync Server 2013 배포를 위한 Standard Edition Server의 영구 채팅 서버도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="426bf-116">그러나 성능 및 확장성이 영향을 받으며,이 새 배포에 대 한 고가용성 옵션이 없기 때문에 개념 증명, 평가 등의 목적으로이를 주로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="426bf-117">두 토폴로지에 대 한 자세한 내용은이 문서의 <A href="lync-server-2013-planning-for-persistent-chat-server.md">Lync server 2013에서 영구 채팅 서버 계획</A> 및 배포 설명서의 <A href="lync-server-2013-deploying-persistent-chat-server.md">lync Server 2013에서 영구 채팅 서버 배포</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="426bf-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="426bf-118">단일 서버 토폴로지</span><span class="sxs-lookup"><span data-stu-id="426bf-118">Single-Server Topology</span></span>

<span data-ttu-id="426bf-119">영구 채팅 서버에 대 한 최소 구성 및 가장 간단한 배포는 단일 영구 채팅 서버 프런트 엔드 서버 토폴로지입니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="426bf-120">이 배포를 사용 하려면 영구 채팅 서버를 실행 하는 단일 서버 (필요한 경우 준수 서비스를 실행 하는 경우), SQL Server 데이터베이스를 모두 호스트 하는 서버, 준수 해야 하는 경우 SQL Server 데이터베이스에서 준수 데이터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="426bf-121">토폴로지 작성기에서 단일 서버 배포로 시작 된 영구 채팅 서버 풀에는 서버를 더 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="426bf-122">단일 서버를 사용 하는 경우에도 다중 서버 풀 토폴로지를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="426bf-123">이렇게 하면 나중에 서버를 더 추가할 수 있습니다 (필요한 경우).</span><span class="sxs-lookup"><span data-stu-id="426bf-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="426bf-124">다음 그림에서는 준수와 함께 단일 영구 채팅 서버 프런트 엔드 서버에 대 한 토폴로지의 모든 필수 및 선택적 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="426bf-125">**단일 영구 채팅 서버**</span><span class="sxs-lookup"><span data-stu-id="426bf-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="426bf-126">![준수 서비스를 사용 하는 단일 서버 토폴로지](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "준수 서비스를 사용 하는 단일 서버 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="426bf-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="426bf-127">다중 서버 토폴로지</span><span class="sxs-lookup"><span data-stu-id="426bf-127">Multiple-Server Topology</span></span>

<span data-ttu-id="426bf-128">더 많은 용량과 안정성을 제공 하기 위해 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)에 설명 된 대로 다중 서버 토폴로지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="426bf-129">다중 서버 토폴로지에는 영구 채팅 서버를 실행 하는 활성 컴퓨터가 최대 4 개까지 포함 될 수 있습니다 (고가용성 및 재해 복구 구성의 경우 8 개까지 가능 하지만 4 개만 활성화 될 수 있으며 나머지 4 개는 대기 중에 있음).</span><span class="sxs-lookup"><span data-stu-id="426bf-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="426bf-130">각 서버는 최대 2만 명의 동시 사용자를 지원할 수 있으며, 서버 4 대와 영구 채팅 서버 풀에 연결 된 총 8만 동시 사용자에 게 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="426bf-131">다중 서버 토폴로지는 다중 서버가 영구 채팅 서버를 호스트 하는 것을 제외 하 고는 단일 서버 토폴로지와 동일 하며 더 높은 규모를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="426bf-132">영구 채팅 서버를 실행 하는 여러 컴퓨터가 Lync Server 및 준수 서비스와 동일한 Active Directory 도메인 서비스 도메인에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="426bf-133">다음 그림에서는 영구 채팅 서버, 선택적 준수 서비스 및 별도의 준수 데이터베이스를 실행 하는 여러 컴퓨터를 사용 하는 다중 서버 토폴로지의 모든 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="426bf-134">**여러 영구 채팅 서버**</span><span class="sxs-lookup"><span data-stu-id="426bf-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="426bf-135">![다중 서버 토폴로지](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "다중 서버 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="426bf-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="426bf-136">5 대의 서버 영구 채팅 서버 배포에서 8만 사용자가 동시에 영구 채팅에 로그인 하 여 사용할 수 있는 경우 부하는 서버당 2만 사용자에 게 균등 하 게 분산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="426bf-137">한 서버를 사용할 수 없는 경우 해당 서버에 연결 된 사용자는 영구 채팅 서버에 대 한 액세스 권한을 잃게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="426bf-138">연결이 끊긴 사용자는 해당 서버가 복원될 때까지 나머지 서버로 자동으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="426bf-139">네트워크의 영구 채팅 트래픽 양에 따라이 전송에 몇 분 이상 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="426bf-140">나머지 각 서버가 3만 명의 사용자를 호스트 하는 경우에는 가능한 한 빨리 사용할 수 없는 서버를 복원 하 여 성능 문제가 발생 하지 않도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="426bf-141">그렇지 않으면 토폴로지 작성기 또는 Windows PowerShell cmdlet ( **set-cspersistentchatactiveserver)** 을 사용 하 여 다른 영구 채팅 서버를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="426bf-142">영구 채팅 서버 용량 계획</span><span class="sxs-lookup"><span data-stu-id="426bf-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="426bf-143">다음 표에서는 영구 채팅 서버에 대 한 용량 계획을 세울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="426bf-144">다양 한 영구 채팅 서버 설정이 용량 기능에 미치는 영향을 모델링 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="426bf-145">영구 채팅 서버에 대 한 최대 용량 계획</span><span class="sxs-lookup"><span data-stu-id="426bf-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="426bf-146">다음 샘플 표를 사용하여 지원할 사용자 수를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="426bf-147">영구 채팅 서버 풀 최대 용량 샘플</span><span class="sxs-lookup"><span data-stu-id="426bf-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="426bf-148">활성 영구 채팅 서비스 인스턴스</span><span class="sxs-lookup"><span data-stu-id="426bf-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="426bf-149"><em>1-4</em></span><span class="sxs-lookup"><span data-stu-id="426bf-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-150">영구 채팅 서비스 인스턴스</span><span class="sxs-lookup"><span data-stu-id="426bf-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="426bf-151"><em>8 (4는 비활성 이어야 하 고 최대 4 개만 활성화할 수 있음)</em></span><span class="sxs-lookup"><span data-stu-id="426bf-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-152">활성 사용자 연결 됨</span><span class="sxs-lookup"><span data-stu-id="426bf-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="426bf-153"><em>8만</em></span><span class="sxs-lookup"><span data-stu-id="426bf-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-154">총 프로 비전 된 사용자</span><span class="sxs-lookup"><span data-stu-id="426bf-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="426bf-155">15만</span><span class="sxs-lookup"><span data-stu-id="426bf-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-156">끝점 수</span><span class="sxs-lookup"><span data-stu-id="426bf-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="426bf-157">12만</span><span class="sxs-lookup"><span data-stu-id="426bf-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="426bf-158">앞의 예제에서이 계획은 영구 채팅 서버에서 허용 하는 최대 사용자 수를 지원 하 고, 영구 채팅 서비스의 서버/인스턴스 (고가용성 및 재해 복구를 위해 영구 채팅 서버를 실행 하는 수동 서버가 4 개 이상 있을 수 있음) 및 서버당 사용자 2만 명에 게 총 8만 활성 사용자를 지 원하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="426bf-159">영구 대화방 액세스 관리를 위한 용량 계획</span><span class="sxs-lookup"><span data-stu-id="426bf-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="426bf-160">다음 예제 테이블은 영구 채팅 서버 풀에서 영구 대화방 액세스 관리를 계획 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="426bf-161">대화방 액세스 관리 샘플</span><span class="sxs-lookup"><span data-stu-id="426bf-161">Managing Chat Room Access Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="426bf-162">작은 채팅방</span><span class="sxs-lookup"><span data-stu-id="426bf-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="426bf-163">중간 대화방</span><span class="sxs-lookup"><span data-stu-id="426bf-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="426bf-164">큰 대화방</span><span class="sxs-lookup"><span data-stu-id="426bf-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="426bf-165">합계</span><span class="sxs-lookup"><span data-stu-id="426bf-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="426bf-166">대화방 크기 (연결 된 사용자 수)</span><span class="sxs-lookup"><span data-stu-id="426bf-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="426bf-167">대화방 당 30 개</span><span class="sxs-lookup"><span data-stu-id="426bf-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="426bf-168">대화방 당 150</span><span class="sxs-lookup"><span data-stu-id="426bf-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="426bf-169">대화방 당 16000</span><span class="sxs-lookup"><span data-stu-id="426bf-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-170">대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-171">32000</span><span class="sxs-lookup"><span data-stu-id="426bf-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="426bf-172">1067</span><span class="sxs-lookup"><span data-stu-id="426bf-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="426bf-173">10  </span><span class="sxs-lookup"><span data-stu-id="426bf-173">10</span></span></p></td>
<td><p><span data-ttu-id="426bf-174">33077</span><span class="sxs-lookup"><span data-stu-id="426bf-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-175">강당 인 대화방의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="426bf-176">개</span><span class="sxs-lookup"><span data-stu-id="426bf-176">1%</span></span></p></td>
<td><p><span data-ttu-id="426bf-177">개</span><span class="sxs-lookup"><span data-stu-id="426bf-177">1%</span></span></p></td>
<td><p><span data-ttu-id="426bf-178">50%</span><span class="sxs-lookup"><span data-stu-id="426bf-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-179">열린 대화방 의%</span><span class="sxs-lookup"><span data-stu-id="426bf-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="426bf-180">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="426bf-180">3%</span></span></p></td>
<td><p><span data-ttu-id="426bf-181">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="426bf-181">3%</span></span></p></td>
<td><p><span data-ttu-id="426bf-182">50%</span><span class="sxs-lookup"><span data-stu-id="426bf-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-183">대화방 열기 (명시적 멤버 자격 없음)</span><span class="sxs-lookup"><span data-stu-id="426bf-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="426bf-184">960</span><span class="sxs-lookup"><span data-stu-id="426bf-184">960</span></span></p></td>
<td><p><span data-ttu-id="426bf-185">32</span><span class="sxs-lookup"><span data-stu-id="426bf-185">32</span></span></p></td>
<td><p><span data-ttu-id="426bf-186">5 </span><span class="sxs-lookup"><span data-stu-id="426bf-186">5</span></span></p></td>
<td><p><span data-ttu-id="426bf-187">997</span><span class="sxs-lookup"><span data-stu-id="426bf-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-188">열려 있지 않은 대화방 (명시적 구성원이 있는 일반 대화방)</span><span class="sxs-lookup"><span data-stu-id="426bf-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="426bf-189">31040</span><span class="sxs-lookup"><span data-stu-id="426bf-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="426bf-190">1.035</span><span class="sxs-lookup"><span data-stu-id="426bf-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="426bf-191">5 </span><span class="sxs-lookup"><span data-stu-id="426bf-191">5</span></span></p></td>
<td><p><span data-ttu-id="426bf-192">32080</span><span class="sxs-lookup"><span data-stu-id="426bf-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-193">강당 대화방 (추가 발표자 항목)</span><span class="sxs-lookup"><span data-stu-id="426bf-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="426bf-194">개</span><span class="sxs-lookup"><span data-stu-id="426bf-194">0</span></span></p></td>
<td><p><span data-ttu-id="426bf-195">32</span><span class="sxs-lookup"><span data-stu-id="426bf-195">32</span></span></p></td>
<td><p><span data-ttu-id="426bf-196">5 </span><span class="sxs-lookup"><span data-stu-id="426bf-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-197">직접 멤버 자격이 관리 하는 대화방</span><span class="sxs-lookup"><span data-stu-id="426bf-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="426bf-198">50%</span><span class="sxs-lookup"><span data-stu-id="426bf-198">50%</span></span></p></td>
<td><p><span data-ttu-id="426bf-199">10</span><span class="sxs-lookup"><span data-stu-id="426bf-199">10%</span></span></p></td>
<td><p><span data-ttu-id="426bf-200">개</span><span class="sxs-lookup"><span data-stu-id="426bf-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-201">사용자 그룹에서 관리하는 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="426bf-202">50%</span><span class="sxs-lookup"><span data-stu-id="426bf-202">50%</span></span></p></td>
<td><p><span data-ttu-id="426bf-203">90%</span><span class="sxs-lookup"><span data-stu-id="426bf-203">90%</span></span></p></td>
<td><p><span data-ttu-id="426bf-204">100%</span><span class="sxs-lookup"><span data-stu-id="426bf-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-205">열려 있는 대화방에 대 한 각 대화방의 구성원 목록에 있는 사용자 그룹 (명시적으로 지정 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="426bf-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="426bf-206">개</span><span class="sxs-lookup"><span data-stu-id="426bf-206">0</span></span></p></td>
<td><p><span data-ttu-id="426bf-207">개</span><span class="sxs-lookup"><span data-stu-id="426bf-207">0</span></span></p></td>
<td><p><span data-ttu-id="426bf-208">개</span><span class="sxs-lookup"><span data-stu-id="426bf-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-209">열려 있지 않은 채팅방에 대 한 각 대화방의 구성원 목록 사용자</span><span class="sxs-lookup"><span data-stu-id="426bf-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-210">kb</span><span class="sxs-lookup"><span data-stu-id="426bf-210">30</span></span></p></td>
<td><p><span data-ttu-id="426bf-211">150</span><span class="sxs-lookup"><span data-stu-id="426bf-211">150</span></span></p></td>
<td><p><span data-ttu-id="426bf-212">16000</span><span class="sxs-lookup"><span data-stu-id="426bf-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-213">열려 있지 않은 대화방에 대 한 각 대화방의 구성원 목록에 있는 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="426bf-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-214">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="426bf-214">3</span></span></p></td>
<td><p><span data-ttu-id="426bf-215">5 </span><span class="sxs-lookup"><span data-stu-id="426bf-215">5</span></span></p></td>
<td><p><span data-ttu-id="426bf-216">10  </span><span class="sxs-lookup"><span data-stu-id="426bf-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-217">각 대화방의 관리자 목록에 있는 사용자 및 사용자 그룹 (개방 된 채팅방의 경우)</span><span class="sxs-lookup"><span data-stu-id="426bf-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="426bf-218">6 </span><span class="sxs-lookup"><span data-stu-id="426bf-218">6</span></span></p></td>
<td><p><span data-ttu-id="426bf-219">6 </span><span class="sxs-lookup"><span data-stu-id="426bf-219">6</span></span></p></td>
<td><p><span data-ttu-id="426bf-220">6 </span><span class="sxs-lookup"><span data-stu-id="426bf-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-221">각 강당 대화방의 발표자 목록에 있는 사용자 및 사용자 그룹 (개방 된 채팅방 용)</span><span class="sxs-lookup"><span data-stu-id="426bf-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="426bf-222">6 </span><span class="sxs-lookup"><span data-stu-id="426bf-222">6</span></span></p></td>
<td><p><span data-ttu-id="426bf-223">6 </span><span class="sxs-lookup"><span data-stu-id="426bf-223">6</span></span></p></td>
<td><p><span data-ttu-id="426bf-224">6 </span><span class="sxs-lookup"><span data-stu-id="426bf-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-225">열려 있지 않은 모든 대화방의 사용자 기반 구성원 엔터티</span><span class="sxs-lookup"><span data-stu-id="426bf-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-226">465600</span><span class="sxs-lookup"><span data-stu-id="426bf-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="426bf-227">15520</span><span class="sxs-lookup"><span data-stu-id="426bf-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-228">열려 있지 않은 모든 대화방의 사용자 그룹 기반 구성원 엔터티</span><span class="sxs-lookup"><span data-stu-id="426bf-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-229">46560</span><span class="sxs-lookup"><span data-stu-id="426bf-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="426bf-230">4656</span><span class="sxs-lookup"><span data-stu-id="426bf-230">4656</span></span></p></td>
<td><p><span data-ttu-id="426bf-231">50</span><span class="sxs-lookup"><span data-stu-id="426bf-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-232">모든 강당 대화방에서 사용자 및 사용자 그룹 기반 엔터티</span><span class="sxs-lookup"><span data-stu-id="426bf-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-233">개</span><span class="sxs-lookup"><span data-stu-id="426bf-233">0</span></span></p></td>
<td><p><span data-ttu-id="426bf-234">192</span><span class="sxs-lookup"><span data-stu-id="426bf-234">192</span></span></p></td>
<td><p><span data-ttu-id="426bf-235">50</span><span class="sxs-lookup"><span data-stu-id="426bf-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-236">모든 대화방 관리자 목록에서 사용자 및 사용자 그룹 기반 관리자 엔터티</span><span class="sxs-lookup"><span data-stu-id="426bf-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="426bf-237">192000</span><span class="sxs-lookup"><span data-stu-id="426bf-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="426bf-238">6400</span><span class="sxs-lookup"><span data-stu-id="426bf-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="426bf-239">60</span><span class="sxs-lookup"><span data-stu-id="426bf-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-240">대화방당 활성 사용자 수</span><span class="sxs-lookup"><span data-stu-id="426bf-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="426bf-241"><em>kb</em></span><span class="sxs-lookup"><span data-stu-id="426bf-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="426bf-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-243"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="426bf-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-244">사용자당 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="426bf-245"><em>12</em></span><span class="sxs-lookup"><span data-stu-id="426bf-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="426bf-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="426bf-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-248"><em>~</em></span><span class="sxs-lookup"><span data-stu-id="426bf-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-249">각 대화방의 구성원 목록에 있는 사용자 그룹 수</span><span class="sxs-lookup"><span data-stu-id="426bf-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="426bf-250"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="426bf-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-251"><em>10</em></span><span class="sxs-lookup"><span data-stu-id="426bf-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-252"><em>f</em></span><span class="sxs-lookup"><span data-stu-id="426bf-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-253">사용자 그룹에서 관리하는 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="426bf-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="426bf-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="426bf-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="426bf-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-257">모든 대화방의 사용자 그룹 기반 구성원 엔터티 수</span><span class="sxs-lookup"><span data-stu-id="426bf-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-258">155200</span><span class="sxs-lookup"><span data-stu-id="426bf-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="426bf-259">5173</span><span class="sxs-lookup"><span data-stu-id="426bf-259">5173</span></span></p></td>
<td><p><span data-ttu-id="426bf-260">68</span><span class="sxs-lookup"><span data-stu-id="426bf-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-261">모든 대화방의 사용자 기반 구성원 엔터티 수</span><span class="sxs-lookup"><span data-stu-id="426bf-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-262">465600</span><span class="sxs-lookup"><span data-stu-id="426bf-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="426bf-263">77600</span><span class="sxs-lookup"><span data-stu-id="426bf-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="426bf-264">72000</span><span class="sxs-lookup"><span data-stu-id="426bf-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-265">각 대화방의 관리자, 발표자 및 범위 목록에 있는 사용자 및 사용자 그룹 수</span><span class="sxs-lookup"><span data-stu-id="426bf-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="426bf-266">6 </span><span class="sxs-lookup"><span data-stu-id="426bf-266">6</span></span></p></td>
<td><p><span data-ttu-id="426bf-267">6 </span><span class="sxs-lookup"><span data-stu-id="426bf-267">6</span></span></p></td>
<td><p><span data-ttu-id="426bf-268">6 </span><span class="sxs-lookup"><span data-stu-id="426bf-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-269">모든 대화방의 관리자, 발표자 및 범위 목록에 있는 사용자 및 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="426bf-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="426bf-270">192000</span><span class="sxs-lookup"><span data-stu-id="426bf-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="426bf-271">6400</span><span class="sxs-lookup"><span data-stu-id="426bf-271">6400</span></span></p></td>
<td><p><span data-ttu-id="426bf-272">60</span><span class="sxs-lookup"><span data-stu-id="426bf-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-273">액세스 제어 항목 수</span><span class="sxs-lookup"><span data-stu-id="426bf-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="426bf-274">704160</span><span class="sxs-lookup"><span data-stu-id="426bf-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="426bf-275">26768</span><span class="sxs-lookup"><span data-stu-id="426bf-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="426bf-276">160</span><span class="sxs-lookup"><span data-stu-id="426bf-276">160</span></span></p></td>
<td><p><span data-ttu-id="426bf-277">731088</span><span class="sxs-lookup"><span data-stu-id="426bf-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-278">최대 액세스 제어 항목 수</span><span class="sxs-lookup"><span data-stu-id="426bf-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="426bf-279">200만</span><span class="sxs-lookup"><span data-stu-id="426bf-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="426bf-280">위의 예제에서 권장 지침에 따라 영구 채팅 서버를 배포 하는 경우 준수를 사용 하도록 설정 된 4 대의 서버 풀에서 최대 8만 명의 활성 사용자를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="426bf-281">이 샘플은 작은 대화방 (지정 된 시간에 30 명의 활성 사용자), 보통 (150 활성 사용자) 및 대규모 (16000 활성 사용자)으로 분류 된 채팅방을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="426bf-282">특정 크기의 대화방 수는 다음 항목의 합계를 기반으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="426bf-283">시스템의 활성 사용자 수</span><span class="sxs-lookup"><span data-stu-id="426bf-283">Active users in the system</span></span>

  - <span data-ttu-id="426bf-284">지정된 크기의 대화방에 있는 활성 사용자 수</span><span class="sxs-lookup"><span data-stu-id="426bf-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="426bf-285">단일 사용자가 참가하는 지정된 크기의 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="426bf-286">각 대화방에 대해 이전 용량 계획 테이블은 대화방에 직접 할당 된 항목을 포함 하 여 대화방과 연결 된 액세스 제어 항목 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-286">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="426bf-287">ACL(액세스 제어 목록)을 사용하여 개별 대화방에 대한 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-287">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="426bf-288">또한 범주 수준에서 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-288">You can also control access at the category level.</span></span> <span data-ttu-id="426bf-289">ACL에서 개별 액세스 제어 항목은 사용자 그룹 (예: 보안 그룹, 메일 목록 또는 단일 사용자)이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-289">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="426bf-290">대화방 관리자, 발표자 및 구성원에 대한 액세스 제어 항목을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-290">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="426bf-291">채팅방을 관리 하기 위한 전략을 계획할 때 허용 되는 총 액세스 제어 항목 수가 200만 이라는 점을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-291">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="426bf-292">계산 된 액세스 제어 항목이 200만를 초과 하면 서버 성능이 크게 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-292">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="426bf-293">가능한 경우이 문제를 방지 하려면 액세스 제어 항목이 개별 사용자가 아닌 사용자 그룹 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-293">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="426bf-294">초대에 의한 대화방 액세스 관리를 위한 용량 계획</span><span class="sxs-lookup"><span data-stu-id="426bf-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="426bf-295">다음 용량 계획 표를 사용 하 여 영구 채팅 서버가 초대를 보내도록 구성 된 경우 영구 채팅 데이터베이스에서 만들고 저장 하는 초대 수를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="426bf-296">범주에 대 한 초대는 Lync Server 제어판의 **채팅방 범주 설정** 페이지를 사용 하거나, Windows PowerShell cmdlet **get-cspersistentchatcategory**를 사용 하 여 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="426bf-297">Lync 클라이언트에서 시작 된 **대화방 관리** 페이지를 사용 하거나 Windows PowerShell cmdlet **clear-cspersistentchatroom**를 사용 하 여 대화방 (범주에서 허용 하는 것과 같은 채팅방)에서 초대를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="426bf-298">다음 표의 예제 데이터에서는 대화방 **설정** 페이지에서 모든 대화방의 50%에 대 한 **초대** 옵션을 **' 예 '** 로 설정 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="426bf-299">서버에서 생성 하는 초대 수에 대해 계산 된 값이 100만를 초과 하면 서버 성능이 크게 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="426bf-300">이 문제를 방지 하려면 초대를 보내도록 구성 된 대화방 수를 최소화 하거나 초대를 보내도록 구성 된 대화방에 참가할 수 있는 사용자 수를 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="426bf-301">초대에 의한 대화방 액세스 샘플</span><span class="sxs-lookup"><span data-stu-id="426bf-301">Chat Room Access by Invitation Sample</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="426bf-302">작은 채팅방</span><span class="sxs-lookup"><span data-stu-id="426bf-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="426bf-303">중간 대화방</span><span class="sxs-lookup"><span data-stu-id="426bf-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="426bf-304">큰 대화방</span><span class="sxs-lookup"><span data-stu-id="426bf-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="426bf-305">합계</span><span class="sxs-lookup"><span data-stu-id="426bf-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="426bf-306">대화방에 액세스할 수 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="426bf-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="426bf-307">대화방 당 30 개</span><span class="sxs-lookup"><span data-stu-id="426bf-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="426bf-308">대화방 당 150</span><span class="sxs-lookup"><span data-stu-id="426bf-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="426bf-309">대화방 당 16000</span><span class="sxs-lookup"><span data-stu-id="426bf-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-310">초대가 있는 대화방의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="426bf-311">50%</span><span class="sxs-lookup"><span data-stu-id="426bf-311">50%</span></span></p></td>
<td><p><span data-ttu-id="426bf-312">50%</span><span class="sxs-lookup"><span data-stu-id="426bf-312">50%</span></span></p></td>
<td><p><span data-ttu-id="426bf-313">50%</span><span class="sxs-lookup"><span data-stu-id="426bf-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-314">초대를 보내도록 구성된 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="426bf-315"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="426bf-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="426bf-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-317"><em>2-5</em></span><span class="sxs-lookup"><span data-stu-id="426bf-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-318">대화방에 액세스할 수 있는 사용자 수</span><span class="sxs-lookup"><span data-stu-id="426bf-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="426bf-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="426bf-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="426bf-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="426bf-321"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="426bf-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-322">영구 채팅 서버에서 생성 된 초대</span><span class="sxs-lookup"><span data-stu-id="426bf-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="426bf-323">96만</span><span class="sxs-lookup"><span data-stu-id="426bf-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="426bf-324">12만</span><span class="sxs-lookup"><span data-stu-id="426bf-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="426bf-325">8만</span><span class="sxs-lookup"><span data-stu-id="426bf-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="426bf-326">116만</span><span class="sxs-lookup"><span data-stu-id="426bf-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-327">허용되는 최대 초대 수</span><span class="sxs-lookup"><span data-stu-id="426bf-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="426bf-328">200만</span><span class="sxs-lookup"><span data-stu-id="426bf-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-329">모델 1-일별 초당 예상 메시지 수로 시작</span><span class="sxs-lookup"><span data-stu-id="426bf-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-330">대화방 당 채팅 속도 (일별)</span><span class="sxs-lookup"><span data-stu-id="426bf-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="426bf-331">50</span><span class="sxs-lookup"><span data-stu-id="426bf-331">50</span></span></p></td>
<td><p><span data-ttu-id="426bf-332">500</span><span class="sxs-lookup"><span data-stu-id="426bf-332">500</span></span></p></td>
<td><p><span data-ttu-id="426bf-333">100</span><span class="sxs-lookup"><span data-stu-id="426bf-333">100</span></span></p></td>
<td><p><span data-ttu-id="426bf-334">650</span><span class="sxs-lookup"><span data-stu-id="426bf-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-335">모든 대화방에서의 초당 채팅 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-336">55.56</span><span class="sxs-lookup"><span data-stu-id="426bf-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="426bf-337">18.52</span><span class="sxs-lookup"><span data-stu-id="426bf-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="426bf-338">0.03</span><span class="sxs-lookup"><span data-stu-id="426bf-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="426bf-339">74</span><span class="sxs-lookup"><span data-stu-id="426bf-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-340">모델 2-사용자 당 하루에 게시 된 메시지 수에 따라 시작</span><span class="sxs-lookup"><span data-stu-id="426bf-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-341">일별 사용자 당 채팅 속도</span><span class="sxs-lookup"><span data-stu-id="426bf-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="426bf-342">15 </span><span class="sxs-lookup"><span data-stu-id="426bf-342">15</span></span></p></td>
<td><p><span data-ttu-id="426bf-343">5 </span><span class="sxs-lookup"><span data-stu-id="426bf-343">5</span></span></p></td>
<td><p><span data-ttu-id="426bf-344">0.1</span><span class="sxs-lookup"><span data-stu-id="426bf-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="426bf-345">20cm(8</span><span class="sxs-lookup"><span data-stu-id="426bf-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-346">대화방 당 채팅 속도 (일별)</span><span class="sxs-lookup"><span data-stu-id="426bf-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="426bf-347">38</span><span class="sxs-lookup"><span data-stu-id="426bf-347">38</span></span></p></td>
<td><p><span data-ttu-id="426bf-348">375</span><span class="sxs-lookup"><span data-stu-id="426bf-348">375</span></span></p></td>
<td><p><span data-ttu-id="426bf-349">800</span><span class="sxs-lookup"><span data-stu-id="426bf-349">800</span></span></p></td>
<td><p><span data-ttu-id="426bf-350">1213</span><span class="sxs-lookup"><span data-stu-id="426bf-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-351">모든 대화방에서의 초당 채팅 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-352">41.67</span><span class="sxs-lookup"><span data-stu-id="426bf-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="426bf-353">13.89</span><span class="sxs-lookup"><span data-stu-id="426bf-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="426bf-354">0.28</span><span class="sxs-lookup"><span data-stu-id="426bf-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="426bf-355">56</span><span class="sxs-lookup"><span data-stu-id="426bf-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="426bf-356">영구 채팅 서버 성능 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="426bf-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="426bf-357">다음 표에서는 영구 채팅 서버에 대 한 사용자 모델을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="426bf-358">용량 계획 요구 사항에 대 한 기반을 제공 하며, 4 대의 서버에서 동시 사용자 8만을 사용 하는 일반적인 조직을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="426bf-359">영구 채팅 서버 성능 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="426bf-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="426bf-360">연결 된 활성 사용자 수</span><span class="sxs-lookup"><span data-stu-id="426bf-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="426bf-361">8만</span><span class="sxs-lookup"><span data-stu-id="426bf-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-362">영구 채팅 서버 서비스 인스턴스 수</span><span class="sxs-lookup"><span data-stu-id="426bf-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="426bf-363">4 </span><span class="sxs-lookup"><span data-stu-id="426bf-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-364">소규모 대화방의 크기</span><span class="sxs-lookup"><span data-stu-id="426bf-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-365">사용자 30명</span><span class="sxs-lookup"><span data-stu-id="426bf-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-366">중규모 대화방의 크기</span><span class="sxs-lookup"><span data-stu-id="426bf-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-367">사용자 150명</span><span class="sxs-lookup"><span data-stu-id="426bf-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-368">대규모 대화방의 크기</span><span class="sxs-lookup"><span data-stu-id="426bf-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-369">16000 사용자</span><span class="sxs-lookup"><span data-stu-id="426bf-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-370">총 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-371">33077</span><span class="sxs-lookup"><span data-stu-id="426bf-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-372">소규모 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-373">32000</span><span class="sxs-lookup"><span data-stu-id="426bf-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-374">중규모 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-375">1067</span><span class="sxs-lookup"><span data-stu-id="426bf-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-376">대규모 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-377">10  </span><span class="sxs-lookup"><span data-stu-id="426bf-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-378">사용자당 총 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="426bf-379">16 </span><span class="sxs-lookup"><span data-stu-id="426bf-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-380">사용자당 소규모 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="426bf-381">12 </span><span class="sxs-lookup"><span data-stu-id="426bf-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-382">사용자당 중규모 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="426bf-383">2</span><span class="sxs-lookup"><span data-stu-id="426bf-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-384">사용자당 대규모 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="426bf-385">2</span><span class="sxs-lookup"><span data-stu-id="426bf-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-386">사용자 당 가입 된 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="426bf-387">mb</span><span class="sxs-lookup"><span data-stu-id="426bf-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-388">최대 참가 비율</span><span class="sxs-lookup"><span data-stu-id="426bf-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="426bf-389">10/초</span><span class="sxs-lookup"><span data-stu-id="426bf-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-390">총 채팅 비율</span><span class="sxs-lookup"><span data-stu-id="426bf-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="426bf-391">24/초</span><span class="sxs-lookup"><span data-stu-id="426bf-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-392">소규모 대화방의 채팅 비율</span><span class="sxs-lookup"><span data-stu-id="426bf-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-393">22.22/second</span><span class="sxs-lookup"><span data-stu-id="426bf-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-394">중규모 대화방의 채팅 비율</span><span class="sxs-lookup"><span data-stu-id="426bf-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-395">1.67/second</span><span class="sxs-lookup"><span data-stu-id="426bf-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-396">대규모 대화방의 채팅 비율</span><span class="sxs-lookup"><span data-stu-id="426bf-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="426bf-397">~ 0.15/second</span><span class="sxs-lookup"><span data-stu-id="426bf-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-398">초대에 대해 구성된 대화방의 비율</span><span class="sxs-lookup"><span data-stu-id="426bf-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="426bf-399">50%</span><span class="sxs-lookup"><span data-stu-id="426bf-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-400">직접 구성원의 비율</span><span class="sxs-lookup"><span data-stu-id="426bf-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="426bf-401">50%</span><span class="sxs-lookup"><span data-stu-id="426bf-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-402">그룹 구성원의 비율</span><span class="sxs-lookup"><span data-stu-id="426bf-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="426bf-403">50%</span><span class="sxs-lookup"><span data-stu-id="426bf-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-404">Active Directory 도메인 서비스의 평균 상위 항목 수</span><span class="sxs-lookup"><span data-stu-id="426bf-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="426bf-405">100 - 200</span><span class="sxs-lookup"><span data-stu-id="426bf-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-406">사용자당 등록된 대화 상대 수</span><span class="sxs-lookup"><span data-stu-id="426bf-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="426bf-407">80</span><span class="sxs-lookup"><span data-stu-id="426bf-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-408">사용자 당 평균 끝점 수</span><span class="sxs-lookup"><span data-stu-id="426bf-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="426bf-409">1.5</span><span class="sxs-lookup"><span data-stu-id="426bf-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-410">끝점 당 표시 되는 평균 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="426bf-411">1.5</span><span class="sxs-lookup"><span data-stu-id="426bf-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-412">사용자 당 표시 되는 평균 대화방 수</span><span class="sxs-lookup"><span data-stu-id="426bf-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="426bf-413">2.25 (1 개의 채팅방에 50%를, 2 채팅방의 경우 50%); 모니터 마다 하나씩 최대 6 개의 채팅방이 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="426bf-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-414">간격당 폴링되는 참가자 수</span><span class="sxs-lookup"><span data-stu-id="426bf-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="426bf-415">가시 대화방 당 25 개</span><span class="sxs-lookup"><span data-stu-id="426bf-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-416">폴링 간격</span><span class="sxs-lookup"><span data-stu-id="426bf-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="426bf-417">5분</span><span class="sxs-lookup"><span data-stu-id="426bf-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-418">초당당 폴링되는 참가자 수</span><span class="sxs-lookup"><span data-stu-id="426bf-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="426bf-419">15000</span><span class="sxs-lookup"><span data-stu-id="426bf-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="426bf-420">사용자별 시간당 현재 상태 변경 수</span><span class="sxs-lookup"><span data-stu-id="426bf-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="426bf-421">6 </span><span class="sxs-lookup"><span data-stu-id="426bf-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="426bf-422">초당 현재 상태 변경 수</span><span class="sxs-lookup"><span data-stu-id="426bf-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="426bf-423">133.33</span><span class="sxs-lookup"><span data-stu-id="426bf-423">133.33</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

