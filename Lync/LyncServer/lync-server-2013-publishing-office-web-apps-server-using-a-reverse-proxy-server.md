---
title: 역방향 프록시 서버를 사용하여 Office Online Server 게시
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f68ae51dba366282d7d3a5668b1358042a29917
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>리버스 프록시 서버를 사용 하 여 Lync Server 2013에서 Office Web Apps 서버 게시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-25_

외부 사용자 (즉, 조직의 방화벽 외부에서 로그온 하는 사용자)가 Office Web Apps Server PowerPoint 프레젠테이션에 액세스할 수 있도록 하려면 Office Web Apps 서버와 Microsoft Forefront와 같은 역방향 프록시 서버를 사용 해야 합니다. 위협 관리 게이트웨이. 이는 또한 사용자가 웹 사이트 게시 규칙을 만들고 구성 해야 한다는 것을 의미 합니다. 이 규칙은 사용자가 서버에 연결할 수 있도록 하는 데 도움이 됩니다. 외부 사용자에 대 한 액세스를 제공할 필요가 없는 경우에는 웹 사이트 게시 규칙을 구성할 필요가 없습니다.

Forefront Threat Management Gateway에서 웹 사이트 게시 규칙을 구성 하려면 다음 절차를 완료 합니다.

1.  **시작**, **모든 프로그램**, **MICROSOFT Forefront TMG**, **forefront TMG Management**를 차례로 클릭 합니다.

2.  Forefront TMG에서 **방화벽 정책을**마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 가리킨 다음 **웹 사이트 게시 규칙**을 클릭 합니다.

3.  새 웹 게시 규칙 마법사의 **새 웹 게시 규칙 마법사 시작** 페이지에서 **웹 게시 규칙 이름** 상자에 새 규칙의 이름 (예: **Office Web Apps 서버 규칙**)을 입력 하 고 **다음**을 클릭 합니다.

4.  **규칙 동작 지정** 페이지에서 **허용** 을 선택 하 고 **다음**을 클릭 합니다.

5.  **게시 유형** 페이지에서 **단일 웹 사이트 또는 부하 분산 장치 게시** 를 선택 하 고 **다음**을 클릭 합니다.

6.  **서버 연결 보안** 페이지에서 **SSL을 사용 하 여 게시 된 웹 서버 또는 서버 팜에 연결** 을 선택 하 고 **다음**을 클릭 합니다.

7.  **내부 게시 세부 정보** 페이지에서 **내부 사이트 이름** 상자에 Office Web Apps 서버 (예: **officewebapps01.contoso.com**)의 FQDN을 입력 하 고 **다음**을 클릭 합니다. **내부 사이트 이름** 상자에 입력 한 이름은 Office Web Apps Server에 할당 한 인증서의 제목 필드 또는 주체 대체 이름 필드에 나타나야 합니다.

8.  **내부 게시 세부 정보** 페이지에서 ** / ** **경로 (선택 사항)** 상자에 입력 하 고 **다음**을 클릭 합니다. /\* 구문을 사용 하면 사이트에 대 한 모든 폴더와 하위 폴더가 게시 되는 것을 확인할 수 있습니다.

9.  **공개 이름 정보** 페이지에서 다음 **에 대 한 요청 허용** 드롭다운 목록에서 **이 도메인 이름 (아래에 입력)** 을 선택한 다음, 공공 이름 상자에 Office Web Apps 서버의 정규화 된 항목을 입력 합니다. 이 이름은 웹 사이트에 액세스 하는 데 사용 되는 이름 이어야 합니다. 예를 들어 URL http://officewebapps01.contoso.com 을 사용 하 여 사이트에 액세스 한 경우에는 **공용 이름** 상자에 **officewebapps01.contoso.com** 를 입력 해야 합니다.

10. **다음**을 클릭 합니다.

11. **웹 수신기 선택** 페이지에서 **새로 만들기**를 클릭 합니다.

12. 새 웹 수신기 정의 마법사의 **웹 수신기 이름** 상자에 새 웹 수신기의 이름 (예: **SSL**)을 입력 하 고 **다음**을 클릭 합니다.

