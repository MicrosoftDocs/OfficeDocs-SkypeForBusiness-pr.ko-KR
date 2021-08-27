---
title: Region 테이블
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
ms.assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
description: Region 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 국가/지역을 나타냅니다.
ms.openlocfilehash: ba0937fba73810fce834a6da7472315147fbd501
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578572"
---
# <a name="region-table"></a>Region 테이블
 
Region 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 국가/지역을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**RegionKey** <br/> |int  <br/> |Primary  <br/> |국가/지역을 식별하는 고유 번호입니다.  <br/> |
|**RegionName** <br/> |nvarchar(128)  <br/> |Unique  <br/> |국가/지역의 이름입니다.  <br/> |
   

