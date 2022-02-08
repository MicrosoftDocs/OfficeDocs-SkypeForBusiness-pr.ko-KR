---
title: Roles 테이블
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 38999dd3d90dc39ac2afea9c667224f73da7208c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394870"
---
# <a name="roles-table"></a>Roles 테이블
 
Roles 테이블은 참석자 및 발표자와 같은 가능한 회의 역할 목록을 저장하는 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**역할** <br/> |nvarchar(256)  <br/> || 허용되는 값 <br/>  0 - 알 수 없음 <br/>  1 - 발표자 <br/>  2 - 참석자 <br/> |
   

