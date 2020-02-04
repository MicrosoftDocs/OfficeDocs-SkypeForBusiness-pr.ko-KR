---
title: 'Lync Server 2013: 역방향 프록시 서버 설치'
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
ms.openlocfilehash: fbc6e0aee918d08f47c6df88f91493cd62ae6a3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>Lync Server 2013에 대한 역방향 프록시 서버 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-08_

Microsoft Lync Server 2013 Edge 서버 배포의 경우 외부 클라이언트에서 주변 네트워크의 HTTPS 역방향 프록시를 사용 하 여 디렉터와 사용자의 홈 풀에서 Lync Server 2013 웹 서비스 (Office Communications Server의 *웹 구성 요소* )에 액세스 해야 합니다. 리버스 프록시를 통해 외부 액세스를 필요로 하는 일부 기능에는 다음이 포함 됩니다.

  - 외부 사용자가 모임에 대 한 모임 콘텐츠를 다운로드할 수 있도록 합니다.

  - 외부 사용자가 메일 그룹을 확장할 수 있도록 합니다.

  - 원격 사용자가 주소록 서비스에서 파일을 다운로드할 수 있도록 합니다.

  - Lync Web App 클라이언트에 액세스 합니다.

  - 전화 접속 회의 설정 웹 페이지에 액세스 합니다.

  - 외부 장치에서 장치 업데이트 웹 서비스에 연결 하 고 업데이트를 얻을 수 있도록 합니다.

  - 모바일 응용 프로그램이 인터넷에서 이동성 (Mcx) Url을 자동으로 검색 하 고 사용할 수 있도록 합니다.

  - Lync 2013 클라이언트, Lync Windows 스토어 앱 및 Lync 2013 모바일 클라이언트를 사용 하도록 설정 하 여 Lync 검색 (검색) Url을 찾고 통합 커뮤니케이션 웹 API (c)를 사용 합니다.

모든 풀의 모든 웹 서비스를 게시 하도록 HTTP 역방향 프록시를 구성 하는 것이 좋습니다. Https://ExternalFQDN/게시\* -풀에 대 한 모든 IIS 가상 디렉터리를 게시 합니다. 조직의 각 스탠더드 버전 서버, 프런트 엔드 풀 또는 디렉터 또는 디렉터 풀에 대해 하나의 게시 규칙이 필요 합니다.

또한 간단한 Url을 게시 해야 합니다. 조직에 디렉터 또는 디렉터 풀이 있으면 HTTP 역방향 프록시가 간단한 Url에 대 한 HTTP/HTTPS 요청을 수신 하 고 디렉터 또는 디렉터 풀의 외부 웹 서비스 가상 디렉터리에이를 프록시 합니다. 디렉터를 배포 하지 않은 경우에는 단순 Url에 대 한 요청을 처리 하도록 풀을 하나 지정 해야 합니다. (이 사용자의 홈 풀이 아닌 경우 사용자의 홈 풀에 있는 웹 서비스로 이동 됩니다.) 간단한 Url은 전용 웹 게시 규칙을 통해 처리 되거나, 디렉터에 대 한 웹 게시 규칙의 공개 이름에 추가할 수 있습니다. 외부 자동 검색 서비스 URL도 게시 해야 합니다.

Microsoft Forefront 위협 관리 게이트웨이 2010, Microsoft 인터넷 보안 및 가속 (ISA) Server 2006 SP1 또는 IIS ARR (응용 프로그램 요청 라우팅)을 사용 하는 인터넷 정보 서버 7.0, 7.5 또는 8.0을 리버스 프록시로 사용할 수 있습니다. 이 섹션의 자세한 단계에서는 Forefront Threat Management 게이트웨이 2010를 구성 하는 방법에 대해 설명 하 고 ISA Server 2006를 구성 하는 단계는 거의 동일 합니다. IIS ARR에 대 한 지침도 제공 됩니다. 다른 리버스 프록시를 사용 하는 경우 해당 제품에 대 한 설명서를 참조 하 고 여기에 정의 된 요구 사항을 다른 역방향 프록시의 관련 기능에 매핑하십시오.

<div>


