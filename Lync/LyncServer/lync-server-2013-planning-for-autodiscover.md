---
title: 'Lync Server 2013: 자동 검색 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 990e58dc01171001e896b03e5a32fc8175c93b2f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013의 자동 검색 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-16_

Lync server 2010 용 누적 업데이트에는 Lync Server에 대 한 자동 검색이 도입 되었습니다 2011. 이 초기 자동 검색 구현의 기본 목적은 Lync Mobile이 이동성 서비스 (Mcx)를 찾을 수 있도록 하는 것 이었습니다. Lync Server 2013의 자동 검색 서비스는 이제 모든 클라이언트에서 서버 및 사용자 서비스를 찾는 데 사용 하는 서비스입니다. Microsoft Lync Server 2013 자동 검색 서비스는 디렉터 및 프런트 엔드 서버에서 실행 됩니다.

<div>


> [!TIP]  
> 자동 검색 및 클라이언트와 통신 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-understanding-autodiscover.md">Lync Server 2013의 자동 검색 이해</A>를 참조 하십시오.<BR>이동성은 여전히 고유한 시나리오 이며, 모바일 서비스에는 여전히 특별 한 계획이 필요 합니다. 자세한 내용은 <A href="lync-server-2013-planning-for-mobility.md">Lync Server 2013에서 모바일 기능 계획</A>을 참조 하세요.



</div>

Lync Server 2010에 자동 검색이 도입 된 경우 기존 서버 배포에 대 한 잠재적인 인증서 변경이 필요한 서비스를 구현 하기 위해 수행 해야 하는 손상이 있었습니다. 자동 검색은 HTTPS에 대 한 포트 TCP 443 또는 HTTP에 대 한 포트 TCP 80를 통해 사용할 수 있습니다. HTTPS를 사용 하기로 결정 한 경우 필요한 `lyncdiscover.<domain>` 및 `lyncdiscoverinternal.<domain>` DNS 레코드를 수용할 수 있도록 역방향 프록시, 디렉터 및 프런트 엔드 서버의 인증서를 다시 발급 해야 합니다. 결정이 HTTP를 사용 하는 경우에는 DNS CNAME (또는 별칭) 레코드를 사용 하 여 인증서의 기존 이름을 사용 하 여 인증서를 다시 발급 하지 못할 수 있습니다. HTTP를 사용 하는 경우 초기 통신이 암호화 되지 않았음을 의미 합니다.

Lync Server 2013에서는 모든 클라이언트에 자동 검색을 사용 하기 때문에 주요 시나리오는 HTTPS를 독점적으로 사용 하 고 lyncdiscover를 사용 하 여 인증서를 만드는 것입니다. \<역방향\> 프록시, 디렉터 및 프런트 엔드 서버 구성의 일부로 도메인 Lync Server 2010에서 업그레이드 된 배포에 자동 검색을 구현 하는 경우 HTTP를 사용 하 여 인증서를 재발급 하지 않을 수 있습니다. 두 시나리오에 대 한 지침은 다음 섹션에서 제공 됩니다.

<div>


> [!IMPORTANT]  
> 외부 웹 서비스 게시 규칙에서 사용 하는 인증서의 주체 대체 이름 목록에는 <EM>lyncdiscover가 포함&lt; 되어야 합니다. 조직&gt; </EM> 내의 각 SIP 도메인에 대 한 microsoft.rtc.management.xds.sipdomain object 항목 디렉터, 프런트 엔드 서버 및 역방향 프록시에 필요한 주체 대체 이름 항목에 대 한 자세한 내용은 <A href="lync-server-2013-certificate-summary-autodiscover.md">Lync Server 2013의 인증서 요약-자동 검색</A>을 참조 하십시오.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 인증서 요약-자동 검색](lync-server-2013-certificate-summary-autodiscover.md)

  - [포트 요약-Lync Server 2013의 자동 검색](lync-server-2013-port-summary-autodiscover.md)

  - [Lync Server 2013의 DNS 요약-자동 검색](lync-server-2013-dns-summary-autodiscover.md)

  - [Lync Server 2013의 하이브리드 및 분할 도메인 자동 검색](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

