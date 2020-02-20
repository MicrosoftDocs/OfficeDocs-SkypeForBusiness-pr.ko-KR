---
title: 'Lync Server 2013: 주요 보안 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a03a5c312123d714eebe8d49674a19ce712e37bc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a>Lync Server 2013의 주요 보안 기능

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-18_

Lync Server 2013에는 서버 간 인증, 역할 기반 액세스 제어 및 구성 데이터의 중앙 집중식 저장소를 포함 하 여 여러 가지 보안 기능이 포함 되어 있습니다.

이 문서에서는 Lync Server 2013 보안에 대 한 높은 수준의 개요를 제공 합니다.

<div>

## <a name="key-security-features-in-lync-server-2013"></a>Lync Server 2013의 주요 보안 기능

보안은 매우 광범위 한 항목입니다. Lync Server 2013의 모든 기능과 Lync 에코 시스템을 구성 하는 데이터베이스, 서비스 및 하드웨어에 대 한 보안에도 도달 합니다. 이 문서에서는 보안을 위해 설계 된 Lync Server 2013의 몇 가지 기능에 대해 간략하게 설명 합니다.

<div>

## <a name="planning-and-design-tools"></a>계획 및 디자인 도구

Lync Server 2013에서는 계획 및 디자인을 용이 하 게 하 고 Lync Server 구성 요소를 잘못 구성 하는 기회를 줄이기 위한 두 가지 도구를 제공 합니다.

  - **토폴로지 계획 도구** 는 토폴로지 디자인 프로세스의 대부분을 자동화 합니다. Lync Server 2013를 실행 하는 각 서버를 설치 하는 데 필요한 도구인 계획 도구에서 토폴로지 작성기로 결과를 내보낼 수 있습니다.

  - **토폴로지 작성기** 는 모든 구성 정보를 중앙 관리 저장소에 저장 합니다.

이러한 도구에 대 한 자세한 내용은 [Lync Server 2013에 대 한 계획](lync-server-2013-planning.md)을 참조 하십시오.

</div>

<div>

## <a name="central-management-store"></a>중앙 관리 저장소

Lync Server 2013에서 서버 및 서비스에 대 한 구성 데이터는 중앙 관리 저장소의 일부입니다. 중앙 관리 저장소는 Lync Server 배포를 정의, 설정, 유지 관리, 관리, 설명 및 운영 하는 데 필요한 데이터에 대 한 강력한 schematized 저장소를 제공 합니다. 또한 데이터의 유효성을 검사하여 구성 일관성을 보장합니다. 이 구성 데이터에 대 한 모든 변경 내용은 중앙 관리 저장소에서 수행 되며 "비동기화" 문제를 제거 합니다.

데이터의 읽기 전용 복사본이 Edge 서버를 포함한 토폴로지의 모든 서버로 복제됩니다. 복제는 기본적으로 네트워크 서비스의 컨텍스트에서 실행 되는 서비스에 의해 관리 되며, 컴퓨터의 단순 사용자에 대 한 권한 및 사용 권한을 줄입니다.

</div>

<div>

## <a name="server-to-server-authentication"></a>서버 간 인증

Lync Server 2013에서는 OAuth (Open Authorization) 프로토콜을 사용 하 여 서버 간에 인증을 구성할 수 있습니다. 예를 들어 Exchange Server 2013를 실행 하는 서버에서 인증을 받도록 Lync Server 2013를 구성할 수 있습니다. Lync server와 Exchange 서버는 OAuth 프로토콜을 사용 하 여 서로를 신뢰할 수 있습니다. 이렇게 하면 제품을 원활 하 게 통합 하는 기능이 제공 됩니다. 자세한 내용은 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 참조 하세요.

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a>Windows PowerShell 기반 관리 및 웹 기반 관리 인터페이스

Lync Server 2013에서는 Windows PowerShell 명령줄 인터페이스를 기반으로 하는 강력한 관리 인터페이스를 제공 합니다. 여기에는 보안을 관리 하기 위한 cmdlet이 포함 되어 있으며 사용자가 스크립트를 쉽게 또는 모르고 실행할 수 없도록 Windows PowerShell 보안 기능이 기본적으로 사용 되도록 설정 됩니다. 즉, 소프트웨어 기본값은 보안을 최대화 하 고 공격에 대 한 정보를 줄이기 위해 자동으로 설정 됩니다. Lync Server 2013의 Windows PowerShell 관리 지원에 대 한 자세한 내용은 [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)을 참조 하십시오.

</div>

<div>

## <a name="role-based-access-control-rbac"></a>RBAC(역할 기반 액세스 제어)

