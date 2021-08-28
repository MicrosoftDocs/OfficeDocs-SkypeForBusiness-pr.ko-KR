---
title: SessionCorrelation 테이블
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
ms.localizationpriority: medium
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 테이블은 지원 테이블입니다. 각 레코드는 여러 세션의 상관 관계에 사용되는 하나의 CorrelationID를 나타내며,
ms.openlocfilehash: a0ec0a2e1435aab02ba1733530271b2ad648869e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634122"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation 테이블
 
SessionCorrelation 테이블은 지원 테이블입니다. 각 레코드는 여러 세션의 상관 관계에 사용되는 하나의 CorrelationID를 나타내며, 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**체크섬** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |Primary  <br/> |이 A/V 회의 서버를 식별하는 고유 번호입니다.  <br/> |
|**CorrelationID** <br/> |nvarchar(256)  <br/> |Unique  <br/> |상관 관계가 있는 세션의 상관 관계 ID는 동일합니다.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> | <br/> |내부 용도로만 사용됩니다.  <br/> |
   

