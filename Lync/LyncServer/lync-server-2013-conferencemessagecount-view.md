---
title: 'Lync Server 2013: ConferenceMessageCount view'
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
ms.openlocfilehash: 73944e1561b88301b740fcb52cf301645154c6e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="b92a5-102">Lync Server 2013의 ConferenceMessageCount 보기</span><span class="sxs-lookup"><span data-stu-id="b92a5-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b92a5-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b92a5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b92a5-104">ConferenceMessageCount 보기는 사용자가 회의에 보낸 메시지 수에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b92a5-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="b92a5-105">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b92a5-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b92a5-106">ConferenceMessageCount 보기에는 <A href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013의 ConferenceSessionDetails 보기</A> 에 아래 나열 된 열 외에 모든 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b92a5-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b92a5-107">열</span><span class="sxs-lookup"><span data-stu-id="b92a5-107">Column</span></span></th>
<th><span data-ttu-id="b92a5-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b92a5-108">Data Type</span></span></th>
<th><span data-ttu-id="b92a5-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="b92a5-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b92a5-110"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="b92a5-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b92a5-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b92a5-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b92a5-112">메시지를 보낸 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b92a5-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92a5-113"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b92a5-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b92a5-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b92a5-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b92a5-115">메시지를 보낸 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b92a5-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="b92a5-116">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b92a5-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b92a5-117"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="b92a5-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b92a5-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b92a5-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b92a5-119">메시지를 보낸 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="b92a5-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="b92a5-120">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b92a5-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b92a5-121"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="b92a5-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="b92a5-122">smallint</span><span class="sxs-lookup"><span data-stu-id="b92a5-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="b92a5-123">회의 세션 동안 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b92a5-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

