---
title: 'Lync Server 2013: 네트워크 어댑터 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network adapters
ms:assetid: 6519ed80-020f-47a3-851c-03dea5eac5d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429707(v=OCS.15)
ms:contentKeyID: 48184320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30889a6b145e7256a313c4deedafc74d99499719
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-adapters-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 어댑터 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-07_

하나 이상의 IP 주소를 외부 네트워크 어댑터 및 하나 이상의 IP 주소에 내부 네트워크 어댑터에 할당 해야 합니다.

다음 절차에서 Forefront TMG (위협 관리 게이트웨이) 2010 또는 Internet Information Server 응용 프로그램 요청 라우팅 중 하나를 실행 하는 서버에는 두 개의 네트워크 어댑터가 있습니다.

  - 웹 사이트 (일반적으로 인터넷을 통해)에 연결 하려고 하는 클라이언트에 대 한 공용 또는 외부 네트워크 어댑터

  - 웹 서비스를 호스팅하는 Lync Server를 실행 하는 내부 서버의 개인 또는 내부 네트워크 인터페이스입니다.

<div>


> [!IMPORTANT]  
> Edge 서버와 유사 하 게, 외부 네트워크 어댑터에만 기본 게이트웨이를 설정할 수 있습니다. 기본 게이트웨이는 트래픽을 인터넷에 연결 하는 라우터 또는 외부 방화벽의 IP 주소를 말합니다. 역방향 프록시에서 내부 네트워크 어댑터에서 향하는 트래픽에 대해 웹 게시 규칙에서 참조 하는 서버가 포함 된 모든 서브넷에 대해 영구 고정 경로 (예: Windows Server의 경로 명령)를 사용 해야 합니다. 영구 경로를 설정 하면 컴퓨터가 라우터가 되지 않습니다. IP 전달을 사용할 수 없는 경우 컴퓨터는 다른 네트워크로 향하는 특정 트래픽만 적절 한 인터페이스로 작동 하는 것입니다. 이는 본질적으로 두 게이트웨이를 외부 네트워크를 가리키는 기본으로 설정 하 고, 내부 인터페이스로 전송 되는 트래픽과 라우터 또는 다른 네트워크에 연결할 수 있습니다.<BR>그러나 네트워크 라우터가 경로를 요약 하도록 구성 된 경우 모든 서브넷에 대해 영구 경로 만들기가 필요 하지 않을 수 있습니다. 라우터가 정의 된 네트워크에 대 한 영구 경로를 만들고 기본 게이트웨이로 라우터를 사용 합니다. 네트워크를 구성 하는 방법을 잘 모르는 경우, 만들어야 할 영구 경로에 대 한 지침이 필요한 경우 회사의 네트워크 엔지니어에 게 문의 하세요.<BR>역방향 프록시는 웹 게시 규칙에 사용 되는 내부 디렉터 또는 프런트 엔드 서버 및 다음 홉 풀 Fqdn에 대 한 DNS 호스트 (A) 레코드를 확인할 수 있어야 합니다. Edge 서버와 마찬가지로 보안상의 이유로, 역방향 프록시를 구성 하 여 내부 네트워크에 있는 DNS 서버를 사용 하는 것이 좋습니다. 즉, 경계에 DNS 서버가 필요 하거나 이러한 각 Fqdn을 서버의 내부 IP 주소로 확인 하는 호스트 파일 항목이 리버스 프록시에 필요 합니다.



</div>

<div>

## <a name="to-configure-the-network-adapter-cards-on-the-reverse-proxy-computer"></a>역방향 프록시 컴퓨터에서 네트워크 어댑터 카드를 구성 하려면

1.  리버스 프록시로 실행 되는 Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 또는 Windows Server 2012 R2 서버에서 **시작**을 클릭 하 고 **제어판**을 가리킨 다음 **네트워크 및 공유 센터**를 클릭 하 고 **어댑터 설정 변경을**클릭 하 여 **어댑터 설정 변경을** 엽니다.

2.  외부 인터페이스에 사용할 외부 네트워크 연결을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

3.  **속성** 페이지에서 **네트워킹** 탭을 클릭 하 고 **이 연결에 다음 항목 사용** 목록에서 **인터넷 프로토콜 버전 4 (tcp/ip)** 를 클릭 한 다음 **속성**을 클릭 합니다.

4.  **인터넷 프로토콜 (tcp/ip) 속성** 페이지에서 네트워크 어댑터가 연결 된 네트워크 서브넷에 대해 IP 주소를 적절 하 게 구성 합니다.
    
    <div>
    

    > [!NOTE]  
    > 역방향 프록시를 HTTPS/TCP/443을 사용 하는 다른 응용 프로그램에서 이미 사용 하 고 있는 경우 Outlook Web Access 게시와 같은 경우에는 다른 IP 주소를 추가 하 여 기존 규칙 및 웹 수신기를 방해 하지 않고, HTTPS/TCP/443에 Lync Server 2013 웹 서비스를 게시 하거나, 기존 인증서를 대체 하 여 새 외부 FQDN 이름을 주체 대체 이름에 추가 하는 것으로 변경 해야 합니다.

    
    </div>

5.  **확인**을 클릭 한 다음 **확인**을 클릭 합니다.

6.  **네트워크 연결**에서 내부 인터페이스에 사용할 내부 네트워크 연결을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

7.  3 ~ 5 단계를 반복 하 여 내부 네트워크 연결을 구성 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

