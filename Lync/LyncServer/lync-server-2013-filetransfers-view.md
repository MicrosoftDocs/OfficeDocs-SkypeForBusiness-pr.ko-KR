---
title: 'Lync Server 2013: FileTransfers view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4228bbe42f2e7bcf88b26f9147e514f09c106ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="d752f-102">Lync Server 2013의 FileTransfers 보기</span><span class="sxs-lookup"><span data-stu-id="d752f-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d752f-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d752f-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d752f-104">FileTransfer 보기는 피어 투 피어 파일 전송 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d752f-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="d752f-105">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d752f-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d752f-106">FileTransfers 보기에는 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013의 Sessiondetails 보기</A> 에 아래 나열 된 열 외에 모든 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d752f-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d752f-107">열</span><span class="sxs-lookup"><span data-stu-id="d752f-107">Column</span></span></th>
<th><span data-ttu-id="d752f-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d752f-108">Data Type</span></span></th>
<th><span data-ttu-id="d752f-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="d752f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d752f-110"><strong>이름이</strong></span><span class="sxs-lookup"><span data-stu-id="d752f-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="d752f-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d752f-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d752f-112">전송 된 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d752f-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d752f-113"><strong>쿠키란</strong></span><span class="sxs-lookup"><span data-stu-id="d752f-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="d752f-114">name</span><span class="sxs-lookup"><span data-stu-id="d752f-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d752f-115">모든 추가 작업 메시지를이 항목에 연결 된 것으로 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d752f-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d752f-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="d752f-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="d752f-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d752f-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d752f-118">동일한 파일 이름을 포함 하는 파일 전송을 구분 하는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d752f-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d752f-119"><strong>사항</strong></span><span class="sxs-lookup"><span data-stu-id="d752f-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="d752f-120">다소</span><span class="sxs-lookup"><span data-stu-id="d752f-120">bit</span></span></p></td>
<td><p><span data-ttu-id="d752f-121">TRUE 또는 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d752f-121">Can be TRUE or NULL.</span></span> <span data-ttu-id="d752f-122">TRUE 인 경우 거부 및 취소는 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="d752f-122">If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d752f-123"><strong>거부</strong></span><span class="sxs-lookup"><span data-stu-id="d752f-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="d752f-124">다소</span><span class="sxs-lookup"><span data-stu-id="d752f-124">bit</span></span></p></td>
<td><p><span data-ttu-id="d752f-125">TRUE 또는 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d752f-125">Can be TRUE or NULL.</span></span> <span data-ttu-id="d752f-126">TRUE 이면 Accept와 Cancel은 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="d752f-126">If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d752f-127"><strong>취소</strong></span><span class="sxs-lookup"><span data-stu-id="d752f-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="d752f-128">다소</span><span class="sxs-lookup"><span data-stu-id="d752f-128">bit</span></span></p></td>
<td><p><span data-ttu-id="d752f-129">TRUE 또는 NULL 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d752f-129">Can be TRUE or NULL.</span></span> <span data-ttu-id="d752f-130">TRUE 이면 Accept 및 Reject는 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="d752f-130">If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

