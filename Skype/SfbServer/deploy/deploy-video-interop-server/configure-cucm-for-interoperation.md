---
title: 비즈니스용 Skype 서버와 상호 운용할 CUCM 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: '요약: 비즈니스용 Skype 서버에서 작동 하도록 CUCM를 구성 합니다.'
ms.openlocfilehash: b0087e54b91b8c11bfcaba0c1eb732183db252bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197354"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>비즈니스용 Skype 서버와 상호 운용할 CUCM 구성
 
**요약:** 비즈니스용 Skype 서버에서 작동 하도록 CUCM를 구성 합니다.
  
> [!CAUTION]
> 이 접근 권한 값은 Trunks 설치를 사용 하 여 TCP만을 통해 Cisco 통합 커뮤니케이션 관리자 (CallManager 또는 CUCM) 버전 10.5에서 테스트 합니다. 계속 하기 전에 CUCM 환경이 이러한 기준을 충족 하는지 확인 합니다. 
  
여기에서 설명 하는 설정은 VIS와 작동 하도록 CUCM를 구성할 수 있는 방법의 예제로만 사용 됩니다. 다른 설정 및/또는 대체 CUCM 기능을 사용 하 여 동일한 결과를 얻을 수도 있습니다. 특정 시나리오에 대 한 최적 구성에 대 한 권장 사항은 없습니다.
  
VIS와의 상호 운용을 위해 몇 가지 CUCM 설정을 확인 하거나 변경 해야 합니다. 필요한 설정이 누락 되지 않도록 하려면 아래 절차를 따르세요.
  
### <a name="configure-the-cucm"></a>CUCM 구성

1. CUCM에 로그인 하 여 Cisco 통합 CM 관리로 이동-\>호출 라우팅-\>제어\>파티션의 종류
    
2. 파티션 구성 화면에서 파티션 이름과 설명을 입력 하 고 **새로 추가**를 클릭 합니다.
    
3. Cisco 통합 CM 관리로 이동-\>호출 라우팅-\>컨트롤\>호출 검색 공간 클래스
    
4. 호출 검색 공간 구성 화면에서 호출 검색 공간의 이름을 입력 하 고 선택한 파티션에는 방금 만든 파티션의 이름을 입력 합니다. 완료 되 면 **저장** 을 클릭 합니다.
    
5. Cisco 통합 CM 관리-\>시스템\>보안-\>SIP 트렁크 보안 프로필로 이동 합니다.
    
6. SIP 트렁크 보안 프로필 구성 화면에서 표시 된 대로 SIP 트렁크 보안 프로필 정보 옵션을 설정 하 고 **새로 추가**를 클릭 합니다.
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |이름  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |장치 보안 모드  <br/> |비보안  <br/> |
   |들어오는 전송 종류  <br/> |TCP + UDP  <br/> |
   |보내는 전송 종류  <br/> |NET.TCP  <br/> |
   |수신 포트  <br/> |5060  <br/> |
   
7. Cisco 통합 CM 관리-\>장치-\>장치 설정-\>SIP 프로필으로 이동 합니다.
    
8. SIP 프로필 구성 화면에서 표시 된 대로 SIP 프로필 정보 옵션을 설정 합니다. 
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |이름  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |설명  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. 동일한 화면에서 SDP 프로필 정보 섹션이 나올 때까지 아래로 스크롤합니다. **조기 제공 및 재 초대 옵션에 대 한 SDP 세션 수준의 대역폭 한정자** 는 기본적으로 및의 tias 설정 됩니다. 이 옵션을 ' 팁 '으로 변경 합니다. 이 옵션을 기본 설정으로 두면 비즈니스용 Skype 서버에서 SIP 메시지의 대역폭 한정자 정보를 인식 하지 못합니다. TIAS는 특정 응용 프로그램에만 해당 하는 경우를 의미 합니다. RFC3890에 지정 된 SIP 옵션입니다.
    
10. 같은 화면에서 더 아래로 스크롤합니다. SIP 프로필의 트렁크 구성 아래에서 **음성 및 영상 통화에 대 한 초기 지원 제공** 을 선택 하 고 **필수 (필요한 경우 MTP 삽입)** 옵션으로 설정 합니다. 이렇게 하면 CUCM에서 초기 제공으로 보내는 SIP 통화를 설정할 수 있습니다. CUCM 8.5 및 그 이상의 새로운 기능 중 하나는 MTP (미디어 종료 시점 없음)를 사용 하지 않고 초기 제공으로 나가는 통화 설정을 지원 한다는 것입니다.
    
11. SIP 옵션 ping 섹션에서 "옵션 선택 Ping을 사용 하 여 서비스 종류가 ' 없음 (기본값) ' 인 Trunks에 대 한 대상 상태 모니터링" 확인란 옆에 있음을 확인 합니다.
    
12. 마쳤으면 **새로 추가**를 클릭 합니다.
    
13. Cisco 통합 CM 관리-\>장치\>트렁크로 이동 합니다. 
    
14. 장치 프로토콜을 SIP로 설정 하 고 **다음**을 누릅니다.
    
15. 장치 정보에서 디바이스 이름 및 설명 (예: SfBVideoInterop_SIPTrunk)을 설정 하 고 미디어 리소스 그룹 목록을 올바른 미디어 리소스를 포함 하는 MRGL로 설정 합니다. 
    
