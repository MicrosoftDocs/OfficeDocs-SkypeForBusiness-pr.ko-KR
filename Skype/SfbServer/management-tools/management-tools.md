---
title: 비즈니스용 Skype 서버 2015 관리 도구
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 4e956558-8cba-47d9-b96a-537d7f6ed938
description: '요약: 비즈니스용 Skype 서버 2015의 서비스 관리 도구에 대해 자세히 알아보는 방법을 설명하는 문서입니다.'
---

# <a name="skype-for-business-server-2015-management-tools"></a>비즈니스용 Skype 서버 2015 관리 도구
 
**요약:** 2015의 서비스 관리 도구에 비즈니스용 Skype 서버 대해 자세히 알아보습니다.
  
비즈니스용 Skype 서버 2015 통신 소프트웨어(이전의 Lync Server)에서는 엔터프라이즈 수준의 공동 작업 요구 사항을 지원하는 IM(인스턴트 메시징), 현재 상태, 회의 및 전화 통신 솔루션을 제공합니다. 이러한 서비스를 관리하는 도구는 유연하고 강력합니다. 
  
## <a name="skype-for-business-server-2015-tools"></a>비즈니스용 Skype 서버 2015 도구

|&nbsp;|콘텐츠|설명|
|:-----|:-----|:-----|
||[Microsoft 통화 품질 방법론 Scorecard, v1.5](https://go.microsoft.com/fwlink/p/?LinkId=615208) (.zip 다운로드) <br/> [CQM 포스터 for 비즈니스용 Skype](https://go.microsoft.com/fwlink/p/?LinkID=617898) <br/> [Lync 2013용 CQM 포스터](https://go.microsoft.com/fwlink/p/?LinkId=391841)  |Lync Server 및 2015용 Microsoft CQM(통화 품질 방법론) 비즈니스용 Skype 서버 버전입니다. CQM 점수 기록표를 사용하여 통화 품질 방법론을 구현할 수 있습니다. 이 방법을 사용하면 네트워킹 가이드에 설명된 메서드에 따라 통화 품질을 체계적으로 정의하고 보장할 수 있습니다. CQM은 Lync/비즈니스용 Skype 구현을 품질에 영향을 미치는 10개 영역으로 나누고 각각에 대한 대상 및 수정 계획을 정의합니다. CQM은 통화 품질 문제를 해결하기 위한 프레임워크입니다. 네트워크의 특정 조건을 해결하기 위해 이를 수정하거나 확장할 수 있습니다.  <br/> CQM 포스터는 Lync/Lync/비즈니스용 Skype 구현에 대한 통화 품질 및 사용자 경험에 영향을 주는 문제를 찾아서 제거하는 데 도움이 되는 Lync 및 Ly 비즈니스용 Skype nc용 통화 품질 방법론인 CQM에 대해 자세히 알아보는 데 도움이 될 수 있습니다.  <br/>**참고:** 이러한 도구는 2019년 8월에 비즈니스용 Skype 서버 않습니다. |
|![대시보드 아이콘.](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[통화 품질 대시보드](./call-quality-dashboard/call-quality-dashboard.md)  |CQD(통화 품질 대시보드)는 사용자 환경 또는 Lync 환경에서 QoE(QoE) 데이터를 기반으로 보고서를 빠르게 만들고 구성하기 위한 웹 비즈니스용 Skype 포털입니다. CQD는 SSAS 큐브를 배포하여 QoEMetrics 데이터베이스의 데이터를 집계하여 사용자가 보고서를 만들고 수정하고 실시간으로 업데이트를 볼 수 있도록 합니다. 또한 CQD는 사용자가 사용자 지정 대시보드에서 사용할 큐브 데이터에 프로그래밍된 액세스 권한을 부여하는 웹 API를 노출합니다.   |
|![KHI 아이콘입니다.](../media/8759b767-b689-4a95-94a5-5b27c5688688.png)|[KHI 리소스](https://go.microsoft.com/fwlink/p/?LinkId=534843)  |KHI(키 상태 표시기)는 사용자 환경에 영향을 줄 수 있는 문제를 표시하기 위한 권장 임계값이 있는 성능 카운터입니다. KHI 가이드에서는 정상 배포를 유지하기 위한 운영 프로세스 및 수정 단계를 간략하게 설명하고 KHI 데이터 수집기 구성에 사용되는 예제 PowerShell 스크립트와 KHI 성능 데이터를 분석할 수 있는 분석 및 정의 통합 문서가 포함되어 있습니다.   |
|![대시보드 아이콘.](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[2015년 비즈니스용 Skype 서버 통계 관리자](statistics-manager/statistics-manager.md)  |StatsMan은 인프라 전체에서 집계된 그래프 성능 카운터뿐만 아니라 KHI 계산을 실시간으로 볼 수 있는 대시보드 솔루션입니다. 대시보드를 사용하여 지속적인 성능 문제를 확인하고, 환경의 계획된 변경 결과를 보고, 중단 해결을 추적하는 등 다양한 정보를 볼 수 있습니다. KHI 리소스의 KHI 임계값으로 구성됩니다. 배포의 고유한 요구 사항에 맞게 사용자 지정될 수 있습니다.   |
|![대시보드 아이콘.](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[비즈니스용 Skype 서버 2015 Resource Kit 도구](https://www.microsoft.com/download/details.aspx?id=52631)  |비즈니스용 Skype 서버 2015 리소스 키트 도구를 사용하면 2015년을 배포하고 관리하는 IT 관리자가 몇 가지 일상적인 작업을 비즈니스용 Skype 서버 있습니다.   |
|![네트워크 아이콘.](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[네트워킹 가이드](https://go.microsoft.com/fwlink/p/?LinkID=390677)  |Microsoft Lync Server 2013 및 비즈니스용 Skype 2015 통신 소프트웨어는 피어-투-피어 A/V(오디오 및 비디오) 통화, 회의 및 공동 작업을 지원하고 최적화된 신뢰할 수 있는 네트워크 인프라를 사용하여 클라이언트 간에 고품질 미디어 세션을 전달합니다. 네트워킹 가이드는 계획, 모니터링 및 문제 해결의 비즈니스용 Skype Lync 및 Lync에 대한 네트워크 인프라를 관리하기 위한 모델을 제공합니다. 이러한 단계는 새 Lync 또는 비즈니스용 Skype 서버 배포 또는 기존 배포에 적용할 수 있습니다. 네트워킹 가이드에 대한 최근 변경된 Lync/Skype 및 Wi-Fi 정책 구성에 대해 설명했습니다.   |
|![클립보드 아이콘](../media/2e0c9c21-cd2a-4db5-8cb7-d2c0b1b159b7.png)|[비즈니스용 Skype 2015의 중앙 로깅 서비스](centralized-logging-service/centralized-logging-service.md)  |중앙 로깅 서비스는 근본 원인 분석에서 성능 문제까지 크고 작은 문제에 대한 강력한 문제 해결 도구입니다. 모든 예제는 관리 셸을 사용하여 비즈니스용 Skype 서버 있습니다. 도구 자체를 통해 명령줄 도구에 대한 도움말이 제공되지만 명령줄에서 실행할 수 있는 기능은 제한적입니다. 비즈니스용 Skype 서버 관리 셸을 사용하면 훨씬 더 크고 훨씬 더 많은 구성 가능한 기능 집합에 액세스할 수 있으므로 항상 첫 번째 선택이 될 수 있습니다.   |
|![SCOM 아이콘.](../media/3a7601cb-dd2f-4606-8a3b-07c7abdc091a.png)|[SCOM 비즈니스용 Skype 서버 사용하여 2015 관리](use-scom-management-pack/use-scom-management-pack.md)  |2015 비즈니스용 Skype 서버 팩을 사용하면 잠재적인 문제를 사전 예방적으로 식별하고 해결할 수 있습니다. 이러한 방식으로 비즈니스용 Skype 서버 2015 관리 팩은 System Center 관리자의 기능을 확장합니다.   |
|![대시보드 아이콘.](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[비즈니스용 Skype 서버 2015 계획 도구](planning-tool/planning-tool.md)  |비즈니스용 Skype 2015 계획 도구에서는 토폴로지 계획을 시작할 수 있는 지침을 제공합니다.  <br/> **참고:** 이 도구는 2019년 8월에 비즈니스용 Skype 서버 않습니다. |
|![대시보드 아이콘.](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[비즈니스용 Skype 서버 2015 용량 계획 계산기](capacity-planning-calculator.md)  |비즈니스용 Skype 서버 2015 용량 계획 계산기를 사용하면 조직의 요구에 따라 토폴로지 모델링을 할 수 있습니다.   |
|![네트워크 아이콘.](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[비즈니스용 Skype 서버 2015 스트레스 및 성능 도구](stress-and-performance-tool/stress-and-performance-tool.md)  |이 도구를 사용하면 2015 환경의 사용자 부하를 사용하여 다양한 성능 관련 테스트를 비즈니스용 Skype 서버 수 있습니다. 예제 스크립트는 고유한 환경 요구에 도움이 되는 도구와 함께 제공됩니다.  <br/>**참고:** 이 도구는 2019년 8월에 비즈니스용 Skype 서버 않습니다. |
   
## <a name="see-also"></a>참고 항목

[Lync Server 2013 도구](/previous-versions/office/lync-server-2013/lync-server-2013-tools)
  
[Lync Server 2010 도구](/previous-versions/office/lync-server-2010-tools/dn145002(v=ocs.14))