---
title: Device 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: 장치 테이블은 다양 한 캡처 또는 렌더링 장치에 대 한 정보를 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 장치를 나타냅니다.
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196574"
---
# <a name="device-table"></a>Device 테이블
 
장치 테이블은 다양 한 캡처 또는 렌더링 장치에 대 한 정보를 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 장치를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |주요한  <br/> |이 장치를 식별 하는 고유 번호입니다.  <br/> |
|**이름** <br/> |nvarchar (256)  <br/> |장치 이름 + DeviceType는 고유 합니다.  <br/> |장치 이름입니다.  <br/> |
|**DeviceType** <br/> |다소  <br/> |장치 이름 + DeviceType는 고유 합니다.  <br/> |장치 유형. 1은 캡처 장치이 고 0은 렌더링 장치입니다.  <br/> |
   

