---
title: 'Lync Server 2013: ClientVersions 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06e250528a56c10a573c19181fddb1d9acee494d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499165"
---
# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="4cfa0-102">Lync Server 2013의 ClientVersions 보기</span><span class="sxs-lookup"><span data-stu-id="4cfa0-102">ClientVersions view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cfa0-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4cfa0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4cfa0-104">ClientVersions 보기에는 데이터베이스에 기록되는 세션에 참여한 다양한 클라이언트 유형 및 버전 정보가 저장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfa0-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="4cfa0-105">보기의 각 레코드는 하나의 클라이언트 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4cfa0-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="4cfa0-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfa0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4cfa0-107">특정 열에 여러 레코드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfa0-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cfa0-108">열</span><span class="sxs-lookup"><span data-stu-id="4cfa0-108">Column</span></span></th>
<th><span data-ttu-id="4cfa0-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4cfa0-109">Data Type</span></span></th>
<th><span data-ttu-id="4cfa0-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="4cfa0-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cfa0-111"><strong>#</strong></span><span class="sxs-lookup"><span data-stu-id="4cfa0-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="4cfa0-112">int</span><span class="sxs-lookup"><span data-stu-id="4cfa0-112">int</span></span></p></td>
<td><p><span data-ttu-id="4cfa0-113">이 클라이언트 유형 및 버전을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="4cfa0-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cfa0-114"><strong>버전</strong></span><span class="sxs-lookup"><span data-stu-id="4cfa0-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="4cfa0-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4cfa0-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4cfa0-116">사용자 에이전트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4cfa0-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cfa0-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="4cfa0-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="4cfa0-118">int</span><span class="sxs-lookup"><span data-stu-id="4cfa0-118">int</span></span></p></td>
<td><p><span data-ttu-id="4cfa0-119">클라이언트 유형입니다</span><span class="sxs-lookup"><span data-stu-id="4cfa0-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cfa0-120"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="4cfa0-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="4cfa0-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="4cfa0-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4cfa0-p102">클라이언트가 속한 범주입니다. 예를 들어 Conferencing_Attendant_1.0 클라이언트는 ClientCategory CAA에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfa0-p102">Category that the client belongs to. For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

