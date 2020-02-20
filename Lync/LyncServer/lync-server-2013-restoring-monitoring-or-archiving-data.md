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
ms.openlocfilehash: 5be8d5409a5770ef2ee928075c147c126ce4219a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Lync Server 2013에서 모니터링 또는 보관 데이터 복원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-18_

장애 발생 후 Lync Server를 실행 하 고 실행할 때는 모니터링 및 보관 데이터를 복원 하지 않아도 됩니다. 그러나 모니터링 및 보관 데이터가 조직에 중요 한 경우 데이터베이스를 다시 만든 후에 데이터를 복원 해야 합니다.

다음 절차에서는 SQL Server Management Studio를 사용 하 여 보관 또는 모니터링 데이터를 복원 하는 방법에 대해 설명 합니다.

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>백업 파일로부터 모니터링 또는 보관 데이터를 복원하려면

1.  로컬 컴퓨터에서 Administrators 그룹의 구성원 또는 이와 동등한 사용자 권한을 가진 그룹으로 복원 중인 서버에 로그온 합니다.

2.  SQL Server Management Studio 열기: **시작**, **모든 프로그램**, **Microsoft SQL Server 2012** 또는 **microsoft sql server 2008 R2**를 차례로 클릭 한 다음 **SQL server Management Studio**를 클릭 합니다.

3.  **서버에 연결**에서 최소한 서버 이름 및 인증 정보를 제공하여 SQL Server 인스턴스에 연결합니다.

4.  **개체 탐색기**에서 **데이터베이스**를 마우스 오른쪽 단추로 클릭한 후 **데이터베이스 복원**을 클릭합니다.

5.  **페이지 선택** 아래에서 **일반**을 클릭한 후 **데이터베이스**에서 다음과 같이 데이터베이스 이름을 선택합니다.
    
      - 보관 데이터베이스의 경우에는 **Lcslog**를 선택 합니다.
    
      - CDR(통화 정보 기록) 데이터베이스에 대해 **LcsCDR**을 선택합니다.
    
      - QoE(체감 품질) 데이터베이스에 대해 **QoEMetrics**를 선택합니다.

6.  **장치**를 클릭합니다.

7.  **복원에 사용할 백업 세트 선택**에서 백업 파일을 클릭한 후 **복원**을 클릭합니다.

8.  **페이지 선택**에서 **옵션**을 클릭하고 데이터 파일 경로 및 로그 경로가 올바른 폴더에 있는지 확인한 후 **확인**을 클릭합니다.

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>Acl (액세스 제어 목록)이 올바른지 확인 하려면

1.  **데이터베이스**를 확장하고, 보관 또는 모니터링 데이터베이스를 확장하고, **보안**을 확장한 후 **사용자**를 확장합니다.

2.  도메인 그룹 RTCComponentUniversalServices가 사용자로 존재하는지 확인합니다.

3.  **사용자**에 RTCComponentUniversalServices이 없는 경우 다음을 수행 합니다.
    
    1.  **사용자**를 마우스 오른쪽 단추로 클릭한 다음 **새 사용자**를 클릭합니다.
    
    2.  **로그인 이름**에 누락 된 그룹 이름 RTCComponentUniversalServices을 입력 합니다.
    
    3.  **데이터베이스 역할 멤버 자격** 아래에서 **ServerRole** 권한을 선택한 후 **확인**을 클릭합니다.
    
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

