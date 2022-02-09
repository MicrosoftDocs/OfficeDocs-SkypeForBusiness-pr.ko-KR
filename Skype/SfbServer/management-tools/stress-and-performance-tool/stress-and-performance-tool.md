---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: 이 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 비 프로덕션 또는 테스트 환경에서 용량 계획 및 성능 조정 중에 사용됩니다.
ms.openlocfilehash: b8858d4aa9ca0b31bd53489c505181e34af9cf4f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396310"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구
 
이 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 비 프로덕션 또는 테스트 환경에서 용량 계획 및 성능 조정 중에 사용됩니다.
  
비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에는 2015년의 용량 계획을 간소화하는 비즈니스용 Skype 서버 포함되어 있습니다. 2015 비즈니스용 Skype 서버 및 성능 도구를 통해 다음을 할 수 있습니다.
  
- 사용자에 대한 하드웨어 계획 비즈니스용 Skype 서버
    
- 성능 조정을 위한 더 많은 지식과 모범 사례 제공
    
- 배포의 성능 비즈니스용 Skype 서버 측정
    
일반적으로 비즈니스용 Skype 서버 [2015 계획](../../management-tools/planning-tool/planning-tool.md) 도구를 사용하여 토폴로지 디자인 및 비즈니스용 Skype 서버 [2015](../../management-tools/capacity-planning-calculator.md) 용량 계획 계산기를 사용하여 토폴로지 구체화한 후에 이 도구를 사용합니다. 

> [!NOTE]
> 이 도구는 2019년 8월에 비즈니스용 Skype 서버 않습니다.
  
## <a name="tests"></a>테스트

스트레스 및 성능 도구는 다음 유형의 사용자 부하를 시뮬레이트할 수 있습니다.
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|IM(인스턴트 메시징) 및 현재 상태   |오디오 회의   |
|응용 프로그램 공유   |VoIP(Voice over IP), PTSN(Public Switched Telephone Network) 시뮬레이션 포함   |
|웹 액세스 클라이언트 회의   |회의 자동 회의   |
|응답 그룹   |메일 목록 확장   |
|주소부 다운로드 및 주소부 쿼리   |E911(고급 911) 통화 및 위치 프로필(다이얼 플랜)   |
|MultiView   |데이터 공동 작업   |
|이동성   ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 포함된 응용 프로그램 및 파일

이러한 응용 프로그램은 스트레스 및 비즈니스용 Skype 서버 도구의 일부입니다.
  
|도구|설명|
|:-----|:-----|
|UserProvisioningTool.exe   |이 도구는 사용자 및 연락처를 만드는 데 사용됩니다.   |
|UserProfileGenerator.exe   |시뮬레이션할 사용자 부하의 특성을 구성하는 데 사용됩니다.   |
|LyncPerfTool.exe   |사용자 부하를 시뮬레이트하는 도구입니다.   |
|Default.tmx   |2015 로깅 비즈니스용 Skype 서버 사용하는 데 필요합니다.   |
|프로비저닝 스크립트 예제   |특정 시나리오에 따라 부하 테스트를 실행하기 위한 토폴로지 구성에 사용됩니다. 특정 환경과 관련이 있도록 수정해야 할 수 있습니다.   |
   
## <a name="topics-in-this-section"></a>이 섹션의 항목

자세한 내용은 다음 문서를 검토해야 합니다.
  
- [부시 스트레스 및 성능 도구에 대한 Skype 및 설치의 선행 작업](prerequisites-and-setup.md)
    
- [2015 스트레스 비즈니스용 Skype 서버 성능 도구에 대한 성능 시나리오](scenarios.md)
    
  - [스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로비전](provisioning-the-topology-to-run-load.md)
    
  - [2015 스트레스 비즈니스용 Skype 서버 도구에 대한 정책 구성](configuring-policies.md)
    
- [2015 스트레스 비즈니스용 Skype 서버 도구 사용](using-the-tool.md)
    
- [2015 스트레스 비즈니스용 Skype 서버 성능 도구에 대한 FAQ](faq.md)
    

