---
title: 'Lync Server 2013: UserAgent 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b82d8a03f159aa1c99d53dd06a0811847f77b12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="f9447-102">Lync Server 2013의 UserAgent 보기</span><span class="sxs-lookup"><span data-stu-id="f9447-102">UserAgent view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9447-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f9447-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f9447-104">UserAgent 보기에는 데이터베이스에 레코드가 있는 세션에 참여한 사용자 에이전트에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9447-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="f9447-105">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9447-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9447-106">열</span><span class="sxs-lookup"><span data-stu-id="f9447-106">Column</span></span></th>
<th><span data-ttu-id="f9447-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f9447-107">Data Type</span></span></th>
<th><span data-ttu-id="f9447-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f9447-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9447-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="f9447-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="f9447-110">int</span><span class="sxs-lookup"><span data-stu-id="f9447-110">int</span></span></p></td>
<td><p><span data-ttu-id="f9447-111">이 사용자 에이전트를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="f9447-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9447-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="f9447-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="f9447-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="f9447-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f9447-114">사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f9447-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9447-115">UAType</span><span class="sxs-lookup"><span data-stu-id="f9447-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="f9447-116">smallint</span><span class="sxs-lookup"><span data-stu-id="f9447-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="f9447-117">사용자 에이전트의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f9447-117">Type of user agent.</span></span> <span data-ttu-id="f9447-118">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9447-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9447-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="f9447-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="f9447-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f9447-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f9447-p103">사용자가 속한 범주입니다. 예를 들어 사용자 에이전트 Conferencing_Attendant_1.0은 UACategory CAA에 속해 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9447-p103">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

