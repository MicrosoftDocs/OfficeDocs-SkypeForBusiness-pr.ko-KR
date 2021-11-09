---
title: 사용자 환경의 위치를 수동으로 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: SIP 트렁크 공급자를 사용하여 E9-1-1 배포의 로밍 사용자에 대한 계획은 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: d412c3368dc6f3e302ab8f589aaed1585ea0b233
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855285"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>사용자 환경의 위치를 수동으로 비즈니스용 Skype 서버
 
SIP 트렁크 공급자를 사용하여 E9-1-1 배포의 로밍 사용자에 대한 계획은 비즈니스용 Skype 서버 Enterprise Voice.
  
클라이언트가 네트워크 외부 또는 정의되지 않은 서브넷에 있는 경우 사용자는 위치를 수동으로 입력할 수 있습니다. 그러나 긴급 통화 중에 통화가 PSAP(Public Safety Answering Point)로 라우팅되기 전에 먼저 ECRC(국가/지역 E9-1-1 긴급 통화 응답 센터) 디스패치더로 라우팅됩니다. ECRC는 발신자에 대해 위치를 구두로 쿼리한 다음 제공된 정보에 따라 통화를 적절한 PSAP로 전달합니다. 
  
**위치 정보 서비스에서 자동으로 제공되지 않는 위치를 입력하라는 메시지가 사용자에게 표시되어 있나요?**
  
예를 들어 클라이언트가 정의되지 않은 서브넷, 집, 호텔 또는 네트워크 외부의 다른 위치에 있는 경우 사용자가 위치를 입력해야 합니까?
    
위치 정책에서 **위치** 필요 설정을 구성하여 클라이언트 동작을 정의할 수 있습니다. 이 값을 아니요로 설정하면 사용자에게 위치를 묻는 메시지가 표시되지 않습니다. 이 값을 '예'로 설정하면 사용자에게 위치를 묻는 메시지가 표시되지만 메시지를 지우면 됩니다. 이 값을 고지로 설정하면 사용자에게 위치를 묻는 메시지가 표시될 수 있으며, 메시지를 삭제하려고 하면 고지 메시지가 표시됩니다. 모든 경우에 사용자는 평소와 같이 클라이언트를 계속 사용할 수 있습니다.
    
사용자가 위치를 수동으로 입력하면 위치가 클라이언트 네트워크의 기본 게이트웨이의 MAC 주소에 매핑되고 클라이언트에 있는 사용자 테이블에 저장됩니다. 사용자가 이전에 저장된 위치로 돌아오면 비즈니스용 Skype 자동으로 해당 위치로 설정됩니다. 
  
> [!NOTE]
> 클라이언트의 현재 위치만 수정할 수 있지만 로컬 사용자 테이블에 저장된 모든 위치를 삭제할 수도 있습니다. 
  

