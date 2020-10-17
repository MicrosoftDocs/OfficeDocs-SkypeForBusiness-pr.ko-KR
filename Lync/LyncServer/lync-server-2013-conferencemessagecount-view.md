---
title: 'Lync Server 2013: ConferenceMessageCount 보기'
description: 'Lync Server 2013: ConferenceMessageCount 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 212d6e1a346253809fb70806424350cc7fc0dfe2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561614"
---
# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="4fbca-103">Lync Server 2013의 ConferenceMessageCount 보기</span><span class="sxs-lookup"><span data-stu-id="4fbca-103">ConferenceMessageCount view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fbca-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4fbca-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4fbca-105">ConferenceMessageCount 보기에는 사용자가 회의에 전송한 메시지 수에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fbca-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="4fbca-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4fbca-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4fbca-107">ConferenceMessageCount 보기에는 아래 나열 된 열 외에도 <A href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013의 ConferenceSessionDetails 보기</A> 에 있는 모든 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fbca-107">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4fbca-108">열</span><span class="sxs-lookup"><span data-stu-id="4fbca-108">Column</span></span></th>
<th><span data-ttu-id="4fbca-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4fbca-109">Data Type</span></span></th>
<th><span data-ttu-id="4fbca-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="4fbca-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4fbca-111"><strong>변수와 useruri</strong></span><span class="sxs-lookup"><span data-stu-id="4fbca-111"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="4fbca-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="4fbca-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="4fbca-113">메시지를 보낸 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="4fbca-113">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fbca-114"><strong>Userurit<</strong></span><span class="sxs-lookup"><span data-stu-id="4fbca-114"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="4fbca-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4fbca-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4fbca-116">메시지를 보낸 사용자 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4fbca-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="4fbca-117">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fbca-117">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4fbca-118"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="4fbca-118"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="4fbca-119">고유</span><span class="sxs-lookup"><span data-stu-id="4fbca-119">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="4fbca-120">메시지를 보낸 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="4fbca-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="4fbca-121">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4fbca-121">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4fbca-122"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="4fbca-122"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="4fbca-123">smallint</span><span class="sxs-lookup"><span data-stu-id="4fbca-123">smallint</span></span></p></td>
<td><p><span data-ttu-id="4fbca-124">회의 세션 중 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4fbca-124">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

