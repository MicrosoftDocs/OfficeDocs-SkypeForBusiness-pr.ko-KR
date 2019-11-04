---
title: SCOM 관리 팩을 사용 하 여 비즈니스용 Skype 서버 2015 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: '요약: System Center Operations Manager와 함께 사용 하도록 비즈니스용 Skype 서버 2015 인프라를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 5622b09b3d55b4d0d3a3fe026f66b28e3c4be75e
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "36824551"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>SCOM 관리 팩을 사용 하 여 비즈니스용 Skype 서버 2015 관리
 
**요약:** System Center Operations Manager와 함께 사용 하도록 비즈니스용 Skype 서버 2015 인프라를 구성 하는 방법에 대해 알아봅니다.
  
이상적인 세상에는 비즈니스용 Skype 서버 2015에 대 한 문제가 발생 하지 않을 것입니다. 그러나 비즈니스용 Skype 서버는 외부 요인 (예: 네트워크 중단 및 하드웨어 오류)의 영향을 받을 수 있습니다. 비즈니스용 Skype Server 2015 관리 팩을 사용 하 여 잠재적인 문제를 사전에 파악 하 고 해결할 수 있습니다. 이 방법으로 비즈니스용 Skype 서버 2015 관리 팩은 System Center Operations Manager의 기능을 확장 합니다.
  
이 정보는 비즈니스용 Skype Server 2015 통신 소프트웨어용 모니터링 팩의 버전 9319.0를 기반으로 작성 되었습니다.
  
## <a name="configuration-overview"></a>구성 개요

 System Center Operations Manager와 함께 작동 하도록 비즈니스용 Skype 서버 2015 인프라를 구성 하려면 다음 세 가지 작업을 수행 해야 합니다.
  
[주 관리 서버를](configure-the-primary.md)식별 하 고 구성 합니다. 이렇게 하려면 System Center Operations Manager 2012 SP1 또는 R2를 설치 해야 합니다. 
  
 [모니터링할 비즈니스용 Skype 서버 컴퓨터](configure-computers-to-monitor.md)를 식별 하 고 구성 합니다. System Center Operations Manager를 사용 하 여 비즈니스용 Skype 서버 컴퓨터를 모니터링 하려면 System Center Operations Manager 에이전트 파일을 설치 하 고 각 서버가 프록시로 작동 하도록 구성 해야 합니다. 
  
 감시자 노드를 식별 하 고 [설치 하 고 구성](watcher-nodes.md)합니다. 감시자 노드는 비즈니스용 skype Server 가상 트랜잭션을 정기적으로 실행 하는 컴퓨터, 시스템에 로그온 하는 기능과 같은 비즈니스용 Skype 서버 구성 요소를 확인 하는 Windows PowerShell cmdlet 또는 exchange 인스턴트 키 기능을 제공 합니다. 메시지가 정상적으로 작동 합니다. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager 루트 관리 서버 및 에이전트 지원

관리 팩은 System Center Operations Manager 2007 R2 (64 비트) (마이그레이션 용도로만 지원) 또는 System center operations manager 2012 SP1 &amp; R2 (64 비트) 또는 System Center operations manager 2016 (64 비트)에서 사용할 수 있습니다. 다음 표에는 비즈니스용 Skype Server 2015의 관리 팩에 대해 지원 되는 구성이 나와 있습니다. 
  
|구성|지원?|
|:-----|:-----|
|Windows Server 2008 R2 운영 체제  <br/> Windows Server 2012 R2 운영 체제  <br/> |'. 비즈니스용 Skype 서버 2015 서버 및 가상 트랜잭션 감시자 노드 모두  <br/> |
|클러스터 된 서버  <br/> |지원 되지 않습니다.  <br/> |
|에이전트 없는 모니터링  <br/> |지원 되지 않습니다.  <br/> |
|가상 환경  <br/> |'.  <br/> |
|도메인에 가입 된 서버 역할  <br/> |모든 내부 비즈니스용 Skype 서버 2015 서버 역할은 도메인에 가입 되어 있어야 합니다.  <br/> |
|독립 실행형 서버 역할  <br/> |비즈니스용 Skype 서버 2015 Edge 서버는 도메인에 가입 하지 않아도 됩니다.  <br/> |
|토폴로지 제한 사항  <br/> |배포의 모든 서버 역할은 동일한 Operations Manager 관리 그룹에서 모니터링 해야 합니다.  <br/> |
|가상 트랜잭션 감시자 노드  <br/> |가상 트랜잭션 감시자 노드를 사용 하 여 시나리오 가용성 모니터링이 지원 됩니다 (추가 구성 필요). 감시자 노드는 도메인에 가입 하지 않아도 됩니다.  <br/> |
   
