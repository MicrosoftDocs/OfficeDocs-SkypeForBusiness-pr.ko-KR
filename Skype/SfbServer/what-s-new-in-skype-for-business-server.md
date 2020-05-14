---
title: 비즈니스용 Skype 서버 2015의 새로운 기능
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 요약:이 항목을 읽으면 비즈니스용 Skype 서버 2015의 새로운 기능에 대해 알아볼 수 있습니다. 새 클라이언트 환경에 대 한 자세한 내용은 now for the Lync to 비즈니스용 Skype--what 's new를 참조 하세요.
ms.openlocfilehash: b8d0d8334977b5367419991d1bcabba303718c89
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221088"
---
# <a name="whats-new-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 새로운 기능

**요약:** 비즈니스용 Skype 서버 2015의 새로운 기능에 대 한 자세한 내용을 보려면이 항목을 읽어 보십시오. 새 클라이언트 환경에 대 한 자세한 내용은 [now for The Lync To 비즈니스용 Skype--what 's new를 참조](https://go.microsoft.com/fwlink/p/?LinkId=529022)하세요.
  
Lync는 이제 비즈니스용 Skype, 비즈니스를 위한 커뮤니케이션 및 공동 작업 플랫폼, 그리고 Lync에서 기업 수준의 보안, 규정 준수 및 제어권을 사용 하 여 공동으로 아이디어를 얻은 환경을 제공 합니다. 비즈니스용 Skype는 현재 상태, 메신저 대화, 음성 및 화상 통화, 온라인 모임을 비롯 한 기능을 제공 합니다. 비즈니스용 Skype는 새로운 클라이언트 환경, 새 서버 릴리스 및 Microsoft 365 또는 Office 365의 서비스 업데이트를 제공 합니다. 조직의 사용자가 이미 Skype를 익숙하게 사용 하는 경우에는 비즈니스용 Skype의 강력 함과 단순성을 이해 하 고 동료와 쉽게 연결할 수 있습니다. 조직의 사용자가 Lync에서 비즈니스용 Skype로 이동할 경우에는 이미 사용 중인 모든 기능을 인식 하지만 단순화 된 컨트롤 및 새로운 추가 기능이 있는 새롭게 새롭게 제공 되는 인터페이스가 제공 됩니다. 새로운 클라이언트 환경 외에도, 비즈니스용 Skype 서버 2015에서는 온-프레미스 서버와 하이브리드 솔루션의 관리 효율성을 향상 시킬 수 있는 몇 가지 새로운 기능을 제공 합니다.
  
비즈니스용 Skype 서버 2015의 새로운 기능에는 다음과 같은 기능이 개선 되었습니다.
  
- 사용자 환경  
- 음성 및 비디오 지원
- 모바일 지원
- 온-프레미스 서버 관리
- 하이브리드 솔루션 배포 및 관리
- 다단계 인증 지원
    
## <a name="user-experience"></a>사용자 환경

비즈니스용 Skype 클라이언트는 Skype 소비자 버전과 매우 유사 하며 동일한 단추 및 아이콘을 사용 합니다. 메뉴와 flatter 작업 계층 구조가 적을수록 사용자가 필요한 컨트롤과 명령을 빠르게 찾을 수 있습니다. 
  
비즈니스용 Skype에는 위에서 설명한 새로운 사용자 환경 및 이전에 출시 된 Lync 2013 사용자 환경이 포함 되어 있습니다. 두 가지 경험을 모두 포함 하면 기업이 새 클라이언트 롤아웃 프로세스와 타이밍을 제어 하 여 사용자에 대 한 변경을 관리할 수 있습니다. 기본 사용자 환경은 사용 중인 서버의 버전에 따라 달라 집니다. 관리자는 EnableSkypeUI 매개 변수와 함께 **CsClientPolicy** cmdlet을 사용 하 여 기본 설정 환경을 선택 합니다. 클라이언트 환경을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 Skype에 대 한 Skype 및 [데스크톱 클라이언트 기능 비교](plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)를 [사용 하 여 클라이언트 환경 구성을](deploy/deploy-clients/configure-the-client-experience.md) 참조 하세요.
  
> [!NOTE]
> Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전에 대 한 옵션이 아닙니다. 클라이언트 환경에서 Lync 2013 클라이언트를 사용 하도록 구성 하기 전에 클라이언트 버전에서 번호 16으로 시작 하지 않는지 확인 하십시오. 예: x.x.x. 
  
## <a name="voice-and-video-improvements"></a>향상 된 음성 및 비디오 기능

비즈니스용 Skype 서버 2015에는 통화 데이터 수집 및 분석을 비롯 하 여 음성 및 비디오 기능이 개선 되었으며 타사 비디오 원격 대화 시스템과의 향상 된 상호 운용성이 포함 되어 있습니다.
  
### <a name="call-data-collection-and-analysis"></a>통화 데이터 수집 및 분석

내 통화 속도 기능을 사용 하면 비즈니스용 Skype 서버 2015 관리자가 통화 데이터를 수집할 수 있습니다. 이 기능은 온-프레미스 배포에만 사용할 수 있습니다. 통화를 완료 한 후 설문 조사를 수행 하 라는 메시지가 사용자에 게 표시 됩니다. 자세한 내용은 [Rate My Call In 비즈니스용 Skype 서버 2015](manage/health-and-monitoring/rate-my-call.md)을 참조 하세요.
  
### <a name="improved-interoperability-with-third-party-video-teleconferencing-systems"></a>타사 비디오 원격 대화 시스템과의 향상 된 상호 운용성

VIS (비디오 Interop 서버)는 비즈니스용 Skype 서버와 VTC (Cisco Video 원격 대화) 시스템 간의 중개 역할을 합니다. 모임에 참가할 때 사용자는 이제 Cisco VTC 시스템을 선택할 수 있습니다. VIS (동영상 Interop 서버)는 온-프레미스 배포를 위한 독립 실행형 서버 역할로 구현 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 비디오 Interop 서버 계획](plan-your-deployment/video-interop-server.md)을 참조 하십시오.
  
