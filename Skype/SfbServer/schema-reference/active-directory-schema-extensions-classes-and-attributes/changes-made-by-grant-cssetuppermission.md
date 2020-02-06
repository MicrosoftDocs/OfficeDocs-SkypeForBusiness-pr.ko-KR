---
title: 비즈니스용 Skype 서버에서-Cssetupsetuppermission 허용에의 한 변경 내용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: 설치를 위임 하려면 특정 Active Directory OU (조직 구성 단위)에 대 한 RTCUniversalServerAdmins 유니버설 그룹에 대 한 사용 권한을 부여 하 여 해당 OU에 있는 RTCUniversalServerAdmins 그룹의 구성원이 비즈니스용 Skype Server를 설치할 수 있도록 합니다. 도메인 관리자 그룹의 구성원이 아닌 지정 된 도메인
ms.openlocfilehash: 844cfa586523750b804564482146c0e76b39fc38
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815516"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서-Cssetupsetuppermission 허용에의 한 변경 내용
 
설치를 위임 하려면 특정 Active Directory OU (조직 구성 단위)에 대 한 RTCUniversalServerAdmins 유니버설 그룹에 대 한 사용 권한을 부여 하 여 해당 OU에 있는 RTCUniversalServerAdmins 그룹의 구성원이 비즈니스용 Skype Server를 설치할 수 있도록 합니다. 도메인 관리자 그룹의 구성원이 아닌 지정 된 도메인 
  
**부여-CsSetupPermission** cmdlet은 다음 표에 지정 된 대로 OU에 대 한 RTCUniversalServerAdmins 그룹 권한을 부여 합니다.
  
**OU의 개체에 부여 된 사용 권한**

|**사용 권한은 다음에 적용 됩니다.**|**부여 된 사용 권한은 다음과 같습니다.**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | 특별 액세스: <br/>  ServicePrincipalName 읽기 <br/>  ServicePrincipalName 쓰기 <br/>  트리 삭제 <br/>  디렉터리 변경 내용 복제 <br/> |
|하위 항목 serviceConnectionPoint 개체  <br/> | 특별 액세스: <br/>  읽기 권한 <br/>  쓰기 권한 <br/>  하위 항목 만들기 <br/>  하위 항목 삭제 <br/>  내용 목록 <br/>  쓰기 속성 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 항목 msRTCSIP-서버 개체  <br/> | 특별 액세스: <br/>  쓰기 속성 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 msRTCSIP-WebComponents 개체  <br/> | 특별 액세스: <br/>  쓰기 속성 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 항목 msRTCSIP-MCU 개체  <br/> | 특별 액세스: <br/>  쓰기 속성 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 항목 msRTCSIP-MediationServer 개체  <br/> | 특별 액세스: <br/>  쓰기 속성 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 항목 msRTCSIP-ApplicationServer 개체  <br/> | 특별 액세스: <br/>  쓰기 속성 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 msRTCSIP-ConnectionPoint 개체  <br/> | 특별 액세스: <br/>  쓰기 속성 <br/>  속성 읽기 <br/>  트리 삭제 <br/> |
|하위 컴퓨터 개체  <br/> | ServiceConnectionPoint에 대 한 특수 액세스: <br/>  자식 개체 만들기 <br/>  자식 개체 삭제 <br/>  트리 삭제 <br/>  공개 정보에 대 한 특별 액세스: <br/>  속성 읽기 <br/>  DNS 호스트 이름에 대 한 특수 액세스: <br/>  속성 읽기 <br/> |
   

