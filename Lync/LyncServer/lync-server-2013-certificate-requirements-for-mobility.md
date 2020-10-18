---
title: 'Lync Server 2013: 모바일 기능에 대 한 인증서 요구 사항'
description: 'Lync Server 2013: 모바일 기능에 대 한 인증서 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51af74b3efc1ffcb4fe38d7431e315f9b55af943
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575204"
---
# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="b9e17-103">Lync Server 2013의 모바일 기능에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9e17-103">Certificate requirements for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9e17-104">_**마지막으로 수정 된 항목:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="b9e17-104">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="b9e17-105">모바일 기능을 배포하고 모바일 클라이언트에 대해 자동 검색을 지원하는 경우에는 모바일 클라이언트로부터의 보안 연결을 지원하기 위해 인증서에 특정 주체 대체 이름 항목을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e17-105">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="b9e17-106">자동 검색용 주체 대체 이름 항목을 포함해야 하는 인증서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e17-106">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="b9e17-107">디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="b9e17-107">Director pool</span></span>

  - <span data-ttu-id="b9e17-108">프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="b9e17-108">Front End pool</span></span>

  - <span data-ttu-id="b9e17-109">역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="b9e17-109">Reverse proxy</span></span>

<span data-ttu-id="b9e17-110">이 섹션에서는 자동 검색을 위해 인증서에 필요한 주체 대체 이름 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e17-110">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b9e17-111">내부 인증 기관을 통해 인증서를 다시 발급하는 과정은 일반적으로는 간단하지만, 역방향 프록시에서 사용되는 공용 인증서에 여러 주체 대체 이름 항목을 추가하려면 비용이 많이 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e17-111">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="b9e17-112">SIP 도메인이 여러 개인 경우 주체 대체 이름 추가 비용이 매우 크므로, 초기 자동 검색 서비스 요청에 대해 HTTPS(기본 구성) 대신 HTTP를 사용하도록 역방향 프록시를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e17-112">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="b9e17-113">자세한 내용은 <A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013에서 모바일 기능에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9e17-113">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="b9e17-114">디렉터 풀 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9e17-114">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9e17-115">설명</span><span class="sxs-lookup"><span data-stu-id="b9e17-115">Description</span></span></th>
<th><span data-ttu-id="b9e17-116">주체 대체 이름 항목</span><span class="sxs-lookup"><span data-stu-id="b9e17-116">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9e17-117">내부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="b9e17-117">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b9e17-118">SAN = lyncdiscoverinternal. &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="b9e17-118">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e17-119">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="b9e17-119">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b9e17-120">SAN = lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="b9e17-120">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b9e17-121">또는 SAN = \*를 사용할 수 있습니다. &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="b9e17-121">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="b9e17-122">프런트 엔드 풀 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9e17-122">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9e17-123">설명</span><span class="sxs-lookup"><span data-stu-id="b9e17-123">Description</span></span></th>
<th><span data-ttu-id="b9e17-124">주체 대체 이름 항목</span><span class="sxs-lookup"><span data-stu-id="b9e17-124">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9e17-125">내부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="b9e17-125">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b9e17-126">SAN = lyncdiscoverinternal. &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="b9e17-126">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9e17-127">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="b9e17-127">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b9e17-128">SAN = lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="b9e17-128">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b9e17-129">또는 SAN = \*를 사용할 수 있습니다. &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="b9e17-129">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="b9e17-130">역방향 프록시(공용 CA) 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9e17-130">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9e17-131">설명</span><span class="sxs-lookup"><span data-stu-id="b9e17-131">Description</span></span></th>
<th><span data-ttu-id="b9e17-132">주체 대체 이름 항목</span><span class="sxs-lookup"><span data-stu-id="b9e17-132">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9e17-133">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="b9e17-133">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b9e17-134">SAN = lyncdiscover &lt; microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="b9e17-134">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b9e17-135">역방향 프록시의 SSL 수신기에 할당된 인증서에 이 SAN을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e17-135">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b9e17-136">역방향 프록시 수신기에는 외부 웹 서비스 URL에 대 한 주체 대체 이름 (예: SAN = lyncwebextpool01.contoso.com, 그리고 선택적 디렉터를 배포한 경우 dirwebexternal.contoso.com)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e17-136">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

