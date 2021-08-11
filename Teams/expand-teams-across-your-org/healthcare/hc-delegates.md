---
title: 메시지 위임
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: 자리 비움 상태 또는 방해 금지 상태의 사용자가 상태 메시지에 명시적으로 다른 사용자를 대리인으로 설정하는 방법을 알아봅니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 967ed83f89d991ad001dbac9001d4d20b412efec80f0edb5bf4caca77e487a87
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276533"
---
# <a name="message-delegation"></a>메시지 위임

사용자는 이미 명시적으로 자리 비움 또는 방해 금지로 상태를 설정한 다음 사용자 지정 텍스트를 입력할 수 있습니다. 메시지 위임 기능은 다음과 같이 작동합니다.

1. @username의 사용자가 텍스트 상태 메시지의 일부분에서 다른 사용자를 언급하며 본인이 없는 동안 본인에게 연락하려는 사람들은 대신 @username이 언급한 사용자에게 연락하라고 합니다.
2. 대리인으로 할당된 사람은 본인이 대리인으로 지명되었다는 통지를 받습니다.
3. 그러면 첫 번째 사용자에게 연락하려는 누군가가 지명된 대리인에게로 마우스를 이동하여 대신 대리인에게 쉽게 메시지를 보낼 수 있습니다.  

해당 기능은 클라이언트에서 사용자가 시작하는 프로세스이므로 이 기능을 사용하도록 설정하기 위해 관리자의 개입이 필요하지 않습니다. 

## <a name="delegation-use-scenario-in-healthcare"></a>의료 분야에서 위임 사용 시나리오

*위임을 설정하지 않은 사용 예:*  Dr. Franco Piccio는 방사선과 긴급 대기 중입니다. 긴급한 개인 전화를 받고 이후 두 시간가량 자리를 비워야 합니다. 박사는 방사선과의 동료 중 한 명인 Dr. Lena Ehrle에게 본인이 부재 중일 때 업무를 대신해달라고 요청합니다. 그는 비공식적으로 본인의 무선 호출기를 Dr. Ehrle에게 넘기고 Dr. Ehrle은 현재 책임에 추가로 Dr. Piccio를 대신하여 호출기의 긴급 메시지와 호출을 수신하고 이에 응답합니다. 다른 팀원들은 비공식 위임이 있었음을 알지 못하고 환자를 돌보는 데 혼동이 일어납니다.

*위임을 설정한 사용 예:* Dr. Franco Piccio는 방사선과 긴급 대기 중입니다. 긴급한 개인 전화를 받고 이후 두 시간가량 자리를 비워야 합니다. 박사는 방사선과의 동료 중 한 명인 Dr. Lena Ehrle에게 본인이 부재 중일 때 업무를 대신해달라고 요청합니다. 박사는 "다음 몇 시간 동안 자리를 비우니 긴급 상황 시 @DrEhrle에게 연락하세요"와 유사한 표현으로 본인의 사용자 지정 상태 메시지를 변경합니다.  다른 팀원들이 Dr. Piccio에게 연락하려 할 때 위임이 발생했음을 알고 그동안 Dr. Ehrle에게 연락해야 한다는 것을 알 수 있습니다. 환자를 돌보는 데 있어 혼동이 전혀 또는 거의 없습니다.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>공존 모드가 Teams 클라이언트의 사용자 상태에 미치는 영향

관리자는 상태 메모 및 위임 언급 동작이 부분적으로 사용자의 공존 모드에 의존하게 됨을 알아야 합니다. 이 행렬형은 다음과 같은 가능성을 보여줍니다.

|공존 모드 | 예상 동작|
|---|---|
|TeamsOnly |사용자는 Teams에서만 메모를 설정할 수 있습니다. <br> 사용자의 Teams 메모는 Teams 및 SfB에 표시됩니다. |
|Islands | Teams에서 설정한 사용자 메모는 Teams에만 표시됩니다. <br> SfB에서 설정한 사용자 메모는 SfB에만 표시됩니다. |
|SfB* 모드 | 사용자는 SfB에서만 메모를 설정할 수 있습니다. <br> 사용자의 SfB 메모는 SfB 및 Teams에 표시됩니다.  |
|||

사용자는 모드가 TeamsOnly 또는 Islands인 경우 Teams에서만 메모를 설정할 수 있습니다.  

### <a name="displaying-notes-set-in-skype-for-business"></a>비즈니스용 Skype에서 설정한 메모 표시
  
비즈니스용 Skype에서 설정된 메모라는 시각적 표시가 없습니다.

비즈니스용 Skype에는 상태 메모의 문자 제한이 없습니다. Microsoft Teams는 비즈니스용 Skype에서 설정된 메모의 처음 280자만 표시합니다. 메모 끝에 있는 생략 부호(...)는 메모가 잘렸음을 나타냅니다.
  
비즈니스용 Skype는 메모 만료 시간을 지원하지 않습니다.

사용자가 TeamsOnly 모드로 업그레이드된 경우 비즈니스용 Skype에서 Teams로 메모 마이그레이션이 지원되지 않습니다.

## <a name="related-topics"></a>관련 주제

[비즈니스용 Skype와 공존](../../coexistence-chat-calls-presence.md)
