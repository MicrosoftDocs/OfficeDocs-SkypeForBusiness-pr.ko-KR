---
title: Lync Server 2013:에 지 서버 계획에 영향을 주는 Lync Server의 변경 사항
description: Lync Server 2013:에 지 서버 계획에 영향을 주는 Lync Server의 변경 사항입니다.
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
ms.openlocfilehash: 8660a281d858cf92a48d5eaed6d5caf3141b3817
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543754"
---
# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>에 지 서버 계획에 영향을 주는 Lync Server 2013의 변경 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

Lync Server 2013에서는 사용자에 대 한 기능 및 통신 방법을 확장 하는 새로운 기능을 소개 합니다. 또한 Lync Server 2013에서는 조직에서 사용할 수 있는 서비스를 보다 효율적으로 통합 하 고 확장 하기 위해 기존 서비스의 변경 사항을 도입 합니다. 다음은 Lync Server 2013 Edge Server 서비스의 계획 및 배포에 영향을 줄 수 있는 변경 사항에 대 한 요약입니다.

<div>

## <a name="support-for-ipv6-addressing"></a>IPv6 주소 지정 지원

Lync Server 2013에서는 모든에 지 서버 서비스에 대 한 IPv6 주소 지정을 지원 합니다. Windows Server의 구성을 통해 인터페이스에 대 한 IPv6 주소를 제공한 경우 토폴로지 작성기의 IP 주소 구성을 통해에 지 서버 구성에 IPv6 주소를 사용할 수 있습니다. 또한 XMPP(Extensible Messaging and Presence Protocol)에서도 IPv6이 지원됩니다. 추가 구성은 필요하지 않습니다. 토폴로지에 IPv6가 구성된 경우 XMPP에서 IPv6가 사용됩니다(필요한 경우).

Lync Server 2013에서 i p v 6을 지 원하는 데 필요한 추가 요구 사항은 IPv6 주소로 검색 및 확인 해야 하는 레코드에 대 한 도메인 이름 시스템 레코드를 만드는 것입니다. IPv6 DNS는 **AAAA**("quad-A"라고 부름)로 정의되는 호스트 레코드를 사용합니다. 다른 레코드 유형은 해당 IPv4 항목과 비슷합니다.

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>XMPP(Extensible Messaging and Presence Protocol) 배포 지원

에 지 서버에는 전체 통합 XMPP 프록시 (에 지 서버에 배포 됨) 및 XMPP 게이트웨이 (프런트 엔드 서버에 배포 됨)가 도입 되었습니다. XMPP 페더레이션은 선택적인 구성 요소로 배포할 수 있습니다. XMPP 프록시 및 XMPP 게이트웨이를 추가 하 고 구성 하면 Microsoft Lync 2013 사용자가 IM (인스턴트 메시징) 및 현재 상태를 위해 XMPP 기반 파트너에서 연락처를 추가할 수 있습니다.

<div>


> [!NOTE]  
> 현재에 지 서버의 XMPP 서비스는 Lync Server 클라이언트와 XMPP 기반 연락처 사이에 IM 및 현재 상태를 제공 합니다. 또한 XMPP는 하나의 사이트에서만 호스팅됩니다.



</div>

<div>


> [!IMPORTANT]  
> Lync Server 2013의 XMPP 기능은 Google 대화를 사용한 인스턴트 메시징 페더레이션을 위해 Microsoft에서 테스트 하 고 지원 합니다. 다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션과 모든 배포 또는 문제 해결 권장 사항을 지원 하는지 확인 합니다.



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>오디오/비디오 인증 롤링 및 서버 간 인증 인증서 지원

인증서는 A/V 인증 서비스의 클라이언트 및 기타 소비자와 서버 간 인증을 위해 발급되는 토큰을 생성하는 데 사용됩니다. 오디오/비디오 인증 인증서는 *AudioVideoAuthentication* 유형이며 서버 간 인증 인증서는 *OAuthTokenIssuer* 유형입니다.

오디오/비디오 인증의 경우 토큰은 포트 할당 요청을 인증하는 데 사용되며, 토큰이 최대 8시간(토큰의 기본 수명) 동안 캐시에 저장됩니다. 정상 작동 상황에서는 A/V 소비자에 대해 인증 자료를 만들고 배포하는 데 매우 안정적인 방법이지만 인증서는 제한된 수명을 갖고 있으며 미리 정의된 날짜 및 시간(만든 날짜와 인증서를 만든 인증 기관에서 적용되는 정책 기반, 이 유형의 인증서의 경우 일반적으로 2년)에 만료됩니다. 인증서가 만료되면 만료된 인증서로 만들어지고 소비자가 캐시한 모든 토큰이 무효가 됩니다. 만료된 인증서로 만들어진 토큰을 사용하려고 시도하면 미디어 중계 할당이 실패하고 현재 오디오/비디오 세션이 실패합니다. 클라이언트가 정상적인 오디오 및 비디오 기능을 다시 사용하려면 유효한 인증서로 만들어진 새 토큰을 얻어야 합니다.

서버 간 인증은 배포의 모든 서버에 요청 되 고 적용 되는 전역 인증서에 의해 관리 됩니다. 이 인증서는 Exchange 2013 및 Microsoft SharePoint Server 2013 인증 뿐만 아니라 Lync Server 2013의 서버 인증을 담당 합니다. 서버 간 인증 방법에 대 한 자세한 내용은 [Lync server 2013에서 서버 대 서버 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)를 참조 하세요. 인증 또는 토큰의 수명에는 오디오/비디오 인증 프로세스와 서버 간 인증 프로세스 간의 매우 중요 한 차이가 있습니다. 오디오/비디오 인증의 경우 8 시간 후에 인증이 만료 됩니다. 서버 간 인증의 수명은 24 시간입니다. 각 인증서 유형에 맞게 계획을 세워야 합니다.

