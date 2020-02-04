---
title: 'Lync Server 2013: 사용자별 현재 상태 정책 지정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ec15b826614afcca970989b6436d3ad94d7941f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="40b9b-102">Lync Server 2013에서 사용자 단위 현재 상태 정책 지정</span><span class="sxs-lookup"><span data-stu-id="40b9b-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40b9b-103">_**마지막으로 수정한 주제:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="40b9b-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="40b9b-104">현재 상태 정책은 현재 상태에 영향을 주는 제한 및 제한 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="40b9b-105">다음 표에서는 Lync Server 2013에서 사용할 수 있는 현재 상태 정책 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="40b9b-106">현재 상태 정책 설정</span><span class="sxs-lookup"><span data-stu-id="40b9b-106">Presence Policy Settings</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40b9b-107">XML 이름</span><span class="sxs-lookup"><span data-stu-id="40b9b-107">XML name</span></span></th>
<th><span data-ttu-id="40b9b-108">표시 이름</span><span class="sxs-lookup"><span data-stu-id="40b9b-108">Display name</span></span></th>
<th><span data-ttu-id="40b9b-109">설명</span><span class="sxs-lookup"><span data-stu-id="40b9b-109">Description</span></span></th>
<th><span data-ttu-id="40b9b-110">유형</span><span class="sxs-lookup"><span data-stu-id="40b9b-110">Type</span></span></th>
<th><span data-ttu-id="40b9b-111">값</span><span class="sxs-lookup"><span data-stu-id="40b9b-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40b9b-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="40b9b-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="40b9b-113">최대 구독자 범주 구독 수</span><span class="sxs-lookup"><span data-stu-id="40b9b-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="40b9b-114">구독자 범주 구독 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-114">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="40b9b-115">예를 들어 Communicator에서 사용자의 현재 상태를 구독할 때 각 연락처 카드, 일정 데이터, 메모, 서비스 및 상태 범주에 대 한 범주 구독을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-115">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="40b9b-116">0으로 설정 하면 사용자 또는 연락처 개체가 다른 사람에 의해 구독 될 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="40b9b-117">이 설정은 높은 번호로 설정 했 고 평균 사용자가 자신의 현재 상태를 구독 하는 사용자 수가 많은 경우 성능에 큰 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="40b9b-118">정수</span><span class="sxs-lookup"><span data-stu-id="40b9b-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="40b9b-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="40b9b-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b9b-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="40b9b-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="40b9b-121">대기 중인 현재 상태 구독 알림의 최대 수</span><span class="sxs-lookup"><span data-stu-id="40b9b-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="40b9b-122">메시지를 입력 하 여 구독자 테이블의 항목 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-122">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="40b9b-123">이 설정은 지정 된 사용자에 대해 대기 시킬 수 있는 최대 메시지 수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-123">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="40b9b-124">예를 들어 사용자 A가 사용자 B의 현재 상태를 구독 하는 경우 사용자 B가 사용자 B에 게 구독 하 라는 메시지가 표시 되 고 사용자 B의 질문 구독자 테이블에 승인 메시지가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-124">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="40b9b-125">사용자 B가 구독을 수락 하거나 승인 하면 사용자 B의 질문 구독자 테이블에서 승인 메시지가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-125">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="40b9b-126">0으로 설정 하면 다른 사용자가 자신의 현재 상태를 구독할 때 메시지가 표시 되지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="40b9b-127">정수 또는 토큰</span><span class="sxs-lookup"><span data-stu-id="40b9b-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="40b9b-128">0-500</span><span class="sxs-lookup"><span data-stu-id="40b9b-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="40b9b-129">기본적으로 **기본 정책** 및 **서비스:** 사용자가 Lync Server를 배포할 때 중간 현재 상태 정책이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="40b9b-130">다음 표에서는 두 현재 상태 정책의 특정 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="40b9b-131">현재 상태 정책</span><span class="sxs-lookup"><span data-stu-id="40b9b-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40b9b-132">정책 이름</span><span class="sxs-lookup"><span data-stu-id="40b9b-132">Policy name</span></span></th>
<th><span data-ttu-id="40b9b-133">설명</span><span class="sxs-lookup"><span data-stu-id="40b9b-133">Description</span></span></th>
<th><span data-ttu-id="40b9b-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="40b9b-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="40b9b-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="40b9b-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40b9b-136">기본 정책</span><span class="sxs-lookup"><span data-stu-id="40b9b-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="40b9b-137">일반 사용자를 위한 정책.</span><span class="sxs-lookup"><span data-stu-id="40b9b-137">Policy for typical users.</span></span> <span data-ttu-id="40b9b-138">이는 기본 현재 상태 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-138">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="40b9b-139">1000</span><span class="sxs-lookup"><span data-stu-id="40b9b-139">1000</span></span></p></td>
<td><p><span data-ttu-id="40b9b-140">200</span><span class="sxs-lookup"><span data-stu-id="40b9b-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40b9b-141">서비스: 보통</span><span class="sxs-lookup"><span data-stu-id="40b9b-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="40b9b-142">더 많은 사용자가 개체의 현재 상태를 구독 하도록 요구 하는 응용 프로그램에 대 한 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="40b9b-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="40b9b-143">1000</span><span class="sxs-lookup"><span data-stu-id="40b9b-143">1000</span></span></p></td>
<td><p><span data-ttu-id="40b9b-144">0</span><span class="sxs-lookup"><span data-stu-id="40b9b-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

