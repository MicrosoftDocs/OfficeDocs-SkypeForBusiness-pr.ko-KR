---
title: Microsoft Teams에서 오디오 회의 PIN 다시 설정
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Microsoft Teams에서 사용자의 오디오 회의 PIN을 다시 설정하는 방법을 알아보고 PIN에 대한 중요한 사실을 알아봅니다.
ms.openlocfilehash: 51c936580010899355db539a45477afd932fb53d
ms.sourcegitcommit: d3eb876e58c9e4a0a11a21b9292d3a6177508d81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2022
ms.locfileid: "68329032"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Microsoft Teams에서 오디오 회의 PIN 다시 설정

PIN은 오디오 회의를 사용하도록 설정된 각 Microsoft Teams 사용자에 대해 생성된 숫자로 구성된 코드입니다. 오디오 회의 PIN은 모임 이끌이가 모임 이끌이임을 식별하고 전화를 통해 모임을 시작할 수 있도록 하는 데 사용됩니다. Microsoft Teams 앱을 사용하여 모임을 시작하는 경우 PIN이 필요하지 않습니다. 사용자가 PIN을 잊어버리고 오디오 회의를 사용하도록 설정했을 때 보낸 전자 메일에서 PIN을 찾을 수 없는 경우 관리자는 PIN을 다시 설정하거나 자신의 PIN을 다시 설정할 수 있습니다.
  
인증된 사용자가 Microsoft Teams 앱을 사용하여 참가하거나 이끌이가 전화를 통해 PIN에 조인할 때 모임을 시작할 수 있습니다. 모임을 시작하기 위해 PIN이 필요한 경우 전화를 통해 참가하는 사용자는 로비에 배치되고 이끌이가 이를 인정할 때까지 보류 중인 음악을 듣습니다. 모임 이끌이가 전화를 통해 모임을 시작하는 데 PIN이 필요하지 않은 경우 발신자는 모임에 참가할 때 PIN을 제공하라는 요청을 받지 않습니다.

## <a name="reset-a-users-pin"></a>사용자의 PIN 다시 설정

Microsoft Teams 관리 센터 사용:

1. 왼쪽 탐색 영역에서 **사용자를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. **편집** 을 클릭합니다.

3. **오디오 회의** 아래에서 **PIN 다시 설정을** 클릭합니다.

4. **다시 설정을** 클릭합니다.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="have-a-user-reset-their-own-pin"></a>사용자가 자신의 PIN을 다시 설정하게 합니다.

1. 사용자가 .로 이동하도록 합니다 [https://dialin.teams.microsoft.com/usp](https://dialin.teams.microsoft.com/usp).
2. **PIN 재설정** 을 클릭합니다.

> [!NOTE]
> GCCH의 경우 다음 [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp)으로 이동합니다.
> DoD의 경우 다음 [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp)으로 이동합니다.

> [!NOTE]
> 이 메서드를 사용하는 경우 PIN 재설정 전자 메일은 사용자에게 전송되지 않습니다.

## <a name="what-else-should-you-know-about-pins"></a>PIN에 대해 알아야 할 다른 사항

- 보안을 위해 PIN이 다시 설정되는 경우 PIN은 관리자에게 한 번만 표시됩니다. 관리자가 PIN을 다시 설정하면 PIN이 ***********로 나열됩니다.

- 사용자에게 전자 메일을 자동으로 보내는 것은 기본적으로 사용하도록 설정되며, 사용자는 오디오 회의를 사용하도록 설정하거나 PIN을 다시 설정할 때 PIN이 포함된 전자 메일을 받게 됩니다. 그러나 전자 메일을 자동으로 전송하지 않도록 설정한 경우 PIN 재설정 전자 메일은 사용자에게 전송되지 않으며 사용자에게 PIN 정보를 수동으로 보내야 합니다.

- 모임이 시작되면 이끌이는 로비에 있는 모든 PSTN 사용자가 모임에 참가하도록 허용해야 합니다. 예를 들어 두 명의 PSTN 참가자가 모임을 시작하기 전에 모임에 참가하려고 하면 대기실에 배치되고 대기 중인 음악을 들으며 모임 이끌이가 전화를 통해 PIN을 사용하여 참가하면 모임이 시작되고 이끌이가 모임 내 명령(*21 누르기)을 사용하여 로비에 있는 모든 PSTN 사용자를 허용할 수 있습니다.

- 기본 설정은 익명 호출자가 모임을 시작하도록 허용하지 않는 것입니다.

- 사용자가 오디오 회의를 사용하도록 설정하면 기본적으로 회의 정보 및 해당 PIN이 포함된 전자 메일이 전송됩니다. PIN이 다시 설정되면 새 PIN이 사용자에 대해 설정된 기본 SMTP 주소(별칭)로 전자 메일로 사용자에게 전송되기 때문에 사용자에게 Microsoft 365 또는 Office 365 사서함이 있어야 합니다.

- 오디오 회의를 설정할 때 조직의 PIN에 필요한 숫자를 설정합니다. PIN은 4~12자리일 수 있으며 기본값은 5입니다. PIN 길이 설정을 변경하면 새로 생성된 PIN에만 설정이 적용되며 오디오 회의를 사용하도록 설정된 기존 사용자의 PIN 설정에는 적용되지 않습니다. [오디오 회의 모임의 PIN 길이 설정을 참조하세요](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).

- 기본적으로 전자 메일은 사용자의 Microsoft 365 또는 Office 365 기본 SMTP 주소로 설정됩니다. 핫메일 또는 MSN 전자 메일 주소와 같은 비 Microsoft 365 또는 Office 365 이외의 주소로 전자 메일을 보낼 수 있습니다. Windows PowerShell 사용하여 기본 전자 메일 주소를 재정의할 수 있습니다. 이는 사용자에게 Microsoft 365 또는 Office 365 Exchange 사서함이 없는 경우에 유용합니다.

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell 대해 자세히 알고 싶으신가요?

Windows PowerShell 사용자를 관리하는 것과 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. Windows PowerShell 사용하면 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 관리할 수 있습니다. Windows PowerShell 시작하려면 다음 항목을 참조하세요.

- [Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell 사용하여 Microsoft 365 또는 Office 365 관리하는 가장 좋은 방법](/previous-versions//dn568025(v=technet.10))

Windows PowerShell 대한 자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps)를 참조하세요.
  
## <a name="related-topics"></a>관련 주제

[사용자의 회의 ID 다시 설정](reset-a-conference-id-for-a-user-in-teams.md)
