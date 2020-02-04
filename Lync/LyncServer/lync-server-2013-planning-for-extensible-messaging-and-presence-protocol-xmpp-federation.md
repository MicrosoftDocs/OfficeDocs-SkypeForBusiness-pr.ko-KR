---
title: XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ee0543d36cb43a05042ca4341a837ae10b52051
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013에서 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 페더레이션 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

이전 버전의 Lync Server 및 Office Communications Server에서는 XMPP 배포와 페더레이션 할 수 있는 별도의 서버 역할로 배포할 수 있는 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이를 제공 했습니다. Microsoft Lync Server 2013에서 XMPP 기능은 기능으로 배포할 수 있습니다. XMPP 기능은 Edge 서버에서 실행 되는 XMPP 프록시와 프런트 엔드 서버에서 실행 되는 XMPP 게이트웨이 등 두 부분으로 설치 됩니다.

XMPP의 배포 및 구성은 방화벽에서 포트 및 프로토콜 규칙을 정의 하 고, 인증서를 구성 하 고, DNS 레코드를 추가 하 여 조직에서 XMPP를 지원 하도록 계획 하는 [Lync Server 2013에서 외부 사용자 액세스를 배포](lync-server-2013-deploying-external-user-access.md) 하는 데 적용 됩니다. 이 단원의 다음 항목에서는 배포에 대해 XMPP 페더레이션을 성공적으로 계획 하는 데 필요한 정보를 요약 합니다.

<div>


> [!IMPORTANT]
> Google 대화가 포함 된 인스턴트 메시징 페더레이션에 대해 Microsoft에서 Lync Server 2013의 XMPP 기능을 테스트 하 고 지원 합니다. 다른 XMPP 시스템의 경우 타사 공급 업체에 문의 하 여 Lync Server 2013의 페더레이션이 지원 되는지 여부와 배포 또는 문제 해결에 대 한 권장 사항을 확인 합니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [인증서 요약-Lync Server 2013의 XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) 페더레이션](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [포트 요약-Lync Server 2013의 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 페더레이션](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [DNS 요약-Lync Server 2013의 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 페더레이션](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 XMPP 페더레이션 설정](lync-server-2013-setting-up-xmpp-federation.md)  
[Lync Server 2013에서 XMPP 페더레이션 사용자 액세스를 제어하도록 정책 구성](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[Lync Server 2013에서 XMPP 페더레이션 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))  
[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))  
[Get-Csxmpp게이트웨이 구성](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

