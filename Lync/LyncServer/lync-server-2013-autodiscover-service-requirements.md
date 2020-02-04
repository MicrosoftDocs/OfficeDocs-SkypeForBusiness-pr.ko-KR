---
title: 'Lync Server 2013: 자동 검색 서비스 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 777d70b20a51e5408fe9d9248028c3dbcaebeba2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Lync Server 2013에 대한 자동 검색 서비스 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-25_

Microsoft Lync Server 2013 자동 검색 서비스는 디렉터 및 프런트 엔드 풀 서버에서 실행 되며 DNS에 게시 되는 경우 Lync Mobile을 실행 하는 모바일 장치에서 모바일 서비스를 찾기 위해 사용할 수 있습니다. Lync Mobile을 실행 하는 모바일 장치에서 자동 검색 기능을 활용할 수 있으려면 우선 검색 서비스를 실행 하는 모든 디렉터 및 프런트 엔드 서버에서 인증서 주체 대체 이름 목록을 수정 해야 합니다. 또한 역방향 프록시에서 외부 웹 서비스 게시 규칙에 사용 되는 인증서의 주체 대체 이름 목록을 수정 해야 할 수 있습니다.

디렉터, 프런트 엔드 서버 및 역방향 프록시에 필요한 주체 대체 이름 항목에 대 한 자세한 내용은 모바일 기능 계획에서 [Lync Server 2013의 모바일 기능에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-mobility.md) 참조 하세요.

리버스 프록시에서 주체 대체 이름 목록을 사용 하는 것에 대 한 결정은 포트 80 또는 포트 443에 자동 검색 서비스를 게시할지 여부에 따라 달라 집니다.

  - **포트 80**   에 게시 된 자동 검색 서비스에 대 한 초기 쿼리가 포트 80를 통해 발생 하는 경우 인증서 변경이 필요 하지 않습니다. Lync를 실행 하는 모바일 장치는 포트 80의 역방향 프록시에 액세스 한 다음 내부적으로 포트 8080의 디렉터 또는 프런트 엔드 서버로 리디렉션되 때문입니다. 자세한 내용은이 항목의 뒷부분에 나오는 "포트 80를 사용 하 여 초기 자동 검색 프로세스" 섹션을 참조 하세요.

  - **포트 443**   에 게시 됨 외부 웹 서비스 게시 규칙에 사용 되는 인증서의 주체 대체 이름 목록에는 *lyncdiscover을\< 포함 해야 합니다. 조직\> * 내 각 SIP 도메인에 대 한 sipdomain 항목.

내부 인증 기관을 사용 하 여 인증서를 재발급 하는 것은 일반적으로 간단한 프로세스 이지만, 웹 서비스 게시 규칙에 사용 되는 공개 인증서의 경우 여러 주체의 대체 이름 항목을 추가 하는 데 많은 비용이 듭니다. 이 문제를 해결 하려면 포트 80을 통한 초기 자동 검색 연결을 지원 하 고, 그런 다음 디렉터 또는 프런트 엔드 서버의 포트 8080로 리디렉션됩니다.

예를 들어 Lync Mobile을 실행 하는 모바일 클라이언트가 초기 요청에 대해 HTTP를 사용 하 여 자동 검색 기능을 사용 하 여 Lync Server 2013에 로그인 하도록 구성 되어 있다고 가정 합니다.

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>포트 80를 사용 하는 모바일 장치에 대 한 초기 자동 검색 프로세스

1.  Lync Mobile을 실행 하는 모바일 장치가 DNS를 사용 하 여 A 레코드가 있는 lyncdiscover.contoso.com을 찾습니다.

2.  외부 DNS는 외부 웹 서비스의 IP 주소를 클라이언트에 반환 합니다.

3.  Lync Mobile을 실행 하는 모바일 http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com 장치가 리버스 프록시로 요청을 보냅니다.

4.  웹 게시 규칙은 포트 80에서 내부적으로 포트 8080로 요청을 연결 하 고, 그 후에는 디렉터 또는 프런트 엔드 서버로 라우팅합니다.
    
    요청이 HTTP이 고 HTTPS가 아니기 때문에 자동 검색 서비스를 지원 하기 위해 외부 웹 서비스 게시 규칙의 인증서에 대 한 수정이 필요 하지 않습니다.

5.  자동 검색 서비스는 외부 웹 서비스 Url (HTTPS 형식)을 반환 합니다.