Microsoft Lync Server 2013에서는 RBAC (역할 기반 액세스 제어)를 제공 하 여 보안에 대 한 높은 표준을 유지 하면서 관리 작업을 위임할 수 있도록 합니다. RBAC를 사용 하 여 사용자에 게 작업에 필요한 관리 권한만 부여 되는 "최소 권한"의 원칙을 따를 수 있습니다. Lync Server 2013에서는 새 역할을 만드는 기능이 도입 되었으며 기존 역할을 수정할 수도 있습니다. 자세한 내용은 [Lync Server 2013에서 역할 기반 액세스 제어 계획](lync-server-2013-planning-for-role-based-access-control.md)을 참조 하십시오.

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a>NAT (Network Address Translation)

Lync Server 2013은에 지 서버의 내부 인터페이스에 NAT (network address translation) 사용을 지원 하지 않지만, 단일 및 확장 된 통합에 지 서버 토폴로지에 대해 NAT (network address translation)를 수행 하는 라우터나 방화벽 뒤에는 액세스에 지 서비스, 웹 회의에 지 서비스 및 A/V에 지 서비스의 외부 인터페이스를 제공 하는 것을 지원 합니다. 하드웨어 부하 분산 장치 뒤에 있는 여러 개의에 지 서버는 NAT를 사용할 수 없습니다. 여러에 지 서버가 외부 인터페이스에서 NAT를 사용 하는 경우 DNS (Domain Name System) 부하 분산이 필요 합니다. 그러면 DNS 부하 분산을 사용 하 여에 지 서버 풀의에 지 서버 당 공용 IP 주소 수를 줄일 수 있습니다. 자세한 내용은[Lync Server 2013에서 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md)을 참조 하십시오.

<div>


> [!NOTE]  
> Microsoft Office Communications Server 2007 배포가 있는 기업과 페더레이션 하 고 있으며 엔터프라이즈와 페더레이션 엔터프라이즈 사이에 오디오/비디오를 사용 해야 하는 경우에는 배포 되는에 지 서버의 이전 버전에 대 한 포트 요구 사항이 됩니다. 예를 들어 이러한 이전 버전에 필요한 포트 범위는 페더레이션 파트너가 해당에 지 서버를 Lync Server 2013로 업그레이드할 때까지 두 엔터프라이즈에서 모두 열어야 합니다. 이때 새 구성에 따라 포트 요구 사항을 검토 하 고 축소할 수 있습니다.



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a>에 지 서버에 대 한 간소화 된 인증서

배포 마법사에서 주체 이름 (SNs) 및 주체 대체 이름 (San)을 자동으로 채워 불필요 하 고 안전 하지 않을 수 있는 항목을 포함할 가능성이 줄어듭니다.

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a>SDL (보안 개발 수명 주기)의 신뢰할 수 있는 컴퓨팅

Lync Server 2013는에 <https://go.microsoft.com/fwlink/?linkid=68761>설명 되어 있는 Microsoft의 신뢰할 수 있는 컴퓨팅 SDL (보안 개발 수명 주기)을 준수 하 여 설계 및 개발 되었습니다.

  - **신뢰할**   수 있는 것으로 디자인이 보다 안전한 통합 통신 시스템을 만드는 첫 번째 단계는 위협 모델을 디자인 하 고 설계 된 각 기능을 테스트 하는 것 이었습니다. 또한 Microsoft는 예기치 않은 제품 문제로 인해 발생 하는 보안 취약성을 찾기 위해 디자인 된 동작 외부에서 테스트를 수행 합니다. 여러 보안 관련 향상 된 기능이 코딩 프로세스 및 사례에 기본적으로 제공 됩니다. 빌드 시간 도구는 코드가 최종 제품에 체크 인 되기 전에 버퍼 오버런과 기타 잠재적 보안 위협을 검색 합니다. 물론 알려지지 않은 모든 보안 위험을 디자인 하는 것은 불가능 합니다. 시스템에서 완전 한 보안을 보장할 수 없습니다. 그러나 제품 개발 embraced 시작에서 보안 디자인 원리를 구성 하기 때문에 Lync Server 2013는 업계 표준 보안 기술을 해당 아키텍처의 기본 부분으로 통합 합니다.

  - **신뢰할**수 기본적으로 기본적으로 Lync Server 2013의 네트워크 통신은 암호화 되어 있습니다.    모든 서버는 인증서 및 Kerberos 인증, TLS, 보안 실시간 전송 프로토콜 (SRTP) 및 128 비트 AES (Advanced Encryption Standard) 암호화를 비롯 한 기타 업계 표준 암호화 기법을 사용 하므로 사실상 모든 Lync 네트워크에서 서버 데이터가 보호 됩니다. 또한 역할 기반 액세스 제어를 통해 Lync Server 2013을 실행 하는 서버를 배포 하 여 각 서버 역할이 서비스만 실행 되 고 해당 서비스와 관련 된 사용 권한만 있으면 서버 역할에 적합 합니다.

  - **신뢰할**   수 있는 프로그램 배포 모든 Lync Server 2013 설명서에는 배포에 최적의 보안 수준을 결정 및 구성 하는 데 도움이 되 고 비기본 옵션을 활성화 하는 경우의 보안 위험을 평가할 수 있는 모범 사례 및 권장 사항이 포함 되어 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

