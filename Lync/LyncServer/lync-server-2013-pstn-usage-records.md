---
title: 'Lync Server 2013: PSTN 사용 레코드'
description: 'Lync Server 2013: PSTN 사용 레코드'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f8ff428dc2fa5cf8cf0f10e37f0f79c38d70d70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565584"
---
# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="d9f77-103">Lync Server 2013의 PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="d9f77-103">PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9f77-104">_**마지막으로 수정 된 항목:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="d9f77-104">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="d9f77-p101">PSTN 사용 레코드 계획은 주로 CEO에서 임시 직원, 컨설턴트 및 비정규직 직원에 이르기까지 조직에서 현재 적용 중인 모든 통화 권한을 나열하는 작업으로 구성됩니다. 이 프로세스에서 기존 통화 권한을 다시 검사하고 수정할 수도 있습니다. 예상 Enterprise Voice 사용자에게 적용되는 통화 권한에 대해서만 PSTN 사용 레코드를 만들 수도 있지만 일부 통화 권한이 현재 Enterprise Voice를 사용할 수 있는 사용자 그룹에 적용되지 않는다 해도 모든 통화 권한에 대한 PSTN 사용 레코드를 만드는 것이 더 나은 장기적 솔루션이 될 수 있습니다. 통화 권한이 변경되거나 다른 통화 권한을 가진 새 사용자가 추가되어도 필요한 PSTN 사용 레코드를 이미 만들었을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d9f77-p101">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff. This process also provides an opportunity to reexamine existing call permissions and revise them. You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice. If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="d9f77-109">다음 표는 일반적인 PSTN 사용 표를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9f77-109">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="d9f77-110">PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="d9f77-110">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9f77-111">전화 특성</span><span class="sxs-lookup"><span data-stu-id="d9f77-111">Phone attribute</span></span></th>
<th><span data-ttu-id="d9f77-112">설명</span><span class="sxs-lookup"><span data-stu-id="d9f77-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9f77-113">로컬</span><span class="sxs-lookup"><span data-stu-id="d9f77-113">Local</span></span></p></td>
<td><p><span data-ttu-id="d9f77-114">시내 전화</span><span class="sxs-lookup"><span data-stu-id="d9f77-114">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f77-115">Long-Distance</span><span class="sxs-lookup"><span data-stu-id="d9f77-115">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="d9f77-116">시외 전화</span><span class="sxs-lookup"><span data-stu-id="d9f77-116">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f77-117">영어</span><span class="sxs-lookup"><span data-stu-id="d9f77-117">International</span></span></p></td>
<td><p><span data-ttu-id="d9f77-118">국제 전화</span><span class="sxs-lookup"><span data-stu-id="d9f77-118">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f77-119">Delhi</span><span class="sxs-lookup"><span data-stu-id="d9f77-119">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d9f77-120">델리 정규 직원</span><span class="sxs-lookup"><span data-stu-id="d9f77-120">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f77-121">니다</span><span class="sxs-lookup"><span data-stu-id="d9f77-121">Redmond</span></span></p></td>
<td><p><span data-ttu-id="d9f77-122">레드몬드 정규 직원</span><span class="sxs-lookup"><span data-stu-id="d9f77-122">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9f77-123">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="d9f77-123">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="d9f77-124">레드몬드 임시 직원</span><span class="sxs-lookup"><span data-stu-id="d9f77-124">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9f77-125">취리히 정규</span><span class="sxs-lookup"><span data-stu-id="d9f77-125">Zurich</span></span></p></td>
<td><p><span data-ttu-id="d9f77-126">취리히 정규 직원</span><span class="sxs-lookup"><span data-stu-id="d9f77-126">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d9f77-p102">PSTN 사용 레코드 자체는 아무 작업도 수행하지 않습니다. PSTN 사용 레코드가 작동하려면 다음과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f77-p102">By themselves, PSTN usage records do not do anything. For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="d9f77-129">사용자에게 할당된 음성 정책</span><span class="sxs-lookup"><span data-stu-id="d9f77-129">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="d9f77-130">전화 번호에 할당된 경로</span><span class="sxs-lookup"><span data-stu-id="d9f77-130">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="d9f77-131">음성 정책 및 경로에 대 한 자세한 내용은 [Lync server 2013의 음성 정책](lync-server-2013-voice-policies.md) 및 [lync Server 2013의 음성 경로](lync-server-2013-voice-routes.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d9f77-131">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="d9f77-132">이를 만들고 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 아웃 바운드 통화에 대 한 음성 경로 구성을](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d9f77-132">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

