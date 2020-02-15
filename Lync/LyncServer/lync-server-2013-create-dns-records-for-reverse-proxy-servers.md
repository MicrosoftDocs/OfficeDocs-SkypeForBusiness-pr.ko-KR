---
title: 'Lync Server 2013: 역방향 프록시 서버에 대 한 DNS 레코드 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60cd3033ae06f3fd9f0fc4a7a1e881f08f2ee90f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Lync Server 2013에서 역방향 프록시 서버에 대 한 DNS 레코드 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-29_

[Lync server 2013에서에 지 지원에 대 한 DNS 구성](lync-server-2013-configure-dns-for-edge-support.md)에 설명 된 대로 Microsoft 인터넷 보안 및 가속 (ISA) 서버 2006 SP1, Forefront Threat Management Gateway 2010 Server 또는 Internet Information Server 응용 프로그램 요청 라우팅의 공용 외부 인터페이스를 가리키는 외부 DNS A 레코드를 만듭니다. 각 풀, 디렉터 (또는 디렉터 풀) 및 각 단순 URL에 대 한 외부 웹 서비스 Fqdn에 대 한 DNS 레코드가 필요 합니다.

클라이언트의 역방향 프록시 확인을 위한 최소한의 DNS 레코드를 위해 다음 레코드를 만들어야 합니다.

  - 디렉터 및 디렉터 풀에 대해 게시 된 외부 웹 서비스를 정의 하는 호스트 (A) 레코드 (예: **webdirext.contoso.com**)

  - 모든 프런트 엔드 풀 및 Standard Edition 서버 역할 (예: **webext.contoso.com**)에 호스트 되는 외부 웹 서비스에 대해 게시 된 외부 웹 서비스를 정의 하는 호스트 (A) 레코드

  - 단순 URL에 대한 호스트 (A) 레코드(예: **dialin.contoso.com** 및 **meet.contoso.com**)

  - Lync 검색 외부 레코드의 호스트 (A) 레코드 및 Lync 웹 앱, 스케줄러 및 모바일 기능을 비롯 한 모든 웹 응용 프로그램에 대 한 자동 검색에 대 한 포인터 (예: **lyncdiscover.contoso.com**)도 제공 됩니다.

  - Office Web Apps 서버 URL에 대 한 호스트 (A) 레코드 (예: **officewebapp01.contoso.com**)

자세한 내용은 [Lync Server 2013의 DNS 요약-역방향 프록시](lync-server-2013-dns-summary-reverse-proxy.md)를 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

