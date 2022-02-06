---
title: (선택 사항) 통화 파크 배포를 비즈니스용 Skype
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 통화 파킹된 통화 파킹의 배포를 비즈니스용 Skype 서버 Enterprise Voice.
---

# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(선택 사항) 통화 파크 배포를 비즈니스용 Skype
 
통화 파킹된 통화 파킹의 배포를 비즈니스용 Skype 서버 Enterprise Voice. 
  
통화 파킹을 설치 및 구성한 후 구성을 확인하여 통화를 파킹하고 검색하는 것이 예상대로 작동하는지 확인해야 합니다. 최소한 다음 사항을 확인하십시오.
  
- 통화 파크를 사용하도록 설정한 사용자에게 전화를 걸고 사용자가 통화를 파크하도록 합니다.
    
    > [!NOTE]
    > 이 테스트를 수행하기 직전에 음성 정책에서 통화 파킹을 사용하도록 설정한 경우 통화를 파킹한 사용자는 통화를 전송 목록에서 비즈니스용 Skype 로그인한 후 다시 로그인해야 전송 통화 목록에서 통화 파킹 옵션을 볼 수 있습니다. 
  
- 파킹된 통화 번호로 전화를 걸어 통화를 재개합니다.
    
- 다른 통화를 대기 상태로 설정하고 대기된 통화의 제한 시간을 초과시키며 되걸려오는 전화를 받지 않습니다. 제한 시간이 초과된 통화가 **OnTimeoutURI** 에 지정한 대체 대상으로 제대로 라우팅되는지 확인합니다.
    

