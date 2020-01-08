---
title: 'Lync Server 2013: 영구 채팅 서버의 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af60947a1132d26d5e8ba015d54cdbea80b8b54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="f2068-102">Lync Server 2013의 영구 채팅 서버 용량 계획</span><span class="sxs-lookup"><span data-stu-id="f2068-102">Capacity planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2068-103">_**마지막으로 수정한 주제:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f2068-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f2068-104">영구 채팅 서버는 향후 검색 및 검색을 위해 유지할 수 있는 다중 사용자 실시간 채팅을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-104">Persistent Chat Server can perform multi-user real-time chat that can persist for future retrieval and search.</span></span> <span data-ttu-id="f2068-105">사용자의 사서함에 저장 된 IM (그룹 인스턴트 메시징)과 달리, 대화 내용이 구성 되어 있지 않으면 영구 채팅 서버 세션이 더 이상 열려 있는 상태로 유지 되 고, 콘텐츠는 서버에 저장 되며, 메시지, 파일, Url, 기타 데이터를 포함 합니다. 진행 중인 대화.</span><span class="sxs-lookup"><span data-stu-id="f2068-105">Unlike group instant messaging (IM) that is saved in a user’s mailbox if conversation history is configured, a Persistent Chat Server session stays open longer, and the content is saved on a server, along with the messages, files, URLs, and other data that are part of an ongoing conversation.</span></span>

<span data-ttu-id="f2068-106">용량 계획은 영구 채팅 서버 배포를 준비 하는 데 중요 한 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-106">Capacity planning is an important part of preparing to deploy Persistent Chat Server.</span></span> <span data-ttu-id="f2068-107">이 항목에서는 배포에 가장 적합 한 구성을 결정 하는 데 사용할 수 있는 지원 되는 영구 채팅 서버 토폴로지와 용량 계획 표에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-107">This topic provides details about supported Persistent Chat Server topologies and capacity planning tables that you can use to determine the best configuration for your deployment.</span></span> <span data-ttu-id="f2068-108">또한 사용량이 가장 많은 시간에 더 많은 용량을 필요로 하는 영구 채팅 서버 배포를 최상으로 관리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-108">It also describes how to best manage Persistent Chat Server deployments that require greater capacity at peak times.</span></span>

<span data-ttu-id="f2068-109">영구 채팅 서버를 다운로드 하려면 "Microsoft Lync Server 13 영구 채팅 서버"를 참조 [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)하세요.</span><span class="sxs-lookup"><span data-stu-id="f2068-109">To download Persistent Chat Server, see "Microsoft Lync Server 13 Persistent Chat Server" at [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539).</span></span>

<span data-ttu-id="f2068-110">영구 채팅 서버를 설치 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 영구 채팅 서버 설치](lync-server-2013-installing-persistent-chat-server.md) 및 [lync Server 2013의 영구 채팅 서버 구성](lync-server-2013-configuring-persistent-chat-server.md) 에서 배포 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f2068-110">For details about installing Persistent Chat Server, see [Installing Persistent Chat Server in Lync Server 2013](lync-server-2013-installing-persistent-chat-server.md) and [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="f2068-111">Lync Server 계획 도구와 같은 지원 도구는 용량 계획에 대 한 추가 지원을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-111">Support tools, such as Lync Server Planning Tool, can further assist you with capacity planning.</span></span> <span data-ttu-id="f2068-112">계획 도구에 대 한 자세한 내용은 계획 문서에서 [Lync Server 2013에 대 한 계획 프로세스 시작](lync-server-2013-beginning-the-planning-process.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f2068-112">For details about the Planning Tool, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<div>

## <a name="persistent-chat-server-supported-topologies"></a><span data-ttu-id="f2068-113">영구 채팅 서버 지원 토폴로지</span><span class="sxs-lookup"><span data-stu-id="f2068-113">Persistent Chat Server Supported Topologies</span></span>

<span data-ttu-id="f2068-114">단일 서버 또는 다중 서버 풀에서 영구 채팅 서버를 배포 하 고 단일 풀 또는 다중 풀 토폴로지에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-114">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span>

<span data-ttu-id="f2068-115">이제 새 Lync Server 2013 배포에 대 한 Standard Edition server의 영구 채팅 서버도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-115">We now also support Persistent Chat Server on Standard Edition server for new Lync Server 2013 deployments.</span></span> <span data-ttu-id="f2068-116">그러나 성능 및 확장성에 영향을 줄 수 있으며,이 새로운 배포에 대 한 고가용성 옵션이 없기 때문에 개념 입증, 평가 등의 목적으로이를 주로 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-116">However, performance and scale will be affected, and because there is no high availability option for this new deployment, we expect you to use this primarily for the purposes of proof of concept, evaluation, and so on.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2068-117">두 토폴로지에 대 한 자세한 내용은이 설명서의 <A href="lync-server-2013-planning-for-persistent-chat-server.md">Lync server 2013에서 영구</A> 채팅 서버 계획 및 배포 설명서의 <A href="lync-server-2013-deploying-persistent-chat-server.md">lync Server 2013에서 영구 채팅 서버</A> 설정 및 배포를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f2068-117">For additional details about both topologies, see <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync Server 2013</A> in this documentation set and <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="f2068-118">단일 서버 토폴로지</span><span class="sxs-lookup"><span data-stu-id="f2068-118">Single-Server Topology</span></span>

<span data-ttu-id="f2068-119">영구 채팅 서버용 최소 구성과 가장 간단한 배포는 단일 영구 채팅 서버 프런트 엔드 서버 토폴로지입니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-119">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="f2068-120">이 배포에는 영구 채팅 서버를 실행 하는 단일 서버 (선택적으로 준수 서비스를 실행 하는 경우), SQL Server 데이터베이스를 모두 호스트 하는 서버, 준수 해야 하는 SQL Server 데이터베이스 등이 필요 합니다. 준수 데이터</span><span class="sxs-lookup"><span data-stu-id="f2068-120">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f2068-121">토폴로지 작성기에서 단일 서버 배포로 시작 되는 영구 채팅 서버 풀에는 다른 서버를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-121">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="f2068-122">단일 서버를 사용 하 고 있는 경우에도 다중 서버 풀 토폴로지를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-122">We recommend using the multiple-server pool topology, even if you’re using a single server.</span></span> <span data-ttu-id="f2068-123">따라서 필요한 경우 나중에 서버를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-123">This is so that you’ll be able to add more servers later, if it's necessary.</span></span> 


</div>

<span data-ttu-id="f2068-124">다음 그림에는 단일 영구 채팅 서버 프런트 엔드 서버에 대 한 모든 필수 및 선택적 구성 요소 (준수)가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-124">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="f2068-125">**단일 영구 채팅 서버**</span><span class="sxs-lookup"><span data-stu-id="f2068-125">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="f2068-126">규정 준수 서비스를 사용 ![하는 단일]서버 토폴로지,(images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "준수 서비스를 사용 하는 단일 서버 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="f2068-126">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="f2068-127">다중 서버 토폴로지</span><span class="sxs-lookup"><span data-stu-id="f2068-127">Multiple-Server Topology</span></span>

<span data-ttu-id="f2068-128">더 나은 용량과 안정성을 제공 하기 위해 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)에서 설명한 대로 다중 서버 토폴로지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-128">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="f2068-129">다중 서버 토폴로지에는 영구 채팅 서버를 실행 하는 4 대의 활성 컴퓨터가 포함 될 수 있습니다 (고가용성 및 재해 복구 구성은 최대 8 개까지 허용 되지만, 나머지 4 개는 활성 상태로 유지 될 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="f2068-129">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="f2068-130">각 서버는 최대 2만 명의 동시 사용자를 지원할 수 있으며, 서버 4 대에서 영구 채팅 서버 풀에 연결 된 총 8만 동시 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-130">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="f2068-131">다중 서버 토폴로지는 여러 서버에서 영구 채팅 서버를 호스트 하는 것을 제외 하 고 단일 서버 토폴로지와 동일 하며 더 높은 배율을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-131">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="f2068-132">영구 채팅 서버를 실행 하는 여러 컴퓨터는 Lync Server 및 준수 서비스와 동일한 Active Directory 도메인 서비스 도메인에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-132">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="f2068-133">다음 그림은 영구 채팅 서버, 선택적 준수 서비스, 별도 규정 준수 데이터베이스를 실행 하는 여러 컴퓨터가 있는 다중 서버 토폴로지의 모든 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-133">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="f2068-134">**여러 영구 채팅 서버**</span><span class="sxs-lookup"><span data-stu-id="f2068-134">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="f2068-135">![다중 서버 토폴로지](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "다중 서버 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="f2068-135">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="f2068-136">8만 사용자가 영구 채팅에 동시에 로그인 하 여 사용할 수 있는 4 서버 영구 채팅 서버 배포의 경우 서버 당 2만 사용자가 부하를 균등 하 게 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-136">In a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="f2068-137">한 서버를 사용할 수 없게 되 면 해당 서버에 연결 된 사용자가 영구 채팅 서버에 대 한 액세스 권한을 잃게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-137">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="f2068-138">연결이 끊긴 사용자는 사용할 수 없는 서버가 복원 될 때까지 자동으로 나머지 서버로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-138">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> <span data-ttu-id="f2068-139">네트워크의 영구 채팅 소통량의 양에 따라,이 전송은 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-139">Depending on the amount of Persistent Chat traffic on the network, this transfer can take a few minutes or longer.</span></span> <span data-ttu-id="f2068-140">나머지 서버는 각각 3만 사용자를 호스트할 수 있기 때문에 사용 불가능 한 서버를 가능한 한 빨리 복원 하 여 성능 문제를 방지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-140">Because each of the remaining servers might be hosting as many as 30,000 users, we recommend that you restore the unavailable server as quickly as possible to avoid performance issues.</span></span> <span data-ttu-id="f2068-141">그렇지 않으면 토폴로지 작성기 또는 Windows PowerShell cmdlet ( **CsPersistentChatActiveServer)** 을 사용 하 여 다른 영구 채팅 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-141">Otherwise, you can make another Persistent Chat Server available by using the Topology Builder or the Windows PowerShell cmdlet, **set-CsPersistentChatActiveServer**.</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a><span data-ttu-id="f2068-142">영구 채팅 서버 용량 계획</span><span class="sxs-lookup"><span data-stu-id="f2068-142">Persistent Chat Server Capacity Planning</span></span>

