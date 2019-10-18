---
title: 메시지 위임
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: 사용자는 상태 메시지의 대리인으로 다른 사용자를 명시적으로 설정할 수 있습니다.
ms.openlocfilehash: 56c0e9bd5394e738170130bab15803e5cb4d741c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570361"
---
# <a name="message-delegation"></a>메시지 위임

사용자는 이미 상태를 자리 비움 또는 방해 금지로 명시적으로 설정 하 고 사용자 지정 텍스트를 제공할 수 있습니다. 메시지 위임 기능은 다음과 같이 작동 합니다.

1. 사용자 @username 텍스트 상태 메시지의 일부에서 다른 사용자에 게 멘 션을 사용할 수 없는 동안 대화 상대에 게 연락 하려는 사용자가 대신 해당 사용자에 @username 게 연락 하는 것을 제안 합니다.
2. 대리인으로 지정 된 사용자에 게 대리인 이라는 메시지가 표시 됩니다.
3. 첫 번째 사용자에 게 연락 하려고 하는 누군가가 지정한 대리인 위에 마우스를 놓고 대리인에 게 쉽게 메시지를 전송 하도록 할 수 있습니다.  

이것은 클라이언트에서 사용자가 시작한 프로세스 이며,이 기능을 사용 하도록 설정 하는 데 관리자가 관여 하지 않아도 됩니다. 

## <a name="delegation-use-scenario-in-healthcare"></a>의료의 위임 사용 시나리오

*대리인 설정 없이 사용 예제:*  Franco  Cio는 radiology 부서에서 통화 중입니다. 긴급 한 개인 통화를 수신 하 고 다음 몇 시간 동안 작업을 한 번에 한 곳으로 이동 해야 합니다. Radiology 부서별, Dr. Lena Ehrle에서 자신의 피어 중 하나를 요청 하 여, 그 사람을 죽 였을 때 그에 대해 다루겠습니다. 그는 자신의 호출기를 Dr. Hrle에 게 전달 하며,이는 호출기에서 긴급 한 메시지 및 ping을 수신 대기 하 고 현재 책임 외에도 Dr. 를 대신 하 여 해당 사용자에 게 응답 합니다. 팀의 다른 멤버가 비공식적인 위임이 발생 하는 것을 모르고, 환자를 ensues 혼동을 겪을 수 있습니다.

*대리인 설정의 사용 예:* Franco  Cio는 radiology 부서에서 통화 중입니다. 긴급 한 개인 통화를 수신 하 고 다음 몇 시간 동안 작업을 한 번에 한 곳으로 이동 해야 합니다. 그는 radiology 부서별, Dr. Lena Ehrle에 속한 동료 중 한 명에 게 그 사람을 이야기 하는 것을 요청 합니다. "다음 몇 시간 동안 사용할 수 없습니다."와 유사한 사용자 지정 상태 메시지를 변경 합니다. 모든 비상시에 게 연락 @DrEhrle 주십시오. "  팀의 다른 사용자는 이제 Dr. t e t t e t t e t t e t t e t t e t t e t t e t t e t e. 환자에 대 한 주의를 ensues 혼란 스 러 울 수는 거의 없습니다.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>팀 클라이언트의 사용자 상태에 대 한 공존 모드의 영향

관리자는 상태 메모와 위임 멘 션 동작은 부분적으로 사용자의 공동 존재 모드에 따라 달라 지는 것을 인식 해야 합니다. 이 행렬은 다음의 가능성을 보여줍니다.

|동시 존재 모드 | 예상 되는 동작|
|---|---|
|TeamsOnly |사용자는 팀에서 메모를 설정할 수 있습니다. <br> 팀 & SfB에서 사용자의 팀 메모를 볼 수 있습니다. |
|분리 | 팀에서 설정한 사용자의 메모는 팀 에서만 표시 됩니다. <br> SfB에서 설정한 사용자의 메모는 SfB에만 표시 됩니다. |
|SfB * 모드 | 사용자는 SfB에서 메모를 설정할 수 있습니다. <br> 사용자의 SfB 메모는 SfB & 팀에서 볼 수 있습니다.  |
|||

사용자는 해당 모드가 팀 전용 또는 아일랜드 인 경우에만 팀에서 메모를 설정할 수 있습니다.  

### <a name="displaying-notes-set-in-skype-for-business"></a>비즈니스용 Skype에서 설정한 노트 표시
  
비즈니스용 Skype에서 메모가 설정 되었음을 시각적으로 알 수는 없습니다.

비즈니스용 Skype는 상태 메모에 대해 문자 제한을 적용 하지 않습니다. Microsoft 팀은 비즈니스용 Skype에서 설정한 첫 번째 280 자만 표시 합니다. 메모 끝에 있는 타원 (...)이 잘린 것으로 표시 됩니다.
  
비즈니스용 Skype는 노트의 만료 시간을 지원 하지 않습니다.

사용자가 TeamsOnly 모드로 업그레이드 된 경우 비즈니스용 Skype에서 팀으로 노트 마이그레이션이 지원 되지 않습니다.

## <a name="related-topics"></a>관련 항목

[비즈니스용 Skype와 공존](../../coexistence-chat-calls-presence.md)
