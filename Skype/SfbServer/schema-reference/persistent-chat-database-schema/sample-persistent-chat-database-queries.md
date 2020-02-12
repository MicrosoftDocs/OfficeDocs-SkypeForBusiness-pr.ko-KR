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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: 이 섹션에는 영구 채팅 데이터베이스에 대 한 예제 쿼리가 포함 되어 있습니다.
ms.openlocfilehash: f161deb55cb9ecb0e42eb23e71cd842aa8f3d99a
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887717"
---
# <a name="sample-persistent-chat-database-queries"></a>샘플 영구 채팅 데이터베이스 쿼리
 
이 섹션에는 영구 채팅 데이터베이스에 대 한 예제 쿼리가 포함 되어 있습니다.
  
다음 예제를 사용 하 여 특정 날짜 이후에 가장 활발 한 영구 채팅방의 목록을 가져옵니다.
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

다음 예제를 사용 하 여 특정 날짜 이후에 가장 활발 한 사용자 목록을 가져올 수 있습니다.
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

다음 예제를 사용 하 여 "Hello World"를 사용 하 여 메시지를 보낸 모든 사용자의 목록을 가져올 수 있습니다.
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

다음 예제를 사용 하 여 특정 주체에 대 한 그룹 구성원 목록을 가져옵니다.
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

다음 예제를 사용 하 여 "홍길동 Dow" 사용자가 직접 구성원 인 모든 채팅방의 목록을 가져옵니다.
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

다음 예제를 사용 하 여 사용자가 받은 초대 목록을 가져옵니다.
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
