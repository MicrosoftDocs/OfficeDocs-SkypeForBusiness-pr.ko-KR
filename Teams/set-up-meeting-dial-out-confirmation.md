---
title: Microsoft Teams에서 사용자에 대한 모임 전화 접속 확인 설정
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 호출된 사람이 통화에 응답할 수 없는 경우 음성 메일 시스템이 모임에 연결되지 않도록 전화 접속 확인을 요청하도록 Teams를 설정하는 방법을 알아봅니다.
ms.localizationpriority: medium
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: a74a02b8d6c0a11202676144ce2dba91618118c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271563"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Microsoft Teams에서 사용자에 대한 모임 전화 접속 확인 설정

모임 전화 걸기 및 통화는 참가자를 모임에 초대하고 기존 참가자가 기존 또는 휴대폰을 사용하여 모임에 참가하도록 초대하는 유용한 방법입니다. 그러나 호출된 사람이 통화에 응답할 수 없고 음성 메일 시스템에서 전화를 받으면 음성 메일 시스템이 모임에 연결됩니다. 참가자는 모임에서 제거될 때까지 이를 들을 수 있습니다.

전화 번호로 모임 전화 접속이 전송되고 호출된 사람이 통화에 응답할 수 없는 경우 음성 메일 시스템이 모임에 연결되지 않도록 하기 위해 Teams를 설정하여 전화를 받은 사람이 모임에 참가할 수 있도록 확인을 요청할 수 있습니다. 호출된 사람이 통화에 응답할 수 없고 음성 메일 시스템에서 통화에 응답하는 경우 음성 메일 시스템은 모임에 참가할 수 있는 확인을 제공하지 않으므로 모임에 연결되지 않습니다.

이 기능을 사용하도록 설정하면 전화 걸기 또는 전화 통화를 받는 사용자는 기존 또는 휴대폰에서 1을 누르거나 "좋아요"라고 말하여 모임에 참가할 것인지 확인해야 합니다. 확인은 사용자의 음성 메일 메시지가 모임에 참가하지 못하게 합니다.

조직의 모든 모임에 대해 이 기능을 사용하도록 설정하려면 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet```true```의 매개 변수를 로 설정합니다```EnableDialOutJoinConfirmation```. 이 매개 변수를 설정하려면 다음 명령을 실행합니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>관련 항목

- [사용자의 전화 받기 기능 설정](set-up-the-call-me-feature-for-your-users.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)
