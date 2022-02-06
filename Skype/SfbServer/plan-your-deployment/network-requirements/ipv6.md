---
title: IPv6 in 비즈니스용 Skype
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: '요약: 설치하기 전에 IPv6을 구현하는 비즈니스용 Skype 서버.'
---

# <a name="plan-for-ipv6-in-skype-for-business"></a>IPv6 in 비즈니스용 Skype
 
**요약:** 설치하기 전에 IPv6을 비즈니스용 Skype 서버.
  
비즈니스용 Skype 서버 IP 버전 6(IPv6) 주소에 대한 지원과 IP 버전 4(IPv4) 주소가 계속 지원됩니다. 

IPv4 주소는 컴퓨터가 인터넷을 통해 통신할 수 있도록 하는 32비트 주소입니다. 전 세계적으로 증가하는 장치 수로 인해 사용 가능한 IPv4 주소가 모두 사용되었습니다. 이 때문에 많은 새 장치가 IPv6 주소를 사용하여 이동하고 있습니다. IPv6 주소는 IPv4 주소와 같은 기능을 수행하며 일부 추가 기능을 제공하지만, 32비트만 사용하는 대신 128비트도 사용합니다. 따라서 새로운 주소 집합이 매우 많이 제공됩니다. 

일반적인 IPv4 주소는 192.0.2.235와 같으며, IPv6 주소는 2001:0db8:85a3:0000:0000:8a2e:0370:7334와 같습니다. IPv6 주소를 사용하는 장치의 서식 및 기능이 변경되어 설치 시 몇 가지 배포 및 구성 비즈니스용 Skype 서버 필요합니다. 

이 항목에는 다음 섹션이 포함되어 있습니다.
  
