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
ms.openlocfilehash: 6d192388d03bb96a5d630a230ab4bd35e22c3217
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013의 DNS 인프라 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-08_

Lync Server 2013에는 DNS (Domain Name System)가 필요 하며 다음과 같은 방식으로 사용 됩니다.

  - 서버 간 통신을 위한 내부 서버 또는 풀을 검색 합니다.

  - 클라이언트가 다양 한 SIP 트랜잭션에 사용 되는 프런트 엔드 풀 또는 Standard Edition 서버를 검색할 수 있도록 합니다.

  - 해당 회의를 호스트 하는 서버와 회의를 위한 간단한 Url을 연결 합니다.

  - 외부 서버 및 클라이언트가 Edge 서버에 연결 하거나 인스턴트 메시징 (IM) 또는 회의에 대 한 HTTP 역방향 프록시에 연결할 수 있도록 설정 합니다.

  - 로그인 하지 않은 통합 커뮤니케이션 (UC) 장치를 사용 하도록 설정 하려면 Device Update 웹 서비스를 실행 하는 Standard Edition server를 검색 하 고 업데이트를 얻고 로그를 보냅니다.

  - 사용자가 수동으로 장치 설정에 Url을 입력할 필요 없이 모바일 클라이언트가 웹 서비스 리소스를 자동으로 검색할 수 있도록 합니다.

  - DNS 로드 균형 조정.

<div>


> [!NOTE]  
> Lync Server 2013는 다국어 도메인 이름 (IDNs)을 지원 하지 않습니다.



</div>

<div>


> [!IMPORTANT]  
> 지정하는 이름은 서버에 구성된 컴퓨터 이름과 동일해야 합니다. 기본적으로 도메인에 연결 되지 않은 컴퓨터의 컴퓨터 이름은 정식 도메인 이름 (FQDN)이 아닌 짧은 이름입니다. 토폴로지 작성기에서는 짧은 이름이 아닌 FQDN을 사용합니다. 따라서 도메인에 가입 되어 있지 않은 Edge 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성 해야 합니다. Lync Server, Edge 서버 및 풀의 Fqdn을 할당할 때는 표준 문자 (-Z, a-z, 0 – 9, 하이픈 포함) <STRONG>만 사용</STRONG> 합니다. 유니코드 문자나 밑줄은 사용 하지 마세요. FQDN의 비표준 문자는 외부 DNS 및 공개 Ca (즉 FQDN을 인증서의 SN에 할당 해야 하는 경우)에서 지원 되지 않는 경우가 많습니다.



</div>

</div>

<span> </span>

</div>

</div>

</div>

