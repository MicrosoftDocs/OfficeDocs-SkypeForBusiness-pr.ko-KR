---
title: VideoMetricsThreshold 테이블
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
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: VideoMetricsThreshold 테이블은 비디오 통화에 사용되는 체감 품질 메트릭에 대한 최적의 값과 적절한 값을 포함합니다.
ms.openlocfilehash: 1885e1d5bfbea10ffed518aaedcc8bf47a2b5217c333c187eaf2a2ee0dc7b0d2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340004"
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold 테이블
 
VideoMetricsThreshold 테이블은 비디오 통화에 사용되는 체감 품질 메트릭에 대한 최적의 값과 적절한 값을 포함합니다.
  

| **열**                                               | **데이터 형식**       | **키/인덱스**  | **세부 정보**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | Primary  <br/> | 건 전화의 유형입니다.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal(5,2)  <br/> |                | 기본값은 0.05입니다.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal(5,2)  <br/> |                | 기본값은 0.10입니다.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal(5,2)  <br/> |                | 기본값은 5.0입니다.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal(5,2)  <br/> |                | 기본값은 10.0입니다.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | decimal(9,4)  <br/> |                | 기본값은 12.0000입니다.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | decimal(9,4)  <br/> |                | 기본값은 7.0000입니다.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal(5,2)  <br/> |                | 기본값은 5.0입니다.  <br/>     |
| \****LowFrameRateCallPercentAcceptable** _\_ <br/>        | decimal(5,2)  <br/> |                | 기본값은 10.0입니다.  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | 기본값은 5.0입니다.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | 기본값은 10.0입니다.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | 기본값은 0.05입니다.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | 기본값은 0.10입니다.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | 기본값은 12입니다.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | 기본값은 7입니다.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal(5,2)  <br/> |                | 기본값은 5.00입니다.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal(5,2)  <br/> |                | 기본값은 10.00입니다.  <br/>   |

