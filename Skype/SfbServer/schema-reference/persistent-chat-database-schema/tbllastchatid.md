---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId에는 각 사용자에 대해 생성(및 tblChat 테이블에서 사용)된 마지막 채팅 ID가 포함됩니다.
ms.openlocfilehash: 7ab281b31869b4a761a6360978b57ec9591daaf0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741884"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId에는 각 사용자에 대해 생성(및 tblChat 테이블에서 사용)된 마지막 채팅 ID가 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, null이 아님  <br/> |노드 ID(대화방 유형 전용)입니다.  <br/> |
|lastChatID  <br/> |bigint, null이 아님  <br/> |마지막으로 사용된 채팅 ID입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |기본 키(처리를 위해서는 nodeID만으로도 충분함)입니다.  <br/> |
|nodeID  <br/> |tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   
## <a name="see-also"></a>참고 항목

[tblChat](tblchat.md)
