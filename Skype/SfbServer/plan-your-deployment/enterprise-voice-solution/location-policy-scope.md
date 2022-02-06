---
title: 2016에서 위치 정책 범위 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: E9-1-1 배포에 대한 위치 비즈니스용 Skype 서버 Enterprise Voice.
---

# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>2016에서 위치 정책 범위 비즈니스용 Skype 서버
 
E9-1-1 배포에 대한 위치 비즈니스용 Skype 서버 Enterprise Voice.
  
다른 비즈니스용 Skype 서버 정책과 함께 위치 정책을 전역, 사이트 및 사용자와 같은 여러 범위 수준에서 할당할 수 있습니다. 그러나 사용자 수준 위치 정책의 범위는 다른 사용자 수준 정책과 약간 비즈니스용 Skype 서버 다릅니다. 사용자 및 공통 영역 정책과 같은 끝점 개체(예: 사용자 및 공통 영역 전화)에도 사용자당 위치 정책을 적용할 수 있을 비즈니스용 Skype 서버 있습니다. 네트워크 사이트는 지리적 위치와 연결된 클라이언트 서브넷의 그룹이지만 전체 중앙 사이트 또는 분기 사이트의 일부 서브넷일 필요는 없습니다. 네트워크 사이트의 서브넷에 연결된 모든 클라이언트는 해당 네트워크 사이트에 할당된 위치 정책을 자동으로 선택합니다. 사용자 수준 위치 정책이 사용자 및 네트워크 사이트에 모두 할당된 경우 네트워크 사이트 기반 위치 정책은 사용자 기준 정책 설정을 모두 에버합니다.
  
각 네트워크 사이트에는 위치 정책이 할당되어 있으며 각 정책에는 서로 다른 PSTN 사용, 알림 URI 및 회의 URI 값이 할당됩니다.
  
> [!NOTE]
> 이러한 특수한 정책의 지정 동작은 한 사무실 사이트의 풀에 있는 사용자가 다른 사이트를 방문하여 긴급 통화를 하도록 하는 경우 사용자가 할당된 풀 또는 사이트에 상관없이 해당 네트워크 사이트에 적합한 E9-1-1 통화 라우팅 설정이 적용될 수 있도록 합니다. 
  

