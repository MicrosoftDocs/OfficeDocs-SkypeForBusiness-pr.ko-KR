---
title: SIP, XMPP 페더레이션 및 공용 인스턴트 메시징 계획
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
ms.openlocfilehash: c1e31e9fd0de6135dd1fd3f552d0d692f1bf7543
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Lync Server 2013에서 SIP, XMPP 페더레이션 및 공용 인스턴트 메시징 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-28_

내부 및 외부 사용자가 파트너 조직이 나 서비스에서 연락처에 액세스할 수 있도록에 지 서버를 구성할 수 있습니다. 페더레이션이라고도 하는 이러한 파트너 계약은 다음 기능 중 하나 또는 모든 기능을 파트너 페더레이션에 포함된 사용자 조직 내의 연락처 또는 사용자에 대한 파트너 페더레이션 내의 연락처에게 제공할 수 있습니다.

  - 인스턴트 메시징 및 현재 상태

  - 공동 작업 및 회의(예: 웹 회의)

  - 오디오 회의나 비디오 회의 중 하나 또는 둘 다

경우에 따라 Microsoft Lync Server 2013와 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 대화 상대와의 IM (인스턴트 메시징) 및 현재 상태 사이의 통신은 피어 투 피어 전용 이며 페더레이션에서 사용자와의 대화 상대를 지원 합니다. 파트너. Lync server와 같은 lync server 2010 lync server 2013 페더레이션에 연결 하는 다른 경우에는 여러 참가자가 대화에 참가 하도록 초대를 받을 수 있습니다.

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Lync Server 및 Office Communications Server 페더레이션

Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server 간의 페더레이션에서는 피어-투-피어 및 멀티 당사자 통신을 지원 합니다. 피어 투 피어 대화는 단체 대화로 확대되어 임시 모임을 허용할 수 있습니다. 웹 회의 또는 오디오/비디오 회의 같은 모임은 페더레이션 파트너의 대화 상대뿐 아니라 조직 내 대화 상대를 포함하도록 예약할 수 있습니다.

페더레이션은 Microsoft Office Live Communications Server 2005에 처음 표시 되며 한 종류의 페더레이션 (직접 페더레이션)을 지원 합니다. 직접 페더레이션에서는 페더레이션 파트너의 SIP (세션 시작 프로토콜) 도메인과 파트너에 지 서버의 FQDN (정규화 된 도메인 이름)을 확인 해야 합니다. Live Communications Server 2005 SP1에는 추가 페더레이션 유형이 도입 되었으며, 모든 필수 DNS (domain name system) SRV 레코드를 페더레이션 파트너가 해당에 지 서버를 찾기 위해 게시 해야 합니다. 해당 릴리스에 사용되는 용어는 다음과 같습니다.

  - *확장 페더레이션 열기*: 모든 SIP 도메인 이름을 수락 하 고 DNS SRV를 사용 하 여 파트너에 지 서버를 찾습니다.

  - *확장 페더레이션*: 파트너의 SIP 도메인 이름을 조직의 페더레이션 파트너로 구성 하 고 DNS SRV를 사용 하 여 파트너에 지 서버를 찾습니다.

  - *직접 페더레이션*: 파트너의 SIP 도메인 이름과 FQDN을 파트너의에 지 서버에 구성 합니다.

  - *서버 허용 목록*: 모든 도메인을 수락 하 고, DNS SRV를 사용 하 여 호스팅 공급자 또는 공용 IM (인스턴트 메시징) 연결 공급자의에 지 서버를 찾습니다.

Microsoft Office Communications Server 2007에서는 실제로 수행 되는 각 페더레이션 유형에 대해 보다 효율적으로 정의할 수 있도록 페더레이션 유형에 대 한 명명 된 이름이 도입 되었습니다.

  - 개방형 확장 페더레이션은 *검색된 파트너 도메인*으로 변경되었습니다.

  - 확장 페더레이션은 *허용된 파트너 도메인*으로 변경되었습니다.

  - 직접 페더레이션은 *허용된 파트너 서버*로 변경되었습니다.

  - 서버 허용 목록은 *호스팅 공급자* 및 *공용 메신저 공급자*로 변경되었습니다.

