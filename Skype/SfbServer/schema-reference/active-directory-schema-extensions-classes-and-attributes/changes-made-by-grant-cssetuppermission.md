---
title: Grant-CsSetupPermission 변경한 비즈니스용 Skype 서버
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
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: 설치를 위임하려면 특정 Active Directory OU(조직 구성 단위)에 대한 RTCUniversalServerAdmins 유니버설 그룹에 사용 권한을 부여하여 해당 OU의 RTCUniversalServerAdmins 그룹의 구성원이 Domain Admins 그룹의 구성원이 아니어도 지정된 도메인에 비즈니스용 Skype 서버 설치하도록 할 수 있습니다.
ms.openlocfilehash: 32c0d48c5b6c63a38ff48e7808b8009c3ef265e6f0b6eb739094f797e47ace4d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349710"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>Grant-CsSetupPermission 변경한 비즈니스용 Skype 서버
 
설치를 위임하려면 특정 Active Directory OU(조직 구성 단위)에 대한 RTCUniversalServerAdmins 유니버설 그룹에 사용 권한을 부여하여 해당 OU의 RTCUniversalServerAdmins 그룹의 구성원이 Domain Admins 그룹의 구성원이 아니어도 지정된 도메인에 비즈니스용 Skype 서버 설치하도록 할 수 있습니다. 
  
**Grant-CsSetupPermission** cmdlet을 실행하면 다음 표에 지정된 것과 같이 OU의 RTCUniversalServerAdmins 그룹에 사용 권한을 부여할 수 있습니다.
  
**OU의 개체에 부여되는 사용 권한**

|**사용 권한의 적용 대상**|**부여받는 사용 권한**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | 특수 액세스 권한: <br/>  servicePrincipalName 읽기 <br/>  servicePrincipalName 쓰기 <br/>  트리 삭제 <br/>  디렉터리 변경 내용 복제 <br/> |
|하위 serviceConnectionPoint 개체  <br/> | 특수 액세스 권한: <br/>  사용 권한 읽기 <br/>  사용 권한 쓰기 <br/>  자식 항목 만들기 <br/>  자식 항목 삭제 <br/>  콘텐츠 나열 <br/>  속성 쓰기 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 msRTCSIP-Server 개체  <br/> | 특수 액세스 권한: <br/>  속성 쓰기 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 msRTCSIP-WebComponents 개체  <br/> | 특수 액세스 권한: <br/>  속성 쓰기 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 msRTCSIP-MCU 개체  <br/> | 특수 액세스 권한: <br/>  속성 쓰기 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 msRTCSIP-MediationServer 개체  <br/> | 특수 액세스 권한: <br/>  속성 쓰기 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 msRTCSIP-ApplicationServer 개체  <br/> | 특수 액세스 권한: <br/>  속성 쓰기 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 msRTCSIP-ConnectionPoint 개체  <br/> | 특수 액세스 권한: <br/>  속성 쓰기 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 Computer 개체  <br/> | serviceConnectionPoint에 대한 특수 액세스 권한: <br/>  자식 개체 만들기 <br/>  자식 개체 삭제 <br/>  트리 삭제 <br/>  공개 정보에 대한 특수 액세스 권한: <br/>  속성 읽기 <br/>  DNS 호스트 이름에 대한 특수 액세스 권한: <br/>  속성 읽기 <br/> |
   

