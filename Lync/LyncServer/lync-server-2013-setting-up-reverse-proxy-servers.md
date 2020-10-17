---
title: 'Lync Server 2013: 역방향 프록시 서버 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 640d8e97cf8b7a31e11cb2dc8f1b1394e4b1aae3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521815"
---
# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Lync Server 2013에 대 한 역방향 프록시 서버 설정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-08_

Microsoft Lync Server 2013에 지 서버 배포의 경우 외부 클라이언트가 디렉터 및 사용자의 홈 풀에서 Lync Server 2013 웹 서비스 (Office Communications Server의 *웹 구성 요소* )에 액세스 하려면 경계 네트워크의 HTTPS 역방향 프록시를 사용 해야 합니다. 다음은 역방향 프록시를 통한 외부 액세스가 필요한 몇 가지 기능입니다.

  - 외부 사용자가 모임의 모임 콘텐츠를 다운로드할 수 있도록 설정

  - 원격 사용자가 메일 그룹을 확장할 수 있도록 설정

  - 원격 사용자가 주소록 서비스에서 파일을 다운로드할 수 있도록 설정

  - Lync Web App 클라이언트 액세스

  - 전화 접속 회의 설정 웹 페이지 액세스

  - 외부 장치에서 장치 업데이트 웹 서비스에 연결하여 업데이트를 받을 수 있도록 설정

  - 모바일 응용 프로그램이 인터넷에서 이동성 (Mcx) Url을 자동으로 검색 하 고 사용할 수 있도록 설정

  - Lync 2013 클라이언트, Lync Windows 스토어 앱 및 Lync 2013 모바일 클라이언트를 사용 하 여 Lync 검색 (자동 검색) Url을 찾고 통합 커뮤니케이션 웹 API (c)를 사용 하도록 설정 합니다.

모든 풀에서 모든 웹 서비스를 게시하려면 HTTP 역방향 프록시를 구성하는 것이 좋습니다. 게시 https://ExternalFQDN/ \* 풀에 대 한 모든 IIS 가상 디렉터리를 게시 합니다. 조직의 각 Standard Edition 서버, 프런트 엔드 풀 또는 디렉터/디렉터 풀에 대해 게시 규칙이 하나 필요합니다.

또한 단순 URL도 게시해야 합니다. 조직에 디렉터 또는 디렉터 풀이 있는 경우 HTTP 역방향 프록시는 단순 URL에 대한 HTTP/HTTPS 요청을 수신하고 이를 디렉터 또는 디렉터 풀에 있는 외부 웹 서비스 가상 디렉터리에 프록시합니다. 디렉터를 배포하지 않은 경우에는 단순 URL에 대한 요청을 처리하는 풀 하나를 지정해야 합니다. 이 풀이 사용자 홈 풀이 아닌 경우에는 사용자 홈 풀의 웹 서비스로 리디렉션됩니다. 단순 URL은 전용 웹 게시 규칙을 통해 처리할 수도 있고, 디렉터에 대한 웹 게시 규칙의 공용 이름에 추가할 수도 있습니다. 외부 자동 검색 서비스 URL도 게시 해야 합니다.

Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and 가속도 (ISA) Server 2006 SP1 또는 IIS ARR (응용 프로그램 요청 라우팅)을 사용 하는 Internet Information Server 7.0, 7.5 또는 8.0을 역방향 프록시로 사용할 수 있습니다. 이 섹션의 자세한 단계는 Forefront Threat Management Gateway 2010를 구성 하는 방법과 ISA Server 2006을 구성 하는 단계는 거의 동일 합니다. IIS ARR에 대 한 지침도 제공 됩니다. 다른 역방향 프록시를 사용 하는 경우 해당 제품에 대 한 설명서를 참조 하 고 여기에 정의 된 요구 사항을 다른 역방향 프록시의 관련 기능에 매핑합니다.

<div>


