---
title: 비즈니스용 Skype 서버 2015 관리 도구
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4e956558-8cba-47d9-b96a-537d7f6ed938
description: '요약: 비즈니스용 Skype 서버 2015의 서비스 관리 도구에 대해 알아봅니다.'
ms.openlocfilehash: 58d6184f1fc68e87831b3d7d3177085c482784f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031062"
---
# <a name="skype-for-business-server-2015-management-tools"></a>비즈니스용 Skype 서버 2015 관리 도구
 
**요약:** 비즈니스용 Skype 서버 2015의 서비스 관리 도구에 대해 알아봅니다.
  
비즈니스용 Skype 서버 2015 communications software (이전의 Lync Server)에서는 엔터프라이즈 수준 공동 작업 요구 사항을 지 원하는 IM (인스턴트 메시징), 현재 상태, 회의 및 전화 통신 솔루션을 제공 합니다. 이러한 서비스를 관리 하는 도구는 유연 하 고도 강력 합니다. 
  
## <a name="skype-for-business-server-2015-tools"></a>비즈니스용 Skype 서버 2015 도구

||**콘텐츠**|**설명**|
|:-----|:-----|:-----|
||[Microsoft 통화 품질 방법론 성과 기록표, v 1.5](https://go.microsoft.com/fwlink/p/?LinkId=615208) (.zip 다운로드) <br/> [비즈니스용 Skype에 대 한 CQM 포스터](https://go.microsoft.com/fwlink/p/?LinkID=617898) <br/> [Lync 2013 용 CQM 포스터](https://go.microsoft.com/fwlink/p/?LinkId=391841) <br/> |Lync Server 및 비즈니스용 Skype 서버 2015에 대 한 Microsoft CQM (통화 품질 방법론) 성과 기록표가 업데이트 된 버전입니다. CQM 성과 기록표를 사용 하 여 네트워크 가이드에 설명 된 방법에 따라 전체적으로 통화 품질을 정의 하 고 어설션할 수 있는 방법인 통화 품질 방법론을 구현 합니다. CQM에서는 비즈니스용 Skype 구현에 품질에 영향을 주는 10 개의 개별 영역인 각 영역에 대 한 목표 및 업데이트 관리 계획을 나눕니다. CQM는 통화 품질 문제를 처리 하는 프레임 워크 이며 네트워크의 특정 조건에 맞게 수정 하거나 확장할 수 있습니다.  <br/> CQM 포스터를 통해 CQM, lync 및 비즈니스용 Skype에 대 한 통화 품질 방법론은 enterprise voice 기능을 포함 하는 Lync/비즈니스용 skype 구현의 통화 품질 및 사용자 환경에 영향을 주는 문제를 찾아서 제거할 수 있도록 도와줍니다.  <br/>**참고:** 이러한 도구는 비즈니스용 Skype 서버 2019에 대해서는 업데이트 되지 않습니다. |
|![대시보드 아이콘](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[통화 품질 대시보드](https://go.microsoft.com/fwlink/p/?LinkId=534842) <br/> |CQD (통화 품질 대시보드)는 비즈니스용 Skype 또는 Lync 환경의 QoE (경력 품질) 데이터를 기반으로 하는 보고서를 신속 하 게 작성 및 구성 하기 위한 웹 포털입니다. CQD는 QoEMetrics 데이터베이스의 데이터를 집계 하기 위해 SSAS 큐브를 배포 하며,이를 통해 사용자가 보고서를 만들고 수정 하 고 실시간으로 확인할 수 있습니다. 또한 CQD는 사용자가 사용자 지정 대시보드에서 사용할 큐브 데이터에 프로그래밍 방식으로 액세스할 수 있도록 하는 웹 Api를 제공 합니다.  <br/> |
|![KHI 아이콘](../media/8759b767-b689-4a95-94a5-5b27c5688688.png)|[KHI 리소스](https://go.microsoft.com/fwlink/p/?LinkId=534843) <br/> |KHI (키 상태 지표)는 사용자 환경에 영향을 줄 수 있는 문제 노출을 위한 권장 임계값을 갖는 성능 카운터입니다. KHI 가이드에서는 정상적인 배포를 유지 하기 위한 운영 프로세스 및 업데이트 관리 단계를 간략하게 설명 하 고, khi 데이터 수집기를 구성 하는 데 사용 되는 샘플 PowerShell 스크립트와 KHI 성능 데이터를 분석할 수 있는 분석 및 정의 통합 문서를 포함 합니다.  <br/> |
|![대시보드 아이콘](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[비즈니스용 Skype 서버 2015에 대 한 통계 관리자](statistics-manager/statistics-manager.md) <br/> |StatsMan은 실시간으로 KHI를 보고, 인프라에서 집계 된 성능 카운터를 그래프로 표시 하는 대시보드 솔루션입니다. 대시보드를 사용 하 여 진행 중인 성능 문제를 파악 하 고, 환경에 대 한 계획 된 변경 결과를 확인 하 고, 작동 중단 문제를 추적 하 고, 더 많은 작업을 수행할 수 있습니다. 이 상자는 KHI 리소스의 KHI 임계값을 사용 하 여 구성 되며, 배포의 고유한 요구 사항에 맞게 사용자 지정할 수 있습니다.  <br/> |
|![대시보드 아이콘](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[비즈니스용 Skype 서버 2015 리소스 키트 도구](https://www.microsoft.com/download/details.aspx?id=52631) <br/> |비즈니스용 skype 서버 2015는 IT 관리자가 비즈니스용 Skype 서버 2015를 배포 하 고 관리 하는 데 도움이 되는 몇 가지 일상적인 작업을 지원 하기 위해 제공 됩니다.  <br/> |
|![네트워크 아이콘](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[네트워킹 가이드](https://go.microsoft.com/fwlink/p/?LinkID=390677) <br/> |피어 투 피어 오디오 및 비디오 (A/V) 통화, 회의 및 공동 작업을 가능 하 게 하 고 클라이언트 간의 고품질 미디어 세션을 제공 하는 최적화 된 안정적인 네트워크 인프라에 의존 하는 Microsoft Lync Server 2013 및 비즈니스용 Skype 2015 통신 소프트웨어입니다. 네트워킹 가이드에서는 계획, 모니터링 및 문제 해결의 세 단계로 구성 된 비즈니스용 Skype 및 Lync에 대 한 네트워크 인프라를 관리 하기 위한 모델을 제공 합니다. 이러한 단계는 새로운 Lync 또는 비즈니스용 Skype 서버 배포 또는 기존 배포에 적용할 수 있습니다. 네트워킹 가이드에 대 한 최근 변경 사항에 대 한 내용은 Lync/Skype over Wi-fi 및 서비스 품질 정책 구성에 포함 되어 있습니다.  <br/> |
|![클립보드 아이콘](../media/2e0c9c21-cd2a-4db5-8cb7-d2c0b1b159b7.png)|[비즈니스용 Skype 2015의 중앙 로깅 서비스](centralized-logging-service/centralized-logging-service.md) <br/> |중앙 로깅 서비스는 광범위 하거나 작은 문제에 대 한 강력한 문제 해결 도구로, 근본적인 원인 분석에서 성능 문제에 이르기까지 다양 합니다. 모든 예는 비즈니스용 Skype 서버 관리 셸을 사용 하 여 표시 됩니다. 도움말은 도구 자체를 통해 명령줄 도구에 제공 되지만 명령줄에서 실행할 수 있는 제한 된 함수 집합이 있습니다. 비즈니스용 Skype 서버 관리 셸을 사용 하면 훨씬 더 광범위 하 고 구성 가능한 기능 집합에 액세스할 수 있으므로 항상 첫 번째로 선택 해야 합니다.  <br/> |
|![SCOM 아이콘](../media/3a7601cb-dd2f-4606-8a3b-07c7abdc091a.png)|[SCOM 관리 팩을 사용 하 여 비즈니스용 Skype 서버 2015 관리](use-scom-management-pack/use-scom-management-pack.md) <br/> |비즈니스용 Skype 서버 2015 관리 팩을 사용 하 여 잠재적 문제를 사전에 파악 하 고 해결할 수 있습니다. 이런 식으로 비즈니스용 Skype 서버 2015 관리 팩은 System Center Operations Manager의 기능을 확장 합니다.  <br/> |
|![대시보드 아이콘](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[비즈니스용 Skype 서버 2015 계획 도구](planning-tool/planning-tool.md) <br/> |비즈니스용 Skype 2015 계획 도구는 토폴로지 계획을 시작 하는 데 사용할 수 있는 규범적 지침을 제공 합니다.  <br/> **참고:** 이 도구는 비즈니스용 Skype 서버 2019에 대해서는 업데이트 되지 않습니다. |
|![대시보드 아이콘](../media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[비즈니스용 Skype 서버 2015 용량 계획 계산기](capacity-planning-calculator.md) <br/> |비즈니스용 Skype 서버 2015 용량 계획 계산기는 조직의 요구 사항에 맞는 토폴로지를 모델링 하는 데 도움이 됩니다.  <br/> |
|![네트워크 아이콘](../media/c74d45da-b10f-43c9-aa80-b1935f45c3ee.png)|[비즈니스용 Skype 서버 2015 스트레스 및 성능 도구](stress-and-performance-tool/stress-and-performance-tool.md) <br/> |이 도구를 사용 하면 비즈니스용 Skype 서버 2015 환경에 대해 사용자 부하로 다양 한 성능 관련 테스트를 수행할 수 있습니다. 예제 스크립트는 고유한 환경 요구에 도움을 주는 도구와 함께 제공 됩니다.  <br/>**참고:** 이 도구는 비즈니스용 Skype 서버 2019에 대해서는 업데이트 되지 않습니다. |
   
## <a name="see-also"></a>참고 항목

[Lync Server 2013 도구](https://technet.microsoft.com/library/dn163598%28v=ocs.15%29.aspx)
  
[Lync Server 2010 도구](https://technet.microsoft.com/library/dn145002%28v=ocs.14%29.aspx)
