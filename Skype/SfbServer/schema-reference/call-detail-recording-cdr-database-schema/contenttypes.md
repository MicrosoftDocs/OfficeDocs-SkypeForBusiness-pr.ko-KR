---
title: 2015년 비즈니스용 Skype 서버 ContentTypes 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes 테이블은 피어-투-피어 세션 및 회의 세션에 사용되는 콘텐츠 유형 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 콘텐츠 유형을 나타냅니다.
ms.openlocfilehash: ca6497cad38c6e4e59f4da725ab03b8d027f2d93
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827401"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 ContentTypes 테이블
 
ContentTypes 테이블은 피어-투-피어 세션 및 회의 세션에 사용되는 콘텐츠 유형 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 콘텐츠 유형을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ContentTypeId** <br/> |int  <br/> |Primary  <br/> |콘텐츠 유형을 식별하는 고유 번호입니다.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> ||콘텐츠 유형 이름입니다.  <br/> |
   

