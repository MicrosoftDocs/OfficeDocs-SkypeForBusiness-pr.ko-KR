---
title: 비즈니스용 Skype Online에서 오디오 회의 모임에 대 한 PIN 길이 설정
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
description: PIN의 길이 및 요구 사항에 대 한 매개 변수를 알아보고 비즈니스용 Skype에서 모임의 길이를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 9e1be77b18c5b416d220ce5d7432562888ce5752
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164537"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 오디오 회의 모임에 대 한 PIN 길이 설정


> [!NOTE]
> Microsoft 팀에서 PIN 길이를 설정 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에서 오디오 회의 모임에 대 한 pin 길이](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)설정을 참조 하세요.

비즈니스용 Skype에 대 한 오디오 회의를 설정 하는 경우 오디오 회의 브리지가 제공 됩니다. 회의 브리지에는 하나 이상의 전화 번호가 포함될 수 있습니다. 설정한 전화 번호는 비즈니스용 Skype 앱에 대 한 모임 초대에 포함 됩니다.
  
오디오 회의 브리지는 전화기를 사용하여 모임에 전화를 거는 사람들의 통화에 응답합니다. 자동 전화 교환에서 음성 메시지가 표시 된 호출자에 게 응답 한 다음 설정에 따라 알림을 재생 하 고 호출자에 게 해당 이름을 기록 하도록 요청할 수 있습니다. **Microsoft bridge 설정을** 사용 하 여 모임 알림과 모임 참가 환경에 대 한 설정을 변경 하 고 모임 이끌이가 사용 하는 핀 길이를 설정할 수 있습니다. 모임 이끌이는 비즈니스용 Skype 앱을 사용 하 여 모임에 참가할 수 없는 경우 모임을 시작 하기 위해 Pin을 사용 합니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN 길이 설정
 
1. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.
    
2. **보안** > **pin 길이**에서 PIN에 대해 원하는 자릿수를 선택한 다음 **저장**을 클릭 합니다.
    
> [!NOTE]
> PIN이 전화 회의 ID와 다릅니다. 회의 Id는 발신자가 모임에 참가할 때 사용 합니다. 회의를 식별 하는 데 사용 됩니다. PIN은 모임 이끌이로 서 호출자를 인증 하는 데 사용 됩니다. 

## <a name="want-to-know-more-about-pin-settings"></a>PIN 설정에 대 한 자세한 내용을 확인 하 고 싶으신가요?

- Pin의 자릿수는 4 ~ 12 자리입니다. 기본값은 5입니다. 숫자는 핀을 만들 때만 사용 됩니다. 문자 및 특수 문자는 사용 되지 않습니다.
    
- PIN은 비즈니스용 Skype 사용자가 아직 모임을 시작 하지 않은 경우 모임 이끌이에게만 필요 합니다. 모든 사용자가 모임에 전화를 거는 경우 모임 이끌이가 모임을 시작 하려면 PIN이 필요 합니다.
    
- PIN 보안 설정은 Microsoft bridge와 연결 된 모든 전화 번호에 적용 됩니다. 해당 브리지에 연결 된 전화 번호를 사용 하는 모든 모임에 적용 됩니다. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

- 시간을 절약 하거나이 작업을 자동화 하려면 [Set-사용](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet을 사용 하면 됩니다.
    
- PIN의 숫자를 8로 설정 하려면 다음을 실행 합니다.`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요. 
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="see-also"></a>참고 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 체험 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
