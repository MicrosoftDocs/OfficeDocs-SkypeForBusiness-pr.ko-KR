---
title: 비즈니스용 Skype 서버의 Edge 서버 환경 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버에서 Edge 서버의 환경 요구 사항에 대해 알아보세요.'
ms.openlocfilehash: 15cc6c54d420cd95962afb1faa219a3a370056a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803378"
---
# <a name="edge-server-environmental-requirements-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 Edge 서버 환경 요구 사항
 
**요약:** 비즈니스용 Skype 서버에서 Edge 서버의 환경 요구 사항에 대해 알아보세요.
  
비즈니스용 Skype Server Edge 서버 환경 자체 외에 많은 계획 및 준비를 수행 해야 합니다. 이 문서에서는 아래 목록에 따라 조직 환경에서 수행 해야 하는 준비 사항을 검토 합니다.
  
- [토폴로지 계획](edge-environmental-requirements.md#TopoPlan)
    
- [DNS 계획](edge-environmental-requirements.md#DNSPlan)
    
- [인증서 계획](edge-environmental-requirements.md#CertPlan)
    
- [포트 및 방화벽 계획](edge-environmental-requirements.md#PortFirewallPlan)
    
## <a name="topology-planning"></a>토폴로지 계획
<a name="TopoPlan"> </a>

비즈니스용 Skype Server Edge 서버 토폴로지에서는 다음을 사용할 수 있습니다.
  
- 라우팅 가능한 공용 IP 주소
    
- **대칭** 네트워크 주소 변환 (NAT)을 사용 하는 경우 라우팅할 수 없는 개인 IP 주소
    
> [!TIP]
> 각 서비스에 대해 별도의 포트가 있는 단일 IP 주소를 사용 하도록 Edge 서버를 구성 하거나 각 서비스에 대해 고유한 IP 주소를 사용할 수 있지만, 기본적으로 TCP 443이 기본 포트를 사용 하도록 설정할 수 있습니다. 자세한 내용은 아래의 IP 주소 요구 사항 섹션을 참조 하세요. 
  
NAT를 사용 하 여 라우팅할 수 없는 개인 IP 주소를 선택 하는 경우 다음 사항에 유의 해야 합니다.
  
- **세 개의 모든** 외부 인터페이스에서 라우팅할 수 있는 개인 IP 주소를 사용 해야 합니다.
    
- 들어오고 나가는 트래픽에 대해 **대칭** NAT를 구성 해야 합니다. 대칭 NAT는 비즈니스용 Skype Server Edge 서버에서 사용할 수 있는 유일한 지원 되는 NAT입니다.
    
- 들어오는 원본 주소를 변경 하지 않도록 NAT를 구성 합니다. A/V Edge 서비스는 수신 되는 원본 주소를 수신 하 여 최적의 미디어 경로를 찾을 수 있어야 합니다.
    
- Edge 서버는 공용 A/V에 지 IP 주소에서 서로 통신할 수 있어야 합니다. 방화벽에서이 트래픽을 허용 해야 합니다.
    
- DNS 부하 분산을 사용 하는 경우에 **만** NAT를 사용 하 여 통합 된 Edge 서버를 확장할 수 있습니다. HLB (하드웨어 부하 분산)를 사용 하는 경우에는 NAT **없이** 공개적으로 라우팅할 수 있는 IP 주소를 사용 해야 합니다.
    
단일 및 배율 통합 Edge 서버 토폴로지에 대해 대칭 NAT를 수행 하는 라우터 또는 방화벽 뒤의 Access, 웹 회의 및 A/V Edge 인터페이스 (하드웨어 로드 균형 조정을 사용 하지 않는 한)에는 문제가 없습니다.
  
### <a name="summary-of-edge-server-topology-options"></a>Edge 서버 토폴로지 옵션 요약

비즈니스용 Skype Server Edge 서버 배포에 사용할 수 있는 여러 가지 토폴로지 옵션이 있습니다.
  
- 개인 IP 주소와 NAT를 사용 하는 단일 통합 된 가장자리
    
- 공용 IP 주소가 있는 통합 된 단일 Edge
    
- 개인 IP 주소 및 NAT로 크기가 조정 된 통합 된 가장자리
    
- 공용 IP 주소를 사용 하 여 크기가 조정 된 통합 된 가장자리
    
- 하드웨어 부하 분산 장치를 사용 하 여 확장 된 통합 가장자리
    
하나를 선택 하는 데 도움이 되도록 각 토폴로지에 사용할 수 있는 옵션에 대 한 요약을 제공 하는 다음 표가 있습니다.
  
|**토폴로지**|**고가용성**|**Edge 풀의 외부에 지 서버에 추가 DNS 레코드가 필요 한가요?**|**비즈니스용 Skype 서버 세션에 대 한 Edge 장애 조치**|**비즈니스용 Skype 서버 페더레이션 세션에 대 한 Edge 장애 조치**|
|:-----|:-----|:-----|:-----|:-----|
|개인 IP 주소와 NAT를 사용 하는 단일 통합 된 가장자리  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|공용 IP 주소가 있는 통합 된 단일 Edge  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |아니요  <br/> |
|개인 IP 주소 및 NAT를 사용 하 여 크기 조정 된 통합 된 가장자리 (DNS 부하 분산)  <br/> |예  <br/> |예  <br/> |예  <br/> |예&sup1  <br/> |
|공용 IP 주소를 사용 하 여 크기 조정 된 통합 된 가장자리 (DNS 부하 분산)  <br/> |예  <br/> |예  <br/> |예  <br/> |예&sup1  <br/> |
|하드웨어 부하 분산 장치를 사용 하 여 확장 된 통합 가장자리  <br/> |예  <br/> |없음 (VIP 당 하나의 DNS A 레코드)  <br/> |예  <br/> |예  <br/> |
   
&sup1 DNS 부하 분산을 사용 하는 exchange UM (통합 메시징) 원격 사용자 장애 조치에는 Exchange 2013 이상 버전이 필요 합니다.
  
### <a name="ip-address-requirements"></a>IP 주소 요구 사항

기본 수준에서 세 가지 서비스에는 IP 주소가 필요 합니다. 액세스에 지 서비스, 웹 회의에 지 서비스, A/V Edge 서비스. 각 서비스에 대해 하나씩 세 개의 IP 주소를 사용 하거나 한 가지 및 옵트인을 사용 하 여 각 서비스를 다른 포트에 배치할 수 있습니다 (일부에 대 한 자세한 내용은 [포트 및 방화벽 계획](edge-environmental-requirements.md#PortFirewallPlan) 섹션을 참조 하세요). 통합 된 단일 Edge 환경의 경우 매우 유용 합니다.
  
> [!NOTE]
> 위에서 설명한 대로 세 가지 서비스 모두에 대해 하나의 IP 주소를 선택 하 여 다른 포트에서 실행할 수 있습니다. 하지만이 방법을 선택 하지 않는 것이 좋습니다. 고객이이 시나리오에서 사용 하는 대체 포트에 액세스할 수 없는 경우에는 Edge 환경의 전체 기능에 액세스할 수 없습니다. 
  
통합 된 토폴로지가 축소 되어 약간 더 복잡할 수 있으므로, 토폴로지 선택에 대 한 기본 결정 지점이 높은 가용성 및 부하 분산 이라는 점을 염두에 두면서 IP 주소 요구 사항을 배치 하는 일부 테이블을 살펴보겠습니다. 높은 사용 가능성 요구는 부하 분산 선택에 영향을 줄 수 있습니다 (테이블 뒤에 표시 됨).
  
#### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>확장 통합 된 가장자리에 대 한 IP 주소 요구 사항 (역할별 IP 주소)

|**풀 당 Edge 서버 수**|**DNS 부하 분산에 필요한 IP 주소 수**|**하드웨어 부하 분산에 필요한 IP 주소 수**|
|:-----|:-----|:-----|
|2  <br/> |26  <br/> |3 (VIP 당 1 개) + 6  <br/> |
|3  <br/> |되었는지  <br/> |3 (VIP 당 1 개) + 9  <br/> |
|4(tcp/ipv4)  <br/> |까지  <br/> |3 (VIP 당 1 개) + 12  <br/> |
|5mb  <br/> |~  <br/> |3 (VIP 당 1) + 15  <br/> |
   
#### <a name="ip-address-requirements-for-scale-consolidated-edge-single-ip-address-for-all-roles"></a>통합 된 Edge 확장에 대 한 IP 주소 요구 사항 (모든 역할의 단일 IP 주소)

|**풀 당 Edge 서버 수**|**DNS 부하 분산에 필요한 IP 주소 수**|**하드웨어 부하 분산에 필요한 IP 주소 수**|
|:-----|:-----|:-----|
|2  <br/> |2  <br/> |1 (VIP 당 1 개) + 2  <br/> |
|3  <br/> |3  <br/> |1 (VIP 당 1 개) + 3  <br/> |
|4(tcp/ipv4)  <br/> |4(tcp/ipv4)  <br/> |1 (VIP 당 1 개) + 4  <br/> |
|5mb  <br/> |5mb  <br/> |1 (VIP 당 1 개) + 5  <br/> |
   
계획 하는 동안 고려해 야 할 몇 가지 추가 작업을 살펴보겠습니다.
  
- **고가용성: 배포**에 높은 가용성을 필요로 하는 경우 풀에 Edge 서버를 두 개 이상 배포 해야 합니다. 단일 Edge 풀이 최대 12 대의 서버를 지원 하기는 하지만 토폴로지 작성기를 사용 하면 테스트 하거나 지원 하지 않는 최대 20 개까지 지원할 수 있으므로이 작업을 수행 하지 않는다는 것을 권장 합니다. Edge 서버를 12 개 이상 필요로 하는 경우에는 추가 Edge 풀을 만들어야 합니다.
    
- **하드웨어 로드 균형 조정**: 대부분의 시나리오에서 DNS 부하 분산을 권장 합니다. 물론 하드웨어 로드 균형 조정도 지원 되지만, 특히 DNS 부하 분산을 통한 단일 시나리오에 필요 합니다.
    
  - Exchange 2007 또는 Exchange 2010 (SP 없음)에 대 한 외부 액세스 UM (통합 메시징)
    
- **Dns 부하 분산**: UM, EXCHANGE 2010 SP1 이상에서 dns 부하 분산을 통해 지원할 수 있습니다. 이전 버전의 Exchange에 대 한 DNS 부하 분산을 사용 해야 하는 경우에는 작동 하지만,이에 대 한 모든 트래픽은 풀의 첫 번째 서버로 이동 하 고, 사용할 수 없는 경우에는 해당 트래픽이 계속 실패 하 게 됩니다.
    
    다음과 같은 기능을 사용 하 여 회사와 페더레이션 하는 경우에도 DNS 부하 분산이 권장 됩니다.
- 비즈니스용 Skype 서버 2015:
    - Lync Server 2010
    - Lync Server 2013
    - Microsoft Office O365
- 비즈니스용 Skype 서버 2019:
    - Lync Server 2013
    - 비즈니스용 Skype 서버 2015
    - Microsoft Office 365.
    
## <a name="dns-planning"></a>DNS 계획
<a name="DNSPlan"> </a>

비즈니스용 Skype Server Edge 서버 배포의 경우 DNS를 올바르게 준비 하는 것이 중요 합니다. 적절 한 레코드를 사용 하 여 배포 하는 것이 훨씬 더 쉽습니다. 개요를 수행 하기 위해 위의 섹션에서 토폴로지를 선택한 후 이러한 시나리오에 대 한 DNS 레코드를 개요로 표시 하는 두 개의 테이블을 나열 하는 것이 좋습니다. 또한 필요한 경우 더 자세한 정보를 얻을 수 있도록 [비즈니스용 Skype 서버용 고급 Edge SERVER DNS 계획](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md) 을 제공 합니다.
  
### <a name="dns-records-for-single-consolidated-edge-server-scenarios"></a>통합 된 단일에 지 서버 시나리오에 대 한 DNS 레코드

이는 공용 Ip 또는 NAT와의 사설 Ip를 사용 하 여 단일 Edge 서버에 필요한 DNS 레코드입니다. 이는 샘플 데이터 이므로 사용자 자신의 항목을 보다 쉽게 사용할 수 있도록 예제 IPs를 제공 합니다.
  
- 내부 네트워크 어댑터: 172.25.33.10 (할당 된 기본 게이트웨이 없음)
    
    > [!NOTE]
    > Edge 내부 인터페이스를 포함 하는 네트워크에서 비즈니스용 Skype Server 또는 Lync Server 2013 클라이언트 (예: 172.25.33.0에서 192.168.10.0)를 실행 하는 서버가 포함 된 네트워크에 대 한 경로가 있는지 확인 합니다. 
  
- 외부 네트워크 어댑터:
    
  - 공용 Ip:
    
  - 액세스에 지: 131.107.155.10 (기본 게이트웨이가 공용 라우터에 설정 된 경우 (예: 131.107.155.1)
    
  - 웹 회의에 지: 131.107.155.20 (보조)
    
  - A/V Edge: 131.107.155.30 (보조)
    
  웹 회의 및 A/V Edge 공용 IP 주소는 Windows Server의 로컬 영역 연결 속성에 대 한 인터넷 프로토콜 버전 4 (TCP/IP) 및 인터넷 프로토콜 버전 6 (TCP/IP)의 고급 섹션에 있는 추가 (보조) IP 주소입니다.
    
  - 개인 Ip:
    
  - 액세스에 지: 10.45.16.10 (기본 게이트웨이가 라우터에 설정 된 경우 (예: 10.45.16.1)
    
  - 웹 회의에 지: 10.45.16.20 (보조)
    
  - A/V Edge: 10.45.16.30 (보조)
    
웹 회의 및 A/V Edge 공용 IP 주소는 Windows Server의 로컬 영역 연결 속성에 대 한 인터넷 프로토콜 버전 4 (TCP/IP) 및 인터넷 프로토콜 버전 6 (TCP/IP)의 고급 섹션에 있는 추가 (보조) IP 주소입니다.
  
> [!TIP]
>여기에는 다음과 같은 다양 한 구성이 있습니다.
  
- 외부 네트워크 어댑터에서 하나의 IP 주소를 사용할 수 있습니다. 다른 포트 (비즈니스용 Skype 서버에서 수행할 수 있음)를 사용 하 여 사용자의 서비스를 구분 해야 하지만 대체 포트를 차단할 수 있는 방화벽이 있는 경우에는이 방법을 사용 하지 않는 것이 좋습니다. 이에 대 한 자세한 내용은 [포트 및 방화벽 계획](edge-environmental-requirements.md#PortFirewallPlan) 섹션을 참조 하세요.
    
- 하나 대신 3 개의 외부 네트워크 어댑터를 사용 하 고 각 어댑터가 각각에 서비스 Ip 중 하나를 할당할 수 있습니다. 그 이유는 무엇 인가요? 서비스를 구분 하 고 문제가 발생 하는 경우 문제를 쉽게 해결 하 고, 문제가 해결 되는 동안 다른 서비스가 계속 작동 하도록 할 수 있습니다.
    
|**위치**|**유형**|**포트**|**FQDN 또는 DNS 레코드**|**IP 주소 또는 FQDN**|**상속자**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|외부 DNS  <br/> |A 레코드  <br/> |NA  <br/> |sip.contoso.com  <br/> |**공용:** 131.107.155.10 <br/> **비공개:** 10.45.16.10 <br/> |액세스에 지 서비스에 대 한 외부 인터페이스. 모든 SIP 도메인에 대해 비즈니스용 Skype 사용자를 위한 1 개가 필요 합니다.  <br/> |
|외부 DNS  <br/> |A 레코드  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**공용:** 131.107.155.20 <br/> **비공개:** 10.45.16.20 <br/> |웹 회의에 지 서비스에 대 한 외부 인터페이스.  <br/> |
|외부 DNS  <br/> |A 레코드  <br/> |NA  <br/> |av.contoso.com  <br/> |**공용:** 131.107.155.30 <br/> **비공개:** 10.45.16.30 <br/> |A/V Edge 서비스에 대 한 외부 인터페이스.  <br/> |
|외부 DNS  <br/> |SRV 레코드  <br/> |443  <br/> |_sip _tls. m m .com  <br/> |sip.contoso.com  <br/> |액세스에 지 서비스에 대 한 외부 인터페이스. 이 SRV 레코드는 비즈니스용 Skype 서버, Lync Server 2013 및 Lync Server 2010 클라이언트가 외부적으로 작업 하는 데 필요 합니다. 모든 도메인에 비즈니스용 Skype 사용자가 있는 경우 1 개가 필요 합니다.  <br/> |
|외부 DNS  <br/> |SRV 레코드  <br/> |5061  <br/> |_sipfederationtls _tcp. m m .com  <br/> |sip.contoso.com  <br/> |액세스에 지 서비스에 대 한 외부 인터페이스. 이 SRV 레코드는 허용 된 SIP 도메인 이라고 불리는 페더레이션 파트너의 자동 DNS 검색에 필요 합니다. 모든 도메인에 비즈니스용 Skype 사용자가 있는 경우 1 개가 필요 합니다.  <br/> |
|내부 DNS  <br/> |A 레코드  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10  <br/> |통합 된 가장자리에 대 한 내부 인터페이스입니다.  <br/> |
   
### <a name="dns-records-for-scaled-dns-and-hardware-edge-server-scenarios"></a>확장 된 DNS 및 하드웨어 Edge 서버 시나리오에 대 한 DNS 레코드

이는 공용 Ip 또는 NAT와의 사설 Ip를 사용 하 여 단일 Edge 서버에 필요한 DNS 레코드입니다. 이는 샘플 데이터 이므로 사용자 자신의 항목을 보다 쉽게 사용할 수 있도록 예제 IPs를 제공 합니다.
  
- 내부 네트워크 어댑터:
    
  - 노드 1:172.25.33.10 (기본 게이트웨이가 할당 되지 않음)
    
  - 노드 2:172.25.33.11 (기본 게이트웨이가 할당 되지 않음)
    
    > [!NOTE]
    > Edge 내부 인터페이스를 포함 하는 네트워크에서 비즈니스용 Skype Server 또는 Lync Server 2013 클라이언트 (예: 172.25.33.0에서 192.168.10.0)를 실행 하는 서버가 포함 된 네트워크에 대 한 경로가 있는지 확인 합니다. 
  
- 외부 네트워크 어댑터:
    
  - 노드 1
    
     - 공용 Ip:
    
        - 액세스에 지: 131.107.155.10 (기본 게이트웨이가 공용 라우터에 설정 된 경우 (예: 131.107.155.1)
    
        - 웹 회의에 지: 131.107.155.20 (보조)
    
        - A/V Edge: 131.107.155.30 (보조)
    
          웹 회의 및 A/V Edge 공용 IP 주소는 Windows Server의 로컬 영역 연결 속성에 대 한 인터넷 프로토콜 버전 4 (TCP/IP) 및 인터넷 프로토콜 버전 6 (TCP/IP)의 고급 섹션에 있는 추가 (보조) IP 주소입니다.
    
    - 개인 Ip:
    
         - 액세스에 지: 10.45.16.10 (기본 게이트웨이가 라우터에 설정 된 경우 (예: 10.45.16.1)
    
         - 웹 회의에 지: 10.45.16.20 (보조)
    
         - A/V Edge: 10.45.16.30 (보조)
    
      웹 회의 및 A/V Edge 공용 IP 주소는 Windows Server의 로컬 영역 연결 속성에 대 한 인터넷 프로토콜 버전 4 (TCP/IP) 및 인터넷 프로토콜 버전 6 (TCP/IP)의 고급 섹션에 있는 추가 (보조) IP 주소입니다.
    
  - 노드 2
    
    - 공용 Ip:
    
      - 액세스에 지: 131.107.155.11 (기본 게이트웨이가 공용 라우터에 설정 된 경우 (예: 131.107.155.1)
    
      - 웹 회의에 지: 131.107.155.21 (보조)
    
      - A/V Edge: 131.107.155.31 (보조)
    
      웹 회의 및 A/V Edge 공용 IP 주소는 Windows Server의 로컬 영역 연결 속성에 대 한 인터넷 프로토콜 버전 4 (TCP/IP) 및 인터넷 프로토콜 버전 6 (TCP/IP)의 고급 섹션에 있는 추가 (보조) IP 주소입니다.
    
  - 개인 Ip:
    
    - 액세스에 지: 10.45.16.11 (기본 게이트웨이가 라우터에 설정 된 경우 (예: 10.45.16.1)
    
    - 웹 회의에 지: 10.45.16.21 (보조)
    
    - A/V Edge: 10.45.16.31 (보조)
    
      웹 회의 및 A/V Edge 공용 IP 주소는 Windows Server의 로컬 영역 연결 속성에 대 한 인터넷 프로토콜 버전 4 (TCP/IP) 및 인터넷 프로토콜 버전 6 (TCP/IP)의 고급 섹션에 있는 추가 (보조) IP 주소입니다.
    
여기에는 다음과 같은 다양 한 구성이 있습니다.
  
- 외부 네트워크 어댑터에서 하나의 IP 주소를 사용할 수 있습니다. 다른 포트 (비즈니스용 Skype 서버에서 수행할 수 있음)를 사용 하 여 사용자의 서비스를 구분 해야 하지만 대체 포트를 차단할 수 있는 방화벽이 있는 경우에는이 방법을 사용 하지 않는 것이 좋습니다. 이에 대 한 자세한 내용은 [포트 및 방화벽 계획](edge-environmental-requirements.md#PortFirewallPlan) 섹션을 참조 하세요.
    
- 하나 대신 3 개의 외부 네트워크 어댑터를 사용 하 고 각 어댑터가 각각에 서비스 Ip 중 하나를 할당할 수 있습니다. 그 이유는 무엇 인가요? 서비스를 구분 하 고 문제가 발생 하는 경우 문제를 쉽게 해결 하 고, 문제가 해결 되는 동안 다른 서비스가 계속 작동 하도록 할 수 있습니다.
    
|**위치**|**유형**|**포트**|**FQDN 또는 DNS 레코드**|**IP 주소 또는 FQDN**|**상속자**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|외부 DNS  <br/> |A 레코드  <br/> |NA  <br/> |sip.contoso.com  <br/> |**공개:** 131.107.155.10 및 131.107.155.11 <br/> **비공개:** 10.45.16.10 및 10.45.16.11 <br/> |액세스에 지 서비스에 대 한 외부 인터페이스. 모든 SIP 도메인에 대해 비즈니스용 Skype 사용자를 위한 1 개가 필요 합니다.  <br/> |
|외부 DNS  <br/> |A 레코드  <br/> |NA  <br/> |webcon.contoso.com  <br/> |**공개:** 131.107.155.20 및 131.107.155.21 <br/> **비공개:** 10.45.16.20 및 10.45.16.21 <br/> |웹 회의에 지 서비스에 대 한 외부 인터페이스.  <br/> |
|외부 DNS  <br/> |A 레코드  <br/> |NA  <br/> |av.contoso.com  <br/> |**공개:** 131.107.155.30 및 131.107.155.31 <br/> **비공개:** 10.45.16.30 및 10.45.16.31 <br/> |A/V Edge 서비스에 대 한 외부 인터페이스.  <br/> |
|외부 DNS  <br/> |SRV 레코드  <br/> |443  <br/> |_sip _tls. m m .com  <br/> |sip.contoso.com  <br/> |액세스에 지 서비스에 대 한 외부 인터페이스. 이 SRV 레코드는 비즈니스용 Skype 서버, Lync Server 2013 및 Lync Server 2010 클라이언트가 외부적으로 작업 하는 데 필요 합니다. 비즈니스용 Skype를 사용 하는 모든 도메인에 대해 1 개가 필요 합니다.  <br/> |
|외부 DNS  <br/> |SRV 레코드  <br/> |5061  <br/> |_sipfederationtls _tcp. m m .com  <br/> |sip.contoso.com  <br/> |액세스에 지 서비스에 대 한 외부 인터페이스. 이 SRV 레코드는 허용 된 SIP 도메인 이라고 불리는 페더레이션 파트너의 자동 DNS 검색에 필요 합니다. 비즈니스용 Skype를 사용 하는 모든 도메인에 대해 1 개가 필요 합니다.  <br/> |
|내부 DNS  <br/> |A 레코드  <br/> |NA  <br/> |sfvedge.contoso.net  <br/> |172.25.33.10 및 172.25.33.11  <br/> |통합 된 가장자리에 대 한 내부 인터페이스입니다.  <br/> |
   
### <a name="dns-record-for-federation-all-scenarios"></a>페더레이션에 대 한 DNS 레코드 (모든 시나리오)

|**위치**|**유형**|**포트**|**Q**|**FQDN 호스트 레코드**|**상속자**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|외부 DNS  <br/> |SRV  <br/> |5061  <br/> |_sipfederationtls_tcp  <br/> |sip.contoso.com  <br/> |자동 DNS 검색을 위해서는 SIP 액세스에 지 외부 인터페이스가 필요 합니다. 다른 잠재적 페더레이션 파트너가 사용 합니다. "SIP 도메인 허용"이 라고도 합니다. 비즈니스용 Skype 사용자의 각 SIP 도메인에 대해 이러한 작업 중 하나가 필요 합니다.  <br/><br/> **참고:** 이동성 및 푸시 알림 클리어 링 하우스에는이 SRV 레코드가 필요 합니다. <br/> |
   
### <a name="dns-records-for-extensible-messaging-and-presence-protocol"></a>확장 가능한 메시징 및 현재 상태 프로토콜에 대 한 DNS 레코드

|**위치**|**유형**|**포트**|**Q**|**IP 주소 또는 FQDN 호스트 레코드**|**상속자**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|외부 DNS  <br/> |SRV  <br/> |5269  <br/> |_xmpp-서버 _tcp. c a m.  <br/> |xmpp.contoso.com  <br/> |액세스에 지 서비스 또는 Edge 풀의 XMPP 프록시 인터페이스입니다. 이 작업은 비즈니스용 Skype Server를 사용 하는 모든 내부 SIP 도메인에 대해 필요에 따라, XMPP 연락처와의 연락처가 허용 되는 사용자를 위해 반복 해야 합니다.  <br/> • 글로벌 정책  <br/> • 사용자가 사용 하도록 설정 된 사이트 정책  <br/> • 비즈니스용 Skype 서버 사용 가능 사용자에 게 적용 되는 사용자 정책  <br/> 허용 된 XMPP 정책은 XMPP 페더레이션 사용자 정책 에서도 구성 해야 합니다.  <br/> |
|외부 DNS  <br/> |SRV  <br/> |에서  <br/> |xmpp.contoso.com  <br/> |XMPP 프록시 서비스를 호스트 하는 Edge 서버 또는 Edge 풀에 있는 액세스에 지 서비스의 IP 주소  <br/> |이는 XMPP 프록시 서비스를 호스트 하는 Edge 서버나 Edge 풀의 액세스에 지 서비스를 가리킵니다. 일반적으로 사용자가 만드는 SRV 레코드는이 호스트 (A 또는 AAAA) 레코드를 가리킵니다.  <br/> |
   
> [!NOTE]
> XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 자세한 내용은 [XMPP 페더레이션 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조 하세요.

## <a name="certificate-planning"></a>인증서 계획
<a name="CertPlan"> </a>

비즈니스용 Skype 서버는 서버와 서버 간에 모두 안전한 암호화 통신을 위해 인증서를 사용 합니다. 예상 대로 인증서에는 서버에 대 한 DNS 레코드가 인증서의 모든 주체 이름 (SN) 및 주체 대체 이름 (SAN)과 일치 해야 합니다. 이 작업은 현재 계획 단계에서 인증서에 대 한 SN 및 SAN 항목에 대해 DNS에 올바른 Fqdn이 등록 되어 있는지 확인 하는 데 사용 됩니다.
  
외부 및 내부 인증서의 필요에 대해 개별적으로 논의 한 다음 두 가지 요구 사항을 모두 제공 하는 테이블을 살펴봅니다.
  
### <a name="external-certificates"></a>외부 인증서

적어도 외부에 지 서버 인터페이스에 할당 된 인증서는 CA (공개 인증 기관)에서 제공 해야 합니다. 특정 CA를 추천할 수는 없지만, 기본 제공 CA가 나열 되어 있는지 확인 하기 위해 사용할 수 있는 Ca, [통합 커뮤니케이션 인증서 파트너](/SkypeForBusiness/certification/services-ssl) 목록이 있습니다.
  
이 공용 인증서에 대 한 요청을 CA에 제출 해야 하는 시기는 언제 인가요? 이 작업을 수행 하는 몇 가지 방법이 있습니다.
  
- 비즈니스용 Skype 서버 설치 및 Edge 서버 배포를 진행할 수 있습니다. 비즈니스용 Skype 서버 배포 마법사에는 인증서 요청을 생성 하는 단계가 있으며, 이렇게 하면 선택한 CA에 보낼 수 있습니다.
    
- 또한 비즈니스 요구 사항 또는 배포 전략에 더 많은 문제가 있는 경우에는 Windows PowerShell 명령을 사용 하 여이 요청을 생성할 수 있습니다.
    
- 마지막으로 CA에는 고유한 제출 프로세스가 있을 수 있으며, 여기에는 Windows PowerShell 또는 다른 방법이 포함 될 수도 있습니다. 이 경우 참조에 제공 되는 정보 외에도 해당 설명서를 사용 해야 합니다.
    
인증서를 구입한 후에는 비즈니스용 Skype 서버에서 다음 서비스에 할당 해야 합니다.
  
- 액세스에 지 서비스 인터페이스
    
- 웹 회의에 지 서비스 인터페이스
    
- 오디오/비디오 인증 서비스 (이는 인증서를 사용 하 여 오디오 및 비디오 스트림을 암호화 하지 않으므로이를 A/V Edge 서비스와 혼동 하지 마세요.)
    
> [!IMPORTANT]
> 모든 Edge 서버 (동일한 Edge 서버 풀에 속해 있는 경우)는 미디어 릴레이 인증 서비스에 대해 동일한 개인 키를 사용 하 여 정확히 동일한 인증서를 보유 해야 합니다. 
  
### <a name="internal-certificates"></a>내부 인증서

내부에 지 서버 인터페이스의 경우 공개 CA의 공개 인증서 또는 조직의 내부 CA에서 발급 한 인증서를 사용할 수 있습니다. 내부 인증서에 대해 기억해 야 할 점은 SN 항목을 사용 하는 것이 고, SAN 항목이 없기 때문에 내부 인증서의 SAN에 대해 걱정할 필요가 없다는 것입니다.
  
### <a name="required-certificates-table"></a>필수 인증서 테이블

여기에는 요청을 해결 하는 데 도움이 되는 표가 있습니다. 이 FQDN 항목은 예제 도메인에만 해당 됩니다. 사용자의 개인 및 공용 도메인을 기반으로 요청을 수행 해야 하지만, 사용 하는 항목에 대 한 가이드는 다음과 같습니다.
  
- contoso<span></span>: Public FQDN
    
- fabrikam<span></span>: 두 번째 공용 FQDN (여러 SIP 도메인이 있는 경우 요청할 항목의 데모로 추가 됨)
    
- Contoso<span></span>.Net: 내부 도메인
    
#### <a name="edge-certificate-table"></a>Edge 인증서 표

단일 Edge 서버나 Edge 풀을 수행 하 고 있는지 여부에 관계 없이 인증서에는 다음이 필요 합니다.
  
|**요소가**|**주체 이름 (SN)**|**SAN (주체 대체 이름)/order**|**상속자**|
|:-----|:-----|:-----|:-----|
|외부에 지  <br/> |sip.contoso.com  <br/> |sip.contoso.com  <br/> webcon.contoso.com  <br/> sip.fabrikam.com  <br/> |공개 CA에서 요청 해야 하는 인증서입니다. 다음과 같은 경우 외부에 지 인터페이스에 할당 해야 합니다.  <br/> • 액세스에 지  <br/> • 웹 회의에 지  <br/> • 오디오/비디오 인증  <br/> <br/>좋은 소식은 사용자가 인증서 요청에 자동으로 추가 되며, 따라서 토폴로지 작성기에서이 배포에 대해 정의한 사항을 기반으로 해당 요청을 제출한 후 인증서가 표시 됩니다. 추가 SIP 도메인 또는 지원 해야 하는 다른 항목에 대 한 SAN 항목을 추가 하기만 하면 됩니다. 이 인스턴스에 sip.contoso.com이 복제 되는 이유는 무엇 인가요? 이는 자동으로 일어나 며 제대로 작동 하는 데 필요 합니다.  <br/><br/> **참고:** 이 인증서는 공용 인스턴트 메시징 연결에도 사용할 수 있습니다. 다른 작업을 수행할 필요는 없지만 이전 버전의이 설명서에서는 별도의 테이블로 나열 되었으며 이제는 그렇지 않습니다. <br/> |
|내부에 지  <br/> |sfbedge.contoso.com  <br/> |NA  <br/> |공용 CA 또는 내부 CA에서이 인증서를 가져올 수 있습니다. 서버 EKU (확장 된 키 사용)를 포함 하 고 내부에 지 인터페이스에 할당 해야 합니다.  <br/> |
   
XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜)에 대 한 인증서가 필요한 경우 위의 외부 Edge 테이블 항목과 동일 하지만 다음과 같은 두 개의 추가 SAN 항목이 표시 됩니다.
  
- xmpp <span> </span>contoso<span></span>. c a m
    
- \*contoso<span></span>. c a m
    
현재 XMPP는 비즈니스용 Skype Server for Google 문의 경우에만 지원 되며, 다른 사용자에 게 사용 해야 하는 경우에는 타사 공급 업체와 관련 된 기능을 확인 해야 합니다.
  
## <a name="port-and-firewall-planning"></a>포트 및 방화벽 계획
<a name="PortFirewallPlan"> </a>

비즈니스용 Skype Server Edge 용 포트 및 방화벽에 대 한 계획 수립 권한을 얻으려면 문제 해결 및 스트레스의 일을 줄일 수 있습니다. 따라서, 사용자의 프로토콜 사용량을 나타내는 몇 개의 테이블과 NAT 및 공용 IP 시나리오의 경우 열기, 인바운드 및 아웃 바운드를 사용 해야 하는 포트가 나열 됩니다. 또한 하드웨어 부하 분산 시나리오 (HLB)에 대 한 별도의 테이블 및 그에 대 한 추가 지침을 제공 합니다. 여기서는 [비즈니스용 Skype 서버에 몇 가지 Edge 서버 시나리오가](scenarios.md) 포함 되어 있으므로 특정 배포 문제를 확인할 수 있습니다.
  
### <a name="general-protocol-usage"></a>일반 프로토콜 사용

외부 및 내부 방화벽에 대 한 요약 테이블을 살펴보기 전에 다음 표를 참조 하겠습니다.
  
|**오디오/비디오 전송**|**용도**|
|:-----|:-----|
|UDP  <br/> |오디오 및 비디오에 대 한 기본 전송 계층 프로토콜입니다.  <br/> |
|NET.TCP  <br/> |오디오 및 비디오에 대 한 대체 전송 계층 프로토콜입니다.  <br/> 비즈니스용 Skype Server, Lync Server 2013 및 Lync Server 2010에 대 한 응용 프로그램 공유에 필요한 전송 계층 프로토콜입니다.  <br/> 비즈니스용 Skype Server, Lync Server 2013 및 Lync Server 2010에 파일을 전송 하는 데 필요한 전송 계층 프로토콜입니다.  <br/> |
   
### <a name="external-port-firewall-summary-table"></a>외부 포트 방화벽 요약 표

원본 IP 주소와 대상 IP 주소에는 NAT와 함께 개인 IP 주소를 사용 하는 사용자 및 공용 IP 주소를 사용 하는 사람에 대 한 정보가 포함 됩니다. 이는 비즈니스용 [Skype server의 Edge 서버 시나리오](scenarios.md) 에서 모든 순열을 다룹니다.
  
|**역할 또는 프로토콜**|**TCP 또는 UDP**|**대상 포트 또는 포트 범위**|**원본 IP 주소**|**대상 IP 주소**|**상속자**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> 비즈니스용 Skype 서버 2019에서 지원 되지 않음 |NET.TCP  <br/> |5269  <br/> |이상  <br/> |XMPP 프록시 서비스 (액세스 경계 서비스를 사용 하 여 IP 주소 공유  <br/> |XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처의 트래픽을 허용 합니다.  <br/> |
|Access/HTTP  <br/> |NET.TCP  <br/> |80  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 액세스에 지 서비스 <br/> **공용 IP:** Edge 서버 액세스에 지 서비스 공용 IP 주소 <br/> |이상  <br/> |인증서 해지 및 CRL 검사 및 검색  <br/> |
|Access/DNS  <br/> |NET.TCP  <br/> |53  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 액세스에 지 서비스 <br/> **공용 IP:** Edge 서버 액세스에 지 서비스 공용 IP 주소 <br/> |이상  <br/> |TCP를 통한 DNS 쿼리.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 액세스에 지 서비스 <br/> **공용 IP:** Edge 서버 액세스에 지 서비스 공용 IP 주소 <br/> |이상  <br/> |UDP를 통한 DNS 쿼리.  <br/> |
|TLS (액세스/SIP)  <br/> |NET.TCP  <br/> |443  <br/> |이상  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 액세스에 지 서비스 <br/> **공용 IP:** Edge 서버 액세스에 지 서비스 공용 IP 주소 <br/> |외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽.  <br/> |
|액세스/SIP (MTLS)  <br/> |NET.TCP  <br/> |5061  <br/> |이상  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 액세스에 지 서비스 <br/> **공용 IP:** Edge 서버 액세스에 지 서비스 공용 IP 주소 <br/> |SIP를 사용 하는 페더레이션 및 공용 IM 연결  <br/> |
|액세스/SIP (MTLS)  <br/> |NET.TCP  <br/> |5061  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 액세스에 지 서비스 <br/> **공용 IP:** Edge 서버 액세스에 지 서비스 공용 IP 주소 <br/> |이상  <br/> |SIP를 사용 하는 페더레이션 및 공용 IM 연결  <br/> |
|웹 회의/PSOM (TLS)  <br/> |NET.TCP  <br/> |443  <br/> |이상  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 웹 회의에 지 서비스 <br/> **공용 IP:** Edge 서버 웹 회의에 지 서비스 공용 IP 주소 <br/> |웹 회의 미디어.  <br/> |
|A/V/RTP  <br/> |NET.TCP  <br/> |50000-59999  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 A/V Edge 서비스 <br/> **공용 IP:** Edge 서버 A/V Edge 서비스 공용 IP 주소 <br/> |이상  <br/> |미디어 트래픽을 릴레이 하는 데 사용 됩니다.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 A/V Edge 서비스 <br/> **공용 IP:** Edge 서버 A/V Edge 서비스 공용 IP 주소 <br/> |이상  <br/> |미디어 트래픽을 릴레이 하는 데 사용 됩니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 A/V Edge 서비스 <br/> **공용 IP:** Edge 서버 A/V Edge 서비스 공용 IP 주소 <br/> |이상  <br/> |3478 아웃 바운드:  <br/> • 비즈니스용 Skype 서버에서 통신 중인 Edge 서버의 버전을 확인 하는 데 사용 됩니다.  <br/> • Edge 서버 간의 미디어 트래픽에 사용 됩니다.  <br/> • Lync Server 2010의 페더레이션에 필요 합니다.  <br/> • 조직 내에 여러 개의 Edge 풀이 배포 된 경우 필요 합니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |이상  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 A/V Edge 서비스 <br/> **공용 IP:** Edge 서버 A/V Edge 서비스 공용 IP 주소 <br/> |포트 3478에서 UDP를 통해 후보의 협상을 STUN/설정 합니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |NET.TCP  <br/> |443  <br/> |이상  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 A/V Edge 서비스 <br/> **공용 IP:** Edge 서버 A/V Edge 서비스 공용 IP 주소 <br/> |포트 443에서 TCP를 통한 후보의 협상을 STUN/설정 합니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |NET.TCP  <br/> |443  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 A/V Edge 서비스 <br/> **공용 IP:** Edge 서버 A/V Edge 서비스 공용 IP 주소 <br/> |이상  <br/> |포트 443에서 TCP를 통한 후보의 협상을 STUN/설정 합니다.  <br/> |
   
### <a name="internal-port-firewall-summary-table"></a>내부 포트 방화벽 요약 테이블

|**프로토콜별**|**TCP 또는 UDP**|**포트**|**원본 IP 주소**|**대상 IP 주소**|**상속자**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |NET.TCP  <br/> |23456  <br/> |XMPP 게이트웨이 서비스를 실행 하는 경우는 다음과 같습니다.  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀  <br/> |Edge 서버 내부 인터페이스  <br/> |프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽  <br/> **참고:** XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 자세한 내용은 [XMPP 페더레이션 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조 하세요.|
|SIP/MTLS  <br/> |NET.TCP  <br/> |5061  <br/> |이상  <br/> • 이사  <br/> • 이사 풀  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀  <br/> |Edge 서버 내부 인터페이스  <br/> |디렉터, 디렉터 풀, 프런트 엔드 서버 또는 프런트 엔드 풀에서 Edge Server 내부 인터페이스로 나가는 아웃 바운드 SIP 트래픽.  <br/> |
|SIP/MTLS  <br/> |NET.TCP  <br/> |5061  <br/> |Edge 서버 내부 인터페이스  <br/> |이상  <br/> • 이사  <br/> • 이사 풀  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀  <br/> |사용자의 Edge 서버 내부 인터페이스에서 디렉터, 디렉터 풀, 프런트 엔드 서버 또는 프런트 엔드 풀로 인바운드 SIP 트래픽.  <br/> |
|PSOM/MTLS  <br/> |NET.TCP  <br/> |8057  <br/> |이상  <br/> • 프런트 엔드 서버  <br/> • 각 프런트 엔드 서버  <br/>  프런트 엔드 풀의 <br/> |Edge 서버 내부 인터페이스  <br/> |프런트 엔드 서버 또는 각 프런트 엔드 서버 (프런트 엔드 풀을 사용 하는 경우)에서 Edge Server 내부 인터페이스에 이르기까지 웹 회의 소통량.  <br/> |
|SIP/MTLS  <br/> |NET.TCP  <br/> |5062  <br/> |이상  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀  <br/> •이 Edge 서버를 사용 하는 모든 Survivable 지사 기기  <br/> •이 Edge 서버를 사용 하는 모든 Survivable 분기 서버  <br/> |Edge 서버 내부 인터페이스  <br/> |Edge 서버를 사용 하 여 프런트 엔드 서버 또는 프런트 엔드 풀 또는 Survivable Branch 기기 또는 Survivable Branch 서버에서 A/V 사용자를 인증 합니다.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |이상  <br/> |Edge 서버 내부 인터페이스  <br/> |내부 및 외부 사용자와 Survivable Branch 기기 또는 Survivable Branch 서버 간의 A/V 미디어 전송에 대 한 기본 설정 경로입니다.  <br/> |
|STUN/MSTURN  <br/> |NET.TCP  <br/> |443  <br/> |이상  <br/> |Edge 서버 내부 인터페이스  <br/> |UDP 통신이 작동 하지 않는 경우 내부 및 외부 사용자와 Survivable Branch 기기 또는 Survivable Branch 서버 간의 A/V 미디어 전송에 대 한 대체 경로입니다. 그러면 TCP는 파일 전송 및 데스크톱 공유에 사용 됩니다.  <br/> |
|HTTPS  <br/> |NET.TCP  <br/> |4443  <br/> |이상  <br/> • 중앙 관리 저장소를 보유 하는 프런트 엔드 서버  <br/> • 중앙 관리 저장소를 보유 하는 프런트 엔드 풀  <br/> |Edge 서버 내부 인터페이스  <br/> |중앙 관리 저장소의 변경 내용을 Edge 서버로 복제 합니다.  <br/> |
|MTLS  <br/> |NET.TCP  <br/> |50001  <br/> |이상  <br/> |Edge 서버 내부 인터페이스  <br/> |비즈니스용 Skype Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러.  <br/> |
|MTLS  <br/> |NET.TCP  <br/> |50002  <br/> |이상  <br/> |Edge 서버 내부 인터페이스  <br/> |비즈니스용 Skype Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러.  <br/> |
|MTLS  <br/> |NET.TCP  <br/> |50003  <br/> |이상  <br/> |Edge 서버 내부 인터페이스  <br/> |비즈니스용 Skype Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러.  <br/> |
   
### <a name="hardware-load-balancers-for-edge-port-tables"></a>Edge 포트 테이블의 하드웨어 부하 분산 장치

HLBs (하드웨어 부하 분산 장치) 및 Edge 포트에는 추가 하드웨어를 사용 하는 것이 조금 더 복잡 하므로 자체의 섹션을 제공 합니다. 이 특정 시나리오에 대 한 지침은 아래 표를 참조 하세요.
  
#### <a name="external-port-firewall-summary-table"></a>외부 포트 방화벽 요약 표

원본 IP 주소와 대상 IP 주소에는 NAT와 함께 개인 IP 주소를 사용 하는 사용자 및 공용 IP 주소를 사용 하는 사람에 대 한 정보가 포함 됩니다. 이는 비즈니스용 [Skype server의 Edge 서버 시나리오](scenarios.md) 에서 모든 순열을 다룹니다.
  
|**역할 또는 프로토콜**|**TCP 또는 UDP**|**대상 포트 또는 포트 범위**|**원본 IP 주소**|**대상 IP 주소**|**상속자**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Access/HTTP  <br/> |NET.TCP  <br/> |80  <br/> |Edge 서버 액세스에 지 서비스 공용 IP 주소  <br/> |이상  <br/> |인증서 해지 및 CRL 검사 및 검색  <br/> |
|Access/DNS  <br/> |NET.TCP  <br/> |53  <br/> |Edge 서버 액세스에 지 서비스 공용 IP 주소  <br/> |이상  <br/> |TCP를 통한 DNS 쿼리.  <br/> |
|Access/DNS  <br/> |UDP  <br/> |53  <br/> |Edge 서버 액세스에 지 서비스 공용 IP 주소  <br/> |이상  <br/> |UDP를 통한 DNS 쿼리.  <br/> |
|A/V/RTP  <br/> |NET.TCP  <br/> |50000-59999  <br/> |Edge 서버 A/V Edge 서비스 IP 주소  <br/> |이상  <br/> |미디어 트래픽을 릴레이 하는 데 사용 됩니다.  <br/> |
|A/V/RTP  <br/> |UDP  <br/> |50000-59999  <br/> |Edge 서버 A/V Edge 서비스 공용 IP 주소  <br/> |이상  <br/> |미디어 트래픽을 릴레이 하는 데 사용 됩니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |Edge 서버 A/V Edge 서비스 공용 IP 주소  <br/> |이상  <br/> |3478 아웃 바운드:  <br/> • 비즈니스용 Skype 서버에서 통신 중인 Edge 서버의 버전을 확인 하는 데 사용 됩니다.  <br/> • Edge 서버 간의 미디어 트래픽에 사용 됩니다.  <br/> • 페더레이션에 필요 합니다.  <br/> • 조직 내에 여러 개의 Edge 풀이 배포 된 경우 필요 합니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |이상  <br/> |Edge 서버 A/V Edge 서비스 공용 IP 주소  <br/> |포트 3478에서 UDP를 통해 후보의 협상을 STUN/설정 합니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |NET.TCP  <br/> |443  <br/> |이상  <br/> |Edge 서버 A/V Edge 서비스 공용 IP 주소  <br/> |포트 443에서 TCP를 통한 후보의 협상을 STUN/설정 합니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |NET.TCP  <br/> |443  <br/> |Edge 서버 A/V Edge 서비스 공용 IP 주소  <br/> |이상  <br/> |포트 443에서 TCP를 통한 후보의 협상을 STUN/설정 합니다.  <br/> |
   
#### <a name="internal-port-firewall-summary-table"></a>내부 포트 방화벽 요약 테이블

|**프로토콜별**|**TCP 또는 UDP**|**포트**|**원본 IP 주소**|**대상 IP 주소**|**상속자**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP/MTLS  <br/> |NET.TCP  <br/> |23456  <br/> |XMPP 게이트웨이 서비스를 실행 하는 경우는 다음과 같습니다.  <br/> • 프런트 엔드 서버  <br/> • XMPP 게이트웨이 서비스를 실행 하는 프런트 엔드 풀 VIP 주소  <br/> |Edge 서버 내부 인터페이스  <br/> |프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽  <br/><br/> **참고:** XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 자세한 내용은 [XMPP 페더레이션 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조 하세요. |
|HTTPS  <br/> |NET.TCP  <br/> |4443  <br/> |이상  <br/> • 중앙 관리 저장소를 보유 하는 프런트 엔드 서버  <br/> • 중앙 관리 저장소를 보유 하는 프런트 엔드 풀  <br/> |Edge 서버 내부 인터페이스  <br/> |중앙 관리 저장소의 변경 내용을 Edge 서버로 복제 합니다.  <br/> |
|PSOM/MTLS  <br/> |NET.TCP  <br/> |8057  <br/> |이상  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀의 각 프런트 엔드 서버  <br/> |Edge 서버 내부 인터페이스  <br/> |프런트 엔드 서버 또는 각 프런트 엔드 서버 (프런트 엔드 풀을 사용 하는 경우)에서 Edge Server 내부 인터페이스에 이르기까지 웹 회의 소통량.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |이상  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀의 각 프런트 엔드 서버  <br/> |Edge 서버 내부 인터페이스  <br/> |내부 및 외부 사용자와 Survivable Branch 기기 또는 Survivable Branch 서버 간의 A/V 미디어 전송에 대 한 기본 설정 경로입니다.  <br/> |
|STUN/MSTURN  <br/> |NET.TCP  <br/> |443  <br/> |이상  <br/> • 프런트 엔드 서버  <br/> • 풀의 각 프런트 엔드 서버  <br/> |Edge 서버 내부 인터페이스  <br/> |UDP 통신이 작동 하지 않는 경우 내부 및 외부 사용자와 Survivable Branch 기기 또는 Survivable Branch 서버 간의 A/V 미디어 전송에 대 한 대체 경로입니다. 그러면 TCP는 파일 전송 및 데스크톱 공유에 사용 됩니다.  <br/> |
|MTLS  <br/> |NET.TCP  <br/> |50001  <br/> |이상  <br/> |Edge 서버 내부 인터페이스  <br/> |비즈니스용 Skype Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러.  <br/> |
|MTLS  <br/> |NET.TCP  <br/> |50002  <br/> |이상  <br/> |Edge 서버 내부 인터페이스  <br/> |비즈니스용 Skype Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러.  <br/> |
|MTLS  <br/> |NET.TCP  <br/> |50003  <br/> |이상  <br/> |Edge 서버 내부 인터페이스  <br/> |비즈니스용 Skype Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러.  <br/> |
   
#### <a name="external-interface-virtual-ips"></a>외부 인터페이스 가상 Ip

|**역할 또는 프로토콜**|**TCP 또는 UDP**|**대상 포트 또는 포트 범위**|**원본 IP 주소**|**대상 IP 주소**|**상속자**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|XMPP  <br/> Businesss Server 2019 용 Skype에서 지원 되지 않음 |NET.TCP  <br/> |5269  <br/> |이상  <br/> |XMPP 프록시 서비스 (액세스 Edge 서비스를 사용 하 여 IP 주소 공유)  <br/> |XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처의 트래픽을 허용 합니다.  <br/> |
|XMPP  <br/>Businesss Server 2019 용 Skype에서 지원 되지 않음 |NET.TCP  <br/> |5269  <br/> |XMPP 프록시 서비스 (액세스 Edge 서비스를 사용 하 여 IP 주소 공유)  <br/> |이상  <br/> |XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처의 트래픽을 보냅니다.  <br/> |
|TLS (액세스/SIP)  <br/> |NET.TCP  <br/> |443  <br/> |이상  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 액세스에 지 서비스 <br/> **공용 IP:** Edge 서버 액세스에 지 서비스 공용 IP 주소 <br/> |외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽.  <br/> |
|액세스/SIP (MTLS)  <br/> |NET.TCP  <br/> |5061  <br/> |이상  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 액세스에 지 서비스 <br/> **공용 IP:** Edge 서버 액세스에 지 서비스 공용 IP 주소 <br/> |SIP를 사용 하는 페더레이션 및 공용 IM 연결  <br/> |
|액세스/SIP (MTLS)  <br/> |NET.TCP  <br/> |5061  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 액세스에 지 서비스 <br/> **공용 IP:** Edge 서버 액세스에 지 서비스 공용 IP 주소 <br/> |이상  <br/> |SIP를 사용 하는 페더레이션 및 공용 IM 연결  <br/> |
|웹 회의/PSOM (TLS)  <br/> |NET.TCP  <br/> |443  <br/> |이상  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 웹 회의에 지 서비스 <br/> **공용 IP:** Edge 서버 웹 회의에 지 서비스 공용 IP 주소 <br/> |웹 회의 미디어.  <br/> |
|A/V/STUN. MSTURN  <br/> |UDP  <br/> |3478  <br/> |이상  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 A/V Edge 서비스 <br/> **공용 IP:** Edge 서버 A/V Edge 서비스 공용 IP 주소 <br/> |포트 3478에서 UDP를 통해 후보의 협상을 STUN/설정 합니다.  <br/> |
|A/V/STUN. MSTURN  <br/> |NET.TCP  <br/> |443  <br/> |이상  <br/> |**NAT를 사용 하는 개인 IP:** Edge 서버 A/V Edge 서비스 <br/> **공용 IP:** Edge 서버 A/V Edge 서비스 공용 IP 주소 <br/> |포트 443에서 TCP를 통한 후보의 협상을 STUN/설정 합니다.  <br/> |
   
#### <a name="internal-interface-virtual-ips"></a>내부 인터페이스 가상 Ip

여기에 나와 있는 지침이 약간 다를 수 있습니다. 실제로 HLB 상황에서는 다음과 같은 상황에서 내부 VIP를 통해서만 라우팅을 사용 하는 것이 좋습니다.
  
- Exchange 2007 또는 Exchange 2010 UM (통합 메시징)을 사용 하는 경우
    
- Edge를 사용 하는 레거시 클라이언트가 있는 경우
    
다음 표에는 이러한 시나리오에 대 한 지침이 제공 되지만, 그렇지 않은 경우에는 개인 Edge 서버로 트래픽을 라우팅하기 위해 CMS (중앙 관리 저장소)를 사용할 수 있어야 합니다 (이 경우에는 CMS가 Edge Server에서 최신 상태로 유지 되어야 함). 물론 정보.
  
|**프로토콜별**|**TCP 또는 UDP**|**포트**|**원본 IP 주소**|**대상 IP 주소**|**상속자**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|액세스/SIP (MTLS)  <br/> |NET.TCP  <br/> |5061  <br/> |이상  <br/> • 이사  <br/> • 디렉터 풀 VIP 주소  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀 VIP 주소  <br/> |Edge 서버 내부 인터페이스  <br/> |디렉터, 디렉터 풀 VIP 주소, 프런트 엔드 서버 또는 프론트 엔드 풀 VIP 주소에서 Edge Server 내부 인터페이스로 나가는 아웃 바운드 SIP 트래픽.  <br/> |
|액세스/SIP (MTLS)  <br/> |NET.TCP  <br/> |5061  <br/> |Edge 서버 내부 VIP 인터페이스  <br/> |이상  <br/> • 이사  <br/> • 디렉터 풀 VIP 주소  <br/> • 프런트 엔드 서버  <br/> • 프런트 엔드 풀 VIP 주소  <br/> |사용자의 Edge 서버 내부 인터페이스에서 디렉터, 디렉터 풀 VIP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 VIP 주소로 인바운드 SIP 트래픽.  <br/> |
|SIP/MTLS  <br/> |NET.TCP  <br/> |5062  <br/> |이상  <br/> • 프런트 엔드 서버 IP 주소  <br/> • 프런트 엔드 풀 IP 주소  <br/> •이 Edge 서버를 사용 하는 모든 Survivable 지사 기기  <br/> •이 Edge 서버를 사용 하는 모든 Survivable 분기 서버  <br/> |Edge 서버 내부 인터페이스  <br/> |Edge 서버를 사용 하 여 프런트 엔드 서버 또는 프런트 엔드 풀 또는 Survivable Branch 기기 또는 Survivable Branch 서버에서 A/V 사용자를 인증 합니다.  <br/> |
|STUN/MSTURN  <br/> |UDP  <br/> |3478  <br/> |이상  <br/> |Edge 서버 내부 인터페이스  <br/> |내부 및 외부 사용자 간의 A/V 미디어 전송에 대 한 기본 경로입니다.  <br/> |
|STUN/MSTURN  <br/> |NET.TCP  <br/> |443  <br/> |이상  <br/> |Edge 서버 내부 VIP 인터페이스  <br/> |UDP 통신이 작동 하지 않는 경우 내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로입니다. 그러면 TCP는 파일 전송 및 데스크톱 공유에 사용 됩니다.  <br/> |