### <a name="call-via-work"></a>회사 번호로 전화

회사 번호로 전화 기능을 사용 하면 기업 사용자가 비즈니스용 Skype 클라이언트에서 음성 통화를 할 수 있습니다. 사용자가 음성 통화를 하는 경우 비즈니스용 Skype에서 보낸 사람의 PBX 또는 PSTN 전화로 라우팅됩니다. 주관자가 전화에 응답 하면 통화가 대상 번호로 리디렉션됩니다. 전화가 통화 되며 통화는 제어판의 비즈니스용 Skype를 사용 하 여 설정 됩니다. 발신자는 비즈니스용 Skype의 현재 상태 및 통화 제어를 관리할 수 있습니다. 서버 관리자는 회사의 회사를 통해 전화를 사용 하도록 설정 하 고 구성 합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 작업을 통한 통화 계획](plan-your-deployment/enterprise-voice-solution/call-via-work.md)을 참조 하세요. 
  
## <a name="mobile-device-support-improvements"></a>향상 된 모바일 장치 지원

모바일 장치 지원의 향상 된 기능에는 Office에서의 대화 기록 및 로그 데이터 액세스, 고급 모바일 모임 환경 및 단일 사인온 지원과 관련 하 여 Enterprise Edition 사용자의 모바일 환경을 개선 하기 위한 기능이 포함 되어 있습니다. 또한 일반적인 앱 프레임 워크를 통한 통합을 간소화 하기 위해 Android 지원, 성능 개선 및 기능이 개선 되었습니다. 
  
> [!NOTE]
> 모바일 클라이언트를 지원 하려면 Lync 2013 UPWA 서버를 비즈니스용 Skype 서버 2015로 업그레이드 해야 합니다. 
  
### <a name="server-side-conversation-history-is-now-available-on-mobile-devices"></a>이제 모바일 장치에서 서버 쪽 대화 기록을 사용할 수 있습니다.

대화 기록, 부재 중 IM 및 통화 로그 데이터에 대 한 모바일 액세스를 사용 하도록 설정 하기 위해 이제는 모든 모바일 클라이언트에 대 한 서버를 통해이 정보를 보관 합니다. IM에 대 한 자동 수락 기능은 모바일 사용자가 즉시 IM에 응답 하지 않을 때 서버 시간 초과 메시지를 차단 하 여 안정성을 향상 시킵니다. 서버 기반 Exchange/Outlook 폴더 통합, Exchange Server 2013 이상 및 업데이트 된 모바일 클라이언트를 활용 하려면 다음을 수행 해야 합니다. 
  
### <a name="enhanced-meeting-experiences"></a>향상 된 모임 환경

이제 데스크톱에서 사용할 수 있는 모임 기능을 모바일 사용자도 사용할 수 있습니다. 새로운 기능은 다음과 같습니다.
  
- 공유 PowerPoint 콘텐츠의 비동기 탐색
- 발표자가 공유 PowerPoint 콘텐츠를 제어할 수 있습니다.
- 발표자를 위한 로비 관리를 통해 참가자를 허용 하거나 거부할 수 있습니다.
    
