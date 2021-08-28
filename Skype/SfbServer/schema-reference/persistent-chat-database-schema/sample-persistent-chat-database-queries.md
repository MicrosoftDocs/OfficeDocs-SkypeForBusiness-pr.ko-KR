---
title: 샘플 영구 채팅 데이터베이스 쿼리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: 이 섹션에는 영구 채팅 데이터베이스에 대한 예제 쿼리가 포함되어 있습니다.
ms.openlocfilehash: 041726f4f9e24d9d291d73e119cd62524b0a6288
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595320"
---
# <a name="sample-persistent-chat-database-queries"></a>샘플 영구 채팅 데이터베이스 쿼리
 
이 섹션에는 영구 채팅 데이터베이스에 대한 예제 쿼리가 포함되어 있습니다.
  
다음 예제를 사용하여 특정 날짜 이후에 가장 활성 상태인 영구 채팅방 목록을 얻습니다.
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

특정 날짜 이후에 가장 활동이 많은 사용자 목록을 가져오려면 다음 예를 사용합니다.
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

"Hello World"가 포함된 메시지를 전송한 모든 사용자의 목록을 가져오려면 다음 예를 사용합니다.
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

특정 사용자에 대해 그룹 구성원 자격의 목록을 가져오려면 다음 예를 사용합니다.
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

Jane Dow라는 사용자가 직접 구성원으로 있는 모든 대화방의 목록을 가져오려면 다음 예를 사용합니다.
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

사용자가 수신한 초대 목록을 가져오려면 다음 예를 사용합니다.
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
