---
title: 'Lync Server 2013: 대화방 범주에 사용자 및 사용자 그룹의 도메인 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding domains of users and user groups to the room category
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215884(v=OCS.15)
ms:contentKeyID: 48706013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9e918d5c1f888d508220279426d6d6125f1416f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-domains-of-users-and-user-groups-to-the-room-category-in-lync-server-2013"></a><span data-ttu-id="815f3-102">Lync Server 2013의 대화방 범주에 사용자 및 사용자 그룹의 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="815f3-102">Adding domains of users and user groups to the room category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="815f3-103">_**마지막으로 수정 된 항목:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="815f3-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="815f3-104">대화방에 사용자 그룹을 더 많이 추가 하려면 배포 설명서에서 [Lync Server 2013의 범주 구성](lync-server-2013-configure-categories.md) 및 [관리 범주](manage-categories.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="815f3-104">To add larger groups of users to a chat room, see [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) and [Manage categories](manage-categories.md) in the Deployment documentation.</span></span> <span data-ttu-id="815f3-105">예를 들어이 명령은 active Directory에서 NorthAmericaUsers OU의 모든 사용자를 북미 채팅방에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="815f3-105">For example, this command adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

<span data-ttu-id="815f3-106">이 명령은 재무 메일 그룹의 모든 구성원을 동일한 대화방에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="815f3-106">His command adds all the members from the Finance distribution group to the same chat room:</span></span>

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

</div>

<span> </span>

</div>

</div>

</div>