<span data-ttu-id="f2068-143">다음 표는 영구 채팅 서버의 용량을 계획 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-143">The following tables can help you with capacity planning for Persistent Chat Server.</span></span> <span data-ttu-id="f2068-144">다양 한 영구 채팅 서버 설정을 변경 하는 방법이 용량 기능에 미치는 영향을 모델링 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-144">They model how changing various Persistent Chat Server settings affect capacity capabilities.</span></span>

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a><span data-ttu-id="f2068-145">영구 채팅 서버의 최대 용량 계획</span><span class="sxs-lookup"><span data-stu-id="f2068-145">Planning Your Maximum Capacity for Persistent Chat Server</span></span>

<span data-ttu-id="f2068-146">다음 예제 테이블을 사용 하 여 지원할 수 있는 사용자 수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-146">Use the following sample table to determine the number of users you will be able to support.</span></span>

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a><span data-ttu-id="f2068-147">영구 채팅 서버 풀 최대 용량 샘플</span><span class="sxs-lookup"><span data-stu-id="f2068-147">Persistent Chat Server pool Maximum Capacity Sample</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2068-148">활성 영구 채팅 서비스 인스턴스</span><span class="sxs-lookup"><span data-stu-id="f2068-148">Active Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="f2068-149"><em>4(tcp/ipv4)</em></span><span class="sxs-lookup"><span data-stu-id="f2068-149"><em>4</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-150">영구 채팅 서비스 인스턴스</span><span class="sxs-lookup"><span data-stu-id="f2068-150">Persistent Chat service instances</span></span></p></td>
<td><p><span data-ttu-id="f2068-151"><em>8 (4는 비활성 이어야 하 고 최대 4 개까지 활성화할 수 있음)</em></span><span class="sxs-lookup"><span data-stu-id="f2068-151"><em>8 (4 must be inactive; only a maximum of 4 can be active)</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-152">활성 사용자가 연결 됨</span><span class="sxs-lookup"><span data-stu-id="f2068-152">Active users connected</span></span></p></td>
<td><p><span data-ttu-id="f2068-153"><em>8만</em></span><span class="sxs-lookup"><span data-stu-id="f2068-153"><em>80,000</em></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-154">프로 비전 된 총 사용자</span><span class="sxs-lookup"><span data-stu-id="f2068-154">Total provisioned users</span></span></p></td>
<td><p><span data-ttu-id="f2068-155">15만</span><span class="sxs-lookup"><span data-stu-id="f2068-155">150,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-156">끝점 수</span><span class="sxs-lookup"><span data-stu-id="f2068-156">Number of endpoints</span></span></p></td>
<td><p><span data-ttu-id="f2068-157">12만</span><span class="sxs-lookup"><span data-stu-id="f2068-157">120,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2068-158">앞의 예제에서 계획은 영구 채팅 서버에서 허용 하는 최대 사용자 수 인 영구 채팅 서비스의 네 가지 서버/인스턴스 (고가용성 및 재해 복구용으로 영구 채팅 서버를 실행 하는 4 개 이상의 수동 서버를 포함할 수 있음) 및 서버당 2만 사용자의 총 8만 활성 사용자를 지원 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-158">In the preceding sample, the plan is to support the maximum number of users that Persistent Chat Server allows: four servers/instances of the Persistent Chat service (can have four more passive servers running Persistent Chat Server for high availability and disaster recovery) and 20,000 users per server, for a total of 80,000 active users.</span></span>

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a><span data-ttu-id="f2068-159">영구 채팅방 액세스를 관리 하기 위한 용량 계획</span><span class="sxs-lookup"><span data-stu-id="f2068-159">Capacity Planning for Managing Persistent Chat Room Access</span></span>

