---
title: 설정이 변경되면 사용자에게 전송되는 전자 메일
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '전화 접속 회의 설정이 변경될 때 사용자에게 전자 메일로 자동으로 전송되는 정보를 Microsoft Teams. '
ms.openlocfilehash: 590d2b9431950464aab051b73a70a1c30e6a55ad
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004210"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>사용자가 설정이 변경될 때 사용자에게 Microsoft Teams

Microsoft를 오디오 회의 공급자로 [](set-up-audio-conferencing-in-teams.md) 사용하여 오디오 회의를 사용하도록 설정된 사용자에게 전자 메일이 자동으로 전송됩니다.

기본적으로 오디오 회의를 사용하도록 설정된 사용자에게 전송되는 4가지 유형의 전자 메일이 있습니다. 그러나 사용자에게 보낸 전자 메일의 수를 제한하려는 경우 해제할 수 있습니다. 다음이 Microsoft 365 또는 Office 365 오디오 회의가 사용자의 전자 메일로 전송됩니다.

- **오디오 회의 라이선스가 사용자에게 할당되거나 오디오 회의 공급자를 Microsoft로 변경할 때 할당됩니다.**

     이 전자 메일에는 회의 ID, 모임의 기본 전화 번호, 사용자의 오디오 회의 PIN 및 사용자에 대한 기존 모임을 업데이트하는 데 사용되는 비즈니스용 Skype 온라인 모임 업데이트 도구를 사용하는 지침 및 링크가 포함됩니다. 추가 [Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 라이선스 할당 또는 오디오 회의 공급자로 Microsoft 할당을 [참조하세요.](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)

    > [!NOTE]
    > 조직에서 동적 회의 ID를 사용하도록 설정한 경우 예약한 모든 사용자의 모임에는 고유한 회의 ID가 있습니다. 조직에서 오디오 회의 동적 [아이디를 설정할 수 있습니다.](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user) 

    다음은 이 전자 메일의 예입니다.

     ![비즈니스용 Skype 라이선스 확인](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    라이선스에 대한 자세한 내용은 추가 Microsoft Teams [를 참조합니다.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

- **사용자의 회의 ID 또는 기본 전화 회의 전화 번호가 변경됩니다.**

    이 전자 메일에는 사용자에 대한 기존 모임을 업데이트하는 데 사용되는 비즈니스용 Skype 온라인 모임 업데이트 도구를 사용하는 지침 및 링크가 포함되어 있습니다. 그러나 이 전자 메일에는 사용자의 오디오 회의 PIN이 포함되어 없습니다. 사용자의 [회의 ID 재설정을 참조합니다.](reset-a-conference-id-for-a-user-in-teams.md)

    다음은 이 전자 메일의 예입니다.

     ![전화 접속 회의 정보가 변경되었습니다.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **사용자의 오디오 회의 PIN이 재설정됩니다.**

    이 전자 메일에는 이끌이의 오디오 회의 PIN, 기존 회의 ID 및 사용자의 기본 전화 번호가 포함되어 있습니다. 오디오 회의 PIN 재설정을 [참조합니다.](reset-the-audio-conferencing-pin-in-teams.md)
    
     다음은 이 전자 메일의 예입니다.
    
     ![전화 접속 회의 PIN이 변경되었습니다.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **사용자의 라이선스가 제거되거나 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 없음으로 변경되는 경우.**

    오디오 회의  라이선스가 사용자에서 제거되거나 오디오 회의 공급자를 없음으로 설정할 때 **발생합니다.**

    비즈니스용 라이선스 할당 또는 [Microsoft 365 참조](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

    다음은 이 전자 메일의 예입니다.

     ![전화 접속 회의가 꺼져 있습니다.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>전송된 전자 메일 메시지를 변경합니다.

사용자에게 자동으로 전송되는 전자 메일을 변경할 수 있습니다. 기본적으로 전자 메일의 보낸 사람이 Microsoft 365 Office 365 표시 이름을 변경할 수 Windows PowerShell. 자세한 [내용은 Microsoft Teams PowerShell 참조를](/powershell/module/teams/?view=teams-ps) 참조하세요.

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>전자 메일을 보내지 못하게 하려는 경우 어떻게 하나요?

사용자에게 전자 메일 보내기 기능을 사용하지 않도록 설정하면 사용자가 라이선스를 할당한 경우에도 전자 메일이 전송되지 않습니다. 이 경우 회의 ID, 기본 회의 전화 번호 및 더 중요한 것은 해당 오디오 회의 PIN이 사용자에게 전송되지 않습니다. 이 경우 사용자에게 별도의 전자 메일을 보내거나 호출하여 사용자에게 알려야 합니다.

기본적으로 전자 메일은 사용자에게 전송되지만 오디오 회의를 위해 전자 메일을 수신하지 못하게 하려는 경우 전자 메일을 Microsoft Teams 또는 Windows PowerShell. 

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.** 

2. 컨퍼런스 브리지  페이지의 맨 위에 있는 브리지 설정을 **클릭합니다.** 

3. 브리지 **설정 창에서** 전화 접속 설정이 변경될 경우 사용자에게 자동으로 전자 메일 보내기를 사용하도록 설정하거나 **사용하지 않도록 설정합니다.**

4. **저장** 을 클릭합니다.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Windows PowerShell**

PowerShell 모듈을 사용하여 Microsoft Teams 실행할 수 있습니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

[Set-CsOnlineDialInConferencingTenantSettings를](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.

자세한 [내용은 Microsoft Teams PowerShell 참조를](/powershell/module/teams/?view=teams-ps) 참조하세요.

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

기본적으로 전자 메일의 보낸 사람이 Microsoft 365 Office 365 전자 메일 주소 및 표시 이름을 변경할 수 Windows PowerShell. 

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.

  - [PowerShell을 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [데이터를 사용하여 Office 365 관리하는 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.


## <a name="related-topics"></a>관련 항목

[오디오 회의 설정이 변경되면 전자 메일 보내기 사용 또는 사용 안 함](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
