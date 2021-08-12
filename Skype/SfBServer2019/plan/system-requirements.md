---
title: 2019년 비즈니스용 Skype 서버 시스템 요구 사항
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
description: '요약: 이 비즈니스용 Skype 서버 2019 서버 및 도메인 인프라를 준비합니다. 서버 팜을 성공적으로 설치 및 배포하는 데 도움이 되도록 하드웨어, OS, 데이터베이스, 소프트웨어, 모든 시스템 요구 사항 및 권장 사항과 인증서 DNS, 파일 공유 및 Active Directory 정보가 여기에 있습니다.'
ms.openlocfilehash: 3d7c8f4346ce0d965c9d9d87cc9fc124824f1d65f24cb7c05ef5d3aa58df1a07
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295985"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>2019년 비즈니스용 Skype 서버 시스템 요구 사항
 
**요약:** 이 항목과 비즈니스용 Skype 서버 2019 설치 준비 하드웨어, OS, 소프트웨어, 데이터베이스, 인증서, Active Diretory, DNS 및 파일 공유에 대해 다를 수 있습니다. 서버 팜을 성공적으로 설치 및 배포하는 데 도움이 되는 모든 시스템 요구 사항 및 권장 사항이 여기에 있습니다.
  
2019년 배포를 시작하기 전에 몇 가지 준비를 비즈니스용 Skype 서버 있습니다. 이 문서에서는 다음에 대한 계획을 세우는 것입니다.
  
