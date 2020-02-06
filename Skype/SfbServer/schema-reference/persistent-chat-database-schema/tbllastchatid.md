---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId에는 각 사용자에 대해 생성 된 마지막 채팅 ID (및 tblChat 테이블에 사용 됨)가 포함 되어 있습니다.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814586"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId에는 각 사용자에 대해 생성 된 마지막 채팅 ID (및 tblChat 테이블에 사용 됨)가 포함 되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, null 아님  <br/> |노드 ID (채팅방에만 입력 하세요).  <br/> |
|lastChatID  <br/> |bigint, null이 아님  <br/> |마지막으로 사용한 채팅 ID.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |기본 키 (nodeID만 처리에 충분 합니다.)  <br/> |
|nodeID  <br/> |NodeID 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
   
## <a name="see-also"></a>참고 항목

[tblChat](tblchat.md)
