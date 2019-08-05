---
title: Roles 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: '역할 테이블은 가능한 컨퍼런스 역할 목록 (예: 참석자 및 발표자)을 저장 하는 정적 테이블입니다.'
ms.openlocfilehash: 2cf1fb22230d92951df0b3b8e18a5bd666c73519
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196694"
---
# <a name="roles-table"></a>Roles 테이블
 
역할 테이블은 가능한 컨퍼런스 역할 목록 (예: 참석자 및 발표자)을 저장 하는 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |주요한  <br/> ||
|**역할인** <br/> |nvarchar (256)  <br/> || 허용 되는 값: <br/>  0-알 수 없음 <br/>  1-발표자 <br/>  2-참석자 <br/> |
   

