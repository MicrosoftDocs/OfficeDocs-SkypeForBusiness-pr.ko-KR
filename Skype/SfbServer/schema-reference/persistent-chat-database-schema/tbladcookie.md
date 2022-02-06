---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie에는 현재 LDAP(Lightweight Directory Access Protocol) 동기화 쿠키가 포함됩니다.
---

# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie에는 현재 LDAP(Lightweight Directory Access Protocol) 동기화 쿠키가 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, null이 아님  <br/> |모니터링 중인 도메인의 사용자 GUID입니다.  <br/> |
|prinDCHost  <br/> |nvarchar(255)  <br/> |Active Directory 도메인 서비스 동기화에 사용되는 현재 도메인 컨트롤러의 FQDN(정식 도메인 이름)입니다. 정보 값이 있습니다.  <br/> |
|adcContent  <br/> |image(바이너리)  <br/> |Active Directory 동기화 쿠키입니다.  <br/> |
|lastUpdated  <br/> |datetime  <br/> |행 업데이트 시간이 포함된 타임스탬프입니다.  <br/> |
|lockedUntil  <br/> |datetime  <br/> |변경할 수 없도록 행이 잠길 때까지의 시간입니다. 이 방식은 한 번에 하나의 채팅 서비스만 Active Directory 동기화를 수행할 수 있도록 보장하는 소프트웨어 내부 잠금 메커니즘입니다.  <br/> |
   
**키**

|**Column(s)**|**설명**|
|:-----|:-----|
|prinGuid  <br/> |기본 키입니다.  <br/> |
|prinGuid  <br/> |Principal.prinGuid 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

