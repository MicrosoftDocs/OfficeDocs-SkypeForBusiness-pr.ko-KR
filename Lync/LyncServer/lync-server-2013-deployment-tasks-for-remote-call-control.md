---
title: 'Lync Server 2013: 원격 통화 제어에 대한 배포 작업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df80ebcdc879598677a037d60c9eeeee46ba5209
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762556"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013의 원격 통화 제어에 대한 배포 작업

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-05_

이 항목에서는 Lync Server 환경에서 사용자에 대 한 원격 통화 제어를 사용 하도록 설정 하기 위해 수행 해야 하는 배포 작업에 대해 설명 합니다.

<div>


> [!NOTE]  
> Microsoft Office Communicator 2007 R2에서 이전에 원격 통화 제어에 대해 사용 하도록 설정 된 사용자를 마이그레이션하는 경우에는이 항목에서 설명 하는 원격 통화 제어 배포 작업을 시작 하기 전에 추가 배포 작업을 수행 해야 합니다. Lync Server로 마이그레이션 프로세스를 진행 하는 동안에는 Office Communications Server 2007 R2 관리 도구를 사용 하 여 신뢰할 수 있는 응용 프로그램 항목 (이전에는 <EM>권한이 있는 호스트 항목</EM>이라고 함)을 제거 해야 합니다.<BR>권한이 부여 된 호스트를 제거 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Lync Server 2013에서 레거시 권한 있는 호스트 제거 (선택 사항)</A>를 참조 하세요.



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>1 단계: SIP/CSTA 게이트웨이를 설치 하 고 구성 하 여 PBX와 통신

사용자에 게 원격 통화 제어 기능을 제공 하려면 해당 환경에서 Lync 서버와 기존 개인 분기 교환 (PBX)에 연결할 수 있는 SIP/CSTA 게이트웨이를 하나 이상 설치 해야 합니다. SIP/CSTA 게이트웨이는 SIP와 컴퓨터에서 지 원하는 텔레커뮤니케이션 응용 프로그램 (CSTA) 간의 게이트웨이입니다. 게이트웨이를 여러 개 설치 하 든 둘 중 하나를 설치할지에 관계 없이 각 사용자는 하나의 게이트웨이 또는 PBX를 사용 하 여 구성할 수 있습니다. 기존 PBX에 SIP/CSTA 인터페이스가 없으면 독점 PBX 공급자별 신호 프로토콜에 대 한 지원을 포함 하 여 PBX를 지원할 수 있는 SIP/CSTA 게이트웨이를 배포 해야 합니다. 기능에 대 한 자세한 내용은 각 공급 업체를 직접 참조 하세요.

원격 통화 제어를 위해 Lync Server와 통합할 수 있는 SIP/CSTA 게이트웨이를 배포할 준비가 되 면 다음 정보에 대해 게이트웨이에 필요한 구문에 대 한 게이트웨이 공급 업체나 공급 업체의 게이트웨이 문서를 참조 하세요.

  - 게이트웨이의 회선 서버 URI

  - 게이트웨이에 할당 되는 사용자의 회선 URI

앞의 설정이 사용자 구성 중에 필요 하며, 게이트웨이에 올바르게 라우팅하고 연결 하는 데 필요한 대로 게이트웨이가 지정 되어야 합니다.

의 Microsoft 통합 커뮤니케이션에서 상호 운용성 프로그램 웹 사이트를 통해 공급 업체를 [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)참조할 수 있습니다.

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>2 단계: CSTA 요청을 SIP/CSTA 게이트웨이로 라우팅하도록 Lync Server 구성

원격 통화 제어 요청을 라우팅할 배포의 모든 SIP/CSTA 게이트웨이의 대상 주소 (서버 URI)에 대 한 고정 경로를 Lync Server 풀에 만들어야 합니다. 또한 각 대상 주소에 해당 하는 신뢰할 수 있는 응용 프로그램 항목을 만들어야 합니다. 게이트웨이를 신뢰할 수 있는 응용 프로그램으로 지정 하면 타사에서 개발 하는 경우에도 Lync Server 환경의 일부로 실행할 신뢰할 수 있는 상태가 지정 되 고 제품의 기본 제공 부분이 아닌 서비스 이므로 *외부 서비스로* 참조 되는 항목을 실행 합니다. 마지막으로 Lync Server가 TLS (전송 계층 보안) 연결 대신 TCP (전송 제어 프로토콜) 연결을 사용 하 여 SIP/CSTA 게이트웨이에 연결 하는 경우 토폴로지 작성기를 사용 하 여 게이트웨이 IP 주소도 정의 해야 합니다.

고정 경로를 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 원격 통화 제어에 대 한 고정 경로 구성을](lync-server-2013-configure-a-static-route-for-remote-call-control.md)참조 하세요.

신뢰할 수 있는 응용 프로그램 항목을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 원격 통화 제어에 대해 신뢰할 수 있는 응용 프로그램 항목 구성을](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)참조 하세요

토폴로지 작성기에서 SIP/CSTA 게이트웨이 IP 주소를 정의 하는 방법에 대 한 자세한 내용은 [Lync 서버 2013에서 sip/CSTA 게이트웨이 ip 주소 정의](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)를 참조 하세요.

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>3 단계: 원격 통화 제어를 위해 Lync 사용자 구성

Lync Server에 대해 사용자를 설정한 후에는 Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 원격 통화 제어에 사용 하도록 설정할 수 있습니다. 이 배포 단계에서는 각 사용자에 게 회선 서버 URI와 줄 URI를 할당 합니다. 줄 서버 URI는 사용자에 게 할당할 SIP/CSTA 게이트웨이의 SIP URI입니다. 줄 URI는 사용자에 게 할당 된 고유 전화 번호입니다.

원격 통화 제어를 위해 사용자를 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 lync 사용자를 위한 원격 통화 제어 사용](lync-server-2013-enable-lync-users-for-remote-call-control.md)을 참조 하세요.

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>4 단계: Lync Server 전화 번호 정규화 규칙 정의

원격 통화 제어 시나리오에서 Lync Server는 전화 번호 정규화 규칙을 사용 하 여 수신 하는 전화 번호를 SIP/CSTA 게이트웨이에서 E-164 형식으로 변환 합니다. 전화 번호는 특정 원격 통화 제어 기능이 제대로 작동 하려면이 표준화 된 형식 이어야 합니다. 원격 통화 제어는 주소록 서비스 전화 번호 정규화에 대해 구성 하는 것과 동일한 전화 번호 정규화 규칙을 사용 하 여 Enterprise Voice에 사용 되는 전화 번호 정규화 규칙과는 다릅니다.

원격 통화 제어에서 전화 번호 정규화 규칙을 사용 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 원격 통화 제어 및 전화 번호 정규화](lync-server-2013-remote-call-control-and-phone-number-normalization.md)를 참조 하세요. 주소록 서비스에 대 한 전화 번호 정규화 규칙에 대 한 자세한 내용은 운영 설명서의 [Lync Server 2013에서 주소록 서비스 관리](lync-server-2013-administering-the-address-book-service.md) 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

