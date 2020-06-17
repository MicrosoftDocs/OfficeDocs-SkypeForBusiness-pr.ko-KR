---
title: 레거시 풀로 파일럿 풀 동시 사용 확인
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 레거시 풀과의 파일럿 풀 공존 성을 확인 하기 위한 프로세스입니다.
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751660"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>레거시 풀로 파일럿 풀 동시 사용 확인

 **이 문서의 내용**
  
[비즈니스용 Skype 서버 2019 서비스가 시작 되었는지 확인](#sectionSection0)
  
[비즈니스용 Skype 서버 2019 제어판 열기](#sectionSection1)
  
[레거시 토폴로지 작성기에서 토폴로지 열기 시도 안 함](#sectionSection2)
  
파일럿 풀을 배포한 후 관리 도구를 사용하여 풀 정보를 살펴보면서 두 풀이 모두 존재하는지 확인해야 합니다. 비즈니스용 Skype 서버 2019 풀 및 레거시 풀의 경우 비즈니스용 Skype 서버 2019 제어판 및 토폴로지 작성기 도구를 사용 해야 합니다. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>비즈니스용 Skype 서버 2019 서비스가 시작 되었는지 확인
<a name="sectionSection0"> </a>

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 관리 도구 \ 서비스 애플릿으로 이동 합니다.
    
2. 프런트 엔드 서버에서 다음 서비스가 실행되고 있는지 확인합니다.

    - 중앙 로깅 서비스 에이전트
    - 응용 프로그램 공유
    - 오디오 테스트 서비스
    - 오디오/비디오 회의
    - 통화 대기
    - 회의 알림
    - 회의 전화 교환
    - 프런트 엔드
    - IM 회의
    - 중재
    - 복제본 복제기 에이전트
    - 응답 그룹
    - 웹 회의
    - XMPP 변환 게이트웨이

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>비즈니스용 Skype 서버 2019 제어판 열기
<a name="sectionSection1"> </a>

비즈니스용 Skype 서버 2019 배포의 프런트 엔드 서버에서 비즈니스용 Skype 서버 2019 제어판을 열고 레거시 풀을 선택 합니다. 다음 절차를 반복 하 여 비즈니스용 Skype 서버 2019 풀을 엽니다.
  
> [!IMPORTANT]
> 비즈니스용 Skype 서버 2019에서 비즈니스용 Skype 서버 제어판을 사용 하기 전에 Silverlight를 Silverlight 버전 5로 업그레이드 해야 합니다. 
  
이 토폴로지에는 이제 레거시 및 비즈니스용 Skype 서버 2019 서버 역할이 포함 되어 있습니다. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>레거시 토폴로지 작성기에서 토폴로지 열기 시도 안 함
<a name="sectionSection2"> </a>

토폴로지는 비즈니스용 Skype 서버 2019 토폴로지 작성기를 사용해 서만 볼 수 있습니다. 비즈니스용 skype 서버 2019 및 레거시 설치를 위한 풀을 만드는 데에는 lync for Business Server 2019 Topology Builder를 사용 해야 합니다.

  

