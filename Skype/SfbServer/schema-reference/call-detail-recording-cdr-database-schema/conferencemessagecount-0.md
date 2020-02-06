---
title: ConferenceMessageCount 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 보기는 사용자가 회의에 보낸 메시지 수에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815386"
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount 보기
 
ConferenceMessageCount 보기는 사용자가 회의에 보낸 메시지 수에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
> [!NOTE]
> ConferenceMessageCount 보기에는 [ConferenceSessionDetails 보기](conferencesessiondetails.md) 의 모든 열과 아래에 나열 된 열이 포함 됩니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar (450)  <br/> |메시지를 보낸 사용자의 URI입니다.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |메시지를 보낸 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**UserTenant 넌 트** <br/> |uniqueidentifier  <br/> |메시지를 보낸 사용자의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |회의 세션 동안 사용자가 보낸 메시지 수입니다.  <br/> |
   

