---
title: 2015년 비즈니스용 Skype 서버 Mcus 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 테이블은 지원 테이블입니다. 각 레코드에는 하나의 회의 서비스에 대한 정보가 저장됩니다. 여기에는 IM 회의 서비스 및 전화 통신 회의 서비스(프런트 엔드 서버에서 프로세스로 실행) 및 웹 회의 서비스 및 A/V 회의 서비스가 포함됩니다.
ms.openlocfilehash: abbbe20d6b247b23f0042dcc3bf552dd4a1362f1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846311"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 Mcus 테이블
 
Mcus 테이블은 지원 테이블입니다. 각 레코드에는 하나의 회의 서비스에 대한 정보가 저장됩니다. 여기에는 IM 회의 서비스 및 전화 통신 회의 서비스(프런트 엔드 서버에서 프로세스로 실행) 및 웹 회의 서비스 및 A/V 회의 서비스가 포함됩니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |이 회의 서버를 식별하는 고유 번호입니다.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | 외계인 <br/> |회의 서버 유형(예: conf:chat(IM용) 또는 conf:audio-video) 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
   

