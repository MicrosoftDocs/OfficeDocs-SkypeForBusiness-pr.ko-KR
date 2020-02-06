---
title: 비즈니스용 Skype 서버 2015의 공유 라인 모양에 대 한 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: 이 항목을 읽으면 비즈니스용 Skype Server 2015, 2015 누적 업데이트에 대 한 SLA (공유 라인 표시)를 계획 하는 방법을 알아보세요.
ms.openlocfilehash: 14f0f6cbd163ecff42543d3ad57bed0020434cfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802438"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 공유 라인 모양에 대 한 계획
 
이 항목을 읽으면 비즈니스용 Skype Server 2015, 2015 누적 업데이트에 대 한 SLA (공유 라인 표시)를 계획 하는 방법을 알아보세요. 
  
공유 선 모양은 공유 번호 라는 특정 번호에서 여러 통화를 처리 하기 위해 비즈니스용 Skype의 기능입니다. SLA는 비즈니스용 Skype 사용자에 게 여러 회선을 사용 하 여 여러 통화에 응답할 수 있는 공유 번호로 구성 합니다. 전화는 실제로 공유 번호로 수신 되지 않고 공유 번호의 대리인 역할을 하는 사용자에 게 전달 됩니다. 대리인 중 한 명의 대리인은 통화를 선택한 사람에 대 한 알림 메시지를 받을 수 있으며, 그 결과로 약속이 있는 줄이 있는지에 대 한 알림이 전화에 제공 됩니다. 줄 수와 대리인은 모두 SLA에서 공유 되는 번호로 구성할 수 있습니다. 또한 BusyOption (모든 회선이 사용 중일 때 발생 하는 상황) 및 MissedCallOption (대리인의 모든 항목이 없는 경우)과 같은 고급 옵션이 공유 번호에 대해 구성할 수도 있습니다.
  
SLA는 다음 전화 장치 에서만 지원 됩니다 (컴퓨터, 휴대 전화 또는 기타 장치에서는 비즈니스용 Skype 클라이언트는 지원 되지 않음). 
  
- Polycom VVX300 펌웨어 업데이트 5.4.1
    
- Polycom VVX400 펌웨어 업데이트 5.4.1
    
- Polycom VVX500 펌웨어 업데이트 5.4.1
    
- Polycom VVX600 펌웨어 업데이트 5.4.1
    
SLA는 비즈니스용 Skype 서버의 새로운 기능으로, 11 월 2015 누적 업데이트입니다. 
  
SLA 배포에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 공유 라인 모양 배포](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)를 참조 하세요.
  
## <a name="feature-list"></a>기능 목록

SLA 그룹을 설정 하면 다음과 같은 기능을 사용할 수 있습니다.
  
- 그룹의 모든 대리인은 같은 공유 번호로 들어오는 전화를 받을 수 있습니다. 통화는 PSTN 기반 이거나 SIP 기반 일 수 있습니다.
    
- 대리인은 통화를 보류 하 고 선택할 수 있습니다.
    
- 대리인은 전화를 SLA 그룹 밖의 번호로 양도할 수 있습니다.
    
- 대리인은 현재 공유 번호에 있는 통화 수를 확인 하 고 각 통화의 상태를 볼 수 있습니다.
    
- 공유 번호에 대 한 최대 동시 통화 수를 구성할 수 있습니다. 이 최대값에 도달한 후 추가 통화를 처리 하는 방법을 설정할 수도 있습니다. 불필요 한 통화는 통화 중 신호를 통해 거부 하거나, 대체 번호로 착신 전환 하거나, 음성 메일로 착신 전환할 수 있습니다.
    
- 부재 중 통화 (특정 시간 이후에 선택 되지 않은 통화)를 처리 하는 방법을 구성할 수 있습니다. 그룹 id에 대해 음성 메일을 사용 하도록 설정 하면 부재 중 통화가 자동으로 음성 메일로 이동 합니다. 그룹 id (공유 번호)에 대해 음성 메일을 사용할 수 없는 경우 부재 중 통화를 거부 하거나 다른 번호로 착신 전환 하거나 연결을 끊지 선택할 수 있습니다.
    

