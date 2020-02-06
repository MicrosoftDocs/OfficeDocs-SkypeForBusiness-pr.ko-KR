---
title: 비즈니스용 Skype 서버 2019에 대 한 시스템 요구 사항
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: 요약:이 항목을 사용 하 여 비즈니스용 Skype 서버 2019 서버 및 도메인 인프라를 준비 합니다. 서버 팜을 성공적으로 설치 및 배포 하는 데 도움이 되도록 하드웨어, OS, 데이터베이스, 소프트웨어, 모든 시스템 요구 사항, Active Directory 정보 등이 여기에 포함 됩니다.
ms.openlocfilehash: c6f30ad4caa8dcb31cf035c3f82de4ab87c41f3d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812596"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019에 대 한 시스템 요구 사항
 
**요약:** 이 주제를 사용 하 여 비즈니스용 Skype 서버 2019을 설치할 준비를 합니다. 여기에는 하드웨어, OS, 소프트웨어, 데이터베이스, 인증서, 활성,, Ory, DNS 및 fileshares 포함 됩니다. 서버 팜을 성공적으로 설치 및 배포 하는 데 도움이 되는 모든 시스템 요구 사항 및 권장 사항이 여기에 나와 있습니다.
  
예상 대로 비즈니스용 Skype 서버 2019에 대 한 배포를 시작 하기 전에 몇 가지 준비를 수행 해야 할 수 있습니다. 이 문서에서는 다음에 대 한 계획을 안내 합니다.
  
