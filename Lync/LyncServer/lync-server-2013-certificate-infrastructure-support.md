---
title: Lync Server 2013 인증서 인프라 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc8cb5bdad02de4fcb407d7eb27960258a46dd3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013의 인증서 인프라 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-07_

Lync Server 2013에는 TLS (전송 계층 보안) 및 MTLS (상호 TLS) 연결을 지원 하기 위한 PKI (공개 키 인프라)가 필요 합니다. 기본적으로 Lync Server 2013는 클라이언트에서 서버로의 연결에 TLS를 사용 하도록 구성 됩니다. MTLS는 서버 간 연결에 사용 됩니다.

MTLS 인증서는 Lync Server 2013의 신뢰할 수 있는 Ca (인증 기관)에서 발급 해야 합니다. Lync Server는 다음 Ca에서 발급 된 인증서를 지원 합니다.

  - 내부 CA에서 발급 한 인증서:
    
      - Windows Server 2003 운영 체제 CA
    
      - Windows Server 2008 운영 체제 CA
    
      - Windows Server 2008 R2 운영 체제 CA
    
      - Windows Server 2012 운영 체제 CA
    
      - Windows Server 2012 R2 운영 체제 CA

  - 공개 CA에서 발급 한 인증서

Exchange 2013와 같은 다른 응용 프로그램 및 서버와의 통신에는 다른 응용 프로그램 및 제품에서 지원 되는 인증서가 필요 합니다. 2013 릴리스, Lync Server 2013 및 Exchange 2013 및 SharePoint Server를 비롯 한 기타 Microsoft 서버 제품은 서버 간 인증 및 권한 부여를 위한 개방형 권한 부여 (OAuth) 프로토콜을 지원 합니다. 자세한 내용은 배포 설명서 또는 운영 설명서의 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 참조 하세요.

Windows 7 운영 체제, Windows Server 2008 R2 운영 체제 및 Microsoft Office Communicator 2007 Phone Edition을 실행 하는 클라이언트에서 연결 하는 경우 Lync Server 2013에는 SHA-256를 사용 하 여 서명한 인증서에 대 한 지원이 포함 되지만 필요 하지는 않습니다. 암호화 해시 함수 SHA-256를 사용 하 여 외부 액세스를 지원 하기 위해 외부 인증서는 SHA-256를 사용 하 여 공용 CA에서 발급 합니다.

인증서 요구 사항에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에 대 한 인증서 인프라 요구 사항을](lync-server-2013-certificate-infrastructure-requirements.md) 참조 하세요. 인증서와 함께 와일드 카드를 사용 하는 방법에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync Server 2013에서 와일드 카드 인증서 지원](lync-server-2013-wildcard-certificate-support.md) 을 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

