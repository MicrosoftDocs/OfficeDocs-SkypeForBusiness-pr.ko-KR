---
title: 비즈니스용 Skype 서버 2015의 ContentTypes 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes 테이블은 피어 투 피어 세션과 회의 세션에 사용 되는 콘텐츠 형식의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 한 가지 콘텐츠 형식을 나타냅니다.
ms.openlocfilehash: 6dadf7de0107005cca751e27f0c0250bc8f9f03a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815306"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 ContentTypes 테이블
 
ContentTypes 테이블은 피어 투 피어 세션과 회의 세션에 사용 되는 콘텐츠 형식의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 한 가지 콘텐츠 형식을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |주요한  <br/> |콘텐츠 형식을 식별 하는 고유 번호입니다.  <br/> |
|**ContentType** <br/> |nvarchar (256)  <br/> ||콘텐츠 형식 이름입니다.  <br/> |
   

