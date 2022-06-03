---
title: 비즈니스용 Skype 서버 2015로 업그레이드 계획
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: '요약: 비즈니스용 Skype 서버 2015로 업그레이드할 때 고려해야 할 사항에 대해 알아봅니다.'
ms.openlocfilehash: 0b31234bbb0cbc5c2475b241b810430f7595f411
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860599"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015로 업그레이드 계획
 
요약: 비즈니스용 Skype 서버 2015로 업그레이드할 때 고려해야 할 사항에 대해 알아봅니다.
  
비즈니스용 Skype 서버 2015로 업그레이드하려는 계획의 일환으로 이 항목을 사용하여 비즈니스용 Skype 서버 2015에 권장되는 업그레이드 경로, In-Place 업그레이드의 작동 방식, 지원되는 공존 시나리오 및 업그레이드 프로세스의 모양을 이해합니다.

> [!NOTE]
> 2015년 비즈니스용 Skype 서버 현재 위치 업그레이드를 사용할 수 있었지만 2019년 비즈니스용 Skype 서버 더 이상 지원되지 않습니다. 나란히 공존이 지원됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2019로 마이그레이션](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md)을 참조하세요.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에 권장되는 업그레이드 경로

 Lync Server 2013, Lync Server 2010 또는 Office Communications Server 2007 R2에서 비즈니스용 Skype 서버 2015로 업그레이드하려면 다음 업그레이드 경로를 사용합니다.
  
> [!CAUTION]
> In-Place 업그레이드는 Lync Server 2013에서 비즈니스용 Skype 서버 2015로 회의 디렉터리를 자동으로 이동합니다. 그러나 회의 디렉터리를 수동으로 이동하려는 경우 비즈니스용 Skype 서버 2015 Management Shell을 사용하는 것이 매우 중요합니다. Lync Server 2013 관리 셸을 사용하여 Lync Server 2013에서 비즈니스용 Skype 서버 2015로 회의 디렉터리를 이동하려고 하면 데이터 손실이 발생할 수 있습니다. 일반적으로 모든 용량에서 비즈니스용 Skype 서버 2015로 작업할 때마다 비즈니스용 Skype 서버 2015 도구 집합을 사용해야 합니다.  
  
|**버전**|**권장 사항**|
|:-----|:-----|
|Lync Server 2013  <br/> | 업그레이드하려면 풀과 연결된 각 서버에서 비즈니스용 Skype 서버 토폴로지 작성기 및 새 In-Place 업그레이드 기능을 사용합니다. 자세한 단계는 [Lync Server 2013에서 비즈니스용 Skype 서버 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013)[로 업그레이드하고 비즈니스용 Skype 서버 2015로 업그레이드하는](../deploy/upgrade-to-skype-for-business-server.md) 계획을 참조하세요. <br/> |
|Lync Server 2010 + Lync Server 2013(이중 모드)  <br/> |먼저 Lync Server 2013으로 업그레이드한 다음 새 In-Place 업그레이드 기능을 사용하여 비즈니스용 Skype 서버 2015로 업그레이드합니다. 그러나 토폴로지를 기본 Lync Server 2010인 경우 Lync Server 2013 구성 요소를 Lync Server 2010으로 롤백한 다음 비즈니스용 Skype 서버 2015로 직접 업그레이드할 수도 있습니다. 이 경우 In-Place 업그레이드를 활용할 수 없으며 Lync Server 2010과 비즈니스용 Skype 서버 2015 사이에 직선 공존을 사용합니다. 삼중 존재는 지원되지 않지만 공존이 지원됩니다.  <br/> |
|Lync Server 2010  <br/> |새 비즈니스용 Skype 서버 2015 풀을 가져온 다음 사용자를 이 새 풀로 마이그레이션합니다. 그런 다음 이전 Lync Server 2010 풀을 해제할 수 있습니다. Lync Server 2010에서 비즈니스용 Skype 서버 2015로 업그레이드하는 것은 Lync Server 2010에서 Lync Server 2013으로 업그레이드하는 것과 비슷합니다. [Lync Server 2010에서 Lync Server 2013으로 마이그레이션을](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013) 참조하세요.  <br/> |
|Office Communications Server 2007 R2  <br/> | 다음 두 가지 옵션 중 하나를 선택합니다. <br/>  새 비즈니스용 Skype 서버 2015 환경을 설정합니다. <br/>  또는 하드웨어 및 소프트웨어가 비즈니스용 Skype 서버 2015에 대한 요구 사항을 충족하는 경우 Lync Server 2013으로 업그레이드한 다음 새 In-Place 업그레이드 기능을 사용하여 비즈니스용 Skype 서버 2015로 업그레이드합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에 대한 서버 요구 사항](requirements-for-your-environment/server-requirements.md) 및 [Office Communications Server 2007 R2에서 Lync Server 2013으로의 마이그레이션](/previous-versions/office/lync-server-2013/migration-from-office-communications-server-2007-r2-to-lync-server-2013)을 참조하세요.  <br/> |
   