<span data-ttu-id="f2068-160">다음 예제 표는 영구 채팅 서버 풀에서 영구 채팅방 액세스를 관리 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-160">The following sample table can help you plan for managing Persistent Chat room access in a Persistent Chat Server pool.</span></span>

### <a name="managing-chat-room-access-sample"></a><span data-ttu-id="f2068-161">채팅방 액세스 관리 샘플</span><span class="sxs-lookup"><span data-stu-id="f2068-161">Managing Chat Room Access Sample</span></span>

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
<th><span data-ttu-id="f2068-162">작은 채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-162">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="f2068-163">중간 채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-163">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="f2068-164">대형 채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-164">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="f2068-165">Total</span><span class="sxs-lookup"><span data-stu-id="f2068-165">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2068-166">채팅방 크기 (연결 된 사용자 수)</span><span class="sxs-lookup"><span data-stu-id="f2068-166">Size of chat rooms (number of users connected)</span></span></p></td>
<td><p><span data-ttu-id="f2068-167">회의실 당 30 개</span><span class="sxs-lookup"><span data-stu-id="f2068-167">30 per room</span></span></p></td>
<td><p><span data-ttu-id="f2068-168">회의실 당 150</span><span class="sxs-lookup"><span data-stu-id="f2068-168">150 per room</span></span></p></td>
<td><p><span data-ttu-id="f2068-169">회의실 당 16000</span><span class="sxs-lookup"><span data-stu-id="f2068-169">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-170">채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-170">Chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-171">32000</span><span class="sxs-lookup"><span data-stu-id="f2068-171">32,000</span></span></p></td>
<td><p><span data-ttu-id="f2068-172">1067</span><span class="sxs-lookup"><span data-stu-id="f2068-172">1,067</span></span></p></td>
<td><p><span data-ttu-id="f2068-173">1천만</span><span class="sxs-lookup"><span data-stu-id="f2068-173">10</span></span></p></td>
<td><p><span data-ttu-id="f2068-174">33077</span><span class="sxs-lookup"><span data-stu-id="f2068-174">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-175">auditorium 된 채팅방 의%</span><span class="sxs-lookup"><span data-stu-id="f2068-175">% of rooms that are auditorium</span></span></p></td>
<td><p><span data-ttu-id="f2068-176">raid-1</span><span class="sxs-lookup"><span data-stu-id="f2068-176">1%</span></span></p></td>
<td><p><span data-ttu-id="f2068-177">raid-1</span><span class="sxs-lookup"><span data-stu-id="f2068-177">1%</span></span></p></td>
<td><p><span data-ttu-id="f2068-178">50%</span><span class="sxs-lookup"><span data-stu-id="f2068-178">50%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-179">열려 있는 채팅방 의%</span><span class="sxs-lookup"><span data-stu-id="f2068-179">% of rooms that are open</span></span></p></td>
<td><p><span data-ttu-id="f2068-180">3-4</span><span class="sxs-lookup"><span data-stu-id="f2068-180">3%</span></span></p></td>
<td><p><span data-ttu-id="f2068-181">3-4</span><span class="sxs-lookup"><span data-stu-id="f2068-181">3%</span></span></p></td>
<td><p><span data-ttu-id="f2068-182">50%</span><span class="sxs-lookup"><span data-stu-id="f2068-182">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-183">채팅방 열기 (명시적 멤버쉽 없음)</span><span class="sxs-lookup"><span data-stu-id="f2068-183">Open rooms (no explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="f2068-184">960</span><span class="sxs-lookup"><span data-stu-id="f2068-184">960</span></span></p></td>
<td><p><span data-ttu-id="f2068-185">32</span><span class="sxs-lookup"><span data-stu-id="f2068-185">32</span></span></p></td>
<td><p><span data-ttu-id="f2068-186">5mb</span><span class="sxs-lookup"><span data-stu-id="f2068-186">5</span></span></p></td>
<td><p><span data-ttu-id="f2068-187">997</span><span class="sxs-lookup"><span data-stu-id="f2068-187">997</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-188">열지 않은 방 (명시적 구성원 자격이 있는 일반 회의실)</span><span class="sxs-lookup"><span data-stu-id="f2068-188">Non-open rooms (regular rooms with explicit membership)</span></span></p></td>
<td><p><span data-ttu-id="f2068-189">31040</span><span class="sxs-lookup"><span data-stu-id="f2068-189">31,040</span></span></p></td>
<td><p><span data-ttu-id="f2068-190">1.035</span><span class="sxs-lookup"><span data-stu-id="f2068-190">1.035</span></span></p></td>
<td><p><span data-ttu-id="f2068-191">5mb</span><span class="sxs-lookup"><span data-stu-id="f2068-191">5</span></span></p></td>
<td><p><span data-ttu-id="f2068-192">32080</span><span class="sxs-lookup"><span data-stu-id="f2068-192">32,080</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-193">Auditorium 채팅방 (추가 발표자 항목)</span><span class="sxs-lookup"><span data-stu-id="f2068-193">Auditorium rooms (additional presenters entry)</span></span></p></td>
<td><p><span data-ttu-id="f2068-194">0</span><span class="sxs-lookup"><span data-stu-id="f2068-194">0</span></span></p></td>
<td><p><span data-ttu-id="f2068-195">32</span><span class="sxs-lookup"><span data-stu-id="f2068-195">32</span></span></p></td>
<td><p><span data-ttu-id="f2068-196">5mb</span><span class="sxs-lookup"><span data-stu-id="f2068-196">5</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-197">직접 회원 들이 관리 하는 채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-197">Rooms managed by direct membership</span></span></p></td>
<td><p><span data-ttu-id="f2068-198">50%</span><span class="sxs-lookup"><span data-stu-id="f2068-198">50%</span></span></p></td>
<td><p><span data-ttu-id="f2068-199">1천만</span><span class="sxs-lookup"><span data-stu-id="f2068-199">10%</span></span></p></td>
<td><p><span data-ttu-id="f2068-200">0</span><span class="sxs-lookup"><span data-stu-id="f2068-200">0%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-201">사용자 그룹이 관리 하는 채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-201">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="f2068-202">50%</span><span class="sxs-lookup"><span data-stu-id="f2068-202">50%</span></span></p></td>
<td><p><span data-ttu-id="f2068-203">90%</span><span class="sxs-lookup"><span data-stu-id="f2068-203">90%</span></span></p></td>
<td><p><span data-ttu-id="f2068-204">100%</span><span class="sxs-lookup"><span data-stu-id="f2068-204">100%</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-205">열려 있는 채팅방의 각 채팅방 구성원 목록에 있는 사용자 그룹 (명시적으로 지정 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="f2068-205">User groups in each chat room's membership list for open rooms (not specified explicitly)</span></span></p></td>
<td><p><span data-ttu-id="f2068-206">0</span><span class="sxs-lookup"><span data-stu-id="f2068-206">0</span></span></p></td>
<td><p><span data-ttu-id="f2068-207">0</span><span class="sxs-lookup"><span data-stu-id="f2068-207">0</span></span></p></td>
<td><p><span data-ttu-id="f2068-208">0</span><span class="sxs-lookup"><span data-stu-id="f2068-208">0</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-209">비 열려 있는 채팅방의 각 채팅방 구성원 목록에 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="f2068-209">Users in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-210">30</span><span class="sxs-lookup"><span data-stu-id="f2068-210">30</span></span></p></td>
<td><p><span data-ttu-id="f2068-211">150</span><span class="sxs-lookup"><span data-stu-id="f2068-211">150</span></span></p></td>
<td><p><span data-ttu-id="f2068-212">16000</span><span class="sxs-lookup"><span data-stu-id="f2068-212">16,000</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-213">비 열려 있는 채팅방의 각 채팅방 구성원 목록에 있는 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="f2068-213">User groups in each chat room's membership list for non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-214">3</span><span class="sxs-lookup"><span data-stu-id="f2068-214">3</span></span></p></td>
<td><p><span data-ttu-id="f2068-215">5mb</span><span class="sxs-lookup"><span data-stu-id="f2068-215">5</span></span></p></td>
<td><p><span data-ttu-id="f2068-216">1천만</span><span class="sxs-lookup"><span data-stu-id="f2068-216">10</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-217">각 채팅방의 관리자 목록에 있는 사용자 및 사용자 그룹 (개방 또는 비 열려 있는 채팅방)</span><span class="sxs-lookup"><span data-stu-id="f2068-217">Users and user groups in each chat room's manager list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="f2068-218">26</span><span class="sxs-lookup"><span data-stu-id="f2068-218">6</span></span></p></td>
<td><p><span data-ttu-id="f2068-219">26</span><span class="sxs-lookup"><span data-stu-id="f2068-219">6</span></span></p></td>
<td><p><span data-ttu-id="f2068-220">26</span><span class="sxs-lookup"><span data-stu-id="f2068-220">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-221">각 auditorium 대화방의 발표자 목록에 있는 사용자 및 사용자 그룹 (열기 및 열지 않은 채팅방)</span><span class="sxs-lookup"><span data-stu-id="f2068-221">Users and user groups in each auditorium chat room's presenters list (for open and non-open rooms)</span></span></p></td>
<td><p><span data-ttu-id="f2068-222">26</span><span class="sxs-lookup"><span data-stu-id="f2068-222">6</span></span></p></td>
<td><p><span data-ttu-id="f2068-223">26</span><span class="sxs-lookup"><span data-stu-id="f2068-223">6</span></span></p></td>
<td><p><span data-ttu-id="f2068-224">26</span><span class="sxs-lookup"><span data-stu-id="f2068-224">6</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-225">열려 있지 않은 모든 채팅방에 걸친 사용자 기반 구성원 자격 엔터티</span><span class="sxs-lookup"><span data-stu-id="f2068-225">User-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-226">465600</span><span class="sxs-lookup"><span data-stu-id="f2068-226">465,600</span></span></p></td>
<td><p><span data-ttu-id="f2068-227">15520</span><span class="sxs-lookup"><span data-stu-id="f2068-227">15,520</span></span></p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-228">열려 있지 않은 모든 채팅방에서 사용자 그룹 기반 구성원 자격 엔터티</span><span class="sxs-lookup"><span data-stu-id="f2068-228">User-group-based membership entities across all non-open rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-229">46560</span><span class="sxs-lookup"><span data-stu-id="f2068-229">46,560</span></span></p></td>
<td><p><span data-ttu-id="f2068-230">4656</span><span class="sxs-lookup"><span data-stu-id="f2068-230">4656</span></span></p></td>
<td><p><span data-ttu-id="f2068-231">50</span><span class="sxs-lookup"><span data-stu-id="f2068-231">50</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-232">모든 auditorium 채팅방에 걸친 사용자 및 사용자 그룹 기반 엔터티</span><span class="sxs-lookup"><span data-stu-id="f2068-232">Users and user groups based entities across all auditorium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-233">0</span><span class="sxs-lookup"><span data-stu-id="f2068-233">0</span></span></p></td>
<td><p><span data-ttu-id="f2068-234">192</span><span class="sxs-lookup"><span data-stu-id="f2068-234">192</span></span></p></td>
<td><p><span data-ttu-id="f2068-235">50</span><span class="sxs-lookup"><span data-stu-id="f2068-235">50</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-236">모든 채팅방 관리자 목록에서 사용자 및 사용자 그룹 기반 관리자 엔터티</span><span class="sxs-lookup"><span data-stu-id="f2068-236">Users and user groups based manager entities across all chat rooms manager lists</span></span></p></td>
<td><p><span data-ttu-id="f2068-237">192000</span><span class="sxs-lookup"><span data-stu-id="f2068-237">192,000</span></span></p></td>
<td><p><span data-ttu-id="f2068-238">6400</span><span class="sxs-lookup"><span data-stu-id="f2068-238">6,400</span></span></p></td>
<td><p><span data-ttu-id="f2068-239">60</span><span class="sxs-lookup"><span data-stu-id="f2068-239">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-240">채팅방 별 활성 사용자</span><span class="sxs-lookup"><span data-stu-id="f2068-240">Active users per chat room</span></span></p></td>
<td><p><span data-ttu-id="f2068-241"><em>30</em></span><span class="sxs-lookup"><span data-stu-id="f2068-241"><em>30</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-242"><em>150</em></span><span class="sxs-lookup"><span data-stu-id="f2068-242"><em>150</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-243"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="f2068-243"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-244">사용자 당 채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-244">Chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="f2068-245"><em>까지</em></span><span class="sxs-lookup"><span data-stu-id="f2068-245"><em>12</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-246"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="f2068-246"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-247"><em>2</em></span><span class="sxs-lookup"><span data-stu-id="f2068-247"><em>2</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-248"><em>16</em></span><span class="sxs-lookup"><span data-stu-id="f2068-248"><em>16</em></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-249">각 채팅방의 구성원 목록에 있는 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="f2068-249">User groups in each chat room’s membership list</span></span></p></td>
<td><p><span data-ttu-id="f2068-250"><em>1천만</em></span><span class="sxs-lookup"><span data-stu-id="f2068-250"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-251"><em>1천만</em></span><span class="sxs-lookup"><span data-stu-id="f2068-251"><em>10</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-252"><em>~</em></span><span class="sxs-lookup"><span data-stu-id="f2068-252"><em>15</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-253">사용자 그룹이 관리 하는 채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-253">Rooms managed by user groups</span></span></p></td>
<td><p><span data-ttu-id="f2068-254"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="f2068-254"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-255"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="f2068-255"><em>50%</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-256"><em>50%</em></span><span class="sxs-lookup"><span data-stu-id="f2068-256"><em>50%</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-257">모든 채팅방에 걸친 사용자 그룹 기반 구성원 자격 엔터티</span><span class="sxs-lookup"><span data-stu-id="f2068-257">User-group-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-258">155200</span><span class="sxs-lookup"><span data-stu-id="f2068-258">155,200</span></span></p></td>
<td><p><span data-ttu-id="f2068-259">5173</span><span class="sxs-lookup"><span data-stu-id="f2068-259">5173</span></span></p></td>
<td><p><span data-ttu-id="f2068-260">68</span><span class="sxs-lookup"><span data-stu-id="f2068-260">68</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-261">모든 채팅방에 걸친 사용자 기반 구성원 자격 엔터티</span><span class="sxs-lookup"><span data-stu-id="f2068-261">User-based membership entities across all chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-262">465600</span><span class="sxs-lookup"><span data-stu-id="f2068-262">465,600</span></span></p></td>
<td><p><span data-ttu-id="f2068-263">77600</span><span class="sxs-lookup"><span data-stu-id="f2068-263">77,600</span></span></p></td>
<td><p><span data-ttu-id="f2068-264">72000</span><span class="sxs-lookup"><span data-stu-id="f2068-264">72,000</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-265">각 채팅방의 관리자, 발표자 및 범위 목록에 있는 사용자 및 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="f2068-265">Users and user groups in each chat room's manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="f2068-266">26</span><span class="sxs-lookup"><span data-stu-id="f2068-266">6</span></span></p></td>
<td><p><span data-ttu-id="f2068-267">26</span><span class="sxs-lookup"><span data-stu-id="f2068-267">6</span></span></p></td>
<td><p><span data-ttu-id="f2068-268">26</span><span class="sxs-lookup"><span data-stu-id="f2068-268">6</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-269">모든 채팅방의 관리자, 발표자 및 범위 목록에 걸친 사용자 및 사용자 그룹</span><span class="sxs-lookup"><span data-stu-id="f2068-269">Users and user groups across all chat rooms' manager, presenter, and scope lists</span></span></p></td>
<td><p><span data-ttu-id="f2068-270">192000</span><span class="sxs-lookup"><span data-stu-id="f2068-270">192,000</span></span></p></td>
<td><p><span data-ttu-id="f2068-271">6400</span><span class="sxs-lookup"><span data-stu-id="f2068-271">6400</span></span></p></td>
<td><p><span data-ttu-id="f2068-272">60</span><span class="sxs-lookup"><span data-stu-id="f2068-272">60</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-273">액세스 제어 항목</span><span class="sxs-lookup"><span data-stu-id="f2068-273">Access control entries</span></span></p></td>
<td><p><span data-ttu-id="f2068-274">704160</span><span class="sxs-lookup"><span data-stu-id="f2068-274">704,160</span></span></p></td>
<td><p><span data-ttu-id="f2068-275">26768</span><span class="sxs-lookup"><span data-stu-id="f2068-275">26,768</span></span></p></td>
<td><p><span data-ttu-id="f2068-276">160</span><span class="sxs-lookup"><span data-stu-id="f2068-276">160</span></span></p></td>
<td><p><span data-ttu-id="f2068-277">731088</span><span class="sxs-lookup"><span data-stu-id="f2068-277">731,088</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-278">최대 액세스 제어 항목</span><span class="sxs-lookup"><span data-stu-id="f2068-278">Maximum access control entries</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="f2068-279">200만</span><span class="sxs-lookup"><span data-stu-id="f2068-279">2,000,000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f2068-280">앞의 예제에서 권장 지침에 따라 영구 채팅 서버를 배포 하는 경우 준수가 설정 된 4 개 서버 풀에서 최대 8만 명의 활성 사용자를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-280">In the preceding sample, when you deploy the Persistent Chat Servers according to the recommended guidelines, they can handle up to 80,000 active users across a four-server pool with compliance enabled.</span></span>

