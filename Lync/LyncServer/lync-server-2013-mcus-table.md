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
ms.openlocfilehash: 696a32ec4329b06c67dc8c54ba3ff2c1f15486d5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524665"
---
# <a name="mcus-table-in-lync-server-2013"></a><span data-ttu-id="9f7e1-102">Lync Server 2013의 Mcus 테이블</span><span class="sxs-lookup"><span data-stu-id="9f7e1-102">Mcus table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f7e1-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9f7e1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9f7e1-104">Mcus 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="9f7e1-104">The Mcus table is a supporting table.</span></span> <span data-ttu-id="9f7e1-105">각 레코드에는 하나의 회의 서비스에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f7e1-105">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="9f7e1-106">여기에는 IM 회의 서비스와 전화 회의 서비스 (프런트 엔드 서버에서 프로세스로 실행), 웹 회의 서비스 및 A/V 회의 서비스가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f7e1-106">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f7e1-107">열</span><span class="sxs-lookup"><span data-stu-id="9f7e1-107">Column</span></span></th>
<th><span data-ttu-id="9f7e1-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9f7e1-108">Data Type</span></span></th>
<th><span data-ttu-id="9f7e1-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="9f7e1-109">Key/Index</span></span></th>
<th><span data-ttu-id="9f7e1-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="9f7e1-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f7e1-111"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="9f7e1-111"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="9f7e1-112">int</span><span class="sxs-lookup"><span data-stu-id="9f7e1-112">int</span></span></p></td>
<td><p><span data-ttu-id="9f7e1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9f7e1-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="9f7e1-114">이 회의 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9f7e1-114">Unique number identifying this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f7e1-115"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="9f7e1-115"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9f7e1-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9f7e1-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f7e1-117"><strong>M가공선 Ypeid</strong></span><span class="sxs-lookup"><span data-stu-id="9f7e1-117"><strong>McuTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="9f7e1-118">inyint</span><span class="sxs-lookup"><span data-stu-id="9f7e1-118">inyint</span></span></p></td>
<td><p><span data-ttu-id="9f7e1-119"> 외부</span><span class="sxs-lookup"><span data-stu-id="9f7e1-119"> Foreign</span></span></p></td>
<td><p><span data-ttu-id="9f7e1-120">회의 서버 유형 (예: 전화 (IMs) 또는 회의: 오디오-비디오)입니다.</span><span class="sxs-lookup"><span data-stu-id="9f7e1-120">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="9f7e1-121">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f7e1-121">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

