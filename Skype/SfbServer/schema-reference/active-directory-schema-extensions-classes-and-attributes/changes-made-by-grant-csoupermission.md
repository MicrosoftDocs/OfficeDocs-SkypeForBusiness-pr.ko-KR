---
title: Grant-CsOUPermission 변경한 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: 비즈니스용 Skype 서버 관리 권한을 위임하려면 포리스트 준비에서 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 될 필요 없이 US에 액세스할 수 있도록 지정된 US(조직 구성 단위)에 권한을 추가할 수 있습니다.
ms.openlocfilehash: 412fd5eb19f3dac23bbbf68cfd4eb751f56fa3bc
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416401"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>Grant-CsOUPermission 변경한 비즈니스용 Skype 서버
 
비즈니스용 Skype 서버 관리 권한을 위임하려면 포리스트 준비에서 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 될 필요 없이 US에 액세스할 수 있도록 지정된 US(조직 구성 단위)에 권한을 추가할 수 있습니다. 
  
**Grant-CsOuPermission** cmdlet을 사용하면 다음 표에 지정된 대로 지정한 OU의 개체에 대한 사용 권한이 부여됩니다.
  
## <a name="granting-permission-for-user-objects"></a>User 개체에 대한 사용 권한 부여

OU의 User 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.
  
**User 개체에 대해 부여되는 사용 권한**

|**Group**|**사용 권한**|**적용 대상**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |디렉터리 변경 내용 복제  <br/> |이 개체만  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |콘텐츠 나열  <br/> 모든 속성 읽기  <br/> 사용 권한 읽기  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |콘텐츠 나열  <br/> 모든 속성 읽기  <br/> 사용 권한 읽기  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet 읽기  <br/> RTCUserProvisioningPropertySet 읽기  <br/> RTCPropertySet 읽기  <br/> 공용 정보 읽기  <br/> 일반 정보 읽기  <br/> 사용자 계정 제한 사항 읽기  <br/> |하위 User 개체  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet 쓰기  <br/> msExchUCVoiceMailSettings 쓰기  <br/> RTCUserProvisioningPropertySet 쓰기  <br/> RTCPropertySet 쓰기  <br/> proxyAddresses 쓰기  <br/> |하위 User 개체  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>Computer 개체에 대한 사용 권한 부여

OU의 Computer 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.
  
**Computer 개체에 대해 부여되는 사용 권한**

|**Group**|**사용 권한**|**적용 대상**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |디렉터리 변경 내용 복제  <br/> |이 개체만  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |콘텐츠 나열  <br/> 모든 속성 읽기  <br/> 사용 권한 읽기  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |콘텐츠 나열  <br/> 모든 속성 읽기  <br/> 사용 권한 읽기  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |공용 정보 읽기  <br/> Validated-DNS-Host-Name 읽기  <br/> |하위 Computer 개체  <br/> |
|RTCUniversalUserAdmins  <br/> |공용 정보 읽기  <br/> Validated-DNS-Host-Name 읽기  <br/> |하위 Computer 개체  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Contact 또는 AppContact 개체에 대한 사용 권한 부여

OU의 Contact 또는 AppContact 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.
  
**Contact 또는 AppContact 개체에 대해 부여되는 사용 권한**

|**Group**|**사용 권한**|**적용 대상**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |디렉터리 변경 내용 복제  <br/> |이 개체만  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |콘텐츠 나열  <br/> 모든 속성 읽기  <br/> 사용 권한 읽기  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |콘텐츠 나열  <br/> 모든 속성 읽기  <br/> 사용 권한 읽기  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet 읽기  <br/> RTCUserProvisioningPropertySet 읽기  <br/> RTCPropertySet 읽기  <br/> 공용 정보 읽기  <br/> 일반 정보 읽기  <br/> 개인 정보 읽기  <br/> 사용자 계정 제한 사항 읽기  <br/> |하위 Contact 개체  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet 쓰기  <br/> otherIpPhone 쓰기  <br/> displayName 쓰기  <br/> description 쓰기  <br/> telephoneNumber 쓰기  <br/> msExchUCVoiceMailSettings 쓰기  <br/> RTCUserProvisioningPropertySet 쓰기  <br/> RTCPropertySet 쓰기  <br/> proxyAddresses 쓰기  <br/> |하위 Contact 개체  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>Device 개체에 대한 사용 권한 부여

OU의 Device 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.
  
**Device 개체에 대해 부여되는 사용 권한**

|**Group**|**사용 권한**|**적용 대상**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |디렉터리 변경 내용 복제  <br/> |이 개체만  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |콘텐츠 나열  <br/> 모든 속성 읽기  <br/> 사용 권한 읽기  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |콘텐츠 나열  <br/> 모든 속성 읽기  <br/> 사용 권한 읽기  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet 읽기  <br/> RTCUserProvisioningPropertySet 읽기  <br/> RTCPropertySet 읽기  <br/> 공용 정보 읽기  <br/> 개인 정보 읽기  <br/> 일반 정보 읽기  <br/> 사용자 계정 제한 사항 읽기  <br/> |하위 Contact 개체  <br/> |
|RTCUniversalUserAdmins  <br/> |자식 항목 만들기  <br/> 자식 항목 삭제  <br/> 트리 삭제  <br/> |담당자  <br/> |
|RTCUniversalUserAdmins  <br/> |displayName 쓰기  <br/> description 쓰기  <br/> telephoneNumber 쓰기  <br/> |하위 User 개체  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet 쓰기  <br/> otherIpPhone 쓰기  <br/> displayName 쓰기  <br/> description 쓰기  <br/> telephoneNumber 쓰기  <br/> msExchUCVoiceMailSettings 쓰기  <br/> RTCUserProvisioningPropertySet 쓰기  <br/> RTCPropertySet 쓰기  <br/> proxyAddresses 쓰기  <br/> |하위 Contact 개체  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>InetOrgPerson 개체에 대한 사용 권한 부여

OU의 InetOrgPerson 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.
  
**InetOrgPerson 개체에 대해 부여되는 사용 권한**

|**Group**|**사용 권한**|**적용 대상**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |디렉터리 변경 내용 복제  <br/> |이 개체만  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |콘텐츠 나열  <br/> 모든 속성 읽기  <br/> 사용 권한 읽기  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |콘텐츠 나열  <br/> 모든 속성 읽기  <br/> 사용 권한 읽기  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet 읽기  <br/> RTCUserProvisioningPropertySet 읽기  <br/> RTCPropertySet 읽기  <br/> 개인 정보 읽기  <br/> 공용 정보 읽기  <br/> 일반 정보 읽기  <br/> 사용자 계정 제한 사항 읽기  <br/> |하위 inetOrgPerson 개체  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet 쓰기  <br/> RTCUserProvisioningPropertySet 쓰기  <br/> RTCPropertySet 쓰기  <br/> proxyAddresses 쓰기  <br/> |하위 inetOrgPerson 개체  <br/> |
   

