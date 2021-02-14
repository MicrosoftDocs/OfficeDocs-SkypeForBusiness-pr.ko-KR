---
title: 비즈니스용 Skype Online에서 오디오 회의에 대한 자동 전화 연결 언어 설정
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 비즈니스용 Skype Online의 오디오 회의 번호에 대한 오디오 회의 자동 전화 회의 언어를 선택하는 방법을 참조하세요.
ms.openlocfilehash: 93b6ea917c7f79747273366893efc47a22b89bb2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163909"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 오디오 회의에 대한 자동 전화 연결 언어 설정

> [!Note]
> Microsoft Teams에서 자동 참석 언어 설정에 대한 자세한 내용은 Microsoft Teams에서 오디오 회의에 대한 자동 참석 언어 [설정을 참조하세요.](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)

비즈니스용 Skype의 오디오 회의 자동 전화 번호는 모임에 참가할 때 다양한 언어로 오디오 발신자들에게 인사말을 할 수 있습니다.
  
하나의 기본 언어와 최대 4개의 보조 언어를 선택 합니다. 설정한 기본 언어는 먼저 사용하며, 보조 언어는 선택한 순서대로 자동 attendant에서 사용됩니다. 
  
> [!NOTE]
>  전용 범주에 속하는 오디오 회의 번호의 언어만 변경할 수 있습니다. 공유 오디오 회의 번호의 언어는 변경할 수 없습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>회의 자동 참석 언어 설정

이 단계를 [수행하려면](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 전역 관리자 또는 [비즈니스용 Skype](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 관리자 되어야 합니다.
    
1. 비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 레거시 **포털로 이동하세요.** 레거시 포털에서 오디오 회의를 선택한 다음 Microsoft **브리지를 클릭합니다.**
    
2. 목록에서 오디오 회의 전화 번호를 선택하고 작업 창에서 언어 **설정을 클릭합니다.** 전용 오디오 회의 번호의 언어만 변경할 수 있습니다.  
    
3. 언어 **설정 페이지에서** 기본 언어  목록을 클릭하여 사용 가능한 언어의 전체 목록을 볼 수 있습니다. 필요한 경우 각 보조 언어  목록을 클릭하여 보조 언어를 선택합니다.
    
    > [!NOTE]
    > 지원되는 기본 및 보조 언어가 나열됩니다. 목록에서 선택한 순서는 발신자에 제시된 언어의 순서가 됩니다. 
  
4. **저장** 을 클릭합니다.
    
## <a name="want-else-should-i-know"></a>알아야 할 다른 것이 있나요?

- 오디오 회의에 지원되는 언어 목록을 보시고 오디오 회의 지원 언어를 [참조하세요.](/MicrosoftTeams/audio-conferencing-supported-languages)
    
- 언어는 전용으로 설정할 수 있지만 공유 전화 번호에는 설정할 수 없습니다.
    
- 공급자로 Microsoft를 사용하여 Microsoft 365 또는 Office 365에서 오디오 회의를 사용할 수 있는 국가/지역 [](phone-numbers-for-audio-conferencing.md)목록을 표시하는 경우 오디오 회의 전화 번호를 참조하세요.
    
## <a name="want-to-use-windows-powershell"></a>이 기능을 Windows PowerShell?

이 단계를 자동화하기 위해 [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) 및 [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet을 사용할 수 있습니다.
  
자세한 내용은 비즈니스용 Skype Online Windows PowerShell 작업을 수행하는 방법을 [참조하세요.](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
