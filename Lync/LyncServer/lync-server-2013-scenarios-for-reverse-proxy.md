---
title: 'Lync Server 2013: 역방향 프록시에 대 한 시나리오'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82d5874393e69083ee7058e4e737d21a2fe865ad
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013의 역방향 프록시에 대 한 시나리오

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-21_

Lync Server 2013에는 모임 및 전화 접속 단순 Url, 주소록, 모임 콘텐츠, 메일 그룹 확장, 모바일 서비스 등의 서비스 및 리소스에 대 한 액세스 권한을 제공 하기 위해 역방향 프록시가 필요 합니다. Lync Server 2013의 일반적인 역방향 프록시 시나리오는 디렉터 또는 프런트 엔드 서버 외부 웹 서비스에 대 한 외부 클라이언트 (예: 데스크톱 클라이언트 또는 Lync Web App 클라이언트) 액세스를 허용 하는 것입니다.

**역방향 프록시 및 외부 웹 서비스**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

계획 단계 중에 Lync Server 2013 배포의 역방향 프록시에 대 한 요구 사항을 정의 합니다. 역방향 프록시를 사용 하면 다음 외부 클라이언트의 기능에 액세스할 수 있습니다.

  - Microsoft Lync 2013 데스크톱 클라이언트

  - Microsoft Lync Web App

  - Microsoft Lync 모바일

  - Lync Windows 스토어 앱

Lync Server 2013 배포를 계획할 때는 Lync Server 2013에 대 한 실제 요구 사항을 역방향 프록시 기능에 매핑합니다.

1.  외부 클라이언트는 TCP 443 포트의 역방향 프록시에 연결 되 고 SSL (secure sockets layer) 또는 TLS (전송 계층 보안)를 사용 합니다. Microsoft Lync 모바일 클라이언트는 TCP 80 포트에 연결할 수 있지만, Lync 검색 서비스에 대 한 초기 연결을 수행 하 고 관리자가 적절 한 DNS (domain name system) CNAME (또는 별칭) 레코드를 구성한 경우에만이 통신은 암호화 되지 않습니다.

2.  Lync Server 2013 external web services (프런트 엔드 서버 및/또는 디렉터에 배포 됨)는 TCP 4443 포트의 역방향 프록시 연결을 기대 하며 연결이 SSL/TLS가 될 것으로 예상 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 외부 웹 서비스에 대해 제안 되는 기본 수신 대기 포트는 HTTP 트래픽의 경우 TCP 8080이 고 HTTPS 트래픽의 경우 TCP 4443입니다. 토폴로지 작성기를 통해 기본 설정을 재정의 하 고 외부 웹 서비스에 대해 자체 수신 대기 포트를 정의할 수 있습니다. 역방향 프록시는 외부 웹 서비스와 통신 하 고 외부 클라이언트는 역방향 프록시와 통신 한다는 점에 유의 해야 합니다. 외부 클라이언트는 포트 TCP 443의 역방향 프록시와 통신 하지만 역방향 프록시가 외부 웹 서비스와 통신 하는 포트를 다시 정의할 수 있습니다. 토폴로지 작성기의 옵션을 사용 하 여 웹 서비스의 기본 수신 대기 포트를 재정의 하면 인프라에서 발생할 수 있는 수신 대기 포트 충돌을 해결할 수 있습니다.

    
    </div>

3.  Lync Server 2013 외부 웹 서비스는 클라이언트에서 수정 되지 않은 호스트 헤더가 클라이언트에서 사용 하려는 서비스 및 웹 서버 디렉터리를 식별 하는 데 필요 합니다. 요청이 역방향 프록시에서 보낸 것 처럼 표시 되어야 함

4.  외부 웹 서비스는 클라이언트에 제공 되는 서비스를 제공 하는 정의 된 vDir (웹 서버 가상 디렉터리)을 사용 합니다. 특정 외부에서 식별할 수 있는 웹 서비스는 다음과 같습니다.
    
      - 웹 전화 회의에 대 한 vDir "모임"
    
      - 전화 액세스 및 전화 회의에 대 한 "전화 접속" vDir
    
      - Lync Windows 스토어 앱, Lync Mobile 및 데스크톱 클라이언트 Lync 2013에 대 한 "자동 검색" vDir Lync Server 2013의 자동 검색은 DNS 이름 "lyncdiscover"에서 알 수 있습니다.
    
      - 정의 되지 않은 서비스는 외부 웹 서비스를 직접 호출 하 여 외부 클라이언트에서 액세스 합니다. 예를 들어 DLX (메일 그룹 확장) 및 ABS (주소록 서비스)에는 외부 웹 서비스 및 관련 vDirs에 대 한 직접 호출을 통해 액세스 합니다. 클라이언트는 vDir의 실제 경로를 알고 있으며이 정보를 기반으로 하 여 URL (uniform record locator)을 생성 합니다. 클라이언트는 다음과 비슷한 URL을 사용 하 여 주소록 서비스에 액세스 합니다.`https://externalweb.contoso.com/abs/handler`
    
      - Lync Server 토폴로지의 일부로 회의를 정의 하 고 구성 하는 경우 Office Web Apps 서버
        
        <div>
        

        > [!NOTE]  
        > Office Web Apps 서버는 별도의 역할 서버 이며, 외부 웹 서비스의 일부로 구성 되지 않습니다. 이 서버는 클라이언트 액세스를 위해 별도로 게시 됩니다.

        
        </div>

5.  각 서비스에 대해 SSL 브리징을 정의 합니다. 외부 포트 TCP 443이 TCP 4443의 외부 웹 서비스 포트에 매핑됩니다. 암호화 되지 않은 HTTP의 경우 tcp 80 포트가 외부 웹 서비스 포트 TCP 8080에 매핑됩니다.

6.  웹 서버 리소스를 게시 하는 역방향 프록시 수신기 계획

7.  제공 될 서비스를 기반으로 역방향 프록시에 대 한 인증서를 요청 하 고 구성 합니다. 올바른 주체 대체 이름으로 구성 된 경우이 인증서는 역방향 프록시 서버의 구성 된 모든 수신기에서 공유할 수 있습니다.

역방향 프록시 배포 계획 시 사용 가능한 리소스

  - [Lync Server 2013의 데이터 수집](lync-server-2013-data-collection.md)

  - [인증서 요약-Lync Server 2013의 역방향 프록시](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [포트 요약-Lync Server 2013의 역방향 프록시](lync-server-2013-port-summary-reverse-proxy.md)

  - [Lync Server 2013의 DNS 요약-역방향 프록시](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