<span data-ttu-id="f2068-281">이 샘플에서는 작은 (주어진 시간에 30 명의 활성 사용자), 중간 (150 활성 사용자) 및 대규모 (16000 활성 사용자) 채팅방을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-281">This sample shows chat rooms categorized as small (30 active users at any given time), medium (150 active users), and large (16,000 active users).</span></span> <span data-ttu-id="f2068-282">특정 크기의 채팅방 수는 총 수를 기준으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-282">The number of chat rooms of a certain size is computed based on the total number of:</span></span>

  - <span data-ttu-id="f2068-283">시스템의 활성 사용자</span><span class="sxs-lookup"><span data-stu-id="f2068-283">Active users in the system</span></span>

  - <span data-ttu-id="f2068-284">지정 된 크기의 채팅방에 있는 활성 사용자</span><span class="sxs-lookup"><span data-stu-id="f2068-284">Active users in chat rooms of the given size</span></span>

  - <span data-ttu-id="f2068-285">단일 사용자가 참가 하는 지정 된 크기의 채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-285">Chat rooms of the given size that a single user joins</span></span>

<span data-ttu-id="f2068-286">각 채팅방에 대해 앞의 용량 계획 표는 채팅방에 직접 할당 된 항목을 포함 하 여 채팅방과 연결 된 액세스 제어 항목의 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-286">For each chat room, the preceding capacity planning table specifies the number of access control entries that are associated with the chat room, including entries that are assigned directly to the chat room.</span></span> <span data-ttu-id="f2068-287">Acl (액세스 제어 목록)을 사용 하 여 각 채팅방에 대 한 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-287">You can control access to individual chat rooms by using access control lists (ACLs).</span></span> <span data-ttu-id="f2068-288">범주 수준에서 액세스를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-288">You can also control access at the category level.</span></span> <span data-ttu-id="f2068-289">ACL에서 개별 액세스 제어 항목은 사용자 그룹 (예: 보안 그룹, 메일 목록 또는 단일 사용자) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-289">In an ACL, an individual access control entry can be either a user group—for example, a security group, a distribution list, or a single user.</span></span> <span data-ttu-id="f2068-290">채팅방 관리자, 발표자 및 구성원에 대 한 액세스 제어 항목을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-290">You can define access control entries for chat room managers, presenters, and members.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f2068-291">채팅방을 관리 하기 위한 전략 계획에서는 허용 되는 총 액세스 제어 항목 수가 200만이 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f2068-291">In planning your strategy for managing chat rooms, keep in mind that the total number of allowed access control entries is 2 million.</span></span> <span data-ttu-id="f2068-292">계산 된 액세스 제어 항목이 200만를 초과 하는 경우 서버 성능이 크게 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-292">If the calculated access control entries exceed 2 million, server performance could degrade significantly.</span></span> <span data-ttu-id="f2068-293">가능 하면이 문제를 방지 하려면 액세스 제어 항목이 개별 사용자 대신 사용자 그룹 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-293">To avoid this issue, whenever possible, be sure that your access control entries are user groups instead of individual users.</span></span>



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a><span data-ttu-id="f2068-294">초대에의 한 채팅방 액세스를 관리 하기 위한 용량 계획</span><span class="sxs-lookup"><span data-stu-id="f2068-294">Capacity Planning for Managing Chat Room Access by Invitation</span></span>

