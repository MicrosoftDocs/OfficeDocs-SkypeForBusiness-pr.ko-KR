---
title: 'Lync Server 2013: MediationServers 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediationServers table
ms:assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412743(v=OCS.15)
ms:contentKeyID: 48184929
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7854306eefb1bed16753e8f6408a8c06f95bd04f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediationservers-table-in-lync-server-2013"></a><span data-ttu-id="20080-102">Lync Server 2013의 MediationServers 테이블</span><span class="sxs-lookup"><span data-stu-id="20080-102">MediationServers table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20080-103">_**마지막으로 수정한 주제:** 2010-11-06_</span><span class="sxs-lookup"><span data-stu-id="20080-103">_**Topic Last Modified:** 2010-11-06_</span></span>

<span data-ttu-id="20080-104">MediationServers 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="20080-104">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="20080-105">각 레코드는 데이터베이스의 레코드를 포함 하는 호출에 관련 된 중재 서버 하나에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="20080-105">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20080-106">열</span><span class="sxs-lookup"><span data-stu-id="20080-106">Column</span></span></th>
<th><span data-ttu-id="20080-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="20080-107">Data Type</span></span></th>
<th><span data-ttu-id="20080-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="20080-108">Key/Index</span></span></th>
<th><span data-ttu-id="20080-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="20080-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20080-110"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="20080-110"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="20080-111">int</span><span class="sxs-lookup"><span data-stu-id="20080-111">int</span></span></p></td>
<td><p><span data-ttu-id="20080-112">주요한</span><span class="sxs-lookup"><span data-stu-id="20080-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="20080-113">이 중재 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="20080-113">Unique number identifying this Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20080-114"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="20080-114"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="20080-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="20080-115">nvarchar(256)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="20080-116">중재 서버 이름.</span><span class="sxs-lookup"><span data-stu-id="20080-116">Mediation Server name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

