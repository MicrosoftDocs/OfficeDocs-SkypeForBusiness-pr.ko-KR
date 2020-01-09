---
title: MediaList 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 테이블은 다양 한 미디어 유형의 목록을 저장 하는 정적 테이블입니다.
ms.openlocfilehash: 243fd3fb705826584f4e786441cdc1faa9075777
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992928"
---
# <a name="medialist-table"></a>MediaList 테이블
 
MediaList 테이블은 다양 한 미디어 유형의 목록을 저장 하는 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |주요한  <br/> |값: 1-7  <br/> |
|**미디어** <br/> |nvarchar (256)  <br/> || MediaID 및 Media 값의 정적 매핑: <br/>  1--메신저 대화 <br/>  2-파일 전송 <br/>  3-원격 지원 <br/>  4-응용 프로그램 공유 <br/>  5--오디오 <br/>  6--영상 <br/>  7-앱 초대 <br/> |
   
LcsCDR에서 MediaTypes의 값에 대 한 형식 지정을 확인 하려는 경우 다음 조인 조각을 사용 해야 합니다. 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
