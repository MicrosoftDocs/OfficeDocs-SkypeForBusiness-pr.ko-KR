---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie에는 현재 LDAP (Lightweight Directory Access Protocol) 동기화 쿠키가 포함 되어 있습니다.
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814706"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie에는 현재 LDAP (Lightweight Directory Access Protocol) 동기화 쿠키가 포함 되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID (null 아님)  <br/> |모니터링 중인 도메인의 Principal GUID입니다.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Active Directory 도메인 서비스 동기화에 사용 되는 현재 도메인 컨트롤러의 FQDN (정규화 된 도메인 이름)입니다. 정보 값이 있습니다.  <br/> |
|adcContent  <br/> |image (binary)  <br/> |Active Directory 동기화 쿠키입니다.  <br/> |
|lastUpdated 됨  <br/> |dmtf  <br/> |행 업데이트 시간이 포함 된 타임 스탬프입니다.  <br/> |
|lockedUntil  <br/> |dmtf  <br/> |행이 변경 내용에 맞게 잠길 때 까지의 시간입니다. 이는 채팅 서비스 중 하나만 Active Directory Sync를 한 번에 수행 하도록 하는 소프트웨어 연동 메커니즘의 일부입니다.  <br/> |
   
**핵심**

|**개 열**|**설명**|
|:-----|:-----|
|prinGuid  <br/> |기본 키입니다.  <br/> |
|prinGuid  <br/> |PrinGuid 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
   

