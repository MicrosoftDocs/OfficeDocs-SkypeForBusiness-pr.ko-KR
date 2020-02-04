---
title: 모니터링 서버 연결 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f26a809056674c231212db3f824a2ecb7ce7ecd1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>모니터링 서버 연결 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-04_

모니터링 서버를 제거 하려면 연결 된 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch 기기 및 Survivable Branch 서버에 대 한 종속성을 변경 하거나 선택 취소 해야 합니다. 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch 기기 및 Survivable Branch 서버의 속성을 편집 하 여 종속성을 제거 합니다. 종속성을 지우고 토폴로지 작성기에서 서버를 삭제 하면 토폴로지 작성기의 관련 데이터베이스 저장소 개체도 삭제 된다는 알림이 표시 됩니다.

<div>

## <a name="to-remove-the-monitoring-server-association"></a>모니터링 서버 연결을 제거 하려면

1.  Lync Server 2013 프런트 엔드 서버를 열고 토폴로지 작성기를 엽니다.

2.  Lync Server 2010 노드로 이동 합니다.

3.  토폴로지 작성기에서 모니터링 서버가 정의 된 위치에 따라 **Enterprise Edition 프런트 엔드 풀**, **Standard Edition 프런트 엔드 서버**또는 **분기 사이트**를 확장 합니다.

4.  연결 된 Survivable Branch 서버가 있는 경우 **분기**사이트를 확장 하 고 분기 사이트 이름을 확장 한 다음 **Survivable branch 기기**를 확장 합니다.
    
    <div>
    

    > [!NOTE]  
    > 사용자 인터페이스의 <STRONG>Survivable Branch 기기</STRONG> 는 Survivable branch 서버와 Survivable branch 기기 둘 다에 적용 됩니다.

    
    </div>

5.  모니터링 서버와 연결 된 풀, 서버 또는 장치를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

6.  **속성 편집**의 **일반**아래에 있는 **연결**에서 **모니터링 서버 연결** 확인란의 선택을 취소 한 다음 **확인**을 클릭 합니다.

7.  모니터링 서버와 연결 된 다른 풀, 서버 또는 장치에 대해 앞의 단계를 반복 합니다.

8.  모니터링 서버를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.

9.  **종속 저장소 삭제**에서 **확인**을 클릭 합니다.

10. 토폴로지를 게시 하 고, 복제 상태를 확인 하 고, 필요에 따라 Lync Server 배포 마법사를 실행 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

