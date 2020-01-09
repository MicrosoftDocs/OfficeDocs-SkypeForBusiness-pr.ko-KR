---
title: 비즈니스용 Skype 서버 2015에서 TLS 1.0/1.1 비활성화
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '요약: 사용자의 환경에서 TLS 1.0 및 1.1의 비활성화를 준비하고 구현합니다.'
ms.openlocfilehash: f10bd213be62b2d1dfa705e8ec8e0cc762706ee6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991553"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 TLS 1.0/1.1 비활성화

이 문서의 목적은 사용자의 환경에서 TLS 1.0 및 1.1의 비활성화를 준비하고 구현하는 데 필요한 지침을 제공하는 것입니다. 이 프로세스에는 방대한 계획 및 준비 작업이 필요합니다. 조직에서 TLS 1.0 및 1.1를 비활성화하는 계획을 수립하면서 이 문서의 모든 정보를 주의해서 검토하세요. TLS 1.0/1.1의 비활성화로 많은 외부 종속성과 연결 조건이 영향을 받을 수 있으므로 방대한 계획과 테스트가 보장됩니다.

## <a name="in-this-article"></a>이 문서의 내용

- [배경 및 범위](#background)
- [필수 구성 요소 및 프로세스](#prerequisites-and-process)
- [고급 배포 시나리오](#advanced-deployment-scenarios)

## <a name="background"></a>배경

비즈니스용 Skype 서버 온-프레미스에 대한TSL 1.0 및 1.1 비활성화 지원을 제공하는 주요 견인 요소는 결제카드산업(PCI) 보안표준협의회와 연방 정보 처리 표준 요구 사항입니다. PCI 요구 사항에 대한 자세한 내용은 [여기](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)서 확인할 수 있습니다.  Microsoft는 조직이 이러한 요구 사항 혹은 그 외의 요구 사항을 준수해야 하는지에 대한 지침은 제공할 수 없습니다. 환경에서 TLS 1.0 및/또는 1.1의 비활성화가 필요한지는 사용자가 판단해야 합니다.

Microsoft는 [여기에](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/) 사용할 수 있는 TLS에 대한 백서를 만들었으며 또한 이 [Exchange 블로그](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)에서 사용할 수 있는 배경 읽기를 권장합니다.

## <a name="supportability-scope"></a>지원 가능성 범위

*범위*는 지원 가능성 범위를 의미합니다. *완벽히 테스트했고 지원되는*은 당사가 나열된 제품 버전에 대한 TLS 1.0 및 1.1의 비활성화를 완벽히 지원하고 테스트하였음을 의미합니다. *현재 조사 중*은 당사가 이들 제품을 TLS 비활성화 지원의 범위에 포함시킬지를 적극적으로 조사하고 있음을 의미합니다. *범위를 벗어남*은 이들 제품 버전이 TLS 1.0 혹은 1.1의 비활성화를 지원하지 않고 작동하지 않을 것임을 의미합니다(참고 예외사항 제시).

### <a name="fully-tested-and-supported-servers"></a>완벽히 테스트했고 지원되는 서버

- 비즈니스용 Skype 서버 2019 CU1 17.0.2046.123(2019년 7월) 이상
- Windows Server 2012(KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 또는 대체 업데이트), 2012 R2 또는 2016에서의 비즈니스용 Skype 서버 2015 CU9 6.0.9319.548(2019년 5월) 이상
- Windows Server 2008 R2, 2012(KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) 또는 대체 업데이트) 또는 2012 R2에서 현재 실행 중인 업그레이드된 비즈니스용 Skype 서버 2015 CU9 6.0.9319.548(2019년 5월) 이상
- Exchange 연결 및 Exchange Server 2010 SP3 RU19 이상을 사용하는 Outlook 웹 앱 [여기](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)에 지침이 있습니다.
- 비즈니스용 Skype 서버 2015 CU6 HF2 이상을 사용하는 Survivable Branch Appliance(SBA)(판매자가 적정 업데이트를 패키지화했으며 어플라이언스에서도 사용할 수 있는지를 판매자와 확인하세요)
- 비즈니스용 Skype 서버 2015 CU6 HF2 이상을 사용하는 Survivable Branch Server(SBS)
- Lync Server 2013 **Edge 역할만**, 이는 Edge 역할이 Windows Fabric 1.0에 종속되지 않았기 때문입니다.

### <a name="fully-tested-and-supported-clients"></a>완벽히 테스트했고 지원되는 클라이언트

- Lync 2013(비즈니스용 Skype) 데스크톱 클라이언트, MSI 및 C2R(기본 [15.0.5023.1000 이상을 포함)](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- 비즈니스용 Skype 2016 데스크톱 클라이언트, MSI [16.0.4678.1000 이상](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)(기본 포함)
- 비즈니스용 Skype 2016를 간편 실행은 [2018년 4월](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) 업데이트를 필요로 합니다. 
    - 매월 그리고 반기를 대상으로 16\.0\.9126\.2152 이상
    - 반기 및 지연 채널, 16\.0\.8431\.2242 이상
- Mac의 비즈니스용 Skype 16.15 이상
- iOS용 비즈니스용 Skype 및 Android 6.19 이상
- Microsoft Teams Rooms(이전에는 Skype 회의실 시스템 V2 SRS V2로 알려짐) 4.0.64.0 (2018년 12월) 이상
- KB4499162 기반 Team 버전에 대한 Surface Hub 업데이트(2019년 5월, OS 빌드 15063.1835) 이상
- Skype 웹 앱 2015 CU6 HF2 이상(서버와 함께 제공)

### <a name="currently-being-investigated"></a>현재 조사 중

- 통화 품질 대시보드(TLS 1.0, 1.1을 비활성화한 후 새로운 설치, 아래를 참조하세요)*
 
### <a name="out-of-scope"></a>범위를 벗어남

언급된 경우를 제외하고 다음의 제품은 TLS 1.0/1.1 비활성화 지원의 범위에 있지 않으므로 TLS 1.0 및 1.1이 비활성화된 환경에서 작동하지 않습니다. 즉, 아직 범위를 벗어난 서버나 클라이언트를 사용하는 경우 비즈니스용 Skype 서버 온-프레미스를 배포하는 데 어디에서나 TLS 1.0/1.1을 비활성화해야 하는 경우 이들을 업데이트하거나 제거해야 합니다.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 이하
- Mac용 Lync 2011
- 모바일용 Lync 2013 - iOS, iPad, Android 또는 Windows Phone
- Lync "MX" Windows Store 클라이언트
- Lync 채팅방 시스템(a.k.a. SRSv1). LRS이 2018년 10월 9일에 지원을 종료했으며 TLS 1.2를 지원하도록 업데이트되지 않을 것입니다.
- 모든 Lync 2010 클라이언트
- Lync Phone Edition- [여기에](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035) 업데이트된 지침서가 있습니다.
- 2013 기반 Survivable Branch Appliance(SBA) 혹은 Survivable Branch Server(SBS)
- Cloud Connector Edition(CCE)
- Windows Phone용 비즈니스용 Skype

### <a name="exceptions"></a>예외

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013는 Windows Fabric 버전 1.0에 종속되어 있습니다.  Lync Server 2013의 설계 단계에서 복제, 고가용성 및 내결함성을 제공하기 위해 Windows Fabric 1.0이 그 강력하고 새로운 배포 아키텍처로 인해 선택되었습니다.  시간이 지나면서 비즈니스용 Skype 서버와 Windows Fabric이 모두 이후 버전에서 중요한 재설계를 통해 이 공동 아키텍처를 크게 개선시켰습니다.  예를 들어 현재 비즈니스용 Skype 서버 2015는 Windows Fabric 3.0을 사용합니다.

아쉽게도 Windows Fabric 1.0는 **TLS 1.2를 지원하지 않습니다. 그러나 TLS 1.2와 작동하도록 당사는 Lync Server 2013를 업데이트할 것입니다**. 업데이트는 Lync Server 2013의 다음 누적 업데이트에서 제공될 것입니다.  공동 존재, 마이그레이션, 페더레이션 및 하이브리드 시나리오를 사용하기 위해 TLS 1.2 지원을 제공하고 있습니다.

조직에서 TLS 1.0 및 1.1을 비활성화해야 하고 현재 Lync Server 2013를 사용하고 있는 경우, 업그레이드를 준비하거나 또는 병렬로 비즈니스용 Skype 서버 2015 이상으로 마이그레이션(새로운 풀, 사용자 이동)을 해야할 가능성을 염두에 두고 계획 프로세스를 시작할 것을 권장합니다.   또는 비즈니스용 Skype Online으로의 마이그레이션을 신속히 진행하는 것이 좋습니다.

#### <a name="call-quality-dashboard"></a>통화 품질 대시보드

온-프레미스 통화 품질 대시보드는 현재 새로 설치하는 동안 TLS 1.0에 종속성을 가지고 있습니다(사용자의 온-프레미스 환경에 최초 설치).  현재 이 문제를 조사 중이며 가까운 장래에 픽스를 릴리스할 예정입니다.  CQD를 설치하고 또한 TLS 1.0을 비활성화하려는 경우에는 먼저 CQD 설치를 완료한 다음 TLS 1.0 비활성화를 진행할 것을 권장합니다.

#### <a name="third-party-devices"></a>타사 장치

3PIP 휴대폰, 비디오 회의, 역방향 프록시 및 부하 분산 장치와 같은 타사 장치에서 TLS 1.2 지원 가능성을 확인하고 신중하게 테스트하며 필요한 경우 판매자에게 문의하도록 합니다.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Edge 서버에서 TLS 1.0/1.1을 비활성화할 때의 페더레이션 고려 사항

Edge 서버에서 TLS 1.0/1.1의 비활성화를 신중하게 계획하고 그 영향을 고려해야 합니다.  TLS 1.0 및 1.1이 비활성화되면 다른 조직이 사용자의 조직과 더 이상 페더레이션을 할 수 없게 됩니다.

Edge 서버에서 TLS 1.0/1.1을 사용할 수 있도록 선택하여 패치가 없는(SfB 2015, Lync 2013) 또는 이전의(2010) 외부 시스템과 하위 호환성을 유지할 수 있습니다.

Microsoft는 Edge 네트워크(또는 네트워크)가 PCI 표준에 속하는지에 대한 조언이나 권고를 제공할 수 없으며 이는 개별 회사에서 판단해야 합니다.

비즈니스용 Skype Online은 현재 TLS 1.2를 사용할 수 있으므로, 하이브리드/페더레이션에 영향을 주지 않을 것으로 예상됩니다.

PIC(공용 IM 연결)를 Skype 소비자 서비스로의 연결: TLS 1.0/1.1의 비활성화가 [Skype 연결성](../../deploy/deploy-skype-connectivity.md)에 영향을 주지 않을 것으로 예상됩니다. Microsoft PIC Gateway는 이미 TLS 1.2를 사용할 수 있습니다.

## <a name="prerequisites-and-process"></a>필수 구성 요소 및 프로세스

위에서 설명한 경우를 제외하고 TLS 1.0 및 1.1이 서버의 범위를 벗어나 비활성화가 되면 클라이언트와 장치가 제대로 작동하지 않거나 전혀 작동하지 않게됩니다. 이는 잠시 진행을 멈추고 Microsoft에서 제공하는 업데이트된 지침을 기다려야함을 의미할 수 있습니다. 모든 요구 사항을 충족하고 격차를 해결할 계획이 있다면 계속 진행합니다.

높은 수준에서 비즈니스용 Skype 서버 2019는설치 시 절차가 준비되어 있지만 비즈니스용 Skype 서버 2015는 CU9를 설치하고 .NET 및 SQL에 필수 업데이트의 적용 및 필수 레지스트리 키의 배포 그리고 마지막으로 별도의 OS 구성 업데이트 라운드를(즉, 레지스트리 파일 가져오기를 통해 TLS 1.0 및 1.1 비활성화) 필요로 합니다. 사용자 환경의 모든 서버에서 TLS 1.0 및 1.1을 비활성화하기 전에 비즈니스용 Skype 서버 2015 CU6 HF2를 포함하여 모든 필수 구성 요소를 설치하는 것은 매우 중요합니다. Edge 역할 및 SQL Backends을 비롯한 모든 비즈니스용 Skype 서버에 업데이트가 필요합니다. 또한 모든 지원되는(범위 내의) 클라이언트가 필수 최소 버전으로 업데이트되어 있는지도 확인 합니다. 관리 워크스테이션을 업데이트하는 것도 잊지 않도록 합니다.

당사는 비즈니스용 Skype 서버를 업그레이드하는 데 "인사이드 아웃" 작업의 일반적인 순서를 따르고자 합니다. 평소와 같은 방식으로 디렉터 풀, 영구적 채팅 및 페어링된 풀을 처리합니다. 업그레이드를 위한 순서와 방법에 대한 내용은 [여기](topology.md)와 [여기](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)에서 확인할 수 있습니다.

### <a name="high-level-process"></a>고급 프로세스

1. 프로덕션 서버를 구성하기 전에 랩에서 모든 단계를 테스트합니다.
2. 업데이트되는 개별 서버마다 그리고 각각의 내보낸 레지스트리를 백업하고 보존합니다. 서버 간에는 레지스트리를 공유할 수 없습니다. 고유한 컴퓨터 기반의 키를 포함하고 있습니다.
3. 모든 비즈니스용 Skype 서버 2015를 CU9 이상으로 업그레이드합니다. 비즈니스용 Skype 서버 2019의 경우 CU1 이상으로 업그레이드합니다.
4. 모든 서버에 모든 필수 구성 요소를 설치합니다.
5. 필수 구성 요소 레지스트리 키를 배포합니다.
6. 모든 범위에 있는 클라이언트가 업데이트되었는지 확인합니다.
7. 레지스트리 가져오기를 통해 TLS 1.0 및 1.1을 비활성화합니다.
8. 워크로드가 예상대로 작동하는지 확인합니다.
    - 문제가 발생할 경우 문제를 문제 해결을 진행하여 해결하고 또는
    - 2 단계에서 레지스트리를 복원하여 TLS 1.0 및 1.1을 다시 사용하도록 설정합니다.
9. TLS 1.2만 사용 중인지 확인합니다.

### <a name="install-prerequisites-to-all-servers"></a>모든 서버에 모든 필수 구성 요소를 설치합니다.

비즈니스용 Skype 서버 2015 배포 시 운영 체제 수준에서 TLS 1.0 및 1.1의 비활성화를 시작하기 전에 방대한 종속성 업데이트를 수행해야 합니다. TLS 1.2를 지원할 수 있는 최소 버전은 다음과 같습니다. TLS 1.0 및 1.1의 비활성화를 시작하기 전에 사용자 환경에서 모든 비즈니스용 Skype 서버에 모든 필수 업데이트를 배포합니다.

- 비즈니스용 Skype 서버 2015 CU9 6.0.9319.548(2019년 5월) 이상
- 레지스트리에서 SchUseStrongCrypto를 사용하도록 설정한 경우(아래에서 제공) [.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) 이상
- 모든 비즈니스용 Skype 2015 서버 및 백엔드에서 SQL을 업데이트해야 합니다. Enterprise Edition Pool SQL 백엔드를 먼저 업데이트하고 해당 FEs를 업데이트합니다. 
    - [SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), 이상/SQL Server 2012 SP2 + CU16 이상/[SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), 이상/SQL Server 2014 SP2
     - [SQL Server 2012용 SQL Server Native Client](https://www.microsoft.com/download/details.aspx?id=50402)
     - [SQL Server용 Microsoft ODBC Driver 11](https://www.microsoft.com/download/details.aspx?id=36434), 이상
     - [SQL Server 2014 SP2용 공유 관리 개체](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQL server 2014 SP2용 SQLSysClrTypes](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>권장되는 작업 순서대로 사전 필수 구성 요소를 설치하는 기본 단계

1. 모든 서버에 비즈니스용 Skype 서버 CU9 업데이트를 설치합니다. 
    1. 업데이트기를 사용하여 구성 요소에 업데이트를 설치합니다.
    2. 문서화된 절차에 따라 데이터베이스를 업데이트합니다. 비즈니스용 Skype 서버 2015의 경우 KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)를 참조합니다. 
    3. 다른 변경 사항을 진행하기 전에 배포 시 제품 기능에 대한 유효성 검사를 수행합니다.
2. .NET 4.7 설치 관리자를 다운로드합니다. 
    1. 참조: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. 프론트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중단되었는지 확인합니다.
    3. 참조: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. 예 (Standard Edition): ```Stop-CsWindowsService```
    5. 예 (Enterprise Edition): ```Invoke-CsComputerFailover```
    6. 설치 관리자 패키지를 실행합니다.
    7. 서버를 다시 부팅합니다.
3. 모든 서버에서 SQL Express 2014를 업데이트합니다. 
    1. 참조: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. SQL 2014 SP2를 다운로드합니다. 
        - 참조: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. 서버에 있는 폴더에 설치 미디어를 복사합니다(예: C:\ 01_2014SqlSp2).
    4. 프론트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중단되었는지 확인합니다. 
        - 예 (Standard Edition): ```Stop-CsWindowsService```
        - 예 (Enterprise Edition): ```Invoke-CsComputerFailover```
    5. 관리 명령 프롬프트를 열고 설치한 모든 구성 요소와 인스턴스를 업그레이드합니다. 
        - 예: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances
4. SQL Native Client를 업데이트합니다. 
    1. 참조: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)에서 다운로드합니다.
    3. 프론트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중단되었는지 확인합니다. 
        - 예 (Standard Edition): ```Stop-CsWindowsServices```
        - 예 (Enterprise Edition): ```Invoke-CsComputerFailover```
    4. 설치된 SQL 인스턴스의 실행을 중지합니다. 
        - 예: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - 예: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - 예 (Standard Edition만): ```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. 업데이트를 설치합니다.
5. TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server))에 대한 지원을 포함 하도록 SQL Server용 ODBC Driver 11을 업데이트합니다.
    1. [SQL Server용 ODBC 드라이버 11 - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434)를 다운로드합니다.
    2. 프론트 엔드 서버에서 비즈니스용 Skype 서버 2015 서비스가 중단되었는지 확인합니다.
        - 예 (Standard Edition): ```Stop-CsWindowsService```
        - 예 (Enterprise Edition): ```Invoke-CsComputerFailover```
    3. 업데이트를 설치합니다.
6. 필수 구성 요소 레지스트리 키를 배포합니다.

### <a name="pre-requisite-registry-keys"></a>필수 구성 요소 레지스트리 키

다음의 테스트를 복사하여 메모장에 붙여 넣고 TLSPreReq 또는 원하는 이름으로 바꾼 다음 가져오기를 수행합니다.

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

Enterprise Edition 풀에 대한 SQL 백엔드의 경우 필수 구성 요소 및 TLS의 비활성화는 SQL 또는 OS 업데이트와 같이 처리해야 합니다. 참고: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

필수 구성 요소 응용 프로그램과 TLS 비활성화 단계는 결합될 수 있지만 운영 체제 수준에서 TLS 1.0 및 1.1의 비활성화를 진행하기 전에 모든 필수 구성 요소를 적용할 것을 권장합니다. 최상의 방법은 모든 필수 구성 요소를 배포하고 모든 작업이 제대로 수행되었는지 확인한 후 나중에 TLS 1.0/1.1의 비활성화를 진행하여 환경을 준비하는 것입니다.

### <a name="disable-tls-10-and-11-via-registry-import"></a>레지스트리 가져오기를 통해 TLS 1.0 및 1.1을 비활성화합니다.

다음 단계를 진행하기 전에 *모든 필수 구성 요소를 완료하였고 비즈니스용 Skype 서버를 업데이트했는지를 확인합니다*.

다음의 텍스트를 메모장 파일에 복사하고 **TLSDisable.reg**로 파일의 이름을 변경합니다.

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

TLS 1.0 및 1.1을 비활성화하려는 각 서버에서 .reg 파일을 가져옵니다. 서버를 다시 부팅합니다. 서비스가 다시 온라인 상태가 되면 다음 서버로 이동합니다. Enterprise Edition 풀에 대한 접근 방법은 OS 업데이트에 대해 수행하는 것과 동일합니다.

여기에서 TLS 1.0 및 1.1의 비활성화 보다 더 많은 작업을 수행하고 있음을 확인하셨을 것입니다. 당사는 암호 제품군 재정렬(위에 설명한 대로) 및 일부 오래된 weak 암호의 비활성화를 지원하고 있습니다. 이번이 당사가 비즈니스용 Skype 서버에서 SCHANNEL 및 Crypto API에 대한 이러한 변경 사항을 공식으로 지원하는 최초 지원이며 이들 변경 사항만이 현재 당사가 지원하 고 테스트를 거친 사항임을 참고하시기 바랍니다. 차후에 추가 구성을 고려할 수도 있지만 지금으로서는 구현 시 레지스트리 가져오기 파일을 수정하지 마십시오.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>워크로드가 예상대로 작동하는지 확인합니다.

환경에서 TLS 1.0 및 1.1가 비활성화된 후에는 IM & 현재 상태, P2P 통화, Enterprise Voice 등과 같은 모든 주요 워크로드가 예상 대로 작동하는지 확인합니다.

**TLS 1.2만 사용 중인지 확인합니다**.

보안 팀이 비즈니스용 Skype에 대한 새로운 감사를 수행하여 이전 프로토콜 TLS 1.0 및 1.1가 더 이상 사용되지 않는지 확인합니다.

또는 TLS 1.0 및 TLS 1.1를 비활성화한 후 Internet Explorer를 사용하여 비즈니스용 Skype 서버 2015에서 웹 서비스로의 TLS 연결을 테스트할 수 있습니다.

1. Internet Explorer를 실행합니다.
2. **도구** > **인터넷 옵션**을 선택합니다.
3. **고급** 탭을 선택합니다.
4. **설정**에서 아래로 스크롤합니다.
5. TLS 1.0, TLS 1.1 및 TLS 1.2이 사용하도록 설정되어 있는지 확인합니다.
6. SfB 2015 풀의 내부 웹 서비스 URL을 검색합니다(제대로 연결되어야 함).
7. 다시 Internet Explorer로 돌아가 **TLS 1.2만 사용** 옵션을 비활성화합니다.
8. SfB 2015 풀의 내부 웹 서비스 URL을 다시 검색합니다(연결되지 않아야 함).

![인터넷 옵션](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>고급 배포 시나리오

일부 종속성 필수 구성 요소가 비즈니스용 Skype Ser 2015에서 TLS 1.2를 지원하는데 필요하므로 RTM 미디어에서 TLS 1.0과 1.1가 해제된 시스템에 설치 시 오류가 발생합니다.

**환경에서 TLS 1.0 및 1.1이 비활성화된 경우 새 Standard Edition 서버나 Enterprise Edition 풀 배포.**

**옵션 1:**[SmartSetup](../../deploy/install/install-skype-for-business-server.md)을 사용합니다. 당사는 향후 CU에서 업데이트된 SQL 바이너리를 수용할 수 있는 SmartSetup을 업데이트하고 있으며 향후에 이 문서를 업데이트할 것임을 참고하시기 바랍니다.

**옵션 2:** 로컬 SQL 인스턴스를 사전 설치(RTCLOCAL 및 LLYNCLOCAL)

1. SQL Express 2014 SP2(SQLEXPR_x64.exe)를 다운로드하고 FE의 로컬 폴더에 복사합니다. 폴더 경로가 <SQL_FOLDER_PATH>라고 가정해 보겠습니다.
2. PowerShell 또는 명령 프롬프트를 시작하고 <SQL_FOLDER_PATH>로 이동합니다.
3. 아래 명령을 실행하여 RTCLOCAL SQL 인스턴스를 만듭니다. 진행하기 전에 SQLEXPR_x64.exe가 완료될 때까지 기다립니다.

    SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati
1. 아래 명령을 실행하여 RTCLOCAL SQL 인스턴스를 만듭니다. 다음 단계로 넘어가기 전에 SQLEXPR_x64.exe가 완료될 때까지 기다립니다.

    SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic
1. 비즈니스용 Skype 서버 2015 RTM 설치를 실행합니다.
2. 위의 필수 구성 요소 섹션에서 나머지 단계를 따릅니다.

**옵션 3:** 로컬 설치 미디어 디렉터리에서 바이너리를 다음과 같이 수동으로 바꿀 수도 있습니다.

1. [비즈니스용 Skype 서버 및 Exchange 서버의 필수 구성 요소 설치](../../deploy/install/install-prerequisites.md)  
2. .NET 4.7를 설치합니다. 
      - **참고:** 처음에는 비즈니스용 Skype 서버 2015 CU5 (6.0.9319.281)에서 .NET 4.7에 대한 지원을 도입했습니다. 따라서 아래 단계에서는 주 설치 이전의 핵심 구성 요소를 업데이트할 것입니다.
      - 다운로드: https://www.microsoft.com/download/details.aspx?id=55167. 
      - 참고: [비즈니스용 Skype 서버 2015 배포 이전에 설치해야 하는 소프트웨어](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. ISO 파일/폴더를 복사. 
    - 비즈니스용 Skype 서버 2015 ISO를 첨부한 상태에서 드라이브의 루트 디렉터리를 첨부된 대로 엽니다(예: D: 파일 탐색기의 \).
    - 모든 폴더와 파일을 로컬 디스크의 폴더(예: C:\SkypeForBusiness2015ISO)로 복사합니다.
    - **참고**: 구성 요소를 설치하기 전에 TLS 1.2를 지원하기 위해 일부 파일을 업데이트 해야 합니다.
4. MSI/EXE 패키지 대체. 
    - 로컬 컴퓨터의 설치 미디어의 /Setup/amd64/ 폴더의 기존 MSI 및 EXE 패키지를 대체합니다.
    - SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - 로컬 컴퓨터에서 SQLEXPR_x64으로 이름을 변경하고 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.
    - SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **참고**: 필요한 경우 sqlncli.msi로 이름을 변경한 다음 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.
    - SQL 관리 개체: https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **참고:** 기능 팩은 다운로드 가능한 많은 항목을 포함할 것입니다. SharedManagementObjects.msi만 다운로드하록 선택합니다.
        - **참고**: 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.
    - SQL CLR 유형: https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **참고:** 기능 팩은 다운로드 가능한 많은 항목을 포함할 것입니다. CQLSysClrTypes.msi만 다운로드하도록 선택 합니다.
        - **참고**: 설치 미디어의 Setup/amd64/ 폴더에 있는 기존 파일을 대체합니다.
5. 핵심 구성 요소 설치. 
    - 설치 미디어의 Setup/amd64/ 폴더에서 Setup.exe를 실행합니다. 지침에 따라 핵심 구성 요소 설치
    - 핵심 구성 요소를 닫습니다.
6. 핵심 구성 요소를 업데이트합니다. 
    - 비즈니스용 Skype 업데이트 설치 관리자를 다운로드합니다.
    - 설치 관리자를 실행하여 핵심 구성 요소를 업데이트하고 성능 카운터를 설치합니다.
    - **참고:** CU6HF2 릴리스의 자동 업데이트 기능은 현재 CU6까지만 설치합니다. 따라서 6.0.9319.516에 핵심 구성 요소를 업데이트하려면 업데이트기를 별도로 실행해야 합니다.
    - 참조: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. 관리 도구 설치(선택 사항): 
    - 업데이트된 파일을 사용하여 Microsoft SQL Server 2012 Native Client, SQL server 2014 관리 개체(x64) 및 SQL 2014 Server(x64)용Microsoft System CLR 유형을 설치합니다. 추가로 비즈니스용 Skype 서버 2015 토폴로지 작성기와 제어판을 로컬 컴퓨터에서 사용할 수 있게 됩니다.
8. 로컬 구성 저장소 설치(1단계): 
     - 배포 마법사를 열고 설치 혹은 비즈니스 서버 시스템용 비즈니스용 Skype 업데이트를 클릭한 다음 1단계, 로컬 구성 저장소 설치에서 **실행**을 클릭합니다.
     - **로컬 구성 저장소 설치** 대화 상자에서 **다음**을 클릭합니다.
     ![로컬 구성 저장소 대화 상자 설치](../../media/local-configuration-store.png)
     - 결과를 검토하고 작업 상태가 완료로 되었는지 확인합니다. **로그 보기**를 클릭하여 결과 로그 파일을 검토합니다.
     ![완료로 표시되는 작업 상태](../../media/local-configuration-task-completed.png)
     - **마침**을 클릭합니다.
9. 비즈니스용 Skype 서버 구성 요소 설치 또는 제거(2단계):
    - 배포 마법사를 열고 **비즈니스용 Skype 서버 시스템 설치 혹은 업데이트**를 클릭하고 2단계, 비즈니스용 Skype 서버 구성 요소 설치 혹은 제거에서 **실행**을 클릭합니다.
    - 비즈니스용 Skype 서버 구성 요소 설정 대화 상자에서 **다음**을 클릭합니다.
    ![비즈니스용 Skype 서버 구성 요소 설치 창](../../media/set-up-skype-for-business-server-components-window.png)
    - 로그 보기를 사용하여 로그를 검토하고 설치가 문제없이 완료되었는지 확인합니다. 
    - **마침**을 클릭합니다.
10. 필요에 따라 추가 설치 및 구성 작업을 진행 합니다(이 시점에서 일반 설치 절차를 다시 시작할 수 있음).
