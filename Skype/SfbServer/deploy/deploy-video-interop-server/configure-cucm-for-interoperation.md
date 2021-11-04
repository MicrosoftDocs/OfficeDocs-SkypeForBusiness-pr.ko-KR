---
title: 사용자와의 상호 연결에 대해 CUCM 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: '요약: 사용자 계정에서 작동하도록 CUCM을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 809ad19e89f398c507673ec677b4ce882d341327
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741324"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>사용자와의 상호 연결에 대해 CUCM 비즈니스용 Skype 서버
 
**요약:** 사용자와 함께 작동하도록 CUCM을 비즈니스용 Skype 서버.
  
> [!CAUTION]
> 이 기능은 TCP 전용 트렁크 설치를 사용하여 Cisco Unified Communications Manager(CallManager 또는 CUCM) 버전 10.5에서 테스트됩니다. 계속하기 전에 CUCM 환경이 이러한 기준을 충족하는지 확인해야 합니다. 
  
여기에 설명된 설정은 VIS에서 작동하도록 CUCM을 구성할 수 있는 방법의 예로만 사용할 수 있습니다. 다른 설정 및/또는 대체 CUCM 기능의 사용법을 사용하여 동일한 결과를 얻을 수도 있습니다. 특정 시나리오에 대한 최적의 구성은 권장하지 않습니다.
  
VIS와의 상호 연동을 위해 여러 CUCM 설정을 확인하거나 변경해야 합니다. 필요한 설정이 누락되는 것을 방지하려면 아래 절차를 따르세요.
  
### <a name="configure-the-cucm"></a>CUCM 구성

1. CUCM에 로그인하고 Cisco 통합 CM 관리 - \> 통화 라우팅 - 제어 \> 클래스- 파티션으로 \> 이동합니다.
    
2. 파티션 구성 화면에서 파티션 이름 및 설명을 입력하고 새로 **추가를 클릭합니다.**
    
3. Cisco 통합 CM 관리 - 통화 라우팅 - 제어 클래스 - 호출 검색 \> \> \> 공간으로 이동합니다.
    
4. 검색 공간 구성 호출 화면에서 호출 검색 공간의 이름을 입력하고 선택한 파티션에 방금 만든 파티션의 이름을 입력합니다. 완료되면 **저장을** 클릭합니다.
    
5. Cisco 통합 CM 관리 - \> 시스템 - 보안 - \> \> SIP 트렁크 보안 프로필로 이동합니다.
    
6. SIP 트렁크 보안 프로필 구성 화면에서 표시된 SIP 트렁크 보안 프로필 정보 옵션을 설정하고 새로 **추가를 클릭합니다.**
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |이름  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |장치 보안 모드  <br/> |비보안  <br/> |
   |들어오는 전송 유형  <br/> |TCP + UDP  <br/> |
   |전송 유형  <br/> |TCP  <br/> |
   |들어오는 포트  <br/> |5060  <br/> |
   
7. Cisco Unified CM Administration - \> Device- \> Device 설정- \> SIP Profile으로 이동합니다.
    
8. SIP 프로필 구성 화면에서 표시된 SIP 프로필 정보 옵션을 설정합니다. 
    
   |**매개 변수**|**권장 설정**|
   |:-----|:-----|
   |이름  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |설명  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. 동일한 화면에서 아래로 스크롤하여 SDP 프로필 정보 섹션으로 스크롤합니다. 조기 제안 및 다시 초대에 대한 **SDP** 세션 수준 대역폭 수정자 옵션은 기본적으로 TIAS 및 AS로 설정됩니다. 이 옵션을 TIAS 전용으로 변경합니다. 이 옵션을 기본 설정으로 두면 비즈니스용 Skype 서버 SIP 메시지의 대역폭 수정자 정보를 이해하지 못합니다. TIAS는 AS는 응용 프로그램별을 의미하는 반면, 전송 독립 응용 프로그램 관련을 의미합니다. RFC3890에 지정된 SIP 옵션입니다.
    
10. 같은 화면에서 아래로 아래로 스크롤합니다. SIP 프로필의 트렁크 관련 구성에서  음성 및 비디오 통화에 대한 초기 지원 제공을 선택하고 필수(필요한 경우 **MTP 삽입)** 옵션으로 설정하세요. 이렇게 하면 CUCM에서 Early Offer를 사용하여 발신 SIP 호출을 설정할 수 있습니다. CUCM 8.5 이상의 새로운 기능 중 하나는 MTP(미디어 종료 지점)를 요구하지 않고 Early Offer를 사용하여 발신 전화 설정을 지원하는 것입니다.
    
11. SIP 옵션 ping 섹션에서 "옵션 Ping을 사용하여 서비스 유형이 '없음(기본값)'인 트렁크의 대상 상태를 모니터링하려면 옵션 Ping 사용" 옆의 확인란이 선택되어 있는지 확인해야 합니다.
    
12. 완료되면 새로 추가 **를 클릭합니다.**
    
13. Cisco Unified CM Administration - \> Device- \> Trunk로 이동합니다. 
    
14. 장치 프로토콜을 SIP로 설정하고 다음 을 **누르고 있습니다.**
    
15. 장치 정보에서 장치 이름 및 설명(예: SfBVideoInterop_SIPTrunk)을 설정하고 미디어 리소스 그룹 목록을 올바른 미디어 리소스가 포함된 MRGL로 설정합니다. 
    
