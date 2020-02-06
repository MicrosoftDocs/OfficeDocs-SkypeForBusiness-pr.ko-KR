---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData에는 규정 준수 어댑터에서 아직 처리 하지 않은 준수 이벤트가 포함 됩니다.
ms.openlocfilehash: f09acd44e803c629e45afa18683ac7bc863564a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814666"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData에는 규정 준수 어댑터에서 아직 처리 하지 않은 준수 이벤트가 포함 됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, null이 아님  <br/> |이벤트 ID입니다.  <br/> |
|entryDate  <br/> |smalldatetime, null이 아님  <br/> |삽입 시간 (이 경우에는 항목이 자리 표시자 일 수 있으므로 cmplType = 9의 미래입니다).  <br/> |
|cmplType  <br/> |int, null 아님  <br/> | 준수 이벤트 유형: <br/>  1: 채팅 <br/>  2: 백 채팅 <br/>  3: 파일 다운로드 <br/>  4: 파일 업로드 <br/>  9: Provisional 파일 전송 <br/>  10: 채팅 삭제 (바꾸기 사용) <br/>  11: 채팅 제거 <br/> |
|cmplTime  <br/> |bigint, null이 아님  <br/> |이벤트에 대 한 타임 스탬프입니다.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), null 아님  <br/> |채널 URI (Uniform Resource Identifier)입니다.  <br/> |
|cmplChatID  <br/> |bigint  <br/> |채팅 ID (chatId 테이블에 해당).  <br/> |
|cmplUserID  <br/> |int, null 아님  <br/> |포스터의 Principal ID (tblPrincipal 테이블에 해당)  <br/> |
|cmplUserUri  <br/> |nvarchar (255), null 아님  <br/> |사용자 URI입니다.  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |메시지 (인코딩은 cmplType에 따라 다름)  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|cmplEventID  <br/> |기본 키입니다.  <br/> |
   