다음 표에서는 가상 트랜잭션 감시자 노드에 대 한 용량 및 운영 체제 요구 사항을 보여 줍니다.
  
|하드웨어 구성 요소|최소 요구 사항|
|:-----|:-----|
|%  <br/> |다음 중 하나입니다.  <br/> 64 비트 프로세서, 쿼드 코어, 2.33 GHz 이상  <br/> 64 비트 양방향 프로세서, 듀얼 코어, 2.33 GHz 이상  <br/> |
|Memory  <br/> |8gb  <br/> |
|운영 체제  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|사설망  <br/> |1 Gbps의 네트워크 어댑터 1 개  <br/> |
   
## <a name="prerequisites"></a>필요 조건

가상 트랜잭션 감시자 노드를 실행 하려면 먼저 다음을 설치 해야 합니다.
  
- System Center Operations Manager 에이전트 
    
-  Microsoft .NET Framework 4.5
    
- 비즈니스용 skype Server core 설치 파일 (OcsCore) 및 통합 커뮤니케이션 관리 API (버전는 비즈니스용 Skype Server WatcherNode 버전과 일치 해야 함)
    
## <a name="files-in-this-monitoring-pack"></a>이 모니터링 팩의 파일

비즈니스용 Skype Server 2015에 대 한 모니터링 팩에는 다음 파일이 포함 되어 있습니다.
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode
    
## <a name="whats-new"></a>새로운 기능

다음 기능은 비즈니스용 Skype 서버 2015 관리 팩에 새로 적용 되었습니다.