16. 아래로 스크롤합니다. 비디오 통화를 위해 MTP(미디어 종료 지점)가 필요하지 않습니다. 아직 이(가) 없는 경우 MTP(미디어 종료 지점)를 아직 확정하지 않은 경우, MTP(미디어 종료 지점)를 사용할 필요는 없습니다. 활성 모든 통합 CM 노드에서 실행 **옵션을 선택합니다.** 모든 CUCM 노드를 구성에 추가해야 비즈니스용 Skype 서버 있습니다.
    
17. 아래로 스크롤합니다. 인바운드 통화 및 연결된 설정 옵션을 설정하세요.
    
    |**매개 변수**|**권장 설정**|
    |:-----|:-----|
    |검색 공간 호출  <br/> |CSS_SfBVideoInterop  <br/> |
    |AAR 호출 검색 공간  <br/> |CSS_SfBVideoInterop  <br/> |
    |연결된 파티 변환 CSS  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. 아래로 스크롤합니다. SIP 트렁크 구성의 SIP 정보 대상 섹션에서 VIS 풀의 FQDN 또는 풀에 있는 개별 VIS 서버의 IP 주소를 지정합니다(여러 항목 추가). 대상 포트에서 VIS가 CUCM에서 연결을 수신하는 포트를 지정합니다(기본값은 6001). 또한 앞에서 만든 SIP 트렁크 보안 프로필 및 SIP 프로필을 다음과 같이 지정합니다.
    
    |**매개 변수**|**권장 설정**|
    |:-----|:-----|
    |SIP 트렁크 보안 프로필  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |호출 검색 공간 다시우기  <br/> |CSS_SfBVideoInterop  <br/> |
    |대화 상자에서 검색 공간 호출  <br/> |CSS_SfBVideoInterop  <br/> |
    |호출 검색 공간 구독  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP 프로필  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF 신호 방법  <br/> |RFC 2833  <br/> |
   
19.  아래로 스크롤합니다. 기록 정보를 시스템에 적절하게 설정하세요. 없음으로 설정하는 것은 **괜찮습니다.** 
    
20. 완료되면 새로 추가 **를 클릭합니다.**
    
21. Cisco 통합 CM 관리 - \> 통화 라우팅 - \> 경로/헌트- \> 경로 패턴으로 이동합니다.
    
22. 경로 패턴 구성 화면에서 아래 표시된 패턴 정의 매개 변수를 입력합니다. 호출된 파티 변환 섹션까지 아래로 스크롤하여 표시된 마스크를 설정한 다음 마쳤을 때 새로 **추가를** 클릭합니다.
    
    |**매개 변수**|**권장 설정**|
    |:-----|:-----|
    |경로 패턴  <br/> |7779999  <br/> |
    |경로 파티션  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |설명  <br/> |SfBVideoInterop용 파티션  <br/> |
    |게이트웨이/경로 목록  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |Party Transform Mask라고 불리는  <br/> |+14257779999  <br/> |
   
23. Cisco 통합 CM 관리 - \> 통화 라우팅 - \> SIP 경로 패턴으로 이동합니다.
    
24. SIP 경로 패턴 구성 화면에서 패턴 정의 옵션을 표시된 것으로 설정하고 새로 **추가를 클릭합니다.**
    
    |**매개 변수**|**권장 설정**|
    |:-----|:-----|
    | 패턴 사용 <br/> |도메인 라우팅  <br/> |
    |IPv4 패턴  <br/> |contoso.com(IPv6을 사용하는 경우 비워 두기)  <br/> |
    |IPv6 패턴  <br/> |contoso.com(IPv4를 사용하는 경우 비워 두기)  <br/> |
    |설명  <br/> |SIPRoute Pattern to mediarv  <br/> |
    |경로 파티션  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |SIP 트렁크/경로 목록  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |차단 패턴 확인란  <br/> |그대로 두기  <br/> |
   
25. 오디오 또는 비디오 비트 비율을 기본 설정에서 변경한 경우 기본값으로 되 돌아가야 합니다. 오디오/비디오 통화의 비트 비율을 설정하기 위해 Cisco Unified CM Administration- \> System- \> Region Information- \> Region으로 이동합니다. 참조를 위해 기본값은 다음과 같습니다.
    
    |**매개 변수**|**권장 설정**|
    |:-----|:-----|
    |지역  <br/> |기본값  <br/> |
    |오디오 코덱 기본 설정 목록  <br/> |시스템 기본값  <br/> |
    |최대 오디오 비트 속도  <br/> |64 kbps(G.722, G.711)  <br/> |
    |비디오 통화에 대한 최대 세션 비트 속도  <br/> |200000 kbps  <br/> |
    |최대 세션 비트 속도  <br/> |2000000000 kbps  <br/> |
   
이때 CUCM 비디오 게이트웨이는 VIS와 함께 작동하도록 구성됩니다. 해당 구성은 통합하려는 각 VTC에서 수행해야 합니다.
> [!NOTE]
> 탄력성을 향상하기 위해 두 번째 Video Interop 서버 또는 VIS 풀에서 작동하도록 이 CUCM 게이트웨이를 구성할 수 있습니다. 자세한 [내용은 탄력성 메커니즘을](../../plan-your-deployment/video-interop-server.md#resiliency) 참조하세요.
  
## <a name="see-also"></a>참고 항목

[VTC를 구성하여 상호 비즈니스용 Skype 서버](configure-a-vtc-for-interoperation.md)
