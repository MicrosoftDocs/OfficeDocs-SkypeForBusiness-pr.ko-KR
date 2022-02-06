---
title: 2015년 비즈니스용 Skype 서버 Devices 테이블
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: Devices 테이블은 지원 테이블입니다. 각 레코드에는 하나의 장치(일반 전화)에 대한 정보가 저장됩니다.
---

# <a name="devices-table-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 Devices 테이블
 
Devices 테이블은 지원 테이블입니다. 각 레코드에는 하나의 장치(일반 전화)에 대한 정보가 저장됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |이 하드웨어 버전을 식별하는 고유 번호입니다.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |외계인  <br/> |이 장치의 제조업체입니다. 자세한 [내용은 비즈니스용 Skype 서버 2015의 Manufacturers 테이블](manufacturers.md)을 참조하십시오. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |외계인  <br/> |이 장치의 하드웨어 버전입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 HardwareVersions 테이블](hardwareversions.md)을 참조하세요. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC 주소  <br/> |
   