- [IP 주소 유형 개요](ipv6.md#over)
    
- [IPv6에 대한 기술 요구 사항](ipv6.md#tech)
    
- [IPv6에 대한 마이그레이션 및 동시 사용 고려 사항](ipv6.md#migration)
    
IPv6 주소를 사용할 것으로 결정되면 다음 문서의 IP 주소 유형 [구성을 비즈니스용 Skype](ip-address-types.md) 참조하세요.
  
## <a name="overview-of-ip-address-types"></a>IP 주소 유형 개요
<a name="over"> </a>

2016에서 IP 주소를 구성할 때 세 가지 옵션이 비즈니스용 Skype 서버. IPv4(ip 비즈니스용 Skype 서버 4), IP 버전 6(IPv6) 또는 둘의 조합(이중 스택)을 지원하도록 구성할 수 있습니다. 구성 유형마다 고려해야 할 몇 가지 사항이 있습니다.
  
- **IPv4만** IPv6은 전 세계에 IPv4 주소가 사용 중이기 때문에 만들어졌습니다. 궁극적으로 IPv6은 전 세계에 완전히 지원되지만, 현재 기업에서 통신해야 할 수 있는 많은 회사 및 장치는 IPv6을 아직 지원하지 않고 당분 동안 지원하지 않을 수 있습니다. IPv4 전용 구성을 사용하면 기존 장치와 통신할 비즈니스용 Skype 서버 수 있습니다.
    
- **IPv6만** 반대로, 전체 IPv6 구현은 많은 기존 장치와의 통신을 제외합니다.
    
- **이중 스택** 이중 스택은 IPv4 및 IPv6 주소가 모두 사용하도록 설정된 네트워크입니다. 이 구성은 대부분의 비즈니스용 Skype 서버 전체 IPv4에서 전체 IPv6으로 전환하는 데 몇 년이 걸릴 수 있기 때문에 지원됩니다.
    
다음 섹션에서는 다양한 구성 기능의 이러한 세 가지 구성 간 호환성을 비즈니스용 Skype 서버 설명합니다.
  
> [!NOTE]
> IPv6를 사용한 클라이언트 또는 서버 구성은 연구 또는 검사 목적으로만 지원됩니다. IPv6 전용 구성은 프로덕션 배포에는 지원되지 않습니다. 
  
### <a name="client-registration"></a>클라이언트 등록
<a name="client"> </a>

|**클라이언트 끝점 네트워크**|**서버 네트워크**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |이중 스택  <br/> |
|이중 스택  <br/> |IPv4  <br/> |
|이중 스택  <br/> |이중 스택  <br/> |
|이중 스택  <br/> |IPv6  <br/> |
|IPv6  <br/> |이중 스택  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>피어 투 피어 클라이언트
<a name="peer"> </a>

피어 투 피어 통신에는 오디오, 오디오/비디오, 응용 프로그램 공유 및 파일 전송이 포함됩니다. 두 클라이언트가 성공적으로 등록된 후에는 다음 조합이 지원됩니다.
  
|**클라이언트 끝점 1**|**클라이언트 끝점 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |이중 스택  <br/> |
|이중 스택  <br/> |이중 스택  <br/> |
|IPv6  <br/> |이중 스택  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>전화 회의
<a name="conf"> </a>

회의에는 오디오/비디오, 응용 프로그램 공유 및 화이트보드 및 파일 공유와 같은 데이터 공동 작업 응용 프로그램이 포함됩니다.
  
|**클라이언트 끝점 네트워크**|**서버 네트워크**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |이중 스택  <br/> |
|이중 스택  <br/> |IPv4  <br/> |
|이중 스택  <br/> |이중 스택  <br/> |
|이중 스택  <br/> |IPv6  <br/> |
|IPv6  <br/> |이중 스택  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>중재 서버/PSTN
<a name="med"> </a>

비즈니스용 Skype 서버 IPv6 인터페이스를 통해 트래픽을 사용하는 경우 PSTN(Public Switched Telephone Network) 통화에 대한 미디어 우회를 지원하지 않습니다. 미디어 바이패스가 필요할 경우 PSTN 게이트웨이를 IPv4로 구성하는 것이 좋습니다. 
  
|**기본 인터페이스 1**|**PSTN 인터페이스(중재 서버)**|**PSTN 게이트웨이 설정**|
|:-----|:-----|:-----|
|IPv4  <br/> |이중 스택  <br/> |IPv4  <br/> |
|이중 스택  <br/> |이중 스택  <br/> |IPv4  <br/> |
|이중 스택  <br/> |이중 스택  <br/> |IPv6  <br/> |
   
1. 기본 인터페이스는 기본 구성 요소와 통신하는 비즈니스용 Skype 서버 인터페이스입니다.
  
### <a name="remote-user-peer-to-peer-communications"></a>원격 사용자 피어 투 피어 통신
<a name="remote"> </a>

원격 사용자와의 피어 투 피어 통신에는 인스턴트 메시징, 오디오/비디오, 응용 프로그램 공유 및 파일 전송이 포함됩니다.
  
|**원격 사용자 네트워크**|**에지 서버(외부 에지)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|이중 스택  <br/> |IPv4  <br/> |
|이중 스택  <br/> |이중 스택  <br/> |
|IPv6  <br/> |이중 스택  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>프런트 엔드 풀과 에지 풀 구성
<a name="FE_pool"> </a>

다음 표에서는 프런트 엔드 서버 풀과 내부 에지 서버 풀 간의 지원 매트릭스를 보여줍니다.
  
**프런트 엔드 풀과 에지 풀(내부 에지) 매트릭스**

||**에지 풀: IPv4** <br/> |**에지 풀: 이중 스택** <br/> |**에지 풀: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**프런트 엔드 풀: IPv4** <br/> |예  <br/> |예  <br/> |아니요  <br/> |
|**프런트 엔드 풀: 이중 스택** <br/> |예  <br/> |예  <br/> |아니요  <br/> |
|**프런트 엔드 풀: IPv6** <br/> |아니요  <br/> |아니요  <br/> |예\*  <br/> |
   
\* 이 조합은 랩 환경에서만 사용할 수 있습니다.
  
다음 표는 지원되는 내부 및 외부 에지 인터페이스 조합 매트릭스입니다.
  
**에지 풀(내부 에지)과 에지 풀(외부 에지) 매트릭스**

||**에지 풀(외부 에지) : IPv4** <br/> |**에지 풀(외부 에지): 이중 스택** <br/> |**에지 풀(외부 에지) : IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**에지 풀(내부 에지) : IPv4** <br/> |예  <br/> |예  <br/> |아니요  <br/> |
|**에지 풀(내부 에지): 이중 스택** <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |
|**에지 풀(내부 에지) : IPv6** <br/> |아니요  <br/> |아니요  <br/> |예\*  <br/> |
   
\* 이 조합은 랩 환경에서만 사용할 수 있습니다.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6에 대한 고급 Enterprise Voice 지원
<a name="Ent_V"> </a>

CAC(통화 허용 제어 서비스), E9-1-1(고급 9-1-1) 또는 미디어 바이패스를 포함하는 배포는 IPv4 전용 또는 이중 스택 구현으로 구성해야 합니다. IPv6만 사용하는 끝점에서는 이러한 기능을 사용할 수 없습니다.
  
> [!NOTE]
> 이중 누적 배포에서는 비즈니스용 Skype 서버 클라이언트가 IPv6을 사용하여 비즈니스용 Skype 서버 연결한 경우에도 비즈니스용 Skype 서버 E9-1-1을 지원하기 위해 적절한 IPv4 주소를 매핑하기 위해 최선을 다할 것입니다. 
  
IPv6 주소가 있는 위치 정보 서비스는 지원되지 않습니다.
  
Exchange UM(통합 메시징)에서는 IPv6을 지원하지 않습니다. Exchange UM의 경우 DNS 확인 시 IPv6 주소가 반환되지 않습니다. IPv6을 사용하면 통화가 음성 사서함로 올바르게 전송될 때 실패할 수도 있습니다. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>IPv6에 비즈니스용 Skype 서버 기타 기능 지원
<a name="Ent_V"> </a>

앞서 언급한 기능 및 구성 요소 외에도 비즈니스용 Skype 서버 기능에 대해 IPv6을 지원할 수 있습니다.
  
- **영구 채팅**
    
    토폴로지 작성기에서 영구 채팅에 대해 IPv6을 구성합니다. 영구 채팅을 구성하는 데 대한 자세한 내용은 Deploying Persistent Chat Server 설명서를 참조하십시오.
    
- **QoE(체감 품질)과 CDR(통화 정보 기록) 보고서**
    
    모니터링 보고서에는 IPv4 형식인지 IPv6 형식인지에 관계 없이 모니터링 서버 데이터베이스에 저장된 IP 주소가 포함됩니다.
    
## <a name="technical-requirements-for-ipv6"></a>IPv6에 대한 기술 요구 사항
<a name="tech"> </a>

IPv6에 비즈니스용 Skype 서버 구성할 계획인 경우 다음 요구 사항에 유의하세요.
  
- IPv6 주소와 함께 비즈니스용 Skype 서버 검색하고 IPv6 주소로 확인해야 하는 레코드에 대한 DNS(Domain Name System) 레코드를 만들어야 합니다. IPv6 DNS는 호스트 AAAA(4개의 A) 레코드를 사용합니다. 배포 환경에 IPv4 및 IPv6를 모두 사용하는 경우 IPv4에 대한 호스트 A 레코드 및 IPv6에 대한 호스트 AAAA 레코드를 모두 구성하고 유지 관리하는 것이 가장 좋습니다. 배포 환경을 IPv6로 완전히 전환하는 경우라도 IPv4를 계속 사용하는 외부 사용자를 위해 IPv4 DNS 호스트 레코드가 계속 필요할 수 있습니다.
    
    IPv6의 사용을 시작하기 전에 IPv6 DNS 호스트 레코드를 배포할 수 있습니다. 클라이언트 또는 서버가 IPv6를 사용하지 않는 경우 레코드는 참조되지 않습니다. 변환 기술 구성 및 정책에 기반하여 사용할 레코드가 변환 기술에 따라 결정됩니다.
    
- 각 IPv6 주소에는 범위가 있습니다. IPv6 주소 지정에 사용할 수 있는 세 가지 범위는 IPv6 전역 주소(공용 IPv4 주소와 유사), IPv6 고유 로컬 주소(개인 IPv4 주소 범위와 유사) 및 IPv6 링크 로컬 주소(IPv4용 Windows Server의 자동 개인 IP 주소와 유사)입니다. 풀 내의 모든 서버는 동일한 범위의 IPv6 주소를 보유해야 합니다. 
    
> [!IMPORTANT]
> IPv6은 복잡한 항목으로, Windows Server 수준 및 비즈니스용 Skype 서버 수준으로 지정하는 주소가 예상대로 작동하도록 하려면 네트워킹 팀 및 인터넷 공급자와 신중하게 계획해야 합니다. IPv6 주소 지정 및 계획에 대한 추가 리소스는 이 항목의 끝에 있는 링크를 참조하십시오. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>IPv6에 대한 마이그레이션 및 동시 사용 고려 사항
<a name="migration"> </a>

Lync Server 2010 또는 IPv6(IP 버전 6)은 Lync Server 2010 또는 Office 지원되지 않습니다. 파일럿을 위해 Lync Server 2010을 테스트하고 이중 스택 비즈니스용 Skype 서버 수 있습니다. 모든 풀에 대해 IPv6(이중 스택 네트워크)을 사용하도록 설정하기 전에 특정 중앙 사이트의 모든 풀을 비즈니스용 Skype 서버 업그레이드하는 것이 좋습니다. IPv6 전용의 풀을 구성해야 할 경우에는 랩 환경에서 테스트 목적으로 IPv6 전용 풀을 설정하는 것이 좋습니다.
  
마이그레이션 및 동시 사용 중에는 다음과 같은 시나리오가 지원됩니다.
  
- 비즈니스용 Skype 서버, Lync Server 2013 및 Lync Server 2010 풀(IPv4 모드)은 비즈니스용 Skype 서버 모드로 공존합니다.
    
- 비즈니스용 Skype 서버 풀을 IPv6 전용 모드로 설정하면 IPv6 전용 풀이 사일로 설정됩니다.
    
## <a name="see-also"></a>참고 항목
<a name="migration"> </a>

[2016에서 IP 주소 비즈니스용 Skype](ip-address-types.md)

[IP 버전 6 주소 아키텍처](https://tools.ietf.org/html/rfc4291)
  
[IPv6 전역 유니캐스트 주소 형식](https://tools.ietf.org/html/rfc3587)
  
[고유한 로컬 IPv6 유니캐스트 주소](https://tools.ietf.org/html/rfc4193)