### <a name="skype-for-business-on-android-improvements"></a>Android 향상 된 비즈니스용 Skype

Android의 비즈니스용 skype에서는 이제 iOS의 비즈니스용 Skype 및 Windows의 비즈니스용 Skype에서 사용할 수 있는 기능과 비슷한 기능을 제공 합니다.
  
- 계속 하거나 대화에 다시 참가
- 인증서 및 수동 인증을 사용 하도록 설정
- 다른 사용자에 게 대화 초대
- 쉽게 그룹 대화 시작
- 비즈니스용 Skype 사용자가 없어도 모임에 참가
- Android 태블릿에서 smartphone UI 사용
- 참석자를 추가 또는 제거 하 여 모임 관리
    
> [!NOTE]
> 이러한 기능에는 Android OS 버전 4.0 이상이 필요 합니다. 
  
## <a name="management-of-on-premises-servers"></a>온-프레미스 서버 관리

비즈니스용 Skype 서버 2015에서는 현재 위치 업그레이드, smart Setup, 향상 된 패치 및 업그레이드 프로세스, 향상 된 프런트 엔드 풀 콜드 시작 기능, SQL Server AlwaysOn 지원 및 중앙 집중식 로깅 및 문제 해결을 비롯 하 여 온-프레미스 서버의 관리 효율성을 향상 시킬 수 있는 몇 가지 새로운 기능을 제공 합니다.
  
### <a name="in-place-upgrade-for-on-premises-servers"></a>온-프레미스 서버에 대 한 전체 업그레이드

이제 Lync Server 2013 시스템을 기존 Lync Server 2013 하드웨어 및 서버 투자를 사용 하는 새로운 전체 업그레이드 기능을 사용 하 여 비즈니스용 Skype 서버 2015로 업그레이드할 수 있으므로 비즈니스용 Skype 서버 2015을 배포 하기 위한 전반적인 비용이 절감 됩니다.
  
현재 위치 업그레이드에는 사용자 이동 방법, 가동 중지 시간 및 가동 중지 시간이 필요한 오프 라인 방법의 두 가지 시나리오가 있습니다. 비즈니스에 적합 한 업그레이드 절차에 대 한 자세한 내용은 [Plan to upgrade To 비즈니스용 Skype 서버 2015](plan-your-deployment/upgrade.md)을 참조 하십시오. 
  
> [!NOTE]
> Lync Server 2010에서 업그레이드 하는 경우에는 현재 위치 옵션을 사용할 수 없습니다. Lync Server 2010에서 업그레이드 하는 방법에 대 한 자세한 내용은 [Plan to upgrade To 비즈니스용 Skype Server 2015](plan-your-deployment/upgrade.md)을 참조 하십시오. 
  
### <a name="smart-setup"></a>스마트 설정

업데이트를 자동으로 검색 하 고 다운로드 하는 스마트 설치 기능이 이제 설치 프로그램의 일부로 구성 됩니다. 설치 프로세스 중에 사용자에 게 설치 프로세스에서 업데이트를 확인 해야 하는지 묻습니다. 자세한 내용은 [비즈니스용 Skype 서버 2015](deploy/install/install.md)를 참조 하세요.
  
### <a name="improved-front-end-server-patching-and-upgrade-process"></a>향상 된 프런트 엔드 서버 패치 및 업그레이드 프로세스

비즈니스용 Skype 서버에는 이전 버전의 Lync Server 보다 훨씬 쉽게 프런트 엔드 서버를 업그레이드 하거나 패치할 수 있도록 하는 새로운 두 가지 cmdlet이 도입 되었습니다.
  
프런트 엔드 서버에 패치를 적용 하거나 다른 유지 관리 작업을 수행 해야 하는 경우에는 **Invoke-CsComputerFailOver 조치 (failover)** 를 입력 하 고 해당 서버 이름을 지정 하기만 하면 됩니다. 비즈니스용 Skype 서버는 서버의 워크 로드를 풀의 다른 서버로 일시적으로 이동 합니다. 그런 다음 유지 관리를 수행한 후에는 **CsComputerFailback** cmdlet을 사용 하 여 해당 서버를 다시 서비스를 제공할 수 있습니다. 풀의 각 서버에 패치를 적용 해야 하는 경우에는 각 서버에 대해 한 번에 하나씩이 절차를 수행 하면 됩니다. 이러한 새 cmdlet을 사용 하면 이전 버전 보다 훨씬 더 빠르게 서버를 패치 하 고 더 많은 안정성과 보다 간단한 워크플로를 사용할 수 있습니다.
  
