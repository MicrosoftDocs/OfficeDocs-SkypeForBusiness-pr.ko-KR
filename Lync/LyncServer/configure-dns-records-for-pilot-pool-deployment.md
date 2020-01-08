---
title: 파일럿 풀 배포를 위한 DNS 레코드 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07d10612a5dd4eb1a61523a662eddebfa33a7209
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40984743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a>파일럿 풀 배포를 위한 DNS 레코드 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-29_

Lync Server 2013 파일럿 풀을 배포 하기 전에 파일럿 풀에 대 한 DNS 호스트 항목을 업데이트 해야 합니다. 이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 서버나 도메인에 로그온 해야 합니다.

**DNS 호스트 A 레코드를 구성 하려면**

1.  DNS (도메인 이름 시스템) 서버에서 **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **DNS**를 클릭 합니다.

2.  도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013을 설치할 도메인을 마우스 오른쪽 단추로 클릭 합니다.

3.  **새 호스트 (A 또는 AAAA)** 를 클릭 합니다.

4.  **이름을**클릭 하 고 Lync Server 2013 풀의 호스트 이름을 입력 합니다 (해당 레코드가 정의 되어 있고 A 레코드의 일부로 입력할 필요가 없는 영역에서 도메인 이름을 가정).

5.  **Ip 주소**를 클릭 하 고 프런트 엔드 풀의 ip 주소를 입력 합니다.

6.  **호스트 추가**를 클릭 한 다음 **확인**을 클릭 합니다.

7.  마쳤으면 **완료**를 클릭 합니다.

</div>

<span> </span>

</div>

</div>

</div>

