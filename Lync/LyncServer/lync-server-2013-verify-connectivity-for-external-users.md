---
title: 'Lync Server 2013: 외부 사용자에 대 한 연결 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89f1721967ec693556fecd12d31f45b9b3d108d4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>Lync Server 2013에서 외부 사용자에 대 한 연결 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

외부 사용자의 연결 유효성을 검사하려면 액세스 에지 서비스에 대해 사용자로부터 서버 및 포트로의 연결을 확인해야 합니다.

구성을 확인 하 고, 외부 사용자 액세스에 필요한 시나리오에 대해 올바른 메시지를 보내고 받을 수 있는 기능을 구성 하는 데 유용한 리소스로는 원격 연결 분석기 사이트 (<http://www.testocsconnectivity.com>)가 있습니다. 이 사이트는 Microsoft 지원 서비스에 의해 관리 및 유지 관리 됩니다. 원격 연결 분석기에 연결하려면 브라우저에서 웹 사이트를 열고 지침에 따라 시나리오를 선택합니다.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>외부 사용자 및 외부 액세스 연결 테스트

외부 사용자 액세스 테스트에는 다음 중 일부 또는 모든 항목을 비롯하여 조직에서 지원하는 각 외부 사용자 유형이 포함되어야 합니다.

  - 하나 이상의 페더레이션 도메인, 테스트 IM, 현재 상태, A/V 및 데스크톱 공유에 속한 사용자

  - 조직에서 지원하며 구축이 완료된 각 공용 IM 서비스 공급자의 사용자

  - 익명 사용자

  - Lync에 원격으로 로그인했으나 VPN을 사용하지는 않는 조직 내의 사용자

이러한 테스트에서는 에지 서버에 대해 다음 사항을 확인합니다.

  - 네트워크 외부의 텔넷 클라이언트를 사용하여 필요한 포트를 수신 대기하는지 여부
    
      - 예: telnet sip.contoso.com 443
    
      - 배포에 따라 에지 서버 또는 에지 서버 풀에서 사용 중인 포트에 대해 위의 테스트를 수행합니다.

  - 정확한 외부 DNS 확인을 수행하는지 여부
    
      - 네트워크 외부에서 에지 또는 에지 풀의 각 FQDN에 대해 네트워크 ping을 수행합니다. ping이 실패해도 IP 주소는 표시되므로 지정한 주소와 비교할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

