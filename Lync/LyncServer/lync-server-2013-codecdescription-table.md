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
ms.openlocfilehash: c45300800ad83bbeee0d71abd1a38879f41c903d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="f58f9-102">Lync Server 2013의 CodecDescription 테이블</span><span class="sxs-lookup"><span data-stu-id="f58f9-102">CodecDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f58f9-103">_**마지막으로 수정 된 항목:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="f58f9-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="f58f9-104">CodecDescription 테이블은 고유 코덱 식별자를 해당 코덱에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f58f9-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="f58f9-105">코덱은 전송 및 브로드캐스트용으로 디지털 신호를 인코딩한 다음 재생용으로 신호를 디코딩하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f58f9-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="f58f9-106">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f58f9-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f58f9-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="f58f9-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f58f9-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="f58f9-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f58f9-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="f58f9-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f58f9-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="f58f9-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f58f9-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="f58f9-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f58f9-112">smallint</span><span class="sxs-lookup"><span data-stu-id="f58f9-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="f58f9-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f58f9-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f58f9-114">코덱에 할당된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f58f9-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f58f9-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="f58f9-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f58f9-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f58f9-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f58f9-117">고유한</span><span class="sxs-lookup"><span data-stu-id="f58f9-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="f58f9-118">CodecDescriptionKey에 해당하는 코덱의 고유한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f58f9-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

