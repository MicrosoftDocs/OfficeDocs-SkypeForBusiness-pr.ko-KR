---
title: 비즈니스용 Skype의 IPv6 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: '요약: 비즈니스용 Skype 서버를 설치 하기 전에 IPv6을 구현 합니다.'
ms.openlocfilehash: 5fe8cd186d152d368ac89c1d6bc9c07cebb7bfe7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802078"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>비즈니스용 Skype의 IPv6 계획
 
**요약:** 비즈니스용 Skype 서버를 설치 하기 전에 IPv6을 구현 합니다.
  
비즈니스용 Skype 서버에는 ip 버전 6(Ipv6) 주소에 대 한 지원과 함께 IP 버전 4 (IPv4) 주소를 계속 사용할 수 있는 기능이 포함 되어 있습니다. 

IPv4 주소는 컴퓨터에서 인터넷을 통해 통신할 수 있도록 하는 32 비트 주소입니다. 전세계 장치 수가 증가 함에 따라 사용 가능한 IPv4 주소가 초과 되었습니다. 이 때문에 많은 새 장치가 IPv6 주소를 사용 하도록 이동 합니다. IPv6 주소는 IPv4 주소와 동일한 기능을 수행 하지만 (일부 추가 기능 포함), 32 비트만 사용 하는 대신 128 비트를 사용 하는 것이 좋습니다. 이렇게 하면 새 주소 집합 뿐만 아니라 훨씬 더 많은 수가 제공 됩니다. 

일반적인 IPv4 주소는 다음과 같이 표시 됩니다. 192.0.2.235, IPv6 주소는 다음과 같습니다: 2001:0db8:85a3:0000:0000:8a2e: 0370:7334. IPv6 주소를 사용 하는 디바이스의 서식 및 기능 변경에는 비즈니스용 Skype 서버 설치에 몇 가지 배포 및 구성 고려 사항이 필요 합니다. 

이 항목에서는 다음 섹션을 다룹니다.
  
