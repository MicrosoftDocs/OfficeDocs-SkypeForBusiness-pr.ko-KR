---
title: 'Lync Server 2013: 사용자별 현재 상태 정책 할당'
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
ms.openlocfilehash: c169c6995ca49cc89742bd026b18dc254430cb9d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="dabab-102">Lync Server 2013에서 사용자별 현재 상태 정책 할당</span><span class="sxs-lookup"><span data-stu-id="dabab-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dabab-103">_**마지막으로 수정 된 항목:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="dabab-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="dabab-104">현재 상태 정책은 현재 상태에 영향을 미치는 제한 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="dabab-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="dabab-105">다음 표에서는 Lync Server 2013에서 사용할 수 있는 현재 상태 정책 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dabab-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="dabab-106">현재 상태 정책 설정</span><span class="sxs-lookup"><span data-stu-id="dabab-106">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="dabab-107">XML 이름</span><span class="sxs-lookup"><span data-stu-id="dabab-107">XML name</span></span></th>
<th><span data-ttu-id="dabab-108">표시 이름</span><span class="sxs-lookup"><span data-stu-id="dabab-108">Display name</span></span></th>
<th><span data-ttu-id="dabab-109">설명</span><span class="sxs-lookup"><span data-stu-id="dabab-109">Description</span></span></th>
<th><span data-ttu-id="dabab-110">유형</span><span class="sxs-lookup"><span data-stu-id="dabab-110">Type</span></span></th>
<th><span data-ttu-id="dabab-111">값</span><span class="sxs-lookup"><span data-stu-id="dabab-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dabab-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="dabab-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="dabab-113">구독자 범주의 최대 구독 수</span><span class="sxs-lookup"><span data-stu-id="dabab-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="dabab-p102">구독자의 범주 구독 수를 제한합니다. 예를 들어 Communicator가 사용자의 현재 상태를 구독하면 대화 상대 카드, 일정 데이터, 메모, 서비스 및 상태 범주 각각에 대한 범주 구독을 가져오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabab-p102">Limits the number of subscriber category subscriptions. For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="dabab-116">설정이 0인 경우 다른 사용자가 사용자나 대화 상대 개체의 상태를 구독할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dabab-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="dabab-117">이 설정에 지정된 숫자가 높을 경우 성능이 심각하게 저하될 수 있으며 해당 사용자의 현재 상태를 구독하는 사용자가 많아집니다.</span><span class="sxs-lookup"><span data-stu-id="dabab-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="dabab-118">정수</span><span class="sxs-lookup"><span data-stu-id="dabab-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="dabab-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="dabab-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dabab-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="dabab-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="dabab-121">현재 상태 구독에 대해 대기할 수 있는 최대 알림 수</span><span class="sxs-lookup"><span data-stu-id="dabab-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="dabab-p103">프롬프트 구독자 테이블의 항목 수를 제한합니다. 이 설정으로, 해당 사용자에 대해 대기할 수 있는 최대 프롬프트 수가 결정됩니다. 예를 들어 사용자 A가 사용자 B의 현재 상태를 구독할 때 사용자 B는 사용자 A가 이제 사용자 B의 현재 상태를 구독한다는 프롬프트를 받게 되며 사용자 B의 프롬프트 구독자 테이블에서 승인 프롬프트가 만들어집니다. 사용자 B가 구독을 수락하거나 승인하고 나면 사용자 B의 프롬프트 구독자 테이블에서 승인 프롬프트가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabab-p103">Limits the number of entries in the prompted subscribers table. This setting determines the maximum number of prompts that can be queued for a given user. For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table. After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="dabab-126">설정이 0인 경우 다른 사람이 사용자의 현재 상태를 구독할 때 해당 사용자에게 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dabab-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="dabab-127">정수 또는 토큰</span><span class="sxs-lookup"><span data-stu-id="dabab-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="dabab-128">0-500</span><span class="sxs-lookup"><span data-stu-id="dabab-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dabab-129">기본적으로 **기본 정책** 및 **서비스: 중간** 거점 정책은 Lync Server를 배포할 때 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dabab-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="dabab-130">다음 표에는 두 개의 현재 상태 정책에 대한 특정 설정이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dabab-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="dabab-131">현재 상태 정책</span><span class="sxs-lookup"><span data-stu-id="dabab-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dabab-132">정책 이름</span><span class="sxs-lookup"><span data-stu-id="dabab-132">Policy name</span></span></th>
<th><span data-ttu-id="dabab-133">설명</span><span class="sxs-lookup"><span data-stu-id="dabab-133">Description</span></span></th>
<th><span data-ttu-id="dabab-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="dabab-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="dabab-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="dabab-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dabab-136">기본 정책</span><span class="sxs-lookup"><span data-stu-id="dabab-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="dabab-p105">일반 사용자를 위한 정책이며, 기본 현재 상태 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dabab-p105">Policy for typical users. This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="dabab-139">1000</span><span class="sxs-lookup"><span data-stu-id="dabab-139">1000</span></span></p></td>
<td><p><span data-ttu-id="dabab-140">200</span><span class="sxs-lookup"><span data-stu-id="dabab-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dabab-141">서비스: 보통</span><span class="sxs-lookup"><span data-stu-id="dabab-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="dabab-142">기타 사용자가 개체의 현재 상태를 구독해야 하는 응용 프로그램을 위한 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dabab-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="dabab-143">1000</span><span class="sxs-lookup"><span data-stu-id="dabab-143">1000</span></span></p></td>
<td><p><span data-ttu-id="dabab-144">개</span><span class="sxs-lookup"><span data-stu-id="dabab-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

