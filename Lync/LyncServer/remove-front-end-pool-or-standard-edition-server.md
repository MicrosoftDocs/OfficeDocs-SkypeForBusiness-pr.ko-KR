---
title: 프런트 엔드 풀 또는 Standard Edition 서버 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8628f883285eec61a179c27d5dfda16b8c9b51d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a>프런트 엔드 풀 또는 Standard Edition 서버 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-04_

이 항목에서는 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 제거 하는 과정을 안내 합니다. 프런트 엔드 풀을 제거 하면 풀에 속한 각 프런트 엔드 서버를 그룹 제거 프로세스의 일부로 제거 합니다. Standard Edition 프런트 엔드 서버를 제거 하는 경우 토폴로지 작성기에서 SQL 스토어 정의를 제거 해야 합니다.

<div>

## <a name="to-remove-a-front-end-server-pool"></a>프런트 엔드 서버 풀을 제거 하려면

1.  토폴로지 작성기를 엽니다.

2.  Lync Server 2010 노드로 이동 합니다.

3.  **Enterprise Edition 프런트 엔드 풀**을 확장 하 고 프런트 엔드 풀을 확장 한 다음 제거 하려는 프런트 엔드 풀을 마우스 오른쪽 단추로 클릭 하 고 **삭제**를 클릭 합니다.

4.  토폴로지를 게시 하 고, 복제 상태를 확인 한 다음 필요에 따라 Lync Server 배포 마법사를 실행 합니다.

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>Standard Edition 프런트 엔드 서버를 제거 하려면

1.  토폴로지 작성기를 엽니다.

2.  Lync Server 2010 노드로 이동 합니다.

3.  **Standard Edition 프런트 엔드 서버**를 확장 하 고 제거 하려는 프런트 엔드 서버를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.

4.  **Sql 저장소**를 확장 하 고 Standard Edition 프런트 엔드 서버와 연결 된 sql Server 데이터베이스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 스탠더드 버전의 프런트 엔드 서버에서 collocated SQL Server 데이터베이스의 정의를 제거 해야 합니다.

    
    </div>

5.  토폴로지를 게시 하 고, 복제 상태를 확인 한 다음 필요에 따라 Lync Server 배포 마법사를 실행 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

