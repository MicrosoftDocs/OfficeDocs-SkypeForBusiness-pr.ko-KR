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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: '요약: System Center Operations Manager와 함께 작동 하도록 비즈니스용 Skype 서버 2015 인프라를 구성 하는 방법을 알아봅니다.'
ms.openlocfilehash: 06297ba7e0ab70e7046fc2f3db189275cc90f9d4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005943"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>SCOM 관리 팩을 사용 하 여 비즈니스용 Skype 서버 2015 관리
 
**요약:** System Center Operations Manager와 함께 작동 하도록 비즈니스용 Skype 서버 2015 인프라를 구성 하는 방법을 알아봅니다.
  
이상적인 세상에서 비즈니스용 Skype 서버 2015에 문제가 발생 하지 않습니다. 그러나 비즈니스용 Skype 서버는 외부 요인 (예: 네트워크 중단 및 하드웨어 오류)의 영향을 받을 수 있습니다. 비즈니스용 Skype 서버 2015 관리 팩을 사용 하 여 잠재적 문제를 사전에 파악 하 고 해결할 수 있습니다. 이런 식으로 비즈니스용 Skype 서버 2015 관리 팩은 System Center Operations Manager의 기능을 확장 합니다.
  
이 정보는 비즈니스용 Skype 서버 2015 통신 소프트웨어용 모니터링 팩의 버전 9319.0을 기반으로 작성 되었습니다.
  
## <a name="configuration-overview"></a>구성 개요

 System Center Operations Manager와 함께 작동 하도록 비즈니스용 Skype 서버 2015 인프라를 구성 하려면 다음 세 가지 작업을 수행 해야 합니다.
  
[기본 관리 서버를](configure-the-primary.md)식별 하 고 구성 합니다. 이 작업을 수행 하려면 System Center Operations Manager 2012 SP1 또는 s p 1을 설치 해야 합니다. 
  
 [모니터링할 비즈니스용 Skype 서버 컴퓨터를](configure-computers-to-monitor.md)식별 하 고 구성 합니다. System Center Operations Manager를 사용 하 여 비즈니스용 Skype 서버 컴퓨터를 모니터링 하려면 System Center Operations Manager 에이전트 파일을 설치 하 고 각 서버가 프록시로 작동 하도록 구성 해야 합니다. 
  
 감시자 노드를 식별 하 고 [설치 하 고 구성](watcher-nodes.md)합니다. 감시자 노드는 비즈니스용 Skype 서버 가상 트랜잭션을 주기적으로 실행 하는 컴퓨터로, 시스템에 로그온 하는 기능과 같은 비즈니스용 Skype 서버 구성 요소를 확인 하는 Windows PowerShell cmdlet, 즉 exchange 인스턴트를 교환 하는 기능입니다. 메시지가 정상적으로 작동 합니다. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager 루트 관리 서버 및 에이전트 지원

관리 팩은 System Center Operations Manager 2007 R2 (64 비트) (마이그레이션 목적 으로만 지원 됨) 또는 System center Operations manager 2012 SP1 &amp; R2 (64 비트) 또는 System Center operations manager 2016 (64 비트)와 함께 사용할 수 있습니다. 다음 표에는 비즈니스용 Skype 서버 2015의 관리 팩에 대해 지원 되는 구성이 나와 있습니다. 
  
|구성|지원?|
|:-----|:-----|
|Windows Server 2008 R2 운영 체제  <br/> Windows Server 2012 R2 운영 체제  <br/> |예. 둘 다 비즈니스용 Skype 서버 2015 서버 및 가상 트랜잭션 감시자 노드  <br/> |
|클러스터 된 서버  <br/> |지원되지 않습니다.  <br/> |
|에이전트 없는 모니터링  <br/> |지원되지 않습니다.  <br/> |
|가상 환경  <br/> |예.  <br/> |
|도메인에 가입 된 서버 역할  <br/> |모든 내부 비즈니스용 Skype 서버 2015 서버 역할은 도메인에 가입 되어 있어야 합니다.  <br/> |
|독립 실행형 서버 역할  <br/> |비즈니스용 Skype 서버 2015에 지 서버는 도메인에 가입 하지 않아도 됩니다.  <br/> |
|토폴로지 제한 사항  <br/> |배포의 모든 서버 역할은 동일한 Operations Manager 관리 그룹에서 모니터링 해야 합니다.  <br/> |
|가상 트랜잭션 감시자 노드  <br/> |가상 트랜잭션 감시자 노드를 사용 하 여 시나리오 가용성 모니터링이 지원 됩니다 (추가 구성 필요). 감시자 노드는 도메인에 가입 하지 않아도 됩니다.  <br/> |
   
