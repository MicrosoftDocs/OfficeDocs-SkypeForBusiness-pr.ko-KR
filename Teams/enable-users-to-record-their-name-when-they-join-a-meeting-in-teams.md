---
title: 사용자가 모임의 이름을 기록할 수 있도록 설정
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: 사용자가 Microsoft Teams에서 모임에 참가할 때 자신의 이름을 기록할 수 있는지 여부를 사용하거나 사용하지 않도록 설정하는 방법을 알아봅니다.
ms.openlocfilehash: 8d626437d1e7dd04ce8b4f91428bfe22cc3aeb43
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641729"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a>사용자가 Microsoft Teams에서 모임에 참가할 때 자신의 이름을 기록할 수 있도록 설정

Microsoft 365 또는 Office 365 오디오 회의를 설정하는 경우 전화 번호와 오디오 회의 브리지라고 하는 항목을 받게 됩니다. 회의 브리지에는 전용 또는 공유 전화 번호일 수 있는 하나 이상의 전화 번호가 포함될 수 있습니다.
  
회의 브리지는 전화를 사용하여 모임에 전화를 걸고 있는 사용자에 대한 통화에 응답합니다. 회의 브리지는 자동 전화 교환의 음성 프롬프트로 발신자에게 응답한 다음, 설정에 따라 알림을 재생하고, 발신자에게 이름을 기록하도록 요청하고, 모임 이끌이를 위한 PIN 보안을 설정할 수 있습니다. 모임 이끌이가 모임을 시작할 수 있도록 PIN이 제공됩니다. 그러나 모임을 시작하는 데 PIN이 필요하지 않도록 설정할 수 있습니다.

## <a name="set-whether-callers-should-record-their-name"></a>호출자가 자신의 이름을 기록해야 하는지 여부 설정

Microsoft Teams 관리 센터 사용:

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지** 로 이동합니다.

2. **컨퍼런스 브리지** 페이지 위쪽에서 **브리지 설정을** 클릭합니다.

3. **모임 항목 및 종료 알림을** 사용하거나 사용하지 않도록 설정합니다.

4. 알림을 사용하도록 설정하는 경우 **항목/종료 공지 유형** 에서 **이름 또는 전화 번호를** 선택한 다음 **모임에 참가하기 전에 발신자에게 자신의 이름을 기록하도록 요청합니다.**

5. **저장** 을 클릭합니다.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell 대해 자세히 알고 싶으신가요?

Windows PowerShell 사용자를 관리하는 것과 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. Windows PowerShell 사용하면 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 관리할 수 있습니다. Windows PowerShell 시작하려면 다음 항목을 참조하세요.

- [Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell 사용하여 Office 365 관리하는 가장 좋은 방법](/previous-versions//dn568025(v=technet.10))

Windows PowerShell 대한 자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps)를 참조하세요.
