---
title: 비즈니스용 Skype 서버 2015에 대 한 업그레이드 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버 2015에 대 한 업그레이드를 계획할 때 고려해 야 할 사항에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버 2015의 무료 평가판을 다운로드 하세요. https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server'
ms.openlocfilehash: 91cc78f22c03bf7ec59c9ac0c936f194ece71a35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030642"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에 대 한 업그레이드 계획
 
요약: 비즈니스용 Skype 서버 2015에 대 한 업그레이드를 계획할 때 고려해 야 할 사항에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버 2015의 무료 평가판을 다운로드 하세요. [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
비즈니스용 Skype 서버 2015로 업그레이드 하는 계획의 일환으로이 항목을 사용 하 여 비즈니스용 Skype 서버 2015에 대 한 권장 업그레이드 경로, 전체 업그레이드 작동 방식, 지원 되는 동시 사용 시나리오 및 업그레이드 프로세스를 이해 합니다. 같습니다.

> [!NOTE]
> 현재 위치 업그레이드는 비즈니스용 Skype 서버 2015에서 사용할 수 있었지만 비즈니스용 Skype 서버 2019에서는 더 이상 지원 되지 않습니다. Side-by-side coexistance 지원 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2019로 마이그레이션을](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 참조 하세요.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에 대 한 권장 업그레이드 경로

 Lync Server 2013, Lync Server 2010 또는 Office Communications Server 2007 R2에서 비즈니스용 Skype 서버 2015로 업그레이드 하려면 다음 업그레이드 경로를 사용 합니다.
  
> [!CAUTION]
> 전체 업그레이드 전화 회의 디렉터리를 Lync Server 2013에서 비즈니스용 Skype 서버 2015로 자동으로 이동 합니다. 그러나 전화 회의 디렉터리를 수동으로 이동 하려는 경우 비즈니스용 Skype 서버 2015 관리 셸을 사용 하는 것이 매우 중요 합니다. Lync server 2013 관리 셸을 사용 하 여 전화 회의 디렉터리를 Lync Server 2013에서 비즈니스용 Skype 서버 2015로 이동 하려고 하면 데이터 손실이 발생할 수 있습니다. 일반적으로 비즈니스용 Skype 서버 2015에서 모든 용량을 사용할 때마다 비즈니스용 Skype 서버 2015 도구 집합을 사용 해야 합니다.  
  
|**버전**|**추천**|
|:-----|:-----|
|Lync Server 2013  <br/> | 업그레이드 하려면 해당 풀과 연결 된 각 서버에서 비즈니스용 Skype 서버 토폴로지 작성기 및 새로운 전체 업그레이드 기능을 사용 합니다. 자세한 단계는 [Lync server 2013에서 비즈니스용 Skype 서버 2015로 업그레이드 계획](upgrade.md#BKMK_PlanUpgradeFromLync2013) 및 [비즈니스용 skype 서버 2015으로 업그레이드](../deploy/upgrade-to-skype-for-business-server.md) 를 참조 하세요. <br/> |
|Lync Server 2010 + Lync Server 2013 (이중 모드)  <br/> |먼저, Lync Server 2013로 업그레이드 한 다음 새로운 전체 업그레이드 기능을 사용 하 여 비즈니스용 Skype 서버 2015로 업그레이드 합니다. 그러나 토폴로지가 기본 Lync Server 2010 인 경우 lync server 2013 구성 요소를 Lync Server 2010로 롤백한 다음 비즈니스용 Skype 서버 2015로 직접 업그레이드할 수도 있습니다. 이 경우에는 전체 업그레이드를 사용할 수 없으며 Lync Server 2010과 비즈니스용 Skype 서버 2015 사이에는 직접 공존을 사용 해야 합니다. 3 번은 지원 되지 않지만 동시 존재는 지원 됩니다.  <br/> |
|Lync Server 2010  <br/> |새 비즈니스용 Skype 서버 2015 풀을 가져온 다음 사용자를이 새 풀로 마이그레이션합니다. 그런 다음 이전 Lync Server 2010 풀을 해제할 수 있습니다. Lync server 2010에서 비즈니스용 Skype 서버 2015로 업그레이드 하는 것은 Lync Server 2010에서 Lync Server 2013로 업그레이드 하는 것과 비슷합니다. [Lync server 2010에서 Lync server 2013로 마이그레이션을](https://go.microsoft.com/fwlink/p/?LinkId=526615)참조 하세요.  <br/> |
|Office Communications Server 2007 R2  <br/> | 다음 두 옵션 중 하나를 선택 합니다. <br/>  새 비즈니스용 Skype 서버 2015 환경을 설정 합니다. <br/>  또는 하드웨어 및 소프트웨어가 비즈니스용 Skype 서버 2015 요구 사항을 충족 하는 경우 새로운 전체 업그레이드 기능을 사용 하 여 Lync Server 2013로 업그레이드 한 다음 비즈니스용 Skype 서버 2015으로 업그레이드 합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 서버 요구 사항](requirements-for-your-environment/server-requirements.md) 및 [Office Communications Server 2007 R2에서 Lync server 2013로의 마이그레이션을](https://go.microsoft.com/fwlink/p/?LinkId=526616)참조 하십시오.  <br/> |
   
> [!NOTE]
> SQL Server 2014은 비즈니스용 Skype 서버 2015에서 지원 되지만 Lync Server 2013에서는 지원 되지 않습니다. SQL Server 2012에서 SQL Server 2014로 업그레이드 하려면 먼저이 문서에 설명 된 대로 전체 업그레이드 방법을 사용 하 여 풀을 비즈니스용 Skype 서버 2015로 업그레이드 해야 합니다. 그런 다음 SQL server 2012에서 SQL Server 2014로 업그레이드할 수 있으며 [Sql server 2014 업그레이드를](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx)참조 하세요. 데이터베이스 요구 사항에 대 한 자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](requirements-for-your-environment/server-requirements.md)참조 하세요. 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Lync Server 2013에서 비즈니스용 Skype 서버 2015로의 업그레이드 계획
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

새로운 전체 업그레이드 기능을 사용 하 여 Lync Server 2013 시스템을 비즈니스용 Skype 서버 2015로 업그레이드할 수 있습니다. 전체 업그레이드는 인증서를 백업 하 고, 서버 구성 요소를 제거 하 고, 로컬 데이터베이스를 업그레이드 하 고, 비즈니스용 Skype 서버 2015 역할을 설치 하는 한 클릭 솔루션을 제공 합니다. 현재 위치 업그레이드를 통해 기존 하드웨어 및 서버 투자를 유지 하 여 비즈니스용 Skype 서버 2015를 배포 하기 위한 전반적인 비용을 절감할 수 있습니다.
  
> [!NOTE]
> 전체 업그레이드를 사용 하면 비즈니스용 Skype 서버로 업그레이드할 때 동일한 하드웨어를 사용할 수 있습니다. 그러나 같은 하드웨어를 다시 사용 하는 것은 동일한 성능 용량으로 변환 되지 않습니다. Lync Server 2013 및 비즈니스용 Skype 서버 2015에 대 한 성능 부하는 동일 하 게 예상 되어서는 안 됩니다. 
  
> [!NOTE]
> 전체 업그레이드에서는 비즈니스용 Skype 서버에 대 한 고가용성 또는 재해 복구를 지원 하지 않습니다. 
  
전체 업그레이드는 Lync Server 2013 풀을 오프 라인으로 전환 하 여 비즈니스용 Skype 서버 2015 풀로 업그레이드 하는 작업을 수행 합니다. 
  
### <a name="create-an-in-place-upgrade-plan"></a>전체 업그레이드 계획 만들기

다음을 포함 하는 계획을 만듭니다.
  
1. 현재 토폴로지에 대 한 이해
    
    > [!NOTE]
    > 전체 업그레이드를 실행 하기 전에 LRS Admin tool for Lync Server 2013을 먼저 제거 해야 합니다. Lync Server 2013에 대 한 LRS 관리 도구는 비즈니스용 Skype 서버 2015과 함께 사용할 수 없습니다. 전체 업그레이드를 실행 한 후에는 새 LRS 관리 도구를 설치 합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에 대 한 Microsoft Lync 대화방 시스템 관리 웹 포털](https://go.microsoft.com/fwlink/?LinkID=544807) 을 참조 하세요.
  
2. 업그레이드에 대 한 기본 풀입니다.
    
3. 보관 및 모니터링 데이터베이스를 업그레이드할지 아니면 새로 만들지를 지정 합니다.
    
4. 오프 라인 또는 사용자 이동을 사용 하 여 전체 업그레이드 방법을 사용할 수 있습니다. 사용자 이동의 일부로 기본 풀과 연결 된 전역 회의 디렉터리도 마이그레이션해야 합니다. 
    
5. 영향을 받는 사용자에 대 한 통신 계획
    
6. 업그레이드에 실패 하는 경우의 백업 계획
    
업그레이드 중에 기본 풀에 있는 모든 사용자는 업그레이드가 완료 될 때까지 서비스를 사용할 수 없게 됩니다. 보조 풀을 사용 하는 경우에는 업그레이드 전에 보조 풀로 이동 하 여 사용자에 게 영향을 주지 않도록 할 수 있습니다. 업그레이드 후에 사용자를 기본 풀로 다시 이동 합니다.
  
### <a name="in-place-upgrade-methods"></a>전체 업그레이드 방법

현재 위치 업그레이드에는 다음과 같은 두 가지 시나리오가 있습니다. 
  
- 사용자 이동 방법-사용자에 대 한 가동 중지 시간이 필요 하지 않습니다. 
    
- 가동 중지 시간이 필요한 오프 라인 방법
    
유지 관리 기간 중에는 오프 라인 메서드 업그레이드를 예약 하 고 사용자에 게 가동 중지 시간을 알리는 것이 좋습니다.
  
> [!NOTE]
> Lync Server 2013의 페어링 된 풀을 업그레이드 하는 경우 두 풀을 비즈니스용 Skype 서버 2015로 업그레이드 하려는 경우 첫 번째 풀을 업그레이드 한 후에 두 번째 풀을 즉시 업그레이드 해야 합니다. 한 풀이 Lync Server 2013을 실행 하 고 두 번째 풀이 비즈니스용 Skype 서버 2015를 실행 하는 경우 재해 복구 옵션이 최소화 됩니다. 예를 들어 한 풀이 2013을 실행 중이 고 두 번째는 2015이 고 재해가 발생 한 경우에는 연결 된 풀이 버전이 같을 때 재해 모드에서 풀 장애 조치 (failover)가 지원 되지 않으므로 데이터 손실이 발생할 수 있습니다. 
  
#### <a name="in-place-upgrade-offline-method"></a>전체 업그레이드 오프 라인 방법

사용자 풀 간에 사용자를 이동 하지 않으려면이 방법을 사용 합니다. 업그레이드 중에는 사용자가 Lync 또는 비즈니스용 Skype 서비스를 사용할 수 없게 됩니다. 
  
다음 다이어그램에서는이 프로세스의 개요를 보여 줍니다.
  
![Lync 2013을 Skype 사용자에 게 오프 라인으로 설정](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> 연결 된 풀이 있는 경우 업그레이드 전에 unpair 하지 마십시오. 
  
서버 풀 업그레이드를 시작한 후에는 전체 풀의 업그레이드를 완료 해야 합니다. 비즈니스용 Skype 서버는 풀 일부만 업그레이드 하는 것을 지원 하지 않습니다. 
  
#### <a name="move-users-method-no-user-downtime"></a>사용자 이동 방법 (사용자 가동 중지 시간 없음)
<a name="bkmk_MoveUsersMethod"> </a>

이 방법을 사용 하려면 업그레이드를 시작 하기 전에 사용자를 다른 풀로 이동 합니다. 업그레이드 중에는 사용자가 Lync services를 사용할 수 있습니다. 업그레이드 된 풀로 이동한 후 비즈니스용 Skype를 사용할 수 있습니다. 다음 다이어그램에서는이 프로세스의 개요를 보여 줍니다.
  
> [!IMPORTANT]
> 사용자 이동의 일부로 기본 풀과 연결 된 전역 회의 디렉터리도 마이그레이션해야 합니다. PSTN 전화 접속 회의는 여전히 연결 된 풀 대신 업그레이드 되는 풀에 대 한 ConferenceID를 확인 합니다. 따라서 업그레이드 중에 풀에 예약 된 PSTN 회의에 액세스 하려면 전화 회의 디렉터리를 이동 해야 합니다. 
  
![풀이 업그레이드 된 후 풀로 다시 이동 되기 전에 사용자를 다른 풀로 이동 하는 것을 보여 주는 스윔 다이어그램입니다.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>하드웨어 업그레이드를 위해 사용자 이동
<a name="bkmk_MoveUsersMethod"> </a>

 하드웨어가 [비즈니스용 Skype 서버 2015의 서버 요구 사항을](requirements-for-your-environment/server-requirements.md)충족 하지 않는 경우 비즈니스용 skype 서버 2015 환경을 새로 설치 하 고 사용자를 이동 합니다. 다음 다이어그램에서는이 Lync Server 2010의 업그레이드 프로세스에 대 한 개요를 보여 줍니다. 
  
![Lync server 기본 프런트 엔드 풀의 사용자가 비즈니스용 Skype 서버 2015 및 해제 중인 Lync Server 풀로 이동 하는 것을 보여 주는 스윔 레인 다이어그램입니다.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>전체 업그레이드 프로세스

 다음 단계를 사용 하 여 Lync Server 2013에서 비즈니스용 Skype 서버 2015로 업그레이드 합니다.
  
1. 업그레이드 전에 모든 데이터베이스를 백업 합니다.
    
2. 업그레이드할 모든 서비스가 실행 중 상태 인지 확인 합니다.
    
3. 토폴로지 작성기를 사용 하 여 토폴로지 파일을 업그레이드 하 고 게시 합니다.
    
4. 모든 프런트 엔드 서버에서 모든 서비스를 중지 합니다.
    
5. 비즈니스용 Skype 서버에 필요한 새 필수 구성 요소를 설치 합니다.
    
6. 각 프런트 엔드 서버에서 전체 업그레이드를 시작 합니다.
    
7. 업그레이드가 완료 되 면 모든 서비스를 다시 시작 합니다.
    
   - 프런트 엔드 풀에 대해 Start-CsPool 명령을 사용 하 여 서비스를 다시 시작 합니다.
    
   - 프런트 엔드 서버가 아닌 경우에는 CSWindowsService를 사용 합니다.
    
> [!NOTE]
>  기존 보관 및 모니터링 데이터베이스를 업그레이드 하지 않으려면 토폴로지를 업그레이드 하기 전에 종속성을 제거 합니다. 새 보관 및 모니터링 데이터베이스를 만들려면 업그레이드 중에 새 SQL 저장소를 만들어 풀과 연결 하면 됩니다. 이 작업을 수행 하는 방법에 대 한 단계는[비즈니스용 Skype 서버 2015으로 업그레이드](../deploy/upgrade-to-skype-for-business-server.md)항목에서 찾을 수 있습니다. 전체 업그레이드 > 비즈니스용 Skype 서버에 대 한 고가용성 또는 재해 복구를 지원 하지 않습니다. 사용자의 서비스가 중단 되지 않도록 하려면 [Move users 메서드 (사용자가 중단 되지 않음)](upgrade.md#bkmk_MoveUsersMethod) 를 사용 하 여 업그레이드 합니다. 업그레이드 프로세스 중 > xds-복제본은 사용 가능한 공간이 가장 많은 디스크 드라이브의 로컬 공유 폴더에 놓입니다. 해당 디스크를 나중에 제거 하는 경우 서비스가 시작 되지 않는 등의 문제가 발생할 수 있습니다.
  
### <a name="upgrade-order"></a>업그레이드 순서

내부에서 외부로 토폴로지를 업그레이드 합니다. 먼저 모든 풀을 업그레이드 한 다음에 지 서버와 CMS (중앙 관리 저장소) 풀을 차례로 클릭 합니다. 
  
### <a name="kerberos-authentication-considerations"></a>Kerberos 인증 고려 사항

웹 서비스에 대해 Kerberos 인증을 사용 하는 경우에는 전체 업그레이드가 완료 된 후 Kerberos 계정을 다시 할당 하 고 암호를 다시 설정 해야 합니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은 [Kerberos 인증 설정을](https://go.microsoft.com/fwlink/p/?LinkId=530342)참조 하십시오.
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Lync Server 2013 및 Lync Server 2010의 동시 사용 지원
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Lync Server 2013 또는 Lync Server 2010과 동일한 토폴로지에서 비즈니스용 Skype 서버 2015을 실행할 수는 있지만, 동일한 토폴로지에서 3 개를 모두 가질 수는 없습니다.
  
Lync Server 2010와 Lync Server 2013 사이에 공존 하는 경우 전체 토폴로지를 Lync Server 2013로 업그레이드 한 다음, 현재 위치 업그레이드를 사용 하 여 비즈니스용 Skype 서버 2015로 업그레이드 하는 것이 좋습니다. 자세한 내용은 [Lync server 2010에서 Lync server 2013로 마이그레이션을](https://go.microsoft.com/fwlink/p/?LinkId=526615)참조 하세요.
  
토폴로지가 주로 Lync Server 2010 이면 비즈니스용 Skype 서버 2015로 토폴로지를 업그레이드 하기 전에 lync server 2013 구성 요소를 Lync Server 2010에 롤백합니다. 이 경우에는 전체 업그레이드의 이점을 잃게 되며 Lync Server 2010과 비즈니스용 Skype 서버 2015 간에 공존 토폴로지가 유지 됩니다.
  
다음 다이어그램은 Lync Server 2013 및 Lync Server 2010을 사용 하는 비즈니스용 Skype 서버 2015의 동시 사용 지원을 보여 줍니다.
  
![Lync Server 2013 또는 Lync Server 2010을 사용 하 여 비즈니스용 Skype 서버 2015에 대 한 coexistance 지원을 보여주는 다이어그램](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>기존 Sba (survivable Branch 기기 및 서버를 사용한 업그레이드 프로세스
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

비즈니스용 Skype 서버 2015는 SBA (Sba (survivable Branch 기기의) 또는 SBS (Sba (survivable Branch Server)의 전체 업그레이드를 지원 하지 않습니다.
  
그러나 Lync Server 2010 또는 Lync Server 2013 SBA/SBS와 함께 비즈니스용 Skype 서버 데이터 센터 공존을 지원 합니다. 
  
연결 된 분기를 사용 하 여 Lync Server 2013 프런트 엔드 (FE) 풀의 전체 업그레이드를 계획할 때는 기존 사용자를 Lync Server 2013 SBA/SBS에 남길 수 있습니다. 업그레이드 하는 동안 SBA/SBS 사용자는 복구 모드로 전환 되며 업그레이드가 완료 되 면 일반 기능으로 돌아갑니다. 복원 모드 중의 사용자 환경에 대 한 자세한 내용은 [Lync Server 2013의 분기 사이트 복구 기능](https://technet.microsoft.com/library/gg398715.aspx)을 참조 하십시오.
  
Lync Server 2010 토폴로지를 비즈니스용 Skype 서버 2015로 마이그레이션하는 경우 SBA/SBS는 Lync Server 2013로의 마이그레이션과 마찬가지로 토폴로지에 다시 추가 해야 합니다. 필요한 단계는 [Sba (survivable Branch 어플라이언스를 Lync Server 2013 프런트 엔드 풀에 연결을](https://technet.microsoft.com/library/jj688026.aspx)참조 하세요.
  
Lync Server 2010 및 Lync Server 2013의 공존 토폴로지에 대 한 자세한 내용은 ' Lync Server 2013 및 Lync Server 2010의 동시 사용 지원 ' 섹션에 나오는 권장 사항에 먼저 맞춤을 따르십시오.
  
## <a name="see-also"></a>참고 항목
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[비즈니스용 Skype 서버 2015로 업그레이드](../deploy/upgrade-to-skype-for-business-server.md)
  
[비즈니스용 Skype 서버 2015에 대 한 환경 요구 사항](requirements-for-your-environment/environmental-requirements.md)
  
[비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항](requirements-for-your-environment/server-requirements.md)
