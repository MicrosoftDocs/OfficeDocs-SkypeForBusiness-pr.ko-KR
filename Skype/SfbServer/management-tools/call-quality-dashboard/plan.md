---
title: 비즈니스용 Skype 서버에 대 한 통화 품질 대시보드 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: '요약: 통화 품질 대시보드를 계획할 때 고려해 야 할 사항에 대해 알아봅니다.'
ms.openlocfilehash: 25342998332a596abce9ecd02e63e153be6e6d94
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029419"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 통화 품질 대시보드 계획 
 
**요약:** 통화 품질 대시보드를 계획할 때 고려해 야 할 사항에 대해 알아봅니다.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>비즈니스용 Skype 서버 통화 품질 대시보드 개요

Skype for Business Server Call Quality 대시보드 (CQD)는 비즈니스용 Skype 서버의 모니터링 서버에서 경험 치를 데이터베이스 위쪽에 있는 보고 계층입니다. CQD는 Microsoft SQL Server Analysis Services를 사용 하 여 데이터 집합에 대 한 필터링 및 피벗을 비롯 하 여 집계 사용 및 통화 품질 정보를 제공 합니다. CQD 기능에는 다음이 포함 됩니다.
  
- **CQD의 QoE 보관 구성 요소를 통해 QoE 데이터를 보관 합니다.** QoE 보관 구성 요소는 모니터링 서버에서 사용할 수 있는 것 보다 훨씬 긴 기간 동안 QoE 데이터를 저장할 수 있습니다. 이를 통해 한 번에 최대 7 개월 동안의 데이터에 대 한 추세와 보고를 수행할 수 있으며, 보고 창을 데이터와 동일 하 게 되돌릴 수 있습니다.
- **Microsoft SQL Server Analysis Services의 전력 및 속도를 사용 하는 보고 및 분석** Microsoft SQL Analysis Services를 활용 하 여 신속한 요약, 필터 및 피벗 기능을 제공 하 여 분석 큐브를 통해 대시보드의 전원을 공급 합니다. 실행 속도를 보고 하 고 데이터를 드릴 다운 시키는 기능을 통해 분석 시간을 크게 줄일 수 있습니다.
- **통화 품질 보고용으로 최적화 된 새 데이터 스키마** 큐브에는 음성 품질 보고 및 조사를 위해 디자인 된 스키마가 있습니다. 포털 사용자는 QoE 메트릭 데이터베이스 스키마가 필요한 보기에 매핑되는 방식을 파악 하는 대신 보고 작업에 집중할 수 있습니다. QoE 보관 함과 큐브를 조합 하면 CQD를 통한 보고 및 분석의 복잡성을 줄일 수 있는 추상화가 제공 됩니다. QoE 보관 데이터베이스 스키마에는 데이터의 전체 값을 향상 시키기 위해 배포 관련 데이터로 채울 수 있는 테이블도 포함 되어 있습니다.
- **기본 제공 보고서 디자이너 및 원본 위치 보고서 편집** Portal 구성 요소는 통화 품질 방법론 후에 모델링 된 몇 가지 기본 제공 보고서와 함께 제공 됩니다. 포털 사용자는 포털의 편집 기능을 통해 보고서를 수정 하 고 새 보고서를 만들 수 있습니다.
- **보고서 구조 및 분석 큐브 데이터에 대 한 Web API 액세스** 대시보드 보고 프레임 워크는 큐브의 데이터를 표시 하는 유일한 방법은 아닙니다. CQD에서는 HTML 및 JavaScript를 사용 하 여 CQD 웹 Api에서 데이터를 검색 하 고 데이터를 사용자 지정 형식으로 렌더링 하는 몇 가지 예를 제공 합니다. 보고서 편집기와 CQD 웹 Api를 함께 사용 하면 보고서 및 사용자 지정 보고서 레이아웃을 빠르게 프로토타입화 할 수 있습니다.