### <a name="improved-front-end-pool-cold-start-capability"></a>향상 된 프런트 엔드 풀 콜드 시작 기능

비즈니스용 Skype 서버에는 전체 프런트 엔드 풀에 대 한 콜드 시작 프로세스를 단순화 하 고 개선 하는 새로운 cmdlet이 도입 되었습니다. 새 **시작** cmdlet을 사용 하는 경우에는 풀에 있는 모든 프런트 엔드 서버에 대 한 필수 구성 요소를 확인 한 다음 각 서버를 시작 하려고 시도 합니다. 문제가 발견 되 면 해당 문제를 진단 하 고 세부 정보 및 해결 방법을 알려 주는 경고를 생성 합니다. 일부 경우에는 개별 서버 중 일부를 시작할 수 없는 경우에도 풀을 시작 하는 데 사용할 수 있습니다.
  
### <a name="sql-server-alwayson-support-for-on-premises-servers"></a>온-프레미스 서버에 대 한 SQL Server AlwaysOn 지원

비즈니스용 Skype 서버 2015은 SQL Server AlwaysOn 가용성 그룹 및 SQL Server AlwaysOn 장애 조치 (Failover) 클러스터 인스턴스 둘 다에 대 한 지원을 추가 합니다. 이러한 기능 외에도, 비즈니스용 Skype 서버는 이전의 Lync Server 버전에서와 마찬가지로 데이터베이스 미러링 및 SQL Server 클러스터링을 계속 지원 합니다.
  
SQL Server AlwaysOn 가용성 그룹은 데이터베이스 미러링에 대 한 대체 기능을 제공 하는 SQL Server 2012 및 SQL Server 2014의 고가용성 및 재해 복구 솔루션입니다. 가용성 그룹은 장애 조치 (failover 데이터베이스 라고도 함)가 함께 작동 하는 분리 된 데이터베이스 집합에 대 한 장애 복구 환경을 지원 합니다. 가용성 그룹은 읽기/쓰기 기본 데이터베이스 집합과 해당 하는 보조 데이터베이스 집합 하나를 지원 합니다. 선택적으로 보조 데이터베이스를 읽기 전용 액세스로 설정 하 고 일부 백업 작업을 수행할 수 있습니다.
  
SQL Server 장애 조치 (failover) 클러스터 인스턴스는 WSFC (Windows Server 장애 조치 (Failover) 클러스터링) 기능을 활용 하 여 서버 인스턴스 수준 (장애 조치 (failover) 클러스터 인스턴스)에서 중복성을 통해 로컬 고가용성을 제공 합니다. FCI는 WSFC (Windows Server 장애 조치 (Failover) 클러스터링) 노드와 여러 서브넷 간에 설치 되는 단일 SQL Server 인스턴스입니다.
  
자세한 내용은 [비즈니스용 Skype 서버 2015에서 고가용성 및 재해 복구 계획](plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)을 참조 하세요.
  
### <a name="centralized-logging-and-troubleshooting-improvements-for-on-premises-servers"></a>온-프레미스 서버에 대 한 중앙 집중식 로깅 및 문제 해결 개선

중앙 로깅 서비스는 비즈니스용 Skype 서버 2015에 대 한 기본 로깅 환경입니다. 이번 릴리스의 새로운 기능은 없지만 서비스 및 중앙화 된 로깅 서비스 에이전트 (ClsAgent) 모두에 대해 안정성과 성능이 향상 되었으며, 컨트롤러와 통신 하 고 관리자가 발급 한 명령을 수신 하는 서비스 실행 파일입니다.
  
비즈니스용 Skype 서버 2015는 Windows PowerShell cmdlet을 사용 하 여 로깅 서비스 에이전트를 관리 하 고 추적을 시작 하 고 보고서를 생성 합니다. (Lync Server 2013에서는 ClsController .exe를 사용 하 여 이러한 작업을 수행 합니다.)
  
중앙 로깅 서비스는 모든 비즈니스용 Skype 서버 2015에서 실행할 수 있습니다. 기본 제공 시나리오 (미리 정의 된 추적)는 사용자 지정 시나리오를 만드는 기능과 마찬가지로 동일 하 게 유지 됩니다. AlwaysOn 이라는 특별 한 시나리오는 항상 실행 되며 관리자가 거의 실시간으로 일반적인 문제를 찾을 수 있도록 합니다.
  
