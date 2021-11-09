---
title: MediaList 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 테이블은 다양한 미디어 유형 목록이 저장된 정적 테이블입니다.
ms.openlocfilehash: 643c373eb7e6a73cf8755f14ea0f5497efee6fed
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849631"
---
# <a name="medialist-table"></a>MediaList 테이블
 
MediaList 테이블은 다양한 미디어 유형 목록이 저장된 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |값: 1-7  <br/> |
|**미디어** <br/> |nvarchar(256)  <br/> || MediaID 및 Media 값의 정적 매핑: <br/>  1 -- IM <br/>  2 - 파일 전송 <br/>  3 - 원격 지원 <br/>  4 - 응용 프로그램 공유 <br/>  5 -- 오디오 <br/>  6 -- 비디오 <br/>  7 - 앱 초대 <br/> |
   
LcsCDR.SessionDetailsView.MediaTypes의 값에 대한 형식 형식을 확인하려는 경우 다음 조인 코드만 사용해야 합니다. 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
