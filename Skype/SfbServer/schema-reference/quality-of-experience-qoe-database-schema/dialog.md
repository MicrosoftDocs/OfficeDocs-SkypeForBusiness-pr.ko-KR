---
title: Dialog 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog 테이블은 각 레코드가 하나의 SIP(Session Initiation Protocol) 대화를 나타내는 지원 테이블입니다.
ms.openlocfilehash: ab466a158ca059ff3110012a03e5c9c1e39b3d2d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851792"
---
# <a name="dialog-table"></a>Dialog 테이블
 
Dialog 테이블은 각 레코드가 하나의 SIP(Session Initiation Protocol) 대화를 나타내는 지원 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |QoE(체감 품질) 에이전트가 발신자 또는 수신자로부터 첫 번째 보고서를 받는 시간입니다. SessionSeq와 함께 세션을 고유하게 식별하기 위해 사용됩니다.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |ConferenceDateTime이 동일할 때 세션을 구분하기 위한 시퀀스 번호입니다.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||전역으로 고유한 대화 ID입니다.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |index  <br/> |대화 ID의 체크섬입니다.  <br/> |
   

