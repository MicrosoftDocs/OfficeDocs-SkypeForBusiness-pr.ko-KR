---
title: 모니터링 서버 연결 제거
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0381f65ee233abcac60268b9c8e491b31e88c24f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529875"
---
# <a name="remove-the-monitoring-server-association"></a>모니터링 서버 연결 제거

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-04_

모니터링 서버를 제거 하려면 연결 된 프런트 엔드 풀, 프런트 엔드 서버, Sba (survivable Branch 기기 및 Sba (survivable 분기 서버에 대 한 종속성을 변경 하거나 지워야 합니다. 프런트 엔드 풀, 프런트 엔드 서버, Sba (survivable Branch 기기 및 Sba (survivable 분기 서버의 속성을 편집 하 여 종속성을 제거할 수 있습니다. 종속성을 지우고 토폴로지 작성기에서 서버를 삭제 한 후에는 토폴로지 작성기의 연결 된 데이터베이스 저장소 개체도 삭제 된다는 메시지가 표시 됩니다.

<div>

## <a name="to-remove-the-monitoring-server-association"></a>모니터링 서버 연결을 제거하려면

1.  Lync Server 2013 프런트 엔드 서버를 열고 토폴로지 작성기를 엽니다.

2.  Lync Server 2010 노드로 이동 합니다.

3.  토폴로지 작성기에서 모니터링 서버가 정의 된 위치에 따라 **Enterprise Edition 프런트 엔드 풀**, **Standard Edition 프런트 엔드 서버**또는 **분기 사이트**를 확장 합니다.

4.  Sba (survivable Branch Server가 연결 되어 있는 경우 **분기**사이트를 확장 하 고 분기 사이트 이름을 확장 한 다음 **sba (survivable 분기 기기**를 확장 합니다.
    
    <div>
    

    > [!NOTE]  
    > 사용자 인터페이스의 <STRONG>Sba (survivable Branch 기기</STRONG> 는 Sba (survivable branch Server 및 Sba (survivable branch 기기 둘 다에 적용 됩니다.

    
    </div>

5.  모니터링 서버와 연결 된 풀, 서버 또는 장치를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

6.  **속성 편집**의 **일반** 아래에 있는 **연결**에서 **모니터링 서버 연결** 확인란의 선택을 취소한 후 **확인**을 클릭합니다.

7.  모니터링 서버와 연결 된 다른 모든 풀, 서버 또는 장치에 대해 이전 단계를 반복 합니다.

8.  모니터링 서버를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.

9.  **종속 저장소 삭제**에서 **확인**을 클릭합니다.

10. 토폴로지를 게시 하 고, 복제 상태를 확인 하 고, 필요에 따라 Lync Server 배포 마법사를 실행 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