> [!IMPORTANT]  
> Internet Information Server 응용 프로그램 요청 라우팅 (IIS ARR)은 Lync Server 2010 및 Lync Server 2013에 대 한 역방향 프록시를 구현 하기 위해 완벽 하 게 테스트 되 고 지원 되는 옵션입니다. 11 월, 2012, Microsoft는 ForeFront Threat Management Gateway 2010 또는 TMG의 라이선스 판매량을 더 이상 사용 하지 않습니다. TMG은 여전히 완벽 하 게 지원 되는 제품 이므로 타사에서 판매 하는 기기의 판매에도 사용할 수 있습니다. 또한 많은 타사 하드웨어 부하 분산 장치 및 방화벽은 역방향 프록시 지원을 제공 합니다. 역방향 프록시 기능을 제공 하는 하드웨어 부하 분산 장치 및 방화벽의 경우 Lync Server에 대 한 역방향 프록시 지원을 제공 하도록 제품을 구성 하는 방법에 대 한 구체적인 지침을 공급 업체에 문의 하십시오. 제품에 대 한 설명서를 Microsoft에 제출한 타사도 볼 수 있습니다. 지원은 해당 솔루션의 타사에서 제공 합니다. 솔루션 제공에서 활성 상태인 제 3 자를 보려면 <A href="https://go.microsoft.com/fwlink/?linkid=268730">Microsoft Lync에 대 한 인프라 자격이</A>있는지 확인 하세요.



</div>

다음 항목 및 절차에서는 배포 및 구성 절차의 기반으로 Forefront Threat Management Gateway 2010 및 IIS ARR을 사용 합니다.

  - [Lync Server 2013에 대 한 웹 팜 Fqdn 구성](lync-server-2013-configure-web-farm-fqdns.md)

  - [Lync Server 2013에서 네트워크 어댑터 구성](lync-server-2013-configure-network-adapters.md)

  - [Lync Server 2013에서 역방향 HTTP 프록시에 대 한 인증서 요청 및 구성](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Lync Server 2013의 단일 내부 풀에 대 한 웹 게시 규칙 구성](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Lync Server 2013의 IIS 가상 디렉터리에 대 한 인증 및 인증 확인 또는 구성](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Lync Server 2013에서 역방향 프록시 서버에 대 한 DNS 레코드 만들기](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Lync Server 2013에서 역방향 프록시를 통해 액세스 확인](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>시작하기 전에

Forefront Threat Management Gateway 2010을 역방향 프록시로 올바르게 배포하려면 Forefront Threat Management Gateway 2010 설명서에 정의되어 있는 필수 구성 요소 및 하드웨어 요구 사항에 따라 서버를 설치 및 구성해야 합니다. 계속 진행 하기 전에 하드웨어를 올바르게 구성 하 고 서버에 Forefront Threat Management 게이트웨이 2010을 설치 하려면 다음 항목을 참조 하십시오.

  - <span></span>  
    [Forefront TMG(Threat Management Gateway) 2010](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Forefront TMG 2010 하드웨어 권장 사항](https://go.microsoft.com/fwlink/?linkid=291293)

IIS ARR을 역방향 프록시로 배포 하려면 다음 항목을 검토 하 여 하드웨어 및 필수 구성 요소 소프트웨어를 구성 합니다.

  - <span></span>  
    Windows Server 2008 또는 Windows Server 2008 r 2에 IIS를 설치 하려면 [Windows server 2008 또는 Windows server 2008 r 2에서 iis 7 설치](https://go.microsoft.com/fwlink/?linkid=291296) 를 참조 하세요.

  - <span></span>  
    Windows Server 2012에 IIS를 설치 하려면 [Windows server 2012에 iis 8 설치](https://go.microsoft.com/fwlink/?linkid=291297) 를 참조 하세요.

  - <span></span>  
    Windows Server 2012 r 2에 IIS를 설치 하려면 [Windows server 2012 r 2에 iis 8.5 설치](https://go.microsoft.com/fwlink/?linkid=330687) 를 참조 하세요.

  - <span></span>  
    IIS 용 응용 프로그램 요청 라우팅 확장을 다운로드 하려면 [응용 프로그램 요청 라우팅 v 2.5 다운로드](https://go.microsoft.com/fwlink/?linkid=291298) 의 지침을 따르세요.

  - <span></span>  
    [응용 프로그램 요청 라우팅 버전 2 설치](https://go.microsoft.com/fwlink/?linkid=291299) 의 지침에 대해 ARR을 설치 하려면
    
    <div>
    

    > [!NOTE]  
    > 현재 게시 된 지침은 ARR 2.0에 대 한 것입니다. 확장 설치의 경우 두 버전에 차이가 없습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

