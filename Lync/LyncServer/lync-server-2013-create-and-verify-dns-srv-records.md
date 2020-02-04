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
ms.openlocfilehash: 8440d2ae91d535c8c4747c923b1b17dda9bb0f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Lync Server 2013에서 DNS SRV 레코드 만들기 및 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 최소한 서버나 도메인에 로그온 해야 합니다.

이 항목에서는 Lync Server 2013 배포에서 만들어야 하는 DNS (Domain Name System) 레코드와 자동 클라이언트가 로그인 하는 데 필요한 사용자를 구성 하는 방법에 대해 설명 합니다. 프런트 엔드 풀을 만들면 설치 프로그램에서 풀의 Active Directory 개체와 설정 (FQDN (정규화 된 도메인 이름) 포함)을 만듭니다. 스탠더드 버전 서버에 대 한 유사한 개체와 설정이 만들어집니다. 클라이언트가 풀 또는 Standard Edition 서버에 연결할 수 있으려면 풀 또는 Standard Edition 서버의 FQDN이 DNS에 등록 되어 있어야 합니다. 모든 SIP 도메인에 대해 내부 DNS에 DNS SRV 레코드를 만들어야 합니다. 이 절차에서는 내부 DNS에 SIP 사용자 도메인에 대 한 영역이 있다고 가정 합니다.

<div>

## <a name="to-configure-a-dns-srv-record"></a>DNS SRV 레코드를 구성 하려면

1.  DNS 서버에서 **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **dns**를 클릭 합니다.

2.  SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013을 설치할 SIP 도메인을 마우스 오른쪽 단추로 클릭 합니다.

3.  **다른 새 레코드**를 클릭 합니다.

4.  **리소스 레코드 종류 선택**에서 **서비스 위치 (SRV)** 를 클릭 한 다음 **레코드 만들기**를 클릭 합니다.

5.  **서비스**를 클릭 한 다음 ** \_sipinternaltls**를 입력 합니다.

6.  **프로토콜**을 클릭 한 다음 ** \_tcp**를 입력 합니다.

7.  **포트 번호**를 클릭 한 다음 **5061**을 입력 합니다.

8.  **이 서비스를 제공**하는 호스트를 클릭 한 다음 풀 또는 Standard EDITION 서버의 FQDN을 입력 합니다.

9.  **확인**을 클릭 한 다음 **완료**를 클릭 합니다.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>DNS SRV 레코드의 생성을 확인 하려면

1.  인증 된 사용자 그룹의 구성원 이거나 동등한 권한이 있는 계정을 사용 하 여 도메인의 클라이언트 컴퓨터에 로그온 합니다.

2.  **시작**을 클릭 한 다음 **실행**을 클릭 합니다.

3.  **열기** 상자에 **cmd**를 입력 한 다음 **확인**을 클릭 합니다.

4.  명령 프롬프트에서 **nslookup**을 입력 한 다음 enter 키를 누릅니다.

5.  **Set type = srv**를 입력 한 다음 enter 키를 누릅니다.

6.  ** \_Sipinternaltls를 입력\_ 합니다. tcp.contoso.com**을 입력 한 다음 enter 키를 누릅니다. TLS (전송 계층 보안) 레코드에 대해 표시 되는 출력은 다음과 같습니다.
    
    서버: \<dns server\>. contoso.com
    
    주소: \<DNS 서버의 IP 주소\>
    
    비 정식 답변:
    
    \_sipinternaltls. \_tcp.contoso.com SRV 서비스 위치:
    
    우선 순위 = 0
    
    weight = 0
    
    port = 5061
    
    poolname.contoso.com (또는 Standard Edition server A 레코드)
    
    poolname.contoso.com internet address = \<하나의\> Enterprise Edition server \<\> 또는 \<Standard edition server의 ip 주소를 포함 하는 풀에 대 한 단일 enterprise edition 서버의 부하 분산 또는 ip 주소에 대 한 가상 IP 주소\>

7.  작업이 완료 되 면 명령 프롬프트에 **exit**를 입력 한 다음 enter 키를 누릅니다.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>프런트 엔드 풀 또는 Standard Edition 서버의 FQDN을 확인할 수 있는지 확인 하려면

1.  도메인의 클라이언트 컴퓨터에 로그온 합니다.

2.  **시작**을 클릭 한 다음 **실행**을 클릭 합니다.

3.  **열기** 상자에 **cmd**를 입력 한 다음 **확인**을 클릭 합니다.

4.  명령 프롬프트에서 프런트 엔드 풀 **** \<\> 의 nslookup fqdn 또는 \<Standard Edition server\>의 fqdn을 입력 한 다음 enter 키를 누릅니다.

5.  FQDN에 대 한 적절 한 IP 주소로 확인 되는 회신을 수신 하 고 있는지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

