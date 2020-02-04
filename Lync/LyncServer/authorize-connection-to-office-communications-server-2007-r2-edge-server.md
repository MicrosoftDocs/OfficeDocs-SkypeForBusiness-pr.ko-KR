---
title: Office Communications Server 2007 R2 Edge 서버에 대 한 연결 권한 부여
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: 8dbce32a12f05dff768d23a2bdccfe1b84a567cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Office Communications Server 2007 R2 Edge 서버에 대 한 연결 권한 부여

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

파일럿 풀의 각 Lync Server 2013 프런트 엔드 서버 또는 Standard Edition 서버에 대해 Office Communications Server 2007 R2 Edge 서버에 연결할 수 있는 내부 서버 목록을 업데이트 해야 합니다. 이러한 업데이트가 없으면 레거시 Edge 서버를 사용 하 여 참가 하는 사용자를 위한 외부 오디오/시각적 (A/V) 회의는 작동 하지 않습니다.

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a>Office Communications Server 2007 R2 Edge 서버에 대 한 연결을 승인 하려면

1.  Office Communications Server 2007 R2 Edge 서버에서 **관리 도구** 그룹에 있는 **컴퓨터 관리** 스냅인을 엽니다.

2.  콘솔 트리에서 **서비스 및 응용 프로그램**을 확장 합니다.

3.  **Office Communications Server 2007 R2**를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

4.  **내부** 탭을 클릭 합니다.

5.  **서버 추가**에서 **추가**를 클릭 합니다.

6.  **Office Communications Server 추가** 대화 상자에서 적절 한 정보를 입력 합니다.
    
      - 각 Lync Server 2013 프런트 엔드 서버 또는 Standard Edition Server 및 Lync Server 2013 풀의 FQDN (정규화 된 도메인 이름)을 지정 합니다.
    
      - 해당 FQDN으로 다음 홉 컴퓨터를 지정 하는 풀에서 고정 경로를 구성한 경우 Lync Server 2013 디렉터의 FQDN을 지정 합니다.

7.  각 Lync Server 2013, 프런트 엔드 서버, Standard Edition Server, 풀 및 디렉터에 대 한 항목을 추가한 후 **적용** 을 클릭 한 다음 **확인** 을 클릭 하 여 속성 페이지를 닫습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

