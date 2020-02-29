---
title: Microsoft 팀에서 모임 전화 걸기 설정-사용자에 대 한 확인
author: LanaChin
ms.author: v-lanac
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 음성 메일 시스템이 전화를 받을 수 없는 경우에도 모임에 연결 되지 않도록 전화 걸기 확인을 요청 하는 팀을 설정 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a7d36d499ff7466fc1e0441bfd37bd7e6f863ae
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339480"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Microsoft 팀에서 사용자에 대 한 모임 전화 걸기 확인 설정

모임 다이얼 아웃 및 통화 전화 통화는 참가자를 모임 참가에 초대 하 고 기존 참가자가 일반 전화기 나 휴대폰을 사용 하 여 모임에 참가 하도록 하는 매우 유용한 방법입니다. 그러나 통화 한 사람이 전화를 받을 수 없고, 음성 메일 시스템에서 통화에 전화를 거는 경우, 음성 메일 시스템은 모임에 연결 되며 참가자가 모임에서 제거 될 때까지이를 수신할 수 있습니다.

모임에 전화를 걸 수 없을 때 음성 메일 시스템이 모임에 연결 되지 않도록 하려면 전화를 건 사람에 게 통화에 대 한 응답을 요청 하도록 팀을 설정할 수 있습니다. 상대방이 전화를 받을 수 없고, 음성 메일 시스템에서 통화에 응답 하는 경우, 음성 메일 시스템은 참가 확인을 제공 하지 않으므로 모임에 연결 되지 않습니다.

이 접근 권한 값을 사용 하는 경우 전화 걸기 또는 전화를 거는 전화를 받는 사용자는 일반 전화기 나 휴대폰에서 1을 눌러 모임에 참가 하 고 있는지 확인 해야 합니다.

조직의 모든 모임에 대해이 기능을 사용 하도록 설정 하려면 ```EnableDialOutJoinConfirmation``` [사용](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet의 매개 변수를으로 ```true```설정 합니다. 이렇게 하려면 다음 명령을 실행 합니다.

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>관련 주제

- [사용자의 전화 받기 기능 설정](set-up-the-call-me-feature-for-your-users.md)
- [팀 PowerShell 개요](teams-powershell-overview.md)