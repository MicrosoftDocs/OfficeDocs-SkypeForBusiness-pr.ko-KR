---
title: 모바일 모바일 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: 모바일 사용자에 대한 모바일 비즈니스용 Skype 서버.
ms.openlocfilehash: 59523076dc3b59b92af41fc85ef4193a92c87d08
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632722"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>모바일 모바일 비즈니스용 Skype 서버
 
모바일 사용자에 대한 모바일 비즈니스용 Skype 서버.
  
모바일 비즈니스용 Skype 서버 모바일 기능을 배포하여 모바일 장치에서 비즈니스용 Skype 서버 기능을 제공할 수 있습니다. 이 문서에서는 모바일 기능에 대해 자세히 설명하고 배포를 계획하는 데 도움이 됩니다.
  
모바일 기능의 비즈니스용 Skype 서버 2010으로 돌아가는 Lync 클라이언트뿐만 비즈니스용 Skype 클라이언트도 지원할 수 있습니다. 배포가 배포되면 사용자는 지원되는 iOS비즈니스용 Skype 서버 Android 및 Windows Phone 모바일 장치를 사용하여 Enterprise Voice 배포에 연결할 수 있습니다. 아래 부분 목록을 포함했습니다. 자세한 내용은 [](clients-and-devices/desktop-feature-comparison.md) 데스크톱 클라이언트 기능 비교에서 비즈니스용 Skype 수 있습니다.
  
- 메시지 보내기 및 받기
    
- 현재 상태 보기
    
- 연락처 보기
    
- 클릭하여 회의 참가
    
- 직장 전화
    
- 단일 번호 도달
    
- 음성 사서함
    
- 부재 중 전화 알림
    
- VoIP(Voice over IP)
    
- 참석자 비디오(H.264)
    
- 모임 콘텐츠 보기(PowerPoint 및 데스크톱/응용 프로그램 공유)
    
이 모든 작업을 통합 통신 웹 API 또는 UCWA를 통해 수행됩니다. UCWA는 Lync Server 2013에서 처음 도입되어 현재도 LYnc Server 2013에 비즈니스용 Skype 서버. Lync 2010 클라이언트 및 MCX(Mobility Service)와 통신하기 위한 추가 기능이 있습니다. 이러한 서비스는 무료 서비스로, Lync Server 2010 및 2013 클라이언트와 비즈니스용 Skype 클라이언트가 비즈니스용 Skype 서버 액세스할 수 있습니다.
  
> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 2019년 8월 비즈니스용 Skype 서버 없습니다. 현재 비즈니스용 Skype 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.
  
Mobility이 구현된 후 이러한 모든 기능을 사용할 수 있는 반면 일부 장치에서는 약간 다르게 작동할 수 있습니다. 에 대한 모바일 클라이언트 기능 비교에서 어떤 장치에서 작동할지 설명하는 웹 [비즈니스용 Skype.](clients-and-devices/mobile-feature-comparison.md) 또한 Plan for clients and devices(클라이언트 및 장치 계획)에 몇 가지 멋진 장치 및 OS [정보도 있습니다.](clients-and-devices/clients-and-devices.md)
  
모바일 기능은 자동 검색 기능을 사용하여 클라이언트가 사용자가 URL을 입력하지 않고도 비즈니스용 Skype 서버 웹 서비스를 자동으로 찾을 수 있도록 합니다(알 필요도 없습니다). 일부 문제 해결을 해야 하는 경우 URL의 수동 입력이 계속 지원됩니다.
  
푸시 알림은 비즈니스용 Skype 앱이 백그라운드에서 실행되지 않는 경우(또는 백그라운드에서 실행되는 응용 프로그램을 지원하지 않는 모바일 장치에 대해) 지원됩니다. 푸시 알림은 장치 또는 앱이 비활성일 때 발생하는 이벤트에 대해 모바일 장치로 전송됩니다. 좋은 예로는 휴대폰이 활성화되지 않은 경우 IM 메시지가 누락되고 푸시 알림이 전송됩니다(앱이 백그라운드에서 실행되는 경우와 같이 알림 또는 알림으로 표시). 푸시 알림을 통해 사용자는 IM 또는 음성 통화를 놓치지 않습니다.
  
자세한 내용은 다음 섹션을 참조하세요.
  
