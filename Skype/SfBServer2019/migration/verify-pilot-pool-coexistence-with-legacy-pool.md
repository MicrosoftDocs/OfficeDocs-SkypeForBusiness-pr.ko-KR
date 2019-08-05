---
title: 레거시 풀과의 파일럿 풀 공존 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 레거시 풀과의 파일럿 풀 공존을 확인 하는 프로세스입니다.
ms.openlocfilehash: b41a1f24786fdf807f9c9c1d5854e397654fdadb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2019
ms.locfileid: "36197987"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>레거시 풀과의 파일럿 풀 공존 확인

 **이 문서의 내용**
  
[비즈니스용 Skype Server 2019 서비스가 시작 되었는지 확인](#sectionSection0)
  
[비즈니스용 Skype 서버 2019 제어판을 엽니다.](#sectionSection1)
  
[레거시 토폴로지 작성기에서 토폴로지 열기 시도 안 함](#sectionSection2)
  
파일럿 풀을 배포한 후에는 관리 도구를 사용 하 여 풀 정보를 보는 방법으로 두 풀의 공존을 확인 해야 합니다. 비즈니스용 Skype 서버 2019 풀 및 레거시 풀에는 비즈니스용 Skype Server 2019 제어판 및 토폴로지 작성기 도구를 사용 해야 합니다. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>비즈니스용 Skype Server 2019 서비스가 시작 되었는지 확인
<a name="sectionSection0"> </a>

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 관리 toolservices 애플릿으로 이동 합니다.
    
2. 프런트 엔드 서버에서 다음 서비스가 실행 중인지 확인 합니다.

    - 중앙 로깅 서비스 에이전트
    - 응용 프로그램 공유
    - 오디오 테스트 서비스
    - 오디오/비디오 회의
    - 통화 대기
    - 회의 알림
    - 회의 전화 교환
    - 프런트 엔드
    - 메신저 대화 회의
    - 중재
    - 복제 복제기 에이전트
    - 응답 그룹
    - 웹 회의
    - XMPP 번역 게이트웨이

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>비즈니스용 Skype 서버 2019 제어판을 엽니다.
<a name="sectionSection1"> </a>

비즈니스용 Skype Server 2019 배포의 프런트 엔드 서버에서 비즈니스용 Skype Server 2019 제어판을 열고 레거시 풀을 선택 합니다. 이 절차를 반복 하 여 비즈니스용 Skype 서버 2019 풀을 엽니다.
  
> [!IMPORTANT]
> 비즈니스용 Skype Server 2019에서 비즈니스용 Skype 서버 제어판을 사용 하기 전에 silverlight 버전 5로 Silverlight를 업그레이드 해야 합니다. 
  
이 토폴로지에는 이제 레거시 및 비즈니스용 Skype 서버 2019 서버 역할이 포함 됩니다. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>레거시 토폴로지 작성기에서 토폴로지 열기 시도 안 함
<a name="sectionSection2"> </a>

토폴로지는 비즈니스용 Skype 서버 2019 토폴로지 작성기를 사용해 서만 볼 수 있습니다. 비즈니스용 skype server 2019 토폴로지 작성기를 사용 하 여 비즈니스용 Skype Server 2019과 레거시 설치 모두에 대 한 풀을 만들어야 합니다.

  

