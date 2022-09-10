---
title: 오디오 회의 모임의 PIN 길이 설정
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
- seo-marvel-mar2020
description: PIN의 길이 및 요구 사항에 대한 매개 변수를 알아보고 Microsoft Teams에서 모임의 길이를 설정하는 방법을 알아봅니다.
ms.openlocfilehash: e589a550eba48401612e183200e54f678f9890c4
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641959"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Microsoft Teams에서 오디오 회의 모임의 PIN 길이 설정

Microsoft Teams에 대한 오디오 회의를 설정할 때 오디오 회의 브리지가 표시됩니다. 회의 브리지에는 하나 이상의 전화 번호가 포함될 수 있습니다. 설정한 전화 번호는 Microsoft Teams 앱의 모임 초대에 포함됩니다.
  
오디오 회의 브리지는 전화기를 사용하여 모임에 전화를 거는 사람들의 통화에 응답합니다. 자동 전화 교환의 음성 프롬프트로 발신자에게 응답한 다음 설정에 따라 알림을 재생하고 발신자에게 이름을 기록하도록 요청할 수 있습니다. **Microsoft 브리지 설정을** 사용하면 모임 알림 및 모임 참가 환경에 대한 설정을 변경하고 모임 이끌이가 사용하는 PIN의 길이를 설정할 수 있습니다. 모임 이끌이는 MICROSOFT Teams 앱을 사용하여 모임에 참가할 수 없는 경우 PIN을 사용하여 모임을 시작합니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN 길이 설정

Microsoft Teams 관리 센터 사용:

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지** 로 이동합니다.

2. **컨퍼런스 브리지** 페이지 위쪽에서 **브리지 설정을** 클릭합니다.

3. **브리지 설정** 창의 **PIN 길이에서 PIN** 에 대해 원하는 자릿수를 선택합니다.

4. **저장** 을 클릭합니다.

> [!NOTE]
> PIN은 전화 회의 ID와 다릅니다. 전화 회의 ID는 모임에 참가할 때 호출자가 사용합니다. 모임을 식별하는 데 사용됩니다. PIN은 호출자를 모임 이끌이로 인증하는 데 사용됩니다.

## <a name="want-to-know-more-about-pin-settings"></a>PIN 설정에 대해 자세히 알고 싶으신가요?

- PIN은 4~12자리일 수 있습니다. 기본값은 5입니다. 숫자는 PIN을 만들 때만 사용됩니다. 문자와 특수 문자는 사용되지 않습니다.

- PIN은 Microsoft Teams 사용자가 아직 모임을 시작하지 않은 경우에만 모임 이끌이에게 필요합니다. 모든 사용자가 모임에 전화 접속하는 경우 모임 이끌이가 모임을 시작하려면 PIN이 필요합니다.

- PIN 보안 설정은 Microsoft 브리지와 연결된 모든 전화 번호에 적용됩니다. 지정된 브리지와 연결된 전화 번호를 사용하는 모든 모임에 적용됩니다.

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell 대해 자세히 알고 싶으신가요?

Windows PowerShell 사용자를 관리하는 것과 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. Windows PowerShell 사용하면 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 관리할 수 있습니다. Windows PowerShell 시작하려면 다음 항목을 참조하세요.

- [Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell 사용하여 Microsoft 365 또는 Office 365 관리하는 가장 좋은 방법](/previous-versions//dn568025(v=technet.10))

Windows PowerShell 대한 자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps)를 참조하세요.

## <a name="related-topics"></a>관련 주제

[Microsoft Teams용 Microsoft 365에서 오디오 회의 체험 또는 구매](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
