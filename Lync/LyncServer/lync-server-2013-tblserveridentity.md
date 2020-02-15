---
title: 'Lync Server 2013: tblServerIdentity'
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
ms.openlocfilehash: 5f6ed7f0eed08dbb4ab3b0d6f41c9ec91fb719f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a><span data-ttu-id="85161-102">Lync Server 2013의 tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="85161-102">tblServerIdentity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85161-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="85161-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="85161-104">tblServerIdentity에는 영구 채팅 서버 풀의 활성 채팅 서버가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85161-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>

### <a name="columns"></a><span data-ttu-id="85161-105">단</span><span class="sxs-lookup"><span data-stu-id="85161-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85161-106">열</span><span class="sxs-lookup"><span data-stu-id="85161-106">Column</span></span></th>
<th><span data-ttu-id="85161-107">형식</span><span class="sxs-lookup"><span data-stu-id="85161-107">Type</span></span></th>
<th><span data-ttu-id="85161-108">설명</span><span class="sxs-lookup"><span data-stu-id="85161-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85161-109">serverID</span><span class="sxs-lookup"><span data-stu-id="85161-109">serverID</span></span></p></td>
<td><p><span data-ttu-id="85161-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="85161-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="85161-111">서버 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="85161-111">Server ID.</span></span> <span data-ttu-id="85161-112">중앙 관리 저장소의 인스턴스 ID에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="85161-112">Corresponds to the instance ID from Central Management store.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="85161-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="85161-113">serverAddress</span></span></p></td>
<td><p><span data-ttu-id="85161-114">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="85161-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="85161-115">Windows Communication Foundation 주소를 사용 중인 서버 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="85161-115">Server address using the Windows Communication Foundation address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="85161-116">Serverlast(Time)</span><span class="sxs-lookup"><span data-stu-id="85161-116">serverLastPingTime</span></span></p></td>
<td><p><span data-ttu-id="85161-117">datetime</span><span class="sxs-lookup"><span data-stu-id="85161-117">datetime</span></span></p></td>
<td><p><span data-ttu-id="85161-118">실행 중임에 대한 증거를 제공하기 위해 채널 서버가 이 행을 마지막으로 업데이트한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="85161-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="85161-119">키</span><span class="sxs-lookup"><span data-stu-id="85161-119">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="85161-120">열</span><span class="sxs-lookup"><span data-stu-id="85161-120">Column</span></span></th>
<th><span data-ttu-id="85161-121">설명</span><span class="sxs-lookup"><span data-stu-id="85161-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="85161-122">serverID</span><span class="sxs-lookup"><span data-stu-id="85161-122">serverID</span></span></p></td>
<td><p><span data-ttu-id="85161-123">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="85161-123">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

