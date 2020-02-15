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
ms.openlocfilehash: 618ab1b18f92d19f65084d321b71219cc0fafb06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030031"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="d2b97-102">Lync Server 2013에서 사용자별 현재 상태 정책 할당</span><span class="sxs-lookup"><span data-stu-id="d2b97-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2b97-103">_**마지막으로 수정 된 항목:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="d2b97-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="d2b97-104">현재 상태 정책은 현재 상태에 영향을 미치는 제한 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="d2b97-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="d2b97-105">다음 표에서는 Lync Server 2013에서 사용할 수 있는 현재 상태 정책 설정에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2b97-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="d2b97-106">현재 상태 정책 설정</span><span class="sxs-lookup"><span data-stu-id="d2b97-106">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="d2b97-107">XML 이름</span><span class="sxs-lookup"><span data-stu-id="d2b97-107">XML name</span></span></th>
<th><span data-ttu-id="d2b97-108">표시 이름</span><span class="sxs-lookup"><span data-stu-id="d2b97-108">Display name</span></span></th>
<th><span data-ttu-id="d2b97-109">설명</span><span class="sxs-lookup"><span data-stu-id="d2b97-109">Description</span></span></th>
<th><span data-ttu-id="d2b97-110">유형</span><span class="sxs-lookup"><span data-stu-id="d2b97-110">Type</span></span></th>
<th><span data-ttu-id="d2b97-111">값</span><span class="sxs-lookup"><span data-stu-id="d2b97-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2b97-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="d2b97-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="d2b97-113">구독자 범주의 최대 구독 수</span><span class="sxs-lookup"><span data-stu-id="d2b97-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="d2b97-p102">구독자의 범주 구독 수를 제한합니다. 예를 들어 Communicator가 사용자의 현재 상태를 구독하면 대화 상대 카드, 일정 데이터, 메모, 서비스 및 상태 범주 각각에 대한 범주 구독을 가져오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2b97-p102">Limits the number of subscriber category subscriptions. For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="d2b97-116">설정이 0인 경우 다른 사용자가 사용자나 대화 상대 개체의 상태를 구독할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b97-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d2b97-117">이 설정에 지정된 숫자가 높을 경우 성능이 심각하게 저하될 수 있으며 해당 사용자의 현재 상태를 구독하는 사용자가 많아집니다.</span><span class="sxs-lookup"><span data-stu-id="d2b97-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="d2b97-118">정수</span><span class="sxs-lookup"><span data-stu-id="d2b97-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="d2b97-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="d2b97-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2b97-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="d2b97-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="d2b97-121">현재 상태 구독에 대해 대기할 수 있는 최대 알림 수</span><span class="sxs-lookup"><span data-stu-id="d2b97-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="d2b97-p103">프롬프트 구독자 테이블의 항목 수를 제한합니다. 이 설정으로, 해당 사용자에 대해 대기할 수 있는 최대 프롬프트 수가 결정됩니다. 예를 들어 사용자 A가 사용자 B의 현재 상태를 구독할 때 사용자 B는 사용자 A가 이제 사용자 B의 현재 상태를 구독한다는 프롬프트를 받게 되며 사용자 B의 프롬프트 구독자 테이블에서 승인 프롬프트가 만들어집니다. 사용자 B가 구독을 수락하거나 승인하고 나면 사용자 B의 프롬프트 구독자 테이블에서 승인 프롬프트가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2b97-p103">Limits the number of entries in the prompted subscribers table. This setting determines the maximum number of prompts that can be queued for a given user. For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table. After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="d2b97-126">설정이 0인 경우 다른 사람이 사용자의 현재 상태를 구독할 때 해당 사용자에게 메시지가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b97-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="d2b97-127">정수 또는 토큰</span><span class="sxs-lookup"><span data-stu-id="d2b97-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="d2b97-128">0-500</span><span class="sxs-lookup"><span data-stu-id="d2b97-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d2b97-129">기본적으로 **기본 정책** 및 **서비스: 중간** 거점 정책은 Lync Server를 배포할 때 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2b97-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="d2b97-130">다음 표에는 두 개의 현재 상태 정책에 대한 특정 설정이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2b97-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="d2b97-131">현재 상태 정책</span><span class="sxs-lookup"><span data-stu-id="d2b97-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2b97-132">정책 이름</span><span class="sxs-lookup"><span data-stu-id="d2b97-132">Policy name</span></span></th>
<th><span data-ttu-id="d2b97-133">설명</span><span class="sxs-lookup"><span data-stu-id="d2b97-133">Description</span></span></th>
<th><span data-ttu-id="d2b97-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="d2b97-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="d2b97-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="d2b97-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2b97-136">기본 정책</span><span class="sxs-lookup"><span data-stu-id="d2b97-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="d2b97-p105">일반 사용자를 위한 정책이며, 기본 현재 상태 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="d2b97-p105">Policy for typical users. This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="d2b97-139">1000</span><span class="sxs-lookup"><span data-stu-id="d2b97-139">1000</span></span></p></td>
<td><p><span data-ttu-id="d2b97-140">200</span><span class="sxs-lookup"><span data-stu-id="d2b97-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2b97-141">서비스: 보통</span><span class="sxs-lookup"><span data-stu-id="d2b97-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="d2b97-142">기타 사용자가 개체의 현재 상태를 구독해야 하는 응용 프로그램을 위한 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="d2b97-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="d2b97-143">1000</span><span class="sxs-lookup"><span data-stu-id="d2b97-143">1000</span></span></p></td>
<td><p><span data-ttu-id="d2b97-144">개</span><span class="sxs-lookup"><span data-stu-id="d2b97-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

