---
title: 비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 요약:이 항목을 사용 하 여 비즈니스용 Skype 서버 2015 서버를 준비 합니다. 하드웨어, OS, 데이터베이스, 소프트웨어, 서버 팜의 성공적인 설치 및 배포를 보장 하는 데 도움이 되는 모든 시스템 요구 사항 및 권장 사항이 여기에 나와 있습니다.
ms.openlocfilehash: 02ccebca4eebef84638992dd88ba45040e733d19
ms.sourcegitcommit: b1f7f1435c5e72c2eea4069fbb0bea29b197cb80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "44342458"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항
 
**요약:** 이 항목을 사용 하 여 비즈니스용 Skype 서버 2015 서버를 준비 합니다. 하드웨어, OS, 데이터베이스, 소프트웨어, 서버 팜의 성공적인 설치 및 배포를 보장 하는 데 도움이 되는 모든 시스템 요구 사항 및 권장 사항이 여기에 나와 있습니다.

Active Directory, DNS 또는 인증서와 같은 환경 요구 사항을 찾으려는 경우 [비즈니스용 Skype 서버 2015 문서에 대 한 환경 요구 사항을](environmental-requirements.md) 확인할 수 있습니다.
  
예상할 수 있듯이 비즈니스용 Skype 서버 2015의 배포를 시작 하기 전에 몇 가지 준비 작업을 수행 해야 합니다. 이 문서에서는 다음에 대 한 계획을 안내 합니다.
  
