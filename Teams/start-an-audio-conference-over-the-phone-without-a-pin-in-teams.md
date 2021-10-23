---
title: 휴대폰에서 PIN 없이 오디오 회의를 Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: '익명 호출자들이 관리자 센터에서 모임에 참가하지 않도록 설정하거나 사용하지 않도록 설정하는 Teams 대해 자세히 알아보습니다. '
ms.openlocfilehash: da31c734275113eab3e96b67230a578d0609c1bb
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537309"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>휴대폰에서 PIN 없이 오디오 회의를 Microsoft Teams

모임 이끌이가 모임을 시작하지 않은 경우 모임의 로비에서 음악이 들리는 모임에 Microsoft Teams 사용자가 좌절할 수 있습니다. 
  
모임 이끌이가 모임에 호출하는 경우 기본적으로 모임을 시작하려면 PIN이 필요합니다. 누구나 모임에 전화 접속할 수 있으며 PIN이 모임을 시작하라는 메시지가 표시되지 않을 수 있도록 설정할 수 있습니다. 관리 센터를 사용하여 단일 사용자에 대해 이 설정을 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.
  
다른 사용자가 앱에서 모임을 시작한 경우 모임 이끌이에 PIN이 Microsoft Teams 없습니다. PIN은 모임 이끌이가 휴대폰을 통해 모임에 참가할 때만 필요합니다. 모임에 대한 PIN은 오디오 회의 라이선스가 할당되어 오디오 회의에 사용할 수 있는 경우 오디오 사용자에게 전송됩니다.  오디오 [회의](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) 설정이 변경될 때 사용자에게 자동으로 전송되는 오디오 회의 정보 및 전자 메일이 있는 사용자에게 전자 메일 보내기 를 [참조하세요.](emails-sent-to-users-when-their-settings-change-in-teams.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>익명 호출자 모임에 참가하지 않도록 설정하거나 사용하지 않도록 설정

 **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 사용자 를 **클릭합니다.** 

2. 목록에서 사용자를 선택한 다음 페이지 맨 위에 **있는** 편집을 클릭합니다. 

3. 오디오 **회의** 옆에 있는 편집을 **클릭합니다.**

4. 오디오 **회의** 창에서 전화 접속 호출을 사용하도록 설정하거나 사용하지 않도록 설정하면 모임의 첫 번째 사용자가 될 **수 있습니다.**
    
4. 적용 **을 클릭합니다.** 

**Windows PowerShell**
  
자세한 [내용은 Microsoft Teams PowerShell 참조를](/powershell/module/teams/?view=teams-ps) 참조하세요.

## <a name="what-else-should-you-know"></a>또 어떤 것을 알아야 하나요?

- PIN을 다시 설정하려는 경우 오디오 회의 [PIN 재설정을 참조합니다.](reset-the-audio-conferencing-pin-in-teams.md)
    
- 익명 액세스 또는 모임 시작에 PIN이 필요 없는 경우 다음을 사용하지 않도록 설정됩니다.
    
  - 모임이 시작되지 않은 경우(모임에 아직 아무도 없습니다. 이끌이인 경우 발신자가 묻는 메시지가 표시됨). 예를 말하면 PIN에 대한 메시지가 표시될 것이고 PIN을 입력하면 모임이 시작하고 사용자가 모임에 참가합니다.
    
  - 모임이 이미 시작된 경우(다른 사람이 모임에 이미 있는 경우): 주최자인 경우 발신자가 묻는 메시지가 표시되지 않습니다. PIN에 대한 메시지가 표시되지 않습니다. 모임이 이미 시작되어 호출자는 모임에 참가합니다.
    
- 익명 액세스 또는 모임 시작에 PIN이 필요 없는 경우 다음을 사용하도록 설정합니다.
    
  - 모임을 시작하지 않은 경우(아직 모임에 참석하지 않은 경우): 주최자인 경우 발신자가 묻는 메시지가 표시되지 않고 PIN에 대한 메시지가 표시되지 않습니다. 이끌이의 설정이 해제로 설정되어 있기 때문에 모임이 시작되어 익명 호출자가 모임에 참가합니다.
    
  - 모임이 이미 시작된 경우(다른 사람이 모임에 이미 있는 경우): 주최자인 경우 발신자가 묻는 메시지가 표시되지 않습니다. PIN에 대한 메시지가 표시되지 않습니다. 모임이 이미 시작되어 호출자는 모임에 참가합니다.
    
## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell을 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.
  
## <a name="related-topics"></a>관련 항목

[오디오 회의를 시도하거나 Microsoft 365 또는 Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)