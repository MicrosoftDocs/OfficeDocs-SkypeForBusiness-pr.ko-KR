---
title: 사용자에 대한 모임 전화 접속 확인 설정 Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 전화 통화에 응답할 수 Teams 음성 메일 시스템이 모임에 연결되지 않도록 전화 접속 확인을 요청하는 방법을 알아보습니다.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f72641742101a84c572335f2416599fccb6c809bdece75eb75c4db6ff95067c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54299078"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>사용자에 대한 모임 전화 접속 확인을 Microsoft Teams

모임 전화 걸기 및 전화 통화는 참가자를 모임에 참가할 수 있는 초대하고 기존 참가자가 기존 또는 휴대폰을 사용하여 모임에 참가할 수 있는 매우 유용한 방법입니다. 그러나 호출된 사용자가 통화에 응답할 수 없는 경우 음성메일 시스템이 모임에 연결되고 참가자는 모임에서 제거될 때까지 수신 수신을 수신할 수 있습니다.

전화 번호로 모임 전화 걸기를 보내고 호출한 사람이 통화에 응답할 수 없는 경우 음성 메일 시스템이 모임에 연결되지 않도록 Teams 모임에 참가할 수 있는 호출된 사람의 확인을 요청할 수 있습니다. 호출된 사용자가 통화에 응답할 수 없는 경우 음성 메일 시스템에서 전화를 걸면 음성 메일 시스템이 모임에 연결되지 않습니다.

이 기능을 사용하도록 설정하면 전화 걸기 또는 전화 통화를 받는 사용자가 기존 또는 휴대폰에서 1을 눌러 모임에 참가할지 확인해야 합니다.

조직의 모든 모임에 대해 이 기능을 사용하도록 설정하려면 ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet의 매개 변수를 ```true``` 으로 설정합니다. 이렇게 하여 다음 명령을 실행합니다.

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>관련 항목

- [사용자의 전화 받기 기능 설정](set-up-the-call-me-feature-for-your-users.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)