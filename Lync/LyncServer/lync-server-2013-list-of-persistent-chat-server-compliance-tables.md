---
title: 'Lync Server 2013: 영구 채팅 서버 준수 테이블 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c4f6e9622e839e2f1fd719b8e2d7ba95286247e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="056fa-102">Lync Server 2013의 영구 채팅 서버 준수 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="056fa-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="056fa-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="056fa-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="056fa-104">영구 채팅 준수 데이터베이스 스키마는 다음 테이블로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="056fa-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="056fa-105">영구 채팅 서버 준수 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="056fa-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="056fa-106">테이블로</span><span class="sxs-lookup"><span data-stu-id="056fa-106">Table</span></span></th>
<th><span data-ttu-id="056fa-107">설명</span><span class="sxs-lookup"><span data-stu-id="056fa-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="056fa-108"><a href="lync-server-2013-tblcompliancedata.md">Lync Server 2013의 tblComplianceData</a></span><span class="sxs-lookup"><span data-stu-id="056fa-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="056fa-109">구성 된 어댑터에서 아직 처리 하지 않은 준수 이벤트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="056fa-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="056fa-110">이 표에는 채팅 메시지 및 파일 다운로드와 같은 지속적인 채팅 관련 이벤트가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fa-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="056fa-111">(참가자 이벤트는 tblComplianceParticipant 테이블에서 추적 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="056fa-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="056fa-112">(이 테이블의 이벤트를 처리 하는 서버는 tblComplianceFanout 테이블에 나열 되어 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="056fa-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="056fa-113"><a href="lync-server-2013-tblcompliancefanout.md">Lync Server 2013의 tblComplianceFanout</a></span><span class="sxs-lookup"><span data-stu-id="056fa-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="056fa-114">규정 준수 이벤트를 처리 한 서버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="056fa-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="056fa-115">이 표는 tblComplianceData 테이블과 밀접 하 게 결합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fa-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="056fa-116"><a href="lync-server-2013-tblcomplianceparticipant.md">Lync Server 2013의 tblComplianceParticipant</a></span><span class="sxs-lookup"><span data-stu-id="056fa-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="056fa-117">채팅 서비스 및 서버 별로 현재 참가자가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="056fa-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="056fa-118">영구 채팅 서비스에서 받은 참가 및 파트 규정 준수 이벤트에 따라 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="056fa-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="056fa-119"><a href="lync-server-2013-tblcompliancestate.md">Lync Server 2013의 tblComplianceState</a></span><span class="sxs-lookup"><span data-stu-id="056fa-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="056fa-120">풀 전체의 준수 상태 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="056fa-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

