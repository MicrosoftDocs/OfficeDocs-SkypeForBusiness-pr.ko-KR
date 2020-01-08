---
title: 'Lync Server 2013: tblServerIdentity'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7bdd939f838a9f72191d3aae27b9a4a56d26be3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="2386b-102">Lync Server 2013의 tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="2386b-102">tblServerIdentity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2386b-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="2386b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="2386b-104">tblServerIdentity는 영구 채팅 서버 풀의 활성 채팅 서버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2386b-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="2386b-105">열</span><span class="sxs-lookup"><span data-stu-id="2386b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2386b-106">열</span><span class="sxs-lookup"><span data-stu-id="2386b-106">Column</span></span></th>
<th><span data-ttu-id="2386b-107">유형</span><span class="sxs-lookup"><span data-stu-id="2386b-107">Type</span></span></th>
<th><span data-ttu-id="2386b-108">설명</span><span class="sxs-lookup"><span data-stu-id="2386b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2386b-109">serverID</span><span class="sxs-lookup"><span data-stu-id="2386b-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="2386b-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="2386b-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="2386b-111">서버 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2386b-111">Server ID.</span></span> <span data-ttu-id="2386b-112">중앙 관리 저장소의 인스턴스 ID에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2386b-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2386b-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="2386b-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="2386b-114">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="2386b-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="2386b-115">Windows Communication Foundation 주소를 사용 하는 서버 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2386b-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2386b-116">Serverlast(Time)</span><span class="sxs-lookup"><span data-stu-id="2386b-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="2386b-117">dmtf</span><span class="sxs-lookup"><span data-stu-id="2386b-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="2386b-118">채널 서버가이 행을 업데이트 하 여 증거를 실행 하 고 있음을 제공 하는 최근 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2386b-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="2386b-119">키</span><span class="sxs-lookup"><span data-stu-id="2386b-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2386b-120">열</span><span class="sxs-lookup"><span data-stu-id="2386b-120">Column</span></span></th>
<th><span data-ttu-id="2386b-121">설명</span><span class="sxs-lookup"><span data-stu-id="2386b-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2386b-122">serverID</span><span class="sxs-lookup"><span data-stu-id="2386b-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="2386b-123">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="2386b-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

