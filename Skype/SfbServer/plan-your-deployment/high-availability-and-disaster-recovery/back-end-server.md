---
title: 비즈니스용 Skype 서버의 백 엔드 서버 고가용성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: AlwaysOn 가용성 그룹, AlwaysOn 장애 조치 클러스터 인스턴스, 데이터베이스 미러링, SQL 장애 조치 클러스터링을 비롯 하 여 비즈니스용 Skype 서버에서 지원 되는 백 엔드 서버 고가용성 옵션에 대해 알아봅니다.
ms.openlocfilehash: 4c814e525b3a1d0900e7162255ec4d7e86d79605
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888617"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 백 엔드 서버 고가용성
 
AlwaysOn 가용성 그룹, AlwaysOn 장애 조치 클러스터 인스턴스, 데이터베이스 미러링, SQL 장애 조치 클러스터링을 비롯 하 여 비즈니스용 Skype 서버에서 지원 되는 백 엔드 서버 고가용성 옵션에 대해 알아봅니다.
  
백 엔드 서버의 가용성을 높이기 위해 다음 네 가지 옵션을 사용할 수 있습니다.
  
- 데이터베이스 미러링
    
- AlwaysOn 가용성 그룹
    
- FCI (Failover) 클러스터 인스턴스 (AlwaysOn)
    
- SQL 장애 조치 클러스터링
    
이러한 솔루션 중 하나를 사용 하는 것은 선택 사항 이지만 조직의 비즈니스 연속성을 유지 관리 하는 것이 좋습니다. 그렇지 않으면 단일 데이터베이스 서버를 종료 하면 중요 한 비즈니스용 Skype 서버 데이터가 손실 될 수 있습니다. 
  
토폴로지 작성기만 사용 하 여 데이터베이스 미러링을 설정할 수 있습니다. AlwaysOn 가용성 그룹, AlwaysOn 장애 조치 클러스터 인스턴스 또는 SQL 장애 조치 (failover) 클러스터링의 경우 SQL Server를 사용 하 여 고가용성 솔루션을 만든 다음 토폴로지 작성기를 사용 하 여 프런트 엔드 풀과 연결할 수 있습니다.
  
재해 복구를 위해 다른 프런트 엔드 풀과 쌍을 이루는 프런트 엔드 풀에서 백 엔드 서버 가용성을 사용 하는 경우 두 풀에서 동일한 백 엔드 고가용성 솔루션을 사용 해야 합니다. 
  
## <a name="database-mirroring"></a>데이터베이스 미러링

비즈니스용 Skype 서버는 다음 데이터베이스 소프트웨어와의 미러링을 지원 합니다.
  
- SQL Server 2019 (Enterprise Edition 및 Standard Edition 모두)

- SQL Server 2017 (Enterprise Edition 및 Standard Edition 모두)

- SQL Server 2016 (Enterprise Edition 및 Standard Edition 모두)

- SQL Server 2014 (Enterprise Edition 및 Standard Edition 모두)
    
- SQL Server 2012 SP2 및 CU2 (Enterprise Edition 및 Standard Edition 모두 해당)
    

> [!NOTE]
> SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. AlwaysOn 가용성 그룹, AlwaysOn 장애 조치 (Failover) 클러스터 인스턴스 (FCI) 및 SQL 장애 조치 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 유일 하 게 지원 되는 옵션입니다.
    
비즈니스용 Skype 서버에서 백 엔드 서버의 고가용성을 사용할 수 없는 경우 비동기 데이터베이스 미러링이 지원 되지 않습니다. 이 문서의 나머지 부분에서 데이터베이스 미러링은 명시적으로 명시 되지 않은 경우 동기 데이터베이스 미러링을 의미 합니다. 
  
프런트 엔드 풀에서 데이터베이스 미러링을 배포 하는 경우 중앙 관리 저장소를 포함 하 여 해당 풀에 있는 모든 비즈니스용 Skype 서버 데이터베이스가 미러링 되며 응답 그룹 응용 프로그램 데이터베이스 및 통화 대기 시간에도 해당 됩니다. 응용 프로그램이 풀에서 실행 되는 경우 해당 데이터베이스 
  
데이터베이스 미러링에서는 서버에 공유 저장소를 사용할 필요가 없습니다. 각 서버는 로컬 저장소에 데이터베이스 복사본을 유지 합니다. 
  
미러링 모니터 서버와 함께 데이터베이스 미러링을 배포 하도록 선택할 수 있습니다. 미러링 모니터 서버를 사용 하 여 백 엔드 서버의 장애 조치를 자동으로 수행할 수 있도록 하는 것이 좋습니다. 그렇지 않으면 관리자가 장애 조치를 수동으로 호출 해야 합니다. 미러링 모니터 서버가 배포 된 경우에도 관리자는 필요한 경우 백 엔드 서버 장애 조치를 수동으로 호출할 수 있습니다.
  
