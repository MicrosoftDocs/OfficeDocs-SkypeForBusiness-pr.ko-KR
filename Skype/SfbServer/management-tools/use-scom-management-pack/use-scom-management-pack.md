---
title: SCOM 관리 팩을 사용하여 비즈니스용 Skype 서버 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: '요약: System Center Operations Manager에서 작동하도록 비즈니스용 Skype 서버 2015 인프라를 구성하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: cfb48338d4022c1de7c5944f66d72e58dd8b403d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814848"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>SCOM 관리 팩을 사용하여 비즈니스용 Skype 서버 관리
 
**요약:** System Center Operations Manager와 함께 작동하도록 비즈니스용 Skype 서버 2015 인프라를 구성하는 방법을 배워야 합니다.
  
이상적인 세계에서는 비즈니스용 Skype 서버 2015에 문제가 없습니다. 그러나 비즈니스용 Skype 서버는 네트워크 크래시 및 하드웨어 오류와 같은 외부 요인의 영향을 받을 수 있습니다. 비즈니스용 Skype 서버 2015 관리 팩을 사용하면 잠재적인 문제를 사전 예방적으로 식별하고 해결할 수 있습니다. 이러한 방식으로 비즈니스용 Skype 서버 2015 관리 팩은 System Center Operations Manager의 기능을 확장합니다.
  
이 정보는 비즈니스용 Skype 서버 2015 통신 소프트웨어용 모니터링 팩 버전 9319.0을 기반으로 작성되었습니다.
  
## <a name="configuration-overview"></a>구성 개요

 비즈니스용 Skype 서버 2015 인프라가 System Center Operations Manager와 함께 작동하도록 구성하려면 다음 세 가지 작업을 수행해야 합니다.
  
기본 관리 [서버를 식별하고 구성합니다.](configure-the-primary.md) 이렇게하려면 System Center Operations Manager 2012 SP1 또는 R2를 설치해야 합니다. 
  
 모니터링할 비즈니스용 Skype 서버 컴퓨터를 [식별하고 구성합니다.](configure-computers-to-monitor.md) System Center Operations Manager를 사용하여 비즈니스용 Skype 서버 컴퓨터를 모니터링하려면 System Center Operations Manager 에이전트 파일을 설치하고 프록시 역할을 하도록 각 서버를 구성해야 합니다. 
  
 감시자 [노드를 식별하고 설치 및 구성합니다.](watcher-nodes.md) 감시자 노드는 비즈니스용 Skype 서버 가상 트랜잭션을 주기적으로 실행하는 컴퓨터입니다Windows PowerShell cmdlet은 시스템에 로그온하는 능력 또는 인스턴트 메시지 교환과 같은 주요 비즈니스용 Skype 서버 구성 요소가 예상대로 작동하고 있는지를 확인하는 cmdlet입니다. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager 루트 관리 서버 및 에이전트 지원

관리 팩은 System Center Operations Manager 2007 R2(64비트)(마이그레이션에만 지원) 또는 System Center Operations Manager 2012 SP1 &amp; R2(64비트) 또는 System Center Operations Manager 2016(64비트)과 함께 사용할 수 있습니다. 다음 표에서는 비즈니스용 Skype 서버 2015의 관리 팩에 대해 지원되는 구성을 보여줍니다. 
  
|구성|지원 여부|
|:-----|:-----|
|Windows Server 2008 R2 운영 체제  <br/> Windows Server 2012 R2 운영 체제  <br/> |예. 비즈니스용 Skype 서버 2015 서버와 가상 트랜잭션 감시자 노드 둘 다.  <br/> |
|클러스터된 서버  <br/> |지원되지 않습니다.  <br/> |
|에이전트 없는 모니터링  <br/> |지원되지 않습니다.  <br/> |
|가상 환경  <br/> |예.  <br/> |
|도메인에 가입된 서버 역할  <br/> |모든 내부 비즈니스용 Skype 서버 역할은 도메인에 가입되어야 합니다.  <br/> |
|독립 실행형 서버 역할  <br/> |비즈니스용 Skype 서버 2015 에지 서버는 도메인에 가입할 필요는 없습니다.  <br/> |
|토폴로지 제한 사항  <br/> |배포의 모든 서버 역할은 동일한 Operations Manager 관리 그룹에서 모니터링해야 합니다.  <br/> |
|가상 트랜잭션 감시자 노드  <br/> |가상 트랜잭션 감시자 노드를 통해 시나리오 가용성 모니터링이 지원됩니다(추가 구성 필요). 감시자 노드는 도메인에 가입할 필요는 없습니다.  <br/> |
   