16. 아래로 스크롤합니다. 비디오 통화에 MTP (미디어 종료 시점)가 필요 하지 않으면 아직 선택 되어 있지 않은 경우 선택을 취소 합니다. **모든 활성 통합 CM 노드에서 실행할**옵션을 선택 합니다. 모든 CUCM 노드를 비즈니스용 Skype 서버 구성에 추가 해야 한다는 점에 유의 하세요.
    
17. 아래로 스크롤합니다. 표시 된 대로 인바운드 통화 및 연결 된 파티 설정 옵션을 설정 합니다.
    
    |**매개 변수**|**권장 설정**|
    |:-----|:-----|
    |검색 공간 호출  <br/> |CSS_SfBVideoInterop  <br/> |
    |AAR 통화 검색 공간  <br/> |CSS_SfBVideoInterop  <br/> |
    |연결 된 파티 변형 CSS  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. 아래로 스크롤합니다. SIP 트렁크 구성의 SIP 정보 대상 섹션에서 VIS 풀의 FQDN 또는 풀에 있는 개별 VIS 서버의 IP 주소 (여러 항목 추가)를 지정 합니다. 대상 포트에서 VIS가 CUCM에서의 연결을 수신 대기 하는 포트를 지정 합니다 (기본값은 6001). 다음과 같이 앞에서 만든 SIP 트렁크 보안 프로필 및 SIP 프로필도 지정 합니다.
    
    |**매개 변수**|**권장 설정**|
    |:-----|:-----|
    |SIP 트렁크 보안 프로필  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |호출 검색 공간 다시 라우팅  <br/> |CSS_SfBVideoInterop  <br/> |
    |대화 종료-검색 공간 호출 참조  <br/> |CSS_SfBVideoInterop  <br/> |
    |통화 검색 공간 등록  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP 프로필  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF 신호 방법  <br/> |RFC 2833  <br/> |
   
19.  아래로 스크롤합니다. 기록 정보를 시스템에 맞게 설정 합니다. ' **없음**'으로 설정 하는 것은 괜찮습니다. 
    
20. 마쳤으면 **새로 추가**를 클릭 합니다.
    
21. Cisco 통합 CM 관리-\>호출 라우팅-\>경로/헌트\>경로 패턴으로 이동 합니다.
    
22. 경로 패턴 구성 화면에서 아래에 표시 된 패턴 정의 매개 변수를 입력 합니다. ' 파티 변형 ' 섹션으로 아래로 스크롤하여 표시 된 대로 마스크를 설정한 다음 완료 되 면 **새로 추가** 를 클릭 합니다.
    
    |**매개 변수**|**권장 설정**|
    |:-----|:-----|
    |경로 패턴  <br/> |7779999  <br/> |
    |경로 파티션  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |설명  <br/> |SfBVideoInterop 용 파티션  <br/> |
    |게이트웨이/경로 목록  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |파티 변환 마스크 호출  <br/> |+ 14257779999  <br/> |
   
23. Cisco 통합 CM 관리-\>호출 라우팅-\>SIP 경로 패턴으로 이동 합니다.
    
24. SIP 경로 패턴 구성 화면에서 표시 된 패턴 정의 옵션을 설정 하 고 **새로 추가**를 클릭 합니다.
    
    |**매개 변수**|**권장 설정**|
    |:-----|:-----|
    | 패턴 사용 <br/> |도메인 라우팅  <br/> |
    |IPv4 패턴  <br/> |contoso.com (IPv6을 사용 하는 경우 비워 둡니다.)  <br/> |
    |IPv6 패턴  <br/> |contoso.com (IPv4를 사용 하는 경우 비워 둡니다.)  <br/> |
    |설명  <br/> |SIPRoute 패턴-mediarv  <br/> |
    |경로 파티션  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |SIP 트렁크/라우트 목록  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |블록 패턴 확인란  <br/> |선택 하지 않은 상태로 나가기  <br/> |
   
25. 기본 설정에서 오디오 또는 비디오 비트 전송률을 변경한 경우이를 기본값으로 반환 해야 합니다. 오디오/비디오 통화에 대 한 비트 전송률을 설정 하려면 Cisco 통합 CM 관리-\>시스템\>지역 정보-\>지역으로 이동 합니다. 참조에 대 한 기본값은 다음과 같습니다.
    
    |**매개 변수**|**권장 설정**|
    |:-----|:-----|
    |영역인  <br/> |기본값  <br/> |
    |오디오 코덱 기본 설정 목록  <br/> |시스템 기본값  <br/> |
    |최대 오디오 비트 전송률  <br/> |64 kbps (722, 711)  <br/> |
    |비디오 통화에 대 한 최대 세션 비트 전송률  <br/> |20만 kbps  <br/> |
    |최대 세션 비트 전송률  <br/> |20억 kbps  <br/> |
   
이 시점에서 CUCM video gateway는 VIS와 함께 작동 하도록 구성 되어 있습니다. 통합 하고자 하는 각 VTC에서 해당 구성을 수행 해야 합니다.
> [!NOTE]
> 복구 력을 향상 시키기 위해 두 번째 비디오 Interop 서버 또는 VIS 풀에서 작동 하도록이 CUCM gateway를 구성할 수 있습니다. 자세한 내용은 [회복성 메커니즘](../../plan-your-deployment/video-interop-server.md#resiliency) 을 참조 하세요.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버와 상호 운용을 위한 VTC 구성](configure-a-vtc-for-interoperation.md)
