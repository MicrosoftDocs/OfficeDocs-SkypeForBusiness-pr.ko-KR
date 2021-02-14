---
title: 비즈니스용 Skype Online에서 오디오 회의 모임의 PIN 길이 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: PIN의 길이 및 요구 사항에 대한 매개 변수를 알아보고 비즈니스용 Skype에서 모임의 길이를 설정하는 방법을 참조하세요.
ms.openlocfilehash: 9e1be77b18c5b416d220ce5d7432562888ce5752
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164537"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 오디오 회의 모임의 PIN 길이 설정


> [!NOTE]
> Microsoft Teams에서 PIN 길이를 설정하는 자세한 내용은 Microsoft Teams에서 오디오 회의 모임의 PIN 길이 [설정을 참조하세요.](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)

비즈니스용 Skype의 오디오 회의를 설정하면 오디오 회의 브리지가 열리게 됩니다. 회의 브리지에는 하나 이상의 전화 번호가 포함될 수 있습니다. 설정한 전화 번호는 비즈니스용 Skype 앱의 모임 초대에 포함됩니다.
  
오디오 회의 브리지는 전화기를 사용하여 모임에 전화를 거는 사람들의 통화에 응답합니다. 자동 전화 회의에서 음성 프롬프트로 발신자에 응답한 다음 설정에 따라 알림을 재생하고 발신자 이름을 기록해 달라고 요청합니다. **Microsoft 브리지** 설정을 사용하면 모임 알림 및 모임 참가 환경 설정을 변경하고 모임 이끌이가 사용하는 PI의 길이를 설정할 수 있습니다. 모임 이끌이는 비즈니스용 Skype 앱을 사용하여 모임에 참가할 수 없는 경우 PI를 사용하여 모임을 시작할 수 있습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN 길이 설정
 
1. 비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의 Microsoft 브리지  >  **설정으로 이동합니다.**
    
2. 보안   >  **PIN 길이에서** PIN에 사용할 자릿수와 저장을 **클릭합니다.**
    
> [!NOTE]
> PIN은 회의 ID와 다릅니다. 전화 회의 신분은 발신자들이 모임에 참가할 때 사용됩니다. 모임을 식별하는 데 사용됩니다. PIN은 발신자가 모임 이끌이로 인증하는 데 사용됩니다. 

## <a name="want-to-know-more-about-pin-settings"></a>PIN 설정에 대해 더 알고 싶나요?

- PINS는 4자리에서 12자리까지 사용할 수 있습니다. 기본값은 5입니다. 숫자는 PINS를 만들 때만 사용됩니다. 문자와 특수 문자는 사용되지 않습니다.
    
- PIN은 비즈니스용 Skype 사용자가 아직 모임을 시작하지 않은 경우 모임 이끌이에게만 필요합니다. 모든 사용자가 모임에 전화 접속하는 경우 모임 이끌이가 모임을 시작하려면 PIN이 필요합니다.
    
- PIN 보안 설정은 Microsoft 브리지와 연결된 모든 전화 번호에 적용됩니다. 해당 브리지와 연결된 전화 번호를 사용하는 모든 모임에 적용됩니다. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?

- 시간을 절약하거나 이 작업을 자동화하기 위해 [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet을 사용할 수 있습니다.
    
- PIN의 자릿수는 8로 설정하는 경우:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 예를 들어 한 번으로 많은 사용자에 대해 설정을 변경할 때도 그렇습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다. 
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스 Windows PowerShell용 Skype Online 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 [Skype Online용](https://go.microsoft.com/fwlink/?LinkId=294688) Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="see-also"></a>참고 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
