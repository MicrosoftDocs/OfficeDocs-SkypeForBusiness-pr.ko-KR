---
title: AppSharingMetricsThreshold 테이블
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
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: AppSharingMetricsThreshold 테이블에는 응용 프로그램 공유에 사용되는 QoE(체감 품질) 메트릭에 대한 최적값 및 허용 가능한 값이 포함되어 있습니다. 이러한 임계값은 응용 프로그램 공유 환경을 불량으로 분류해야 하는지 여부를 확인하는 데 사용됩니다.
ms.openlocfilehash: 747497affbf561976bc6dd626bdce060efc1eca8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809698"
---
# <a name="appsharingmetricsthreshold-table"></a>AppSharingMetricsThreshold 테이블
 
AppSharingMetricsThreshold 테이블에는 응용 프로그램 공유에 사용되는 QoE(체감 품질) 메트릭에 대한 최적값 및 허용 가능한 값이 포함되어 있습니다. 이러한 임계값은 응용 프로그램 공유 환경을 불량으로 분류해야 하는지 여부를 확인하는 데 사용됩니다.
  
이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primary  <br/> |수행된 통화 유형입니다.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||응용 프로그램 공유에 대한 최적의 대역폭 제한입니다. 기본값은 1000000입니다.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||응용 프로그램 공유에 대한 허용 가능한 대역폭 제한입니다. 기본값은 500000입니다.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |decimal(5,2)  <br/> ||응용 프로그램 공유 품질을 분류하기 위한 "부실" 타일에 대한 최적 비율입니다. 이 값은 공유자의 콘텐츠 중 뷰어에 도달하지 못한 비율입니다. 공유자가 그래픽 원본에서 타일을 삭제하거나 ASMCU 타일이 각각의 공유자에서 타일을 삭제하면 콘텐츠가 삭제(또는 잘못됨)될 수 있습니다. 기본값은 11%입니다.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |decimal(5,2)  <br/> ||응용 프로그램 공유 품질을 분류하기 위한 "부실" 타일에 대한 허용 가능한 비율입니다. 이 값은 공유자의 콘텐츠 중 뷰어에 도달하지 못한 비율입니다. 공유자가 그래픽 원본에서 타일을 삭제하거나 ASMCU 타일이 각각의 공유자에서 타일을 삭제하면 콘텐츠가 삭제(또는 잘못됨)될 수 있습니다. 기본값은 36%입니다.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||이 열은 Microsoft Lync Server 2013에서 사용되지 않습니다.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||이 열은 Microsoft Lync Server 2013에서 사용되지 않습니다.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||이 열은 Microsoft Lync Server 2013에서 사용되지 않습니다.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||이 열은 Microsoft Lync Server 2013에서 사용되지 않습니다.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||이 열은 Microsoft Lync Server 2013에서 사용되지 않습니다.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||이 열은 Microsoft Lync Server 2013에서 사용되지 않습니다.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||응용 프로그램 공유에 포함된 두 개의 미디어 끝점 사이의 상대적 단방향 지연 시간에 대한 최적 값입니다. 이 값은 단일 홉 지연 시간 측정값입니다. 기본값은 1.0초입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||응용 프로그램 공유에 포함된 두 개의 미디어 끝점 사이의 상대적 단방향 지연 시간에 대한 최적 값입니다. 이 값은 단일 홉 지연 시간 측정값입니다. 기본값은 1.75초입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||보기 세션 기간 중 AS 회의 서버의 평균 RDP 타일 처리 지연 시간에 대한 최적 값입니다. 대기 시간은 시작 프레임이 서버에 인코딩되는 시간 차이(시나리오에 따라 공유자 또는 MCU)와 동일한 시작 프레임이 뷰어에서 디코딩되는 시간 차이입니다.  <br/> 평균 값이 높으면 보기 환경의 지연 시간이 길다는 것을 나타냅니다. 부하가 높은 회의 서버는 평균 대기 시간이 높을 수 있습니다. 기본값은 200ms입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||보기 세션 기간 중 AS 회의 서버의 평균 RDP 타일 처리 지연 시간에 대한 허용 가능한 값입니다. 대기 시간은 시작 프레임이 서버에 인코딩되는 시간 차이(시나리오에 따라 공유자 또는 MCU)와 동일한 시작 프레임이 뷰어에서 디코딩되는 시간 차이입니다.  <br/> 평균 값이 높으면 보기 환경의 지연 시간이 길다는 것을 나타냅니다. 부하가 높은 회의 서버는 평균 대기 시간이 높을 수 있습니다. 기본값은 200ms입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
   

