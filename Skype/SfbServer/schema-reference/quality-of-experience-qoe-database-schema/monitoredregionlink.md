---
title: MonitoredRegionLink 테이블
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 테이블은 지원 테이블입니다. 각 레코드는 두 국가/지역 간의 하나의 링크를 나타내며,
ms.openlocfilehash: 0efac1d496889645ffb52db5c419397337ebf9f2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858105"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink 테이블
 
MonitoredRegionLink 테이블은 지원 테이블입니다. 각 레코드는 두 국가/지역 간의 하나의 링크를 나타내며,
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primary, Foreign  <br/> |[Region 테이블에서 참조됩니다.](region.md)  <br/> |
|**Region2Key** <br/> |int  <br/> |Primary, Foreign  <br/> |[Region 테이블에서 참조됩니다.](region.md)  <br/> |
   

