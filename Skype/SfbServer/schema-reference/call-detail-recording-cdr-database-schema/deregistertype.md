---
title: 비즈니스용 Skype 서버 2015의 DeRegisterType 테이블
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 테이블은 ' 클라이언트 시작 ', ' 등록 만료 ' 또는 ' 클라이언트가 응답을 중지 했습니다. ' 등 사용 가능한 사용자의 등록 취소 형식 목록을 저장 하는 정적 테이블입니다.
ms.openlocfilehash: ae9afafe91336b1e5c74fd0a854e2975a3b4ba8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815296"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 DeRegisterType 테이블
 
DeRegisterType 테이블은 ' 클라이언트 시작 ', ' 등록 만료 ' 또는 ' 클라이언트가 응답을 중지 했습니다. ' 등 사용 가능한 사용자의 등록 취소 형식 목록을 저장 하는 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |주요한  <br/> ||
|**DeRegisterReason** <br/> |nvarchar (256)  <br/> || 허용 되는 값: <br/>  0--알 수 없음 <br/>  1--클라이언트에서 초기화 된 등록 취소 <br/>  2--등록이 만료 됨 <br/>  3-클라이언트가 충돌 합니다. <br/>  4--사용자 특성이 변경 됨 <br/>  5-기본 등록 기관 변경 <br/>  6--생존 모드의 레거시 클라이언트 <br/> |
   

