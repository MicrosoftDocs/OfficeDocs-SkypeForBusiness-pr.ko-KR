---
title: 설정이 변경되면 사용자에게 전송되는 전자 메일
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Microsoft Teams에서 전화 접속 회의 설정이 변경되면 전자 메일로 사용자에게 자동으로 전송되는 정보에 대해 알아봅니다. '
ms.openlocfilehash: b2ebb07562300a02058f3bfeaad103347299ba0c
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642139"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Microsoft Teams에서 설정이 변경되면 사용자에게 보낸 전자 메일

Microsoft를 오디오 회의 공급자로 사용하여 [오디오 회의를 사용하도록 설정된](set-up-audio-conferencing-in-teams.md) 사용자에게 전자 메일이 자동으로 전송됩니다.

기본적으로 오디오 회의를 사용하도록 설정된 사용자에게 전송되는 네 가지 유형의 전자 메일이 있습니다. 그러나 사용자에게 보낸 전자 메일 수를 제한하려는 경우 해제할 수 있습니다. Microsoft 365 또는 Office 365 오디오 회의는 다음과 같은 경우 사용자의 전자 메일로 전자 메일을 보냅니다.

- **오디오 회의 라이선스가 할당되거나 오디오 회의 공급자를 Microsoft로 변경할 때 할당됩니다.**

     이 전자 메일에는 회의 ID, 모임의 기본 전화 번호, 사용자의 오디오 회의 PIN, 사용자의 기존 모임을 업데이트하는 데 사용되는 Teams 모임 업데이트 도구를 사용하는 지침 및 링크가 포함됩니다. [Microsoft Teams 추가 기능 라이선스 할당을 참조하세요](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > 조직에서 동적 회의 ID를 사용하도록 설정한 경우 예약하는 모든 사용자의 모임에는 고유한 회의 ID가 있습니다. 자세한 내용은 [Microsoft Teams 문서에서 사용자에게 할당된 회의 ID 보기를 확인하고 다시 설정합니다](see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams.md) .

    이 전자 메일의 예는 다음과 같습니다.

     ![Teams 라이선스를 확인합니다.](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    라이선스에 대한 자세한 내용은 [Microsoft Teams 추가 기능 라이선스를](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 참조하세요.

- **사용자의 전화 회의 ID 또는 기본 전화 회의 전화 번호가 변경됩니다.**

    이 전자 메일에는 회의 ID, 기본 전화 회의 전화 번호, 사용자의 기존 모임을 업데이트하는 데 사용되는 Teams 모임 업데이트 도구를 사용하는 지침 및 링크가 포함되어 있습니다. 그러나 이 전자 메일에는 사용자의 오디오 회의 PIN이 포함되지 않습니다. [사용자의 전화 회의 ID 재설정을 참조하세요](reset-a-conference-id-for-a-user-in-teams.md).

    이 전자 메일의 예는 다음과 같습니다.

     ![전화 접속 회의 정보가 변경되었습니다.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **사용자의 오디오 회의 PIN이 다시 설정됩니다.**

    이 전자 메일에는 이끌이의 오디오 회의 PIN, 기존 회의 ID 및 사용자의 기본 전화 회의 전화 번호가 포함되어 있습니다. [오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin-in-teams.md) 참조하세요.

     이 전자 메일의 예는 다음과 같습니다.

     ![전화 접속 회의 PIN이 변경되었습니다.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **사용자의 라이선스가 제거되거나 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 없음으로 변경될 때**

    이는 사용자로부터 **오디오 회의** 라이선스가 제거되거나 오디오 회의 공급자를 None으로 설정할 때 발생 **합니다**.

    [비즈니스용 Microsoft 365 라이선스 할당 또는 제거를 참조하세요](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    이 전자 메일의 예는 다음과 같습니다.

     ![전화 접속 회의가 꺼져 있습니다.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>보낸 전자 메일 메시지를 변경합니다.

사용자에게 자동으로 전송되는 전자 메일을 변경할 수 있습니다. 기본적으로 전자 메일의 발신자는 Microsoft 365 또는 Office 365 전송되지만 Windows PowerShell 사용하여 표시 이름을 변경할 수 있습니다. 자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps) 를 참조하세요.

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>전자 메일을 보내지 않으려면 어떻게 해야 할까요?

사용자에게 전자 메일 보내기를 사용하지 않도록 설정하면 사용자에게 라이선스가 할당된 경우에도 전자 메일이 전송되지 않습니다. 이 경우 전화 회의 ID, 기본 회의 전화 번호 및 더 중요한 것은 해당 오디오 회의 PIN이 사용자에게 전송되지 않는다는 것입니다. 이 경우 별도의 전자 메일을 보내거나 전화를 걸어 사용자에게 알려야 합니다.

기본적으로 전자 메일은 사용자에게 전송되지만 오디오 회의를 위해 전자 메일을 받지 못하게 하려면 Microsoft Teams 또는 Windows PowerShell 사용할 수 있습니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지** 로 이동합니다.

2. **컨퍼런스 브리지** 페이지 위쪽에서 **브리지 설정을** 클릭합니다.

3. **브리지 설정** 창에서 **전화 접속 설정이 변경되면 자동으로 사용자에게 전자 메일을 보내도록** 설정하거나 사용하지 않도록 설정합니다.

4. **저장** 을 클릭합니다.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Windows PowerShell 사용

Microsoft Teams PowerShell 모듈을 사용하여 다음을 실행할 수도 있습니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

[Set-CsOnlineDialInConferencingTenantSettings를](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.

자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps) 를 참조하세요.

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell 대해 자세히 알고 싶으신가요?

기본적으로 전자 메일의 발신자는 Microsoft 365 또는 Office 365 전송되지만 Windows PowerShell 사용하여 전자 메일 주소 및 표시 이름을 변경할 수 있습니다.

Windows PowerShell 사용자를 관리하는 것과 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. Windows PowerShell 사용하면 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 관리할 수 있습니다. Windows PowerShell 시작하려면 다음 항목을 참조하세요.

- [Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell 사용하여 Office 365 관리하는 가장 좋은 방법](/previous-versions//dn568025(v=technet.10))

Windows PowerShell 대한 자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps)를 참조하세요.

## <a name="related-topics"></a>관련 주제

[오디오 회의 설정이 변경되면 전자 메일 보내기 사용 또는 사용 안 함](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
