---
title: SIP, XMPP 페더레이션 및 공개 인스턴트 메시지에 대 한 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 994a1395363c28976c8bbfe325edae99e97cdc48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>SIP, XMPP 페더레이션 및 Lync Server 2013에서 공개 인스턴트 메시지에 대 한 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-28_

내부 및 외부 사용자가 파트너 조직 또는 서비스에서 연락처에 액세스할 수 있도록 Edge 서버를 구성할 수 있습니다. 이러한 파트너 계약을 알 수 있듯이, 페더레이션에서는 파트너 페더레이션 또는 파트너 연합의 연락처에 있는 조직의 연락처에 다음 중 일부 또는 모두를 제공 합니다.

  - 인스턴트 메시징 및 현재 상태

  - 공동 작업 및 회의 (예: 웹 회의)

  - 오디오 회의, 영상 회의 또는 둘 다

경우에 따라 Microsoft Lync Server 2013와 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 연락처 사이에 인스턴트 메시지 (IM)와 현재 상태 간의 통신을 전달 하는 경우 피어 투 피어 전용-사용자와 페더레이션에 있는 대화 상대만 지원 됩니다. partner. Lync Server, lync server 2013 페더레이션에 2010 등의 다른 경우에는 여러 참가자가 대화에 참여 하도록 초대할 수 있습니다.

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Lync Server 및 Office Communications Server Federation

Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server 간 페더레이션은 피어 투 피어 및 멀티 파티 통신을 지원 합니다. 피어 투 피어 대화를 여러 파티 대화로 에스컬레이션 하 여 임시 모임을 허용 합니다. 모임 – 웹 회의 또는 오디오/시각적 회의-조직 내부의 연락처 및 페더레이션 하는 파트너의 연락처를 포함 하도록 예약할 수 있습니다.

페더레이션이 먼저 Microsoft Office Live Communications Server 2005에 표시 되며 한 종류의 페더레이션 (직접 페더레이션)이 지원 됩니다. 직접 페더레이션에서는 페더레이션 파트너의 SIP (세션 초기화 프로토콜) 도메인과 파트너의 Edge 서버에 대 한 FQDN (정규화 된 도메인 이름)을 알고 있어야 합니다. 실시간 통신 서버 2005에는 해당 Edge 서버를 찾기 위해 페더레이션 파트너가 게시 하는 필수 DNS (domain name system) SRV 레코드가 추가 페더레이션 유형이 도입 되었습니다. 해당 릴리스의 용어는 다음과 같습니다.

  - *확장 페더레이션 열기*: 모든 SIP 도메인 이름 수락 및 DNS SRV를 사용 하 여 파트너에 지 서버 찾기

  - *확장 페더레이션*: 파트너의 SIP 도메인 이름을 조직의 페더레이션 파트너로 구성 하 고 DNS SRV를 사용 하 여 파트너에 지 서버를 찾습니다.

  - *직접 페더레이션*: 파트너의 SIP 도메인 이름 및 FQDN을 파트너의 Edge 서버로 구성 합니다.

  - *서버 허용 목록*: 모든 도메인 허용, DNS SRV를 사용 하 여 호스팅 공급자 또는 공용 인스턴트 메시징 (IM) 연결 공급자의 Edge 서버 찾기

Microsoft Office 통신 서버 2007은 페더레이션 형식에 대 한 명명 된 이름을 업데이트 하 여 각 페더레이션 형식이 실제로 수행 하는 항목을 더 잘 정의 합니다.

  - 개방형 확장 페더레이션이 검색 된 *파트너 도메인* 이라고 함

  - 확장 페더레이션이 허용 된 *파트너 도메인* 이라고 함

  - 직접 페더레이션이 허용 된 *파트너 서버* 라고 됨

  - 서버 허용 목록을 *호스팅 공급자* 및 *공용 IM 공급자* 라고 합니다.

