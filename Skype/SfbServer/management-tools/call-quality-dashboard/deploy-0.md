---
title: 비즈니스용 Skype 서버에 대 한 통화 품질 대시보드 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: '요약: 통화 품질 대시보드의 배포 프로세스에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버에 대 한 도구입니다.'
ms.openlocfilehash: d42d735ab5a60ec02ad2e1f4f696908996457c0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042265"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 통화 품질 대시보드 배포
 
**요약:** 통화 품질 대시보드의 배포 프로세스에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버에 대 한 도구입니다.
  
## <a name="deployment-overview"></a>배포 개요

CQD (통화 품질 대시보드)는 다음과 같은 세 가지 주요 구성 요소로 구성 됩니다.
  
- **보관 데이터베이스**(QoE) 데이터를 복제 하 고 저장 합니다.
    
- QoE 보관 데이터베이스의 데이터가 최적화 되 고 빠른 액세스를 위해 집계 되는 **큐브**
    
- **포털**-사용자가 QoE 데이터를 쉽게 쿼리하고 시각화할 수 있습니다.
    
![CQD 구성 요소](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
QoE 보관을 위한 설치 프로세스에는 QoE 보관 데이터베이스를 만들고, 원본 QoE 메트릭 데이터베이스의 데이터를 QoE 보관 데이터베이스로 이동 하 고, SQL Server 에이전트 작업을 설정 하 여 저장 된 데이터베이스를 실행 하는 SQL Server 저장 프로시저를 배포 하는 작업이 포함 됩니다. 정기적으로 프로시저를 만듭니다. 
  
큐브 배포는 QoE 보관 사서함이 있는 사용자 로부터 정보를 가져오고, 큐브를 배포 하 고, 정기적으로 큐브를 새로 고치는 정기적인 SQL Server 에이전트 작업을 설정 합니다.
  
Portal 설치 각 사용자의 보고서/쿼리에 CQD 사용자 매핑을 저장 하는 리포지토리 데이터베이스를 만듭니다. 그런 다음 사용자 지정 및 직접 쿼리를 만들어 큐브의 데이터를 시각화 하는 대시보드 인 IIS 웹 응용 프로그램을 설정 합니다. Portal 설치 프로그램에서는 사용자가 리포지토리 및 큐브에 프로그래밍 방식으로 액세스할 수 있도록 Api를 제공 하는 두 개의 추가 웹 응용 프로그램이 만들어집니다. 이러한 Api는 대시보드의 내부에도 사용 됩니다.
  

|**작업 단계**|**단계**|**역할 및 그룹 구성원**|**설명서**|
|:-----|:-----|:-----|:-----|
|하드웨어 및 소프트웨어 필수 구성 요소를 설치 합니다.  <br/> |CQD 구성을 결정 하 고 설치를 수행할 SQL Server를 선택 합니다.  <br/> |로컬 Administrators 그룹의 구성원인 도메인 사용자  <br/> |배포 설명서의 "사전 설치 요구 사항" 섹션  <br/> |
|CQD 설치  <br/> |배포 문서 다음에 MSI를 실행 합니다.  <br/> |설치를 수행 하려면 설치 하는 계정은 로컬 administrators 그룹의 구성원 인 도메인 사용자 여야 하며 모니터링 서버의 QoE 메트릭 데이터베이스에 대 한 읽기 액세스 권한이 있어야 합니다.  <br/> |배포 설명서의 "계정 및 배포 단계" 섹션  <br/> |
|사용자에 게 액세스 권한을 부여 합니다.  <br/> |포털에 대 한 사용자 권한 부여를 관리 하려면 IIS 7.0에 도입 된 URL 권한 부여를 사용 하는 것이 좋습니다. 자세한 내용은 [IIS 7.0 URL 권한 부여 이해](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)(영문)를 참조 하십시오.  <br/> |로컬 Administrators 그룹의 구성원인 도메인 사용자  <br/> |배포 설명서의 포털 섹션에 대 한 사용자 액세스 관리  <br/> |
|선택 사항: 서브넷 매핑 정보를 제공 합니다.  <br/> |QoE 보관 데이터베이스에서 네트워크 및 건물 매핑 테이블을 채웁니다.  <br/> |QoE 보관 데이터베이스에 대 한 쓰기 권한이 있는 계정입니다.  <br/> |사용자 설명서의 "서브넷 정보 제공" 섹션  <br/> |
   


통화 품질 대시보드를 배포 하려면 인프라를 설정 하 고 소프트웨어를 설치 해야 합니다. 다음 절차에서는이 프로세스를 간략하게 설명 합니다.
  
## <a name="deployment-steps"></a>배포 단계

1. CQD의 보관 데이터베이스 구성 요소가 설치 될 컴퓨터 (SQL Server가 설치 된 컴퓨터)에 CallQualityDashboard를 복사 합니다. 
    
2. MSI를 실행 합니다 (Windows에서 관리자 권한으로 실행 하 라는 메시지가 표시 됨). 
    
3. 사용권 계약서에 동의 합니다.
    
4. 통화 품질 대시보드 구성 요소와 관련 된 파일을 찾을 대상 폴더를 선택 하거나 기본 위치를 그대로 사용 합니다.
    
5. 모든 기능을 선택 합니다.
    
6. QoE 보관 구성 페이지에서 다음 정보를 제공 합니다.
    
   - **QoE 메트릭 SQL Server:** QoE 메트릭 DB가 있는 (데이터 원본이 됨) SQL Server 인스턴스 이름입니다.
    
   - **QoE 보관 SQL Server 이름:** 이 필드는 읽기 전용으로 로컬 컴퓨터의 정규화 된 도메인 이름으로 고정 됩니다. 보관 데이터베이스는 로컬 컴퓨터에만 설치할 수 있습니다.
    
   - **QoE ARCHIVE SQL Server 인스턴스:** 보관 데이터베이스를 만들 로컬 SQL Server 인스턴스 이름입니다. 기본 SQL Server 인스턴스를 사용 하려면이 필드를 비워 둡니다. 명명 된 SQL Server 인스턴스를 사용 하려면 인스턴스 이름 (예: 이름 뒤에 "\")을 지정 합니다.
    
   - **QoE 보관 데이터베이스:** 기본적으로이 옵션은 "새 데이터베이스 만들기"로 설정 됩니다. 보관 DB 업그레이드는 지원 되지 않으므로 "기존 데이터베이스 사용" 옵션을 사용할 수 있는 유일한 경우는 기존 보관 데이터베이스에 설치할 빌드와 같은 스키마가 있는 경우입니다.
    
   - **데이터베이스 파일 디렉터리:** 보관 DB 데이터베이스 파일 (.mdf 및 .ldf)이 위치할 경로입니다. 이는 OS와 별개인 드라이브 (권장 하드웨어 구성의 HDD2)에 있어야 합니다. 파일 이름이 설치 중에 수정 되므로 잠재적인 충돌을 방지 하기 위해 파일이 없는 빈 디렉터리를 사용 하는 것이 좋습니다.
    
   - **여러 파티션 사용:** 기본값은 Business Intelligence edition 또는 Enterprise edition SQL Server가 필요한 "여러 파티션"으로 설정 됩니다. Standard edition의 경우 "단일 파티션" 옵션을 선택 합니다. 단일 파티션을 사용 하는 경우에는 큐브 처리 성능이 영향을 받을 수 있습니다.
    
     > [!NOTE]
     > 설치가 완료 되 면 여러 파티션 사용 옵션을 변경할 수 없습니다. 이를 변경 하려면 먼저 큐브 기능을 제거한 다음 제어판의 "변경" 옵션을 사용 하 여 다시 설치 해야 합니다. 
  
   - **파티션 파일 디렉터리:** QoE 보관 데이터베이스에 대 한 파티션을 배치할 경로입니다. 이는 OS 드라이브 및 SQL 데이터베이스 로그 파일 드라이브와는 별개의 드라이브 (권장 하드웨어 구성의 HDD3)에 있어야 합니다. 파일 이름이 설치 중에 수정 되므로 잠재적인 충돌을 방지 하기 위해 파일이 없는 빈 디렉터리를 사용 하는 것이 좋습니다.
    
   - **SQL 에이전트 작업 사용자-사용자 이름 &amp; 암호:** SQL Server 에이전트 작업의 "QoE 보관 데이터" 단계 (저장 프로시저를 실행 하 여 QoE 메트릭 DB에서 보관 DB로 데이터를 페치 함)를 실행 하는 데 사용 되는,이 계정에는 Accounts 섹션에 나와 있는 것 처럼 QoE 메트릭 DB에 대 한 읽기 권한이 있어야 합니다. 또한이 계정에는 QoE Archive SQL Server 인스턴스에 로그인이 있어야 합니다.
    
     > [!NOTE]
     > SQL Server 인스턴스가 실행 중인 계정 (예: NT SERVICE\MSSQLSERVER)에는 설치에 성공 하기 위해 위에 지정 된 디렉터리에 대 한 액세스/권한이 있어야 합니다. 자세한 내용은 [데이터베이스 엔진 액세스에 대 한 파일 시스템 권한 구성](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx) 를 참조 하십시오.
  
7. 다음을 클릭 하면 설치 관리자가 필수 구성 요소 검사를 수행 하 고 문제가 발생 한 경우 보고 합니다. 모든 필수 구성 요소 확인이 통과 되 면 설치 관리자는 큐브 구성 페이지로 이동 합니다. 
    
    > [!NOTE]
    > 설치 관리자에 QoE Archive SQL Server 인스턴스에 대 한 SQL Server 에이전트 서비스가 현재 실행 되 고 있지 않은 경고 메시지가 표시 되 면 설치를 계속할 수 있지만 설치 후에는 SQL 에이전트 서비스가 실행 되 고 있는지 확인 하 고 시작 유형을 다음으로 설정 해야 합니다. 자동으로 예약 된 작업을 실행 합니다. 
  
8. 큐브 구성 페이지에서 다음 정보를 입력 합니다.
    
   - **QoE 보관 SQL Server 이름:** 이 필드는 읽기 전용으로 로컬 컴퓨터의 정규화 된 도메인 이름으로 고정 됩니다. QoE 보관 데이터베이스가 있는 컴퓨터 에서만 큐브를 설치할 수 있습니다 (참고). 큐브 자체가 원격 컴퓨터에 설치 되어 있을 수 있습니다. 아래 참조)
    
   - **QoE ARCHIVE SQL Server 인스턴스:** QoE 보관 데이터베이스를 배치할 SQL Server 인스턴스 이름입니다. 기본 SQL Server 인스턴스를 지정 하려면이 필드를 비워 둡니다. 명명 된 SQL Server 인스턴스를 지정 하려면 인스턴스 이름 (예: 이름 뒤에 name\")을 입력 합니다. 설치를 위해 QoE 보관 구성 요소를 선택한 경우이 필드는 QoE 보관 구성 페이지에 제공 된 값으로 미리 채워집니다.
    
   - **큐브 분석 서버:** 큐브를 만들 SQL Server Analysis Service 인스턴스 이름입니다. 이는 다른 컴퓨터 일 수 있지만 설치 사용자는 대상 SQL Server Analysis Services 인스턴스의 서버 관리자 구성원 이어야 합니다.
    
     > [!NOTE]
     >  Analysis Services 서버 관리자 권한을 구성 하는 방법에 대 한 자세한 내용은 [Grant Server Administrator permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx) 를 참조 하십시오.
  
   - **여러 파티션 사용:** 기본값은 Business Intelligence edition 또는 Enterprise edition SQL Server가 필요한 "여러 파티션"으로 설정 됩니다. Standard edition의 경우 "단일 파티션" 옵션을 선택 합니다. 단일 파티션을 사용 하는 경우에는 큐브 처리 성능이 영향을 받을 수 있습니다.
    
     > [!NOTE]
     >  설치가 완료 되 면 여러 파티션 사용 옵션을 변경할 수 없습니다. 이를 변경 하려면 먼저 큐브 기능을 제거한 다음 제어판의 "변경" 옵션을 사용 하 여 다시 설치 해야 합니다.
  
   - **큐브 사용자-사용자 이름 &amp; 암호:** 큐브 처리를 시작할 도메인 서비스 계정 이름 및 암호 (마스크 됨)입니다. QoE 보관 구성 요소를 설치 하도록 선택한 경우이 필드는 SQL 에이전트 작업 사용자의 보관 구성 페이지에 제공 된 값으로 미리 채워지고, 설치 프로그램에서 다음을 허용 하도록 다른 도메인 서비스 계정을 지정 하는 것이 좋습니다. 최소 필요한 권한
    
9. 다음을 클릭 하면 다른 유효성 검사 라운드를 수행 하 고 문제가 보고 됩니다. 유효성 검사가 성공적으로 완료 되 면 설치 관리자가 포털 구성 페이지로 이동 합니다. 
    
10. 포털 구성 페이지에서 다음 정보를 제공 합니다.
    
    - **QoE 보관 SQL Server:** QoE 보관 데이터베이스가 있는 위치에 대 한 SQL Server 인스턴스 이름입니다. QoE 보관 구성 페이지와 큐브 구성 페이지와 달리 컴퓨터 이름은 고정 되어 있지 않으므로 제공 해야 합니다. 설치를 위해 QoE 보관 구성 요소를 선택한 경우이 필드는 QoE 보관 구성 페이지에 제공 된 값으로 미리 채워집니다.
    
    - **큐브 분석 서버:** 큐브가 있는 SQL Server Analysis Service 인스턴스 이름입니다. 설치를 위해 큐브 구성 요소를 선택한 경우이 필드는 큐브 구성 페이지에서 제공 되는 값으로 미리 채워집니다.
    
    - **리포지토리 SQL Server:** 리포지토리 데이터베이스를 만들 SQL Server 인스턴스 이름입니다. QoE 보관 데이터베이스가 있는 위치에 대 한 SQL Server 인스턴스 이름이 설치 프로그램에서 이전에 제공 된 경우 (기타 구성 요소)이 필드는 QoE 보관 DB SQL Server 인스턴스 이름으로 미리 채워집니다. 모든 SQL Server 인스턴스를 사용할 수 있습니다.
    
    - **리포지토리 데이터베이스:** 기본적으로이 옵션은 "새 데이터베이스 만들기"로 설정 됩니다. 리포지토리 DB 업그레이드는 지원 되지 않으므로 "기존 데이터베이스 사용" 옵션을 사용할 수 있는 유일한 경우는 기존 리포지토리 DB에 설치할 빌드와 같은 스키마가 있는 경우입니다.
    
    - **IIS 응용 프로그램 풀 사용자-사용자 &amp; 이름 암호:** IIS 응용 프로그램 풀을 실행 해야 하는 계정입니다. 기본 제공 시스템 계정을 선택한 경우 사용자 이름 및 암호 필드가 회색으로 표시 됩니다. 사용자가 도메인 서비스 계정 정보를 입력할 수 있도록 드롭다운 상자에서 "기타"를 선택한 경우에만 이러한 필드를 사용할 수 있습니다.
    
11. 다음을 클릭 하면 마지막으로 유효성 검사를 수행 하 여 제공 된 자격 증명을 사용 하 여 SQL Server 인스턴스에 액세스할 수 있고 해당 컴퓨터에서 IIS를 사용할 수 있는지를 확인 합니다. 유효성 검사가 성공적으로 완료 되 면 설치 관리자는 설정을 계속 진행 합니다. 
    
설치 관리자가 완료 되 면 SQL Server 에이전트 작업이 진행 중인 것 이며,이는 QoE 데이터의 초기 로드와 큐브 처리를 수행 하는 것입니다. QoE의 데이터 양에 따라 포털에는 아직 볼 수 있는 데이터가 포함 되지 않습니다. 데이터 로드 및 큐브 처리 상태를 확인 하려면로 `http://<machinename>/CQD/#/Health`이동 합니다. 
> [!NOTE]
> 다운로드 큐브 처리의 상태를 확인 하는 URL은 대/소문자를 구분 합니다. ' Health '를 입력 하면 URL이 작동 하지 않습니다. 대문자 H를 사용 하 여 URL의 끝에 ' Health '를 입력 해야 합니다. 
  
디버그 모드를 사용 하는 경우 자세한 로그 메시지가 표시 됩니다. 디버그 모드를 사용 하도록 설정 하려면 **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**으로 이동 하 고 다음 줄을 업데이트 하 여 값을 **True**로 설정 합니다.

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

기본 포털 페이지는을 통해 `http://<machinename>/CQD`액세스할 수 있습니다. 
## <a name="managing-user-access-for-the-portal"></a>포털에 대 한 사용자 액세스 관리

포털에 대 한 사용자 권한 부여를 관리 하려면 IIS 7.0에 도입 된 URL 권한 부여를 사용 하는 것이 좋습니다. IIS 보안에 대 한 자세한 내용은 [iis 7.0 URL 권한 부여 이해](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)(영문)를 참조 하십시오.
  
모든 웹 사이트 또는 웹 응용 프로그램은 전체 IIS에 대해 구성 된 기본 URL 권한 부여 (일반적으로 "모든 사용자 허용")를 상속 합니다. 포털에 대 한 액세스를 보다 엄격 하 게 제한 해야 하는 경우 관리자는 "권한 부여 규칙"을 편집 하 여 특정 사용자 그룹 에게만 액세스 권한을 부여할 수 있습니다.
  
![IIS에서 통화 품질-권한 부여 규칙 배포](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> 권한 부여 규칙 아이콘은 서로 다른 인증 메커니즘인 ASP.NET 섹션에 있는 ".NET 인증"과 혼동 하지 않도록 합니다. 
  
관리자는 먼저 상속 된 "모든 사용자에 게 허용" 규칙을 제거 해야 합니다. 이렇게 하면 권한이 없는 사용자가 포털에 액세스할 수 없습니다.
  
![CQD 배포](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
다음으로, 관리자는 새 허용 규칙을 추가 하 고 특정 사용자에 게 포털 액세스 권한을 부여 해야 합니다. 사용자를 관리 하기 위해 "CQDPortalUsers" 라는 로컬 그룹을 만드는 것이 좋습니다.
  
![통화 품질 대시보드 배포](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
구성 세부 정보는 포털의 실제 디렉터리에 있는 web.config에 저장 됩니다.
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

다음 단계에서는 CQD의 대시보드를 구성 합니다. 사용자가 IIS에서 인증 된 후에는 웹 포털 콘텐츠에 액세스 하기 위해 CQD 디렉터리에 대 한 파일 사용 권한이 있어야 합니다. CQD 디렉터리 속성의 보안 탭을 통해 Acl을 변경 하 여 개별 사용자 또는 그룹을 추가할 수 있습니다. 그러나 권장 되는 방법은 파일 사용 권한을 그대로 유지 하는 것입니다. 대신 IIS 작업자 프로세스를 사용 하 여 인증 된 사용자에 관계 없이 CQD 디렉터리에 액세스 하도록 IIS 설정을 변경 합니다. 
  
> [!IMPORTANT]
> 두 가지 API 응용 프로그램 인 QoEDataService 및 QoERepositoryService에 대 한 것이 아니라 CQD 응용 프로그램에 대해서만이 설정을 변경 하는 것이 중요 합니다. 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a>CQD (대시보드)에 대 한 파일 액세스 구성

1. CQD 용 구성 편집기를 엽니다.
    
     ![통화 품질 대시보드 배포](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. 섹션에서 **system.webserver/serverRuntime**를 선택 합니다.
    
     ![통화 품질 대시보드 배포](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. AuthenticatedUserOverride를 **Use2| Processuser**로 변경 합니다.
    
     ![통화 품질 대시보드 배포-구성 편집기](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. 페이지 오른쪽에서 **적용** 을 클릭 합니다.
    
## <a name="known-issues"></a>알려진 문제

### <a name="the-cqd-shows-no-data-after-deployment"></a>배포 후 CQD에 데이터가 표시 되지 않음

다음 오류가 표시 될 수 있습니다.

*큐브를 실행 하는 동안 쿼리를 수행할 수 없습니다. 쿼리 편집기를 사용 하 여 쿼리를 수정 하 고 문제를 수정 합니다. 또한 큐브에 액세스할 수 있는지 확인 합니다.*

즉, 큐브가 CQD에서 사용 되기 전에 SQL Server Analysis Services에서 처리 되어야 합니다. 다음 단계를 수행 하 여이 문제를 해결할 수 있습니다.

1. SQL Management Studio를 열고 **Analysis Services**를 선택 합니다.

2. **QoECube** 개체를 확장 하 고, **QoE Metric**을 선택한 다음, 마우스 오른쪽 단추를 클릭 하 고 **찾아보기를**선택 합니다. 

    이 경우 빈 브라우저가 반환 되 면 큐브가 아직 처리 되지 않은 것입니다.

3. **QoE Metric** angain을 마우스 오른쪽 단추로 클릭 하 고 **프로세스**를 선택 합니다.

4. 처리가 완료 되 면 개체를 다시 마우스 오른쪽 단추로 클릭 하 고 **찾아보기를** 선택 하 여 브라우저 페이지에 데이터가 표시 되는지 확인 합니다. 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a>설치 관리자가 IIS에서 올바른 설정을 만들지 못했으므로 로그인 하는 데 문제가 있습니다.

드문 경우 지만 설치 관리자가 IIS에서 올바른 설정을 만들지 못할 수 있습니다. 수동 변경은 사용자가 CQD에 로그인 할 수 있도록 하기 위해 필요 합니다. 사용자가 로그인 하는 데 문제가 있는 경우 다음 단계를 수행 하세요.
  
1. IIS 관리자를 열고 기본 웹 사이트로 이동 합니다.
    
     ![통화 품질 대시보드 배포](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. "인증"을 클릭 합니다. "익명 인증", "ASP.NET 가장", "폼 인증" 및 "Windows 인증"이 아래 표시 된 설정과 일치 하지 않으면 아래 설정과 일치 하도록 수동으로 변경 합니다. 다른 모든 인증 메커니즘을 사용 하지 않도록 설정 해야 합니다.
    
     ![통화 품질 대시보드 배포](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. "Windows 인증"의 경우 오른쪽의 고급 설정을 클릭 합니다.
    
     ![통화 품질 대시보드 배포](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. "확장 된 보호"를 설정 하 여 수락 하 고 "커널 모드 인증 사용" 확인란을 선택 합니다.
    
     ![통화 품질 대시보드 배포](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. 각 "CQD", "QoEDataService" 및 "QoERepositoryService" 항목 아래에 있는 "기본 웹 사이트" 아래에서 위의 단계를 반복 합니다.
    
HTTP 및 HTTPS 포트 바인딩의 경우 설치 관리자가 기본 포트 번호 (HTTP의 경우 포트 80, HTTPS의 경우 포트 443)에 포트 바인딩을 만듭니다. 컴퓨터에 이러한 바인딩을 사용 하는 다른 웹 사이트가 있으면 충돌이 발생 하 고 IIS 동작을 예측할 수 없습니다. 이 문제를 방지 하는 가장 좋은 방법은 CQD를 설치 하기 전에 포트 80 및 443에 다른 웹 사이트가 매핑되어 있지 않은지 확인 하는 것입니다. 
  
IIS에서 SSL/TLS를 사용 하도록 설정 하 고 사용자가 HTTP 대신 보안 HTTPS를 통해 연결 하도록 강제 하려면 다음을 수행 합니다.
  
1. Secure Sockets layer 구성 IIS에서 [iis 7의 Secure sockets Layer 구성을](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx)참조 하십시오. 작업이 완료 되 면 `http` 로 `https`대체 합니다.
    
2. SQL Server 연결에서 TLS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Microsoft Management Console을 사용 하 여 Sql server 인스턴스에 대해 SSL 암호화를 사용 하도록 설정 하는 방법을](https://support.microsoft.com/kb/316898/)참조 하십시오.
    
## <a name="cube-sync-fails"></a>큐브 동기화 실패

QoEMetrics에는 최종 사용자 시계를 기반으로 하는 일부 잘못 된 레코드가 포함 될 수 있습니다. 시간 기울이기를 60 yrs 보다 크면 큐브 가져오기가 실패 합니다.
  
 아래 선택을 사용 하 여 Min and Max StartTime/EndTime을 확인 합니다. 레코드를 찾아서 삭제 하는 것이 가장 멀리, 그 이후에는 무시 하 고 동기화 프로세스를 중단 시킬 수 있습니다.
  
- Cqdpartition Edstreamview에서 MIN (StartTime)을 선택 합니다.
    
- Cqdpartition Edstreamview에서 MAX (StartTime) 선택
    
- Cqdpartition Edstreamview에서 최소 (EndTime)을 선택 합니다.
    
- Cqdpartition Edstreamview에서 MAX (EndTime)를 선택 합니다.
    
## <a name="post-install-tasks"></a>설치 후 작업

### <a name="importing-buildings-and-networks"></a>건물 및 네트워크 가져오기

CQD를 설치한 후에는 다음 구성 작업을 수행 합니다.
  
1. 건물 유형 정의 (권장)
    
2. 건물 소유권 유형 정의 (권장)
    
3. 네트워크 유형 정의 (권장)
    
4. 건물 가져오기 (권장)
    
5. 가져오기 서브넷 (권장)
    
### <a name="define-building-types"></a>건물 유형 정의

건물 유형은 조직 내의 다양 한 건물 정의 또는 유형을 설명 하는 데 사용 됩니다. 
  
> [!NOTE]
> 이 단계는 선택 사항 이지만 권장 됩니다. 
  
예
  
- 본사
    
- 원격 Office
    
- 공동으로 사용 하는 위치
    
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
  
### <a name="define-building-ownership-types"></a>건물 소유권 유형 정의

소유권 유형은 소유한 vs 임대 자산을 구분 하는 데 사용 됩니다.
  
> [!NOTE]
> 이 단계는 선택 사항 이지만 권장 됩니다. 
  
예
  
- Contoso 온-서 비&amp;F 임대
    
- Contoso 임대 다시&amp;F
    
- Contoso 소유
    
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

소유자 \ Typeid 및 소유자 배송 매개 변수는 필수입니다. 
  
### <a name="define-network-names"></a>네트워크 이름 정의

네트워크 유형은 조직 내에서 다양 한 유형의 네트워크를 설명 하는 데 사용 됩니다. 이렇게 하면 특정 네트워크 형식을 필터링 하거나 필터링 할 수 있습니다.
  
> [!NOTE]
> 네트워크 이름은 정의 하는 것이 좋지만 선택 사항입니다. 네트워크 이름을 정의 하지 않기로 결정 한 경우 각 CqdNetwork 항목에 BuildingId 0이 지정 되어 있는지 확인 합니다. 
  
예
  
- VPN
    
- 연구원
    
  **예제 SQL 구문**
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

NetworkNameID 및 Networknameid 매개 변수는 필수 이며 NetworkType 매개 변수는 선택 사항 이지만 권장 되는 방법입니다.
  
### <a name="import-buildings"></a>건물 가져오기

건물을 가져오면 특정 정보를 작성할 수 있는 기능 (WiFi/유선을 사용 하는 경우에는 제작 별 통화 불량 등)이 제공 됩니다. 
  
> [!NOTE]
> 이 단계는 선택 사항 이지만 권장 됩니다. 
  
새 건물을 가져오기 전에 미리 정의 된 BuildingKey를 이미 확인 해야 합니다. 이 작업을 수행 하려면 현재 값을 식별 하는 "MAX (BuildingKey)를 선택 합니다." SQL 명령을 실행 하 고 결과에 1을 추가 합니다.
  
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

BuildingKey, BuildingName, BuildingShortName, 소유자, BuildingTypeId 매개 변수가 필요한 경우 다른 매개 변수는 선택 사항입니다.
  
### <a name="import-subnets"></a>가져오기 서브넷

건물을 가져오면 특정 정보를 작성할 수 있는 기능 (WiFi/유선을 사용 하는 경우에는 제작 별 통화 불량 등)이 제공 됩니다. 
  
> [!NOTE]
> 이 단계는 선택 사항 이지만 권장 됩니다. 
  
서브넷을 가져와서 마지막 단계에서 가져온 건물에 매핑합니다. NetworkName을 채우지 않기로 결정 한 경우이 테이블의 각 항목은 Networkname 0을 사용 하는지 확인 합니다.
  
 **예제 SQL 구문**
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

Network 및 UpdatedDate 매개 변수가 필요한 경우 다른 매개 변수는 선택 사항입니다.
  
### <a name="optional-bssid"></a>선택 사항: BSSID

BSSID 정보를 채우면 컨트롤러 또는 라디오에 의해 추가 WiFi stream 상관 관계가 제공 됩니다. 이는 건물이 나 subnet을 기준으로 필터링 하는 것 외에도 있습니다. 
  
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

|**CQD와 같이**|**CQDBssid 테이블**|**예제 입력**|
|:-----|:-----|:-----|
|Ap NName  <br/> |MUX  <br/> |AP1  <br/> |
|BBssid  <br/> |유형이  <br/> |00-00-00-00-00-00 (구분 된 fformat을 사용 해야 함)  <br/> |
|컨트롤러  <br/> |건설  <br/> |아루바 AP 7  <br/> |
|디바이스  <br/> |ess  <br/> |Controller1  <br/> |
|휴대폰  <br/> |phy  <br/> |bgn  <br/> |
   
### <a name="processing-the-imported-data"></a>가져온 데이터 처리

기본적으로 건물/네트워크 데이터를 가져온 후에는 해당 시점 이후에 생성 된 레코드에만 적용 됩니다. 
  
위의 모든 레코드에이 새 데이터로 태그를 표시 하려면 아래와 같이 CqdUpdateBuilding 저장 프로시저를 실행 해야 합니다. 
  
첫 번째 레코드의 날짜를 지정 합니다 (Select MIN (StartTime) FROM Cqdpartition Edstreamview SQL 명령을 사용 하는 경우), 내일 EndDate, 마지막 두 값에 대해 NULL을 식별 합니다.
  
데이터가 stream 데이터와 연결 되 면 SSIS 큐브가 모든 레코드를 다시 처리 해야 합니다. 이는 BSSID/ISP 데이터를 대량 추가할 때에도 적용 됩니다. "전체 처리"가 선택 되어 있는지 확인 합니다.
  

