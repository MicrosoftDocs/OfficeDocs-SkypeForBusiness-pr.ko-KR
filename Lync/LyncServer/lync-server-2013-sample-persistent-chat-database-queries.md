---
title: 'Lync Server 2013: 샘플 영구 채팅 데이터베이스 쿼리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Sample Persistent Chat database queries
ms:assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558649(v=OCS.15)
ms:contentKeyID: 48184133
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5e442ebf3aef34d297a1b23da06b00fc4724aa0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sample-persistent-chat-database-queries-for-lync-server-2013"></a><span data-ttu-id="8501f-102">Lync Server 2013의 샘플 영구 채팅 데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="8501f-102">Sample Persistent Chat database queries for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8501f-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="8501f-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="8501f-104">이 섹션에는 영구 채팅 데이터베이스에 대 한 예제 쿼리가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8501f-104">This section contains sample queries for the Persistent Chat database.</span></span>

<span data-ttu-id="8501f-105">다음 예제를 사용 하 여 특정 날짜 이후에 가장 활발 한 영구 채팅방의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8501f-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>

    SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
      FROM tblChat, tblNode
      WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY nodeName
      ORDER BY ChatMessages DESC

<span data-ttu-id="8501f-106">다음 예제를 사용 하 여 특정 날짜 이후에 가장 활발 한 사용자 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8501f-106">Use the following example to get a list of your most active users after a certain date.</span></span>

    SELECT prinName as Name, count(*) as ChatMessages
      FROM tblChat, tblPrincipal
      WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY prinName
      ORDER BY ChatMessages DESC

<span data-ttu-id="8501f-107">다음 예제를 사용 하 여 "Hello World"를 사용 하 여 메시지를 보낸 모든 사용자의 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8501f-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>

    SELECT nodeName as ChatRoom, prinName as Name, content as Message
      FROM tblChat, tblNode, tblPrincipal
      WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'

<span data-ttu-id="8501f-108">다음 예제를 사용 하 여 특정 주체에 대 한 그룹 구성원 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8501f-108">Use the following example to get a list of group memberships for a certain principal.</span></span>

    SELECT prinName as Name    
      FROM tblPrincipalAffiliations as pa, tblPrincipal
      where principalID = 7 and affiliationID = prinID

<span data-ttu-id="8501f-109">다음 예제를 사용 하 여 "홍길동 Dow" 사용자가 직접 구성원 인 모든 채팅방의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8501f-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>

    SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
      FROM tblPrincipalRole, tblPrincipal, tblNode
      WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'

<span data-ttu-id="8501f-110">다음 예제를 사용 하 여 사용자가 받은 초대 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8501f-110">Use the following example to get a list of invitations that a user has received.</span></span>

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

