---
title: 'Lync Server 2013: 원격 통화 제어에 대 한 배포 작업'
description: 'Lync Server 2013: 원격 통화 제어에 대 한 배포 작업입니다.'
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
ms.openlocfilehash: 61d0d57489bd93d7e6ce0209c605f05a2417bded
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553584"
---
# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013의 원격 통화 제어에 대 한 배포 작업

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-05_

이 항목에서는 Lync Server 환경에서 사용자에 대 한 원격 통화 제어를 사용 하도록 설정 하기 위해 수행 해야 하는 배포 작업에 대해 설명 합니다.

<div>


> [!NOTE]  
> Microsoft Office Communicator 2007 r 2의 원격 통화 제어를 위해 이전에 사용 하도록 설정한 사용자를 마이그레이션하는 경우에는이 항목에서 설명 하는 원격 통화 제어 배포 작업을 수행 하기 전에 추가 배포 작업을 수행 해야 합니다. Lync Server로의 마이그레이션 프로세스 중에는 적절 한 Office Communications Server 2007 R2 관리 도구를 사용 하 여 신뢰할 수 있는 응용 프로그램 항목 (이전에는 <EM>권한이 부여 된 호스트 항목</EM>으로 알려진)을 제거 해야 합니다.<BR>권한이 부여 된 호스트를 제거 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy 공인 host in a Lync Server 2013 (optional)</A>을 참조 하십시오.



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>1단계: PBX와 통신할 SIP/CSTA 게이트웨이 설치 및 구성

사용자에 게 원격 통화 제어 기능을 제공 하기 위해 해당 환경의 Lync Server 및 기존 PBX (private branch exchange) 둘 다에 연결할 수 있는 SIP/CSTA 게이트웨이를 하나 이상 설치 해야 합니다. SIP/CSTA 게이트웨이는 SIP와 CSTA(Computer-Supported Telecommunications Application) 사이에 있는 게이트웨이입니다. 게이트웨이를 여러 개 설치하든 하나만 설치하든 관계없이 하나의 게이트웨이 또는 PBX만 사용하여 각 사용자를 구성할 수 있습니다. 기존 PBX에 SIP/CSTA 인터페이스가 없는 경우에는 소유 PBX 공급업체별 신호 프로토콜에 대한 지원을 포함하여 PBX를 지원할 수 있는 SIP/CSTA 게이트웨이를 배포해야 합니다. 기능에 대한 자세한 내용은 각 공급업체에 직접 문의하십시오.

원격 통화 제어를 위해 Lync Server와 통합할 수 있는 SIP/CSTA 게이트웨이를 배포할 준비가 되 면 게이트웨이 공급 업체나 공급 업체의 게이트웨이 설명서에서 다음 정보에 대 한 게이트웨이에 필요한 구문을 참조 하세요.

  - 게이트웨이의 회선 서버 URI

  - 게이트웨이에 할당할 사용자에 대한 줄 URI

위 설정은 사용자 구성 중에 필요하며, 게이트웨이에서 예상대로 지정해야 PBX를 올바르게 라우팅하고 연결할 수 있습니다.

의 Microsoft 통합 통신 오픈 상호 운용성 프로그램 웹 사이트에서 공급 업체를 참조할 수 있습니다 [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) .

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>2 단계: CSTA 요청을 SIP/CSTA 게이트웨이로 라우팅하도록 Lync Server 구성

원격 통화 제어 요청을 라우팅할 배포에 있는 모든 SIP/CSTA 게이트웨이의 대상 주소 (서버 URI)에 대 한 고정 경로를 Lync Server 풀에 만들어야 합니다. 또한 각 대상 주소에 해당하는 신뢰할 수 있는 응용 프로그램 항목을 만들어야 합니다. 게이트웨이를 신뢰할 수 있는 응용 프로그램으로 지정 하는 경우, 타사에서 개발 하는 경우에도 신뢰할 수 있는 상태가 Lync Server 환경의 일부로 실행 되도록 지정 되며,이는 제품의 기본 제공 부분이 아닌 서비스 이기 때문에 *외부 서비스로* 참조 되는 것으로 간주 됩니다. 마지막으로 Lync Server에서 TLS (전송 계층 보안) 연결 대신 TCP (전송 제어 프로토콜) 연결을 사용 하 여 SIP/CSTA 게이트웨이에 연결 하는 경우 토폴로지 작성기를 사용 하 여 게이트웨이 IP 주소도 정의 해야 합니다.

고정 경로를 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 원격 통화 제어에 대 한 고정 경로 구성을](lync-server-2013-configure-a-static-route-for-remote-call-control.md)참조 하십시오.

신뢰할 수 있는 응용 프로그램 항목 구성에 대 한 자세한 내용은 [Lync Server 2013에서 원격 통화 제어에 대 한 신뢰할 수 있는 응용 프로그램 항목 구성을](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)참조 하십시오.

토폴로지 작성기에서 SIP/CSTA 게이트웨이 IP 주소를 정의 하는 방법에 대 한 자세한 내용은 [Define a sip/CSTA GATEWAY ip address in a Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)을 참조 하십시오.

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>3 단계: 원격 통화 제어에 대 한 Lync 사용자 구성

Lync Server를 사용 하도록 설정한 후 Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 원격 통화 제어에 대해 사용자를 사용 하도록 설정할 수 있습니다. 각 사용자에 게 줄 서버 URI와 줄 URI를 할당 하는이 배포 단계 중에 수행 됩니다. 회선 서버 URI는 사용자에 게 할당할 SIP/CSTA 게이트웨이의 SIP URI입니다. 줄 URI는 사용자에 게 할당 되는 고유한 전화 번호입니다.

원격 통화 제어에 대 한 사용자를 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 lync 사용자에 대 한 원격 통화 제어 사용](lync-server-2013-enable-lync-users-for-remote-call-control.md)을 참조 하십시오.

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>4단계: Lync Server 전화 번호 정규화 규칙 정의

원격 통화 제어 시나리오에서 Lync Server는 전화 번호 정규화 규칙을 사용 하 여 SIP/CSTA 게이트웨이에서 수신 하는 전화 번호를 E. 164 형식으로 변환 합니다. 특정 원격 통화 제어 기능이 제대로 작동 하려면 전화 번호가이 표준화 된 형식 이어야 합니다. 원격 통화 제어는 Enterprise Voice에 사용 되는 전화 번호 정규화 규칙과는 다른, 주소록 서비스 전화 번호 정규화에 대해 구성한 것과 동일한 전화 번호 정규화 규칙을 사용 합니다.

원격 통화 제어에서 전화 번호 정규화 규칙을 사용 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 원격 통화 제어 및 전화 번호 정규화](lync-server-2013-remote-call-control-and-phone-number-normalization.md)를 참조 하세요. 주소록 서비스에 대 한 전화 번호 정규화 규칙에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013의 주소록 서비스 관리](lync-server-2013-administering-the-address-book-service.md) 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

