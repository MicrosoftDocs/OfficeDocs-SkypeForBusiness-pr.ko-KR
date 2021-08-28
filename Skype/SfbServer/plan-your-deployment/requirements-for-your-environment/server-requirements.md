---
title: 비즈니스용 Skype 서버 서버 요구 사항
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
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
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: '요약: 이 비즈니스용 Skype 서버 2015 서버를 준비합니다. 하드웨어, OS, 데이터베이스, 소프트웨어, 모든 시스템 요구 사항 및 권장 사항은 서버 팜을 성공적으로 설치 및 배포하는 데 도움이 됩니다.'
ms.openlocfilehash: 0e93742e917e25f968d500ed01bb4a83d8ac8904
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604667"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 서버 요구 사항
 
**요약:** 이 비즈니스용 Skype 서버 2015 서버를 준비합니다. 하드웨어, OS, 데이터베이스, 소프트웨어, 모든 시스템 요구 사항 및 권장 사항은 서버 팜을 성공적으로 설치 및 배포하는 데 도움이 됩니다.

Active Directory, DNS 또는 인증서와 같은 환경 요구 사항을 찾고 있는 경우 [2015년 2015의](environmental-requirements.md) 환경 요구 사항을 비즈니스용 Skype 서버 있습니다.
  
2015에서 배포를 시작하기 전에 몇 가지 준비를 비즈니스용 Skype 서버 있습니다. 이 문서에서는 다음에 대한 계획을 세우는 것입니다.
  
