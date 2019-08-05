---
title: SIPResponseMetaData 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable에는 SIP 응답 코드 목록과 각 코드의 분류 및 정의가 포함 되어 있습니다. 이러한 코드는 SIP 장치 및 SIP 통신 세션에 영향을 주는 이벤트에 대 한 응답으로 생성 됩니다. 예를 들어 응답 코드 403는 SIP 장치가 요청할 때 생성 되지만 서버는 해당 요청을 처리 하는 것을 거절 합니다.
ms.openlocfilehash: eecd8397315b93ebce9e5fad973f1274a6eb763a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196686"
---
# <a name="sipresponsemetadata-table"></a>SIPResponseMetaData 테이블
 
SIPResponseMetaDataTable에는 SIP 응답 코드 목록과 각 코드의 분류 및 정의가 포함 되어 있습니다. 이러한 코드는 SIP 장치 및 SIP 통신 세션에 영향을 주는 이벤트에 대 한 응답으로 생성 됩니다. 예를 들어 응답 코드 403는 SIP 장치가 요청할 때 생성 되지만 서버는 해당 요청을 처리 하는 것을 거절 합니다.
  
이 표는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |주요한  <br/> |SIP 응답 코드를 나타내는 숫자 값입니다.  <br/> |
|**클래스만** <br/> |int  <br/> || 응답 코드에 대 한 일반 분류입니다. 분류에는 다음이 포함 됩니다. <br/>  1-정보 응답 <br/>  2-성공 응답 <br/>  3-리디렉션 응답 <br/>  4-클라이언트 오류 응답 <br/>  5--서버 실패 응답 <br/>  6-전역 실패 응답 <br/> |
|**설명** <br/> |nvarchar (256)  <br/> ||SIP 응답 코드에 대 한 설명입니다. 예를 들어, 응답 코드 181에는 다음 설명이 포함 됩니다.  <br/> 착신 통화 전달 중  <br/> |
   

