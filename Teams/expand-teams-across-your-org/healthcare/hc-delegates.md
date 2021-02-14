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
description: 부재 중 상태 또는 방해 금지 상태가 있는 사용자가 상태 메시지에서 다른 사용자를 대리인으로 명시적으로 설정하는 방법을 배워야 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790470"
---
# <a name="message-delegation"></a>메시지 위임

사용자는 이미 자신의 상태를 부재 중 또는 방해 금지로 명시적으로 설정하고 사용자 지정 텍스트를 제공할 수 있습니다. 메시지 위임 기능은 다음과 같이 작동합니다.

1. 사용자가 @username 상태 메시지의 일부로 다른 사용자를 언급하여 연락할 수 없는 사용자를 대신 언급한 사용자에게 @username 제안합니다.
2. 대리인으로 할당된 사용자에게는 대리인으로 지명된 사람이 표시됩니다.
3. 그런 다음 첫 번째 사용자에게 연락하려는 누군가가 지명된 대리인을 마우스로 이동하고 대신 대리인에게 쉽게 메시지를 보낼 수 있습니다.  

이 프로세스는 클라이언트에서 사용자가 시작한 프로세스로, 기능을 사용하도록 설정하는 데 관리자 개입이 필요하지 않습니다. 

## <a name="delegation-use-scenario-in-healthcare"></a>의료에서 위임 사용 시나리오

*대리자를 설정하지 않은 사용 예:*  Dr. Franco Piccio는 방사통과에서 통화 중입니다. 긴급한 개인 전화가 걸려오고 몇 시간 동안 멀어지기만 합니다. He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for he while he' gone. 그는 비공식적으로 이진에게 전달합니다. 이진국씨는 현재의 책임 외에도 긴급한 메시지와 ping을 수신하고 Dr. Piccio를 대신하여 응답합니다. 팀의 다른 사람들은 비공식 위임이 발생했다는 것을 알지 못하고 환자 관리에 혼동을 일 수 있습니다.

*대리자를 설정하는 사용 예:* Dr. Franco Piccio는 방사통과에서 통화 중입니다. 긴급한 개인 전화가 걸려오고 몇 시간 동안 멀어지기만 합니다. He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover he while he' gone. "다음 몇 시간 동안 사용할 수 없습니다. 긴급한 @DrEhrle 문의하시기 바랍니다."  팀의 다른 사람들은 Dr. Piccio에게 연락하려고 할 때 위임이 발생했다는 것을 알고 있으므로, 그동안 이성화에게 연락할 것을 알 수 있습니다. 환자를 진료하는 데 혼동을 거의 발생하지도 말아야 합니다.

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a>Teams 클라이언트의 사용자 상태에 대한 공 존재 모드의 영향

관리자는 상태 메모 및 위임 언급 동작이 사용자의 공 존재 모드에 따라 부분적으로 달라 진다는 것을 알고 있어야 합니다. 이 행렬은 가능성을 보여줍니다.

|Co-Existence 모드 | 예상 동작|
|---|---|
|TeamsOnly |사용자는 Teams에서만 메모를 설정할 수 있습니다. <br> 사용자의 Teams 메모는 Teams 및 SfB에 & 표시됩니다. |
|아일랜드 | Teams에서만 볼 수 있는 Teams의 사용자 노트 집합입니다. <br> SfB에서만 볼 수 있는 SfB의 사용자 메모 집합 |
|SfB* 모드 | 사용자는 SfB에서만 메모를 설정할 수 있습니다. <br> 사용자의 SfB 메모는 Teams의 SfB에 & 있습니다.  |
|||

사용자는 TeamsOnly 또는 Islands 모드인 경우 Teams에서 메모를 설정할 수 있습니다.  

### <a name="displaying-notes-set-in-skype-for-business"></a>비즈니스용 Skype에서 노트 집합 표시
  
비즈니스용 Skype에서 메모가 설정되어 있는 시각적 표시는 없습니다.

비즈니스용 Skype는 상태 노트에 문자 제한을 적용하지 않습니다. Microsoft Teams는 비즈니스용 Skype에서 노트 집합의 처음 280자만 표시합니다. 노트 끝에 있는 타원(...)은 자국을 나타냅니다.
  
비즈니스용 Skype는 노트의 만료 시간을 지원하지 않습니다.

사용자가 TeamsOnly 모드로 업그레이드된 경우 비즈니스용 Skype에서 Teams로 노트 마이그레이션이 지원되지 않습니다.

## <a name="related-topics"></a>관련 항목

[비즈니스용 Skype와 공존](../../coexistence-chat-calls-presence.md)