- [비즈니스용 Skype 서버 2015의 하드웨어](server-requirements.md#Hardware)
  
- [비즈니스용 Skype 서버 2015의 운영 체제](server-requirements.md#OS)
  
- [비즈니스용 Skype 서버 2015에서 작동 하는 백 엔드 데이터베이스](server-requirements.md#DBs)
  
- [비즈니스용 Skype 서버 2015 배포 전에 설치 해야 하는 소프트웨어](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 하드웨어
<a name="Hardware"> </a>

이제 토폴로지가 다운 되었으므로 (그리고, 그렇지 않은 경우 [비즈니스용 Skype 서버 2015에 대 한 토폴로지 기본 사항](../../plan-your-deployment/topology-basics/topology-basics.md) 확인), 서버를 고려해 야 합니다. 비즈니스용 Skype 서버 2015 서버에는 64 비트 하드웨어가 필요 합니다. 하드웨어에 대 한 권장 사항은 다음과 같습니다. 이러한 기능은 요구 사항은 아니지만 최적의 성능을 유지 하는 데 필요한 요구 사항을 반영 합니다. 이 문서에는 환경에 따라이 두 개 이상의 요구 사항이 필요한 지를 결정 하는 데 도움이 되는 용량 계획 설명서가 포함 되어 있습니다.
  
프런트 엔드 서버, 백 엔드 서버, Standard Edition server 및 영구 채팅 서버에 대 한 권장 하드웨어:
  
|**하드웨어 구성 요소**|**권장**|
|:-----|:-----|
|CPU  <br/> |64 비트 이중 프로세서, 16 진수 코어, 2.26 ghz 이상  <br/> Intel Itanium 프로세서는 비즈니스용 Skype 서버 2015 역할에 지원 되지 않습니다.  <br/> |
|메모리  <br/> |32 기가바이트 (GB)입니다.  <br/> |
|공간이  <br/> |일  <br/> • 72 GB 이상의 사용 가능한 디스크 공간을 사용 하는 8 개 이상의 1만 RPM 하드 디스크 드라이브 (raid 1 및 6을 사용 하는 디스크 2 개)  <br/> 또는  <br/> • Ssd (솔리드 스테이트 드라이브)는 8 1만 RPM 기계적 디스크 드라이브에 동일한 사용 가능 공간 및 이와 유사한 성능을 제공할 수 있습니다.  <br/> |
|네트워크  <br/> |1 개의 이중 포트 네트워크 어댑터, 1Gbps 이상 (네트워크 어댑터 2 개를 사용할 수 있지만 단일 MAC 주소와 단일 IP 주소를 사용 하 여 팀을 만들어야 합니다.)  <br/> 프런트 엔드 서버, 백 엔드 서버, Standard Edition 서버 및 영구 채팅 서버에는 이중 또는 멀티홈 구성이 지원 **되지 않습니다** . <br/> 운영 체제에 노출 되지 않고 서버 하드웨어를 모니터링 하 고 관리 하는 데 사용 되는 경우 DRAC 또는 ILO와 같은 대역 외 관리 시스템을 사용할 수 있습니다. 이 시나리오는 다중 홈 서버를 구성 하지 않으며 지원 됩니다.  <br/> |
   
에 지 서버, 독립 실행형 중재 서버, 동영상 Interop 서버 및 디렉터에 대 한 권장 하드웨어:
  
|**하드웨어 구성 요소**|**권장**|
|:-----|:-----|
|CPU  <br/> |64 비트 이중 프로세서, 쿼드 코어, 2.26 ghz 이상  <br/> Intel Itanium 프로세서는 비즈니스용 Skype 서버 2015 역할에 지원 되지 않습니다.  <br/> |
|메모리  <br/> |16gb  <br/> |
|공간이  <br/> |일  <br/> • 72 GB 이상의 사용 가능한 디스크 공간이 있는 4 개 이상의 1만 RPM 하드 디스크 드라이브 (디스크가 2x RAID 1 구성에 있어야 함).  <br/> 또는  <br/> • Ssd (솔리드 스테이트 드라이브)는 4 1만 RPM 기계적 디스크 드라이브에 동일한 사용 가능 공간 및 이와 유사한 성능을 제공할 수 있습니다.  <br/> |
|네트워크  <br/> |1 개의 이중 포트 네트워크 어댑터, 1Gbps 이상 (네트워크 어댑터 2 개를 사용할 수 있지만 단일 MAC 주소와 단일 IP 주소를 사용 하 여 팀을 만들어야 합니다.)  <br/> 이중 또는 멀티홈 구성은 비디오 Interop 서버 및 디렉터에서 지원 **되지 않습니다** . <br/> 에 지 서버에는 이중 포트 네트워크 어댑터, 1Gbps 이상 (두 개의 연결 된 네트워크 어댑터, 총 4 개, 단일 MAC 주소와 단일 IP 주소를 사용 하 여 각 쌍을 그룹화 하 고 총 두 쌍에 대해 연결 된 두 개의 네트워크 어댑터가 필요 합니다.)  <br/> 독립 실행형 중재 서버에서 특정 PSTN IP 주소 구성을 허용 하기 위해 추가 Nic (네트워크 인터페이스 카드)를 설치 하는 것이 지원 됩니다.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 운영 체제
<a name="OS"> </a>

하드웨어를 마련 했으면 운영 체제 (OS)를 설치 해야 합니다. 비즈니스용 Skype 서버 2015을 설치 및 사용 하는 데 사용할 수 있는 OS가 여기에 해당 합니다.
  
|||
|:-----|:-----|
|Windows Server 2019 (비즈니스용 Skype 누적 업데이트 9 이상)이 필요 합니다. <br/> |Windows Server 2016 (비즈니스용 Skype 누적 업데이트가 5 이상 필요 합니다. 자세한 내용은 [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016)를 참조 하십시오.  <br/> ||
|필요한 업데이트가 모두 설치 된 Windows Server 2012 R2 데이터 센터 OS  <br/> |모든 필수 업데이트가 설치 된 Windows Server 2012 R2 Standard OS  <br/> |
|모든 필수 업데이트가 설치 된 Windows Server 2012 데이터 센터 OS  <br/> |모든 필수 업데이트가 설치 된 Windows Server 2012 Standard OS  <br/> |
   
이 목록에 없는 경우에도 제대로 작동 하지 않으면 비즈니스용 Skype 서버 2015의 새 설치에 대해 시도해 보세요.

> [!NOTE]
> OS의 전체 업그레이드는 Lync Server 2013에서 지원 되지 않습니다. 별도의 풀을 배포 하 고 다른 운영 체제를 사용 하 여 새 풀로 사용자를 마이그레이션해야 합니다. 풀에 있는 모든 서버는 동일한 OS 버전을 가져야 합니다.
  
> [!NOTE]
> Windows Server 2008 R2가이 목록에 없는 것을 발견 했을 수 있습니다. 이는 SFB에 사용 되는 모든 새 서버에 대해 Windows Server 2012 R2가 권장 되기 때문입니다. Lync Server 2013이 이미 설치 되어 있는 기존 서버가 있고 해당 사용자의 전체 업그레이드를 수행할 예정인 경우에만 Windows Server 2008 R2를 사용 해야 합니다. Windows Server 2008 R2는 1/13/2015의 기본 지원 수명 주기의 끝에 도달 했으며 1/14/2020의 지원 기간 종료에 도달 합니다.
  
최신 서비스 팩 외에 다음과 같은 업데이트가 설치 되어 있는지 확인 하는 것이 좋습니다.
  
- Windows Server 2012의 경우, 업그레이드 전에 기술 자료 문서 2858668을 설치 해야 합니다. [여기에서 가져옵니다](https://support.microsoft.com/kb/2858668/).
    
- Windows Server 2012 R2가 있는 경우 업그레이드 하기 전에 기술 자료 문서 2982006을 설치 하세요. [여기에서 찾을 수](https://support.microsoft.com/kb/2982006/)있습니다.
    
- Windows Server 2008 R2 box (위의 참고 자료 참조)에서 업그레이드 하는 경우 먼저 기술 자료 문서 2533623을 설치 해야 합니다. [이 링크](https://support.microsoft.com/kb/2533623/)는 다음과 같습니다.
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 작동 하는 백 엔드 데이터베이스
<a name="DBs"> </a>


비즈니스용 Skype 서버 2015 Standard Edition을 설치할 때 SQL Server 2014 Express (64 비트 버전)도 자동으로 설치 됩니다.
  
비즈니스용 Skype 서버 2015 Enterprise Edition은 다소 복잡 하지만 지원 되는 목록은 아래 (모두 64 비트 버전입니다. 32 비트 버전을 사용 하지 마십시오.)가 표시 됩니다.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64 비트 버전), 최신 서비스 팩을 실행 하는 것이 좋습니다. <br/> |Microsoft SQL Server 2017 Enterprise (64 비트 버전), 최신 서비스 팩을 실행 하는 것이 좋습니다. <br/> |Microsoft SQL Server 2016 Enterprise (64 비트 버전) 서비스 팩 1 이상이 필요 하며, 비즈니스용 Skype 누적 업데이트 7 이상 (비즈니스용[Skype 누적 업데이트 다운로드](https://support.microsoft.com/help/3061064))을 사용 하 여 실행 해야 합니다.  <br/> |Microsoft SQL Server 2014 Enterprise (64 비트 버전)에서는 누적 업데이트 6 이상 ([누적 업데이트 6 다운로드](https://support.microsoft.com/kb/3031047/))을 사용 하 여 실행 해야 합니다.  <br/> |Microsoft SQL Server 2012 Enterprise (64 비트 버전), 최신 서비스 팩을 실행 하는 것이 좋습니다.  <br/> |
|Microsoft SQL Server 2019 Standard (64 비트 버전)-최신 서비스 팩을 실행 하는 것이 좋습니다. <br/> |Microsoft SQL Server 2017 Standard (64 비트 버전)-최신 서비스 팩을 실행 하는 것이 좋습니다. <br/> |Microsoft SQL Server 2016 Standard (64 비트 버전) 서비스 팩 1 이상이 필요 하며 비즈니스용 Skype 누적 업데이트 7 이상을 실행 해야 합니다 (비즈니스용[Skype 누적 업데이트 다운로드](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Standard (64 비트 버전)에서는 누적 업데이트 6 이상 ([누적 업데이트 6 다운로드](https://support.microsoft.com/kb/3031047/))을 사용 하 여 실행 해야 합니다.  <br/> |Microsoft SQL Server 2012 Standard (64 비트 버전)-최신 서비스 팩을 실행 하는 것이 좋습니다.  <br/> |
   
여기에 나열 된 SQL Server 버전이 표시 되지 않는 경우에는 사용할 수 없습니다.
  
- 또한 모니터링 서버 역할에 대 한 SQL Server Reporting Services도 설치 해야 합니다.
- 잘 연결 된 SQL 백 엔드에서는 비즈니스용 Skype 프런트 엔드에 대 한 연결이 저속 연결을 통해 수행 되는 것이 아니라 로컬 이어야 합니다. 
- 두 개 이상의 풀 간에 SQL 백 엔드를 공유 하는 것은 지원 되지 않습니다.

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 저장소
모임 콘텐츠 파일(예: PowerPoint 프레젠테이션)이 첨부 파일로 보관됩니다. Exchange 준수 데이터와 함께 비즈니스용 Skype 보관 데이터를 저장 하려면 exchange 배포에 Exchange를 사용 하 고 최대 저장소 크기가 모임 콘텐츠 파일의 저장을 지원 하는지 확인 해야 합니다. Microsoft Exchange 통합 옵션을 사용 하 여 보관을 배포 하 고 사용 하도록 설정 하기 전에 Exchange를 배포 해야 합니다. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 보관에 대 한 하드웨어 및 소프트웨어 요구 사항
  
보관은 정의 된 서버 역할이 아니므로 보관을 위해 별도의 서버를 설치할 필요가 없습니다. 통합 데이터 수집 에이전트는 모든 Enterprise Edition 프런트 엔드 풀 및 모든 Standard Edition 서버에서 자동으로 설치 및 활성화 됩니다. 토폴로지 작성기를 사용 하 여 보관 토폴로지를 사용 하도록 설정 하 고 게시 해야 합니다.
    
보관은 비즈니스용 Skype 서버 파일 저장소를 사용 하 여 모임 콘텐츠 파일을 임시로 저장 하므로 보관을 위해 별도의 파일 저장소를 설정 하지 않아도 됩니다.
    
Microsoft Message Queuing이 필요 하지 않습니다.
    
보관 저장소에 대 한 인프라를 설정 해야 합니다. 여기에는 SQL Server를 사용 하 여 Exchange 또는 보관 저장소를 선택 하는 작업이 포함 됩니다.   비즈니스용 skype 서버 보관 인프라 요구 사항은 비즈니스용 Skype 서버를 배포 하는 경우와 동일 합니다. 자세한 내용은 [비즈니스용 Skype 환경에 대 한 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)참조 하세요. 
  
> [!NOTE]
> Exchange 서버에 없는 사용자를 지원 하거나 Microsoft Exchange 통합 옵션을 사용 하지 않으려는 경우에는 64 비트 SQL Server 데이터베이스를 사용 하 여 보관 저장소를 배포 해야 합니다. 
    
보관을 배포 하 고 사용 하도록 설정 하기 전에 SQL Server 플랫폼을 설정 해야 합니다. 토폴로지를 게시하는 데 사용될 계정에 적절한 관리자 권한 및 권한이 있는 경우 토폴로지를 게시할 때 보관 데이터베이스(LcsLog)를 만들 수 있습니다. 나중에 설치 절차의 일부로 포함 하 여 데이터베이스를 만들 수도 있습니다. SQL Server에 대 한 자세한 내용은 [Sql server 설명서](https://go.microsoft.com/fwlink/p/?linkID=129045)를 참조 하십시오.
    
보관에 대 한 부하 증가는 중요할 수 있습니다. 따라서 보관이 사용 하도록 설정 된 프런트 엔드 서버에 대 한 디스크 공간이 충분 한지 확인 해야 합니다.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL 미러링, SQL 클러스터링 및 SQL Always On

비즈니스용 Skype 서버 2015에서 SQL 미러링 또는 SQL 클러스터링을 사용할 수 있으며,이 기능은 지원 됩니다. 비즈니스용 Skype 서버 토폴로지 작성기를 통해 설정 된 SQL 미러링 SQL 클러스터링을 설정 하려면 SQL Server에서 작업을 수행 해야 합니다.
  
SQL 클러스터링에 대 한 활성/수동 구성이 지원 새로운 확인 해야 합니다. 수동 노드를 다른 SQL 인스턴스와 공유 하지 않습니다.
  
장애 조치 (failover) 클러스터링에 대 한 다음을 사용할 수 있습니다.
  
노드가 두 개인 경우:
  
- Microsoft SQL Server 2019 Standard (64 비트 버전)-최신 서비스 팩을 실행 하는 것이 좋습니다.

- Microsoft SQL Server 2017 Standard (64 비트 버전)-최신 서비스 팩을 실행 하는 것이 좋습니다.

- Microsoft SQL Server 2016 Standard (64 비트 버전) 서비스 팩 1 이상 최신 서비스 팩을 실행 하는 것이 좋습니다.

- Microsoft SQL Server 2014 Standard (64 비트 버전)-최신 서비스 팩을 실행 하는 것이 좋습니다.
    
-  Microsoft SQL Server 2012 Standard (64 비트 버전)-최신 서비스 팩을 실행 하는 것이 좋습니다.

16 노드:

- Microsoft SQL Server 2019 Enterprise (64 비트 버전), 최신 서비스 팩을 실행 하는 것이 좋습니다.

- Microsoft SQL Server 2017 Enterprise (64 비트 버전), 최신 서비스 팩을 실행 하는 것이 좋습니다.

- Microsoft SQL Server 2016 Enterprise (64 비트 버전) 서비스 팩 1 이상 최신 서비스 팩을 실행 하는 것이 좋습니다.
  
- Microsoft SQL Server 2014 Enterprise (64 비트 버전), 최신 서비스 팩을 실행 하는 것이 좋습니다.
    
- Microsoft SQL Server 2012 Enterprise (64 비트 버전), 최신 서비스 팩을 실행 하는 것이 좋습니다.

> [!IMPORTANT]
> 업그레이드를 위해 프런트 엔드 서버에서 업그레이드 전에 최소한 SQL Server 2012 SP1이 설치 되어 있는지 확인 합니다. 바로 다운로드 하려면 SP1 [링크가 여기에 나와](https://www.microsoft.com/download/details.aspx?id=35575) 있습니다.
  
SQL 미러링을 더 자세히 확인 해야 하는 경우에는 비즈니스용 Skype 서버 2015 항목의 백 엔드 서버 고가용성이 제공 됩니다. 비즈니스용 Skype 서버 2015에 대해 SQL Server 클러스터링 구성 클러스터링을 준비 하는 단계를 설명 합니다. SQL의 장애 조치 (failover) 클러스터링에 대 한 추가 링크는 [2014](https://technet.microsoft.com/library/hh231721.aspx), [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)및 [2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)에도 있습니다.
  
> [!NOTE]
> 2015 릴리스의 신규 기능은 SQL server Always On을 지원 합니다. 지원 되며,이를 통해 [백 엔드 서버 고가용성 (비즈니스용 Skype 서버 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) 항목)에서 자세한 내용을 확인할 수 있습니다.

> [!NOTE]
> SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서는 더 이상 지원 되지 않습니다. AlwaysOn 가용성 그룹, AlwaysOn 장애 조치 (Failover) 클러스터 인스턴스 (FCI) 및 SQL 장애 조치 (failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 더 선호 됩니다.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>비즈니스용 Skype 서버 2015 배포 전에 설치 해야 하는 소프트웨어
<a name="Software"> </a>

비즈니스용 Skype 서버 2015을 실행 하는 모든 서버에 대해 설치 하거나 구성 해야 할 몇 가지 사항이 있습니다. 그 후에는 특정 서버 역할에 대 한 추가 요구 사항입니다.

  
 **모든 서버:**
  
|**소프트웨어/역할**|**세부 정보**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |모든 비즈니스용 Skype 서버 서버에 Windows PowerShell 3.0이 설치 되어 있어야 합니다.  <br/> • Windows Server 2012 또는 Windows Server 2012 r 2에서 설치를 수행 하는 경우 이미 있는 설정입니다.  <br/> • Windows Server 2008 r 2에서 업그레이드를 수행 하는 경우 [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595) 를 다운로드 하 여 가져올 수 있습니다. <br/> **팁:** 올바른 PowerShell이 있으면 PowerShell 프롬프트로 이동 하 여 입력 하 여 BuildVersion 6.2.9200.0 이상 인지 확인 `$PSVersionTable` 합니다. 이렇게 하면 필요한 정보를 가져올 수 있습니다.  <br/> |
|Microsoft .NET Framework  <br/> |WCF services는 **서버 관리자**에 Windows 기능으로 설치 되어 있는 **기능** 으로, 필요한 다운로드는 없습니다. <br/> •이 기능을 설치 하는 경우,이 기능이 이미 설치 되어 있고,이를 수행 하 고 있는지 확인 해야 하는 경우에는 다음과 같이 **HTTP 정품 인증** 옵션도 확인 되 고 설치 됩니다. <br/> ![.NET Framework 4.5 기능 ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) 에 나와 있는 HTTP 활성화 옵션을 보여 주는 스크린샷 HTTP 정품 인증을 설치 하려면 추가 팝업을 설치 해야 하는 경우에도 걱정할 필요가 없습니다. 정상, 확인을 클릭 하 고 계속 진행 합니다. 이 팝업이 표시 되지 않으면 이미 설치 되어 있는 것으로 가정 하 고 계속 진행 합니다.  <br/> Microsoft .NET Framework는 대개 Windows Server 2012 R2 또는 Windows Server 2016가 설치 된 경우에 설치 됩니다. 비즈니스용 Skype 서버는 다음 Microsoft .NET Framework 버전에서 작동 합니다.  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 (비즈니스용 Skype Server CU 5 이상 버전)  <br/> • .NET 4.7.2 (비즈니스용 Skype Server CU 6 이상 버전)  <br/>  • .NET 4.8 (비즈니스용 Skype 서버 CU 9 이상 릴리스) <br/>  .NET Framework 3.5는 Windows Server 2008 R2 컴퓨터에 기본적으로 설치 될 수 있지만 (업그레이드 전에 확실히 확인 해야 함) 실제로 Windows Server 2012/Windows Server 2012 R2 서버 (새 설치의 경우)에는 표시 되지 않습니다. 이를 추가 하려면 설치 드라이브 또는 미디어 (Windows Server가 설치 된 위치 또는 설치 파일이 현재 있는 위치)에 대 한 액세스 권한이 있어야 합니다. 그리고 나 서이를 서버 관리자에 게 기능으로 설치 하 고 설치 미디어 (특히 **\sources\sxs** 폴더)를 가리킨 다음 설치를 계속 진행 합니다. <br/> |
|미디어 파운데이션  <br/> |Windows Server 2016의 경우 Windows Server 2012 및 Windows Server 2012 R2 Windows Media 형식 런타임이 Microsoft Media Foundation과 함께 설치 됩니다.  <br/> 회의에 사용 되는 모든 프런트 엔드 서버 및 Standard Edition 서버에는 통화 대기, 알림 및 응답 그룹 응용 프로그램이 알림 및 음악을 재생 하는 Windows Media 오디오 (.wma) 파일을 실행 하기 위한 windows Media 형식 런타임이 필요 합니다.  <br/> |
|Windows Identity Foundation  <br/> |비즈니스용 Skype 서버 2015에 대 한 서버 간 인증 시나리오를 지원 하려면 Windows Identity Foundation 3.5이 필요 합니다.  <br/> • Windows Server 2012 및 Windows Server 2012 r 2에서는 아무 것도 다운로드할 필요가 없습니다. **서버 관리자**를 열고 **역할 및 기능 추가 마법사로**이동 합니다. **Windows Identity Foundation 3.5** 이 **Features** 섹션 아래에 표시 됩니다. 이 확인란을 선택 하면 문제가 없는 것입니다. 그렇지 않으면 선택 하 고 다음을 클릭 하 여 **설치** 단추에 연결 합니다. <br/> |
|원격 서버 관리 도구  <br/> |역할 관리 도구: AD DS 및 AD LDS 도구  <br/> |
   
 **프런트 엔드 서버 및 Standard Edition 서버에도 다음이 필요 합니다.**
  
|**소프트웨어/역할**|**세부 정보**|
|:-----|:-----|
|IIS(인터넷 정보 서비스)  <br/> |IIS는 모든 프런트 엔드 서버 뿐만 아니라 모든 Standard Edition 서버에서 다음 모듈을 선택한 상태로 사용 해야 합니다.  <br/> • 일반적인 HTTP 기능: 기본 문서, HTTP 오류, 정적 콘텐츠  <br/> • 상태 및 진단: HTTP 로깅, 로깅 도구, 추적  <br/> • 성능: 정적 콘텐츠 압축, 동적 콘텐츠 압축  <br/> • 보안: 요청 필터링, 클라이언트 인증서 매핑 인증, Windows 인증  <br/> • 응용 프로그램 개발: .NET 확장성 3.5, .NET 확장성 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI Extensions, ISAPI 필터  <br/> • 관리 도구: IIS 관리 콘솔, IIS 관리 스크립트 및 도구  <br/> 또한 익명 액세스만 필요 하지만 IIS를 설치할 때 목록에서 선택할 수 있는 위치를 사용할 수 있습니다.  <br/> |
|Windows Media 형식 런타임  <br/> | Windows Server 2016, Windows Server 2012 및 Windows Server 2012 r 2의 경우 **서버 관리자**에 **미디어 파운데이션** 기능을 설치 해야 합니다. 이제는 비즈니스용 skype 서버 2015 설치를 실행 하는 것이 좋지만,이를 설치 하 라는 메시지가 표시 되지만 비즈니스용 Skype 서버 2015 설치를 계속 하기 전에 서버를 다시 부팅 해야 합니다. 보다 빠른 시간에 수행 하는 것이 좋습니다. <br/> |
|Silverlight  <br/> |[이 링크](https://www.microsoft.com/silverlight/)에는 최신 버전의 Silverlight를 설치할 수 있습니다.  <br/> |
   
> [!NOTE] 
> 부하 분산 장치를 사용 하는 경우 디렉터리 검색을 사용 하도록 설정 해야 할 수도 있습니다. 그렇지 않으면 부하 분산 장치에서 오류를 고려할 수 있는 새 페이지가 로드 됩니다. 

이를 위해 다음과 같은 샘플 PowerShell 스크립트를 실행 하 여이를 자동화할 수 있습니다.

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> 이 명령은 특정 순서 대로 원본 파일을 찾습니다. 온라인 상태인 경우이 명령은 Windows Update에 액세스 합니다. 그러나 오프 라인 상태 이면 명령에 원본 파일을 사용할 수 있는지 확인 해야 합니다. PowerShell을 사용 하 여 역할 및 기능을 설치 하는 방법에 대 한 자세한 내용은 PowerShell 명령을 사용 하는 경우에도 [설치 또는 제거 역할, 역할 서비스 또는 기능](https://technet.microsoft.com/library/hh831809.aspx) 을 설치한 후에 Windows Update를 다시 실행 하는 것을 잊지 마십시오.

 **디렉터에는 다음도 필요 합니다.**
  
다음 모듈을 선택한 상태로 IIS를 선택 합니다.
  
- 일반 HTTP 기능
    
  - 기본 문서
    
  - HTTP 오류
    
  - 정적 콘텐츠
    
- 상태 및 진단
    
  - HTTP 로깅
    
  - 로깅 도구
    
  - 추적은
    
- 성능
    
  - 정적 콘텐츠 압축
    
- 보안
    
  - 요청 필터링
    
  - 클라이언트 인증서 매핑 인증
    
  - Windows 인증
    
- 응용 프로그램 개발
    
  - .NET 확장성 3.5
    
  - .NET Extensibility 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI 확장
    
  - ISAPI 필터
    
(여기에서 소개 하는 것은 프런트 엔드 서버 및 Standard Edition 서버와 동일한 모듈이 며, 동적 콘텐츠 압축 및 관리 도구를 그대로 유지 하는 것입니다.)
  
여기에는 다음과 같은 몇 가지 PowerShell 코드가 포함 되어 있습니다.
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **영구 채팅 서버에도 다음이 필요 합니다.**
  
메시지 큐 (MSMQ 라고도 함) Windows Server 구성 요소 이며, 서버 관리자의 Features (기능) 섹션에 설치할 수 있습니다. 이에 대 한 자세한 내용은 [메시지 큐 설치 및 관리](https://technet.microsoft.com/library/cc771474.aspx)를 참조 하세요.
  
 **마지막 생각:**
  
모든 프런트 엔드 서버 또는 독립 실행형 중재 서버에는 Microsoft Internet Security and 가속이 (ISA) 서버 클라이언트 소프트웨어 또는 다른 Winsock 계층화 된 LSP (레이어 서비스 공급자) 소프트웨어 (여기에 포함 된 모든 타사 방화벽 또는 바이러스 백신 네트워크 검사 소프트웨어)를 설치 하지 마세요. 해당 소프트웨어를 설치할 때 잘못 된 미디어 트래픽 성능이 나타났습니다.
  