> [!NOTE]
> 관리자는 이제 [Cqd 버전 3](https://cqd.teams.microsoft.com) (관리자 자격 증명으로 로그인)을 사용 하 여 비즈니스용 Skype 서버 2019를 관리할 수 있습니다. 이를 위해서는 하이브리드 구현 및 CDC (Call Data Connector)를 사용 해야 합니다. CDC 사용에 대 한 자세한 내용은 [Plan Call Data Connector](/SkypeForBusiness/hybrid/plan-call-data-connector) 를 참조 하십시오. CQD 버전 3 설명서의 경우 CQD 버전 3에 대 한 자세한 내용은 [Microsoft 팀 및 비즈니스용 Skype 온라인에 대 한 통화 품질 대시보드 켜기 및 사용](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) 을 참조 하세요.

## <a name="cqd-design-goals"></a>CQD 디자인 목표

IT 전문가는 CQD를 사용 하 여 미디어 품질 문제가 발생 하는 환경에서 포커스 영역을 식별 하는 데 집계 데이터를 사용할 수 있습니다. It 전문가가 서로 다른 사용자 그룹에 대 한 통계를 비교 하 고 추세 및 패턴을 파악할 수 있습니다. 개별 통화 문제를 해결 하는 데 중점을 만들지만, 지정 된 환경의 여러 사용자에 게 적용할 문제 및 솔루션을 식별 하는 것은 중요 하지 않습니다. 
  
## <a name="call-quality-dashboard-components"></a>통화 품질 대시보드 구성 요소

통화 품질 대시보드는 여러 데이터베이스, Microsoft SQL 에이전트 작업, 프로세스 및 웹 응용 프로그램으로 구성 됩니다. Microsoft SQL 에이전트 작업은 QoE 메트릭 데이터베이스의 데이터를 정기적으로 QoE 보관 데이터베이스에 복사 하 고 QoE 보관 데이터베이스에 있는 데이터를 사용 하 여 큐브를 처리 합니다. 리포지토리 데이터베이스에는 포털을 지 원하는 보고서 정의가 저장 됩니다. 포털에서 큐브 데이터에 대 한 브라우저 액세스를 제공 합니다. 
  
QoE 보관, 큐브 및 리포지토리 데이터베이스를 포함 한 CQD 구성 요소는 모니터링 서버에 설치 하거나, 자체 서버에 설치 하거나, 여러 서버에 설치할 수 있습니다. 특정 설치 방법은 CQD의 성능 요구 및 동일한 서버의 다른 프로세스에 대 한 영향에 따라 달라 집니다. 자세한 내용은이 문서 뒷부분의 "CQD의 구성 요소 및 토폴로지" 섹션을 참조 하십시오.
  
### <a name="architectural-overview"></a>아키텍처 개요

요약 하자면, CQD에는 다음 요소가 필요 합니다.
  
- 두 데이터베이스: 보관 데이터베이스와 리포지토리 데이터베이스
    
- 집계 된 데이터를 시각화 하는 SSAS 큐브 1 개 
    
- IIS 호스트 웹 포털
    
![CQD 구성 요소](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
동일한 CQD 아키텍처는 Lync Server 2013 및 비즈니스용 Skype를 지원 합니다. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD 및 비즈니스용 Skype 및 Lync 2013

 비즈니스용 Skype 환경 에서만 다음과 같은 기능을 사용할 수 있습니다.
  
- 신호 강도의 wi-fi 보고
    
- 칩셋 드라이버에 대 한 wi-fi 보고
    
- 통화 데이터 평가 
    
## <a name="information-available-through-cqd"></a>CQD를 통해 사용할 수 있는 정보

CQD는 비즈니스용 Skype 서버 오디오, 비디오 및 응용 프로그램 공유 스트림 횟수와 양호한 통화 및 불량 통화 수를 보여 줍니다. 보기를 분리 하 여 다양 한 차원에서 필터링 할 수 있습니다. CQD는 모니터링 서버의 QoE 메트릭 데이터베이스에서 데이터를 그립니다. 그러면 데이터가 "건물 당 통화 품질" 등의 보고서를 만들기 위해 네트워크 서브넷 간 매핑과 같은 고객 제공 데이터와 병합 됩니다. 
  
또한 CQD는 "caller" 및 "피호출자"와 같은 내부 QoE 데이터 idiosyncrasies을 추상화 하 여 "server" 및 "client"를 중심으로 보고서 보기를 작성 하는 데 집중할 수 있도록 합니다. 통화 품질 방법론에 따라 CQD는 능률적인 통화의 포켓이 발생 하는 상황을 식별 하는 데 도움이 되도록 간소화 되었습니다 (통화 품질 개선을 위한 tenets 중 하나).
  
## <a name="viewing-data-in-cqd"></a>CQD의 데이터 보기

CQD 데이터는 CQD 포털을 통해 보고 REST API 호출을 통해 액세스할 수 있습니다.
  
### <a name="cqd-portal"></a>CQD 포털

포털은 큐브의 데이터를 가장 빠르게 볼 수 있는 방법입니다. 포털에는 즉시 사용할 수 있는 몇 가지 기본 제공 보고가 제공 됩니다. 기본 제공 보고서가 구조화 된 방식으로 연결 되어 사용자에 게 더 작은 통화 데이터 조각이 더 작게 표시 되는 것을 안내 합니다. 기본 제공 보고서를 사용 하면 여러 피벗, 필터 및 측정값을 갖는 차트와 테이블을 조합 하 여 데이터를 표시할 수 있는 다양 한 방법을 강조 표시할 수도 있습니다. 포털에 액세스 하는 각 사용자는 자신이 수정 하 고 공유할 수 있는 자체 보고서 집합을 포함할 수 있습니다. CQD 웹 포털을 사용 하는 방법에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 통화 품질 대시보드 사용](use.md)을 참조 하세요.
  
CQD 포털에 대해 지원 되는 운영 체제: Windows 8.1, Windows 8, Windows Server 2012 R2, Windows Server 2012 및 Windows Server 2016 (비즈니스용 Skype Server 2019 CQD에만 해당)
  
CQD 포털에 대해 지원 되는 브라우저: Internet Explorer 11, Internet Explorer 10 및 Internet Explorer 9
  
### <a name="rest-apis"></a>REST Api

REST API 호출을 통해 큐브 데이터에 액세스할 수도 있습니다. REST API 호출을 통해 검색 되는 데이터는 HTML 페이지를 통해 렌더링할 수 있습니다. 사용자는 비즈니스 요구에 가장 적합 한 사용자 지정 보고서를 만드는 동시에, 쿼리 속도와 CQD의 높은 수준의 스키마를 활용할 수 있습니다. API 및 샘플에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 통화 품질 대시보드 개발](develop.md)을 참조 하십시오. 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>CQD에 대 한 조직의 요구 사항 정의

