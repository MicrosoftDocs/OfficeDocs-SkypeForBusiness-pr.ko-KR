---
title: 고급 에지 서버 배포 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 단일 서버를 비즈니스용 Skype 서버 또는 DNS 또는 HLB가 있는 서버 풀을 선호하는지 여부에 따라 배포 옵션에 대한 시나리오를 검토합니다.
ms.openlocfilehash: 5b58d9aa79566f7aee3ac102f1c5e73996bc6dae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767646"
---
# <a name="plan-advanced-edge-server-deployment-for-skype-for-business-server"></a>고급 에지 서버 배포 비즈니스용 Skype 서버
 
**요약:** 배포 옵션에 대한 비즈니스용 Skype 서버 검토합니다. 단일 서버를 사용하려는 경우 또는 DNS 또는 HLB가 있는 서버 풀을 선호하는 경우 이 항목은 도움이 됩니다.
  
DNS(Domain Name System) 계획과 비즈니스용 Skype 서버 결정에 많은 요소가 영향을 미치게 될 수 있습니다. 조직의 도메인 구조가 이미 있는 경우 진행 방법을 검토하는 데 문제가 될 수 있습니다. 아래에서 찾은 항목부터 시작해보아야 합니다.
  
- [서비스 찾기 비즈니스용 Skype 클라이언트에 대한 Walkthrough](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [분할 DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [분할 DNS를 사용하지 않은 자동 구성](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS 재해 복구](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [DNS 부하 분산](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>서비스 찾기 비즈니스용 Skype 클라이언트에 대한 Walkthrough
<a name="WalkthroughOfSkype"> </a>

비즈니스용 Skype 클라이언트는 Lync 클라이언트에서 서비스를 찾고 액세스하는 방법에서 이전 버전의 Lync 클라이언트와 비즈니스용 Skype 서버. 이 섹션에서는 서버 위치 프로세스에 대해 자세히 설명합니다.
  
1. lyncdiscoverinternal.\<domain\>
    
     *이 레코드는 내부 웹 서비스의 자동 검색 서비스에 대한 호스트 레코드입니다.* 
    
2. lyncdiscover.\<domain\>
    
     *이 레코드는 외부 웹 서비스의 자동 검색 서비스에 대한 호스트 레코드입니다.* 
    
3. _sipinternaltls._tcp.\<domain\>
    
     *내부 TLS 연결에 대한 SRV 레코드입니다.* 
    
4. _sip._tls.\<domain\>
    
     *외부 TLS 연결에 대한 SRV 레코드입니다.* 
    
5. sipinternal.\<domain\>
    
     *이 레코드는 내부 네트워크에서만 사용할 수 있는 프런트 엔드 풀 또는 Director의 호스트 레코드입니다.* 
    
6. sip.\<domain\>
    
     *이 레코드는 내부 네트워크에서만 사용할 수 있는 프런트 엔드 풀 또는 Director의 호스트 레코드입니다.* 
    
7. sipexternal.\<domain\>
    
     *클라이언트가 외부에 있는 경우 액세스 에지 서비스의 호스트 레코드입니다.* 
    
자동 검색 서비스는 항상 서비스 위치에 대한 기본 방법으로 선호되는 것이고, 다른 방법은 fallback 메서드입니다.
  
> [!NOTE]
> SRV 레코드를 만들 때 DNS SRV 레코드를 만드는 동일한 도메인에서 DNS A(및 IPv6 주소 지정을 사용하는 경우 AAAA)를 지정해야 합니다. 예를 들어 SRV 레코드가 contoso.com A(및 AAAA) 레코드는 SRV 레코드에 있을 수 fabrikam.com. 
  
원하는 경우 서비스를 수동으로 검색할 수 있도록 모바일 장치를 설정할 수 있습니다. 이 경우 각 사용자는 다음과 같이 프로토콜 및 경로를 포함하여 전체 내부 및 외부 자동iscover 서비스 URIS를 사용하여 모바일 장치 설정을 구성해야 합니다.
  
- 외부 액세스: \<ExtPoolFQDN\> https:// /Autodiscover/autodiscoverservice.svc/Root
    
- 내부 액세스: https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root
    
수동 검색이 아니라 자동 검색을 사용하는 것이 좋습니다. 그러나 몇 가지 문제 해결 또는 테스트를 수행하고 있는 경우 수동 설정이 매우 유용할 수 있습니다.
  
## <a name="split-brain-dns"></a>분할 DNS
<a name="SplitBrainDNS"> </a>

네임스페이스가 같은 두 DNS 영역이 있는 DNS 구성입니다. 첫 번째 DNS 영역은 내부 요청을 처리하고 두 번째 DNS 영역은 외부 요청을 처리합니다.
  
회사에서 이 작업을 하는 이유는 무엇입니까? 내부 및 외부적으로 동일한 네임스페이스를 사용해야 할 수도 있지만, 이 경우 많은 DNS SRV 및 A 레코드가 한 영역이나 다른 영역에서 고유하게 되거나 중복된 경우 이러한 레코드와 연결된 IP 주소가 고유하게 됩니다.
  
이 경우 몇 가지 과제가 있습니다. 가장 중요한 점은 분할 DNS가 모바일 **기능에서 지원되지 않는다는** 것입니다. 이는 LyncDiscover 및 LyncDiscoverInternal DNS 레코드(외부 DNS 서버에 LyncDiscover를 정의해야 하는 반면 LyncDiscoverInternal은 내부 DNS 서버에 정의해야 하기 때문에).
  
여기서는 내부 및 외부 영역의 DNS 레코드를 나열하지만 에지 서버 환경 요구 사항 섹션에서 자세한 예를 확인할 수 있습니다.
  
### <a name="internal-dns"></a>내부 DNS

- 예를 들어 contoso.com(예: 권한이 있는 DNS 영역)가 들어 있습니다.
    
- 이 내부 contoso.com 포함:
    
  - 프런트 엔드 풀, Director 풀 또는 Director 풀 이름 및 조직 네트워크에 있는 모든 내부 서버의 DNS A 및 AAAA(IPv6 주소 지정을 사용하는 경우) 레코드 및 비즈니스용 Skype 서버 실행됩니다.
    
  - 경계 네트워크의 각 에지 서버에 대한 에지 내부 인터페이스에 대한 DNS A 및 AAAA(IPv6 주소 비즈니스용 Skype 서버) 레코드
    
  - 경계 네트워크에 있는 각 역방향 프록시 서버의 내부 인터페이스(역방향 프록시 관리에 선택 사항)에 대한 DNS  A 및 AAAA(IPv6 주소 설정 사용) 레코드
    
  - DNS A 및 AAAA(IPv6 주소를 사용하는 경우) 및 내부 비즈니스용 Skype 서버 클라이언트 자동 구성에 대한 SRV 레코드(선택 **사항).**
    
  - DNS A 및 AAAA(IPv6 주소 사용 시) 또는 CNAME 레코드를 사용하여 비즈니스용 Skype 서버 웹 서비스를 자동으로 검색합니다(선택 **사항).**
    
- 경계 네트워크의 비즈니스용 Skype 서버 내부 에지 인터페이스는 이 내부 DNS 영역으로 쿼리를 확인하여 contoso.com.
    
- 비즈니스용 Skype 서버 실행되는 모든 서버와 회사 네트워크에서 비즈니스용 Skype 서버 실행되는 클라이언트는 쿼리를 해결하기 위해 내부 DNS 서버를 contoso.com 또는 각 에지 서버에서 호스트 파일을 사용하고 다음 홉 서버에 대한 A 및 AAAA(IPv6 주소 처리를 사용하는 경우) 레코드(특히 Director 또는 Director 풀 VIP용) 레코드를 사용하세요.  프런트 엔드 풀 VIP 또는 Standard Edition 서버).
    
### <a name="external-dns"></a>외부 DNS

- 예를 들어 contoso.com(예: 권한이 있는 DNS 영역)가 들어 있습니다.
    
- 이 외부 contoso.com 포함:
    
  - DNS A 및 AAAA(IPv6 주소 사용 시) 또는 CNAME 레코드를 사용하여 웹 서비스의 자동 검색을 비즈니스용 Skype 서버 있습니다. 이동성에 사용하기 위한 것입니다.
    
  - 경계 네트워크에 있는 각 비즈니스용 Skype 서버 에지 서버 또는 HLB(하드웨어 부하가 균형이 잡힌) VIP의 에지 외부 인터페이스에 대한 DNS A 및 AAAA(IPv6 주소) 및 SRV 레코드
    
  - 경계 네트워크에서 역방향 프록시 서버 또는 역방향 프록시 서버 풀의 외부 인터페이스에 대한 DNS A 및 AAAA(IPv6 주소 사용 시) 및 SRV 레코드
    
  - DNS A 및 AAAA(IPv6 주소를 사용하는 경우) 및 클라이언트 자동 구성에 대한 SRV 비즈니스용 Skype 서버(선택 **사항).**
    
## <a name="automatic-configuration-without-split-brain-dns"></a>분할 DNS를 사용하지 않은 자동 구성
<a name="NoSplitBrainDNS"> </a>

분할 DNS를 사용하지 않는 경우 여기에서 사용 중인 해결 비즈니스용 Skype 실행 중인 클라이언트의 내부 자동 구성이 작동하지 않습니다. 그 이유는 무엇인가요? 따라서 비즈니스용 Skype 서버 구성에 지정된 프런트 엔드 풀의 도메인과 일치하려면 사용자의 SIP URI가 필요합니다. 이는 이전 버전의 Lync Server에서 변경되지 않습니다.
  
따라서 두 SIP 도메인을 사용 중이면 다음 DNS SRV 레코드가 필요합니다.
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *사용자가 로그인한 bob@contoso.com 경우 사용자의 SIP 도메인이 프런트 엔드 풀(contoso.com)의 도메인과 일치하기 때문에 이 레코드는 자동 구성에 대해 contoso.com.* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *사용자가 로그인한 alice@fabrikam.com SIP 도메인이 해당 도메인의 프런트 엔드 풀과 일치하기 때문에 두 번째 도메인의 자동 구성에 대해 이 레코드가 작동하게 됩니다.* 
    
이 예제를 더 진행하기 위해 다음과 같은 작업을 할 수 없습니다.
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *SIP 도메인(litwareinc.com)이 풀(tim@litwareinc.com)의 도메인과 일치하지 않는 경우 사용자가 자동 구성에 대해 작동하지 fabrikam.com.* 
    
이제 분할 DNS가 없는 비즈니스용 Skype 클라이언트에 대한 자동 요구 사항이 필요한 경우 다음 옵션을 사용할 수 있습니다.
  
- **그룹 정책 개체**
    
    GOS(그룹 정책 개체)를 사용하여 올바른 서버 값을 채우는 데 사용할 수 있습니다.
    
    > [!NOTE]
    > 이 옵션은 자동 구성을 사용하도록 설정하지 않지만 수동 구성을 자동화합니다. 이 방법을 사용하는 경우 자동 구성과 연결된 SRV 레코드는 필요하지 않습니다. 
  
- **일치하는 내부 영역**
    
    내부 DNS에 외부 DNS 영역과 일치하는 영역(예: contoso.com)을 만든 다음 자동 구성에 사용되는 비즈니스용 Skype 서버 풀에 해당하는 DNS A(및 IPv6 주소 주소를 사용하는 경우 AAAA) 레코드를 만들어야 합니다.
    
    예를 들어 사용자가 pool01.contoso.net 있지만 비즈니스용 Skype bob@contoso.com 로그인한 경우 contoso.com 라는 내부 DNS 영역이 만들어지고 내부 DNS 영역 안에 pool01.contoso.com.
    
- **핀 포인트 내부 영역**
    
    내부 DNS에서 전체 영역 만들기가 옵션에 해당하지 않는 경우 자동 구성에 필요한 SRV 레코드에 해당하는 핀 포인트(전용) 영역 만들기를 수행하여 해당 영역들을 dnscmd.exe. Dnscmd.exe 인터페이스에서 핀 포인트 영역 만들기를 지원하지 않는 경우 이 설정이 필요합니다.
    
    예를 들어 SIP 도메인이 contoso.com 프런트 엔드 풀에 두 개의 프런트 엔드 서버가 포함된 pool01이라는 프런트 엔드 풀이 있는 경우 내부 DNS에 다음과 같은 핀 포인트 영역과 A 레코드가 필요합니다.
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    환경에 두 번째 SIP 도메인이 있을 수 있습니다. 이 경우 내부 DNS에 다음과 같은 핀 포인트 영역과 A 레코드가 필요합니다.
    
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
> 프런트 엔드 풀 FQDN이 두 번 나타나지만 서로 다른 두 IP 주소가 표시됩니다. 이는 DNS 부하 분산이 사용되고 있기 때문에입니다. HLB를 사용하는 경우 프런트 엔드 풀 항목은 하나만 있습니다. 
  
> [!NOTE]
> 또한 프런트 엔드 풀 FQDN 값은 contoso.com fabrikam.com 변경되지만 IP 주소는 동일합니다. 이는 두 SIP 도메인 중 하나에서 로그인하는 사용자가 자동 구성을 위해 동일한 프런트 엔드 풀을 사용하게 기 때문에 그에 해당합니다. 
  
## <a name="dns-disaster-recovery"></a>DNS 재해 복구
<a name="DNSDR"> </a>

웹 트래픽을 비즈니스용 SKYPE 서버 DR(재해 복구) 및 장애 조치 사이트로 리디렉션하도록 DNS를 구성하려면 GeoDNS를 지원하는 DNS 공급자를 사용해야 합니다. 재해 복구를 지원하기 위해 DNS 레코드를 설정하여 하나의 전체 프런트 엔드 풀이 다운된 경우에도 웹 서비스를 사용하는 기능이 계속 진행될 수 있습니다. 이 DR 기능은 자동Iscover, Meet 및 전화 접속 단순 URL을 지원합니다.
  
GeoDNS 공급자에서 웹 서비스의 내부 및 외부 확인을 위해 추가 DNS 호스트 A(IPv6) 레코드를 정의하고 구성합니다. 다음 세부 정보는 페어링된 풀, 지리적으로 분산된 풀 및 공급자가 지원하는 GeoDNS에 라운드 로빈 **DNS가** 있는 경우 또는 Pool1을 기본으로 사용하도록 구성되어 있으며 통신 손실 또는 정전이 있는 경우 Pool2로 장애 조치(fail over)를 가정합니다. 
  
이 표의 모든 DNS 레코드는 예제입니다.
  
|**GeoDNS 레코드**|**풀 레코드**|**CNAME 레코드**|**DNS 설정(하나의 옵션 선택)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com to Meet-int.geolb.contoso.com  <br/>   <br/> |풀 간 라운드 로빈  <br/> **또는** <br/> 기본 사용, 오류가 있는 경우 보조에 연결  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com to Meet-ext.geolb.contoso.com  <br/>   <br/> |풀 간 라운드 로빈  <br/> **또는** <br/> 기본 사용, 오류가 있는 경우 보조에 연결  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com to Meet-int.geolb.contoso.com   <br/>  <br/> |풀 간 라운드 로빈  <br/> **또는** <br/> 기본 사용, 오류가 있는 경우 보조에 연결  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com to Meet-ext.geolb.contoso.com  <br/>  <br/> |풀 간 라운드 로빈  <br/> **또는** <br/> 기본 사용, 오류가 있는 경우 보조에 연결  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com to Meet-int.geolb.contoso.com   <br/>   <br/> |풀 간 라운드 로빈  <br/> **또는** <br/> 기본 사용, 오류가 있는 경우 보조에 연결  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com to Meet-ext.geolb.contoso.com  <br/>  <br/> |풀 간 라운드 로빈  <br/> **또는** <br/> 기본 사용, 오류가 있는 경우 보조에 연결  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com to Meet-int.geolb.contoso.com   <br/>  <br/> |풀 간 라운드 로빈  <br/> **또는** <br/> 기본 사용, 오류가 있는 경우 보조에 연결  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com to Meet-ext.geolb.contoso.com   <br/>  <br/> |풀 간 라운드 로빈  <br/> **또는** <br/> 기본 사용, 오류가 있는 경우 보조에 연결  <br/> |
   
## <a name="dns-load-balancing"></a>DNS load balancing(DNS 부하 분산)
<a name="DNSLB"> </a>

DNS 부하 분산은 일반적으로 응용 프로그램 수준에서 구현됩니다. 응용 프로그램(예: 비즈니스용 Skype 실행 클라이언트)은 풀 FQDN에 대한 DNS A 및 AAAA(IPv6 주소가 사용되는 경우) 레코드 쿼리에서 반환된 IP 주소 중 하나에 연결하여 풀의 서버에 연결합니다.
  
예를 들어 이름이 pool01.contoso.com 프런트 엔드 서버가 3대인 경우 다음과 같은 문제가 발생하게 됩니다.
  
- 클라이언트에서 비즈니스용 Skype DNS에 대한 쿼리를 pool01.contoso.com. 쿼리는 세 개의 IP 주소를 반환하고 다음과 같이 캐시합니다(순서대로).
    
   |&nbsp;|&nbsp;|
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- 클라이언트는 IP 주소 중 하나에 대한 TCP 연결을 설정합니다. 실패하면 해당 목록에서 캐시된 다음 IP 주소를 시도합니다.
    
- TCP 연결이 성공하면 클라이언트는 TLS를 협상하여 TLS의 기본 등록자에 pool01.contoso.com.
    
- 클라이언트가 성공적으로 연결되지 않은 캐시된 항목을 모두 사용하게 될 경우 사용자는 현재 사용할 수 있는 서버가 없음을 비즈니스용 Skype 서버 알림을 받게 됩니다.
    
> [!NOTE]
> DNS 기반 부하 분산은 DNS RR(DNS 라운드 로빈)와는 다르며, 일반적으로 DNS를 사용하여 풀의 서버에 대해 서로 다른 IP 주소 순서를 제공하면 부하 분산을 참조합니다. 일반적으로 DNS RR은 부하 분산을 사용하도록 설정하지만 장애 조치(failover)를 사용하도록 설정할 수 없습니다. 예를 들어 DNS A(또는 IPv6 시나리오의 AAAA) 쿼리에서 반환된 IP 주소 하나에 대한 연결이 실패하면 해당 연결이 실패합니다. 이렇게 하면 DNS 기반 부하 분산보다 DNS RR의 안정성이 낮아질 수 있습니다. 필요한 경우 DNS 기반 부하 분산과 함께 DNS RR을 계속 사용할 수 있습니다. 
  
DNS 부하 분산을 사용하여 다음을 할 수 있습니다.
  
- 서버 대 서버 SIP를 에지 서버로 부하를 조정합니다.
    
- 회의, 응답 그룹 및 통화 파킹된 통화 자동 전화 교환 UCAS(통합 통신 응용 프로그램 서비스) 응용 프로그램의 부하를 조정합니다.
    
- UCAS 응용 프로그램에 대한 새 연결을 방지합니다(드레인).
    
- 클라이언트와 에지 서버 간의 모든 클라이언트-서버 트래픽 부하를 균형 조정합니다.
    
다음에는 DNS 부하 분산을 사용할 수 없습니다.
  
- 프런트 엔드 서버 또는 Director로의 클라이언트-서버 웹 트래픽
    
쿼리에서 여러 DNS 레코드가 반환될 때 DNS SRV 레코드가 선택되는 방식에 대해 좀 더 깊이 있게 이동하기 위해 액세스 에지 서비스는 항상 숫자 우선 순위가 가장 낮은 레코드를 선택하고, 동점 차단이 필요한 경우 가장 높은 숫자 가중치를 가중치로 선택합니다. 이는 Internet [Engineering Task Force 설명서와 일치합니다.](https://www.ietf.org/rfc/rfc2782.txt)
  
따라서 예를 들어 첫 번째 DNS SRV 레코드의 가중치가 20과 우선 순위 40인 경우 두 번째 DNS SRV 레코드의 가중치가 10과 우선 순위 50인 경우 우선 순위가 40이기 때문에 첫 번째 레코드가 선택됩니다. 우선 순위가 항상 우선하며 클라이언트가 먼저 대상으로 하는 호스트입니다. 우선 순위가 같은 대상이 두 개 있는 경우 어떻게 하나요? 
  
이 경우 가중치가 고려됩니다. 이 경우 더 큰 가중치가 선택될 확률이 높아야 합니다. 서버 선택이 없는 경우 DNS 관리자는 가중치 0을 사용해야 합니다. 가중치가 0보다 큰 레코드가 있는 경우 가중치가 0인 레코드는 선택될 가능성이 적습니다.
  
그렇다면 반환된 우선 순위와 가중치가 같은 여러 DNS SRV 레코드가 반환될 경우 어떻게 될까요? 이 경우 액세스 에지 서비스는 DNS 서버에서 먼저 SRV 레코드를 선택하게 됩니다.
  

