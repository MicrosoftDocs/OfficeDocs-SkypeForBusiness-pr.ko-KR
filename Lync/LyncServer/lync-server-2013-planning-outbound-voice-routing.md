---
title: 'Lync Server 2013: 아웃 바운드 음성 라우팅 계획'
description: 'Lync Server 2013: 아웃 바운드 음성 라우팅 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning outbound voice routing
ms:assetid: 37c55fa4-175a-4190-b9e4-c2e5ac7b9261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425853(v=OCS.15)
ms:contentKeyID: 48183835
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 057f81b995e231c2025a9fcb07e675086a662efe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563984"
---
# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="b2468-103">Lync Server 2013의 아웃 바운드 음성 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="b2468-103">Planning outbound voice routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2468-104">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b2468-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b2468-p101">아웃바운드 통화 라우팅은 공중 전화망(PSTN) 게이트웨이, 트렁크 또는 PBX(Private Branch Exchange)로 향하는 통화에 적용됩니다. 사용자가 전화를 걸면 서버는 필요한 경우 전화 번호를 E.164 형식으로 정규화하고 SIP URI에 일치시키려고 합니다. 일치시킬 수 없는 경우 서버는 제공된 다이얼 문자열에 기초하여 아웃바운드 통화 라우팅 논리를 적용합니다. 이 논리는 아래 표에 설명되어 있는 서버 설정을 구성하여 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b2468-p101">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX). When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI. If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string. You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="b2468-109">Lync Server 아웃바운드 통화 라우팅 설정</span><span class="sxs-lookup"><span data-stu-id="b2468-109">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2468-110">나타내는</span><span class="sxs-lookup"><span data-stu-id="b2468-110">Object</span></span></th>
<th><span data-ttu-id="b2468-111">설명</span><span class="sxs-lookup"><span data-stu-id="b2468-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2468-112">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="b2468-112">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="b2468-113">다이얼 플랜은 전화 인증 및 통화 라우팅을 위해 명명된 위치, 개별 사용자 또는 연락처 개체의 전화 번호를 하나의 표준(E.164) 형식으로 변환하는 명명된 정규화 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="b2468-113">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2468-114">정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="b2468-114">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="b2468-p102">정규화 규칙은 다양한 형식으로 표현된 전화 번호를 지정된 각 위치, 사용자 또는 연락처 개체에 대해 라우팅하는 방법을 정의합니다. 전화를 건 위치와 전화를 거는 사람 또는 대화 상대 개체에 따라 동일한 전화 걸기 문자열이 다르게 해석되고 변환될 수 있습니다. 특정 위치에 연결된 정규화 규칙 집합이 다이얼 플랜을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b2468-p102">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call. A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2468-118">음성 정책</span><span class="sxs-lookup"><span data-stu-id="b2468-118">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="b2468-p103">음성 정책은 하나 이상의 PSTN 사용 레코드를 단일 사용자 또는 사용자 그룹과 연결합니다. 또한 음성 정책은 사용하거나 사용하지 않도록 설정할 수 있는 통화 기능 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b2468-p103">A voice policy associates one or more PSTN usage records with one user or a group of users. A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2468-121">PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="b2468-121">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="b2468-122">PSTN 사용 레코드는 조직의 여러 사용자 또는 사용자 그룹이 수행할 수 있는 통화 클래스(내부, 시내, 시외 등)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2468-122">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2468-123">통화 경로</span><span class="sxs-lookup"><span data-stu-id="b2468-123">Call Route</span></span></p></td>
<td><p><span data-ttu-id="b2468-p104">통화 경로는 대상 전화 번호를 특정 트렁크 및 PSTN 사용 레코드와 연결합니다. PSTN 게이트웨이는 트렁크로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2468-p104">A call route associates destination phone numbers with particular trunks and PSTN usage records. A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="b2468-126">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b2468-126">In This Section</span></span>

<span data-ttu-id="b2468-127">이 섹션에서는 다음의 아웃바운드 통화 라우팅 서버 설정을 구성하는 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b2468-127">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="b2468-128">Lync Server 2013의 다이얼 플랜 및 정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="b2468-128">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="b2468-129">Lync Server 2013의 음성 정책</span><span class="sxs-lookup"><span data-stu-id="b2468-129">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="b2468-130">Lync Server 2013의 PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="b2468-130">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="b2468-131">Lync Server 2013의 음성 경로</span><span class="sxs-lookup"><span data-stu-id="b2468-131">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2468-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2468-132">See Also</span></span>


[<span data-ttu-id="b2468-133">Lync Server 2013의 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="b2468-133">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="b2468-134">Lync Server 2013의 직접 SIP 연결</span><span class="sxs-lookup"><span data-stu-id="b2468-134">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

