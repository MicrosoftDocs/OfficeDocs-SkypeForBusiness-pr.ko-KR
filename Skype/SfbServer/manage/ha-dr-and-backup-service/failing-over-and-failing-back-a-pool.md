---
title: 풀 장애 극복 및 복구
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: d5409441336ef2af8bbe9c6a39530584a167ec05
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818209"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 풀 장애 조치 및 장애 복구 

단일 프런트 엔드 풀에 실패 하 여 장애 조치를 수행 해야 하거나 재해가 발생 한 풀이 온라인 상태가 되는 경우 배포를 정상 작업 상태로 복원 해야 하는 경우 다음 절차를 사용 합니다. 또한 비즈니스용 Skype 페더레이션 또는 XMPP 페더레이션에 사용 되는 Edge 풀을 장애 조치 및 장애 복구 하는 방법과 프런트 엔드 풀에 연결 된 Edge 풀을 변경 하는 방법에 대해 알아봅니다.

- [프런트 엔드 풀을 통해 장애 조치](#fail-over-a-front-end-pool)
- [풀 장애 복구](#fail-back-a-pool)
- [비즈니스용 Skype Server federation에 사용 되는 Edge 풀을 통해 장애 조치](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [비즈니스용 Skype 서버에서 XMPP 페더레이션에 사용 되는 Edge 풀을 통해 장애 조치](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [비즈니스용 Skype Server federation 또는 XMPP 페더레이션에 사용 되는 Edge 풀을 복구 합니다.](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [프런트 엔드 풀에 연결 된 Edge 풀 변경](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>프런트 엔드 풀을 통해 장애 조치

이 절차에서는 Datacenter1에 Pool1이 포함 되어 있고 Pool1에 오류가 발생 했습니다. Datacenter2에 위치한 Pool2로 장애 조치 (failover) 합니다.

필요한 경우 풀 장애 조치 (failover)에 대 한 대부분의 작업은 중앙 관리 저장소를 통해 실패 하 게 됩니다. 이는 풀의 사용자가 장애 조치를 할 때 중앙 관리 저장소가 작동 해야 하기 때문에 중요 합니다.

또한 프런트 엔드 풀에는 실패 하지만 해당 사이트의 Edge 풀은 계속 실행 되는 경우에는 Edge 풀이 다음 홉 풀로 실패 한 풀을 사용 하는지 여부를 알아야 합니다. 이 경우 실패 한 프런트 엔드 풀을 장애 조치 (failover) 하기 전에 다른 프런트 엔드 풀을 사용 하도록 Edge 풀을 변경 해야 합니다. 다음 홉 설정을 변경 하는 방법은 Edge가 Edge 풀과 동일한 사이트의 풀을 사용할지 아니면 다른 사이트에 있는지에 따라 달라 집니다.

**같은 사이트에서 다음 홉 풀을 사용 하도록 Edge 풀 설정**

1.  토폴로지 작성기를 열고 변경 해야 하는 Edge 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

2.  **다음 홉**을 클릭 합니다. **다음 홉 풀:** 목록에서 이제 다음 홉 풀 역할을 할 풀을 선택 합니다.

3.  **확인**을 클릭 한 다음 변경 내용을 게시 합니다.

**다른 사이트에서 다음 홉 풀을 사용 하도록 Edge 풀을 설정 하려면**

1.  비즈니스용 Skype Server Management Shell 창을 열고 다음 cmdlet을 입력 합니다.
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**재해에 따라 풀을 장애 조치**

1.  Pool2의 프런트 엔드 서버에 다음 cmdlet을 입력 하 여 중앙 관리 서버의 호스트인 풀을 찾습니다.
    
        Invoke-CsManagementServerFailover -Whatif
    
    이 cmdlet의 결과에는 현재 중앙 관리 서버를 호스트 하는 풀이 표시 됩니다. 이 절차의 나머지 부분에서는이 풀을 CMS\_풀 이라고 합니다.

2.  토폴로지 작성기를 사용 하 여 CMS\_풀에서 실행 되는 비즈니스용 Skype 서버의 버전을 찾습니다. 비즈니스용 Skype 서버를 실행 하는 경우 다음 cmdlet을 사용 하 여 풀 1의 백업 풀을 찾습니다.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    \_백업 풀을 백업 풀로 사용 합니다.

3.  다음 cmdlet을 사용 하 여 중앙 관리 저장소의 상태를 확인 합니다.
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    이 cmdlet은 ActiveMasterFQDN 및 ActiveFileTransferAgents 모두 CMS\_풀의 FQDN을 가리키지만을 표시 합니다. 비어 있는 경우 중앙 관리 서버를 사용할 수 없으며 장애 조치를 수행 해야 합니다.

4.  중앙 관리 저장소를 사용할 수 없거나 중앙 관리 저장소가 Pool1 (즉, 실패 한 풀)에서 실행 되는 경우에는 풀을 통해 실패 하기 전에 중앙 관리 서버를 장애 조치 해야 합니다. 비즈니스용 Skype Server를 실행 하는 풀에 호스트 된 중앙 관리 서버를 장애 조치 해야 하는 경우이 절차의 5 단계에서 cmdlet을 사용 합니다. 중앙 관리 서버를 장애 조치할 필요가 없는 경우에는이 절차의 7 단계로 건너뛰십시오.

5.  비즈니스용 Skype Server를 실행 하는 풀의 중앙 관리 저장소를 장애 조치 하려면 다음을 수행 합니다.
    
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
        ```PowerShell
         
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

7.  비즈니스용 Skype 서버 관리 셸 창에서 다음 cmdlet을 실행 하 여 Pool1에서 Pool2로 사용자를 장애 조치 합니다.
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    중앙 관리 저장소 상태를 검사 하는이 절차의 이전 부분에서 수행 된 단계는 유니버설 하지 않기 때문에 중앙 관리 저장소가 아직 완전히 장애 조치 되지 않아이 cmdlet이 실패할 수도 있습니다. 이 경우 표시 되는 오류 메시지를 기반으로 중앙 관리 저장소를 수정한 다음이 cmdlet을 다시 실행 해야 합니다.
    
    다음 오류 메시지가 표시 되는 경우 풀을 장애 인하기 전에 다음 홉으로 다른 풀을 사용 하도록이 사이트에서 Edge 풀을 변경 해야 합니다. 자세한 내용은이 항목의 시작 부분에 나오는 절차를 참조 하세요.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>풀 장애 복구

재해가 발생 한 풀이 온라인 상태가 된 후 (즉,이 예제에서 Pool1) 다음 단계를 수행 하 여 배포를 정상 작업 상태로 복원 합니다.

장애 복구 프로세스가 완료 되기까지 몇 분이 소요 됩니다.참조용으로 2만 사용자 풀에 대해 최대 60 분이 소요 될 것으로 예상 됩니다.

Pool1에서 원래 홈 이었던 사용자와 다음 cmdlet을 입력 하 여 Pool2에 장애 조치 (Fail over)를 다시 실행 합니다.
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

다른 단계는 필요 하지 않습니다. 중앙 관리 서버를 장애 조치 (Pool2) 한 경우에는 그대로 둘 수 있습니다.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>비즈니스용 Skype Server federation에 사용 되는 Edge 풀을 통해 장애 조치 

비즈니스용 Skype 서버 페더레이션이 구성 된 Edge 풀을 사용할 수 없는 경우 페더레이션에서 다른 Edge 풀을 사용 하도록 페더레이션을 변경 해야 합니다.

1.  프런트 엔드 서버에서 토폴로지 작성기를 엽니다. **Edge 풀**을 확장 한 다음 현재 페더레이션에 대해 구성 되어 있는 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다. **속성 편집**을 선택 합니다.

2.  **일반**아래의 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 취소 합니다. **확인**을 클릭합니다.

3.  **Edge 풀**을 확장 한 다음 현재 페더레이션에 사용할 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다. **속성 편집**을 선택 합니다.

4.  **일반**아래에서 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 합니다. **확인**을 클릭합니다.

5.  **작업**을 클릭 하 고 **토폴로지**를 선택한 다음 **게시**를 선택 합니다. **토폴로지를 게시할**것인지 묻는 메시지가 표시 되 면 **다음**을 클릭 합니다. 게시가 완료 되 면 **마침을**클릭 합니다.

6.  Edge 서버에서 비즈니스용 Skype 서버 배포 마법사를 엽니다. **비즈니스용 Skype 서버 시스템 설치 또는 업데이트**를 클릭 한 다음 설정을 클릭 **하거나 비즈니스용 Skype 서버 구성 요소를 제거**합니다. **다시 실행**을 클릭 합니다.

7.  **다음**을 클릭 합니다. 요약 화면에 실행 되는 작업이 표시 됩니다. 배포가 완료 되 면 **로그 보기** 를 클릭 하 여 사용 가능한 로그 파일을 봅니다. **마침을** 클릭 하 여 배포를 완료 합니다.
    
    실행 중인 프런트 엔드 서버가 실패 한 Edge 풀을 포함 하는 사이트에 포함 되어 있는 경우, 현재 실행 중인 원격 사이트의 Edge 풀을 사용 하도록 이러한 프런트 엔드 풀의 웹 회의 서비스와 A/V 회의 서비스를 업데이트 해야 합니다. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 XMPP 페더레이션에 사용 되는 Edge 풀을 통해 장애 조치 

조직에서 XMPP 페더레이션에 사용할 풀로 지정 된 하나의 Edge 풀이 있습니다. 이 풀이 중단 되 면 xmpp federation에서 다시 작동할 수 있도록 XMPP federation를 장애 조치 하 여 다른 Edge 풀을 사용 해야 합니다.

Edge 풀을 처음 설치 하 고 XMPP 페더레이션을 사용 하면 XMPP 페더레이션의 모든 Edge 풀에 대해 외부 DNS SRV 레코드를 하나만 설정 하는 것이 아니라 장애 복구 프로세스를 단순화할 수 있습니다. 이러한 각각의 SRV 레코드에는 다른 우선 순위가 설정 되어 있어야 합니다. 모든 XMPP 페더레이션 트래픽은 우선 순위가 가장 높은 SRV 레코드를 사용 하 여 풀을 거칩니다. 

다음 절차에서는 EdgePool1가 원래 XMPP 페더레이션을 호스팅하는 풀 이며, EdgePool2는 이제 XMPP federation를 호스트 하는 풀입니다.


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>XMPP 페더레이션에 사용 되는 Edge 풀을 장애 조치

1.  현재 사용 중인 다른 Edge 풀을 아직 배포 하지 않은 경우에는 해당 풀을 배포 합니다. 

2.  이제 XMPP 페더레이션 (EdgePool2)을 호스트 하는 새 Edge 풀의 각 Edge 서버에서 다음 cmdlet을 실행 합니다.
    
        Stop-CsWindowsService

3.  XMPP 페더레이션 경로를 EdgePool2로 다시 가리키도록 다음 cmdlet을 실행 합니다.
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    이 예제에서 Site2는 이제 XMPP 페더레이션 경로를 호스팅하는 Edge 풀을 포함 하는 사이트 이며, EdgeServer2.contoso.com는 해당 풀에 있는 Edge 서버의 FQDN입니다.

4.  외부 DNS 서버에서 XMPP 페더레이션의 DNS A 레코드를 EdgeServer2.contoso.com를 가리키도록 변경 합니다.

5.  이제 XMPP 페더레이션을 호스트 하는 Edge 풀로 확인 되는 DNS SRV 레코드가 아직 없는 경우 다음 예제와 같이 추가 해야 합니다. 이 SRV 레코드의 포트 값은 5269 이어야 합니다.
    
        _xmpp-server._tcp.contoso.com

6.  이제 XMPP federation host에 호스트 되는 Edge 풀에 포트 5269이 외부적으로 열려 있는지 확인 합니다.

7.  이제 Edge 풀에서 XMPP 페더레이션을 호스트 하는 모든 Edge 서버에서 서비스를 시작 합니다.
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>비즈니스용 Skype Server federation 또는 XMPP 페더레이션에 사용 되는 Edge 풀을 복구 합니다. 

페더레이션을 호스트 하는 데 사용 된 실패 한도 풀이 온라인 상태가 되 면이 절차를 사용 하 여 비즈니스용 Skype Server federation route 및/또는 XMPP 페더레이션 경로를 다시 실행 하 여 복원 된이 Edge 풀을 사용 합니다.

1.  지금 다시 사용할 수 있는 Edge 풀에서 Edge 서비스를 시작 합니다.

2.  복원 된 Edge 서버를 사용 하기 위해 비즈니스용 Skype 서버 페더레이션 경로를 장애 복구 하려면 다음을 수행 합니다.
    
      - 프런트 엔드 서버에서 토폴로지 작성기를 엽니다. **Edge 풀**을 확장 한 다음, 현재 페더레이션에 대해 구성 된 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다. **속성 편집**을 선택 합니다.
    
      - **일반**아래의 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 취소 합니다. **확인**을 클릭합니다.
    
      - **Edge 풀**을 확장 한 다음 페더레이션에 사용할 원본 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다. **속성 편집**을 선택 합니다.
    
      - **일반**아래에서 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 합니다. **확인**을 클릭합니다.
    
      - **작업**을 클릭 하 고 **토폴로지**를 선택한 다음 **게시**를 선택 합니다. **토폴로지를 게시할**것인지 묻는 메시지가 표시 되 면 **다음**을 클릭 합니다. 게시가 완료 되 면 **마침을**클릭 합니다.
    
      - Edge 서버에서 비즈니스용 Skype 서버 배포 마법사를 엽니다. **비즈니스용 Skype 서버 시스템 설치 또는 업데이트**를 클릭 한 다음 **설정 또는 비즈니스용 Skype 서버 구성 요소 제거**를 클릭 합니다. **다시 실행**을 클릭 합니다.
    
      - **다음**을 클릭 합니다. 요약 화면에 실행 되는 작업이 표시 됩니다. 배포가 완료 되 면 **로그 보기** 를 클릭 하 여 사용 가능한 로그 파일을 봅니다. **마침을** 클릭 하 여 배포를 완료 합니다.

3.  XMPP 페더레이션 경로를 장애 복구 하 여 복원 된 Edge 서버를 사용 하려는 경우 다음을 수행 합니다.
    
      - 다음 cmdlet을 실행 하 여 XMPP 페더레이션 경로를 다시 지정 합니다. 이제 XMPP 페더레이션 (이 예제에서는 EdgeServer1)을 호스트 하는 Edge 풀을 가리킵니다.
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        이 예제에서 Site1는 이제 XMPP 페더레이션 경로를 호스팅하는 Edge 풀을 포함 하는 사이트 이며, EdgeServer1.contoso.com는 해당 풀에 있는 Edge 서버의 FQDN입니다.
    
      - 이제 XMPP 페더레이션을 호스트 하는 Edge 풀로 확인 되는 DNS SRV 레코드가 아직 없는 경우 다음 예제와 같이 추가 해야 합니다. 이 SRV 레코드의 포트 값은 5269 이어야 합니다.
        
            _xmpp-server._tcp.contoso.com
    
      - 외부 DNS 서버에서 XMPP 페더레이션의 DNS A 레코드를 EdgeServer2.contoso.com를 가리키도록 변경 합니다.
    
      - 이제 XMPP federation host에 호스트 되는 Edge 풀에 포트 5269이 외부적으로 열려 있는지 확인 합니다.

4.  실패 한 Edge 풀을 포함 하는 사이트에서 프런트 엔드 풀이 계속 실행 되 고 있는 경우에는 이러한 프런트 엔드 풀의 웹 회의 서비스와 A/V 회의 서비스를 업데이트 하 여 로컬 사이트의 Edge 풀을 다시 사용 해야 합니다.

5.  실패 한 Edge 풀과 동일한 사이트의 프런트 엔드 풀에도 실패 한 경우에는 Invoke – CsPoolFailback를 사용 하 여 프런트 엔드 풀을 실패할 수 있습니다.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>프런트 엔드 풀에 연결 된 Edge 풀 변경

Edge 풀이 작동 하지 않지만 같은 사이트의 프런트 엔드 풀은 계속 실행 되는 경우에는 프런트 엔드 풀을 설정 하 여 실패 한도 풀이 복원 될 때까지 다른 사이트의 Edge 풀을 사용 해야 합니다.

1.  토폴로지 작성기에서 변경 해야 하는 프런트 엔드 풀의 이름으로 이동 합니다.

2.  풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

3.  **연결** 섹션의 **Edge 풀 연결 (미디어 구성 요소)** 에서 드롭다운 상자를 사용 하 여이 프론트 엔드 풀을 연결할 edge 풀을 선택 합니다.

4.  **확인**을 클릭합니다.
