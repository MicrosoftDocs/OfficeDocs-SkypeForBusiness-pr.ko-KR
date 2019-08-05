---
title: 샘플 영구 채팅 데이터베이스 쿼리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: 이 섹션에는 영구 채팅 데이터베이스에 대 한 예제 쿼리가 포함 되어 있습니다.
ms.openlocfilehash: fef40c2f36547fb0772d2e938bf8259246ec2055
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196656"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="8ecf6-103">샘플 영구 채팅 데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="8ecf6-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="8ecf6-104">이 섹션에는 영구 채팅 데이터베이스에 대 한 예제 쿼리가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ecf6-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="8ecf6-105">다음 예제를 사용 하 여 특정 날짜 이후에 가장 활발 한 영구 채팅방의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8ecf6-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="8ecf6-106">다음 예제를 사용 하 여 특정 날짜 이후에 가장 활발 한 사용자 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ecf6-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="8ecf6-107">다음 예제를 사용 하 여 "Hello World"를 사용 하 여 메시지를 보낸 모든 사용자의 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ecf6-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="8ecf6-108">다음 예제를 사용 하 여 특정 주체에 대 한 그룹 구성원 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8ecf6-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="8ecf6-109">다음 예제를 사용 하 여 "홍길동 Dow" 사용자가 직접 구성원 인 모든 채팅방의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8ecf6-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="8ecf6-110">다음 예제를 사용 하 여 사용자가 받은 초대 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8ecf6-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
