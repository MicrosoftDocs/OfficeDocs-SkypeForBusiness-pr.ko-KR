---
title: 'Lync Server 2013: DNS 요약-단일 디렉터'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205021(v=OCS.15)
ms:contentKeyID: 48184568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76fe7663e0af8eeeb049ca80f1dd92a7cc882b98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="b83d2-102">Lync Server 2013의 DNS 요약-단일 디렉터</span><span class="sxs-lookup"><span data-stu-id="b83d2-102">DNS summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b83d2-103">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="b83d2-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="b83d2-104">다음 표에는 단일 디렉터를 지 원하는 데 필요한 DNS 레코드에 대 한 요약이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b83d2-104">The following table contains a summary of the DNS records that are required to support the single Director.</span></span> <span data-ttu-id="b83d2-105">디렉터 역할에는 프런트 엔드 서버로 서 유사한 DNS 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b83d2-105">The role of the Director requires similar DNS records as the Front End Server.</span></span> <span data-ttu-id="b83d2-106">필요한 레코드 수는 디렉터 인증서에 필요한 주체 대체 이름에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b83d2-106">The number of records needed is reflected in the subject alternative names required on the Director certificate.</span></span> <span data-ttu-id="b83d2-107">프런트 엔드 서버와 달리 디렉터는 사용자 계정을 호스트 하거나 모바일 서비스를 호스트 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b83d2-107">Different from the Front End Server, the Director does not host user accounts or host the Mobility Services.</span></span>

### <a name="dns-records-required-for-the-director"></a><span data-ttu-id="b83d2-108">디렉터에 필요한 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="b83d2-108">DNS Records Required for the Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b83d2-109">Location/TYPE/Port</span><span class="sxs-lookup"><span data-stu-id="b83d2-109">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="b83d2-110">FQDN/DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="b83d2-110">FQDN/DNS Record</span></span></th>
<th><span data-ttu-id="b83d2-111">IP 주소/FQDN</span><span class="sxs-lookup"><span data-stu-id="b83d2-111">IP Address/FQDN</span></span></th>
<th><span data-ttu-id="b83d2-112">매핑 대상/설명</span><span class="sxs-lookup"><span data-stu-id="b83d2-112">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b83d2-113">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="b83d2-113">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b83d2-114">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="b83d2-114">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="b83d2-115">영화</span><span class="sxs-lookup"><span data-stu-id="b83d2-115">Director</span></span></p></td>
<td><p><span data-ttu-id="b83d2-116">복제 및 서버 간 서버에 사용 되는 디렉터 호스트 레코드</span><span class="sxs-lookup"><span data-stu-id="b83d2-116">Director host record used for replication and server to server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b83d2-117">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="b83d2-117">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b83d2-118">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b83d2-118">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b83d2-119">영화</span><span class="sxs-lookup"><span data-stu-id="b83d2-119">Director</span></span></p></td>
<td><p><span data-ttu-id="b83d2-120">에 지 서버의 내부에 지 인터페이스에서 인바운드 SIP (세션 시작 프로토콜)</span><span class="sxs-lookup"><span data-stu-id="b83d2-120">Inbound session initiation protocol (SIP) from the internal Edge interface of the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b83d2-121">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="b83d2-121">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b83d2-122">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b83d2-122">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b83d2-123">영화</span><span class="sxs-lookup"><span data-stu-id="b83d2-123">Director</span></span></p></td>
<td><p><span data-ttu-id="b83d2-124">역방향 프록시에서 게시된 전화 접속 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="b83d2-124">Published dialin web services from reverse proxy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b83d2-125">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="b83d2-125">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b83d2-126">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b83d2-126">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b83d2-127">영화</span><span class="sxs-lookup"><span data-stu-id="b83d2-127">Director</span></span></p></td>
<td><p><span data-ttu-id="b83d2-128">역방향 프록시에서 게시된 모임 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="b83d2-128">Published meet web services from reverse proxy</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b83d2-129">내부 DNS/A</span><span class="sxs-lookup"><span data-stu-id="b83d2-129">Internal DNS/A</span></span></p></td>
<td><p><span data-ttu-id="b83d2-130">webdirexternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b83d2-130">webdirexternal.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="b83d2-131">영화</span><span class="sxs-lookup"><span data-stu-id="b83d2-131">Director</span></span></p></td>
<td><p><span data-ttu-id="b83d2-132">디렉터에 대 한 역방향 프록시 웹 티켓 외부 웹 서비스에서 게시 및 정의 됨</span><span class="sxs-lookup"><span data-stu-id="b83d2-132">Published and defined by the reverse proxy Web Ticket external web services for the Director</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

