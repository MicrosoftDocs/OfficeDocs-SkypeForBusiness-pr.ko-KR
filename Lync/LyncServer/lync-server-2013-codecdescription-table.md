---
title: 'Lync Server 2013: CodecDescription 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f9c6cbdfd24517308321f5f3838fba56e90f842
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="db442-102">Lync Server 2013의 CodecDescription 테이블</span><span class="sxs-lookup"><span data-stu-id="db442-102">CodecDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db442-103">_**마지막으로 수정한 주제:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="db442-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="db442-104">CodecDescription 테이블은 고유 코덱 식별자를 해당 하는 코덱에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="db442-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="db442-105">코덱은 전송 및 브로드캐스트에 대 한 디지털 신호를 인코딩한 다음 재생을 위해 해당 신호를 디코딩 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db442-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="db442-106">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="db442-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db442-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="db442-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="db442-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="db442-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="db442-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="db442-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="db442-110"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="db442-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db442-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="db442-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="db442-112">smallint</span><span class="sxs-lookup"><span data-stu-id="db442-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="db442-113">주요한</span><span class="sxs-lookup"><span data-stu-id="db442-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="db442-114">코덱에 할당 된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="db442-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db442-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="db442-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="db442-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="db442-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db442-117">독특한</span><span class="sxs-lookup"><span data-stu-id="db442-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="db442-118">CodecDescriptionKey에 해당 하는 코덱에 대 한 고유한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="db442-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

