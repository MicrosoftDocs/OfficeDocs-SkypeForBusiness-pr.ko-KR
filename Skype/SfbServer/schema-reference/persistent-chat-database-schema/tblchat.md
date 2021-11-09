---
title: tblChat
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat에는 모든 채팅 메시지가 포함됩니다.
ms.openlocfilehash: e8a07c0c8ff8b3b473855ee86f6fc0c276e959f6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839820"
---
# <a name="tblchat"></a>tblChat
 
tblChat에는 모든 채팅 메시지가 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|channelId  <br/> |int, null이 아님  <br/> |노드 ID입니다.  <br/> |
|chatId  <br/> |bigint, null이 아님  <br/> |tblLastChatId 테이블에서 생성된 대화방 순서를 정의하는 고유한 일련 번호(노드 ID당)입니다.  <br/> |
|chatDate  <br/> |bigint, null이 아님  <br/> |채팅 메시지의 타임스탬프입니다.  <br/> |
|userId  <br/> |int, null이 아님  <br/> |게시자의 사용자 ID입니다.  <br/> |
|isAlert  <br/> |bit, null이 아님  <br/> |메시지가 경고 메시지인 경우 True입니다. 그렇지 않으면 False입니다.  <br/> |
|content  <br/> |nvarchar(max), null이 아님  <br/> | 채팅 콘텐츠(일반 텍스트 버전)입니다. 콘텐츠는 일반적으로 일반 텍스트이지만 다음과 같은 예외가 있습니다. <br/>  파일이 ma-filelink: 링크로 표시됩니다. <br/>  링크는 HTML 요소로 표시됩니다(콘텐츠 형식은 HTML로 간주 할 수 없음). <br/>  스토리는 "[STORY]...."같은 형식으로 인코딩됩니다. <br/> |
|rtf  <br/> |varchar(max)  <br/> |채팅 콘텐츠(RTF 버전)입니다. 클라이언트에서 제공하지 않는 경우 Null일 수 있습니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |기본 키입니다.  <br/> |
   

