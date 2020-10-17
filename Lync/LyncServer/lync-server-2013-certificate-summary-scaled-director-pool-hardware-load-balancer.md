---
title: 인증서 요약-확장 된 디렉터 풀, 하드웨어 부하 분산 장치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c08fb5710e25bf4504d7cb2d10020138221b22c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507925"
---
# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="002bf-102">Lync Server 2013의 인증서 요약-확장 된 디렉터 풀, 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="002bf-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="002bf-103">_**마지막으로 수정 된 항목:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="002bf-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="002bf-104">하드웨어 부하 분산 장치를 사용 하는 디렉터에 대 한 인증서 요구 사항에서는 디렉터 풀이 수신할 수 있는 서비스의 주체 이름 및 주체 대체 이름이 있는 기본 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="002bf-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="002bf-105">풀의 각 디렉터에 대해 인증서가 요청 됩니다.</span><span class="sxs-lookup"><span data-stu-id="002bf-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="002bf-106">또한 서버 인증 목적을 위해 각 서버에 설치된 서버 OAuth Token 인증서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002bf-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="002bf-107">하드웨어 부하 분산 장치를 사용하여 확장된 디렉터의 인증서</span><span class="sxs-lookup"><span data-stu-id="002bf-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="002bf-108">구성 요소</span><span class="sxs-lookup"><span data-stu-id="002bf-108">Component</span></span></th>
<th><span data-ttu-id="002bf-109">SN(주체 이름)</span><span class="sxs-lookup"><span data-stu-id="002bf-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="002bf-110">SAN(주체 대체 이름)</span><span class="sxs-lookup"><span data-stu-id="002bf-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="002bf-111">설명</span><span class="sxs-lookup"><span data-stu-id="002bf-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="002bf-112">기본</span><span class="sxs-lookup"><span data-stu-id="002bf-112">Default</span></span></p></td>
<td><p><span data-ttu-id="002bf-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="002bf-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="002bf-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="002bf-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="002bf-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="002bf-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="002bf-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="002bf-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="002bf-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="002bf-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="002bf-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="002bf-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="002bf-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="002bf-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="002bf-120">(Optionally) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="002bf-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="002bf-121">디렉터 인증서는 내부적으로 관리 되는 CA (인증 기관) 또는 공용 CA에서 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002bf-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="002bf-122">디렉터는 경계에 있는 역방향 프록시 또는에 지 서버의 요청에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="002bf-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="002bf-123">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="002bf-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="002bf-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="002bf-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="002bf-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="002bf-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="002bf-126">항목 없음</span><span class="sxs-lookup"><span data-stu-id="002bf-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="002bf-127">최소 키 길이는 1024이지만 최소 권장 키 길이가 2048비트라는 경고가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002bf-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="002bf-p102">OAuthTokenIssuer 인증서는 대규모 환경에서 서버 인증 목적을 위한 단일 목적 인증서이며 내부 CA 또는 공용 CA에서 요청될 수 있습니다. 이 인증서는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="002bf-p102">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

