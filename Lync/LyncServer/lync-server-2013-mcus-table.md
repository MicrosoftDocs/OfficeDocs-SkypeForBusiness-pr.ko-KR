---
title: 'Lync Server 2013: Mcus 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 522c7babbda63c550679dab1eb8eb03114417169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="407da-102">Lync Server 2013의 Mcus 테이블</span><span class="sxs-lookup"><span data-stu-id="407da-102">Mcus table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="407da-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="407da-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="407da-104">Mcus 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="407da-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="407da-105">각 레코드는 하나의 회의 서비스에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="407da-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="407da-106">여기에는 IM 회의 서비스 및 전화 통신 회의 서비스 (프런트 엔드 서버에서 프로세스로 실행 됨)와 웹 회의 서비스 및 A/V 회의 서비스가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="407da-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="407da-107">열</span><span class="sxs-lookup"><span data-stu-id="407da-107">Column</span></span></th>
<th><span data-ttu-id="407da-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="407da-108">Data Type</span></span></th>
<th><span data-ttu-id="407da-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="407da-109">Key/Index</span></span></th>
<th><span data-ttu-id="407da-110">세부적인</span><span class="sxs-lookup"><span data-stu-id="407da-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="407da-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="407da-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="407da-112">int</span><span class="sxs-lookup"><span data-stu-id="407da-112">int</span></span></p></td>
<td><p><span data-ttu-id="407da-113">주요한</span><span class="sxs-lookup"><span data-stu-id="407da-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="407da-114">이 회의 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="407da-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="407da-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="407da-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="407da-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="407da-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="407da-117"><strong>M가공선 Ypeid</strong></span><span class="sxs-lookup"><span data-stu-id="407da-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="407da-118">inyint</span><span class="sxs-lookup"><span data-stu-id="407da-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="407da-119"> 외부</span><span class="sxs-lookup"><span data-stu-id="407da-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="407da-120">컨퍼런스: 채팅 (Im의 경우) 또는 컨퍼런스: 오디오-비디오 등의 회의 서버 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="407da-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="407da-121">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="407da-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

