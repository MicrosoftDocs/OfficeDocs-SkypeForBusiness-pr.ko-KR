---
title: 비즈니스용 Skype 서버 2015의 컨퍼런스 표
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: 이 테이블의 각 레코드에는 한 회의에 대 한 통화 정보가 포함 됩니다.
ms.openlocfilehash: 41a2a25e80b073b568152422defeee1ca3e2ac19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196777"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 컨퍼런스 표
 
이 테이블의 각 레코드에는 한 회의에 대 한 통화 정보가 포함 됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |주요한  <br/> |전화 회의 요청이 CDR 에이전트에 의해 캡처 된 시간입니다. 회의 인스턴스를 고유 하 게 식별 하는 기본 키로만 사용 됩니다.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |주요한  <br/> |세션을 식별 하는 ID 번호입니다. 회의 인스턴스를 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |외부  <br/> |회의 URI. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 ConferenceUris 테이블](conferenceuris.md) 을 참조 하세요. <br/> |
|**인스턴스** <br/> |uniqueidentifier  <br/> | <br/> |되풀이 회의에 유용 합니다. 각 되풀이 회의의 각 인스턴스는 동일한 **ConferenceUri**를 가지 지만 다양 한 다른 **인스턴스**를 보유 하 게 됩니다. <br/> |
|**ConferenceStartTime** <br/> |dmtf  <br/> | <br/> |회의 시작 시간.  <br/> |
|**ConferenceEndTime** <br/> |dmtf  <br/> | <br/> |회의 시작 시간.  <br/> |
|**PoolId** <br/> |int  <br/> |외부  <br/> |회의를 캡처한 풀을 식별 하는 ID 번호입니다. 자세한 내용은 [풀 테이블](pools.md) 을 참조 하세요. <br/> |
|**OrganizerId** <br/> |Int  <br/> |외부  <br/> |이 컨퍼런스의 이끌이 URI를 식별 하는 ID 번호입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**플래그** <br/> |smallint  <br/> || 컨퍼런스 특성을 포함 하는 비트 마스크입니다. 사용할 수 있는 값은 다음과 같습니다. <br/>  0X01 <br/>  종합적인 <br/>  트랜잭션과 <br/> |
|**처리** <br/> |다소  <br/> ||모니터링 서비스에서 사용 하는 내부 필드입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**LastModifiedTime** <br/> |Dmtf  <br/> ||모니터링 서비스에 내부적으로 사용 합니다.  <br/> 이 필드는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.  <br/> |
   
\*대부분의 세션에서 SessionIdSeq에는 값 1이 사용 됩니다. 두 세션이 정확히 동시에 시작 되 면 1에 대 한 SessionIdSeq는 1이 되 고 다른 하나는 2가 됩니다.
  