- [비즈니스용 Skype 서버 하드웨어](server-requirements.md#Hardware)
  
- [2015용 비즈니스용 Skype 서버 운영 체제](server-requirements.md#OS)
  
- [비즈니스용 Skype 서버 사용할 백 엔드 데이터베이스](server-requirements.md#DBs)
  
- [2015 배포 전에 설치해야 하는 비즈니스용 Skype 서버 소프트웨어](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 하드웨어
<a name="Hardware"> </a>

이제 토폴로지가 다운되어 있으며 그렇지 않은 경우 비즈니스용 Skype 서버 [2015에](../../plan-your-deployment/topology-basics/topology-basics.md) 대한 토폴로지 기본 항목을 확인할 수 있습니다. 이제 서버에 대해 생각해 볼 수 있습니다. 비즈니스용 Skype 서버 2015 서버에는 64비트 하드웨어가 필요합니다. 하드웨어에 대한 권장 사항은 아래와 같습니다. 이러한 요구 사항은 아니며 최적의 성능을 위해 필요한 요구 사항을 반영합니다. 상황에 따라 이보다 더 많은 요구가 필요한지 확인하는 데 도움이 되는 용량 계획 설명서가 있습니다.
  
프런트 엔드 서버, 백 엔드 서버, Standard Edition 및 영구 채팅 서버에 권장되는 하드웨어:
  
|**하드웨어 구성 요소**|**권장**|
|:-----|:-----|
|CPU  <br/> |64비트 듀얼 프로세서, 16진수 코어, 2.26GHz 이상입니다.  <br/> Intel Itanium 프로세서는 2015 역할에 비즈니스용 Skype 서버 지원되지 않습니다.  <br/> |
|메모리  <br/> |32GB  <br/> |
|디스크  <br/> |둘 중 하나:  <br/> • 8개 이상의 10000 RPM 하드 디스크 드라이브(최소 72GB의 사용 공간 사용이 있는 디스크 2개(RAID 1을 사용하는 RAID 1 및 6을 사용하는 디스크 2개)  <br/> 또는  <br/> • 8개 10000 RPM 기계식 디스크 드라이브와 동일한 사용 공간 및 유사한 성능을 제공할 수 있는 솔리드 스테이트 드라이브(SDD)입니다.  <br/> |
|네트워크  <br/> |이중 포트 네트워크 어댑터 1개, 1Gbps 이상(2대의 네트워크 어댑터를 사용할 수 있지만 단일 MAC 주소와 단일 IP 주소로 팀을 구성해야 합니다.  <br/> 프런트 엔드 서버, 백  엔드 서버, Standard Edition 및 영구 채팅 서버에는 이중 또는 다중 홈 구성이 지원되지 않습니다. <br/> 운영 체제에 노출되지 않는 한 서버 하드웨어를 모니터링하고 관리하는 데 사용되는 한 DRAC 또는 ILO와 같은 대역 관리 시스템을 사용할 수 없습니다. 이 시나리오는 다중 홈 서버를 구성하지는 않습니다.  <br/> |
   
에지 서버, 독립 실행형 중재 서버, 비디오 Interop 서버 및 Director에 권장되는 하드웨어:
  
|**하드웨어 구성 요소**|**권장**|
|:-----|:-----|
|CPU  <br/> |64비트 듀얼 프로세서, 쿼드 코어, 2.26GHz 이상  <br/> Intel Itanium 프로세서는 2015 역할에 비즈니스용 Skype 서버 지원되지 않습니다.  <br/> |
|메모리  <br/> |16기가바이트  <br/> |
|디스크  <br/> |둘 중 하나:  <br/> • 4개 이상의 10000 RPM 하드 디스크 드라이브에 최소 72GB의 사용 공간이 있는 디스크 공간이 있습니다(디스크는 RAID 1 구성 2배).  <br/> 또는  <br/> • 4개 10000 RPM 기계식 디스크 드라이브와 동일한 사용 공간 및 유사한 성능을 제공할 수 있는 SDD(Solid State Drive)입니다.  <br/> |
|네트워크  <br/> |이중 포트 네트워크 어댑터 1개, 1Gbps 이상(2대의 네트워크 어댑터를 사용할 수 있지만 단일 MAC 주소와 단일 IP 주소로 팀을 구성해야 합니다.  <br/> 비디오 Interop 서버 및  Director에는 이중 또는 다중 홈 구성이 지원되지 않습니다. <br/> 에지 서버에는 이중 포트 네트워크 어댑터인 1Gbps 이상(또는 총 4개의 쌍으로 각 쌍이 단일 MAC 주소 및 단일 IP 주소로 팀을 이루는 총 2개의 쌍으로 구성되는 2개의 네트워크 어댑터)이 필요합니다.  <br/> 독립 실행형 중재 서버에서는 특정 PSTN IP 주소의 구성을 허용하는 추가 NI(네트워크 인터페이스 카드)의 설치가 지원됩니다.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>2015용 비즈니스용 Skype 서버 운영 체제
<a name="OS"> </a>

하드웨어를 설치한 후 운영 체제(OS)를 설치해야 합니다. 다음은 2015에서 설치하고 성공적으로 사용할 수 있는 비즈니스용 Skype 서버 OS입니다.
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|Windows Server 2019(누적 비즈니스용 Skype 9 이상이 필요합니다. <br/> |Windows Server 2016(누적 비즈니스용 Skype 5 이상이 필요합니다. 자세한 내용은 [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Windows Server 2012 필요한 모든 업데이트가 설치된 R2 데이터 센터 OS  <br/> |Windows Server 2012 모든 필수 업데이트가 설치된 R2 Standard OS  <br/> |
|Windows Server 2012 Datacenter 모든 필수 업데이트가 설치된 OS  <br/> |Windows Server 2012 Standard 모든 필수 업데이트가 설치된 OS  <br/> |
   
이 목록에 없는 경우 제대로 작동하지 않는 경우 2015 또는 2015의 새 설치에는 사용해 비즈니스용 Skype 서버 않습니다.

> [!NOTE]
> Lync Server 2013에서 OS의 현재 현재 업그레이드가 지원되지 않습니다. 별도의 풀을 배포하고 다른 OS를 사용하여 사용자를 새 풀로 마이그레이션해야 합니다. 풀의 모든 서버에 동일한 OS 버전이 있어야 합니다.
  
> [!NOTE]
> 이 목록에 Windows Server 2008 R2가 없는 것으로 나타났을 수 있습니다. SFB에 사용할 모든 새 Windows Server 2012 R2를 사용하는 것이 좋습니다. Lync Server 2013이 이미 설치된 기존 서버가 있는 경우 해당 서버의 현재 Windows Server 2008 R2를 사용하려는 경우만 해당 서버 2008 R2를 사용하게 됩니다. Windows Server 2008 R2는 2015년 1월 13일 주류 지원 수명 주기가 종료된 후 2020년 1월 14일 지원 수명 주기가 끝날 것입니다.
  
최신 서비스 팩 외에 관련성이 있는 경우 다음 업데이트가 설치되도록 할 수 있습니다.
  
- 이 Windows Server 2012 KB 문서는 2858668 전에 설치해야 합니다. [여기에서 을(를) 얻습니다.](https://support.microsoft.com/kb/2858668/)
    
- R2를 Windows Server 2012 업그레이드하기 전에 KB 문서 2982006 설치하세요. [여기에서 찾을 수 있습니다.](https://support.microsoft.com/kb/2982006/)
    
- Windows Server 2008 R2 상자에서 업그레이드하는 경우(위 참고 참조) 먼저 KB 문서를 2533623 합니다. [이 링크에 있습니다.](https://support.microsoft.com/kb/2533623/)
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 사용할 백 엔드 데이터베이스
<a name="DBs"> </a>


비즈니스용 Skype 서버 2015 Standard Edition 설치하는 경우 SQL Server 2014 Express(64비트 버전)도 자동으로 설치됩니다.
  
비즈니스용 Skype 서버 2015 Enterprise Edition 약간 더 복잡하지만 지원되는 목록이 아래에 있습니다(모든 것이 64비트 버전입니다. 32비트 버전은 사용하지 말아야 합니다.
  
|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다. <br/> |Microsoft SQL Server 2017 Enterprise(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다. <br/> |Microsoft SQL Server 2016 Enterprise(64비트 버전) 서비스 팩 1 이상을 설치하고 비즈니스용 Skype 누적 업데이트 7 이상(비즈니스용 Skype 누적 업데이트[다운로드)을](https://support.microsoft.com/help/3061064)실행해야 합니다.  <br/> |Microsoft SQL Server 2014 Enterprise(64비트 버전) 누적 업데이트 6 이상(누적 업데이트[6 다운로드)으로](https://support.microsoft.com/kb/3031047/)실행해야 합니다.  <br/> |Microsoft SQL Server 2012 Enterprise(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.  <br/> |
|Microsoft SQL Server 2019 Standard(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다. <br/> |Microsoft SQL Server 2017 Standard(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다. <br/> |Microsoft SQL Server 2016 Standard(64비트 버전) 서비스 팩 1 이상을 사용하며, 비즈니스용 Skype 누적 업데이트 7 이상(비즈니스용 Skype 누적 업데이트[다운로드)으로](https://support.microsoft.com/help/3061064)실행해야 합니다.  <br/> |Microsoft SQL Server 2014 Standard(64비트 버전)를 설치하고 누적 업데이트 6 이상(누적 업데이트[6 다운로드)을 실행해야 합니다.](https://support.microsoft.com/kb/3031047/)  <br/> |Microsoft SQL Server 2012 Standard(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.  <br/> |
   
여기에 사용하려는 SQL Server 버전이 없는 경우 사용할 수 없습니다.
  
- 또한 모니터링 서버 역할에 대한 SQL Server Reporting Services 설치해야 합니다.
- 백 엔드가 SQL 경우 프런트 엔드에 비즈니스용 Skype 연결은 저속 링크가 아니라 로컬 연결로 설정해야 합니다. 
- 둘 SQL 풀 간의 백 엔드 공유는 지원되지 않습니다.

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange 저장소
모임 콘텐츠 파일(예: PowerPoint 프레젠테이션)이 첨부 파일로 보관됩니다. 비즈니스용 Skype 준수 비즈니스용 Skype 보관 데이터를 Exchange 경우 Exchange 배포에 Exchange 사용하여 최대 저장소 크기가 모임 콘텐츠 파일의 저장소를 지원하는지 확인해야 합니다. Microsoft Exchange 통합 옵션을 사용하여 보관을 배포하고 사용하도록 설정하기 전에 Exchange 합니다. 
    
Exchange 저장소를 사용하기로 선택한 경우 비즈니스용 Skype SQL Server 서버에 있지 않은 비즈니스용 Skype 별도의 Exchange 데이터베이스를 보관에 배포할 필요가 없습니다. Microsoft Exchange 통합 옵션을 사용하여 보관을 배포하는 경우 비즈니스용 Skype 보관 데이터는 Exchange 서버에 있는 사용자에 대한 Exchange 준수 데이터와 함께 Exchange 저장됩니다. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 보관에 대한 하드웨어 및 소프트웨어 요구 사항
  
보관은 정의된 서버 역할이 아니며 보관을 위해 별도의 서버를 설치할 필요가 없습니다. 통합 데이터 수집 에이전트는 모든 프런트 엔드 풀 및 모든 Enterprise Edition 서버에 자동으로 Standard Edition 활성화됩니다. 토폴로지 작성기에서 보관 토폴로지 사용 및 게시를 해야 합니다.
    
보관은 모임 콘텐츠 비즈니스용 Skype 서버 임시 저장을 위해 보관 파일 저장소를 사용하게 하여 보관을 위한 별도의 파일 저장소를 설정하지 않습니다.
    
Microsoft 메시지 큐는 필요하지 않습니다.
    
보관 저장소에 대한 인프라를 설정해야 합니다. 여기에는 저장소를 사용하여 Exchange 또는 보관 저장소를 선택하는 SQL Server.   비즈니스용 Skype 서버 보관 인프라 요구 사항은 보관 인프라 배포와 비즈니스용 Skype 서버. 자세한 내용은 [Requirements for your 비즈니스용 Skype environment을 참조하세요.](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) 
  
> [!NOTE]
> Exchange 서버에 있지 않은 사용자를 지원하거나 Microsoft Exchange 통합 옵션을 사용하지 않을 경우 64비트 SQL Server 데이터베이스를 사용하여 보관 저장소를 배포해야 합니다. 
    
보관을 배포하고 사용하도록 SQL Server 플랫폼을 설정해야 합니다. 토폴로지를 게시하는 데 사용될 계정에 적절한 관리자 권한 및 권한이 있는 경우 토폴로지를 게시할 때 보관 데이터베이스(LcsLog)를 만들 수 있습니다. 나중에 설치 절차의 일부로 포함된 데이터베이스를 만들 수도 있습니다. 자세한 내용은 SQL Server [설명서를 SQL Server 참조하십시오.](/sql/sql-server/)
    
보관에 대한 부하가 증가하는 것이 중요할 수 있습니다. 따라서 보관을 사용하도록 설정한 프런트 엔드 서버에 디스크 공간이 충분한지 확인해야 합니다.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL 미러링, SQL 클러스터링 및 SQL 항상 사용

2015에서 SQL 미러링 또는 SQL 클러스터링을 비즈니스용 Skype 서버 사용할 수 있습니다. SQL 미러링은 토폴로지 작성기에서 비즈니스용 Skype 서버 설정됩니다. 클러스터링을 설정하는 SQL 수행되는 SQL Server.
  
지원되는 것 같은 SQL 클러스터링에 대한 활성/수동 구성이 있는지 확인 합니다. 수동 노드를 다른 SQL 않습니다.
  
장애 조치(failover) 클러스터링에 대해 다음을 사용할 수 있습니다.
  
두 노드:
  
- Microsoft SQL Server 2019 Standard(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.

- Microsoft SQL Server 2017 Standard(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.

- Microsoft SQL Server 2016 Standard(64비트 버전)와 서비스 팩 1 이상을 제공합니다. 최신 서비스 팩으로 실행하는 것이 좋습니다.

- Microsoft SQL Server 2014 Standard(64비트 버전)를 사용하며 최신 서비스 팩으로 실행하는 것이 좋습니다.
    
-  Microsoft SQL Server 2012 Standard(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.

16개 노드:

- Microsoft SQL Server 2019 Enterprise(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.

- Microsoft SQL Server 2017 Enterprise(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.

- Microsoft SQL Server 2016 Enterprise(64비트 버전)와 함께 서비스 팩 1 이상을 제공합니다. 최신 서비스 팩으로 실행하는 것이 좋습니다.
  
- Microsoft SQL Server 2014 Enterprise(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.
    
- Microsoft SQL Server 2012 Enterprise(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.

> [!IMPORTANT]
> 업그레이드를 위해 업그레이드하기 전에 프런트 엔드 서버에 최소 SQL Server 2012 SP1이 설치되어 있지 않은지 확인합니다. [바로 다운로드하려는](https://www.microsoft.com/download/details.aspx?id=35575) 경우 SP1에 대한 링크는 다음과 있습니다.
  
SQL 미러링에 대해 자세히 읽어야 하는 경우 비즈니스용 Skype 서버 2015 항목에서 백 엔드 서버 고가용성을 제공합니다. SQL Server 2015에 대한 비즈니스용 Skype 서버 클러스터링 구성에는 클러스터링 준비 단계가 있습니다. 또한 2014, SQL 및 [2008에](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation)대한 장애 [](/previous-versions/sql/sql-server-2012/hh231721(v=sql.110))조치(failover) 클러스터링에 대한 추가 링크도 [있습니다.](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105))
  
> [!NOTE]
> 2015 릴리스의 새로운 버전은 Always On을 SQL 있습니다. 지원되는 항목은 [2015년](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) 8월의 백 엔드 서버 고가용성 항목에서 비즈니스용 Skype 서버 있습니다.

> [!NOTE]
> SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(failover) 클러스터 인스턴스) 및 SQL 장애 조치(failover) 클러스터링 방법이 비즈니스용 Skype 서버 선호됩니다.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>2015 배포 전에 설치해야 하는 비즈니스용 Skype 서버 소프트웨어
<a name="Software"> </a>

비즈니스용 Skype 서버 2015를 실행하는 서버에 대해 설치하거나 구성해야 하는 몇 가지가 있습니다. 그 이후에는 특정 서버 역할에 대한 추가 요구 사항이 있습니다.

  
 **모든 서버:**
  
|**소프트웨어/역할**|**세부 정보**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |모든 비즈니스용 Skype 서버 3.0을 Windows PowerShell 서버가 필요합니다.  <br/> • R2 또는 Windows Server 2012 Windows Server 2012 설치하는 경우 이미 설치되어 있기 때문에 설정됩니다.  <br/> • Windows Server 2008 R2에서 업그레이드를 수행하고 있는 경우 Windows Management Framework [3.0을](https://www.microsoft.com/download/details.aspx?id=34595) 다운로드하여 업그레이드할 수 있습니다. <br/> **팁:** 올바른 PowerShell이 있는 경우 PowerShell 프롬프트로 가고 를 입력하여 BuildVersion 6.2.9200.0 이상인지 `$PSVersionTable` 확인합니다. 이렇게 해야 필요한 정보가 나타날 수 있습니다.  <br/> |
|Microsoft .NET Framework  <br/> |WCF 서비스는  서버 관리자에서 다운로드가 Windows **기능으로** 설치되는 기능입니다. <br/> • 이 기능을 설치할 때 또는 이 기능이 이미 설치되어 있으며 확인 중이면 다음과 같이 **HTTP** 정품 인증 옵션도 확인하고 설치해야 합니다. <br/> ![Screenshot showing HTTP Activation option under the .NET Framework 4.5 Features. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) HTTP 정품 인증을 설치하려면 몇 가지 다른 것을 설치해야 하다는 추가 팝업이 있는 경우 걱정하지 마세요. 정상입니다. 확인을 클릭하고 진행합니다. 이 팝업을 얻지 못하면 이미 설치된 것으로 가정하고 진행합니다.  <br/> Microsoft .NET Framework R2 또는 Windows Server 2012 설치할 Windows Server 2016 설치됩니다. 비즈니스용 Skype 서버 다음 Microsoft .NET Framework 사용할 수 있습니다.  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1(비즈니스용 SKYPE 서버 CU 5 이상 릴리스용)  <br/> • .NET 4.7.2(비즈니스용 SKYPE 서버 CU 6 이상 릴리스용)  <br/>  • .NET 4.8(비즈니스용 Skype 서버 CU 9 이상 릴리스용) <br/>  .NET Framework 3.5는 기본적으로 Windows Server 2008 R2 컴퓨터에 설치될 수 있지만(업그레이드 전에 반드시 확인) 실제로는 Windows Server 2012/Windows Server 2012 R2 서버에 있지는 않습니다(새 설치의 경우). 추가하려면 설치 드라이브 또는 미디어(Windows Server가 설치된 위치 또는 설치 파일이 있는 위치)에 액세스해야 합니다. 그런 다음 서버 관리자에서 기능으로 설치한 다음 요청이 표시될 때 설치 미디어(특히 **\sources\sxs** 폴더)를 지점하고 계속 설치합니다. <br/> |
|미디어 파운데이션  <br/> |R2 Windows Server 2016 Windows Server 2012 Windows Server 2012 Microsoft Media Foundation과 함께 Windows 미디어 형식 런타임이 설치됩니다.  <br/> 회의에 사용되는 모든 프런트 엔드 서버 및 Standard Edition 서버는 통화 파킹, 공지 및 응답 그룹 응용 프로그램에서 공지 및 음악에 대해 재생하는 Windows 미디어 오디오(.wma) 파일을 실행하려면 Windows 미디어 형식 런타임이 필요합니다.  <br/> |
|Windows Identity Foundation  <br/> |2015에 Windows 서버 대 서버 인증 시나리오를 지원하려면 Identity Foundation 3.5를 비즈니스용 Skype 서버 필요합니다.  <br/> • Windows Server 2012 R2 Windows Server 2012 경우 아무것도 다운로드할 필요가 없습니다. 서버 **관리자를** 열고 역할 및 기능 추가 **마법사 로 이동하십시오.** Windows 섹션 아래에 **Identity Foundation 3.5가** **나열됩니다.** 확인한 경우 좋습니다. 그렇지 않으면 이 단추를 선택하고 다음을 클릭하여 설치 **단추에 도달합니다.** <br/> |
|원격 서버 관리 도구  <br/> |역할 관리 도구: AD DS 및 AD LDS 도구  <br/> |
   
 **프런트 엔드 서버 및 Standard Edition 서버에도 다음이 필요합니다.**
  
|**소프트웨어/역할**|**세부 정보**|
|:-----|:-----|
|IIS(인터넷 정보 서비스)  <br/> |다음 모듈이 선택된 모든 프런트 엔드 서버 및 모든 Standard Edition IIS가 필요합니다.  <br/> • 일반적인 HTTP 기능: 기본 문서, HTTP 오류, 정적 콘텐츠  <br/> • 상태 및 진단: HTTP 로깅, 로깅 도구, 추적  <br/> • 성능: 정적 콘텐츠 압축, 동적 콘텐츠 압축  <br/> • 보안: 요청 필터링, 클라이언트 인증서 매핑 인증, Windows 인증  <br/> • 응용 프로그램 개발: .NET 확장성 3.5, .NET 확장성 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI 확장, ISAPI 필터  <br/> • 관리 도구: IIS 관리 콘솔, IIS 관리 스크립트 및 도구  <br/> 또한 익명 액세스가 필요하지만 IIS를 설치할 때도 익명 액세스가 필요하기 때문에 목록에 해당 액세스 권한을 선택할 수 있는 장소가 없습니다.  <br/> |
|Windows Media 형식 런타임  <br/> | R2 Windows Server 2016, Windows Server 2012 Windows Server 2012 R2의 경우 서버 관리자에 **미디어 파운데이션** 기능을 **설치해야 합니다.** 이제 이 설치 없이 비즈니스용 Skype 서버 2015 설치를 실제로 시작할 수 있지만 2015 설치가 계속되기 전에 설치를 요청한 다음 서버를 다시 시작하라는 메시지가 비즈니스용 Skype 서버 있습니다. 미리 작업을 하는 것이 좋습니다. <br/> |
|Silverlight  <br/> |이 링크에서 최신 버전의 Silverlight를 설치할 [수 있습니다.](https://www.microsoft.com/silverlight/)  <br/> |
   
> [!NOTE] 
> 부하 런저를 사용하는 경우 디렉터리 검색을 사용하도록 설정해야 할 수도 있습니다. 그렇지 않으면 부하 부하가 고려할 수 있는 빈 페이지가 로드됩니다. 

이를 자동화하기 위해 실행할 수 있는 샘플 PowerShell 스크립트는 다음과 같습니다.

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> 이 명령은 원본 파일을 특정 순서로 검색합니다. 온라인인 경우 명령은 업데이트 Windows 액세스합니다. 그러나 오프라인 상태인 경우 명령에서 원본 파일을 사용할 수 있는지 확인해야 합니다. PowerShell을 사용하여 역할 및 기능을 설치하는 데 대한 자세한 내용은 Install [or Uninstall Roles, Role Services, or Features](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) Don't forget to run Windows Update after you install prerequisites, even if you use the PowerShell command을 참조하십시오.

 **또한 이사는 또한 필요합니다.**
  
다음 모듈이 선택된 IIS:
  
- 일반 HTTP 기능
    
  - 기본 문서
    
  - HTTP 오류
    
  - 정적 콘텐츠
    
- 상태 및 진단
    
  - HTTP 로깅
    
  - 로깅 도구
    
  - 추적
    
- 성능
    
  - 정적 콘텐츠 압축
    
- 보안
    
  - 요청 필터링
    
  - 클라이언트 인증서 매핑 인증
    
  - Windows 인증
    
- 응용 프로그램 개발
    
  - .NET Extensibility 3.5
    
  - .NET Extensibility 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI 확장
    
  - ISAPI 필터
    
(궁금한 경우 동적 콘텐츠 압축 및 관리 도구를 남겨두고 프런트 엔드 서버 및 Standard Edition 서버와 동일한 모듈을 설정하는 것이 좋습니다.)
  
또한 아래에 몇 가지 PowerShell 코드도 있습니다.
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **영구 채팅 서버도 필요합니다.**
  
MSMQ라고도 하는 메시지 큐입니다. 이 구성 요소는 Windows 구성 요소로, 서버 관리자의 기능 섹션에서 설치할 수 있습니다. 이에 대한 자세한 내용은 [Installing and Managing Message Queuing 을(를) 확인 합니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771474(v=ws.11))
  
 **마지막 생각:**
  
모든 프런트 엔드 서버 또는 독립 실행형 중재 서버에 Microsoft ISA(Internet Security and Acceleration) 서버 클라이언트 소프트웨어 또는 기타 Winsock LSP(계층형 서비스 공급자) 소프트웨어(타사 방화벽 또는 바이러스 백신 네트워크 검사 소프트웨어가 여기에 포함됩니다.)를 설치하지 말아야 합니다. 소프트웨어가 설치되면 미디어 트래픽 성능이 나쁨으로 표시됩니다.
