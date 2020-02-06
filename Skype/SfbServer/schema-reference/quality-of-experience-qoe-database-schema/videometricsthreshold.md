---
title: VideoMetricsThreshold 테이블
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
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: VideoMetricsThreshold 테이블에는 영상 통화에 사용 되는 경력 메트릭의 품질에 적합 한 값이 포함 되어 있습니다.
ms.openlocfilehash: 89d3095ef7222cacc7633116c43d66cbcc2be2e2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804738"
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold 테이블
 
VideoMetricsThreshold 테이블에는 영상 통화에 사용 되는 경력 메트릭의 품질에 적합 한 값이 포함 되어 있습니다.
  

| **열**                                               | **데이터 형식**       | **키/인덱스**  | **세부적인**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | 주요한  <br/> | 배치 된 통화 유형입니다.  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | 10 진수 (5, 2)  <br/> |                | 기본값은 0.05입니다.  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | 10 진수 (5, 2)  <br/> |                | 기본값은 0.10입니다.  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | 10 진수 (5, 2)  <br/> |                | 기본값은 5.0입니다.  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | 10 진수 (5, 2)  <br/> |                | 기본값은 10.0입니다.  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | 10 진수 (9, 4)  <br/> |                | 기본값은 12.0000입니다.  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | 10 진수 (9, 4)  <br/> |                | 기본값은 7.0000입니다.  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | 10 진수 (5, 2)  <br/> |                | 기본값은 5.0입니다.  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | 10 진수 (5, 2)  <br/> |                | 기본값은 10.0/  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | 10 진수 (5, 2)  <br/> |                | 기본값은 5.0입니다.  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | 10 진수 (5, 2)  <br/> |                | 기본값은 10.0입니다.  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | 에  <br/>         |                | 기본값은 0.05입니다.  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | o  <br/>        |                | 기본값은 0.10입니다.  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | o  <br/>        |                | 기본값은 12입니다.  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | o  <br/>        |                | 기본값은 7입니다.  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | 10 진수 (5, 2)  <br/> |                | 기본값은 5.00입니다.  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | 10 진수 (5, 2)  <br/> |                | 기본값은 10.00입니다.  <br/>   |

