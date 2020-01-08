---
title: 'Lync Server 2013: 역방향 프록시에 대한 시나리오'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1621e8bb0241e82f9f4678d4fe39a4f66f6bcf9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013의 역방향 프록시에 대한 시나리오

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-21_

리버스 프록시는 Lync Server 2013에서 모임 및 전화 접속 간단한 Url, 주소록, 모임 콘텐츠, 메일 그룹 확장, 모바일 서비스 등의 서비스 및 리소스에 대 한 액세스를 제공 하는 데 필요 합니다. Lync Server 2013의 일반적인 리버스 프록시 시나리오는 외부 클라이언트 (예: 데스크톱 클라이언트 또는 Lync Web App 클라이언트)에 대 한 디렉터 또는 프런트 엔드 서버 외부 웹 서비스에 대 한 액세스를 허용 하는 것입니다.

**리버스 프록시 및 외부 웹 서비스**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

계획 단계에서 Lync Server 2013 배포의 리버스 프록시에 대 한 요구 사항을 정의 합니다. 리버스 프록시는 다음 외부 클라이언트의 기능에 액세스할 수 있도록 합니다.

  - Microsoft Lync 2013 데스크톱 클라이언트

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Lync Windows 스토어 앱

Lync Server 2013 배포를 계획할 때 Lync Server 2013의 실제 요구 사항을 리버스 프록시 기능에 매핑합니다.

1.  외부 클라이언트는 TCP 443 포트의 역방향 프록시에 연결 되며 SSL (secure socket layer) 또는 TLS (전송 계층 보안)를 사용 합니다. Microsoft Lync 모바일 클라이언트는 포트 TCP 80에 연결할 수 있지만, Lync 검색 서비스에 대 한 초기 연결을 수행할 때와 관리자가 적절 한 DNS (도메인 이름 시스템) CNAME (또는 별칭) 레코드를 구성 하 고이를 허용 합니다. 통신은 암호화 되지 않습니다.

2.  Lync Server 2013 외부 웹 서비스 (프런트 엔드 서버 및/또는 디렉터에 배포 됨)는 포트 TCP 4443의 역방향 프록시에서 연결을 기대 하며, 연결이 SSL/TLS가 되어야 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 외부 웹 서비스에 대해 제안 된 기본 수신 대기 포트는 HTTP 트래픽에 대 한 TCP 8080이 고 HTTPS 트래픽에는 TCP 4443입니다. 토폴로지 작성기는 기본값을 재정의 하 고 외부 웹 서비스에 대 한 수신 대기 포트를 정의할 수 있는 기회를 제공 합니다. 역방향 프록시는 외부 웹 서비스와 통신 하 고 외부 클라이언트는 역방향 프록시와 통신 한다는 점에 유의 해야 합니다. 외부 클라이언트는 포트 TCP 443의 역방향 프록시와 통신 하지만, 역방향 프록시가 외부 웹 서비스와 통신 하는 포트를 재정의할 수 있습니다. 토폴로지 작성기의 옵션을 사용 하 여 웹 서비스의 기본 수신 대기 포트를 재정의 하면 인프라에 발생할 수 있는 수신 대기 포트 충돌을 해결할 수 있습니다.

    
    </div>

3.  Lync Server 2013 외부 웹 서비스는 클라이언트에서 수정 되지 않은 호스트 헤더를 사용 하 여 클라이언트에서 사용할 서비스와 웹 서버 디렉터리를 식별 하는 데 필요한 기능을 제공 합니다. 요청이 역방향 프록시에서 보낸 것 처럼 표시 되어야 합니다.

4.  외부 웹 서비스는 클라이언트에 제공 되는 서비스를 제공 하는 정의 된 웹 서버 가상 디렉터리 (vDir)를 사용 합니다. 특정 외부 식별 가능 웹 서비스:
    
      - 웹 컨퍼런스 모임에 대 한 "모임" vDir
    
      - 전화 액세스 및 전화 회의를 위한 "전화 접속" vDir
    
      - Lync Windows 스토어 앱, Lync Mobile, 데스크톱 클라이언트 Lync 2013에 대 한 "자동 검색" vDir. Lync Server 2013의 자동 검색은 DNS 이름 "lyncdiscover"에서 알 수 있습니다.
    
      - 정의 되지 않은 서비스는 외부 웹 서비스로 직접 전화를 걸어 외부 클라이언트에서 액세스 합니다. 예를 들어, 외부 웹 서비스 및 연결 된 vDirs에 대 한 직접 호출을 통해 메일 그룹 확장 (DLX)과 ABS (주소록 서비스)에 액세스할 수 있습니다. 클라이언트는 vDir의 실제 경로를 인식 하 고이 정보에 따라 URL (uniform record locator) 로케이터를 생성 합니다. 클라이언트는 다음과 유사한 URL을 사용 하 여 주소록 서비스에 액세스 합니다.`https://externalweb.contoso.com/abs/handler`
    
      - Lync Server 토폴로지의 일부로 회의를 정의 하 고 구성 하는 Office Web Apps 서버
        
        <div>
        

        > [!NOTE]  
        > Office Web Apps 서버는 별도의 역할 서버 이며 외부 웹 서비스의 일부로 구성 되지 않습니다. 이 서버는 클라이언트 액세스를 위해 개별적으로 게시 됩니다.

        
        </div>

5.  각 서비스에 대 한 SSL 브리징을 정의 합니다. 외부 포트 TCP 443이 TCP 4443의 외부 웹 서비스 포트에 매핑됩니다. 암호화 되지 않은 HTTP의 경우 포트 TCP 80이 외부 웹 서비스 포트 TCP 8080에 매핑됩니다.

6.  웹 서버 리소스를 게시 하기 위해 리버스 프록시 수신기에 대 한 계획

7.  제공 될 서비스에 따라 역방향 프록시에 대 한 인증서를 요청 하 고 구성 합니다. 올바른 제목 대체 이름을 사용 하 여 구성 하는 경우이 인증서는 역방향 프록시 서버의 구성 된 모든 수신기를 통해 공유할 수 있습니다.

리버스 프록시 배포를 계획 하는 데 사용할 수 있는 리소스:

  - [Lync Server 2013의 데이터 수집](lync-server-2013-data-collection.md)

  - [Lync Server 2013의 인증서 요약 - 역방향 프록시](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Lync Server 2013의 포트 요약 - 역방향 프록시](lync-server-2013-port-summary-reverse-proxy.md)

  - [Lync Server 2013의 DNS 요약 - 역방향 프록시](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

