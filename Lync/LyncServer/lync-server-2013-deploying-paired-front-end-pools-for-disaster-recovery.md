---
title: 'Lync Server 2013: 재해 복구를 위해 페어링된 프런트 엔드 풀 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 309c8f7ac7da4e40f2b16e5d13015330b2d9b611
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514535"
---
# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013에서 재해 복구를 위한 페어링된 프런트 엔드 풀 배포

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

토폴로지 작성기를 사용 하 여 쌍으로 된 프런트 엔드 풀의 재해 복구 토폴로지를 쉽게 배포할 수 있습니다.

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>프런트 엔드 풀 쌍을 배포하려면

1.  풀이 새로 생성 되었지만 아직 정의 되지 않은 경우 토폴로지 작성기를 사용 하 여 풀을 만듭니다.

2.  토폴로지 작성기에서 두 풀 중 하나를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.

3.  왼쪽 창에서 **탄성**을 클릭하고 오른쪽 창에서 **연결된 백업 풀**을 선택합니다.

4.  **연결된 백업 풀** 아래 상자에서 이 풀과 쌍으로 지정할 풀을 선택합니다. 이미 다른 풀과 쌍으로 지정되어 있지 않은 기존 풀만 선택할 수 있습니다.
    
    ![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")  

5.  **자동 음성 장애 조치(failover) 및 장애 복구(failback)** 를 선택하고 **확인**을 클릭합니다.
    
    이제 이 풀에 대한 세부 정보를 표시하면 연결된 풀이 오른쪽 창의 **탄성** 아래에 표시됩니다.

6.  토폴로지 작성기를 사용 하 여 토폴로지를 게시 합니다.

7.  두 풀이 아직 배포되지 않은 경우 지금 배포하면 구성이 완료됩니다. 이 절차의 마지막 두 단계는 건너뛰어도 됩니다.
    
    그러나 쌍으로 지정된 관계를 정의하기 전에 풀을 이미 배포한 경우에는 다음의 마지막 두 단계를 완료해야 합니다.

8.  두 풀에 모두 포함되어 있는 모든 프런트 엔드 서버에서 다음을 실행합니다.
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    그러면 백업 페어링이 올바르게 작동하는 데 필요한 다른 서비스가 구성됩니다.

9.  Lync Server 관리 셸 명령 프롬프트에서 다음을 실행 합니다.
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. 다음 cmdlet을 사용하여 두 풀의 사용자 및 전화 회의 데이터가 서로 동기화되도록 강제 지정합니다.
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    데이터를 동기화하는 데는 시간이 걸릴 수 있습니다. 다음 cmdlet을 사용하여 상태를 확인할 수 있습니다. 두 방향의 상태가 모두 안정 된 상태 인지 확인 합니다.
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> 토폴로지 작성기에서 <STRONG>자동 장애 조치 (failover) 및</STRONG> 연결 된 시간 간격은 Lync Server 2010에 도입 된 음성 복구 기능에만 적용 됩니다. 해당 옵션을 선택해도 이 문서에서 설명하는 풀 장애 조치(failover)가 자동으로 수행되는 것은 아닙니다. 풀 장애 조치(failover) 및 장애 복구(failback)를 수행하려면 항상 관리자가 장애 조치(failover) 및 장애 복구(failback) cmdlet을 각각 수동으로 호출해야 합니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

