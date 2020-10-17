---
title: Office Web Apps 서버에서 작동 하도록 Lync Server 2013 구성
description: Office Web Apps 서버에서 작동 하도록 Lync Server 2013을 구성 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e53500e0ad272c81340c25946f5b7f8e72a121
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570874"
---
# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>Office Web Apps 서버에서 작동 하도록 Lync Server 2013 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-04-22_

Office Web Apps 서버를 사용 하도록 Lync Server 2013을 구성 하려면 먼저 Office Web Apps 서버를 배포 및 구성 해야 합니다. 단일 Office Web Apps Server를 설치 및 구성하는 방법에 또는 고가용성을 위해 Office Web Apps Server 팜을 설치하고 구성하는 방법에 대한 자세한 내용은 **Office Web Apps Server 및 Office Web Apps 배포 지침** 문서를 참조하십시오.

Office Web Apps 서버를 성공적으로 설치 하 고 웹 팜을 올바르게 구성한 후에는 새 서버와 통신 하도록 Lync Server를 구성 해야 합니다. 이 작업은 Office Web Apps 서버 검색 URL을 Lync Server 토폴로지에 추가 하 여 수행 합니다. Office Web Apps 서버를 토폴로지에 추가 하려면 다음 단계를 완료 합니다.

1.  **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  **토폴로지 작성기** 대화 상자에서 **기존 배포에서 토폴로지 다운로드**를 선택한 후 **확인**을 클릭합니다.

3.  **토폴로지를 다른 이름으로 저장** 대화 상자에서 **파일 이름** 상자에 토폴로지 문서 이름(예: **PreWebAppsServerTopology**)을 입력한 후 **저장**을 클릭합니다. 이 토폴로지는 나중에 새 토폴로지에 문제가 발생한 경우 검색하고 다시 게시할 수 있습니다.

4.  토폴로지 작성기에서 **Lync Server 2013**, 사이트 이름, **Enterprise Edition 프런트 엔드 풀**을 차례로 확장 하 고 풀 중 하나의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

5.  **속성 편집** 대화 상자의 **일반** 탭에서 **Office Web Apps Server 연결** 제목을 찾아서 **새로 만들기**를 클릭합니다(또는 드롭다운 목록에서 기존 Office Web Apps Server 선택).

6.  **새 Office Web Apps Server 정의** 대화 상자에서 **Office Web Apps Server FQDN** 상자에 Office Web Apps Server 컴퓨터의 FQDN(정규화된 도메인 이름)을 입력합니다. 이렇게 하면 Office Web Apps Server 검색 URL이 **Office Web Apps Server 검색 URL** 상자에 자동으로 입력됩니다.
    
    Office Web Apps 서버를 Lync Server 2013와 동일한 네트워크 영역에 설치 하는 경우에는 **Office Web Apps 서버를 외부 네트워크 (경계/인터넷)에 배포** 하는 옵션을 선택 하면 안 됩니다.
    
    Office Web Apps Server가 내부 방화벽 외부에 배포된 경우 **Office Web Apps Server가 외부 네트워크에 배포되어 있습니다(경계/인터넷).** 옵션을 선택합니다.

7.  **새 Office Web Apps Server 정의** 대화 상자에서 **확인**을 클릭한 후 **속성 편집** 대화 상자에서 **확인**을 클릭합니다. 그러면 Office Web Apps 검색 URL이 풀의 연결 중 하나로 나열됩니다.

Office Web Apps Server와 연결해야 하는 각 풀에 대해 이 프로세스를 반복해야 합니다.

토폴로지에 검색 URL을 추가한 후에는 이 업데이트된 토폴로지를 게시해야 합니다. 이렇게 하려면 토폴로지 작성기에서 다음을 수행합니다.

1.  **동작**을 클릭하고, **토폴로지 게시**를 클릭합니다.

2.  토폴로지 게시 마법사의 **토폴로지 게시** 페이지에서 **다음**을 클릭합니다.

3.  **게시 마법사 완료** 페이지에서 **마침**을 클릭합니다.

4.  토폴로지 작성기를 닫습니다.

</div>

<span> </span>

</div>

</div>

</div>

