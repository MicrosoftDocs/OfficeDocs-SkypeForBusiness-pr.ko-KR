---
title: 'Lync Server 2013: 리버스 프록시에 대 한 구성 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0367ea79a0f3de6ad716f18aab980e9d9442e148
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013의 리버스 프록시에 대 한 구성 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-05_

Lync Server 2013는 외부 클라이언트로부터 통신에 대 한 몇 가지 요구 사항을 충족 하며,이는 디렉터, 디렉터 풀, 프런트 엔드 서버 또는 프런트 엔드 풀에 호스팅된 외부 웹 서비스로 전달 됩니다. 역방향 프록시는 사용자에 게 회의를 제공 하는 경우에도 Office Web Apps 서버를 게시 하는 책임을 집니다.

<div>


> [!NOTE]  
> Lync Server 2013는 사용 해야 하는 특정 역 프록시를 지정 하지 않습니다. Lync Server 2013는 리버스 프록시가 수행할 수 있어야 하는 작동 요구 사항도 정의 합니다. 일반적으로 인프라에 이미 배포 된 역방향 프록시는 요구 사항을 충족 시킬 수 있습니다.



</div>

<div>

## <a name="reverse-proxy-requirements"></a>리버스 프록시 요구 사항

Lync Server 2013이 리버스 프록시로 예상 하는 기능 작업은 다음과 같습니다.

  - 공개 인증 기관에서 얻은 인증서를 사용 하 여 디렉터, 디렉터 풀, 프런트 엔드 서버 또는 프런트 엔드 풀의 게시 된 외부 웹 서비스에 연결 하 여 구현한 SSL (secure socket layer) 및 TLS (전송 계층 보안)를 사용 합니다. 디렉터 및 프런트 엔드 서버는 하드웨어 부하 분산 장치를 사용 하 여 부하 분산 풀에 있을 수 있습니다.

  - 암호화를 위해 인증서를 사용 하 여 내부 웹 사이트를 게시 하거나, 필요에 따라이를 암호화 하지 않은 상태로 게시할 수 있습니다.

  - 정규화 된 도메인 이름 (FQDN)을 사용 하 여 외부적으로 호스팅되는 웹 사이트를 게시할 수 있습니다.

  - 호스트 된 웹 사이트의 모든 콘텐츠를 게시할 수 있습니다. 기본적으로 대부분의 웹 서버에서 ** / ** 인식 하는이 지시어를 사용 하 여 "웹 서버의 모든 콘텐츠 게시"를 의미 합니다. "가상 디렉터리의 모든 콘텐츠 게시"를 의미 하는 **/Uwca/\*** 와 같은 지시문을 수정할 수도 있습니다.

  - 게시 된 웹 사이트의 콘텐츠를 요청 하는 클라이언트와 SSL (Secure Sockets layer) 및 TLS (전송 계층 보안) 연결이 필요 하도록 구성 해야 합니다.

  - 주체 대체 이름 (SAN) 항목이 있는 인증서를 수락 해야 합니다.

  - 외부 웹 서비스 FQDN이 확인 하는 수신기 또는 인터페이스에 대 한 인증서 바인딩을 허용할 수 있어야 합니다. 수신기 구성은 인터페이스 보다 더 좋습니다. 단일 인터페이스에서 여러 수신기를 구성할 수 있습니다.

  - 호스트 헤더 처리의 구성을 허용 해야 합니다. 요청 클라이언트에서 보낸 원본 호스트 헤더는 역방향 프록시를 통해 수정 되지 않고 투명 하 게 전달 되어야 하는 경우가 많습니다.

  - 외부에서 정의 된 하나의 포트 (예: TCP 443)에서 다른 정의 된 포트로 (예: TCP 4443) SSL 및 TLS 트래픽을 브리징 합니다. 역방향 프록시는 확인 시 패킷을 해독 한 다음 전송 되는 동안 패킷을 reencrypt 수 있습니다.

  - 한 포트 (예: TCP 80)에서 다른 포트로의 암호화 되지 않은 TCP 트래픽 브리징 (예: TCP 8080).

  - NTLM 인증, 허용, 인증, 통과 인증 등의 구성 또는 수락을 허용 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

