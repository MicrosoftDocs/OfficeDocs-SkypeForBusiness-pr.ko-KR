---
title: 비즈니스용 Skype 서버 2015로 업그레이드 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: '요약: 비즈니스용 Skype 서버 2015로의 업그레이드를 계획할 때 고려해야 할 사항들을 설명하는 문서입니다. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 2015 무료 평가판을 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 다운로드합니다.'
ms.openlocfilehash: 69b1d9df20330ad0baecbc1c5abe59e76808185a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831978"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015로 업그레이드 계획
 
요약: 비즈니스용 Skype 서버 2015로의 업그레이드를 계획할 때 고려해야 할 사항들을 설명하는 문서입니다. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 2015 무료 평가판을 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 다운로드합니다.
  
비즈니스용 Skype 서버 2015로 업그레이드하기 위한 계획의 일부로 이 항목을 사용하여 비즈니스용 Skype 서버 2015에 대한 권장 업그레이드 경로, In-Place 업그레이드의 작동 방식, 지원되는 동시 사용 시나리오 및 업그레이드 프로세스의 모양을 파악합니다.

> [!NOTE]
> 현재 장소 업그레이드는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. 나란히 공존하는 것이 지원됩니다. 자세한 내용은 비즈니스용 [Skype 서버 2019로](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 마이그레이션을 참조하세요.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015로의 권장 업그레이드 경로

 Lync Server 2013, Lync Server 2010 또는 Office Communications Server 2007 R2에서 비즈니스용 Skype 서버 2015로 업그레이드하려면 다음 업그레이드 경로를 사용하세요.
  
> [!CAUTION]
> In-Place 업그레이드하면 전화 회의가 Lync Server 2013에서 비즈니스용 Skype 서버 2015로 자동으로 이동됩니다. 그러나 전화 회의를 수동으로 이동하려면 비즈니스용 Skype 서버 2015 관리 셸을 사용하는 것이 매우 중요합니다. Lync Server 2013 관리 셸을 사용하여 회의 센터를 Lync Server 2013에서 비즈니스용 Skype 서버 2015로 이동하려고 시도하면 데이터 손실이 발생할 수 있습니다. 일반적으로 모든 용량으로 비즈니스용 Skype 서버 2015를 사용할 때마다 비즈니스용 Skype 서버 2015 도구 집합을 사용해야 합니다.  
  
|**버전**|**추천**|
|:-----|:-----|
|Lync Server 2013  <br/> | 업그레이드하려면 비즈니스용 Skype 서버 토폴로지 작성기 및 풀과 연결된 In-Place 새 업그레이드 기능을 사용하세요. 자세한 [단계는 Lync Server 2013에서 비즈니스용 Skype 서버 2015로](upgrade.md#BKMK_PlanUpgradeFromLync2013) 업그레이드하고 비즈니스용 [Skype 서버 2015로](../deploy/upgrade-to-skype-for-business-server.md) 업그레이드하는 계획을 참조하세요. <br/> |
|Lync Server 2010 + Lync Server 2013(이중 모드)  <br/> |먼저 Lync Server 2013으로 업그레이드한 다음 새로운 In-Place 업그레이드 기능을 사용하여 비즈니스용 Skype 서버 2015로 업그레이드합니다. 그러나 토폴로지가 기본 Lync Server 2010인 경우 Lync Server 2013 구성 요소를 Lync Server 2010으로 롤백한 다음 비즈니스용 Skype 서버 2015로 직접 업그레이드할 수도 있습니다. 이 경우 In-Place 업그레이드를 활용할 수 없는 것이고 Lync Server 2010과 비즈니스용 Skype 서버 2015 간에 직접 공유를 사용할 수 있습니다. 삼각형은 지원되지 않지만 동시 사용이 지원됩니다.  <br/> |
|Lync Server 2010  <br/> |새 비즈니스용 Skype 서버 2015 풀을 가져오고 사용자를 이 새 풀로 마이그레이션합니다. 그런 다음 이전 Lync Server 2010 풀을 해제할 수 있습니다. Lync Server 2010에서 비즈니스용 Skype 서버 2015로 업그레이드하는 것은 Lync Server 2010에서 Lync Server 2013으로 업그레이드하는 경우와 비슷합니다. [Lync Server 2010에서 Lync Server 2013으로](https://go.microsoft.com/fwlink/p/?LinkId=526615)마이그레이션을 참조합니다.  <br/> |
|Office Communications Server 2007 R2  <br/> | 두 가지 옵션 중 하나를 선택합니다. <br/>  새 비즈니스용 Skype 서버 2015 환경을 설치합니다. <br/>  또는 하드웨어 및 소프트웨어가 비즈니스용 Skype 서버 2015의 요구 사항을 충족하는 경우 Lync Server 2013으로 업그레이드한 다음 새로운 In-Place 업그레이드 기능을 사용하여 비즈니스용 Skype 서버로 업그레이드합니다. 자세한 내용은 비즈니스용 Skype 서버 [2015에](requirements-for-your-environment/server-requirements.md) 대한 서버 요구 사항 및 [Office Communications Server 2007 R2에서 Lync Server 2013으로](https://go.microsoft.com/fwlink/p/?LinkId=526616)마이그레이션을 참조하세요.  <br/> |
   
> [!NOTE]
> SQL Server 2014는 비즈니스용 Skype 서버에서 지원되지만 Lync Server 2013에서는 지원되지 않습니다. SQL Server 2012에서 SQL Server 2014로 업그레이드하려면 이 문서에 설명된 In-Place Upgrade 방법을 사용하여 먼저 풀을 비즈니스용 Skype 서버 2015로 업그레이드해야 합니다. 그런 다음 SQL Server 2012에서 SQL Server 201 SQL Server 4로 업그레이드할 수 [있습니다.](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx) 데이터베이스 요구 사항에 대한 자세한 내용은 비즈니스용 [Skype 서버 2015의 서버 요구 사항을 참조하세요.](requirements-for-your-environment/server-requirements.md) 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Lync Server 2013에서 비즈니스용 Skype 서버 2015로 업그레이드 계획
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

새로운 업그레이드 기능으로 Lync Server 2013 시스템을 비즈니스용 Skype 서버 2015로 In-Place 수 있습니다. 전체 업그레이드에서는 인증서를 백업하고, 서버 구성 요소를 제거하고, 로컬 데이터베이스를 업그레이드하고, 비즈니스용 Skype 서버 2015 역할을 설치하는 원 클릭 솔루션을 제공합니다. 전체 업그레이드는 기존 하드웨어 및 서버 투자를 유지하여 비즈니스용 Skype 서버 2015 배포에 대한 전체 비용을 절감하기 위해 노력합니다.
  
> [!NOTE]
> In-Place 업그레이드를 사용하면 비즈니스용 Skype 서버로 업그레이드할 때 동일한 하드웨어를 사용할 수 있습니다. 그러나 동일한 하드웨어를 다시 사용할 경우 동일한 성능 용량으로 변환되지는 않습니다. Lync Server 2013 및 비즈니스용 Skype 서버 2015의 성능 부하가 동일할 것으로 예상되지는 않습니다. 
  
> [!NOTE]
> In-Place 비즈니스용 Skype 서버에 대한 고가용성 또는 재해 복구를 지원하지 않습니다. 
  
바로 업그레이드에는 Lync Server 2013 풀을 오프라인으로 전환하고 비즈니스용 Skype 서버 2015 풀로 업그레이드하는 과정이 진행됩니다. 
  
### <a name="create-an-in-place-upgrade-plan"></a>업그레이드 In-Place 만들기

다음을 포함하는 계획을 수립합니다.
  
1. 현재 토폴로지 이해
    
    > [!NOTE]
    > 업그레이드를 실행하기 전에 Lync Server 2013용 LRS 관리 도구를 In-Place 합니다. Lync Server 2013용 LRS 관리 도구는 비즈니스용 Skype 서버 2015와 함께 사용할 수 없습니다. 업그레이드를 In-Place 새 LRS 관리 도구를 설치합니다. 자세한 내용은 비즈니스용 Skype 서버 [2015용 Microsoft Lync Room System](https://go.microsoft.com/fwlink/?LinkID=544807) 관리 웹 포털을 참조하세요.
  
2. 업그레이드의 기본 풀입니다.
    
3. 보관 및 모니터링 데이터베이스를 업그레이드할지 또는 새 데이터베이스를 만들지 여부
    
4. 사용할 In-Place 업그레이드 방법(오프라인 또는 사용자 이동)입니다. 또한 사용자 이동의 일부로 기본 풀과 연결된 전역 회의를 마이그레이션해야 합니다. 
    
5. 영향을 미치는 사용자에 대한 통신 계획입니다.
    
6. 업그레이드가 실패할 경우의 백업 계획
    
업그레이드되는 동안 기본 풀에 있는 사용자는 업그레이드가 완료될 때까지 서비스를 사용할 수 없습니다. 작업하는 보조 풀이 있는 경우 업그레이드 전에 사용자를 보조 풀로 이동하여 영향을 피할 수 있습니다. 업그레이드 후 사용자를 기본 풀로 다시 이동하십시오.
  
### <a name="in-place-upgrade-methods"></a>전제 업그레이드 방법

업그레이드에 대한 두 가지 시나리오가 In-Place 있습니다. 
  
- 사용자 이동 메서드- 사용자에게는 다운타임이 필요 없습니다. 
    
- 오프라인 메서드로, 다운타임이 필요합니다.
    
유지 관리 기간 동안 오프라인 방법 업그레이드를 예약하는 것이 좋습니다. 그러면 사용자에게 다운타임이 통보됩니다.
  
> [!NOTE]
> Lync Server 2013에서 쌍으로 된 풀을 업그레이드하고 두 풀을 모두 비즈니스용 Skype 서버 2015로 업그레이드하려는 경우 첫 번째 풀을 업그레이드한 직후 두 번째 풀을 업그레이드해야 합니다. 한 풀에서 Lync Server 2013을 실행하고 두 번째 풀이 비즈니스용 Skype 서버 2015를 실행 중인 경우 재해 복구 옵션이 최소화됩니다. 예를 들어 한 풀이 2013을 실행 중이고 두 번째 풀은 2015에 재해가 발생하면 쌍으로 처리된 풀이 동일한 버전이 아닌 경우 재해 모드에서 풀 장애 조치(failover)가 지원되지 않습니다. 
  
#### <a name="in-place-upgrade-offline-method"></a>In-place upgrade Offline 메서드

사용자 풀 간에 사용자를 이동하지 않는 경우 이 방법을 사용합니다. 업그레이드하는 동안 사용자는 Lync 또는 비즈니스용 Skype 서비스를 사용할 수 없습니다. 
  
다음 다이어그램에서는 이 프로세스에 대한 개요를 보여줍니다.
  
![Lync 2013에서 오프라인으로 Skype 사용자](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> 쌍으로 된 풀이 있는 경우 업그레이드 전에 언 페어링하지 않습니다. 
  
서버 풀 업그레이드를 시작한 후 전체 풀의 업그레이드를 완료해야 합니다. 비즈니스용 Skype 서버는 풀의 일부만 업그레이드할 수 없습니다. 
  
#### <a name="move-users-method-no-user-downtime"></a>Move Users 메서드(사용자 다운타임 없음)
<a name="bkmk_MoveUsersMethod"> </a>

이 방법을 사용하려면 업그레이드를 시작하기 전에 사용자를 다른 풀로 이동해야 합니다. 업그레이드하는 동안 사용자는 Lync 서비스를 사용할 수 있습니다. 업그레이드된 풀로 이동한 후 비즈니스용 Skype를 사용할 수 있습니다. 다음 다이어그램에서는 이 프로세스에 대한 개요를 보여줍니다.
  
> [!IMPORTANT]
> 또한 사용자 이동의 일부로 기본 풀과 연결된 전역 회의를 마이그레이션해야 합니다. PSTN 전화 접속 회의에서는 페어링된 풀이 아닌 업그레이드되는 풀로 ConferenceID를 계속 확인하게 됩니다. 따라서 업그레이드 중에 풀에 예약된 PSTN 회의에 계속 액세스할 수 있도록 하려는 경우 회의 센터를 이동해야 합니다. 
  
![풀이 업그레이드되기 전에 사용자가 다른 풀로 이동되어 업그레이드된 후 다시 풀로 이동되는 것을 보여 주는 다이어그램입니다.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>하드웨어 업그레이드를 위해 사용자 이동
<a name="bkmk_MoveUsersMethod"> </a>

 하드웨어가 비즈니스용 Skype [서버 2015에](requirements-for-your-environment/server-requirements.md)대한 서버 요구 사항을 충족하지 않는 경우 새 비즈니스용 Skype 서버 2015 환경을 설정하고 사용자를 해당 환경으로 이동하십시오. 다음 다이어그램에서는 Lync Server 2010에서 업그레이드하는 이 프로세스에 대한 개요를 보여줍니다. 
  
![비즈니스용 Skype 서버 2015 및 해제할 Lync Server 풀로 이동되는 Lync Server 기본 프런트 엔드 풀의 사용자를 보여 주며 스위치 차선 다이어그램입니다.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>In-place upgrade process

 다음 단계를 사용하여 Lync Server 2013에서 비즈니스용 Skype 서버 2015로 업그레이드합니다.
  
1. 업그레이드 전에 모든 데이터베이스를 백업합니다.
    
2. 업그레이드할 모든 서비스가 실행 중인지 확인
    
3. 토폴로지 작성기에서 토폴로지 파일을 업그레이드하고 게시합니다.
    
4. 모든 프런트 엔드 서버에서 모든 서비스를 중지합니다.
    
5. 비즈니스용 Skype 서버에 필요한 새 필수 요구를 설치합니다.
    
6. 각 프런트 엔드 서버에서 업그레이드 In-Place 시작하십시오.
    
7. 업그레이드가 완료되면 모든 서비스를 다시 시작합니다.
    
   - 프런트 엔드 풀의 경우 Start-CsPool 명령을 사용하여 서비스를 다시 시작합니다.
    
   - 프런트 엔드 서버가 아닌 서버의 경우 Start-CSWindowsService를 사용 합니다.
    
> [!NOTE]
>  기존 보관 및 모니터링 데이터베이스를 업그레이드하지 않는 경우 토폴로지 업그레이드 전에 종속성 제거 새 보관 및 모니터링 데이터베이스를 만들하려는 경우 업그레이드하는 동안 새 보관 데이터베이스 저장소를 SQL 풀에 연결하면 됩니다. 이 작업을 하는 방법에 대한 단계는 비즈니스용[Skype 서버 2015로](../deploy/upgrade-to-skype-for-business-server.md)업그레이드 항목에서 찾을 수 있습니다. > 전체 업그레이드는 비즈니스용 Skype 서버에 대한 고가용성 또는 재해 복구를 지원하지 않습니다. 사용자의 서비스가 중단되지 않도록 방지하려면 [사용자](upgrade.md#bkmk_MoveUsersMethod) 이동 방법(사용자 중단 시간 없음)을 사용하여 upgrade.> 업그레이드 프로세스 중에 xds-replica가 디스크 드라이브의 로컬 공유 폴더에 가장 많은 사용 공간이 있는 폴더에 배치됩니다. 해당 디스크가 나중에 제거되면 서비스가 시작되지 않는 등의 문제가 발생합니다.
  
### <a name="upgrade-order"></a>업그레이드 순서

내부에서 외부로 토폴로지 업그레이드 먼저 모든 풀을 업그레이드한 다음 에지 서버, 그리고 마지막으로 CMS(중앙 관리 저장소) 풀을 업그레이드합니다. 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 인증 고려 사항

웹 서비스에 Kerberos 인증을 사용하는 경우 업그레이드가 완료된 후 Kerberos 계정을 다시 In-Place 합니다. 이 작업을 하는 방법에 대한 자세한 내용은 [Kerberos](https://go.microsoft.com/fwlink/p/?LinkId=530342)인증 설정을 참조합니다.
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Lync Server 2013 및 Lync Server 2010과의 동시 사용 지원
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Lync Server 2013 또는 Lync Server 2010과 동일한 토폴로지에서 비즈니스용 Skype 서버 2015를 실행할 수 있지만 동일한 토폴로지에서 세 가지를 모두 사용할 수 없습니다.
  
Lync Server 2010과 Lync Server 2013을 함께 사용하는 경우 전체 토폴로지가 Lync Server 2013으로 업그레이드된 다음 In-Place 업그레이드를 사용하여 비즈니스용 Skype 서버 2015로 업그레이드하는 것이 좋습니다. 자세한 내용은 [Lync Server 2010에서 Lync Server 2013으로](https://go.microsoft.com/fwlink/p/?LinkId=526615)마이그레이션을 참조하세요.
  
토폴로지가 주로 Lync Server 2010인 경우 토폴로지가 비즈니스용 Skype 서버 2015로 업그레이드되기 전에 Lync Server 2013 구성 요소를 Lync Server 2010으로 롤백합니다. 이 경우 In-Place 업그레이드의 이점을 Lync Server 2010과 비즈니스용 Skype 서버 2015 간에 함께 사용할 수 있습니다.
  
다음 다이어그램은 Lync Server 2013 및 Lync Server 2010과 함께 비즈니스용 Skype 서버 2015의 동시 사용 지원을 보여줍니다.
  
![Lync Server 2013 또는 Lync Server 2010과 함께 비즈니스용 Skype 서버 2015에 대한 동시 사용 지원을 보여주는 다이어그램입니다.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>기존 Survivable Branch Appliance 및 Server를 통해 업그레이드 프로세스
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

비즈니스용 Skype 서버 2015에서는 SBA(Survivable Branch Appliance) In-Place SBS(Survivable Branch Server)의 업그레이드를 지원하지 않습니다.
  
그러나 비즈니스용 Skype 서버 데이터 센터를 Lync Server 2010 또는 Lync Server 2013 SBA/SBS와 함께 사용할 수 있습니다. 
  
연결된 In-Place Lync Server 2013 프런트 엔드(FE) 풀의 업그레이드를 계획할 때 기존 사용자를 Lync Server 2013 SBA/SBS에 그대로 두면 됩니다. 업그레이드 중에 SBA/SBS 사용자는 탄력성 모드로 전환되어 업그레이드가 완료된 후 정상 기능으로 돌아갑니다. 탄력성 모드 중 사용자 경험에 대한 자세한 내용은 [Lync Server 2013의](https://technet.microsoft.com/library/gg398715.aspx)분기 사이트 탄력성 기능을 참조하세요.
  
Lync Server 2010 토폴로지에서 비즈니스용 Skype 서버 2015로 마이그레이션할 때 Lync Server 2013으로의 마이그레이션과 마찬가지로 SBA/SBS를 토폴로지에 다시 추가해야 합니다. 필요한 단계는 Lync Server 2013 프런트 엔드 풀에 [Survivable Branch Appliance 연결(Survivable Branch Appliance)을 읽어 보십시오.](https://technet.microsoft.com/library/jj688026.aspx)
  
Lync Server 2010 및 Lync Server 2013의 동시 토폴로지의 경우 먼저 'Lync Server 2013 및 Lync Server 2010과의 동시 사용 지원' 섹션의 권장 사항에 맞춰야 합니다.
  
## <a name="see-also"></a>참고 항목
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[비즈니스용 Skype 서버 2015로 업그레이드](../deploy/upgrade-to-skype-for-business-server.md)
  
[비즈니스용 Skype 서버 2015의 환경 요구 사항](requirements-for-your-environment/environmental-requirements.md)
  
[비즈니스용 Skype 서버 2015에 대한 서버 요구 사항](requirements-for-your-environment/server-requirements.md)
