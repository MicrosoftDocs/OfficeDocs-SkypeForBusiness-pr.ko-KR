---
title: 'Lync Server 2013: UserAgent view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f7d4cf6d79bdd69b28fb88f9a7d6c6a2095ba99
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978103"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="4c352-102">Lync Server 2013의 UserAgent 보기</span><span class="sxs-lookup"><span data-stu-id="4c352-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c352-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4c352-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4c352-104">UserAgent 보기는 데이터베이스에 레코드가 있는 세션과 관련 된 사용자 에이전트에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c352-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="4c352-105">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4c352-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c352-106">열</span><span class="sxs-lookup"><span data-stu-id="4c352-106">Column</span></span></th>
<th><span data-ttu-id="4c352-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4c352-107">Data Type</span></span></th>
<th><span data-ttu-id="4c352-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="4c352-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c352-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="4c352-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="4c352-110">int</span><span class="sxs-lookup"><span data-stu-id="4c352-110">int</span></span></p></td>
<td><p><span data-ttu-id="4c352-111">이 사용자 에이전트를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="4c352-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c352-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="4c352-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="4c352-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4c352-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4c352-114">사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4c352-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c352-115">UAType</span><span class="sxs-lookup"><span data-stu-id="4c352-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="4c352-116">smallint</span><span class="sxs-lookup"><span data-stu-id="4c352-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="4c352-117">사용자 에이전트의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="4c352-117">Type of user agent.</span></span> <span data-ttu-id="4c352-118">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4c352-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c352-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="4c352-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="4c352-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="4c352-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4c352-121">사용자 에이전트가 속한 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="4c352-121">Category that the user agent belongs to.</span></span> <span data-ttu-id="4c352-122">예를 들어 사용자 에이전트 Conferencing_Attendant_1 .0는 UACategory CAA에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="4c352-122">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

