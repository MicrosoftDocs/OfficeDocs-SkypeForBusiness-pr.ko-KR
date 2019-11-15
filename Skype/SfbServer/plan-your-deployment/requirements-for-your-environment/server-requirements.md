---
title: 비즈니스용 Skype 서버 2015의 서버 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 요약:이 항목을 사용 하 여 비즈니스용 Skype 서버 2015 서버를 준비 합니다. 서버 팜을 성공적으로 설치 및 배포 하는 데 도움이 되도록 하드웨어, OS, 데이터베이스, 소프트웨어, 모든 시스템 요구 사항 및 권장 사항이 여기에 나와 있습니다.
ms.openlocfilehash: 3ca52a6d7a61a3f6b06985bf507461fe9285e337
ms.sourcegitcommit: 4060f20e8e3ce5a0464c12cfebdf8fe3473733fe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626994"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 서버 요구 사항
 
**요약:** 이 항목을 사용 하 여 비즈니스용 Skype 서버 2015 서버를 준비 합니다. 서버 팜을 성공적으로 설치 및 배포 하는 데 도움이 되도록 하드웨어, OS, 데이터베이스, 소프트웨어, 모든 시스템 요구 사항 및 권장 사항이 여기에 나와 있습니다.

Active Directory, DNS 또는 인증서와 같은 환경 요구 사항을 찾고 있는 경우 [비즈니스용 Skype Server 2015 doc에 대 한 환경 요구 사항을](environmental-requirements.md) 확인 하세요.
  
예상 대로 비즈니스용 Skype 서버 2015에 대 한 배포를 시작 하기 전에 몇 가지 준비를 수행 해야 할 수 있습니다. 이 문서에서는 다음에 대 한 계획을 안내 합니다.
  