Microsoft Lync Server 2010는 Microsoft Lync Online 2010 및 Microsoft Office 365에 따라 호스팅 공급자의 좁은 정의를 도입 했으며, 허용 된 파트너 도메인 페더레이션 유형에 의해 정의 된 것과 동일한 허용 목록을 적용 했습니다.

Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server 간 페더레이션을 사용 하도록 설정 하는 경우 Edge 서버 및 역방향 프록시를 사용 하 여 사용자가 정의한 규칙과 허용 된 파트너 도메인을 적용 합니다. 다른 Lync Server와 페더레이션 하는 계획의 관점에서 Office Communications Server에는 다음이 필요 합니다.

  - 토폴로지 작성기에서 페더레이션을 사용 합니다. 자세한 내용은 [Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공개 인스턴트 메시지 구성](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)배포 항목을 참조 하세요.

  - 페더레이션 도메인 검색에 대 한 요구 사항 결정:
    
      - <span></span>  
        페더레이션을 수동으로 구성 하려면 파트너의 Edge 서버 및 도메인 이름에 대 한 FQDN (정규화 된 도메인 이름)과 Lync Server 제어판, **페더레이션 및 외부 액세스**, **SIP 페더레이션 도메인**에 입력 한 온라인 도메인 이름이 있어야 합니다. **새** 정책을 만들거나 기존 정책을 **편집** 하 여 도메인을 FQDN으로 허용 하거나 차단 합니다.
        
        <div>
        

        > [!WARNING]
        > 페더레이션 파트너의 Edge 서버의 수동 구성은 파트너가 해당 Edge 서버의 IP 주소를 변경 하는 경우 오류가 발생 하기 쉽습니다.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <STRONG>새로운 SIP 페더레이션 도메인</STRONG>의 경우 Microsoft Lync Online, microsoft Office 365에 대 한 <STRONG>도메인 이름 (FQDN)</STRONG> 을 제공 해야 합니다. Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server의 경우에도 액세스에 <STRONG>지 서비스 (FQDN)</STRONG> 를 제공 해야 합니다.

        
        </div>
    
      - <span></span>  
        파트너가 Edge 서버를 검색할 수 있는 검색 된 파트너 페더레이션의 경우 외부 DNS- \_SIPFEDERATIONTLS에 SRV 레코드를 만듭니다. \_tcp.contoso.com – 포트 5061 및 Edge 서버의 호스트 (A) 레코드를 가리키는 위치
        
        <div>
        

        > [!IMPORTANT]
        > Windows Phone 또는 Apple iPhone, iPad 또는 기타 Apple 장치에서 Microsoft Lync 모바일 클라이언트를 지원 하며 푸시 알림 서비스 또는 푸시 알림 서비스를 사용 하는 경우에는 _sipfederationtls에 대 한 계획을 세워야 합니다 _tcp. &lt;Lync 모바일&gt; 클라이언트를 사용 하는 각 sip 도메인에 대 한 sip 도메인 SRV 레코드. Android 및 Nokia Symbian Lync Mobile은 푸시 알림을 사용 하지 않으며이 요구 사항이 적용 되지 않습니다.

        
        </div>

  - 페더레이션 도메인을 지원 하도록 외부 사용자 액세스 정책 구성

  - SIP (세션 시작 프로토콜), 웹 회의 및 오디오/시각적에 대 한 방화벽 포트를 열어 활성화 하려는 페더레이션 또는 대화 상대를 수용 합니다. 자세한 내용은 다음을 참조 하세요. [Lync Server 2013의 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

다음 정보는 Microsoft Lync Server 2013 및 Lync Server 2010의 페더레이션에 대 한 인증서, 포트/프로토콜 및 DNS 요구 사항을 정의 하는 데 도움이 됩니다.

Microsoft Lync Server 2013 Edge 서버를 계획 하거나 배포한 경우 인증서, 방화벽, 포트/프로토콜 요구 사항 및 DNS 요구 사항에 대 한 계획은 일반적으로 직선 전달 프로세스입니다. 페더레이션은 기존 Edge 서버를 사용 하는 추가 기능이 기 때문에 Edge 서버 계획 및 배포에 의해 일반적으로 계획 요구 사항이 충족 됩니다. 다음 표를 사용 하 여 요구 사항이 충족 되는지 확인 하 고 포트/프로토콜 및 DNS에서 적절 하 게 변경 합니다.

<div>


> [!IMPORTANT]
> Edge 서버 풀이 있고 Lync Server 2013 또는 Lync Server 2010 파트너와 페더레이션 하는 경우에는 Edge 서버의 내부 및 외부 측면에서 DNS 부하 분산 또는 하드웨어 부하 분산 장치를 사용할 수 있습니다. Office Communications Server 2007 또는 Office Communications Server 2007 R2에 페더레이션 하는 경우 하드웨어 로드 균형 조정은 Edge 서버의 이벤트에 장애 조치 (failover) 지원을 제공 합니다. Office Communications Server 2007 및 Office Communications Server 2007 R2는 DNS 부하 분산을 인식 하지 않습니다. 파트너에 지 서버는 풀에서 응답 하는 첫 번째 Edge 서버와 통신을 설정 합니다. 해당 Edge 서버에 장애가 발생 하면 통신은 자동으로 장애 조치 되지 않습니다.



</div>

일반적으로 인증서 요구 사항은 선택한 Edge 서버 또는 풀링된 Edge 서버 요금제의 인증서 계획을 통해 충족 됩니다.

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>공용 인스턴트 메시지 연결

공용 인스턴트 메시징 연결은 페더레이션 클래스 이며, 내부 및 외부 Lync Server 2013 사용자가 다음 중 한 곳에서 연락처를 추가할 수 있도록 구성 되었습니다.

  - Messenger 연락처

  - Yahoo\! 상대가

  - 아메리카 온라인 (AOL) 연락처

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 (PIC USL)는 더 이상 신규 또는 갱신 계약을 구매할 수 없습니다. 활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 (정확한 날짜는 결정 되지만 6 월 2013 미만) Messenger를 사용할 수 있습니다.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server가 Yahoo!에 페더레이션 하는 데 필요한 사용자별, 월별 구독 라이선스입니다. 받으려면. 이 서비스를 제공 하는 Microsoft의 기능은 갱신 되지 않을 기본 규약 인 Yahoo!의 지원으로 부과 됩니다.</P>
> <LI>
> <P>이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다. Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Skype 페더레이션은이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 통해 수백만 명에 게 연락할 수 있도록 합니다.</P></LI></UL>



</div>

이 페더레이션 클래스에는 다음과 같은 계획 고려 사항이 필요 합니다.

  - Windows Live Messenger 사용자는 인스턴트 메시지 외에도 Lync Server 2013 사용자와 피어 투 피어 오디오/시각적 통신을 할 수 있습니다. Edge 서버는 특정 포트 및 프로토콜 요구 사항을 충족 해야 합니다. 자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항을 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)하세요.

  - Yahoo 인스턴트 메시징에는 페더레이션을 제공 하는 일반 Edge 서버의 계획 및 배포에 일반적으로 사용 되는 것이 아닌 고유한 요구 사항이 없습니다.

  - 아메리카 온라인에서 액세스에 지 서비스에 할당 된 Edge 서버 인증서에는 EKU (클라이언트 확장 키 사용)가 있어야 합니다.

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션

