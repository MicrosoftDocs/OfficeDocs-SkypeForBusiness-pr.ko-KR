---
title: 'Lync Server 2013: DNS SRV 레코드 만들기 및 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f56b2c406a14a6a1781705017d13d8b823472c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Lync Server 2013에서 DNS SRV 레코드 만들기 및 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

이 절차를 성공적으로 완료하려면 서버 또는 도메인에 최소한 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.

이 항목에서는 Lync Server 2013 배포에 필요 하 고 자동 클라이언트 로그인에 필요한 DNS (Domain Name System) 레코드를 구성 하는 방법을 설명 합니다. 프런트 엔드 풀을 만들 때 설치 프로그램은 풀 FQDN (정규화 된 도메인 이름)을 포함 하 여 풀에 대 한 Active Directory 개체 및 설정을 만듭니다. Standard Edition 서버에 대 한 유사한 개체 및 설정이 만들어집니다. 클라이언트가 풀 또는 Standard Edition 서버에 연결할 수 있으려면 풀 또는 Standard Edition 서버의 FQDN이 DNS에 등록 되어 있어야 합니다. 모든 SIP 도메인에 대해 내부 DNS에 DNS SRV 레코드를 만들어야 합니다. 이 절차에서는 내부 DNS에 SIP 사용자 도메인의 영역이 있다고 가정합니다.

<div>

## <a name="to-configure-a-dns-srv-record"></a>DNS SRV 레코드를 구성하려면

1.  DNS 서버에서 **시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.

2.  SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013을 설치할 SIP 도메인을 마우스 오른쪽 단추로 클릭 합니다.

3.  **다른 새 레코드**를 클릭합니다.

4.  **리소스 레코드 종류 선택**에서 **서비스 위치(SRV)** 를 클릭한 다음 **레코드 만들기**를 클릭합니다.

5.  **서비스**를 클릭 한 다음 ** \_sipinternaltls**를 입력 합니다.

6.  **프로토콜**을 클릭 한 다음 ** \_tcp**를 입력 합니다.

7.  **포트 번호**를 클릭한 다음 **5061**을 입력합니다.

8.  **이 서비스를 제공**하는 호스트를 클릭 하 고 풀 또는 Standard EDITION 서버의 FQDN을 입력 합니다.

9.  **확인**을 클릭한 다음 **완료**를 클릭합니다.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>DNS SRV 레코드의 생성을 확인하려면

1.  Authenticated Users 그룹의 구성원이거나 이와 동일한 권한을 가진 계정을 사용하여 도메인의 클라이언트 컴퓨터에 로그온합니다.

2.  **시작**을 클릭한 다음 **실행**을 클릭합니다.

3.  **열기** 상자에 **cmd**를 입력한 다음 **확인**을 클릭합니다.

4.  명령 프롬프트에서 **nslookup**을 입력한 다음 Enter 키를 누릅니다.

5.  **set type=srv**를 입력한 다음 Enter 키를 누릅니다.

6.  ** \_Sipinternaltls를 입력\_ 합니다. tcp.contoso.com**를 입력 한 다음 enter 키를 누릅니다. TLS(전송 계층 보안) 레코드에 대해 표시되는 결과는 다음과 같습니다.
    
    서버: \<\>contoso.com
    
    주소: \<DNS 서버의 IP 주소\>
    
    Non-authoritative answer:
    
    \_sipinternaltls. \_tcp.contoso.com SRV 서비스 위치:
    
    우선 순위 = 0
    
    가중치 = 0
    
    포트 = 5061
    
    offhostname = poolname.contoso.com (또는 Standard Edition server A record)
    
    poolname.contoso.com internet address = \<하나의\> Enterprise Edition server \<\> 또는 \<Standard edition server의 ip 주소를 하나만 사용 하는 풀에 대 한 단일 enterprise edition 서버의 부하 분산 또는 ip 주소에 대 한 가상 IP 주소\>

7.  작업이 끝나면 명령 프롬프트에서 **exit**를 입력한 다음 Enter 키를 누릅니다.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>프런트 엔드 풀 또는 Standard Edition 서버의 FQDN을 확인할 수 있는지 확인하려면

1.  도메인의 클라이언트 컴퓨터에 로그온합니다.

2.  **시작**을 클릭한 다음 **실행**을 클릭합니다.

3.  **열기** 상자에 **cmd**를 입력한 다음 **확인**을 클릭합니다.

4.  명령 프롬프트에 프런트 엔드 풀 **** \<\> 의 nslookup fqdn 또는 \<Standard Edition 서버의\>FQDN을 입력 한 다음 enter 키를 누릅니다.

5.  FQDN에 대해 적절한 IP 주소로 확인되는 응답이 수신되는지 확인합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

