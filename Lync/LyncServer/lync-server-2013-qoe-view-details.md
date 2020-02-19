---
title: 'Lync Server 2013: QoE view details'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f6d2b30654272baf0ce8db712461acb3e4f13a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="13cf5-102">QoE Lync Server 2013의 세부 정보 보기</span><span class="sxs-lookup"><span data-stu-id="13cf5-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13cf5-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="13cf5-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="13cf5-104">보기에는 QoE SQL 데이터베이스에서 데이터를 반환 하는 가장 일반적인 시나리오가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cf5-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="13cf5-105">데이터베이스 테이블에 직접 액세스 하는 대신 사용자 지정 보고서를 작성 하는 데 사용 하는 것이 좋습니다. 이는 보기가 향후 버전과의 호환성을 유지 하는 것이 더 많기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="13cf5-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13cf5-106">보기 이름</span><span class="sxs-lookup"><span data-stu-id="13cf5-106">View Name</span></span></th>
<th><span data-ttu-id="13cf5-107">설명</span><span class="sxs-lookup"><span data-stu-id="13cf5-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13cf5-108"><a href="lync-server-2013-audiostreamdetail-view.md">Lync Server 2013의 오디오 Streamdetail 보기</a></span><span class="sxs-lookup"><span data-stu-id="13cf5-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="13cf5-109">데이터베이스의 각 오디오 스트림에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="13cf5-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13cf5-110"><a href="lync-server-2013-medialine-view.md">Lync Server 2013의 MediaLine</a></span><span class="sxs-lookup"><span data-stu-id="13cf5-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="13cf5-111">데이터베이스의 각 미디어 라인에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="13cf5-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="13cf5-112">하나의 오디오 세션은 일반적으로 오디오 미디어 회선 하나를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="13cf5-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="13cf5-113">하나의 A/V(오디오 및 비디오) 세션은 보통 오디오 미디어 회선과 비디오 미디어 회선을 하나씩 포함하지만, 회의 장치나 갤러리 보기를 사용하는 경우에는 세션이 비디오 미디어 회선 두 개를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13cf5-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13cf5-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">Lync Server 2013의 NetworkConfigurationSettings 보기</a></span><span class="sxs-lookup"><span data-stu-id="13cf5-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="13cf5-115">네트워크 구성에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="13cf5-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13cf5-116"><a href="lync-server-2013-session-view.md">Lync Server 2013의 세션 보기</a></span><span class="sxs-lookup"><span data-stu-id="13cf5-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="13cf5-117">데이터베이스의 레코드가 포함 된 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="13cf5-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13cf5-118"><a href="lync-server-2013-useragent-view.md">Lync Server 2013의 UserAgent 보기</a></span><span class="sxs-lookup"><span data-stu-id="13cf5-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="13cf5-119">데이터베이스의 레코드를 포함 하는 세션에 포함 된 사용자 에이전트에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="13cf5-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13cf5-120"><a href="lync-server-2013-videostreamdetail-view.md">Lync Server 2013의 VideoStreamDetail 보기</a></span><span class="sxs-lookup"><span data-stu-id="13cf5-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="13cf5-121">데이터베이스의 각 비디오 스트림에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="13cf5-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

