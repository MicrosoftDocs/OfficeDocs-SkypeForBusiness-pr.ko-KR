---
title: 'Lync Server 2013: 아웃바운드 음성 라우팅 계획'
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
ms.openlocfilehash: 9d33fbe8d15b78bed9dd651cd7facf35a8249f64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-outbound-voice-routing-in-lync-server-2013"></a><span data-ttu-id="5f82f-102">Lync Server 2013에서 아웃바운드 음성 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="5f82f-102">Planning outbound voice routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f82f-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5f82f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5f82f-104">아웃 바운드 통화 라우팅은 PSTN (공개 교환 전화 네트워크) 게이트웨이, 트렁크 또는 개인 분기 교환 (PBX)으로 향하는 통화에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-104">Outbound call routing applies to calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX).</span></span> <span data-ttu-id="5f82f-105">사용자가 전화를 걸 때 서버는 필요한 경우에는 휴대폰 번호를 E-164 형식으로 정규화 하 고이를 SIP URI와 일치 시 키 려 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-105">When a user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="5f82f-106">서버에서 일치 하는 항목을 만들 수 없는 경우에는 제공 된 다이얼 문자열을 기반으로 하는 아웃 바운드 호출 라우팅 논리가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-106">If the server cannot make the match, it applies outbound call routing logic based on the supplied dial string.</span></span> <span data-ttu-id="5f82f-107">다음 표에서 설명 하는 서버 설정을 구성 하 여 해당 논리를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-107">You define that logic by configuring the server settings that are described in the following table.</span></span>

### <a name="lync-server-outbound-call-routing-settings"></a><span data-ttu-id="5f82f-108">Lync Server 아웃 바운드 통화 라우팅 설정</span><span class="sxs-lookup"><span data-stu-id="5f82f-108">Lync Server Outbound Call Routing Settings</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f82f-109">오브젝트가</span><span class="sxs-lookup"><span data-stu-id="5f82f-109">Object</span></span></th>
<th><span data-ttu-id="5f82f-110">설명</span><span class="sxs-lookup"><span data-stu-id="5f82f-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f82f-111">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="5f82f-111">Dial Plan</span></span></p></td>
<td><p><span data-ttu-id="5f82f-112">다이얼 플랜은 전화 인증 및 통화 라우팅과 같은 목적으로 명명 된 위치, 개인 사용자 또는 연락처 개체의 전화 번호를 단일 표준 (E) 형식으로 변환 하는 정규화 규칙의 명명 된 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-112">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f82f-113">정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="5f82f-113">Normalization rule</span></span></p></td>
<td><p><span data-ttu-id="5f82f-114">정규화 규칙은 다양 한 형식으로 표시 되는 전화 번호가 지정 된 각 위치, 사용자 또는 연락처 개체에 대해 라우팅되는 방법을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-114">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="5f82f-115">전화 거는 위치와 전화를 걸고 있는 사람 또는 연락처 개체에 따라 같은 다이얼 문자열을 다르게 해석 하 고 번역할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-115">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object that makes the call.</span></span> <span data-ttu-id="5f82f-116">특정 위치와 관련 된 정규화 규칙 집합은 다이얼 플랜을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-116">A set of normalization rules associated with a particular location constitutes a dial plan.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f82f-117">음성 정책</span><span class="sxs-lookup"><span data-stu-id="5f82f-117">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="5f82f-118">음성 정책은 하나 이상의 PSTN 사용 레코드를 한 사용자 또는 사용자 그룹에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-118">A voice policy associates one or more PSTN usage records with one user or a group of users.</span></span> <span data-ttu-id="5f82f-119">음성 정책은 또한 사용 하거나 사용 하지 않도록 설정할 수 있는 통화 기능 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-119">A voice policy also provides a list of calling features that you can enable or disable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f82f-120">PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="5f82f-120">PSTN usage record</span></span></p></td>
<td><p><span data-ttu-id="5f82f-121">PSTN 사용 레코드는 조직의 여러 사용자 또는 사용자 그룹에 의해 이루어질 수 있는 호출 클래스 (예: 내부, 지역 또는 시외)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-121">A PSTN usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users, or groups of users, in an organization.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f82f-122">통화 경로</span><span class="sxs-lookup"><span data-stu-id="5f82f-122">Call Route</span></span></p></td>
<td><p><span data-ttu-id="5f82f-123">통화 경로는 대상 전화 번호와 특정 trunks 및 PSTN 사용 레코드를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-123">A call route associates destination phone numbers with particular trunks and PSTN usage records.</span></span> <span data-ttu-id="5f82f-124">PSTN 게이트웨이는 트렁크로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-124">A PSTN gateway is considered a trunk.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="5f82f-125">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="5f82f-125">In This Section</span></span>

<span data-ttu-id="5f82f-126">이 섹션에서는 다음 아웃 바운드 통화 라우팅 서버 설정을 구성 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f82f-126">This section provides guidelines for configuring the following outbound call routing server settings:</span></span>

  - <span></span>  
    [<span data-ttu-id="5f82f-127">Lync Server 2013의 다이얼 플랜 및 정규화 규칙</span><span class="sxs-lookup"><span data-stu-id="5f82f-127">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)

  - <span></span>  
    [<span data-ttu-id="5f82f-128">Lync Server 2013의 음성 정책</span><span class="sxs-lookup"><span data-stu-id="5f82f-128">Voice policies in Lync Server 2013</span></span>](lync-server-2013-voice-policies.md)

  - <span></span>  
    [<span data-ttu-id="5f82f-129">Lync Server 2013의 PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="5f82f-129">PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-pstn-usage-records.md)

  - <span></span>  
    [<span data-ttu-id="5f82f-130">Lync Server 2013의 음성 경로</span><span class="sxs-lookup"><span data-stu-id="5f82f-130">Voice routes in Lync Server 2013</span></span>](lync-server-2013-voice-routes.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f82f-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f82f-131">See Also</span></span>


[<span data-ttu-id="5f82f-132">Lync Server 2013의 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="5f82f-132">SIP trunking in Lync Server 2013</span></span>](lync-server-2013-sip-trunking.md)  
[<span data-ttu-id="5f82f-133">Lync Server 2013에서 직접 SIP 연결</span><span class="sxs-lookup"><span data-stu-id="5f82f-133">Direct SIP connections in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