- [하드웨어](system-requirements.md#Hardware)
  
- [운영 체제](system-requirements.md#OS)
  
- [소프트웨어](system-requirements.md#Software)

- [백 엔드 SQL 데이터베이스](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [도메인 이름 시스템(DNS)](system-requirements.md#DNS)
  
- [인증서](system-requirements.md#Certs)
  
- [파일 공유](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019용 하드웨어
<a name="Hardware"> </a>

토폴로지가 다운된 후(그렇지 않은 경우 [topology Basics for 비즈니스용 Skype 서버 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) 항목을 참조할 수 있습니다) 이제 서버에 대해 생각해 볼 시간입니다. 비즈니스용 Skype 서버 2019 서버에는 64비트 하드웨어가 필요합니다. 하드웨어에 대한 권장 사항은 아래와 같습니다. 이러한 요구 사항은 아니며 최적의 성능을 위해 필요한 요구 사항을 반영합니다. 상황에 따라 이보다 더 많은 요구가 필요한지 확인하는 데 도움이 되는 용량 계획 설명서가 있습니다.
  
서버의 Standard Edition 권장 하드웨어:

|**하드웨어 구성 요소**|**권장**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 듀얼 프로세서, 6코어, 2.4GHz 이상.  <br/> Intel Itanium 프로세서는 2019 2019 역할에 비즈니스용 Skype 서버 지원되지 않습니다.  <br/> |
|메모리  <br/> |32GB  <br/> |
|디스크  <br/> |둘 중 하나:  <br/> • 8개 이상의 10000 RPM 하드 디스크 드라이브(최소 72GB의 사용 공간 사용이 있는 디스크 2개(RAID 1을 사용하는 RAID 1 및 6을 사용하는 디스크 2개)  <br/> 또는  <br/> • 8개 10000 RPM 기계식 디스크 드라이브와 동일한 사용 공간 및 유사한 성능을 제공할 수 있는 솔리드 스테이트 드라이브(SDD)입니다.  <br/> |
|네트워크  <br/> |이중 포트 네트워크 어댑터 1개, 1Gbps 이상(2대의 네트워크 어댑터를 사용할 수 있지만 단일 MAC 주소와 단일 IP 주소로 팀을 구성해야 합니다.  <br/> 이중 또는 다중 홈 구성은 프런트 엔드 서버, 백 엔드 서버 및 Standard Edition 지원되지 않습니다.  <br/> 운영 체제에 노출되지 않는 한 서버 하드웨어를 모니터링하고 관리하는 데 사용되는 한 DRAC 또는 ILO와 같은 대역 외 관리 시스템이 있을 수 있습니다. 이 시나리오는 다중 홈 서버를 구성하지는 않습니다.  <br/> |


프런트 엔드 서버 및 백 엔드 서버에 권장되는 하드웨어:
  
|**하드웨어 구성 요소**|**권장**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 듀얼 프로세서, 6코어, 2.4GHz 이상. <br/> Intel Itanium 프로세서는 2019 2019 역할에 비즈니스용 Skype 서버 지원되지 않습니다.  <br/> |
|메모리  <br/> |64GB  <br/> |
|디스크  <br/> |둘 중 하나:  <br/> • 8개 이상의 10000 RPM 하드 디스크 드라이브(최소 72GB의 사용 공간 사용이 있는 디스크 2개(RAID 1을 사용하는 RAID 1 및 6을 사용하는 디스크 2개)  <br/> 또는  <br/> • 8개 10000 RPM 기계식 디스크 드라이브와 동일한 사용 공간 및 유사한 성능을 제공할 수 있는 솔리드 스테이트 드라이브(SDD)입니다.  <br/> |
|네트워크  <br/> |이중 포트 네트워크 어댑터 1개, 1Gbps 이상(2대의 네트워크 어댑터를 사용할 수 있지만 단일 MAC 주소와 단일 IP 주소로 팀을 구성해야 합니다.  <br/> 이중 또는 다중 홈 구성은 프런트 엔드 서버, 백 엔드 서버 및 Standard Edition 지원되지 않습니다.  <br/> 운영 체제에 노출되지 않는 한 서버 하드웨어를 모니터링하고 관리하는 데 사용되는 한 DRAC 또는 ILO와 같은 대역 외 관리 시스템이 있을 수 있습니다. 이 시나리오는 다중 홈 서버를 구성하지는 않습니다.  <br/> |
   
에지 서버, 독립 실행형 중재 서버 및 Director에 권장되는 하드웨어:
  
|**하드웨어 구성 요소**|**권장**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 듀얼 프로세서, 6코어, 2.4GHz 이상.  <br/> Intel Itanium 프로세서는 2019 2019 역할에 비즈니스용 Skype 서버 지원되지 않습니다.  <br/> |
|메모리  <br/> |32기가바이트  <br/> |
|디스크  <br/> |둘 중 하나:  <br/> • 4개 이상의 10000 RPM 하드 디스크 드라이브에 최소 72GB의 사용 공간이 있는 디스크 공간이 있습니다(디스크는 RAID 1 구성 2배).  <br/> 또는  <br/> • 4개 10000 RPM 기계식 디스크 드라이브와 동일한 사용 공간 및 유사한 성능을 제공할 수 있는 SDD(Solid State Drive)입니다.  <br/> |
|네트워크  <br/> |이중 포트 네트워크 어댑터 1개, 1Gbps 이상(2대의 네트워크 어댑터를 사용할 수 있지만 단일 MAC 주소와 단일 IP 주소로 팀을 구성해야 합니다.  <br/> 비디오 Interop 서버 및  Director에는 이중 또는 다중 홈 구성이 지원되지 않습니다. <br/> 에지 서버에는 이중 포트 네트워크 어댑터인 1Gbps 이상(또는 총 4개의 쌍으로 각 쌍이 단일 MAC 주소 및 단일 IP 주소로 팀을 이루는 총 2개의 쌍으로 구성되는 2개의 네트워크 어댑터)이 필요합니다.  <br/> 독립 실행형 중재 서버에서는 특정 PSTN IP 주소의 구성을 허용하는 추가 NI(네트워크 인터페이스 카드)의 설치가 지원됩니다.  <br/> |


> [!NOTE]
> 서버 역할에 관계없이 비즈니스용 Skype 서버 2019에 대해 다음 하드웨어 설정도 사용하는 것이 좋습니다(구입한 하드웨어 브랜드에 따라 다를 수 있으므로 자세한 내용은 제조업체 설명서를 참조하세요.
> - BIOS 구성 - NUMA에서 FLAT로 설정해야 합니다.
> - 하이퍼스레드를 사용하도록 설정
> - RSS 큐 설정은 8 큐로 설정해야 합니다.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>2019년 비즈니스용 Skype 서버 운영 체제
<a name="OS"> </a>

하드웨어를 설치한 후 2019에서 설치 및 성공적으로 사용할 수 있는 운영 체제(OS)를 설치해야 비즈니스용 Skype 서버 있습니다.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
여기에 나열된 운영 체제 외의 다른 운영 체제는 제대로 작동하지 않습니다. please don't try it for installs of 비즈니스용 Skype 서버. 예를 들어 Server Core 옵션은 나열되지 않습니다. 따라서 지원되지 않습니다.

> [!NOTE]
> Lync Server 2013에서 OS의 현재 현재 업그레이드가 지원되지 않습니다. 별도의 풀을 배포하고 다른 OS를 사용하여 사용자를 새 풀로 마이그레이션해야 합니다. 풀의 모든 서버에 동일한 OS 버전이 있어야 합니다.

> [!NOTE]
> 
> Windows Server 2019 컴퓨터에 Windows Admin Center 2019를 설치하는 경우 포트에서 수신할지 묻는 메시지가 표시됩니다. 포트 443을 선택할 수 있지만 해당 컴퓨터에 비즈니스용 Skype 서버 2019가 설치되어 있는 경우 또는 컴퓨터에 비즈니스용 Skype 서버 2019가 설치되어 있는 경우 다른 포트 번호를 선택해야 합니다.
> 
>그 이유는 무엇일까요? Windows 관리 센터 2019가 포트 443에서 실행되는 경우 비즈니스용 Skype 제어판을 사용하여 서버에 연결할 수 없으며 서버에서 실행되는 내부 웹 서비스(주소 예약 웹 서비스, 자동 검색 서비스, WebTicket 서비스 등)에 연결할 수도 없습니다.  실제로 내부 웹 서비스 URL에는 연결할 수 없습니다. 필요한 경우 또는 2019가 있는 서버에 Windows 관리 센터 2019를 비즈니스용 Skype 서버 포트를 선택하세요.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>2019년 배포 전에 설치해야 하는 비즈니스용 Skype 서버 소프트웨어
<a name="Software"> </a>

2019년 8월에 실행되는 모든 서버에 대해 몇 가지를 설치하거나 구성해야 비즈니스용 Skype 서버 있습니다. 이러한 요구 사항은 아래에 나와 있습니다. 그 다음에 특정 서버 역할에 대한 추가 요구 사항이 표시됩니다.

> [!IMPORTANT]
> Skype For Business 2019 supports .Net Framework 4.8. 
  
 **모든 서버:**
  
|**소프트웨어/역할**|**세부 정보**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |모든 비즈니스용 Skype 서버 3.0을 Windows PowerShell 서버가 필요합니다.  <br/> • 이 설정은 기본적으로 설치해야 Windows Server 2016.<br/> |
|Microsoft .NET Framework  <br/> |WCF 서비스는  서버 관리자에서 처음에 다운로드가 필요하지 Windows 기능으로 설치되는 기능입니다. <br/> • 이 기능을 설치할 때 또는 이 기능이 이미 설치되어 있으며 확인 중이면 **HTTP** 정품 인증 옵션도 확인하여 설치하는지 확인합니다. <br/> ![Screenshot showing HTTP Activation option under the .NET Framework 4.5 Features.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> HTTP 정품 인증을 설치하려면 몇 가지 다른 것을 설치해야 하다는 추가 팝업이 있는 경우 걱정하지 마세요. 정상입니다. 확인을 클릭하고 진행합니다. 이 팝업을 얻지 못하면 이미 설치된 것으로 가정하여 진행할 수 있습니다.  <br/> Microsoft .NET Framework 설치 시 일반적으로 Windows Server 2016 설치됩니다. 비즈니스용 Skype 서버 Microsoft .NET Framework 4.7 또는 4.8이 필요하기 때문에 업데이트해야 할 수 있습니다. 여기에서 업데이트를 찾을 [수 있습니다.](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)<br/> |
|미디어 파운데이션  <br/> |이 Windows Server 2016 경우 Windows 미디어 형식 런타임이 Microsoft 미디어 파운데이션과 함께 설치됩니다.  <br/> 회의에 사용되는 모든 프런트 엔드 서버 및 Standard Edition 서버는 통화 파킹, 공지 및 응답 그룹 응용 프로그램에서 공지 및 음악에 대해 재생하는 Windows 미디어 오디오(.wma) 파일을 실행하려면 Windows 미디어 형식 런타임이 필요합니다.  <br/> |
|Windows Identity Foundation  <br/> |2019에 Windows 서버 대 서버 인증 시나리오를 지원하려면 Identity Foundation 3.5를 비즈니스용 Skype 서버 필요합니다.  <br/> • Windows Server 2016 경우 아무것도 다운로드할 필요가 없습니다. 서버 **관리자를** 열고 역할 및 기능 추가 **마법사 로 이동하십시오.** Windows 섹션 아래에 **Identity Foundation 3.5가** **나열됩니다.** 선택한 경우 좋습니다. 그렇지 않으면 이 단추를 선택하고 **다음을** 클릭하여 설치 **단추에 도달합니다.** <br/> |
|원격 서버 관리 도구  <br/> |역할 관리 도구: AD DS 및 AD LDS 도구  <br/> |
   
 **프런트 엔드 서버 및 Standard Edition 서버에도 다음이 필요합니다.**
  
|**소프트웨어/역할**|**세부 정보**|
|:-----|:-----|
|IIS(인터넷 정보 서비스)  <br/> |다음 모듈이 선택된 모든 프런트 엔드 서버 및 모든 Standard Edition IIS가 필요합니다.  <br/> • 일반적인 HTTP 기능: 기본 문서, HTTP 오류, 정적 콘텐츠  <br/> • 상태 및 진단: HTTP 로깅, 로깅 도구, 추적  <br/> • 성능: 정적 콘텐츠 압축, 동적 콘텐츠 압축  <br/> • 보안: 요청 필터링, 클라이언트 인증서 매핑 인증, Windows 인증  <br/> • 응용 프로그램 개발: .NET 확장성 3.5, .NET 확장성 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI 확장, ISAPI 필터  <br/> • 관리 도구: IIS 관리 콘솔, IIS 관리 스크립트 및 도구  <br/> 익명 액세스도 필요하지만 IIS를 설치할 때 목록에 선택할 수 있는 장소가 없습니다.  <br/> |
|Windows Media 형식 런타임  <br/> | 이 Windows Server 2016 서버 관리자에 **미디어 파운데이션** 기능을 **설치해야 합니다.** 이 없이 비즈니스용 Skype 서버 2019 설치를 실제로 시작할 수 있지만 2019 설치가 계속되기 전에 설치를 요청한 다음 서버를 다시 비즈니스용 Skype 서버 합니다. 미리 작업을 하는 것이 좋습니다. <br/> |
|Silverlight  <br/> |여기에서 최신 버전의 Silverlight를 설치할 수 [있습니다.](https://www.microsoft.com/silverlight/)  <br/> |
   
이를 자동화하기 위해 실행할 수 있는 샘플 PowerShell 스크립트는 다음과 같습니다.
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 사용할 백 엔드 데이터베이스
<a name="DBs"> </a>

When installing 비즈니스용 Skype 서버 2019 Standard Edition, you'll have SQL Server 2016 Express (64-bit edition).

비즈니스용 Skype 서버 2019 Enterprise Edition 아래와 SQL Server 전체 버전이 필요하게 됩니다(64비트 버전만 해당합니다. 32비트 버전은 사용하지 말아야 합니다).
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019(64비트 버전) 최신 업데이트로 실행해야 합니다.  <br/> |Microsoft SQL Server 2017(64비트 버전) 최신 업데이트로 실행해야 합니다.  <br/> |
Microsoft SQL Server 2016(64비트 버전)을 설치하고 최신 업데이트로 실행해야 합니다.|
 |

여기에 사용하려는 SQL Server 버전이 없는 경우 사용할 수 없습니다.
  
> [!NOTE]
> 모니터링 서버 역할에 SQL Server Reporting Services 설치해야 합니다. 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL 클러스터링 및 SQL 항상 사용

SQL 2019를 비즈니스용 Skype 서버 클러스터링이 지원됩니다. 클러스터링을 설정하려는 SQL 클러스터링에서 SQL Server.
  
지원되는 클러스터링에 대한 활성/SQL 구성이 있는지 확인 수동 노드를 다른 SQL 않습니다.
  
장애 조치(failover) 클러스터링에 대해 다음을 사용할 수 있습니다.
  
두 노드:
  
- Microsoft SQL Server 2019 Standard(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.
- Microsoft SQL Server 2017 Standard(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.
- Microsoft SQL Server 2016 Standard(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.

16개 노드:
  
- Microsoft SQL Server 2019 Enterprise(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.
- Microsoft SQL Server 2017 Enterprise(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.
- Microsoft SQL Server 2016 Enterprise(64비트 버전) 최신 서비스 팩으로 실행하는 것이 좋습니다.

SQL Always On은 지원되는 기능으로, [2019년](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)8월의 백 엔드 서버 고가용성에서 비즈니스용 Skype 서버 있습니다.
  

###  <a name="additional-server-installation-recommendations"></a>추가 서버 설치 권장 사항:
  
모든 프런트 엔드 서버 또는 독립 실행형 중재 서버에 Microsoft ISA(Internet Security and Acceleration) 서버 클라이언트 소프트웨어 또는 기타 Winsock LSP(계층형 서비스 공급자) 소프트웨어(타사 방화벽 또는 바이러스 백신 네트워크 검사 소프트웨어가 여기에 포함됩니다.)를 설치하지 말아야 합니다. 소프트웨어가 설치되면 미디어 트래픽 성능이 나쁨으로 표시됩니다.
  

## <a name="active-directory"></a>PowerShell 연결
<a name="AD"> </a>

서버 및 서비스에 대한 구성 데이터 중 상당수는 비즈니스용 Skype 서버 2019 중앙 관리 저장소에 저장되어도 여전히 Active Directory에 몇 가지가 저장됩니다.
  
|**Active Directory 개체**|**개체 유형**|
|:-----|:-----|
|Schema extensions  <br/> |사용자 개체 확장  <br/> |
||지원되는 비즈니스용 Skype 서버 이전 버전과의 호환성을 유지하기 위한 비즈니스용 Skype 서버 2015 및 Lync Server 2013용 확장  <br/> |
|데이터  <br/> |사용자 SIP URI 및 기타 사용자 설정  <br/> |
||응용 프로그램의 연락처 개체(예: 응답 그룹 응용 프로그램 및 회의 도우미 애플리케이션)  <br/> |
||호환성을 위해 게시된 데이터  <br/> |
||중앙 관리 저장소의 SCP(서비스 제어 지점)  <br/> |
||Kerberos 인증 계정(선택적 컴퓨터 개체)  <br/> |
   
### <a name="os-for-domain-controllers"></a>도메인 컨트롤러용 OS

다음 도메인 컨트롤러 운영 체제를 사용할 수 있습니다.
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
비즈니스용 Skype 서버 2019에 배포하는 모든 도메인의 도메인 기능 수준과 비즈니스용 Skype 서버 2019에 배포하는 포리스트의 포리스트 기능 수준은 다음 중 하나되어야 합니다.
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
이러한 환경에 읽기 전용 도메인 컨트롤러가 있습니까? 사용 가능한 덮어 사용할 수 있는 도메인 컨트롤러도 있는 한
  
2019에서 단일 레이블이 비즈니스용 Skype 서버 지원하지 않는다는 점에 유의해야 합니다. 이 방법들은 무엇인가요? 루트 도메인에 contoso.local 레이블이 지정되어 있는 경우 괜찮습니다. 방금 로컬이라는 루트 도메인이 있는 경우 해당 도메인이 작동하지 않을 것이고 그 결과로 지원되지 않습니다. 이에 대한 자세한 내용은 이 기술 자료 문서 [에서 작성했습니다.](https://support.microsoft.com/kb/300684/)
  
비즈니스용 Skype 서버 2019에서도 도메인 이름 변경을 지원하지 않습니다. 실제로 도메인 이름을 변경해야 하는 경우 비즈니스용 Skype 서버 2019를 제거하고 도메인 이름을 바운 다음 2019년 2019년을 다시 비즈니스용 Skype 서버 합니다.
  
마지막으로 잠긴 AD DS 환경을 사용 중일 수 있으며 이는 당연한 일입니다. 배포 설명서의 잠긴 AD DS 환경에 비즈니스용 Skype 서버 2019를 배포하는 방법에 대한 자세한 정보가 있습니다.
  
### <a name="ad-topologies"></a>AD 토폴로지

2019년 비즈니스용 Skype 서버 지원되는 토폴로지:
  
- 도메인이 하나인 단일 포리스트
    
- 트리가 하나이고 도메인이 여러 개인 단일 포리스트
    
- 트리 여러 개와 연결되지 않은 네임스페이스가 포함된 단일 포리스트
    
- 중앙 포리스트 토폴로지의 다중 포리스트
    
- 리소스 포리스트 토폴로지의 다중 포리스트
    
- 포리스트가 있는 비즈니스용 Skype 리소스 포리스트 토폴로지의 여러 Exchange Online
    
- 리소스 포리스트 토폴로지의 여러 포리스트(비즈니스용 Skype Online 및 Azure Active Directory 커넥트
    
환경에 있는 토폴로지 또는 2019년 2019 설치 전에 설정해야 할 수 있는 토폴로지 결정에 도움이 되는 다이어그램 및 설명이 비즈니스용 Skype 서버 있습니다. 간단하게 유지하기 위해 키도 포함해야 합니다.
  
![은 토폴로지 다이어그램에 사용되는 아이콘의 비즈니스용 Skype 키입니다.](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>도메인이 하나인 단일 포리스트

![단일 도메인을 사용하는 Active Directory 단일 포리스트 다이어그램](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
이보다 더 쉬워진 것은 아니며, 단일 도메인 포리스트, 일반적인 토폴로지입니다.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>트리가 하나이고 도메인이 여러 개인 단일 포리스트

![단일 포리스트, 단일 트리 및 음소거 도메인 다이어그램](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
이 다이어그램은 단일 포리스트를 보여 주지만 하나 이상의 하위 도메인도 있습니다(이 특정 예에는 3개가 있습니다). 따라서 사용자가 만든 도메인은 2019가 배포된 도메인과 비즈니스용 Skype 서버 다를 수 있습니다. 왜 걱정할까요? 프런트 엔드 풀을 배포할 때 비즈니스용 Skype 서버 풀의 모든 서버는 단일 도메인에 있을 수 있습니다. 유니버설 관리자 그룹을 지원하지 비즈니스용 Skype 서버 도메인 간 관리가 Windows 있습니다.
  
위의 다이어그램에서는 한 도메인의 사용자가 동일한 도메인 또는 다른 도메인에서 비즈니스용 Skype 서버 풀에 액세스할 수 있습니다(해당 사용자가 하위 도메인에 있는 경우에도 마찬가지).
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>트리 여러 개와 연결되지 않은 네임스페이스가 포함된 단일 포리스트

![단일 포리스트, 여러 트리 및 불연속 네임스페이스 다이어그램](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
포리스트가 하나 있지만 해당 포리스트 내에 별도의 AD 네임스페이스가 있는 여러 도메인인 이 다이어그램과 유사한 토폴로지가 있을 수 있습니다. 이 다이어그램은 2019에 액세스하는 세 개의 서로 다른 도메인에 있는 비즈니스용 Skype 서버 그림입니다. 실선은 자신의 도메인에 있는 비즈니스용 Skype 서버 풀에 액세스하고 있는 반면, 대시선은 다른 트리의 풀로 모두 액세스하고 있는 것을 나타냅니다.
  
보시다시보시다시: 동일한 도메인, 동일한 트리 또는 다른 트리의 사용자가 풀에 성공적으로 액세스할 수 있습니다.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>중앙 포리스트 토폴로지의 다중 포리스트

![중앙 포리스트 토폴로지 다이어그램의 여러 포리스트](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
비즈니스용 Skype 서버 2019에서는 중앙 포리스트 토폴로지에서 구성된 여러 포리스트를 지원할 수 있습니다. 이러한 설정이 확실하지 않은 경우 토폴로지의 중앙 포리스트는 토폴로지의 개체를 사용하여 다른 포리스트의 사용자를 나타내고 포리스트의 모든 사용자에 대한 사용자 계정을 호스팅합니다.
  
이 방식은 어떻게 작동하나요? 디렉터리 동기화 제품(예: Forefront Identity Manager 또는 FIM)은 전체적으로 조직의 사용자 계정을 관리합니다. 포리스트에서 계정을 만들거나 삭제하면 해당 변경 내용은 중앙 포리스트의 해당 연락처로 동기화됩니다.
  
AD 인프라가 준비되어 있는 경우 이 토폴로지로 이동하는 것은 쉽지 않을 수 있지만 이미 있는 경우나 포리스트 인프라를 계획하는 경우 좋은 선택이 될 수 있습니다. 단일 포리스트 내에서 비즈니스용 Skype 서버 2019 배포를 중앙 집중화할 수 있으며, 사용자는 모든 포리스트에서 다른 사용자의 현재 상태를 검색, 통신 및 볼 수 있습니다. 모든 사용자 연락처 업데이트는 동기화 소프트웨어를 통해 자동으로 처리됩니다.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>단일 리소스 포리스트 토폴로지의 비즈니스용 Skype 포리스트
<a name="BKMK_multipleforestopology"> </a>

![리소스 포리스트 토폴로지 다이어그램의 여러 포리스트](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
리소스 포리스트 토폴로지도 지원됩니다. 여기서 포리스트는 2019 및 2019와 같은 서버 응용 프로그램 Microsoft Exchange Server 전용으로 비즈니스용 Skype 서버 있습니다. 또한 이 리소스 포리스트는 활성 사용자 개체의 동기화된 표현을 호스팅하지만 로그온 가능 사용자 계정은 호스팅하지 않습니다. 따라서 리소스 포리스트는 사용자 개체가 있는 다른 포리스트의 공유 서비스 환경으로, 리소스 포리스트와 포리스트 수준 트러스트 관계가 있습니다.
  
이 Exchange Server 포리스트와 동일한 리소스 포리스트 또는 다른 포리스트에 비즈니스용 Skype 서버 수 있습니다.
  
이 유형의 토폴로지에서 비즈니스용 Skype 서버 2019를 배포하려면 사용자 포리스트의 각 사용자 계정에 대해 리소스 포리스트에 사용되지 않도록 설정한 사용자 개체를 하나씩 만듭니다(Microsoft Exchange Server 환경에 이미 있는 경우 이 작업 수행이 수행될 수 있습니다). 그런 다음 수명 주기 동안 사용자 계정을 관리하기 위한 디렉터리 동기화 도구(예: Forefront Identity Manager 또는 FIM)가 필요합니다.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>포리스트가 있는 비즈니스용 Skype 리소스 포리스트 토폴로지의 여러 Exchange Online
<a name="BKMK_multipleforestopology"> </a>

이 토폴로지는 단일 리소스 포리스트 토폴로지의 여러 포리스트에 설명된 비즈니스용 Skype [비슷합니다.](system-requirements.md#BKMK_multipleforestopology)
  
이 토폴로지에는 하나 이상의 사용자 포리스트가 있으며 비즈니스용 Skype 서버 포리스트에 배포됩니다. Exchange Server 동일한 리소스 포리스트 또는 다른 포리스트에 사내에 배포하고 Exchange Online 하이브리드에 대해 구성할 수 있습니다. 또는 전자 메일 서비스는 Exchange Online 계정에 대해 단독으로 제공될 수 있습니다. 이 토폴로지에는 다이어그램을 사용할 수 없습니다.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>리소스 포리스트 토폴로지의 여러 포리스트(비즈니스용 Skype Online 및 Azure Active Directory 커넥트
<a name="BKMK_multipleforestopology"> </a>

![AD 포리스트 2개, 사용자 포리스트 1개 및 리소스 포리스트 1개가 표시 두 포리스트에는 트러스트 관계가 있습니다. Azure AD 계정을 사용하여 Microsoft 365 동기화 커넥트. 모든 사용자는 웹 응용 비즈니스용 Skype 사용할 수 Microsoft 365.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
이 시나리오에서는 리소스 포리스트 토폴로지가 있는 여러 포리스트가 사내에 있습니다. Active Directory 포리스트 간에는 전체 트러스트 관계가 있습니다. Azure Active Directory 커넥트 도구는 사내 사용자 포리스트와 사용자 포리스트 간에 계정을 동기화하는 데 Microsoft 365 Office 365.
  
 조직은 또한 Microsoft 365 또는 Office 365 사용하여 Azure Active Directory 커넥트 계정을 [](/azure/active-directory/connect/active-directory-aadconnect) Microsoft 365 또는 Office 365. 비즈니스용 Skype 사용할 수 있는 사용자는 Microsoft 365 또는 Office 365 비즈니스용 Skype 있습니다. 비즈니스용 Skype 서버 배포되지 않습니다.
  
Single Sign-On 인증은 사용자 포리스트에 있는 Active Directory Federation Services 팜에서 제공됩니다.
  
이 시나리오에서는 Exchange, Exchange Online, 하이브리드 Exchange 솔루션을 배포하거나 배포할 Exchange 지원됩니다. 이 다이어그램에는 온-프레미스 Exchange 표시하지만 다른 Exchange 솔루션도 완전히 지원됩니다.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>하이브리드 포리스트가 있는 리소스 포리스트 토폴로지의 여러 포리스트 비즈니스용 Skype
<a name="BKMK_multipleforestopology"> </a>

이 시나리오에는 하나 이상의 사내 사용자 포리스트가 있으며, 비즈니스용 Skype 전용 리소스 포리스트에 배포되어 비즈니스용 Skype Online을 통해 하이브리드 모드로 비즈니스용 Skype 있습니다. Exchange Server 동일한 리소스 포리스트 또는 다른 포리스트에 사내에 배포할 수 있으며 하이브리드 포리스트와 함께 구성할 Exchange Online. 또는 전자 메일 서비스를 단독으로 제공하면 Exchange Online 계정의 경우 전자 메일 서비스를 단독으로 사용할 수 있습니다.
  
자세한 내용은 [Configure a multi-forest environment for hybrid](../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)비즈니스용 Skype.
  
## <a name="domain-name-system-dns"></a>도메인 이름 시스템(DNS)
<a name="DNS"> </a>

비즈니스용 Skype 서버 2019에는 다음과 같은 이유로 DNS가 필요합니다.
  
- DNS를 비즈니스용 Skype 서버 2019에서 내부 서버 또는 풀을 검색하여 서버 간 통신을 허용합니다.
    
- DNS를 사용하면 클라이언트 컴퓨터는 SIP 트랜잭션에 사용되는 프런트 엔드 풀 또는 Standard Edition 서버를 검색할 수 있습니다.
    
- 이 URL은 회의의 단순 URL을 해당 회의를 호스팅하는 서버와 연결합니다.
    
- DNS를 사용하면 외부 사용자 및 클라이언트 컴퓨터를 IM(인스턴트 메시징) 또는 회의에 대해 에지 서버 또는 HTTP 역방향 프록시에 연결할 수 있습니다.
    
- 이 기능을 사용하면 로그인하지 않은 UC(통합 통신) 장치가 장치 업데이트 웹 서비스를 실행하는 프런트 엔드 풀 또는 Standard Edition 서버를 검색하여 업데이트를 다운로드하고 로그를 보낼 수 있습니다.
    
- DNS를 사용하면 모바일 클라이언트가 사용자가 장치 설정에 URL을 수동으로 입력하지 않고도 웹 서비스 리소스를 자동으로 검색할 수 있습니다.
    
- DNS 부하 분산에 사용됩니다.
    
2019년은 비즈니스용 SKYPE 서버(다국어 도메인 이름)를 지원하지 않는다는 점에 유의해야 합니다.
  
또한 DNS의 모든 이름은 2019년 8월에 사용되지 비즈니스용 Skype 서버 컴퓨터 이름과 동일합니다. 특히 환경에는 짧은 이름을 사용할 수 없습니다. 토폴로지 작성기용 FQDNS가 있어야 합니다.
  
이는 이미 도메인에 가입된 모든 컴퓨터에 논리적일 수 있지만 도메인에 가입되지 않은 에지 서버가 있는 경우 도메인 접미사 없이 짧은 이름의 기본값을 사용할 수 있습니다. 이러한 문제는 DNS 또는 에지 서버 또는 2019 서버 또는 비즈니스용 Skype 서버 2019 서버 또는 풀에 있는 것이 아닙니다.
  
유니코드 문자나 밑면을 사용하지 않는 것이 까다로우면 안 됩니다. 표준 문자(A-Z, a-z, 0-9 및 하이픈)는 외부 DNS 및 공용 인증 기관에서 지원됩니다(인증서의 SN에 FQDN을 할당해야 하며 기억해야 합니다.) 이 문제를 염두에 두면 시작부터 많은 문제를 겪게 됩니다.
  
네트워킹에 대한 DNS 요구 사항에 대한 자세한 내용은 계획 설명서의 [네트워킹](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) 섹션을 참조하세요.
  
## <a name="certificates"></a>인증서
<a name="Certs"> </a>

배포하기 전에 할 수 있는 가장 중요한 일 중 하나는 인증서가 순서대로 있는지를 확인한 것입니다. 비즈니스용 Skype 서버 2019에는 TLS(전송 계층 보안) 및 MTLS(상호 전송 계층 보안) 연결을 위한 PKI(공개 키 인프라)가 필요합니다. 기본적으로 표준화된 방식으로 안전하게 통신하기 위해 비즈니스용 SKYPE 서버 인증 기관(CAS)에서 발급한 인증서를 사용하게 됩니다.
  
다음은 2019에서 인증서를 비즈니스용 Skype 서버 몇 가지입니다.
  
- 클라이언트와 서버 간의 TLS 연결
    
- 서버 간의 MTLS 연결
    
- 파트너의 자동 DNS 검색을 사용한 페더레이션
    
- IM(인스턴트 메시징)에 대한 원격 사용자 액세스
    
- AV(오디오/비디오) 세션, 응용 프로그램 공유 및 회의에 대한 외부 사용자 액세스
    
- 웹 응용 프로그램 및 OWA(Outlook 웹 액세스) 사용
    
따라서 인증서 계획이 반드시 있어야 합니다. 이제 인증서를 요청할 때 유의해야 할 몇 가지 사항의 목록을 살펴보아야 합니다.
  
- 모든 서버 인증서는 서버 권한 부여(서버 EKU)를 지원해야 합니다.
    
- 모든 서버 인증서에는 CDP(CRL 배포 지점)가 포함되어 있어야 합니다.
    
- 모든 인증서는 운영 체제에서 지원하는 서명 알고리즘을 사용하여 서명해야 합니다. 비즈니스용 Skype 서버 2019는 다이제스트 크기(224, 256, 384 및 512비트)의 SHA-1 및 SHA-2 제품군을 지원하며 운영 체제 요구 사항을 충족하거나 초과합니다.
    
- 자동 등록은 2019년 8월에 실행되는 내부 비즈니스용 Skype 서버 지원됩니다.
    
- 자동 등록은 2019 에지 비즈니스용 Skype 서버 지원되지 않습니다.
    
> [!NOTE]
> RSASSA-PSS 서명 알고리즘을 사용할 수 없는 경우 로그인 및 전달 문제와 기타 문제로 인해 오류가 발생할 수 있습니다. 
  
- 암호화 키 길이는 1024, 2048 및 4096입니다. 키 길이가 2048 이상인 것이 좋습니다.
    
- 기본 다이제스트 또는 해시 서명 알고리즘은 RSA입니다. ECDH_P256, ECDH_P384 및 ECDH_P521 알고리즘도 지원됩니다.
    
생각해 볼 것이 많고 CA에서 인증서를 요청하는 데는 다양한 편안함 수준이 있습니다. 아래의 몇 가지 추가 지침을 제공하여 가능한 한 계획을 까다로우면 만들 것입니다.
  
### <a name="certificates-for-your-internal-servers"></a>내부 서버에 대한 인증서

대부분의 내부 서버에 대한 인증서가 필요하며, 대부분의 경우 내부 CA(도메인에 있는 CA)에서 인증서를 얻게 됩니다. 원하는 경우 외부 CA(인터넷에 있는 CA)에서 이러한 인증서를 요청할 수 있습니다. 어떤 공용 CA로 이동해야 하는지 궁금한 경우 통합 통신 인증서 파트너 목록을 [확인할 수](../../SfbPartnerCertification/certification/services-ssl.md) 있습니다.
  
또한 2019년 2019년 8월에 다른 응용 프로그램 및 서버와 통신하는 비즈니스용 Skype 서버 인증서가 Microsoft Exchange Server. 이 인증서는 이러한 다른 앱과 서버가 지원되는 방식으로 사용할 수 있는 인증서가 서는 안 됩니다. 비즈니스용 Skype 서버 2019 및 기타 Microsoft 제품은 서버 대 서버 인증 및 권한 부여를 위한 OAuth(Open Authorization) 프로토콜을 지원합니다. 이 문서에 관심이 있는 경우 OAuth 및 2019에 대한 추가 계획 비즈니스용 Skype 서버 있습니다.
  
비즈니스용 Skype 서버 2019에는 SHA-256 암호화 해시 함수를 사용하여 서명된 인증서(필요 없이)에 대한 지원도 포함되어 있습니다. SHA-256을 사용하여 외부 액세스를 지원하기 위해 SHA-256을 사용하는 공용 CA에서 외부 인증서를 발급해야 합니다.
  
이를 위해 Standard Edition 서버, 프런트 엔드 풀 및 기타 역할에 대한 인증서 요구 사항을 다음 표에 추가했습니다. 이 표에는 다음과 같은 contoso.com 예제에 사용하게 됩니다(작업 환경에서 다른 기능을 사용하게 될 수 있습니다). 이러한 인증서는 모두 표준 웹 서버 인증서로, 내보낼 수 없는 개인 키가 있습니다. 참고할 몇 가지 추가 사항:
  
- 인증서 마법사를 사용하여 인증서를 요청할 때 서버 EKU(확장된 키 사용)가 자동으로 구성됩니다.
    
- 각 인증서 이름은 컴퓨터 저장소에서 고유해야 합니다.
    
- 아래 샘플 이름에 따라 DNS에서 sipinternal.contoso.com 또는 sipexternal.contoso.com 구성한 경우 인증서의 SAN(주체 대체 이름)에 추가해야 합니다.
    
Standard Edition 서버용 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|기본값  <br/> |풀의 FQDN  <br/> |풀의 FQDN 및 서버의 FQDN  <br/> SIP 도메인이 여러 개 있고 자동 클라이언트 구성을 활성화한 경우 인증서 마법사는 지원되는 각 SIP 도메인 FQDN을 검색하고 추가합니다.  <br/> 이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS(Domain Name System) 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> 이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.  <br/> |Standard Edition 서버에서 서버 FQDN은 풀 FQDN과 동일합니다.  <br/> 이 마법사는 설치 시 지정한 SIP 도메인을 검색한 다음 주체 대체 이름에 자동으로 추가합니다.  <br/> 서버 대 서버 인증에 이 인증서를 사용할 수도 있습니다.  <br/> |
|웹 내부  <br/> |서버의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 내부 웹 FQDN(서버의 FQDN과 동일)  <br/> 그리고  <br/> • 단순 URL 충족  <br/> • 전화 접속 단순 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 단순 URL에 대한 와일드카드 항목  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 와일드카드 인증서 사용:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |토폴로지 작성기에서 내부 웹 FQDN을 다시 만들 수 있습니다.  <br/> Meet 단순 URL이 여러 개 있는 경우 이러한 URL을 모두 SA로 포함해야 합니다.  <br/> 와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.  <br/> |
|웹 외부  <br/> |서버의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 외부 웹 FQDN  <br/> 그리고  <br/> • 전화 접속 단순 URL  <br/> • SIP 도메인당 단순 URL 충족  <br/> 또는  <br/> • 단순 URL에 대한 와일드카드 항목  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 와일드카드 인증서 사용:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.  <br/> 와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.  <br/> |
   
프런트 엔드 풀의 프런트 엔드 서버에 대한 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|기본값  <br/> |풀의 FQDN  <br/> |풀의 FQDN 및 서버의 FQDN  <br/> SIP 도메인이 여러 개 있고 자동 클라이언트 구성을 활성화한 경우 인증서 마법사는 지원되는 각 SIP 도메인 FQDN을 검색하고 추가합니다.  <br/> 이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS(Domain Name System) 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> 이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.  <br/> |이 마법사는 설치 시 지정한 SIP 도메인을 검색한 다음 주체 대체 이름에 자동으로 추가합니다.  <br/> 서버 대 서버 인증에 이 인증서를 사용할 수도 있습니다.  <br/> |
|웹 내부  <br/> |풀의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 내부 웹 FQDN(서버의 FQDN과 같지 않은)  <br/> • 서버 FQDN  <br/> • 비즈니스용 Skype 풀 FQDN  <br/> 그리고  <br/> • 단순 URL 충족  <br/> • 전화 접속 단순 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 단순 URL에 대한 와일드카드 항목  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 와일드카드 인증서 사용:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.  <br/> 와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.  <br/> |
|웹 외부  <br/> |풀의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 외부 웹 FQDN  <br/> 그리고  <br/> • 전화 접속 단순 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 단순 URL에 대한 와일드카드 항목  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 와일드카드 인증서 사용:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |모임 단순 URL이 여러 개인 경우 모두 주체 대체 이름으로 포함해야 합니다.  <br/> 와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.  <br/> |
   
Director에 대한 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본값  <br/> |Director 풀  <br/> |Director의 FQDN, Director 풀의 FQDN입니다.  <br/> 이 풀이 클라이언트의 자동 로그온 서버인 경우 그룹 정책에 엄격한 DNS 일치가 필요한 경우 sip.sipdomain에 대한 항목도 필요합니다(보유하고 있는 각 SIP 도메인에 대해).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> 이 디렉터 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.  <br/> |
|웹 내부  <br/> |서버의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 내부 웹 FQDN(서버의 FQDN과 동일)  <br/> • 서버 FQDN  <br/> • 비즈니스용 Skype 풀 FQDN  <br/> 그리고  <br/> • 단순 URL 충족  <br/> • 전화 접속 단순 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 단순 URL에 대한 와일드카드 항목  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 와일드카드 인증서 사용:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|웹 외부  <br/> |서버의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 외부 웹 FQDN  <br/> 그리고  <br/> • SIP 도메인당 단순 URL 충족  <br/> • 전화 접속 단순 URL  <br/> 또는  <br/> • 단순 URL에 대한 와일드카드 항목  <br/> |Director 외부 웹 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버와 달라야 합니다.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 와일드카드 인증서 사용:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
독립 실행형 중재 서버용 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본값  <br/> |풀의 FQDN  <br/> |풀의 FQDN  <br/> 풀 구성원 서버의 FQDN  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Survivable Branch Appliance(특히 2019용 Survivable Branch Appliance 2015)에 비즈니스용 Skype 서버 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본값  <br/> |SBA의 FQDN  <br/> |SIP.\<sipdomain\> (SIP 도메인당 하나의 항목만 필요)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>외부 사용자 액세스용 인증서(Edge)

비즈니스용 Skype 서버 2019에서는 액세스 및 웹  회의 에지 외부 인터페이스에 단일 공용 인증서와 모두 에지 서버를 통해 제공되는 A/V 인증 서비스를 사용할 수 있습니다. 에지 내부 인터페이스는 일반적으로 내부 CA에서 발급한 개인 인증서를 사용하지만 원하는 경우 신뢰할 수 있는 CA에서 발급한 공용 인증서도 사용할 수 있습니다.
  
RP(역방향 프록시)도 공용 인증서를 사용하게 되며, RP에서 클라이언트로의 통신을 암호화하고 HTTP(또는 보다 정확하게는 HTTP를 통해 TLS)를 사용하여 내부 서버로의 통신을 암호화합니다.
  
### <a name="certificates-for-mobility"></a>모바일을 위한 인증서

모바일 기능을 배포하고 모바일 클라이언트에 대한 자동 검색을 지원하는 경우 모바일 클라이언트의 보안 연결을 지원하려면 인증서에 몇 가지 주체 대체 이름 항목을 추가로 포함해야 합니다.
  
다음 인증서에서 자동 검색을 위해 SAN 이름이 필요합니다.
  
- Director 풀
    
- 프런트 엔드 풀
    
- 역방향 프록시
    
구체적인 설명은 아래 표에 나와 있습니다.
  
이 경우 약간의 사전 계획이 좋지만, 모바일을 배포하지 않고 비즈니스용 Skype 서버 2019를 배포한 경우도 있으며, 나중에 환경에 인증서가 이미 있는 경우도 있습니다. 내부 CA를 통해 이러한 인증서를 다시 발급하는 것은 일반적으로 매우 간단하지만 공용 CA의 공용 인증서를 사용하여 약간 더 많은 가격을 책정할 수 있습니다.
  
이 경우 SIP 도메인이 많을 경우(SANS 추가 비용이 더 많이 드는) HTTPS를 사용하는 대신 초기 자동 검색 서비스 요청에 HTTP를 사용하도록 역방향 프록시를 구성할 수 있습니다(기본 구성). 모바일 [계획 문서에는](../../SfbServer/plan-your-deployment/mobility.md) 이에 대한 자세한 정보가 있습니다.
  
Director 풀 및 프런트 엔드 풀 인증서 요구 사항:
  
|**설명**|**SAN 항목**|
|:-----|:-----|
|내부 자동iscover 서비스 URL  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|외부 자동iscover 서비스 URL  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
또는 SAN= 을 사용할 수 \* 있습니다.\<sipdomain\>
  
공용 CA(역방향 프록시) 인증서 요구 사항:
  
|**설명**|**SAN 항목**|
|:-----|:-----|
|외부 자동iscover 서비스 URL  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
이 SAN은 역방향 프록시의 SSL 수신기에 할당된 인증서에 할당해야 합니다.
  
> [!NOTE]
> 역방향 프록시 수신기에는 외부 웹 서비스 URL에 대한 SANS가 있습니다. 일부 예로는 SAN=skypewebextpool01.contoso.com 및 dirwebexternal.contoso.com 배포한 경우(선택 사항)가 있습니다. 
  
## <a name="file-share"></a>파일 공유
<a name="Fileshare"> </a>

비즈니스용 Skype 서버 2019에서는 모든 파일 저장소에 동일한 파일 공유를 사용할 수 있습니다. 다음에 유의해야 합니다.
  
- 파일 공유는 DAS(직접 연결된 저장소) 또는 SAN(저장소 영역 네트워크)에 포함되어야 하며, 여기에는 DFS(분산 파일 시스템) 및 파일 저장소용 RAID(Redundant Array of Independent Disks)가 포함됩니다. 자세한 내용은 DFS for Windows Server 2012 [DFS 페이지를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))
    
- 파일 공유에 대한 공유 클러스터를 권장합니다. 이미 하나를 사용 중이면 상위 버전을 Windows Server 2012 합니다.

> [!Note]
> **최신 버전이 Windows?** 이전 버전에는 모든 기능을 사용하도록 설정할 수 있는 권한이 없는 경우도 있습니다. 클러스터 관리자를 사용하여 파일 공유를 만들 수 있습니다. 자세한 내용은 이 지원 문서를 참조하세요. [클러스터에서](https://support.microsoft.com/help/224967) 파일 공유를 만드는 방법을 참조하세요.
    
> [!CAUTION]
> NAS(네트워크 연결 저장소)를 파일 공유로 사용할 수 없습니다. 따라서 위에 나열된 옵션 중 하나를 사용하세요. 이러한 지원 제한은 장치의 공유 파일 시스템에 액세스하는 Windows 서버 기반 컴퓨터에 파일 시스템 적응성을 제공해야 하는 NAS 장치의 가변 디자인으로 인해 발생했습니다.
