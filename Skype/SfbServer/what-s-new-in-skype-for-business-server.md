---
title: 2015의 새로운 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: '요약: 이 항목을 통해 2015년 8월의 새로운 기능에 대해 비즈니스용 Skype 서버 있습니다. 새 클라이언트 경험에 대한 자세한 내용은 이제 Lync가 비즈니스용 Skype 새로운 것을 참조하세요.'
ms.openlocfilehash: aac68c369983b85ecb95b5000dc41d95e2080d6d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760566"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>2015의 새로운 비즈니스용 Skype 서버

**요약:** 이 항목을 통해 2015년 8월의 새로운 기능에 대해 비즈니스용 Skype 서버 있습니다. 새 클라이언트 경험에 대한 자세한 내용은 [Lync is now 비즈니스용 Skype -- see what's new](https://go.microsoft.com/fwlink/p/?LinkId=529022).
  
Lync는 이제 비즈니스용 Skype, 엔터프라이즈급 보안, 규정 준수 및 제어와 함께 Skype 환경을 통합하는 커뮤니케이션 및 공동 작업 플랫폼입니다. 비즈니스용 Skype, IM, 음성 및 화상 통화, 온라인 모임 등의 기능을 제공합니다. 비즈니스용 Skype 새 클라이언트 환경, 새 서버 릴리스 및 서비스 업데이트는 Microsoft 365 Office 365. 조직의 사용자가 이미 조직에 익숙한 경우 Skype 쉽게 찾아서 연결할 수 있는 비즈니스용 Skype 간편한 조직의 능력과 단순성을 평가할 것입니다. 조직의 사용자가 Lync에서 비즈니스용 Skype 사용하는 모든 기능이 인식되지만, 간소화된 컨트롤 및 새로운 추가 기능이 있는 새로운 인터페이스에서 사용할 수 있습니다. 새로운 클라이언트 환경 외에도 비즈니스용 Skype 서버 2015에서는 몇 가지 새로운 기능을 제공하여 사내 서버 및 하이브리드 솔루션의 관리 성능을 향상합니다.
  
2015의 비즈니스용 Skype 서버 기능은 다음과 같습니다.
  
- 사용자 환경  
- 음성 및 비디오 지원
- 모바일 지원
- 사내 서버 관리
- 하이브리드 솔루션 배포 및 관리
- 다단계 인증 지원
    
## <a name="user-experience"></a>사용자 환경

이 비즈니스용 Skype 클라이언트는 동일한 단추와 아이콘을 Skype 소비자 버전과 매우 유사합니다. 메뉴 수가 적고 작업 계층 구조가 간단해지기 때문에 사용자가 필요한 컨트롤과 명령을 쉽게 찾을 수 있습니다. 
  
비즈니스용 Skype 설명한 새 사용자 환경과 이전에 릴리스된 Lync 2013 사용자 환경이 포함됩니다. 두 환경을 모두 포함하면 기업은 새 클라이언트 롤아웃의 프로세스와 타이밍을 제어하여 사용자에 대한 변경을 관리할 수 있습니다. 기본 사용자 환경은 사용 하는 서버의 버전에 따라 다를 수 있습니다. 관리자는 **Set-CsClientPolicy** cmdlet을 EnableSkypeUI 매개 변수와 함께 사용하여 기본 환경을 선택할 수 있습니다. 클라이언트 환경을 구성하는 데 대한 자세한 내용은 [Configure the client experience with 비즈니스용 Skype](deploy/deploy-clients/configure-the-client-experience.md) and Desktop client feature comparison for [비즈니스용 Skype.](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
  
> [!NOTE]
> Lync 2013 클라이언트 환경은 2016 클라이언트 비즈니스용 Skype 옵션이 아닙니다. Lync 2013 클라이언트를 사용하도록 클라이언트 환경을 구성하기 전에 클라이언트 버전을 확인하여 번호 16으로 시작하지 않는지 확인하시기 바랍니다. 예: 16.x.x.x 
  
## <a name="voice-and-video-improvements"></a>음성 및 비디오 개선

비즈니스용 Skype 서버 2015에는 통화 데이터 수집 및 분석을 비롯한 음성 및 비디오 기능이 개선되어 타사 비디오 원격 구성 시스템과의 상호 운영성이 향상되었습니다.
  
### <a name="call-data-collection-and-analysis"></a>통화 데이터 수집 및 분석

내 통화 속도 기능을 사용하면 2015 비즈니스용 Skype 서버 데이터를 수집할 수 있습니다. 이 기능은 사내 배포에만 사용할 수 있습니다. 통화를 완료한 후 설문 조사를 묻는 메시지가 사용자에게 표시될 수 있습니다. 자세한 내용은 [Rate my Call in 비즈니스용 Skype 서버 2015을 참조하십시오.](manage/health-and-monitoring/rate-my-call.md)
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>타사 비디오 원격 구성 시스템과의 상호 운영성 개선

VIS(Video Interop Server)는 VTC(비디오 비즈니스용 Skype 서버) 시스템 간의 중계자 역할을 합니다. 모임에 참가할 때 사용자는 이제 Cisco VTC 시스템을 선택할 수 있습니다. VIS(Video Interop Server)는 사내 배포를 위한 독립 실행형 서버 역할로 구현됩니다. 자세한 내용은 [Plan for Video Interop Server in 비즈니스용 Skype 서버 2015을 참조하십시오.](plan-your-deployment/video-interop-server.md)
  
### <a name="call-via-work"></a>업무를 통해 전화

기업 사용자는 업무용 전화 기능을 통해 클라이언트에서 음성 통화를 할 비즈니스용 Skype 있습니다. 사용자가 음성 통화를 걸면 발신자 비즈니스용 Skype PBX 또는 PSTN 전화로 라우팅됩니다. 발신자 전화에 응답하면 통화가 대상 번호로 연결됩니다. 전화 받는 사람이 응답하고 제어판의 비즈니스용 Skype 호출이 설정됩니다. 발신자 는 자신의 현재 상태 및 통화 제어를 비즈니스용 Skype. 서버 관리자는 엔터프라이즈에 대해 직장을 통한 통화를 사용하도록 설정하고 구성합니다. 자세한 내용은 [Plan for Call Via Work in 비즈니스용 Skype 서버 2015을 참조하십시오.](plan-your-deployment/enterprise-voice-solution/call-via-work.md) 
  
## <a name="mobile-device-support-improvements"></a>향상된 모바일 장치 지원

모바일 장치 지원 개선에는 대화 기록 및 로그 데이터에 대한 액세스Enterprise Edition 향상된 모바일 모임 환경, 사용자 전체의 Single Sign-On 지원 등 Office. 또한 Android 지원, 성능 향상 및 공통 앱 프레임워크를 통한 통합을 간소화하는 기능이 개선되었습니다. 
  
> [!NOTE]
> 모바일 클라이언트를 지원하려면 Lync 2013 UCWA 서버를 비즈니스용 Skype 서버 2015로 업그레이드해야 합니다. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>이제 모바일 장치에서 서버 쪽 대화 기록을 사용할 수 있습니다.

대화 기록, 부재 중 IM 및 통화 로그 데이터에 모바일 액세스를 사용하도록 설정하기 위해 이 정보의 보관은 이제 모든 모바일 클라이언트에 대해 서버를 통해 처리됩니다. IM의 자동 수락 기능은 모바일 사용자가 IM에 즉시 응답하지 않는 경우 서버 시간 아웃 메시지를 방지하여 안정성을 향상시킵니다. 서버 기반 Exchange/Outlook 폴더 통합을 활용하려면 Exchange Server 2013 이상 및 업데이트된 모바일 클라이언트가 필요합니다. 
  
### <a name="enhanced-meeting-experiences"></a>향상된 모임 환경

이제 모바일 사용자도 데스크톱에서 사용할 수 있는 모임 기능을 사용할 수 있습니다. 새 기능에는 다음이 포함됩니다.
  
- 공유 콘텐츠의 비동기 PowerPoint 탐색
- 발표자는 공유 콘텐츠에 대한 제어를 PowerPoint 있습니다.
- 발표자에 대한 대기실 관리- 참가자를 허용하거나 거부할 수 있습니다.
    
### <a name="skype-for-business-on-android-improvements"></a>비즈니스용 Skype Android의 향상된 기능

비즈니스용 Skype Android에서는 이제 iOS 및 비즈니스용 Skype 버전에서 사용할 수 있는 기능과 비즈니스용 Skype Windows.
  
- 대화 계속 또는 다시 참가
- 인증서 및 수동 인증 사용
- 대화에 다른 사람 초대
- 그룹 대화를 쉽게 시작할 수 있습니다.
- 사용자가 되지 않고 모임에 참가할 비즈니스용 Skype
- Android 태블릿에서 스마트폰 UI 사용
- 참가자를 추가 또는 제거하여 모임 관리
    
> [!NOTE]
> 이러한 기능을 사용하려면 Android OS 버전 4.0 이상이 요구됩니다. 
  
## <a name="management-of-on-premises-servers"></a>사내 서버 관리

비즈니스용 Skype 서버 2015에서는 바로 업그레이드, 스마트 설치, 향상된 패치 및 업그레이드 프로세스, 향상된 프런트 엔드 풀 콜드 시작 기능, AlwaysOn 지원 SQL Server 및 중앙 로깅 및 문제 해결을 비롯한 여러 가지 새로운 기능을 통해 사내 서버의 관리 성능을 향상시킵니다.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>사내 서버의 전제 업그레이드

이제 기존 Lync Server 2013 하드웨어 및 서버 투자를 사용하는 새로운 전체 업그레이드 기능을 사용하여 Lync Server 2013 시스템을 비즈니스용 Skype 서버 2015로 업그레이드할 수 있어 2015를 배포하는 데 드는 전체 비용이 비즈니스용 Skype 서버 있습니다.
  
현재 상태 업그레이드에는 두 가지 시나리오가 있습니다. 즉, 다운타임이 필요 없는 Move User 메서드와 오프라인 메서드(다운타임이 필요)가 있습니다. 비즈니스에 적합한 업그레이드 절차에 대한 자세한 내용은 [Plan to upgrade to 비즈니스용 Skype 서버 2015을 참조하십시오.](plan-your-deployment/upgrade.md) 
  
> [!NOTE]
> Lync Server 2010에서 업그레이드하는 경우 현재 기능을 사용할 수 없습니다. Lync Server 2010에서 업그레이드하는 데 대한 자세한 내용은 [Plan to upgrade to 비즈니스용 Skype 서버 2015을 참조하십시오.](plan-your-deployment/upgrade.md) 
  
### <a name="smart-setup"></a>스마트 설정

업데이트를 자동으로 검색하고 다운로드하는 스마트 설치 기능은 이제 설치 프로그램의 일부입니다. 설치 프로세스 중에 사용자에게 설치 프로세스에서 업데이트를 확인해야 하는지 묻는 질문이 사용자에게 있습니다. 자세한 내용은 [Install 비즈니스용 Skype 서버 2015를 참조하십시오.](deploy/install/install.md)
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>향상된 프런트 엔드 서버 패치 및 업그레이드 프로세스

비즈니스용 Skype 서버 프런트 엔드 서버를 이전 버전 Lync Server보다 훨씬 쉽게 업그레이드 또는 패치할 수 있도록 하는 두 가지 새로운 cmdlet이 도입되었습니다.
  
프런트 엔드 서버에 패치를 적용하거나 다른 유지 관리 작업을 수행해야 하는 경우 **Invoke-CsComputerFailOver를** 입력하고 해당 서버의 이름을 지정하면 됩니다. 비즈니스용 Skype 서버 서버의 작업을 풀의 다른 서버로 일시적으로 이동합니다. 그런 다음 유지 관리 작업을 수행한 다음 **Invoke-CsComputerFailback** cmdlet을 사용하여 해당 서버를 다시 서비스로 가져올 수 있습니다. 풀의 각 서버를 패치해야 하는 경우 각 서버에 대해 한 번씩 이 절차를 수행하면 됩니다. 이러한 새로운 cmdlet을 사용하면 이전 버전보다 훨씬 빠르게 서버를 패치할 수 있으며 안정성과 워크플로가 더 간단해집니다.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>향상된 프런트 엔드 풀 콜드 시작 기능

비즈니스용 Skype 서버 전체 프런트 엔드 풀을 콜드 시작하는 프로세스를 간소화하고 개선하는 새로운 cmdlet을 도입했습니다. 새 **Start-CsPool** cmdlet을 사용하면 풀의 모든 프런트 엔드 서버에 대한 선행 준비를 확인한 다음 각 서버를 시작하려고 시도합니다. 문제가 발생하면 진단하고 세부 정보 및 해결 사항을 알리는 경고를 제공합니다. 경우에 따라 개별 서버 중 일부를 시작할 수 없는 경우에도 풀을 시작할 수 있습니다.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>SQL Server AlwaysOn의 사내 서버에 대한 지원

비즈니스용 Skype 서버 2015에서는 AlwaysOn 가용성 그룹 및 SQL Server AlwaysOn 장애 조치(failover) 클러스터 SQL Server 모두에 대한 지원을 추가합니다. 이러한 기능 외에도 이전 비즈니스용 Skype 서버 Lync Server와 SQL Server 미러링 및 SQL Server 지원이 계속 지원됩니다.
  
SQL Server AlwaysOn 가용성 그룹은 데이터베이스 미러링에 대한 대안을 제공하는 SQL Server 2012 및 SQL Server 2014의 고가용성 및 재해 복구 솔루션입니다. 가용성 그룹은 함께 장애 조치(failover)하는 서로 다른 데이터베이스 집합(가용성 데이터베이스라고도 하는)에 대한 장애 조치(failover) 환경을 지원합니다. 가용성 그룹은 읽기-쓰기 기본 데이터베이스 집합과 해당 보조 데이터베이스 집합 1-4개 집합을 지원합니다. 선택적으로 읽기 전용 액세스 및 일부 백업 작업에 보조 데이터베이스를 사용할 수 있습니다.
  
SQL Server 장애 조치(failover) 클러스터 인스턴스는 Windows WSFC(서버 장애 조치(Failover) 클러스터링) 기능을 활용하여 서버 인스턴스 수준의 중복을 통해 로컬 고가용성(FCI(장애 조치(failover) 클러스터 인스턴스)을 제공합니다. FCI는 WSFC(SQL Server 서버 장애 조치(failover) 클러스터링) Windows 여러 서브넷에 설치되는 단일 서버 인스턴스입니다.
  
자세한 내용은 [Plan for high availability and disaster recovery in 비즈니스용 Skype 서버 2015을 참조하십시오.](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>중앙 집중식 로깅 및 문제 해결 개선된 사내 서버

중앙 로깅 서비스는 2015년 8월 25일의 기본 로깅 비즈니스용 Skype 서버 환경입니다. 이 릴리스에는 새로운 기능이 없지만 서비스 및 중앙 로깅 서비스 에이전트(ClsAgent.exe)(컨트롤러와 통신하고 관리자가 실행한 명령을 받는 서비스 실행)에 대해 안정성과 성능이 개선되었습니다.
  
비즈니스용 Skype 서버 2015에서는 Windows PowerShell cmdlet을 사용하여 로깅 서비스 에이전트를 관리하고 추적을 시작하고 보고서를 생성합니다. (Lync Server 2013에서는 이러한 ClsController.exe 작업을 수행하는 데 사용했습니다.)
  
중앙 로깅 서비스는 2015년 10월에 비즈니스용 Skype 서버 있습니다. 기본 제공 시나리오(미리 정의된 추적)는 사용자 지정 시나리오를 만드는 능력과 동일하게 유지됩니다. AlwaysOn이라는 특수한 시나리오가 있으며 항상 실행되고 있으며 관리자는 거의 실시간으로 일반적인 문제를 찾을 수 있습니다.
  
또한 모바일 로그 디버깅을 허용하도록 Snooper 디버깅 도구가 업데이트되어 Lync 2013 또는 비즈니스용 Skype 서버 2015에 연결하는 장치에서 작동합니다. 이 도구는 디버깅 도구 에서 웹 [다운로드로 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=285257)
  
## <a name="hybrid-deployment-and-management"></a>하이브리드 배포 및 관리

비즈니스용 Skype 서버 2015에서는 다음 기능을 도입하여 하이브리드 배포 관리 및 관리 기능을 사용할 수 있습니다.
  
- 권장 사항 자동 지원 도구에 대한 OnRamp에 따라 고객의 Office 365 자산의 상태를 기반으로 하이브리드 배포에 대한 정보를 제공합니다.
- 관리자가 이러한 도구를 사용하여 하이브리드 배포를 관리할 수 있도록 비즈니스용 Skype 서버 제어판 및 비즈니스용 Skype 서버 관리 센터의 향상된 기능
- 관리자가 Microsoft 365 또는 Office 365 테넌트에 로그인하고 하이브리드 구성 마법사를 사용하여 비즈니스용 Skype Online을 사용하여 하이브리드를 설정할 수 있는 제어판 기능이 향상되었습니다.
- 제어판은 온라인에서 온라인으로 이동하거나 비즈니스용 Skype 온라인 사용자를 비즈니스용 Skype 이동하기 위한 제어판 지원입니다.
- 제어판 기능은 비즈니스용 Skype Online(즉, 하이브리드 사용자)으로 이동된온-프레미스 사용자 개체를 식별하고 필터링하는 기능입니다.
- 비즈니스용 Skype Online에서 처음 만든 클라우드 사용자를 식별하고 필터링하기 위한 관리 센터 기능입니다.
- 제어판을 사용하여 하이브리드 사용자를 관리하고, 관리 센터는 온라인에서 관리할 수 있는 속성에 비즈니스용 Skype 있습니다.
- DirSync와 암호 동기화를 사용하여 온-프레미스 Active Directory 암호를 온라인 테넌트와 동기화할 수 있습니다. 이 기능을 구성하면 페더니트 인증을 위해 AD FS를 배포할 필요가 없지만 다단계 인증에는 여전히 AD FS가 필요합니다. 
- 비즈니스용 Skype Online과 Exchange 공존을 계속 지원
    
> [!NOTE]
> Lync Online 2013 및 온-프레미스 Exchange 지원 환경은 변경되지 않습니다. 
  
## <a name="multi-factor-authentication"></a>다단계 인증

다단계 인증은 두 개 이상의 인증 방법을 사용해야 하는 인증 방법으로, 사용자 로그인 및 트랜잭션에 중요한 두 번째 보안 계층을 추가합니다. 예를 들어 사용자 이름과 암호 및 인증서를 요구합니다. 비즈니스용 Skype 서버 2015는 Lync Server 2013 누적 업데이트에서 사용할 수 있는 다단계 인증 기능을 계속 빌드합니다. 다단계 인증이 크게 변경된 경우:
  
- Office 및 통합에 Office 2013 SP1 Active Directory 인증 라이브러리를 Exchange SharePoint
- 클라이언트에서 다단계 인증 기능에 비즈니스용 Skype Web App 지원
    
다단계 비즈니스용 Skype 사용하여 이제는 지리에 따라 다양한 인증 옵션을 제공할 수 있습니다. 예를 들어 고객은 조직 외부에서 인증하는 직원이 다단계 인증을 Windows 통합 인증을 사용하도록 환경을 구성할 수 있습니다. 
  
다단계 비즈니스용 Skype 환경은 다음에 관계없이 원활하게 사용할 수 있습니다.
  
- 지리적 위치 - 사용자가 조직 내부 또는 외부에서 로그인하는지 여부 
- 클라이언트/장치 유형 - 클라이언트가 비즈니스용 Skype 및 클라이언트가 실행 중인 장치(PC, 모바일, iPad 등)입니다.
- 계정 위치 - 사용자가온-프레미스 Active Directory에서 호스팅되어 있는지 아니면 온라인에서 Azure Active Directory.
