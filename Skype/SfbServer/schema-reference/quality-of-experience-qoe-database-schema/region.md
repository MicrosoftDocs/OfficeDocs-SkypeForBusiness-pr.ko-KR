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
localization_priority: Normal
ms.assetid: 1751a6aa-a6e8-4f16-8eb7-ae731c2e3ee3
description: Region 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 국가/지역을 나타냅니다.
ms.openlocfilehash: 538d574037d7cd3798b63c6d8773f99e1c376d9f5ad115f73bfa725a9aec6b55
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341663"
---
# <a name="region-table"></a>Region 테이블
 
Region 테이블은 지원 테이블입니다. 각 레코드는 네트워크 구성 설정에 정의된 하나의 국가/지역을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**RegionKey** <br/> |int  <br/> |Primary  <br/> |국가/지역을 식별하는 고유 번호입니다.  <br/> |
|**RegionName** <br/> |nvarchar(128)  <br/> |Unique  <br/> |국가/지역의 이름입니다.  <br/> |
   

