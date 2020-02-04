---
title: 'Lync Server 2013: 인증서 요약 - 단일 디렉터'
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
ms.openlocfilehash: f18fcec270104be1620402ddee0c665c0f3f3a4f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---single-director-in-lync-server-2013"></a><span data-ttu-id="9114a-102">Lync Server 2013의 인증서 요약 - 단일 디렉터</span><span class="sxs-lookup"><span data-stu-id="9114a-102">Certificate summary - Single Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9114a-103">_**마지막으로 수정한 주제:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="9114a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="9114a-104">단일 디렉터에 대 한 인증서 요구 사항은 해당 디렉터에서 받을 수 있는 서비스에 대 한 주체 이름과 주체의 대체 이름을 가진 기본 인증서로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9114a-104">Certificate requirements for a single Director consist of a default certificate that has a subject name and subject alternative names for services that the Director can receive.</span></span> <span data-ttu-id="9114a-105">또한 서버 대 서버 인증 용도로 사용할 수 있는 OAuth 토큰 인증서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9114a-105">Additionally, there is an OAuth Token certificate for server to server authentication purposes.</span></span>

### <a name="certificates-for-director"></a><span data-ttu-id="9114a-106">디렉터에 대 한 인증서</span><span class="sxs-lookup"><span data-stu-id="9114a-106">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9114a-107">요소가</span><span class="sxs-lookup"><span data-stu-id="9114a-107">Component</span></span></th>
<th><span data-ttu-id="9114a-108">주체 이름 (SN)</span><span class="sxs-lookup"><span data-stu-id="9114a-108">Subject name (SN)</span></span></th>
<th><span data-ttu-id="9114a-109">주제 대체 이름 (SAN)</span><span class="sxs-lookup"><span data-stu-id="9114a-109">Subject alternative names (SAN)</span></span></th>
<th><span data-ttu-id="9114a-110">메모</span><span class="sxs-lookup"><span data-stu-id="9114a-110">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9114a-111">기본값</span><span class="sxs-lookup"><span data-stu-id="9114a-111">Default</span></span></p></td>
<td><p><span data-ttu-id="9114a-112">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9114a-112">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="9114a-113">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9114a-113">dir01.contoso.net</span></span></p>
<p><span data-ttu-id="9114a-114">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9114a-114">dialin.contoso.com</span></span></p>
<p><span data-ttu-id="9114a-115">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9114a-115">meet.contoso.com</span></span></p>
<p><span data-ttu-id="9114a-116">lyncdiscoverinternal.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9114a-116">lyncdiscoverinternal.contoso.com</span></span></p>
<p><span data-ttu-id="9114a-117">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9114a-117">lyncdiscover.contoso.com</span></span></p>
<p><span data-ttu-id="9114a-118">(선택적) \*. contoso.com</span><span class="sxs-lookup"><span data-stu-id="9114a-118">(Optionally) \*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="9114a-119">디렉터 인증서는 내부에서 관리 하는 CA (인증 기관) 또는 공용 CA에서 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9114a-119">Director certificates can be requested from either an internally managed certification authority (CA) or from a public CA.</span></span></p>
<p><span data-ttu-id="9114a-120">디렉터는 주변 서버나 Edge 서버의 역방향 프록시 요청에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="9114a-120">The Director responds to requests from the reverse proxy in the perimeter or from the Edge Server.</span></span> <span data-ttu-id="9114a-121">내부 클라이언트는 디렉터를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9114a-121">Internal clients will not use the Director.</span></span></p>
<p><span data-ttu-id="9114a-122">또는 간단한 Url의 와일드 카드 항목</span><span class="sxs-lookup"><span data-stu-id="9114a-122">Or, a wildcard entry for the simple URLs</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9114a-123">OAuthTokenIssuer</span><span class="sxs-lookup"><span data-stu-id="9114a-123">OAuthTokenIssuer</span></span></p></td>
<td><p><span data-ttu-id="9114a-124">dir01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="9114a-124">dir01.contoso.net</span></span></p></td>
<td><p><span data-ttu-id="9114a-125">입력 내용 없음</span><span class="sxs-lookup"><span data-stu-id="9114a-125">No Entry</span></span></p></td>
<td><div>

> [!IMPORTANT]  
> <span data-ttu-id="9114a-126">최소 키 길이는 1024 이지만 최소 권장 키 길이는 2048 비트 라고 알리는 경고가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9114a-126">Note that the minimum key length is 1024, but you may receive a warning that the minimum recommended key length is 2048 bits.</span></span>


</div>
<p><span data-ttu-id="9114a-127">OAuthTokenIssuer 인증서는 대규모 환경에서 서버를 인증 하기 위한 용도로만 사용할 수 있는 단일 용도의 인증서 이며, 내부 CA 또는 공용 CA에서 요청을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9114a-127">The OAuthTokenIssuer certificate is a single-purpose certificate for the purpose of authenticating servers in a large-scale environment, and can be requested from an internal CA or from a public CA.</span></span> <span data-ttu-id="9114a-128">인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9114a-128">The certificate is required.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

