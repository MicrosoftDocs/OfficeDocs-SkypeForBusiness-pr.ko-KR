---
title: 비즈니스용 Skype 서버에서 변경 사항 허용-CsOUPermission
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
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: 비즈니스용 Skype 서버 관리를 위임 하려면 포리스트 준비를 통해 만든 RTC 유니버설 그룹의 구성원이 도메인 관리자 그룹의 구성원으로도 액세스할 수 없도록 지정 된 조직 구성 단위 (Ou)에 대 한 사용 권한을 추가 하면 됩니다.
ms.openlocfilehash: 8342d1801d2df91f940f02e8bfc05c3c5b91c4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815526"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 변경 사항 허용-CsOUPermission
 
비즈니스용 Skype 서버 관리를 위임 하려면 포리스트 준비를 통해 만든 RTC 유니버설 그룹의 구성원이 도메인 관리자 그룹의 구성원으로도 액세스할 수 없도록 지정 된 조직 구성 단위 (Ou)에 대 한 사용 권한을 추가 하면 됩니다. 
  
**허용-CsOuPermission** cmdlet은 다음 표에 지정 된 대로 지정 된 OU의 개체에 대 한 사용 권한을 부여 합니다.
  
## <a name="granting-permission-for-user-objects"></a>사용자 개체에 대 한 사용 권한 부여

OU의 사용자 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하는 경우 그룹에는 다음 표에 나와 있는 것 처럼 권한이 부여 됩니다.
  
**사용자 개체에 부여 된 사용 권한**

|**그룹과**|**있는**|**적용 대상**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |디렉터리 변경 내용 복제  <br/> |이 개체만  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |내용 목록  <br/> 모든 속성 읽기  <br/> 읽기 권한  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |내용 목록  <br/> 모든 속성 읽기  <br/> 읽기 권한  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet 읽기  <br/> RTCUserProvisioningPropertySet 읽기  <br/> RTCPropertySet 읽기  <br/> 공개 정보 읽기  <br/> 일반 정보 읽기  <br/> 사용자 계정 제한 사항 읽기  <br/> |하위 사용자 개체  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet 쓰기  <br/> MsExchUCVoiceMailSettings 쓰기  <br/> RTCUserProvisioningPropertySet 쓰기  <br/> RTCPropertySet 쓰기  <br/> ProxyAddresses 쓰기  <br/> |하위 사용자 개체  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>컴퓨터 개체에 대 한 사용 권한 부여

OU의 컴퓨터 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하는 경우 그룹에는 다음 표에 나와 있는 것 처럼 권한이 부여 됩니다.
  
**컴퓨터 개체에 부여 된 사용 권한**

|**그룹과**|**있는**|**적용 대상**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |디렉터리 변경 내용 복제  <br/> |이 개체만  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |내용 목록  <br/> 모든 속성 읽기  <br/> 읽기 권한  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |내용 목록  <br/> 모든 속성 읽기  <br/> 읽기 권한  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |공개 정보 읽기  <br/> 읽음 확인 됨-DNS-호스트 이름  <br/> |하위 컴퓨터 개체  <br/> |
|RTCUniversalUserAdmins  <br/> |공개 정보 읽기  <br/> 읽음 확인 됨-DNS-호스트 이름  <br/> |하위 컴퓨터 개체  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>연락처 또는 AppContact 개체에 대 한 사용 권한 부여

OU의 Contact objects 또는 AppContact 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하면 다음 표에 표시 된 것 처럼 그룹에 권한이 부여 됩니다.
  
**연락처 또는 AppContact 개체에 부여 된 사용 권한**

|**그룹과**|**있는**|**적용 대상**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |디렉터리 변경 내용 복제  <br/> |이 개체만  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |내용 목록  <br/> 모든 속성 읽기  <br/> 읽기 권한  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |내용 목록  <br/> 모든 속성 읽기  <br/> 읽기 권한  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet 읽기  <br/> RTCUserProvisioningPropertySet 읽기  <br/> RTCPropertySet 읽기  <br/> 공개 정보 읽기  <br/> 일반 정보 읽기  <br/> 개인 정보 읽기  <br/> 사용자 계정 제한 사항 읽기  <br/> |하위 연락처 개체  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet 쓰기  <br/> OtherIpPhone 작성  <br/> DisplayName 쓰기  <br/> 설명 쓰기  <br/> TelephoneNumber 쓰기  <br/> MsExchUCVoiceMailSettings 쓰기  <br/> RTCUserProvisioningPropertySet 쓰기  <br/> RTCPropertySet 쓰기  <br/> ProxyAddresses 쓰기  <br/> |하위 연락처 개체  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>디바이스 개체에 대 한 사용 권한 부여

OU의 디바이스 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하면 다음 표에 표시 된 대로 그룹에 대 한 권한이 부여 됩니다.
  
**장치 개체에 부여 된 사용 권한**

|**그룹과**|**있는**|**적용 대상**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |디렉터리 변경 내용 복제  <br/> |이 개체만  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |내용 목록  <br/> 모든 속성 읽기  <br/> 읽기 권한  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |내용 목록  <br/> 모든 속성 읽기  <br/> 읽기 권한  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet 읽기  <br/> RTCUserProvisioningPropertySet 읽기  <br/> RTCPropertySet 읽기  <br/> 공개 정보 읽기  <br/> 개인 정보 읽기  <br/> 일반 정보 읽기  <br/> 사용자 계정 제한 사항 읽기  <br/> |하위 연락처 개체  <br/> |
|RTCUniversalUserAdmins  <br/> |하위 항목 만들기  <br/> 하위 항목 삭제  <br/> 트리 삭제  <br/> |Contact  <br/> |
|RTCUniversalUserAdmins  <br/> |DisplayName 쓰기  <br/> 설명 쓰기  <br/> TelephoneNumber 쓰기  <br/> |하위 사용자 개체  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet 쓰기  <br/> OtherIpPhone 작성  <br/> DisplayName 쓰기  <br/> 설명 쓰기  <br/> TelephoneNumber 쓰기  <br/> MsExchUCVoiceMailSettings 쓰기  <br/> RTCUserProvisioningPropertySet 쓰기  <br/> RTCPropertySet 쓰기  <br/> ProxyAddresses 쓰기  <br/> |하위 연락처 개체  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>InetOrgPerson 개체에 대 한 사용 권한 부여

OU의 InetOrgPerson 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하는 경우 그룹에는 다음 표에 나와 있는 것 처럼 권한이 부여 됩니다.
  
**InetOrgPerson 개체에 부여 된 사용 권한**

|**그룹과**|**있는**|**적용 대상**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |디렉터리 변경 내용 복제  <br/> |이 개체만  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |내용 목록  <br/> 모든 속성 읽기  <br/> 읽기 권한  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |내용 목록  <br/> 모든 속성 읽기  <br/> 읽기 권한  <br/> |이 개체만  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |RTCUserSearchPropertySet 읽기  <br/> RTCUserProvisioningPropertySet 읽기  <br/> RTCPropertySet 읽기  <br/> 개인 정보 읽기  <br/> 공개 정보 읽기  <br/> 일반 정보 읽기  <br/> 사용자 계정 제한 사항 읽기  <br/> |하위 항목 inetOrgPerson 개체  <br/> |
|RTCUniversalUserAdmins  <br/> |RTCUserSearchPropertySet 쓰기  <br/> RTCUserProvisioningPropertySet 쓰기  <br/> RTCPropertySet 쓰기  <br/> ProxyAddresses 쓰기  <br/> |하위 항목 inetOrgPerson 개체  <br/> |
   

