---
title: 'Lync Server 2013: 인증서 요약-단일 디렉터'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single Director
ms:assetid: 1b769a76-cbf3-46e9-a955-f6cde5faff93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204720(v=OCS.15)
ms:contentKeyID: 48183546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 677f9cf6e7cc9d260846598023435f33d2ebd2fc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="ca9d9-102">인증서 요약-Lync Server 2013의 단일 디렉터</span><span class="sxs-lookup"><span data-stu-id="ca9d9-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca9d9-103">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ca9d9-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ca9d9-104">단일 디렉터에 대 한 인증서 요구 사항은 디렉터가 수신할 수 있는 서비스에 대 한 주체 이름 및 주체 대체 이름이 있는 기본 인증서로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca9d9-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="ca9d9-105">또한 서버 간 인증용 OAuth 토큰 인증서도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca9d9-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="ca9d9-106">디렉터용 인증서</span><span class="sxs-lookup"><span data-stu-id="ca9d9-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca9d9-107">구성 요소</span><span class="sxs-lookup"><span data-stu-id="ca9d9-107">Component</span></span></th>
<th><span data-ttu-id="ca9d9-108">SN(주체 이름)</span><span class="sxs-lookup"><span data-stu-id="ca9d9-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="ca9d9-109">SAN(주체 대체 이름)</span><span class="sxs-lookup"><span data-stu-id="ca9d9-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="ca9d9-110">설명</span><span class="sxs-lookup"><span data-stu-id="ca9d9-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca9d9-111">기본</span><span class="sxs-lookup"><span data-stu-id="ca9d9-111">Default</span></span></p></td>
<td><p><span data-ttu-id="ca9d9-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ca9d9-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ca9d9-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ca9d9-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="ca9d9-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca9d9-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="ca9d9-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca9d9-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="ca9d9-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca9d9-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="ca9d9-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca9d9-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="ca9d9-118">(Optionally) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca9d9-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ca9d9-119">디렉터 인증서는 내부적으로 관리 되는 CA (인증 기관) 또는 공용 CA에서 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca9d9-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="ca9d9-120">디렉터는 경계에 있는 역방향 프록시 또는에 지 서버의 요청에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca9d9-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="ca9d9-121">내부 클라이언트에서 디렉터를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca9d9-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="ca9d9-122">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="ca9d9-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca9d9-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="ca9d9-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="ca9d9-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="ca9d9-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="ca9d9-125">항목 없음</span><span class="sxs-lookup"><span data-stu-id="ca9d9-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="ca9d9-126">최소 키 길이는 1024이지만 최소 권장 키 길이가 2048비트라는 경고가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca9d9-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="ca9d9-p103">OAuthTokenIssuer 인증서는 대규모 환경에서 서버 인증 목적을 위한 단일 목적 인증서이며 내부 CA 또는 공용 CA에서 요청될 수 있습니다. 이 인증서는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="ca9d9-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

