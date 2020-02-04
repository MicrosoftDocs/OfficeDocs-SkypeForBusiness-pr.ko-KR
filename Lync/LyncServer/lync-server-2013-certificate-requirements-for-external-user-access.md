---
title: 'Lync Server 2013: 외부 사용자 액세스에 대한 인증서 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b6495dbad5350f94873099985922f1adc198f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Lync Server 2013의 외부 사용자 액세스에 대한 인증서 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-03-29_

Microsoft Lync Server 2013 통신 소프트웨어는 access 및 웹 회의에 지 외부 인터페이스와 A/V 인증 서비스에 대 한 단일 공용 인증서의 사용을 지원 합니다. Edge 내부 인터페이스는 일반적으로 내부 CA (인증 기관)에서 발급 하는 개인 인증서를 사용 하지만, 신뢰할 수 있는 공용 CA에서 온 것으로 제공 되는 경우 공용 인증서를 사용할 수도 있습니다. 배포의 리버스 프록시는 공용 인증서를 사용 하 고 역방향 프록시에서 클라이언트로의 통신과 HTTP (HTTP를 통한 전송 계층 보안)를 사용 하 여 내부 서버에 대 한 역방향 프록시를 암호화 합니다.

다음은 access 및 웹 회의에 사용 되는 공용 인증서와 A/V 인증 서비스에 대 한 요구 사항입니다.

  - 인증서는 주체 대체 이름을 지 원하는 승인 된 공개 CA에 의해 발급 되어야 합니다. 자세한 내용은 Microsoft 기술 자료 문서 929395, "Exchange Server 및 통신 서버용 통합 커뮤니케이션 인증서 파트너"를 참조 [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)하세요.

  - Edge 풀에서 인증서를 사용 하는 경우에는 edge 풀의 각 Edge 서버에서 동일한 인증서를 사용 하 여 내보낼 수 있는 것으로 만들어야 합니다. 내보낼 수 있는 개인 키 요구 사항은 풀의 모든 Edge 서버에서 동일한 개인 키를 사용 해야 하는 A/V 인증 서비스의 목적에 대 한 것입니다.

  - 오디오/비디오 서비스의 가동 시간을 최대화 하려면 분리 된 A/V Edge 서비스 인증서를 구현 하기 위한 인증서 요구 사항 (즉, 다른 외부 Edge 인증서 용도를 사용 하는 별도의 A/V Edge 서비스 인증서)을 검토 합니다. 자세한 내용은 Edge Server 계획, lync [server 2013의 Edge 서버 인증서에 대 한 계획](lync-server-2013-plan-for-edge-server-certificates.md) , lync server [2013 using-롤에서 CsCertificate의 OAuth 인증서 및 준비 AV](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)의 대/소문자를 사용 [하는 Lync server 2013의 변경 내용을](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)참조 하세요.

  - 인증서의 주체 이름은 액세스 경계 서비스 외부 인터페이스 FQDN (정규화 된 도메인 이름) 또는 하드웨어 부하 분산 장치 VIP (예: access.contoso.com)입니다. ). 제목 이름에는 와일드 카드 문자를 사용할 수 없으며, 이름을 명시적으로 사용 해야 합니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013의 경우에는 더 이상 요구 사항이 아니지만 Office Communications Server와의 호환성을 유지 하는 것이 좋습니다.

    
    </div>

  - 주체 대체 이름 목록에는 다음의 Fqdn이 포함 됩니다.
    
      - 액세스에 지 서비스 외부 인터페이스 또는 하드웨어 부하 분산 장치 VIP (예: sip.contoso.com)
        
        <div>
        

        > [!NOTE]  
        > 인증서 주체 이름이 액세스에 지 FQDN과 동일 하더라도 TLS (전송 계층 보안)에서 주체 이름을 무시 하 고 주체 대체 이름 항목을 사용 하므로 주체 대체 이름에 액세스에 지 FQDN도 포함 해야 합니다. 유효성.

        
        </div>
    
      - 웹 회의에 지 외부 인터페이스 또는 하드웨어 부하 분산 장치 VIP (예: webcon.contoso.com)
    
      - 클라이언트 자동 구성 또는 페더레이션을 사용 하는 경우 회사 내에서 사용 되는 모든 SIP 도메인 Fqdn (예: sip.contoso.com, sip.fabrikam.com)도 포함 합니다.
    
      - A/V Edge 서비스는 주체 이름 또는 주체 대체 이름 항목을 사용 하지 않습니다.
    
    <div>
    

    > [!NOTE]  
    > 주체 대체 이름 목록의 Fqdn 순서는 중요 하지 않습니다.

    
    </div>

사이트에 부하 분산 된 여러 대의 Edge 서버를 배포 하는 경우 각 Edge 서버에 설치 된 A/V 인증 서비스 인증서가 같은 CA에 있어야 하 고 동일한 개인 키를 사용 해야 합니다. 한 Edge 서버 또는 다 수의 Edge 서버에서 사용 하는지 여부에 관계 없이 인증서의 개인 키를 내보낼 수 있어야 한다는 점에 유의 하세요. Edge 서버 이외의 컴퓨터에서 인증서를 요청 하는 경우에도 내보낼 수 있어야 합니다. A/V 인증 서비스는 주체 이름 또는 주체 대체 이름을 사용 하지 않으므로 액세스 가장자리에 대 한 주체 이름 및 주체 대체 이름 요구 사항이 충족 되 고 웹 회의 가장자리와 인증서의 개인 키를 내보낼 수 있는 동안에는 액세스에 지 인증서를 다시 사용 하는 것이 좋습니다.

Edge 내부 인터페이스에 사용 되는 개인 (또는 공용) 인증서에 대 한 요구 사항은 다음과 같습니다.

  - 인증서는 내부 CA 또는 승인 된 공개 인증서 CA에 의해 발급 될 수 있습니다.

  - 인증서의 주체 이름은 일반적으로 Edge 내부 인터페이스 FQDN 또는 하드웨어 부하 분산 장치 VIP (예: lsedge.contoso.com)입니다. 그러나 Edge 내부에서 와일드 카드 인증서를 사용할 수 있습니다.

  - 주체 대체 이름 목록이 필요 하지 않습니다.

배포 서비스의 리버스 프록시는 다음에 대 한 요청을 수행 합니다.

  - 모임 콘텐츠에 대 한 외부 사용자 액세스

  - 메일 그룹 구성원을 확장 하 고 표시 하는 외부 사용자 액세스

  - 주소록 서비스에서 다운로드 가능한 파일에 대 한 외부 사용자 액세스

  - Lync Web App 클라이언트에 대 한 외부 사용자 액세스

  - 전화 접속 회의 설정 웹 페이지에 대 한 외부 사용자 액세스

  - 위치 정보 서비스에 대 한 외부 사용자 액세스

  - 장치 업데이트 서비스에 대 한 외부 장치 액세스 및 업데이트 받기

역방향 프록시는 내부 서버 웹 구성 요소 Url을 게시 합니다. 웹 구성 요소 Url은 디렉터, 프런트 엔드 서버 또는 프런트 엔드 풀에서 토폴로지 작성기의 **외부 웹 서비스로** 정의 됩니다.

와일드 카드 항목은 리버스 프록시에 할당 된 인증서의 주체 대체 이름 필드에서 지원 됩니다. 리버스 프록시에 대 한 인증서 요청을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 역방향 HTTP 프록시에 대 한 인증서 요청 및 구성을](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)참조 하세요.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 와일드카드 인증서 지원](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

