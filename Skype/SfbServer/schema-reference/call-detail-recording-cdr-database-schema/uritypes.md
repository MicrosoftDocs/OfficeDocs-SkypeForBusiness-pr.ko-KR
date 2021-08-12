---
title: UriTypes 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes Table에는 2015년 8월에 모니터링되는 서로 다른 URI(uniform resource identifier) 유형이 비즈니스용 Skype 서버 있습니다.
ms.openlocfilehash: 1e98bc879e7ddb6e2ca92d4f226284e604d22d312f9e2db8c0ff80cad89c33e5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295365"
---
# <a name="uritypes-table"></a>UriTypes 테이블
 
UriTypes Table에는 2015년 8월에 모니터링되는 서로 다른 URI(uniform resource identifier) 유형이 비즈니스용 Skype 서버 있습니다.

CDR DB를 만들면 PhoneUri 및 UserUri를 나타내는 두 개의 레코드가 만들어지며 그 이후에 만들어진 레코드는 동적으로 할당된 UriTypeId입니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |URI 유형에 지정된 고유 식별자입니다.  <br/> 가능한 값 - 0 ~255 |
|**UriType** <br/> |nvarchar(256)  <br/> || 다른 URI 유형에 대한 설명입니다. 다음 값은 미리 할당됩니다. <br/>  1 - 전화 Uri <br/>  0 - 사용자 Uri <br/> <br/>  기타 가능한 유형은 다음과 같습니다. <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