- **2019 년 [9 월 업데이트](https://www.microsoft.com/en-in/download/details.aspx?id=47364) 의 변경 사항** 일부 알림에 특수 문자가 제거 되었습니다. 일부 경우 특수 문자가 SCOM 명령 채널 알림 기능을 방해 하는 경우도 있습니다.

- **자동으로 클라이언트 로그인에 대 한 검색** 비즈니스용 Skype 서버 2015에 로그인 하는 클라이언트 응용 프로그램은 종종 로그인 할 서버를 자동으로 검색 합니다. 이제 가상 트랜잭션은 자동 검색이 올바르게 구성 되었는지 확인 하는 것을 지원 합니다.
    
- **사용자 지정 된 가상 트랜잭션 실행 간격** 감시자 노드의 설정 프로세스를 간소화 하기 위해 가상 트랜잭션은 사용자 계정을 공유할 수 있습니다. 이렇게 하면 충돌을 방지 하기 위해 테스트를 직렬화 할 때 테스트가 실행 되는 빈도가 느려집니다. 기본적으로 모든 테스트를 실행할 시간이 있는지 확인 하기 위해 가상 트랜잭션은 15 분 마다 실행 됩니다. 사용자 당 더 많은 사용자 또는 더 적은 수의 테스트를 사용 하기로 선택한 관리자는 이제 실행 간격도 줄일 수 있습니다.
    
- **비디오 Interop 서비스 가상 트랜잭션** 다른 공급 업체 솔루션에서 비즈니스용 Skype 서버 2015을 마이그레이션하는 고객은 이러한 다른 공급 업체의 VTCs (비디오 teleconferencing 장치)를 계속 사용 하고자 하는 경우가 많습니다. 비디오 Interop 서버는 고객이 비디오 SIP 트렁크를 통해 Cisco CUCM에 연결 하 여 사용자의 회의실에 Cisco VTCs을 계속 사용할 수 있도록 해 주는 새로운 비즈니스용 Skype Server 2015 서버 역할입니다. 이 기능은 또한 비디오 Interop 서버가 켜져 있는지 확인 하 고 비디오 SIP 트렁크를 통해 들어오는 연결을 처리할 수 있도록 가상 트랜잭션을 추가 합니다.
    
- **응용 프로그램 공유 회의 가상 트랜잭션** 이제 응용 프로그램 공유 회의에 대 한 종단 간 시나리오 유효성 검사가 지원 됩니다.
    
## <a name="monitoring-scenarios"></a>모니터링 시나리오

비즈니스용 Skype Server 2015 관리 팩은 문제를 감지 하 고 진단 하는 데 도움이 되는 다양 한 기능을 활용 합니다. 이러한 기능은 비즈니스용 Skype Server 2015 환경 상태에 대 한 실시간 가시성을 제공 합니다.
  
|모니터링 시나리오|설명|
|:-----|:-----|
|가상 트랜잭션  <br/> | Windows PowerShell cmdlet을 사용 하 여 로그인, 현재 상태, 메신저 대화, 사용자를 위한 회의 등의 높은 시나리오 가용성을 테스트 하는 데 도움을 줍니다. <br/> 가상 트랜잭션은 엔터프라이즈 내부 및 지사 외부의 모든 지리적 위치에서 실행할 수 있습니다.  <br/> 가상 트랜잭션에 실패 하면 정확한 오류 특성을 결정 하는 데 도움이 되도록 HTML 로그 s가 생성 됩니다. 여기에는 실패 한 작업, 각 작업의 대기 시간, 테스트를 실행 하는 데 사용 된 명령줄, 발생 한 특정 오류에 대 한 이해가 포함 됩니다.  <br/> |
|호출 안정성 알림  <br/> |비즈니스용 Skype Server 2015 서버에서 작성 한 CDRs (통화 정보 기록)는 사용자가 전화에 연결할 수 있는지 여부 또는 통화가 종료 되는 이유를 반영 합니다. 호출 안정성 알림-CDR 데이터베이스를 쿼리하여 피어 투 피어 통화 또는 기본 회의 기능에 대 한 연결 문제가 많은 사용자에 게 발생 하는 경우를 나타내는 알림을 생성 합니다.  <br/> 시나리오 검사에는 오디오 통화, 피어 투 피어 인스턴트 메시지 (IM) 및 기타 회의 기능이 포함 됩니다.  <br/> |
|미디어 품질 알림  <br/> |각 호출이 끝날 때 비즈니스용 Skype 서버 2015 클라이언트에서 게시 한 경력 (체감 품질) 보고서를 보고 하는 데이터베이스 쿼리 이러한 쿼리는 사용자가 통화와 회의 중에 손상 된 미디어 품질을 경험 하는 시나리오를 정확 하 게 알려 주는 알림을 생성 합니다. 데이터는 패킷 대기 시간, 손실 등과 같이 사용자 환경에 직접적으로 기여 하는 주요 메트릭에 따라 빌드됩니다.  <br/> |
|구성 요소 상태 알림  <br/> |개별 서버 구성 요소는 이벤트 로그 및 성능 카운터를 통해 알림을 발생 시켜 사용자 시나리오에 심각한 영향을 줄 수 있는 오류 조건을 표시 합니다. 이러한 알림은 실행 되지 않는 서비스, 높은 오류율 속도, 높은 메시지 대기 시간 또는 연결 문제 등 다양 한 조건을 나타냅니다.  <br/> |
|종속성 상태 모니터링  <br/> |비즈니스용 Skype 서버는 다양 한 외부 이유로 실패할 수 있습니다. 관리 팩은 심각한 문제점을 나타낼 수 있는 중요 외부 종속성에 대 한 데이터를 모니터링 하 고 수집 합니다. 이러한 종속성에는 비즈니스용 Skype Server에 사용 되는 IIS (인터넷 정보 서비스) 사용 가능성 및 서버의 CPU가 포함 됩니다.  <br/> |
|||
   
### <a name="alert-prioritization"></a>알림 우선 순위 지정

알림은 다음 범주로 분류 됩니다. 
  
 **우선 순위가 높은 알림:** 이러한 알림은 대규모 사용자 그룹에 대 한 서비스 중단을 초래 하 고 즉각적인 조치가 필요한 조건을 나타냅니다. 종합 거래 및 오프 라인 서비스 (예: 비즈니스용 Skype Server 오디오/비디오 회의)에서 중단을 감지 하 여 우선 순위가 높은 알림을 합니다. 반면, 단일 컴퓨터의 구성 요소 오류는 우선 순위가 높은 경고가 아닙니다. 비즈니스용 Skype 서버 2015에는 이러한 상황에 대 한 고가용성 기능 (예: 부하 분산 장치 뒤에 여러 프런트 엔드 서버)이 기본적으로 제공 됩니다.
  
 **보통 우선 순위 알림:** 이러한 알림은 사용자의 하위 집합에 영향을 주거나 통화 품질 문제 (예: 구성 요소 오류, 통화 설정의 대기 시간 설정 또는 통화에서 낮은 음질)를 표시 하는 조건을 나타냅니다. 이 범주의 경고는 상태 저장 (즉, 네트워크 연결 상태에 따라 알림 특성이 변경 됨) 예를 들어 통화 설정 시간이 대기 시간을 나타내고 표준 임계값으로 돌아가면이 보통 우선 순위 알림은 System Center Operations Manager에서 자동으로 해결 되며, 관리자가 조치를 취할 필요는 없습니다. 자동으로 해결할 수 없는 알림은 일반적으로 같은 영업일의 관리자가 처리 합니다.
  
 **기타 알림:** 이러한 알림은 특정 사용자 또는 사용자의 하위 집합에 영향을 줄 수 있는 구성 요소에서 생성 됩니다. 예를 들어 일반적인 알림은 주소록 서비스가 사용자: testuser@contoso.com에 대 한 AD DS (Active Directory® 도메인 서비스) 항목을 구문 분석할 수 없는 것입니다. 관리자는 사용할 수 있는 시간이 있을 때마다 이러한 알림을 해결할 수 있습니다.
  
### <a name="synthetic-transactions"></a>가상 트랜잭션

비즈니스용 Skype Server 2015 관리 팩은 종합 트랜잭션을 통해 알림에 대 한 향상 된 범위를 제공 합니다. 가상 트랜잭션은 Operations Manager 관리 팩에 통합 된 Windows PowerShell cmdlet을 사용 하 여 엔드 투 엔드 사용자 시나리오를 테스트 합니다. 가상 트랜잭션을 실행 하도록 서버를 지정 하면 관리 팩에서 이러한 cmdlet이 정기적으로 트리거됩니다. 가상 트랜잭션에서 발생 한 오류로 인해 상태 저장 경고가 생성 됩니다. 다음은 비즈니스용 Skype 서버 2015에 대해 지원 되는 가상 트랜잭션입니다.
  


|등록, 현재 상태, 대화 상대에 대해 지원 되는 가상 트랜잭션|||
|:-----|:-----|:-----|
|raid-1  <br/> |등록 (사용자 로그인)  <br/> |사용할 수 있는 Lync Server 2010 이상  <br/> |
|2  <br/> |주소록 서비스 (파일 다운로드)  <br/> |사용할 수 있는 Lync Server 2010 이상  <br/> |
|3-4  <br/> |주소록 웹 쿼리  <br/> |사용할 수 있는 Lync Server 2010 이상  <br/> |
|4(tcp/ipv4)  <br/> |늘어  <br/> |사용할 수 있는 Lync Server 2010 이상  <br/> |
|5mb  <br/> |통합 된 대화 상대 저장소  <br/> |사용할 수 있는 Lync Server 2013 이상  <br/> |
||||   

|피어 투 피어 서비스에 지원 되는 가상 트랜잭션|||
|:-----|:-----|:-----|
|26  <br/> |피어 투 피어 인스턴트 메시지  <br/> |Lync Server 2010 이상에서 사용할 수 있는 기능  <br/> |
|7  <br/> |피어 투 피어 오디오 비디오  <br/> |Lync Server 2010 이상에서 사용할 수 있는 기능  <br/> |
|20cm(8  <br/> |MCX 피어 투 피어 인스턴트 메시지 (모바일)  <br/> |Lync Server 2010의 2011 년 9 월에 Skype for Business 2015의 출시를 제공 합니다.  <br/> |
 
> [!NOTE]
> 이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다. 현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다. MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.


|회의 및 영구 채팅을 위해 지원 되는 가상 거래|||
|:-----|:-----|:-----|
|되었는지  <br/> |오디오 영상 회의  <br/> |Lync Server 2010 이상에서 사용할 수 있는 기능  <br/> |
|1천만  <br/> |데이터 회의  <br/> |Lync Server 2013 이상에서 사용할 수 있는 기능  <br/> |
|mb  <br/> |인스턴트 메시지 회의  <br/> |Lync Server 2010 이상에서 사용할 수 있는 기능  <br/> |
|까지  <br/> | 영구 채팅 <br/> |Lync Server 2013 이상에서 사용할 수 있는 기능  <br/> |
|일자  <br/> |참가 시작 관리자 (예약 된 모임)  <br/> |Lync Server 2013 이상에서 사용할 수 있는 기능  <br/> |
|13  <br/> |전화 회의  <br/> |비즈니스용 Skype 서버 2015의 새로운 방법  <br/> |
|~  <br/> |응용 프로그램 공유 회의  <br/> |비즈니스용 Skype 서버 2015의 새로운 방법  <br/> |
|16  <br/> |(웹 모임 참가)  <br/> |비즈니스용 Skype 서버 2015의 새로운 방법  <br/> |
||||

|네트워크 및 파트너 종속성에 대해 지원 되는 가상 트랜잭션|||
|:-----|:-----|:-----|
|17@@  <br/> |AV Edge 연결  <br/> |Lync Server 2013 이상에서 사용할 수 있는 기능  <br/> |
|awg  <br/> |AV Edge 연결 Exchange 통합 메시지 연결 (보이스 메일)  <br/> |Lync Server 2013 이상에서 사용할 수 있는 기능  <br/> |
|인치  <br/> |PSTN 피어 투 피어 통화  <br/> |Lync Server 2010 이상에서 사용할 수 있는 기능  <br/> |
|명  <br/> |XMPP 인스턴트 메시지 (페더레이션)  <br/> |Lync Server 2013 및 비즈니스용 Skype 2015에서 사용 가능  <br/> |
|mb  <br/> |비디오 Interop 서버  <br/> |비즈니스용 Skype 서버 2015의 새로운 방법  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>상태가 롤업되는 방법

다음 표에서는 비즈니스용 Skype 서버 모니터링 팩의 개체 상태를 보여 줍니다.
  
|관리 팩 개체|설명|
|:-----|:-----|
|비즈니스용 Skype 서버 배포  <br/> |조직의 비즈니스용 Skype 서버 2015 배포를 나타냅니다.  <br/> |
|비즈니스용 Skype 서버 사이트  <br/> |서비스가 배포 되는 다른 지리적 위치를 나타냅니다.  <br/> |
|비즈니스용 Skype 서버 풀  <br/> |인스턴트 메시징 및 회의와 같은 통신 서비스를 사용자에 게 제공 하는 풀 (사이트 내)입니다. 지정 된 풀에 하나의 컴퓨터만 있는 경우에도 프런트 엔드 풀, Edge 풀 및 디렉터 풀에 적용 됩니다.  <br/> |
|비즈니스용 Skype 서버 역할  <br/> |비즈니스용 Skype 서버 서비스를 호스트 하는 서버 역할.  <br/> |
|비즈니스용 Skype 서버 서비스  <br/> |특정 컴퓨터에 배포 된 기능을 나타냅니다 (예: fp01.contoso.com의 사용자 서비스).  <br/> |
|비즈니스용 Skype 서버 구성 요소  <br/> |서비스의 구성 요소 (예: 주소록 다운로드 구성 요소는 웹 서비스의 일부)입니다.  <br/> |
|비즈니스용 Skype 서버 풀 감시자  <br/> |하나의 풀에 대해 실행 되는 가상 트랜잭션의 인스턴스입니다.  <br/> |
|비즈니스용 Skype Server 등록자 감시자  <br/> |하나의 등록자 풀에 대해 실행 되는 가상 트랜잭션의 인스턴스입니다.  <br/> |
|비즈니스용 Skype 서버 사용자 서비스 풀 감시자  <br/> |하나의 사용자 서비스 풀에 대해 실행 되는 가상 트랜잭션의 인스턴스입니다.  <br/> |
|비즈니스용 Skype 서버 음성 풀 감시자  <br/> |하나의 음성 풀에 대해 실행 되는 가상 트랜잭션의 인스턴스입니다.  <br/> |
|비즈니스용 Skype 서버 포트 감시자  <br/> |하나의 풀에 대해 실행 되는 포트 검사의 인스턴스입니다.  <br/> |
|간단한 URL 감시자  <br/> |배포에서 구성 된 단순 Url의 HTTPS 검색을 수행 합니다.  <br/> |
   
![SCOM 롤업](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
비즈니스용 skype 서버 풀에는 비즈니스용 skype 서버 시스템을 여러 개 포함할 수 있으며 (비즈니스를 위한 Skype Server 역할, 비즈니스용 skype server 서비스, 비즈니스용 Skype 서버 구성 요소)가 있습니다. 따라서 같은 풀에 있는 다른 서버에서 클라이언트에 응용 프로그램 서비스를 제공할 수 있으므로 개별 서버 또는 구성 요소에 대 한 장애는 비즈니스용 Skype 서버 풀의 전반적인 상태에 덜 중요 합니다. 상태는 비즈니스용 Skype 서버 풀에 대해 백분율 수준으로 롤업 됩니다. 
  
비즈니스용 Skype 서버 풀 감시자는 비즈니스용 Skype Server 풀에 대해 종합 트랜잭션을 수행 합니다. 하나 이상의 가상 트랜잭션 (연속 폴링 간격 이라고 함)의 연속적인 오류는 다음 다이어그램에 표시 된 것 처럼 풀 수준 (가상 트랜잭션의 최하위)에 대 한 위험 상태를 롤업 합니다. 
  
![SCOM 롤업 연속 폴링](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>모범 사례: 사용자 지정을 위한 관리 팩 만들기

기본적으로 Operations Manager는 재정의 등의 모든 사용자 지정을 기본 관리 팩에 저장 합니다. 가장 좋은 방법은 사용자 지정 하려는 봉인 된 관리 팩에 대해 별도의 관리 팩을 만들어야 한다는 것입니다. 
  
봉인 된 관리 팩에 대 한 사용자 지정 설정을 저장 하기 위한 관리 팩을 만들 때 "비즈니스용 Skype Server 2015 사용자 지정"과 같이 새 관리 팩의 이름을 적절 하 게 지정 하는 것이 좋습니다. 
  
각 봉인 된 관리 팩의 사용자 지정을 저장 하기 위한 새 관리 팩을 만들면 테스트 환경에서 프로덕션 환경으로 사용자 지정을 손쉽게 내보낼 수 있습니다. 이렇게 하면 관리 팩을 삭제 하기 전에 종속성을 삭제 해야 하므로 관리 팩을 더 쉽게 삭제할 수 있습니다. 모든 관리 팩에 대 한 사용자 지정을 기본 관리 팩에 저장 하 고 단일 관리 팩을 삭제 해야 하는 경우 먼저 기본 관리 팩을 삭제 한 후에 다른 관리 팩에 대 한 사용자 지정도 삭제 해야 합니다. 
  
## <a name="links"></a>링크

다음 링크를 사용 하 여 System Center 2012 모니터링 팩과 연결 된 일반적인 작업에 대 한 정보로 연결 합니다.
  
- [관리 팩 수명 주기](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [Operations Manager 2012에서 관리 팩을 가져오는 방법](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [규칙 또는 모니터를 재정의 하는 방법](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [Operations Manager 2012에서 실행 계정을 만드는 방법](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [실행 계정 및 프로필 관리](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [Operations Manager 관리 팩을 내보내는 방법](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [Operations Manager 관리 팩을 제거 하는 방법](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
다음 링크를 사용 하 여 System Center 2007 모니터링 팩과 연결 된 일반적인 작업에 대 한 정보로 연결 합니다.
  
- [관리 팩 수명 주기 관리](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Operations Manager 2007에서 관리 팩을 가져오는 방법](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [재정의 사용을 모니터링 하는 방법](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Operations Manager 2007에서 실행 계정을 만드는 방법](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [기존 실행 프로필을 수정 하는 방법](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [관리 팩 사용자 지정을 내보내는 방법](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [관리 팩을 제거 하는 방법](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Operations Manager 및 모니터링 팩에 대 한 질문은 [System Center Operations Manager 커뮤니티 포럼](https://go.microsoft.com/fwlink/p/?LinkID=179635)을 참조 하세요.
  
유용한 리소스는 특정 모니터링 팩에 대 한 "예" 게시를 포함 하는 [System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/) 블로그입니다.
  
Operations Manager에 대 한 추가 정보는 다음 블로그를 참조 하세요. 
  
- [Operations Manager 팀 블로그](https://blogs.technet.com/momteam/default.aspx)
    
- [Kevin Holman의 OpsMgr 블로그](https://blogs.technet.com/kevinholman/default.aspx)
    
- [OpsMgr의 생각](https://thoughtsonopsmgr.blogspot.com/)
    
- [Raphael 삼 부 리의 블로그](https://rburri.wordpress.com/)
    
- [BWren의 관리 공간](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> 타사 사이트의 모든 정보와 콘텐츠는 소유자나 웹 사이트의 사용자가 제공 합니다. Microsoft는이 웹사이트의 정보에 대 한 명시적, 묵시적 또는 법률적 보증도 하지 않습니다. 
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015 관리 도구](../../management-tools/management-tools.md)
