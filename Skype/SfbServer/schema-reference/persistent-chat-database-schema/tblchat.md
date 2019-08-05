---
title: tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat에는 모든 채팅 메시지가 포함 됩니다.
ms.openlocfilehash: 15c7030fe14f62c5d32af54c0f5a6901da3f977b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196644"
---
# <a name="tblchat"></a>tblChat
 
tblChat에는 모든 채팅 메시지가 포함 됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|channelId  <br/> |int, null 아님  <br/> |노드 ID입니다.  <br/> |
|chatId  <br/> |bigint, null이 아님  <br/> |TblLastChatId 테이블에서 생성 된 채팅방 순서를 정의 하는 고유 순차 번호 (노드 ID 당)입니다.  <br/> |
|로이 날짜  <br/> |bigint, null이 아님  <br/> |채팅 메시지에 대 한 타임 스탬프입니다.  <br/> |
|userId  <br/> |int, null 아님  <br/> |포스터의 사용자 ID입니다.  <br/> |
|isAlert  <br/> |bit, null이 아님  <br/> |메시지가 알림 메시지 이면 True를 지정 합니다. 그렇지 않으면 False입니다.  <br/> |
|콘텐트가  <br/> |nvarchar (max), null 아님  <br/> | 채팅 콘텐츠 (일반 텍스트 버전). 일반적으로 콘텐츠는 다음과 같은 예외를 포함 하는 일반 텍스트로 되어 있습니다. <br/>  파일은 ma-filelink: 링크로 표시 됩니다. <br/>  링크는 HTML 요소로 표시 됩니다 (콘텐츠 형식을 HTML로 간주할 수 없음). <br/>  스토리는 "[스토리] ..."와 같은 형식으로 인코딩됩니다. <br/> |
|서식  <br/> |varchar (max)  <br/> |채팅 콘텐츠 (RTF 버전). 클라이언트가 제공 하지 않는 경우 Null 일 수 있습니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<channelID,로 d\>  <br/> |기본 키입니다.  <br/> |
   

