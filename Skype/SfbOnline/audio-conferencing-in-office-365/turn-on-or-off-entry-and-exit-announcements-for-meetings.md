---
title: 온라인에서 모임에 대한 항목 및 종료 비즈니스용 Skype 켜기
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '관리 센터를 사용하여 비즈니스용 Skype 온라인 모임에서 공지 사항을 켜거나 종료하는 비즈니스용 Skype 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: f097563ca8dce47277a44573f2af66ed7f1539dd
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237574"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>온라인에서 모임에 대한 항목 및 종료 비즈니스용 Skype 켜기

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 의 입장 및 종료 Microsoft Teams 대한 자세한 내용은 에서 모임에 대한 항목 및 종료 Microsoft Teams 를 [Microsoft Teams 참조하세요.](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)

오디오 회의를 Microsoft 365 또는 Office 365 경우 오디오 회의 브리지가 있습니다. 회의 브리지에는 사용자들이 모임에 전화하는 데 사용할 하나 이상의 전화 비즈니스용 Skype 수 있습니다. 
  
회의 브리지는 전화를 사용하여 모임에 전화 접속하는 사용자에 대한 호출에 응답합니다. 회의 브리지는 회의 자동 참석자로부터 음성 프롬프트를 사용하여 발신자에 응답한 다음 설정에 따라 알림을 재생하고 발신자들에게 이름을 기록할 것을 요청하고 PIN 보안을 설정할 수 있습니다. PIN은 비즈니스용 Skype 모임 이끌이에게 주어지며, 모임 이끌이가 앱을 사용하여 모임을 시작할 수 없는 비즈니스용 Skype 수 있습니다. 그러나 PIN이 모임을 시작하는 데 필요하지 않은지 설정할 수 있습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>모임 조인 옵션 설정
    
1. 관리 **비즈니스용 Skype** 왼쪽 탐색에서 오디오 회의 Microsoft 브리지 설정으로   >  **이동합니다.**
    
2. 모임 **참가 환경 아래에서** 을 사용하도록 설정한 모임 항목 및 종료 알림 사용 을 **선택하거나 선택 취소합니다.** 기본적으로 선택됩니다. 모임을 지우면 모임에 이미 참가한 사용자에게 다른 사용자가 모임에 참가하거나 나가는 경우 알림을 들을 수 없습니다.
    
3. **진입/종료 공지 유형에서** 이름 **또는 전화** 번호 또는 **톤을 선택합니다.**
    
4. 모임에 참가하기 전에 발신자에 이름을 기록할지 확인하거나 **선택을 선택하지 않습니다.**
    
5. 변경한 후 저장을 **클릭합니다.**
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자와 함께 관리하는 방법을 알고 Windows PowerShell?

- 시간을 절약하거나 자동화하기 위해 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet을 사용할 수 있습니다.
    
- 이 경우 Windows PowerShell 온라인에서 비즈니스용 Skype 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 모두 관리할 수 있습니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell 또는 Microsoft 365 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 많은 사용자에 대한 설정을 한 Microsoft 365 경우와 같이 관리 센터를 사용하는 것만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다. 
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Windows PowerShell 온라인용 비즈니스용 Skype 모듈을 사용하면 온라인에 연결하는 원격 Windows PowerShell 세션을 만들 비즈니스용 Skype 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 온라인용 Microsoft 다운로드 센터에서 Windows PowerShell 다운로드할 [비즈니스용 Skype 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>관련 항목

[오디오 회의 일반적인 질문](/MicrosoftTeams/audio-conferencing-common-questions)
