---
title: 풀 장애 극복 및 복구
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: .
ms.openlocfilehash: 0b1f79ff40584c82d6da603ede49004f3c0c8968
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675040"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>비즈니스용 Skype 서버 풀 장애 조치(failover) 및 장애 복구(failover)

단일 Front-End 풀이 실패하고 장애 조치(failover)해야 하거나 재해가 발생한 풀이 다시 온라인 상태가 되어 배포를 일반 작업 상태로 복원해야 하는 경우 다음 절차를 사용합니다. 비즈니스용 Skype 페더레이션 또는 XMPP 페더레이션에 사용되는 Edge 풀을 장애 조치(failover)하고 장애 복구(failback)하거나 Front-End 풀과 연결된 Edge 풀을 변경하는 방법을 알아봅니다.

- [프런트 엔드 풀 장애 조치(failover)](#fail-over-a-front-end-pool)
- [풀 장애 복구](#fail-back-a-pool)
- [비즈니스용 Skype 서버 페더레이션에 사용되는 Edge 풀 장애 조치(failover)](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [비즈니스용 Skype 서버 XMPP 페더레이션에 사용되는 Edge 풀 장애 조치(failover)](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [비즈니스용 Skype 서버 페더레이션 또는 XMPP 페더레이션에 사용되는 Edge 풀 장애 복구](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [프런트 엔드 풀과 연결된 Edge 풀 변경](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>Front-End 풀 장애 조치(failover)

Datacenter1에 Pool1이 포함되어 있으며 Pool1이 실패했습니다. Datacenter2에 있는 Pool2로 장애 조치합니다.

풀 장애 조치(failover)에 대한 대부분의 작업에는 필요한 경우 중앙 관리 저장소를 장애 조치(failover)하는 작업이 포함됩니다. 풀의 사용자가 장애 조치(failover)될 때 중앙 관리 저장소가 작동해야 합니다.

Front-End 풀이 실패하지만 해당 사이트의 Edge 풀이 계속 실행 중인 경우 Edge 풀에서 실패한 풀을 다음 홉 풀로 사용하는지 여부를 알고 있어야 합니다. 이 경우 실패한 Front-End 풀을 장애 조치하기 전에 다른 Front-End 풀을 사용하도록 Edge 풀을 변경해야 합니다. 다음 홉 설정을 변경하는 방법은 에지가 에지 풀과 같은 사이트의 풀을 사용하는지 아니면 다른 사이트의 풀을 사용하는지에 따라 달라집니다.

**동일한 사이트에서 다음 홉 풀을 사용하도록 Edge 풀을 설정하려면**

1. 토폴로지 작성기를 열고 변경해야 하는 Edge 풀을 마우스 오른쪽 단추로 클릭하고 **속성 편집** 을 선택합니다.

2. **다음 홉** 을 선택합니다. **다음 홉 풀:** 목록에서 이제 다음 홉 풀로 사용할 풀을 선택합니다.

3. **확인을** 선택한 다음 변경 내용을 게시합니다.

**다른 사이트에서 다음 홉 풀을 사용하도록 Edge 풀을 설정하려면**

1. 비즈니스용 Skype 서버 관리 셸 창을 열고 다음 cmdlet을 입력합니다.

    ```powershell
    Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>
    ```

**재해에서 풀을 장애 조치하려면**

1. Pool2의 Front-End 서버에 다음 cmdlet을 입력하여 중앙 관리 서버에 대한 호스트 풀을 찾습니다.

    ```powershell
    Invoke-CsManagementServerFailover -Whatif
    ```

    이 cmdlet의 결과는 현재 중앙 관리 서버를 호스트하는 풀을 보여 줍니다. 이 절차의 나머지 단계에서는 이 풀을 CMS\_풀이라고 합니다.

2. 토폴로지 작성기를 사용하여 CMS\_풀에서 실행되는 비즈니스용 Skype 서버 버전을 찾습니다. 비즈니스용 Skype 서버 실행하는 경우 다음 cmdlet을 사용하여 풀 1의 백업 풀을 찾습니다.

    ```powershell
    Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    ```

    백업 풀이 백업\_풀이 되도록 합니다.

3. 다음 cmdlet을 사용하여 중앙 관리 저장소의 상태를 확인합니다.

    ```powershell
    Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
    ```

    이 cmdlet은 ActiveMasterFQDN과 ActiveFileTransferAgent가 모두 CMS\_풀의 FQDN을 가리키고 있음을 보여 줍니다. 비어 있는 경우 중앙 관리 서버를 사용할 수 없으므로 장애 조치(failover)해야 합니다.

4.  중앙 관리 저장소를 사용할 수 없거나 중앙 관리 저장소가 Pool1에서 실행되고 있는 경우(즉, 실패한 풀) 풀을 장애 조치(failover)하기 전에 중앙 관리 서버를 장애 조치해야 합니다. 비즈니스용 Skype 서버 실행하는 풀에서 호스트된 중앙 관리 서버를 장애 조치(failover)해야 하는 경우 이 절차의 5단계에서 cmdlet을 사용합니다. 중앙 관리 서버를 장애 조치(failover)할 필요가 없는 경우 이 절차의 7단계로 건너뜁니다.

5.  비즈니스용 Skype 서버 실행되는 풀에서 중앙 관리 저장소를 장애 조치하려면 다음을 수행합니다.

    1. 먼저 다음을 입력하여 중앙 관리 저장소의 주 인스턴스를 실행하는 백업\_풀의 Back-End 서버를 확인합니다.

        ```powershell
        Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
        ```
    
    1. 백업\_풀의 주 Back-End 서버가 보안 주 서버인 경우 다음을 입력합니다.

        ```powershell        
        Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        ```
        
    1. 백업\_풀의 미러 Back-End 서버가 보안 주체인 경우 다음을 입력합니다.
    
        ```powershell
        Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
        ```
    
    1. 중앙 관리 서버 장애 조치(failover)가 완료되었는지 확인합니다. 다음 명령을 입력합니다.
    
        ```powershell    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        ActiveMasterFQDN 및 ActiveFileTransferAgent가 모두 백업\_풀의 FQDN을 가리키는지 확인합니다.
    
    1. 마지막으로 다음을 입력하여 모든 Front-End 서버에 대한 복제본 상태를 확인합니다.
        
        ```powershell
        Get-CsManagementStoreReplicationStatus 
        ```
        
        모든 복제본의 값이 True인지 확인합니다.
        
        이 절차의 7단계로 건너뜁니다.

6.  백업\_풀의 백 엔드 서버에 중앙 관리 저장소를 설치합니다.
    
    1. 먼저 다음 명령을 실행합니다.

        ```powershell
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
    1. 백업\_풀의 프런트 엔드 서버 중 하나에서 다음 명령을 실행하여 중앙 관리 저장소를 강제로 이동합니다.

        ```powershell
        Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force
        ```
    
    1. 이동이 완료되었는지 확인합니다.

        ```powershell
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus
        ```
        
        ActiveMasterFQDN 및 ActiveFileTransferAgent가 모두 백업\_풀의 FQDN을 가리키는지 확인합니다.
    
    1. 다음을 입력하여 모든 프런트 엔드 서버의 복제 상태를 확인합니다.

        ```powershell
        Get-CsManagementStoreReplicationStatus
        ```
        
        모든 복제본의 값이 True인지 확인합니다.
    
    1. 백업\_풀의 나머지 프런트 엔드 서버에 중앙 관리 서버 서비스를 설치합니다. 이렇게 하려면 이 절차의 앞부분에서 중앙 관리 저장소를 강제로 이동할 때 사용한 서버를 제외하고 모든 프런트 엔드 서버에서 다음 명령을 실행합니다.

        ```console
        Bootstrapper /Setup
        ```

7.  비즈니스용 Skype 서버 관리 셸 창에서 다음 cmdlet을 실행하여 Pool1에서 Pool2로 사용자를 장애 조치합니다.

    ```powershell
    Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    ```
    
    중앙 관리 저장소 상태를 확인하기 위해 이 절차의 이전 부분에서 수행한 단계가 범용이 아니므로 중앙 관리 저장소가 아직 완전히 장애 조치되지 않았기 때문에 이 cmdlet이 실패할 가능성이 있습니다. 이 경우 표시되는 오류 메시지에 따라 중앙 관리 저장소를 수정한 다음 이 cmdlet을 다시 실행해야 합니다.
    
    다음 오류 메시지가 표시되는 경우에는 이 사이트의 에지 풀이 다음 홉으로 다른 풀을 사용하도록 변경한 후에 풀을 장애 조치(failover)해야 합니다. 자세한 내용은 이 항목 첫 부분의 절차를 참조하십시오.
    
    ```console
    Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
    topology as the next hop for the Edge server. Failing over this pool may cause External
    access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
    change the Edge internal next hop setting to point to a different Front-end pool,  before you
    proceed.
    ```


## <a name="fail-back-a-pool"></a>풀 장애 복구

재해가 발생한 풀을 다시 온라인으로 전환한 후(이 예의 Pool1) 다음 단계에 따라 배포를 일반 작업 상태로 복원합니다.

장애 복구 프로세스를 완료하는 데 몇 분 정도 걸립니다. 참조를 위해 20,000명의 사용자 풀에 대해 최대 60분이 소요될 것으로 예상됩니다.

다음 cmdlet을 사용해서 원래 Pool1에 있다가 Pool2로 장애 조치(Failover)되었던 사용자를 복구(Failback)합니다.

```powershell
Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose
```

다른 단계는 필요하지 않습니다. 중앙 관리 서버를 장애 조치(failover)한 경우 Pool2에 그대로 둘 수 있습니다.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>비즈니스용 Skype 서버 페더레이션에 사용되는 Edge 풀 장애 조치(failover) 

페더레이션을 구성한 비즈니스용 Skype 서버 Edge 풀이 다운되면 페더레이션이 작동하려면 다른 Edge 풀을 사용하도록 페더레이션을 변경해야 합니다.

1.  프런트 엔드 서버에서 토폴로지 작성기를 엽니다. **Edge 풀을 확장한** 다음 현재 페더레이션에 대해 구성된 Edge 서버 또는 Edge 서버 풀을 마우스 오른쪽 단추로 클릭합니다. **속성 편집** 을 선택합니다.

2.  **일반** 아래의 **속성 편집** 에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 의 선택을 취소합니다. **확인** 을 선택합니다.

3.  **Edge 풀을 확장한** 다음 이제 페더레이션에 사용할 Edge 서버 또는 Edge 서버 풀을 마우스 오른쪽 단추로 클릭합니다. **에지 속성** 을 선택합니다.

4.  **일반** 아래의 **속성 편집** 에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 을 선택합니다. **확인** 을 선택합니다.

5.  **작업을** 선택하고 **토폴로지**, **게시** 를 선택합니다. **토폴로지 게시** 에 대한 메시지가 표시되면 **다음** 을 선택합니다. 게시가 완료되면 **마침** 을 선택합니다.

6.  Edge 서버에서 비즈니스용 Skype 서버 배포 마법사를 엽니다. **비즈니스용 Skype 서버 시스템 설치 또는 업데이트를** 선택한 다음, **비즈니스용 Skype 서버 구성 요소 설정 또는 제거를** 선택합니다. **다시 실행을** 선택합니다.

7.  **다음** 을 선택합니다. 요약 화면에 실행되는 작업이 표시됩니다. 배포가 완료되면 **로그 보기를** 선택하여 사용 가능한 로그 파일을 봅니다. **마침** 을 선택하여 배포를 완료합니다.
    
    실패한 Edge 풀이 포함된 사이트에 여전히 실행 중인 프런트 엔드 서버가 포함된 경우 이러한 Front-End 풀에서 웹 회의 서비스 및 A/V 회의 서비스를 업데이트하여 여전히 실행 중인 원격 사이트의 Edge 풀을 사용해야 합니다. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>비즈니스용 Skype 서버 XMPP 페더레이션에 사용되는 Edge 풀 장애 조치(failover) 

조직에는 XMPP 페더레이션에 사용할 풀로 하나의 에지 풀이 지정됩니다. 이 풀이 다운되면 XMPP 페더레이션이 다시 작동하기 전에 다른 에지 풀을 사용하도록 XMPP 페더레이션을 장애 조치(failover)해야 합니다.

에지 풀을 처음 설치하고 XMPP 페더레이션을 사용하도록 설정할 때는 XMPP 페더레이션용으로 모든 에지 풀에 대해 하나가 아니라 여러 개의 외부 DNS SRV 레코드를 설정하여 재해 복구 프로세스를 간소화할 수 있습니다. 이러한 각 SRV 레코드에는 우선 순위를 다르게 설정해야 합니다. 모든 XMPP 페더레이션 트래픽은 우선 순위가 가장 높은 SRV 레코드가 포함된 풀을 통과합니다. 

다음 절차에서 EdgePool1은 원래 XMPP 페더레이션을 호스팅한 풀이고, EdgePool2는 이제 XMPP 페더레이션을 호스트할 풀입니다.
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>XMPP 페더레이션에 사용되는 Edge 풀을 장애 조치하려면

1.  다른 Edge 풀이 아직 배포되지 않은 경우(현재 다운된 풀 외에) 해당 풀을 배포합니다. 

2.  이제 XMPP 페더레이션을 호스팅할 새로운 에지 풀(EdgePool2)의 각 에지 서버에서 다음 cmdlet을 실행합니다.

    ```powershell
    Stop-CsWindowsService
    ```

3.  다음 cmdlet을 실행하여 XMPP 페더레이션 경로를 다시 EdgePool2로 지정합니다.

    ```powershell
    Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    ```
    
    이 예에서 Site2는 XMPP 페더레이션 경로를 이제 호스팅할 에지 풀이 포함된 사이트입니다. EdgeServer2.contoso.com은 이 풀에 있는 에지 서버의 FQDN입니다.

4.  외부 DNS 서버에서 XMPP 페더레이션용 DNS A 레코드를 EdgeServer2.contoso.com을 가리키도록 변경합니다.

5.  이제 XMPP 페더레이션을 호스팅할 에지 풀로 확인되는 XMPP 페더레이션용 DNS SRV 레코드가 없으면 다음 예에 표시된 것처럼 지금 추가해야 합니다. 이 SRV 레코드는 포트 값 5269를 포함해야 합니다.

    ```console
    _xmpp-server._tcp.contoso.com
    ```

6.  이제 XMPP 페더레이션을 호스팅할 에지 풀의 포트 5269가 외부적으로 열려 있는지 확인합니다.

7.  이제 XMPP 페더레이션을 호스팅할 에지 풀의 모든 에지 서버에서 서비스를 시작합니다.

    ```powershell
    Start-CsWindowsService
    ```

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>비즈니스용 Skype 서버 페더레이션 또는 XMPP 페더레이션에 사용되는 Edge 풀 장애 복구 

페더레이션을 호스트하는 데 사용된 실패한 Edge 풀이 다시 온라인 상태가 된 후 이 절차를 사용하여 복원된 에지 풀을 다시 사용하도록 비즈니스용 Skype 서버 페더레이션 경로 및/또는 XMPP 페더레이션 경로를 장애 복구합니다.

1.  이제 다시 사용할 수 있는 Edge 풀에서 Edge 서비스를 시작합니다.

2.  복원된 에지 서버를 사용하도록 비즈니스용 Skype 서버 페더레이션 경로를 장애 복구하려면 다음을 수행합니다.
    
    1. 프런트 엔드 서버에서 토폴로지 작성기를 엽니다. **Edge 풀을 확장한** 다음 현재 페더레이션에 대해 구성된 Edge 서버 또는 Edge 서버 풀을 마우스 오른쪽 단추로 클릭합니다. **속성 편집** 을 선택합니다.
    
    1. **일반** 아래의 **속성 편집** 에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 의 선택을 취소합니다. **확인** 을 선택합니다.
    
    1. **Edge 풀을 확장한** 다음 페더레이션에 다시 사용할 원래 Edge 서버 또는 Edge 서버 풀을 마우스 오른쪽 단추로 클릭합니다. **에지 속성** 을 선택합니다.
    
    1. **일반** 아래의 **속성 편집** 에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 을 선택합니다. **확인** 을 선택합니다.
    
    1. **작업을** 선택하고 **토폴로지**, **게시** 를 선택합니다. **토폴로지 게시** 에 대한 메시지가 표시되면 **다음** 을 선택합니다. 게시가 완료되면 **마침** 을 선택합니다.
    
    1. Edge 서버에서 비즈니스용 Skype 서버 배포 마법사를 엽니다. **비즈니스용 Skype 서버 시스템 설치 또는 업데이트를** 선택한 다음 설치 **또는 제거 비즈니스용 Skype 서버 구성 요소를** 선택합니다. **다시 실행을** 선택합니다.
    
    1. **다음** 을 선택합니다. 요약 화면에 실행되는 작업이 표시됩니다. 배포가 완료되면 **로그 보기를** 선택하여 사용 가능한 로그 파일을 봅니다. **마침** 을 선택하여 배포를 완료합니다.

3.  복원된 Edge Server를 사용하도록 XMPP 페더레이션 경로를 장애 복구하려면 다음을 수행합니다.
    
    1. 다음 cmdlet을 실행하여 XMPP 페더레이션을 호스트할 Edge 풀에 대한 XMPP 페더레이션 경로를 다시 지정합니다(이 예제에서는 EdgeServer1).
  
        ```powershell
        Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        ```
        
        이 예제에서 Site1은 이제 XMPP 페더레이션 경로를 호스트할 Edge 풀을 포함하는 사이트이며, EdgeServer1.contoso.com 해당 풀에 있는 Edge Server의 FQDN입니다.
    
    1. 이제 XMPP 페더레이션을 호스팅할 에지 풀로 확인되는 XMPP 페더레이션용 DNS SRV 레코드가 없으면 다음 예에 표시된 것처럼 지금 추가해야 합니다. 이 SRV 레코드는 포트 값 5269를 포함해야 합니다.

        ```console
        _xmpp-server._tcp.contoso.com
        ```
    
    1. 외부 DNS 서버에서 XMPP 페더레이션용 DNS A 레코드를 EdgeServer2.contoso.com을 가리키도록 변경합니다.
    
    1. 이제 XMPP 페더레이션을 호스팅할 에지 풀의 포트 5269가 외부적으로 열려 있는지 확인합니다.

4.  실패하고 복원된 Edge 풀이 포함된 사이트에서 프런트 엔드 풀이 계속 실행되고 있는 경우 이러한 프런트 엔드 풀에서 웹 회의 서비스 및 A/V 회의 서비스를 업데이트하여 로컬 사이트의 Edge 풀을 다시 사용해야 합니다.

5.  실패한 Edge 풀과 동일한 사이트의 프런트 엔드 풀도 실패한 경우 이제 Invoke-CsPoolFailback을 사용하여 프런트 엔드 풀을 장애 복구할 수 있습니다.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>프런트 엔드 풀과 연결된 Edge 풀 변경

에지 풀이 다운되었는데 동일 사이트의 프런트 엔드 풀은 계속 실행되는 경우에는 오류가 발생한 에지 풀을 복원하는 동안 다른 사이트의 에지 풀을 사용하도록 프런트 엔드 풀을 설정해야 합니다.

1.  토폴로지 작성기에서 변경해야 하는 프런트 엔드 풀의 이름을 탐색합니다.

2.  풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집** 을 선택합니다.

3.  **연결** 섹션의 **에지 풀 연결(미디어 구성 요소)** 에서 드롭다운 상자를 사용하여 이 프런트 엔드 풀과 연결할 에지 풀을 선택합니다.

4.  **확인** 을 선택합니다.
