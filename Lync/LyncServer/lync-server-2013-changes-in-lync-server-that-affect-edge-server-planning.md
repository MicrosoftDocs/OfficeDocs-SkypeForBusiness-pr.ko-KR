---
title: 'Lync Server 2013: 에지 서버 계획에 영향을 주는 Lync Server의 변경 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73eda15acbce7eb4b47a0a52602776e8fc830b0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>에지 서버 계획에 영향을 주는 Lync Server 2013의 변경 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

Lync Server 2013는 사용자의 기능 및 통신 방법을 확장 하는 새로운 기능을 소개 합니다. 또한 Lync Server 2013는 조직에서 사용할 수 있는 서비스를 더욱 효율적으로 통합 하 고 확장 하기 위해 기존 서비스에 대 한 변경 사항을 소개 합니다. 다음은 Lync Server 2013 Edge 서버 서비스의 계획 및 배포에 영향을 줄 수 있는 변경 내용에 대 한 요약입니다.

<div>

## <a name="support-for-ipv6-addressing"></a>IPv6 주소 지정 지원

Lync Server 2013는 모든 Edge 서버 서비스에 대 한 IPv6 주소 지정을 지원 합니다. Windows Server의 구성을 통해 인터페이스에 대 한 IPv6 주소를 제공한 경우 토폴로지 작성기의 IP 주소 구성을 통해 Edge 서버 구성에서 IPv6 주소를 사용할 수 있습니다. 또한 XMPP는 확장 가능한 메시징 및 현재 상태 프로토콜을 지원 합니다. 추가 구성은 필요 하지 않습니다. 토폴로지에서 IPv6이 구성 된 경우 XMPP는 IPv6을 사용 합니다 (필요한 경우).

Lync Server 2013에서 IPv6을 지원 하기 위해 추가 요구 사항은 검색 하 고 IPv6 주소로 확인 해야 하는 레코드에 대 한 도메인 이름 시스템 레코드를 만드는 것입니다. IPv6 DNS는 **AAAA** 로 정의 되 고 "쿼드 A" 라고 하는 호스트 레코드를 사용 합니다. 다른 레코드 형식은 해당 IPv4와 일관성을 유지 합니다.

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 배포 지원

Edge 서버에는 완전 하 게 통합 된 XMPP 프록시 (Edge 서버에 배포 됨)와 XMPP 게이트웨이 (프런트 엔드 서버에 배포 됨)가 도입 되었습니다. XMPP 페더레이션은 선택적 구성 요소로 배포할 수 있습니다. XMPP 프록시 및 XMPP 게이트웨이를 추가 하 고 구성 하면 사용자가 인스턴트 메시지 (IM) 및 현재 상태에 대 한 XMPP 기반 파트너의 연락처를 추가 하도록 2013 설정할 수 있습니다.

<div>


> [!NOTE]  
> 현재 Edge 서버의 XMPP 서비스는 Lync Server 클라이언트와 XMPP 기반 연락처 간에 IM 및 현재 상태를 제공 합니다. 또한 XMPP는 하나의 사이트 에서만 호스팅됩니다.



</div>

<div>


> [!IMPORTANT]  
> Google 대화가 포함 된 인스턴트 메시징 페더레이션에 대해 Microsoft에서 Lync Server 2013의 XMPP 기능을 테스트 하 고 지원 합니다. 다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션이 지원 되는지 여부와 배포 또는 문제 해결에 대 한 권장 사항을 확인 합니다.



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>오디오/비디오 인증 및 서버에서 서버에 대 한 인증 인증서 롤링 지원

인증서는 클라이언트 및 A/V 인증 서비스의 다른 소비자와 서버에서 서버에 대 한 인증을 위해 발급 되는 토큰을 생성 하는 데 사용 됩니다. 오디오/비디오 인증 인증서의 형식은 e *Videoauthentication* 이며 서버 대 서버 인증 인증서의 형식은 *Oauthtokenissuer*입니다.

오디오/비디오 인증을 위해 토큰은 포트 할당 요청을 인증 하는 데 사용 되며 최대 8 시간 동안 토큰의 기본 수명으로 캐시 됩니다. 정상 작동 중에는 인증 자료를 만들어 A/V 소비자에 게 배포 하는 매우 안정적인 방법입니다. 그러나 인증서는 정해진 날짜와 시간에 만료 되며, 생성 날짜 및 인증서를 만든 인증 기관에 적용 되는 정책 (일반적으로 이러한 유형의 인증서에 대해 2 년)에 사용 됩니다. 인증서가 만료 되 면 만료 된 인증서로 생성 되 고 소비자가 캐시 한 모든 토큰이 유효 하지 않게 됩니다. 만료 된 인증서로 만든 토큰을 사용 하려는 경우 미디어 릴레이 할당이 실패 하 고 현재 오디오/비디오 세션이 실패 하 게 됩니다. 클라이언트는 일반 오디오 및 비디오 기능을 다시 시작 하기 위해 유효한 인증서로 만든 새 토큰을 취득 해야 합니다.

서버 대 서버 인증은 배포의 모든 서버에 요청 되 고 적용 되는 전역 인증서로 관리 됩니다. 이 인증서는 Lync Server 2013에서 서버를 인증 하는 것은 물론 Exchange 2013 및 Microsoft SharePoint Server 2013에 대 한 인증을 담당 합니다. 서버에서 서버 인증을 수행 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)를 참조 하세요. 오디오/비디오 인증 프로세스와 서버 간 인증 프로세스 간에 매우 중요 한 차이점은 인증 또는 토큰의 수명입니다. 오디오/비디오 인증의 경우 8 시간 후에 인증이 만료 됩니다. 서버 간 인증의 수명은 24 시간입니다. 각 인증서 유형에 대해 적절 하 게 계획을 세워야 합니다.