CQD는 QoE 데이터 보관 및 통화 품질 데이터에 대 한 빠르고 깊이 있는 분석을 제공 합니다. 다음 가이드에서는 CQD를 배포 하는 시기와 방법을 결정 하는 데 도움이 되는 정보를 제공 합니다.
  
### <a name="when-to-deploy-cqd"></a>CQD를 배포 하는 경우

 **조직에 통화 품질 문제가 발생 하지 않는 경우에도 CQD를 배포 하 여 기본 통화 품질 측정을 설정할 수 있습니다.** 모든 조직은 Wi-fi와 유선 및 원격 및 office worker를 서로 다르게 조합해 서 기본 통화 품질 측정을 설정 하는 것이 중요 합니다. 통화 품질 문제가 발생 하면 가장 최근 통화 품질 측정이 이전 시간 간격과 비교 될 수 있습니다. CQD의 추세 기능을 사용 하면 시간에 따라 통화 품질의 변경 내용을 쉽게 감지할 수 있습니다.
  
 **CQD는 통화 품질에 영향을 줄 수 있는 문제 영역을 사전에 찾도록 배포할 수 있습니다.** 조직의 평균 통화 품질이 조직에서 설정한 목표를 충족 하는 경우에도 평균 메트릭 보다 숨겨진 통화 품질 문제에 대 한 포켓이 있을 수 있습니다. CQD를 사용 하면 QoEMetrics 데이터베이스의 여러 차원에 대 한 통화 품질 메트릭 분석을 수행할 수 있습니다. 피어 그룹의 Spotting 이상으로, 통화 품질 문제를 사전에 쉽게 찾을 수 있습니다.
  
 **조직에 통화 품질 문제가 있으면 문제를 해결 하는 데 필요한 시간을 줄이기 위해 CQD를 배포 해야 합니다.** CQD는 빠른 보고 성능 및 동적 드릴 다운 기능을 제공 하 여 기존 통화 품질 조사를 단순화할 수 있습니다. CQD는 환경에 대 한 복구의 통화 품질 조사 유효성 검사에서 다양 한 유형의 워크플로를 위해 디자인 되었습니다.
  
### <a name="why-deploy-cqd"></a>CQD를 배포 하는 이유

 **3 개월 이상의 데이터를 QoE 보고 해야 하는 경우에는 CQD를 배포 해야 합니다.** QoEMetrics 데이터베이스 및 모니터링 서버 보고서는 작은 데이터 집합을 유지 하 고 보고 하도록 설계 되었습니다. QoE 메트릭 데이터베이스는 빠른 삽입에 최적화 되어 있으므로 보고 성능은 대규모 통화 량 이나 데이터베이스에 대 한 보고 된 액세스와 상충 하 여 나타났습니다 수 있습니다. CQD의 QoE 보관 데이터베이스는 보존 기능이 훨씬 더 긴 QoE 메트릭 데이터의 두 번째 복사본을 제공 합니다. 또한 포털은 한 번에 최대 7 개월의 데이터를 표시 하도록 최적화 되었으며 필요한 경우 QoE 보관의 모든 데이터에 대해 보고할 수 있습니다.
  
 **사용자 지정 QoE 보고서가 필요한 경우에는 CQD를 배포 해야 합니다.** 포털에는 보고서를 빠르고 쉽게 만들고 프로토타입화 하기 위한 보고서 편집기 기능이 있습니다. 또한 큐브 데이터에 프로그래밍 방식으로 액세스 하는 데 사용할 수 있는 REST Api를 만들기 때문에 HTML/JavaScript를 사용 하거나 다른 많은 프레임 워크를 통해 프레젠테이션을 사용자 지정할 수 있습니다 보고를 위해 사용자 지정 데이터 뷰를 만드는 용도로는 더 이상 새 SQL 쿼리를 작성할 필요가 없습니다.
  
 **기존 QoE 보고 기능이 조직에 필요한 속도나 깊이를 충족 하지 않는 경우 CQD를 배포 해야 합니다.** CQD는 여러 기본 제공 보고서와 함께 제공 됩니다. 보고서는 즉시 유용 하며 데이터를 점진적으로 드릴 하 여 각 수준에서 추가 정보를 제공할 수 있는 방법을 보여 줍니다. 또한 보고서 계층 구조는 논리적 방식으로 수많은 보고서를 관리 하는 데 도움이 되며, 쉽게 액세스할 수 있고 이해 하기 fosters 많은 보고서를 만들 수 있습니다. CQD는 속도와 유연성을 제공 하는 것이 아니라 통화 품질 방법론에 의해 개발 된 워크플로에 최적화 되어 있습니다.
  
