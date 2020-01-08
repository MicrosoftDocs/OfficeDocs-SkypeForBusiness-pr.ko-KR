---
title: Office Web Apps 서버에서 작동 하도록 Lync Server 2013 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ba6926af243b15449c5b8baa4b29706a2ec8ade
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>Office Web Apps 서버에서 작동 하도록 Lync Server 2013 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-04-22_

Office Web Apps Server를 사용 하도록 Lync Server 2013를 구성 하려면 먼저 Office Web Apps 서버를 배포 하 고 구성 해야 합니다. 단일 Office Web apps 서버를 설치 하 고 구성 하는 방법에 대 한 자세한 내용 또는 office web apps 서버 팜을 고가용성을 위해 설치 하 고 구성 하는 방법에 대 한 자세한 내용은 **Office Web Apps 서버 및 Office Web apps를 배포 하** 는 문서 가이드를 참조 하세요.

Office Web Apps Server를 성공적으로 설치 하 고 웹 팜을 올바르게 구성한 후에는 새 서버와 통신 하도록 Lync Server를 구성 해야 합니다. 이 작업은 Office Web Apps 서버 검색 URL을 Lync 서버 토폴로지에 추가 하 여 수행 됩니다. 토폴로지에 Office Web Apps 서버를 추가 하려면 다음 단계를 완료 하세요.

1.  **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  **토폴로지 작성기** 대화 상자에서 **기존 배포의 토폴로지 다운로드** 를 선택한 다음 **확인**을 클릭 합니다.

3.  다른 이름 **으로 토폴로지 저장** 대화 상자에서 **파일 이름** 상자에 토폴로지 문서의 이름 (예: **PreWebAppsServerTopology**)을 입력 한 다음 **저장**을 클릭 합니다. 새 토폴로지에서 문제가 발생 하는 경우 나중에이 토폴로지를 검색 하 고 다시 게시할 수 있습니다.

4.  토폴로지 작성기에서 **Lync Server 2013**을 확장 하 고, 사이트 이름을 확장 하 고, **Enterprise Edition 프런트 엔드 풀**을 확장 하 고, 풀 중 하나의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

5.  **속성 편집** 대화 상자의 **일반** 탭에서 **Office Web apps 서버 연결** 제목을 찾은 다음 **새로 만들기** (또는 드롭다운 목록에서 기존 Office Web apps 서버 선택)를 클릭 합니다.

6.  **새 Office Web Apps 서버 정의** 대화 상자에서 office web APPS 서버 **Fqdn** 상자에 office ONLINE server 컴퓨터의 fqdn (정규화 된 도메인 이름)을 입력 합니다. 이렇게 하면 office Web Apps 서버 검색 URL이 **Office Web Apps server 검색 url** 상자에 자동으로 입력 됩니다.
    
    Office Web Apps 서버가 Lync Server 2013와 같은 네트워크 영역에 설치 되어 있는 경우 **외부 네트워크 (즉, 경계/인터넷)에 Office Web Apps 서버를 배포** 하는 옵션을 선택 하지 않아야 합니다.
    
    Office Web Apps 서버가 내부 방화벽 외부에 배포 된 경우 **Office Web Apps 서버를 외부 네트워크 (즉, 외곽/인터넷)에 배포**하는 옵션을 선택 합니다.

7.  **새 Office Web Apps 서버 정의** 대화 상자에서 **확인**을 클릭 한 다음 **속성 편집** 대화 상자에서 **확인** 을 클릭 합니다. 그러면 Office Web Apps 검색 URL이 풀의 연결 중 하나로 나열 됩니다.

Office Web Apps 서버와 연결 되어야 하는 각 풀에 대해이 프로세스를 반복 해야 합니다.

검색 URL을 토폴로지에 추가한 후에는이 업데이트 된 토폴로지를 게시 해야 합니다. 토폴로지 작성기에서 다음을 수행 합니다.

1.  **작업** 을 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.

2.  토폴로지 게시 마법사의 **토폴로지 게시** 페이지에서 **다음**을 클릭 합니다.

3.  **게시 마법사 완료** 페이지에서 **마침을**클릭 합니다.

4.  토폴로지 작성기를 닫습니다.

</div>

<span> </span>

</div>

</div>

</div>