또한 모바일 로그 디버깅을 허용 하도록 Snooper 디버깅 도구를 업데이트 했으며 Lync 2013 또는 비즈니스용 Skype 서버 2015에 연결 하는 장치와 함께 작동 합니다. 이 도구는 [디버깅 도구](https://go.microsoft.com/fwlink/?LinkId=285257)에서 웹으로 다운로드 하 여 사용할 수 있습니다.
  
## <a name="hybrid-deployment-and-management"></a>하이브리드 배포 및 관리

비즈니스용 Skype 서버 2015에서는 다음과 같은 기능을 도입 하 여 하이브리드 배포 관리 기능을 제공 합니다.
  
- Office 365 자동 지원 도구에 대 한 OnRamp에 따라 결정 되는 고객의 온-프레미스 자산 상태를 기반으로 하는 하이브리드 배포에 대 한 권장 사항입니다.
- 관리자가 이러한 도구를 사용 하 여 하이브리드 배포를 관리할 수 있도록 비즈니스용 Skype 서버 제어판 및 비즈니스용 Skype 서버 관리 센터의 향상 된 기능입니다.
- 관리자가 Microsoft 365 또는 Office 365 테 넌 트에 로그인 하 고 하이브리드 구성 마법사를 사용 하 여 비즈니스용 Skype Online에 하이브리드를 설정 하는 데 사용할 수 있는 제어판 기능이 향상 되었습니다.
- 제어판 지원-온-프레미스 사용자를 비즈니스용 Skype로 이동 하거나 비즈니스용 Skype Online 사용자를 온-프레미스로 다시 이동할 수 있습니다.
- 제어판 기능-온-프레미스 사용자 로부터 비즈니스용 Skype Online (즉, 하이브리드 사용자)으로 이동한 온-프레미스 사용자 개체를 식별 하 고 필터링 합니다.
- 온-프레미스에서 온라인으로 마이그레이션한 하이브리드 사용자 로부터 비즈니스용 Skype Online에서 처음 만든 클라우드 사용자를 식별 하 고 필터링 하기 위한 관리 센터 기능입니다.
- 온-프레미스에서 관리 가능한 속성에 대 한 제어판을 사용 하 여 하이브리드 사용자를 관리 하는 기능 및 비즈니스용 Skype Online에서 관리할 수 있는 속성에 대 한 관리 센터
- DirSync와 암호 동기화를 사용 하 여 온-프레미스 Active Directory 암호를 온라인 테 넌 트와 동기화 할 수 있습니다. 이 기능을 구성 하면 페더레이션 인증을 위해 AD FS를 배포할 필요가 없지만 multi-factor authentication에는 AD FS가 여전히 필요 합니다. 
- 비즈니스용 Skype 온라인 및 Exchange 온-프레미스 간의 동시 사용 지원이 계속 지원 됩니다.
    
> [!NOTE]
> Lync Online 2013와 Exchange 온-프레미스 동시 사용 및 지원 환경이 변경 되지 않습니다. 
  
## <a name="multi-factor-authentication"></a>다단계 인증

Multi-factor authentication은 두 가지 이상의 확인 방법을 사용 해야 하 고 사용자 로그인 및 트랜잭션에 중요 한 보조 보안 계층을 추가 하는 인증 방법입니다. 예를 들어 사용자 이름 및 암호와 인증서가 필요 합니다. 비즈니스용 Skype 서버 2015 Lync Server 2013 누적 업데이트에서 사용할 수 있는 다단계 인증 기능을 계속 구축 합니다. 다단계 인증이 크게 변경 되는 요소는 다음과 같습니다.
  
- Exchange 및 SharePoint와의 통합을 위해 Office 2013 SP1 Active Directory 인증 라이브러리 사용
- 비즈니스용 Skype 웹 앱 클라이언트의 multi-factor authentication 기능 지원
    
비즈니스용 Skype 다단계 인증을 사용 하는 경우 이제 지리에 따라 다양 한 인증 옵션을 제공할 수 있습니다. 예를 들어, 조직 외부에서 인증 하는 직원이 다단계 인증을 사용 하는 반면, 내부 인증을 통해 Windows 통합 인증을 사용할 수 있도록 사용자 환경을 구성 하는 것이 좋습니다. 
  
비즈니스용 Skype multi-factor authentication 경험은 다음에 관계 없이 원활 하 게 수행 됩니다.
  
- 지리적 위치-사용자가 조직 내부 또는 외부에서 로그인 하 고 있는지 여부 
- 클라이언트/장치 유형-사용 되는 비즈니스용 Skype 클라이언트 및 클라이언트에서 실행 되는 장치 (PC, 모바일, iPad 등)
- 계정 위치-사용자가 온-프레미스 Active Directory 또는 Azure Active Directory Online에 호스트 되어 있는지 여부
