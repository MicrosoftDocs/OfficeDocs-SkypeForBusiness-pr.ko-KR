---
title: 모니터링 보고서 설치 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: '요약: 각 서비스에서 모니터링 보고서를 생성하는 서비스를 설치하는 비즈니스용 Skype 서버.'
ms.openlocfilehash: 703bb209c68558ba8f98c8e3a3efcde94e4ce5eb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861825"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>모니터링 보고서 설치 비즈니스용 Skype 서버
 
**요약:** 2013에서 모니터링 보고서를 생성하는 서비스를 설치하는 비즈니스용 Skype 서버.
  
비즈니스용 Skype 서버 모니터링 보고서는 조직에서 진행되는 통신 세션의 품질 및 수량에 대한 다양한 정보를 제공합니다. 
  
## <a name="install-monitoring-reports"></a>모니터링 보고서 설치

모니터링 보고서는 설치 시 자동으로 설치되지 비즈니스용 Skype 서버. 대신 모니터링 보고서를 별도로 설치해야 합니다. 모니터링 보고서는 컴퓨터에 비즈니스용 Skype 서버 후에만 설치해야 합니다.
  
> [!NOTE]
> 모니터링 데이터베이스가 설치된 컴퓨터에 모니터링 보고서를 설치하는 것이 좋습니다. 이렇게 하면 보고서에 액세스하기 위한 사용 권한을 할당하는 프로세스가 간소화됩니다. 모니터링 저장소를 호스트하는 컴퓨터에 모니터링 보고서를 설치하면 한 컴퓨터의 데이터베이스가 두 번째 컴퓨터에서 실행되는 Reporting Services와 상호 작용할 수 있도록 권한을 구성할 필요가 없습니다. 
  
비즈니스용 Skype 서버 모니터링 보고서에는 회의, 피어 투 피어 IM 세션, 사용자 등록, 응답 그룹 응용 프로그램 등 자세한 정보를 제공하도록 설계된 30개 이상의 보고서가 포함되어 있습니다. 2013 버전의 경우 비즈니스용 Skype 서버 모니터링 보고서에는 다음과 같은 다양한 기능이 향상되었습니다.
  
- **새 음성 품질 보고서입니다.** 이러한 새 보고서에는 다양한 유형의 [통화(예: 유선 통화와 무선 통화 간)](../../manage/health-and-monitoring/comparison.md)간의 품질을 비교하는 비즈니스용 Skype 서버 미디어 품질 비교 보고서가 포함되어 있습니다. 및 [전화](../../manage/health-and-monitoring/join-time-report.md)회의 참가 비즈니스용 Skype 서버 보고서는 사용자가 전화 회의에 참가하는 데 필요한 시간 관련 정보를 제공합니다. 
    
- **비디오 및 응용 프로그램 공유 세션을 분석하고 문제 해결하기 위한 보고서가 개선되어 있습니다.** 비즈니스용 Skype 서버 [](../../manage/health-and-monitoring/summary.md) 미디어 품질 요약 보고서는 비디오 및 응용 프로그램 공유 통화를 [](../../manage/health-and-monitoring/server-performance.md) 분석하는 방법을 제공하는 반면, 비즈니스용 Skype 서버 서버 성능 보고서에서는 이러한 통화를 생성하는 서버의 성능에 대해 자세히 설명합니다. 비디오 및 응용 프로그램 공유 메트릭은 이제 의 피어 투 [피어](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md) 세션 세부 정보 보고서 및 비즈니스용 Skype 서버의 회의 세부 정보 보고서에서도 [비즈니스용 Skype 서버.](../../manage/health-and-monitoring/detail-report.md)
    
- **보고서 성능 향상.** 여기에는 더 빠른 응답 및 데이터 검색 시간뿐만 아니라 보고서를 보다 빠르고 쉽게 탐색할 수 있습니다.
    
