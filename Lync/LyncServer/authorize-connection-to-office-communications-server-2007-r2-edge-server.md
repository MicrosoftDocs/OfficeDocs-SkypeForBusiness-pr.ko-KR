---
title: Office Communications Server 2007 R2에 지 서버에 대 한 연결 권한 부여
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6181f3d42facaf49b84b7c07776dc8717e88b271
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499765"
---
# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Office Communications Server 2007 R2에 지 서버에 대 한 연결 권한 부여

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

파일럿 풀의 각 Lync Server 2013 프런트 엔드 서버 또는 Standard Edition 서버에 대해 Office Communications Server 2007 R2에 지 서버에 연결 하도록 허용 된 내부 서버 목록을 업데이트 해야 합니다. 이와 같이 업데이트하지 않으면 레거시 에지 서버를 사용하여 참가하는 사용자에 대해 외부 A/V(오디오/비디오) 회의가 작동하지 않습니다.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Office Communications Server 2007 R2에 지 서버에 대 한 연결을 승인 하려면

1.  Office Communications Server 2007 R2에 지 서버의 **관리 도구** 그룹에서 **컴퓨터 관리** 스냅인을 엽니다.

2.  콘솔 트리에서 **서비스 및 응용 프로그램**을 확장합니다.

3.  **Office Communications Server 2007 R2**를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

4.  **내부** 탭을 클릭합니다.

5.  **서버 추가**에서 **추가**를 클릭합니다.

6.  **Office Communications Server 추가** 대화 상자에서 적합한 정보를 입력합니다.
    
      - 각 Lync Server 2013 프런트 엔드 서버 또는 Standard Edition Server 및 Lync Server 2013 풀의 FQDN (정규화 된 도메인 이름)을 지정 합니다.
    
      - 해당 FQDN으로 다음 홉 컴퓨터를 지정 하는 풀에 고정 경로를 구성한 경우 Lync Server 2013 디렉터의 FQDN을 지정 합니다.

7.  각 Lync Server 2013, 프런트 엔드 서버, Standard Edition Server, 풀 및 디렉터에 대 한 항목을 추가한 후에 **적용** 을 클릭 하 고 **확인** 을 클릭 하 여 속성 페이지를 닫습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

