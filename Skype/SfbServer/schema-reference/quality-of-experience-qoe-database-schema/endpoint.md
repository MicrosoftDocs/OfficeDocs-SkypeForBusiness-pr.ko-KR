---
title: Endpoint 테이블
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: 끝점 테이블은 데이터베이스에 기록 된 세션에 참가 한 끝점에 대 한 정보를 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 끝점을 나타냅니다.
ms.openlocfilehash: b64b19a3149fa3d490ea8dc957699c0a114f763c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809556"
---
# <a name="endpoint-table"></a>Endpoint 테이블
 
끝점 테이블은 데이터베이스에 기록 된 세션에 참가 한 끝점에 대 한 정보를 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 끝점을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |주요한  <br/> |이 끝점을 식별 하는 고유 번호입니다.  <br/> |
|**이름** <br/> |nvarchar (256)  <br/> |독특한  <br/> |끝점 이름입니다.  <br/> |
|**변경할** <br/> |name  <br/> | <br/> |끝점의 OS (운영 체제)입니다.  <br/> |
|**CPUName** <br/> |name  <br/> ||끝점의 CPU 이름입니다.  <br/> |
|**Cpunum Of코어** <br/> |smallint  <br/> ||끝점의 CPU 코어 수입니다.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||끝점의 CPU 프로세서 속도입니다.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || 시스템이 가상화 된 환경에서 실행 되 고 있는지를 나타내는 비트 플래그입니다. <br/>  0x0000e-없음 <br/>  0x0001-HyperV <br/>  0x0002-VMWare <br/>  0x0004-가상 PC <br/>  0x0008-Xen PC <br/> |
   

