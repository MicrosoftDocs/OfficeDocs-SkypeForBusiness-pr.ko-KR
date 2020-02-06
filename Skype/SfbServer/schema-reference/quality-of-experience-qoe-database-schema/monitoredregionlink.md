---
title: MonitoredRegionLink 테이블
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: Monitored국가 링크 테이블은 지원 테이블입니다. 각 레코드는 두 국가/지역 간의 하나의 링크를 나타냅니다.
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807816"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink 테이블
 
Monitored국가 링크 테이블은 지원 테이블입니다. 각 레코드는 두 국가/지역 간의 하나의 링크를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |기본, 외래  <br/> |[지역 테이블](region.md)에서 참조 됩니다.  <br/> |
|**Region2Key** <br/> |int  <br/> |기본, 외래  <br/> |[지역 테이블](region.md)에서 참조 됩니다.  <br/> |
   

