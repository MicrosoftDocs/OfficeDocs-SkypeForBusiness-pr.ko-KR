---
title: 'Lync Server 2013: 인증서 요약-DNS 및 HLB 부하 분산 됨'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e915a8b9d7e339453c687d269ed10bc744ab761b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="2cf50-102">인증서 요약-Lync Server 2013에서 DNS 및 HLB 부하 분산</span><span class="sxs-lookup"><span data-stu-id="2cf50-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cf50-103">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2cf50-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2cf50-104">DNS 부하 분산 및 하드웨어 부하 분산 장치에 대 한 인증서 요구 사항은 디렉터가 수신할 수 있는 서비스에 대 한 주체 이름 및 주체 대체 이름이 있는 기본 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf50-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="2cf50-105">풀의 각 디렉터에 대해 인증서가 요청 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cf50-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="2cf50-106">하드웨어 부하 분산 장치는 역방향 프록시의 트래픽만 부하를 분산합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf50-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="2cf50-107">또한 서버 인증 목적을 위해 각 서버에 설치된 서버 OAuth Token 인증서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf50-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="2cf50-108">디렉터용 인증서</span><span class="sxs-lookup"><span data-stu-id="2cf50-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cf50-109">구성 요소</span><span class="sxs-lookup"><span data-stu-id="2cf50-109">Component</span></span></th>
<th><span data-ttu-id="2cf50-110">SN(주체 이름)</span><span class="sxs-lookup"><span data-stu-id="2cf50-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="2cf50-111">SAN(주체 대체 이름)</span><span class="sxs-lookup"><span data-stu-id="2cf50-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="2cf50-112">설명</span><span class="sxs-lookup"><span data-stu-id="2cf50-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cf50-113">기본</span><span class="sxs-lookup"><span data-stu-id="2cf50-113">Default</span></span></p></td>
<td><p><span data-ttu-id="2cf50-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2cf50-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2cf50-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2cf50-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="2cf50-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2cf50-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="2cf50-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cf50-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="2cf50-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cf50-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="2cf50-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cf50-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="2cf50-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cf50-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="2cf50-121">(Optionally) \*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2cf50-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2cf50-122">디렉터 인증서는 내부적으로 관리 되는 CA (인증 기관) 또는 공용 CA에서 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf50-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="2cf50-123">디렉터는 경계에 있는 역방향 프록시 또는에 지 서버의 요청에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cf50-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="2cf50-124">내부 클라이언트에서 디렉터를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf50-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="2cf50-125">또는 단순 URL에 대한 와일드카드 항목</span><span class="sxs-lookup"><span data-stu-id="2cf50-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cf50-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="2cf50-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="2cf50-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="2cf50-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="2cf50-128">항목 없음</span><span class="sxs-lookup"><span data-stu-id="2cf50-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="2cf50-129">최소 키 길이는 1024이지만 최소 권장 키 길이가 2048비트라는 경고가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cf50-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="2cf50-p103">OAuthTokenIssuer 인증서는 대규모 환경에서 서버 인증 목적을 위한 단일 목적 인증서이며 내부 CA 또는 공용 CA에서 요청될 수 있습니다. 이 인증서는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="2cf50-p103">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA. The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