<span data-ttu-id="f2068-295">다음 용량 계획 표를 사용 하 여 초대를 보내도록 구성 된 영구 채팅 서버에서 영구 채팅 데이터베이스를 만들고 저장 하는 초대 수를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-295">You can use the following capacity planning table to understand the number of invitations that Persistent Chat Server creates and stores in the Persistent Chat database when it is configured to send invitations.</span></span> <span data-ttu-id="f2068-296">Lync Server 제어판의 **채팅방 범주 설정** 페이지를 사용 하거나 Windows PowerShell Cmdlet 인 **csPersistentChatCategory**를 사용 하 여 범주에 대 한 초대를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-296">You manage invitations on the Category by using the **Chat Room Category settings** page in the Lync Server Control Panel, or by using the Windows PowerShell cmdlet, **set-csPersistentChatCategory**.</span></span> <span data-ttu-id="f2068-297">Lync 클라이언트에서 시작 된 채팅방 **관리** 페이지를 사용 하거나 Windows PowerShell Cmdlet 인 **csPersistentChatRoom**를 사용 하 여 채팅방에서 초대를 관리할 수 있습니다 (범주에서 허용 하는 내용에 해당).</span><span class="sxs-lookup"><span data-stu-id="f2068-297">You can manage invitations on a chat room (in line with what the category allows) by using the **Room Management** page launched from the Lync client, or by using a Windows PowerShell cmdlet, **set-csPersistentChatRoom**.</span></span>

