---
title: 'Lync Server 2013: 모바일 기능에 대 한 인증서 요구 사항'
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
ms.openlocfilehash: bbf7dd0f3ce9868fbeac5c757fce5371ad77fba4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="57355-102">Lync Server 2013의 모바일 기능에 대 한 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="57355-102">Certificate requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57355-103">_**마지막으로 수정 된 항목:** 2012-06-24_</span><span class="sxs-lookup"><span data-stu-id="57355-103">_**Topic Last Modified:** 2012-06-24_</span></span>

<span data-ttu-id="57355-104">모바일 기능을 배포하고 모바일 클라이언트에 대해 자동 검색을 지원하는 경우에는 모바일 클라이언트로부터의 보안 연결을 지원하기 위해 인증서에 특정 주체 대체 이름 항목을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57355-104">If you deploy the mobility feature and support automatic discovery for mobile clients, you need to include certain subject alternative name entries on certificates to support secure connections from the mobile clients.</span></span>

<span data-ttu-id="57355-105">자동 검색용 주체 대체 이름 항목을 포함해야 하는 인증서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57355-105">You need to include subject alternative name entries for automatic discovery on the following certificates:</span></span>

  - <span data-ttu-id="57355-106">디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="57355-106">Director pool</span></span>

  - <span data-ttu-id="57355-107">프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="57355-107">Front End pool</span></span>

  - <span data-ttu-id="57355-108">역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="57355-108">Reverse proxy</span></span>

<span data-ttu-id="57355-109">이 섹션에서는 자동 검색을 위해 인증서에 필요한 주체 대체 이름 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="57355-109">This section describes the subject alternative name entries that are required on your certificates for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57355-110">내부 인증 기관을 통해 인증서를 다시 발급하는 과정은 일반적으로는 간단하지만, 역방향 프록시에서 사용되는 공용 인증서에 여러 주체 대체 이름 항목을 추가하려면 비용이 많이 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57355-110">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="57355-111">SIP 도메인이 여러 개인 경우 주체 대체 이름 추가 비용이 매우 크므로, 초기 자동 검색 서비스 요청에 대해 HTTPS(기본 구성) 대신 HTTP를 사용하도록 역방향 프록시를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57355-111">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to use HTTP for the initial Autodiscover Service request, instead of using HTTPS (the default configuration).</span></span> <span data-ttu-id="57355-112">자세한 내용은 <A href="lync-server-2013-technical-requirements-for-mobility.md">Lync Server 2013에서 모바일 기능에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57355-112">For details, see <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical requirements for mobility in Lync Server 2013</A>.</span></span>



</div>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="57355-113">디렉터 풀 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="57355-113">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57355-114">설명</span><span class="sxs-lookup"><span data-stu-id="57355-114">Description</span></span></th>
<th><span data-ttu-id="57355-115">주체 대체 이름 항목</span><span class="sxs-lookup"><span data-stu-id="57355-115">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57355-116">내부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="57355-116">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="57355-117">SAN = lyncdiscoverinternal. &lt;microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="57355-117">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57355-118">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="57355-118">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="57355-119">SAN = lyncdiscover &lt;microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="57355-119">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="57355-120">또는 SAN = \*를 사용할 수 있습니다. &lt;microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="57355-120">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="57355-121">프런트 엔드 풀 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="57355-121">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57355-122">설명</span><span class="sxs-lookup"><span data-stu-id="57355-122">Description</span></span></th>
<th><span data-ttu-id="57355-123">주체 대체 이름 항목</span><span class="sxs-lookup"><span data-stu-id="57355-123">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57355-124">내부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="57355-124">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="57355-125">SAN = lyncdiscoverinternal. &lt;microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="57355-125">SAN=lyncdiscoverinternal.&lt;sipdomain&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57355-126">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="57355-126">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="57355-127">SAN = lyncdiscover &lt;microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="57355-127">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="57355-128">또는 SAN = \*를 사용할 수 있습니다. &lt;microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="57355-128">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="57355-129">역방향 프록시(공용 CA) 인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="57355-129">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57355-130">설명</span><span class="sxs-lookup"><span data-stu-id="57355-130">Description</span></span></th>
<th><span data-ttu-id="57355-131">주체 대체 이름 항목</span><span class="sxs-lookup"><span data-stu-id="57355-131">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57355-132">외부 자동 검색 서비스 URL</span><span class="sxs-lookup"><span data-stu-id="57355-132">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="57355-133">SAN = lyncdiscover &lt;microsoft.rtc.management.xds.sipdomain object&gt;</span><span class="sxs-lookup"><span data-stu-id="57355-133">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="57355-134">역방향 프록시의 SSL 수신기에 할당된 인증서에 이 SAN을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="57355-134">You assign this SAN to the certificate assigned to the SSL Listener on the reverse proxy.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="57355-135">역방향 프록시 수신기에는 외부 웹 서비스 URL에 대 한 주체 대체 이름 (예: SAN = lyncwebextpool01.contoso.com, 그리고 선택적 디렉터를 배포한 경우 dirwebexternal.contoso.com)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57355-135">Your reverse proxy listener will have subject alternative names for your external Web Services URL(s) (for example, SAN=lyncwebextpool01.contoso.com, and dirwebexternal.contoso.com if you have deployed the optional Director).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

