---
title: 회의 보기
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: 회의 보기에는 회의에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
---

# <a name="conferences-view"></a>회의 보기
 
회의 보기에는 회의에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |세션 요청 시간입니다. SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs 테이블](dialogs.md)을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |세션을 식별하기 위한 ID 번호입니다. SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs 테이블](dialogs.md)을 참조하십시오. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |회의의 URI입니다.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |회의 URI의 형식입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조하십시오. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |되풀이 회의에 유용합니다. 되풀이 회의의 각 인스턴스에는 동일한 ConferenceUri가 포함되지만 ConfInstance가 서로 다릅니다.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |회의의 시작 날짜입니다.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |회의의 종료 날짜입니다.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |회의를 구성한 사용자의 URI입니다.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |회의를 구성한 사용자의 URI 형식입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조하십시오. <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |회의를 구성한사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블](tenants.md) 을 참조하세요. <br/> |
|**풀** <br/> |nvarchar(256)  <br/> |회의를 호스팅한 풀의 정규화된 도메인 이름입니다  <br/> |
|**플래그** <br/> |smallint  <br/> |회의 특성을 포함하는 비트 마스크입니다. 사용할 수 있는 값은 다음과 같습니다.  <br/> 0X01 - 가상 트랜잭션  <br/> |
   

