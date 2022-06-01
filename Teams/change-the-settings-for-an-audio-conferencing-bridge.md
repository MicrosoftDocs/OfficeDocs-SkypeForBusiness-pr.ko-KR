---
title: 오디오 회의 브리지의 설정 변경
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: 입장 및 종료 알림, 재생 이름 또는 전화 번호, 톤 및 프롬프트 발신자의 이름을 기록하는 음성 회의 브리지 설정을 변경합니다.
ms.openlocfilehash: 48925c30d9ac42c76b6f00d8416d767c6e0ab14d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823047"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>오디오 회의 브리지의 설정 변경

Microsoft 365 또는 Office 365 오디오 회의 설정하는 경우 오디오 회의 브리지라고 하는 위치에서 사용자의 전화 번호를 받게 됩니다. 회의 브리지에는 하나 이상의 전화 번호가 포함될 수 있습니다. 이러한 전화 번호는 발신자가 모임에 전화를 걸 때 사용됩니다. 전화 번호는 비즈니스용 Skype 또는 Microsoft Teams 모임 초대의 맨 아래에 포함됩니다.
  
회의 브리지는 통화에 응답하고 모임 자동 전화 교환을 사용하여 음성 프롬프트로 발신자에게 메시지를 표시한 다음 설정에 따라 알림을 재생하고 발신자에게 이름을 기록하도록 요청하고 PIN 설정을 제어할 수 있습니다. 모임 이끌이가 비즈니스용 Skype 또는 Microsoft Teams 앱을 사용하지 않을 때 모임을 시작할 수 있도록 PIN이 제공됩니다.

  > [!IMPORTANT]
  > PIN은 비즈니스용 Skype 또는 Microsoft Teams 앱 사용자가 아직 모임을 시작하지 않은 경우에만 모임 이끌이에게 필요합니다. 모든 사용자가 모임에 전화 접속하는 경우 모임 이끌이가 모임을 시작하려면 PIN이 필요합니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 영역에서 **모임** > **회의 브리지** 로 이동합니다.

2. **회의 브리지** 페이지의 위쪽에서 **브리지 설정을** 클릭합니다.

3. **브리지 설정** 창에서 다음을 선택합니다.
   - **모임 참가 및 종료 알림** 이 기능을 해제하면 모임에 이미 참가한 사용자는 다른 사용자가 모임에 참가하거나 모임을 떠날 때 알림을 받지 않습니다.

     **모임 항목 및 종료 알림을** 켜면 다음 옵션을 선택할 수 있습니다.

   - **이름 또는 전화 번호** 사용자가 모임에 전화를 걸면 모임에 참가할 때 전화 번호가 재생됩니다.

   - **음색** 사용자가 모임에 전화를 걸면 모임에 참가할 때 오디오 톤이 재생됩니다.

   - **모임에 참가하기 전에 발신자에게 자신의 이름을 기록하도록 요청** 이 기능을 해제하면 모임에 참가하기 전에 발신자에게 자신의 이름을 기록하라는 메시지가 표시되지 않습니다.

4. 모임의 PIN 길이를 설정하려면 **PIN 길이** 목록에서 PIN에 대해 원하는 자릿수를 선택합니다.

5. 사용자에게 전자 메일을 보낼지 여부를 지정하려면 **오디오 회의 구성이 변경된 경우 사용자에게 전자 메일을 자동으로 보내도록** 설정하거나 사용하지 않도록 설정합니다.
    자세한 내용은 [Microsoft Teams 오디오 회의 설정이 변경되거나 비즈니스용 Skype](emails-sent-to-users-when-their-settings-change-in-teams.md) [Online에서 설정이 변경되면 사용자에게 전송되는 전자 메일](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)을 참조하세요.

6. **저장** 을 클릭합니다.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell 사용하여 관리하는 방법을 알고 싶으신가요?

- 시간을 절약하거나 이 프로세스를 자동화하려면 [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet을 사용할 수 있습니다.

- Windows PowerShell 사용자를 관리하는 것과 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. Windows PowerShell 사용하면 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 관리할 수 있습니다. Windows PowerShell 시작하려면 다음 항목을 참조하세요.

  - [Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Windows PowerShell 사용하여 Microsoft 365 또는 Office 365 관리하는 가장 좋은 방법](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell 한 번에 많은 사용자에 대해 설정을 변경하는 경우와 같이 Microsoft 365 관리 센터 사용하는 것에 비해 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아봅니다.

  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Windows PowerShell 사용하여 일반적인 비즈니스용 Skype Online 관리 작업 수행](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

    > [!NOTE]
    > 비즈니스용 Skype Online용 Windows PowerShell 모듈을 사용하면 비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 Skype [Online용 Windows PowerShell 모듈](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="related-topics"></a>관련 주제

[Microsoft Teams용 오디오 회의 설정하기](set-up-audio-conferencing-in-teams.md)

[비즈니스용 Skype Online에 대한 오디오 회의 설정](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
