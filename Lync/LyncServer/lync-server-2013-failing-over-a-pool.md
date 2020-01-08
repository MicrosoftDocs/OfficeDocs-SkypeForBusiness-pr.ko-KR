---
title: 'Lync Server 2013: 풀 장애 조치(failover)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 512d7bc09d40d7b99cc66970cdd2a5584030fea9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a>Lync Server 2013 에서 풀 장애 조치(failover)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-10-10_

단일 프런트 엔드 풀에 오류가 발생 하 여 장애 조치 해야 하는 경우 다음 절차를 사용 합니다. 이 절차에서는 Datacenter1에 Pool1이 포함 되어 있고 Pool1에 오류가 발생 했습니다. Datacenter2에 위치한 Pool2로 장애 조치 (failover) 합니다.

필요한 경우 풀 장애 조치 (failover)에 대 한 대부분의 작업은 중앙 관리 저장소를 통해 실패 하 게 됩니다. 이는 풀의 사용자가 장애 조치를 할 때 중앙 관리 저장소가 작동 해야 하기 때문에 중요 합니다.

또한 프런트 엔드 풀에는 실패 하지만 해당 사이트의 Edge 풀은 계속 실행 되는 경우에는 Edge 풀이 다음 홉 풀로 실패 한 풀을 사용 하는지 여부를 알아야 합니다. 이 경우 실패 한 프런트 엔드 풀을 장애 조치 (failover) 하기 전에 다른 프런트 엔드 풀을 사용 하도록 Edge 풀을 변경 해야 합니다. 다음 홉 설정을 변경 하는 방법은 Edge가 Edge 풀과 동일한 사이트의 풀을 사용할지 아니면 다른 사이트에 있는지에 따라 달라 집니다.

**같은 사이트에서 다음 홉 풀을 사용 하도록 Edge 풀 설정**

1.  토폴로지 작성기를 열고 변경 해야 하는 Edge 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

2.  **다음 홉**을 클릭 합니다. **다음 홉 풀:** 목록에서 이제 다음 홉 풀 역할을 할 풀을 선택 합니다.

3.  **확인**을 클릭 한 다음 변경 내용을 게시 합니다.

**다른 사이트에서 다음 홉 풀을 사용 하도록 Edge 풀을 설정 하려면**

1.  Lync Server Management Shell 창을 열고 다음 cmdlet을 입력 합니다.
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**재해에 따라 풀을 장애 조치**

1.  Pool2의 프런트 엔드 서버에 다음 cmdlet을 입력 하 여 중앙 관리 서버의 호스트인 풀을 찾습니다.
    
        Invoke-CsManagementServerFailover -Whatif
    
    이 cmdlet의 결과에는 현재 중앙 관리 서버를 호스트 하는 풀이 표시 됩니다. 이 절차의 나머지 부분에서는이 풀을 CMS\_풀 이라고 합니다.

2.  토폴로지 작성기를 사용 하 여 CMS\_풀에서 실행 되는 Lync Server 버전을 찾습니다. Lync Server 2013을 실행 하는 경우 다음 cmdlet을 사용 하 여 풀 1의 백업 풀을 찾습니다.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    \_백업 풀을 백업 풀로 사용 합니다.

3.  다음 cmdlet을 사용 하 여 중앙 관리 저장소의 상태를 확인 합니다.
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    이 cmdlet은 ActiveMasterFQDN 및 ActiveFileTransferAgents 모두 CMS\_풀의 FQDN을 가리키지만을 표시 합니다. 비어 있는 경우 중앙 관리 서버를 사용할 수 없으며 장애 조치를 수행 해야 합니다.

4.  중앙 관리 저장소를 사용할 수 없거나 중앙 관리 저장소가 Pool1 (즉, 실패 한 풀)에서 실행 되는 경우에는 풀을 통해 실패 하기 전에 중앙 관리 서버를 장애 조치 해야 합니다. Lync Server 2013를 실행 하는 풀에 호스트 된 중앙 관리 서버를 장애 조치 해야 하는 경우이 절차의 5 단계에서 cmdlet을 사용 합니다. Lync Server 2010를 실행 하는 풀에 호스트 된 중앙 관리 서버를 장애 조치 해야 하는 경우이 절차의 6 단계에서 cmdlet을 사용 합니다. 중앙 관리 서버를 장애 조치할 필요가 없는 경우에는이 절차의 7 단계로 건너뛰십시오.

5.  Lync Server 2013를 실행 하는 풀의 중앙 관리 저장소를 장애 조치 하려면 다음을 수행 합니다.
    
      - 먼저 다음을 입력 하 여 백업\_풀의 백 엔드 서버가 중앙 관리 저장소의 principal 인스턴스를 실행 하는지 확인 합니다.
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 백업\_풀의 주 백 엔드 서버가 주 서버 이면 다음을 입력 합니다.
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        백업\_풀의 미러 백 엔드 서버가 주 서버 이면 다음을 입력 합니다.
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 중앙 관리 서버 장애 조치 (failover)가 완료 되었는지 확인 합니다. 다음을 입력 합니다.
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN와 ActiveFileTransferAgents 모두 백업\_풀의 FQDN을 가리키고 있는지 확인 합니다.
    
      - 마지막으로, 다음을 입력 하 여 모든 프런트 엔드 서버의 복제 상태를 확인 합니다.
        
            Get-CsManagementStoreReplicationStatus 
        
        모든 복제본에 True 값이 있는지 확인 합니다.
        
        이 절차의 7 단계로 건너뛰십시오.

6.  백업\_풀의 백 엔드 서버에 중앙 관리 저장소를 설치 합니다.
    
      - 먼저 다음 명령을 실행 합니다.
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - 백업\_풀의 프런트 엔드 서버 중 하나에서 다음 명령을 실행 하 여 중앙 관리 저장소의 이동을 강제로 수행 합니다.
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 이동이 완료 되었는지 확인 합니다.
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN와 ActiveFileTransferAgents 모두 백업\_풀의 FQDN을 가리키고 있는지 확인 합니다.
    
      - 다음을 입력 하 여 모든 프런트 엔드 서버의 복제 상태를 확인 합니다.
        
            Get-CsManagementStoreReplicationStatus 
        
        모든 복제본에 True 값이 있는지 확인 합니다.
    
      - 백업\_풀의 프런트 엔드 서버 나머지 부분에 중앙 관리 서버 서비스를 설치 합니다. 이렇게 하려면이 절차의 앞부분에서 중앙 관리 저장소를 강제로 이동할 때 사용한 것을 제외 하 고 모든 프런트 엔드 서버에서 다음 명령을 실행 합니다.
        
            Bootstrapper /Setup 

7.  Lync Server Management Shell 창에서 다음 cmdlet을 실행 하 여 Pool1에서 Pool2로 사용자를 장애 조치 합니다.
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    중앙 관리 저장소 상태를 검사 하는이 절차의 이전 부분에서 수행 된 단계는 유니버설 하지 않기 때문에 중앙 관리 저장소가 아직 완전히 장애 조치 되지 않아이 cmdlet이 실패할 수도 있습니다. 이 경우 표시 되는 오류 메시지를 기반으로 중앙 관리 저장소를 수정한 다음이 cmdlet을 다시 실행 해야 합니다.
    
    다음 오류 메시지가 표시 되는 경우 풀을 장애 인하기 전에 다음 홉으로 다른 풀을 사용 하도록이 사이트에서 Edge 풀을 변경 해야 합니다. 자세한 내용은이 항목의 시작 부분에 나오는 절차를 참조 하세요.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

