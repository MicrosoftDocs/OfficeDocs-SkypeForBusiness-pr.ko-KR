---
title: Device 테이블
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
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device 테이블은 여러 캡처 또는 렌더링 장치에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 장치를 나타냅니다.
ms.openlocfilehash: e999cf493cce69ee05d8a342e346cf8277d8d5d8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827421"
---
# <a name="device-table"></a>Device 테이블
 
Device 테이블은 여러 캡처 또는 렌더링 장치에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 장치를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |이 장치를 식별하는 고유 번호입니다.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType은 고유합니다.  <br/> |장치 이름입니다.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType은 고유합니다.  <br/> |장치 유형입니다. 1은 캡처 장치이고 0은 렌더링 장치입니다.  <br/> |
   

