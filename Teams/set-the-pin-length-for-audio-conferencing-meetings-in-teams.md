---
title: Microsoft 팀에서 오디오 회의 모임에 대 한 PIN 길이 설정
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: PIN의 길이 및 요구 사항에 대 한 매개 변수를 알아보고 Microsoft 팀에서 모임의 길이를 설정 하는 방법을 살펴봅니다.
ms.openlocfilehash: 7f7f477d14556baa7d2a47e5062aacd5de5796fd
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41694003"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Microsoft 팀에서 오디오 회의 모임에 대 한 PIN 길이 설정

Microsoft 팀에 대 한 오디오 회의를 설정 하는 경우 오디오 회의 브리지가 제공 됩니다. 회의 브리지에는 하나 이상의 전화 번호가 포함 될 수 있습니다. 설정한 전화 번호는 Microsoft 팀 앱에 대 한 모임 초대에 포함 됩니다.
  
오디오 회의 브리지가 휴대폰을 사용 하 여 모임에 전화를 거는 사람들을 위한 통화에 응답 합니다. 자동 전화 교환에서 음성 메시지가 표시 된 호출자에 게 응답 한 다음 설정에 따라 알림을 재생 하 고 호출자에 게 해당 이름을 기록 하도록 요청할 수 있습니다. **Microsoft bridge 설정을** 사용 하 여 모임 알림과 모임 참가 환경에 대 한 설정을 변경 하 고 모임 이끌이가 사용 하는 핀 길이를 설정할 수 있습니다. 모임 이끌이는 Pin을 사용 하 여 Microsoft 팀 앱을 사용 하 여 모임에 참가할 수 없는 경우 모임을 시작 합니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>PIN 길이 설정

![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지로**이동 합니다. 

2. **회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다. 

3. **브리지 설정** 창의 **pin 길이**에서 원하는 PIN의 자릿수를 선택 합니다.

4. **저장**을 클릭 합니다.

> [!NOTE]
> PIN이 전화 회의 ID와 다릅니다. 회의 Id는 발신자가 모임에 참가할 때 사용 합니다. 회의를 식별 하는 데 사용 됩니다. PIN은 모임 이끌이로 서 호출자를 인증 하는 데 사용 됩니다. 

## <a name="want-to-know-more-about-pin-settings"></a>PIN 설정에 대 한 자세한 내용을 확인 하 고 싶으신가요?

- Pin의 자릿수는 4 ~ 12 자리입니다. 기본값은 5입니다. 숫자는 핀을 만들 때만 사용 됩니다. 문자 및 특수 문자는 사용 되지 않습니다.
    
- PIN은 Microsoft 팀 사용자가 모임을 아직 시작 하지 않은 경우 모임 이끌이에게만 필요 합니다. 모든 사용자가 모임에 전화를 거는 경우 모임 이끌이가 모임을 시작 하려면 PIN이 필요 합니다.
    
- PIN 보안 설정은 Microsoft bridge와 연결 된 모든 전화 번호에 적용 됩니다. 해당 브리지에 연결 된 전화 번호를 사용 하는 모든 모임에 적용 됩니다. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.
    
  
## <a name="related-topics"></a>관련 주제

[Office 365에서 오디오 회의 체험 또는 구매](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
