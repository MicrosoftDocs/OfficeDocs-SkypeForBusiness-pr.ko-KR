---
title: 역방향 프록시 서버를 사용 하 여 Office Web Apps 서버 게시
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1d1dae773c96cfa6d16994e5b3c6aec2504b16c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a>역방향 프록시 서버를 사용 하 여 Lync Server 2013에서 Office Web Apps 서버 게시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-25_

외부 사용자(조직 방화벽 외부에서 로그온하는 사용자)가 Office Web Apps PowerPoint 프레젠테이션에 액세스할 수 있도록 하려면 Office Web Apps Server 및 역방향 프록시 서버(예: Microsoft Forefront Threat Management Gateway)를 사용해야 합니다. 즉, 웹 사이트 게시 규칙을 만들고 구성 해야 합니다. 이 규칙은 사용자가 서버에 연결할 수 있도록 하는 데 도움이 됩니다. 외부 사용자에게 액세스 권한을 제공할 필요가 없으면 웹 사이트 게시 규칙을 구성할 필요가 없습니다.

Forefront Threat Management Gateway에서 웹 사이트 게시 규칙을 구성하려면 다음 절차를 완료합니다.

1.  **시작**, **모든 프로그램**, **Microsoft Forefront TMG**, **Forefront TMG 관리**를 차례로 클릭합니다.

2.  Forefront TMG에서 **방화벽 정책**을 마우스 오른쪽 단추로 클릭하고 **새로 만들기**를 가리킨 후에 **웹 사이트 게시 규칙**을 클릭합니다.

3.  웹 게시 규칙 생성 마법사의 **웹 게시 규칙 생성 마법사 시작** 페이지에서 **웹 게시 규칙 이름** 상자에 새 규칙의 이름을 **Office Web Apps Server 규칙**과 같이 입력하고 **다음**을 클릭합니다.

4.  **규칙 동작 지정** 페이지에서 **허용**을 선택한 후 **다음**을 클릭합니다.

5.  **게시 유형** 페이지에서 **단일 웹 사이트 또는 부하 분산 장치 게시**를 선택한 후 **다음**을 클릭합니다.

6.  **서버 연결 보안** 페이지에서 **SSL을 사용하여 게시된 웹 서버 또는 서버 팜에 연결**을 선택한 후 **다음**을 클릭합니다.

7.  **내부 게시 정보** 페이지의 **내부 사이트 이름** 상자에 Office Web Apps Server의 FQDN을 **officewebapps01.contoso.com**과 같이 입력하고 **다음**을 클릭합니다. **내부 사이트 이름** 상자에 입력한 이름은 Office Web Apps Server에 할당한 인증서의 제목 필드 또는 주체 대체 이름 필드에 나타나야 합니다.

8.  **내부 게시 정보** 페이지의 ** / ** **경로 (옵션)** 상자에 다음을 입력 하 고 **다음**을 클릭 합니다. /\* 구문을 통해 사이트의 모든 폴더와 하위 폴더가 게시 되는 것을 확인할 수 있습니다.

9.  **공개 이름 정보** 페이지의 **다음에 대한 요청 허용** 드롭다운 목록에서 **이 도메인 이름(아래에 입력)** 을 선택하고 공개 이름 상자에 Office Web Apps Server의 정규화된 도메인 이름을 입력합니다. 이 이름은 웹 사이트에 액세스하는 데 사용하는 이름이어야 합니다. 예를 들어 URL http://officewebapps01.contoso.com 을 사용 하 여 사이트에 액세스 하는 경우 **공개 이름** 상자에 **officewebapps01.contoso.com** 를 입력 해야 합니다.

10. **다음**을 클릭합니다.

11. **웹 수신기 선택** 페이지에서 **새로 만들기**를 클릭합니다.

12. 새 웹 수신기 정의 마법사의 **웹 수신기 이름** 상자에 새 웹 수신기의 이름을 **SSL**과 같이 입력하고 **다음**을 클릭합니다.

