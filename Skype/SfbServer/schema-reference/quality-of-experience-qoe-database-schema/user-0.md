---
title: User 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: User 테이블은 데이터베이스에 기록된 세션에 참가한 다양한 사용자 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 한 사용자를 나타내는 것입니다.
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800078"
---
# <a name="user-table"></a>User 테이블
 
User 테이블은 데이터베이스에 기록된 세션에 참가한 다양한 사용자 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 한 사용자를 나타내는 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |이 사용자를 식별하는 고유 번호입니다.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |고유  <br/> |URI 문자열입니다.  <br/> |
|**URIType** <br/> |int  <br/> ||1은 알 수 없는 URI 형식입니다.  <br/> 2는 사용자 URI입니다.  <br/> 4는 회의 URI입니다.  <br/> 8은 전화 URI입니다.  <br/> |
|**TenantKey** <br/> |int  <br/> |외계인  <br/> |테넌트 테이블에서 참조되는 사용자의 테넌트입니다.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||사용자가 음성 통화가 불량한 경우의 최신 타임스탬프입니다.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||내부 용도로만 사용됩니다.  <br/> |
   

