---
title: 비즈니스용 Skype 서버와의 상호 연계를 위한 VTC 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: '요약: 비즈니스용 Skype 서버에서 작동하도록 VTC 장치를 구성합니다.'
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802078"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>비즈니스용 Skype 서버와의 상호 연계를 위한 VTC 구성
 
**요약:** 비즈니스용 Skype 서버에서 작동하도록 VTC 장치를 구성합니다.
  
SIP 트렁크 및 Cisco Unified Communications Manager(CallManager 또는 CUCM) 비디오 게이트웨이를 통해 비즈니스용 Skype VIS 서버에 연결할 각 VTC에 대해 다음 구성 사용자 지정 절차를 수행해야 합니다.
  
여기에 설명된 설정은 VIS에서 작동하도록 CUCM을 구성하는 방법의 예로만 사용할 수 있습니다. 다른 설정 및/또는 대체 CUCM 기능의 사용법을 사용하여 동일한 결과를 얻을 수도 있습니다. 특정 시나리오에 대해 최적의 구성을 권장하지는 않습니다.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>CUCM에 등록된 VTC 구성

1. Cisco VTC 장치에 로그인하고 Configuration- \> System Configuration- \> Provisioning으로 이동합니다.
    
2. 다음 설정을 확인하고 필요한 경우 수정합니다. 
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |프로비저닝 모드  <br/> | CUCM <br/> |
   |ExternalManager 주소  <br/> | CUCM의 FQDN <br/> |
   | ExternalManager 도메인 <br/> |CUCM의 도메인  <br/> |
   
3. 구성 - \> 시스템 구성 - \> 네트워크로 이동합니다.
    
4. 다음 설정을 확인하고 필요한 경우 수정합니다. 
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |DNS 도메인 이름  <br/> | CUCM의 도메인 이름 <br/> |
   |DNS Server 1 주소  <br/> | 원하는 DNS 서버 주소 <br/> |
   
5. 구성- 시스템 구성 \> - \> 네트워크 서비스로 이동합니다. H.323 모드가 꺼져 있으며 SIP 모드가 켜져 있는지 확인 
    
6. 이러한 옵션은 끝점이 CUCM에 등록될 때 자동으로 설정됩니다. 다음 설정을 확인하고 필요한 경우 수정합니다. 
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |H.323 모드  <br/> | 해제 <br/> |
   |HTTP 모드  <br/> | 켜짐 <br/> |
   | SIP 모드 <br/> | 켜짐 <br/> |
   |텔넷 모드  <br/> | 켜짐 <br/> |
   |WelcomeText  <br/> | 켜짐 <br/> |
   |XMLAPI 모드  <br/> | 켜짐 <br/> |
   
7. 구성- \> 시스템 구성 - \> SIP로 이동합니다.
    
8. 다음 설정을 확인하고 필요한 경우 수정합니다. 
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |프로필 1 - DefaultTransport  <br/> | TCP <br/> |
   |프로필 1 - 아웃바운드  <br/> | 해제 <br/> |
   |프로필 1 - TlsVerify  <br/> | 켜짐 <br/> |
   |프로필 1 - 유형  <br/> | Cisco <br/> |
   |프로필 1 - URI  <br/> | CUCM 등록 시 자동으로 할당 <br/> |
   |프록시 1 - 주소  <br/> |CUCM의 호스트 이름  <br/> |
   
이제 VTC가 상호 연결에 대해 구성됩니다. 서비스를 시작하기 전에 CUCM 쪽에서 수행할 마지막 단계가 있습니다.
### <a name="configure-vtc-devices-on-cucm"></a>CUCM에서 VTC 장치 구성

1. CUCM에 로그인하고 Cisco 통합 CM 관리 - \> 장치 - \> 전화 찾기로 \> 이동합니다. 
    
2. 구성할 VTC 장치를 선택합니다. 전화 구성 화면에서 다음 설정을 확인하고 필요한 경우 수정합니다. 이러한 설정을 변경하거나 확인한 후 저장을 **클릭합니다.**
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |장치 정보 - 전화 단추 템플릿  <br/> | Standard Cisco Telepresence Codec C40 <br/> |
   |장치 정보 - 일반 전화 프로필  <br/> | 표준 일반 전화 프로필 <br/> |
   |장치 정보 - 검색 공간 호출  <br/> | CSS_SfBVideoInterop <br/> |
   |장치 정보 - AAR 호출 검색 공간  <br/> | CSS_SfBVideoInterop <br/> |
   |장치 정보 - 미디어 리소스 그룹 목록  <br/> | MRGL_SfBVideoInterop <br/> |
   |프로토콜 관련 정보 - 장치 보안 프로필  <br/> | Cisco Telepresence Codec C40 <br/> |
   |프로토콜 관련 정보 - 호출 검색 공간 다시우기  <br/> | CSS_SfBVideoInterop <br/> |
   |프로토콜 관련 정보 - 구독 호출 검색 공간  <br/> | CSS_SfBVideoInterop <br/> |
   |프로토콜 관련 정보 -SIP 프로필  <br/> | 표준 SIP Profile for Telepresence Endpoint <br/> |
   
3. VTC 구성을 저장한 후 장치의 전화 구성 화면으로 다시 이동합니다. 연결 그룹의 화면 맨 위에 있는 비디오 Interop에 대한 연결(연결)을 클릭합니다. 그러면 디렉터리 번호 구성 화면이 나타납니다. 
    
4. 다음 설정을 확인하고 필요한 경우 수정합니다. 
    
    디렉터리 번호 정보 및 디렉터리 번호 설정에 표시된 적절하게 변경합니다.
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   | 디렉터리 번호 정보 - 경로 파티션 <br/> | SfBVideoInterop_RoutePartition <br/> |
   |디렉터리 번호 설정 - 검색 공간 호출  <br/> | CSS_SfBVideoInterop <br/> |
   |MLPP 대체 사용자 및 기밀 액세스 수준 설정 - MLPP 호출 검색 공간  <br/> | CSS_SfBVideoInterop <br/> |
   |디바이스의 줄 1 - 디스플레이(발신자 ID)  <br/> | 원하는 경우 <br/> |
   |디바이스의 줄 1 - ASCII 디스플레이(발신자 ID)  <br/> | 원하는 경우 <br/> |
   
5. 완료되면 화면 맨 위로 스크롤하고 저장을 **누르고 있습니다.** 
    
이제 이 VTC 장치에 대한 구성이 완료되었습니다. 엔터프라이즈의 다른 VTC 장치에 대해 이 프로세스를 반복해야 합니다.

