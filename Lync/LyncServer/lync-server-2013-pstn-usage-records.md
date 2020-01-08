---
title: 'Lync Server 2013: PSTN 사용 레코드'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32000f1664591a3e054d058ced4f996a98f27cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="b88eb-102">Lync Server 2013의 PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="b88eb-102">PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b88eb-103">_**마지막으로 수정한 주제:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="b88eb-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="b88eb-104">PSTN 사용 레코드 계획은 주로 조직에서 현재 적용 되는 모든 통화 사용 권한 (CEO에서 임시 작업자, 컨설턴트, 불확정 스태프)으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b88eb-104">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff.</span></span> <span data-ttu-id="b88eb-105">이 프로세스는 또한 기존 통화 권한을 찾아 수정할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88eb-105">This process also provides an opportunity to reexamine existing call permissions and revise them.</span></span> <span data-ttu-id="b88eb-106">예상 엔터프라이즈 음성 사용자에 게 적용 되는 통화 권한에 대해서만 PSTN 사용 레코드를 만들 수 있지만, 더 나은 범위의 해결 방법은 일부 통화 권한에 대 한 PSTN 사용 레코드를 만드는 것이 현재 일부 경우에는 발생 하지 않을 수 있는지 여부에 관계 없이 엔터프라이즈 음성에 대해 사용 하도록 설정할 사용자 그룹에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88eb-106">You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice.</span></span> <span data-ttu-id="b88eb-107">통화 권한이 변경 되거나 다른 통화 권한이 있는 새 사용자가 추가 된 경우에는 이미 필요한 PSTN 사용 레코드가 생성 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b88eb-107">If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="b88eb-108">다음 표에는 일반적인 PSTN 사용 테이블이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88eb-108">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="b88eb-109">PSTN 사용 레코드</span><span class="sxs-lookup"><span data-stu-id="b88eb-109">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b88eb-110">Phone 특성</span><span class="sxs-lookup"><span data-stu-id="b88eb-110">Phone attribute</span></span></th>
<th><span data-ttu-id="b88eb-111">설명</span><span class="sxs-lookup"><span data-stu-id="b88eb-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b88eb-112">로컬</span><span class="sxs-lookup"><span data-stu-id="b88eb-112">Local</span></span></p></td>
<td><p><span data-ttu-id="b88eb-113">시내 통화</span><span class="sxs-lookup"><span data-stu-id="b88eb-113">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b88eb-114">시외</span><span class="sxs-lookup"><span data-stu-id="b88eb-114">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="b88eb-115">시외 통화</span><span class="sxs-lookup"><span data-stu-id="b88eb-115">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b88eb-116">국제화</span><span class="sxs-lookup"><span data-stu-id="b88eb-116">International</span></span></p></td>
<td><p><span data-ttu-id="b88eb-117">국제 전화</span><span class="sxs-lookup"><span data-stu-id="b88eb-117">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b88eb-118">뉴델리</span><span class="sxs-lookup"><span data-stu-id="b88eb-118">Delhi</span></span></p></td>
<td><p><span data-ttu-id="b88eb-119">뉴델리 전일 근무 직원</span><span class="sxs-lookup"><span data-stu-id="b88eb-119">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b88eb-120">Redmond</span><span class="sxs-lookup"><span data-stu-id="b88eb-120">Redmond</span></span></p></td>
<td><p><span data-ttu-id="b88eb-121">Redmond 전일 근무 직원</span><span class="sxs-lookup"><span data-stu-id="b88eb-121">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b88eb-122">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="b88eb-122">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="b88eb-123">Redmond 임시 직원</span><span class="sxs-lookup"><span data-stu-id="b88eb-123">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b88eb-124">Zurich</span><span class="sxs-lookup"><span data-stu-id="b88eb-124">Zurich</span></span></p></td>
<td><p><span data-ttu-id="b88eb-125">Zurich 전일 근무 직원</span><span class="sxs-lookup"><span data-stu-id="b88eb-125">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b88eb-126">PSTN 사용 레코드는 그 자체로 아무런 작업도 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b88eb-126">By themselves, PSTN usage records do not do anything.</span></span> <span data-ttu-id="b88eb-127">이 작업을 수행 하려면 다음을 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88eb-127">For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="b88eb-128">사용자에 게 할당 되는 음성 정책</span><span class="sxs-lookup"><span data-stu-id="b88eb-128">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="b88eb-129">경로-전화 번호에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b88eb-129">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="b88eb-130">음성 정책 및 경로에 대 한 자세한 내용은 lync [server 2013의 음성 정책](lync-server-2013-voice-policies.md) 및 [lync Server 2013의 음성 경로](lync-server-2013-voice-routes.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b88eb-130">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="b88eb-131">이를 만들고 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 발신 통화에 대 한 음성 경로 구성을](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b88eb-131">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