> [!NOTE]
> SQL Server 2014는 비즈니스용 Skype 서버 2015에서 지원되지만 Lync Server 2013에서는 지원되지 않습니다. SQL Server 2012에서 SQL Server 2014로 업그레이드하려면 먼저 이 문서에 설명된 대로 In-Place 업그레이드 방법을 사용하여 풀을 비즈니스용 Skype 서버 2015로 업그레이드해야 합니다. 그런 다음 SQL Server 2012에서 SQL Server 2014로 업그레이드할 수 있습니다. [SQL Server 2014로 업그레이드를](/sql/database-engine/install-windows/upgrade-sql-server?viewFallbackFrom=sql-server-2014) 참조하세요. 데이터베이스 요구 사항에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015의 서버 요구 사항을](requirements-for-your-environment/server-requirements.md) 참조하세요. 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Lync Server 2013에서 비즈니스용 Skype 서버 2015로 업그레이드 계획
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

새 In-Place 업그레이드 기능을 사용하여 Lync Server 2013 시스템을 비즈니스용 Skype 서버 2015로 업그레이드할 수 있습니다. 현재 위치 업그레이드는 인증서를 백업하고, 서버 구성 요소를 제거하고, 로컬 데이터베이스를 업그레이드하고, 비즈니스용 Skype 서버 2015 역할을 설치하는 원클릭 솔루션을 제공합니다. 현재 위치 업그레이드는 기존 하드웨어 및 서버 투자를 보존하여 2015년 비즈니스용 Skype 서버 배포하는 데 드는 전체 비용을 절감하고자 합니다.
  
> [!NOTE]
> In-Place 업그레이드를 사용하면 비즈니스용 Skype 서버 업그레이드할 때 동일한 하드웨어를 사용할 수 있습니다. 그러나 동일한 하드웨어를 다시 사용한다고 해서 동일한 성능 용량으로 변환되지는 않습니다. Lync Server 2013 및 비즈니스용 Skype 서버 2015의 성능 로드가 동일하지는 않습니다. 
  
> [!NOTE]
> In-Place 업그레이드는 비즈니스용 Skype 서버 대한 고가용성 또는 재해 복구를 지원하지 않습니다. 
  
현재 위치 업그레이드에는 Lync Server 2013 풀을 오프라인으로 전환하고 비즈니스용 Skype 서버 2015 풀로 업그레이드하는 작업이 포함됩니다. 
  
### <a name="create-an-in-place-upgrade-plan"></a>In-Place 업그레이드 계획 만들기

다음을 포함하는 계획을 수립합니다.
  
