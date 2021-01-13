---
title: 풀 장애 극복 및 복구
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 1ebd4e8110b8783c869530d95eda0646a895b88e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826568"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 풀 장애 조치(fail over) 및 장애 조치(fail back) 

단일 프런트 엔드 풀이 실패하여 복구해야 하는 경우 또는 재해가 발생한 풀이 다시 온라인 상태가 되거나 배포를 일반 작업 상태로 복원해야 하는 경우 다음 절차를 사용하세요. 또한 비즈니스용 Skype 페더ation 또는 XMPP 페더ation에 사용되는 에지 풀을 장애 조치(fail over) 및 장애 조치(fail back)하거나 프런트 엔드 풀과 연결된 에지 풀을 변경하는 방법도 알아보십시오.

- [프런트 엔드 풀 장애 조치(fail over)](#fail-over-a-front-end-pool)
- [풀 장애 조치(fail back)](#fail-back-a-pool)
- [비즈니스용 Skype 서버 페더전에 사용되는 에지 풀 장애 조치(fail over)](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [비즈니스용 Skype 서버에서 XMPP 페더럴에 사용되는 에지 풀 장애 조치(fail over)](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [비즈니스용 Skype 서버 페더ation 또는 XMPP 페더ation에 사용되는 에지 풀 장애 조치(fail back)](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [프런트 엔드 풀과 연결된 에지 풀 변경](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a>프런트 엔드 풀 장애 조치(fail over)

이 절차에서 Datacenter1은 Pool1을 포함하며 Pool1에서 오류가 발생한 상태입니다. Pool1을 Datacenter2에 있는 Pool2로 장애 조치(failover)합니다.

풀 장애 조치(failover)에 대한 대부분의 작업에서는 필요한 경우 중앙 관리 저장소를 장애 조치(failover)합니다. 이는 풀의 사용자가 실패할 때 중앙 관리 저장소가 작동해야 하기 때문에 중요합니다.

또한 프런트 엔드 풀에 오류가 발생했는데 해당 사이트의 에지 풀은 계속 실행되는 경우에는 에지 풀이 오류가 발생한 풀을 다음 홉 풀로 사용하는지 여부를 확인해야 합니다. 오류가 발생한 풀이 다음 홉 풀로 사용되는 경우에는 해당 프런트 엔드 풀을 장애 조치(failover)하기 전에 다른 프런트 엔드 풀을 사용하도록 에지 풀을 변경해야 합니다. 다음 홉 설정을 변경하는 방법은 에지가 에지 풀과 같은 사이트의 풀을 사용하는지 아니면 다른 사이트의 풀을 사용하는지에 따라 달라집니다.

**에지 풀이 동일한 사이트에서 다음 홉 풀을 사용하게 설정**

1.  토폴로지 작성기에서 변경해야 하는 에지 풀을 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 클릭합니다.**

2.  **다음 홉** 을 클릭합니다. **다음 홉 풀:** 목록에서 다음 홉 풀로 사용할 풀을 선택합니다.

3.  **확인** 을 클릭하고 변경 내용을 게시합니다.

**다른 사이트에서 다음 홉 풀을 사용하기 위해 에지 풀을 설정**

1.  비즈니스용 Skype 서버 관리 셸 창을 열고 다음 cmdlet을 입력합니다.
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

**재해에서 풀을 장애 조치(fail over)를 위해**

1.  Pool2의 프런트 엔드 서버에서 다음 cmdlet을 입력하여 중앙 관리 서버의 호스트 풀을 찾을 수 있습니다.
    
        Invoke-CsManagementServerFailover -Whatif
    
    이 cmdlet의 결과에는 중앙 관리 서버를 현재 호스트하는 풀이 표시됩니다. 이 절차의 나머지부분에서 이 풀을 CMS 풀로 \_ 지명합니다.

2.  토폴로지 작성기에서 CMS 풀에서 실행되는 비즈니스용 Skype 서버 버전을 찾을 수 \_ 있습니다. 비즈니스용 Skype 서버를 실행하는 경우 다음 cmdlet을 사용하여 풀 1의 백업 풀을 찾을 수 있습니다.
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    백업 \_ 풀을 백업 풀로 지정합니다.

3.  다음 cmdlet을 통해 중앙 관리 저장소의 상태를 검사합니다.
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    이 cmdlet은 ActiveMasterFQDN과 ActiveFileTransferAgents가 모두 CMS 풀의 FQDN을 지칭하는지 표시해야 \_ 합니다. 이 서버가 비어 있는 경우 중앙 관리 서버를 사용할 수 없습니다.

4.  중앙 관리 저장소를 사용할 수 없는 경우 또는 Pool1에서 중앙 관리 저장소가 실행 중이던 경우(즉, 오류가 있는 풀) 풀을 장애 조치(fail over)하기 전에 중앙 관리 서버를 장애 조치(fail over)해야 합니다. 비즈니스용 Skype 서버를 실행하는 풀에서 호스트된 중앙 관리 서버를 장애 조치(fail over)해야 하는 경우 이 절차의 5단계에서 cmdlet을 사용합니다. 중앙 관리 서버를 장애 조치(fail over)할 필요가 없는 경우 이 절차의 7단계로 건너뜁니 다.

5.  비즈니스용 Skype 서버를 실행하는 풀에서 중앙 관리 저장소를 장애 조치(fail over)를 실행하기 위해 다음을 실행합니다.
    
      - 먼저 다음을 입력하여 백업 풀에서 중앙 관리 저장소의 주 인스턴스를 실행하는 백 엔드 \_ 서버를 검사합니다.
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - 백업 풀의 주 백 엔드 서버가 주 서버인 경우 \_ 다음을 입력합니다.
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        백업 풀의 미러 백 엔드 서버가 주 서버인 경우 \_ 다음을 입력합니다.
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - 중앙 관리 서버 장애 조치(failover)가 완료된지 검사합니다. 다음을 입력합니다.
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN과 ActiveFileTransferAgents가 모두 백업 풀의 FQDN을 지정하는지 \_ 검사합니다.
    
      - 마지막으로 다음을 입력하여 모든 프런트 엔드 서버의 복제본 상태를 검사합니다.
        
            Get-CsManagementStoreReplicationStatus 
        
        모든 복제본의 값이 True인지 확인합니다.
        
        이 절차의 7단계로 건너뜁니다.

6.  백업 풀의 백 엔드 서버에 중앙 관리 저장소를 \_ 설치합니다.
    
      - 먼저 다음 명령을 실행합니다.
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - 백업 풀의 프런트 엔드 서버 중 하나에서 다음 명령을 실행하여 중앙 관리 저장소를 \_ 강제로 이동합니다.
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - 이동이 완료되었는지 확인합니다.
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        ActiveMasterFQDN과 ActiveFileTransferAgents가 모두 백업 풀의 FQDN을 지정하는지 \_ 검사합니다.
    
      - 다음을 입력하여 모든 프런트 엔드 서버의 복제 상태를 확인합니다.
        
            Get-CsManagementStoreReplicationStatus 
        
        모든 복제본의 값이 True인지 확인합니다.
    
      - 백업 풀의 나머지 프런트 엔드 서버에 중앙 관리 서버 서비스를 \_ 설치합니다. 이렇게 하여 이 절차의 앞부분에서 중앙 관리 저장소를 이동하게 할 때 사용한 명령을 제외한 모든 프런트 엔드 서버에서 다음 명령을 실행합니다.
        
            Bootstrapper /Setup 

7.  비즈니스용 Skype 서버 관리 셸 창에서 다음 cmdlet을 실행하여 Pool1에서 Pool2로 사용자를 장애 조치(fail over)합니다.
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    중앙 관리 저장소 상태를 확인하기 위해 이 절차의 이전 부분에서 수행한 단계는 범용이 아니기 때문에 중앙 관리 저장소가 아직 완전히 장애 조치(fail over)되지 않았기 때문에 이 cmdlet이 실패할 가능성이 여전히 있습니다. 이 경우 표시하는 오류 메시지에 따라 중앙 관리 저장소를 수정한 다음 이 cmdlet을 다시 실행해야 합니다.
    
    다음 오류 메시지가 표시되는 경우에는 이 사이트의 에지 풀이 다음 홉으로 다른 풀을 사용하도록 변경한 후에 풀을 장애 조치(failover)해야 합니다. 자세한 내용은 이 항목 첫 부분의 절차를 참조하십시오.
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a>풀 장애 조치(fail back)

재해가 발생한 풀을 다시 온라인으로 전환한 후(이 예의 Pool1) 다음 단계에 따라 배포를 일반 작업 상태로 복원합니다.

복구(Failback) 프로세스는 완료하는 데 몇 분 정도 걸립니다.  일반적으로 사용자가 20,000명인 풀을 복구하는 데에는 최대 60분 정도 소요될 수 있습니다.

다음 cmdlet을 사용해서 원래 Pool1에 있다가 Pool2로 장애 조치(Failover)되었던 사용자를 복구(Failback)합니다.
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

다른 단계는 필요하지 않습니다. 중앙 관리 서버를 실패한 경우 Pool2에 그대로 두면 됩니다.

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a>비즈니스용 Skype 서버 페더전에 사용되는 에지 풀 장애 조치(fail over) 

비즈니스용 Skype 서버 페더전을 구성한 에지 풀이 다운되면 페더전이 작동하려면 다른 에지 풀을 사용하도록 페더전을 변경해야 합니다.

1.  프런트 엔드 서버에서 토폴로지 작성기를 엽니다. **에지 풀을** 확장한 다음 현재 페더ation에 대해 구성된 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다. **속성 편집** 을 선택합니다.

2.  **일반** 아래의 **속성 편집** 에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 의 선택을 취소합니다. **확인** 을 클릭합니다.

3.  **에지 풀을** 확장한 다음 이제 페더전에 사용할 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다. **에지 속성** 을 선택합니다.

4.  **일반** 아래의 **속성 편집** 에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 을 선택합니다. **확인** 을 클릭합니다.

5.  **작업** 을 클릭하고, **토폴로지**, **게시** 를 차례로 클릭합니다. **토폴로지 게시** 프롬프트가 표시되면 **다음** 을 클릭합니다. 게시가 완료되면 **마침** 을 클릭합니다.

6.  에지 서버에서 비즈니스용 Skype 서버 배포 마법사를 여십시오. 비즈니스용 **Skype 서버** 시스템 설치 또는 업데이트를 클릭한 다음 비즈니스용 Skype 서버 구성 요소 설치 또는 **제거를 클릭합니다.** **다시 실행** 을 클릭합니다.

7.  **다음** 을 클릭합니다. 요약 화면에 실행되는 작업이 표시됩니다. 배포가 완료되었으면 **로그 보기** 를 클릭하여 사용 가능한 로그 파일을 확인합니다. **마침** 을 클릭하여 배포를 완료합니다.
    
    실패한 에지 풀을 포함하는 사이트에 아직 실행 중인 프런트 엔드 서버가 포함된 경우 아직 실행 중인 원격 사이트의 에지 풀을 사용하도록 해당 프런트 엔드 풀에서 웹 회의 서비스 및 A/V 회의 서비스를 업데이트해야 합니다. 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 XMPP 페더럴에 사용되는 에지 풀 장애 조치(fail over) 

조직에는 XMPP 페더레이션에 사용할 풀로 하나의 에지 풀이 지정됩니다. 이 풀이 다운되면 XMPP 페더레이션이 다시 작동하기 전에 다른 에지 풀을 사용하도록 XMPP 페더레이션을 장애 조치(failover)해야 합니다.

에지 풀을 처음 설치하고 XMPP 페더레이션을 사용하도록 설정할 때는 XMPP 페더레이션용으로 모든 에지 풀에 대해 하나가 아니라 여러 개의 외부 DNS SRV 레코드를 설정하여 재해 복구 프로세스를 간소화할 수 있습니다. 이러한 각 SRV 레코드에는 우선 순위를 다르게 설정해야 합니다. 모든 XMPP 페더레이션 트래픽은 우선 순위가 가장 높은 SRV 레코드가 포함된 풀을 통과합니다. 

다음 절차에서 EdgePool1은 원래 XMPP 페더레이션을 호스팅한 풀이고 EdgePool2는 XMPP 페더레이션을 이제 호스팅할 풀입니다.


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a>XMPP 페더럴에 사용되는 에지 풀을 장애 조치(fail over)를 사용

1.  아직 다른 에지 풀을 배포하지 않았으면(현재 다운된 에지 풀과 별도) 해당 풀을 배포합니다. 

2.  이제 XMPP 페더레이션을 호스팅할 새로운 에지 풀(EdgePool2)의 각 에지 서버에서 다음 cmdlet을 실행합니다.
    
        Stop-CsWindowsService

3.  다음 cmdlet을 실행하여 XMPP 페더레이션 경로를 다시 EdgePool2로 지정합니다.
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    이 예에서 Site2는 XMPP 페더레이션 경로를 이제 호스팅할 에지 풀이 포함된 사이트입니다. EdgeServer2.contoso.com은 이 풀에 있는 에지 서버의 FQDN입니다.

4.  외부 DNS 서버에서 XMPP 페더레이션용 DNS A 레코드를 EdgeServer2.contoso.com을 가리키도록 변경합니다.

5.  이제 XMPP 페더레이션을 호스팅할 에지 풀로 확인되는 XMPP 페더레이션용 DNS SRV 레코드가 없으면 다음 예에 표시된 것처럼 지금 추가해야 합니다. 이 SRV 레코드는 포트 값 5269를 포함해야 합니다.
    
        _xmpp-server._tcp.contoso.com

6.  이제 XMPP 페더레이션을 호스팅할 에지 풀의 포트 5269가 외부적으로 열려 있는지 확인합니다.

7.  이제 XMPP 페더레이션을 호스팅할 에지 풀의 모든 에지 서버에서 서비스를 시작합니다.
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a>비즈니스용 Skype 서버 페더ation 또는 XMPP 페더ation에 사용되는 에지 풀 장애 조치(fail back) 

페더럴을 호스팅하는 데 사용된 실패한 에지 풀이 다시 온라인으로 되돌아온 후 이 절차에 따라 비즈니스용 Skype 서버 페더ation 경로 및/또는 XMPP 페더임 경로를 장애 복구(fail back)하여 복원된 에지 풀을 다시 사용합니다.

1.  이제 다시 사용할 수 있는 에지 풀에서 에지 서비스를 시작하십시오.

2.  복원된 에지 서버를 사용하기 위해 비즈니스용 Skype 서버 페더ation 경로를 장애 복구(fail back)하려는 경우 다음을 실행합니다.
    
      - 프런트 엔드 서버에서 토폴로지 작성기를 엽니다. **에지 풀** 을 확장하고 현재 페더레이션에 대해 구성된 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다. **속성 편집** 을 선택합니다.
    
      - **일반** 아래의 **속성 편집** 에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 의 선택을 취소합니다. **확인** 을 클릭합니다.
    
      - **에지 풀을** 확장한 다음 다시 연결에 사용할 원래 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다. **에지 속성** 을 선택합니다.
    
      - **일반** 아래의 **속성 편집** 에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 을 선택합니다. **확인** 을 클릭합니다.
    
      - **작업** 을 클릭하고, **토폴로지**, **게시** 를 차례로 클릭합니다. **토폴로지 게시** 프롬프트가 표시되면 **다음** 을 클릭합니다. 게시가 완료되면 **마침** 을 클릭합니다.
    
      - 에지 서버에서 비즈니스용 Skype 서버 배포 마법사를 여십시오. 비즈니스용 **Skype 서버** 시스템 설치 또는 업데이트, 비즈니스용 Skype 서버 구성 요소 설치 또는 **제거를 클릭합니다.** **다시 실행** 을 클릭합니다.
    
      - **다음** 을 클릭합니다. 요약 화면에 실행되는 작업이 표시됩니다. 배포가 완료되었으면 **로그 보기** 를 클릭하여 사용 가능한 로그 파일을 확인합니다. **마침** 을 클릭하여 배포를 완료합니다.

3.  복원된 에지 서버를 사용하기 위해 XMPP 페더ation 경로를 장애 복구(fail back)하려는 경우 다음을 실행합니다.
    
      - 다음 cmdlet을 실행하여 이제 XMPP 페더럴을 호스팅할 에지 풀(이 예에서는 EdgeServer1)으로 XMPP 페더ation 경로를 다시 점화합니다.
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        이 예제에서 Site1은 이제 XMPP 페더럴 경로를 호스팅할 에지 풀이 포함된 사이트로, EdgeServer1.contoso.com 풀에 있는 에지 서버의 FQDN입니다.
    
      - 이제 XMPP 페더레이션을 호스팅할 에지 풀로 확인되는 XMPP 페더레이션용 DNS SRV 레코드가 없으면 다음 예에 표시된 것처럼 지금 추가해야 합니다. 이 SRV 레코드는 포트 값 5269를 포함해야 합니다.
        
            _xmpp-server._tcp.contoso.com
    
      - 외부 DNS 서버에서 XMPP 페더레이션용 DNS A 레코드를 EdgeServer2.contoso.com을 가리키도록 변경합니다.
    
      - 이제 XMPP 페더레이션을 호스팅할 에지 풀의 포트 5269가 외부적으로 열려 있는지 확인합니다.

4.  프런트 엔드 풀이 실패하고 복원된 에지 풀이 포함된 사이트에서 실행된 상태로 유지된 경우 이러한 프런트 엔드 풀에서 웹 회의 서비스 및 A/V 회의 서비스를 업데이트하여 로컬 사이트의 에지 풀을 다시 사용해야 합니다.

5.  오류가 발생한 에지 풀과 동일한 사이트의 프런트 엔드 풀도 실패한 경우 이제 Invoke-CsPoolFailback을 사용하여 프런트 엔드 풀을 장애 조치(failback)할 수 있습니다.


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a>프런트 엔드 풀과 연결된 에지 풀 변경

에지 풀이 다운되었는데 동일 사이트의 프런트 엔드 풀은 계속 실행되는 경우에는 오류가 발생한 에지 풀을 복원하는 동안 다른 사이트의 에지 풀을 사용하도록 프런트 엔드 풀을 설정해야 합니다.

1.  토폴로지 작성기에서 변경해야 하는 프런트 엔드 풀의 이름을 탐색합니다.

2.  풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집** 을 클릭합니다.

3.  **연결** 섹션의 **에지 풀 연결(미디어 구성 요소)** 에서 드롭다운 상자를 사용하여 이 프런트 엔드 풀과 연결할 에지 풀을 선택합니다.

4.  **확인** 을 클릭합니다.
