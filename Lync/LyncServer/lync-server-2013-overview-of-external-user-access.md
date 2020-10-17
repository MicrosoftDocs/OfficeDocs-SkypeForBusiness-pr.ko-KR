---
title: 'Lync Server 2013: 외부 사용자 액세스 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abbaa443231bfde1e780869a625859036b2e2506
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530595"
---
# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Lync Server 2013의 외부 사용자 액세스 개요

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-07_

이 문서에서는 *외부 사용자* 라는 용어를 사용 하 여 방화벽 외부에서 lync Server 2013 및 lync 2013 사용자와 통신 하는 대규모 사용자 범주를 정의 합니다. Lync Server 2013을 내부 사용자와 통신 하도록 권한을 부여할 수 있는 외부 사용자 (즉, 방화벽 내에서 Lync Server에 로그인 하는 사용자는 다음을 포함할 수 있습니다.

  - **원격 사용자**     방화벽 외부에서 Lync Server에 로그인 하는 조직의 사용자입니다.

  - **페더레이션 사용자**     Lync Server 2010, Lync Server 2013 또는 Office Communications Server 2007 r 2와 같이 신뢰할 수 있는 고객 또는 파트너 조직에 계정이 있는 사용자입니다. 페더레이션 사용자는 프런트 엔드 서버 또는 풀에 있는에 지 서버 및 XMPP 게이트웨이에서 XMPP 프록시를 통해 확장 메시징 및 현재 상태 프로토콜 (XMPP)을 사용 하 여 정의 된 파트너 조직의 구성원 일 수도 있습니다. 페더레이션 이라고 하는 정의 된 트러스트 관계는 Active Directory 도메인 서비스 트러스트 관계와 관련 되거나 종속 되지 않습니다.
    
    <div>
    

    > [!NOTE]  
    > AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.

    
    </div>

  - **공용 인스턴트 메시징 연결 사용자**     사용자가 공용 인스턴트 메시징 연결 서비스를 통해 설정한 연락처 (Windows Live, Yahoo\! 및 AOL)

  - **모바일 사용자**     Lync 모바일 클라이언트를 실행 하는 스마트 전화나 태블릿을 사용 하는 조직의 구성원 인 사용자는 내부 배포에 로그인 하 고 다른 사용자 클래스와 통신할 수 있습니다. 모바일 사용자는 역방향 프록시를 통해 게시 된 모바일 서비스를 사용 하 여 내부 배포에 액세스 합니다. Lync Mobile에서 사용할 수 있는 기능에 대 한 자세한 내용은 모바일 클라이언트 비교 표를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkID=234777](https://go.microsoft.com/fwlink/p/?linkid=234777) .

  - **익명 사용자**     조직의 Active Directory 도메인 서비스 또는 지원 되는 페더레이션 도메인에 사용자 계정이 없지만 온-프레미스 회의에 원격으로 참가할 수 있는 초대를 받은 사용자입니다.

에 지 배포에서는 다음과 같은 유형의 통신에 대 한 외부 액세스를 제공 합니다.

  - **IM 및 현재 상태**     권한 있는 외부 사용자가 IM 대화 및 회의에 참가할 수 있으며, 다른 사람의 현재 상태에 대 한 정보를 볼 수 있습니다. 공용 IM 서비스 공급자의 사용자는 조직에 있는 개별 Lync Server 사용자와의 IM 대화에 참가할 수 있으며 현재 상태 정보에는 연결 되지만 Lync Server를 사용 하 여 IM 단체 회의에 참가할 수는 없습니다. 이 회의는 엄격히 피어 투 피어 통신입니다. 공용 IM 서비스 공급자의 사용자는 파일 전송을 지원 하지 않으며, 피어 투 피어 통신의 오디오/비디오는 Windows Messenger 2011 사용자에 대해 지원 되지만 공용 IM 서비스 공급자의 다른 사용자에 게는 제공 되지 않습니다.
    
    SIP 및 XMPP 프로토콜이 둘 다 지원 됩니다. XMPP에 대 한 서비스를 제공 하려면 [Lync Server 2013에서 SIP, XMPP 페더레이션 및 공용 인스턴트 메시징에 대 한 계획](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)을 참조 하세요.

  - **웹 회의**     권한 있는 외부 사용자는 Lync Server 배포에서 호스트 되는 회의에 참가할 수 있습니다. 원격 사용자, 페더레이션 사용자 및 익명 사용자는 웹 회의에 참가할 수 있지만 공용 IM 사용자는 회의에 참가할 수 없습니다. 선택하는 옵션에 따라 웹 회의 가능 사용자는 데스크톱 및 응용 프로그램 공유에 참가할 수 있고 모임 이끌이나 발표자 역할을 할 수 있습니다.

  - **A/V 회의**     권한 있는 외부 사용자는 Lync Server 배포에서 호스트 하는 오디오 및 비디오 회의에 참가할 수 있습니다. 피어 투 피어 통신의 오디오/비디오는 Windows Messenger 2011 사용자에 대해 지원 되지만 다른 공용 IM 서비스 공급자의 사용자에 게는 사용할 수 없습니다.

통신을 제어 하기 위해 조직 내부 및 외부의 사용자가 서로 통신 하는 방식을 정의 하는 하나 이상의 정책을 구성할 수 있습니다. 또한 외부 사용자와의 통신을 제어하기 위해 특정 유형의 외부 사용자 또는 개별 내부 사용자에 대한 설정을 구성하고 정책을 적용할 수 있습니다.

Lync Server 2013에서는 외부 액세스를 제공 하는 데 사용 되는 역할을 설명 합니다.

에 **지 서버**     에 지 서버는 IM 및 현재 상태, 회의, 오디오/비디오 및 기타 미디어 (예: 파일 전송) 서비스에 대 한 외부 액세스를 허용 하는 서비스를 실행 하는 서버 또는 서버 풀입니다. 필요에 따라 다른 Lync Server 또는 Office Communications Server 2007 R2 배포 및 기타 XMPP 배포와 페더레이션 할에 지 서버를 구성할 수 있습니다. 선택적 공용 IM 연결 기능을 사용 하도록 설정 하 고에 지 서버를 통해 구성 합니다.

**디렉터**     디렉터는 사용자 요청을 미리 인증 하 고 사용자의 홈 프런트 엔드 서버 또는 프런트 엔드 풀로 요청을 라우팅하는 Lync Server 2013 디렉터 역할을 실행 하는 선택적 서버 또는 서버 풀로, 사용자 계정에는 home을 사용 하지 않습니다.

**역방향 프록시**     역방향 프록시는 내부 네트워크에서 사용할 수 있는 리소스를 게시 하 고 게시 된 리소스에서 클라이언트에 대 한 정보를 검색 하는 특수 서버에 대 한 일반적인 용어입니다. Lync Server 2013에서는 역방향 프록시를 사용 하 여 회의 모임, 전화 회의 참가 위치, 주소록, 메일 그룹 확장, 모임 콘텐츠, 장치 업데이트, 모바일 서비스 등의 다양 한 기능을 게시 합니다. 필요한 리소스 위치를 게시 하기 위한 요구 사항을 충족할 수 있는 모든 역방향 프록시를 사용할 수 있습니다. Microsoft Forefront Threat Management Gateway (TMG) 2010은 필요한 게시 규칙을 설명 하기 위한 예로 사용 되지만 Forefront TMG 2010는 필수 항목이 아닙니다.

<div>


> [!IMPORTANT]  
> Lync Server 2013는 IPv4 및 IPv6을 모두 지원 합니다. Windows Server &nbsp; 2008 &nbsp; R2, windows server 2012 및 windows Server 2012 R2는 IPv4 및 IPv6을 동시에 사용할 수 있는 이중 스택을 사용 합니다. 이는 배포의 전환 특성이 IPv4에서 IPv6으로 이동 하기 때문에 중요 합니다. IPv4는 배포의 다른 영역에서 IPv6을 사용할 수 있는 일부 지역에서 지원 될 수 있습니다. 이는 인터넷 및 내부 배포에 관련 된 경우 특히 중요 합니다. 외부 클라이언트는 이동성, 회의, 주소록 다운로드 등의 서비스를 사용 하기 위해 역방향 프록시를 통해 통신 해야 합니다. 현재 배포 된 운영 체제 버전에 관계 없이 Forefront Threat Management Gateway 2010와 Internet 보안 및 가속 서버 2006에서는 IPv6 주소 지정을 지원 하지 않습니다. 외부 클라이언트와 관련 된 IPv6 및 IPv4 사용과 관련 하 여 적절 한 계획을 세워야 합니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

