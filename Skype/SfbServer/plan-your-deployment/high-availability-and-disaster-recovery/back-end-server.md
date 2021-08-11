---
title: 백 엔드 서버의 고가용성 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: AlwaysOn 가용성 그룹, AlwaysOn 장애 조치(failover) 클러스터 인스턴스, 데이터베이스 미러링 및 장애 조치(failover) 클러스터링을 비즈니스용 Skype 서버 백 엔드 서버 고가용성 옵션에 대해 자세히 SQL 대해 자세히 알아보습니다.
ms.openlocfilehash: 5cc325b0726afab72581f679873fe454d8302dec5a478685c24e84b430a25017
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318741"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>백 엔드 서버의 고가용성 비즈니스용 Skype 서버
 
AlwaysOn 가용성 그룹, AlwaysOn 장애 조치(failover) 클러스터 인스턴스, 데이터베이스 미러링 및 장애 조치(failover) 클러스터링을 비즈니스용 Skype 서버 백 엔드 서버 고가용성 옵션에 대해 자세히 SQL 대해 자세히 알아보습니다.
  
백 엔드 서버의 고가용성을 향상하기 위해 다음과 같은 네 가지 옵션이 있습니다.
  
- 데이터베이스 미러링
    
- AlwaysOn 가용성 그룹
    
- AlwaysOn FCI(장애 조치(Failover) 클러스터 인스턴스)
    
- SQL 클러스터링
    
이러한 솔루션 중 하나를 사용하는 것은 선택 사항이지만 조직의 비즈니스 연속성을 유지하는 것이 좋습니다. 그렇지 않으면 데이터베이스 서버가 하나만 다운되어도 데이터가 손실될 비즈니스용 Skype 서버 있습니다. 
  
토폴로지 작성기만 사용하여 데이터베이스 미러링을 설정할 수 있습니다. AlwaysOn 가용성 그룹, AlwaysOn 장애 조치(failover) 클러스터 인스턴스 또는 SQL 장애 조치(failover) 클러스터링의 경우 SQL Server 사용하여 고가용성 솔루션을 만든 다음 토폴로지 작성기에서 이를 프런트 엔드 풀과 연결합니다.
  
재해 복구를 위해 다른 프런트 엔드 풀과 페어링된 프런트 엔드 풀에서 백 엔드 서버 고가용성을 사용하는 경우 두 풀에서 동일한 백 엔드 고가용성 솔루션을 사용해야 합니다. 
  
## <a name="database-mirroring"></a>데이터베이스 미러링

비즈니스용 Skype 서버 다음 데이터베이스 소프트웨어를 사용하여 미러링을 지원할 수 있습니다.
  
- SQL Server 2019는 Enterprise Edition Standard Edition

- SQL Server 2017에서는 Enterprise Edition Standard Edition

- SQL Server 2016에서는 Enterprise Edition Standard Edition

- SQL Server 2014에서는 Enterprise Edition Standard Edition
    
- SQL Server 2012 SP2 및 CU2는 Enterprise Edition STANDARD EDITION
    

> [!NOTE]
> SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(failover) 클러스터 인스턴스) 및 SQL 장애 조치(failover) 클러스터링 방법만 2019에서 지원되는 유일한 비즈니스용 Skype 서버 있습니다.
    
비동기 데이터베이스 미러링은 백 엔드 서버의 고가용성에 대해 지원되지 비즈니스용 Skype 서버. 이 문서의 나머지부분에서 데이터베이스 미러링은 다른 명시적 설명이 없는 한 동기 데이터베이스 미러링을 의미합니다. 
  
프런트 엔드 풀에 데이터베이스 미러링을 배포하면 풀에 있는 모든 비즈니스용 Skype 서버 데이터베이스(이 풀에 있는 경우) 및 응답 그룹 응용 프로그램 데이터베이스 및 통화 파킹 응용 프로그램 데이터베이스(해당 응용 프로그램이 풀에서 실행되는 경우)를 포함하여 풀의 모든 비즈니스용 Skype 서버 데이터베이스가 미러링됩니다. 
  
데이터베이스 미러링을 사용하는 경우 서버에 대해 공유 저장소를 사용할 필요가 없습니다. 각 서버는 로컬 저장소에 데이터베이스 복사본을 유지합니다. 
  
미러링되지 않은 데이터베이스 미러링을 배포할 수도 있습니다. 하지만 벡 엔드 서버의 장애 조치(failover)를 자동화할 수 있도록 미러링 모니터를 사용하는 것이 좋습니다. 그렇지 않으면 관리자가 수동으로 장애 조치를 호출해야 합니다. 참고로, 미러링 모니터가 구축된 경우라도 필요하면 관리자가 수동으로 백 엔드 서버의 장애 조치를 호출할 수 있습니다.
  