- [비즈니스용 Skype 서버 2015의 하드웨어](server-requirements.md#Hardware)
  
- [비즈니스용 Skype Server 2015의 운영 체제](server-requirements.md#OS)
  
- [비즈니스용 Skype 서버 2015에서 작동 하는 백 엔드 데이터베이스](server-requirements.md#DBs)
  
- [비즈니스용 Skype Server 2015 배포 전에 설치 해야 하는 소프트웨어](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 하드웨어
<a name="Hardware"> </a>

이제 토폴로지가 내려 지 며 (그렇지 않은 경우 [비즈니스용 Skype Server 2015에 대 한 토폴로지 기본 사항](../../plan-your-deployment/topology-basics/topology-basics.md) 확인), 서버에 대해 고려해 야 할 때가 있습니다. 비즈니스용 Skype 서버 2015 서버에는 64 비트 하드웨어가 필요 합니다. 하드웨어에 대 한 권장 사항은 아래에 있습니다. 이러한 요구 사항은 필요 하지 않지만 최적의 성능에 필요한 요구 사항을 반영 합니다. 이 문서에는 사용자의 상황에 따라 이러한 작업을 수행 해야 하는지 결정 하는 데 도움이 되는 용량 계획 설명서가 있습니다.
  
프런트 엔드 서버, 백 엔드 서버, Standard Edition 서버 및 영구 채팅 서버에 권장 되는 하드웨어:
  
|**하드웨어 구성 요소**|**권장**|
|:-----|:-----|
|%  <br/> |64 비트 듀얼 프로세서, 16 진수 코어, 2.26 ghz 이상.  <br/> 인텔 아이테니엄 프로세서는 비즈니스용 Skype 서버 2015 역할에 지원 되지 않습니다.  <br/> |
|Memory  <br/> |32 기가바이트 (GB).  <br/> |
|공간  <br/> |어떤  <br/> • 최소 72 GB의 무료 디스크 공간을 제공 하는 8 개 이상의 1만 RPM (raid 10을 사용 하는 RAID 1 및 6을 사용 하는 두 개의 디스크)  <br/> 또는  <br/> • Ssd (고체 드라이브)는 8 1만 RPM 기계적 디스크 드라이브에 동일한 여유 공간 및 유사한 성능을 제공할 수 있습니다.  <br/> |
|네트워크  <br/> |1 Gbps 이상의 듀얼 포트 네트워크 어댑터 (2 개의 네트워크 어댑터를 사용할 수 있지만 단일 MAC 주소 및 단일 IP 주소로 팀에 있어야 함).  <br/> 프런트 엔드 서버, 백 엔드 서버, Standard Edition 서버 및 영구 채팅 서버에서는 듀얼 또는 멀티홈 구성이 지원 **되지 않습니다** . <br/> 운영 체제에 표시 되지 않고 서버 하드웨어를 모니터링 하 고 관리 하는 데 사용 되는 동안에는 DRAC 또는 ILO와 같은 대역 외 관리 시스템을 사용할 수 있습니다. 이 시나리오는 멀티홈 서버를 구성 하지 않으며 지원 됩니다.  <br/> |
   
Edge 서버용 권장 하드웨어, 독립 실행형 중재 서버, 영상 Interop 서버, 이사회:
  
|**하드웨어 구성 요소**|**권장**|
|:-----|:-----|
|%  <br/> |64 비트 듀얼 프로세서, 쿼드 코어, 2.26 ghz 이상  <br/> 인텔 아이테니엄 프로세서는 비즈니스용 Skype 서버 2015 역할에 지원 되지 않습니다.  <br/> |
|Memory  <br/> |16gb.  <br/> |
|공간  <br/> |어떤  <br/> • 최소 72 GB의 무료 디스크 공간을 제공 하는 4 개 이상의 1만 RPM 하드 디스크 드라이브 (디스크가 2 배로 RAID 1 구성 되어 있어야 함).  <br/> 또는  <br/> • Ssd (고체 드라이브)는 4 1만 RPM 기계적 디스크 드라이브에 동일한 여유 공간 및 유사한 성능을 제공할 수 있습니다.  <br/> |
|네트워크  <br/> |1 Gbps 이상의 듀얼 포트 네트워크 어댑터 (2 개의 네트워크 어댑터를 사용할 수 있지만 단일 MAC 주소 및 단일 IP 주소로 팀에 있어야 함).  <br/> 듀얼 또는 멀티홈 구성은 비디오 Interop 서버 및 디렉터에 대해 지원 **되지 않습니다** . <br/> Edge 서버에는 이중 포트 네트워크 어댑터용 1 Gbps 이상 (또는 두 개의 연결 된 네트워크 어댑터와 총 4 개, 단일 MAC 주소와 단일 IP 주소로 그룹화 된 각 쌍 중 총 2 쌍) 인 2 개의 네트워크 인터페이스가 필요 합니다.  <br/> 독립 실행형 중재 서버에서 특정 PSTN IP 주소의 구성을 허용 하는 추가 Nic (네트워크 인터페이스 카드)를 설치 하는 것이 지원 됩니다.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>비즈니스용 Skype Server 2015의 운영 체제
<a name="OS"> </a>

하드웨어가 제자리에 있으면 OS (운영 체제)를 설치 해야 합니다. 다음은 비즈니스용 Skype 서버 2015를 설치 하 고 성공적으로 사용 하는 데 사용할 수 있는 OS입니다.
  
|||
|:-----|:-----|
|Windows Server 2019 (비즈니스용 Skype 누적 업데이트 9 이상)이 필요 합니다. <br/> |Windows Server 2016 (비즈니스용 Skype 누적 업데이트 5 이상이 필요 합니다. 자세한 내용은 [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016)를 확인 하세요.  <br/> ||
|필요한 모든 업데이트가 설치 된 Windows Server 2012 R2 Datacenter OS  <br/> |필요한 모든 업데이트가 설치 된 Windows Server 2012 R2 표준 OS.  <br/> |
|필요한 모든 업데이트가 설치 된 Windows Server 2012 데이터 센터 OS  <br/> |필요한 모든 업데이트가 설치 된 Windows Server 2012 표준 OS  <br/> |
   
이 목록에 없는 경우, 제대로 작동 하지 않는 경우 비즈니스용 Skype Server 2015의 새로운 설치에 대해 시도해 보세요.
  
> [!NOTE]
> Windows Server 2008 R2가이 목록에 없는 것을 발견 했을 수 있습니다. SFB에 사용할 모든 새 서버에 대해 Windows Server 2012 R2를 사용 하는 것이 좋습니다. 기존 서버에 Lync Server 2013이 이미 설치 되어 있는 경우에만 Windows Server 2008 R2를 사용 하 고 사용자가 해당 앱의 현재 상태 업그레이드를 수행할 예정인 경우에만 사용할 수 있습니다. Windows Server 2008 R2는 1/13/2015의 기본 지원 수명 종료 날짜에 도달 했으며 1/14/2020의 지원 수명 주기 종료까지 연락 하 게 됩니다.
  
최신 서비스 팩 외에도 다음과 같은 업데이트가 설치 되어 있는지 확인 해야 합니다.
  
- Windows Server 2012의 경우에는 업그레이드 전에 KB 아티클 2858668을 설치 해야 합니다. [여기에서 받으세요](https://support.microsoft.com/kb/2858668/).
    
- Windows Server 2012 R2를 사용 하는 경우 업그레이드 하기 전에 KB 문서 2982006을 설치 하세요. [여기에서 확인할 수](https://support.microsoft.com/kb/2982006/)있습니다.
    
- Windows Server 2008 R2 box (위 참고 참조)에서 업그레이드 하는 경우 KB 문서 2533623를 먼저 설치 하는 것이 더 필요 합니다. [이 링크를](https://support.microsoft.com/kb/2533623/)참고 하세요.
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 작동 하는 백 엔드 데이터베이스
<a name="DBs"> </a>


비즈니스용 Skype Server 2015 Standard Edition을 설치 하는 경우 SQL Server 2014 Express (64 비트 버전)도 자동으로 설치 됩니다.
  
비즈니스용 Skype Server 2015 Enterprise Edition은 조금 더 복잡 하지만 지원 되는 목록은 아래와 같습니다 (모든 것은 64 비트 버전 이며, 32 비트 버전을 사용 하지 마세요).
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다. <br/> |Microsoft SQL Server 2017 Enterprise (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다. <br/> |Microsoft SQL Server 2016 Enterprise (64 비트 버전) 서비스 팩 1 이상에서 비즈니스용 Skype 누적 업데이트 7 이상에서 실행 해야 합니다 (비즈니스용에서[누적 업데이트를 다운로드](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Enterprise (64 비트 버전), 누적 업데이트 6 이상으로 실행 해야 합니다 ([누적 업데이트 6 다운로드](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.  <br/> |
|Microsoft SQL Server 2019 Standard (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다. <br/> |Microsoft SQL Server 2017 Standard (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다. <br/> |Microsoft SQL Server 2016 Standard (64 비트 버전), 서비스 팩 1 이상, 비즈니스용 Skype 누적 업데이트 7 이상에서 실행 해야 합니다 (비즈니스용에서[누적 업데이트를 다운로드](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Standard (64 비트 버전), 누적 업데이트 6 이상 ([누적 업데이트 6 다운로드](https://support.microsoft.com/kb/3031047/))으로 실행 해야 합니다.  <br/> |Microsoft SQL Server 2012 Standard (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.  <br/> |
   
사용 하려는 SQL Server 버전이 여기에 나와 있지 않으면 사용할 수 없습니다.
  
- 또한 모니터링 서버 역할을 위해 SQL Server Reporting Services를 설치 해야 합니다.
- 제대로 연결 된 SQL 백 엔드의 경우 비즈니스용 Skype 프런트 엔드에서의 연결은 저렴 한 속도의 링크를 통해 로컬 이어야 합니다. 
- 두 개 이상의 풀 간에 SQL 백 엔드를 공유 하는 것은 지원 되지 않습니다.

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 저장소
PowerPoint 프레젠테이션과 같은 모임 콘텐츠 파일은 첨부 파일로 보관 됩니다. Exchange 규정 준수 데이터와 함께 비즈니스용 Skype 보관 데이터를 저장 하려는 경우 exchange 배포에 Exchange를 사용 하 고 최대 저장소 크기가 모임 콘텐츠 파일의 저장소를 지원 하는지 확인 해야 합니다. Microsoft Exchange 통합 옵션을 사용 하 여 보관을 배포 하 고 사용 하도록 설정 하기 전에 Exchange를 배포 해야 합니다. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 보관에 대한 하드웨어 및 소프트웨어 요구 사항
  
보관은 정의 된 서버 역할이 아니므로 보관을 위해 별도의 서버를 설치할 필요가 없습니다. 통합 된 데이터 수집 에이전트는 모든 Enterprise Edition 프런트 엔드 풀 및 모든 Standard Edition 서버에 자동으로 설치 되 고 활성화 됩니다. 토폴로지 작성기를 사용 하 여 보관 토폴로지를 사용 하도록 설정 하 고 게시 해야 합니다.
    
보관은 비즈니스용 Skype Server 파일 저장소를 모임 콘텐츠 파일의 임시 저장소에 사용 하므로 보관을 위해 별도의 파일 저장소를 설정 하지 않아도 됩니다.
    
Microsoft Message Queuing이 필요 하지 않습니다.
    
저장소 보관을 위한 인프라를 설정 해야 합니다. 여기에는 SQL Server를 사용 하 여 Exchange 또는 보관 저장소를 선택 하는 작업이 포함 됩니다.   비즈니스용 skype 서버 보관 인프라 요구 사항은 비즈니스용 Skype 서버 배포와 동일 합니다. 자세한 내용은 [비즈니스용 Skype 환경에 대 한 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)참조 하세요. 
  
> [!NOTE]
> Exchange 서버에 없는 사용자를 지원 하거나 Microsoft Exchange 통합 옵션을 사용 하지 않으려는 경우 64 비트 SQL Server 데이터베이스를 사용 하 여 보관 저장소를 배포 해야 합니다. 
    
보관을 배포 하 고 사용 하기 전에 SQL Server 플랫폼을 설정 해야 합니다. 토폴로지를 게시 하는 데 사용 되는 계정에 적절 한 관리자 권한과 사용 권한이 있는 경우, 토폴로지를 게시할 때 LcsLog (보관 데이터베이스)를 만들 수 있습니다. 나중에 설치 절차의 일부로 포함 된 데이터베이스를 만들 수도 있습니다. SQL Server에 대 한 자세한 내용은 [Sql server 설명서](https://go.microsoft.com/fwlink/p/?linkID=129045)를 참조 하세요.
    
보관에 대 한 부하 증가는 중요할 수 있습니다. 따라서 디스크 공간이 보관을 사용 하도록 설정 된 프런트 엔드 서버에 적절 한지 확인 해야 합니다.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL 미러링, SQL 클러스터링 및 SQL은 항상 켜져 있습니다.

비즈니스용 Skype Server 2015에서 SQL 미러링 또는 SQL 클러스터링을 사용할 수 있으며, 지원 되는 기능입니다. 비즈니스용 Skype 서버 토폴로지 작성기를 통해 설정 된 SQL 미러링 SQL 클러스터링을 설정 하는 경우에는 SQL Server에서 수행 됩니다.
  
새로운 기능은 다음과가 지원 되므로 SQL 클러스터링에 대 한 능동/수동 구성이 있는지 확인 합니다. 수동 노드를 다른 SQL 인스턴스와 공유 하지 마세요.
  
장애 조치 클러스터링용으로 사용할 수 있는 작업은 다음과 같습니다.
  
2 노드:
  
- Microsoft SQL Server 2019 Standard (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.

- Microsoft SQL Server 2017 Standard (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.

- Microsoft SQL Server 2016 Standard (64 비트 버전) 서비스 팩 1 이상 최신 서비스 팩으로 실행 하는 것이 좋습니다.

- Microsoft SQL Server 2014 Standard (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.
    
-  Microsoft SQL Server 2012 Standard (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.

16 개 노드:

- Microsoft SQL Server 2019 Enterprise (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.

- Microsoft SQL Server 2017 Enterprise (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.

- Microsoft SQL Server 2016 Enterprise (64 비트 버전) 서비스 팩 1 이상 최신 서비스 팩으로 실행 하는 것이 좋습니다.
  
- Microsoft SQL Server 2014 Enterprise (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.
    
- Microsoft SQL Server 2012 Enterprise (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.

> [!IMPORTANT]
> 업그레이드 하기 전에 프런트 엔드 서버에서 최소 SQL Server 2012 SP1이 설치 되어 있는지 확인 합니다. 지금 바로 다운로드할 경우 SP1 [링크가 나와](https://www.microsoft.com/download/details.aspx?id=35575) 있습니다.
  
SQL 미러링에 대 한 자세한 정보를 알고 싶은 경우 비즈니스용 Skype Server 2015 항목에서 백 엔드 서버의 가용성을 높일 수 있습니다. 비즈니스용 Skype Server 2015에 대 한 SQL Server 클러스터링 구성에는 클러스터링을 준비 하는 단계가 포함 되어 있습니다. SQL의 장애 조치 (failover) 클러스터링에 대 한 추가 링크 ( [2014](https://technet.microsoft.com/library/hh231721.aspx), [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx), [2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx))도 있습니다.
  
> [!NOTE]
> 2015 릴리스의 새로운 기능은 항상 SQL을 지원 한다는 것입니다. 이 기능은 지원 되며 [백 엔드 서버에서 비즈니스용 Skype 서버 2015 항목의](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) 고가용성을 읽을 수 있습니다.

> [!NOTE]
> SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. AlwaysOn 가용성 그룹,이 어 장애 조치 (Failover) 클러스터 인스턴스 (FCI) 및 SQL 장애 조치 (failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 선호 됩니다.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>비즈니스용 Skype Server 2015 배포 전에 설치 해야 하는 소프트웨어
<a name="Software"> </a>

비즈니스용 Skype Server 2015을 실행 하는 모든 서버에 대해 설치 하거나 구성 해야 하는 몇 가지 사항이 있으며 아래에 나열 되어 있습니다. 그 이후에는 특정 서버 역할에 대 한 추가 요구 사항입니다.
  
> [NOTE!] 비즈니스용 Skype 서버 2015는 .NET Framework 4.8을 지원 하지 않습니다.
  
 **모든 서버:**
  
|**소프트웨어/역할**|**세부적인**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |모든 비즈니스용 Skype 서버 서버에는 Windows PowerShell 3.0가 설치 되어 있어야 합니다.  <br/> • Windows Server 2012 또는 Windows Server 2012 R2에 설치 하는 경우 이미 존재 하므로 설정 됩니다.  <br/> • Windows Server 2008 R2에서 업그레이드 하는 경우 [Windows 관리 프레임 워크 3.0](https://www.microsoft.com/download/details.aspx?id=34595) 을 다운로드 하 여 가져올 수 있습니다. <br/> **팁:** 올바른 PowerShell이 있으면 PowerShell 프롬프트로 이동한 후 입력 `$PSVersionTable`하 여 BuildVersion 6.2.9200.0 이상 인지 확인 합니다. 이렇게 하면 필요한 정보를 가져올 수 있습니다.  <br/> |
|Microsoft .NET Framework  <br/> |WCF 서비스는 Windows 기능으로 설치 된 **기능** 으로, **서버 관리자**에는 다운로드가 필요 하지 않습니다. <br/> •이 기능을 설치 하거나, 이미 설치 되어 있고, 체크 인하는 경우에는 다음과 같이 **HTTP 활성화** 옵션도 선택 되 고 설치 되어 있는지 확인 해야 합니다. <br/> ![.NET Framework 4.5 기능 아래에서 HTTP 활성화 옵션을 보여 주는 스크린샷 ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)HTTP 정품 인증을 설치 하기 위해 다른 항목을 설치 해야 하는 추가 팝업이 표시 되는 경우 걱정 하지 마세요. 평소에는 확인을 클릭 하 고 계속 진행 하세요. 이 팝업이 표시 되지 않는 경우에는 이미 설치 되어 있는 것으로 간주 하 여 앞으로 이동 합니다.  <br/> Microsoft .NET Framework는 일반적으로 Windows Server 2012 R2 또는 Windows Server 2016이 설치 되어 있는 경우에 설치 됩니다. 비즈니스용 Skype Server는 다음 Microsoft .NET Framework 버전과 함께 작동 합니다.  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 (비즈니스용 Skype Server CU (5 이상 버전)  <br/>  .NET Framework 3.5은 기본적으로 Windows Server 2008 R2 컴퓨터에 설치 될 수 있습니다 (업그레이드 하기 전에 확인 해야 하는 경우), 실제로 Windows Server 2012/Windows Server 2012 R2 서버에 있지 않습니다 (새 설치의 경우). 이 파일을 추가 하려면 설치 드라이브나 미디어 (Windows Server를 설치 하는 위치 또는 설치 파일이 현재 위치)에 대 한 액세스 권한이 필요 합니다. 그런 다음 서버 관리자에서 기능으로이를 설치 하 고 설치 미디어 (특히 **\sources\sxs** 폴더)를 가리킨 후 설치를 계속 합니다. <br/> |
|미디어 파운데이션  <br/> |Windows Server 2016의 경우 windows Server 2012 및 Windows Server 2012 R2 Windows Media 형식 런타임은 Microsoft Media Foundation을 사용 하 여 설치 합니다.  <br/> 회의에 사용 되는 모든 프런트 엔드 서버와 Standard Edition 서버는 Windows Media 형식 런타임을 통해 통화 공원, 알림 및 응답 그룹 응용 프로그램이 공지 사항 및 음악에 대해 재생 하는 Windows Media 오디오 (.wma) 파일을 실행 해야 합니다.  <br/> |
|Windows Identity Foundation  <br/> |비즈니스용 Skype Server 2015에 대 한 서버 간 인증 시나리오를 지원 하려면 Windows Identity Foundation 3.5이 필요 합니다.  <br/> • Windows Server 2012 및 Windows Server 2012 R2의 경우 아무 것도 다운로드 하지 않아도 됩니다. **서버 관리자**를 열고 **역할 및 기능 추가 마법사**로 이동 합니다. **Windows Id 파운데이션 3.5** 이 **기능** 섹션 아래에 나열 됩니다. 이 확인란이 선택 되어 있다면 문제가 없는 것입니다. 그렇지 않으면 선택 하 고 다음을 클릭 하 여 **설치** 단추에 도달 합니다. <br/> |
|원격 서버 관리 도구  <br/> |역할 관리 도구: AD DS 및 AD LDS 도구  <br/> |
   
 **프런트 엔드 서버와 스탠더드 버전 서버에도 다음이 필요 합니다.**
  
|**소프트웨어/역할**|**세부적인**|
|:-----|:-----|
|IIS (인터넷 정보 서비스)  <br/> |모든 프런트 엔드 서버와 모든 Standard Edition 서버에는 IIS가 필요 하며 다음 모듈이 선택 되어 있습니다.  <br/> • 일반적인 HTTP 기능: 기본 문서, HTTP 오류, 정적 콘텐츠  <br/> • 상태 및 진단: HTTP 로깅, 로깅 도구, 추적  <br/> • 성능: 정적 콘텐츠 압축, 동적 콘텐츠 압축  <br/> • 보안: 요청 필터링, 클라이언트 인증서 매핑 인증, Windows 인증  <br/> • 응용 프로그램 개발: .NET 확장성 3.5, .NET 확장성 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI 확장, ISAPI 필터  <br/> • 관리 도구: IIS 관리 콘솔, IIS 관리 스크립트 및 도구  <br/> 또한 익명 액세스만 필요 하지만, IIS를 설치할 때 목록에서 선택할 수 있는 위치가 없다는 것을 알 수 있습니다.  <br/> |
|Windows Media 형식 런타임  <br/> | Windows Server 2016, Windows Server 2012 및 Windows Server 2012 R2의 경우 **서버 관리자**에서 **Media Foundation** 기능을 설치 해야 합니다. 이제는 비즈니스용 Skype Server 2015 설치를이 방법 없이 시작할 수 있지만, 비즈니스용 Skype Server 2015 설치를 계속 하려면 먼저이를 설치 하 라는 메시지가 표시 되지만 서버를 다시 부팅 해야 합니다. 사전에 좋은 시간. <br/> |
|Silverlight  <br/> |[이 링크](https://www.microsoft.com/silverlight/)에서 최신 버전의 Silverlight를 설치할 수 있습니다.  <br/> |
   
> [!NOTE] 
> 부하 분산 장치를 사용 하는 경우 디렉터리 검색을 사용 하도록 설정 해야 할 수도 있습니다. 그렇지 않으면 빈 페이지는 부하 분산 장치가 오류를 고려할 수 있는 로드를 만듭니다. 

이를 돕기 위해 다음과 같은 샘플 PowerShell 스크립트를 실행 하 여이를 자동화할 수 있습니다.

```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> 명령은 특정 순서로 원본 파일을 찾습니다. 온라인 상태 이면 명령이 Windows 업데이트에 액세스 합니다. 그러나 오프 라인 상태에서는 명령에 원본 파일을 사용할 수 있는지 확인 해야 합니다. PowerShell을 사용 하 여 역할 및 기능을 설치 하는 방법에 대 한 자세한 내용은 PowerShell 명령을 사용 하는 경우에도 [역할 설치 또는 제거, 역할 서비스 또는 기능](https://technet.microsoft.com/library/hh831809.aspx) 을 설치 하 고 Windows Update를 다시 실행 하는 방법을 참조 하세요.

 **또한 디렉터에는 다음이 필요 합니다.**
  
다음 모듈이 선택 된 상태로 IIS를 실행 합니다.
  
- 일반적인 HTTP 기능
    
  - 기본 문서
    
  - HTTP 오류
    
  - 정적 콘텐츠
    
- 상태 및 진단
    
  - HTTP 로깅
    
  - 로깅 도구
    
  - 추적할
    
- 성능을
    
  - 정적 콘텐츠 압축
    
- 보안
    
  - 요청 필터링
    
  - 클라이언트 인증서 매핑 인증
    
  - Windows 인증
    
- 응용 프로그램 개발
    
  - .NET 확장성 3.5
    
  - .NET 확장성 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI 확장
    
  - ISAPI 필터
    
(이에 대 한 자세한 내용은 프런트 엔드 서버 및 스탠더드 버전 서버와 동일한 모듈으로, 동적 콘텐츠 압축 및 관리 도구를 사용 하지 않는 것이 좋습니다.)
  
또한 다음과 같은 몇 가지 PowerShell 코드가 있습니다.
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **영구 채팅 서버에도 다음이 필요 합니다.**
  
MSMQ 라고도 하는 메시지 큐 Windows Server 구성 요소 이며, 서버 관리자의 기능 섹션 아래에 설치할 수 있습니다. 이에 대 한 자세한 내용은 [메시지 큐 설치 및 관리](https://technet.microsoft.com/library/cc771474.aspx)를 참조 하세요.
  
 **마지막 생각:**
  
Microsoft 인터넷 보안 및 가속 (ISA) 서버 클라이언트 소프트웨어를 설치 하지 마세요. 또는 다른 모든 타사 방화벽 또는 바이러스 백신 네트워크 검사 소프트웨어를 여기에 포함 시킬 수 있습니다. 모든 프런트 엔드 서버 또는 독립 실행형 중재 서버 해당 소프트웨어를 설치할 때 불량 미디어 소통량 성능이 표시 되었습니다.
  

