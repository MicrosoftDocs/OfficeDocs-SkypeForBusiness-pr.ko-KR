---
title: UriTypes 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: UriTypes 테이블에는 비즈니스용 Skype 서버 2015에서 모니터링 하는 다양 한 URI (Uniform resource identifier) 형식이 포함 되어 있습니다.
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196677"
---
# <a name="uritypes-table"></a>UriTypes 테이블
 
UriTypes 테이블에는 비즈니스용 Skype 서버 2015에서 모니터링 하는 다양 한 URI (Uniform resource identifier) 형식이 포함 되어 있습니다.

CDR DB가 만들어지면 PhoneUri 및 UserUri를 나타내는 두 개의 레코드가 만들어지고 그 후에 생성 된 레코드가 UriTypeId에 동적으로 지정 됩니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |주요한  <br/> |URI 형식에 할당 된 고유 식별자입니다.  <br/> 사용할 수 있는 값-0 ~ 255 |
|**UriType** <br/> |nvarchar (256)  <br/> || 다양 한 URI 형식에 대 한 설명입니다. 미리 지정 된 값은 다음과 같습니다. <br/>  1-전화 Uri <br/>  0-사용자 Uri <br/> <br/>  다른 종류의 유형은 다음과 같습니다. <br/>회의: applicationsharing <br/> 회의: 오디오-영상<br/> 회의: 채팅<br/>    회의: 포커스<br/>   mras<br/>
