---
title: 인증서 요약 - 조정된 디렉터 풀, 하드웨어 부하 분산 장치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Scaled Director pool, hardware load balancer
ms:assetid: 45940add-8027-418d-b79a-9033b494762f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204846(v=OCS.15)
ms:contentKeyID: 48183992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21b1688641d09e00c82ea952d57bd2a9547ac0dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---scaled-director-pool-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="d2c34-102">Lync Server 2013의 인증서 요약 - 조정된 디렉터 풀, 하드웨어 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="d2c34-102">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2c34-103">_**마지막으로 수정한 주제:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d2c34-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d2c34-104">하드웨어 로드 균형 조정기를 사용 하는 디렉터에 대 한 인증서 요구 사항은 디렉터 풀이 받을 수 있는 서비스에 대 한 주체 이름 및 주체 대체 이름이 있는 기본 인증서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c34-104">Certificate requirements for a Director with a hardware load balancer will use a default certificate that has a subject name and subject alternative names for services that the Director pool can receive.</span></span> <span data-ttu-id="d2c34-105">풀의 각 디렉터에 대 한 인증서가 요청 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2c34-105">A certificate is requested for each Director in the pool.</span></span> <span data-ttu-id="d2c34-106">또한 각 서버에 설치 된 서버 대 서버 인증 용도의 OAuth 토큰 인증서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c34-106">Additionally there is an OAuth Token certificate for server to server authentication purposes that is installed on each server.</span></span>

### <a name="certificates-for-a-scaled-director-using-a-hardware-load-balancer"></a><span data-ttu-id="d2c34-107">하드웨어 부하 분산 장치를 사용 하 여 확장 된 디렉터에 대 한 인증서</span><span class="sxs-lookup"><span data-stu-id="d2c34-107">Certificates for a Scaled Director Using a Hardware Load Balancer</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2c34-108">요소가</span><span class="sxs-lookup"><span data-stu-id="d2c34-108">Component</span></span></th>
<th><span data-ttu-id="d2c34-109">주체 이름 (SN)</span><span class="sxs-lookup"><span data-stu-id="d2c34-109">Subject name (SN)</span></span></th>
<th><span data-ttu-id="d2c34-110">주제 대체 이름 (SAN)</span><span class="sxs-lookup"><span data-stu-id="d2c34-110">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="d2c34-111">메모</span><span class="sxs-lookup"><span data-stu-id="d2c34-111">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2c34-112">기본값</span><span class="sxs-lookup"><span data-stu-id="d2c34-112">Default</span></span></p></td>
<td><p><span data-ttu-id="d2c34-113">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d2c34-113">dirpool01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d2c34-114">dirpool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d2c34-114">dirpool01.contoso.net</span></span></p>
<p><span data-ttu-id="d2c34-115">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d2c34-115">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="d2c34-116">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d2c34-116">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="d2c34-117">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d2c34-117">meet.contoso.com</span></span></p>
<p><span data-ttu-id="d2c34-118">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d2c34-118">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="d2c34-119">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d2c34-119">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="d2c34-120">(선택적) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="d2c34-120">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="d2c34-121">디렉터 인증서는 내부에서 관리 하는 CA (인증 기관) 또는 공용 CA에서 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c34-121">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="d2c34-122">디렉터는 주변 서버나 Edge 서버의 역방향 프록시 요청에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c34-122">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span></p>
<p><span data-ttu-id="d2c34-123">또는 간단한 Url의 와일드 카드 항목</span><span class="sxs-lookup"><span data-stu-id="d2c34-123">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2c34-124">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="d2c34-124">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="d2c34-125">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="d2c34-125">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="d2c34-126">입력 내용 없음</span><span class="sxs-lookup"><span data-stu-id="d2c34-126">No Entry</span></span></p></td>
<td>


> [!IMPORTANT]
> <span data-ttu-id="d2c34-127">최소 키 길이는 1024 이지만 최소 권장 키 길이는 2048 비트 라고 알리는 경고가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2c34-127">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


<p><span data-ttu-id="d2c34-128">OAuthTokenIssuer 인증서는 대규모 환경에서 서버를 인증 하기 위한 용도로만 사용할 수 있는 단일 용도의 인증서 이며, 내부 CA 또는 공용 CA에서 요청을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c34-128">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="d2c34-129">인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2c34-129">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

