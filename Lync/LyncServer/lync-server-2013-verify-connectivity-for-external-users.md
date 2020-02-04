---
title: 'Lync Server 2013: 외부 사용자에 대한 연결 확인'
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
ms.openlocfilehash: 1c1f8a9bbda54c596a9ccae8451b15ce7300bffd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>Lync Server 2013에서 외부 사용자에 대한 연결 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

외부 사용자에 대 한 연결의 유효성을 검사 하려면 액세스에 지 서비스에 대 한 서버 및 포트에 대 한 사용자 연결을 보장 해야 합니다.

구성을 확인 하 고 외부 사용자 액세스가 필요한 시나리오에 대 한 올바른 메시지를 보내고 받을 수 있는 유용한 리소스는 원격 연결 분석기 사이트 (<http://www.testocsconnectivity.com>)입니다. 이 사이트는 Microsoft Support에서 관리 및 관리 합니다. 원격 연결 분석기에 연결 하려면 브라우저에서 웹 사이트를 열고 지침에 따라 시나리오를 선택 합니다.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>외부 사용자 및 외부 액세스 연결 테스트

외부 사용자 액세스에 대 한 테스트에는 조직에서 지 원하는 각 외부 사용자 유형이 포함 되며 다음 중 일부 또는 모두를 포함 해야 합니다.

  - 하나 이상의 페더레이션 도메인에서 사용자를 확인 하 고 IM, 현재 상태, A/V 및 데스크톱 공유를 테스트 합니다.

  - 조직에서 지 원하는 각 공용 IM 서비스 공급자의 사용자 및 프로 비전이 완료 되었습니다.

  - 익명 사용자.

  - 조직 내에서 Lync에 원격으로 로그인 되지만 VPN을 사용 하지 않는 사용자

이러한 테스트는 Edge 서버가 다음과 같은지 여부를 확인 합니다.

  - 네트워크 외부의 텔넷 클라이언트를 사용 하 여 필요한 포트를 수신 대기 합니다.
    
      - 예: telnet sip.contoso.com 443
    
      - 배포에 따라 Edge 서버 또는 Edge 서버 풀에서 사용 하는 포트에서 위의 테스트를 수행 합니다.

  - 정확한 외부 DNS 확인을 수행 합니다.
    
      - 네트워크 외부에서 Edge 또는 Edge 풀의 각 외부 FQDN에 대해 ping을 수행 합니다. Ping이 실패 하는 경우에도 할당 한 IP 주소와 비교할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

