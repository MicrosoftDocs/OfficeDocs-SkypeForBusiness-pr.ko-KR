---
title: DeviceDriver 테이블
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
ms.localizationpriority: medium
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: DeviceDriver 테이블은 지원 테이블입니다. 각 레코드는 캡처 장치 또는 렌더링 장치에서 사용되는 드라이버를 나타냅니다.
ms.openlocfilehash: 1dc316d68903455de03c2d1f5ace461f5eef478f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603787"
---
# <a name="devicedriver-table"></a>DeviceDriver 테이블
 
DeviceDriver 테이블은 지원 테이블입니다. 각 레코드는 캡처 장치 또는 렌더링 장치에서 사용되는 드라이버를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**DeviceDriverKey** <br/> |int  <br/> |Primary  <br/> |이 장치 드라이버 레코드를 식별하는 고유 번호입니다.  <br/> |
|**DeviceDriver** <br/> |varchar(256)  <br/> |unique  <br/> |장치 드라이버 이름입니다.  <br/> |
   