다음 표에서는 가상 트랜잭션 감시자 노드에 대한 용량 및 운영 체제 요구 사항을 보여줍니다.
  
|하드웨어 구성 요소|최소 요구 사항|
|:-----|:-----|
|CPU  <br/> |다음 중 하나여야 합니다.  <br/> 64비트 프로세서, 쿼드 코어, 2.33GHz 이상  <br/> 64비트 2웨이 프로세서, 듀얼 코어, 2.33GHz 이상  <br/> |
|메모리  <br/> |8GB  <br/> |
|운영 체제  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|네트워크  <br/> |1Gbps의 네트워크 어댑터 1개  <br/> |
   
## <a name="prerequisites"></a>필수 구성 요소

가상 트랜잭션 감시자 노드를 실행하려면 먼저 다음을 설치해야 합니다.
  
- System Center Operations Manager 에이전트 
    
-  Microsoft .NET Framework 4.5
    
- 비즈니스용 Skype 서버 핵심 설치 파일(OcsCore.msi) 및 UCMA(Unified Communications Managed API)(버전은 비즈니스용 Skype 서버 WatcherNode.msi 버전과 일치해야 합니다.)
    
## <a name="files-in-this-monitoring-pack"></a>이 모니터링 팩의 파일

비즈니스용 Skype 서버 2015용 모니터링 팩에는 다음 파일이 포함되어 있습니다.
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>새로운 기능

다음 기능은 비즈니스용 Skype 서버 2015 관리 팩의 새로운 기능입니다.