## <a name="components-and-topologies-for-cqd"></a>CQD의 구성 요소 및 토폴로지

CQD는 여러 구성 요소와 함께 제공 되며, 각 구성 요소의 요구 사항을 이해 하 고이를 통해 도구를 가장 간단 하 고 효율적으로 배포할 수 있습니다. 다음 표에서는 각 CQD 구성 요소에 대 한 종속 구성 요소에 대해 설명 합니다.
  

|**구성 요소 이름**|**종속 구성 요소**|
|:-----|:-----|
|QoE 보관 함  <br/> |Microsoft SQL Server  <br/> |
|입방체  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|포탈  <br/> |Microsoft Information Services  <br/> |
|리포지토리 서비스 (포털 설치의 일부)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> QoE 보관 및 큐브에 대해 특정 배포 옵션에는 Microsoft SQL Server 비즈니스 인텔리전스 또는 Enterprise edition이 필요 합니다. 자세한 내용은 아래의 [CQD의 인프라 요구 사항](plan.md#Infrastructure_Req) 섹션을 참조 하세요.
  
![CQD 구성 요소](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>단일 서버 구성

모든 CQD 구성 요소와 종속 구성 요소를 한 컴퓨터에 설치할 수 있습니다. 단일 상자 구성은 가장 간단한 구성 이며 CQD를 독립적으로 사용할 수 있습니다. CQD는 모니터링 서버의 QoE 메트릭 데이터베이스에 액세스 하기만 하면 됩니다. CQD 서버는 독립 실행형 시스템 일 수도 있고, 가상 컴퓨터 이거나, 호스트 컴퓨터의 사용 가능한 리소스 및 성능 요구 사항에 따라 모니터링 서버인 경우도 있습니다. 
  
설치 중에 설치를 수행 하는 사용자는 Microsoft SQL Server 및 Microsoft SQL Server Analysis Services 인스턴스를 제공 하기만 하면 되지만, 이전에는 CQD를 설치할 컴퓨터에 설정 되어 있습니다. 자세한 내용은 [비즈니스용 Skype 서버에 대 한 통화 품질 대시보드 배포](deploy-0.md) 를 참조 하세요.
  
### <a name="multiserver-configuration"></a>다중 서버 구성

다중 서버 구성에서는 QoE 보관, 큐브 및 포털이 모두 서로 다른 컴퓨터에 있을 수 있습니다. 다중 서버 구성은 두 가지 주요 용도로 사용 됩니다.
  
- 다른 서버에서 CQD 웹 포털 및 CQD 큐브 호스팅
    
- "개발" 포털을 "프로덕션" 포털과 별개로 호스팅 
    
  **다른 컴퓨터에서 CQD 웹 포털 및 CQD 큐브 호스팅** Sql server 설치에서 CQD 포털을 분리 하 여 sql server 인스턴스에 대 한 SQL Server 버전을 혼합 및 일치 시킬 수 있는 요구 사항이 있거나 sql server Analysis Services 인스턴스를 설치할 필요가 있는 조직은 CQD 포털을 설치 하도록 선택 하 고 다른 컴퓨터의 CQD 큐브 QoE 보관 구성 요소는 조직에서 모니터링 서버에 대 한 성능 제한 없이 QoE 데이터를 보관 하는 지속 가능한 방법을 원할 경우에 설치 되는 단독 CQD 구성 요소 일 수도 있습니다.
  
![단일 서버 CQD](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **"개발" 포털을 "프로덕션" 포털과 별개로 호스팅** REST Api를 통해 자체 사용자 지정 보고서를 개발 하는 조직에서는 일반 사용자가 통화 품질 모니터링 또는 조사를 위해 액세스 하는 프로덕션 포털 옆에 추가 (CQD) 포털 인스턴스를 배포 하는 것이 좋습니다. 개발 포털은 프로덕션 환경에서 포털에 대 한 수정 내용을 격리할 수 있습니다. 추가 웹 포털은 다음과 같이 서로 다른 컴퓨터에 배포 하거나 같은 컴퓨터의 서로 다른 웹 디렉터리에 배포 될 수 있습니다 (표시 되지 않음). CQD 설치 프로세스는 항상 CQD 웹 포털을 미리 정의 된 웹 응용 프로그램 이름을 사용 하는 기본 웹 사이트에 배포 하므로 후자를 수행 하려면 추가 CQD 웹 포털을 프로덕션 컴퓨터에 수동으로 복사 해야 합니다.
  
![CQD 다중 서버 계획](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>지원되는 토폴로지

CQD는 여러 개의 비즈니스용 Skype 서버 토폴로지가 각각 자체 모니터링 서버를 포함 하는 경우 처럼 여러 QoEMetrics 데이터베이스의 데이터를 병합 하지 않습니다. 각 CQD 인스턴스는 QoEMetrics 데이터베이스 하나를 가리켜야 합니다. 그러나 CQD는 모니터링 서버에서 대부분의 보고 작업 부하를 이동 하기 때문에 비즈니스용 Skype 서버 토폴로지로 하나의 모니터링 서버를 배포 해야 하는 대규모 조직은 모든 토폴로지에 대해 하나의 모니터링 서버를 사용 하는 것이 좋습니다.
  
## <a name="infrastructure-requirements-for-cqd"></a>CQD의 인프라 요구 사항
<a name="Infrastructure_Req"> </a>

모든 구성 요소와 종속 구성 요소를 포함 하는 CQD는 가상 컴퓨터, 단일 컴퓨터 또는 여러 컴퓨터에 배포 될 수 있습니다. 최소 소프트웨어 및 하드웨어 요구 사항은 다음과 같습니다. 데이터 가용성 및 쿼리 성능은 현재 비즈니스용 Skype 서버 사용자의 수와 하드웨어 및 구성에 따라 몇 분에서 몇 시간까지 다를 수 있으므로 다음과 같은 몇 가지 성능 측정이 제공 됩니다.
  
|||
|:-----|:-----|
|CQD 2015 <br/> |  <br/> |
|지원되는 운영 체제   <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|지원 되는 SQL Server  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|CQD 2019 <br/> |  <br/> |
|지원되는 운영 체제   <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|지원 되는 SQL Server  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
CQD는 Microsoft SQL Server, Microsoft SQL Server Analysis Services 및 Microsoft 인터넷 정보 서비스를 활용 하므로, CQD의 최소 하드웨어 및 소프트웨어 요구 사항은 기본적으로 이러한 종속 구성 요소와 동일 합니다. 그러나 조직의 요구 사항 (조직이 생성 하는 QoE 데이터의 볼륨에 따라 부분적으로 영향을 받게 됨)과 배포 비용을 기반으로 추가 배포 고려 사항을 결정 해야 합니다.
  
CQD의 데이터 처리는 두 가지 주요 단계로 구분 됩니다. 
  
- QoE 보관 프로세스
    
- CQD 큐브 처리
    
  **QoE 보관 처리** QoE 보관 처리 작업은 모니터링 서버의 QoE 메트릭 데이터베이스에 있는 데이터를 QoE 보관 데이터베이스에 복사 합니다. 작업 처리 시간이 근본적으로 성능 특성이 서로 다른 두 가지 경우가 있습니다. 첫 번째는 CQD의 초기 설치 후입니다. 새 설치 후에 작업을 처음으로 실행 하면 QoE 보관 처리 작업은 QoE 메트릭 데이터베이스에 있는 모든 데이터를 QoE 보관 데이터베이스에 복사 합니다. 두 번째는 이러한 초기 라운드 후의 주기적 처리입니다. QoE 보관 처리 작업은 15 분 마다 실행 되며 QoE 메트릭 데이터베이스에 있는 모든 새 QoE 레코드를 처리 합니다. 초기 처리 시간은 CQD가 설치 될 때 처음으로 실행 되므로 문제가 되지 않습니다. 그러나 CQD 서버가 심하게 프로 비전 된 경우에는이 작업에 몇 시간이 걸릴 수 있습니다. 아래 표에는 QoE의 초기 처리 시간 예를 참조 하십시오.
  
  **CQD 큐브 처리** 큐브 처리 작업은 QoE 보관 데이터베이스의 데이터를 큐브로 집계 합니다. 초기 큐브 처리 시간 및 후속 큐브 처리 시간은 CQD 큐브에 사용 되는 SQL Server Analysis Services 버전에 따라 결정 됩니다. Standard edition을 사용 하는 경우, 큐브 데이터를 새로 고칠 때마다 초기 큐브 처리 시간과 후속 큐브 처리 시간 사이에는 아무런 차이가 없으며,이는 항상 사용 가능한 모든 데이터에 대 한 전체 처리가 됩니다. 즉, QoE 보관 데이터베이스의 데이터 양이 늘어나면 큐브 처리 시간이 길어집니다. Business Intelligence Edition 및 Enterprise Edition 버전의 SQL Server에서는 파티션을 지원 하므로 두 버전 중 하나를 사용 하는 경우에만 초기 QoE 보관 데이터베이스의 모든 데이터를 처리 합니다. 후속 실행에서 작업이 15 분 마다 트리거되는 경우 작업은 마지막으로 작업을 실행 한 후에 QoE 보관 데이터베이스에 추가 된 새 레코드만 처리 합니다. 하루에 한 번, 현재 달의 데이터를 포함 하는 파티션에 대 한 전체 처리도 제공 됩니다.
  
실제 컴퓨터 특성은 SQL Server 구성 요소에서 사용할 수 있는 소프트웨어 기능 뿐 아니라 CQD 성능에도 영향을 줄 수 있습니다. QoE 보관 구성 요소는 다른 구성 요소에 비해 디스크를 많이 사용 하지만 큐브 구성 요소는 더 많은 CPU 및 메모리 집약적입니다. 이러한 모든 요인은 데이터의 최신 상태와 가용성에 직접적인 영향을 주는 전체 데이터 처리 시간을 나타내는 데 영향을 줍니다. 조직은 조직의 개별 요구 사항에 따라 하드웨어 및 소프트웨어에 대 한 결정을 내려야 합니다. 
  
### <a name="tested-hardware-configurations"></a>테스트를 거친 하드웨어 구성

이 섹션에서는 환경에 단일 QoEMetrics DB가 있다고 가정 합니다. 
  
**컴퓨터 프로필**

|**컴퓨터**|**CPU 코어**|**RAM**|**같은 디스크의 QoE 보관 및 큐브**|**QoE 보관 및 SQL Temp DB 같은 디스크**|
|:-----|:-----|:-----|:-----|:-----|
|가상 컴퓨터  <br/> |4   <br/> |7G B  <br/> |예  <br/> |예  <br/> |
|코어 4 개  <br/> |4   <br/> |20GB  <br/> |예  <br/> |아니요  <br/> |
|코어 8 개  <br/> |8   <br/> |32GB  <br/> |예  <br/> |아니요  <br/> |
|16 코어  <br/> |16   <br/> |128GB  <br/> |아니요  <br/> |아니요  <br/> |
   
**성능 결과**

|**컴퓨터**|**QoE 메트릭 DB 크기**|**SQL 파티션**|**디스크 유형**|**스트림 수**|**초기 보관 프로세스**|**초기 큐브 프로세스**|**후속 보관 프로세스**|**후속 큐브 프로세스**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|가상 컴퓨터  <br/> |900  <br/> |단일  <br/> |VHD (가변 크기)  <br/> |.5 M  <br/> |30 m  <br/> |2 m  <br/> |30 s  <br/> |1 m  <br/> |
|가상 컴퓨터  <br/> |9G B  <br/> |단일  <br/> |VHD (가변 크기)  <br/> |5 M  <br/> |4 h  <br/> |15 m  <br/> |1 m  <br/> |5 m  <br/> |
|가상 컴퓨터  <br/> |9G B  <br/> |단일  <br/> |VHD (고정 크기)  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |1 m  <br/> |5 m  <br/> |
|가상 컴퓨터  <br/> |30 + G B  <br/> |단일  <br/> |VHD (고정 크기)  <br/> |10 M  <br/> |15 h  <br/> |20 m  <br/> |2 m  <br/> |45 m  <br/> |
|코어 8 개  <br/> |9G B  <br/> |단일  <br/> |여러 디스크  <br/> |5 M  <br/> |2 h  <br/> |5 m  <br/> |25 s  <br/> |5 m  <br/> |
|코어 8 개  <br/> |9G B  <br/> |여러 개  <br/> |여러 디스크  <br/> |5 M  <br/> |2 h  <br/> |15 m  <br/> |35 s  <br/> |2 m  <br/> |
|코어 8 개  <br/> |30 + G B  <br/> |단일  <br/> |여러 디스크  <br/> |20 M  <br/> |9 h  <br/> |20 m  <br/> |1 m  <br/> |20 m  <br/> |
|코어 8 개  <br/> |30 + G B  <br/> |여러 개  <br/> |여러 디스크  <br/> |20 M  <br/> |9 h  <br/> |30 m  <br/> |2 m  <br/> |2 m  <br/> |
|코어 4 개  <br/> |200GB  <br/> |단일  <br/> |여러 디스크  <br/> |125 M  <br/> |6 일 +  <br/> |7 h  <br/> |2 m  <br/> |6 h  <br/> |
|16 코어  <br/> |500GB  <br/> |여러 개  <br/> |여러 스핀 들  <br/> |250 M  <br/> |8 일  <br/> |2 h  <br/> |2 m  <br/> |10 m  <br/> |
   
\*QoE 메트릭 데이터베이스에는 각각 9-18 개월의 데이터가 포함 되어야 하지만 이러한 단계는 완료 하기 위해 제공 되는 것 이므로 실제 배포에서는 이러한 경우가 발생 하지 않습니다.
  
### <a name="service-account-requirements"></a>서비스 계정 요구 사항

CQD 서버의 SQL 에이전트에서 QoEArchiveDB로 데이터를 가져오는 데 사용할 수 있는 계정 (QoEMetrics에 대 한 읽기 액세스 권한 포함)이 필요 합니다.
  
또한 QoEArchiveDB에서 데이터를 가져오기 위해 SSAS 작업에 대해 별도의 계정을 구성 해야 할 수 있습니다 (선택 사항).
  
IIS는 가장 일반적으로 네트워크 서비스를 응용 프로그램 풀 Id로 사용 하지만 서비스 계정으로 구성할 수 있습니다.
  
### <a name="portal-access-control"></a>포털 액세스 제어

기본적으로 인증 된 모든 사용자에 게 액세스 권한이 있습니다. IIS 권한 부여 규칙을 사용 하 여 특정 그룹으로 제한 하 여이를 변경할 수 있습니다.
  
### <a name="pre-install-requirements"></a>사전 설치 요구 사항

이 지침에서는 QoE 메트릭 데이터베이스가 이미 설치 되었으며 비즈니스용 Skype 서버 토폴로지에서 원하는 위치에서 실행 되 고 있다고 가정 합니다.
  
#### <a name="hardware-requirements"></a>하드웨어 요구 사항

CQD는 Microsoft SQL Server, Microsoft SQL Analysis Server 및 Microsoft Internet Information Server를 활용 하므로, CQD의 최소 하드웨어 및 소프트웨어 요구 사항은 기본적으로 이러한 종속 구성 요소와 동일 합니다. 그러나 조직의 요구 사항 (조직이 생성 하는 QoE 데이터의 볼륨에 따라 부분적으로 영향을 받게 됨)과 배포 비용을 기반으로 추가 배포 고려 사항을 결정 해야 합니다.
  
#### <a name="software-requirements"></a>소프트웨어 요구 사항

CQD에는 다음과 같은 운영 체제가 필요 합니다.
  
- Windows Server 2008 R2 (IIS 7.5 포함)
    
- Windows Server 2012 (IIS 8.0 포함)
    
- Windows Server 2012 R2 (IIS 8.5 포함)

- Windows Server 2016 (IIS 10.0) (비즈니스용 Skype 서버 2019 CQD만 해당)

- Windows Server 2019 (비즈니스용 Skype 서버 2019 CQD만 해당)
    
필요한 IIS 역할 서비스는 다음과 같습니다 (계층 구조 순).
  
- 웹 서버
    
  - 일반 HTTP 기능
    
  - 정적 콘텐츠
    
  - 기본 문서
    
  - 응용 프로그램 개발
    
  - ASP.NET
    
  - ISAPI 필터
    
  - 상태 &amp; 진단
    
  - HTTP 로깅
    
  - 보안
    
  - URL 권한 부여
    
  - Windows 인증
    
  - 관리 도구
    
  - IIS 관리 콘솔
    
> [!NOTE]
>  위의 요구 사항에 대 한 자세한 내용은 > 3.5 및 4.5 버전의 .Net framework를 사용할 수 있습니다. 둘 다 필요 합니다 (특히, 3.5 SP1이 필요 함). > 일부 시스템에서 IIS를 설치 하기 전에 ASP.NET을 설치 하는 경우 ASP.NET를 IIS에 등록할 수 없습니다. 이 문제는 해당 .Net 버전에 대 한 응용 프로그램 풀이 없거나 앱 풀 구성에 .NET CLR 버전이 없다는 것을 통해 해결 됩니다. Windows Server 2008 R2에서 이러한 문제를 해결 하려면을 실행 `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru`합니다. Windows Server 2012 및 Windows Server 2012 r 2에서를 `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` 실행 한 후에 IIS 관리자의 기본 웹 사이트에서 "ServiceModel" 모듈을 제거 합니다. > 관리 도구는 선택 사항 이지만 권장 됩니다.
  
PowerShell을 사용 하 여 이러한 요구 사항을 설치 하려면 다음을 실행 합니다.
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

지원 되는 SQL Server 버전은 다음과 같습니다.
  
- SQL Server 2012
    
- SQL Server 2014

- SQL Server 2016

- SQL Server 2017

- SQL Server 2019 (비즈니스용 Skype 서버 2019 CQD만 해당)
    
비즈니스 인텔리전스 또는 Enterprise edition이 성능상의 이유로 권장 됩니다. 이러한 버전은 동시에 처리 될 수 있는 여러 파티션 파일을 사용 하도록 허용 하며, 여러 달 이상으로 확장 되는 데이터를 처리 하는 데 유용 합니다. 
  
권장 되는 것은 아니지만 Standard edition도 지원 됩니다. 프로세스는 설치 중에 구성 해야 하는 단일 파티션으로 제한 됩니다. 
  
모든 경우에 "데이터베이스 엔진 서비스" 및 "Analysis Services"를 설치 해야 합니다. 하지만 Analysis Services에 대해 SQL Server Management Studio 지원을 추가 하는 "관리 도구-완료" 기능을 설치 하는 것도 필요 하지는 않습니다. 기능 선택 화면 모양은 그림과 같습니다.
  
![SQL Server 기능 요구 사항](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
SSAS 설치를 구성할 때 Analysis Services 구성에서 "서버 모드"를 "다차원 및 데이터 마이닝 모드"로 설정 합니다. 
  
SQL Server 비즈니스 인텔리전스 기능을 설치 및 구성 하는 방법에 대 한 자세한 내용은 [다차원 및 데이터 마이닝 모드에서 Analysis Services 설치](https://msdn.microsoft.com/library/ms143708%28v=sql.110%29.aspx)를 참조 하세요.
  
#### <a name="account-requirements"></a>계정 요구 사항

최소 권한 원칙에는 다음과 같은 세 가지 도메인 서비스 계정이 권장 됩니다. 
  
- QoE 메트릭 데이터베이스에 대 한 로그인 보안 주체 (db_datareader 권한)와 QoE 보관 SQL Server 인스턴스의 로그인 보안 주체 (설치 중에 연결 된 서버 개체를 만드는 데 필요 함)가 이미 있는 계정입니다. 이 계정은 SQL Server 에이전트 작업의 "QoE 보관 데이터" 단계를 실행 하는 데 사용 됩니다.
    
- SQL Server 에이전트 작업의 "큐브 처리" 단계를 실행 하는 데 사용 되는 것입니다. 설치 프로그램에서 QoE 보관 데이터베이스 (읽기 및 쓰기 권한 포함)에 대 한 로그인 보안 주체를 만들고 해당 큐브에 대 한 QoE 역할에 구성원 (모든 권한 사용)을 만듭니다.
    
- 웹 포털 및 웹 Api에 대해 IIS 작업자 프로세스를 실행 하는 데 사용 되는 것입니다. 설치 프로그램은 QoE 보관 데이터베이스 (읽기 권한 포함), 리포지토리 데이터베이스에 대 한 로그인 보안 주체 (읽기 및 쓰기 권한 포함), 그리고 큐브에 대 한 QoERole (모든 권한)의 구성원에 대 한 로그인 보안 주체를 만듭니다. 
    
    > [!NOTE]
    > 동일한 SQL Server에서 QoE 보관 데이터베이스와 리포지토리 데이터베이스를 모두 호스트 하는 경우에는 두 개의 사용자 매핑을 사용 하는 로그인 보안 사용자가 하나만 만들어집니다. 
  
처음 두 계정은 논리적으로 "백 엔드 서비스 계정"으로 간주 될 수 있으며 마지막 계정은 "프런트 엔드 서비스 계정"입니다. 권장 되는 것은 아니지만 단일 계정을 모든 경우에 사용할 수 있습니다.
  
> [!NOTE]
> 설치를 시작 하는 사용자 계정에는 설치를 수행 해야 하는 QoE 보관 DB 서버에 대 한 컴퓨터 관리 권한을 보유 하는 것 외에도 QoE 메트릭 DB에 대 한 읽기 액세스 권한이 있어야 합니다. 
  
## <a name="capacity-planning"></a>용량 계획
<a name="Infrastructure_Req"> </a>

CQD는 QoEMetrics에 대 한 영향을 최소화 하 여 데이터를 잠그지 않도록 최적화 되었으며 가져오기 작업은 튜닝할 수 있도록 설계 되었습니다.
  
사용할 하드웨어 유형은 동기화를 실행 하는 속도에 대 한 요구 사항에 따라 달라 집니다. 디스크 크기 조정은 다음과 같습니다.
  
- QoEArchive는 처음에 QoEMetrics DB 보다 큰 ~ 1.5 x 보다 큼
    
- SSIS 큐브가 DB와 데이터를 거의 10x 비교 합니다.
    
- 데이터는 월별 분할 됩니다. 파티션을 삭제할 수 있음
    