Lync Server 2013의 새로운 기능에서는 현재 인증서가 만료 되기 전에 대체 오디오/비디오 인증 인증서와 서버 간 인증 인증서를 준비 하는 기능이 제공 됩니다. 그 다음에는 새로운 토큰 또는 새로운 인증 요청을 생성할 때 새로운 인증서가 사용됩니다. 하지만 이전 인증서는 현재 세션 및 인증을 확인하기 위해 보존됩니다. 이러한 방식으로 토큰 및 인증서 만료로 인한 모든 오류를 효과적으로 방지할 수 있습니다. 이 기능에 대 한 자세한 내용과이를 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013 Using set-cscertificate in-Roll에서 AV 및 OAuth 인증서 준비](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate) 를 참조 하세요.

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>쿠키 기반 선호도에 대한 의존성 감소

이전 버전의 Lync Server 및 Office Communications Server에서는 웹 서비스에서 쿠키 기반 선호도를 사용 하 여 클라이언트 및 웹 서비스 세션 상태가 유지 되도록 했습니다. Lync Server 2013 웹 서비스는 쿠키 기반 선호도에 대 한 대부분의 요구 사항을 제거 하는 기본 제공 선호도 메커니즘을 사용 합니다.

<div>


> [!WARNING]  
> Microsoft Lync 2010 모바일 클라이언트는 여전히 쿠키 기반 선호도를 사용 해야 하며, 예정 된 Microsoft Lync 모바일 클라이언트로 모든 클라이언트를 마이그레이션할 때까지 쿠키 기반 선호도의 구성이 필요 합니다 (릴리스 날짜가 아직 결정 되지 않음).



</div>

Lync Server 2013의 쿠키 기반 선호도에 대 한 자세한 내용은 [Lync server 2013의 외부 사용자 액세스에 필요한 구성 요소](lync-server-2013-components-required-for-external-user-access.md)를 참조 하세요.

</div>

<div>

## <a name="autodiscover-enhancements"></a>자동 검색 향상 기능

Lync Server 2013의 자동 검색 기능을 사용 하면 클라이언트에서 통신에 사용할 수 있는 추가 기능을 찾을 수 있습니다. 자동 검색은 Lync Server 2010 용 누적 업데이트 (이동성의 경우 11 월 2011, Microsoft Lync 2010 Mobile)에서 처음 도입 되었습니다. 자동 검색 기능 (DNS 레코드 이름 LyncDiscover 및 LyncDiscoverInternal이 라고도 함)은 클라이언트가 모바일 서비스 (Microsoft Lync 2010 모바일 클라이언트), Microsoft Lync Web App 및 Lync 웹 스케줄러를 찾고 사용할 수 있으며 Microsoft Exchange Server 및 SharePoint Server와의 통신을 허용 합니다. 자동 검색은 인프라 및 Lync Server 2013 서버 설치 및 배포의 일반적인 부분으로 설치 됩니다. 토폴로지 작성기 및 Lync Server 배포 마법사는 Lync Server 2010의 누적 업데이트에서 필요한 구성 작업 중 대부분을 제거 합니다 2011.

</div>

<div>

## <a name="services-for-mobile-clients"></a>모바일 클라이언트를 위한 서비스

Lync Server에 대 한 누적 업데이트 2010 2011: Lync Server 2013의 모바일 서비스는 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용 하 여 Lync Mobile 및 태블릿 장치를 실행 하는 휴대폰을 사용 하도록 설정 하 여 인스턴트 메시지 보내기 및 받기, 연락처 보기, 현재 상태 보기 등의 작업을 수행 합니다. 또한 모바일 장치에서는 클릭 하 여 전화 회의, 직장 전화, 단일 번호 도착, 음성 메일 및 부재 중 전화 알림 등의 일부 Enterprise Voice 기능을 지원 합니다.

<div>


> [!NOTE]  
> 모바일 서비스에는 역방향 프록시 및 프런트 엔드 서버에 배포되는 게시된 서비스가 사용됩니다. 에지 서버는 변경할 필요가 없습니다. 최소한 Lync Server 액세스에 지 서비스를 실행 하는 서버의 아웃 바운드 SIP/TCP/5061from 사용 해야 합니다.



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>디렉터 역할이 선택 사항임

Lync Server 2013 토폴로지에서 디렉터 서버의 역할은 변경 되지 않았습니다. 이 서버는 여전히 웹 서비스를 호스팅하고, 수신되는 사용자 요청을 사전 인증하고, 외부 사용자를 해당 홈 풀로 전달합니다. 디렉터를 권장 역할에서 선택적 역할로 변경 하면 Microsoft는 디렉터 값을 감소 시 나 가지 않습니다. 이는 기능을 손상 시 키 지 않고 서버 수 및 기타 하드웨어 요구 사항 (예: 디렉터에 대 한 하드웨어 부하 분산 장치)을 줄이기 위한 것입니다. 프런트 엔드 서버는 제공 된 서비스에 영향을 주지 않고 디렉터와 동일한 작업을 수행할 수 있으므로를 선택한 경우에는 디렉터를 배포할 수 있습니다. 프런트 엔드 서버가 디렉터 대신 동일한 서비스를 제공 한다는 확신을 사용 하 여 디렉터를 안전 하 게 제외할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

