---
title: 통화 품질 대시보드를 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: '요약: 통화 품질 대시보드의 배포 프로세스에 대해 설명합니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: fc07bb721c0319d041bd7bbee4a4a327d77f28b9
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733597"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>통화 품질 대시보드를 비즈니스용 Skype 서버
 
**요약:** 통화 품질 대시보드의 배포 프로세스에 대해 설명합니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
## <a name="deployment-overview"></a>배포 개요

CQD(통화 품질 대시보드)는 다음과 같은 세 가지 주요 구성 요소로 구성됩니다.
  
- **보관 데이터베이스**. QoE(QoE) 데이터가 복제되고 저장됩니다.
    
- **큐브**- QoE 보관 데이터베이스의 데이터가 최적화 및 빠른 액세스를 위해 집계됩니다.
    
- **포털**- 사용자가 QoE 데이터를 쉽게 쿼리하고 시각화할 수 있습니다.
    
![CQD 구성 요소.](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
QoE Archive 설치 프로세스에는 QoE 보관 데이터베이스를 만들고, 원본 QoE 메트릭 데이터베이스에서 QoE 보관 데이터베이스로 데이터를 이동하는 SQL Server 저장 프로시저를 배포하고, 저장 프로시저를 정기적으로 실행하도록 SQL Server 에이전트 작업을 설정하는 작업이 수행됩니다. 
  
큐브 배포는 QoE 보관함이 있는 위치의 사용자 정보를 수집하고, 큐브를 배포하고, 정기적으로 큐브를 새로 고칠 정기적인 SQL Server 에이전트 작업을 설정합니다.
  
포털 설치는 각 사용자의 보고서/쿼리에 대한 CQD 사용자 매핑을 저장하는 리포지토리 데이터베이스를 만듭니다. 그런 다음 사용자가 미리 정의된 보고서 집합을 볼 수 있으며 큐브에서 데이터를 시각화하는 자체 쿼리를 사용자 지정하고 만들 수 있는 대시보드인 IIS 웹 응용 프로그램을 설정합니다. 포털 설치는 사용자가 리포지토리 및 큐브에 프로그래밍식으로 액세스할 수 있도록 API를 노출하는 두 개의 추가 웹 응용 프로그램을 만듭니다. 이러한 API는 대시보드에서 내부적으로도 사용됩니다.
  

|**작업 단계**|**단계**|**역할 및 그룹 구성원**|**설명서**|
|:-----|:-----|:-----|:-----|
|필요한 하드웨어 및 소프트웨어를 설치합니다.  <br/> |CQD 구성을 결정하고 설치를 SQL Server 구성을 선택해야 합니다.  <br/> |로컬 Administrators 그룹의 구성원인 도메인 사용자  <br/> |배포 설명서의 "사전 설치 요구 사항" 섹션  <br/> |
|CQD를 설치합니다.  <br/> |배포 문서 다음에 MSI를 실행합니다.  <br/> |설치 계정을 설치하려면 설치 계정이 로컬 관리자 그룹의 구성원인 도메인 사용자로서 모니터링 서버의 QoE 메트릭 데이터베이스에 대한 읽기 권한이 있어야 합니다.  <br/> |배포 설명서의 "계정 및 배포 단계" 섹션  <br/> |
|사용자에게 액세스 권한을 부여합니다.  <br/> |포털에 대한 사용자 권한 부여를 관리하기 위해 IIS 7.0에 도입된 URL 권한 부여를 사용하는 것이 좋습니다. 자세한 내용은 [UNDERSTANDING IIS 7.0 URL Authorization를 참조하십시오.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)  <br/> |로컬 Administrators 그룹의 구성원인 도메인 사용자  <br/> |배포 설명서의 포털에 대한 사용자 액세스 관리 섹션  <br/> |
|선택 사항: 서브넷 매핑 정보를 제공합니다.  <br/> |QoE 보관 데이터베이스에서 네트워크 및 매핑 테이블을 채우고 매핑 테이블을 만듭니다.  <br/> |QoE 보관 데이터베이스에 대한 쓰기 권한이 있는 계정입니다.  <br/> |사용자 설명서의 "서브넷 정보 제공" 섹션  <br/> |
   


통화 품질 대시보드 배포에는 인프라 설정 및 소프트웨어 설치가 수반됩니다. 다음 절차에서는 프로세스를 간략하게 설명합니다.
  
## <a name="deployment-steps"></a>배포 단계

1. CQD의 CallQualityDashboard.msi 구성 요소를 설치할 컴퓨터(이 컴퓨터는 설치되지 않은 컴퓨터)에 SQL Server 복사합니다. 
    
2. MSI를 실행합니다Windows 관리자 권한으로 실행하라는 메시지가 표시될 경우 실행합니다. 
    
3. EULA에 동의합니다.
    
4. 통화 품질 대시보드 구성 요소와 관련된 파일이 위치할 대상 폴더를 선택하거나 기본 위치를 수락합니다.
    
5. 모든 기능을 선택합니다.
    
6. QoE 보관 구성 페이지에서 다음 정보를 제공합니다.
    
   - **QoE** 메트릭 SQL Server: SQL Server 메트릭 DB가 있는 위치의 인스턴스 이름입니다(데이터 원본).
    
   - **QoE 보관 SQL Server 이름:** 이 필드는 읽기 전용 필드로, 로컬 컴퓨터의 정식 도메인 이름에 고정되어 있습니다. 보관 DB는 로컬 컴퓨터에만 설치할 수 있습니다.
    
   - **QoE 보관 SQL Server 인스턴스:** 보관 SQL Server 만들 로컬 인스턴스 이름입니다. 기본 인스턴스를 SQL Server 이 필드를 비워 두십시오. 명명된 인스턴스를 SQL Server 인스턴스 이름(예: " 다음의 이름)을 \" 지정합니다.
    
   - **QoE 보관 데이터베이스:** 기본적으로 이 옵션은 "새 데이터베이스 만들기"로 설정됩니다. 보관 DB 업그레이드는 지원되지 않습니다. "기존 데이터베이스 사용" 옵션을 사용할 수 있는 유일한 상황은 기존 보관 데이터베이스에 설치할 빌드와 동일한 스마마가 있는 경우뿐입니다.
    
   - **데이터베이스 파일 디렉터리:** 보관 DB의 데이터베이스 파일(.mdf 및 .ldf)을 배치할 위치의 경로입니다. 이는 OS와 별개인 드라이브(권장 하드웨어 구성의 HDD2)에 있습니다. 파일 이름은 설치 시 수정되어 있을 수 있는 충돌을 방지하기 위해 파일이 없는 빈 디렉터리를 사용하는 것이 좋습니다.
    
   - **여러 파티션 사용:** 기본값은 "다중 파티션"으로 설정되어 비즈니스 인텔리전스 버전 또는 Enterprise 버전이 SQL Server. Standard Edition의 경우 "단일 파티션" 옵션을 선택합니다. 단일 파티션을 사용하는 경우 큐브 처리 성능에 영향을 줄 수 있습니다.
    
     > [!NOTE]
     > 설치가 완료되면 여러 파티션 사용 옵션을 변경할 수 없습니다. 큐브 기능을 변경하기 위해서는 먼저 큐브 기능을 제거한 다음 제어판에서 "변경" 옵션을 사용하여 다시 설치해야 합니다. 
  
   - **파일 디렉터리 분할:** QoE 보관 데이터베이스의 파티션을 배치할 경로입니다. 이 드라이브는 OS 드라이브와 데이터베이스 로그 파일 드라이브가 분리된 드라이브(권장 하드웨어 구성의 HDD3)에 SQL 합니다. 파일 이름은 설치 시 수정되어 있을 수 있는 충돌을 방지하기 위해 파일이 없는 빈 디렉터리를 사용하는 것이 좋습니다.
    
   - **SQL 에이전트 작업 사용자 - 사용자 이름 &amp; 암호:** SQL Server 에이전트 작업의 "QoE 보관 데이터" 단계를 실행하는 데 사용되는 도메인 서비스 계정 이름 및 암호(마스킹)입니다. 이 작업은 저장 프로시저를 실행하여 QoE 메트릭 DB에서 보관 DB로 데이터를 페치합니다. 따라서 이 계정에는 계정 섹션에 표시된 QoE 메트릭 DB에 대한 읽기 권한이 있어야 합니다. 또한 이 계정은 QoE Archive SQL Server 인스턴스에 로그인해야 합니다.
    
     > [!NOTE]
     > NT SERVICE\MSSQLSERVER와 같이 SQL Server 인스턴스가 실행되는 계정에는 설치가 성공하려면 위에 제공된 Director에 대한 액세스/권한이 있어야 합니다. 자세한 내용은 [Configure File System Permissions for 데이터베이스 엔진 Access을 참조합니다.](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))
  
7. 다음을 클릭하면 설치 관리자에서 선행 작업 확인을 수행하고 문제가 발생하는 경우 보고합니다. 모든 선행 구성 검사가 통과하면 설치 관리자에서 큐브 구성 페이지로 이동합니다. 
    
    > [!NOTE]
    > 설치 관리자에 QoE Archive SQL Server 인스턴스의 SQL Server 에이전트 서비스가 현재 실행되고 있지 않다는 경고 메시지가 표시될 경우 설치를 계속할 수 있지만 설치 후를 수행하려면 SQL 에이전트 서비스가 실행되고 있는지 확인하여 시작 유형을 자동으로 설정하여 예약된 작업이 실행됩니다. 
  
8. 큐브 구성 페이지에서 다음 정보를 제공합니다.
    
   - **QoE 보관 SQL Server 이름:** 이 필드는 읽기 전용 필드로, 로컬 컴퓨터의 정식 도메인 이름에 고정되어 있습니다. 큐브는 QoE 보관 데이터베이스가 있는 컴퓨터(참고)에서만 설치할 수 있습니다. 큐브 자체가 원격 컴퓨터에 설치될 수 있습니다. 아래 참조)
    
   - **QoE 보관** SQL Server 인스턴스: SQL Server DB가 있는 위치의 인스턴스 이름입니다. 기본 SQL Server 지정하기 위해 이 필드를 비워 두십시오. 명명된 SQL Server 인스턴스를 지정하기 위해 인스턴스 이름(예: " 다음의 이름)을 \" 입력합니다. 설치를 위해 QoE 보관 구성 요소를 선택한 경우 이 필드는 QoE 보관 구성 페이지에 제공된 값으로 미리 채워지게 됩니다.
    
   - **큐브 분석 서버:** SQL Server 위치의 Analysis Service 인스턴스 이름을 지정합니다. 이 컴퓨터는 다른 컴퓨터일 수 있지만 설치하는 사용자는 Analysis Service 인스턴스에서 대상 서버 관리자의 SQL Server 합니다.
    
     > [!NOTE]
     >  Analysis Services 서버 관리자 권한을 구성하는 데 대한 자세한 내용은 [Grant Server Administrator Permissions (Analysis Services)을 참조하십시오.](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)
  
   - **여러 파티션 사용:** 기본값은 "다중 파티션"으로 설정되어 비즈니스 인텔리전스 버전 또는 Enterprise 버전이 SQL Server. Standard Edition의 경우 "단일 파티션" 옵션을 선택합니다. 단일 파티션을 사용하는 경우 큐브 처리 성능에 영향을 줄 수 있습니다.
    
     > [!NOTE]
     >  설치가 완료되면 여러 파티션 사용 옵션을 변경할 수 없습니다. 큐브 기능을 변경하기 위해서는 먼저 큐브 기능을 제거한 다음 제어판에서 "변경" 옵션을 사용하여 다시 설치해야 합니다.
  
   - **큐브 사용자 - 사용자 이름 &amp; 암호:** 큐브 처리를 트리거하는 도메인 서비스 계정 이름 및 암호(마스킹)입니다. 설치를 위해 QoE 보관 구성 요소를 선택한 경우 이 필드는 SQL 에이전트 작업 사용자에 대한 보관 구성 페이지에 제공된 값으로 미리 채워지지만 설치 프로그램이 필요한 최소 권한을 부여할 수 있도록 다른 도메인 서비스 계정을 지정하는 것이 좋습니다.
    
9. 다음을 클릭하면 다른 유효성 검사 라운드가 수행되는 것이고 모든 문제가 보고됩니다. 유효성 검사가 성공적으로 완료된 후 설치 관리자에서 포털 구성 페이지로 이동합니다. 
    
10. 포털 구성 페이지에서 다음 정보를 제공합니다.
    
    - **QoE 보관 SQL Server:** SQL Server 위치의 인스턴스 이름입니다. QoE 보관 구성 페이지 및 큐브 구성 페이지와 달리 컴퓨터 이름은 고정되지 않고 제공해야 합니다. 설치를 위해 QoE 보관 구성 요소를 선택한 경우 이 필드는 QoE 보관 구성 페이지에 제공된 값으로 미리 채워지게 됩니다.
    
    - **큐브 분석 서버: SQL Server** 위치의 Analysis Service 인스턴스 이름을 지정합니다. 설치를 위해 큐브 구성 요소를 선택한 경우 큐브 구성 페이지에 제공된 값으로 이 필드가 미리 채워지게 됩니다.
    
    - **리포지토리 SQL Server:** SQL Server 인스턴스 이름을 지정합니다. 설치 SQL Server QoE 보관 데이터베이스가 있는 위치의 SQL Server 인스턴스 이름이 다른 구성 요소에서 제공된 경우 이 필드는 QoE Archive DB 및 SQL Server 인스턴스 이름으로 미리 채워지게 됩니다. 이 인스턴스는 모든 SQL Server 있습니다.
    
    - **리포지토리 데이터베이스:** 기본적으로 옵션은 "새 데이터베이스 만들기"로 설정됩니다. 리포지토리 DB 업그레이드는 지원되지 않습니다. "기존 데이터베이스 사용" 옵션을 사용할 수 있는 유일한 상황은 기존 Repository DB에 설치할 빌드와 동일한 스마마가 있는 경우뿐입니다.
    
    - **IIS 앱 풀 사용자 - 사용자 이름 &amp; 암호:** IIS 응용 프로그램 풀이 실행해야 하는 계정입니다. 기본 제공 시스템 계정을 선택하면 사용자 이름 및 암호 필드가 회색으로 표시됩니다. 이러한 필드는 사용자가 도메인 서비스 계정 정보를 입력할 수 있도록 드롭다운 상자에서 "기타"를 선택한 경우만 사용하도록 설정됩니다.
    
11. 다음을 클릭하면 최종 유효성 검사 라운드가 수행되어 제공된 자격 증명을 사용하여 SQL Server 인스턴스에 액세스할 수 있으며 컴퓨터의 IIS를 사용할 수 있는지를 확인하게 됩니다. 유효성 검사가 성공적으로 완료된 후 설치 프로그램이 설치를 진행합니다. 
    
설치 관리자를 완료하면 QoE SQL Server 큐브 처리의 초기 로드를 수행하여 SQL Server 에이전트 작업이 진행될 것입니다. QoE의 데이터 양에 따라 포털에 아직 데이터를 볼 수 없습니다. 데이터 로드 및 큐브 처리 상태를 확인한 후 로  `http://<machinename>/CQD/#/Health` 이동하십시오. 
> [!NOTE]
> 다운로드 큐브 처리의 상태를 확인할 URL은 대/중입니다. 'health'를 입력하면 URL이 작동하지 않습니다. URL 끝에 대문자 H를 사용하여 'Health'를 입력해야 합니다. 
  
디버그 모드를 사용하는 경우 자세한 로그 메시지가 표시됩니다. 디버그 모드를 사용하도록 설정하려면 **%SYSTEMDRIVE%\Program Files\Skype For Business 2015** CQD\QoEDataService\web.config로 이동하여 값을 **True로** 설정하도록 다음 줄을 업데이트합니다.

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

기본 포털 페이지는 를 통해 액세스할 수  `http://<machinename>/CQD` 있습니다. 
## <a name="managing-user-access-for-the-portal"></a>포털에 대한 사용자 액세스 관리

포털에 대한 사용자 권한 부여를 관리하기 위해 IIS 7.0에 도입된 URL 권한 부여를 사용하는 것이 좋습니다. IIS 보안에 대한 자세한 내용은 [UNDERSTANDING IIS 7.0 URL Authorization를 참조하십시오.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)
  
모든 웹 사이트 또는 웹 응용 프로그램은 일반적으로 "모든 사용자 허용"인 전체 IIS에 대해 구성된 기본 URL 권한 부여를 상속합니다. 포털에 대한 액세스가 보다 제한적인 경우 관리자는 "권한 부여 규칙"을 편집하여 특정 사용자 그룹에만 액세스 권한을 부여할 수 있습니다.
  
![IIS에서 통화 품질 배포 - 권한 부여 규칙.](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> 권한 부여 규칙 아이콘은 다른 권한 부여 메커니즘인 ASP.NET 섹션에서 ".NET 권한 부여"와 혼동하지 않습니다. 
  
관리자는 먼저 상속된 "모든 사용자 허용" 규칙을 제거해야 합니다. 이렇게 하면 권한이 없는 사용자가 포털에 액세스할 수 없습니다.
  
![CQD를 배포합니다.](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
다음으로 관리자는 새 허용 규칙을 추가하고 특정 사용자에게 포털 액세스 권한을 부여해야 합니다. 사용자를 관리하기 위해 "CQDPortalUsers"라는 로컬 그룹을 만들어야 합니다.
  
![통화 품질 대시보드를 배포합니다.](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
구성 세부 정보는 포털의 web.config 디렉터리에 저장됩니다.
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

다음 단계는 CQD의 대시보드를 구성하는 것입니다. IIS에서 사용자를 인증한 후 웹 포털 콘텐츠에 액세스하려면 CQD 디렉터리에 대한 파일 권한이 필요합니다. CQD 디렉터리 속성의 보안 탭을 통해 ACL을 변경하여 개별 사용자 또는 그룹을 추가할 수 있습니다. 그러나 권장되는 방법은 파일 사용 권한을 그대로 두는 것입니다. 대신 인증된 사용자에 상관없이 IIS Worker 프로세스를 사용하여 CQD 디렉터리에 액세스하도록 IIS 설정을 변경합니다. 
  
> [!IMPORTANT]
> CQD 응용 프로그램에 대해 이 설정만 변경해야 합니다. 단, 두 API 응용 프로그램인 QoEDataService 및 QoERepositoryService는 변경하지 않습니다. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>CQD에 대한 파일 액세스 구성(대시보드)

1. CQD에 대한 구성 편집기를 열 수 있습니다.
    
     ![통화 품질 대시보드를 배포합니다.](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. 섹션에서 **system.webServer/serverRuntime 을 선택하십시오.**
    
     ![통화 품질 대시보드를 배포합니다.](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. authenticatedUserOverride를 **UseWorkerProcessUser로 변경합니다.**
    
     ![통화 품질 대시보드 배포 - 구성 편집기.](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. 페이지 **오른쪽에서** 적용을 클릭합니다.
    
## <a name="known-issues"></a>알려진 문제

### <a name="the-cqd-shows-no-data-after-deployment"></a>배포 후 CQD에 데이터가 없음

다음과 같은 오류가 표시될 수 있습니다.

*큐브에서 쿼리를 실행하는 동안 쿼리를 수행할 수 없습니다. 쿼리 편집기를 사용하여 쿼리를 수정하고 문제를 해결합니다. 큐브에 액세스할 수 있는지도 확인 합니다.*

즉, CQD에서 사용하려면 SQL Server Analysis Services에서 큐브를 처리해야 합니다. 다음 단계에 따라 이 문제를 해결할 수 있습니다.

1. 를 SQL Management Studio Analysis **Services 를 선택합니다.**

2. **QoECube** 개체를 확장하고 **QoE 메트릭을 선택하고** 마우스 오른쪽 단추를 클릭한 다음 **찾아보기를 선택합니다.** 

    이 경우 빈 브라우저가 반환될 경우 큐브가 아직 진행되지 않은 것입니다.

3. **QoE 메트릭을 마우스 오른쪽 단추로** 클릭하고 프로세스를 **클릭합니다.**

4. 처리가 완료되면 개체를 마우스 오른쪽 단추로  다시 클릭하고 찾아보기를 클릭하여 브라우저 페이지에 데이터가 표시되어 있는지 확인하십시오. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>설치 관리자에서 IIS에서 올바른 설정을 만들지 못하기 때문에 로그인하는 데 문제가 있습니다.

드문 경우지만 설치 관리자에서 IIS에서 올바른 설정을 만들지 못합니다. 사용자가 CQD에 로그인할 수 있도록 수동으로 변경해야 합니다. 사용자가 로그인하는 데 문제가 있는 경우 다음 단계를 따르세요.
  
1. IIS 관리자를 열고 기본 웹 사이트로 이동합니다.
    
     ![통화 품질 대시보드를 배포합니다.](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. "인증"을 클릭합니다. "익명 인증", "ASP.NET 가장", "양식 인증" 및 "Windows 인증"이 아래 표시된 설정과 일치하지 않는 경우 아래 설정과 일치하도록 수동으로 변경합니다. 다른 모든 인증 메커니즘은 사용하지 않도록 설정해야 합니다.
    
     ![통화 품질 대시보드를 배포합니다.](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. "Windows 인증"의 경우 오른쪽의 고급 설정 클릭합니다.
    
     ![통화 품질 대시보드를 배포합니다.](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. "확장된 보호"를 수락으로 설정하고 "커널 모드 인증 사용" 확인란을 선택합니다.
    
     ![통화 품질 대시보드를 배포합니다.](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. "기본 웹 사이트" 아래의 각 "CQD", "QoEDataService" 및 "QoERepositoryService" 항목에 대해 위의 단계를 반복합니다.
    
HTTP 및 HTTPS 포트 바인딩의 경우 설치 관리자에서 기본 포트 번호(HTTP의 경우 포트 80, HTTPS의 경우 포트 443)에 포트 바인딩을 생성합니다. 이러한 바인딩을 사용하는 다른 웹 사이트가 있는 경우 충돌이 있으며 IIS 동작을 예측할 수 없습니다. 이 문제를 방지하는 가장 좋은 방법은 CQD를 설치하기 전에 다른 웹 사이트가 포트 80 및 443에 매핑되어 있는지 확인하는 것입니다. 
  
IIS에서 SSL/TLS를 사용하도록 설정하고 사용자가 HTTP 대신 보안 HTTPS를 통해 연결하도록 강제하려면
  
1. IIS에서 Secure Sockets Layer 구성은 [IIS 7에서 Secure Sockets Layer 구성을 참조합니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)) 완료되면 으로  `http` `https` 대체합니다.
    
2. SQL Server 연결에서 TLS를 사용하도록 설정하는 방법에 대한 자세한 내용은 Microsoft Management Console을 사용하여 SQL Server 인스턴스에 [대해 SSL 암호화를](https://support.microsoft.com/kb/316898/)사용하도록 설정하는 방법을 참조하세요.
    
## <a name="cube-sync-fails"></a>큐브 동기화 실패

QoEMetrics에는 최종 사용자 시계에 따라 일부 잘못된 레코드가 포함될 수 있습니다. 시간이 60yrs보다 크면 큐브 가져오기에 실패합니다.
  
 아래 선택을 사용하여 Min 및 Max StartTime/EndTime을 선택합니다. 먼 미래에 레코드를 찾아 삭제하면 무시될 수 있으며 동기화 프로세스가 중단됩니다.
  
- MIN(StartTime) FROM CqdPartitionedStreamView를 선택합니다.
    
- MAX(StartTime) FROM CqdPartitionedStreamView를 선택합니다.
    
- MIN(EndTime) FROM CqdPartitionedStreamView를 선택합니다.
    
- MAX(EndTime) FROM CqdPartitionedStreamView를 선택합니다.
    
## <a name="post-install-tasks"></a>설치 후 작업

### <a name="importing-buildings-and-networks"></a>건물 및 네트워크 가져오기

CQD를 설치한 후 다음 구성 작업을 수행합니다.
  
1. 구축 유형 정의(권장)
    
2. 소유권 유형 정의(권장)
    
3. 네트워크 유형 정의(권장)
    
4. 건물 가져오기(권장)
    
5. 서브넷 가져오기(권장)
    
### <a name="define-building-types"></a>건물 유형 정의

건물 유형은 조직 내의 다양한 건물 정의 또는 유형을 설명하는 데 사용됩니다. 
  
> [!NOTE]
> 이 단계는 선택 사항이지만 권장됩니다. 
  
예
  
- 본사
    
- 원격 Office
    
- 공동 위치
    
  **예제 SQL 구문**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

BuildingTypeId 및 BuildingTypeDesc 매개 변수는 필수입니다.
  
### <a name="define-building-ownership-types"></a>소유권 유형 정의

소유권 유형은 소유 자산과 임대 자산을 구분하는 데 사용됩니다.
  
> [!NOTE]
> 이 단계는 선택 사항이지만 권장됩니다. 
  
예
  
- Contoso Leased non-RE &amp; F
    
- Contoso Leased RE &amp; F
    
- Contoso Owned
    
- 자회사 임대
    
  **예제 SQL 구문**
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

OwnershipTypeId 및 OwnershipTypeDesc 매개 변수가 필요합니다. 
  
### <a name="define-network-names"></a>네트워크 이름 정의

네트워크 유형은 조직 내에서 다양한 유형의 네트워크를 설명하는 데 사용됩니다. 이렇게 하면 특정 네트워크 유형을 필터링(또는 필터링)할 수 있습니다.
  
> [!NOTE]
> 네트워크 이름을 정의하는 것이 되지만 선택 사항입니다. 네트워크 이름을 정의하지 않도록 결정한 경우 각 CqdNetwork 항목에 BuildingId가 0인지 확인합니다. 
  
예
  
- VPN
    
- 랩
    
  **예제 SQL 구문**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

NetworkNameID 및 NetworkName 매개 변수는 필수이며 NetworkType 매개 변수는 선택 사항이지만 권장됩니다.
  
### <a name="import-buildings"></a>건물 가져오기

건물을 가져오면 특정 정보(WiFi/유선 등에서 건물당 불량 통화 수)를 구축할 수 있습니다. 
  
> [!NOTE]
> 이 단계는 선택 사항이지만 권장됩니다. 
  
새 건물을 가져오기 전에 미리 정의한 BuildingKey가 이미 식별되어 있습니다. 이를 위해 "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL 명령을 실행하여 현재 값을 식별하고 결과에 1을 추가합니다.
  
 **예제 SQL 구문**
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId 매개 변수는 필수이며 다른 매개 변수는 선택 사항입니다.
  
### <a name="import-subnets"></a>서브넷 가져오기

건물을 가져오면 특정 정보(WiFi/유선 등에서 건물당 불량 통화 수)를 구축할 수 있습니다. 
  
> [!NOTE]
> 이 단계는 선택 사항이지만 권장됩니다.
  
서브넷을 가져와서 마지막 단계에서 가져온 건물에 매핑합니다. NetworkName을 채우지 않도록 결정한 경우 이 표의 각 항목이 NetworkNameID 0을 사용하는지 확인합니다. 통화 품질 대시보드의 SQL 및 매개 변수에 대한 자세한 내용은 [Use Call Quality Dashboard for 비즈니스용 Skype 서버.](./use.md)
  
 **예제 SQL 구문**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

Network 및 UpdatedDate 매개 변수는 필수이며 다른 매개 변수는 선택 사항입니다.
  
### <a name="optional-bssid"></a>선택 사항: BSSID

BSSID 정보를 채우면 컨트롤러 또는 라디오에 대한 추가 WiFi 스트림 상관 관계가 있습니다. 이는 구성 또는 서브넷을 사용하여 필터링하는 것 외에 추가됩니다. 
  
 **예제 SQL 구문**
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

**CqdBssidTable 세부 정보**

|**CQD에 표시된 것**|**CQDBssid 테이블**|**예제 입력**|
|:-----|:-----|:-----|
|Ap NName  <br/> |AP  <br/> |AP1  <br/> |
|BBssid  <br/> |BSS  <br/> |00-00-00-00-00-00(나만의 fformat 사용)  <br/> |
|컨트롤러  <br/> |건물  <br/> |아루바 AP 7  <br/> |
|디바이스  <br/> |ess  <br/> |Controller1  <br/> |
|라디오  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>가져온 데이터 처리

기본적으로 건물/네트워크 데이터를 가져온 후 해당 시점 이후에 생성된 레코드에만 적용됩니다. 
  
이 새 데이터를 사용하여 이전 레코드에 태그를 지정하려면 아래와 같이 CqdUpdateBuilding 저장 프로시저를 실행해야 합니다. 
  
첫 번째 레코드의 날짜를 제공합니다(SELECT MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of my last two values, then NULL.
  
데이터가 스트림 데이터와 연결된 후 SSIS 큐브는 모든 레코드를 다시 처리해야 합니다. 이는 BSSID/ISP 데이터를 대량으로 추가할 때도 적용됩니다. "전체 프로세스"가 선택되어 있도록 합니다.