<span data-ttu-id="f2068-298">다음 표의 예제 데이터는 모든 채팅방의 50%에 대 한 **채팅방 설정** 페이지에서 **초대** 옵션을 **Yes**로 설정 하는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-298">The sample data in the following table assumes that, on the **Chat room settings** page for 50 percent of all chat rooms, the **Invitations** option is set to **Yes**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f2068-299">서버에서 생성 된 초대 수에 대해 계산 된 값이 100만를 초과 하는 경우 서버 성능이 크게 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-299">If the calculated value for the number of invitations that is generated by the server exceeds 1 million, server performance could degrade significantly.</span></span> <span data-ttu-id="f2068-300">이 문제를 방지 하려면 초대를 보내도록 구성 된 채팅방 수를 최소화 하거나 초대를 보내도록 구성 된 채팅방에 참가할 수 있는 사용자 수를 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-300">To avoid this issue, be sure that you minimize the number of chat rooms that are configured to send invitations or restrict the number of users who can join chat rooms that have been configured to send invitations.</span></span>



</div>

### <a name="chat-room-access-by-invitation-sample"></a><span data-ttu-id="f2068-301">초대에의 한 채팅방 액세스 샘플</span><span class="sxs-lookup"><span data-stu-id="f2068-301">Chat Room Access by Invitation Sample</span></span>

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
<th><span data-ttu-id="f2068-302">작은 채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-302">Small Chat Rooms</span></span></th>
<th><span data-ttu-id="f2068-303">중간 채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-303">Medium Chat Rooms</span></span></th>
<th><span data-ttu-id="f2068-304">대형 채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-304">Large Chat Rooms</span></span></th>
<th><span data-ttu-id="f2068-305">Total</span><span class="sxs-lookup"><span data-stu-id="f2068-305">Total</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2068-306">채팅방에 액세스할 수 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="f2068-306">Users who can access chat room</span></span></p></td>
<td><p><span data-ttu-id="f2068-307">회의실 당 30 개</span><span class="sxs-lookup"><span data-stu-id="f2068-307">30 per room</span></span></p></td>
<td><p><span data-ttu-id="f2068-308">회의실 당 150</span><span class="sxs-lookup"><span data-stu-id="f2068-308">150 per room</span></span></p></td>
<td><p><span data-ttu-id="f2068-309">회의실 당 16000</span><span class="sxs-lookup"><span data-stu-id="f2068-309">16,000 per room</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-310">초대가 있는 채팅방의 백분율</span><span class="sxs-lookup"><span data-stu-id="f2068-310">Percentage of rooms that have invitations</span></span></p></td>
<td><p><span data-ttu-id="f2068-311">50%</span><span class="sxs-lookup"><span data-stu-id="f2068-311">50%</span></span></p></td>
<td><p><span data-ttu-id="f2068-312">50%</span><span class="sxs-lookup"><span data-stu-id="f2068-312">50%</span></span></p></td>
<td><p><span data-ttu-id="f2068-313">50%</span><span class="sxs-lookup"><span data-stu-id="f2068-313">50%</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-314">초대를 보낼 수 있도록 구성 된 채팅방</span><span class="sxs-lookup"><span data-stu-id="f2068-314">Chat rooms configured to send invitations</span></span></p></td>
<td><p><span data-ttu-id="f2068-315"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="f2068-315"><em>16,000</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-316"><em>533</em></span><span class="sxs-lookup"><span data-stu-id="f2068-316"><em>533</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-317"><em>5mb</em></span><span class="sxs-lookup"><span data-stu-id="f2068-317"><em>5</em></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-318">채팅방에 액세스할 수 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="f2068-318">Users who can access the chat room</span></span></p></td>
<td><p><span data-ttu-id="f2068-319"><em>60</em></span><span class="sxs-lookup"><span data-stu-id="f2068-319"><em>60</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-320"><em>225</em></span><span class="sxs-lookup"><span data-stu-id="f2068-320"><em>225</em></span></span></p></td>
<td><p><span data-ttu-id="f2068-321"><em>16000</em></span><span class="sxs-lookup"><span data-stu-id="f2068-321"><em>16,000</em></span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-322">영구 채팅 서버에서 생성 된 초대</span><span class="sxs-lookup"><span data-stu-id="f2068-322">Invitations generated by Persistent Chat Server</span></span></p></td>
<td><p><span data-ttu-id="f2068-323">96만</span><span class="sxs-lookup"><span data-stu-id="f2068-323">960,000</span></span></p></td>
<td><p><span data-ttu-id="f2068-324">12만</span><span class="sxs-lookup"><span data-stu-id="f2068-324">120,000</span></span></p></td>
<td><p><span data-ttu-id="f2068-325">8만</span><span class="sxs-lookup"><span data-stu-id="f2068-325">80,000</span></span></p></td>
<td><p><span data-ttu-id="f2068-326">116만</span><span class="sxs-lookup"><span data-stu-id="f2068-326">1,160,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-327">허용 되는 최대 초대 수</span><span class="sxs-lookup"><span data-stu-id="f2068-327">Maximum allowable number of invitations</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td><p><span data-ttu-id="f2068-328">200만</span><span class="sxs-lookup"><span data-stu-id="f2068-328">2,000,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-329">모델 1-일일 저장소당 예상 메시지 수로 시작</span><span class="sxs-lookup"><span data-stu-id="f2068-329">Model 1 - Start with expected number of messages per room per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-330">회의실 당 채팅 속도 (일별)</span><span class="sxs-lookup"><span data-stu-id="f2068-330">Chat Rate Per Room (per day)</span></span></p></td>
<td><p><span data-ttu-id="f2068-331">50</span><span class="sxs-lookup"><span data-stu-id="f2068-331">50</span></span></p></td>
<td><p><span data-ttu-id="f2068-332">500</span><span class="sxs-lookup"><span data-stu-id="f2068-332">500</span></span></p></td>
<td><p><span data-ttu-id="f2068-333">100</span><span class="sxs-lookup"><span data-stu-id="f2068-333">100</span></span></p></td>
<td><p><span data-ttu-id="f2068-334">650</span><span class="sxs-lookup"><span data-stu-id="f2068-334">650</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-335">모든 채팅방의 채팅 속도 (초당)</span><span class="sxs-lookup"><span data-stu-id="f2068-335">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-336">55.56</span><span class="sxs-lookup"><span data-stu-id="f2068-336">55.56</span></span></p></td>
<td><p><span data-ttu-id="f2068-337">18.52</span><span class="sxs-lookup"><span data-stu-id="f2068-337">18.52</span></span></p></td>
<td><p><span data-ttu-id="f2068-338">0.03</span><span class="sxs-lookup"><span data-stu-id="f2068-338">0.03</span></span></p></td>
<td><p><span data-ttu-id="f2068-339">74</span><span class="sxs-lookup"><span data-stu-id="f2068-339">74</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-340">모델 2-하루에 한 사용자에 게 게시 된 메시지 수에 따라 시작</span><span class="sxs-lookup"><span data-stu-id="f2068-340">Model 2 - Start with number of messages posted per user per day</span></span></p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-341">일일 사용자 당 채팅 요금</span><span class="sxs-lookup"><span data-stu-id="f2068-341">Chat rate per user per day</span></span></p></td>
<td><p><span data-ttu-id="f2068-342">~</span><span class="sxs-lookup"><span data-stu-id="f2068-342">15</span></span></p></td>
<td><p><span data-ttu-id="f2068-343">5mb</span><span class="sxs-lookup"><span data-stu-id="f2068-343">5</span></span></p></td>
<td><p><span data-ttu-id="f2068-344">0.1</span><span class="sxs-lookup"><span data-stu-id="f2068-344">0.1</span></span></p></td>
<td><p><span data-ttu-id="f2068-345">명</span><span class="sxs-lookup"><span data-stu-id="f2068-345">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-346">회의실 당 채팅 속도 (일별)</span><span class="sxs-lookup"><span data-stu-id="f2068-346">Chat rate per room (per day)</span></span></p></td>
<td><p><span data-ttu-id="f2068-347">38</span><span class="sxs-lookup"><span data-stu-id="f2068-347">38</span></span></p></td>
<td><p><span data-ttu-id="f2068-348">375</span><span class="sxs-lookup"><span data-stu-id="f2068-348">375</span></span></p></td>
<td><p><span data-ttu-id="f2068-349">800</span><span class="sxs-lookup"><span data-stu-id="f2068-349">800</span></span></p></td>
<td><p><span data-ttu-id="f2068-350">1213</span><span class="sxs-lookup"><span data-stu-id="f2068-350">1,213</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-351">모든 채팅방의 채팅 속도 (초당)</span><span class="sxs-lookup"><span data-stu-id="f2068-351">Chat rate (per second) across all rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-352">41.67</span><span class="sxs-lookup"><span data-stu-id="f2068-352">41.67</span></span></p></td>
<td><p><span data-ttu-id="f2068-353">13.89</span><span class="sxs-lookup"><span data-stu-id="f2068-353">13.89</span></span></p></td>
<td><p><span data-ttu-id="f2068-354">0.28</span><span class="sxs-lookup"><span data-stu-id="f2068-354">0.28</span></span></p></td>
<td><p><span data-ttu-id="f2068-355">56</span><span class="sxs-lookup"><span data-stu-id="f2068-355">56</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="f2068-356">영구 채팅 서버 성능 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="f2068-356">Persistent Chat Server Performance User Model</span></span>

