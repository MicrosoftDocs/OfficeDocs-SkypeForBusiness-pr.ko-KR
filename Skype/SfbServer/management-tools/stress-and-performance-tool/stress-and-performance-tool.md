---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 프로덕션이 아닌 환경이 나 테스트 환경에서 용량 계획과 성능 조정 중에 사용 됩니다.
ms.openlocfilehash: d82d5ed33e6dca1303aed9f49150dd6b56fc4e1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197021"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구
 
비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 프로덕션이 아닌 환경이 나 테스트 환경에서 용량 계획과 성능 조정 중에 사용 됩니다.
  
비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에는 비즈니스용 Skype Server 2015에 대 한 용량 계획을 간소화 하는 도구가 포함 되어 있습니다. 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 다음을 수행 하는 데 도움이 됩니다.
  
- 비즈니스용 Skype 서버에 대 한 하드웨어 계획 간소화
    
- 향상 된 성능 조정에 대 한 지식 및 모범 사례 제공
    
- 비즈니스용 Skype 서버 배포의 성과 측정
    
일반적으로이 도구는 비즈니스용 [Skype 서버 2015 계획 도구](../../management-tools/planning-tool/planning-tool.md) 를 사용 하 여 토폴로지를 디자인 하 고 [비즈니스용 Skype Server 2015 용량 계획 계산기](../../management-tools/capacity-planning-calculator.md)를 사용 하 여 토폴로지를 구체화 한 후에 사용 합니다. 

> [!NOTE]
> 이 도구는 비즈니스용 Skype 서버 2019 업데이트 되지 않습니다.
  
## <a name="tests"></a>테스트용

스트레스 및 성능 도구를 사용 하 여 이러한 유형의 사용자 부하를 시뮬레이션할 수 있습니다.
  
|||
|:-----|:-----|
|인스턴트 메시지 (IM) 및 현재 상태  <br/> |오디오 회의  <br/> |
|응용 프로그램 공유  <br/> |PTSN (공개 통신 네트워크) 시뮬레이션을 포함 한 VoIP (Voice over IP)  <br/> |
|웹 액세스 클라이언트 회의  <br/> |회의 자동 전화 교환  <br/> |
|응답 그룹  <br/> |메일 그룹 확장  <br/> |
|주소록 다운로드 및 주소록 쿼리  <br/> |향상 된 911 (E911) 통화 및 위치 프로필 (다이얼 플랜)  <br/> |
|MultiView  <br/> |데이터 공동 작업  <br/> |
|간의  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 포함 된 응용 프로그램 및 파일

이러한 응용 프로그램은 비즈니스용 Skype 서버 스트레스 및 성능 도구의 일부입니다.
  
|**도구**|**설명**|
|:-----|:-----|
|UserProvisioningTool  <br/> |이 도구는 사용자 및 연락처를 만드는 데 사용 됩니다.  <br/> |
|UserProfileGenerator  <br/> |시뮬레이트 하는 사용자 부하의 특성을 구성 하는 데 사용 됩니다.  <br/> |
|L Cperftool .exe  <br/> |사용자 부하를 시뮬레이트하는 도구입니다.  <br/> |
|Default. tmx  <br/> |비즈니스용 Skype 서버 2015 로깅 도구를 사용 하는 데 필요 합니다.  <br/> |
|프로비저닝 스크립트 예제  <br/> |특정 시나리오에 따라 부하 테스트 실행에 대 한 토폴로지를 구성 하는 데 사용 됩니다. 특정 환경과 관련 되도록 수정 해야 할 가능성이 큽니다.  <br/> |
   
## <a name="topics-in-this-section"></a>이 섹션의 항목

자세한 정보를 알고 싶은 경우 다음 문서를 검토 하셔야 합니다.
  
- [명함 스트레스 및 성능 도구에 대 한 필수 구성 요소 및 설정](prerequisites-and-setup.md)
    
- [비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 성능 시나리오](scenarios.md)
    
  - [스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로 비전](provisioning-the-topology-to-run-load.md)
    
  - [비즈니스용 Skype Server 2015 스트레스 및 성능 도구에 맞게 정책 구성](configuring-policies.md)
    
- [비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 사용](using-the-tool.md)
    
- [비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 질문과 대답](faq.md)
    

