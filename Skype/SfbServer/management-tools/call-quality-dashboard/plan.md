---
title: 비즈니스용 Skype 서버의 통화 품질 대시보드 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: cc2fbf41-a7e0-4ef8-a939-47bc42da5529
description: '요약: 통화 품질 대시보드를 계획할 때 고려할 내용을 자세히 알아보는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: d75e7a07d6f461c6b4b8e1e33ae86869984aae08
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095192"
---
# <a name="plan-for-call-quality-dashboard-for-skype-for-business-server"></a>비즈니스용 Skype 서버의 통화 품질 대시보드 계획 
 
**요약:** 통화 품질 대시보드를 계획할 때 고려할 내용을 자세히 알아보습니다.
  
## <a name="overview-of-the-skype-for-business-server-call-quality-dashboard"></a>비즈니스용 Skype 서버 통화 품질 대시보드 개요

비즈니스용 Skype 서버 CQD(통화 품질 대시보드)는 비즈니스용 Skype 서버의 모니터링 서버의 경험 품질 데이터베이스 위에 있는 보고 계층입니다. CQD는 Microsoft SQL Server Analysis Services를 사용하여 데이터 집합에 대한 필터링 및 피벗뿐만 아니라 집계 사용 현황 및 통화 품질 정보를 제공합니다. CQD 기능은 다음과 같습니다.
  
- **CQD의 QoE 보관 구성 요소를 통해 QoE 데이터의 보관 저장소입니다.** QoE 보관 구성 요소는 모니터링 서버보다 훨씬 긴 기간 동안 QoE 데이터를 저장할 수 있습니다. 이를 통해 한동안 최대 7개월 동안 데이터를 추세화하고 보고할 수 있으며, 보고 창을 데이터만큼 뒤로 미끄러지기 기능을 사용할 수 있습니다.
- **Analysis Services의 전원과 속도를 Microsoft SQL Server 분석.** CQD는 Microsoft SQL Analysis Services를 사용하여 빠른 요약, 필터링 및 피벗 기능을 제공하여 분석 큐브를 통해 대시보드에 전원을 공급합니다. 보고 실행 속도 및 데이터로 드릴다운하는 기능을 통해 분석 시간을 크게 줄일 수 있습니다.
- **통화 품질 보고에 최적화된 새로운 데이터 스마마입니다.** 큐브에는 음성 품질 보고 및 조사를 위해 설계된 스마마가 있습니다. 포털 사용자는 QoE 메트릭 데이터베이스가 필요한 보기에 매핑되는 방법을 알지 않고 보고 작업에 집중할 수 있습니다. QoE 보관 파일과 큐브를 조합하면 CQD를 통한 보고 및 분석의 복잡성을 줄이는 추상화가 있습니다. QoE Archive 데이터베이스 schema에는 데이터의 전체적인 가치를 향상하기 위해 배포 관련 데이터로 채울 수 있는 테이블도 포함되어 있습니다.
- **기본 제공 보고서 디자이너 및 기본 제공 보고서 편집** 포털 구성 요소에는 통화 품질 방법론 이후 모델링된 몇 가지 기본 제공 보고서가 함께 제공되어 있습니다. 포털 사용자는 포털의 편집 기능을 통해 보고서를 수정하고 새 보고서를 만들 수 있습니다.
- **보고서 구조 및 분석 큐브 데이터에 대한 웹 API 액세스** 대시보드 보고 프레임워크를 통해 큐브의 데이터를 표시할 수 있는 유일한 방법은 없습니다. CQD는 HTML 및 JavaScript를 사용하여 CQD 웹 API에서 데이터를 검색하고 데이터를 사용자 지정 형식으로 렌더링하는 몇 가지 예를 제공합니다. 보고서 편집기 및 CQD 웹 API를 조합하면 보고서 및 사용자 지정 보고서 레이아웃을 빠르게 프로토타이핑할 수 있습니다.

