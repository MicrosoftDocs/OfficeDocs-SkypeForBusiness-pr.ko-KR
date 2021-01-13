---
title: 비즈니스용 Skype 서버의 Devices 테이블
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
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices 테이블은 지원 테이블입니다. 각 레코드에는 하나의 장치(일반 전화)에 대한 정보가 저장됩니다.
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831818"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버의 Devices 테이블
 
Devices 테이블은 지원 테이블입니다. 각 레코드에는 하나의 장치(일반 전화)에 대한 정보가 저장됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |이 하드웨어 버전을 식별하는 고유 번호입니다.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |외계인  <br/> |이 장치의 제조업체입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Manufacturers](manufacturers.md) 테이블을 참조하세요. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |외계인  <br/> |이 장치의 하드웨어 버전입니다. 자세한 내용은 비즈니스용 [Skype 서버 2015의 HardwareVersions](hardwareversions.md) 테이블을 참조하세요. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC 주소  <br/> |
   

