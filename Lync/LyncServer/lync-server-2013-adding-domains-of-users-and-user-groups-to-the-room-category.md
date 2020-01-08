---
title: 'Lync Server 2013: 채팅방 범주에 사용자 및 사용자 그룹의 도메인 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding domains of users and user groups to the room category
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215884(v=OCS.15)
ms:contentKeyID: 48706013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32539c66523cf625c80d5f113cf788b02d3c905b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-domains-of-users-and-user-groups-to-the-room-category-in-lync-server-2013"></a>Lync Server 2013에서 채팅방 범주에 사용자 및 사용자 그룹의 도메인 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-07_

채팅방에 더 많은 사용자 그룹을 추가 하려면 [Lync Server 2013에서 범주 구성](lync-server-2013-configure-categories.md) 및 배포 설명서에서 [범주 관리](manage-categories.md) 를 참조 하세요. 예를 들어이 명령은 active Directory에서 NorthAmericaUsers OU의 모든 사용자를 NorthAmerica 채팅방에 추가 합니다.

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

이 명령은 재무 메일 그룹의 모든 구성원을 같은 채팅방에 추가 합니다.

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

</div>

<span> </span>

</div>

</div>

</div>