개별 보고서에 대한 자세한 내용은 모니터링 보고서 설명서에서 찾을 수 있습니다.
  
> [!NOTE]
> QoE 통화 정보 하위 보고서와 같은 다른 보고서가 비즈니스용 Skype 서버. 그러나 이 보고서는 주로 내부용이기 때문에 직접 액세스하지는 않습니다. 
  
비즈니스용 Skype 서버 모니터링 보고서를 설치하는 방법에는 비즈니스용 Skype 서버 배포 마법사를 사용하거나 Windows PowerShell 설치 파일에 포함된 Windows PowerShell 스크립트를 비즈니스용 Skype 서버 있습니다. 보고서를 설치하는 데 사용하는 방법에 관계없이 먼저 다음을 반드시 해야 합니다.
  
- 모니터링 데이터베이스의 사용자 계정에 데이터베이스 역할을 추가할 수 있는 권리가 있습니다.
    
- 콘텐츠 관리자 역할은 SQL Server Reporting Services. 이 역할은 사용자에게 보고서를 배포할 수 있는 SQL Server Reporting Services.
    
배포 마법사를 사용하여 모니터링 보고서를 설치하려면 다음 단계를 완료합니다.
  
1. **시작,** **모든** 프로그램, 비즈니스용 Skype 서버 **를** 클릭한 다음 배포 **비즈니스용 Skype 서버 클릭합니다.**
    
2. 배포 마법사에서  모니터링 보고서 배포를 클릭하여 모니터링 보고서 배포 마법사를 시작할 수 있습니다.
    
3. 모니터링 보고서 배포 마법사의 모니터링  데이터베이스 지정 페이지에서 모니터링 저장소를 호스팅하는 컴퓨터의 정식 도메인 이름이 모니터링 데이터베이스  드롭다운 목록에 나타나는지 확인합니다. 모니터링 저장소가 여러 개 있는 경우 드롭다운 목록에서 적절한 서버를 선택해야 합니다. 올바른 SQL Server 인스턴스가 SQL Server Reporting Services(예: **atl-sql-001.litwareinc.com/archinst)에** 나타나는지 확인하고 다음 **을** **클릭합니다.**
    
4. 자격  증명 지정 페이지의 사용자  이름 상자에 모니터링 보고서에 액세스할 때 사용할 계정의 도메인 이름과 사용자 이름을 입력합니다(예: **litwareinc\kenmyer).** 이 형식(도메인\사용자 이름)을 사용하지 않는 경우 오류가 발생합니다.
    
    암호 상자에 사용자 계정 **암호를 입력하고** 다음 을 **클릭합니다.** 이 계정에는 특별한 권한은 필요하지 않습니다. 설치가 완료되면 계정에 필요한 로그온 및 데이터베이스 권한이 자동으로 부여됩니다.
    
5. 사용자 **Read-Only** 지정 페이지에서 사용자 그룹에 대한 읽기 전용 액세스 권한을 부여할 보안 그룹의 SQL Server Reporting Services 입력합니다. 예를 들어 읽기 전용 관리자에게 보고서에 대한 액세스 권한을 부여하기 위해 **RTCUniversalReadOnlyAdmins를 입력합니다.** **다음** 을 클릭합니다.
    
6. **명령 실행** 페이지에서 **마침** 을 클릭합니다.
    
모니터링 보고서는 스크립트 실행을 통해 비즈니스용 Skype 서버 관리 셸에서 설치할 수도 DeployReports.ps1. 이 Windows PowerShell 스크립트는 \<install location\> \비즈니스용 Skype 서버 2015\Deployment\Setup 폴더에서 찾을 수 있습니다. 모니터링 보고서를 사용하여 DeployReports.ps1 관리 셸 프롬프트에 다음과 같은 명령을 입력합니다.
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

다음 표에서는 위의 명령에 사용된 매개 변수에 대한 설명을 제공합니다.
  
