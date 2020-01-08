---
title: 'Lync Server 2013: EdgeServers 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: EdgeServers table
ms:assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412833(v=OCS.15)
ms:contentKeyID: 48185081
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca947d710693590d6121242e79a6d29088432e0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edgeservers-table-in-lync-server-2013"></a><span data-ttu-id="ab24a-102">Lync Server 2013의 EdgeServers 테이블</span><span class="sxs-lookup"><span data-stu-id="ab24a-102">EdgeServers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab24a-103">_**마지막으로 수정한 주제:** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="ab24a-103">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="ab24a-104">EdgeServers 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ab24a-104">The EdgeServers table is a supporting table.</span></span> <span data-ttu-id="ab24a-105">각 레코드는 데이터베이스의 레코드를 포함 하는 호출에 관련 된 하나의 Edge 서버에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab24a-105">Each record stores information about one Edge Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab24a-106">열</span><span class="sxs-lookup"><span data-stu-id="ab24a-106">Column</span></span></th>
<th><span data-ttu-id="ab24a-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab24a-107">Data Type</span></span></th>
<th><span data-ttu-id="ab24a-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="ab24a-108">Key/Index</span></span></th>
<th><span data-ttu-id="ab24a-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="ab24a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab24a-110"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ab24a-110"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ab24a-111">int</span><span class="sxs-lookup"><span data-stu-id="ab24a-111">int</span></span></p></td>
<td><p><span data-ttu-id="ab24a-112">주요한</span><span class="sxs-lookup"><span data-stu-id="ab24a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ab24a-113">이 Edge 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ab24a-113">Unique number identifying this Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab24a-114"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="ab24a-114"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ab24a-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ab24a-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ab24a-116">Edge 서버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ab24a-116">Edge Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

