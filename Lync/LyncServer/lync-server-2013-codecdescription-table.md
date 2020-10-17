---
title: 'Lync Server 2013: CodecDescription 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ed272afa7fe21a7b40004fb93dcdfa239b4caf8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520665"
---
# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="7e197-102">Lync Server 2013의 CodecDescription 테이블</span><span class="sxs-lookup"><span data-stu-id="7e197-102">CodecDescription table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e197-103">_**마지막으로 수정 된 항목:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="7e197-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="7e197-104">CodecDescription 테이블은 고유 코덱 식별자를 해당 코덱에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="7e197-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="7e197-105">코덱은 전송 및 브로드캐스트용으로 디지털 신호를 인코딩한 다음 재생용으로 신호를 디코딩하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e197-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="7e197-106">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e197-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e197-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="7e197-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7e197-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="7e197-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7e197-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="7e197-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7e197-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="7e197-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e197-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="7e197-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7e197-112">smallint</span><span class="sxs-lookup"><span data-stu-id="7e197-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="7e197-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7e197-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="7e197-114">코덱에 할당된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7e197-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e197-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="7e197-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="7e197-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e197-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e197-117">고유한</span><span class="sxs-lookup"><span data-stu-id="7e197-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="7e197-118">CodecDescriptionKey에 해당하는 코덱의 고유한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="7e197-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

