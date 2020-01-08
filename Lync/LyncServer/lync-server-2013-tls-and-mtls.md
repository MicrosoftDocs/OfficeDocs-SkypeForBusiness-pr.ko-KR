---
title: 'Lync Server 2013: TLS 및 MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 066612f08c61ad1df342b4f2dd9b61ff5a5cc286
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>Lync Server 2013 용 TLS 및 MTLS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-07_

TLS (전송 계층 보안) 및 MTLS (상호 전송 계층 보안) 프로토콜은 인터넷에서 암호화 된 통신과 끝점 인증을 제공 합니다. Microsoft Lync Server 2013에서는 이러한 두 가지 프로토콜을 사용 하 여 신뢰할 수 있는 서버의 네트워크를 만들고 해당 네트워크를 통한 모든 통신이 암호화 되도록 합니다. 서버 간의 모든 SIP 통신은 MTLS를 통해 수행 됩니다. 클라이언트에서 서버로의 SIP 통신은 TLS를 통해 수행 됩니다.

TLS는 클라이언트 소프트웨어를 통해 사용자가 연결 하는 Lync Server 2013 서버를 인증할 수 있도록 합니다. TLS 연결에서는 클라이언트가 서버에서 유효한 인증서를 요청 합니다. 유효 하려면 인증서가 클라이언트에서 신뢰 하는 CA에 의해 발급 되었고 서버의 DNS 이름이 인증서의 DNS 이름과 일치 해야 합니다. 인증서가 유효한 경우 클라이언트는 인증서의 공개 키를 사용 하 여 통신에 사용할 대칭 암호화 키를 암호화 하므로, 인증서의 원래 소유자만 개인 키를 사용 하 여 통신의 콘텐츠를 해독할 수 있습니다. 그 결과, 신뢰할 수 있는 다른 서버 또는 클라이언트는 그 시점부터 연결 되지 않습니다. 이 컨텍스트 내에서 웹 서비스에 사용 되는 SSL (Secure Sockets Layer)을 TLS 기반으로 연결할 수 있습니다.

서버 간 연결은 MTLS 상호 인증을 사용 합니다. MTLS 연결에서 서버가 보낸 메시지와 서버가 상호 신뢰 하는 CA에서 exchange 인증서를 수신 합니다. 인증서는 각 서버의 신분을 서로를 증명 합니다. Lync Server 2013 배포에서 Active Directory 도메인의 모든 구성원이 유효 기간 중에 있고 발급 CA에서 해지 하지 않은 엔터프라이즈 CA에서 발급 한 인증서가 모든 내부 클라이언트 및 서버에서 자동으로 유효한 것으로 간주 됩니다. 해당 도메인의 엔터프라이즈 CA를 신뢰 합니다. 페더레이션된 시나리오에서는 발급 CA를 두 페더레이션 파트너 모두에서 신뢰 해야 합니다. 원하는 경우 각 파트너는 다른 파트너에 의해 해당 CA도 신뢰 하 게 되므로 다른 CA를 사용할 수 있습니다. 이 신뢰는 파트너의 루트 CA 인증서가 신뢰 된 루트 ca에 포함 되거나 두 당사자가 신뢰 하는 타사 CA를 사용 하 여 가장 쉽게 수행할 수 있습니다.

TLS 및 MTLS 도움말을 사용 하 여 도청 및 중간자 공격을 방지할 수 있습니다. 중간자 개입 공격에서 공격자는 두 당사자에 대 한 지식 없이도 공격자의 컴퓨터를 통해 두 네트워크 엔터티 간의 통신을 조정 합니다. TLS 및 Lync Server 2013 신뢰 하는 서버 (토폴로지 작성기에 지정 된 것만 해당)를 지정 하면 공개 키 암호화를 사용 하 여 종단 간 암호화를 사용 하 여 응용 프로그램 계층에서 중간자 공격이 부분적으로 발생할 위험을 줄일 수 있습니다. 두 끝점 간에 공격자는 해당 개인 키가 있는 유효한 신뢰할 수 있는 인증서를 보유 하 고 있으며, 통신을 해독 하기 위해 클라이언트가 통신 하는 서비스의 이름에 발급 해야 합니다. 단, 궁극적으로는 네트워킹 인프라 (이 경우 회사 DNS)를 사용 하 여 최상의 보안 절차를 따라야 합니다. Lync Server 2013에서는 DNS 서버가 도메인 컨트롤러와 글로벌 카탈로그를 신뢰할 수 있는 것과 같은 방식으로 신뢰 되는 것으로 간주 되지만, DNS는 공격자의 서버가 성공적으로 응답 하지 못하도록 하 여 DNS 가로채기 공격에 대 한 보호 수준을 제공 합니다. 위장 이름에 대 한 요청.

다음 그림은 Lync Server 2013에서 MTLS를 사용 하 여 신뢰할 수 있는 서버의 네트워크를 만드는 상위 수준입니다.

**Lync Server 네트워크의 신뢰 된 연결**

![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

