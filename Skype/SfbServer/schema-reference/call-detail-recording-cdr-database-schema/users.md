---
title: Users 테이블
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Users 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 데이터베이스에 레코드가 있는 통화 또는 세션에 관련된 한 사용자에 대한 정보가 저장됩니다.
ms.openlocfilehash: 66f3e1247d29969ecef36a5d6247510b5eae022c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389780"
---
# <a name="users-table"></a>Users 테이블
 
Users 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 데이터베이스에 레코드가 있는 통화 또는 세션에 관련된 한 사용자에 대한 정보가 저장됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||내부용 타임스탬프입니다.  <br/> |
|**UserId** <br/> |int  <br/> |Primary  <br/> |이 사용자를 식별하는 고유 번호입니다.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |사용자 URI입니다.  <br/> |
|**TenantId** <br/> |int  <br/> |외계인  <br/> |이 사용자의 테넌트 ID입니다. 자세한 내용은 [Tenants 테이블](tenants.md) 을 참조하세요. <br/> |
|**UriTypeId** <br/> |int  <br/> |외계인  <br/> |이 사용자의 URI 형식입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조하십시오. <br/> |
   

