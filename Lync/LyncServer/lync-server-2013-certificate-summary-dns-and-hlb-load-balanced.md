---
title: 'Lync Server 2013: 인증서 요약 - DNS 및 HLB 부하 분산됨'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - DNS and HLB load balanced
ms:assetid: 8318a1a4-b423-47b7-95e6-9541adfad391
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205047(v=OCS.15)
ms:contentKeyID: 48184676
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e145e2f1ac3d331906713584b365adf7cd48aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---dns-and-hlb-load-balanced-in-lync-server-2013"></a><span data-ttu-id="23663-102">인증서 요약 - Lync Server 2013에서 DNS 및 HLB 부하 분산됨</span><span class="sxs-lookup"><span data-stu-id="23663-102">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23663-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="23663-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="23663-104">DNS 부하 분산이 있는 디렉터에 대 한 인증서 요구 사항과 하드웨어 로드 균형 조정기는 디렉터에서 수신할 수 있는 서비스에 대 한 주체 이름 및 주체 대체 이름이 있는 기본 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23663-104">Certificate requirements for a Director with DNS load balancing and a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="23663-105">풀의 각 디렉터에 대 한 인증서가 요청 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23663-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="23663-106">하드웨어 로드 균형 조정기는 역방향 프록시의 트래픽에만 로드 균형을 조정 한다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23663-106">It is important to remember that the hardware load balancer is load balancing only the traffic from the reverse proxy.</span></span> <span data-ttu-id="23663-107">또한 각 서버에 설치 된 서버 대 서버 인증 용도의 OAuth 토큰 인증서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23663-107">Additionally, there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="23663-108">디렉터에 대 한 인증서</span><span class="sxs-lookup"><span data-stu-id="23663-108">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23663-109">요소가</span><span class="sxs-lookup"><span data-stu-id="23663-109">Component</span></span></th>
<th><span data-ttu-id="23663-110">주체 이름 (SN)</span><span class="sxs-lookup"><span data-stu-id="23663-110">Subject name (SN)</span></span></th>
<th><span data-ttu-id="23663-111">주제 대체 이름 (SAN)</span><span class="sxs-lookup"><span data-stu-id="23663-111">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="23663-112">메모</span><span class="sxs-lookup"><span data-stu-id="23663-112">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23663-113">기본값</span><span class="sxs-lookup"><span data-stu-id="23663-113">Default</span></span></p></td>
<td><p><span data-ttu-id="23663-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="23663-114">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="23663-115">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="23663-115">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="23663-116">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="23663-116">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="23663-117">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23663-117">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="23663-118">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23663-118">meet.contoso.com</span></span></p>
<p><span data-ttu-id="23663-119">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23663-119">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="23663-120">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="23663-120">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="23663-121">(선택적) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="23663-121">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="23663-122">디렉터 인증서는 내부에서 관리 하는 CA (인증 기관) 또는 공용 CA에서 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23663-122">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="23663-123">디렉터는 주변 서버나 Edge 서버의 역방향 프록시 요청에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="23663-123">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="23663-124">내부 클라이언트는 디렉터를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23663-124">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="23663-125">또는 간단한 Url의 와일드 카드 항목</span><span class="sxs-lookup"><span data-stu-id="23663-125">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23663-126">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="23663-126">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="23663-127">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="23663-127">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="23663-128">입력 내용 없음</span><span class="sxs-lookup"><span data-stu-id="23663-128">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="23663-129">최소 키 길이는 1024 이지만 최소 권장 키 길이는 2048 비트 라고 알리는 경고가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23663-129">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="23663-130">OAuthTokenIssuer 인증서는 대규모 환경에서 서버를 인증 하기 위한 용도로만 사용할 수 있는 단일 용도의 인증서 이며, 내부 CA 또는 공용 CA에서 요청을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23663-130">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="23663-131">인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="23663-131">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

