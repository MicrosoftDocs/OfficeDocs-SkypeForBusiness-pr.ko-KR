---
title: 'Lync Server 2013: ClientVersions 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba578209ca6c22360da73c2317334ecf77da569
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="09c96-102">Lync Server 2013의 ClientVersions 테이블</span><span class="sxs-lookup"><span data-stu-id="09c96-102">ClientVersions table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09c96-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="09c96-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="09c96-104">ClientVersions 테이블은 다양 한 클라이언트 유형 및 데이터베이스에 기록 된 세션에 참가 한 버전의 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="09c96-104">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="09c96-105">테이블의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09c96-105">Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09c96-106">열</span><span class="sxs-lookup"><span data-stu-id="09c96-106">Column</span></span></th>
<th><span data-ttu-id="09c96-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="09c96-107">Data Type</span></span></th>
<th><span data-ttu-id="09c96-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="09c96-108">Key/Index</span></span></th>
<th><span data-ttu-id="09c96-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="09c96-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09c96-110"><strong>#</strong></span><span class="sxs-lookup"><span data-stu-id="09c96-110"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="09c96-111"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="09c96-111"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="09c96-112">주요한</span><span class="sxs-lookup"><span data-stu-id="09c96-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="09c96-113">이 클라이언트 유형 및 버전을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="09c96-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09c96-114"><strong>버전</strong></span><span class="sxs-lookup"><span data-stu-id="09c96-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="09c96-115"><strong>nvarchar (256)</strong></span><span class="sxs-lookup"><span data-stu-id="09c96-115"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="09c96-116">버전 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="09c96-116">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09c96-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="09c96-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="09c96-118">int</span><span class="sxs-lookup"><span data-stu-id="09c96-118">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="09c96-119">세션에 사용 되는 클라이언트 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c96-119">Specifies the type of client used in the session.</span></span> <span data-ttu-id="09c96-120">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="09c96-120">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="09c96-121">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09c96-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