- [IP 주소 유형 개요](ipv6.md#over)
    
- [IPv6에 대한 기술 요구 사항](ipv6.md#tech)
    
- [IPv6에 대한 마이그레이션 및 동시 사용 고려 사항](ipv6.md#migration)
    
IPv6 주소를 사용 하 게 되는 경우 비즈니스용 [Skype 문서에서 IP 주소 유형 구성](ip-address-types.md) 을 참조 하세요.
  
## <a name="overview-of-ip-address-types"></a>IP 주소 유형 개요
<a name="over"> </a>

비즈니스용 Skype 서버에서 IP 주소를 구성할 때는 세 가지 옵션이 있습니다. IPv4 (IP 버전 4)만 지원 하도록 비즈니스용 Skype 서버를 구성 하거나 (IP 버전 6), IPv6 또는 둘 다 (이중 스택 이라고 함)를 조합 하 여 사용할 수 있습니다. 각 구성 유형에 대해 고려해 야 할 몇 가지 문제가 있습니다.
  
- **IPv4만** 세계에 IPv4 주소가 부족 하 여 IPv6이 만들어졌습니다. 궁극적으로 IPv6은 전세계에서 완벽 하 게 지원 되지만 이번에는 엔터프라이즈에서 아직 IPv6을 지원 하지 않는 것으로 통신 해야 하는 많은 회사 및 장치를 사용할 수 있습니다. IPv4 전용 구성은 비즈니스용 Skype 서버 구현이 대부분의 기존 장치와 통신할 수 있도록 하는 데 도움이 됩니다.
    
- **IPv6만** 반대로, 전체 IPv6 구현은 기존의 여러 장치와 통신을 제외 합니다.
    
- **이중 스택** 이중 스택은 IPv4 및 IPv6 주소를 모두 사용할 수 있는 네트워크입니다. 이 구성은 대부분의 경우 전체 IPv4에서 full-IPv6으로 전환 하는 데 몇 년이 소요 되므로 비즈니스용 Skype 서버에서 지원 됩니다.
    
다음 섹션에서는 다양 한 비즈니스용 Skype 서버 기능에 대 한 세 가지 구성 간의 호환성을 간략하게 설명 합니다.
  
> [!NOTE]
> IPv6을 사용 하는 클라이언트 또는 서버 구성은 랩 또는 유효성 검사 용도로만 지원 됩니다. IPv6 전용 구성은 프로덕션 배포에서 지원 되지 않습니다. 
  
### <a name="client-registration"></a>클라이언트 등록
<a name="client"> </a>

|**클라이언트 끝점 네트워크**|**서버 네트워크**|
|:-----|:-----|
|(Ipv4  <br/> |(Ipv4  <br/> |
|(Ipv4  <br/> |이중 스택  <br/> |
|이중 스택  <br/> |(Ipv4  <br/> |
|이중 스택  <br/> |이중 스택  <br/> |
|이중 스택  <br/> |IPv6  <br/> |
|IPv6  <br/> |이중 스택  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>피어 투 피어 클라이언트
<a name="peer"> </a>

피어 투 피어 통신에는 오디오, 오디오/비디오, 응용 프로그램 공유, 파일 전송이 포함 됩니다. 두 클라이언트가 성공적으로 등록 되 면 다음 조합이 지원 됩니다.
  
|**클라이언트 끝점 1**|**클라이언트 끝점 2**|
|:-----|:-----|
|(Ipv4  <br/> |(Ipv4  <br/> |
|(Ipv4  <br/> |이중 스택  <br/> |
|이중 스택  <br/> |이중 스택  <br/> |
|IPv6  <br/> |이중 스택  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>회의
<a name="conf"> </a>

회의에는 오디오/비디오, 응용 프로그램 공유, whiteboarding 및 파일 공유와 같은 데이터 공동 작업 응용 프로그램이 포함 됩니다.
  
|**클라이언트 끝점 네트워크**|**서버 네트워크**|
|:-----|:-----|
|(Ipv4  <br/> |(Ipv4  <br/> |
|(Ipv4  <br/> |이중 스택  <br/> |
|이중 스택  <br/> |(Ipv4  <br/> |
|이중 스택  <br/> |이중 스택  <br/> |
|이중 스택  <br/> |IPv6  <br/> |
|IPv6  <br/> |이중 스택  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>중재 서버/PSTN
<a name="med"> </a>

비즈니스용 Skype 서버는 트래픽이 IPv6 인터페이스를 사용 하는 경우에는 PSTN (공개 통신 네트워크) 통화에 대 한 미디어 바이패스를 지원 하지 않습니다. 미디어 바이패스가 필요한 경우 PSTN 게이트웨이가 IPv4로 구성 되는 것이 좋습니다. 
  
|**기본 인터페이스 1**|**PSTN 인터페이스 (중재 서버에서)**|**PSTN 게이트웨이 설정**|
|:-----|:-----|:-----|
|(Ipv4  <br/> |이중 스택  <br/> |(Ipv4  <br/> |
|이중 스택  <br/> |이중 스택  <br/> |(Ipv4  <br/> |
|이중 스택  <br/> |이중 스택  <br/> |IPv6  <br/> |
   
1. 기본 인터페이스는 비즈니스용 Skype 서버 구성 요소와 통신 하는 인터페이스입니다.
  
### <a name="remote-user-peer-to-peer-communications"></a>원격 사용자 피어 투 피어 통신
<a name="remote"> </a>

원격 사용자와의 피어 투 피어 통신에는 인스턴트 메시지, 오디오/비디오, 응용 프로그램 공유, 파일 전송 등이 포함 됩니다.
  
|**원격 사용자 네트워크**|**Edge 서버 (외부 가장자리)**|
|:-----|:-----|
|(Ipv4  <br/> |(Ipv4  <br/> |
|이중 스택  <br/> |(Ipv4  <br/> |
|이중 스택  <br/> |이중 스택  <br/> |
|IPv6  <br/> |이중 스택  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>프런트 엔드 풀 및 Edge 풀 구성
<a name="FE_pool"> </a>

다음 표에는 프런트 엔드 서버 풀과 내부 Edge 서버 풀 사이의 지원 행렬이 나와 있습니다.
  
**프런트 엔드 풀 및 Edge 풀 (내부에 지) 행렬**

||**Edge 풀: IPv4** <br/> |**Edge 풀: 이중 스택** <br/> |**Edge 풀: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**프런트 엔드 풀: IPv4** <br/> |예  <br/> |예  <br/> |아니요  <br/> |
|**프런트 엔드 풀: 이중 스택** <br/> |예  <br/> |예  <br/> |아니요  <br/> |
|**프런트 엔드 풀: IPv6** <br/> |아니요  <br/> |아니요  <br/> |예\*  <br/> |
   
\*랩 환경 에서만이 조합을 사용 합니다.
  
다음 표는 내부 및 외부 경계 인터페이스의 지원 되는 조합의 행렬입니다.
  
**Edge 풀 (내부에 지) 및 Edge 풀 (외부 가장자리) 행렬**

||**Edge 풀 (외부 가장자리): IPv4** <br/> |**Edge 풀 (외부 가장자리): 이중 스택** <br/> |**Edge 풀 (외부에 지): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Edge 풀 (내부에 지): IPv4** <br/> |예  <br/> |예  <br/> |아니요  <br/> |
|**Edge 풀 (내부에 지): 이중 스택** <br/> |아니요  <br/> |예  <br/> |아니요  <br/> |
|**Edge 풀 (내부에 지): IPv6** <br/> |아니요  <br/> |아니요  <br/> |예\*  <br/> |
   
\*랩 환경 에서만이 조합을 사용 합니다.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6에 대 한 고급 엔터프라이즈 음성 지원
<a name="Ent_V"> </a>

CAC (호출 허용 제어), 향상 된 9-1-1 (E9-1-1) 또는 미디어 바이패스를 포함 하는 배포는 IPv4 전용 또는 듀얼 누적 구현으로 구성 되어야 합니다. IPv6만 사용 하는 끝점은 이러한 기능을 사용할 수 없습니다.
  
> [!NOTE]
> 듀얼 누적 배포의 경우 비즈니스용 skype 서버 클라이언트가 IPv6을 사용 하 여 비즈니스용 Skype 서버에 연결 하더라도 비즈니스용 Skype 서버는 E9-1-1을 지원 하기 위해 적절 한 IPv4 주소를 매핑하는 데 가장 좋은 노력을 기울여야 합니다. 
  
IPv6 주소를 사용 하는 위치 정보 서비스는 지원 되지 않습니다.
  
UM (통합 메시징)는 IPv6을 지원 하지 않습니다. Exchange UM의 경우 DNS 확인이 IPv6 주소를 반환 하지 않도록 해야 합니다. 전화를 음성 메일로 보내면 IPv6을 사용 하면 오류를 일으킬 수 있습니다. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>IPv6에 대 한 다른 비즈니스용 Skype 서버 기능 지원
<a name="Ent_V"> </a>

앞에서 언급 한 기능 및 구성 요소 외에도 비즈니스용 Skype Server는 다음 기능에 대 한 IPv6을 지원 합니다.
  
- **영구 채팅**
    
    토폴로지 작성기를 사용 하 여 영구 채팅을 위해 IPv6을 구성 합니다. 영구 채팅 구성에 대 한 자세한 내용은 영구 채팅 서버 배포 설명서를 참조 하세요.
    
- **경력 (체감 품질) 및 통화 정보 기록 (CDR) 보고서**
    
    모니터링 보고서에는 IPv4 또는 IPv6 유형에 관계 없이 모니터링 서버 데이터베이스에 저장 되는 IP 주소가 포함 됩니다.
    
## <a name="technical-requirements-for-ipv6"></a>IPv6에 대한 기술 요구 사항
<a name="tech"> </a>

IPv6 용 비즈니스용 Skype Server를 구성 하려는 경우 다음 요구 사항을 염두에 두어야 합니다.
  
- 비즈니스용 Skype Server에서 IPv6 주소를 사용 하려면 IPv6 주소로 검색 하 고 확인 해야 하는 레코드에 대 한 DNS (domain name system) 레코드를 만들어야 합니다. IPv6 DNS가 호스트 AAAA (쿼드-A) 레코드를 사용 합니다. 배포에 IPv4와 IPv6을 모두 사용 하는 경우 IPv4에 대 한 호스트 A 레코드와 IPv6의 호스트 AAAA 레코드를 모두 구성 하 고 유지 관리 하는 것이 좋습니다. 배포를 IPv6으로 완전히 전환 하더라도 여전히 IPv4를 사용 하는 외부 사용자에 대해 IPv4 DNS 호스트 레코드가 필요할 수 있습니다.
    
    Ipv6 사용을 시작 하기 전에 IPv6 DNS 호스트 레코드를 배포할 수 있습니다. 클라이언트나 서버에서 IPv6을 사용 하지 않는 경우 레코드가 참조 되지 않습니다. 전환 기술에는 변환 기술 구성 및 정책에 따라 어떤 레코드를 사용할지 결정 하 게 됩니다.
    
- 각 IPv6 주소에는 범위가 있습니다. Ipv6 주소 지정에 사용할 수 있는 세 가지 범위는 IPv6 전역 주소 (공용 IPv4 주소와 유사), IPv6 고유 로컬 주소 (사설 IPv4 주소 범위와 비슷함), IPv6 링크 로컬 주소 (다음의 자동 개인 IP 주소와 유사) IPv4 용 Windows Server). 풀 내의 모든 서버에는 동일한 범위의 IPv6 주소가 있어야 합니다. 
    
> [!IMPORTANT]
> IPv6은 복잡 한 주제로, 네트워크 팀과 인터넷 공급자와의 신중한 계획이 필요 하며, Windows Server 수준에서 지정 하는 주소와 비즈니스용 Skype 서버 수준이 제대로 작동 하는지 확인 하는 데 도움이 됩니다. IPv6 주소 지정 및 계획에 대 한 추가 리소스는이 항목의 끝부분에 있는 링크를 참조 하세요. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>IPv6에 대한 마이그레이션 및 동시 사용 고려 사항
<a name="migration"> </a>

Lync Server 2010 또는 Office Communications Server에서는 IPv6 (IP 버전 6)이 지원 되지 않습니다. 시험 운용 목적으로 Lync Server 2010 및 비즈니스용 Skype 서버 이중 스택 공존을 테스트할 수 있습니다. 모든 풀에 대해 IPv6 (듀얼 스택 네트워크)을 사용 하도록 설정 하기 전에 지정 된 중앙 사이트의 모든 풀을 비즈니스용 Skype 서버로 업그레이드 하는 것이 좋습니다. IPv6에 대해서만 풀을 구성 해야 하는 경우 테스트를 위해 랩 환경에서 IPv6 전용 풀을 설정 하는 것이 좋습니다.
  
마이그레이션 및 공존 중에 지원 되는 시나리오는 다음과 같습니다.
  
- IPv4 모드의 비즈니스용 skype 서버, Lync Server 2013 및 Lync Server 2010 풀은 듀얼 스택 모드의 비즈니스용 Skype 서버와 함께 공존할만 합니다.
    
- Ipv6 전용 풀에 siloed 인 경우에는 비즈니스용 Skype 서버 풀 for IPv6 전용 모드입니다.
    
## <a name="see-also"></a>참고 항목
<a name="migration"> </a>

[비즈니스용 Skype에서 IP 주소 유형 구성](ip-address-types.md)

[IP 버전 6 주소 지정 아키텍처](https://tools.ietf.org/html/rfc4291)
  
[IPv6 글로벌 유니캐스트 주소 형식](https://tools.ietf.org/html/rfc3587)
  
[고유한 로컬 IPv6 유니캐스트 주소](https://tools.ietf.org/html/rfc4193)
