---
title: 비즈니스용 Skype 서버에 대 한 고급 Edge Server DNS 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: '요약: 비즈니스용 Skype 서버 배포 옵션에 대 한 시나리오를 검토 합니다. 이 항목은 단일 서버를 사용 하거나 DNS 또는 HLB 서버 풀을 사용할 수 있도록 하는 데 도움이 될 것입니다.'
ms.openlocfilehash: b3893c11e1ce0cfdf9ab0b0452ef0a30a6442ee7
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887765"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 고급 Edge Server DNS 계획
 
**요약:** 비즈니스용 Skype 서버 배포 옵션에 대 한 시나리오를 검토 합니다. 이 항목은 단일 서버를 사용 하거나 DNS 또는 HLB 서버 풀을 사용할 수 있도록 하는 데 도움이 될 것입니다.
  
비즈니스용 Skype Server에 대 한 DNS (Domain Name System) 계획과 관련 된 경우에는 다양 한 요인에 따라 결정을 내릴 수 있습니다. 조직의 도메인 구조가 이미 존재 하는 경우에는 어떻게 진행할 지 검토 하는 것이 중요 합니다. 시작 하는 항목은 다음과 같습니다.
  
- [서비스를 찾는 비즈니스용 Skype 클라이언트의 연습](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [분할-두뇌 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [분할 하는 DNS 없이 자동 구성](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS 재해 복구](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS 부하 분산](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>서비스를 찾는 비즈니스용 Skype 클라이언트의 연습
<a name="WalkthroughOfSkype"> </a>

비즈니스용 skype 클라이언트는 비즈니스용 Skype 서버에서 서비스를 찾고 액세스 하는 방법에 대 한 이전 버전의 Lync 클라이언트와 비슷합니다. 이 섹션에서는 서버 위치 프로세스에 대해 자세히 설명 합니다.
  
1. lyncdiscoverinternal. \<도메인\>
    
     *내부 웹 서비스의 자동 검색 서비스에 대 한 호스트 레코드입니다.* 
    
2. lyncdiscover. \<도메인\>
    
     *외부 웹 서비스의 자동 검색 서비스에 대 한 호스트 레코드입니다.* 
    
3. _tcp _sipinternaltls. \<도메인\>
    
     *내부 TLS 연결에 대 한 SRV 레코드입니다.* 
    
4. _tls _sip. \<도메인\>
    
     *외부 TLS 연결에 대 한 SRV 레코드입니다.* 
    
5. sipinternal. \<도메인\>
    
     *이는 내부 네트워크 에서만 확인할 수 있는 프런트 엔드 풀 또는 디렉터에 대 한 호스트 레코드입니다.* 
    
6. sip. \<도메인\>
    
     *이는 내부 네트워크 에서만 확인할 수 있는 프런트 엔드 풀 또는 디렉터에 대 한 호스트 레코드입니다.* 
    
7. sipexternal. \<도메인\>
    
     *클라이언트가 외부에 있는 경우 액세스에 지 서비스에 대 한 호스트 레코드입니다.* 
    
자동 검색 서비스는 서비스 위치에 대 한 기본 설정 방식으로 항상 선호 되며 나머지는 fallback 메서드입니다.
  
> [!NOTE]
> SRV 레코드를 만드는 경우 DNS SRV 레코드를 만들 때 사용 하는 도메인에서 DNS A (IPv6 주소 지정을 사용 하는 경우 AAAA)를 가리켜야 한다는 것을 기억해 야 합니다. 예를 들어 contoso.com에 해당 하는 레코드가 있는 경우에는 해당 레코드를 가리키는 A (및 AAAA) 레코드가 fabrikam.com에 있을 수 없습니다. 
  
이 작업을 inclined 경우 서비스를 수동으로 검색 하도록 모바일 장치를 설정할 수 있습니다. 원하는 작업을 수행 하는 경우 각 사용자는 다음과 같이 프로토콜 및 경로를 포함 하 여 전체 내부 및 외부 자동 검색 서비스 Uri를 사용 하 여 모바일 장치 설정을 구성 해야 합니다.
  
- 외부 액세스: https://\<extpoolfqdn/Autodiscover/autodiscoverservice.svc/Root\>
    
- 내부 액세스: https://\<intpoolfqdn/AutoDiscover/AutoDiscover.svc/Root\>
    
수동 검색 대신 자동 검색을 사용 하는 것이 좋습니다. 그러나 일부 문제 해결 이나 테스트를 수행 하는 경우에는 수동 설정이 매우 유용할 수 있습니다.
  
## <a name="split-brain-dns"></a>분할-두뇌 DNS
<a name="SplitBrainDNS"> </a>

이는 같은 네임 스페이스를 사용 하는 두 개의 DNS 영역이 있는 DNS 구성입니다. 첫 번째 DNS 영역은 내부 요청을 처리 하 고 두 번째 DNS 영역은 외부 요청을 처리 합니다.
  
회사가이 작업을 수행 하는 이유는 무엇 인가요? 이러한 사용자는 내부 및 외부에서 동일한 네임 스페이스를 사용 해야 하는 경우가 있을 수 있지만, 이렇게 하면 여러 DNS SRV와 하나 이상의 영역에 대해 고유 하 고 중복 되는 레코드가 있는 경우 이러한 레코드와 연결 된 IP 주소는 고유 합니다.
  
여기에 몇 가지 과제가 표시 됩니다. 가장 중요 한 것은 분할 두뇌 DNS가 이동성에 대해 **지원 되지** 않는 것입니다. 이는 LyncDiscover 및 LyncDiscoverInternal DNS 레코드 (LyncDiscover가 외부 DNS 서버에 정의 되어야 하는 반면, 내부 DNS 서버에는 LyncDiscoverInternal가 정의 되어 있지 않기 때문입니다).
  
여기에는 내부 및 외부 영역에 대 한 DNS 레코드가 나열 되지만 Edge 서버 환경 요구 사항 섹션에서 자세한 예제를 확인할 수 있습니다.
  
### <a name="internal-dns"></a>내부 DNS

- 권한이 있는 (예:) contoso.com DNS 영역을 포함 합니다.
    
- 이 내부 contoso.com에는 다음이 포함 됩니다.
    
  - 프런트 엔드 풀, 디렉터 풀 또는 디렉터 풀 이름, 그리고 조직의 네트워크에서 비즈니스용 Skype 서버를 실행 하는 모든 내부 서버에 대 한 DNS A 및 AAAA (IPv6 주소 사용) 레코드가 표시 됩니다.
    
  - 경계 네트워크의 각 비즈니스용 Skype Server Edge 서버에 대 한 Edge 내부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드가 표시 됩니다.
    
  - 경계 네트워크에서 각 역방향 프록시 서버의 내부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드 (역방향 프록시 관리의 경우 **선택 사항** ).
    
  - DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 내부 비즈니스용 Skype 서버 클라이언트 자동 구성에 대 한 SRV 레코드 ( **선택 사항** ).
    
  - DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 또는 비즈니스용 Skype 서버 웹 서비스의 자동 검색을 위한 CNAME 레코드 ( **선택 사항** )
    
- 주변 네트워크의 모든 비즈니스용 Skype Server 내부 Edge 인터페이스는 contoso.com에 대 한 쿼리 확인을 위해이 내부 DNS 영역을 사용 합니다.
    
- 비즈니스용 Skype Server를 실행 하는 모든 서버와 회사 네트워크에서 비즈니스용 Skype Server를 실행 하는 클라이언트는 contoso.com에 대 한 쿼리 확인을 위한 내부 DNS 서버를 가리키거나 각 Edge 서버의 호스트 파일 및 목록 A 및 AAAA (사용 중인 경우)를 사용 합니다. IPv6 주소 지정) 다음 홉 서버 (특히 디렉터 또는 디렉터 풀 VIP, 프론트 End pool VIP 또는 Standard Edition 서버)에 대 한 레코드입니다.
    
### <a name="external-dns"></a>외부 DNS

- 권한이 있는 (예:) contoso.com DNS 영역을 포함 합니다.
    
- 이 외부 contoso.com에는 다음이 포함 됩니다.
    
  - 비즈니스용 Skype 서버 웹 서비스의 자동 검색을 위해 DNS A와 AAAA (IPv6 주소를 사용 하는 경우) 또는 CNAME 레코드 이는 이동성에 사용 하기 위한 것입니다.
    
  - DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 경계 네트워크의 각 비즈니스용 Skype Server Edge 서버 또는 HLB (하드웨어 부하 분산) VIP의 Edge 외부 인터페이스에 대 한 SRV 레코드.
    
  - DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 역방향 프록시 서버의 외부 인터페이스에 대 한 SRV 레코드 (경계 네트워크의 경우 역방향 프록시 서버 풀의 VIP)
    
  - DNS A와 AAAA (IPv6 주소를 사용 하는 경우) 및 비즈니스용 Skype 서버 클라이언트 자동 구성에 대 한 SRV 레코드 ( **선택 사항** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>분할 하는 DNS 없이 자동 구성
<a name="NoSplitBrainDNS"> </a>

분할 하는 DNS를 사용 하지 않는 경우에는 여기에서 제공 하는 해결 방법 중 하나를 사용 하지 않는 한 비즈니스용 Skype를 실행 하는 클라이언트의 내부 자동 구성이 작동 하지 않습니다. 왜 안 돼요? 비즈니스용 Skype Server에는 자동 구성에 대해 지정 된 프런트 엔드 풀의 도메인을 일치 시키기 위해 사용자의 SIP URI가 필요 합니다. 이는 이전 버전의 Lync Server에서 변경 되지 않았습니다.
  
따라서 두 개의 SIP 도메인을 사용 하는 경우 다음과 같은 DNS SRV 레코드가 필요 합니다.
  
- _sipinternaltls _tcp. c a m. SRV 0 0 5061 pool01.contoso.com의 86400
    
     *사용자가 bob@contoso.com로 로그인 하는 경우이 레코드는 사용자의 SIP 도메인이 프런트 엔드 풀 (contoso.com)의 도메인과 일치 하므로 자동 구성에 사용할 수 있습니다.* 
    
- _sipinternaltls _tcp. c a m. SRV 0 0 5061 pool01.fabrikam.com의 86400
    
     *사용자가 alice@fabrikam.com로 로그인 하는 경우이 레코드는 SIP 도메인이 해당 도메인의 프런트 엔드 풀과 일치 하기 때문에 두 번째 도메인의 자동 구성에 대해 작동 합니다.* 
    
이 예제를 더 자세히 살펴보려면 다음을 수행 하지 않습니다.
  
- litwareinc. _tcp. _sipinternaltls. SRV 0 0 5061 pool01.fabrikam.com의 86400
    
     *Tim@litwareinc.com로 로그인 하는 사용자는 해당 SIP 도메인 (litwareinc.com)이 풀 (fabrikam.com)의 도메인과 일치 하지 않기 때문에 자동 구성에는 적용 되지 않습니다.* 
    
이제 모든 것을 알고 있으므로, 사용자는 비즈니스용 Skype 클라이언트에 대 한 자동 요구 사항이 있는 경우, 분할 하는 DNS가 필요 하지 않은 경우 다음과 같은 옵션이 있습니다.
  
- **그룹 정책 개체**
    
    Gpo (그룹 정책 개체)를 사용 하 여 올바른 서버 값을 채울 수 있습니다.
    
    > [!NOTE]
    > 이 옵션은 자동 구성을 사용 하지 않지만 수동 구성은 자동화 합니다. 이 방법을 사용 하는 경우 자동 구성에 연결 된 SRV 레코드가 필요 하지 않습니다. 
  
- **내부 영역이 일치 합니다.**
    
    내부 DNS에 외부 DNS 영역과 일치 하는 영역 (예: contoso.com)을 만든 다음 자동으로 사용 되는 비즈니스용 Skype 서버 풀에 해당 하는 DNS A (및 IPv6 주소를 사용 하는 경우 AAAA)를 만들어야 합니다. 구성.
    
    예를 들어 pool01.contoso.net에 속한 사용자가 비즈니스용 Skype에 bob@contoso.com에 로그인 하는 경우 contoso.com 이라는 내부 DNS 영역을 만들고, 그 안에는 DNS A (및 IPv6 주소 지정을 사용 하는 경우)를 만들어야 pool01.contoso.com에 대 한 레코드를 기록해 야 합니다.
    
- **핀 점 내부 영역**
    
    내부 DNS에 전체 영역을 만드는 옵션이 없는 경우 자동 구성에 필요한 SRV 레코드에 해당 하는 pin 포인트 (전용) 영역을 만들고 dnscmd를 사용 하 여 해당 영역을 채울 수 있습니다. DNS 사용자 인터페이스가 pin 포인트 영역의 생성을 지원 하지 않으므로 Dnscmd이 필요 합니다.
    
    예를 들어 SIP 도메인이 contoso.com 경우 두 프런트 엔드 서버를 포함 하는 pool01 라는 프런트 엔드 풀을 사용 하는 경우에는 내부 DNS에 다음과 같은 핀 점 영역과 레코드가 필요 합니다.
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    환경에 두 번째 SIP 도메인이 있을 수 있습니다. 이 경우 내부 DNS에 다음과 같은 핀 위치 영역과 레코드가 필요 합니다.
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> 프런트 엔드 풀 FQDN은 두 번 나타나지만 서로 다른 IP 주소를 사용 하 여 표시 됩니다. 이것은 DNS 부하 분산이 사용 되기 때문입니다. HLB를 사용 하는 경우 단일 프론트 엔드 풀 항목만 있습니다. 
  
> [!NOTE]
> 또한 contoso.com 및 fabrikam.com 예제 간에 프런트 엔드 풀 FQDN 값이 변경 되지만 IP 주소는 동일 하 게 유지 됩니다. 이는 SIP 도메인에서 로그인 하는 사용자가 자동 구성에 동일한 프런트 엔드 풀을 사용 하는 것 이기 때문입니다. 
  
## <a name="dns-disaster-recovery"></a>DNS 재해 복구
<a name="DNSDR"> </a>

비즈니스용 Skype 서버 웹 트래픽을 재해 복구 (DR) 및 장애 조치 사이트로 리디렉션하도록 DNS를 구성 하려면 GeoDNS를 지 원하는 DNS 공급자를 사용 해야 합니다. 장애 복구를 지원 하도록 DNS 레코드를 설정 하 여 전체 프런트 엔드 풀 하나가 다운 되는 경우에도 웹 서비스를 사용 하는 기능이 계속 작동 하도록 할 수 있습니다. 이 DR 기능은 자동 검색, 모임 및 전화 접속 간단한 Url을 지원 합니다.
  
GeoDNS 공급자에서 웹 서비스의 내부 및 외부 해상도에 대 한 추가 DNS 호스트 A (IPv6을 사용 하는 경우 AAAA) 레코드를 정의 하 고 구성 합니다. 다음은 쌍으로 분산 된 풀이 있는 것으로 간주 하 고 **, 공급자가** 지 원하는 geodns에 라운드 **로빈 Dns가 있거나 Pool1** 를 기본으로 사용 하도록 구성 되어 있으며 통신 손실 또는 전원 장애가 발생 하는 경우에는 Pool2에 대 한 장애 조치를 수행할 수 있다는 것을 설명 합니다.
  
이 테이블의 모든 DNS 레코드는 예제입니다.
  
|**GeoDNS 레코드**|**풀 레코드**|**CNAME 레코드**|**DNS 설정 (한 옵션 선택)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com에 Meet.contoso.com 별칭  <br/> Pool2InternalWebFQDN.contoso.com에 Meet.contoso.com 별칭  <br/> |풀 간의 라운드 로빈  <br/> **또는** <br/> 오류가 있는 경우 기본, 보조에 연결을 사용 합니다.  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com에 Meet.contoso.com 별칭  <br/> Pool2ExternalWebFQDN.contoso.com에 Meet.contoso.com 별칭  <br/> |풀 간의 라운드 로빈  <br/> **또는** <br/> 오류가 있는 경우 기본, 보조에 연결을 사용 합니다.  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com에 Dialin.contoso.com 별칭  <br/> Pool2InternalWebFQDN.contoso.com에 Dialin.contoso.com 별칭  <br/> |풀 간의 라운드 로빈  <br/> **또는** <br/> 오류가 있는 경우 기본, 보조에 연결을 사용 합니다.  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com에 Dialin.contoso.com 별칭  <br/> Pool2ExternalWebFQDN.contoso.com에 Dialin.contoso.com 별칭  <br/> |풀 간의 라운드 로빈  <br/> **또는** <br/> 오류가 있는 경우 기본, 보조에 연결을 사용 합니다.  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com에 Lyncdiscoverinternal.contoso.com 별칭  <br/> Pool2InternalWebFQDN.contoso.com에 Lyncdiscoverinternal.contoso.com 별칭  <br/> |풀 간의 라운드 로빈  <br/> **또는** <br/> 오류가 있는 경우 기본, 보조에 연결을 사용 합니다.  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com에 Lyncdiscover.contoso.com 별칭  <br/> Pool2ExternalWebFQDN.contoso.com에 Lyncdiscover.contoso.com 별칭  <br/> |풀 간의 라운드 로빈  <br/> **또는** <br/> 오류가 있는 경우 기본, 보조에 연결을 사용 합니다.  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com에 Scheduler.contoso.com 별칭  <br/> Pool2InternalWebFQDN.contoso.com에 Scheduler.contoso.com 별칭  <br/> |풀 간의 라운드 로빈  <br/> **또는** <br/> 오류가 있는 경우 기본, 보조에 연결을 사용 합니다.  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com에 Scheduler.contoso.com 별칭  <br/> Pool2ExternalWebFQDN.contoso.com에 Scheduler.contoso.com 별칭  <br/> |풀 간의 라운드 로빈  <br/> **또는** <br/> 오류가 있는 경우 기본, 보조에 연결을 사용 합니다.  <br/> |
   
## <a name="dns-load-balancing"></a>DNS 부하 분산
<a name="DNSLB"> </a>

DNS 부하 분산은 일반적으로 응용 프로그램 수준에서 구현 됩니다. 응용 프로그램 (예: 비즈니스용 Skype를 실행 하는 클라이언트)은 DNS A 및 AAAA (IPv6 주소 지정을 사용 하는 경우)에서 반환 된 IP 주소 중 하나에 연결 하 여 풀의 서버에 연결 하려고 시도 합니다. 풀 FQDN에 대 한 레코드 쿼리.
  
예를 들어 pool01.contoso.com 이라는 풀에 프런트 엔드 서버가 세 개 있는 경우 다음이 발생 합니다.
  
- Pool01.contoso.com 용 비즈니스용 Skype 쿼리 DNS를 실행 하는 클라이언트입니다. 쿼리는 IP 주소를 세 개 반환 하 고 다음과 같이 (순서 대로) 캐시 합니다.
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- 클라이언트가 IP 주소 중 하나에 TCP 연결을 설정 하려고 합니다. 이 문제가 발생 하면 해당 목록에서 캐시 된 다음 IP 주소를 시도 합니다.
    
- TCP 연결이 성공 하면 클라이언트는 pool01.contoso.com의 기본 등록 기관에 연결 하도록 TLS를 협상 합니다.
    
- 연결에 성공 하지 않고 모든 캐시 된 항목을 시도 하면 사용자는 비즈니스용 Skype 서버를 실행 하는 서버를 현재 사용할 수 없다는 알림을 받습니다.
    
> [!NOTE]
> DNS 기반 부하 분산은 dns를 사용 하 여 풀의 서버에 대 한 IP 주소를 다른 순서로 제공 하는 dns 라운드 로빈 (DNS RR)과 다릅니다. 일반적으로 DNS RR은 부하 분산을 가능 하 게 하지만 장애 조치를 사용 하도록 설정 하는 것을 허용 하지 않습니다. 예를 들어 DNS A (또는 IPv6 시나리오에서 AAAA)가 반환 하는 IP 주소에 대 한 연결에 실패 하면 해당 연결이 실패 하 게 됩니다. Dns RR을 DNS 기반 부하 분산 보다 덜 안정적으로 만드는 것입니다. 이 작업을 수행 해야 하는 경우 dns 기반 부하 분산과 함께 DNS RR을 계속 사용할 수 있습니다. 
  
DNS 부하 분산을 사용 하 여 다음을 수행 합니다.
  
- 서버 간 SIP에 대 한 부하를 Edge 서버로 조정 합니다.
    
- 회의 자동 전화 교환, 응답 그룹, 통화 공원 등 통합 커뮤니케이션 응용 프로그램 서비스 (c) 응용 프로그램의 부하 분산.
    
- 응용 프로그램으로 새 연결 (드레이닝이 라고도 함)을 방지 합니다.
    
- 클라이언트와 Edge 서버 간의 모든 클라이언트 간 트래픽에 대 한 부하 균형을 조정 합니다.
    
다음에 대해 DNS 부하 분산을 사용할 수 없습니다.
  
- 프런트 엔드 서버 또는 디렉터에 대 한 클라이언트 대 서버 웹 트래픽
    
쿼리를 통해 mutiple DNS 레코드를 반환 하는 경우 DNS SRV 레코드를 선택 하는 방법에 대 한 자세한 내용을 더 자세히 설명 하기 위해, Access Edge 서비스는 항상 가장 낮은 숫자 우선 순위의 레코드를 선택 하 고, 연결 분리기가 필요한 경우 가장 높은 숫자 가중치를 사용 합니다. 이는 [인터넷 엔지니어링 작업 힘 설명서](https://www.ietf.org/rfc/rfc2782.txt)와 일치 합니다.
  
예를 들어 첫 번째 DNS SRV 레코드의 가중치가 20이 고 우선 순위가 40이 고 두 번째 DNS SRV 레코드의 가중치가 10이 고 우선 순위가 50 인 경우 첫 번째 레코드의 40 우선 순위가 낮은 것이 선택 됩니다. 우선 순위는 항상 먼저, 즉 클라이언트가 먼저 대상으로 하는 호스트입니다. 우선 순위가 같은 대상이 두 개 있는 경우 
  
이 경우에는 비중을 고려해 야 합니다. 가중치가 클수록이 환경에서 선택 되는 확률이 높음으로 지정 되어야 합니다. DNS 관리자는 수행할 서버 선택이 없는 경우 가중치 0을 사용 해야 합니다. 가중치가 0 보다 큰 레코드가 있는 경우 가중치가 0 인 레코드는 선택 된 상태로 만들 확률이 매우 낮습니다.
  
따라서 우선 순위가 같고 가중치가 반환 되는 여러 DNS SRV 레코드가 있는 경우 어떻게 되나요? 이 상황에서 액세스에 지 서비스는 먼저 DNS 서버에서 받은 SRV 레코드를 선택 합니다.
  