<span data-ttu-id="f2068-357">다음 표에서는 영구 채팅 서버의 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-357">The following table describes the user model for Persistent Chat Server.</span></span> <span data-ttu-id="f2068-358">용량 계획 요구 사항에 대 한 기반을 제공 하며, 4 대의 서버에서 8만 동시 사용자를 사용 하는 일반적인 조직을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-358">It provides the basis for the capacity planning requirements and represents a typical organization with 80,000 concurrent users on four servers.</span></span>

### <a name="persistent-chat-server-performance-user-model"></a><span data-ttu-id="f2068-359">영구 채팅 서버 성능 사용자 모델</span><span class="sxs-lookup"><span data-stu-id="f2068-359">Persistent Chat Server Performance User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2068-360">연결 된 활성 사용자 수</span><span class="sxs-lookup"><span data-stu-id="f2068-360">Number of active users connected</span></span></p></td>
<td><p><span data-ttu-id="f2068-361">8만</span><span class="sxs-lookup"><span data-stu-id="f2068-361">80,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-362">영구 채팅 서버 서비스 인스턴스 수</span><span class="sxs-lookup"><span data-stu-id="f2068-362">Number of Persistent Chat Server service instances</span></span></p></td>
<td><p><span data-ttu-id="f2068-363">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="f2068-363">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-364">소량 채팅방의 크기</span><span class="sxs-lookup"><span data-stu-id="f2068-364">Size of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-365">사용자 30 명</span><span class="sxs-lookup"><span data-stu-id="f2068-365">30 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-366">중간 채팅방 크기</span><span class="sxs-lookup"><span data-stu-id="f2068-366">Size of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-367">150 사용자</span><span class="sxs-lookup"><span data-stu-id="f2068-367">150 users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-368">큰 채팅방의 크기</span><span class="sxs-lookup"><span data-stu-id="f2068-368">Size of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-369">16000 사용자</span><span class="sxs-lookup"><span data-stu-id="f2068-369">16,000 users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-370">총 채팅방 수</span><span class="sxs-lookup"><span data-stu-id="f2068-370">Total number of chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-371">33077</span><span class="sxs-lookup"><span data-stu-id="f2068-371">33,077</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-372">작은 채팅방의 수</span><span class="sxs-lookup"><span data-stu-id="f2068-372">Number of small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-373">32000</span><span class="sxs-lookup"><span data-stu-id="f2068-373">32,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-374">중간 채팅방의 수</span><span class="sxs-lookup"><span data-stu-id="f2068-374">Number of medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-375">1067</span><span class="sxs-lookup"><span data-stu-id="f2068-375">1,067</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-376">대형 채팅방 수</span><span class="sxs-lookup"><span data-stu-id="f2068-376">Number of large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-377">1천만</span><span class="sxs-lookup"><span data-stu-id="f2068-377">10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-378">사용자 당 총 채팅방 수</span><span class="sxs-lookup"><span data-stu-id="f2068-378">Total number of chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="f2068-379">16</span><span class="sxs-lookup"><span data-stu-id="f2068-379">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-380">사용자 당 작은 채팅방의 수</span><span class="sxs-lookup"><span data-stu-id="f2068-380">Number of small chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="f2068-381">까지</span><span class="sxs-lookup"><span data-stu-id="f2068-381">12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-382">사용자 당 중간 채팅방의 수</span><span class="sxs-lookup"><span data-stu-id="f2068-382">Number of medium chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="f2068-383">2</span><span class="sxs-lookup"><span data-stu-id="f2068-383">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-384">사용자 당 큰 채팅방의 수</span><span class="sxs-lookup"><span data-stu-id="f2068-384">Number of large chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="f2068-385">2</span><span class="sxs-lookup"><span data-stu-id="f2068-385">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-386">사용자 당 참가 한 회의실 수</span><span class="sxs-lookup"><span data-stu-id="f2068-386">Number of rooms joined per user</span></span></p></td>
<td><p><span data-ttu-id="f2068-387">fps</span><span class="sxs-lookup"><span data-stu-id="f2068-387">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-388">최고 참여 율</span><span class="sxs-lookup"><span data-stu-id="f2068-388">Peak join rate</span></span></p></td>
<td><p><span data-ttu-id="f2068-389">10/초</span><span class="sxs-lookup"><span data-stu-id="f2068-389">10/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-390">총 채팅 요금</span><span class="sxs-lookup"><span data-stu-id="f2068-390">Total chat rate</span></span></p></td>
<td><p><span data-ttu-id="f2068-391">24/초</span><span class="sxs-lookup"><span data-stu-id="f2068-391">24/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-392">작은 채팅방에 대 한 채팅 요금</span><span class="sxs-lookup"><span data-stu-id="f2068-392">Chat rate for small chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-393">22.22/초</span><span class="sxs-lookup"><span data-stu-id="f2068-393">22.22/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-394">중간 채팅방에 대 한 채팅 요금</span><span class="sxs-lookup"><span data-stu-id="f2068-394">Chat rate for medium chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-395">1.67/초</span><span class="sxs-lookup"><span data-stu-id="f2068-395">1.67/second</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-396">대형 채팅방에 대 한 채팅 요금</span><span class="sxs-lookup"><span data-stu-id="f2068-396">Chat rate for large chat rooms</span></span></p></td>
<td><p><span data-ttu-id="f2068-397">~ 0.15/second</span><span class="sxs-lookup"><span data-stu-id="f2068-397">~0.15/second</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-398">초대장에 대해 구성 된 채팅방의 백분율</span><span class="sxs-lookup"><span data-stu-id="f2068-398">Percentage of chat rooms configured for invitations</span></span></p></td>
<td><p><span data-ttu-id="f2068-399">50%</span><span class="sxs-lookup"><span data-stu-id="f2068-399">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-400">직접 회원의 백분율</span><span class="sxs-lookup"><span data-stu-id="f2068-400">Percentage of direct memberships</span></span></p></td>
<td><p><span data-ttu-id="f2068-401">50%</span><span class="sxs-lookup"><span data-stu-id="f2068-401">50%</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-402">그룹 구성원의 백분율</span><span class="sxs-lookup"><span data-stu-id="f2068-402">Percentage of group memberships</span></span></p></td>
<td><p><span data-ttu-id="f2068-403">50%</span><span class="sxs-lookup"><span data-stu-id="f2068-403">50%</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-404">Active Directory 도메인 서비스의 평균 조상 가입 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-404">Average number of ancestor affiliations in Active Directory Domain Services</span></span></p></td>
<td><p><span data-ttu-id="f2068-405">100-200</span><span class="sxs-lookup"><span data-stu-id="f2068-405">100 - 200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-406">사용자 당 구독 한 대화 상대 수</span><span class="sxs-lookup"><span data-stu-id="f2068-406">Number of subscribed contacts per user</span></span></p></td>
<td><p><span data-ttu-id="f2068-407">80</span><span class="sxs-lookup"><span data-stu-id="f2068-407">80</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-408">사용자 당 평균 끝점 수</span><span class="sxs-lookup"><span data-stu-id="f2068-408">Average number of endpoints per user</span></span></p></td>
<td><p><span data-ttu-id="f2068-409">1.5</span><span class="sxs-lookup"><span data-stu-id="f2068-409">1.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-410">끝점 당 표시 되는 대화방의 평균 수</span><span class="sxs-lookup"><span data-stu-id="f2068-410">Average number of visible chat rooms per endpoint</span></span></p></td>
<td><p><span data-ttu-id="f2068-411">1.5</span><span class="sxs-lookup"><span data-stu-id="f2068-411">1.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-412">사용자 당 표시 되는 대화방의 평균 수</span><span class="sxs-lookup"><span data-stu-id="f2068-412">Average number of visible chat rooms per user</span></span></p></td>
<td><p><span data-ttu-id="f2068-413">2.25 (1 개 채팅방의 경우 50%, 룸의 경우 50%); 각 모니터에 하나씩 최대 6 개의 채팅방을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2068-413">2.25 (50% for 1 room and 50% for 2 rooms); Up to 6 rooms open, one per monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-414">간격당 폴링 된 참가자 수</span><span class="sxs-lookup"><span data-stu-id="f2068-414">Number of participants polled per interval</span></span></p></td>
<td><p><span data-ttu-id="f2068-415">가시 채팅방 당 25</span><span class="sxs-lookup"><span data-stu-id="f2068-415">25 per visible chat room</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-416">폴링 간격 길이</span><span class="sxs-lookup"><span data-stu-id="f2068-416">Length of polling interval</span></span></p></td>
<td><p><span data-ttu-id="f2068-417">5 분</span><span class="sxs-lookup"><span data-stu-id="f2068-417">5 minutes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-418">초당 폴링 된 참가자 수</span><span class="sxs-lookup"><span data-stu-id="f2068-418">Number of participants polled per second</span></span></p></td>
<td><p><span data-ttu-id="f2068-419">15000</span><span class="sxs-lookup"><span data-stu-id="f2068-419">15,000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2068-420">사용자별 현재 시간 당 변경 수</span><span class="sxs-lookup"><span data-stu-id="f2068-420">Number of presence changes per hour per user</span></span></p></td>
<td><p><span data-ttu-id="f2068-421">26</span><span class="sxs-lookup"><span data-stu-id="f2068-421">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2068-422">초당 현재 상태 변경 수</span><span class="sxs-lookup"><span data-stu-id="f2068-422">Number of presence changes per second</span></span></p></td>
<td><p><span data-ttu-id="f2068-423">133.33</span><span class="sxs-lookup"><span data-stu-id="f2068-423">133.33</span></span></p></td>
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

