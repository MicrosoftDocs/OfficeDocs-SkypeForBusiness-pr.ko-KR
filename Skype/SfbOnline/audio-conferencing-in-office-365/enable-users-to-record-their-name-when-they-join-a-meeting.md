---
title: 비즈니스용 Skype Online에서 모임에 참가할 때 사용자가 자신의 이름을 기록할 수 있도록 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: 비즈니스용 Skype Online에서 모임에 참가할 때 사용자가 자신의 이름을 기록할 수 있는지 여부를 설정하거나 사용하지 않도록 설정하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 7fd8afb71ee524b20f24f9583ec847adbec2ff43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114244"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 모임에 참가할 때 사용자가 자신의 이름을 기록할 수 있도록 설정

> [!Note]
> 사용자가 Teams에 자신의 이름을 기록하도록 허용하려면 Microsoft Teams에서 모임에 참가할 때 사용자가 자신의 이름을 기록하도록 설정 [을 참조합니다.](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams)

Microsoft 365 또는 Office 365에서 오디오 회의를 설정하면 전화 번호와 오디오 회의 브리지라고 하는 전화 번호가 수신됩니다. 회의 브리지에는 전용 전화 번호 또는 공유 전화 번호일 수 있는 하나 이상의 전화 번호가 포함될 수 있습니다.
  
회의 브리지는 전화를 사용하여 모임에 전화 접속하는 사용자에 대한 호출에 응답합니다. 회의 브리지는 자동 참석자로부터 음성 프롬프트를 사용하여 발신자에 응답한 다음, 설정에 따라 알림을 재생하고 발신자들에게 이름을 기록할 수 있도록 요청하고, 모임 이끌이를 위한 PIN 보안을 설정할 수 있습니다. 모임 이끌이에게는 모임을 시작할 수 있도록 PINS가 부여됩니다. 그러나 PIN이 모임을 시작할 필요는 없습니다.

## <a name="set-whether-callers-should-record-their-name"></a>발신자 이름을 기록해야 하는지 여부를 설정합니다.
    
1. 비즈니스용 Skype 관리 **센터의** 왼쪽 탐색에서 오디오 회의 Microsoft 브리지 설정으로  >  **이동합니다.**
    
2. 모임 **참가 환경 아래에서** 모임 항목 사용 및 종료 알림이 켜져 있는 확인란을 **참조하세요.**
    
   - **선택된** 발신자는 모임에 들어가기 전에 이름을 기록해야 합니다. 기본적으로 선택됩니다.
    
   - **지우기** 발신자는 모임에 들어가기 전에 이름을 기록할지 묻는 요청이 없습니다.
    
3. 변경한 후 저장을 **클릭합니다.**
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자와 함께 관리하는 방법을 알고 Windows PowerShell.

- 시간을 절약하거나 자동화하기 위해 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet을 사용할 수 있습니다.
    
- Windows PowerShell 사용자 관리 및 사용자가 허용하는 작업을 모두 제공합니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell 많은 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 Microsoft 365 관리 센터를 사용하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다. 
    
  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [비즈니스용 skype Windows PowerShell 관리하기 위해 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [비즈니스용 Windows PowerShell Skype 온라인 관리 작업을 수행하는 데 사용할 수 있습니다.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > 비즈니스용 skype Windows PowerShell 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 Skype 온라인용 Windows PowerShell Microsoft 다운로드 센터에서 다운로드할 [수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)