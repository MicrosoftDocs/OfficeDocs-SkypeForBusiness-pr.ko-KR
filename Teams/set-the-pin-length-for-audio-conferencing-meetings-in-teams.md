---
title: 오디오 회의 모임의 PIN 길이 설정
ms.author: tonysmit
author: tonysmit
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
description: PIN의 길이 및 요구 사항에 대한 매개 변수를 알아보고 모임의 길이를 설정하는 방법을 Microsoft Teams.
ms.openlocfilehash: 68297e437bdf0f3be9affa4d5e5518295dd05ab7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608785"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>오디오 회의 모임에 대한 PIN 길이를 Microsoft Teams

오디오 회의를 설정하는 경우 Microsoft Teams 브리지를 얻게 됩니다. 회의 브리지에는 하나 이상의 전화 번호가 포함될 수 있습니다. 설정한 전화 번호는 앱의 모임 초대에 Microsoft Teams 있습니다.
  
오디오 회의 브리지는 전화기를 사용하여 모임에 전화를 거는 사람들의 통화에 응답합니다. 자동 참석자에서 음성 프롬프트를 사용하여 발신자에 응답한 다음 설정에 따라 알림을 재생하고 발신자들에게 이름을 기록할 것을 요청할 수 있습니다. **Microsoft 브리지 설정을** 사용하면 모임 알림 및 모임 참가 환경 설정을 변경하고 모임 이끌이가 사용하는 PI의 길이를 설정할 수 있습니다. 모임 이끌이는 PINS를 사용하여 모임에 참가할 수 없는 Microsoft Teams 있습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN 길이 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.** 

2. 컨퍼런스 브리지  페이지의 맨 위에 있는 브리지 **설정.** 

3. 브리지 **설정** 창의 PIN 길이 아래에서 **PIN에** 대해 원하는 자릿수 수를 선택합니다.

4. **저장** 을 클릭합니다.

> [!NOTE]
> PIN은 회의 ID와 다릅니다. 회의 신분은 모임에 참가할 때 발신자에 의해 사용됩니다. 모임을 식별하는 데 사용됩니다. PIN은 발신자를 모임 이끌이로 인증하는 데 사용됩니다. 

## <a name="want-to-know-more-about-pin-settings"></a>PIN 설정에 대해 더 알고 싶나요?

- PINS는 4에서 12자리까지일 수 있습니다. 기본값은 5입니다. 숫자는 PINS를 만들 때만 사용됩니다. 문자 및 특수 문자는 사용되지 않습니다.
    
- PIN은 사용자가 모임을 아직 시작하지 않은 Microsoft Teams 모임 이끌이에게만 필요합니다. 모든 사용자가 모임에 전화 접속하는 경우 모임 이끌이가 모임을 시작하려면 PIN이 필요합니다.
    
- PIN 보안 설정은 Microsoft 브리지와 연결된 모든 전화 번호에 적용됩니다. 해당 브리지와 연결된 전화 번호를 사용하는 모든 모임에 적용됩니다. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell을 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.
    
  
## <a name="related-topics"></a>관련 주제

[오디오 회의를 시도하거나 Microsoft 365 또는 Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)