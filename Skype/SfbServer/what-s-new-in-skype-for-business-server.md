---
title: 비즈니스용 Skype 서버 2015의 새로운
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2017
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e62c9229-b738-45ef-b637-0b58ca8225a4
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버 2015의 새로운 기능에 대해 자세히 알아보습니다. 새 클라이언트 경험에 대한 자세한 내용은 Lync가 이제 비즈니스용 Skype입니다. 새로운 것을 참조하세요.'
ms.openlocfilehash: 09774f722020ef750ae16ad01a29873d43d25e76
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827588"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 새로운

**요약:** 이 항목을 읽고 비즈니스용 Skype 서버 2015의 새로운 기능에 대해 자세히 알아보습니다. 새 클라이언트 경험에 대한 자세한 내용은 [Lync가](https://go.microsoft.com/fwlink/p/?LinkId=529022)이제 비즈니스용 Skype입니다. 새로운 것을 참조하세요.
  
Lync는 이제 비즈니스용 Skype로, 엔터프라이즈급 보안, 규정 준수 및 Lync 제어를 통해 Skype에서 영감을 얻은 환경을 제공합니다. 비즈니스용 Skype는 현재 상태, IM, 음성 및 화상 통화, 온라인 모임 등의 기능을 제공합니다. 비즈니스용 Skype는 새로운 클라이언트 환경, 새 서버 릴리스 및 Microsoft 365 또는 Office 365의 서비스에 대한 업데이트를 제공합니다. 조직의 사용자가 이미 Skype에 익숙한 경우, 비즈니스용 Skype를 쉽게 찾아서 연결할 수 있는 비즈니스용 Skype의 간편함이 도움이 될 것입니다. 조직의 사용자가 Lync에서 비즈니스용 Skype에 오고 있는 경우 이미 사용 중이지만 간소화된 컨트롤 및 새로운 추가 기능이 있는 새로운 인터페이스에서 모든 기능을 인식하게 됩니다. 비즈니스용 Skype 서버 2015는 새로운 클라이언트 환경 외에도, 몇 가지 새로운 기능을 제공 하여 관리가 프레미스 서버 및 하이브리드 솔루션의 관리 성능을 향상합니다.
  
비즈니스용 Skype 서버 2015의 새로운 기능에는 다음과 같은 향상된 기능이 포함되어 있습니다.
  
- 사용자 환경  
- 음성 및 비디오 지원
- 모바일 지원
- 프레미스 서버 관리
- 하이브리드 솔루션 배포 및 관리
- 다단계 인증 지원
    
## <a name="user-experience"></a>사용자 환경

비즈니스용 Skype 클라이언트는 소비자 버전의 Skype와 매우 유사하게 표시되어 동일한 단추와 아이콘을 사용하게 됩니다. 메뉴 수가 적고 작업 계층 구조가 간단해지기 때문에 사용자가 필요한 컨트롤과 명령을 쉽게 찾을 수 있습니다. 
  
비즈니스용 Skype에는 위에서 설명한 새로운 사용자 환경과 이전에 릴리스된 Lync 2013 사용자 환경이 포함되어 있습니다. 두 환경을 모두 포함하면 기업은 새 클라이언트 롤아웃의 프로세스 및 타이밍을 제어하여 사용자에 대한 변경을 관리할 수 있습니다. 기본 사용자 환경은 사용 하는 서버의 버전에 따라 다를 수 있습니다. 관리자는 **Set-CsClientPolicy** cmdlet을 EnableSkypeUI 매개 변수와 함께 사용하여 기본 환경을 선택할 수 있습니다. 클라이언트 환경을 구성하는 데 대한 자세한 내용은 비즈니스용 Skype 및 비즈니스용 [Skype의](deploy/deploy-clients/configure-the-client-experience.md) 데스크톱 클라이언트 기능 비교를 사용하여 클라이언트 환경 [구성을 참조하세요.](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
  
> [!NOTE]
> Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전에 대한 옵션이 아닙니다. Lync 2013 클라이언트를 사용하도록 클라이언트 환경을 구성하기 전에 클라이언트 버전을 확인하여 번호 16으로 시작하지 않는지 확인하시기 바랍니다. 예: 16.x.x.x 
  
## <a name="voice-and-video-improvements"></a>음성 및 비디오 개선

비즈니스용 Skype 서버 2015에는 통화 데이터 수집 및 분석을 비롯한 음성 및 비디오 기능이 개선되어 타사 비디오 전화 회의 시스템과의 상호 운영성이 향상되었습니다.
  
### <a name="call-data-collection-and-analysis"></a>통화 데이터 수집 및 분석

내 통화 속도 기능을 사용하면 비즈니스용 Skype 서버 2015 관리자가 통화 데이터를 수집할 수 있습니다. 이 기능은 프레미스 배포에만 사용할 수 있습니다. 사용자는 통화를 완료한 후 설문 조사를 묻는 메시지가 사용자에게 표시될 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버 [2015에서 내](manage/health-and-monitoring/rate-my-call.md)통화 평가를 참조하세요.
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>타사 비디오 원격 구성 시스템과의 상호 운영성 개선

VIS(Video Interop Server)는 비즈니스용 Skype 서버와 Cisco VTC(비디오 전화 회의) 시스템 간의 중간 역할을 합니다. 이제 사용자가 모임에 참가할 때 Cisco VTC 시스템을 선택할 수 있습니다. VIS(Video Interop Server)는온-프레미스 배포에 대한 독립 실행형 서버 역할로 구현됩니다. 자세한 내용은 비즈니스용 Skype 서버 [2015의 Video Interop 서버 계획(Plan for Video Interop Server)을 참조하세요.](plan-your-deployment/video-interop-server.md)
  
### <a name="call-via-work"></a>직장을 통한 통화

기업 사용자는 업무로 전화 기능을 통해 비즈니스용 Skype 클라이언트에서 음성 통화를 할 수 있습니다. 사용자가 음성 통화를 걸면 비즈니스용 Skype에서 원래의 PBX 또는 PSTN 전화로 라우팅됩니다. 발신자 전화에 응답하면 통화가 대상 번호로 연결됩니다. 통화 받는 사람이 응답하고 통화는 제어판으로 사용할 수 있는 비즈니스용 Skype로 설정됩니다. 발신자도 비즈니스용 Skype에서 현재 상태 및 통화 제어를 관리할 수 있습니다. 서버 관리자가 엔터프라이즈에 대해 직장 전화 기능을 사용하도록 설정하고 구성합니다. 자세한 내용은 비즈니스용 Skype 서버 [2015에서 Work를 통한 통화 계획(Plan for Call Via Work)을 참조하세요.](plan-your-deployment/enterprise-voice-solution/call-via-work.md) 
  
## <a name="mobile-device-support-improvements"></a>향상된 모바일 장치 지원

모바일 장치 지원 개선에는 대화 기록 및 로그 데이터에 대한 액세스, 향상된 모바일 모임 환경, Office 전반의 Single Sign-On 지원과 같이 Enterprise Edition 사용자의 모바일 환경을 개선하는 기능이 포함되어 있습니다. 또한 Android 지원, 성능 향상, Common App Framework를 통한 통합을 간소화하는 기능이 개선되었습니다. 
  
> [!NOTE]
> 모바일 클라이언트를 지원하려면 Lync 2013 UCWA 서버를 비즈니스용 Skype 서버 2015로 업그레이드해야 합니다. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>이제 모바일 장치에서 서버 쪽 대화 기록을 사용할 수 있습니다.

대화 기록, 부재 중 IM 및 통화 로그 데이터에 대한 모바일 액세스를 사용하도록 설정하기 위해 이 정보의 보관은 이제 모든 모바일 클라이언트에 대해 서버를 통해 처리됩니다. IM의 자동 수락 기능은 모바일 사용자가 IM에 즉시 응답하지 않는 경우 서버 시간 아웃 메시지를 방지하여 안정성을 향상시킵니다. 서버 기반 Exchange/Outlook 폴더 통합을 활용하려면 Exchange Server 2013 이상 및 업데이트된 모바일 클라이언트가 필요합니다. 
  
### <a name="enhanced-meeting-experiences"></a>향상된 모임 환경

이제 모바일 사용자도 데스크톱에서 사용할 수 있는 모임 기능을 사용할 수 있습니다. 새로운 기능에는 다음이 포함됩니다.
  
- 공유 PowerPoint 콘텐츠의 비동기 탐색
- 발표자는 공유 PowerPoint 콘텐츠를 제어할 수 있습니다.
- 참가자를 허용하거나 거부할 수 있는 발표자에 대한 대기실 관리
    
### <a name="skype-for-business-on-android-improvements"></a>Android의 비즈니스용 Skype 개선

이제 Android의 비즈니스용 Skype는 iOS의 비즈니스용 Skype와 Windows의 비즈니스용 Skype에서 사용할 수 있는 기능과 유사한 기능을 제공합니다.
  
- 대화 계속 또는 다시 참가
- 인증서 및 수동 인증 사용
- 대화에 다른 사람 초대
- 그룹 대화를 쉽게 시작할 수 있습니다.
- 비즈니스용 Skype 사용자 없이 모임에 참가
- Android 태블릿에서 스마트폰 UI 사용
- 참가자를 추가 또는 제거하여 모임 관리
    
> [!NOTE]
> 이러한 기능을 사용하려면 Android OS 버전 4.0 이상이 필요할 수 있습니다. 
  
## <a name="management-of-on-premises-servers"></a>프레미스 서버 관리

비즈니스용 Skype 서버 2015에서는 전체 업그레이드, 스마트 설치, 향상된 패치 및 업그레이드 프로세스, 향상된 프런트 엔드 풀 콜드 시작 기능, SQL Server AlwaysOn 지원 및 중앙 로깅 및 문제 해결을 비롯한 여러 가지 새로운 기능을 사용하여 전체 업그레이드의 관리 성능을 향상시킵니다.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>On-premises 서버의 인스프레미스 업그레이드

이제 기존 Lync Server 2013 하드웨어 및 서버 투자를 사용하는 새로운 전체 업그레이드 기능을 사용하여 Lync Server 2013 시스템을 비즈니스용 Skype 서버 2015로 업그레이드할 수 있어 비즈니스용 Skype 서버 2015를 배포하는 전체 비용을 줄일 수 있습니다.
  
현재 상태 업그레이드에는 두 가지 시나리오가 있습니다. 즉, 다운타임이 필요 없는 Move User 메서드와 오프라인 메서드(다운타임이 필요 없음)가 있습니다. 비즈니스에 적합한 업그레이드 절차에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015로의 업그레이드 계획(Plan to upgrade to Business Server)을 참조하세요.](plan-your-deployment/upgrade.md) 
  
> [!NOTE]
> Lync Server 2010에서 업그레이드하는 경우 현재 기능을 사용할 수 없습니다. Lync Server 2010에서 업그레이드하는 데 대한 자세한 내용은 [비즈니스용 Skype 서버 2015로 업그레이드 계획(Plan to upgrade to Business Server)을 참조하세요.](plan-your-deployment/upgrade.md) 
  
### <a name="smart-setup"></a>스마트 설치

이제 업데이트를 자동으로 검색하고 다운로드하는 스마트 설치 기능이 설치 프로그램의 일부입니다. 설치 프로세스 중에 사용자에게 설치 프로세스에서 업데이트를 확인할지 묻는 질문이 사용자에게 있습니다. 자세한 내용은 [비즈니스용 Skype 서버 2015 설치를 참조하세요.](deploy/install/install.md)
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>향상된 프런트 엔드 서버 패치 및 업그레이드 프로세스

비즈니스용 Skype 서버는 프런트 엔드 서버를 이전 버전의 Lync Server보다 훨씬 쉽게 업그레이드 또는 패치할 수 있도록 하는 두 가지 새로운 cmdlet을 도입했습니다.
  
패치를 적용하거나 다른 유지 관리 작업을 프런트 엔드 서버에 수행해야 하는 경우 **Invoke-CsComputerFailOver를** 입력하고 해당 서버의 이름을 지정하기만하면 됩니다. 비즈니스용 Skype 서버는 해당 서버의 작업을 일시적으로 풀의 다른 서버로 이동합니다. 그런 다음 유지 관리 작업을 수행한 다음 **Invoke-CsComputerFailback** cmdlet을 사용하여 해당 서버를 다시 서비스로 가져올 수 있습니다. 풀의 각 서버를 패치해야 하는 경우 각 서버에 대해 이 절차를 한 번씩 수행하면 됩니다. 이러한 새로운 cmdlet을 사용하면 이전 버전보다 훨씬 더 빠르게 서버를 패치할 수 있으며 안정성이 향상되고 워크플로가 더 간단해집니다.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>향상된 프런트 엔드 풀 콜드 시작 기능

비즈니스용 Skype 서버는 전체 프런트 엔드 풀을 콜드 시작 프로세스를 간소화하고 개선하는 새로운 cmdlet을 도입했습니다. 새 **Start-CsPool** cmdlet을 사용하면 풀에 있는 모든 프런트 엔드 서버의 선행 필요합니다. 그런 다음 각 서버를 시작하려고 시도합니다. 문제가 발생하면 이를 진단하고 세부 정보 및 해결 사항을 알리는 경고를 제공합니다. 경우에 따라 개별 서버 중 일부를 시작할 수 없는 경우에도 풀을 시작할 수 있습니다.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>SQL Server 서버에 대한 AlwaysOn 지원

비즈니스용 Skype 서버 2015는 AlwaysOn 가용성 그룹 및 SQL Server AlwaysOn 장애 조치(failover) 클러스터 SQL Server 모두에 대한 지원을 추가합니다. 이러한 기능 외에도 비즈니스용 Skype 서버는 이전 버전의 Lync Server와 SQL Server 미러링 및 데이터 클러스터링을 계속 지원하고 있습니다.
  
SQL Server AlwaysOn 가용성 그룹은 데이터베이스 미러링 대신 SQL Server 2012 및 SQL Server 2014의 고가용성 및 재해 복구 솔루션입니다. 가용성 그룹은 함께 장애 조치(failover)하는 서로 다른 데이터베이스 집합(가용성 데이터베이스)에 대한 장애 조치(failover) 환경을 지원합니다. 가용성 그룹은 읽기-쓰기 기본 데이터베이스 집합과 해당 보조 데이터베이스 집합 1-4개 집합을 지원합니다. 선택적으로 보조 데이터베이스를 읽기 전용 액세스 및 일부 백업 작업에 사용할 수 있습니다.
  
SQL Server 장애 조치(failover) 클러스터 인스턴스는 WSFC(Windows Server 장애 조치(Failover) 클러스터링) 기능을 활용하여 서버 인스턴스 수준에서 중복을 통해 로컬 고가용성을 제공합니다(FCI(장애 조치 클러스터 인스턴스). FCI는 WSFC(Windows Server 장애 조치(failover) 클러스터링) SQL Server 여러 서브넷에서 설치되는 단일 서버 인스턴스입니다.
  
자세한 내용은 비즈니스용 Skype 서버 [2015의](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)고가용성 및 재해 복구 계획을 참조하세요.
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>중앙 로깅 및 문제 해결 개선된 On-프레미스 서버

중앙 로깅 서비스는 비즈니스용 Skype 서버 2015의 기본 로깅 환경입니다. 이 릴리스에는 새로운 기능이 없지만, 서비스 및 중앙 로깅 서비스 에이전트(ClsAgent.exe)(컨트롤러와 통신하고 관리자가 실행한 명령을 받는 서비스 실행)에 대해 안정성과 성능이 개선되었습니다.
  
비즈니스용 Skype 서버 2015에서는 Windows PowerShell cmdlet을 사용하여 로깅 서비스 에이전트를 관리하고 추적을 시작하고 보고서를 생성합니다. (Lync Server 2013에서는 이러한 ClsController.exe 작업을 수행하는 데 사용했습니다.)
  
중앙 로깅 서비스는 모든 비즈니스용 Skype 서버에서 실행할 수 있습니다. 기본 제공 시나리오(미리 정의된 추적)는 사용자 지정 시나리오를 만드는 기능을 만들 때와 동일하게 유지됩니다. AlwaysOn이라는 특수한 시나리오가 항상 실행되고 있으며 관리자는 거의 실시간으로 일반적인 문제를 찾을 수 있습니다.
  
또한 모바일 로그 디버깅을 허용하도록 Snooper 디버깅 도구가 업데이트되어 Lync 2013 또는 비즈니스용 Skype 서버 2015에 연결하는 장치에서도 작동합니다. 이 도구는 디버깅 도구에서 웹 [다운로드로 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=285257)
  
## <a name="hybrid-deployment-and-management"></a>하이브리드 배포 및 관리

비즈니스용 Skype 서버 2015에서는 다음 기능을 도입하여 하이브리드 배포 관리 및 관리 기능을 사용할 수 있습니다.
  
- Office 365용 OnRamp 자동화 지원 도구에 의해 결정된 고객의 프레미스 자산 상태를 기반으로 하는 하이브리드 배포에 대한 권장 사항입니다.
- 관리자가 이러한 도구를 사용하여 하이브리드 배포를 관리할 수 있도록 비즈니스용 Skype 서버 제어판 및 비즈니스용 Skype 서버 관리 센터의 향상된 기능
- 관리자가 Microsoft 365 또는 Office 365 테넌트에 로그인하고 하이브리드 구성 마법사를 사용하여 비즈니스용 Skype Online을 사용하여 하이브리드를 설정할 수 있는 제어판의 향상된 기능입니다.
- 제어판에서는 비즈니스용 Skype Online으로의 이동 또는 비즈니스용 Skype Online 사용자를 다시 On-premises로 이동하기 위한 제어판 지원.
- 제어판 기능은 비즈니스용 Skype Online(즉, 하이브리드 사용자)으로 이동된, 해당 개체를 식별하고 필터링하는 기능입니다.
- 관리 센터 기능은 비즈니스용 Skype Online에서 처음 만든 클라우드 사용자를 식별하고, 하이브리드 사용자가 온라인에서 마이그레이션된 경우 이를 식별하고 필터링하는 기능입니다.
- 비즈니스용 Skype Online에서 관리할 수 있는 속성에 대해 제어판을 사용하여 하이브리드 사용자를 관리하는 능력 및 관리 센터에서 관리할 수 있습니다.
- DirSync와 암호 동기화를 사용하여 온-프레미스 Active Directory 암호를 온라인 테넌트와 동기화할 수 있습니다. 이 기능을 구성한 경우 페더러타 인증을 위해 AD FS를 배포할 필요가 없지만 다단계 인증에는 AD FS가 여전히 필요합니다. 
- 비즈니스용 Skype Online과 Exchange온-프레미스 간의 동시 사용에 대한 지원을 계속 제공합니다.
    
> [!NOTE]
> Lync Online 2013 및 Exchange 온-프레미스 동시성 및 지원 환경은 변경되지 않습니다. 
  
## <a name="multi-factor-authentication"></a>다단계 인증

다단계 인증은 두 개 이상의 인증 방법을 사용해야 하는 인증 방법으로, 사용자 로그인 및 트랜잭션에 중요한 두 번째 보안 계층을 추가합니다. 예를 들어 사용자 이름과 암호 및 인증서를 요구합니다. 비즈니스용 Skype 서버 2015는 Lync Server 2013 누적 업데이트에서 사용할 수 있는 다단계 인증 기능을 계속 빌드합니다. 다단계 인증은 크게 변경됩니다.
  
- Exchange 및 SharePoint와의 통합을 위해 Office 2013 SP1 Active Directory 인증 라이브러리 사용
- 비즈니스용 Skype Web App 클라이언트의 다단계 인증 기능 지원
    
비즈니스용 Skype 다단계 인증을 사용하여 이제는 지리에 따라 다른 인증 옵션을 제공할 수 있습니다. 예를 들어 고객은 내부 인증에서 Windows 통합 인증을 사용하도록 환경을 구성하고 조직 외부에서 인증하는 직원은 다단계 인증을 사용할 수 있습니다. 
  
비즈니스용 Skype 다단계 인증 환경은 다음에 관계없이 원활하게 사용할 수 있습니다.
  
- 지리적 위치 - 사용자가 조직 내부 또는 외부에서 로그인하는지 여부 
- 클라이언트/장치 유형 - 사용되는 비즈니스용 Skype 클라이언트 및 클라이언트가 실행 중인 장치(PC, 모바일, iPad 등)
- 계정 위치 - 사용자가온-프레미스 Active Directory 또는 Azure Active Directory Online에서 호스팅되어 있는지 여부.
