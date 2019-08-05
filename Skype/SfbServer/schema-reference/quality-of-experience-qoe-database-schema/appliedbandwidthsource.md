---
title: AppliedBandwidthSource 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: AppliedBandwidthSource 테이블은 지원 테이블입니다. 각 레코드는 하나의 원본을 나타냅니다.
ms.openlocfilehash: 6d40701b74dd5e7312a504127675eed686de7321
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196589"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource 테이블
 
AppliedBandwidthSource 테이블은 지원 테이블입니다. 각 레코드는 하나의 원본을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |주요한  <br/> |출처를 식별 하는 고유 번호입니다.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar (256)  <br/> |독특한  <br/> |적용 되는 대역폭 cap의 원본입니다. 대역폭 한도가 시작 되는 위치를 설명 합니다 (예: "정책 서버", "서버 설정" 또는 "모달").  <br/> |
   

