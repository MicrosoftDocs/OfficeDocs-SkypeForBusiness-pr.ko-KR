---
title: 비즈니스용 Skype 서버의 ConferenceJoinTimeThresholds 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 테이블에는 회의 참가 시간 요약 보고서에서 사용하는 분류 경계가 포함됩니다. 회의 참가 시간 요약 보고서에는 사용자가 회의에 정상적으로 참가하는 데 걸리는 시간이 요약되어 있습니다. 이러한 시간 값은 평균 및 다음 범주 중 하나로 보고됩니다.
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813308"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버의 ConferenceJoinTimeThresholds 테이블
 
ConferenceJoinTimeThresholds 테이블에는 회의 참가 시간 요약 보고서에서 사용하는 분류 경계가 포함됩니다. 회의 참가 시간 요약 보고서에는 사용자가 회의에 정상적으로 참가하는 데 걸리는 시간이 요약되어 있습니다. 이러한 시간 값은 평균 및 다음 범주 중 하나로 보고됩니다.
  
- 2초 미만
    
- 2~5초
    
- 5~10초
    
- 10초 초과
    
ConferenceJoinTimeThresholds 테이블에는 분류 값 2초, 5초, 10초가 포함됩니다.
  
이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primary  <br/> |분류의 고유한 식별자입니다.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || 분류의 상한입니다. 허용되는 값은 다음과 같습니다. <br/>  2  <br/>  5  <br/>  10   <br/> |
   

