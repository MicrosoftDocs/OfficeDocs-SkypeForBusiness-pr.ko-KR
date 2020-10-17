---
title: DNS SRV 레코드 업데이트
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d45abd1599666079705f3e77b74ac2ba81d9df71
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503515"
---
# <a name="update-dns-srv-records"></a>DNS SRV 레코드 업데이트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-29_

이 절차를 성공적으로 완료하려면 서버 또는 도메인에 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.

이 항목에서는 Lync Server 2013로 마이그레이션한 후 DNS (Domain Name System) 레코드를 업데이트 하는 방법에 대해 설명 합니다. 모든 사용자를 Lync Server 2013로 이동한 후에 레거시 Lync Server 2010 풀 또는 디렉터를 해제 하기 전에 모든 SIP 도메인에 대해 내부 DNS의 DNS SRV 레코드를 업데이트 해야 합니다. 이 절차에서는 내부 DNS에 SIP 사용자 도메인의 영역이 있다고 가정합니다.

**DNS SRV 레코드를 구성하려면**

1.  DNS 서버에서 **시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.

2.  SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 하 고 Lync Server 2013이 설치 된 SIP 도메인을 확장 한 다음 ** \_ tcp** 설정으로 이동 합니다.

3.  오른쪽 창에서 ** \_ sipinternaltls** 를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.

4.  **이 서비스를 제공**하는 호스트에서 Lync Server 2013 풀을 가리키도록 호스트 FQDN을 업데이트 합니다.

5.  **확인**을 클릭합니다.

**프런트 엔드 풀 또는 Standard Edition Server의 FQDN을 확인할 수 있는지 확인하려면**

1.  도메인의 클라이언트 컴퓨터에 로그온합니다.

2.  **시작**을 클릭한 다음 **실행**을 클릭합니다.

3.  **열기** 상자에 **cmd**를 입력한 다음 **확인**을 클릭합니다.

4.  명령 프롬프트에서 **nslookup** \<FQDN of the Front End pool\> 또는을 입력 한 \<FQDN of the Standard Edition server\> 다음 enter 키를 누릅니다.

5.  FQDN에 대해 적절한 IP 주소로 확인되는 응답이 수신되는지 확인합니다.

</div>

<span> </span>

</div>

</div>

</div>