Microsoft Lync Server 2010에서는 Microsoft Lync Online 2010 및 Microsoft Office 365에 따라 호스팅 공급자가 보다 제한적으로 정의 되었으며, 허용 되는 파트너 도메인 페더레이션 유형에 서 정의 된 것과 동일한 허용 목록을 적용 했습니다.

Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server 간 페더레이션을 사용 하도록 설정에서는에 지 서버 및 역방향 프록시를 사용 하 여 사용자가 정의한 규칙과 허용 되는 파트너 도메인을 적용 합니다. 계획 측면에서 다른 Lync Server와 페더레이션-Office Communications Server에는 다음이 필요 합니다.

  - 토폴로지 작성기에서 페더레이션을 사용하도록 설정해야 합니다. 자세한 내용은 [Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공용 인스턴트 메시징 구성](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)에 대 한 배포 항목을 참조 하십시오.

  - 페더레이션 도메인 검색에 필요한 요구 사항을 결정합니다.
    
      - <span></span>  
        페더레이션 수동 구성을 사용 하려면 Lync Server 제어판, **페더레이션 및 외부 액세스**, **SIP 페더레이션 도메인**에 입력 된 파트너에 지 서버 및 도메인 이름 또는 온라인 도메인 이름의 FQDN (정규화 된 도메인 이름)이 있어야 합니다. FQDN으로 도메인을 허용하거나 차단하려면 **새로 만들기**로 정책을 새로 만들거나 **편집**으로 기존 정책을 편집합니다.
        
        <div>
        

        > [!WARNING]
        > 페더레이션 파트너의에 지 서버를 수동으로 구성 하면 파트너가 해당에 지 서버의 IP 주소를 변경 하는 경우 오류가 발생할 가능성이 높습니다.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <STRONG>새 SIP 페더레이션 도메인</STRONG>의 경우 microsoft Office 365에 대 한 사용자의 <STRONG>도메인 이름 (또는 FQDN)</STRONG> 을 제공 해야 합니다. Microsoft Lync Server 2013, Lync Server 2010 및 Office Communications Server의 경우에는 <STRONG>FQDN (액세스에 지 서비스)</STRONG> 도 제공 해야 합니다.

        
        </div>
    
      - <span></span>  
        파트너가에 지 서버를 검색할 수 있는 검색 된 파트너 페더레이션에 대해 외부 DNS- \_SIPFEDERATIONTLS에 SRV 레코드를 만듭니다. \_tcp.contoso.com –에 지 서버에 대 한 포트 5061 및 호스트 (A) 레코드를 가리킵니다.
        
        <div>
        

        > [!IMPORTANT]
        > Windows Phone 또는 Apple iPhone, iPad 또는 기타 Apple 장치에서 Microsoft Lync 모바일 클라이언트를 지원 하 고 푸시 알림 서비스 또는 푸시 알림 서비스를 사용 하는 경우에는 _sipfederationtls에 대 한 계획을 세워야 합니다 _tcp. &lt;Lync Mobile&gt; 클라이언트를 가진 각 sip 도메인에 대 한 SIP 도메인 SRV 레코드 Android 및 Nokia Symbian Lync Mobile에서는 푸시 알림을 사용 하지 않으며,이 요구 사항이 적용 되지 않습니다.

        
        </div>

  - 페더레이션 도메인을 지원하도록 외부 사용자 액세스 정책을 구성해야 합니다.

  - 사용하는 대화 상대 또는 페더레이션을 수용할 수 있도록 SIP(Session Initiation Protocol), 웹 회의 및 오디오/비디오용 방화벽 포트를 열어야 합니다. 자세한 내용은: [External A/V 방화벽 및 포트 요구 사항 확인에서 Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) 를 참조 하세요.

다음 정보는 Microsoft Lync Server 2013 및 Lync Server 2010와의 페더레이션에 대 한 인증서, 포트/프로토콜 및 DNS 요구 사항을 정의 하는 데 도움이 됩니다.

인증서, 방화벽 및 포트/프로토콜 요구 사항에 대 한 계획은 일반적으로 Microsoft Lync Server 2013에 지 서버를 계획 하거나 배포한 경우의 직선 전달 프로세스입니다. 페더레이션은 기존에 지 서버를 사용 하는 추가 기능이 기 때문에, 계획 요구 사항은 일반적으로에 지 서버 계획 및 배포에 의해 충족 됩니다. 다음 표를 참조하여 현재 요구 사항이 충족되는지, 표에 따라 포트/프로토콜 및 DNS를 변경해야 하는지 확인해야 합니다.

<div>


> [!IMPORTANT]
> 에 지 서버 풀이 있고 Lync Server 2013 또는 Lync Server 2010 파트너와 페더레이션 중인 경우에는에 지 서버의 내부 및 외부 측면에서 DNS 부하 분산 또는 하드웨어 부하 분산 장치를 사용할 수 있습니다. Office Communications Server 2007 또는 Office Communications Server 2007 r 2와 페더레이션 하는 경우 하드웨어 부하 분산은에 지 서버의 경우 장애 조치 (failover) 지원을 제공 합니다. Office Communications Server 2007 및 Office Communications Server 2007 R2는 DNS 부하 분산을 고려 하지 않습니다. 파트너에 지 서버는 풀에서 응답 하는 첫 번째에 지 서버와의 통신을 설정 합니다. 해당에 지 서버에 오류가 발생 하면 통신이 자동으로 장애 조치 (failover) 되지 않습니다.



</div>

