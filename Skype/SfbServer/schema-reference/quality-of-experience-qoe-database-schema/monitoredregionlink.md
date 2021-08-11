---
title: MonitoredRegionLink 테이블
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 테이블은 지원 테이블입니다. 각 레코드는 두 국가/지역 간의 하나의 링크를 나타내며,
ms.openlocfilehash: 991cc3b6ce2f442ad13c350d2e37cc7c9d592d40d16da51932975a4907040569
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321630"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink 테이블
 
MonitoredRegionLink 테이블은 지원 테이블입니다. 각 레코드는 두 국가/지역 간의 하나의 링크를 나타내며,
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Primary, Foreign  <br/> |[Region 테이블에서 참조됩니다.](region.md)  <br/> |
|**Region2Key** <br/> |int  <br/> |Primary, Foreign  <br/> |[Region 테이블에서 참조됩니다.](region.md)  <br/> |
   

