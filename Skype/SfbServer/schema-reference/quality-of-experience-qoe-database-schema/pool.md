---
title: 풀 테이블
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool 테이블은 여러 프런트 엔드 풀에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 풀을 나타냅니다.
---

# <a name="pool-table"></a>풀 테이블
 
Pool 테이블은 여러 프런트 엔드 풀에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 풀을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |이 풀을 식별하는 고유 번호입니다.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Unique  <br/> |풀 FQDN입니다.  <br/> |
   

