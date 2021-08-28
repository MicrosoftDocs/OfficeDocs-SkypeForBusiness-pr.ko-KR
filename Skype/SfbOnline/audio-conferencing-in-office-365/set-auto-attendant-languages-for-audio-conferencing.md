---
title: 온라인에서 오디오 회의에 대한 자동 비즈니스용 Skype 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 온라인에서 오디오 회의 번호에 대한 오디오 회의 자동 참석 언어를 선택하는 비즈니스용 Skype 참조하세요.
ms.openlocfilehash: 15eca114c4f3d108a078642e6af23923fe817f66
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584432"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>온라인에서 오디오 회의에 대한 자동 비즈니스용 Skype 설정

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 자동 참석 언어 설정에 대한 자세한 내용은 Microsoft Teams 에서 오디오 회의에 대한 자동 참석 언어 [Microsoft Teams.](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)

오디오 회의 자동 비즈니스용 Skype 모임에 참가할 때 다양한 언어로 오디오 발신자들을 맞이할 수 있습니다.
  
하나의 기본 언어와 최대 4개의 보조 언어를 선택할 수 있습니다. 설정한 기본 언어는 먼저 사용하며, 보조 언어는 선택한 순서대로 자동 참석자가 사용됩니다. 
  
> [!NOTE]
>  전용 범주의 오디오 회의 번호의 언어만 변경할 수 있습니다. 공유 오디오 회의 번호의 언어를 변경할 수 없습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>회의 자동 참석 언어 설정

이 단계를 [](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 수행하려면 전역 관리자 또는 비즈니스용 Skype [관리자](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 되어야 합니다.
    
1. 관리 **비즈니스용 Skype** 왼쪽 탐색에서 레거시 포털 **으로 이동하세요.** 레거시 포털에서 오디오 회의를 선택한 다음 Microsoft **브리지 를 클릭합니다.**
    
2. 목록에서 오디오 회의 전화 번호를 선택하고 작업 창에서 언어 설정 **을 클릭합니다.** 전용 오디오 회의 번호의 언어를 변경할 수만 있습니다.  
    
3. 언어 **설정 페이지에서** 기본 언어  목록을 클릭하여 사용 가능한 언어의 전체 목록을 볼 수 있습니다. 필요한 경우 각 보조 언어  목록을 클릭하여 보조 언어를 선택합니다.
    
    > [!NOTE]
    > 지원되는 기본 언어 및 보조 언어가 나열됩니다. 목록에서 선택한 순서는 발신자에 제시된 언어의 순서입니다. 
  
4. **저장** 을 클릭합니다.
    
## <a name="want-else-should-i-know"></a>다른 것을 알고 싶나요?

- 오디오 회의에 지원되는 언어 목록은 오디오 회의 지원 언어 [를 참조하세요.](/MicrosoftTeams/audio-conferencing-supported-languages)
    
- 언어는 전용으로 설정할 수 있지만 공유 전화 번호는 설정할 수 없습니다.
    
- Microsoft를 사용하여 오디오 회의를 사용할 수 있는 Microsoft 365 Office 365 국가/지역 목록을 보시고 오디오 회의의 전화 숫자를 [참조하세요.](phone-numbers-for-audio-conferencing.md)
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell?

이 단계를 자동화하기 위해 [Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) 및 [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) cmdlet을 사용할 수 있습니다.
  
자세한 내용은 온라인 관리 Windows PowerShell 작업을 수행하기 위해 비즈니스용 Skype [참조하세요.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>관련 주제

[오디오 회의를 시도하거나 Microsoft 365 또는 Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