이전 버전의 Lync Server 및 Office Communications Server에서는 XMPP 배포와 페더레이션 할 수 있는 별도의 서버 역할로 배포할 수 있는 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이를 제공 했습니다. Microsoft Lync Server 2013에서 XMPP 기능은 기능으로 배포할 수 있습니다. XMPP 기능은 Edge 서버에서 실행 되는 XMPP 프록시와 프런트 엔드 서버에서 실행 되는 XMPP 게이트웨이 등 두 부분으로 설치 됩니다.

XMPP의 배포 및 구성은 방화벽에서 포트 및 프로토콜 규칙을 정의 하 고, 인증서를 구성 하 고, DNS 레코드를 추가 하 여 조직에서 XMPP를 지원 하도록 계획 하는 [Lync Server 2013에서 외부 사용자 액세스를 배포](lync-server-2013-deploying-external-user-access.md) 하는 데 적용 됩니다. 이 단원의 다음 항목에서는 배포에 대해 XMPP 페더레이션을 성공적으로 계획 하는 데 필요한 정보를 요약 합니다.

<div>


> [!IMPORTANT]
> Google 대화가 포함 된 인스턴트 메시징 페더레이션에 대해 Microsoft에서 Lync Server 2013의 XMPP 기능을 테스트 하 고 지원 합니다. 다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션이 지원 되는지 여부와 배포 또는 문제 해결에 대 한 권장 사항을 확인 합니다.



</div>

<div>


> [!IMPORTANT]
> XMPP federation는 survivable branch 기기에 속한 사용자에 대해 지원 되지 않습니다. 이는 현재 상태 정보를 보고 메신저 대화 메시지를 교환 하는 데 모두 적용 됩니다.



</div>

</div>

<div id="sectionSection3" class="section">

다음 항목에는 지원 되는 페더레이션 시나리오의 종류에 대 한 인증서, 방화벽 포트 및 DNS 항목을 정의 하는 지침이 포함 되어 있습니다.

  - <span></span>  
    [인증서 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공개 인스턴트 메시지](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [포트 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공개 인스턴트 메시지](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [DNS 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공개 인스턴트 메시지](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 페더레이션 사용자 액세스를 제어할 정책 구성](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Lync Server 2013의 외부 사용자 액세스에 대한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013에 대한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Lync Server 2013에 대한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)  


[Lync Server 2013에서 조직에 대한 액세스 에지 구성 관리](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Lync Server 2013에서 조직의 SIP 페더레이션된 도메인 관리](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Lync Server 2013에서 조직에 대한 SIP 페더레이션 공급자 관리](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

