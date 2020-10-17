---
title: 파일럿 풀 배포에 대한 DNS 레코드 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63348a4e092953beede96a10d109ee5ba23daba4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499535"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a>파일럿 풀 배포에 대한 DNS 레코드 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-24_

Lync Server 2013 파일럿 풀을 배포 하기 전에 파일럿 풀에 대 한 DNS 호스트 항목을 업데이트 해야 합니다. 이 절차를 성공적으로 완료하려면 서버 또는 도메인에 최소한 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 로그온해야 합니다.

**DNS 호스트 A 레코드를 구성하려면**

1.  DNS(Domain Name System) 서버에서 **시작**, **관리 도구**를 차례로 클릭한 다음 **DNS**를 클릭합니다.

2.  도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013을 설치할 도메인을 마우스 오른쪽 단추로 클릭 합니다.

3.  **새 호스트(A 또는 AAAA)** 를 클릭합니다.

4.  **이름**을 클릭하고 풀의 호스트 이름을 입력합니다(도메인 이름은 레코드가 정의된 영역에서 가져온 것으로 가정되며 A 레코드의 일부로 입력할 필요는 없음).

5.  **Ip 주소**를 클릭 하 고 프런트 엔드 풀의 ip 주소를 입력 합니다.

6.  **호스트 추가**를 클릭한 다음 **확인**을 클릭합니다.

7.  작업을 마쳤으면 **완료**를 클릭합니다.

</div>

<span> </span>

</div>

</div>

</div>

