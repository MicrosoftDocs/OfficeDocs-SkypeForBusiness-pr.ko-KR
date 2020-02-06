---
title: Users 테이블
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: 사용자 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 데이터베이스의 레코드를 포함 하는 호출 또는 세션과 관련 된 한 사용자에 대 한 정보가 저장 됩니다.
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814806"
---
# <a name="users-table"></a>Users 테이블
 
사용자 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 데이터베이스의 레코드를 포함 하는 호출 또는 세션과 관련 된 한 사용자에 대 한 정보가 저장 됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |dmtf  <br/> ||내부 사용을 위한 타임 스탬프입니다.  <br/> |
|**UserId** <br/> |int  <br/> |주요한  <br/> |이 사용자를 식별 하는 고유 번호입니다.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> | <br/> |사용자 URI입니다.  <br/> |
|**TenantId** <br/> |int  <br/> |외부  <br/> |이 사용자의 테 넌 트 ID입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**UriTypeId** <br/> |int  <br/> |외부  <br/> |이 사용자의 URI 형식입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
   