- [하드웨어](system-requirements.md#Hardware)
  
- [운영 체제](system-requirements.md#OS)
  
- [소프트웨어](system-requirements.md#Software)

- [백 엔드 SQL 데이터베이스](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [DNS (Domain Name System)](system-requirements.md#DNS)
  
- [인증](system-requirements.md#Certs)
  
- [파일 공유](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019의 하드웨어
<a name="Hardware"> </a>

토폴로지가 종료 된 후 (그렇지 않은 경우 [비즈니스용 Skype Server 2019 항목에 대 한 토폴로지 기본 사항](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) 확인), 서버에 대해 고려해 야 할 때가 있습니다. 비즈니스용 Skype Server 2019 서버에는 64 비트 하드웨어가 필요 합니다. 하드웨어에 대 한 권장 사항은 아래에 있습니다. 이러한 요구 사항은 필요 하지 않지만 최적의 성능에 필요한 요구 사항을 반영 합니다. 이 문서에는 사용자의 상황에 따라 이러한 작업을 수행 해야 하는지 결정 하는 데 도움이 되는 용량 계획 설명서가 있습니다.
  
Standard Edition 서버용 권장 하드웨어:

|**하드웨어 구성 요소**|**권장**|
|:-----|:-----|
|%  <br/> |인텔 제온 E5-2673 v3 듀얼 프로세서, 6-코어, 2.4 ghz 이상.  <br/> 인텔 아이테니엄 프로세서는 비즈니스용 Skype 서버 2019 역할에 지원 되지 않습니다.  <br/> |
|Memory  <br/> |32 기가바이트 (GB).  <br/> |
|공간  <br/> |어떤  <br/> • 최소 72 GB의 무료 디스크 공간을 제공 하는 8 개 이상의 1만 RPM (raid 10을 사용 하는 RAID 1 및 6을 사용 하는 두 개의 디스크)  <br/> 또는  <br/> • Ssd (고체 드라이브)는 8 1만 RPM 기계적 디스크 드라이브에 동일한 여유 공간 및 유사한 성능을 제공할 수 있습니다.  <br/> |
|네트워크  <br/> |1 Gbps 이상의 듀얼 포트 네트워크 어댑터 (2 개의 네트워크 어댑터를 사용할 수 있지만 단일 MAC 주소 및 단일 IP 주소로 팀에 있어야 함).  <br/> 프런트 엔드 서버, 백 엔드 서버 및 Standard Edition 서버에서는 듀얼 또는 멀티홈 구성이 지원 **되지 않습니다** . <br/> 운영 체제에 표시 되지 않고 서버 하드웨어를 모니터링 하 고 관리 하는 데 사용 되는 동안에는 DRAC 또는 ILO와 같은 대역외 관리 시스템을 사용할 수 있습니다. 이 시나리오는 멀티홈 서버를 구성 하지 않으며 지원 됩니다.  <br/> |


프런트 엔드 서버 및 백 엔드 서버에 권장 되는 하드웨어:
  
|**하드웨어 구성 요소**|**권장**|
|:-----|:-----|
|%  <br/> |인텔 제온 E5-2673 v3 듀얼 프로세서, 6-코어, 2.4 ghz 이상. <br/> 인텔 아이테니엄 프로세서는 비즈니스용 Skype 서버 2019 역할에 지원 되지 않습니다.  <br/> |
|Memory  <br/> |64 기가바이트 (GB).  <br/> |
|공간  <br/> |어떤  <br/> • 최소 72 GB의 무료 디스크 공간을 제공 하는 8 개 이상의 1만 RPM (raid 10을 사용 하는 RAID 1 및 6을 사용 하는 두 개의 디스크)  <br/> 또는  <br/> • Ssd (고체 드라이브)는 8 1만 RPM 기계적 디스크 드라이브에 동일한 여유 공간 및 유사한 성능을 제공할 수 있습니다.  <br/> |
|네트워크  <br/> |1 Gbps 이상의 듀얼 포트 네트워크 어댑터 (2 개의 네트워크 어댑터를 사용할 수 있지만 단일 MAC 주소 및 단일 IP 주소로 팀에 있어야 함).  <br/> 프런트 엔드 서버, 백 엔드 서버 및 Standard Edition 서버에서는 듀얼 또는 멀티홈 구성이 지원 **되지 않습니다** . <br/> 운영 체제에 표시 되지 않고 서버 하드웨어를 모니터링 하 고 관리 하는 데 사용 되는 동안에는 DRAC 또는 ILO와 같은 대역외 관리 시스템을 사용할 수 있습니다. 이 시나리오는 멀티홈 서버를 구성 하지 않으며 지원 됩니다.  <br/> |
   
Edge 서버, 독립형 중재 서버, 디렉터에 권장 되는 하드웨어:
  
|**하드웨어 구성 요소**|**권장**|
|:-----|:-----|
|%  <br/> |인텔 제온 E5-2673 v3 듀얼 프로세서, 6-코어, 2.4 ghz 이상.  <br/> 인텔 아이테니엄 프로세서는 비즈니스용 Skype 서버 2019 역할에 지원 되지 않습니다.  <br/> |
|Memory  <br/> |32 기가바이트.  <br/> |
|공간  <br/> |어떤  <br/> • 최소 72 GB의 무료 디스크 공간을 제공 하는 4 개 이상의 1만 RPM 하드 디스크 드라이브 (디스크가 2 배로 RAID 1 구성 되어 있어야 함).  <br/> 또는  <br/> • Ssd (고체 드라이브)는 4 1만 RPM 기계적 디스크 드라이브에 동일한 여유 공간 및 유사한 성능을 제공할 수 있습니다.  <br/> |
|네트워크  <br/> |1 Gbps 이상의 듀얼 포트 네트워크 어댑터 (2 개의 네트워크 어댑터를 사용할 수 있지만 단일 MAC 주소 및 단일 IP 주소로 팀에 있어야 함).  <br/> 듀얼 또는 멀티홈 구성은 비디오 Interop 서버 및 디렉터에 대해 지원 **되지 않습니다** . <br/> Edge 서버에는 이중 포트 네트워크 어댑터용 1 Gbps 이상 (또는 두 개의 연결 된 네트워크 어댑터와 총 4 개, 단일 MAC 주소와 단일 IP 주소로 그룹화 된 각 쌍 중 총 2 쌍) 인 2 개의 네트워크 인터페이스가 필요 합니다.  <br/> 독립 실행형 중재 서버에서 특정 PSTN IP 주소의 구성을 허용 하는 추가 Nic (네트워크 인터페이스 카드) 설치가 지원 됩니다.  <br/> |


> [!NOTE]
> 서버 역할에 관계 없이 비즈니스용 Skype Server 2019에 대해 다음 하드웨어 설정을 권장 합니다 (이는 구매한 하드웨어 브랜드에 따라 달라질 수 있음). 자세한 내용은 제조업체 설명서를 참조 하세요.
> - BIOS 구성-NUMA에서 FLAT로 설정 해야 합니다.
> - 하이퍼스레딩을 활성화 합니다.
> - RSS 큐 설정은 큐에서 8 개로 설정 해야 합니다.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>비즈니스용 Skype Server 2019의 운영 체제
<a name="OS"> </a>

하드웨어를 설치한 후에는 비즈니스용 Skype 서버 2019을 설치 하 고 성공적으로 사용할 수 있도록 하는 OS (설치 운영 체제)가 필요 합니다.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
여기에 나열 된 운영 체제 이외의 다른 항목은 제대로 작동 하지 않습니다. 비즈니스용 Skype 서버 2019 설치에 대해 사용해 보세요. 예를 들어 Server Core 옵션이 나열 되지 않으며, 따라서 지원 되지 않습니다.  참고: OS의 현재 위치 업그레이드는 Lync Server 2013에서 지원 되지 않습니다.  다른 OS를 사용 하 여 별도의 풀을 배포 하 고 새 풀로 사용자를 마이그레이션해야 합니다.

> [!NOTE]
> 
> Windows Server 2019 컴퓨터에 Windows 관리 센터 2019을 설치 하는 경우 수신 대기할 포트를 입력 하 라는 메시지가 표시 됩니다. 포트 443을 선택할 수 있는 liklihood, 해당 컴퓨터에 비즈니스용 Skype Server 2019이 설치 되어 있거나 비즈니스용 Skype 서버 2019이 설치 되어 있는 경우에는 다른 포트 번호를 선택 해야 합니다.
> 
>이런 경우는 무엇 인가요? Windows 관리 센터 2019이 포트 443에서 실행 되 고 있는 경우 비즈니스용 Skype 제어판을 사용 하 여 서버에 연결할 수 없으며, 서버에서 실행 되는 내부 웹 서비스 (주소록 웹 서비스)에 연결할 수 없게 됩니다. , 자동 검색 서비스, WebTicket 서비스 등).  사실 내부 웹 서비스 URL에는 연결할 수 없습니다. 필요한 이벤트에서 다른 포트를 선택 하거나 비즈니스용 Skype Server 2019를 사용 하 여 Windows 관리 센터 2019를 서버에 배치 합니다.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>비즈니스용 Skype Server 2019 배포 전에 설치 해야 하는 소프트웨어
<a name="Software"> </a>

비즈니스용 Skype 서버 2019을 실행 하는 모든 서버에 설치 하거나 구성 해야 할 몇 가지 사항이 있습니다. 다음 목록에는 특정 서버 역할에 대 한 추가 요구 사항이 포함 되어 있습니다.

> [!IMPORTANT]
> 비즈니스용 Skype 2019는 .Net Framework 4.8를 지원 합니다. 
  
 **모든 서버:**
  
|**소프트웨어/역할**|**세부적인**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |모든 비즈니스용 Skype 서버 서버에는 Windows PowerShell 3.0가 설치 되어 있어야 합니다.  <br/> • 기본적으로 Windows Server 2016에 설치 되어 있어야 합니다.<br/> |
|Microsoft .NET Framework  <br/> |WCF 서비스는 Windows 기능으로 설치 된 **기능** 으로, **서버 관리자**에는 처음에 다운로드가 필요 하지 않습니다. <br/> •이 기능을 설치 하거나, 이미 설치 되어 있고, 검사 하는 경우에는 다음과 같이 **HTTP 활성화** 옵션도 선택 되어 설치 되어 있는지 확인 해야 합니다. <br/> ![.NET Framework 4.5 기능 아래에서 HTTP 활성화 옵션을 보여 주는 스크린샷](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> HTTP 정품 인증을 설치 하기 위해 다른 항목을 설치 해야 하는 추가 팝업이 표시 되는 경우 걱정 하지 마세요. 그 게 평소입니다. 확인을 클릭 하 고 계속 진행 합니다. 이 팝업이 표시 되지 않는 경우 해당 항목이 이미 설치 되어 있는 것으로 간주할 수 있습니다.  <br/> Microsoft .NET Framework는 일반적으로 Windows Server 2016이 설치 되어 있는 경우에 설치 됩니다. 비즈니스용 Skype Server에는 Microsoft .NET Framework 4.7 또는 4.8이 필요 하므로이를 업데이트 해야 할 것입니다. [여기](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/) 에서 업데이트를 찾을 수 있습니다.<br/> |
|미디어 파운데이션  <br/> |Windows Server 2016의 경우 Windows Media 형식 런타임이 Microsoft 미디어 파운데이션을 사용 하 여 설치 됩니다.  <br/> 회의에 사용 되는 모든 프런트 엔드 서버와 Standard Edition 서버는 Windows Media 형식 런타임을 통해 통화 공원, 알림 및 응답 그룹 응용 프로그램이 공지 사항 및 음악에 대해 재생 하는 Windows Media 오디오 (.wma) 파일을 실행 해야 합니다.  <br/> |
|Windows Identity Foundation  <br/> |비즈니스용 Skype Server 2019에 대 한 서버 간 인증 시나리오를 지원 하려면 Windows Identity Foundation 3.5이 필요 합니다.  <br/> • Windows Server 2016의 경우 아무 것도 다운로드할 필요가 없습니다. **서버 관리자**를 열고 **역할 및 기능 추가 마법사**로 이동 합니다. **Windows Id 파운데이션 3.5** 이 **기능** 섹션 아래에 나열 됩니다. 선택 되어 있는 경우에는 좋은 방법입니다. 그렇지 않으면 선택 하 고 **다음** 을 클릭 하 여 **설치** 단추에 도달 합니다. <br/> |
|원격 서버 관리 도구  <br/> |역할 관리 도구: AD DS 및 AD LDS 도구  <br/> |
   
 **프런트 엔드 서버와 스탠더드 버전 서버에도 다음이 필요 합니다.**
  
|**소프트웨어/역할**|**세부적인**|
|:-----|:-----|
|IIS (인터넷 정보 서비스)  <br/> |모든 프런트 엔드 서버와 모든 Standard Edition 서버에는 IIS가 필요 하며 다음 모듈이 선택 되어 있습니다.  <br/> • 일반적인 HTTP 기능: 기본 문서, HTTP 오류, 정적 콘텐츠  <br/> • 상태 및 진단: HTTP 로깅, 로깅 도구, 추적  <br/> • 성능: 정적 콘텐츠 압축, 동적 콘텐츠 압축  <br/> • 보안: 요청 필터링, 클라이언트 인증서 매핑 인증, Windows 인증  <br/> • 응용 프로그램 개발: .NET 확장성 3.5, .NET 확장성 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI 확장, ISAPI 필터  <br/> • 관리 도구: IIS 관리 콘솔, IIS 관리 스크립트 및 도구  <br/> 익명 액세스만 필요 하지만, IIS를 설치 하는 경우 목록에서 선택할 수 있는 위치가 없는 것을 볼 수 있습니다.  <br/> |
|Windows Media 형식 런타임  <br/> | Windows Server 2016의 경우 **서버 관리자**에서 **Media Foundation** 기능을 설치 해야 합니다. Skype for Business Server 2019 설치를이 없이 시작할 수 있지만,이를 설치 하 라는 메시지가 표시 되지만 비즈니스용 Skype Server 2019 설치를 계속 하기 전에 서버를 다시 부팅 해야 합니다. 미리 작업을 수행 하는 것이 좋습니다. <br/> |
|Silverlight  <br/> |최신 버전의 Silverlight를 [여기](https://www.microsoft.com/silverlight/)에 설치할 수 있습니다.  <br/> |
   
이를 돕기 위해 다음과 같은 샘플 PowerShell 스크립트를 실행 하 여이를 자동화할 수 있습니다.
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

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
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019에서 작동 하는 백 엔드 데이터베이스
<a name="DBs"> </a>

비즈니스용 Skype Server 2019 Standard Edition을 설치 하는 경우 SQL Server 2016 Express (64 비트 버전)가 제공 됩니다.

비즈니스용 Skype Server 2019 엔터프라이즈 에디션에는 아래 표시 된 것 처럼 전체 SQL Server가 필요 합니다 (64 비트 버전 에서만 32 비트 버전을 사용 하지 마세요).
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (64 비트 버전), 최신 업데이트를 사용 하 여 실행 해야 합니다.  <br/> |Microsoft SQL Server 2017 (64 비트 버전), 최신 업데이트를 사용 하 여 실행 해야 합니다.  <br/> |
Microsoft SQL Server 2016 (64 비트 버전), 최신 업데이트를 사용 하 여 실행 해야 합니다.|
 |

사용 하려는 SQL Server 버전이 여기에 나와 있지 않으면 사용할 수 없습니다.
  
> [!NOTE]
> 모니터링 서버 역할에 대 한 SQL Server Reporting Services도 설치 해야 합니다. 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL 클러스터링 및 SQL은 항상 켜져 있습니다.

비즈니스용 Skype 서버 2019에서 SQL 클러스터링이 지원 됩니다. Sql 클러스터링을 설정 하려는 경우에는 SQL Server에서 수행 됩니다.
  
지원 되는 SQL 클러스터링에 대 한 능동/수동 구성이 있는지 확인 합니다. 수동 노드를 다른 SQL 인스턴스와 공유 하지 마세요.
  
장애 조치 클러스터링용으로 사용할 수 있는 작업은 다음과 같습니다.
  
2 노드:
  
- Microsoft SQL Server 2019 Standard (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.
- Microsoft SQL Server 2017 Standard (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.
- Microsoft SQL Server 2016 Standard (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.

16 개 노드:
  
- Microsoft SQL Server 2019 Enterprise (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.
- Microsoft SQL Server 2017 Enterprise (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.
- Microsoft SQL Server 2016 Enterprise (64 비트 버전), 최신 서비스 팩으로 실행 하는 것이 좋습니다.

SQL은 항상 On으로 지원 되며 [백 엔드 서버에서 비즈니스용 Skype 서버 2019의](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)고가용성을 읽을 수 있습니다.
  

###  <a name="additional-server-installation-recommendations"></a>추가 서버 설치 권장 사항:
  
Microsoft 인터넷 보안 및 가속 (ISA) 서버 클라이언트 소프트웨어를 설치 하지 마세요. 또는 다른 모든 타사 방화벽 또는 바이러스 백신 네트워크 검사 소프트웨어를 여기에 포함 시킬 수 있습니다. 모든 프런트 엔드 서버 또는 독립 실행형 중재 서버 소프트웨어를 설치할 때 불량 미디어 소통량 성능이 표시 되었습니다.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

서버 및 서비스에 대 한 대부분의 구성 데이터는 비즈니스용 Skype 서버 2019 중앙 관리 저장소에 저장 되지만 Active Directory에 저장 된 몇 가지 사항이 남아 있습니다.
  
|**Active Directory 개체**|**개체 형식**|
|:-----|:-----|
|스키마 확장  <br/> |사용자 개체 확장  <br/> |
||이전 지원 버전과의 호환성을 유지 하기 위해 비즈니스용 Skype 서버 2015 및 Lync Server 2013의 확장 기능  <br/> |
|데이터  <br/> |사용자 SIP URI 및 기타 사용자 설정  <br/> |
||응용 프로그램 (예: 응답 그룹 응용 프로그램 및 회의 수행자 응용 프로그램)에 대 한 연락처 개체  <br/> |
||이전 버전과의 호환성을 위해 게시 된 데이터  <br/> |
||중앙 관리 저장소에 대 한 SCP (서비스 제어 지점)  <br/> |
||Kerberos 인증 계정 (선택적 컴퓨터 개체)  <br/> |
   
### <a name="os-for-domain-controllers"></a>도메인 컨트롤러용 OS

다음 도메인 컨트롤러 운영 체제를 사용할 수 있습니다.
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
비즈니스용 Skype Server 2019을 배포 하는 도메인의 도메인 기능 수준 및 비즈니스용 Skype Server 2019에 배포 하는 포리스트의 포리스트 기능 수준은 다음 중 하나 여야 합니다.
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
이러한 환경에서 읽기 전용 도메인 컨트롤러를 사용할 수 있나요? 사용할 수 있는 쓰기 가능한 도메인 컨트롤러도 있는 경우에만 가능 합니다.
  
비즈니스용 Skype 서버 2019는 단일 레이블 도메인을 지원 하지 않는다는 것을 알아야 합니다. 그 게 뭐 야? 루트 도메인에 contoso. local 이라는 레이블이 있는 경우이는 정상입니다. 로컬에 명명 된 루트 도메인이 있는 경우 해당 도메인은 작동 하지 않으며 결과적으로 지원 되지 않습니다. 이에 대 한 자세한 내용은 [이 기술 자료 문서를 참고](https://support.microsoft.com/kb/300684/)하세요.
  
비즈니스용 Skype 서버 2019도 도메인 이름 바꾸기를 지원 하지 않습니다. 도메인의 이름을 변경 해야 하는 경우에는 비즈니스용 Skype Server 2019을 제거 하 고, 도메인 이름 바꾸기를 수행 하 고, 비즈니스용 Skype Server 2019을 다시 설치 합니다.
  
마지막으로, 잠긴 AD DS 환경을 사용 하는 도메인을 다룰 수 있으며,이는 좋은 방법입니다. 배포 설명서의 잠겨진 AD DS 환경에 비즈니스용 Skype 서버 2019를 배포 하는 방법에 대 한 자세한 내용은 다음을 참조 하세요.
  
### <a name="ad-topologies"></a>광고 토폴로지

비즈니스용 Skype 서버 2019에서 지원 되는 토폴로지는 다음과 같습니다.
  
- 단일 도메인이 있는 단일 포리스트
    
- 단일 트리 및 여러 도메인이 있는 단일 포리스트
    
- 여러 트리 및 분리 네임 스페이스가 있는 단일 포리스트
    
- 중앙 포리스트 토폴로지의 여러 포리스트
    
- 리소스 포리스트 토폴로지의 여러 포리스트
    
- Exchange Online을 사용 하는 비즈니스용 Skype 리소스 포리스트 토폴로지에 있는 다중 포리스트
    
- 비즈니스용 Skype Online 및 Azure Active Directory Connect를 사용 하는 리소스 포리스트 토폴로지의 여러 포리스트
    
환경에서 사용 하는 토폴로지를 확인 하는 데 도움이 되는 다이어그램과 설명이 있거나 비즈니스용 Skype 서버 2019을 설치 하기 전에 설정 해야 할 수 있는 사항이 있습니다. 간단 하 게 유지 하기 위해 다음과 같은 키를 포함 하 고 있습니다.
  
![은 비즈니스용 Skype 토폴로지 다이어그램에 사용 되는 아이콘의 키입니다.](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>단일 도메인이 있는 단일 포리스트

![단일 도메인을 사용 하는 Active Directory 단일 포리스트 다이어그램](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
이는 보다 쉽게 사용할 수 있습니다. 단일 도메인 포리스트 인 공통 토폴로지입니다.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>단일 트리 및 여러 도메인이 있는 단일 포리스트

![단일 포리스트, 단일 트리 및 mutiple domains 다이어그램](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
이 다이어그램에는 하나의 포리스트가 다시 표시 되지만 하나 이상의 자식 도메인이 있는 경우 (이 특정 예제에는 3 개 있음) 따라서 사용자가 만들어지는 도메인은 비즈니스용 Skype 서버 2019이 배포 되는 도메인과 다를 수 있습니다. 이에 대해 걱정할 필요가 없는 경우 비즈니스용 Skype 서버 프런트 엔드 풀을 배포할 때는 해당 풀의 모든 서버가 단일 도메인에 있어야 한다는 점에 유의 해야 합니다. Windows 유니버설 관리자 그룹의 비즈니스용 Skype 서버 지원을 통해 도메인 간 관리를 할 수 있습니다.
  
위의 다이어그램에서는 한 도메인의 사용자가 하위 도메인에 있는 경우에도 동일한 도메인 또는 다른 도메인에서 비즈니스용 Skype 서버 풀에 액세스할 수 있음을 알 수 있습니다.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>여러 트리 및 분리 네임 스페이스가 있는 단일 포리스트

![단일 포리스트, 여러 트리 및 서로 떨어진 네임 스페이스 다이어그램](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
이 다이어그램과 유사한 토폴로지가 있는데,이는 포리스트 내에서 별도의 AD 네임 스페이스를 사용 하는 여러 도메인을 보유 하 고 있는 것입니다. 이 경우이 다이어그램은 비즈니스용 Skype 서버 2019에 액세스 하는 세 가지 도메인의 사용자를 포함 하기 때문에 좋은 그림입니다. 실선은 해당 도메인의 비즈니스용 Skype 서버 풀에 액세스 하 고 있음을 나타내고, 점선은 다른 트리의 풀로 진행 되 고 있음을 나타냅니다.
  
볼 수 있듯이 같은 도메인의 사용자, 같은 트리 또는 다른 트리로도 풀에 성공적으로 액세스할 수 있습니다.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>중앙 포리스트 토폴로지의 여러 포리스트

![중앙 포리스트 토폴로지 다이어그램의 다중 포리스트](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
비즈니스용 Skype 서버 2019는 중앙 포리스트 토폴로지에 구성 된 여러 포리스트를 지원 합니다. 보유 하 고 있는지 확실 하지 않은 경우 토폴로지에 있는 중앙 포리스트에서 다른 포리스트의 사용자를 나타내는 개체를 사용 하 고 포리스트의 모든 사용자에 대 한 사용자 계정을 호스팅합니다.
  
이 작업을 수행 하는 방법 디렉터리 동기화 제품 (예: Forefront Identity Manager 또는 FIM)은 자신의 존재에 대해 조직의 사용자 계정을 관리 합니다. 포리스트에서 계정이 만들어지거나 삭제 되 면 해당 변경 내용이 중앙 포리스트의 해당 연락처로 동기화 됩니다.
  
물론, 광고 인프라가 있는 경우이 토폴로지로 이동 하는 것이 쉽지 않을 수 있지만, 이미 있는 경우 또는 아직 포리스트 인프라를 계획 하 고 있는 경우에는 좋은 선택 일 수 있습니다. 단일 포리스트 내에서 비즈니스용 Skype 서버 2019 배포를 중앙 집중화할 수 있지만, 사용자는 모든 포리스트에서 다른 사용자가 검색, 통신 및 현재 상태를 볼 수 있습니다. 모든 사용자 연락처 업데이트는 동기화 소프트웨어와 함께 자동으로 처리 됩니다.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>비즈니스용 Skype 리소스 포리스트 토폴로지에 있는 다중 포리스트
<a name="BKMK_multipleforestopology"> </a>

![리소스 포리스트 토폴로지 다이어그램의 여러 포리스트](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
또한 리소스 포리스트 토폴로지가 지원 됩니다. 이는 포리스트는 Microsoft Exchange Server 및 비즈니스용 Skype 서버 2019 등의 서버 응용 프로그램을 실행 하는 것을 전담 합니다. 또한이 리소스 포리스트는 활성 사용자 개체의 동기화 된 표현을 호스팅하며만 로그온 할 수 있는 사용자 계정은 호스팅합니다. 따라서 리소스 포리스트는 사용자 개체가 상주 하는 다른 포리스트의 공유 서비스 환경 이므로 리소스 포리스트와 포리스트 수준의 신뢰 관계를 갖습니다.
  
Exchange Server는 비즈니스용 Skype 서버 또는 다른 포리스트에 있는 동일한 리소스 포리스트에 배포할 수 있습니다.
  
이 유형의 토폴로지에서 비즈니스용 Skype 서버 2019을 배포 하려면 사용자 포리스트의 각 사용자 계정에 대해 사용 하지 않는 사용자 개체를 하나 만듭니다 (Microsoft Exchange Server가 이미 환경에 있는 경우에는이 작업을 수행할 수 있음). 그런 다음 디렉터리 동기화 도구 (예: Forefront Identity Manager 또는 FIM)가 있어야 수명 주기를 통해 사용자 계정을 관리할 수 있습니다.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Exchange Online을 사용 하는 비즈니스용 Skype 리소스 포리스트 토폴로지에 있는 다중 포리스트
<a name="BKMK_multipleforestopology"> </a>

이 토폴로지는 [비즈니스용 Skype 리소스 포리스트 토폴로지에 있는 여러 포리스트에](system-requirements.md#BKMK_multipleforestopology)설명 된 토폴로지와 유사 합니다.
  
이 토폴로지에서는 하나 이상의 사용자 포리스트가 있고 비즈니스용 Skype 서버는 전용 리소스 포리스트에 배포 됩니다. Exchange Server는 동일한 리소스 포리스트나 다른 포리스트에 온-프레미스로 배포 될 수 있으며 Exchange Online과 혼합 하 여 구성 하거나 전자 메일 서비스를 Exchange Online에서 온-프레미스 계정에 대해 독점적으로 제공할 수 있습니다. 이 토폴로지에 사용할 수 있는 다이어그램이 없습니다.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>비즈니스용 Skype Online 및 Azure Active Directory Connect를 사용 하는 리소스 포리스트 토폴로지의 여러 포리스트
<a name="BKMK_multipleforestopology"> </a>

![두 개의 AD 포리스트, 하나의 사용자 포리스트와 하나의 리소스 포리스트를 표시 합니다. 두 포리스트에 신뢰 관계가 있습니다. Azure AD Connect를 사용 하 여 Office 365와 동기화 됩니다. 모든 사용자가 Office 365를 통해 비즈니스용 Skype에 대해 사용 하도록 설정 됩니다.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
이 시나리오에는 리소스 포리스트 토폴로지가 있는 여러 포리스트가 온-프레미스입니다. Active Directory 포리스트 간에 완전 신뢰 관계가 있습니다. Azure Active Directory Connect 도구는 온-프레미스 사용자 포리스트와 Office 365 간의 계정을 동기화 하는 데 사용 됩니다.
  
 또한 조직에 Office 365이 있으며 [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) 를 사용 하 여 온-프레미스 계정을 office 365와 동기화 합니다. 비즈니스용 Skype를 사용 하도록 설정 된 사용자는 Office 365 및 비즈니스용 Skype Online을 통해 사용할 수 있습니다. 비즈니스용 Skype 서버는 온-프레미스에 배포 되어 있지 않습니다.
  
Single sign-on 인증은 사용자 포리스트에 있는 Active Directory Federation Services 팜에 의해 제공 됩니다.
  
이 시나리오에서는 exchange 온-프레미스, Exchange Online, 하이브리드 Exchange 솔루션을 배포 하거나 Exchange를 배포 하지 않는 것이 지원 됩니다. (다이어그램에는 Exchange 온-프레미스만 표시 되지만 다른 Exchange 솔루션도 완벽 하 게 지원 됩니다.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>하이브리드 비즈니스용 Skype를 사용 하는 리소스 포리스트 토폴로지의 여러 포리스트
<a name="BKMK_multipleforestopology"> </a>

이 시나리오에는 하나 이상의 온-프레미스 사용자 포리스트가 있고 비즈니스용 Skype는 전용 리소스 포리스트에 배포 되며 비즈니스용 Skype Online을 사용 하 여 하이브리드 모드로 구성 되어 있습니다. Exchange Server는 동일한 리소스 포리스트나 다른 포리스트에 있는 온-프레미스에 배포 될 수 있으며 Exchange Online과 하이브리드으로 구성 될 수 있습니다. 또는 온-프레미스 계정에 대해 Exchange Online에서 독점적으로 전자 메일 서비스를 제공할 수 있습니다.
  
자세한 내용은 [하이브리드 비즈니스용 Skype에 대 한 다중 포리스트 환경 구성을](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)참조 하세요.
  
## <a name="domain-name-system-dns"></a>DNS (Domain Name System)
<a name="DNS"> </a>

비즈니스용 Skype 서버 2019에는 다음과 같은 이유로 인해 DNS가 필요 합니다.
  
- DNS를 사용 하면 비즈니스용 Skype 서버 2019에서 내부 서버 또는 풀을 검색 하 고 서버 간 통신을 허용 합니다.
    
- DNS를 사용 하면 클라이언트 컴퓨터가 SIP 트랜잭션을 위해 사용 되는 프런트 엔드 풀 또는 Standard Edition 서버를 검색할 수 있습니다.
    
- 이러한 회의를 호스트 하는 서버와의 회의를 위한 간단한 Url을 연결 합니다.
    
- DNS를 통해 외부 사용자 및 클라이언트 컴퓨터는 사용자의 Edge 서버 또는 인스턴트 메시징 (IM) 이나 회의에 대 한 HTTP 역방향 프록시에 연결할 수 있습니다.
    
- 장치 업데이트 웹 서비스를 실행 하는 프런트 엔드 풀 또는 Standard Edition 서버에서 로그인 하지 않은 통합 커뮤니케이션 (UC) 장치를 통해 업데이트를 받고 로그를 보낼 수 있습니다.
    
- DNS를 사용 하면 모바일 클라이언트가 사용자가 수동으로 해당 장치 설정에 Url을 입력할 필요 없이 웹 서비스 리소스를 자동으로 검색할 수 있습니다.
    
- DNS 로드 균형 조정에 사용 됩니다.
    
비즈니스용 Skype 서버 2019는 다국어 도메인 이름 (IDNs)을 지원 하지 않는다는 점에 유의 해야 합니다.
  
또한 DNS의 모든 이름이 비즈니스용 Skype 서버 2019에서 사용 되는 모든 서버에 구성 된 컴퓨터 이름과 동일 하다는 것을 기억해 야 하는 것이 매우 중요 합니다. 특히, 환경에 짧은 이름을 사용할 수 없으며 토폴로지 작성기에 대 한 Fqdn이 있어야 합니다.
  
이는 이미 도메인에 가입 된 컴퓨터에 대해 논리적으로 사용 되지만 도메인에 가입 되어 있지 않은 Edge 서버를 사용 하는 경우에는 도메인 접미사가 없는 약식 이름이 기본 이름으로 표시 될 수 있습니다. DNS 또는 Edge 서버 또는 비즈니스용 Skype Server 2019 Server 또는 풀에 대 한 사례가 아닌지 확인 합니다.
  
유니코드 문자나 밑줄은 사용 하지 않습니다. 표준 문자 (A-z, a-z, 0-9 및 하이픈)는 외부 DNS 및 공개 인증 기관에서 지원 되며 (인증서의 SN에 Fqdn을 할당 해야 함), 사용자가 이름을 입력할 때 많은 문제가 발생할 수 있습니다. 시작부터이 점을 염두에 두어야 합니다.
  
네트워킹 DNS 요구 사항에 대 한 자세한 내용은 계획 설명서의 [네트워킹](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) 섹션을 참조 하세요.
  
## <a name="certificates"></a>인증
<a name="Certs"> </a>

배포 하기 전에 수행할 수 있는 가장 중요 한 작업 중 하나는 인증서가 순서 대로 되어 있는지 확인 하는 것입니다. 비즈니스용 Skype 서버 2019에는 TLS (전송 계층 보안) 및 MTLS (상호 전송 계층 보안) 연결을 위한 PKI (공개 키 인프라)가 필요 합니다. 기본적으로 표준화 된 방식으로 통신 하기 위해 비즈니스용 Skype 서버는 Ca (인증 기관)에서 발급 하는 인증서를 사용 합니다.
  
다음은 비즈니스용 Skype 서버 2019에서 인증서를 사용 하는 몇 가지 사항입니다.
  
- 클라이언트와 서버 간의 TLS 연결
    
- 서버 간 MTLS 연결
    
- 파트너의 자동 DNS 검색을 사용 하는 페더레이션
    
- IM (인스턴트 메시징)에 대 한 원격 사용자 액세스
    
- 오디오/비디오 (AV) 세션, 응용 프로그램 공유, 회의에 대 한 외부 사용자 액세스
    
- 웹 응용 프로그램 및 OWA (Outlook Web Access)로 말하기
    
따라서 인증서 계획은 반드시 필요 합니다. 이제 인증서를 요청할 때 염두에 두어야 할 몇 가지 사항에 대해 살펴보겠습니다.
  
- 모든 서버 인증서는 서버 권한 부여 (서버 EKU)를 지원 해야 합니다.
    
- 모든 서버 인증서에는 CDP (CRL 배포 지점이)가 포함 되어 있어야 합니다.
    
- 모든 인증서는 운영 체제에서 지원 되는 서명 알고리즘을 사용 하 여 서명 해야 합니다. 비즈니스용 Skype 서버 2019는 다이제스트 크기의 SHA-1 및 SHA-2 제품군 (224, 256, 384, 512 비트)을 지원 하 고 운영 체제 요구 사항을 충족 하거나 초과 합니다.
    
- 자동 등록은 비즈니스용 Skype Server 2019을 실행 하는 내부 서버에 대해 지원 됩니다.
    
- 자동 등록은 비즈니스용 Skype 서버 2019 Edge 서버에서 지원 되지 않습니다.
    
> [!NOTE]
> RSASSA 서명 알고리즘을 사용 하는 것은 지원 되지 않으며,이 경우 로그인 및 착신 전환 문제에 대 한 오류가 발생할 수 있습니다 (다른 여러 가지 문제). 
  
- 1024, 2048, 4096의 암호화 키 길이가 지원 됩니다. 2048 이상의 키 길이를 권장 합니다.
    
- 기본 다이제스트 또는 해시 서명 알고리즘은 RSA입니다. 또한 ECDH_P256, ECDH_P384 및 ECDH_P521 알고리즘이 지원 됩니다.
    
이것은 생각 하는 것이 많고, CA에서 인증서를 요청 하는 다양 한 편안 함이 있습니다. 다음의 몇 가지 추가 지침을 사용 하 여 계획을 최대한 쉽게 파악할 수 있습니다.
  
### <a name="certificates-for-your-internal-servers"></a>내부 서버용 인증서

대부분의 내부 서버에 대 한 인증서가 필요 하며,이는 내부 CA (도메인에 있는 CA)에서 얻을 수 있습니다. 필요한 경우 외부 CA (인터넷에 있음)에서 인증서를 요청할 수 있습니다. 어떤 공용 CA를 사용할 것인지 궁금할 경우 [통합 커뮤니케이션 인증서 파트너](/SkypeForBusiness/certification/services-ssl) 목록을 확인해 보세요.
  
또한 비즈니스용 Skype 서버 2019가 Microsoft Exchange Server와 같은 다른 응용 프로그램 및 서버와 통신 하는 경우에도 인증서가 필요 합니다. 이는 다른 앱과 서버에서 지원 되는 방식으로 사용할 수 있는 인증서 일 것입니다. 비즈니스용 Skype 서버 2019 및 기타 Microsoft 제품은 서버 간 인증 및 권한 부여를 위한 개방형 인증 (OAuth) 프로토콜을 지원 합니다. 이에 관심이 있는 경우 OAuth 및 비즈니스용 Skype Server 2019에 대 한 추가 계획 문서를 사용 하 고 있습니다.
  
비즈니스용 Skype 서버 2019에는 SHA-256 암호화 해시 함수를 사용 하 여 서명 된 인증서도 지원 됩니다. SHA-256를 사용 하 여 외부 액세스를 지원 하려면 외부 인증서가 SHA-256를 사용 하 여 공용 CA에서 발급 되어야 합니다.
  
간단 하 게 사용할 수 있도록 표준 버전 서버, 프런트 엔드 풀 및 기타 역할에 대 한 인증서 요구 사항은 예제에 사용 되는 가공의 contoso.com를 사용 하 여 다음 테이블에 저장 합니다. 사용자 환경). 이러한 인증서는 모두 내보낼 수 없는 개인 키와 함께 표준 웹 서버입니다. 몇 가지 추가 참고 사항:
  
- 인증서 마법사를 사용 하 여 인증서를 요청할 때 서버 EKU (확장 키 사용)가 자동으로 구성 됩니다.
    
- 각 인증서 이름은 컴퓨터 스토어에서 고유 해야 합니다.
    
- 아래 샘플 이름에 따라 DNS에서 sipinternal.contoso.com 또는 sipexternal.contoso.com을 구성한 경우 인증서의 주체 대체 이름 (SAN)에 추가 해야 합니다.
    
Standard Edition 서버용 인증서:
  
|**인증**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|**메모**|
|:-----|:-----|:-----|:-----|:-----|
|기본값  <br/> |풀의 FQDN  <br/> |풀의 FQDN 및 서버의 FQDN  <br/> 여러 SIP 도메인이 있고 자동 클라이언트 구성을 사용 하도록 설정한 경우 인증서 마법사가 지원 되는 각 SIP 도메인 Fqdn을 감지 하 여 추가 합니다.  <br/> 이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 DNS (strict Domain Name System) 일치가 필요 하면 sipdomain (각 SIP 도메인에 대해)에 대 한 항목이 필요 합니다.  <br/> |SN = se01; SAN = se01  <br/> 이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 SAN = sip. m a c e;이 필요 합니다. SAN = sip. c a p  <br/> |스탠더드 버전의 서버에서 서버 FQDN은 풀 FQDN과 동일 합니다.  <br/> 마법사가 설치 중에 지정한 SIP 도메인을 감지 하 고 주체 대체 이름에 자동으로 추가 합니다.  <br/> 서버 간 인증에도이 인증서를 사용할 수 있습니다.  <br/> |
|웹 내부  <br/> |서버의 FQDN  <br/> |다음을 각각 수행 합니다.  <br/> • 서버의 FQDN과 동일한 내부 웹 FQDN  <br/> 이름과  <br/> • 간단한 Url 소개  <br/> • 전화 접속 간단한 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 간단한 Url의 와일드 카드 항목  <br/> |SN = se01; SAN = se01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c. SAN = 관리자. m a c  <br/> 와일드 카드 인증서 사용:  <br/> SN = se01; SAN = se01. SAN =\*. contoso.com  <br/> |토폴로지 작성기에서 내부 웹 FQDN을 재정의할 수 없습니다.  <br/> 여러 개의 단순 Url이 있는 경우에는 모든 것을 San으로 포함 해야 합니다.  <br/> 간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.  <br/> |
|웹 외부  <br/> |서버의 FQDN  <br/> |다음을 각각 수행 합니다.  <br/> • 외부 웹 FQDN  <br/> 이름과  <br/> • 전화 접속 간단한 URL  <br/> • SIP 도메인당 간단한 Url 소개  <br/> 또는  <br/> • 간단한 Url의 와일드 카드 항목  <br/> |SN = se01; SAN = webcon01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c  <br/> 와일드 카드 인증서 사용:  <br/> SN = se01; SAN = webcon01. SAN =\*. contoso.com  <br/> |여러 개의 단순 Url이 있는 경우 모든 항목을 제목 대체 이름으로 포함 해야 합니다.  <br/> 간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.  <br/> |
   
프런트 엔드 풀의 프런트 엔드 서버에 대 한 인증서:
  
|**인증**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|**메모**|
|:-----|:-----|:-----|:-----|:-----|
|기본값  <br/> |풀의 FQDN  <br/> |풀의 FQDN 및 서버의 FQDN  <br/> 여러 SIP 도메인이 있고 자동 클라이언트 구성을 사용 하도록 설정한 경우 인증서 마법사가 지원 되는 각 SIP 도메인 Fqdn을 감지 하 여 추가 합니다.  <br/> 이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 DNS (strict Domain Name System) 일치가 필요 하면 sipdomain (각 SIP 도메인에 대해)에 대 한 항목이 필요 합니다.  <br/> |SN = eepool. m a c. SAN = eepool. m a c. SAN = ee01  <br/> 이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 SAN = sip. m a c e;이 필요 합니다. SAN = sip. c a p  <br/> |마법사가 설치 중에 지정한 SIP 도메인을 감지 하 고 주체 대체 이름에 자동으로 추가 합니다.  <br/> 서버 간 인증에도이 인증서를 사용할 수 있습니다.  <br/> |
|웹 내부  <br/> |풀의 FQDN  <br/> |다음을 각각 수행 합니다.  <br/> • 내부 웹 FQDN (서버의 FQDN과 같지 않음)  <br/> • 서버 FQDN  <br/> • 비즈니스용 Skype 풀 FQDN  <br/> 이름과  <br/> • 간단한 Url 소개  <br/> • 전화 접속 간단한 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 간단한 Url의 와일드 카드 항목  <br/> |SN = ee01; SAN = ee01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c. SAN = 관리자. m a c  <br/> 와일드 카드 인증서 사용:  <br/> SN = ee01; SAN = ee01. SAN =\*. contoso.com  <br/> |여러 개의 단순 Url이 있는 경우 모든 항목을 제목 대체 이름으로 포함 해야 합니다.  <br/> 간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.  <br/> |
|웹 외부  <br/> |풀의 FQDN  <br/> |다음을 각각 수행 합니다.  <br/> • 외부 웹 FQDN  <br/> 이름과  <br/> • 전화 접속 간단한 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 간단한 Url의 와일드 카드 항목  <br/> |SN = ee01; SAN = webcon01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c  <br/> 와일드 카드 인증서 사용:  <br/> SN = ee01; SAN = webcon01. SAN =\*. contoso.com  <br/> |여러 개의 단순 Url이 있는 경우 모든 항목을 제목 대체 이름으로 포함 해야 합니다.  <br/> 간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.  <br/> |
   
디렉터에 대 한 인증서:
  
|**인증**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본값  <br/> |디렉터 풀  <br/> |디렉터의 FQDN, 디렉터 풀의 FQDN.  <br/> 이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 sipdomain (사용 하는 각 SIP 도메인)에 대해서도 항목이 필요 합니다.  <br/> |pool.contoso.com SAN = dir01  <br/> 이 디렉터 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 SAN = sip. m a m;이 필요 합니다. SAN = sip. c a p  <br/> |
|웹 내부  <br/> |서버의 FQDN  <br/> |다음을 각각 수행 합니다.  <br/> • 서버의 FQDN과 동일한 내부 웹 FQDN  <br/> • 서버 FQDN  <br/> • 비즈니스용 Skype 풀 FQDN  <br/> 이름과  <br/> • 간단한 Url 소개  <br/> • 전화 접속 간단한 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 간단한 Url의 와일드 카드 항목  <br/> |SN = dir01; SAN = dir01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c. SAN = 관리자. m a c  <br/> 와일드 카드 인증서 사용:  <br/> SN = dir01; SAN = dir01 SAN =\*. contoso.com  <br/> |
|웹 외부  <br/> |서버의 FQDN  <br/> |다음을 각각 수행 합니다.  <br/> • 외부 웹 FQDN  <br/> 이름과  <br/> • SIP 도메인당 간단한 Url 소개  <br/> • 전화 접속 간단한 URL  <br/> 또는  <br/> • 간단한 Url의 와일드 카드 항목  <br/> |디렉터 외부 웹 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버와 달라 야 합니다.  <br/> SN = dir01; SAN = directorwebcon01 SAN =. m a c. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c  <br/> 와일드 카드 인증서 사용:  <br/> SN = dir01; SAN = directorwebcon01 SAN =\*. contoso.com  <br/> |
   
독립 실행형 중재 서버용 인증서:
  
|**인증**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본값  <br/> |풀의 FQDN  <br/> |풀의 FQDN  <br/> 풀 구성원 서버의 FQDN  <br/> |SN = medsvr-pool.contoso.net SAN = medsvr-pool.contoso.net SAN = medsvr01  <br/> |
   
Survivable Branch 기기 인증서 (특히, 비즈니스용 Skype Server 2019에 대 한 Survivable Branch 기기 2015):
  
|**인증**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본값  <br/> |기기의 FQDN  <br/> |SIP. \<SIPDOMAIN\> (SIP 도메인당 하나의 항목만 필요 함)  <br/> |SN = sba01; SAN = sip. SAN = sip. c a p  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>외부 사용자 액세스 (Edge)의 인증서

비즈니스용 Skype 서버 2019는 액세스 및 웹 회의에 지 외부 인터페이스에 대 한 **단일 공개 인증서** 와 edge 서버를 통해 제공 되는 a/V 인증 서비스를 모두 사용할 수 있도록 지원 합니다. Edge 내부 인터페이스는 일반적으로 내부 CA에서 발급 하는 개인 인증서를 사용 하지만, 원한다 면 신뢰할 수 있는 CA에서 공개 인증서를 사용할 수도 있습니다.
  
또한, 역방향 프록시 (RP)는 공용 인증서를 사용 하 고, RP에서 클라이언트로의 통신 및 https를 사용 하 여 HTTP (또는 더 정확 하 게 말하면 HTTP를 통해)를 내부 서버로 암호화 합니다.
  
### <a name="certificates-for-mobility"></a>이동성을 위한 인증서

모바일 클라이언트에 대 한 자동 검색을 지 원하는 이동성을 배포 하는 경우 모바일 클라이언트의 보안 연결을 지원 하기 위해 인증서에 추가 주체 대체 이름 항목을 포함 해야 합니다.
  
다음 인증서에 대해 자동 검색에 대 한 SAN 이름이 필요 합니다.
  
- 디렉터 풀
    
- 프런트 엔드 풀
    
- 역방향 프록시
    
구체적인 내용은 아래 표에 나와 있습니다.
  
이는 사전 계획이 매우 좋은 방법 이지만, 이동성을 배포 하기 위해 의도 하지 않고 비즈니스용 Skype 서버 2019을 배포한 경우와 나중에 환경에 이미 인증서가 있는 경우에도이 문제가 발생 하는 경우가 여기에 해당 합니다. 내부 CA를 통해이를 재발급 하는 것은 일반적으로 매우 간단 하지만 공개 CA의 공개 인증서를 사용 하는 것이 더 pricy 수 있습니다.
  
원하는 결과를 찾고, 많은 SIP 도메인이 있는 경우 (SAN 추가 비용이 더 많이 들기 시작), HTTPS를 사용 하는 대신 초기 자동 검색 서비스 요청에 대해 HTTP를 사용 하도록 역방향 프록시를 구성할 수 있습니다 (기본 설정 구성). 이에 대 한 자세한 내용은 [이동성 계획](../../SfbServer/plan-your-deployment/mobility.md) 문서를 참조 하세요.
  
디렉터 풀 및 프런트 엔드 풀 인증서 요구 사항:
  
|**설명**|**SAN 항목**|
|:-----|:-----|
|내부 자동 검색 서비스 URL  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|외부 자동 검색 서비스 URL  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
또는 SAN =\*을 사용할 수도 있습니다. \<sipdomain\>
  
역방향 프록시 (공개 CA) 인증서 요구 사항:
  
|**설명**|**SAN 항목**|
|:-----|:-----|
|외부 자동 검색 서비스 URL  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
이 SAN은 역방향 프록시의 SSL 수신기에 할당 된 인증서에 할당 해야 합니다.
  
> [!NOTE]
> 역방향 프록시 수신기가 외부 웹 서비스 URL에 대 한 San을 보유 하 고 있습니다. 일부 예는 SAN = skypewebextpool01 및 dirwebexternal.contoso.com (디렉터를 배포한 경우)입니다 (선택 사항). 
  
## <a name="file-share"></a>파일 공유
<a name="Fileshare"> </a>

비즈니스용 Skype 서버 2019는 모든 파일 저장소에 동일한 파일 공유를 사용할 수 있습니다. 다음 사항을 염두에 두어야 합니다.
  
- 파일 공유는 DAS (직접 연결 저장소) 또는 SAN (저장소 영역 네트워크)에 있어야 하며, 여기에는 DFS (분산 파일 시스템)와 파일 저장소에 대 한 독립 디스크 (RAID)의 중복 배열이 포함 됩니다. Windows Server 2012의 DFS에서 더 읽기 위해서는 [이 DFS 페이지](https://technet.microsoft.com/library/jj127250.aspx)를 확인 하세요.
    
- 파일 공유에 대 한 공유 클러스터를 권장 합니다. 이미 계정을 사용 하 고 있는 경우에는 Windows Server 2012 이상 버전을 클러스터 해야 합니다.

> [!Note]
> **최신 Windows의 이유** 이전 버전에는 모든 기능을 사용 하도록 설정 하는 적절 한 권한이 없을 수 있습니다. 클러스터 관리자를 사용 하 여 파일 공유를 만들 수 있습니다. 자세한 내용은 [클러스터에서 파일 공유를 만드는 방법](https://support.microsoft.com/help/224967) 에 대 한이 지원 문서를 참조 하세요.
    
> [!CAUTION]
> 파일 공유로 NAS (네트워크 연결 저장소)를 사용 하는 것이 지원 되지 않으므로 위에 나열 된 옵션 중 하나를 사용 합니다. 이 지원 제한은 장치 공유 파일 시스템에 액세스 하는 Windows Server 기반 컴퓨터에 파일 시스템 적응성을 제공 해야 하는 NAS 디바이스의 변수 디자인 때문에 발생 합니다.
  