미러링 모니터를 사용하는 경우 여러 쌍의 백 엔드 서버에 대해 단일 미러링 모니터를 사용할 수 있습니다. 미러링 모니터와 백 엔드 서버 쌍 간을 엄격하게 1:1로 일치시킬 필요는 없습니다. 여러 백 엔드 서버 쌍에 단일 미러링 모니터를 사용하는 구축의 경우 각 백 엔드 서버 쌍에 별도의 미러링 모니터를 사용하는 토폴로지보다 복원력은 다소 저하됩니다. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>백 엔드 서버 미러링 계획 지침

일반적으로 미러링 모니터 서버가 포함된 두 개의 백 엔드 서버 사이에 SQL 미러링을 설정하려면 다음이 필요합니다.
  
- 기본 서버의 서버 버전은 SQL Server 미러링을 SQL 합니다.
    
- 기본, 미러, 미러링 모니터 서버(배포된 경우)는 모두 SQL Server 버전이 동일해야 합니다. 
    
- 기본 및 미러는 SQL Server의 에디션이 동일해야 합니다. 미러링 모니터 서버는 에디션이 다를 수 있습니다.
    
미러링 SQL 지원되는 버전과 SQL 모범 사례에 대한 자세한 내용은 MSDN 라이브러리의 ["데이터베이스](/sql/database-engine/database-mirroring/database-mirroring-witness) 미러링 지원"을 참조합니다.
  
서버 미러링을 구성하기 전에 먼저 데이터베이스 사용 SQL 설정해야 합니다. 자세한 내용은 "데이터베이스 미러링 또는 AlwaysOn 가용성 그룹에 대한 로그인 계정 [설정(SQL Server)"을 참조합니다.](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)
  
SQL 미러링을 사용할 경우 데이터베이스 복구 모드는 항상 **전체** 로 설정되므로 트랜잭션 로그 크기를 자세히 모니터링하고 백 엔드 서버의 디스크 공간이 부족해지지 않도록 정기적으로 트랜잭션 로그를 백업해야 합니다. 트랜잭션 로그 백업의 빈도는 로그 증가 속도에 따라 달라지며, 이는 다시 프런트 엔드 풀에서의 사용자 활동으로 인해 발생하는 데이터베이스 트랜잭션에 따라 달라집니다. 올바르게 계획할 수 있도록 Lync 배포 작업에 트랜잭션 로그 증가량이 얼마나 예상되는지 확인하는 것이 좋습니다. 다음 문서에서는 SQL 백업 및 로그 관리에 대한 추가 정보를 제공합니다.
  
> [!IMPORTANT]
> 토폴로지 작성기 또는 cmdlet을 사용하여 SQL 미러링을 설정 및 제거하는 것은 기본, 미러 및 미러링 카메라(필요한 경우) 서버가 모두 동일한 도메인에 속하는 경우만 지원됩니다. 다른 도메인에 있는 서버 간에 SQL 미러링을 설정하려는 경우에는 SQL Server 설명서를 참조하십시오. 

> [!NOTE]
> SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(failover) 클러스터 인스턴스) 및 SQL 장애 조치(failover) 클러스터링 방법이 비즈니스용 Skype 서버 선호됩니다.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>데이터베이스 미러링을 통해 자동 백 엔드 서버 장애 조치(failover)에 대한 복구 시간

데이터베이스 미러링을 통해 자동 백 엔드 장애 조치(failover)의 경우 RTO(복구 시간 목표)에 대한 엔지니어링 대상은 5분입니다. 동기 데이터베이스 미러링 때문에 백 엔드 서버 오류 시에는 데이터 손실이 예상되지 않습니다. 단, 드물지만 프런트 엔드 서버와 백 엔드 서버가 모두 서버 간에 데이터를 이동하는 동안 동시에 다운되는 경우는 예외입니다. RPO(복구 지점 목표)에 대한 엔지니어링 대상은 5분입니다.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>데이터베이스 미러링을 통해 백 엔드 서버 오류 발생 시 사용자 환경

오류가 발생한 동안 사용자 환경에 미치는 영향은 오류의 특성과 토폴로지에 따라 달라집니다.
  
데이터베이스 미러링을 사용하며 미러링을 구성한 경우 보안 주체가 실패하면 백 엔드 서버 장애 조치(failover)가 자동으로 빠르고 진행됩니다. 활성 사용자는 진행 중인 세션에서 중단이 발생했는지조차 알아채지 못합니다.
  