다음 표에서는 가상 트랜잭션 감시자 노드에 대 한 용량 및 운영 체제 요구 사항을 보여 줍니다.
  
|하드웨어 구성 요소|최소 요구 사항|
|:-----|:-----|
|CPU  <br/> |다음 중 하나여야 합니다.  <br/> 64 비트 프로세서, 쿼드 코어, 2.33 GHz 이상  <br/> 64 비트 2 방향 프로세서, 듀얼 코어, 2.33 GHz 이상  <br/> |
|메모리  <br/> |8GB  <br/> |
|운영 체제  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|네트워크  <br/> |1 Gbps의 네트워크 어댑터 1 개  <br/> |
   
## <a name="prerequisites"></a>필수 구성 요소

가상 트랜잭션 감시자 노드를 실행 하려면 먼저 다음을 설치 해야 합니다.
  
- System Center Operations Manager 에이전트 
    
-  Microsoft .NET Framework 4.5
    
- 비즈니스용 skype 서버 코어 설치 파일 (OcsCore .msi) 및 통합 커뮤니케이션 관리 API (버전은 비즈니스용 Skype 서버 Watchernode.msi executable 버전과 일치 해야 함)
    
## <a name="files-in-this-monitoring-pack"></a>이 모니터링 팩의 파일

비즈니스용 Skype 서버 2015에 대 한 모니터링 팩에는 다음 파일이 포함 됩니다.
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- Watchernode.msi executable
    
## <a name="whats-new"></a>새로운 기능

다음은 비즈니스용 Skype 서버 2015 관리 팩에 새로 제공 되는 기능입니다.

