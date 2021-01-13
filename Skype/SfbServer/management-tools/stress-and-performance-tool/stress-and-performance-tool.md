---
title: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 비 프로덕션 또는 테스트 환경에서 용량 계획 및 성능 조정 중에 사용됩니다.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814928"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구
 
비즈니스용 Skype 서버 2015 스트레스 및 성능 도구는 비 프로덕션 또는 테스트 환경에서 용량 계획 및 성능 조정 중에 사용됩니다.
  
비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에는 비즈니스용 Skype 서버 2015의 용량 계획을 간소화하는 도구가 포함되어 있습니다. 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 사용하면 다음을 할 수 있습니다.
  
- 비즈니스용 Skype 서버에 대한 하드웨어 계획 간소화
    
- 성능 조정을 위한 더 많은 지식과 모범 사례 제공
    
- 비즈니스용 Skype 서버 배포의 성능 측정
    
일반적으로 비즈니스용 [Skype 서버 2015](../../management-tools/planning-tool/planning-tool.md) 계획 도구를 사용하여 토폴로지 디자인하고 비즈니스용 Skype 서버 [2015](../../management-tools/capacity-planning-calculator.md)용량 계획 계산기를 사용하여 토폴로지 구체화한 후에 이 도구를 사용합니다. 

> [!NOTE]
> 이 도구는 비즈니스용 Skype 서버 2019에 대해 업데이트되지 않습니다.
  
## <a name="tests"></a>테스트

스트레스 및 성능 도구는 다음 유형의 사용자 부하를 시뮬레이트할 수 있습니다.
  
|||
|:-----|:-----|
|IM(인스턴트 메시징) 및 현재 상태  <br/> |오디오 회의  <br/> |
|응용 프로그램 공유  <br/> |PTSN(Public Switched Telephone Network) 시뮬레이션을 포함한 VoIP(Voice over IP)  <br/> |
|웹 액세스 클라이언트 회의  <br/> |회의 자동 회의  <br/> |
|응답 그룹  <br/> |메일 목록 확장  <br/> |
|주소부 다운로드 및 주소부 쿼리  <br/> |E911(Enhanced 911) 통화 및 위치 프로필(다이얼 플랜)  <br/> |
|MultiView  <br/> |데이터 공동 작업  <br/> |
|이동성  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 포함된 응용 프로그램 및 파일

이러한 응용 프로그램은 비즈니스용 Skype 서버 스트레스 및 성능 도구의 일부입니다.
  
|**도구**|**설명**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |이 도구는 사용자 및 연락처를 만드는 데 사용됩니다.  <br/> |
|UserProfileGenerator.exe  <br/> |시뮬레이션할 사용자 부하의 특성을 구성하는 데 사용됩니다.  <br/> |
|LyncPerfTool.exe  <br/> |사용자 부하를 시뮬레이트하는 도구입니다.  <br/> |
|Default.tmx  <br/> |비즈니스용 Skype 서버 2015 로깅 도구를 사용하는 데 필요합니다.  <br/> |
|프로비저닝 스크립트 예제  <br/> |특정 시나리오에 따라 부하 테스트를 실행하도록 토폴로지 구성에 사용됩니다. 특정 환경과 관련이 있도록 수정해야 할 수 있습니다.  <br/> |
   
## <a name="topics-in-this-section"></a>이 섹션의 항목

자세한 내용은 다음 문서를 검토해야 합니다.
  
- [Skype for Busines 스트레스 및 성능 도구의 선행 작업 및 설정](prerequisites-and-setup.md)
    
- [비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 성능 시나리오](scenarios.md)
    
  - [스트레스 및 성능 시나리오에서 부하를 실행할 토폴로지 프로비전](provisioning-the-topology-to-run-load.md)
    
  - [비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 정책 구성](configuring-policies.md)
    
- [비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 사용](using-the-tool.md)
    
- [비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대한 FAQ](faq.md)
    

