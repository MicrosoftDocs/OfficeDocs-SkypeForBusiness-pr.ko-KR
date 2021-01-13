---
title: 비즈니스용 Skype 서버의 에지 서버 환경 요구 사항
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 67435465-b4d0-4e38-8e03-56a60b844a34
description: '요약: 비즈니스용 Skype 서버의 에지 서버에 대한 환경 요구 사항에 대해 자세히 알아보십시오.'
ms.openlocfilehash: 3757a67d36260cce7d14ddf451a3a436429f24fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813838"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 에지 서버 환경 요구 사항
 
**요약:** 비즈니스용 Skype 서버의 에지 서버에 대한 환경 요구 사항에 대해 자세히 알아보십시오.
  
비즈니스용 Skype 서버 에지 서버 환경 자체 외부에서 많은 계획 및 준비를 진행해야 합니다. 이 문서에서는 아래 목록에 따라 조직 환경에서 준비해야 하는 준비를 검토합니다.
  
- [토폴로지 계획](edge-environmental-requirements.md#TopoPlan)
    
- [DNS 계획](edge-environmental-requirements.md#DNSPlan)
    
- [인증서 계획](edge-environmental-requirements.md#CertPlan)
    
- [포트 및 방화벽 계획](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>토폴로지 계획
<a name="TopoPlan"> </a>

비즈니스용 Skype 서버 에지 서버 토폴로지에서는 다음을 사용할 수 있습니다.
  
- 라우팅 가능한 공용 IP 주소입니다.
    
- 라우팅할 수 없는 개인 IP  주소(NAT(대칭 네트워크 주소 변환)가 사용되는 경우).
    
> [!TIP]
> 에지 서버는 각 서비스에 대해 고유한 포트가 있는 단일 IP 주소를 사용하도록 구성하거나 각 서비스에 대해 고유한 IP 주소를 사용할 수 있지만 기본적으로 TCP 443인 동일한 기본 포트를 사용할 수 있습니다. IP 주소 요구 사항 섹션에 자세한 내용은 아래를 참조하세요. 
  
NAT를 통해 라우팅할 수 없는 개인 IP 주소를 선택하는 경우 다음 점에 유의하세요.
  
- 세 가지 외부 인터페이스 모두에서 라우팅 가능한 개인 IP **주소를** 사용해야 합니다.
    
- 들어오는 **트래픽과** 나가는 트래픽에 대해 대칭 NAT를 구성해야 합니다. 대칭 NAT는 비즈니스용 Skype 서버 에지 서버에서 사용할 수 있는 유일한 지원 NAT입니다.
    
- 받는 원본 주소를 변경하지 못하도록 NAT를 구성합니다. A/V 에지 서비스는 들어오는 원본 주소를 수신하여 최적의 미디어 경로를 찾을 수 있도록 합니다.
    
- 에지 서버는 공용 A/V 에지 IP 주소에서 서로 통신할 수 있도록 해야 합니다. 방화벽에서 이 트래픽을 허용해야 합니다.
    
- DNS **부하** 분산을 사용하는 경우 확장된 통합 에지 서버에만 NAT를 사용할 수 있습니다. HLB(하드웨어 부하 분산)를 사용하는 경우 NAT 없이 공개적으로 라우팅 가능한 IP 주소를 **사용해야** 합니다.
    
단일 및 확장된 통합 에지 서버 토폴로지 모두에 대해 대칭 NAT를 수행하는 라우터 또는 방화벽 뒤에 액세스, 웹 회의 및 A/V 에지 인터페이스가 없는 경우(하드웨어 부하 분산을 사용하지 않는 한) 문제가 없습니다.
  
### <a name="summary-of-edge-server-topology-options"></a>에지 서버 토폴로지 옵션 요약

비즈니스용 Skype 서버 에지 서버 배포에 사용할 수 있는 몇 가지 토폴로지 옵션이 있습니다.
  
- 개인 IP 주소 및 NAT가 있는 단일 통합 에지
    
- 공용 IP 주소의 단일 통합 에지
    
- 개인 IP 주소 및 NAT가 있는 확장된 통합 에지
    
- 공용 IP 주소의 확장된 통합 에지
    
- 하드웨어 부하 균형 조정을 통해 확장된 통합 에지
    
토폴로지별로 어떤 옵션을 사용할지 요약하여 제공하는 다음 표를 참조하세요.
  
|**토폴로지**|**고가용성**|**에지 풀의 외부 에지 서버에 필요한 추가 DNS 레코드가 있나요?**|**비즈니스용 Skype 서버 세션에 대한 에지 장애 조치(failover)**|**비즈니스용 Skype 서버 페더ation 세션에 대한 에지 장애 조치(failover)**|
|:-----|:-----|:-----|:-----|:-----|
|개인 IP 주소 및 NAT가 있는 단일 통합 에지  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|공용 IP 주소의 단일 통합 에지  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|개인 IP 주소 및 NAT(DNS 부하가 균형 조정된) 조정된 통합 에지  <br/> |예  <br/> |예  <br/> |예  <br/> |예&sup1;  <br/> |
|공용 IP 주소를 사용하는 조정된 통합 에지(DNS 부하가 균형 조정)  <br/> |예  <br/> |예  <br/> |예  <br/> |예&sup1;  <br/> |
|하드웨어 부하 균형 조정을 통해 확장된 통합 에지  <br/> |예  <br/> |아니요(VIP당 DNS A 레코드 하나)  <br/> |예  <br/> |예  <br/> |
   
&sup1; DNS 부하 분산을 사용하는 Exchange UM(통합 메시징) 원격 사용자 장애 조치(failover)를 수행하려면 Exchange 2013 이상이 필요합니다.
  
### <a name="ip-address-requirements"></a>IP 주소 요구 사항

기본 수준에서 세 가지 서비스에는 IP 주소가 필요합니다. 액세스 에지 서비스, 웹 회의 에지 서비스 및 A/V 에지 서비스 각 서비스에 대해 하나씩 세 개의 IP 주소를 사용할 수도 있습니다. 또는 IP 주소를 하나씩 사용하고 각 서비스를 다른 [](edge-environmental-requirements.md#PortFirewallPlan) 포트에 둘 수 있습니다(포트 및 방화벽 계획 섹션에서 일부에 대한 자세한 내용은 확인할 수 있습니다). 단일 통합 에지 환경의 경우 그 정도입니다.
  
> [!NOTE]
> 위에서 설명한 대로 세 서비스 모두에 대해 하나의 IP 주소를 가지게 선택하고 서로 다른 포트에서 실행할 수 있습니다. 그러나 명확히 말하면 권장되지 않습니다. 고객이 이 시나리오에서 사용하게 될 대체 포트에 액세스할 수 없는 경우 에지 환경의 전체 기능에 액세스할 수 없습니다. 
  
확장된 통합 토폴로지에서는 약간 더 복잡할 수 있으므로, 토폴로지 선택의 기본 결정 지점은 고가용성 및 부하 분산입니다. 고가용성 요구는 부하 분산 선택에 영향을 줄 수 있습니다(표 다음에 더 많은 내용은 설명).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>확장 통합 에지의 IP 주소 요구 사항(역할당 IP 주소)

|**풀당 에지 서버 수**|**DNS 부하 분산에 필요한 IP 주소 수**|**하드웨어 부하 분산에 필요한 IP 주소 수**|
|:-----|:-----|:-----|
|2   <br/> |6   <br/> |3개(VIP당 1개) + 6개  <br/> |
|3   <br/> |9   <br/> |3개(VIP당 1개) + 9개  <br/> |
|4   <br/> |12   <br/> |3개(VIP당 1개) + 12개  <br/> |
|5   <br/> |15   <br/> |3개(VIP당 1개) +15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>확장 통합 에지의 IP 주소 요구 사항(모든 역할의 단일 IP 주소)

|**풀당 에지 서버 수**|**DNS 부하 분산에 필요한 IP 주소 수**|**하드웨어 부하 분산에 필요한 IP 주소 수**|
|:-----|:-----|:-----|
|2   <br/> |2   <br/> |1개(VIP당 1개) + 2개  <br/> |
|3   <br/> |3   <br/> |1개(VIP당 1개) + 3개  <br/> |
|4   <br/> |4   <br/> |1개(VIP당 1개) + 4개  <br/> |
|5   <br/> |5   <br/> |1개(VIP당 1개) + 5개  <br/> |
   
계획하는 동안 생각해 볼 몇 가지 추가 정보를 살펴보아 봐야 합니다.
  
- **고가용성:** 배포에 고가용성이 필요한 경우 풀에 에지 서버를 두 개 이상 배포해야 합니다. 단일 에지 풀이 최대 12대의 에지 서버를 지원할 것입니다(토폴로지 작성기에서는 테스트 또는 지원되지 않는 최대 20대의 에지 서버를 추가할 수 있으므로 이렇게 하지 않는 것이 좋습니다. 에지 서버가 12대 이상 필요한 경우 에지 풀을 추가로 만들어야 합니다.
    
- **하드웨어 부하 분산:** 대부분의 시나리오에서는 DNS 부하 분산을 사용하는 것이 좋습니다. 하드웨어 부하 분산도 지원되지만 특히 DNS 부하 분산을 사용하는 단일 시나리오에는 필요합니다.
    
  - Exchange 2007 또는 Exchange 2010에 대한 외부 액세스(SP 없음) UM(통합 메시징)
    
- **DNS 부하** 분산: UM의 경우 Exchange 2010 SP1 이상은 DNS 부하 분산에서 지원할 수 있습니다. 이전 버전의 Exchange에 대해 DNS 부하 분산을 사용해야 하는 경우 해당 트래픽이 작동하지만 모든 트래픽이 풀의 첫 번째 서버로 이동하고, 사용할 수 없는 경우 이후에 해당 트래픽이 실패합니다.
    
    다음을 사용하는 회사와 페더링하는 경우 DNS 부하 분산을 사용하는 것이 좋습니다.
- 비즈니스용 Skype 서버 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft 365 또는 Office 365
- 비즈니스용 Skype 서버 2019:
    - Lync Server 2013
    - Business Server 2015용 Skype
    - Microsoft 365 또는 Office 365
    
## <a name="dns-planning"></a>DNS 계획
<a name="DNSPlan"> </a>

비즈니스용 Skype 서버 에지 서버 배포의 경우 DNS를 제대로 준비하는 것이 중요합니다. 올바른 레코드가 배치된 경우 배포가 훨씬 더 간단합니다. 개요를 설명한 다음 이러한 시나리오에 대한 DNS 레코드를 설명하는 몇 가지 테이블을 나열하기 위해 위의 섹션에서 토폴로지가 선택되었습니다. 필요한 경우 비즈니스용 Skype 서버에 대한 몇 가지 고급 에지 서버 [DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) 계획도 있습니다.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>단일 통합 에지 서버 시나리오에 대한 DNS 레코드

이러한 레코드는 공용 IPS 또는 NAT가 있는 개인 IPS를 사용하는 Singe 에지 서버에 필요한 DNS 레코드입니다. 예제 데이터이기 때문에 자체 항목을 더 쉽게 작업할 수 있도록 예제 IPS를 제공합니다.
  
- 내부 네트워크 어댑터: 172.25.33.10(기본 게이트웨이가 할당되지 않은 경우)
    
    > [!NOTE]
    > 에지 내부 인터페이스를 포함하는 네트워크에서 비즈니스용 Skype 서버 또는 Lync Server 2013 클라이언트를 실행하는 서버가 포함된 네트워크(예: 172.25.33.0에서 192.168.10.0)로의 경로가 있는지 확인합니다. 
  
- 외부 네트워크 어댑터:
    
  - 공용 IPS:
    
  - 액세스 에지: 131.107.155.10(기본 게이트웨이가 공용 라우터로 설정되어 있습니다.예: 131.107.155.1)
    
  - 웹 회의 에지: 131.107.155.20(보조)
    
  - A/V 에지: 131.107.155.30(보조)
    
  웹 회의 및 A/V 에지 공용 IP 주소는 Windows Server의 로컬 영역 연결 속성에 대한 TCP/IPv4(인터넷 프로토콜 버전 4) 및 인터넷 프로토콜 버전 6(TCP/IPv6) 속성의 고급 섹션에 있는 추가(보조) IP 주소입니다.
    
  - 개인 IPS:
    
  - 액세스 에지: 10.45.16.10(기본 게이트웨이가 라우터로 설정된 기본 게이트웨이 예: 10.45.16.1)
    
  - 웹 회의 에지: 10.45.16.20(보조)
    
  - A/V 에지: 10.45.16.30(보조)
    
웹 회의 및 A/V 에지 공용 IP 주소는 Windows Server의 로컬 영역 연결 속성에 대한 TCP/IPv4(인터넷 프로토콜 버전 4) 및 인터넷 프로토콜 버전 6(TCP/IPv6) 속성의 고급 섹션에 있는 추가(보조) IP 주소입니다.
  
> [!TIP]
>다음과 같은 다른 구성이 가능합니다.
  
- 외부 네트워크 어댑터에 하나의 IP 주소를 사용할 수 있습니다. 다른 포트(비즈니스용 Skype 서버에서 할 수 있는)를 사용하여 서비스 간을 차별화해야 하지만 대체 포트를 차단할 수 있는 방화벽이 몇 가지 있기 때문에 권장되지 않습니다. 이에 대한 자세한 내용은 [포트 및](edge-environmental-requirements.md#PortFirewallPlan) 방화벽 계획 섹션을 참조하세요.
    
- 외부 네트워크 어댑터 1개 대신 3개의 외부 네트워크 어댑터를 사용할 수 있으며 각 어댑터에 서비스 IP 중 하나를 할당할 수 있습니다. 그 이유는 무엇일까요? 서비스가 분리되고 문제가 발생하면 문제를 해결하는 것이 더 쉬워지고 문제를 해결하는 동안 다른 서비스가 계속 작동할 수 있습니다.
    
|**위치**|**Type**|**Port(포트)**|**FQDN 또는 DNS 레코드**|**IP 주소 또는 FQDN**|**참고**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|외부 DNS  <br/> |레코드  <br/> |해당 없음  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 <br/> **private:** 10.45.16.10 <br/> |액세스 에지 서비스의 외부 인터페이스입니다. 비즈니스용 Skype 사용자가 있는 모든 SIP 도메인에 대해 하나씩만 필요합니다.  <br/> |
|외부 DNS  <br/> |레코드  <br/> |해당 없음  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 <br/> **private:** 10.45.16.20 <br/> |웹 회의 에지 서비스의 외부 인터페이스입니다.  <br/> |
|외부 DNS  <br/> |레코드  <br/> |해당 없음  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 <br/> **private:** 10.45.16.30 <br/> |A/V 에지 서비스에 대한 외부 인터페이스입니다.  <br/> |
|외부 DNS  <br/> |SRV record(SRV 레코드)  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |액세스 에지 서비스의 외부 인터페이스입니다. 비즈니스용 Skype 서버, Lync Server 2013 및 Lync Server 2010 클라이언트가 외부에서 작동하려면 이 SRV 레코드가 필요합니다. 비즈니스용 Skype 사용자가 있는 모든 도메인에 대해 하나씩 필요합니다.  <br/> |
|외부 DNS  <br/> |SRV record(SRV 레코드)  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |액세스 에지 서비스의 외부 인터페이스입니다. 이 SRV 레코드는 허용된 SIP 도메인이라고 하는 페더랜드 파트너의 자동 DNS 검색에 필요합니다. 비즈니스용 Skype 사용자가 있는 모든 도메인에 대해 하나씩 필요합니다.  <br/> |
|내부 DNS  <br/> |레코드  <br/> |해당 없음  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |통합 에지의 내부 인터페이스입니다.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>확장된 DNS 및 하드웨어 에지 서버 시나리오에 대한 DNS 레코드

이러한 레코드는 공용 IPS 또는 NAT가 있는 개인 IPS를 사용하는 Singe 에지 서버에 필요한 DNS 레코드입니다. 예제 데이터이기 때문에 자체 항목을 더 쉽게 작업할 수 있도록 예제 IPS를 제공합니다.
  
- 내부 네트워크 어댑터:
    
  - 노드 1: 172.25.33.10(기본 게이트웨이가 할당되지 않은 경우)
    
  - 노드 2: 172.25.33.11(기본 게이트웨이가 할당되지 않은 경우)
    
    > [!NOTE]
    > 에지 내부 인터페이스를 포함하는 네트워크에서 비즈니스용 Skype 서버 또는 Lync Server 2013 클라이언트를 실행하는 서버가 포함된 네트워크(예: 172.25.33.0에서 192.168.10.0)로의 경로가 있는지 확인합니다. 
  
- 외부 네트워크 어댑터:
    
  - 노드 1
    
     - 공용 IPS:
    
        - 액세스 에지: 131.107.155.10(기본 게이트웨이가 공용 라우터로 설정되어 있습니다.예: 131.107.155.1)
    
        - 웹 회의 에지: 131.107.155.20(보조)
    
        - A/V 에지: 131.107.155.30(보조)
    
          웹 회의 및 A/V 에지 공용 IP 주소는 Windows Server의 로컬 영역 연결 속성에 대한 TCP/IPv4(인터넷 프로토콜 버전 4) 및 인터넷 프로토콜 버전 6(TCP/IPv6) 속성의 고급 섹션에 있는 추가(보조) IP 주소입니다.
    
    - 개인 IPS:
    
         - 액세스 에지: 10.45.16.10(기본 게이트웨이가 라우터로 설정된 기본 게이트웨이 예: 10.45.16.1)
    
         - 웹 회의 에지: 10.45.16.20(보조)
    
         - A/V 에지: 10.45.16.30(보조)
    
      웹 회의 및 A/V 에지 공용 IP 주소는 Windows Server의 로컬 영역 연결 속성에 대한 TCP/IPv4(인터넷 프로토콜 버전 4) 및 인터넷 프로토콜 버전 6(TCP/IPv6) 속성의 고급 섹션에 있는 추가(보조) IP 주소입니다.
    
  - 노드 2
    
    - 공용 IPS:
    
      - 액세스 에지: 131.107.155.11(기본 게이트웨이가 공용 라우터로 설정되어 있습니다.예: 131.107.155.1)
    
      - 웹 회의 에지: 131.107.155.21(보조)
    
      - A/V 에지: 131.107.155.31(보조)
    
      웹 회의 및 A/V 에지 공용 IP 주소는 Windows Server의 로컬 영역 연결 속성에 대한 TCP/IPv4(인터넷 프로토콜 버전 4) 및 인터넷 프로토콜 버전 6(TCP/IPv6) 속성의 고급 섹션에 있는 추가(보조) IP 주소입니다.
    
  - 개인 IPS:
    
    - 액세스 에지: 10.45.16.11(기본 게이트웨이가 라우터로 설정되어 있습니다.10.45.16.1)
    
    - 웹 회의 에지: 10.45.16.21(보조)
    
    - A/V 에지: 10.45.16.31(보조)
    
      웹 회의 및 A/V 에지 공용 IP 주소는 Windows Server의 로컬 영역 연결 속성에 대한 TCP/IPv4(인터넷 프로토콜 버전 4) 및 인터넷 프로토콜 버전 6(TCP/IPv6) 속성의 고급 섹션에 있는 추가(보조) IP 주소입니다.
    
다음과 같은 다른 구성이 가능합니다.
  
- 외부 네트워크 어댑터에 하나의 IP 주소를 사용할 수 있습니다. 다른 포트(비즈니스용 Skype 서버에서 할 수 있는)를 사용하여 서비스 간을 차별화해야 하지만 대체 포트를 차단할 수 있는 방화벽이 몇 가지 있기 때문에 권장되지 않습니다. 이에 대한 자세한 내용은 [포트 및](edge-environmental-requirements.md#PortFirewallPlan) 방화벽 계획 섹션을 참조하세요.
    
- 외부 네트워크 어댑터 1개 대신 3개의 외부 네트워크 어댑터를 사용할 수 있으며 각 어댑터에 서비스 IP 중 하나를 할당할 수 있습니다. 그 이유는 무엇일까요? 서비스가 분리되고 문제가 발생하면 문제를 해결하는 것이 더 쉬워지고 문제를 해결하는 동안 다른 서비스가 계속 작동할 수 있습니다.
    
|**위치**|**Type**|**Port(포트)**|**FQDN 또는 DNS 레코드**|**IP 주소 또는 FQDN**|**참고**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|외부 DNS  <br/> |레코드  <br/> |해당 없음  <br/> |sip.contoso.com  <br/> |**public:** 131.107.155.10 및 131.107.155.11 <br/> **private:** 10.45.16.10 및 10.45.16.11 <br/> |액세스 에지 서비스의 외부 인터페이스입니다. 비즈니스용 Skype 사용자가 있는 모든 SIP 도메인에 대해 하나씩만 필요합니다.  <br/> |
|외부 DNS  <br/> |레코드  <br/> |해당 없음  <br/> |webcon.contoso.com  <br/> |**public:** 131.107.155.20 및 131.107.155.21 <br/> **private:** 10.45.16.20 및 10.45.16.21 <br/> |웹 회의 에지 서비스의 외부 인터페이스입니다.  <br/> |
|외부 DNS  <br/> |레코드  <br/> |해당 없음  <br/> |av.contoso.com  <br/> |**public:** 131.107.155.30 및 131.107.155.31 <br/> **private:** 10.45.16.30 및 10.45.16.31 <br/> |A/V 에지 서비스에 대한 외부 인터페이스입니다.  <br/> |
|외부 DNS  <br/> |SRV record(SRV 레코드)  <br/> |443  <br/> |_sip._tls.contoso.com  <br/> |sip.contoso.com  <br/> |액세스 에지 서비스의 외부 인터페이스입니다. 비즈니스용 Skype 서버, Lync Server 2013 및 Lync Server 2010 클라이언트가 외부에서 작동하려면 이 SRV 레코드가 필요합니다. 비즈니스용 Skype가 있는 모든 도메인에 대해 하나씩 필요합니다.  <br/> |
|외부 DNS  <br/> |SRV record(SRV 레코드)  <br/> |5061  <br/> |_sipfederationtls._tcp.contoso.com  <br/> |sip.contoso.com  <br/> |액세스 에지 서비스의 외부 인터페이스입니다. 이 SRV 레코드는 허용된 SIP 도메인이라고 하는 페더랜드 파트너의 자동 DNS 검색에 필요합니다. 비즈니스용 Skype가 있는 모든 도메인에 대해 하나씩 필요합니다.  <br/> |
|내부 DNS  <br/> |레코드  <br/> |해당 없음  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 및 172.25.33.11  <br/> |통합 에지의 내부 인터페이스입니다.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>페더전에 대한 DNS 레코드(모든 시나리오)

|**위치**|**Type**|**Port(포트)**|**FQDN**|**FQDN 호스트 레코드**|**참고**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|외부 DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp.contoso.com  <br/> |sip.contoso.com  <br/> |자동 DNS 검색에 필요한 SIP 액세스 에지 외부 인터페이스입니다. 다른 잠재적 페더러다인 파트너가 사용됩니다. 이를 "SIP 도메인 허용"이라고도 합니다. 비즈니스용 Skype 사용자가 있는 각 SIP 도메인에 대해 이러한 중 하나가 필요합니다.  <br/><br/> **참고:** 모바일 및 푸시 알림 클리어링 하우스에 대해 이 SRV 레코드가 필요합니다. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>Extensible Messaging and Presence Protocol에 대한 DNS 레코드

|**위치**|**Type**|**Port(포트)**|**FQDN**|**IP 주소 또는 FQDN 호스트 레코드**|**참고**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|외부 DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-server._tcp.contoso.com  <br/> |xmpp.contoso.com  <br/> |액세스 에지 서비스 또는 에지 풀의 XMPP 프록시 인터페이스입니다. 비즈니스용 Skype 서버 사용 가능 사용자가 있는 모든 내부 SIP 도메인에 대해 필요에 따라 이 작업을 반복해야 합니다. 여기서 XMPP 연락처에 대한 연락처는 다음을 통해 허용됩니다.  <br/> • 글로벌 정책  <br/> • 사용자가 사용하도록 설정된 사이트 정책  <br/> • 비즈니스용 Skype 서버 사용 가능 사용자에게 적용된 사용자 정책  <br/> 허용된 XMPP 정책도 XMPP 페더럴 사용자 정책에서 구성해야 합니다.  <br/> |
|외부 DNS  <br/> |SRV  <br/> |A  <br/> |xmpp.contoso.com  <br/> |XMPP 프록시 서비스를 호스팅하는 에지 서버 또는 에지 풀에 있는 액세스 에지 서비스의 IP 주소  <br/> |이는 XMPP 프록시 서비스를 호스트하는 에지 서버 또는 에지 풀의 액세스 에지 서비스를 지점으로 합니다. 일반적으로 만드는 SRV 레코드는 이 호스트(A 또는 AAAA) 레코드를 지점합니다.  <br/> |
   
> [!NOTE]
> XMPP 게이트웨이 및 xxies는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. 자세한 [내용은 XMPP 페더링 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조하세요.

## <a name="certificate-planning"></a>인증서 계획
<a name="CertPlan"> </a>

비즈니스용 Skype 서버는 서버 간 및 서버에서 클라이언트로의 보안 및 암호화된 통신을 위해 인증서를 사용 합니다. 예상대로 인증서는 서버의 DNS 레코드가 인증서의 SN(주체 이름) 및 SAN(주체 대체 이름)과 일치해야 합니다. 이렇게 하면 계획 단계에서 인증서의 SN 및 SAN 항목에 대한 올바른 FQDN이 DNS에 등록되어 있습니다.
  
외부 및 내부 인증서 요구 사항에 대해 별도로 논의한 다음 둘 다에 대한 요구 사항을 제공하는 표를 살펴보하겠습니다.
  
### <a name="external-certificates"></a>외부 인증서

최소한 외부 에지 서버 인터페이스에 할당된 인증서는 공용 CA(인증 기관)에서 제공해야 합니다. 특정 CA를 추천할 수 없지만, 선호하는 CA가 나열되어 있는지 확인할 수 있는 CA, [Unified Communications](/SkypeForBusiness/certification/services-ssl) 인증서 파트너 목록이 있습니다.
  
이 공용 인증서에 대한 CA에 요청을 제출해야 하는 경우 어떻게 해야 합니까? 이 작업을 수행하기 위한 몇 가지 방법이 있습니다.
  
- 비즈니스용 Skype 서버 설치를 진행한 다음 에지 서버 배포를 진행할 수 있습니다. 비즈니스용 Skype 서버 배포 마법사에는 인증서 요청을 생성하는 단계가 있습니다. 그러면 선택한 CA로 보낼 수 있습니다.
    
- 또한 비즈니스 요구 Windows PowerShell 배포 전략에 더 많은 인라인이 있는 경우 이 요청을 생성하는 데 이 명령을 사용할 수도 있습니다.
    
- 마지막으로 CA에 자체 제출 프로세스가 있을 수 있습니다. 이 프로세스는 다른 방법이나 다른 Windows PowerShell 수 있습니다. 이 경우 참조를 위해 여기에 제공된 정보 외에 해당 설명서에 따라야 합니다.
    
인증서를 확인한 후 비즈니스용 Skype 서버에서 다음 서비스에 할당해야 합니다.
  
- 액세스 에지 서비스 인터페이스
    
- 웹 회의 에지 서비스 인터페이스
    
- 오디오/비디오 인증 서비스(오디오 및 비디오 스트림을 암호화하는 데 인증서를 사용하지 않는 A/V 에지 서비스에 혼동하지 말 것)
    
> [!IMPORTANT]
> 모든 에지 서버(동일한 에지 서버 풀에 속하는 경우)에는 미디어 릴레이 인증 서비스에 대해 동일한 개인 키를 사용하는 동일한 인증서가 필요합니다. 
  
### <a name="internal-certificates"></a>내부 인증서

내부 에지 서버 인터페이스의 경우 공용 CA의 공용 인증서 또는 조직의 내부 CA에서 발급된 인증서를 사용할 수 있습니다. 내부 인증서에 대해 기억해야 할 점은 SN 항목과 SAN 항목이 사용되지 않는다는 점입니다. 따라서 내부 인증서의 SAN에 대해 걱정할 필요가 없습니다.
  
### <a name="required-certificates-table"></a>필수 인증서 테이블

요청에 대한 도움을 줄 수 있는 표가 있습니다. 여기서 FQDN 항목은 샘플 도메인에만 해당합니다. 자체 개인 도메인 및 공용 도메인을 기반으로 요청을 해야 하지만 사용한 지침은 다음과 같습니다.
  
- <span></span>contoso.com: 공용 FQDN
    
- fabrikam .com: 두 번째 공용 FQDN(여러 SIP 도메인이 있는 경우 요청할 사항의 데모로 <span></span> 추가)
    
- Contoso <span></span> .net: 내부 도메인
    
#### <a name="edge-certificate-table"></a>에지 인증서 테이블

단일 에지 서버 또는 에지 풀을 수행하고 있는지에 관계없이 인증서에 필요한 사항입니다.
  
|**구성 요소**|**SN(주체 이름)**|**SAN(주체 대체 이름)/순서**|**참고**|
|:-----|:-----|:-----|:-----|
|외부 에지  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |공용 CA에서 요청해야 하는 인증서입니다. 다음에 대한 외부 에지 인터페이스에 할당해야 합니다.  <br/> • 액세스 에지  <br/> • 웹 회의 에지  <br/> • 오디오/비디오 인증  <br/> <br/>다행한 소식은 토폴로지 작성기에서 이 배포에 대해 정의한 값에 따라 요청을 제출한 후 인증서에 SA가 자동으로 추가됩니다. 추가 SIP 도메인 또는 지원해야 하는 기타 항목에 대한 SAN 항목만 추가하면 됩니다. 이 인스턴스에서 sip.contoso.com 이유는 무엇입니까? 이는 자동으로 발생하며, 제대로 작동하기 위해 필요합니다.  <br/><br/> **참고:** 이 인증서는 공용 인스턴트 메시징 연결에도 사용할 수 있습니다. 다른 작업을 따로 할 필요는 없지만 이 설명서의 이전 버전에서는 별도의 표로 나열되어 있습니다. <br/> |
|내부 에지  <br/> |sfbedge.contoso.com  <br/> |해당 없음  <br/> |공용 CA 또는 내부 CA에서 이 인증서를 얻을 수 있습니다. 서버 EKU(확장된 키 사용)를 포함해야 하며 내부 에지 인터페이스에 할당합니다.  <br/> |
   
XMPP(Extensible Messaging and Presence Protocol)에 대한 인증서가 필요한 경우 위의 외부 에지 테이블 항목과 동일하게 보이지만 다음과 같은 두 개의 추가 SAN 항목이 있습니다.
  
- xmpp. <span></span> <span></span>contoso.com
    
- \*<span></span>.contoso.com
    
현재 XMPP는 Google Talk용 비즈니스용 Skype 서버에서만 지원됩니다. 원하는 경우 또는 다른 모든 기능에 XMPP를 사용하려는 경우 타사 공급업체와의 기능이 관련되어 있는지 확인해야 합니다.
  
## <a name="port-and-firewall-planning"></a>포트 및 방화벽 계획
<a name="PortFirewallPlan"> </a>

비즈니스용 Skype 서버 에지 서버 배포를 위한 포트 및 방화벽에 대한 계획을 수립하면 문제 해결과 스트레스를 며칠 또는 몇 주가 절약할 수 있습니다. 따라서 프로토콜 사용 현황과 NAT 및 공용 IP 시나리오에서 열고 인바운드 및 아웃바운드해야 하는 포트를 나타내는 몇 가지 테이블을 나열할 것입니다. HLB(하드웨어 부하가 균형 조정된 시나리오)에 대한 별도의 테이블과 이에 대한 몇 가지 추가 지침도 제공됩니다. 비즈니스용 Skype 서버에서 특정 배포 관련 우려를 확인할 수 있는 몇 가지 [에지](scenarios.md) 서버 시나리오도 있습니다.
  
### <a name="general-protocol-usage"></a>일반 프로토콜 사용

외부 및 내부 방화벽에 대한 요약 표를 살펴보기 전에 다음 표도 살펴보아야 합니다.
  
|**오디오/비디오 전송**|**Usage**|
|:-----|:-----|
|UDP  <br/> |오디오 및 비디오에 대한 기본 전송 계층 프로토콜입니다.  <br/> |
|TCP  <br/> |오디오 및 비디오에 대한 폴백 전송 계층 프로토콜입니다.  <br/> 비즈니스용 Skype 서버, Lync Server 2013 및 Lync Server 2010에 대한 응용 프로그램 공유에 필요한 전송 계층 프로토콜입니다.  <br/> 비즈니스용 Skype 서버, Lync Server 2013 및 Lync Server 2010으로의 파일 전송에 필요한 전송 계층 프로토콜입니다.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>외부 포트 방화벽 요약 표

원본 IP 주소 및 대상 IP 주소에는 NAT에서 개인 IP 주소를 사용하는 사용자와 공용 IP 주소를 사용하는 사용자에 대한 정보가 포함되어 있습니다. 이 섹션에서는 비즈니스용 Skype 서버 섹션의 에지 서버 시나리오에 있는 모든 [설정에 대해](scenarios.md) 설명합니다.
  
|**역할 또는 프로토콜**|**TCP 또는 UDP**|**대상 포트 또는 포트 범위**|**원본 IP 주소**|**대상 IP 주소**|**참고**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 비즈니스용 Skype 서버 2019에서 지원되지 않습니다. |TCP  <br/> |5269  <br/> |모두  <br/> |XMPP 프록시 서비스(액세스 에지 서비스와 IP 주소 공유)  <br/> |XMPP 프록시 서비스는 정의된 XMPP 페더전에 있는 XMPP 연락처의 트래픽을 수락합니다.  <br/> |
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 액세스 에지 서비스 <br/> **공용 IP:** 에지 서버 액세스 에지 서비스 공용 IP 주소 <br/> |모두  <br/> |인증서 해지 및 CRL 검사 및 검색  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 액세스 에지 서비스 <br/> **공용 IP:** 에지 서버 액세스 에지 서비스 공용 IP 주소 <br/> |모두  <br/> |TCP를 통해 DNS 쿼리.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 액세스 에지 서비스 <br/> **공용 IP:** 에지 서버 액세스 에지 서비스 공용 IP 주소 <br/> |모두  <br/> |UDP를 통해 DNS 쿼리.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |모두  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 액세스 에지 서비스 <br/> **공용 IP:** 에지 서버 액세스 에지 서비스 공용 IP 주소 <br/> |외부 사용자 액세스에 대한 클라이언트-서버 SIP 트래픽입니다.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |모두  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 액세스 에지 서비스 <br/> **공용 IP:** 에지 서버 액세스 에지 서비스 공용 IP 주소 <br/> |SIP를 사용하는 페더타 및 공용 IM 연결의 경우.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 액세스 에지 서비스 <br/> **공용 IP:** 에지 서버 액세스 에지 서비스 공용 IP 주소 <br/> |모두  <br/> |SIP를 사용하는 페더타 및 공용 IM 연결의 경우.  <br/> |
|웹 회의/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |모두  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 웹 회의 에지 서비스 <br/> **공용 IP:** 에지 서버 웹 회의 에지 서비스 공용 IP 주소 <br/> |웹 회의 미디어.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 A/V 에지 서비스 <br/> **공용 IP:** 에지 서버 A/V 에지 서비스 공용 IP 주소 <br/> |모두  <br/> |미디어 트래픽을 릴레이하는 데 사용됩니다.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 A/V 에지 서비스 <br/> **공용 IP:** 에지 서버 A/V 에지 서비스 공용 IP 주소 <br/> |모두  <br/> |미디어 트래픽을 릴레이하는 데 사용됩니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 A/V 에지 서비스 <br/> **공용 IP:** 에지 서버 A/V 에지 서비스 공용 IP 주소 <br/> |모두  <br/> |3478 아웃바운드:  <br/> • 비즈니스용 Skype 서버에서 통신하는 에지 서버의 버전을 확인하는 데 사용됩니다.  <br/> • 에지 서버 간의 미디어 트래픽에 사용됩니다.  <br/> • Lync Server 2010과의 페더전에 필요합니다.  <br/> • 조직 내에 여러 에지 풀을 배포하는 경우 필요합니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |모두  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 A/V 에지 서비스 <br/> **공용 IP:** 에지 서버 A/V 에지 서비스 공용 IP 주소 <br/> |포트 3478에서 UDP를 통해 STUN/TURN 후보 협상  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |모두  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 A/V 에지 서비스 <br/> **공용 IP:** 에지 서버 A/V 에지 서비스 공용 IP 주소 <br/> |포트 443의 TCP를 통해 STUN/TURN 후보 협상  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 A/V 에지 서비스 <br/> **공용 IP:** 에지 서버 A/V 에지 서비스 공용 IP 주소 <br/> |모두  <br/> |포트 443의 TCP를 통해 STUN/TURN 후보 협상  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>내부 포트 방화벽 요약 표

|**Protocol(프로토콜)**|**TCP 또는 UDP**|**Port(포트)**|**원본 IP 주소**|**대상 IP 주소**|**참고**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |다음 중 XMPP 게이트웨이 서비스를 실행합니다.  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀  <br/> |에지 서버 내부 인터페이스  <br/> |프런트 엔드 서버 또는 프런트 엔드 풀에서 실행되는 XMPP 게이트웨이 서비스에서 아웃바운드 XMPP 트래픽  <br/> **참고:** XMPP 게이트웨이 및 xxies는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. 자세한 [내용은 XMPP 페더링 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조하세요.|
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |모든 경우:  <br/> • Director  <br/> • Director 풀  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀  <br/> |에지 서버 내부 인터페이스  <br/> |Director, Director 풀, 프런트 엔드 서버 또는 프런트 엔드 풀에서 에지 서버 내부 인터페이스로의 아웃바운드 SIP 트래픽입니다.  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5061  <br/> |에지 서버 내부 인터페이스  <br/> |모든 경우:  <br/> • Director  <br/> • Director 풀  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀  <br/> |에지 서버 내부 인터페이스에서 Director, Director 풀, 프런트 엔드 서버 또는 프런트 엔드 풀로의 인바운드 SIP 트래픽  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |모든 경우:  <br/> • 프런트 엔드 서버  <br/> • 각 프런트 엔드 서버  <br/>  프런트 엔드 풀에서 <br/> |에지 서버 내부 인터페이스  <br/> |프런트 엔드 서버 또는 각 프런트 엔드 서버(프런트 엔드 풀이 있는 경우)에서 에지 서버 내부 인터페이스로의 웹 회의 트래픽  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |모든 경우:  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀  <br/> • 이 에지 서버를 사용하는 모든 Survivable Branch Appliance  <br/> • 이 에지 서버를 사용하는 모든 Survivable Branch Server  <br/> |에지 서버 내부 인터페이스  <br/> |에지 서버를 사용하여 프런트 엔드 서버 또는 프런트 엔드 풀 또는 Survivable Branch Appliance 또는 Survivable Branch Server에서 A/V 사용자 인증  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |모두  <br/> |에지 서버 내부 인터페이스  <br/> |내부 및 외부 사용자와 SSS(Survivable Branch Appliance) 또는 Survivable Branch Server 간의 A/V 미디어 전송에 대한 기본 경로입니다.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |모두  <br/> |에지 서버 내부 인터페이스  <br/> |UDP 통신이 작동하지 않는 경우 내부 및 외부 사용자와 SSP(Survivable Branch Appliance) 또는 SSP 서버 간의 A/V 미디어 전송에 대한 폴백 경로입니다. 그런 다음 TCP는 파일 전송 및 데스크톱 공유에 사용됩니다.  <br/> |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |모든 경우:  <br/> • 중앙 관리 저장소를 보유하는 프런트 엔드 서버  <br/> • 중앙 관리 저장소를 보유하는 프런트 엔드 풀  <br/> |에지 서버 내부 인터페이스  <br/> |중앙 관리 저장소에서 에지 서버로의 변경 내용 복제  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |모두  <br/> |에지 서버 내부 인터페이스  <br/> |비즈니스용 Skype 서버 관리 셸 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄(ClsController.exe) 또는 에이전트(ClsAgent.exe) 명령 및 로그 컬렉션을 사용하는 중앙 로깅 서비스 컨트롤러  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |모두  <br/> |에지 서버 내부 인터페이스  <br/> |비즈니스용 Skype 서버 관리 셸 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄(ClsController.exe) 또는 에이전트(ClsAgent.exe) 명령 및 로그 컬렉션을 사용하는 중앙 로깅 서비스 컨트롤러  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |모두  <br/> |에지 서버 내부 인터페이스  <br/> |비즈니스용 Skype 서버 관리 셸 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄(ClsController.exe) 또는 에이전트(ClsAgent.exe) 명령 및 로그 컬렉션을 사용하는 중앙 로깅 서비스 컨트롤러  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>에지 포트 테이블용 하드웨어 부하 균형 조정기

추가 하드웨어에서는 약간 더 복잡하기에 HLB(하드웨어 부하 에지) 및 에지 포트 자체 섹션을 제공합니다. 이 특정 시나리오에 대한 지침은 아래 표를 참조하세요.
  
#### <a name="external-port-firewall-summary-table"></a>외부 포트 방화벽 요약 표

원본 IP 주소 및 대상 IP 주소에는 NAT에서 개인 IP 주소를 사용하는 사용자와 공용 IP 주소를 사용하는 사용자에 대한 정보가 포함되어 있습니다. 이 섹션에서는 비즈니스용 Skype 서버 섹션의 에지 서버 시나리오에 있는 모든 [설정에 대해](scenarios.md) 설명합니다.
  
|**역할 또는 프로토콜**|**TCP 또는 UDP**|**대상 포트 또는 포트 범위**|**원본 IP 주소**|**대상 IP 주소**|**참고**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |TCP  <br/> |80  <br/> |에지 서버 액세스 에지 서비스 공용 IP 주소  <br/> |모두  <br/> |인증서 해지 및 CRL 검사 및 검색  <br/> |
|Access/DNS  <br/> |TCP  <br/> |53  <br/> |에지 서버 액세스 에지 서비스 공용 IP 주소  <br/> |모두  <br/> |TCP를 통해 DNS 쿼리.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |에지 서버 액세스 에지 서비스 공용 IP 주소  <br/> |모두  <br/> |UDP를 통해 DNS 쿼리.  <br/> |
|A/V/RTP  <br/> |TCP  <br/> |50000-59999  <br/> |에지 서버 A/V 에지 서비스 IP 주소  <br/> |모두  <br/> |미디어 트래픽을 릴레이하는 데 사용됩니다.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |에지 서버 A/V 에지 서비스 공용 IP 주소  <br/> |모두  <br/> |미디어 트래픽을 릴레이하는 데 사용됩니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |에지 서버 A/V 에지 서비스 공용 IP 주소  <br/> |모두  <br/> |3478 아웃바운드:  <br/> • 비즈니스용 Skype 서버에서 통신하는 에지 서버의 버전을 확인하는 데 사용됩니다.  <br/> • 에지 서버 간의 미디어 트래픽에 사용됩니다.  <br/> • 페더전에 필요합니다.  <br/> • 조직 내에 여러 에지 풀을 배포하는 경우 필요합니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |모두  <br/> |에지 서버 A/V 에지 서비스 공용 IP 주소  <br/> |포트 3478에서 UDP를 통해 STUN/TURN 후보 협상  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |모두  <br/> |에지 서버 A/V 에지 서비스 공용 IP 주소  <br/> |포트 443의 TCP를 통해 STUN/TURN 후보 협상  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |에지 서버 A/V 에지 서비스 공용 IP 주소  <br/> |모두  <br/> |포트 443의 TCP를 통해 STUN/TURN 후보 협상  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>내부 포트 방화벽 요약 표

|**Protocol(프로토콜)**|**TCP 또는 UDP**|**Port(포트)**|**원본 IP 주소**|**대상 IP 주소**|**참고**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |TCP  <br/> |23456  <br/> |다음 중 XMPP 게이트웨이 서비스를 실행합니다.  <br/> • 프런트 엔드 서버  <br/> • XMPP 게이트웨이 서비스를 실행하는 프런트 엔드 풀 VIP 주소  <br/> |에지 서버 내부 인터페이스  <br/> |프런트 엔드 서버 또는 프런트 엔드 풀에서 실행되는 XMPP 게이트웨이 서비스에서 아웃바운드 XMPP 트래픽  <br/><br/> **참고:** XMPP 게이트웨이 및 xxies는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. 자세한 [내용은 XMPP 페더링 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조하세요. |
|HTTPS  <br/> |TCP  <br/> |4443  <br/> |모든 경우:  <br/> • 중앙 관리 저장소를 보유하는 프런트 엔드 서버  <br/> • 중앙 관리 저장소를 보유하는 프런트 엔드 풀  <br/> |에지 서버 내부 인터페이스  <br/> |중앙 관리 저장소에서 에지 서버로의 변경 내용 복제  <br/> |
|PSOM/MTLS  <br/> |TCP  <br/> |8057  <br/> |모든 경우:  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀의 각 프런트 엔드 서버  <br/> |에지 서버 내부 인터페이스  <br/> |프런트 엔드 서버 또는 각 프런트 엔드 서버(프런트 엔드 풀이 있는 경우)에서 에지 서버 내부 인터페이스로의 웹 회의 트래픽  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |모든 경우:  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀의 각 프런트 엔드 서버  <br/> |에지 서버 내부 인터페이스  <br/> |내부 및 외부 사용자와 SSS(Survivable Branch Appliance) 또는 Survivable Branch Server 간의 A/V 미디어 전송에 대한 기본 경로입니다.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |모든 경우:  <br/> • 프런트 엔드 서버  <br/> • 풀의 각 프런트 엔드 서버  <br/> |에지 서버 내부 인터페이스  <br/> |UDP 통신이 작동하지 않는 경우 내부 및 외부 사용자와 SSP(Survivable Branch Appliance) 또는 SSP 서버 간의 A/V 미디어 전송에 대한 폴백 경로입니다. 그런 다음 TCP는 파일 전송 및 데스크톱 공유에 사용됩니다.  <br/> |
|MTLS  <br/> |TCP  <br/> |50001  <br/> |모두  <br/> |에지 서버 내부 인터페이스  <br/> |비즈니스용 Skype 서버 관리 셸 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄(ClsController.exe) 또는 에이전트(ClsAgent.exe) 명령 및 로그 컬렉션을 사용하는 중앙 로깅 서비스 컨트롤러  <br/> |
|MTLS  <br/> |TCP  <br/> |50002  <br/> |모두  <br/> |에지 서버 내부 인터페이스  <br/> |비즈니스용 Skype 서버 관리 셸 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄(ClsController.exe) 또는 에이전트(ClsAgent.exe) 명령 및 로그 컬렉션을 사용하는 중앙 로깅 서비스 컨트롤러  <br/> |
|MTLS  <br/> |TCP  <br/> |50003  <br/> |모두  <br/> |에지 서버 내부 인터페이스  <br/> |비즈니스용 Skype 서버 관리 셸 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄(ClsController.exe) 또는 에이전트(ClsAgent.exe) 명령 및 로그 컬렉션을 사용하는 중앙 로깅 서비스 컨트롤러  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>외부 인터페이스 가상 IPS

|**역할 또는 프로토콜**|**TCP 또는 UDP**|**대상 포트 또는 포트 범위**|**원본 IP 주소**|**대상 IP 주소**|**참고**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 비즈니스용 Skype 서버 2019에서 지원되지 않습니다. |TCP  <br/> |5269  <br/> |모두  <br/> |XMPP 프록시 서비스(액세스 에지 서비스와 IP 주소 공유)  <br/> |XMPP 프록시 서비스는 정의된 XMPP 페더전에 있는 XMPP 연락처의 트래픽을 수락합니다.  <br/> |
|XMPP  <br/>비즈니스용 Skype 서버 2019에서 지원되지 않습니다. |TCP  <br/> |5269  <br/> |XMPP 프록시 서비스(액세스 에지 서비스와 IP 주소 공유)  <br/> |모두  <br/> |XMPP 프록시 서비스는 정의된 XMPP 페더ations의 XMPP 연락처에서 트래픽을 전송합니다.  <br/> |
|Access/SIP(TLS)  <br/> |TCP  <br/> |443  <br/> |모두  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 액세스 에지 서비스 <br/> **공용 IP:** 에지 서버 액세스 에지 서비스 공용 IP 주소 <br/> |외부 사용자 액세스에 대한 클라이언트-서버 SIP 트래픽입니다.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |모두  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 액세스 에지 서비스 <br/> **공용 IP:** 에지 서버 액세스 에지 서비스 공용 IP 주소 <br/> |SIP를 사용하는 페더타 및 공용 IM 연결의 경우.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 액세스 에지 서비스 <br/> **공용 IP:** 에지 서버 액세스 에지 서비스 공용 IP 주소 <br/> |모두  <br/> |SIP를 사용하는 페더타 및 공용 IM 연결의 경우.  <br/> |
|웹 회의/PSOM(TLS)  <br/> |TCP  <br/> |443  <br/> |모두  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 웹 회의 에지 서비스 <br/> **공용 IP:** 에지 서버 웹 회의 에지 서비스 공용 IP 주소 <br/> |웹 회의 미디어.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |모두  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 A/V 에지 서비스 <br/> **공용 IP:** 에지 서버 A/V 에지 서비스 공용 IP 주소 <br/> |포트 3478에서 UDP를 통해 STUN/TURN 후보 협상  <br/> |
|A/V/STUN. MSTURN  <br/> |TCP  <br/> |443  <br/> |모두  <br/> |**NAT를 사용하는 개인 IP:** 에지 서버 A/V 에지 서비스 <br/> **공용 IP:** 에지 서버 A/V 에지 서비스 공용 IP 주소 <br/> |포트 443의 TCP를 통해 STUN/TURN 후보 협상  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>내부 인터페이스 가상 IPS

여기서 설명하는 지침은 약간 다를 수 있습니다. 실제로 HLB 상황에서는 다음과 같은 상황에서만 내부 VIP를 통해 라우팅하는 것이 좋습니다.
  
- Exchange 2007 또는 Exchange 2010 UM(통합 메시징)을 사용하는 경우
    
- Edge를 사용하는 레거시 클라이언트가 있는 경우
    
다음 표에서는 이러한 시나리오에 대한 지침을 제공하지만, 그렇지 않으면 CMS(중앙 관리 저장소)를 통해 트래픽을 인식하는 개별 에지 서버로 라우팅할 수 있습니다(물론 에지 서버 정보를 최신으로 유지해야 합니다).
  
|**Protocol(프로토콜)**|**TCP 또는 UDP**|**Port(포트)**|**원본 IP 주소**|**대상 IP 주소**|**참고**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |모든 경우:  <br/> • Director  <br/> • Director 풀 VIP 주소  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀 VIP 주소  <br/> |에지 서버 내부 인터페이스  <br/> |Director, Director 풀 VIP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 VIP 주소에서 에지 서버 내부 인터페이스로의 아웃바운드 SIP 트래픽입니다.  <br/> |
|Access/SIP(MTLS)  <br/> |TCP  <br/> |5061  <br/> |에지 서버 내부 VIP 인터페이스  <br/> |모든 경우:  <br/> • Director  <br/> • Director 풀 VIP 주소  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀 VIP 주소  <br/> |에지 서버 내부 인터페이스에서 Director, Director 풀 VIP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 VIP 주소로의 인바운드 SIP 트래픽  <br/> |
|SIP/MTLS  <br/> |TCP  <br/> |5062  <br/> |모든 경우:  <br/> • 프런트 엔드 서버 IP 주소  <br/> • 프런트 엔드 풀 IP 주소  <br/> • 이 에지 서버를 사용하는 모든 Survivable Branch Appliance  <br/> • 이 에지 서버를 사용하는 모든 Survivable Branch Server  <br/> |에지 서버 내부 인터페이스  <br/> |에지 서버를 사용하여 프런트 엔드 서버 또는 프런트 엔드 풀 또는 Survivable Branch Appliance 또는 Survivable Branch Server에서 A/V 사용자 인증  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |모두  <br/> |에지 서버 내부 인터페이스  <br/> |내부 사용자와 외부 사용자 간의 A/V 미디어 전송에 대한 기본 경로입니다.  <br/> |
|STUN/MSTURN  <br/> |TCP  <br/> |443  <br/> |모두  <br/> |에지 서버 내부 VIP 인터페이스  <br/> |UDP 통신이 작동하지 않는 경우 내부 사용자와 외부 사용자 간의 A/V 미디어 전송에 대한 폴백 경로입니다. 그런 다음 TCP는 파일 전송 및 데스크톱 공유에 사용됩니다.  <br/> |
