---
title: 'Lync Server 2013: FileTransfers 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2bf6f78a564ef1fd526ba8d265bedf81c845810
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="d61bd-102">Lync Server 2013의 FileTransfers 보기</span><span class="sxs-lookup"><span data-stu-id="d61bd-102">FileTransfers view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d61bd-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d61bd-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d61bd-104">FileTransfer 보기에는 피어 투 피어 파일 전송 세션에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d61bd-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="d61bd-105">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d61bd-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d61bd-106">FileTransfers 보기에는 아래 나열 된 열 외에도 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013의 Sessiondetails view</A> 의 모든 열이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d61bd-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d61bd-107">열</span><span class="sxs-lookup"><span data-stu-id="d61bd-107">Column</span></span></th>
<th><span data-ttu-id="d61bd-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d61bd-108">Data Type</span></span></th>
<th><span data-ttu-id="d61bd-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d61bd-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d61bd-110"><strong>이름을</strong></span><span class="sxs-lookup"><span data-stu-id="d61bd-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="d61bd-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d61bd-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d61bd-112">전송 된 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d61bd-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d61bd-113"><strong>쿠키나</strong></span><span class="sxs-lookup"><span data-stu-id="d61bd-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="d61bd-114">name</span><span class="sxs-lookup"><span data-stu-id="d61bd-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d61bd-115">이 항목과 연결 중인 모든 후속 작업 메시지를 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d61bd-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d61bd-116"><strong>FileIdentity</strong></span><span class="sxs-lookup"><span data-stu-id="d61bd-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="d61bd-117">고유</span><span class="sxs-lookup"><span data-stu-id="d61bd-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d61bd-118">동일한 파일 이름을 포함하는 각 전송 작업을 구분하기 위한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d61bd-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d61bd-119"><strong>수락</strong></span><span class="sxs-lookup"><span data-stu-id="d61bd-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="d61bd-120">비트만</span><span class="sxs-lookup"><span data-stu-id="d61bd-120">bit</span></span></p></td>
<td><p><span data-ttu-id="d61bd-p102">TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Reject 및 Cancel이 NULL이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d61bd-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d61bd-123"><strong>거부</strong></span><span class="sxs-lookup"><span data-stu-id="d61bd-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="d61bd-124">비트만</span><span class="sxs-lookup"><span data-stu-id="d61bd-124">bit</span></span></p></td>
<td><p><span data-ttu-id="d61bd-p103">TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Cancel이 NULL이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d61bd-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d61bd-127"><strong>취소</strong></span><span class="sxs-lookup"><span data-stu-id="d61bd-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="d61bd-128">비트만</span><span class="sxs-lookup"><span data-stu-id="d61bd-128">bit</span></span></p></td>
<td><p><span data-ttu-id="d61bd-p104">TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Reject가 NULL이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d61bd-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

