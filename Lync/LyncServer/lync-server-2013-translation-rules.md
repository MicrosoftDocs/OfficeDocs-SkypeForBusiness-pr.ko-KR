---
title: 'Lync Server 2013: 변환 규칙'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 783d2bb8de49fc7660998fcf3cbcb7cdb5c18e8b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530355"
---
# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="4c70f-102">Lync Server 2013의 변환 규칙</span><span class="sxs-lookup"><span data-stu-id="4c70f-102">Translation rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c70f-103">_**마지막으로 수정 된 항목:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="4c70f-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="4c70f-104">Lync Server 2013 Enterprise Voice를 사용 하려면 RNL (역방향 번호 조회)를 수행할 목적으로 모든 다이얼 문자열을 E. 164 형식으로 정규화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c70f-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="4c70f-105">Microsoft Lync Server 2010에서 변환 규칙은 호출 된 번호에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c70f-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="4c70f-106">Microsoft Lync Server 2013의 새로운 기능은 통화 번호에 대해서도 변환 규칙을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c70f-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="4c70f-107">*트렁크 피어* (연결 된 게이트웨이, PBX (private branch exchange) 또는 SIP 트렁크)가 해당 번호를 로컬 전화 걸기 형식으로 지정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c70f-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="4c70f-108">E. 164 형식의 숫자를 로컬 전화 걸기 형식으로 변환 하려면이를 트렁크 피어로 라우팅하기 전에 요청 URI를 조작 하는 하나 이상의 변환 규칙을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c70f-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="4c70f-109">예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c70f-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="4c70f-110">서버에서 아웃 바운드 경로 변환을 수행 하 여 전화 번호를 로컬 전화 걸기 형식으로 변환 하기 위해 각 개별 트렁크 피어에서 구성 요구 사항을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c70f-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="4c70f-111">특정 중재 서버 클러스터와 연결할 게이트웨이 및 게이트웨이 개수를 계획할 때는 유사한 로컬 전화 걸기 요구 사항을 적용 하 여 트렁크 피어를 그룹화 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c70f-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="4c70f-112">이를 통해 필요한 변환 규칙의 수와이를 작성 하는 데 소요 되는 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c70f-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4c70f-113">트렁크 피어에서 변환 규칙을 구성 하는 대신 하나 이상의 변환 규칙을 엔터프라이즈 음성 트렁크 구성에 연결 하는 것이 사용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c70f-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="4c70f-114">두 규칙이 충돌할 수 있으므로 트렁크 피어에서 변환 규칙을 구성한 경우에는 변환 규칙을 엔터프라이즈 음성 트렁크 구성과 연결 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="4c70f-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="4c70f-115">예제 변환 규칙</span><span class="sxs-lookup"><span data-stu-id="4c70f-115">Example Translation Rules</span></span>

<span data-ttu-id="4c70f-116">다음 변환 규칙의 예에서는 서버에서 규칙을 개발 하 여 E. 164 형식의 번호를 트렁크 피어의 로컬 형식으로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c70f-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="4c70f-117">변환 규칙을 구현 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4c70f-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c70f-118">설명</span><span class="sxs-lookup"><span data-stu-id="4c70f-118">Description</span></span></th>
<th><span data-ttu-id="4c70f-119">시작 번호</span><span class="sxs-lookup"><span data-stu-id="4c70f-119">Starting Digits</span></span></th>
<th><span data-ttu-id="4c70f-120">Content-length</span><span class="sxs-lookup"><span data-stu-id="4c70f-120">Length</span></span></th>
<th><span data-ttu-id="4c70f-121">제거할 숫자</span><span class="sxs-lookup"><span data-stu-id="4c70f-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="4c70f-122">추가할 숫자</span><span class="sxs-lookup"><span data-stu-id="4c70f-122">Digits to Add</span></span></th>
<th><span data-ttu-id="4c70f-123">일치 패턴</span><span class="sxs-lookup"><span data-stu-id="4c70f-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="4c70f-124">Translation</span><span class="sxs-lookup"><span data-stu-id="4c70f-124">Translation</span></span></th>
<th><span data-ttu-id="4c70f-125">예제</span><span class="sxs-lookup"><span data-stu-id="4c70f-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c70f-126">미국 내에서의 일반적인 시외 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="4c70f-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="4c70f-127">(' + ' 제거)</span><span class="sxs-lookup"><span data-stu-id="4c70f-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="4c70f-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="4c70f-128">+1</span></span></p></td>
<td><p><span data-ttu-id="4c70f-129">정확히 12 개</span><span class="sxs-lookup"><span data-stu-id="4c70f-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="4c70f-130">1 </span><span class="sxs-lookup"><span data-stu-id="4c70f-130">1</span></span></p></td>
<td><p><span data-ttu-id="4c70f-131">개</span><span class="sxs-lookup"><span data-stu-id="4c70f-131">0</span></span></p></td>
<td><p><span data-ttu-id="4c70f-132">^\+(1 \ d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="4c70f-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="4c70f-133">$1</span><span class="sxs-lookup"><span data-stu-id="4c70f-133">$1</span></span></p></td>
<td><p><span data-ttu-id="4c70f-134">+ 14255551010이 14255551010</span><span class="sxs-lookup"><span data-stu-id="4c70f-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c70f-135">미국 국제 장거리 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="4c70f-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="4c70f-136">(' + ' 제거 및 011 추가)</span><span class="sxs-lookup"><span data-stu-id="4c70f-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="4c70f-137">11 이상</span><span class="sxs-lookup"><span data-stu-id="4c70f-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="4c70f-138">1 </span><span class="sxs-lookup"><span data-stu-id="4c70f-138">1</span></span></p></td>
<td><p><span data-ttu-id="4c70f-139">이진수</span><span class="sxs-lookup"><span data-stu-id="4c70f-139">011</span></span></p></td>
<td><p><span data-ttu-id="4c70f-140">^\+(\d \d {9} +) $</span><span class="sxs-lookup"><span data-stu-id="4c70f-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="4c70f-141">011 $1</span><span class="sxs-lookup"><span data-stu-id="4c70f-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="4c70f-142">+ 441235551010이 011441235551010</span><span class="sxs-lookup"><span data-stu-id="4c70f-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

