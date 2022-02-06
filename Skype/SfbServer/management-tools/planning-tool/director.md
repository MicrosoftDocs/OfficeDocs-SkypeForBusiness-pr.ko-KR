---
title: Director 계획 도구
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
  - ms.lync.plan.Director
  - ms.lync.plan.Director
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Director는 사용자 요청을 비즈니스용 Skype 서버 수 있지만 사용자 계정을 홈으로 두지 않는 2015 통신 소프트웨어를 실행하는 서버입니다.
---

# <a name="director-planning-tool"></a>Director 계획 도구
 
Director는 사용자 요청을 인증할 수 있지만 사용자 비즈니스용 Skype 서버 없는 2015 통신 소프트웨어를 실행하는 서버입니다. 
  
이 역할은 선택 사항이며 다음 두 시나리오에서 Director를 배포할 수 있습니다.
  
- 에지 서버를 배포하여 게스트 사용자가 액세스를 사용하도록 설정하는 경우 Director도 배포해야 합니다. 이 시나리오에서 감독은 게스트를 인증한 다음 트래픽을 내부 서버로 전달합니다. 게스트를 인증하는 데 Director를 사용할 경우 이러한 사용자를 인증하는 오버헤드로 프런트 엔드 풀 서버가 완화됩니다. 또한 서비스 거부 공격과 같은 악의적인 트래픽으로부터 내부 프런트 엔드 풀을 보호하는 데도 도움이 됩니다. 네트워크가 이러한 공격에서 잘못된 외부 트래픽으로 넘쳐나면 이 트래픽은 감독에서 종료됩니다.
    
- 중앙 사이트에 여러 프런트 엔드 풀을 배포하는 경우 해당 사이트에 Director를 추가하면 인증 요청을 간소화하고 성능을 향상시킬 수 있습니다. 이 시나리오에서는 모든 요청이 먼저 Director로 이동한 다음 올바른 프런트 엔드 풀로 라우팅합니다.
    