일반적으로 선택한에 지 서버 또는 풀링된에 지 서버 계획에 대 한 인증서를 계획 하는 과정을 통해 인증서 요구 사항을 충족 합니다.

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>공용 인스턴트 메시징 연결

공용 인스턴트 메시징 연결은 페더레이션 클래스 이며 내부 및 외부 Lync Server 2013 사용자가 다음 중 하나에서 연락처를 추가할 수 있도록 구성 됩니다.

  - 메신저 대화 상대

  - Yahoo\! 연락처만

  - 북아메리카 온라인 (AOL) 연락처

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>2012 년 9 월 1 일부 터 신규 또는 갱신 계약에 대 한 Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 (PIC USL)를 더 이상 사용할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 (정확한 날짜는 계속 결정 되지만 6 월 2013 일 보다 일찍) Messenger.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server가 Yahoo!과 페더레이션 하는 데 필요한 사용자별 구독 라이선스 (매달)입니다. 메신저로. 이 서비스를 제공 하는 Microsoft의 기능은 갱신 되지 않을 기본 규약 인 Yahoo!을 지원 합니다.</P>
> <LI>
> <P>이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Lync 사용자가 IM 및 음성을 통해 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</P></LI></UL>



</div>

이 페더레이션 클래스를 사용 하려면 다음과 같은 계획 고려 사항을 충족 해야 합니다.

  - Windows Live Messenger 사용자는 인스턴트 메시징과 함께 Lync Server 2013 사용자와 피어 투 피어 오디오/시각적 통신을 할 수 있습니다. 에 지 서버는 특정 포트 및 프로토콜 요구 사항을 충족 해야 합니다. 자세한 내용은 [Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)을 참조 하십시오.

  - Yahoo 인스턴트 메시징의 경우에는 페더레이션을 제공 하는 일반에 지 서버를 계획 및 배포 하는 데 주로 사용 되는 것과는 다른 고유한 요구 사항이 없습니다.

  - 아메리카 온라인에서 액세스에 지 서비스에 할당 된에 지 서버 인증서에는 클라이언트 EKU (확장 된 키 사용)가 있어야 합니다.

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>XMPP (Extensible Messaging and 거점 Protocol) 페더레이션

이전 버전의 Lync Server 및 Office Communications Server에서는 XMPP 배포와의 페더레이션을 허용 하기 위해 별도의 서버 역할로 배포할 수 있는 XMPP (extensible messaging and 거점 protocol) 게이트웨이를 제공 했습니다. Microsoft Lync Server 2013에서는 XMPP 기능을 기능으로 배포할 수 있습니다. XMPP 기능은에 지 서버에서 실행 되는 XMPP 프록시 및 프런트 엔드 서버에서 실행 되는 XMPP 게이트웨이로 설치 됩니다.

XMPP의 배포 및 구성은 [Lync Server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 에서 설명 하며, 방화벽에 포트 및 프로토콜 규칙을 정의 하 고, 인증서를 구성 하 고, DNS 레코드를 추가 하 여 조직에서 xmpp를 지원 하기 위한 계획입니다. 이 섹션의 다음 항목에서는 배포에 대해 XMPP 페더레이션을 계획 하는 데 필요한 정보를 요약 하 여 설명 합니다.

<div>


> [!IMPORTANT]
> Lync Server 2013의 XMPP 기능은 Google 대화를 사용한 인스턴트 메시징 페더레이션을 위해 Microsoft에서 테스트 하 고 지원 합니다. 다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션과 모든 배포 또는 문제 해결 권장 사항을 지원 하는지 확인 합니다.



</div>

<div>


> [!IMPORTANT]
> XMPP 페더레이션은 sba (survivable branch 기기에 있는 사용자에 대해서는 지원 되지 않습니다. 이는 현재 상태 정보를 확인 하 고 IM 메시지를 교환 하는 방법에 모두 적용 됩니다.



</div>

</div>

<div id="sectionSection3" class="section">

다음 항목에는 지원 되는 페더레이션 시나리오 유형에 대해 인증서, 방화벽 포트 및 DNS 항목을 정의 하기 위한 지침이 포함 되어 있습니다.

  - <span></span>  
    [인증서 요약-Lync Server 2013의 SIP, XMPP 페더레이션 및 공용 인스턴트 메시징](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [포트 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공용 인스턴트 메시징](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [DNS 요약-SIP, XMPP 페더레이션 및 Lync Server 2013의 공용 인스턴트 메시징](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Lync Server 2013의 외부 사용자 액세스에 대 한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013에 대 한 외부 A/V 방화벽 및 포트 요구 사항 확인](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Lync Server 2013에 대 한 DNS 요구 사항 확인](lync-server-2013-determine-dns-requirements.md)  


[Lync Server 2013에서 조직에 대 한 액세스에 지 구성 관리](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Lync Server 2013에서 조직에 대 한 SIP 페더레이션 도메인 관리](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Lync Server 2013에서 조직에 대 한 SIP 페더레이션 공급자 관리](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

