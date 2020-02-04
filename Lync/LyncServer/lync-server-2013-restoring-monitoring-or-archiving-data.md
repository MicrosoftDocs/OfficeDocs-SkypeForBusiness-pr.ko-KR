---
title: 'Lync Server 2013: 모니터링 또는 보관 데이터 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9621fe3c1905dbd34fd3b4da39b2562c608d6355
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Lync Server 2013에서 모니터링 또는 데이터 보관 복원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-18_

오류 발생 후 Lync Server를 시작 하 고 실행할 수 있도록 모니터링 및 보관 데이터 복원이 필요 하지 않습니다. 그러나 모니터링 및 데이터 보관이 조직에 중요 한 경우 데이터베이스를 다시 만든 후에 데이터를 복원 하는 것이 좋습니다.

다음 절차에서는 SQL Server Management Studio를 사용 하 여 보관 또는 모니터링 데이터를 복원 하는 방법을 설명 합니다.

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>백업 파일의 모니터링 또는 데이터 보관을 복원 하려면

1.  로컬 컴퓨터 또는 해당 사용자 권한이 있는 그룹의 관리자 그룹 구성원으로 복원 하는 서버에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft SQL Server 2012** 또는 **microsoft sql server 2008 R2**를 차례로 클릭 한 다음 **Sql Server Management studio**를 클릭 하 여 sql server management studio를 엽니다.

3.  **서버에 연결**에서 최소한 서버 이름과 인증 정보를 제공 하 여 SQL Server 인스턴스에 연결 합니다.

4.  **개체 탐색기**에서 **데이터베이스**를 마우스 오른쪽 단추로 클릭 한 다음 **데이터베이스 복원을**클릭 합니다.

5.  **페이지 선택**에서 **일반**을 클릭 한 다음 **데이터베이스** 에서 데이터베이스 이름을 다음과 같이 선택 합니다.
    
      - 보관 데이터베이스의 경우 **Lcslog**를 선택 합니다.
    
      - CDR (통화 정보 기록) 데이터베이스의 경우 **LcsCDR**를 선택 합니다.
    
      - 체감 품질 (환경 품질) 데이터베이스의 경우에는 **QoEMetrics**를 선택 합니다.

6.  **장치에서를**클릭 합니다.

7.  **복원할 백업 세트 선택**에서 백업 파일을 클릭 한 다음 **복원을**클릭 합니다.

8.  **페이지 선택**에서 **옵션**을 클릭 하 고 데이터 파일 경로와 로그 경로가 올바른 폴더에 있는지 확인 한 다음 **확인**을 클릭 합니다.

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>Acl (액세스 제어 목록)이 정확한 지 확인 하려면

1.  **데이터베이스**를 확장 하 고 보관 또는 모니터링 데이터베이스를 확장 한 다음 **보안**을 확장 하 고 **사용자**를 확장 합니다.

2.  도메인 그룹 RTCComponentUniversalServices 사용자로 존재 하는지 확인 합니다.

3.  **사용자**아래에 RTCComponentUniversalServices가 없는 경우 다음을 수행 합니다.
    
    1.  **사용자**를 마우스 오른쪽 단추로 클릭 한 다음 **새 사용자**를 클릭 합니다.
    
    2.  **로그인 이름**에 누락 된 그룹 이름 RTCComponentUniversalServices을 입력 합니다.
    
    3.  **데이터베이스 역할 구성원**에서 **ServerRole** 권한을 선택한 다음 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 보관 또는 모니터링 서비스를 다시 시작할 필요는 없습니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

