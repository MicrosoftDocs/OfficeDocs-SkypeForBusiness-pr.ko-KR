---
title: Teams에서 PIN 없이 휴대폰을 통해 오디오 회의 시작
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Teams 관리 센터에서 익명 발신자 모임에 참가하지 않도록 설정하거나 사용하지 않도록 설정하는 방법을 배워야 합니다. '
ms.openlocfilehash: 6d5dd7c08d37993c541a0a4f670fd240057bfb3a
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691504"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Microsoft Teams에서 PIN 없이 휴대폰을 통해 오디오 회의 시작

Microsoft Teams 모임 이끌이가 모임을 시작하지 않은 경우 모임에 전화 접속하는 사용자가 모임의 대기실에서 음악을 듣는 데 문제가 될 수 있습니다. 
  
모임 이끌이가 모임에 전화를 걸면 기본적으로 모임을 시작하는 데 PIN이 필요합니다. 누구나 모임에 전화 접속할 수 있도록 설정할 수 있으며 PIN을 사용하여 모임을 시작할지 묻는 메시지가 표시되지 않습니다. 관리 센터를 사용하여 단일 사용자에 대해 이 설정을 설정하거나 사용하지 않도록 설정할 수 있습니다.
  
Microsoft Teams 앱에서 모임을 시작한 경우 모임 이끌이에게 PIN이 필요하지 않습니다. PIN은 모임 이끌이가 전화를 통해 모임에 참가할 때만 필요합니다. 모임에 대한 PIN은 오디오 회의 라이선스가 할당되어 오디오 회의를 사용하도록 설정되면 오디오 사용자에게 전송됩니다.  오디오 [회의](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) 설정이 변경될 때 사용자에게 자동으로 전송되는 오디오 회의 정보와 전자 메일이 있는 전자 메일 보내기를 [참조하세요.](emails-sent-to-users-when-their-settings-change-in-teams.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>익명 발신자 모임에 참가하지 않도록 설정 또는 해제

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 [사용자]를 **클릭합니다.** 

2. 목록에서 사용자를 선택한 다음 페이지 맨 위에 **있는** 편집을 클릭합니다. 

3. 오디오 회의 옆에 **있는** 편집을 **클릭합니다.**

4. 오디오 **회의** 창에서 전화 접속 발신자는 모임의 첫 번째 사용자가 될 수 **있습니다.**
    
4. 적용을 **클릭합니다.** 

**다음 Windows PowerShell**
  
자세한 내용은 [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.

## <a name="what-else-should-you-know"></a>알아야 할 다른 것은 무엇입니까?

- PIN을 다시 설정하려는 경우 오디오 회의 PIN 재설정을 [참조합니다.](reset-the-audio-conferencing-pin-in-teams.md)
    
- 익명 액세스 또는 모임 시작에 PIN을 요구하지 않는 경우 다음을 사용할 수 없습니다.
    
  - 모임이 시작되지 않은 경우(아직 모임에 참석하지 않은 경우): 발신자가 이끌이인 경우 발신자가 묻는 메시지가 표시됨 그렇다면 PIN을 입력하라는 메시지가 표시될 것입니다. PIN을 입력하면 모임이 시작하고 사용자가 모임에 참가합니다.
    
  - 모임이 이미 시작된 경우(다른 사람이 이미 모임에 있는 경우): 발신자가 이끌이인 경우 발신자에 대한 메시지가 표시되지 않습니다. PIN을 묻는 메시지가 표시되지 않습니다. 모임이 이미 시작되어 발신자도 모임에 참가합니다.
    
- 익명 액세스 또는 모임 시작에 PIN이 필요 없는 경우 다음을 사용하도록 설정합니다.
    
  - 모임이 시작되지 않은 경우(아직 모임에 다른 사용자가 없음): 발신자가 이끌이인 경우 발신자에 대한 메시지가 표시되지 않고 PIN을 묻는 메시지가 표시되지 않습니다. 이끌이 설정이 해제되어 있기 때문에 모임이 시작되어 익명 발신자가 모임에 참가합니다.
    
  - 모임이 이미 시작된 경우(다른 사람이 이미 모임에 있는 경우): 발신자가 이끌이인 경우 발신자에 대한 메시지가 표시되지 않습니다. PIN을 묻는 메시지가 표시되지 않습니다. 모임이 이미 시작되어 발신자가 모임에 참가합니다.
    
## <a name="want-to-know-more-about-windows-powershell"></a>자세한 내용은 Windows PowerShell?

Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
자세한 내용은 Windows PowerShell [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.
  
## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
