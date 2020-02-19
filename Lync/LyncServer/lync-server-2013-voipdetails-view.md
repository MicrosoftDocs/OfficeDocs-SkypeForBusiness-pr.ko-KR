---
title: 'Lync Server 2013: VoIPDetails 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5894004244d723d3b233e2963411fdf85b6782ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42118931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="11b29-102">Lync Server 2013의 VoIPDetails 보기</span><span class="sxs-lookup"><span data-stu-id="11b29-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11b29-103">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="11b29-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="11b29-104">VoIPDetails 보기에는 한 명 이상의 사용자가 VoIP 사용자인 피어 투 피어 세션에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="11b29-105">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11b29-106">VoIPDetails 보기에는 아래 나열 된 열 외에도 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013의 Sessiondetails view</A> 의 모든 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11b29-107">열</span><span class="sxs-lookup"><span data-stu-id="11b29-107">Column</span></span></th>
<th><span data-ttu-id="11b29-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="11b29-108">Data Type</span></span></th>
<th><span data-ttu-id="11b29-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="11b29-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11b29-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="11b29-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="11b29-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="11b29-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="11b29-112">세션을 시작한 사용자의 전화 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11b29-113"><strong>ToPhone</strong></span><span class="sxs-lookup"><span data-stu-id="11b29-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="11b29-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="11b29-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="11b29-115">세션에 참가한 사용자의 전화 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11b29-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="11b29-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="11b29-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="11b29-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="11b29-118">세션 연결을 끊은 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11b29-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="11b29-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="11b29-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11b29-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="11b29-121">세션 연결을 끊은 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="11b29-122">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="11b29-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11b29-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="11b29-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="11b29-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11b29-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="11b29-125">세션 연결을 끊은 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11b29-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="11b29-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="11b29-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="11b29-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="11b29-128">세션 연결을 끊은 사용자의 전화 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11b29-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="11b29-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="11b29-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11b29-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="11b29-131">세션을 시작한 사용자가 사용하는 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11b29-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="11b29-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="11b29-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11b29-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="11b29-134">세션에 참가한 사용자가 사용하는 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11b29-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="11b29-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="11b29-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11b29-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="11b29-137">세션을 시작한 사용자가 사용하는 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11b29-138"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="11b29-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="11b29-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="11b29-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="11b29-140">세션에 참가한 사용자가 사용하는 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="11b29-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

