---
title: Roles 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Roles 테이블은 참석자 및 발표자와 같은 가능한 회의 역할 목록을 저장하는 정적 테이블입니다.
ms.openlocfilehash: 2bd15fd98aff2ce8066a396efac0b538d4891a8f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776158"
---
# <a name="roles-table"></a>Roles 테이블
 
Roles 테이블은 참석자 및 발표자와 같은 가능한 회의 역할 목록을 저장하는 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**역할** <br/> |nvarchar(256)  <br/> || 허용되는 값 <br/>  0 - 알 수 없음 <br/>  1 - 발표자 <br/>  2 - 참석자 <br/> |
   