- **2019 년 [9 월 업데이트](https://www.microsoft.com/en-in/download/details.aspx?id=47364) 변경** 일부 경고에 특수 문자가 제거 되었습니다. 특수 문자가 SCOM 명령 채널 알림 기능을 방해 하는 경우도 있습니다.

- **클라이언트 로그인에 대 한 자동 검색** 비즈니스용 Skype 서버 2015에 로그인 하는 클라이언트 응용 프로그램은 로그인 할 서버를 자동으로 검색 하기도 합니다. 이제 가상 트랜잭션은 자동 검색이 제대로 구성 되었는지 확인 하는 것을 지원 합니다.
    
- **사용자 지정 된 가상 트랜잭션 실행 간격** 감시자 노드의 설정 프로세스를 간소화 하기 위해 가상 트랜잭션은 사용자 계정을 공유할 수 있습니다. 따라서 충돌이 발생 하지 않도록 테스트를 직렬화 할 때 테스트가 실행 되는 빈도가 저하 됩니다. 기본적으로 가상 트랜잭션은 15 분 마다 실행 되므로 모든 테스트의 실행이 시간을 확인할 수 있습니다. 사용자 당 더 많은 사용자 또는 더 작은 테스트를 사용 하도록 선택 하는 관리자는 이제 실행 간격도 줄일 수 있습니다.
    
- **비디오 Interop 서비스 가상 트랜잭션** 다른 공급 업체 솔루션에서 비즈니스용 Skype 서버 2015로 마이그레이션하는 고객은 대개 이러한 다른 공급 업체의 VTCs (video 원격 대화 devices)를 계속 사용 하려고 합니다. Video Interop Server는 고객이 비디오 SIP 트렁크를 통해 Cisco 위한 CUCM에 연결 하 여 회의실에서 Cisco VTCs를 계속 사용할 수 있게 해 주는 새로운 비즈니스용 Skype 서버 2015 서버 역할입니다. 또한이 기능은 비디오 Interop 서버가 작동 하 고 비디오 SIP 트렁크를 통해 들어오는 연결을 처리할 수 있는지 확인 하는 데 도움이 되는 가상 트랜잭션도 추가 합니다.
    
- **응용 프로그램 공유 회의 가상 트랜잭션** 이제 응용 프로그램 공유 회의에 대 한 종단 간 시나리오 유효성 검사가 지원 됩니다.
    
## <a name="monitoring-scenarios"></a>모니터링 시나리오

비즈니스용 Skype 서버 2015 관리 팩은 문제를 감지 하 고 진단 하는 데 도움이 되는 다양 한 기능을 활용 합니다. 이러한 기능은 비즈니스용 Skype 서버 2015 환경의 상태를 실시간으로 확인할 지를 제공 합니다.
  
|모니터링 시나리오|설명|
|:-----|:-----|
|가상 트랜잭션  <br/> | Windows PowerShell cmdlet을 사용 하 여 로그인, 현재 상태, IM 및 사용자 회의와 같은 시나리오의 고가용성을 확인 하 고 확인할 수 있습니다. <br/> 가상 트랜잭션은 기업 외부, 지사 및 지사의 모든 지리적 위치에서 실행할 수 있습니다.  <br/> 가상 트랜잭션이 실패 하면 정확한 오류 특성을 결정 하는 데 도움이 되도록 HTML 로그 s가 만들어집니다. 여기에는 실패 한 작업, 각 작업의 대기 시간, 테스트를 실행 하는 데 사용한 명령줄 및 발생 한 특정 오류에 대 한 이해가 포함 됩니다.  <br/> |
|통화 안정성 알림  <br/> |비즈니스용 Skype 서버에서 작성 된 CDRs (통화 정보 기록) 2015 서버는 사용자가 통화에 연결할 수 있는지 여부 또는 통화가 종료 되는 이유를 반영 합니다. Call 안정성 경고 CDR 데이터베이스를 쿼리하여 많은 사용자가 피어 투 피어 통화 또는 기본 회의 기능에 대해 연결에 문제가 발생 하는 경우를 나타내는 경고를 생성 합니다.  <br/> 시나리오 검사에는 오디오 통화, 피어 투 피어 IM (인스턴트 메시징) 및 기타 회의 기능이 포함 되어 있습니다.  <br/> |
|미디어 품질 경고  <br/> |각 통화를 마칠 때 비즈니스용 Skype 서버 2015 클라이언트에서 게시 한 QoE (품질 화질) 보고서를 확인 하는 데이터베이스 쿼리 이러한 쿼리는 사용자가 통화 및 전화 회의 중에 손상 된 미디어 품질을 경험할 가능성이 높은 시나리오를 나타내는 경고를 생성 합니다. 데이터는 패킷 대기 시간, 손실 등의 주요 메트릭에 기반 하 여 사용자 환경에 직접적으로 기여 합니다.  <br/> |
|구성 요소 상태 알림  <br/> |개별 서버 구성 요소는 이벤트 로그 및 성능 카운터를 통해 경고를 발생 시켜 사용자 시나리오에 심각한 영향을 줄 수 있는 오류 조건을 나타냅니다. 이러한 경고는 실행 되지 않는 서비스, 높은 오류율, 높은 메시지 대기 시간 또는 연결 문제 등의 다양 한 조건을 나타냅니다.  <br/> |
|종속성 상태 모니터링  <br/> |비즈니스용 Skype 서버가 다양 한 외부 이유로 인해 실패할 수 있습니다. 관리 팩은 심각한 문제를 표시할 수 있는 중요 외부 종속성에 대 한 데이터를 모니터링 하 고 수집 합니다. 이러한 종속성에는 비즈니스용 Skype 서버에 사용 되는 IIS (인터넷 정보 서비스) 가용성 및 서버의 CPU가 포함 됩니다.  <br/> |
|||
   
### <a name="alert-prioritization"></a>경고 우선 순위 지정

경고는 다음 범주로 분류 됩니다. 
  
 **높은 우선 순위 경고:** 이러한 경고는 대규모 사용자 그룹에 대 한 서비스 중단을 야기 하 고 즉각적인 조치를 요하는 조건을 나타냅니다. 가상 트랜잭션과 오프 라인 서비스 (예: 비즈니스용 Skype 서버 오디오/비디오 회의)에서 발생 한 중단은 우선 순위가 높은 경고로 한정 됩니다. 반면 단일 컴퓨터의 구성 요소 오류는 높은 우선 순위 경고가 아닙니다. 비즈니스용 Skype 서버 2015에는 이러한 상황 (예: 부하 분산 장치에는 여러 프런트 엔드 서버)에 대 한 고가용성 기능이 기본적으로 제공 됩니다.
  
 **중간 우선 순위 경고:** 이러한 경고는 사용자 하위 집합에 영향을 주거나 통화 품질에 문제를 표시 하는 조건 (예: 구성 요소 오류, 통화 설정의 대기 시간 또는 통화 중 낮은 오디오 품질)을 나타냅니다. 이 범주의 경고는 상태 저장 (즉, 네트워크 연결 상태에 따라 경고의 특성이 변경 됨)입니다. 예를 들어 통화 설정 시간이 대기 시간을 나타내는 경우 정상 임계값으로 돌아가면 System Center Operations Manager에서이 중간 우선 순위 경고가 자동으로 확인 되며 관리자가 작업을 수행할 필요가 없습니다. 자동으로 해결할 수 없는 경고는 일반적으로 당일 관리자가 해결 합니다.
  
 **기타 알림:** 이러한 알림은 특정 사용자 또는 사용자 하위 집합에 영향을 줄 수 있는 구성 요소에서 생성 됩니다. 예를 들어, 주소록 서비스가 사용자: testuser@contoso.com에 대 한 AD DS (Active Directory® 도메인 서비스) 항목을 구문 분석할 수 없는 것이 일반적인 알림입니다. 관리자는 사용할 수 있는 시간이 있을 때마다 이러한 알림을 처리할 수 있습니다.
  
### <a name="synthetic-transactions"></a>가상 트랜잭션

비즈니스용 Skype 서버 2015 관리 팩은 가상 트랜잭션을 통한 경고에 대 한 향상 된 수신 범위를 제공 합니다. 가상 트랜잭션은 Operations Manager 관리 팩에 통합 된 Windows PowerShell cmdlet을 사용 하 여 종단 간 사용자 시나리오를 테스트 합니다. 가상 트랜잭션을 실행 하도록 서버를 지정 하는 경우 이러한 cmdlet은 관리 팩에 의해 주기적으로 트리거됩니다. 가상 트랜잭션에서 발생 한 오류로 인해 상태 저장 경고가 생성 됩니다. 비즈니스용 Skype 서버 2015에 대해 지원 되는 가상 트랜잭션은 다음과 같습니다.
  


|등록, 현재 상태 및 대화 상대에 대해 지원 되는 가상 트랜잭션|||
|:-----|:-----|:-----|
|1   <br/> |등록 (사용자 로그인)  <br/> |사용 가능한 Lync Server 2010 이상  <br/> |
|2   <br/> |주소록 서비스 (파일 다운로드)  <br/> |사용 가능한 Lync Server 2010 이상  <br/> |
|3   <br/> |주소록 웹 쿼리  <br/> |사용 가능한 Lync Server 2010 이상  <br/> |
|4   <br/> |이들의  <br/> |사용 가능한 Lync Server 2010 이상  <br/> |
|5   <br/> |통합 연락처 저장소  <br/> |사용 가능한 Lync Server 2013 이상  <br/> |
||||   

|피어-투-피어 서비스에 대해 지원 되는 가상 트랜잭션|||
|:-----|:-----|:-----|
|6   <br/> |피어 투 피어 인스턴트 메시징  <br/> |Lync Server 2010 이상에서 사용 가능  <br/> |
|7   <br/> |피어 투 피어 오디오 비디오  <br/> |Lync Server 2010 이상에서 사용 가능  <br/> |
|8   <br/> |MCX 피어 투 피어 인스턴트 메시지 (모바일)  <br/> |Lync Server 2010에서 비즈니스용 Skype 2015의 9 월 2011 릴리스를 사용할 수 있습니다.  <br/> |
 
> [!NOTE]
> 이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 현재 모든 비즈니스용 Skype 모바일 클라이언트는 IM (인스턴트 메시징), 현재 상태 및 연락처를 지원 하기 위해 이미 통합 커뮤니케이션 웹 API (c)를 사용 합니다. MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.


|회의 및 영구 채팅에 대해 지원 되는 가상 트랜잭션|||
|:-----|:-----|:-----|
|9   <br/> |오디오 비디오 회의  <br/> |Lync Server 2010 이상에서 사용 가능  <br/> |
|10   <br/> |데이터 회의  <br/> |Lync Server 2013 이상에서 사용 가능  <br/> |
|11   <br/> |인스턴트 메시지 회의  <br/> |Lync Server 2010 이상에서 사용 가능  <br/> |
|12   <br/> | 영구 채팅 <br/> |Lync Server 2013 이상에서 사용 가능  <br/> |
|-1  <br/> |참가 시작 관리자 (예약 된 모임)  <br/> |Lync Server 2013 이상에서 사용 가능  <br/> |
|14   <br/> |전화 회의  <br/> |비즈니스용 Skype 서버 2015의 새로운 사항  <br/> |
|15   <br/> |응용 프로그램 공유 회의  <br/> |비즈니스용 Skype 서버 2015의 새로운 사항  <br/> |
|16   <br/> |WA 전화 회의 (웹 모임 참가)  <br/> |비즈니스용 Skype 서버 2015의 새로운 사항  <br/> |
||||

|네트워크 및 파트너 종속성에 대해 지원 되는 가상 트랜잭션|||
|:-----|:-----|:-----|
|17   <br/> |AV에 지 연결  <br/> |Lync Server 2013 이상에서 사용 가능  <br/> |
|18   <br/> |AV에 지 Connectivity Exchange 통합 메시지 연결 (음성 메일)  <br/> |Lync Server 2013 이상에서 사용 가능  <br/> |
|인치  <br/> |PSTN 피어 투 피어 통화  <br/> |Lync Server 2010 이상에서 사용 가능  <br/> |
|20cm(8  <br/> |XMPP 인스턴트 메시징 (페더레이션)  <br/> |Lync Server 2013 및 비즈니스용 Skype 2015에서 사용 가능  <br/> |
|21  <br/> |비디오 Interop 서버  <br/> |비즈니스용 Skype 서버 2015의 새로운 사항  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>상태 롤업 방법

다음 표에서는 비즈니스용 Skype 서버 모니터링 팩의 개체 상태를 보여 줍니다.
  
|관리 팩 개체|설명|
|:-----|:-----|
|비즈니스용 Skype 서버 배포  <br/> |조직의 비즈니스용 Skype 서버 2015에 대 한 배포를 나타냅니다.  <br/> |
|비즈니스용 Skype 서버 사이트  <br/> |서비스가 배포 되는 다른 지리적 위치를 나타냅니다.  <br/> |
|비즈니스용 Skype 서버 풀  <br/> |인스턴트 메시징 및 회의와 같은 통신 서비스를 사용자에 게 제공 하는 풀 (사이트 내)입니다. 지정 된 풀에 컴퓨터가 하나만 있는 경우에도 프런트 엔드 풀,에 지 풀 및 디렉터 풀에 적용 됩니다.  <br/> |
|비즈니스용 Skype 서버 역할  <br/> |비즈니스용 Skype 서버 서비스를 호스트 하는 서버 역할입니다.  <br/> |
|비즈니스용 Skype 서버 서비스  <br/> |특정 컴퓨터에 배포 된 기능 (예: fp01.contoso.com의 사용자 서비스)을 나타냅니다.  <br/> |
|비즈니스용 Skype 서버 구성 요소  <br/> |서비스 구성 요소 (예: 주소록 다운로드 구성 요소)는 웹 서비스의 일부입니다.  <br/> |
|비즈니스용 Skype 서버 풀 감시자  <br/> |하나의 풀에 대해 실행 되는 가상 트랜잭션의 인스턴스입니다.  <br/> |
|비즈니스용 Skype 서버 등록자 감시자  <br/> |하나의 등록자 풀에 대해 실행 되는 가상 트랜잭션의 인스턴스입니다.  <br/> |
|비즈니스용 Skype 서버 사용자 서비스 풀 감시자  <br/> |하나의 사용자 서비스 풀에 대해 실행 되는 가상 트랜잭션의 인스턴스입니다.  <br/> |
|비즈니스용 Skype 서버 음성 풀 감시자  <br/> |하나의 음성 풀에 대해 실행 되는 가상 트랜잭션의 인스턴스입니다.  <br/> |
|비즈니스용 Skype 서버 포트 감시자  <br/> |하나의 풀에 대해 실행 되는 포트 검사 인스턴스입니다.  <br/> |
|단순 URL 감시자  <br/> |배포에서 구성 된 단순 Url에 대 한 HTTPS 검색을 수행 합니다.  <br/> |
   
![SCOM 롤업](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
비즈니스용 skype 서버 풀에는 여러 명의 비즈니스용 Skype 서버 시스템 (비즈니스용 skype 서버 역할, 비즈니스용 Skype 서버 서비스 및 비즈니스용 Skype 서버 구성 요소)이 포함 될 수 있습니다. 따라서 같은 풀에 있는 다른 서버는 클라이언트에 응용 프로그램 서비스를 제공할 수 있으므로 개별 서버나 구성 요소의 오류는 비즈니스용 Skype 서버 풀의 전반적인 상태에 덜 중요 합니다. 상태는 비즈니스용 Skype 서버 풀에 대해 백분율 수준으로 롤업 됩니다. 
  
비즈니스용 Skype 서버 풀 감시자가 비즈니스용 Skype 서버 풀에 대해 가상 트랜잭션을 수행 합니다. 다음 다이어그램에 나와 있는 것 처럼 하나 이상의 가상 트랜잭션 (연속 폴링 간격으로 알려진 프로세스)에서 연속 오류가 발생 하는 경우 해당 풀 수준 (가상 트랜잭션의 최하위)에 위험 상태를 롤업 합니다. 
  
![SCOM 롤업 연속 폴링](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>모범 사례: 사용자 지정을 위한 관리 팩 만들기

기본적으로 Operations Manager는 재정의와 같은 모든 사용자 지정 내용을 기본 관리 팩에 저장 합니다. 가장 좋은 방법은 사용자 지정할 봉인 된 관리 팩 마다 별도의 관리 팩을 만들어야 하는 것입니다. 
  
봉인 된 관리 팩에 대 한 사용자 지정 설정을 저장 하기 위한 관리 팩을 만들 때는 "비즈니스용 Skype 서버 2015 사용자 지정"과 같은 새 관리 팩의 이름을 적절 하 게 지정 하는 것이 좋습니다. 
  
봉인 된 각 관리 팩의 사용자 지정 내용을 저장 하기 위한 새 관리 팩을 만들면 테스트 환경에서 프로덕션 환경으로 사용자 지정 항목을 보다 쉽게 내보낼 수 있습니다. 또한 관리 팩을 삭제 하기 전에 종속성을 삭제 해야 하므로 관리 팩을 보다 쉽게 삭제할 수 있습니다. 모든 관리 팩에 대 한 사용자 지정 내용이 기본 관리 팩에 저장 되어 있고 단일 관리 팩을 삭제 해야 하는 경우 먼저 기본 관리 팩을 삭제 한 다음 다른 관리 팩에 대 한 사용자 지정도 삭제 해야 합니다. 
  
## <a name="links"></a>Links

다음 링크를 사용 하 여 System Center 2012 모니터링 팩과 관련 된 일반적인 작업에 대 한 정보로 연결 합니다.
  
- [관리 팩 수명 주기](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Operations Manager에서 관리 팩을 가져오는 방법 2012](https://technet.microsoft.com/library/hh212691.aspx)
    
- [규칙 또는 모니터를 재정의 하는 방법](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Operations Manager에서 실행 계정을 만드는 방법 2012](https://technet.microsoft.com/library/hh321655.aspx)
    
- [실행 계정 및 프로필 관리](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Operations Manager 관리 팩을 내보내는 방법](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Operations Manager 관리 팩을 제거 하는 방법](https://technet.microsoft.com/library/hh230746.aspx)
    
다음 링크를 사용 하 여 System Center 2007 모니터링 팩과 관련 된 일반적인 작업에 대 한 정보로 연결 합니다.
  
- [관리 팩 수명 주기 관리](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Operations Manager에서 관리 팩을 가져오는 방법 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [재정의를 사용 하 여 모니터링 하는 방법](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Operations Manager에서 실행 계정을 만드는 방법 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [기존 실행 프로필을 수정 하는 방법](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [관리 팩 사용자 지정 내용을 내보내는 방법](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [관리 팩을 제거 하는 방법](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Operations Manager 및 모니터링 팩에 대 한 질문은 [System Center Operations Manager 커뮤니티 포럼](https://go.microsoft.com/fwlink/p/?LinkID=179635)을 참조 하십시오.
  
유용한 리소스는 특정 모니터링 팩에 대 한 "예"를 포함 하는 [System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/) 블로그입니다.
  
Operations Manager에 대 한 자세한 내용은 다음 블로그를 참조 하십시오. 
  
- [Operations Manager 팀 블로그](https://blogs.technet.com/momteam/default.aspx)
    
- [Kevin Holman의 OpsMgr 블로그](https://blogs.technet.com/kevinholman/default.aspx)
    
- [OpsMgr의 생각](https://thoughtsonopsmgr.blogspot.com/)
    
- [Raphael 삼 부 대의 블로그](https://rburri.wordpress.com/)
    
- [BWren의 관리 공간](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> 타사 사이트의 모든 정보와 콘텐츠는 웹 사이트의 소유자나 사용자가 제공 합니다. Microsoft는이 웹 사이트의 정보에 대해 어떠한 명시적, 묵시적 또는 법률적 보증도 하지 않습니다. 
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015 관리 도구](../../management-tools/management-tools.md)
