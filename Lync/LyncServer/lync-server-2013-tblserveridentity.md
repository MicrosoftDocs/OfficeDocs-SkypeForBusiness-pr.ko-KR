---
title: 'Lync Server 2013: tblServerIdentity'
description: 'Lync Server 2013: tblServerIdentity'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e954618cb373f2cf4f1b7ed929c3aaf6d8875e92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564534"
---
# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="aa457-103">Lync Server 2013의 tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="aa457-103">tblServerIdentity in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa457-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="aa457-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="aa457-105">tblServerIdentity에는 영구 채팅 서버 풀의 활성 채팅 서버가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa457-105">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="aa457-106">단</span><span class="sxs-lookup"><span data-stu-id="aa457-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa457-107">열</span><span class="sxs-lookup"><span data-stu-id="aa457-107">Column</span></span></th>
<th><span data-ttu-id="aa457-108">유형</span><span class="sxs-lookup"><span data-stu-id="aa457-108">Type</span></span></th>
<th><span data-ttu-id="aa457-109">설명</span><span class="sxs-lookup"><span data-stu-id="aa457-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa457-110">serverID</span><span class="sxs-lookup"><span data-stu-id="aa457-110">serverID</span></span></p></td>
<td><p><span data-ttu-id="aa457-111">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="aa457-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="aa457-112">서버 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="aa457-112">Server ID.</span></span> <span data-ttu-id="aa457-113">중앙 관리 저장소의 인스턴스 ID에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa457-113">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa457-114">serverAddress</span><span class="sxs-lookup"><span data-stu-id="aa457-114">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="aa457-115">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="aa457-115">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="aa457-116">Windows Communication Foundation 주소를 사용 중인 서버 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="aa457-116">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa457-117">Serverlast(Time)</span><span class="sxs-lookup"><span data-stu-id="aa457-117">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="aa457-118">datetime</span><span class="sxs-lookup"><span data-stu-id="aa457-118">datetime</span></span></p></td>
<td><p><span data-ttu-id="aa457-119">실행 중임에 대한 증거를 제공하기 위해 채널 서버가 이 행을 마지막으로 업데이트한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="aa457-119">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="aa457-120">키</span><span class="sxs-lookup"><span data-stu-id="aa457-120">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa457-121">열</span><span class="sxs-lookup"><span data-stu-id="aa457-121">Column</span></span></th>
<th><span data-ttu-id="aa457-122">설명</span><span class="sxs-lookup"><span data-stu-id="aa457-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa457-123">serverID</span><span class="sxs-lookup"><span data-stu-id="aa457-123">serverID</span></span></p></td>
<td><p><span data-ttu-id="aa457-124">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="aa457-124">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

