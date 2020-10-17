---
title: 'Lync Server 2013: 풀을 장애 조치 (failover)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf54f1949627c39291388be248e0029077e9278
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530965"
---
# <a name="failing-over-a-pool-in-lync-server-2013"></a>Lync Server 2013에서 풀 장애 조치 (failover)

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-10-10_

단일 프런트 엔드 풀에 오류가 발생하여 장애 조치(failover)를 수행해야 하는 경우 다음 절차를 따릅니다. 이 절차에서 Datacenter1은 Pool1을 포함하며 Pool1에서 오류가 발생한 상태입니다. Pool1을 Datacenter2에 있는 Pool2로 장애 조치(failover)합니다.

풀 장애 조치 (failover)를 수행 하는 대부분의 작업은 중앙 관리 저장소 (필요한 경우)를 통과 해야 합니다. 이는 해당 풀의 사용자가 장애 조치 (failover) 될 때 중앙 관리 저장소가 정상적으로 작동 하기 때문에 중요 합니다.

또한 프런트 엔드 풀에 오류가 발생했는데 해당 사이트의 에지 풀은 계속 실행되는 경우에는 에지 풀이 오류가 발생한 풀을 다음 홉 풀로 사용하는지 여부를 확인해야 합니다. 오류가 발생한 풀이 다음 홉 풀로 사용되는 경우에는 해당 프런트 엔드 풀을 장애 조치(failover)하기 전에 다른 프런트 엔드 풀을 사용하도록 에지 풀을 변경해야 합니다. 다음 홉 설정을 변경하는 방법은 에지가 에지 풀과 같은 사이트의 풀을 사용하는지 아니면 다른 사이트의 풀을 사용하는지에 따라 달라집니다.

**에지 풀이 같은 사이트의 다음 홉 풀을 사용하도록 설정하려면**

1.  토폴로지 작성기를 열고 변경 해야 하는에 지 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

2.  **다음 홉**을 클릭합니다. **다음 홉 풀:** 목록에서 다음 홉 풀로 사용할 풀을 선택합니다.

3.  **확인**을 클릭하고 변경 내용을 게시합니다.

**에지 풀이 다른 사이트의 다음 홉 풀을 사용하도록 설정하려면**

1.  Lync Server 관리 셸 창을 열고 다음 cmdlet을 입력 합니다.
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**재해 발생 시 풀을 장애 조치(failover)하려면**

1.  호스트인의 프런트 엔드 서버에 다음 cmdlet을 입력 하 여 중앙 관리 서버에 대 한 호스트인 풀을 찾습니다.
    
        Invoke-CsManagementServerFailover -Whatif
    
    이 cmdlet의 결과는 현재 중앙 관리 서버를 호스트 하는 풀을 보여 줍니다. 이 절차의 나머지 부분에서이 풀을 CMS 풀 이라고 합니다 \_ .

2.  토폴로지 작성기를 사용 하 여 CMS 풀에서 실행 되는 Lync Server의 버전을 찾습니다 \_ . Lync Server 2013를 실행 하는 경우 다음 cmdlet을 사용 하 여 풀 1의 백업 풀을 찾습니다.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    백업 풀 \_ 을 백업 풀로 사용 합니다.

3.  다음 cmdlet을 사용 하 여 중앙 관리 저장소의 상태를 확인 합니다.
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    이 cmdlet은 ActiveMasterFQDN 및 Activefiletransferagents가 둘 다 CMS 풀의 FQDN을 가리키고 있음을 보여 줍니다 \_ . 비어 있는 경우에는 중앙 관리 서버를 사용할 수 없으며 장애 조치 (failover)를 수행 해야 합니다.

