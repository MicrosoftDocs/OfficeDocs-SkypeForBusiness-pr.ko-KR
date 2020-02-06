---
title: 비즈니스용 Skype 서버 2015의 장치 테이블
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
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: 장치 테이블은 지원 테이블입니다. 각 레코드는 한 장치 (일반 전화기)에 대 한 정보를 저장 합니다.
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815286"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 장치 테이블
 
장치 테이블은 지원 테이블입니다. 각 레코드는 한 장치 (일반 전화기)에 대 한 정보를 저장 합니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |주요한  <br/> |이 하드웨어 버전을 식별 하는 고유 번호입니다.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |외부  <br/> |이 장치에 대 한 제조업체입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 제조업체 표](manufacturers.md) 를 참조 하세요. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |외부  <br/> |이 장치에 대 한 하드웨어 버전. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 HardwareVersions 테이블](hardwareversions.md) 을 참조 하세요. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||MAC 주소  <br/> |
   