13. **클라이언트 연결 보안** 페이지에서 **클라이언트와 SSL 보안 연결 필요** 를 선택 하 고 **다음**을 클릭 합니다.

14. **웹 수신기 IP 주소** 페이지에서 **외부**를 선택 하 고 **내부**를 선택한 후 **다음**을 클릭 합니다.

15. **수신기 SSL 인증서** 페이지에서 **이 웹 수신기에 대해 단일 인증서 사용** 을 선택한 다음 **인증서 선택을**클릭 합니다.

16. **인증서 선택** 대화 상자에서이 웹 수신기에 사용할 인증서를 선택한 다음 **선택을**클릭 합니다.

17. **수신기 SSL 인증서** 페이지에서 **다음**을 클릭 합니다.

18. **인증 설정** 페이지의 **클라이언트가 Forefront TMG에 자격 증명을 제공 하는 방법 선택** 드롭다운 목록에서 **인증 안** 됨을 선택 하 고 **다음**을 클릭 합니다.

19. **단일 사인온 설정** 페이지에서 **다음**을 클릭 합니다.

20. **새 웹 수신기 마법사 완료** 페이지에서 사용자가 만든 구성 선택 사항에 대 한 요약을 검토 합니다. 준비가 되 면 **마침을**클릭 합니다.

21. **웹 수신기 선택** 페이지에서 **다음**을 클릭 합니다.

22. **인증 위임** 페이지에서 **위임 없음을 선택 하지만 클라이언트가** **Forefront TMG에서 게시 된 웹 서버 인증을 위해 사용 하는 메서드 선택** 드롭다운 목록에서 직접 인증 하 고 **다음**을 클릭할 수 있습니다.

23. **사용자 집합** 페이지에서 적절 한 사용자 집합이 나열 되어 있는지 확인 합니다. 기본적으로이 사용자 집합은 **모든 사용자** 입니다. **추가** 를 클릭 하 여 정의한 다른 사용자 집합을 추가 합니다. 완료 되 면 **다음**을 클릭 합니다.

24. **새 웹 게시 규칙 마법사 완료** 페이지에서 **마침을**클릭 합니다.

**마침을** 클릭 해도 프로세스가 완료 되었음을 의미 하지는 않습니다. 즉, 새 규칙을 자동으로 적용 하 고 사용 하도록 설정 하지 않습니다. 대신 Forefront TMG 사용자 인터페이스에 표시 되는 **적용** 단추를 클릭 해야 합니다. **구성 변경 설명** **적용** 대화 상자가 표시 되 면을 클릭 합니다. 이 대화 상자에서 **적용** 을 클릭 하 여 새 게시 규칙을 사용 하도록 설정 합니다.

새 규칙을 적용 한 후에는 사용자가 새로운 PowerPoint 프레젠테이션 기능을 사용할 수 있도록 규칙을 약간 수정 해야 합니다. 이렇게 하려면 다음 절차를 수행 합니다.

1.  Forefront TMG에서 새 게시 규칙의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

2.  **속성** 대화 상자의 **받는 사람** 탭에서 **실제 항목 대신 원래 호스트 헤더를 전달**하는 옵션을 선택 합니다.

3.  **트래픽** 탭에서 **필터링** 을 클릭 한 다음 **HTTP 구성을**클릭 합니다.

4.  **규칙에 대 한 HTTP 정책 구성** 대화 상자에서 **정규화 확인** 확인란의 선택을 취소 한 다음 **확인을**클릭 합니다.

5.  **속성** 대화 상자에서 **확인**을 클릭 합니다.

6.  Forefront TMG에서 **적용** 을 클릭 하 여 변경 내용을 활성화 합니다. **구성 변경 설명** 대화 상자가 표시 되 면 **적용**을 클릭 합니다.

설치를 완료 한 후 [Lync server 2013에서 Office Web Apps 서버의 구성 유효성 검사](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)항목에 있는 절차를 사용 하 여 Office Web apps 서버를 테스트할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