4.  중앙 관리 저장소를 사용할 수 없거나 중앙 관리 저장소가 Pool1) (즉, 오류가 발생 한 풀)에서 실행 되 고 있는 경우에는 해당 풀을 장애 조치 (failover) 하기 전에 중앙 관리 서버를 장애 조치 (failover) 해야 합니다. Lync Server 2013을 실행 하는 풀에 호스트 된 중앙 관리 서버를 장애 조치 (failover) 해야 하는 경우에는이 절차의 5 단계에서 cmdlet을 사용 합니다. Lync Server 2010을 실행 하는 풀에 호스트 된 중앙 관리 서버를 장애 조치 (failover) 해야 하는 경우이 절차의 6 단계에 나오는 cmdlet을 사용 합니다. 중앙 관리 서버를 장애 조치할 필요가 없으면이 절차의 7 단계로 건너뜁니다.

5.  Lync Server 2013을 실행 하는 풀에서 중앙 관리 저장소를 장애 조치 (failover) 하려면 다음을 수행 합니다.
    
      - 먼저 \_ 다음을 입력 하 여 백업 풀의 백 엔드 서버가 중앙 관리 저장소의 보안 주체 인스턴스를 실행 하는지 확인 합니다.
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 백업 풀의 주 백 엔드 서버가 주 서버인 경우 \_ 다음을 입력 합니다.
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        백업 풀의 미러 백 엔드 서버가 \_ 보안 주체 인 경우 다음을 입력 합니다.
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 중앙 관리 서버 장애 조치 (failover)가 완료 되었는지 확인 합니다. 다음을 입력합니다.
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN 및 Activefiletransferagents가 모두 백업 풀의 FQDN을 가리키는지 확인 \_ 합니다.
    
      - 마지막으로 다음을 입력 하 여 모든 프런트 엔드 서버의 복제 상태를 확인 합니다.
        
            Get-CsManagementStoreReplicationStatus 
        
        모든 복제본의 값이 True인지 확인합니다.
        
        이 절차의 7단계로 건너뜁니다.

6.  백업 풀의 백 엔드 서버에 중앙 관리 저장소를 설치 \_ 합니다.
    
      - 먼저 다음 명령을 실행합니다.
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - 백업 풀의 프런트 엔드 서버 중 하나에서 다음 명령을 실행 \_ 하 여 중앙 관리 저장소를 강제로 이동 합니다.
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 이동이 완료되었는지 확인합니다.
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN 및 Activefiletransferagents가 모두 백업 풀의 FQDN을 가리키는지 확인 \_ 합니다.
    
      - 다음을 입력하여 모든 프런트 엔드 서버의 복제 상태를 확인합니다.
        
            Get-CsManagementStoreReplicationStatus 
        
        모든 복제본의 값이 True인지 확인합니다.
    
      - 백업 풀의 나머지 프런트 엔드 서버에 중앙 관리 서버 서비스를 설치 \_ 합니다. 이렇게 하려면이 절차의 앞부분에서 중앙 관리 저장소를 이동할 때 사용한 것을 제외 하 고 모든 프런트 엔드 서버에서 다음 명령을 실행 합니다.
        
            Bootstrapper /Setup 

7.  Lync Server 관리 셸 창에서 다음 cmdlet을 실행 하 여 Pool1)에서 호스트인로 사용자를 장애 조치 (failover) 합니다.
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    이 절차의 이전 부분에서 설명한 것 처럼 중앙 관리 저장소 상태를 확인 하기 위해 수행 하는 단계는 universal이 아니므로 중앙 관리 저장소에서 아직 완전히 장애 조치 (failover) 되지 않았으므로이 cmdlet이 실패할 수도 있습니다. 이 경우 표시 되는 오류 메시지를 기반으로 중앙 관리 저장소를 수정한 다음이 cmdlet을 다시 실행 해야 합니다.
    
    다음 오류 메시지가 표시되는 경우에는 이 사이트의 에지 풀이 다음 홉으로 다른 풀을 사용하도록 변경한 후에 풀을 장애 조치(failover)해야 합니다. 자세한 내용은 이 항목 첫 부분의 절차를 참조하십시오.
    
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

