---
title: 풀 테이블
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Pool 테이블은 여러 프런트 엔드 풀에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 풀을 나타냅니다.
ms.openlocfilehash: e9ad0f0661bbd38a2d1175ab38113585c306baf234bc97e98bf40fca949d0cd9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312976"
---
# <a name="pool-table"></a>풀 테이블
 
Pool 테이블은 여러 프런트 엔드 풀에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 풀을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |이 풀을 식별하는 고유 번호입니다.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Unique  <br/> |풀 FQDN입니다.  <br/> |
   