6.  그러면 Lync Mobile을 실행 하는 모바일 장치에서 포트 443의 역방향 프록시에 다시 연결할 수 있으며, 사용자의 홈 풀에서 실행 되는 모바일 서비스로 4443을 통해 리디렉션됩니다.
    
    HTTPS 쿼리는 외부 웹 서비스 URL 및 자동 검색 서비스 URL에 대 한 것 이기 때문에, 인증서에는 외부 웹 서비스의 정규화 된 도메인 이름 (Fqdn)에 대 한 주체 대체 이름 항목이 이미 포함 되어 있기 때문에 성공적으로 수행 됩니다.
    
    이 시나리오에서는 이동성을 지 원하는 데 필요한 인증서 변경이 없습니다.
    
    <div>
    

    > [!NOTE]  
    > 대상 웹 서버에 lyncdiscover.contoso.com에 대 한 일치 하는 값이 없는 인증서가 주체 대체 이름 목록 값으로 표시 되는 경우:<BR>&nbsp;는 "서버 Hello" 및 인증서 없이 응답&nbsp;&nbsp;합니다.<BR>b. Lync mobile을 실행 하는&nbsp;모바일 장치에서 즉시 세션을 종료 합니다.&nbsp;&nbsp;<BR>대상 웹 서버에 lyncdiscover.contoso.com를 주체 대체 이름 목록 값으로 포함 하는 인증서가 있는 경우:<BR>a.&nbsp;&nbsp;&nbsp;웹 서버는 "서버 hello" 및 인증서로 응답 합니다.<BR>b. Lync mobile을 실행 하는&nbsp;모바일 장치에서 인증서의 유효성을 검사 하 고 핸드셰이크를 완료 합니다.&nbsp;&nbsp;

    
    </div>

역방향 프록시 서버에서 포트 80를 사용 하 여 자동 검색 서비스에 대 한 초기 연결을 지원 하기 위해, Forefront Threat Management Gateway 2010 리버스 프록시 웹 게시 규칙에 대해이 예제와 유사한 http 게시 규칙을 만들 수 있습니다.

1.  새 웹 게시 규칙을 만듭니다 (예: **Lync Server 자동 검색 (HTTP)**).

2.  **공개 이름**에 lyncdiscover.contoso.com를 입력 합니다.

3.  **브리징** 탭에서 포트 80에서 포트 8080로의 브리지 요청에 대 한 옵션만 선택 합니다.

4.  **인증** 탭에서 **인증 없음을**선택 하면 **클라이언트가 직접 인증할 수 없습니다**.

5.  변경 내용을 커밋하고 규칙을 Lync 규칙 목록 맨 위로 이동 합니다 (첫 번째 처리 순서).

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>도메인 분할 배포에 대 한 이동성

공유 SIP 주소 공간 ( *분할 도메인*이 라고도 함) 또는 *하이브리드 배포* 는 사용자가 온-프레미스 배포 및 온라인 환경에서 배포 하는 구성입니다. 원하는 결과는 사용자가 홈 서버의 위치 (온-프레미스 또는 온라인)에 관계 없이 배포에 로그인 하 고 해당 홈 서버 위치로 리디렉션되도록 하는 것입니다. 이를 위해 Microsoft Lync Server 2013의 자동 검색 기능은 온라인 사용자를 온라인 토폴로지로 리디렉션하는 데 사용 됩니다. 이 작업은 Lync Server 관리 셸 및 cmdlet **Get-cshostingprovider** 및 **Set/cshostingprovider**를 사용 하 여 URL 자동 검색을 구성 하 여 수행 됩니다.

다음과 같은 배포 된 특성을 수집 하 여 기록해 야 합니다.

  - Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Get-CsHostingProvider

  - 결과에서 **Proxyfqdn**특성이 있는 온라인 공급자를 찾습니다. 예를 들어 sipfed.online.lync.com

  - ProxyFQDN의 값을 기록 합니다.

  - 온라인 공급자와 페더레이션 할 수 있도록 온-프레미스 Lync Server 제어판에서 페더레이션 사용

  - 온라인 공급자에 대해 페더레이션을 사용 하도록 설정 합니다. 기본적으로 모든 온라인 사용자는 도메인 페더레이션에 대해 사용 하도록 설정 되어 있으며 모든 도메인과 통신할 수 있습니다.

  - 차단 되 고 허용 된 도메인을 정의 하는 경우 명시적으로 허용 하거나 차단 하는 도메인을 결정 합니다.

  - 온라인 페더레이션의 경우 방화벽 예외, 인증서 및 DNS 호스트 (IPv6을 사용 하는 경우 A 또는 AAAA) 레코드를 계획 해야 합니다. 또한 페더레이션 정책을 구성 해야 합니다. 자세한 내용은 [Lync server 2013 및 Office Communications server federation에 대 한 계획](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md) 을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

