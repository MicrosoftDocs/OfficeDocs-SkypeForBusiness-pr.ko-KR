---
title: 비즈니스용 Skype 서버 2015의 CallType 테이블
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 테이블은 가능한 통화 형식 목록을 저장 하는 정적 테이블입니다.
ms.openlocfilehash: 294af58755e980200d75c899d6110322e2ff774d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815436"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 CallType 테이블
 
CallType 테이블은 가능한 통화 형식 목록을 저장 하는 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |주요한  <br/> ||
|**CallType** <br/> |varchar  <br/> || 허용 되는 값: <br/>  0--알 수 없음 <br/>  1-인스턴트 메시지 <br/>  2--응용 프로그램 공유 <br/>  3--오디오 <br/>  4-오디오 및 비디오 <br/>  5-파일 전송 <br/> |
   