미러링 모니터 서버를 사용 하는 경우 백 엔드 서버의 여러 쌍에 단일 미러링 모니터를 사용할 수 있습니다. 백 엔드 서버와 witnesses의 짝이 엄격한 1:1 대응 기능은 없습니다. 여러 백 엔드 서버 쌍에 단일 미러링 모니터를 사용 하는 배포는 각 백 엔드 서버 쌍에 대해 별도의 감시가 있는 토폴로지로 탄력적으로 복구 되지 않습니다. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>백 엔드 서버 미러링 계획에 대 한 지침

일반적으로 미러링 모니터로 두 백 엔드 서버 간에 SQL 미러링을 설정 하려면 다음이 필요 합니다.
  
- 주 서버의 SQL Server 버전은 SQL 미러링을 지원 해야 합니다.
    
- 기본, 미러, 미러링 모니터 (배포 된 경우)는 동일한 버전의 SQL Server를 사용 해야 합니다. 
    
- 기본 및 미러에는 동일한 버전의 SQL Server가 있어야 합니다. 미러링 모니터 서버에 다른 버전이 있을 수 있습니다.
    
미러링 모니터 역할에 대해 지원 되는 SQL 버전에 대 한 SQL 모범 사례는 MSDN Library의 ["데이터베이스 미러링 감시"](https://go.microsoft.com/fwlink/p/?LinkId=247345) 를 참조 하세요.
  
서버 미러링을 구성 하기 전에 먼저 SQL 데이터베이스 사용 권한을 올바르게 설정 해야 합니다. 자세한 내용은 ["데이터베이스 미러링 또는 AlwaysOn 가용성 그룹에 대 한 로그인 계정 설정 (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454)을 참조 하세요.
  
SQL 미러링에서는 데이터베이스 복구 모드가 항상 **Full**로 설정 되며,이는 백 엔드 서버의 디스크 공간 부족을 방지 하기 위해 트랜잭션 로그 크기를 면밀 하 게 모니터링 하 고 트랜잭션 로그를 정기적으로 백업 해야 한다는 것입니다. 트랜잭션 로그 백업의 빈도는 로그 증가 속도에 따라 다르며,이는 프런트 엔드 풀의 사용자 활동에서 발생 하는 데이터베이스 트랜잭션에 따라 달라 집니다. 계획을 적절 하 게 수행할 수 있도록 Lync 배포 작업 부하에 예상 되는 트랜잭션 로그 성장이 얼마나 되는지 결정 하는 것이 좋습니다. 다음 문서는 SQL 백업 및 로그 관리에 대 한 추가 정보를 제공 합니다.
  
> [!IMPORTANT]
> 토폴로지 작성기 또는 cmdlet을 사용 하 여 SQL 미러링을 설정 및 제거 하는 것은 주, 미러, 미러링 모니터 (원하는 경우) 서버가 모두 동일한 도메인에 속해 있는 경우에만 지원 됩니다. 다른 도메인의 서버 간에 SQL 미러링을 설정 하려면 SQL Server 설명서를 참조 하세요. 

> [!NOTE]
> SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. AlwaysOn 가용성 그룹,이 어 장애 조치 (Failover) 클러스터 인스턴스 (FCI) 및 SQL 장애 조치 (failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 선호 됩니다.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>데이터베이스 미러링을 사용 하 여 자동 백 엔드 서버 장애 조치 복구 시간

데이터베이스 미러링으로 자동 백 엔드 장애 조치를 사용 하는 경우 RTO (복구 시간 목표)에 대 한 엔지니어링 대상은 5 분입니다. 동기 데이터베이스 미러링 때문에, 서버 간에 데이터를 이동 하는 동안 프런트 엔드 서버와 백 엔드 서버가 동시에 종료 되는 경우를 제외 하 고는 백 엔드 서버 오류 시 데이터 손실이 예상 되지 않습니다. RPO (복구 시점 목표)에 대 한 엔지니어링 대상은 5 분입니다.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>데이터베이스 미러링으로 백 엔드 서버 오류 발생 시 사용자 환경

오류 발생 시 사용자 환경은 오류의 성격 및 토폴로지에 따라 달라 집니다.
  
데이터베이스 미러링을 사용 하 고 미러링 모니터 서버가 구성 되어 있는 경우 주 서버가 실패 하면 백 엔드 서버 장애 조치는 자동으로 신속 하 게 발생 합니다. 활성 사용자는 진행 중인 세션을 크게 중단 하지 않아야 합니다.
  
미러링 모니터가 구성 되어 있지 않은 경우 관리자가 장애 조치를 수동으로 호출 하는 데 시간이 걸릴 수 있습니다. 이 기간 동안에는 활성 사용자에 게 영향을 줄 수 있습니다. 약 30 분 동안에는 세션을 계속 합니다. 기본 상태가 복원 되지 않거나 관리자가 백업으로 장애 조치 되지 않으면 사용자가 복원 모드로 전환 되어 Lync Server (예: 대화 상대 추가)에 영구적으로 변경 해야 하는 작업을 수행할 수 없습니다.
  
주 서버와 미러 백 엔드 서버가 둘 다 실패 하거나 이러한 서버와 미러링 모니터 서버가 실패 한 경우 백 엔드 서버를 사용할 수 없게 됩니다 (아직 작동 중인 주에 포함). 이 경우 활성 사용자는 잠시 후에 복원 모드로 전환 됩니다.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn 가용성 그룹 및 AlwaysOn 장애 조치 (Failover) 클러스터 인스턴스

비즈니스용 Skype 서버는 활성/passive 또는 액티브/액티브는 제외 하 고 AlwaysOn 가용성 그룹만 지원 합니다. 
  
AlwaysOn 가용성 그룹 또는 AlwaysOn 장애 조치 (Failover) 클러스터 인스턴스를 사용 하려면 먼저 SQL Server를 사용 하 여 고가용성 솔루션을 설정 하 고 구성 합니다. 그런 다음 토폴로지 작성기를 사용 하 여 프런트 엔드 풀과 연결할 수 있습니다.

비즈니스용 Skype 서버는 다음 데이터베이스 소프트웨어를 사용 하 여 AlwaysOn을 지원 합니다.

- SQL Server 2019 Enterprise Edition

- 제한 사항이 적용 되는 SQL Server 2019 Standard Edition의 아래 참고 자료를 참조 하세요.

- SQL Server 2017 Enterprise Edition

- 제한 사항이 적용 되는 SQL Server 2017 Standard Edition의 아래 참고 자료를 참조 하세요.

- SQL Server 2016 Enterprise Edition

- 제한 사항이 적용 되는 SQL Server 2016 Standard Edition의 아래 참고 자료를 참조 하세요.

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 및 CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019, 2017 및 2016은 비즈니스용 Skype Server 2019에서 지원 되는 유일한 버전입니다.

> [!NOTE]
> SQL 2016, 2017 및 2019 Standard Edition에서는 always On 가용성 그룹이 지원 **되지** 않지만 항상 장애 조치 (Failover) 클러스터 인스턴스에서 사용할 수 있습니다. 자세한 내용은 [SQL Server 2016의 버전 및 지원 되는 기능](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) 을 참조 하세요.
  
> [!IMPORTANT]
> 여러 AlwaysOn 가용성 그룹 인스턴스의 인스턴스 이름은 동일 해야 합니다. 
  
AlwaysOn 가용성 그룹 배포 단계는 [비즈니스용 Skype 서버의 백 엔드 서버에서 AlwaysOn 가용성 그룹 배포](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)를 참조 하세요.
  
## <a name="sql-server-failover-clustering"></a>SQL Server 장애 조치 클러스터링

비즈니스용 Skype 서버는 다음 데이터베이스 소프트웨어를 사용 하 여 SQL Server 장애 조치 (failover) 클러스터링을 지원 합니다.
  
- SQL Server 2019 (Enterprise Edition 및 Standard Edition 모두)

- SQL Server 2017 (Enterprise Edition 및 Standard Edition 모두)

- SQL Server 2016 (Enterprise Edition 및 Standard Edition 모두)

- SQL Server 2014 (Enterprise Edition 및 Standard Edition 모두)
    
- SQL Server 2012 SP2 및 CU2 (Enterprise Edition 및 Standard Edition 모두 해당)

SQL 장애 조치 (failover) 클러스터링을 사용 하려면 먼저 프런트 엔드 풀을 배포 하기 전에 SQL Server 클러스터를 설정 하 고 구성 해야 합니다. SQL Server 2012의 장애 조치 (failover) 클러스터링에 대 한 모범 사례 [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)및 설정 지침은을 참조 하세요.

> [!NOTE]
> SQL Server 2019, 2017 및 SQL Server 2016는 비즈니스용 Skype 서버 2019에서 지원 되는 유일한 버전입니다.
    
SQL 장애 조치 (failover) 클러스터링을 사용 하려면 먼저 프런트 엔드 풀을 배포 하기 전에 SQL Server 클러스터를 설정 하 고 구성 해야 합니다. SQL Server 2014 및 2016의 장애 조치 (failover) 클러스터링에 대 한 모범 사례 [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)및 설정 지침은을 참조 하세요. SQL Server 2008의 장애 조치 (failover) [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)클러스터링에 대 한 자세한 내용은을 참조 하세요.
  
SQL Server를 설치할 때 데이터베이스 및 로그 파일 위치의 위치를 관리 하려면 SQL Server Management Studio를 설치 해야 합니다. Sql server Management Studio는 SQL Server를 설치할 때 선택적 구성 요소로 설치 됩니다.
  
