---
title: SessionCorrelation 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 관계 테이블은 지원 테이블입니다. 각 레코드는 여러 세션을 연결 하는 데 사용 되는 CorrelationID 하나를 나타냅니다.
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196522"
---
# <a name="sessioncorrelation-table"></a>SessionCorrelation 테이블
 
SessionCorrelation 관계 테이블은 지원 테이블입니다. 각 레코드는 여러 세션을 연결 하는 데 사용 되는 CorrelationID 하나를 나타냅니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**검사** <br/> |int  <br/> |||
|**CorrelationKey** <br/> |int  <br/> |주요한  <br/> |이 A/V 회의 서버를 식별 하는 고유 번호입니다.  <br/> |
|**Legredir** <br/> |nvarchar (256)  <br/> |독특한  <br/> |상호 관련 된 세션은 동일한 상관 관계 ID를 갖습니다.  <br/> |
|**NextUpdateTS** <br/> |dmtf  <br/> | <br/> |내부용 으로만 사용 됩니다.  <br/> |
   

