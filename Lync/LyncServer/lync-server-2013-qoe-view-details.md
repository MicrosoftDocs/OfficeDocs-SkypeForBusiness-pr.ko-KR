---
title: 'Lync Server 2013: 체감 품질 보기 세부 정보'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e223ff2adee63eb8e13304e4df6db519e85014f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="bb373-102">체감 품질 Lync Server 2013의 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="bb373-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb373-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="bb373-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="bb373-104">보기는 체감 품질 SQL 데이터베이스에서 데이터를 반환 하는 가장 일반적인 시나리오를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="bb373-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="bb373-105">데이터베이스 테이블에 직접 액세스 하는 대신 사용자 지정 보고서를 작성 하는 데 사용 하는 것이 좋습니다. 이는 뷰가 향후 릴리스에서 이전 버전과의 호환성을 유지 하는 것이 더 많을 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="bb373-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb373-106">이름 보기</span><span class="sxs-lookup"><span data-stu-id="bb373-106">View Name</span></span></th>
<th><span data-ttu-id="bb373-107">설명</span><span class="sxs-lookup"><span data-stu-id="bb373-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb373-108"><a href="lync-server-2013-audiostreamdetail-view.md">Lync Server 2013의 오디오 Streamdetail 보기</a></span><span class="sxs-lookup"><span data-stu-id="bb373-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bb373-109">데이터베이스에 각 오디오 스트림에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb373-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb373-110"><a href="lync-server-2013-medialine-view.md">Lync Server 2013의 MediaLine</a></span><span class="sxs-lookup"><span data-stu-id="bb373-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bb373-111">데이터베이스의 각 미디어 라인에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb373-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="bb373-112">일반적으로 하나의 오디오 세션에 오디오 미디어 선이 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb373-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="bb373-113">하나의 오디오 및 비디오 (A/V) 세션에는 일반적으로 오디오 미디어 회선 하 나와 비디오 미디어 라인 하나가 포함 됩니다. 그러나 회의 장치를 사용 하거나 갤러리 보기를 사용 하는 경우에는 세션에 두 개의 비디오 미디어 줄이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb373-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb373-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Lync Server 2013의 NetworkConfigurationSettings 보기</a></span><span class="sxs-lookup"><span data-stu-id="bb373-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bb373-115">네트워크 구성에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb373-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb373-116"><a href="lync-server-2013-session-view.md">Lync Server 2013의 세션 보기</a></span><span class="sxs-lookup"><span data-stu-id="bb373-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bb373-117">데이터베이스에 레코드가 있는 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb373-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb373-118"><a href="lync-server-2013-useragent-view.md">Lync Server 2013의 UserAgent 보기</a></span><span class="sxs-lookup"><span data-stu-id="bb373-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bb373-119">데이터베이스에 레코드가 있는 세션과 관련 된 사용자 에이전트에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb373-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb373-120"><a href="lync-server-2013-videostreamdetail-view.md">Lync Server 2013의 VideoStreamDetail 보기</a></span><span class="sxs-lookup"><span data-stu-id="bb373-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bb373-121">데이터베이스의 각 비디오 스트림에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb373-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