|**매개 변수 이름**|**필수**|**설명**|
|:-----|:-----|:-----|
|storedUserName  <br/> |예  <br/> |모니터링 저장소에 액세스하는 데 사용되는 사용자 계정(도메인\사용자 이름 형식) 예를 들어:  <br/> ```-storedUserName "litwareinc\kenmyer"```이 계정에는 이전에 지정한 권한이 SQL Server SQL Server Reporting Services 또는 스크립트가 실패합니다.  <br/> |
|storedPassword  <br/> |예  <br/> |모니터링 저장소에 액세스하는 데 사용되는 사용자 계정의 암호입니다.  <br/> |
|readOnlyGroupName  <br/> |아니오  <br/> |해당 구성원에게 모니터링 보고서에 대한 읽기 전용 액세스 권한이 부여되는 도메인 또는 로컬 보안 그룹입니다. 지정한 그룹이 없는 경우 스크립트가 실패합니다. 나중에 이러한 사용 권한을 해지하기로 결정하거나 다른 사용자 또는 다른 그룹에 액세스 권한을 부여하기로 결정한 경우 SQL Service Reporting Services 보고서 관리자를 사용하여 이 작업을 SQL 있습니다.  <br/> |
|reportSqlServerInstance  <br/> |아니오  <br/> |SQL Server 서비스를 호스팅하는 인스턴스입니다. Reporting 인스턴스는 보고서 서버의 정식 도메인 이름을 사용하여 지정해야 합니다. 예를 들어:  <br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```이 매개 변수를 포함하지 않을 경우 스크립트는 보고 서비스가 모니터링 데이터베이스를 호스트하는 동일한 SQL Server 인스턴스에서 호스팅된다고 가정합니다.  <br/> |
|monitoringDatabaseId  <br/> |아니오  <br/> |모니터링 데이터베이스의 서비스 ID입니다. 다음 명령을 실행하여 모니터링 데이터베이스의 ID를 반환할 수 있습니다.  <br/> ```Get-CsService -MonitoringDatabase```|
   
모니터링 보고서를 설치한 후 New-CsReportingConfiguration cmdlet을 사용하여 이러한 보고서에 액세스하는 데 사용되는 URL을 구성해야 합니다. 이 작업은 다음 관리 셸에서 다음 비즈니스용 Skype 서버 실행하여 수행될 Windows PowerShell 있습니다. 보고 URL을 구성할 때 HTTPS 프로토콜을 사용하는 것이 되지만 필수는 아닙니다.
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

위의 명령에서 ReportingUrl 속성은 2008 R2 Reporting Services에서 사용하는 보고서 관리자 URL로 SQL Server 합니다. 보고서 관리자 URL은 보고서가 설치된 컴퓨터에서 SQL Server Reporting Services 수 있습니다.
  
1. 시작, 모든 프로그램, Microsoft SQL Server 2008 R2, 구성 도구를 클릭한 다음 Reporting Services 구성 관리자를 클릭합니다.
    
2. Reporting Services 구성 연결 대화 상자의 서버 이름 상자에 Reporting Services 컴퓨터의 이름이 나타나는지 확인합니다. 보고서 SQL Server 드롭다운 목록에서 커넥트.
    
3. Reporting Services 구성 관리자에서 보고서 관리자 URL을 클릭합니다. 보고서 관리자 URL 창에 하나 이상의 URL이 표시해야 합니다. 이러한 URL은 모두 보고 URL로 사용할 수 있습니다. 그러나 ReportingUrl은 HTTPS 프로토콜을 사용하는 것이 좋습니다.
    
모니터링 데이터베이스에 대해 미러 데이터베이스를 설정한 경우 모니터링 보고서를 미러 데이터베이스와도 연결해야 합니다. 자세한 내용은 [Associate Monitoring Reports with a mirror database in 비즈니스용 Skype 서버](monitoring-reports-with-a-mirror-database.md) 참조하십시오.
  