Lync Server 2013에 대 한 새로운 기능은 현재 인증서의 만료에 앞서 대체 오디오/비디오 인증 인증서 및 서버에서 서버 인증 인증서를 준비할 수 있습니다. 새 인증서는 새 토큰 또는 새 인증 요청을 생성 하는 데 사용 됩니다. 하지만 현재 세션과 인증을 확인 하기 위한 이전 인증서는 유지 됩니다. 이는 토큰 및 인증서 만료로 인해 거의 모든 오류를 효과적으로 방지 하는 것입니다. 이 기능에 대 한 자세한 내용과 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013 using-롤에서 설정-CsCertificate에서 AV 및 OAuth 인증서 준비](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate) 를 참조 하세요.

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>쿠키 기반 선호도에 대 한 의존도 감소

이전 버전의 Lync Server 및 Office Communications Server에서 쿠키 기반 선호도는 웹 서비스에서 클라이언트 및 웹 서비스 세션 상태가 유지 되도록 하는 데 사용 되었습니다. Lync Server 2013 웹 서비스는 쿠키 기반 선호도에 대 한 대부분의 요구 사항을 제거 하는 기본 제공 선호도 메커니즘을 사용 합니다.

<div>


> [!WARNING]  
> Microsoft Lync 2010 모바일 클라이언트는 여전히 쿠키 기반 접근 허용을 사용 해야 하며, 예정 된 Microsoft Lync 모바일 클라이언트로 모든 클라이언트를 마이그레이션할 때까지 쿠키 기반 선호도를 구성 해야 합니다 (릴리스의 날짜가 아직 결정 되지 않음).



</div>

Lync Server 2013의 쿠키 기반 선호도에 대 한 자세한 내용은 [Lync server 2013의 외부 사용자 액세스에 필요한 구성 요소](lync-server-2013-components-required-for-external-user-access.md)를 참조 하세요.

</div>

<div>

## <a name="autodiscover-enhancements"></a>자동 검색 기능 향상

Lync Server 2013의 자동 검색 기능을 통해 클라이언트는 통신에 사용할 수 있는 추가 기능을 찾을 수 있습니다. 자동 검색은 Lync Server 2010의 누적 업데이트에서 처음 도입 되었으며, 이동성 및 Microsoft Lync 2010 Mobile 용 2011 11 월입니다. 자동 검색 기능 (DNS 레코드 이름에는 LyncDiscover 및 LyncDiscoverInternal이 라고도 함)은 클라이언트가 모바일 서비스 (Microsoft Lync 2010 모바일 클라이언트), Microsoft Lync Web App 및 Lync Web scheduler을 찾아 사용할 수 있도록 합니다. Microsoft Exchange Server 및 SharePoint Server와 통신 자동 검색은 인프라 및 Lync Server 2013 서버 설정 및 배포의 일반적인 부분으로 설치 됩니다. 토폴로지 작성기 및 Lync Server 배포 마법사는 Lync Server 2010의 누적 업데이트에 필요한 대부분의 구성 작업을 제거 합니다 (2011 년 11 월).

</div>

<div>

## <a name="services-for-mobile-clients"></a>모바일 클라이언트용 서비스

Lync Server에 대 한 누적 업데이트 2010: lync 2013 Server의 모바일 서비스에서 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용 하 여 Lync Mobile 및 태블릿 장치를 실행 하는 모바일 전화를 사용할 수 있습니다 2011. 인스턴트 메시지 보내기, 받기, 연락처 보기, 현재 상태 보기 등의 활동 또한 모바일 장치는 클릭 하 여 회의에 참가 하 고, 회사, 단일 전화 접속, 음성 메일, 부재 중 전화 알림 등 일부 엔터프라이즈 음성 기능을 지원 합니다.

<div>


> [!NOTE]  
> 모바일 서비스는 프런트 엔드 서버에 배포 되는 리버스 프록시 및 게시 된 서비스를 사용 합니다. Edge 서버를 변경할 필요는 없습니다. 최소한 Lync Server 액세스 Edge 서비스를 실행 하는 서버에서 아웃 바운드 SIP/TCP/5061from 사용 해야 합니다.



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>디렉터 역할은 선택 사항입니다.

Lync Server 2013 토폴로지에서 디렉터 서버의 역할은 변경 되지 않았습니다. 계속 해 서 웹 서비스를 호스팅하고, 들어오는 사용자 요청을 사전 인증 하 고, 외부 사용자를 홈 풀로 보냅니다. 디렉터를 권장 역할에서 선택적 역할으로 변경 하는 것은 Microsoft가 디렉터 값을 감소 시 게 하지 않으려는 경우입니다. 이는 기능과 기능을 손상 시 키 지 않고 서버 수 및 기타 하드웨어 요구 사항 (예: 디렉터의 하드웨어 부하 분산 장치)을 줄이는 것입니다. 프런트 엔드 서버는 제공 되는 서비스에 영향을 주지 않고 디렉터와 동일한 작업을 수행할 수 있기 때문에를 선택 하는 경우에는 디렉터를 배포할 수 있습니다. 프런트 엔드 서버가 디렉터 대신 동일한 서비스를 제공 한다는 확신 없이 디렉터를 안전 하 게 제외할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

