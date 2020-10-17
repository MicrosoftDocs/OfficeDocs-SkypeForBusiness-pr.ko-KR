---
title: 'Lync Server 2013: ClientVersions 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8987bc1078dfdfaec8cccdb6625ceb9846ef6a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499175"
---
# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="98c1f-102">Lync Server 2013의 ClientVersions 테이블</span><span class="sxs-lookup"><span data-stu-id="98c1f-102">ClientVersions table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98c1f-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="98c1f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="98c1f-p101">ClientVersions 테이블은 데이터베이스에 기록되는 세션에 참여한 다양한 클라이언트 유형 및 버전 목록이 저장된 지원 테이블입니다. 테이블의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="98c1f-p101">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98c1f-106">열</span><span class="sxs-lookup"><span data-stu-id="98c1f-106">Column</span></span></th>
<th><span data-ttu-id="98c1f-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="98c1f-107">Data Type</span></span></th>
<th><span data-ttu-id="98c1f-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="98c1f-108">Key/Index</span></span></th>
<th><span data-ttu-id="98c1f-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="98c1f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98c1f-110"><strong>#</strong></span><span class="sxs-lookup"><span data-stu-id="98c1f-110"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="98c1f-111"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="98c1f-111"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="98c1f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="98c1f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="98c1f-113">이 클라이언트 유형 및 버전을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="98c1f-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98c1f-114"><strong>버전</strong></span><span class="sxs-lookup"><span data-stu-id="98c1f-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="98c1f-115"><strong>nvarchar (256)</strong></span><span class="sxs-lookup"><span data-stu-id="98c1f-115"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="98c1f-116">버전 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="98c1f-116">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98c1f-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="98c1f-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="98c1f-118">int</span><span class="sxs-lookup"><span data-stu-id="98c1f-118">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="98c1f-119">세션에 사용된 클라이언트 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="98c1f-119">Specifies the type of client used in the session.</span></span> <span data-ttu-id="98c1f-120">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="98c1f-120">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="98c1f-121">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="98c1f-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

