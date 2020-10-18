---
title: 'Lync Server 2013: 샘플 영구 채팅 데이터베이스 쿼리'
description: 'Lync Server 2013: 샘플 영구 채팅 데이터베이스 쿼리'
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
ms.openlocfilehash: 5e1cb49e944dbbd3e22c1b944b4c8495c6ff9b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574914"
---
# <a name="sample-persistent-chat-database-queries-for-lync-server-2013"></a><span data-ttu-id="a69ff-103">Lync Server 2013에 대 한 샘플 영구 채팅 데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="a69ff-103">Sample Persistent Chat database queries for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a69ff-104">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="a69ff-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="a69ff-105">이 섹션에는 영구 채팅 데이터베이스에 대 한 샘플 쿼리가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a69ff-105">This section contains sample queries for the Persistent Chat database.</span></span>

<span data-ttu-id="a69ff-106">다음 예를 사용 하 여 특정 날짜 후의 가장 적극적인 영구 대화방 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a69ff-106">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>

    SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
      FROM tblChat, tblNode
      WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY nodeName
      ORDER BY ChatMessages DESC

<span data-ttu-id="a69ff-107">특정 날짜 이후에 가장 활동이 많은 사용자 목록을 가져오려면 다음 예를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a69ff-107">Use the following example to get a list of your most active users after a certain date.</span></span>

    SELECT prinName as Name, count(*) as ChatMessages
      FROM tblChat, tblPrincipal
      WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY prinName
      ORDER BY ChatMessages DESC

<span data-ttu-id="a69ff-108">"Hello World"가 포함된 메시지를 전송한 모든 사용자의 목록을 가져오려면 다음 예를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a69ff-108">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>

    SELECT nodeName as ChatRoom, prinName as Name, content as Message
      FROM tblChat, tblNode, tblPrincipal
      WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'

<span data-ttu-id="a69ff-109">특정 사용자에 대해 그룹 구성원 자격의 목록을 가져오려면 다음 예를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a69ff-109">Use the following example to get a list of group memberships for a certain principal.</span></span>

    SELECT prinName as Name    
      FROM tblPrincipalAffiliations as pa, tblPrincipal
      where principalID = 7 and affiliationID = prinID

<span data-ttu-id="a69ff-110">Jane Dow라는 사용자가 직접 구성원으로 있는 모든 대화방의 목록을 가져오려면 다음 예를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a69ff-110">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>

    SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
      FROM tblPrincipalRole, tblPrincipal, tblNode
      WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'

<span data-ttu-id="a69ff-111">사용자가 수신한 초대 목록을 가져오려면 다음 예를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a69ff-111">Use the following example to get a list of invitations that a user has received.</span></span>

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

