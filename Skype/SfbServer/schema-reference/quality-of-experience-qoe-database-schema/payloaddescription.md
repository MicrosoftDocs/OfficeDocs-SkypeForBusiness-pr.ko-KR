---
title: PayloadDescription 테이블
ms.reviewer: ''
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
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription 테이블은 지원 테이블입니다. 각 레코드는 오디오 및 비디오 세션에 사용되는 하나의 코덱을 나타냅니다.
ms.openlocfilehash: 56241d40be8593a7d5cf5edbf05e8921b2a65ca3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394640"
---
# <a name="payloaddescription-table"></a>PayloadDescription 테이블
 
PayloadDescription 테이블은 지원 테이블입니다. 각 레코드는 오디오 및 비디오 세션에 사용되는 하나의 코덱을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |코덱을 식별하는 고유 번호입니다.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Unique  <br/> |코덱 이름입니다.  <br/> |
   