미러링크가 구성되어 있는 경우 관리자가 수동으로 장애 조치(failover)를 호출하는 데 시간이 다소 걸릴 수 있습니다. 이 시간 동안 활성 사용자가 영향을 받을 수 있습니다. 세션은 약 30분 동안 정상으로 계속됩니다. 기본이 아직 복원되지 않은 경우 또는 관리자가 백업으로 전환하지 않은 경우 사용자는 복구 모드로 전환됩니다. 즉, Lync Server에서 연락처 추가와 같은 영구 변경이 필요한 작업을 수행할 수 없습니다.
  
기본 서버와 미러 백 엔드 서버에 모두 오류가 발생하는 경우 또는 이러한 서버 중 하나와 미러링 모니터에 오류가 발생하는 경우 기본 서버가 실행 중이더라도 백 엔드 서버를 사용할 수 없습니다. 이러한 경우 활성 사용자는 일정 시간이 지난 후 복원 모드로 전환됩니다.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn 가용성 그룹 및 AlwaysOn 장애 조치(failover) 클러스터 인스턴스

비즈니스용 Skype 서버 AlwaysOn 가용성 그룹은 활성/활성이 아닌 활성/수동으로만 지원됩니다. 
  
AlwaysOn 가용성 그룹 또는 AlwaysOn 장애 조치(failover) 클러스터 인스턴스를 사용하기 위해 먼저 SQL Server 고가용성 솔루션을 설정하고 구성합니다. 그런 다음 토폴로지 작성기에서 프런트 엔드 풀과 연결합니다.

비즈니스용 Skype 서버 다음 데이터베이스 소프트웨어로 AlwaysOn을 지원할 수 있습니다.

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition 있는 내용은 아래 참고를 참조하세요.

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition 있는 내용은 아래 참고를 참조하세요.

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition 있는 경우 아래 참고를 참조하세요.

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 및 CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019, 2017 및 201 비즈니스용 Skype 서버6만 2019에서 지원됩니다.

> [!NOTE]
> Always On 가용성  그룹은 SQL 2016, 2017 및 2019 Standard Edition에서 지원되지 않지만 Always On 장애 조치(Failover) 클러스터 인스턴스를 사용할 수 있습니다. 자세한 [내용은 SQL Server 2016의 버전](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) 및 지원되는 기능을 참조합니다.
  
> [!IMPORTANT]
> 여러 AlwaysOn 가용성 그룹 인스턴스의 인스턴스 이름은 같아야 합니다. 
  
AlwaysOn 가용성 그룹을 배포하는 단계는 에서 [Deploy an AlwaysOn Availability Group on a Back End Server를 비즈니스용 Skype 서버.](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)
  
## <a name="sql-server-failover-clustering"></a>SQL Server 장애 조치(failover) 클러스터링

비즈니스용 Skype 서버 다음 데이터베이스 SQL Server 장애 조치(failover) 클러스터링을 지원할 수 있습니다.
  
- SQL Server 2019는 Enterprise Edition Standard Edition

- SQL Server 2017에서는 Enterprise Edition Standard Edition

- SQL Server 2016에서는 Enterprise Edition Standard Edition

- SQL Server 2014에서는 Enterprise Edition Standard Edition
    
- SQL Server 2012 SP2 및 CU2는 Enterprise Edition STANDARD EDITION

장애 조치(failover) 클러스터링을 SQL 프런트 엔드 풀을 배포하기 전에 먼저 SQL Server 클러스터를 설정하고 구성해야 합니다. SQL Server 2012의 장애 조치(failover) 클러스터링에 대한 모범 사례 및 설정 지침은 을(를) [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) 참조하세요.

> [!NOTE]
> SQL Server 2019, 2017 및 SQL Server 2016만 2019에서 지원되는 비즈니스용 Skype 서버 있습니다.
    
장애 조치(failover) 클러스터링을 SQL 프런트 엔드 풀을 배포하기 전에 먼저 SQL Server 클러스터를 설정하고 구성해야 합니다. 2014 및 2016의 장애 조치(failover) 클러스터링에 대한 모범 사례 및 설정 SQL Server 를 [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) 참조하세요. 2008년의 장애 조치(failover) 클러스터링에 SQL Server 을 [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)) 참조합니다.
  
SQL Server를 설치하는 경우 데이터베이스 위치 및 로그 파일 위치를 관리할 SQL Server Management Studio를 설치해야 합니다. SQL Server Management Studio는 SQL Server를 설치할 때 선택적 구성 요소로 설치됩니다.