1. 현재 토폴로지 이해
    
    > [!NOTE]
    > In-Place 업그레이드를 실행하기 전에 Lync Server 2013용 LRS 관리 도구를 제거해야 합니다. Lync Server 2013용 LRS 관리 도구는 비즈니스용 Skype 서버 2015와 공존할 수 없습니다. In-Place 업그레이드를 실행한 후 새 LRS 관리 도구를 설치합니다. 자세한 내용은 [Microsoft Lync Room System 관리 웹 포털에서 비즈니스용 Skype 서버 2015](https://go.microsoft.com/fwlink/?LinkID=544807)를 참조하세요.
  
2. 업그레이드에 대한 기본 풀입니다.
    
3. 보관 및 모니터링 데이터베이스를 업그레이드할지 또는 새 데이터베이스를 만들 것인지 여부입니다.
    
4. 사용할 In-Place 업그레이드 방법: 오프라인 또는 사용자 이동. 사용자 이동의 일부로 기본 풀과 연결된 전역 회의 디렉터리도 마이그레이션해야 합니다. 
    
5. 영향을 받은 사용자를 위한 통신 계획입니다.
    
6. 업그레이드가 실패하는 경우의 백업 계획입니다.
    
업그레이드하는 동안 기본 풀에 있는 모든 사용자는 업그레이드가 완료될 때까지 서비스를 사용할 수 없습니다. 작업 중인 보조 풀이 있는 경우 업그레이드 전에 보조 풀로 이동하여 사용자에게 영향을 주지 않도록 할 수 있습니다. 업그레이드 후 사용자를 기본 풀로 다시 이동합니다.
  
### <a name="in-place-upgrade-methods"></a>현재 위치 업그레이드 방법

In-Place 업그레이드에는 두 가지 시나리오가 있습니다. 
  
- 사용자 이동 메서드로, 사용자에게 가동 중지 시간이 필요하지 않습니다. 
    
- 가동 중지 시간이 필요한 오프라인 메서드입니다.
    
유지 관리 기간 동안 오프라인 메서드 업그레이드를 예약하고 사용자에게 가동 중지 시간을 알려 주는 것이 좋습니다.
  
> [!NOTE]
> Lync Server 2013에서 쌍을 이루는 풀을 업그레이드할 때 두 풀을 모두 비즈니스용 Skype 서버 2015로 업그레이드하려고 합니다. 첫 번째 풀을 업그레이드한 직후에 두 번째 풀을 업그레이드해야 합니다. 한 풀이 Lync Server 2013을 실행하고 두 번째 풀이 2015 비즈니스용 Skype 서버 실행 중인 경우 재해 복구 옵션이 최소화됩니다. 예를 들어 한 풀이 2013을 실행하고 두 번째 풀이 2015이고 재해가 발생하는 경우 쌍을 이루는 풀이 동일한 버전이 아닌 경우 재해 모드에서 풀 장애 조치(failover)가 지원되지 않기 때문에 데이터 손실이 발생할 수 있습니다. 
  
#### <a name="in-place-upgrade-offline-method"></a>오프라인에서 현재 위치 업그레이드 방법

사용자 풀 간에 사용자를 이동하지 않으려면 이 메서드를 사용합니다. 업그레이드하는 동안 사용자는 Lync 또는 비즈니스용 Skype 서비스를 사용할 수 없습니다. 
  
다음 다이어그램에서는 이 프로세스의 개요를 보여  있습니다.
  
![Lync 2013 사용자를 오프라인으로 Skype.](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> 풀을 페어링한 경우 업그레이드 전에 풀을 짝지어 두지 마세요. 
  
서버 풀 업그레이드를 시작하면 전체 풀의 업그레이드를 완료해야 합니다. 비즈니스용 Skype 서버 풀의 일부만 업그레이드하는 것을 지원하지 않습니다. 
  
#### <a name="move-users-method-no-user-downtime"></a>사용자 이동 메서드(사용자 가동 중지 시간 없음)
<a name="bkmk_MoveUsersMethod"> </a>

이 방법을 사용하려면 업그레이드를 시작하기 전에 사용자를 다른 풀로 이동합니다. 업그레이드하는 동안 사용자는 Lync 서비스를 사용할 수 있습니다. 업그레이드된 풀로 이동한 후에는 비즈니스용 Skype 사용할 수 있습니다. 다음 다이어그램에서는 이 프로세스의 개요를 보여  있습니다.
  
> [!IMPORTANT]
> 사용자 이동의 일부로 기본 풀과 연결된 전역 회의 디렉터리도 마이그레이션해야 합니다. PSTN 전화 접속 회의는 페어링된 풀 대신 업그레이드되는 풀에 대한 ConferenceID를 계속 확인합니다. 따라서 업그레이드 중에 풀에 예약된 PSTN 회의에 액세스할 수 있도록 하려면 회의 디렉터리를 이동해야 합니다. 
  
![수영장을 업그레이드하기 전에 다른 수영장으로 이동되고 업그레이드된 후 다시 풀로 이동하는 사용자를 보여 주는 수영 다이어그램.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>하드웨어 업그레이드를 위해 사용자 이동
<a name="bkmk_MoveUsersMethod"> </a>

 하드웨어가 [비즈니스용 Skype 서버 2015의 서버 요구 사항을](requirements-for-your-environment/server-requirements.md) 충족하지 않는 경우 새 비즈니스용 Skype 서버 2015 환경을 설정하고 사용자를 해당 환경으로 이동합니다. 다음 다이어그램에서는 Lync Server 2010에서 업그레이드하기 위한 이 프로세스의 개요를 보여  있습니다. 
  
![Lync Server 기본 프런트 엔드 풀의 사용자가 비즈니스용 Skype 서버 2015로 이동되고 Lync Server 풀이 서비스 해제되는 것을 보여 주는 스윔 레인 다이어그램](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>현재 위치 업그레이드 프로세스

 다음 단계를 사용하여 Lync Server 2013에서 비즈니스용 Skype 서버 2015로 업그레이드합니다.
  
1. 업그레이드하기 전에 모든 데이터베이스를 백업합니다.
    
2. 업그레이드할 모든 서비스가 실행 중 상태인지 확인합니다.
    
3. 토폴로지 작성기를 사용하여 토폴로지 파일을 업그레이드하고 게시합니다.
    
4. 모든 프런트 엔드 서버에서 모든 서비스를 중지합니다.
    
5. 비즈니스용 Skype 서버 필요한 새 필수 구성 요소를 설치합니다.
    
6. 각 프런트 엔드 서버에서 In-Place 업그레이드를 시작합니다.
    
7. 업그레이드가 완료되면 모든 서비스를 다시 시작합니다.
    
   - 프런트 엔드 풀의 경우 Start-CsPool 명령을 사용하여 서비스를 다시 시작합니다.
    
   - 프런트 엔드가 아닌 서버의 경우 Start-CSWindowsService를 사용합니다.
    
> [!NOTE]
>  기존 보관 및 모니터링 데이터베이스를 업그레이드하지 않으려면 토폴로지 업그레이드 전에 종속성을 제거합니다. 새 보관 및 모니터링 데이터베이스를 만들려는 경우 업그레이드하는 동안 새 SQL 저장소를 만들고 풀에 연결할 수 있습니다. [2015년 비즈니스용 Skype 서버](../deploy/upgrade-to-skype-for-business-server.md) 업그레이드 항목에서 이 작업을 수행하는 방법에 대한 단계를 찾을 수 있습니다. > 현재 위치 업그레이드는 비즈니스용 Skype 서버 대한 고가용성 또는 재해 복구를 지원하지 않습니다. 사용자 서비스 중단을 방지하려면 [사용자 이동 방법(사용자 가동 중지 시간 없음)](upgrade.md#bkmk_MoveUsersMethod) 을 사용하여 upgrade.> 업그레이드 프로세스 중에 xds-replica는 사용 가능한 공간이 가장 많은 디스크 드라이브의 로컬 공유 폴더에 배치됩니다. 해당 디스크가 나중에 제거되면 서비스가 시작되지 않는 등의 문제가 발생할 수 있습니다.
  
### <a name="upgrade-order"></a>업그레이드 순서

토폴로지 내부를 외부로 업그레이드합니다. 먼저 모든 풀, 에지 서버 및 마지막으로 CMS(중앙 관리 Microsoft Store) 풀을 업그레이드합니다. 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 인증 고려 사항

웹 서비스에 Kerberos 인증을 사용하는 경우 In-Place 업그레이드가 완료된 후 Kerberos 계정을 다시 할당하고 암호를 다시 설정해야 합니다. 이 작업을 수행하는 방법을 알아보려면 [Kerberos 인증 설정을](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-kerberos-authentication) 참조하세요.
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Lync Server 2013 및 Lync Server 2010과의 공존 지원
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Lync Server 2013 또는 Lync Server 2010과 동일한 토폴로지에서 비즈니스용 Skype 서버 2015를 실행할 수 있지만 동일한 토폴로지에서 세 가지 모두를 사용할 수는 없습니다.
  
Lync Server 2010과 Lync Server 2013 간에 공존하는 경우 전체 토폴로지에서 Lync Server 2013으로 업그레이드한 다음 In-Place 업그레이드를 사용하여 비즈니스용 Skype 서버 2015로 업그레이드하는 것이 좋습니다. 자세한 내용은 [Lync Server 2010에서 Lync Server 2013으로 마이그레이션을](/previous-versions/office/lync-server-2013/migration-from-lync-server-2010-to-lync-server-2013) 참조하세요.
  
토폴로지가 주로 Lync Server 2010인 경우 토폴로지에서 비즈니스용 Skype 서버 2015로 업그레이드하기 전에 Lync Server 2013 구성 요소를 Lync Server 2010으로 롤백합니다. 이 경우 In-Place 업그레이드의 이점을 상실하고 Lync Server 2010과 비즈니스용 Skype 서버 2015 사이에 공존 토폴로지가 있습니다.
  
다음 다이어그램은 Lync Server 2013 및 Lync Server 2010과 비즈니스용 Skype 서버 2015의 공존 지원을 보여줍니다.
  
![Lync Server 2013 또는 Lync Server 2010에서 비즈니스용 Skype 서버 2015에 대한 공존 지원을 보여 주는 다이어그램](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>기존 Survivable 분기 어플라이언스 및 서버를 사용하여 업그레이드 프로세스
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

비즈니스용 Skype 서버 2015는 SBA(Survivable Branch Appliance) 또는 SBS(Survivable Branch Server)의 In-Place 업그레이드를 지원하지 않습니다.
  
그러나 Lync Server 2010 또는 Lync Server 2013 SBA/SBS와 비즈니스용 Skype 서버 데이터 센터의 공존을 지원합니다. 
  
연결된 분기가 있는 Lync Server 2013 FE(프런트 엔드) 풀의 In-Place 업그레이드를 계획할 때 기존 사용자는 Lync Server 2013 SBA/SBS에 그대로 둘 수 있습니다. 업그레이드하는 동안 SBA/SBS 사용자는 복원력 모드로 전환되고 업그레이드가 완료된 후 정상 기능으로 돌아갑니다. 복원력 모드 동안의 사용자 환경에 대한 자세한 내용은 [Lync Server 2013의 분기 사이트 복원력 기능을](/previous-versions/office/lync-server-2013/lync-server-2013-branch-site-resiliency-features) 참조하세요.
  
Lync Server 2010 토폴로지에서 비즈니스용 Skype 서버 2015로 마이그레이션하는 경우 Lync Server 2013으로 마이그레이션하는 것과 유사하게 SBA/SBS를 토폴로지에 추가해야 합니다. 필요한 단계는 [Lync Server 2013 프런트 엔드 풀에 Survivable Branch Appliance 연결에 대해](/previous-versions/office/lync-server-2013/lync-server-2013-connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool) 읽어 보세요.
  
Lync Server 2010 및 Lync Server 2013의 공존 토폴로지의 경우 먼저 'Lync Server 2013 및 Lync Server 2010과의 공존 지원' 섹션의 권장 사항에 맞춥니다.
  
## <a name="see-also"></a>참고 항목
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[비즈니스용 Skype 서버 2015로 업그레이드](../deploy/upgrade-to-skype-for-business-server.md)
  
[2015년 비즈니스용 Skype 서버 환경 요구 사항](requirements-for-your-environment/environmental-requirements.md)
  
[비즈니스용 Skype 서버 2015의 서버 요구 사항](requirements-for-your-environment/server-requirements.md)
