---
title: 'Lync Server 2013: 인증서 요약 - 역방향 프록시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a10259ac4a0beb6d79897b26bf446b109801a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="83c81-102">Lync Server 2013의 인증서 요약 - 역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="83c81-102">Certificate summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83c81-103">_**마지막으로 수정한 주제:** 2012-11-14_</span><span class="sxs-lookup"><span data-stu-id="83c81-103">_**Topic Last Modified:** 2012-11-14_</span></span>

<span data-ttu-id="83c81-104">역방향 프록시에 대 한 인증서 요구 사항은 Edge 서버의 경우 보다 훨씬 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c81-104">Certificate requirements for the reverse proxy are much simpler than that for the Edge Servers.</span></span> <span data-ttu-id="83c81-105">제공 된 순서도에는 필요한 요구 사항이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83c81-105">The provided flowchart presents the requirements necessary.</span></span> <span data-ttu-id="83c81-106">함께 제공 되는 표에는 Edge 서버 토론에서 검토 한 시나리오와 관련 하 여 일반적인 인증서 주체 이름 및 제목 대체 이름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83c81-106">The accompanying table presents typical certificate subject name and subject alternative names in relation to the scenarios that we have been reviewed in the Edge Server discussions.</span></span> <span data-ttu-id="83c81-107">Edge 서버 시나리오에 대 한 자세한 내용은 [Lync server 2013에서 외부 사용자 액세스 시나리오](lync-server-2013-scenarios-for-external-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83c81-107">For more details on the Edge Server scenarios, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="83c81-108">**역방향 프록시에 대 한 인증서 흐름 차트**</span><span class="sxs-lookup"><span data-stu-id="83c81-108">**Certificates Flow Chart for Reverse Proxy**</span></span>

<span data-ttu-id="83c81-109">Edge 서버에 대 한 Edge 서버(images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "인증서 흐름") 차트 ![의 인증서 흐름 차트]</span><span class="sxs-lookup"><span data-stu-id="83c81-109">![Certificates Flow Chart for Edge Server](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Certificates Flow Chart for Edge Server")</span></span>

### <a name="reverse-proxy-external-interface"></a><span data-ttu-id="83c81-110">리버스 프록시: 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="83c81-110">Reverse Proxy: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83c81-111">요소가</span><span class="sxs-lookup"><span data-stu-id="83c81-111">Component</span></span></th>
<th><span data-ttu-id="83c81-112">주체 이름</span><span class="sxs-lookup"><span data-stu-id="83c81-112">Subject name</span></span></th>
<th><span data-ttu-id="83c81-113">SAN (주체 대체 이름)/Order</span><span class="sxs-lookup"><span data-stu-id="83c81-113">Subject alternative name (SAN)/Order</span></span></th>
<th><span data-ttu-id="83c81-114">메모</span><span class="sxs-lookup"><span data-stu-id="83c81-114">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83c81-115">역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="83c81-115">Reverse Proxy</span></span></p></td>
<td><p><span data-ttu-id="83c81-116">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83c81-116">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83c81-117">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83c81-117">webext.contoso.com</span></span></p>
<p><span data-ttu-id="83c81-118">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83c81-118">webdirext.contoso.com</span></span></p>
<p><span data-ttu-id="83c81-119">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83c81-119">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="83c81-120">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83c81-120">meet.contoso.com</span></span></p>
<p><span data-ttu-id="83c81-121">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83c81-121">officewebapps01.contoso.com</span></span></p>
<p><span data-ttu-id="83c81-122">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83c81-122">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="83c81-123">(선택 사항):\* contoso.com</span><span class="sxs-lookup"><span data-stu-id="83c81-123">(Optional):\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="83c81-124">인증서는 공용 CA 및 서버 EKU를 사용 하 여 발급 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c81-124">Certificate must be issued by a public CA and with the server EKU.</span></span> <span data-ttu-id="83c81-125">서비스에는 주소록 서비스, 회의를 위한 메일 그룹 확장 Office Web Apps, Lync IP 장치 게시 규칙이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83c81-125">Services include Address Book Service, distribution group expansion Office Web Apps for conferencing, and Lync IP Device publishing rules.</span></span> <span data-ttu-id="83c81-126">주체 대체 이름에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83c81-126">Subject alternative name includes:</span></span></p>
<ul>
<li><p><span data-ttu-id="83c81-127">프런트 엔드 서버 또는 프런트 엔드 풀의 외부 웹 서비스 FQDN</span><span class="sxs-lookup"><span data-stu-id="83c81-127">External Web Services FQDN for Front End Server or Front End pool</span></span></p></li>
<li><p><span data-ttu-id="83c81-128">디렉터 또는 디렉터 풀에 대 한 외부 웹 서비스 FQDN</span><span class="sxs-lookup"><span data-stu-id="83c81-128">External Web Services FQDN for Director or Director pool</span></span></p></li>
<li><p><span data-ttu-id="83c81-129">전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="83c81-129">Dial-in conferencing</span></span></p></li>
<li><p><span data-ttu-id="83c81-130">온라인 모임 게시 규칙</span><span class="sxs-lookup"><span data-stu-id="83c81-130">Online meeting publishing rule</span></span></p></li>
<li><p><span data-ttu-id="83c81-131">회의를 위한 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="83c81-131">Office Web Apps for conferencing</span></span></p></li>
<li><p><span data-ttu-id="83c81-132">Lyncdiscover (자동 검색)</span><span class="sxs-lookup"><span data-stu-id="83c81-132">Lyncdiscover (Autodiscover)</span></span></p></li>
</ul>
<p><span data-ttu-id="83c81-133">선택적 와일드 카드는 모임 시작 및 전화 접속 SAN을 모두 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="83c81-133">The optional wildcard replaces both meet and dialin SAN</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

