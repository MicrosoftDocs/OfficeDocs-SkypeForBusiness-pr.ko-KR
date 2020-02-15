---
title: 'Lync Server 2013: DNS 인프라 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) infrastructure support
ms:assetid: 37777c16-94ce-436d-b517-bcf53a564513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425850(v=OCS.15)
ms:contentKeyID: 48183878
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 190e0160532ca0ac26ce4f818f260848ea68f0a1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013의 DNS 인프라 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-08_

Lync Server 2013에는 DNS (Domain Name System)가 필요 하며 다음과 같은 방식으로 사용 됩니다.

  - 서버 간 통신을 위한 내부 서버 또는 풀을 검색합니다.

  - 클라이언트가 다양한 SIP 트랜잭션에 사용되는 프런트 엔드 풀 또는 Standard Edition 서버를 검색할 수 있도록 합니다.

  - 회의용 단순 URL을 해당 회의를 호스팅하는 서버에 연결합니다.

  - 외부 서버 및 클라이언트가 IM(인스턴트 메시징) 또는 회의를 위해 에지 서버 또는 HTTP 역방향 프록시에 연결할 수 있도록 합니다.

  - 로그인하지 않은 UC(통합 통신) 장치가 장치 업데이트 웹 서비스를 실행하는 프런트 엔드 풀이나 Standard Edition 서버를 검색하고 업데이트를 가져오고 로그를 보낼 수 있도록 합니다.

  - 사용자가 장치 설정에 URL을 수동으로 입력할 필요 없이 모바일 클라이언트가 웹 서비스 리소스를 자동으로 검색할 수 있도록 합니다.

  - DNS 부하 분산에 사용합니다.

<div>


> [!NOTE]  
> Lync Server 2013는 다국어 도메인 이름 (Idn)을 지원 하지 않습니다.



</div>

<div>


> [!IMPORTANT]  
> 지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다. 기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN(정규화된 이름)이 아닌 짧은 이름입니다. 토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다. 따라서 도메인이 가입되지 않은 에지 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성해야 합니다. Lync Server, 에지 서버 및 풀의 FQDN을 지정할 때는 <STRONG>표준 문자</STRONG>(A-Z, a-z, 0-9 및 하이픈 포함)만 사용하십시오. 유니코드 문자나 밑줄을 사용하지 마십시오. FQDN의 비표준 문자는 외부 DNS 및 공용 CA에서 지원되지 않는 경우가 많습니다(인증서의 SN에 FQDN을 할당해야 하는 경우).



</div>

</div>

<span> </span>

</div>

</div>

</div>

