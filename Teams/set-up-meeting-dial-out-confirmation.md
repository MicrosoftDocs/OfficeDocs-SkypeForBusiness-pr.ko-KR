---
title: Microsoft Teams에서 사용자에 대한 모임 전화 걸기 확인 설정
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 전화에 응답할 수 없는 경우 음성 메일 시스템이 모임에 연결되지 않도록 전화 걸기 확인을 요청하기 위해 Teams를 설정하는 방법을 배워야 합니다.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37d68eb90e42b57ff76d352ea2c856e6904a9308
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806148"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Microsoft Teams에서 사용자에 대한 모임 전화 걸기 확인 설정

모임 전화 걸기 및 전화 통화는 모임에 참가할 참가자를 초대하고 기존 참가자가 기존 또는 휴대폰을 사용하여 모임에 참가할 수 있는 매우 유용한 방법입니다. 그러나 발신자가 통화에 응답할 수 없는 경우 음성 통화 시스템에서 전화를 걸면 음성 시스템이 모임에 연결되고 참가자는 모임에서 제거될 때까지 이를 들을 수 있습니다.

모임 전화 번호로 모임 전화가 걸리며 통화에 응답할 수 없는 경우 음성 메일 시스템이 모임에 연결되지 않도록 Teams를 설정하여 해당 사용자가 모임에 참가할 수 있는 확인을 요청할 수 있습니다. 호출된 사람이 통화에 응답할 수 없는 경우 음성 메일 시스템이 모임에 연결되지 않습니다. 참가 확인을 제공하지 못하기 때문에 음성 메일 시스템이 모임에 연결되지 않습니다.

이 기능을 사용하도록 설정하면 전화 걸기 또는 전화 통화를 받는 사람들이 기존 또는 휴대폰에서 1을 눌러 모임에 참가할지 확인해야 합니다.

조직의 모든 모임에 이 기능을 사용하도록 설정하려면 ```EnableDialOutJoinConfirmation``` [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet의 매개 변수를 ```true``` 으로 설정합니다. 이를 위해 다음 명령을 실행합니다.

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>관련 항목

- [사용자의 전화 받기 기능 설정](set-up-the-call-me-feature-for-your-users.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)