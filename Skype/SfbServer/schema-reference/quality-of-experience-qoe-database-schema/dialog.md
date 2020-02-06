---
title: Dialog 테이블
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
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: 대화 상자 테이블은 지원 테이블입니다. 각 레코드는 하나의 SIP (세션 초기화 프로토콜) 대화 상자를 나타냅니다.
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809536"
---
# <a name="dialog-table"></a>Dialog 테이블
 
대화 상자 테이블은 지원 테이블입니다. 각 레코드는 하나의 SIP (세션 초기화 프로토콜) 대화 상자를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dmtf  <br/> |주요한  <br/> |체감 품질 (고급 품질) 에이전트가 호출자 또는 호출 수신자 중 첫 번째 보고서를 받는 시간입니다. 세션을 고유 하 게 식별 하는 SessionSeq와 함께 사용 됩니다.  <br/> |
|**SessionSeq** <br/> |int  <br/> |주요한  <br/> |동일한 ConferenceDateTime 있을 때 세션을 구분 하는 시퀀스 번호입니다.  <br/> |
|**DialogID** <br/> |varchar (256)  <br/> ||전역으로 고유한 대화 상자 ID입니다.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |색인  <br/> |대화 상자 ID의 체크섬입니다.  <br/> |
   

