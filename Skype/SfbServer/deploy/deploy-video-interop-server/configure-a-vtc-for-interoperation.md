---
title: 비즈니스용 Skype 서버와 상호 운용을 위한 VTC 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: '요약: 비즈니스용 Skype 서버에서 작동 하도록 VTC 장치를 구성 합니다.'
ms.openlocfilehash: 460ac0a301ee9c9b2cb5bb1b4ca4c1aaf6ee4825
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197355"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>비즈니스용 Skype 서버와 상호 운용을 위한 VTC 구성
 
**요약:** 비즈니스용 Skype 서버에서 작동 하도록 VTC 장치를 구성 합니다.
  
SIP 트렁크 및 Cisco 통합 커뮤니케이션 관리자 (CallManager 또는 CUCM) 비디오 게이트웨이를 통해 비즈니스용 Skype VIS 서버에 연결 하는 각 VTC에 대해 다음 구성 사용자 지정 절차를 수행 해야 합니다.
  
여기에서 설명 하는 설정은 VIS와 작동 하도록 CUCM를 구성할 수 있는 방법의 예제로만 사용 됩니다. 다른 설정 및/또는 대체 CUCM 기능을 사용 하 여 동일한 결과를 얻을 수도 있습니다. 특정 시나리오에 대 한 최적 구성에 대 한 권장 사항은 없습니다.
  
### <a name="configure-a-vtc-registered-with-cucm"></a>CUCM를 사용 하 여 등록 된 VTC 구성

1. Cisco VTC 장치에 로그인 하 여 구성-\>시스템 구성-\>프로비저닝으로 이동 합니다.
    
2. 필요에 따라 다음 설정을 확인 합니다. 
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |프로 비전 모드  <br/> | CUCM <br/> |
   |ExternalManager 주소  <br/> | CUCM의 FQDN <br/> |
   | ExternalManager 도메인 <br/> |CUCM의 도메인  <br/> |
   
3. 구성-\>시스템 구성-\>네트워크로 이동 합니다.
    
4. 필요에 따라 다음 설정을 확인 합니다. 
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |DNS 도메인 이름  <br/> | CUCM의 도메인 이름 <br/> |
   |DNS 서버 1 주소  <br/> | 원하는 DNS 서버 주소 <br/> |
   
5. 구성-\>시스템 구성-\>네트워크 서비스를 탐색 합니다. 323 모드가 꺼져 있고 SIP 모드가 켜져 있는지 확인 합니다. 
    
6. 이러한 옵션은 끝점을 CUCM에 등록할 때 자동으로 설정 됩니다. 필요에 따라 다음 설정을 확인 합니다. 
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |323 모드  <br/> | 끄십시오 <br/> |
   |HTTP 모드  <br/> | 등 <br/> |
   | SIP 모드 <br/> | 등 <br/> |
   |Telnet 모드  <br/> | 등 <br/> |
   |WelcomeText  <br/> | 등 <br/> |
   |XMLAPI 모드  <br/> | 등 <br/> |
   
7. 구성으로 이동-\>시스템 구성-\>SIP.
    
8. 필요에 따라 다음 설정을 확인 합니다. 
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |프로필 1-DefaultTransport  <br/> | NET.TCP <br/> |
   |프로필 1-아웃 바운드  <br/> | 끄십시오 <br/> |
   |프로필 1-TlsVerify  <br/> | 등 <br/> |
   |프로필 1-종류  <br/> | Cisco <br/> |
   |프로필 1-URI  <br/> | CUCM 등록 시 자동으로 할당 됨 <br/> |
   |프록시 1-주소  <br/> |CUCM의 호스트 이름입니다.  <br/> |
   
이제 VTC가 상호 운용을 위해 구성 되었습니다. 서비스를 시작 하기 전에 CUCM 측면에서 수행할 마지막 단계가 있습니다.
### <a name="configure-vtc-devices-on-cucm"></a>CUCM에서 VTC 디바이스 구성

1. CUCM에 로그인 하 여 Cisco 통합 CM 관리-\>장치-\>휴대폰-\>검색으로 이동 합니다. 
    
2. 구성할 VTC 장치를 선택 합니다. 전화 구성 화면에서 필요에 따라 수정 하 여 다음 설정을 확인 합니다. 이러한 설정이 변경 되거나 확인 되 면 **저장**을 클릭 합니다.
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |장치 정보-전화 단추 서식 파일  <br/> | 표준 Cisco Telepresence 코덱 C40 <br/> |
   |장치 정보-공통 전화 프로필  <br/> | 표준 일반 전화 프로필 <br/> |
   |장치 정보-검색 공간 호출  <br/> | CSS_SfBVideoInterop <br/> |
   |장치 정보-AAR 통화 검색 공간  <br/> | CSS_SfBVideoInterop <br/> |
   |장치 정보-미디어 리소스 그룹 목록  <br/> | MRGL_SfBVideoInterop <br/> |
   |프로토콜 관련 정보-장치 보안 프로필  <br/> | Cisco Telepresence 코덱 C40 <br/> |
   |프로토콜 관련 정보-호출 검색 공간 다시 라우팅  <br/> | CSS_SfBVideoInterop <br/> |
   |프로토콜 관련 정보-통화 검색 공간 구독  <br/> | CSS_SfBVideoInterop <br/> |
   |프로토콜 관련 정보-SIP 프로필  <br/> | Telepresence 끝점에 대 한 표준 SIP 프로필 <br/> |
   
3. VTC 구성이 저장 되 면 장치에 대 한 전화 구성 화면으로 다시 이동 합니다. 연결 그룹의 화면 맨 위에서 비디오 Interop 연결을 클릭 합니다. 이렇게 하면 디렉터리 번호 구성 화면이 열립니다. 
    
4. 필요에 따라 다음 설정을 확인 합니다. 
    
    디렉터리 번호 정보와 디렉터리 번호 설정에 표시 된 대로 적절 하 게 변경 합니다.
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   | 디렉터리 번호 정보-경로 파티션 <br/> | SfBVideoInterop_RoutePartition <br/> |
   |디렉터리 번호 설정-검색 공간 호출  <br/> | CSS_SfBVideoInterop <br/> |
   |MLPP 대체 파티 및 기밀 액세스 수준 설정-MLPP 검색 공간 호출  <br/> | CSS_SfBVideoInterop <br/> |
   |장치 디스플레이의 라인 1 (발신자 ID)  <br/> | 필요에 따라 <br/> |
   |장치-ASCII 표시의 줄 1 (발신자 ID)  <br/> | 필요에 따라 <br/> |
   
5. 완료 되 면 화면 맨 위로 스크롤하고 **저장**을 누릅니다. 
    
이제이 VTC 장치에 대 한 구성이 완료 되었습니다. 엔터프라이즈의 다른 VTC 장치에 대해이 과정을 반복 해야 합니다.

