---
title: 'Lync Server 2013: 샘플 영구 채팅 데이터베이스 쿼리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sample Persistent Chat database queries
ms:assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558649(v=OCS.15)
ms:contentKeyID: 48184133
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfbe31844e0ca78a3f9b133bde96f2a6f625f759
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511035"
---
# <a name="sample-persistent-chat-database-queries-for-lync-server-2013"></a>Lync Server 2013에 대 한 샘플 영구 채팅 데이터베이스 쿼리

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

이 섹션에는 영구 채팅 데이터베이스에 대 한 샘플 쿼리가 포함 되어 있습니다.

다음 예를 사용 하 여 특정 날짜 후의 가장 적극적인 영구 대화방 목록을 가져옵니다.

    SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
      FROM tblChat, tblNode
      WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY nodeName
      ORDER BY ChatMessages DESC

특정 날짜 이후에 가장 활동이 많은 사용자 목록을 가져오려면 다음 예를 사용합니다.

    SELECT prinName as Name, count(*) as ChatMessages
      FROM tblChat, tblPrincipal
      WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY prinName
      ORDER BY ChatMessages DESC

"Hello World"가 포함된 메시지를 전송한 모든 사용자의 목록을 가져오려면 다음 예를 사용합니다.

    SELECT nodeName as ChatRoom, prinName as Name, content as Message
      FROM tblChat, tblNode, tblPrincipal
      WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'

특정 사용자에 대해 그룹 구성원 자격의 목록을 가져오려면 다음 예를 사용합니다.

    SELECT prinName as Name    
      FROM tblPrincipalAffiliations as pa, tblPrincipal
      where principalID = 7 and affiliationID = prinID

Jane Dow라는 사용자가 직접 구성원으로 있는 모든 대화방의 목록을 가져오려면 다음 예를 사용합니다.

    SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
      FROM tblPrincipalRole, tblPrincipal, tblNode
      WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'

사용자가 수신한 초대 목록을 가져오려면 다음 예를 사용합니다.

    SELECT prinName
          ,nodeName
          ,invID   
          ,createdOn
      FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
      where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
      ORDER BY invID DESC

</div>

<span> </span>

</div>

</div>

</div>

