---
title: 'Lync Server 2013: Lync Windows 스토어 앱 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cc1ab2b397111cef1040592f29a11d55e5f1f64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Lync Server 2013에 대 한 lync Windows 스토어 앱 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-12-03_

Lync Server의 온-프레미스 배포를 사용 하는 조직은 Lync Windows 스토어 앱을 지원 하기 위해 다음 요구 사항을 충족 해야 합니다.

<div>


> [!NOTE]  
> Lync server 2010의 경우 lync server 2010에 대 한 누적 업데이트: 2 월 2012 (at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp, kbid = 2670352</A>사용 가능) 이상 또는 이후 모든 서버에서 실행 합니다. 사용자가 모임에 참가할 수 있도록 하려면 서버에서 Lync Server 2010:10 월 2012 (at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp, kbid = 2737915</A>에 사용 가능)에 대 한 누적 업데이트를 실행 합니다.



</div>

  - 서버에서 자동 검색, Lync Web App, 웹 티켓 서비스를 사용 하도록 설정 합니다.

  - 프런트 엔드 서버 또는 프런트 엔드 풀에서 인증서 인증을 사용 하도록 설정 합니다. 프런트 엔드 서버 또는 프런트 엔드 풀의 사용자 등록 프로세스를 레지스트라 라고도 합니다. 자세한 내용은 [Lync Server 2013에서 등록자 구성 설정 만들기](lync-server-2013-create-registrar-configuration-settings.md)를 참조 하세요.

  - 자동 검색 서비스에 대 한 CNAME (DNS 별칭) 리소스 레코드를 게시 합니다.

  - Lync server에 발급 된 인증서의 CDP (인증서 해지 목록)에서 LDAP 리소스 대신 HTTP 리소스를 가리키는지 확인 하는 것은 더 이상 필요 하지 않습니다. 그러나 클라이언트 컴퓨터에 최신 Windows 업데이트가 설치 되어 있는지 확인 합니다.

  - Lync server 관련 HTTP 트래픽을 허용 하도록 엔터프라이즈의 HTTP 프록시를 구성 합니다.필요한 경우 자동 검색, Lync Web App 및 WebTicket 서비스에 대 한 예외를 추가 합니다.

  - 클라이언트에서 여러 도메인을 사용할 때 일반적으로 발생 하는 로그인 문제를 해결 하기 위해 Windows 8.1 및 최신 버전의 Lync Windows 스토어 앱을 설치 합니다 (예: SIP URI가 **userA@domainZ.com** 되지만 Edge 서버는 **sip.domainX.com**).

조직에서 Lync Online 또는 Office 365를 구독 하 고 사용자 고유의 도메인 이름을 사용 하는 경우 Lync 서버의 자동 검색을 위해 네트워크를 설정 하는 몇 가지 추가 단계를 수행 해야 합니다. 모바일 장치에서 Lync Windows 스토어 앱과 Lync에 대 한 네트워크 구성 요구 사항이 동일 합니다. Office 365 위 키 문서에서 "Lync 모바일 장치 설정"에서 사용할 수 있는 "네트워크 설정"의 지침을 따릅니다 [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Lync Windows 스토어 앱 배포](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