- [모바일 구성 요소](mobility.md#MobilityComponents)
    
- [지원되는 토폴로지](mobility.md#SupportedTopos)
    
- [기술 요구 사항](mobility.md#TechRequirements)
    
- [모바일 요구 정의](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>모바일 구성 요소
<a name="MobilityComponents"> </a>

모바일 서비스에는 다음 네 가지 서비스가 비즈니스용 Skype 서버.
  
- **UCWA(Unified Communications Web API)**
    
    모바일 및 웹 클라이언트와의 실시간 통신을 위한 서비스를 비즈니스용 Skype 서버. 배포 비즈니스용 Skype 서버 UCWA 가상 디렉터리가 내부 및 외부 웹 서비스에 만들어집니다. UCWA 사용 가능 클라이언트의 호출을 수락하는 이 가상 디렉터리의 가상 구성 요소입니다. 클라이언트 앱은 다음에 대한 REST(표현 상태 전송) 인터페이스를 통해 통신합니다.
    
  - presence
    
  - contacts
    
  - IM(인스턴트 메시징)
    
  - VoIP
    
  - 비디오 회의
    
  - 공동 작업
    
    UCWA는 P-GET 기반 채널을 사용하여 수신 전화, 들어오는 IM 또는 메시지와 같은 이벤트를 클라이언트 앱에 전송합니다.
    
- **Mobility Service(MCX)**
    
    모바일 비즈니스용 Skype 서버 IM, 현재 상태 및 연락처와 같은 사용자 기능을 지원합니다. Mobility Service는 모바일 장치에서 모든 프런트 엔드 비즈니스용 Skype 서버 지원하기 위한 모든 프런트 엔드 서버에 설치됩니다. 2015 비즈니스용 Skype 서버 설치하면 프런트 엔드 서버의 내부 및 외부 웹 사이트에 새 가상 디렉터리(Mcx)가 만들어집니다.
    
    > [!NOTE]
    > 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 2019년 8월 비즈니스용 Skype 서버 없습니다. 현재 비즈니스용 Skype 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.
  
- **Autodiscover 서비스**
    
    사용자의 위치를 식별하고 모바일 장치 및 기타 비즈니스용 Skype 클라이언트가 네트워크 위치에 관계없이 리소스를 찾을 수 있도록 합니다(예: 비즈니스용 Skype 서버 웹 서비스의 내부 및 외부 URL, Mcx URL 또는 UCWA URL). 자동 검색은 하드코드된 호스트 이름(네트워크 내부 사용자용 lyncdiscoverinternal, 네트워크 외부 사용자용 lyncdiscover) 및 사용자의 SIP 도메인을 사용 합니다. HTTP 또는 HTTPS를 사용하는 클라이언트 연결을 지원합니다. 
    
    Autodiscover 서비스는 모바일 장치의 모든 프런트 엔드 서버 및 각 풀의 모든 비즈니스용 Skype 서버 설치됩니다. 서비스를 설치하면 프런트 엔드 서버 및 디렉터의 내부 및 외부 웹 사이트에 새 가상 디렉터리(자동 검색)가 만들어집니다.
    
- **푸시 알림 서비스**
    
    비즈니스용 Skype 온라인 데이터 센터에 있는 클라우드 기반 서비스입니다. 백그라운드에서 실행되는 비즈니스용 Skype 없는 휴대폰에서 새 이벤트가 발생하면 부재 중 이벤트 알림(푸시 알림이라고도 하여)에 대한 알림이 모바일 장치로 전송됩니다. Mobility Service는 MPNS(푸시 알림 서비스)로 알림을 보내 모바일 장치로 전송합니다. 그러면 사용자는 모바일 장치에서 알림에 응답하여 앱을 활성화할 수 있습니다. 이 기능을 사용하려면 에지 서버가 필요합니다.
    
## <a name="supported-topologies"></a>지원되는 토폴로지
<a name="SupportedTopos"> </a>

토폴로지 계획에 비즈니스용 Skype 서버 지원되는 응용 프로그램이 있습니다.
  
- 모바일 Standard Edition
    
- 모바일 Enterprise Edition
    
에지 서버 또는 Lync Server 2013 에지 비즈니스용 Skype 서버 이 기능을 사용할 수 있습니다.
  
모바일 서비스는 중재 서버 역할과 함께 두 개의 네트워크 인터페이스가 함께 함께 배포된 경우 프런트 엔드 서버에서 지원되지만 이러한 인터페이스를 구성하려면 적절한 단계를 따라야 합니다. 중재 서버로 통신할 특정 인터페이스와 프런트 엔드 서버로 통신할 네트워크 IP 인터페이스에 IP 주소를 할당해야 합니다. 기본 구성된 모든 IP 주소 사용 선택을 사용하는 대신 각 서비스에 대해 올바른 IP 주소를 선택하여 토폴로지 작성기에서 이 작업을 할 **수** 있습니다.
  
## <a name="technical-requirements"></a>기술 요구 사항
<a name="TechRequirements"> </a>

모바일 사용자가 발생할 수 있는 다양한 모바일 응용 프로그램 시나리오를 계획하는 것이 중요합니다. 예를 들어 누군가가 3G 네트워크를 통해 연결하여 업무 외의 모바일 앱을 시작한 다음 회사 Wi-Fi 네트워크로 전환할 수 있습니다. 건물을 나서면 4G로 전환될 수 있습니다. 이제 계획을 세우면 이러한 네트워크 전환을 지원하고 일관된 사용자 환경을 보장할 수 있습니다.
  
### <a name="dns-configuration"></a>DNS 구성

Mobility Services Mcx와 UCWA는 동일한 방식으로 DNS를 사용 합니다. 자동 검색을 통해 모바일 장치는 DNS를 사용하여 리소스를 찾습니다. DNS를 쿼리하는 동안 내부 DNS 레코드(lyncdiscoverinternal)와 연결된 FQDN에 대한 연결이 시도됩니다. 내부 도메인 이름]) 내부 DNS 레코드를 사용하여 해당 연결을 만들 수 없는 경우 외부 DNS 레코드(lyncdiscover.[ sipdomain]) 그렇다면 두 가지가 있는 이유는 무엇일까요? 네트워크 내부에 있는 모바일 장치는 내부 자동iscover URL을 사용할 수 있습니다. 외부 모바일 장치는 외부 자동iscover URL을 사용합니다. 두 경우 모두 자동 검색 서비스는 모바일 서비스(Mcx 및 UCWA)를 포함하는 사용자의 홈 풀에 대한 모든 웹 서비스 URL을 반환합니다.
  
외부 자동검사 요청은 해당 요청에 대해 구성한 역방향 프록시를 비즈니스용 Skype 서버. 그러나 내부 Mobility Service URL과 외부 Mobility Service URL은 모두 외부 웹 서비스 FQDN과 연결됩니다. 따라서 모바일 장치가 네트워크의 내부 또는 외부에 있는지에 관계없이 장치는 항상 역방향 프록시를 통해 비즈니스용 Skype 서버 Mobility Service에 연결합니다.
  
> [!NOTE]
> 앞서 말한 것 처럼 모든 Mobility Service 트래픽(내부 및 외부)은 역방향 프록시를 통과합니다. 그러나 내부 트래픽이 인터페이스를 통해 나올 때 같은 인터페이스에서 다시 들어오려고 할 때만 문제가 나오는 경우도 있습니다. 이렇게하면 스푸핑(공식적으로 TCP 패킷 스푸핑) 보안 규칙을 위반할 수 있습니다. 이동성 기능을 **사용하려면** 헤어핀을 허용해야 합니다.
  
> [!NOTE]
> 이 작업을 할 준비가 된 경우 방화벽과 별개인 역방향 프록시를 사용할 수도 있습니다(보안을 위해 스푸핑 방지는 항상 방화벽에서 적용해야 합니다). 이렇게 하면 헤어빈이 방화벽의 외부 인터페이스가 아닌 역방향 프록시의 외부 인터페이스에서 발생될 수 있습니다. 이렇게 하면 역방향 프록시에서 규칙을 완화하는 동안 방화벽에서 스푸핑을 제대로 감지하고 모바일 기능을 사용할 수 있습니다. 
  
> [!NOTE]
> 이 경로로 이동하는 경우 가능한 경우 DNS 호스트 또는 CNAME 레코드를 사용하여 헤어빈 동작(방화벽이 아 아닌)에 대한 역방향 프록시를 정의해야 합니다. 
  
회사 네트워크 내부 및 외부의 사용자를 지원하도록 구성해야 하는 몇 가지가 있습니다.
  
내부 및 외부 웹 FQDNS에 대한 규칙은 다음과 같습니다.
  
- 자동 검색을 위해 새 CNAME 또는 A(호스트, IPv6, AAAA) DNS 레코드.
    
- 새 방화벽 규칙( 사용자 네트워크에서 푸시 알림을 지원하려는 Wi-Fi.
    
- 자동 검색을 위해 내부 서버 인증서 및 역방향 프록시 인증서의 주체 대체 이름입니다.
    
- 프런트 엔드 서버 하드웨어 부하가 조정된 구성으로 원본의 효율성이 변경됩니다.
    
Mobility Service 및 Autodiscover 서비스를 지원하는 데 필요한 토폴로지 요구 사항은 다음 사항입니다.
  
- 프런트 엔드 풀 내부 웹 FQDN은 프런트 엔드 풀 외부 웹 FQDN과 구분되어야 합니다.
    
- 내부 웹 FQDN은 회사 네트워크 내에서만 확인하여 액세스할 수 있어야 합니다.
    
- 외부 웹 FQDN은 인터넷에서만 확인하여 액세스할 수 있어야 합니다.
    
- 회사 네트워크 내부의 사용자의 경우 Mobility Service URL의 주소를 외부 웹 FQDN으로 지정해야 합니다. 이 요구 사항은 Mobility Service에 대한 것이고 이 URL에만 적용됩니다.
    
- 회사 네트워크 외부의 사용자의 경우 요청은 프런트 엔드 풀 또는 Director의 외부 웹 FQDN으로 이동해야 합니다.
    
자동 검색을 지원하는 경우 각 SIP 도메인에 대해 다음 DNS 레코드를 만들어야 합니다.
  
- 조직의 네트워크 내부에서 연결하는 모바일 사용자를 지원하기 위한 내부 DNS 레코드입니다.
    
- 인터넷에서 연결하는 모바일 사용자를 지원하기 위한 외부 또는 공용 DNS 레코드입니다.
    
내부 자동 검색 URL은 내부 네트워크 외부에서 주소를 지정하지 말아야 합니다. 외부 자동 검색 URL은 네트워크 내에서 주소를 지정하지 말아야 합니다. 그러나 외부 URL에 대해 이 기능을 사용할 수 없는 경우 내부 URL이 항상 먼저 시도될 것이기 때문에 모바일 클라이언트 기능이 영향을 받지 않습니다.
  
### <a name="port-and-firewall-requirements"></a>포트 및 방화벽 요구 사항

이 문서의 대부분을 다른 설명서에서 다루었지만 특히 Mobility의 경우 SBA(Survivable Branch Appliance)에 있는 사용자가 있는 경우 엔터프라이즈 Wi-Fi 네트워크에서 다음 포트를 열 수 있습니다.
  
- UcwaSipExternalListeningPort에는 5088이 필요합니다.
    
- UcwaSipPrimaryListeningPort에는 5089가 필요합니다.
    
### <a name="certificate-requirements"></a>인증서 요구 사항

비즈니스용 Skype 모바일 클라이언트에 대해 자동 검색을 사용하는 경우 모바일 클라이언트의 보안 연결을 지원하기 위해 인증서의 SAN(주체 대체 이름) 목록을 수정해야 합니다. 인증서가 이미 있는 경우 여기에 설명된 SAN 항목으로 새 인증서를 요청하고 할당해야 합니다. 이 작업 수행은 자동Iscover 서비스를 실행하는 각 프런트 엔드 서버 및 Director(작업 환경의 경우)에 대해 수행해야 합니다. 또한 역방향 프록시 인증서에서 SAN 목록을 수정하고 조직의 모든 SIP 도메인에 대해 SAN 항목을 추가하는 것이 좋습니다.
  
내부 CA(인증 기관)에서 새 인증서를 요청하는 경우 이 프로세스는 간단해야 하지만 공용 인증서는 더 복잡하며 다시 요청하는 데 비용이 훨씬 더 많이 들 수 있습니다. 또한 새 공용 인증서에 많은 SIP 도메인을 추가하는 것은 비용이 많이 들 수 있습니다. 이 경우 지원되지만 권장되지 않는 접근 **방식이 있습니다.** 포트 80을 통해 초기 자동 검색 서비스 요청을 하도록 역방향 프록시를 구성할 수 있습니다. 포트 443(HTTPS 및 443은 기본 구성)이 아니라 HTTP를 사용하게 됩니다. 들어오는 요청은 프런트 엔드 풀 또는 Director의 포트 8080으로 리디렉션됩니다. 이렇게 하면 이 트래픽이 요청에 HTTPS를 사용하지 않는 것이기 때문에 인증서를 변경할 필요가 없습니다. 그렇지만 이 작업을 위해 작동하지만 권장되지는 않습니다.
  
### <a name="windows-and-iis-requirements"></a>Windows 및 IIS 요구 사항

사용자 환경에 대해 지원되는 Windows Server 비즈니스용 Skype 서버 합니다. 따라서 모바일 요구에 대한 IIS 8 또는 IIS 8.5도 필요합니다. 기본 ASP.NET 변경해야 하지만 Mobility Service 설치 관리자에서 자동으로 변경됩니다.
  
### <a name="hlb-requirements"></a>HLB 요구 사항

프런트 엔드 풀에 대한 HLB가 포함된 토폴로지(프런트 엔드 서버가 두 개 이상 포함된 토폴로지)를 포함하는 웹 서비스용 토폴로지의 경우 웹 서비스 트래픽용 외부 웹 서비스 VIP(가상 IP)를 원본에 대해 구성해야 비즈니스용 Skype 서버 합니다. 원본 관련성은 단일 클라이언트의 여러 연결이 세션 상태를 유지하기 위해 동일한 서버로 전송되도록 하는 데 도움이 됩니다.
  
내부 비즈니스용 Skype 네트워크를 통해 비즈니스용 Skype 클라이언트를 지원할 경우 외부 웹 서비스 Wi-Fi 설명된 원본에 대해 내부 웹 서비스 VIP를 구성해야 합니다. 이 경우 HLB의 source_addr 웹 서비스 VIP에 대해 TCP(또는 TCP) 관련성을 사용하여야 합니다.
  
이 모든 내용에 대한 자세한 내용은 해당 설명서의 [부하 분산 요구 사항을 비즈니스용 Skype](network-requirements/load-balancing.md) 참조하세요.
  
### <a name="reverse-proxy-requirements"></a>역방향 프록시 요구 사항

모바일 클라이언트에 대한 자동 비즈니스용 Skype 지원하려면 다음과 같이 현재 게시 규칙을 업데이트해야 합니다.
  
- 역방향 프록시 인증서에서 SAN 목록을 업데이트하기로 결정하고 초기 자동 검색 서비스 요청에 HTTPS를 사용하는 경우 lyncdiscover에 대한 웹 게시 규칙을 업데이트해야 \<sipdomain\> 합니다. 이 작업은 일반적으로 프런트 엔드 풀의 외부 웹 서비스 URL에 대한 게시 룰과 결합됩니다.
    
- 역방향 프록시 인증서에 대해 SAN 목록을 업데이트하지 않고(권장하지 않는) 초기 자동 검색 서비스 요청에 대해 HTTP를 사용하기로 결정한 경우 아직 HTTP/TCP 80 포트에 대한 새 웹 게시 규칙을 만들어야 합니다. 해당 규칙이 있는 경우 lyncdiscover를 포함하게 업데이트합니다.\<sipdomain\> 항목을 입력합니다.
    
## <a name="defining-your-mobility-needs"></a>모바일 요구 정의
<a name="MobilityNeeds"> </a>

토폴로지, 구성 요소 및 기술 요구 사항을 검토했습니다. 이제 모바일 구현 측면에서 조직에 필요한 사항을 살펴보아야 합니다.
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>모바일 클라이언트에 대해 자동 검색을 비즈니스용 Skype 하나요?

자동 검색을 사용하는 것이 좋습니다. 위의 기술 요구 사항 섹션에 설명된 대로 새 내부 및 외부 DNS 레코드를 만들어야 합니다. 자동 검색을 비즈니스용 Skype 클라이언트는 URL을 수동으로 입력하지 않고도 모든 위치에서 비즈니스용 Skype 서버 웹 서비스를 자동으로 찾을 수 있습니다.
  
필요한 경우 수동 설정을 사용할 수 있습니다. 이러한 URL은 사용자가 모바일 장치에 입력해야 합니다.
  
- https:// 외부 액세스에 **\<ExtPoolFQDN\> 대해 /Autodiscover/autodiscoverservice.svc/Root를** 제공합니다.
    
- **https:// \<IntPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root를** 통해 내부 액세스를 허용합니다.
    
자동 검색을 사용하는 것이 좋습니다. 문제 해결을 위해 수동 설정을 사용할 수 있습니다.
  
### <a name="are-you-going-to-support-push-notifications"></a>푸시 알림을 지원할지 여부

푸시 알림은 이 기능을 지원하는 모바일 응용 프로그램에 사용되어 앱이 활성화되지 않은 동안 사용자에게 이벤트를 알릴 수 있습니다. 에지 서버는 비즈니스용 Skype 서버 Online 데이터 센터에 있는 클라우드 기반 비즈니스용 Skype 서버 푸시 알림 서비스와 페더 비즈니스용 Skype 해야 합니다. 푸시 알림을 사용하도록 설정하려면 cmdlet을 실행해야 합니다.
  
> [!NOTE]
> 여전히 Lync Server 2010 클라이언트를 사용하는 사용자가 있는 경우 엔터프라이즈 WiFi 네트워크에서 TCP 포트 5223이 열려 있는 아웃바운드 아웃바운드가 필요합니다. 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>모든 사용자가 모든 Mobility 기능에 액세스하게 하려는 경우 또는 이러한 기능에 액세스할 수 있는 사용자를 지정하고 싶습니까?

모든 사용자가 사용할 수 있는 기능 중 일부와 이러한 방식으로 설정되어 있는지 여부에 대한 도움말을 제공합니다. 전체 목록은 [New-CsMobilityPolicy를 검토하세요.](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)
  
> [!NOTE]
> 이러한 모든 기능에 대한 범위는 전역/사이트/사용자입니다. 
  
|**기능**|**매개 변수 이름**|**설명**|**기본 설정**|
|:-----|:-----|:-----|:-----|
|모바일 기능 사용  <br/> |EnableMobility  <br/> |모바일 클라이언트가 설치되어 있는 비즈니스용 Skype 사용자를 제어합니다. 정책이 False로 설정되어 있는 경우 사용자는 클라이언트로 로그인할 수 없습니다.  <br/> |True  <br/> |
|외부 음성  <br/> |EnableOutsideVoice  <br/> |사용자가 자신의 휴대폰 번호 대신 업무 번호를 사용하여 통화를 보내고 받을 수 있도록 하는 직장번호로 전화 기능을 사용할 수 있습니다. False로 설정하면 사용자가 직장 전화 번호를 사용할 때 휴대폰에서 전화를 걸거나 받을 수 없습니다.  <br/> |True  <br/> |
|IP 오디오 및 비디오 사용  <br/> |EnableIPAudioVideo  <br/> |기본값으로 설정하면 사용자가 VoIP를 사용하여 모바일 장치에서 전화 또는 화상 통화를 걸거나 받을 수 있습니다. False로 설정하면 사용자가 모바일 장치를 사용하여 이러한 작업을 할 수 없습니다.  <br/> |True  <br/> |
|IP 오디오에 WiFi 필요  <br/> |RequireWiFiForIPAudio  <br/> |클라이언트가 셀룰러 데이터 네트워크 대신 WiFi의 VoIP를 통해 전화를 걸고 받을지 여부를 정의합니다. True로 설정하면 사용자가 WiFi를 통해 연결될 때만 VoIP 통화를 걸고 받을 수 있습니다.  <br/> |거짓  <br/> |
|IP 비디오에 WiFi 필요  <br/> |RequireWiFiForIPVideo  <br/> |클라이언트가 셀룰러 데이터 네트워크 대신 WiFi에서 화상 통화를 걸고 받을지 여부를 정의합니다. True로 설정하면 사용자가 WiFi를 통해 연결될 때만 VoIP 통화를 걸고 받을 수 있습니다.  <br/> |거짓  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>회의에 참가할 수 Enterprise Voice 사용자가 클릭하여 참가를 사용하여 회의에 참가할 수 있나요?

사용자가 모바일 기능 및 직장을 통한 통화 기능에 액세스할 수 있도록 설정해야 Enterprise Voice. 그러나 사용하도록 설정되어 있지 않은 경우에도 모바일 장치에서 링크를 클릭하여 전화 회의에 참가할 수 있지만 적절한 음성 정책이 할당된 사용자에게만 해당됩니다. 구체적으로 다음과 같은 옵션을 선택할 수 있습니다.
  
- 이러한 사용자에게 특정 음성 정책을 할당하거나,
    
- 전역 정책 또는 사이트 수준 정책이 있으며 정책에 적용되는지 확인
    
어느 경우든 할당하는 음성 정책에는 사용자가 전화 회의에 참가하기 위해 전화를 걸 수 있는 위치를 정의하는 PSTN(Public Switched Telephone Network) 사용 레코드 및 경로가 필요합니다.
  
> [!NOTE]
> Click to Join을 사용하려는 모바일 사용자에게는 관련 PSTN 사용 레코드 및 음성 경로와 함께 음성 정책이 필요하며, 모바일 장치에서 해당 링크를 클릭하면 해당 사용자의 아웃바운드 통화가 비즈니스용 Skype 서버 됩니다. 
