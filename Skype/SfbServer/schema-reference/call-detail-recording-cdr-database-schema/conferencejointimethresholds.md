---
title: 비즈니스용 Skype 서버 2015의 ConferenceJoinTimeThresholds 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 테이블에는 컨퍼런스 참가 시간 요약 보고서에 사용 되는 분류 경계가 포함 되어 있습니다. 컨퍼런스 참가 시간 요약 보고서에는 사용자가 회의에 참가 하는 데 필요한 시간 시간이 요약 되어 있습니다. 이러한 시간 값은 다음 범주 중 하 나와 평균으로 보고 됩니다.
ms.openlocfilehash: 1874a94448be5957079b1c53944bc127df761e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815396"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 ConferenceJoinTimeThresholds 테이블
 
ConferenceJoinTimeThresholds 테이블에는 컨퍼런스 참가 시간 요약 보고서에 사용 되는 분류 경계가 포함 되어 있습니다. 컨퍼런스 참가 시간 요약 보고서에는 사용자가 회의에 참가 하는 데 필요한 시간 시간이 요약 되어 있습니다. 이러한 시간 값은 다음 범주 중 하 나와 평균으로 보고 됩니다.
  
- 2 초 미만.
    
- 2 초에서 5 초 사이입니다.
    
- 5 초에서 10 초 사이입니다.
    
- 10 초 이상
    
ConferenceJoinTimeThresholds 테이블에는 2 초, 5 초 및 10 초의 분류 값이 포함 됩니다.
  
이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |주요한  <br/> |분류의 고유 식별자입니다.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || 분류에 대 한 상한 값입니다. 사용 가능한 값은 다음과 같습니다. <br/>  2 <br/>  5mb <br/>  1천만 <br/> |
   

