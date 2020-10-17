---
title: 'Lync Server 2013: 긴급 통화에 대 한 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d190d240db85016bd13bfd2480b42b088ca5f88
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504365"
---
# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a><span data-ttu-id="c6092-102">Lync Server 2013의 응급 전화에 대 한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="c6092-102">Defining your requirements for emergency calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6092-103">_**마지막으로 수정 된 항목:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="c6092-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="c6092-104">Microsoft Lync Server 2013 E9-1-1 배포를 시작 하기 전에 먼저 다음 섹션에서 설명 하는 질문에 대 한 답을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6092-104">Before you begin a Microsoft Lync Server 2013 E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="c6092-105">수행 해야 하는 계획은 배포 하도록 선택한 E9-1-1 솔루션, SIP 트렁크 E9-1-1 서비스 공급자 또는 ELIN (응급 위치 식별 번호) 게이트웨이의 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c6092-105">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="c6092-106">다음 표에서는이 계획 통합 문서에서 각 솔루션에 대해 검토 해야 하는 섹션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c6092-106">The following table identifies the sections in this planning workbook that you’ll need to review for each of those solutions.</span></span>

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a><span data-ttu-id="c6092-107">E9-1-1 솔루션 유형별 계획 단계</span><span class="sxs-lookup"><span data-stu-id="c6092-107">Planning Steps by Type of E9-1-1 Solution</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6092-108">SIP 트렁크 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="c6092-108">SIP trunk service provider</span></span></th>
<th><span data-ttu-id="c6092-109">ELIN 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="c6092-109">ELIN gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6092-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013에서 E9-1-1 배포 범위 정의</a></span><span class="sxs-lookup"><span data-stu-id="c6092-110"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c6092-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013에서 E9-1-1 배포 범위 정의</a></span><span class="sxs-lookup"><span data-stu-id="c6092-111"><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Defining the scope of the E9-1-1 deployment in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6092-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Lync Server 2013에서 위치를 확인 하는 데 사용 되는 네트워크 요소 정의</a></span><span class="sxs-lookup"><span data-stu-id="c6092-112"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c6092-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Lync Server 2013에서 위치를 확인 하는 데 사용 되는 네트워크 요소 정의</a></span><span class="sxs-lookup"><span data-stu-id="c6092-113"><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Defining the network elements used to determine location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6092-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Lync Server 2013에서 E9-1-1에 대해 사용자를 사용 하도록 설정</a></span><span class="sxs-lookup"><span data-stu-id="c6092-114"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c6092-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Lync Server 2013에서 E9-1-1에 대해 사용자를 사용 하도록 설정</a></span><span class="sxs-lookup"><span data-stu-id="c6092-115"><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Enabling users for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6092-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Lync Server 2013에서 SIP 트렁크 서비스 공급자 위치 관리</a></span><span class="sxs-lookup"><span data-stu-id="c6092-116"><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Managing locations for SIP trunk service providers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c6092-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Lync Server 2013의 ELIN 게이트웨이 위치 관리</a></span><span class="sxs-lookup"><span data-stu-id="c6092-117"><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Managing locations for ELIN gateways in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6092-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의</a></span><span class="sxs-lookup"><span data-stu-id="c6092-118"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c6092-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의</a></span><span class="sxs-lookup"><span data-stu-id="c6092-119"><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Defining the user experience for manually acquiring a location in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6092-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Lync Server 2013에서 E9-1-1에 대 한 SIP 트렁크 디자인</a></span><span class="sxs-lookup"><span data-stu-id="c6092-120"><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Designing the SIP trunk for E9-1-1 in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c6092-121"><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013의 보안 센터 포함</a></span><span class="sxs-lookup"><span data-stu-id="c6092-121"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6092-122"><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013의 보안 센터 포함</a></span><span class="sxs-lookup"><span data-stu-id="c6092-122"><a href="lync-server-2013-including-the-security-desk.md">Including the security desk in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c6092-123"><a href="lync-server-2013-defining-the-location-policy.md">Lync Server 2013에 대 한 위치 정책 정의</a></span><span class="sxs-lookup"><span data-stu-id="c6092-123"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6092-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Lync Server 2013 용 E9-1-1 서비스 공급자 선택</a></span><span class="sxs-lookup"><span data-stu-id="c6092-124"><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Choosing an E9-1-1 service provider for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="c6092-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Lync Server 2013에서 위치 정책 범위 할당</a></span><span class="sxs-lookup"><span data-stu-id="c6092-125"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6092-126"><a href="lync-server-2013-defining-the-location-policy.md">Lync Server 2013에 대 한 위치 정책 정의</a></span><span class="sxs-lookup"><span data-stu-id="c6092-126"><a href="lync-server-2013-defining-the-location-policy.md">Defining the location policy for Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6092-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Lync Server 2013에서 위치 정책 범위 할당</a></span><span class="sxs-lookup"><span data-stu-id="c6092-127"><a href="lync-server-2013-assigning-location-policy-scope.md">Assigning location policy scope in Lync Server 2013</a></span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="c6092-128">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="c6092-128">In This Section</span></span>

  - [<span data-ttu-id="c6092-129">Lync Server 2013에서 E9-1-1 배포 범위 정의</span><span class="sxs-lookup"><span data-stu-id="c6092-129">Defining the scope of the E9-1-1 deployment in Lync Server 2013</span></span>](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [<span data-ttu-id="c6092-130">Lync Server 2013에서 위치를 확인 하는 데 사용 되는 네트워크 요소 정의</span><span class="sxs-lookup"><span data-stu-id="c6092-130">Defining the network elements used to determine location in Lync Server 2013</span></span>](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [<span data-ttu-id="c6092-131">Lync Server 2013에서 E9-1-1에 대해 사용자를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="c6092-131">Enabling users for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [<span data-ttu-id="c6092-132">Lync Server 2013에서 SIP 트렁크 서비스 공급자 위치 관리</span><span class="sxs-lookup"><span data-stu-id="c6092-132">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [<span data-ttu-id="c6092-133">Lync Server 2013의 ELIN 게이트웨이 위치 관리</span><span class="sxs-lookup"><span data-stu-id="c6092-133">Managing locations for ELIN gateways in Lync Server 2013</span></span>](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [<span data-ttu-id="c6092-134">Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의</span><span class="sxs-lookup"><span data-stu-id="c6092-134">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [<span data-ttu-id="c6092-135">Lync Server 2013에서 E9-1-1에 대 한 SIP 트렁크 디자인</span><span class="sxs-lookup"><span data-stu-id="c6092-135">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [<span data-ttu-id="c6092-136">Lync Server 2013의 보안 센터 포함</span><span class="sxs-lookup"><span data-stu-id="c6092-136">Including the security desk in Lync Server 2013</span></span>](lync-server-2013-including-the-security-desk.md)

  - [<span data-ttu-id="c6092-137">Lync Server 2013 용 E9-1-1 서비스 공급자 선택</span><span class="sxs-lookup"><span data-stu-id="c6092-137">Choosing an E9-1-1 service provider for Lync Server 2013</span></span>](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [<span data-ttu-id="c6092-138">Lync Server 2013에 대 한 위치 정책 정의</span><span class="sxs-lookup"><span data-stu-id="c6092-138">Defining the location policy for Lync Server 2013</span></span>](lync-server-2013-defining-the-location-policy.md)

  - [<span data-ttu-id="c6092-139">Lync Server 2013에서 위치 정책 범위 할당</span><span class="sxs-lookup"><span data-stu-id="c6092-139">Assigning location policy scope in Lync Server 2013</span></span>](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

