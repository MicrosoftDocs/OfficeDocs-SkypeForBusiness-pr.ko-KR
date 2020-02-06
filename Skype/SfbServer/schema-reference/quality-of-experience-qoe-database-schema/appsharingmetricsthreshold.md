---
title: AppSharingMetricsThreshold 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: AppSharingMetricsThreshold 테이블에는 응용 프로그램 공유에 사용 되는 경험 메트릭의 품질 기준에 적합 한 값이 포함 되어 있습니다. 이러한 임계값은 응용 프로그램 공유 환경을 불량으로 분류 해야 하는지 결정 하는 데 사용 됩니다.
ms.openlocfilehash: 3639d9f2783b6433353f23d15e6ce063fb8ec49f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811386"
---
# <a name="appsharingmetricsthreshold-table"></a>AppSharingMetricsThreshold 테이블
 
AppSharingMetricsThreshold 테이블에는 응용 프로그램 공유에 사용 되는 경험 메트릭의 품질 기준에 적합 한 값이 포함 되어 있습니다. 이러한 임계값은 응용 프로그램 공유 환경을 불량으로 분류 해야 하는지 결정 하는 데 사용 됩니다.
  
이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |주요한  <br/> |배치 된 통화 유형입니다.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||응용 프로그램 공유에 대 한 최적의 대역폭 제한. 기본값은 100만입니다.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||응용 프로그램 공유에 허용 되는 대역폭 제한. 기본값은 50만입니다.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |10 진수 (5, 2)  <br/> ||응용 프로그램 공유 품질을 분류 하기 위해 "spoiled" 타일에 대 한 최적 백분율 비율입니다. 이 값은 보기에 도달 하지 않은 공유자 콘텐츠의 백분율입니다. 공유자에서 그래픽 원본의 타일을 포기 하거나 ASMCU 타일이 공유자의 타일을 각각 삭제 하는 경우 콘텐츠가 취소 (또는 spoiled) 될 수 있습니다. 기본 값은 11%입니다.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |10 진수 (5, 2)  <br/> ||응용 프로그램 공유 품질을 분류 하는 "spoiled" 타일에 허용 되는 백분율 비율입니다. 이 값은 보기에 도달 하지 않은 공유자 콘텐츠의 백분율입니다. 공유자에서 그래픽 원본의 타일을 포기 하거나 ASMCU 타일이 공유자의 타일을 각각 삭제 하는 경우 콘텐츠가 취소 (또는 spoiled) 될 수 있습니다. 기본값은 36%입니다.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |o  <br/> ||이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |o  <br/> ||이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |o  <br/> ||이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |o  <br/> ||이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |o  <br/> ||응용 프로그램 공유에 포함 된 두 미디어 끝점 간의 상대적 단방향 지연에 대 한 최적의 값입니다. 이것은 단일 홉 대기 시간 측정입니다. 기본값은 1.0 초입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |o  <br/> ||응용 프로그램 공유에 포함 된 두 미디어 끝점 간의 상대적 단방향 지연에 대 한 최적의 값입니다. 이것은 단일 홉 대기 시간 측정입니다. 기본값은 1.75 초입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |o  <br/> ||보기 세션 중에 회의 서버의 평균 RDP 타일 처리 대기 시간에 대 한 최적의 값입니다. 대기 시간은 서버 (공유자 또는 해당 시나리오에 따라)에서 시작 프레임을 인코딩한 시간과 동일한 시작 프레임을 뷰어에 디코딩할 때의 차이입니다.  <br/> 평균 높음은 보기 환경에서 더 오래 지연 됩니다. 오버 로드 된 회의 서버는 평균 지연 시간을 겪을 수 있습니다. 기본값은 200ms입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |o  <br/> ||보기 세션 중에 회의 서버의 평균 RDP 타일 처리 대기 시간을 허용 하는 값입니다. 대기 시간은 서버 (공유자 또는 해당 시나리오에 따라)에서 시작 프레임을 인코딩한 시간과 동일한 시작 프레임을 뷰어에 디코딩할 때의 차이입니다.  <br/> 평균 높음은 보기 환경에서 더 오래 지연 됩니다. 오버 로드 된 회의 서버는 평균 지연 시간을 겪을 수 있습니다. 기본값은 200ms입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
   