- **[2019년 9월 업데이트 변경 사항](https://www.microsoft.com/en-in/download/details.aspx?id=47364)** 일부 경고에는 특수 문자가 제거되었습니다. 경우에 따라 특수 문자가 SCOM 명령 채널 알림 기능을 방해합니다.

- **클라이언트 로그인 자동 검색** 비즈니스용 Skype 서버 2015에 로그인하는 클라이언트 응용 프로그램은 종종 로그인할 서버를 자동으로 검색합니다. 가상 트랜잭션은 이제 자동 검색이 올바르게 구성되어 있는지 확인하도록 지원됩니다.
    
- **사용자 지정된 가상 트랜잭션 실행 간격** 감시자 노드의 설정 프로세스를 간소화하기 위해 가상 트랜잭션은 사용자 계정을 공유할 수 있습니다. 이렇게 하여 충돌을 방지하기 위해 테스트를 직렬화할 때 테스트가 실행되는 빈도가 느려질 수 있습니다. 기본적으로 가상 트랜잭션은 모든 테스트를 실행할 시간을 확보하기 위해 15분마다 실행됩니다. 사용자당 더 많은 사용자 또는 더 적은 수의 테스트를 사용하기로 선택한 관리자는 이제 실행 간격도 줄일 수 있습니다.
    
- **Video Interop Services 가상 트랜잭션** 다른 공급업체 솔루션에서 비즈니스용 Skype 서버 2015로 마이그레이션하는 고객은 종종 이러한 다른 공급업체의 VTC(비디오 전화 회의 장치)를 계속 사용하길 원합니다. Video Interop Server는 고객이 비디오 SIP 트렁크를 통해 Cisco CUCM에 연결하여 회의실에서 Cisco VTC를 계속 사용할 수 있도록 하는 새로운 비즈니스용 Skype 서버 2015 서버 역할입니다. 또한 이 기능은 비디오 SIP 트렁크를 통해 비디오 Interop 서버가 설치 및 들어오는 연결을 처리할 수 있는지 확인하는 데 도움이 되는 가상 트랜잭션을 추가합니다.
    
- **응용 프로그램 공유 회의 가상 트랜잭션** 이제 응용 프로그램 공유 회의에 대한 종단 간 시나리오 유효성 검사가 지원됩니다.
    
## <a name="monitoring-scenarios"></a>모니터링 시나리오

비즈니스용 Skype 서버 2015 관리 팩은 문제를 감지하고 진단하는 데 도움이 되는 다양한 기능을 활용합니다. 이러한 기능은 비즈니스용 Skype 서버 2015 환경의 상태 정보를 실시간으로 제공합니다.
  
|모니터링 시나리오|설명|
|:-----|:-----|
|가상 트랜잭션  <br/> | Windows PowerShell cmdlet을 사용하면 로그인, 현재 상태, IM 및 회의와 같은 시나리오의 고가용성을 테스트하고 보장할 수 있습니다. <br/> 가상 트랜잭션은 엔터프라이즈 내부를 비롯한 지리적 위치, 엔터프라이즈 외부 및 지점에서 실행할 수 있습니다.  <br/> 가상 트랜잭션이 실패하면 오류의 정확한 특성을 확인할 수 있도록 HTML 로그가 만들어집니다. 여기에는 실패한 작업, 각 작업의 대기 시간, 테스트를 실행하는 데 사용된 명령줄 및 발생한 특정 오류에 대한 이해가 포함됩니다.  <br/> |
|통화 안정성 경고  <br/> |비즈니스용 Skype 서버 2015 서버에서 작성한 CDRS(통화 정보 기록)에는 사용자가 통화에 연결할 수 있는지 또는 통화가 종료되는 이유가 반영됩니다. 통화 안정성 경고는 CDR 데이터베이스를 쿼리하여 많은 수의 사용자가 피어 투 피어 통화 또는 기본 회의 기능에 대한 연결 문제를 경험하는 경우를 나타내는 경고를 생성합니다.  <br/> 시나리오 범위에는 오디오 통화, 피어 투 피어 IM(인스턴트 메시징) 및 기타 회의 기능이 포함됩니다.  <br/> |
|미디어 품질 경고  <br/> |각 통화가 끝날 때 비즈니스용 Skype 서버 2015 클라이언트가 게시한 QoE(QoE) 보고서를 보고 있는 데이터베이스 쿼리입니다. 이러한 쿼리는 사용자가 통화 및 회의 중에 미디어 품질이 손상될 가능성이 가장 높은 시나리오를 고정하는 경고를 생성합니다. 데이터는 패킷 대기 시간 및 손실과 같은 주요 메트릭을 토대하여 만들어지며 이는 사용자 환경의 품질에 직접적인 영향을 미치게 됩니다.  <br/> |
|구성 요소 상태 경고  <br/> |개별 서버 구성 요소는 이벤트 로그 및 성능 카운터를 통해 경고를 발생하여 사용자 시나리오에 큰 영향을 줄 수 있는 오류 조건을 나타냅니다. 이러한 경고는 서비스가 실행되지 않는 서비스, 높은 오류율, 높은 메시지 대기 시간 또는 연결 문제와 같은 다양한 조건을 나타냅니다.  <br/> |
|종속성 상태 모니터링  <br/> |비즈니스용 Skype 서버는 다양한 외부 이유로 실패할 수 있습니다. 관리 팩은 심각한 문제를 나타낼 수 있는 중요한 외부 종속성에 대한 데이터를 모니터링하고 수집합니다. 이러한 종속성에는 IIS(인터넷 정보 서비스) 가용성 및 비즈니스용 Skype 서버에 사용되는 서버의 CPU가 포함됩니다.  <br/> |
|||
   
### <a name="alert-prioritization"></a>경고 우선 순위

경고는 다음 범주로 분류됩니다. 
  
 **높은 우선 순위 경고:** 이러한 경고는 대규모 사용자 그룹에 대한 서비스 정전을 유발하고 즉각적인 조치가 필요한 조건을 나타냅니다. 가상 트랜잭션에서 검색된 정전 및 오프라인 서비스(예: 비즈니스용 Skype 서버 오디오/비디오 회의)는 높은 우선 순위 경고로 자격이 있습니다. 반면, 단일 컴퓨터의 구성 요소 오류는 높은 우선 순위 경고가 아니며, 비즈니스용 Skype 서버 2015에는 이러한 상황에 대한 고가용성 기능이 기본 제공되어 있습니다(예: 부하 부하를 저지르는 여러 프런트 엔드 서버).
  
 **보통 우선 순위 경고:** 이러한 알림은 사용자 하위 집합에 영향을 미치거나 통화 품질 문제를 나타내는 조건(예: 구성 요소 오류, 통화 설정 대기 시간 또는 통화의 오디오 품질 낮음)을 나타냅니다. 이 범주의 알림은 상태 상태입니다(즉, 네트워크 연결의 상태를 기반으로 경고의 특성이 변경됩니다.) 예를 들어 통화 설정 시간이 대기 시간을 나타내지만 정상 임계값으로 돌아오면 System Center Operations Manager에서 이 보통 우선 순위 경고가 자동으로 확인되면 관리자가 조치를 취할 필요가 없습니다. 자동 확인을 할 수 없는 알림은 일반적으로 같은 영업일에 관리자가 해결합니다.
  
 **기타 경고:** 이러한 경고는 특정 사용자 또는 사용자 하위 집합에 영향을 줄 수 있는 구성 요소에서 생성됩니다. 예를 들어 일반적인 경고는 주소 책 서비스가 사용자의 AD DS(Active Directory® 도메인 서비스) 항목을 구문 분석할 수 testuser@contoso.com. 관리자는 사용 가능한 시간이 될 때마다 이러한 경고를 해결할 수 있습니다.
  
### <a name="synthetic-transactions"></a>가상 트랜잭션

비즈니스용 Skype 서버 2015 관리 팩은 가상 트랜잭션을 통해 경고에 대해 더 많은 범위를 제공합니다. 가상 트랜잭션은 Windows PowerShell 관리 팩에 통합된 cmdlet을 통해 종단 내 사용자 시나리오를 테스트하는 데 사용됩니다. 가상 트랜잭션을 실행하도록 서버를 지정하면 이러한 cmdlet이 관리 팩에 의해 주기적으로 트리거됩니다. 가상 트랜잭션으로 인해 발생하는 오류는 상태 관리 경고를 생성합니다. 비즈니스용 Skype 서버 2015에 대해 지원되는 가상 트랜잭션은 다음과 같습니다.
  


|등록, 현재 상태 및 연락처에 대해 지원되는 가상 트랜잭션|||
|:-----|:-----|:-----|
|1   <br/> |등록(사용자 로그인)  <br/> |사용 가능한 Lync Server 2010 이상  <br/> |
|2   <br/> |주소부 서비스(파일 다운로드)  <br/> |사용 가능한 Lync Server 2010 이상  <br/> |
|3   <br/> |주소록 웹 쿼리  <br/> |사용 가능한 Lync Server 2010 이상  <br/> |
|4   <br/> |현재 상태  <br/> |사용 가능한 Lync Server 2010 이상  <br/> |
|5   <br/> |통합 연락처 저장소  <br/> |사용 가능한 Lync Server 2013 이상  <br/> |
||||   

|피어 투 피어 서비스에 대해 지원되는 가상 트랜잭션|||
|:-----|:-----|:-----|
|6   <br/> |피어 투 피어 인스턴트 메시징  <br/> |Lync Server 2010 이상에서 사용 가능  <br/> |
|7   <br/> |피어 투 피어 오디오 비디오  <br/> |Lync Server 2010 이상에서 사용 가능  <br/> |
|8   <br/> |MCX 피어 투 피어 인스턴트 메시지(모바일)  <br/> |Lync Server 2010의 2011년 9월 릴리스에서 비즈니스용 Skype 2015에 제공  <br/> |
 
> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.


|회의 및 영구 채팅에 대해 지원되는 가상 트랜잭션|||
|:-----|:-----|:-----|
|9   <br/> |음성 영상 회의  <br/> |Lync Server 2010 이상에서 사용 가능  <br/> |
|10    <br/> |데이터 회의  <br/> |Lync Server 2013 이상에서 사용 가능  <br/> |
|11   <br/> |인스턴트 메시지 회의  <br/> |Lync Server 2010 이상에서 사용 가능  <br/> |
|12   <br/> | 영구 채팅 <br/> |Lync Server 2013 이상에서 사용 가능  <br/> |
|13   <br/> |시작자 참가(예약된 모임)  <br/> |Lync Server 2013 이상에서 사용 가능  <br/> |
|14   <br/> |전화 접속 회의  <br/> |비즈니스용 Skype 서버 2015의 새로운  <br/> |
|15   <br/> |응용 프로그램 공유 회의  <br/> |비즈니스용 Skype 서버 2015의 새로운  <br/> |
|16   <br/> |UCWA 회의(웹 모임 참가)  <br/> |비즈니스용 Skype 서버 2015의 새로운  <br/> |
||||

|네트워크 및 파트너 종속성에 대해 지원되는 가상 트랜잭션|||
|:-----|:-----|:-----|
|17   <br/> |AV 에지 연결  <br/> |Lync Server 2013 이상에서 사용 가능  <br/> |
|18   <br/> |AV Edge 연결 Exchange 통합 메시지 연결(음성 메일)  <br/> |Lync Server 2013 이상에서 사용 가능  <br/> |
|19  <br/> |PSTN 피어 투 피어 통화  <br/> |Lync Server 2010 이상에서 사용 가능  <br/> |
|20  <br/> |XMPP 인스턴트 메시징(페더전)  <br/> |Lync Server 2013 및 비즈니스용 Skype 2015에서 사용 가능  <br/> |
| 21  <br/> |비디오 Interop 서버  <br/> |비즈니스용 Skype 서버 2015의 새로운  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>상태 롤업 방법

다음 표에는 비즈니스용 Skype 서버 모니터링 팩 개체의 상태가 표시됩니다.
  
|Management Pack 개체|설명|
|:-----|:-----|
|비즈니스용 Skype 서버 배포  <br/> |조직에서 비즈니스용 Skype 서버 2015의 배포를 나타내는 경우  <br/> |
|비즈니스용 Skype 서버 사이트  <br/> |서비스가 배포되는 다양한 지리적 위치를 나타내며,  <br/> |
|비즈니스용 Skype 서버 풀  <br/> |인스턴트 메시징 및 회의와 같은 통신 서비스를 사용자에게 제공하는 풀(사이트 내)입니다. 특정 풀에 컴퓨터 한 대만 있는 경우에도 프런트 엔드 풀, 에지 풀 및 Director 풀에 적용할 수 있습니다.  <br/> |
|비즈니스용 Skype 서버 역할  <br/> |비즈니스용 Skype 서버 서비스를 호스팅하는 서버 역할입니다.  <br/> |
|비즈니스용 Skype 서버 서비스  <br/> |특정 컴퓨터(예: 사용자의 서비스)에 배포된 기능을 fp01.contoso.com.  <br/> |
|비즈니스용 Skype 서버 구성 요소  <br/> |서비스의 구성 요소(예: 주소부 다운로드 구성 요소는 웹 서비스의 일부임)  <br/> |
|비즈니스용 Skype 서버 풀 감시자  <br/> |하나의 풀에 대해 실행되는 가상 트랜잭션의 인스턴스입니다.  <br/> |
|비즈니스용 Skype 서버 등록자 감시자  <br/> |하나의 등록자 풀에 대해 실행되는 가상 트랜잭션의 인스턴스입니다.  <br/> |
|비즈니스용 Skype 서버 사용자 서비스 풀 감시자  <br/> |하나의 User Services 풀에 대해 실행되는 가상 트랜잭션의 인스턴스입니다.  <br/> |
|비즈니스용 Skype 서버 음성 풀 감시자  <br/> |하나의 음성 풀에 대해 실행되는 가상 트랜잭션의 인스턴스입니다.  <br/> |
|비즈니스용 Skype 서버 포트 감시자  <br/> |포트 인스턴스는 한 풀에 대해 실행 중인지 검사합니다.  <br/> |
|단순 URL 감시자  <br/> |배포에서 구성된 단순 URL의 HTTPS 프로비전을 실행합니다.  <br/> |
   
![SCOM 롤업](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
비즈니스용 Skype 서버 풀에는 여러 개별 비즈니스용 Skype 서버 시스템(비즈니스용 Skype 서버 역할, 비즈니스용 Skype 서버 서비스 및 비즈니스용 Skype 서버 구성 요소 포함)이 포함될 수 있습니다. 따라서 개별 서버 또는 구성 요소의 오류는 동일한 풀의 다른 서버가 클라이언트에 응용 프로그램 서비스를 제공할 수 있기 때문에 비즈니스용 Skype 서버 풀의 전체적인 상태는 중요하지 않습니다. 상태는 비즈니스용 Skype 서버 풀에 대한 백분율 수준으로 롤업됩니다. 
  
비즈니스용 Skype 서버 풀 감시자에서 비즈니스용 Skype 서버 풀에 대해 가상 트랜잭션을 수행합니다. 다음 다이어그램과 같이 하나 이상의 가상 트랜잭션(연속 폴링 간격으로 알려진 프로세스)이 연속적으로 실패하면 위험 상태가 풀 수준(가상 트랜잭션의 최악)으로 롤업됩니다. 
  
![SCOM 롤업 연속 폴링](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>모범 사례: 사용자 지정을 위한 관리 팩 만들기

기본적으로 Operations Manager는 기본 관리 팩에 대한 오버라이드와 같은 모든 사용자 지정을 저장합니다. 최상의 방법은 사용자 지정할 봉인된 각 관리 팩에 대해 별도의 관리 팩을 만들어야 합니다. 
  
봉인된 관리 팩에 대한 사용자 지정 설정을 저장하기 위한 관리 팩을 만드는 경우 "비즈니스용 Skype 서버 2015 사용자 지정"처럼 새 관리 팩의 이름을 적절하게 지정하는 것이 좋습니다. 
  
봉인된 각 관리 팩의 사용자 지정을 저장하기 위한 새 관리 팩을 만들면 테스트 환경에서 프로덕션 환경으로 사용자 지정을 보다 쉽게 내보낼 수 있습니다. 이렇게 하면 관리 팩을 삭제하기 전에 종속성도 삭제해야 하게 되기 때문에 관리 팩을 보다 쉽게 삭제할 수 있습니다. 모든 관리 팩에 대한 사용자 지정을 기본 관리 팩에 저장하고 단일 관리 팩을 삭제해야 하는 경우 먼저 기본 관리 팩을 삭제해야 합니다. 이 경우 다른 관리 팩에 대한 사용자 지정도 삭제됩니다. 
  
## <a name="links"></a>Links

다음 링크는 모니터링 팩과 연결된 일반적인 작업에 대한 System Center 2012 연결합니다.
  
- [관리 팩 수명 주기](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Operations Manager 2012에서 관리 팩을 가져오는 방법](https://technet.microsoft.com/library/hh212691.aspx)
    
- [규칙 또는 모니터를 오버라이드하는 방법](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Operations Manager 2012에서 계정으로 실행을 만드는 방법](https://technet.microsoft.com/library/hh321655.aspx)
    
- [계정 및 프로필로 실행 관리](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Operations Manager 관리 팩을 내보내는 방법](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Operations Manager 관리 팩을 제거하는 방법](https://technet.microsoft.com/library/hh230746.aspx)
    
다음 링크는 System Center 2007 모니터링 팩과 연결된 일반적인 작업에 대한 정보로 연결됩니다.
  
- [관리 팩 수명 주기 관리](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Operations Manager 2007에서 관리 팩을 가져오는 방법](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Overrides를 사용하여 모니터링하는 방법](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Operations Manager 2007에서 계정으로 실행을 만드는 방법](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [기존 프로필로 실행을 수정하는 방법](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [관리 팩 사용자 지정을 내보내는 방법](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [관리 팩을 제거하는 방법](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Operations Manager 및 모니터링 팩에 대한 질문은 [System Center Operations Manager 커뮤니티 포럼을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkID=179635)
  
유용한 리소스는 [System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/) 블로그로, 특정 모니터링 팩에 대한 "예제" 게시물이 포함되어 있습니다.
  
Operations Manager에 대한 자세한 내용은 다음 블로그를 참조하세요. 
  
- [Operations Manager 팀 블로그](https://blogs.technet.com/momteam/default.aspx)
    
- [Kevin Holman의 OpsMgr 블로그](https://blogs.technet.com/kevinholman/default.aspx)
    
- [OpsMgr에 대한 생각](https://thoughtsonopsmgr.blogspot.com/)
    
- [Raphael Burri의 블로그](https://rburri.wordpress.com/)
    
- [BWren의 관리 공간](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Microsoft가 아닌 사이트의 모든 정보 및 콘텐츠는 웹 사이트의 소유자 또는 사용자가 제공합니다. Microsoft는 이 웹 사이트의 정보에 대해 보증, 표현, 암시적 또는 법정을 금지합니다. 
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015 관리 도구](../../management-tools/management-tools.md)
