---
title: 2015년 비즈니스용 Skype 서버 회의 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: 이 표의 각 레코드에는 한 회의에 대한 통화 정보가 포함되어 있습니다.
ms.openlocfilehash: 22d394ca447852a32d8028770d7ceefea7adbcf1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763416"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 회의 테이블
 
이 표의 각 레코드에는 한 회의에 대한 통화 정보가 포함되어 있습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |CDR 에이전트가 회의 요청을 캡처한 시간입니다. 회의 인스턴스를 고유하게 식별하기 위해 기본 키로만 사용됩니다.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |세션을 식별하기 위한 ID 번호입니다. **SessionIdTime과** 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |외계인  <br/> |회의 URI입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ConferenceUris 테이블을](conferenceuris.md) 참조하세요. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |재발 회의에 유용합니다. 재발 회의의 각 인스턴스는 **ConferenceUri가** 같지만 **ConfInstance는 다릅니다.** <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |회의 시작 시간입니다.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |회의 시작 시간입니다.  <br/> |
|**PoolId** <br/> |int  <br/> |외계인  <br/> |회의가 캡처된 풀을 식별하기 위한 ID 번호입니다. 자세한 내용은 [Pools 테이블을](pools.md) 참조하십시오. <br/> |
|**OrganizerId** <br/> |임계값  <br/> |외계인  <br/> |이 회의의 이끌이 URI를 식별하는 ID 번호입니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**플래그** <br/> |smallint  <br/> || 회의 특성을 포함하는 비트 마스크입니다. 가능한 값은 다음과 같습니다. <br/>  0X01 <br/>  가상 <br/>  트랜잭션 <br/> |
|**처리** <br/> |bit  <br/> ||모니터링 서비스에서 사용하는 내부 필드입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||모니터링 서비스의 내부 사용 용도  <br/> 이 필드는 2015년 비즈니스용 Skype 서버 도입했습니다.  <br/> |
   
\* 대부분의 세션에서 SessionIdSeq의 값은 1입니다. 두 세션이 정확히 동시에 시작될 경우 한 세션의 SessionIdSeq는 1이 1이 며, 다른 세션은 2가 됩니다.
  

