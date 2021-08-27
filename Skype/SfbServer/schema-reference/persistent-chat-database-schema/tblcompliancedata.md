---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData에는 준수 어댑터에서 아직 처리되지 않은 준수 이벤트가 포함됩니다.
ms.openlocfilehash: e4f10a9a239c752bf5171f4ba7bcadcf111cef35
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596392"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData에는 준수 어댑터에서 아직 처리되지 않은 준수 이벤트가 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, null이 아님  <br/> |이벤트 ID입니다.  <br/> |
|entryDate  <br/> |smalldatetime, null이 아님  <br/> |삽입 시간(cmplType=9의 경우에는 항목이 단순히 자리 표시자이므로 오랜 시간 후일 수 있음)  <br/> |
|cmplType  <br/> |int, null이 아님  <br/> | 준수 이벤트 유형: <br/>  1: 채팅 <br/>  2: 백채트 <br/>  3: 파일 다운로드 <br/>  4: 파일 업로드 <br/>  9: 임시 파일 전송 <br/>  10: 채팅 삭제(바꾸기 포함) <br/>  11: 채팅 삭제 <br/> |
|cmplTime  <br/> |bigint, null이 아님  <br/> |이벤트의 타임스탬프입니다.  <br/> |
|cmplChannelUri  <br/> |nvarchar(255), null이 아님  <br/> |채널 URI(Uniform Resource Identifier)입니다.  <br/> |
|cmplChatID  <br/> |bigint  <br/> |채팅 ID(tblChat.chatId 테이블에 해당됨)  <br/> |
|cmplUserID  <br/> |int, null이 아님  <br/> |게시자의 사용자 ID(tblPrincipal.prinID 테이블에 해당됨)  <br/> |
|cmplUserUri  <br/> |nvarchar(255), null이 아님  <br/> |사용자 URI입니다.  <br/> |
|cmplMessage  <br/> |nvarchar(max)  <br/> |메시지(인코딩은 cmplType에 따라 다름)  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|cmplEventID  <br/> |기본 키입니다.  <br/> |
   