13. **클라이언트 연결 보안** 페이지에서 **클라이언트와의 SSL 보안 연결 필요**를 선택한 다음 **다음**을 클릭합니다.

14. **웹 수신기 IP 주소** 페이지에서 **외부**를 선택하고 **내부**를 선택한 후 **다음**을 클릭합니다.

15. **수신기 SSL 인증서** 페이지에서 **이 웹 수신기에 단일 인증서 사용**을 선택하고 **인증서 선택**을 클릭합니다.

16. **인증서 선택** 대화 상자에서 이 웹 수신기에 사용할 인증서를 선택하고 **선택**을 클릭합니다.

17. **수신기 SSL 인증서** 페이지에서 **다음**을 클릭합니다.

18. **인증 설정** 페이지의 **클라이언트에서 Forefront TMG에 자격 증명을 제공하는 방법 선택** 드롭다운 목록에서 **인증 없음**을 선택한 후 **다음**을 클릭합니다.

19. **Single Sign On 설정** 페이지에서 **다음**을 클릭합니다.

20. **새 웹 수신기 마법사 완료** 페이지에서 선택한 구성의 요약을 검토합니다. 검토를 마친 후 **마침**을 클릭합니다.

21. **웹 수신기 선택** 페이지에서 **다음**을 클릭합니다.

22. **인증 위임** 페이지의 **Forefront TMG에서 게시된 웹 서버의 인증을 받는 데 사용하는 방법 선택** 드롭다운 목록에서 **위임 안 함 - 클라이언트에서 직접 인증**을 선택하고 **다음**을 클릭합니다.

23. **사용자 집합** 페이지에서 적절한 사용자 집합이 나열되어 있는지 확인합니다. 기본적으로 이 집합은 **모든 사용자** 사용자 집합입니다. 정의했을 수 있는 다른 사용자 집합을 추가하려면 **추가**를 클릭합니다. 추가가 완료되면 **다음**을 클릭합니다.

24. **웹 게시 규칙 생성 마법사 완료** 페이지에서 **마침**을 클릭합니다.

**마침**을 클릭해도 프로세스가 완료되는 것은 아니며, 새 규칙이 자동으로 적용 및 사용하도록 설정되지도 않습니다. 대신 Forefront TMG 사용자 인터페이스에 나타나는 **적용** 단추를 클릭해야 합니다. **적용**을 클릭하면 **구성 변경 설명** 대화 상자가 나타납니다. 해당 대화 상자에서 **적용**을 클릭하면 새 게시 규칙이 사용하도록 설정됩니다.

새 규칙을 적용 한 후에는 사용자가 새 PowerPoint 프레젠테이션 기능을 사용할 수 있도록 규칙을 약간 수정 해야 합니다. 이렇게 하려면 다음 절차를 완료합니다.

1.  Forefront TMG에서 새 게시 규칙의 이름을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.

2.  **속성** 대화 상자의 **대상** 탭에서 **실제 호스트 헤더 대신 원래 호스트 헤더 전달** 옵션을 선택합니다.

3.  **트래픽** 탭에서 **필터링**을 클릭하고 **HTTP 구성**을 클릭합니다.

4.  **규칙에 대한 HTTP 정책 구성** 대화 상자에서 **정규화 확인** 확인란 선택을 취소하고 **확인**을 클릭합니다.

5.  **속성** 대화 상자에서 **확인**을 클릭합니다.

6.  Forefront TMG에서 **적용**을 클릭하여 변경 내용을 사용하도록 설정합니다. **구성 변경 설명** 대화 상자가 나타나면 **적용**을 클릭합니다.

설치를 완료 한 후 [Lync Server 2013에서 Office Web Apps 서버의 구성 유효성 검사](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)항목에 나와 있는 절차를 사용 하 여 Office Web apps 서버를 테스트할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

