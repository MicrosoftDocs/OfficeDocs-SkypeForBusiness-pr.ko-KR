---
title: Endpoint 테이블
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Endpoint 테이블은 데이터베이스에 기록된 세션에 참가한 끝점에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 끝점을 나타내고
ms.openlocfilehash: 821f24ae2be38a699ce1c21255a66ec4a2fa2f17e448a1cc7b69a5a91d91d714
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302202"
---
# <a name="endpoint-table"></a>Endpoint 테이블
 
Endpoint 테이블은 데이터베이스에 기록된 세션에 참가한 끝점에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 끝점을 나타내고
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |이 끝점을 식별하는 고유 번호입니다.  <br/> |
|**이름** <br/> |nvarchar(256)  <br/> |Unique  <br/> |끝점 이름입니다.  <br/> |
|**OS** <br/> |nvarchar(128)  <br/> | <br/> |끝점의 운영 체제(OS)입니다.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||끝점의 CPU 이름입니다.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||끝점의 CPU 코어 수입니다.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||끝점의 CPU 프로세서 속도입니다.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || 시스템이 가상화된 환경에서 실행 중인지 나타내는 비트 플래그입니다. <br/>  0x0000 - 없음 <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - 가상 PC <br/>  0x0008 - Xen PC <br/> |
   