> [!NOTE]
> 이제 관리자는 [CQD](https://cqd.teams.microsoft.com) 버전 3(관리자 자격 증명으로 로그인)을 사용하여 비즈니스용 Skype 서버 2019를 관리할 수 있습니다. 이를 위해서는 하이브리드 구현 및 CDC(통화 데이터 커넥터)를 사용해야 합니다. CDC 사용에 대한 자세한 [내용은 Plan Call Data Connector을](../../../SfbHybrid/hybrid/plan-call-data-connector.md) 참조하십시오. CQD 버전 3 설명서의 경우 CQD 버전 3에 대한 자세한 내용은 통화 품질 대시보드 켜기 및 [Microsoft Teams용 통화](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard) 품질 대시보드 사용 및 비즈니스용 Skype Online을 참조하세요.

## <a name="cqd-design-goals"></a>CQD 디자인 목표

CQD를 사용하면 IT Pro가 집계 데이터를 사용하여 미디어 품질 문제가 발생하는 환경의 중점 영역을 식별할 수 있습니다. IT Pro는 다양한 사용자 그룹에 대한 통계를 비교하고 추세 및 패턴을 식별할 수 있습니다. 개별 통화 문제를 해결하는 데 초점을 맞추는 것이 아니라 특정 환경의 많은 사용자에게 적용되는 문제 및 솔루션을 식별하는 데 초점을 맞추고 있습니다. 
  
## <a name="call-quality-dashboard-components"></a>통화 품질 대시보드 구성 요소

통화 품질 대시보드는 여러 데이터베이스, Microsoft SQL 에이전트 작업, 프로세스 및 웹 응용 프로그램으로 구성됩니다. Microsoft SQL 에이전트 작업은 QoE 메트릭 데이터베이스의 데이터를 QoE 보관 데이터베이스로 주기적으로 복사하고 큐브를 QoE 보관 데이터베이스의 데이터로 처리합니다. 리포지토리 데이터베이스에는 포털에 전원을 공급하는 보고서 정의가 저장됩니다. 포털은 큐브 데이터에 대한 브라우저 액세스를 제공합니다. 
  
QoE 보관, 큐브 및 리포지토리 데이터베이스를 비롯한 CQD 구성 요소는 모니터링 서버에 설치하거나 자체 서버에 설치하거나 여러 서버에 설치할 수 있습니다. 특정 설치 방법은 CQD의 성능 요구 및 동일한 서버의 다른 프로세스에 미치는 영향에 따라 달라 습니다. 자세한 내용은 이 문서 부분의 "CQD의 구성 요소 및 토폴로지" 섹션을 참조하십시오.
  
### <a name="architectural-overview"></a>아키텍처 개요

요약하자면, CQD에는 다음 요소가 필요합니다.
  
- 보관 데이터베이스와 리포지토리 데이터베이스의 두 데이터베이스.
    
- 집계된 데이터를 시각화하는 SSAS 큐브 1개 
    
- IIS 호스트 CQD 웹 포털
    
![CQD 구성 요소](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
동일한 CQD 아키텍처가 Lync Server 2013 및 비즈니스용 Skype를 지원합니다. 
  
### <a name="cqd-and-skype-for-business-vs-lync-2013"></a>CQD 및 비즈니스용 Skype와 Lync 2013 비교

 비즈니스용 Skype 환경에서만 다음 기능을 사용할 수 있습니다.
  
- Wi-Fi 강도 보고
    
- Wi-Fi 드라이버 보고
    
- 통화 데이터 평가 
    
## <a name="information-available-through-cqd"></a>CQD를 통해 사용할 수 있는 정보

CQD는 비즈니스용 Skype 서버 오디오, 비디오 및 응용 프로그램 공유 스트림 수와 양호한 통화와 잘못된 통화의 수를 표시하고 잘못된 통화의 비율을 표시 할 수 있습니다. 보기를 여러 차원으로 조각화하고 필터링할 수 있습니다. CQD는 모니터링 서버의 QoE 메트릭 데이터베이스에서 데이터를 그릴 수 있습니다. 그런 다음 데이터가 네트워크 서브넷과 건물 매핑과 같이 고객이 제공한 데이터와 병합하여 "건물당 통화 품질" 같은 보고서를 사용할 수 있도록 합니다. 
  
또한 CQD는 사용자가 "server" 및 "client"에 대한 보고서 보기를 구축하는 데 집중할 수 있도록 "발신자" 및 "발신자"과 같은 여러 내부 QoE 데이터 idiosyncras를 추상화합니다. 통화 품질 방법론에 따라 CQD는 통화 품질 향상을 위한 테넌트 중 하나인 불량 통화가 공통적으로 있는 조건을 식별할 수 있도록 간소화됩니다.
  
## <a name="viewing-data-in-cqd"></a>CQD에서 데이터 보기

CQD 데이터는 CQD 포털을 통해 보고 REST API 호출을 통해 액세스할 수 있습니다.
  
### <a name="cqd-portal"></a>CQD 포털

포털은 큐브에서 데이터를 보는 가장 빠른 방법입니다. 포털에는 바로 사용 가능한 몇 가지 기본 제공 보고서가 함께 제공되어 있습니다. 기본 제공 보고서는 사용자가 연속적으로 더 작고 작은 통화 데이터 조각을 사용할 수 있도록 구조화된 방식으로 연결됩니다. 또한 기본 제공 보고서에서는 피벗, 필터 및 측정값이 서로 다른 차트 및 테이블의 조합을 보여 주어 데이터를 표시하는 다양한 방법도 중시합니다. 포털에 액세스하는 각 사용자는 수정하고 공유할 수 있는 자체 보고서 집합을 사용할 수 있습니다. CQD 웹 포털 사용에 대한 자세한 내용은 비즈니스용 Skype 서버에 통화 품질 [대시보드 사용을 참조하세요.](use.md)
  
CQD 포털에 대해 지원되는 운영 체제: Windows 8.1, Windows 8, Windows Server 2012 R2, Windows Server 2012 및 Windows Server 2016(비즈니스용 Skype 서버 2019 CQD만 해당)
  
CQD 포털에 대해 지원되는 브라우저: Internet Explorer 11, Internet Explorer 10 및 Internet Explorer 9.
  
### <a name="rest-apis"></a>REST API

REST API 호출을 통해 큐브 데이터에 액세스할 수도 있습니다. REST API 호출을 통해 검색된 데이터는 HTML 페이지를 통해 렌더링할 수 있습니다. 사용자는 비즈니스 요구에 맞는 사용자 지정 보고서를 만들면서도 쿼리 속도와 높은 수준의 CQD 스마마를 활용할 수 있습니다. API 및 샘플에 대한 자세한 내용은 비즈니스용 Skype 서버용 [통화 품질 대시보드 개발을 참조하세요.](develop.md) 
  
## <a name="defining-your-organizations-requirements-for-cqd"></a>CQD에 대한 조직의 요구 사항 정의

CQD는 QoE 데이터 보관을 제공하며 통화 품질 데이터에 대한 신속하고 심층적인 분석을 제공합니다. 다음 가이드는 CQD를 배포하는 경우와 이유를 결정하는 데 도움이 됩니다.
  
### <a name="when-to-deploy-cqd"></a>CQD를 배포하는 경우

 **조직에서 통화 품질 문제가 없는 경우에도 CQD를 배포하여 기준 통화 품질 측정을 설정할 수 있습니다.** 모든 조직이 유선 및 원격 작업자와 원격 작업자가 서로 다른 Wi-Fi 때문에 기준 통화 품질 측정을 설정하는 것이 중요합니다. 통화 품질 문제가 발생하면 최근 통화 품질 측정값을 이전 시간 간격과 비교할 수 있습니다. CQD의 추세 기능을 사용하면 시간 경과에 따라 통화 품질 변경 내용을 쉽게 감지할 수 있습니다.
  
 **CQD를 배포하여 통화 품질에 영향을 줄 수 있는 문제 영역을 사전 예방적으로 찾을 수 있습니다.** 조직의 평균 통화 품질이 조직에서 설정한 목표를 충족할 수 있는 경우에도 평균 메트릭 뒤에 숨겨진 통화 품질 문제가 있을 수 있습니다. CQD를 사용하면 QoEMetrics 데이터베이스의 여러 차원에 따라 통화 품질 메트릭을 피벗 테이블과 같은 분석할 수 있습니다. 피어 그룹에서 아웃리저를 검색하는 것은 통화 품질 문제를 신속하게 찾는 빠른 방법입니다.
  
 **조직에 통화 품질 문제가 있는 경우 CQD를 배포하여 문제를 해결하는 데 필요한 시간을 줄여야 합니다.** CQD는 빠른 보고 성능 및 동적 드릴다운 기능을 제공하여 기존 통화 품질 조사를 단순화할 수 있습니다. CQD는 환경에 대한 복구의 통화 품질 조사 유효성 검사에서 다양한 종류의 워크플로를 위해 설계되었습니다.
  
### <a name="why-deploy-cqd"></a>CQD를 배포하는 이유

 **3개월 이상 데이터를 QoE 보고해야 하는 경우 CQD를 배포해야 합니다.** QoEMetrics 데이터베이스 및 모니터링 서버 보고서는 작은 데이터 집합을 보존하고 보고하도록 디자인되었습니다. QoE 메트릭 데이터베이스는 빠른 삽입에 최적화되어 있으므로 많은 수의 통화 또는 데이터베이스에 대한 경쟁 보고 액세스로 보고 성능이 빨라야 할 수 있습니다. CQD의 QoE 보관 데이터베이스는 보존 기능이 훨씬 더 긴 QoE 메트릭 데이터의 두 번째 복사본을 제공합니다. 또한 포털은 한에 최대 7개월의 데이터를 표시하도록 최적화되어 있으며 필요한 경우 QoE 보관함의 모든 데이터를 보고할 수 있습니다.
  
 **사용자 지정 QoE 보고서가 필요한 경우 CQD를 배포해야 합니다.** 포털에는 보고서를 쉽고 빠르게 만들고 프로토타이핑하기 위한 보고서 편집기 기능이 있습니다. 또한 큐브 데이터에 프로그래밍식으로 액세스할 수 있도록 REST API를 사용하여 HTML/JavaScript 또는 다른 여러 프레임워크를 사용하여 사용자 지정 프레젠테이션을 할 수 있습니다. 보고를 위한 사용자 지정 데이터 보기를 만들기 위해 새 SQL 쿼리를 더 이상 만들 필요가 없습니다.
  
 **기존 QoE 보고 기능이 조직에 필요한 속도 또는 깊이를 충족하지 않는 경우 CQD를 배포해야 합니다.** CQD에는 많은 기본 제공 보고서가 함께 제공되어 있습니다. 보고서는 즉시 유용하며 데이터를 점진적으로 드릴링하여 각 수준에서 추가 정보를 제공하는 방법을 보여 주며, 또한 보고서 계층 구조는 여러 보고서를 논리적으로 관리하는 데 도움이 며, 쉽게 액세스할 수 있으며 이해하기 쉽게 더 많은 보고서를 만들 수 있도록 합니다. CQD는 속도와 유연성을 제공하는 것이 아니라 통화 품질 방법론에서 개발한 워크플로에 최적화되어 있습니다.
  
## <a name="components-and-topologies-for-cqd"></a>CQD의 구성 요소 및 토폴로지

CQD는 여러 구성 요소와 함께 제공될 수 있으며 각 구성 요소의 요구 사항과 서로의 관계를 이해하여 가장 간단하고 최상의 도구 배포를 얻을 수 있도록 합니다. 다음 표에서는 각 CQD 구성 요소에 대한 종속 구성 요소에 대해 설명합니다.
  

|**구성 요소 이름**|**종속 구성 요소**|
|:-----|:-----|
|QoE 보관  <br/> |Microsoft SQL Server  <br/> |
|큐브  <br/> |Microsoft SQL Server Analysis Services  <br/> |
|포털  <br/> |Microsoft Information Services  <br/> |
|리포지토리 서비스(포털 설치의 일부)  <br/> |Microsoft SQL Server  <br/> |
   
> [!NOTE]
> QoE 보관 파일 및 큐브의 경우 특정 배포 옵션에는 비즈니스 인텔리전스 또는 Enterprise 버전이 Microsoft SQL Server. 자세한 내용은 [아래의 CQD](plan.md#Infrastructure_Req) 인프라 요구 사항 섹션을 참조하세요.
  
![CQD 구성 요소](../../media/a52f2e6c-a4dd-4de3-879c-47295d2366c3.png)
  
### <a name="single-server-configuration"></a>단일 서버 구성

모든 CQD 구성 요소 및 종속 구성 요소를 하나의 컴퓨터에 설치할 수 있습니다. 단일 상자 구성은 가장 간단한 구성으로 CQD가 자체 포함될 수 있습니다. CQD는 모니터링 서버의 QoE 메트릭 데이터베이스에만 액세스하면 됩니다. CQD 서버는 독립 실행형 컴퓨터일 수도, 가상 컴퓨터일 수도 있으며, 호스트 컴퓨터의 사용 가능한 리소스 및 성능 요구 사항에 따라 모니터링 서버일 수도 있습니다. 
  
설치를 수행하는 사용자는 CQD를 설치할 컴퓨터에 이전에 설정한 Microsoft SQL Server 및 Microsoft SQL Server Analysis Services 인스턴스를 제공하면 됩니다. 자세한 내용은 [비즈니스용 Skype 서버용](deploy-0.md) 통화 품질 대시보드 배포를 참조하세요.
  
### <a name="multiserver-configuration"></a>다중 서비스 구성

다중 서비스 구성에서 QoE 보관함, 큐브 및 포털은 모두 서로 다른 컴퓨터일 수 있습니다. 다중 서비스 구성에는 두 가지 주요 용도가 있습니다.
  
- 서로 다른 서버에서 CQD 웹 포털 및 CQD 큐브 호스팅
    
- "프로덕션" 포털과는 별개로 "개발" 포털을 호스팅합니다. 
    
  **서로 다른 컴퓨터의 CQD 웹 포털 및 CQD 큐브 호스팅** CQD 포털을 SQL Server 설치와 분리해야 할 수 있는 조직 또는 SQL Server 인스턴스 및 SQL Server Analysis Services 인스턴스에 대한 SQL Server 에디션을 혼합하고 일치하려는 조직은 서로 다른 컴퓨터에 CQD 포털 및 CQD 큐브를 설치하도록 선택할 수 있습니다. QoE 보관 구성 요소는 조직이 모니터링 서버의 성능 제한에 도달하지 않고 QoE 데이터를 보관하는 지속 가능한 방법을 사용하려는 경우 설치되는 유일한 CQD 구성 요소일 수도 있습니다.
  
![단일 서버 CQD](../../media/f65be6f3-6bba-4c3d-b3ae-c05e03551b5b.png)
  
 **"프로덕션" 포털과는 별개로 "개발" 포털을 호스팅합니다.** REST API를 통해 자체 사용자 지정 보고서를 개발하는 조직에서는 일반 사용자가 통화 품질 모니터링 또는 조사를 위해 액세스하는 추가(CQD) 포털 인스턴스를 프로덕션 포털과 함께 배포하는 것이 좋습니다. 개발 포털은 포털에 대한 수정 내용을 프로덕션 환경에서 격리할 수 있습니다. 다른 컴퓨터(아래 그림 참조)에 추가 웹 포털을 배포하거나 동일한 컴퓨터의 서로 다른 웹디렉터에 배포할 수 있습니다(표시 안 하세요). 후자의 경우 CQD 설정 프로세스에서 항상 미리 정의한 웹 응용 프로그램 이름이 있는 기본 웹 사이트에 CQD 웹 포털을 배포하기 때문에 추가 CQD 웹 포털을 프로덕션 컴퓨터로 수동으로 복사해야 합니다.
  
![CQD 다중 서버 계획](../../media/2326e61e-b485-43e6-9f82-145237ba89cf.png)
  
### <a name="supported-topologies"></a>지원되는 토폴로지

CQD는 각각 자체 모니터링 서버를 사용하여 비즈니스용 Skype 서버 토폴로지가 여러 개 있는 경우처럼 여러 QoEMetrics 데이터베이스의 데이터를 병합하지 않습니다. 각 CQD 인스턴스는 하나의 QoEMetrics 데이터베이스를 지점으로 해야 합니다. 그러나 CQD는 모니터링 서버의 상당수 보고 작업을 벗어날 것이기 때문에 비즈니스용 Skype 서버 토폴로지당 모니터링 서버 하나를 배포해야 하는 대규모 조직에서는 모든 토폴로지에서 하나의 모니터링 서버를 사용하는 것이 좋습니다.
  
## <a name="infrastructure-requirements-for-cqd"></a>CQD에 대한 인프라 요구 사항
<a name="Infrastructure_Req"> </a>

모든 구성 요소 및 종속 구성 요소를 포함한 CQD는 가상 컴퓨터, 단일 컴퓨터 또는 여러 컴퓨터로 배포할 수 있습니다. 최소 소프트웨어 및 하드웨어 요구 사항은 아래에 나와 있습니다. 데이터 가용성 및 쿼리 성능은 활성 비즈니스용 Skype 서버 사용자 수 및 하드웨어 및 구성에 따라 몇 분에서 몇 시간까지 달라질 수 있으므로 아래에 몇 가지 성능 측정값이 제공됩니다.
  
|||
|:-----|:-----|
|CQD 2015의 경우 <br/> |  <br/> |
|지원되는 운영 체제   <br/> |Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2  <br/> |
|지원되는 SQL Server  <br/> |SQL Server 2012, SQL Server 2014, SQL Server 2016  <br/> |

|||
|:-----|:-----|
|CQD 2019의 경우 <br/> |  <br/> |
|지원되는 운영 체제   <br/> |Windows Server 2016, Windows Server 2019  <br/> |
|지원되는 SQL Server  <br/> |SQL Server 2017, SQL Server 2019  <br/> |
   
CQD는 Microsoft SQL Server, Microsoft SQL Server Analysis Services 및 Microsoft 인터넷 정보 서비스 사용하여 CQD의 최소 하드웨어 및 소프트웨어 요구 사항은 기본적으로 해당 종속 구성 요소와 동일합니다. 그러나 데이터 최신성에 대한 조직의 요구 사항(조직에서 생성하는 QoE 데이터 양에 따라 달라지기) 및 배포 비용에 따라 배포 비용을 추가로 고려해야 합니다.
  
CQD의 데이터 처리는 두 가지 기본 단계로 구분됩니다. 
  
- QoE 보관 프로세스
    
- CQD 큐브 처리
    
  **QoE 보관 처리.** QoE 보관 처리 작업은 모니터링 서버의 QoE 메트릭 데이터베이스에서 QoE 보관 데이터베이스로 데이터를 복사합니다. 작업의 처리 시간이 기본적으로 다른 성능 특성을 가지는 두 가지 상황이 있습니다. 첫 번째는 CQD의 초기 설치 후입니다. 새 설치 후 작업을 처음으로 실행하면 QoE 보관함 처리 작업이 QoE 메트릭 데이터베이스에 있는 모든 데이터를 QoE 보관 데이터베이스로 복사합니다. 두 번째는 이 초기 라운드 이후의 주기적인 처리입니다. QoE 보관 처리 작업은 15분마다 실행하고 QoE 메트릭 데이터베이스에 있는 새 QoE 레코드를 처리합니다. 일반적으로 초기 처리 시간은 CQD가 설치될 때 처음 실행되는 것이기 때문에 걱정할 수 없습니다. 그러나 CQD 서버가 심각하게 프로비전되지 않았다면 이 작업은 몇 시간이 걸릴 수 있습니다. 초기 QoE 보관 처리 시간과 같은 경우 아래 표를 참조하세요.
  
  **CQD 큐브 처리** 큐브 처리 작업은 QoE 보관 데이터베이스의 데이터를 큐브로 집계합니다. 초기 큐브 처리 시간 및 후속 큐브 처리 시간은 CQD SQL Server Analysis Services 버전에 따라 결정됩니다. Standard Edition을 사용하는 경우 큐브 데이터를 새로 고칠 때마다 항상 사용 가능한 모든 데이터를 모두 처리하기 때문에 초기 큐브 처리 시간과 이후 큐브 처리 시간 간에는 차이가 없습니다. 즉, QoE 보관 데이터베이스의 데이터 양이 증가하면 큐브 처리 시간이 증가합니다. Business Intelligence Edition 및 Enterprise Edition은 SQL Server 지원하기 때문에 두 버전 중 하나를 사용하는 경우 초기 실행만 QoE 보관 데이터베이스의 모든 데이터를 처리합니다. 이후 실행에서는 작업이 15분마다 트리거될 때 작업이 마지막으로 실행된 이후 QoE 보관 데이터베이스에 추가된 새 레코드만 처리합니다. 하루 중 한 번만 현재 월의 데이터를 포함하는 파티션에 전체 처리가 진행됩니다.
  
실제 컴퓨터 특성은 CQD 성능과 여러 구성 요소에서 사용할 수 있는 소프트웨어 기능에 SQL Server 있습니다. QoE Archive 구성 요소는 다른 구성 요소에 비해 디스크를 많이 사용하는 반면 큐브 구성 요소는 CPU와 메모리를 많이 사용합니다. 이러한 모든 요인은 CQD의 총 데이터 처리 시간에 영향을 주며, 이는 데이터 신선도 및 가용성에 직접적인 영향을 미치게 됩니다. 조직은 조직의 개별 요구에 따라 하드웨어 및 소프트웨어를 결정해야 합니다. 
  
### <a name="tested-hardware-configurations"></a>테스트된 하드웨어 구성

이 섹션에서는 환경에 QoEMetrics DB가 하나만 있는 것으로 가정합니다. 
  
**컴퓨터 프로필**

|**컴퓨터**|**CPU 코어**|**RAM**|**동일한 디스크의 QoE 보관 및 큐브**|**QoE 보관함 및 SQL 디스크에 Temp DB 추가**|
|:-----|:-----|:-----|:-----|:-----|
|가상 컴퓨터  <br/> |4   <br/> |7GB  <br/> |예  <br/> |예  <br/> |
|4개 코어  <br/> |4   <br/> |20GB  <br/> |예  <br/> |아니요  <br/> |
|8개 코어  <br/> |8   <br/> |32GB  <br/> |예  <br/> |아니요  <br/> |
|16개 코어  <br/> |16   <br/> |128GB  <br/> |아니요  <br/> |아니요  <br/> |
   
**성능 결과**

|**컴퓨터**|**QoE 메트릭 DB 크기**|**SQL 파티션**|**디스크 유형**|**스트림 수**|**초기 보관 프로세스**|**초기 큐브 프로세스**|**후속 보관 프로세스**|**후속 큐브 프로세스**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|가상 컴퓨터  <br/> |900MB  <br/> |단일  <br/> |VHD(가변 크기)  <br/> |.5 M  <br/> |30m  <br/> |2m  <br/> |30 s  <br/> |1m  <br/> |
|가상 컴퓨터  <br/> |9GB  <br/> |단일  <br/> |VHD(가변 크기)  <br/> |5M  <br/> |4시간  <br/> |15m  <br/> |1m  <br/> |5m  <br/> |
|가상 컴퓨터  <br/> |9GB  <br/> |단일  <br/> |VHD(고정 크기)  <br/> |5M  <br/> |2시간  <br/> |5m  <br/> |1m  <br/> |5m  <br/> |
|가상 컴퓨터  <br/> |30GB  <br/> |단일  <br/> |VHD(고정 크기)  <br/> |10M  <br/> |15 h  <br/> |20m  <br/> |2m  <br/> |45m  <br/> |
|8개 코어  <br/> |9GB  <br/> |단일  <br/> |여러 디스크  <br/> |5M  <br/> |2시간  <br/> |5m  <br/> |25 s  <br/> |5m  <br/> |
|8개 코어  <br/> |9GB  <br/> |여러 개  <br/> |여러 디스크  <br/> |5M  <br/> |2시간  <br/> |15m  <br/> |35 s  <br/> |2m  <br/> |
|8개 코어  <br/> |30GB  <br/> |단일  <br/> |여러 디스크  <br/> |20 M  <br/> |9 h  <br/> |20m  <br/> |1m  <br/> |20m  <br/> |
|8개 코어  <br/> |30GB  <br/> |여러 개  <br/> |여러 디스크  <br/> |20 M  <br/> |9 h  <br/> |30m  <br/> |2m  <br/> |2m  <br/> |
|4개 코어  <br/> |200GB  <br/> |단일  <br/> |여러 디스크  <br/> |125M  <br/> |6일 이상  <br/> |7 h  <br/> |2m  <br/> |6 h  <br/> |
|16개 코어  <br/> |500GB  <br/> |여러 개  <br/> |여러 스핀들  <br/> |250M  <br/> |8일  <br/> |2시간  <br/> |2m  <br/> |10m  <br/> |
   
\*QoE 메트릭 데이터베이스에는 각각 9개월과 18개월의 데이터가 저장해야 했지만 완전한 구성을 위해 여기에 제공된 것이기 때문에 실제 배포에서는 이러한 문제가 발생할 수 없습니다.
  
### <a name="service-account-requirements"></a>서비스 계정 요구 사항

CQD 서버의 SQL 에이전트가 QoEArchiveDB로 데이터를 가져오는 데 사용할 수 있는 계정(QoEMetrics에 대한 읽기 권한이 있는)이 필요합니다.
  
QoEArchiveDB에서 데이터를 끌어오도록 SSAS 작업의 별도 계정을 구성해야 할 수도 있습니다(선택적 프로세스임).
  
IIS는 가장 일반적으로 네트워크 서비스를 앱 풀 ID로 사용하지만 서비스 계정으로 구성할 수 있습니다.
  
### <a name="portal-access-control"></a>포털 액세스 제어

기본적으로 인증된 사용자는 액세스할 수 있습니다. 이 설정은 IIS 권한 부여 규칙을 사용하여 특정 그룹으로 제한하여 변경할 수 있습니다.
  
### <a name="pre-install-requirements"></a>사전 설치 요구 사항

이러한 지침에서는 QoE 메트릭 데이터베이스가 이미 설치되어 있으며 비즈니스용 Skype 서버 토폴로지에서 실행되고 있는 것으로 가정합니다.
  
#### <a name="hardware-requirements"></a>하드웨어 요구 사항

CQD는 Microsoft SQL Server, Microsoft SQL Analysis Server 및 Microsoft Internet Information Server를 사용하여 CQD의 최소 하드웨어 및 소프트웨어 요구 사항은 기본적으로 해당 종속 구성 요소와 동일합니다. 그러나 데이터 최신성에 대한 조직의 요구 사항(조직에서 생성하는 QoE 데이터 양에 따라 달라지기) 및 배포 비용에 따라 배포 비용을 추가로 고려해야 합니다.
  
#### <a name="software-requirements"></a>소프트웨어 요구 사항

CQD에는 다음 운영 체제가 필요합니다.
  
- IIS 7.5가 있는 Windows Server 2008 R2
    
- Windows Server 2012 IIS 8.0을 사용할 수 있습니다.
    
- Windows Server 2012 R2 IIS 8.5

- IIS 10.0이 있는 Windows Server 2016(비즈니스용 Skype 서버 2019 CQD만 해당)

- Windows Server 2019(비즈니스용 Skype 서버 2019 CQD만 해당)
    
다음은 필요한 IIS 역할 서비스(계층적 순서)입니다.
  
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
>  위의 요구 사항에 대한 다음 사항에 유의하세요.> 3.5 및 4.5 버전의 .Net framework를 사용할 수 있습니다. 두 가지 모두 필요합니다(특히 3.5 SP1이 필요합니다).> 일부 시스템에서 IIS 설치 전에 ASP.NET 설정되어 있는 경우 IIS에 ASP.NET 등록되지 않을 수 있습니다. 해당 .Net 버전에 대한 응용 프로그램 풀이 없을 때와 앱 풀 구성에서 .NET CLR 버전이 누락되어 문제가 매니페스트됩니다. Windows Server 2008 R2에서 이러한 문제를 해결하기 위해 를 `%systemroot%\Microsoft.NET\Framework64\4.0.30319\aspnet_regiis.exe -iru` 실행합니다. R2 Windows Server 2012 Windows Server 2012 IIS 관리자의 기본 웹 사이트에서 "ServiceModel" 모듈을 제거한 다음 실행합니다.> 관리 도구는 선택 사항이지만  `dism /online /enable-Feature /all /FeatureName:WCF-HTTP-Activation45` 사용하는 것이 좋습니다.
  
PowerShell을 사용하여 이러한 요구 사항을 설치하려면 다음을 실행합니다.
  
```PowerShell
import-module servermanager
```

```PowerShell
add-windowsfeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Asp-Net, Web-Asp-Net45, Web-Net-Ext, Web-Net-Ext45, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Url-Auth, Web-Windows-Auth, Web-Mgmt-Console
```

다음 버전의 SQL Server 지원됩니다.
  
|||
|:-----|:-----|
| CQD 2015 <br/> |  SQL Server 2012, SQL Server 2014, SQL Server 2016  |
|CQD 2019 <br/> |  SQL Server 2017, SQL Server 2019  |
    
성능상의 이유로 비즈니스 인텔리전스 또는 Enterprise 버전이 권장됩니다. 이러한 버전은 병렬로 처리될 수 있는 여러 파티션 파일을 사용할 수 있도록 하여 여러 개월 이상에 걸쳐 데이터를 처리하는 데 도움이 됩니다. 
  
권장되지는 않는 경우 Standard Edition도 지원됩니다. 처리는 설치 중에 구성해야 하는 단일 파티션으로 제한됩니다. 
  
모든 경우에 "데이터베이스 엔진 서비스" 및 "Analysis Services"를 설치해야 합니다. Analysis Services에 대한 추가 지원이 추가되는 "관리 도구 - 완료" 기능도 SQL Server Management Studio 것은 아닙니다. 기능 선택 화면은 그림과 같아야 합니다.
  
![SQL Server 기능 요구 사항](../../media/37f2f64b-49c8-4620-94ba-f6d1ae9abf83.png)
  
SSAS 설정을 구성할 때 Analysis Services 구성에서 "서버 모드"를 "다차원 및 데이터 마이너링 모드"로 설정하십시오. 
  
비즈니스 인텔리전스 기능을 설치 및 구성하는 SQL Server 자세한 내용은 [Install Analysis Services in Multidimensional and Data Mining Mode를 참조합니다.](/previous-versions/sql/sql-server-2012/ms143708(v=sql.110))
  
#### <a name="account-requirements"></a>계정 요구 사항

최소 권한 원칙에 따라 세 개의 도메인 서비스 계정이 권장됩니다. 
  
- QoE 메트릭 데이터베이스에 대한 로그인 보안 주체(db_datareader 권한 사용) 및 QoE Archive SQL Server Instance의 로그인 보안 주체(설치 중에 연결된 서버 개체를 만드는 데 필요함)가 모두 있는 보안 주체입니다. 이 계정은 에이전트 작업의 "QoE 보관 데이터" 단계를 SQL Server 사용됩니다.
    
    > [!NOTE]
    > 과도하게 잠겨 있는 환경에서 작업하는 경우 QoE 메트릭 모니터링 데이터베이스 및 QoE 보관 데이터베이스 모두에 대해 이 서비스 계정에 "일괄 처리 작업으로 로그온" 및 "로컬로 로그온 허용" 사용자 권한이 부여되어 SQL Server 해야 SQL Server.
    
- 에이전트 작업의 "프로세스 큐브" 단계를 SQL Server 사용됩니다. 설치 프로그램이 QoE 보관 데이터베이스에 대한 로그인 보안 주체(읽기 및 쓰기 권한 사용)를 만들고 큐브에 대한 QoE 역할(모든 권한 사용 권한 사용)에 구성원을 만듭니다.
    
- 웹 포털 및 웹 API에 대해 IIS Worker 프로세스를 실행하는 데 사용됩니다. 설치 프로그램이 QoE 보관 데이터베이스에 대한 로그인 보안 주체(읽기 권한 포함), 저장소 데이터베이스에 대한 로그인 보안 주체(읽기 및 쓰기 권한 사용) 및 큐브에 대한 QoERole의 구성원(모든 권한 사용 권한 사용)을 만듭니다. 
    
    > [!NOTE]
    > QoE 보관 데이터베이스와 리포지토리 데이터베이스가 모두 동일한 데이터베이스에서 호스팅되는 SQL Server 두 개의 사용자 매핑이 있는 로그인 보안 주체가 하나만 만들어집니다. 
  
처음 두 계정은 논리적으로 "백 엔드 서비스 계정"으로 간주될 수 있으며 마지막 계정은 "프런트 엔드 서비스 계정"입니다. 권장되지는 않습니다. 그러나 모든 경우에 단일 계정을 사용할 수 있습니다.
  
> [!NOTE]
> 설치를 시작하는 사용자 계정에는 QoE 메트릭 DB에 대한 읽기 권한도 있어야 합니다(설치가 진행되어야 하는 QoE 보관 DB 서버에 대해 컴퓨터 관리자 권한이 있어야 합니다). 
  
## <a name="capacity-planning"></a>용량 계획
<a name="Infrastructure_Req"> </a>

CQD는 QoEMetrics에 대한 영향을 최소화하도록 디자인되어 있습니다. 코드가 데이터를 잠그지 못하도록 최적화되어 있으며 가져오기 작업을 할 수 없습니다.
  
사용할 하드웨어의 유형은 동기화 실행을 얼마나 빨리 해야 하는지의 요구 사항에 따라 다릅니다. 디스크 크기 조정은 다음과 같습니다.
  
- QoEArchive는 처음에 QoEMetrics DB보다 1.5배 더 크기
    
- SSIS 큐브는 DB에 비해 데이터를 10배 정도 압축합니다.
    
- 데이터는 월별 분할됩니다. 파티션을 삭제할 수 있습니다.
