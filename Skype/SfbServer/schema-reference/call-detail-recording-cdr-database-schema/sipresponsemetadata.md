---
title: SIPResponseMetaData 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable에는 SIP 응답 코드 목록과 이러한 각 코드의 분류 및 정의가 포함되어 있습니다. 이러한 코드는 SIP 장치 및 SIP 통신 세션에 영향을 주는 이벤트에 대한 응답으로 생성됩니다. 예를 들어 응답 코드 403은 SIP 장치가 요청을 할 때 생성되지만 서버는 해당 요청을 수락하지 않습니다.
ms.openlocfilehash: acf2c3166628af3a4633e98713ca25a5ae703ff6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863395"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData 테이블
 
SIPResponseMetaDataTable에는 SIP 응답 코드 목록과 이러한 각 코드의 분류 및 정의가 포함되어 있습니다. 이러한 코드는 SIP 장치 및 SIP 통신 세션에 영향을 주는 이벤트에 대한 응답으로 생성됩니다. 예를 들어 응답 코드 403은 SIP 장치가 요청을 할 때 생성되지만 서버는 해당 요청을 수락하지 않습니다.
  
이 표는 2015년 비즈니스용 Skype 서버 도입했습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |SIP 응답 코드를 나타내는 숫자 값입니다.  <br/> |
|**클래스** <br/> |int  <br/> || 응답 코드에 대한 일반 분류입니다. 분류에는 다음이 포함됩니다. <br/>  1 - 정보 응답 <br/>  2 - 성공 응답 <br/>  3 - 리디렉션 응답 <br/>  4 - 클라이언트 오류 응답 <br/>  5 -- 서버 오류 응답 <br/>  6 - 전역 오류 대응 <br/> |
|**설명** <br/> |nvarchar(256)  <br/> ||SIP 응답 코드에 대한 설명입니다. 예를 들어 응답 코드 181에는 다음 설명이 있습니다.  <br/> 통화가 전달되고 있습니다.  <br/> |
   