> [!IMPORTANT]  
> 인터넷 정보 서버 응용 프로그램 요청 라우팅 (IIS ARR)은 Lync Server 2010 및 Lync Server 2013에 대 한 리버스 프록시를 구현 하기 위해 완전히 테스트 되 고 지원 되는 옵션입니다. 11 월 2012 일에는 ForeFront Threat Management Gateway 2010 또는 TMG의 Microsoft 멈추는 라이선스 sales가 있습니다. TMG는 완벽 하 게 지원 되는 제품이 며 제 3 자에서 판매한 기기에 대 한 할인 판매를 계속 받을 수 있습니다. 또한 많은 서드 파티 하드웨어 부하 분산 장치 및 방화벽이 리버스 프록시 지원을 제공 합니다. 역방향 프록시 기능을 제공 하는 하드웨어 부하 분산 장치 및 방화벽의 경우, 해당 제품을 구성 하 여 Lync Server에 대 한 리버스 프록시 지원을 제공 하는 방법에 대 한 구체적인 지침이 공급 업체에 문의 하세요. 제품에 대 한 설명서를 Microsoft에 제출한 타사 파티를 볼 수도 있습니다. 지원은 해당 솔루션의 제 3 자에 의해 제공 됩니다. 솔루션을 제공 하는 데 활성 상태인 제 3 자가 표시 되는 경우 <A href="http://go.microsoft.com/fwlink/?linkid=268730">Microsoft Lync의 인프라 적격</A>을 참조 하세요.



</div>

다음 항목 및 절차에서는 배포 및 구성 절차의 기반으로 Forefront Threat Management 게이트웨이 2010 및 IIS ARR을 사용 합니다.

  - [Lync Server 2013에 대한 웹 팜 FQDN 구성](lync-server-2013-configure-web-farm-fqdns.md)

  - [Lync Server 2013에서 네트워크 어댑터 구성](lync-server-2013-configure-network-adapters.md)

  - [Lync Server 2013에서 HTTP 역방향 프록시에 대한 인증서 요청 및 구성](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [Lync Server 2013에서 단일 내부 풀에 대한 웹 게시 규칙 구성](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [Lync Server 2013에서 IIS 가상 디렉터리에 대한 인증 확인 또는 구성](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [Lync Server 2013에서 역방향 프록시 서버에 대한 DNS 레코드 만들기](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [Lync Server 2013에서 역방향 프록시를 통해 액세스 확인](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>시작 하기 전에

Forefront Threat Management Gateway 2010를 리버스 프록시로 성공적으로 배포 하려면 Forefront Threat Management Gateway 2010 설명서에 정의 된 필수 구성 요소 및 하드웨어 요구 사항에 따라 서버를 설정 하 고 구성 해야 합니다. 계속 진행 하기 전에 하드웨어를 올바르게 구성 하 고 서버에 Forefront Threat Management 게이트웨이 2010를 설치 하려면 다음 항목을 참조 하세요.

  - <span></span>  
    [Forefront TMG (위협 관리 게이트웨이) 2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Forefront TMG 2010 하드웨어 권장 사항](http://go.microsoft.com/fwlink/?linkid=291293)

IIS ARR을 리버스 프록시로 성공적으로 배포 하려면 다음 항목을 검토 하 여 하드웨어 및 필수 구성 요소 소프트웨어를 구성 합니다.

  - <span></span>  
    Windows Server 2008 또는 Windows Server 2008 R2에 IIS를 설치 하려면 [Windows server 2008 또는 Windows server 2008 r2에 iis 7 설치](http://go.microsoft.com/fwlink/?linkid=291296) 를 참조 하세요.

  - <span></span>  
    Windows Server 2012에 IIS를 설치 하려면 [Windows server 2012에 iis 8 설치](http://go.microsoft.com/fwlink/?linkid=291297) 를 참조 하세요.

  - <span></span>  
    Windows Server 2012 R2에 IIS를 설치 하려면 [Windows server 2012 r2에 iis 8.5 설치](http://go.microsoft.com/fwlink/?linkid=330687) 를 참조 하세요.

  - <span></span>  
    IIS에 대 한 응용 프로그램 요청 라우팅 확장을 다운로드 하려면 [응용 프로그램 요청 라우팅 v 2.5 다운로드](http://go.microsoft.com/fwlink/?linkid=291298) 의 지침을 따릅니다.

  - <span></span>  
    [설치 프로그램 요청 라우팅 버전 2](http://go.microsoft.com/fwlink/?linkid=291299) 의 지침에 대해 ARR을 설치 하려면
    
    <div>
    

    > [!NOTE]  
    > 현재 게시 된 지침은 ARR 2.0에 대 한 것입니다. 확장을 설치 하는 경우 두 버전 간에 차이가 없습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

