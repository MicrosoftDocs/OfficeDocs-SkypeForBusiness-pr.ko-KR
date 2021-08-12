---
title: Device 테이블
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
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: Device 테이블은 여러 캡처 또는 렌더링 장치에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 장치를 나타냅니다.
ms.openlocfilehash: d060ec010cc67ea45fb2f7c58ccc574a7bdbc4ea566342943f7a8f587a9676f5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347733"
---
# <a name="device-table"></a>Device 테이블
 
Device 테이블은 여러 캡처 또는 렌더링 장치에 대한 정보를 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 장치를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |이 장치를 식별하는 고유 번호입니다.  <br/> |
|**장치 이름** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType은 고유합니다.  <br/> |장치 이름입니다.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType은 고유합니다.  <br/> |장치 유형입니다. 1은 캡처 장치이고 0은 렌더링 장치입니다.  <br/> |
   

