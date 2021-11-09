---
title: DeviceDriver 테이블
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: DeviceDriver 테이블은 지원 테이블입니다. 각 레코드는 캡처 장치 또는 렌더링 장치에서 사용되는 드라이버를 나타냅니다.
ms.openlocfilehash: 3ca0a88e90b0183bf35c4c84675db5b3327d52ee
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857175"
---
# <a name="devicedriver-table"></a>DeviceDriver 테이블
 
DeviceDriver 테이블은 지원 테이블입니다. 각 레코드는 캡처 장치 또는 렌더링 장치에서 사용되는 드라이버를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**DeviceDriverKey** <br/> |int  <br/> |Primary  <br/> |이 장치 드라이버 레코드를 식별하는 고유 번호입니다.  <br/> |
|**DeviceDriver** <br/> |varchar(256)  <br/> |unique  <br/> |장치 드라이버 이름입니다.  <br/> |
   

