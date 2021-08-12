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
description: 레거시 풀과 파일럿 풀의 동시 사용 여부를 확인하는 프로세스입니다.
ms.openlocfilehash: f9a3fa8a9716d880b8fa2381fd5cafe88509504c2c142ebd5da5c5ab43667cf1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341124"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>레거시 풀로 파일럿 풀 동시 사용 확인

 **이 문서의**
  
[2019 비즈니스용 Skype 서버 시작된지 확인](#sectionSection0)
  
[2019 비즈니스용 Skype 서버 열기](#sectionSection1)
  
[레거시 토폴로지 작성기에서 토폴로지 열지 않습니다.](#sectionSection2)
  
파일럿 풀을 배포한 후 관리 도구를 사용하여 풀 정보를 살펴보면서 두 풀이 모두 존재하는지 확인해야 합니다. 비즈니스용 Skype 서버 2019 풀 및 레거시 풀의 경우 비즈니스용 Skype 서버 2019 제어판 및 토폴로지 작성기 도구를 사용해야 합니다. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>2019 비즈니스용 Skype 서버 시작된지 확인
<a name="sectionSection0"> </a>

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 관리 도구\서비스 애플릿으로 이동합니다.
    
2. 프런트 엔드 서버에서 다음 서비스가 실행되고 있는지 확인합니다.

    - 중앙 로깅 서비스 에이전트
    - 응용 프로그램 공유
    - 오디오 테스트 서비스
    - 오디오/비디오 회의
    - Call Park
    - 회의 알림
    - 회의 도우미
    - 프런트 엔드
    - IM 회의
    - 중재
    - 복제본 복제기 에이전트
    - 응답 그룹
    - 웹 회의
    - XMPP Translating Gateway

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>2019 비즈니스용 Skype 서버 열기
<a name="sectionSection1"> </a>

비즈니스용 Skype 서버 2019 배포의 프런트 엔드 서버에서 비즈니스용 Skype 서버 2019 제어판을 열고 레거시 풀을 선택합니다. 절차에 따라 2019 풀을 비즈니스용 Skype 서버 합니다.
  
> [!IMPORTANT]
> 비즈니스용 Skype 서버 2019에서 비즈니스용 Skype 서버 제어판을 사용하려면 먼저 Silverlight를 Silverlight 버전 5로 업그레이드해야 합니다. 
  
이 토폴로지에는 이제 레거시 및 비즈니스용 Skype 서버 2019 서버 역할이 포함됩니다. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>레거시 토폴로지 작성기에서 토폴로지 열지 않습니다.
<a name="sectionSection2"> </a>

토폴로지는 2019년 2019년 토폴로지 작성기에서만 비즈니스용 Skype 서버 수 있습니다. 비즈니스용 Skype 서버 2019 토폴로지 작성기 를 사용하여 2019 및 비즈니스용 Skype 서버 모두에 대한 풀을 만들어야 합니다.

  

