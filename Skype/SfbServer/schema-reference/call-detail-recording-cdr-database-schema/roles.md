---
title: Roles 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Roles 테이블은 참석자 및 발표자와 같은 가능한 회의 역할 목록을 저장하는 정적 테이블입니다.
ms.openlocfilehash: 56582f5f90693f4156f050ff20558a2bac440b8f531f8ee0076b258755f0fa26
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302272"
---
# <a name="roles-table"></a>Roles 테이블
 
Roles 테이블은 참석자 및 발표자와 같은 가능한 회의 역할 목록을 저장하는 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**역할** <br/> |nvarchar(256)  <br/> || 허용되는 값 <br/>  0 - 알 수 없음 <br/>  1 - 발표자 <br/>  2 - 참석자 <br/> |
   

