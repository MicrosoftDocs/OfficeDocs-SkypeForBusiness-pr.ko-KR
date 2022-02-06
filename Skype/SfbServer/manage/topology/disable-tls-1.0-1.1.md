---
title: 2015년 8월에서 TLS 1.0/1.1을 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 환경에서 TLS 1.0 및 1.1을 사용할 수 없는 경우를 준비하고 구현합니다.
---

# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>2015년 8월에서 TLS 1.0/1.1을 비즈니스용 Skype 서버

이 문서는 환경에서 TLS 1.0 및 1.1의 사용 안 하게 설정하는 것을 준비하고 구현하는 데 도움이 됩니다. 이 프로세스에서는 광범위한 계획과 준비가 필요합니다. 조직에서 TLS 1.0 및 1.1을 사용하지 않도록 설정하는 계획을 세우면 이 문서의 모든 정보를 주의 깊게 검토하십시오. TLS 1.0/1.1을 사용할 수 없는 경우 영향을 줄 수 있는 많은 외부 종속성 및 연결 조건이 있으므로 광범위한 계획 및 테스트가 진행됩니다.

- [백그라운드 및 범위](#background-and-scope)
- [선행 절차 및](#prerequisites-and-process)
- [고급 배포 시나리오](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a>백그라운드 및 범위

비즈니스용 SKYPE 서버 대한 TLS 1.0 및 1.1 비활성화 지원을 제공하기 위한 기본 드라이버는 PCI(Payment Card Industry) 보안 표준 위원회 및 연방 정보 처리 표준 요구 사항입니다. PCI 요구 사항에 대한 자세한 내용은 여기에서 찾을 수 [있습니다](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft는 조직이 이러한 요구 사항 또는 기타 요구 사항을 준수해야 하는지 여부에 대한 지침을 제공할 수 없습니다. 환경에서 TLS 1.0 및/또는 1.1을 사용하지 않도록 설정하는 데 필요한지 여부를 결정해야 합니다.

Microsoft는 여기에서 사용할 수 있는 TLS에 대한 백서를 생성[했습니다. 또한](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/) 이 문서 블로그에서 사용할 수 있는 배경 [Exchange 좋습니다](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>지원 가능성 범위

*범위* 는 지원 가능성 경계를 참조합니다. *완전히 테스트 및* 지원되는 것은 나열된 제품 버전에 대해 TLS 1.0 및 1.1의 사용 안 을 완전히 지원하고 테스트했다는 의미입니다. *현재 조사 중이란* 의미일 수 있습니다. TLS 비활성화 지원을 위해 이러한 제품을 범위로 가져오는 것을 적극적으로 조사하고 있습니다. *범위를 벗* 어났다는 것은 이러한 제품 버전이 TLS 1.0 또는 1.1의 사용 안 을 지원하지 않는 것으로, 예외를 제외하고는 작동하지 않습니다.

### <a name="fully-tested-and-supported-servers"></a>완전히 테스트 및 지원되는 서버

- 비즈니스용 Skype 서버 2019 CU1 17.0.2046.123(2019년 6월) 이상
- 비즈니스용 Skype 서버 2015 CU9 6.0.9319.548(Windows Server 2012 2019년 5월) 이상([KB 3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 또는 변경된 업데이트 사용), 2012 R2 또는 2016.
- Windows Server 2008 R2, 2012([KB 3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 또는 업데이트의 경우) 또는 2012 R2에서 CU9 6.0.9319.548(2019년 5월) 이상인 전체 업그레이드된 비즈니스용 Skype 서버 2015.
- Exchange 연결 및 Outlook Web App Exchange Server 2010 SP3 RU19 이상에 대한 지침은 여기를 [클릭하세요.](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- 비즈니스용 Skype 서버 2015 CU6 HF2 이상이 있는 SBA(Survivable Branch Appliance)(공급업체에 적절한 업데이트를 패키지로 만들며 어플라이언스에서 사용할 수 있도록 설정되어 있는지 공급업체에 확인)
- 2015 CU6 HF2 이상을 비즈니스용 Skype 서버 SBS(Survivable Branch Server)
- Lync Server 2013 **에** 지 역할만, 에지 역할이 1.0에 종속되지 Windows Fabric 있기 때문에입니다.

### <a name="fully-tested-and-supported-clients"></a>완전히 테스트 및 지원되는 클라이언트

- Lync 2013(비즈니스용 Skype) 데스크톱 클라이언트, MSI 및 C2R(기본 [15.0.5023.1000 이상](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334) 포함)
- 비즈니스용 Skype 2016 데스크톱 클라이언트, MSI [16.0.4678.1000](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323) 이상(기본 포함)
- 비즈니스용 Skype 2016 Click to Run(실행하려면 [2018년 4월 업데이트](/officeupdates/release-notes-office365-proplus) 필요) 
    - 월별 및 Semi-Annual 대상, 16091262152\.\.\. 이상
    - Semi-Annual 및 지연 채널, 16084312242\.\.\. 이상
- 비즈니스용 Skype Mac 16.15 이상에서 사용
- 비즈니스용 Skype 및 Android 6.19 이상용 앱
- Microsoft Teams 룸(Skype Room System V2 SRS V2) 4.0.64.0(2018년 12월) 이상
- Surface Hub KB4499162(2019년 5월, OS 빌드 15063.1835) 이상을 기반으로 하는 팀 버전에 대한 업데이트 업데이트
- Skype Web App 2015 CU6 HF2 이상(서버와 함께 배송)

### <a name="currently-being-investigated"></a>현재 조사 중

- 통화 품질 대시보드(TLS 1.0, 1.1이 비활성화된 후 새 설치, 아래 참조)*
 
### <a name="out-of-scope"></a>범위를 벗어남

설명된 경우를 제외하고 다음 제품은 TLS 1.0/1.1 사용 안 의 지원 범위에 있지 않을 뿐만 아니라 TLS 1.0 및 1.1이 비활성화된 환경에서는 작동하지 않습니다. 즉, 여전히 범위를 벗어날 수 있는 서버 또는 클라이언트를 활용하는 경우, 비즈니스용 Skype 서버 배포에서 TLS 1.0/1.1을 사용하지 않도록 설정해야 하는 경우 이러한 서버를 업데이트하거나 제거해야 합니다.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 이상
- Mac 2011용 Lync
- Lync 2013 for Mobile - iOS, iPad, Android 또는 Windows Phone
- Lync "MX" Windows Store 클라이언트
- Lync 룸 시스템(a.k.a. SRSv1). LRS는 2018년 10월 9일 지원이 종료된 후 TLS 1.2를 지원하기 위해 업데이트되지 않습니다.
- 모든 Lync 2010 클라이언트
- Lync 전화 Edition - 여기에서 지침이 업데이트[되었습니다](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- 2013 기반 SBA(Survivable Branch Appliance) 또는 SBS(Survivable Branch Server)
- CCE(Cloud Connector Edition)
- 비즈니스용 Skype for Windows Phone

### <a name="exceptions"></a>예외

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013은 Windows Fabric 버전 1.0에 종속됩니다.  Lync Server 2013의 디자인 단계에서 Windows Fabric 1.0은 복제, 고가용성 및 내결함성을 제공하기 위한 뛰어난 새로운 분산 아키텍처로 선택되었습니다.  시간이 지날 때 비즈니스용 Skype 서버 및 Windows Fabric 버전에서는 이 공동 아키텍처가 크게 개선되었습니다.  현재 비즈니스용 Skype 2015 Server에서는 Windows Fabric 3.0을 사용하는 경우를 예로 들 수 있습니다.

안타깝게도 Windows Fabric 1.0은 **TLS 1.2를 지원하지 않습니다.  그러나 TLS 1.2에서 작동하기 위해 Lync Server 2013을 업데이트할 것입니다**. 이 업데이트는 Lync Server 2013의 다음 누적 업데이트에 추가될 것입니다.  공조, 마이그레이션, 페더전 및 하이브리드 시나리오를 사용할 수 있도록 TLS 1.2 지원을 제공합니다.

조직에서 TLS 1.0 및 1.1을 사용하지 않도록 설정해야 하는 경우 현재 Lync Server 2013을 사용하는 경우 전체 업그레이드 또는 나란히 마이그레이션(새 풀, 사용자 이동)을 비즈니스용 Skype 서버 2015 이상으로 마이그레이션해야 할 가능성이 있는 경우 계획 프로세스를 시작하는 것이 좋습니다.  또는 Online으로의 마이그레이션을 비즈니스용 Skype 있습니다.

#### <a name="call-quality-dashboard"></a>통화 품질 대시보드

현재 새 설치 중에(사내 환경에 처음 설치할 때) On-Premises Call Quality Dashboard는 TLS 1.0에 종속됩니다.  We are currently investigating this issue and plan to release a fix in the near future.  CQD를 설치하고 TLS 1.0도 사용하지 않도록 설정하려면 먼저 CQD 설치를 완료한 다음 TLS 1.0 비활성화를 진행하는 것이 좋습니다.

#### <a name="skype-for-business-sdn-manager"></a>비즈니스용 Skype SDN 관리자

비즈니스용 Skype SDN 관리자를 SQL 새 설치 중에 TLS 1.0에 종속됩니다. 비즈니스용 Skype SDN 관리자를 설치하고 SQL TLS 1.0도 사용하지 않도록 설정하려면 먼저 비즈니스용 Skype SDN 관리자를 완료한 다음 TLS 1.0 비활성화를 진행하는 것이 좋습니다. 설치 전에 TLS 1.0을 사용하지 않도록 설정한 경우 SQL Server SDN Manager 데이터베이스를 호스팅하는 데 사용할 SQL Server 비즈니스용 Skype TLS 1.0을 일시적으로 SQL 합니다.

#### <a name="third-party-devices"></a>타사 장치

3PIP 전화, 비디오 회의, 역방향 Proxies 및 부하 균형 장치와 같은 타사 장치에서는 TLS 1.2 지원 가능성의 유효성을 검사하고 신중하게 테스트한 후 필요한 경우 공급업체에 문의해야 합니다.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>에지 서버에서 TLS 1.0/1.1을 사용할 수 없는 경우의 페더링 고려 사항

에지 서버에서 TLS 1.0/1.1을 사용할 수 없는 경우의 영향을 신중하게 계획하고 고려해야 합니다.  TLS 1.0 및 1.1을 사용하지 않도록 설정하면 다른 조직이 더 이상 조직과 페더러이트할 수 없는 것일 수 있습니다.

패치되지 않은(SfB 2015, Lync 2013) 또는 이전(2010) 외부 시스템과의 호환성을 유지하기 위해 에지 서버에서 TLS 1.0/1.1을 사용하도록 유지할 수 있습니다.

Microsoft는 에지 네트워크(또는 네트워크)가 PCI 표준에 속하는지 여부에 대한 조언이나 권장 사항을 제공할 수 없습니다. 개별 회사에서 결정해야 합니다.

비즈니스용 Skype Online은 현재 TLS 1.2를 사용할 수 있으므로 온라인과의 하이브리드/페더러에 아무 영향도 없습니다.

PIC(공용 IM 연결) Skype 소비자 서비스에 영향을 미치기 위해 TLS 1.0/1.1을 사용할 수 Skype [않습니다](../../deploy/deploy-skype-connectivity.md). Microsoft PIC 게이트웨이는 이미 TLS 1.2를 사용할 수 있습니다.

## <a name="prerequisites-and-process"></a>선행 절차 및

위에서 언급한 경우를 제외하고 TLS 1.0 및 1.1이 범위를 벗어났습니다. 이는 Microsoft의 업데이트된 지침을 일시 중지하고 기다려야 하다는 의미일 수 있습니다. 모든 요구 사항을 충족하고 격차를 해결할 계획이 있는 경우 계속 진행합니다.

높은 수준에서 비즈니스용 Skype 서버 2019를 설치할 준비가 되어 있는 동안 비즈니스용 Skype 서버 2015를 사용하려면 CU9를 설치하고, .NET 및 SQL에 선행 요구 업데이트를 적용하고, 선행 레지스트리 키를 배포하고, 마지막으로 별도의 OS 구성 업데이트 라운드(예: 레지스트리 파일 가져오기에서 TLS 1.0 및 1.1을 사용 안 하도록 설정)를 요구합니다. 환경의 모든 서버에서 TLS 1.0 및 1.1을 사용할 수 있도록 설정하기 전에 비즈니스용 Skype 서버 2015 CU6 HF2를 비롯한 모든 선행 구성 요소의 설치를 완료하는 것이 매우 중요합니다. 에지 비즈니스용 Skype 및 백 SQL 포함하여 모든 서버에는 업데이트가 필요합니다. 또한 지원되는(범위 내) 클라이언트가 필요한 최소 버전으로 업데이트되어 있도록 합니다. 관리 Workstation도 업데이트하는 것을 잊지 마세요.

서버 업그레이드를 위한 "내부 내부" 작업의 일반적인 비즈니스용 Skype 합니다. 일반적으로와 동일한 방식으로 Director 풀, 영구 채팅 및 페어링된 풀을 처리합니다. 여기서는 업그레이드 순서 및 [방법에 대해](topology.md) [다를 수 있습니다](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>높은 수준의 프로세스

1. 프로덕션 서버를 구성하기 전에 랩의 모든 단계를 테스트합니다.
2. 업데이트할 각 개별 서버에서 내보낼 레지스트리 복사본을 백업하고 보존합니다. 서버 간에는 레지스트리를 공유할 수 없습니다. 이러한 키에는 고유한 컴퓨터 기반 키가 포함되어 있습니다.
3. 모든 비즈니스용 Skype 2015 서버를 CU9 이상으로 업그레이드합니다. 2019 비즈니스용 Skype 서버 CU1 이상으로 업그레이드합니다.
4. 모든 서버에 모든 선행 준비를 설치합니다.
5. 선행 레지스트리 키를 배포합니다.
6. 범위 내 클라이언트가 모두 업데이트되도록 합니다.
7. 레지스트리 가져오기에서 TLS 1.0 및 1.1을 사용하지 않도록 설정
8. 워크로드가 예상대로 작동하고 있는지 유효성을 검사합니다.
    - 문제가 발생하면 문제 해결 또는
    - 2단계에서 레지스트리를 복원하여 TLS 1.0 및 1.1을 다시 사용하도록 설정
9. TLS 1.2만 사용 중이지 않은지 검사합니다.

### <a name="install-prerequisites-to-all-servers"></a>모든 서버에 필요한 설치

비즈니스용 Skype 서버 배포의 운영 체제 수준에서 TLS 1.0 및 1.1을 사용하지 않도록 설정하려면 광범위한 종속성 업데이트가 필요합니다. 다음은 TLS 1.2를 지원할 수 있는 최소 버전입니다. TLS 1.0 비즈니스용 Skype 1.1을 사용 안 하게 설정하기 전에 환경의 모든 비즈니스용 Skype 서버에 모든 선행 업데이트를 배포합니다.

- 비즈니스용 Skype 서버 2015 CU9 6.0.9319.548(2019년 5월) 이상
- .NET Framework SchUseStrongCrypto를 사용하여 [4.7](https://www.microsoft.com/download/details.aspx?id=55167) 이상을 사용할 수 있습니다(아래 제공).
- SQL 2015 서버 및 백 비즈니스용 Skype 업데이트해야 합니다. 백 Enterprise Edition 먼저 SQL 풀을 업데이트한 다음 해당 FES를 업데이트합니다. 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926) 이상/SQL Server 2012 SP2 + CU16 이상/[SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014) 이상/ SQL Server 2014 SP2
     - [SQL Server Native Client 2012용 SQL Server](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434) 이상
     - [SQL Server 2014 SP2용 공유 관리 개체](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQL server 2014 SP2용 SQLSysClrTypes](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>권장되는 작업 순서로 선행 준비 단계를 설치하는 기본 단계

1. 모든 비즈니스용 Skype 서버 CU9 업데이트를 설치합니다. 
    1. 업데이트 프로그램을 사용하여 구성 요소에 업데이트를 설치합니다.
    2. 문서화된 절차에 따라 데이터베이스를 업데이트합니다. 2015 비즈니스용 Skype 서버 [KB 3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. 다른 변경 내용을 적용하기 전에 배포에서 제품 기능의 유효성을 검사합니다.
2. .NET 4.7 오프라인 설치 관리자를 다운로드합니다. 
    1. 참조: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. 프런트 엔드 비즈니스용 Skype 서버 2015 서비스가 중지되어 있는지 확인
    3. 참조: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. 예(Standard Edition):```Stop-CsWindowsService```
    5. 예(Enterprise Edition):```Invoke-CsComputerFailover```
    6. 설치 관리자 패키지를 실행합니다.
    7. 서버를 다시 부팅합니다.
3. 모든 SQL Express 2014를 업데이트합니다. 
    1. 참조: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. SQL 2014 SP2 다운로드 
        - 참조: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. 서버의 폴더에 설치 미디어 복사(예: C:\01_2014SqlSp2)
    4. 프런트 비즈니스용 Skype 서버 2015 서비스가 중지되어 있는지 확인 
        - 예(Standard Edition):```Stop-CsWindowsService```
        - 예(Enterprise Edition):```Invoke-CsComputerFailover```
    5. 관리자 명령 프롬프트를 열고 설치된 모든 구성 요소 및 인스턴스 업그레이드 
        - 예: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. 업데이트 SQL Native Client. 
    1. 참조: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. 에서 다운로드 [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. 프런트 비즈니스용 Skype 서버 2015 서비스가 중지되어 있는지 확인 
        - 예(Standard Edition):```Stop-CsWindowsServices```
        - 예(Enterprise Edition):```Invoke-CsComputerFailover```
    4. 설치된 SQL 실행 중지 
        - 예: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - 예: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - 예(Standard Edition 전용):```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. 업데이트를 설치합니다.
5. TLS 1.2(KB SQL Server)에 대한 지원을 포함하기 위해 ODBC 드라이버 11[을 3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    1. [ODBC 드라이버 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. 프런트 엔드 비즈니스용 Skype 서버 2015 서비스가 중지되어 있는지 확인
        - 예제(Standard Edition):```Stop-CsWindowsService```
        - 예제(Enterprise Edition):```Invoke-CsComputerFailover```
    3. 업데이트를 설치합니다.
6. 선행 레지스트리 키를 배포합니다.

### <a name="pre-requisite-registry-keys"></a>사전 레지스트리 키

다음 테스트를 복사하여 메모장 TLSPreReq.reg 또는 이름을 변경한 다음 가져오기합니다.

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

SQL 풀의 Enterprise Edition 풀의 경우, OS 업데이트 또는 OS 업데이트와 같은 SQL 및 TLS 사용 안 하게 처리해야 합니다.[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](./patch-or-update-a-back-end-or-standard-edition-server.md)

선행 응용 프로그램과 TLS를 사용할 수 없는 단계는 모두 결합할 수 있는 반면 운영 체제 수준에서 TLS 1.0 및 1.1을 계속 사용 안 하게 되기 전에 모든 선행 단계를 적용하는 것이 좋습니다. 모범 사례 방법은 모든 선행 구성을 배포하고 모든 워크로드가 예상대로 올바르게 작동하고 유효성을 검사한 다음 나중에 TLS 1.0/1.1을 사용하지 않도록 설정하여 환경을 준비하는 것입니다.

### <a name="disable-tls-10-and-11-via-registry-import"></a>레지스트리 가져오기에서 TLS 1.0 및 1.1을 사용하지 않도록 설정

다음 단계를 진행하기 전에 모든 선행 단계를 완료하고 서버의 모든 비즈니스용 Skype *합니다*.

다음 텍스트를 파일로 메모장 **TLSDisable.reg로 이름을 변경합니다**.

```console
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

TLS 1.0 및 1.1을 사용하지 않도록 설정할 각 서버에서 .reg 파일을 가져오면 됩니다. 서버를 다시 부팅합니다. 서비스가 다시 온라인이 되돌아오면 다음 서버로 이동하십시오. 모든 OS Enterprise Edition 풀에 대한 접근 방식은 동일합니다.

여기에서 TLS 1.0 및 1.1을 사용 안 하게 하는 것 이상으로 많은 작업을 수행하고 있는 것을 알 수 있습니다. 당사는 위에서 설명한 대로 암호 제품군 다시 주문 및 일부 이전 약한 암호의 비동기화가 지원됩니다. 이번이 SCHANNEL 및 비즈니스용 Skype 서버 API에 대한 이러한 변경 내용을 공식적으로 지원한 것은 이번이 처음이기 때문에 이러한 변경 내용은 현재 지원하고 테스트한 유일한 변경 내용입니다. 향후에 추가 구성을 고려할 수 있지만 현재는 구현에서 레지스트리 가져오기 파일을 수정하지 말아야 합니다.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>워크로드가 예상대로 작동하고 있는지 확인

환경에서 TLS 1.0 및 1.1을 사용하지 않도록 설정한 경우 IM & 현재 상태, P2P 통화, Enterprise Voice 등의 모든 기본 워크로드가 예상대로 작동하도록 합니다.

**TLS 1.2만 사용 중이면 유효성 검사**

보안 팀이 이전 프로토콜 TLS 1.0 비즈니스용 Skype 1.1을 더 이상 사용하지 않도록 새 감사를 수행하도록 합니다.

또는 TLS 1.Internet Explorer TLS 1.1을 사용하지 않도록 설정한 후 비즈니스용 Skype 서버 2015에서 웹 서비스에 대한 TLS 연결을 테스트할 수 있습니다.

1. 시작 Internet Explorer.
2. **도구** > **인터넷 옵션** 을 선택합니다.
3. **고급** 탭을 선택합니다.
4. 아래 **설정** 아래쪽으로 스크롤합니다.
5. TLS 1.0, TLS 1.1 및 TLS 1.2가 사용하도록 설정되어 있는지 확인합니다.
6. SfB 2015 풀의 내부 웹 서비스 URL을 검색합니다(성공적으로 연결해야 합니다).
7. 다시 Internet Explorer **TLS 1.2** 만 사용 옵션을 사용하지 않도록 설정하세요.
8. SfB 2015 풀의 내부 웹 서비스 URL을 다시 검색합니다(연결하지 못해야 합니다).

![인터넷 옵션.](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>고급 배포 시나리오

비즈니스용 Skype 서버 2015에서 TLS 1.2를 지원하는 데 일부 종속성 필수 구성이 필요하기 때문에 TLS 1.0 및 1.1이 비활성화된 모든 시스템에서 RTM 미디어에서 설치가 실패합니다.

**환경에서 TLS 1.0 Enterprise Edition 1.1을 사용하지 않도록 설정한 경우 새 Standard Edition 서버 또는 Enterprise Edition 풀 배포**

**옵션 1:** [SmartSetup을 사용 합니다](../../deploy/install/install-skype-for-business-server.md). 향후 CU에서 업데이트된 SQL 이진을 수용하기 위해 SmartSetup을 업데이트하고 있으며 향후 이 문서가 업데이트될 예정입니다.

**옵션 2:** 로컬 SQL 사전 설치(RTCLOCAL 및 LYNCLOCAL)

1. FE의 로컬 폴더에 SQL Express 2014 SP2(SQLEXPR_x64.exe)를 다운로드하여 복사합니다. 폴더 경로 <SQL_FOLDER_PATH>.
2. PowerShell 또는 명령 프롬프트를 시작하고 <SQL_FOLDER_PATH>.
3. 아래 명령을 SQL RTCLOCAL 인스턴스를 만들 수 있습니다. 계속하기 SQLEXPR_x64.exe 완료될 때까지 기다렸다가 다음을 진행합니다.

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati
1. 아래 명령을 SQL LYNCLOCAL 인스턴스를 만들 수 있습니다. 다음 SQLEXPR_x64.exe 완료될 때까지 기다렸다가 다음 단계를 진행합니다.

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. 2015 비즈니스용 Skype 서버 설치를 실행합니다.
2. 위의 선행 구성자 섹션에 있는 나머지 단계를 따릅니다.

**옵션 3:** 다음과 같이 로컬 설치 미디어 디렉터리의 이진 파일을 수동으로 바꿀 수도 있습니다.

1. [설치를 위한 비즈니스용 Skype 서버](../../deploy/install/install-prerequisites.md)  
2. .NET 4.7을 설치합니다. 
      - **참고:** 처음에는 비즈니스용 Skype 서버 CU5(6.0.9319.281)에서 .NET 4.7에 대한 지원을 도입했습니다. 따라서 아래 이후 단계에서는 주 설치 전에 핵심 구성 요소를 업데이트할 것입니다.
      - 다운로드: https://www.microsoft.com/download/details.aspx?id=55167. 
      - 참조: [2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)년 배포 전에 설치해야 하는 비즈니스용 Skype 서버 소프트웨어
3. ISO 파일/폴더를 복사합니다. 
    - 2015 비즈니스용 Skype 서버 ISO가 연결된 경우 첨부된 드라이브의 루트 디렉터리를 파일 탐색기에서 (예: D:\) 를 열 수 있습니다.
    - 모든 폴더와 파일을 로컬 디스크의 폴더에 복사합니다(예: C:\SkypeForBusiness2015ISO).
    - **참고:** 구성 요소를 설치하기 전에 일부 파일을 업데이트하여 TLS 1.2를 지원해야 합니다.
4. MSI/EXE 패키지 바꾸기: 
    - 로컬 컴퓨터의 설치 미디어의 /Setup/amd64/ 폴더에 있는 기존 MSI 및 EXE 패키지를 교체합니다.
    - SQL 2014 SP2 Express:https://www.microsoft.com/download/details.aspx?id=53167 
        - 이름을 SQLEXPR_x64 로컬 컴퓨터로 이름을 바꾸고 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.
    - SQL Native Client:https://www.microsoft.com/download/details.aspx?id=50402 
        - **참고:** 필요한 경우 이름을 sqlncli.msi 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.
    - SQL 관리 개체:https://www.microsoft.com/download/details.aspx?id=53164 
        - **참고:** 기능 팩에는 다운로드할 수 있는 많은 항목이 있습니다. 를 선택하여 SharedManagementObjects.msi만 다운로드합니다.
        - **참고:** 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.
    - SQL CLR 형식:https://www.microsoft.com/download/details.aspx?id=53164 
        - **참고:** 기능 팩에는 다운로드할 수 있는 많은 항목이 있습니다. Select to download CQLSysClrTypes.msi only
        - **참고**: 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.
5. 핵심 구성 요소를 설치합니다. 
    - 설치 Setup.exe/amd64/ 폴더에서 실행합니다. 지침에 따라 핵심 구성 요소 설치
    - 핵심 구성 요소를 닫습니다.
6. 핵심 구성 요소 업데이트: 
    - 업데이트 비즈니스용 Skype 다운로드합니다.
    - 설치 관리자를 실행하여 핵심 구성 요소를 업데이트하고 성능 카운터를 설치합니다.
    - **참고:** CU6HF2 릴리스를 현재 자동 업데이트 기능은 CU6까지만 설치합니다. 따라서 핵심 구성 요소를 6.0.9319.516으로 업데이트하려면 업데이트를 별도로 실행해야 합니다.
    - 참조: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. 관리 도구 설치(선택 사항): 
    - 이렇게 하면 업데이트된 파일을 사용하여 Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects(x64) 및 SQL Server 2014(x64)에 대한 Microsoft System CLR 형식이 설치됩니다. 또한 로컬 비즈니스용 Skype 서버 2015 토폴로지 작성기 및 제어판을 사용할 수 있습니다.
8. 로컬 구성 저장소 설치(1단계): 
     - 배포 마법사를 열고 시스템 비즈니스용 Skype 서버 설치 또는 업데이트를 클릭한 다음 1단계: 로컬 구성  저장소 설치에서 실행을 클릭합니다.
     - 로컬 **구성 저장소** 설치 **대화 상자에서 다음** 을 클릭합니다.
     ![로컬 구성 저장소를 설치합니다.](../../media/local-configuration-store.png)
     - 결과를 검토하고 작업 상태가 완료가 되도록 합니다. 로그 보기를 클릭하여 결과 로그 **파일을 검토합니다**.
     ![작업 상태가 완료로 표시됩니다.](../../media/local-configuration-task-completed.png)
     - **마침** 을 클릭합니다.
9. 구성 요소 비즈니스용 Skype 서버 설정 또는 제거(2단계):
    - 배포 마법사를 열고 비즈니스용 Skype 서버 **시스템** 설치 또는 업데이트를 클릭한 다음 2단계: 구성  요소 설정 또는 제거에서 실행을 비즈니스용 Skype 서버 클릭합니다.
    - 구성 **요소 설정** 비즈니스용 Skype 서버 다음을 클릭합니다.
    ![구성 요소 비즈니스용 Skype 서버 설정 창입니다.](../../media/set-up-skype-for-business-server-components-window.png)
    - 로그 보기를 사용하여 로그를 검토하고 설치가 문제 없이 완료된지 유효성을 검사합니다. 
    - **마침** 을 클릭합니다.
10. 필요한 경우 추가 설치 및 구성을 계속 진행합니다(이 시점에서 일반 설치 절차를 다시 시작할 수 있습니다).