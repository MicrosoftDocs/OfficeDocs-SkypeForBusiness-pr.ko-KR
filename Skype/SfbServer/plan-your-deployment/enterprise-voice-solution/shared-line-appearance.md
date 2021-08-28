---
title: 2015년 비즈니스용 Skype 서버 줄 모양 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
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
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: 이 항목을 통해 2015년 11월 2015년 11월 누적 업데이트에서 SLA(공유 선 모양)를 계획하는 비즈니스용 Skype 서버 방법을 읽어 읽습니다.
ms.openlocfilehash: b3ec50ff74ee246be892636dac4cdb910a2588d7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614038"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 줄 모양 계획
 
이 항목을 통해 2015년 11월 2015년 11월 누적 업데이트에서 SLA(공유 선 모양)를 계획하는 비즈니스용 Skype 서버 방법을 읽어 읽습니다. 
  
공유 행 모양은 공유 비즈니스용 Skype 번호라는 특정 번호에서 여러 통화를 처리하는 데 사용할 수 있는 기능입니다. SLA는 사용자가 여러 통화에 응답할 수 있도록 비즈니스용 Skype 수 있는 공유 번호로 모든 Enterprise Voice를 구성할 수 있습니다. 통화는 실제로 공유 번호로 수신되지 않고 공유 번호의 대리인 역할을 하는 사용자에게 전달됩니다. 대리인 중 한 명만 통화를 선택할 수 있으며 나머지 대리인은 전화를 수신한 사용자와 그 결과로 통화가 바쁘게 된 줄에 대한 알림을 휴대폰에서 받을 수 있습니다. 줄 수와 대리자는 모두 SLA의 공유 번호에 대해 구성할 수 있습니다. 또한 BusyOption(모든 줄이 통화 중일 때 발생하는 상황)과 MissedCallOption(대리인이 통화를 선택하지 않은 경우)과 같은 고급 옵션도 공유 번호에 대해 구성할 수 있습니다.
  
SLA는 다음 전화 장치에서만 지원됩니다(컴퓨터, 휴대폰 또는 기타 비즈니스용 Skype 클라이언트에서는 지원되지 않습니다. 
  
- 펌웨어 업데이트 5.4.1이 있는 Polycom VVX300
    
- 펌웨어 업데이트 5.4.1이 있는 Polycom VVX400
    
- Polycom VVX500 펌웨어 업데이트 5.4.1
    
- 펌웨어 업데이트 5.4.1이 있는 Polycom VVX600
    
SLA는 2015년 11월 비즈니스용 Skype 서버 업데이트의 새로운 기능입니다. 
  
SLA 배포에 대한 자세한 내용은 [Deploy Shared Line Appearance in 비즈니스용 Skype 서버 2015를 참조하십시오.](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)
  
## <a name="feature-list"></a>기능 목록

SLA 그룹을 설정하면 다음을 할 수 있습니다.
  
- 그룹의 모든 대리인은 동일한 공유 번호로의 인바운드 호출에 응답할 수 있습니다. 통화는 PSTN 기반 또는 SIP 기반 통화일 수 있습니다.
    
- 대리인은 통화를 보류하고 선택할 수 있습니다.
    
- 대리인은 SLA 그룹 외부의 번호로 통화를 전송할 수 있습니다.
    
- 대리인은 현재 공유 번호에 있는 통화 수를 보고 각 통화의 상태를 볼 수 있습니다.
    
- 공유 번호에 대한 최대 동시 통화 수를 구성할 수 있습니다. 이 최대값에 도달한 후 추가 호출을 처리할 방법을 설정할 수도 있습니다. 초과 통화는 통화 중 신호로 거부되거나 대체 번호로 전달되거나 음성 메일로 전달될 수 있습니다.
    
- 부재 중 전화(특정 시간 후에 통화를 선택하지 않은 경우)를 처리할 방법을 구성할 수 있습니다. 그룹 ID에 대해 음성 메일을 사용하도록 설정하면 부재 중 전화가 자동으로 음성 메일로 이동됩니다. 그룹 ID(공유 번호)에 대해 음성 메일을 사용할 수 없는 경우 부재 중 신호로 부재 중 전화가 거부되거나 대체 번호로 전달되거나 연결이 끊어진 것을 선택할 수 있습니다.
    

