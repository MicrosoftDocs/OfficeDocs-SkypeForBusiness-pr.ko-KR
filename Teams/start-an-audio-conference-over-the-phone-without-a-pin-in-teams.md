---
title: Microsoft 팀에서 PIN을 사용 하지 않고 전화로 오디오 회의 시작
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '팀 관리 센터에서 익명 호출자가 모임에 참가 하지 않도록 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 78b35b65c1bb27d366e8e9fa27c49ef32864081f
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "37570009"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Microsoft 팀에서 PIN을 사용 하지 않고 전화로 오디오 회의 시작

Microsoft 팀 모임 이끌이가 모임을 시작 하지 않았기 때문에 모임에 전화 접속 하는 사용자가 음악에 대 한 모임 로비에 보관 되는 것은 어려울 수 있습니다. 
  
모임 이끌이가 모임에 전화를 거는 경우 기본적으로 모임을 시작 하려면 PIN이 필요 합니다. 다른 사용자가 모임에 전화를 걸 수 있도록 설정할 수 있으며 모임 시작을 위해 PIN을 묻지 않습니다. 관리 센터를 사용 하 여 단일 사용자에 대해이 설정을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.
  
다른 사용자가 Microsoft 팀 앱에서 모임을 시작 했다면 모임 이끌이에게는 PIN이 필요 하지 않습니다. PIN은 모임 이끌이가 휴대폰을 통해 모임에 참가 하는 경우에만 필요 합니다. 모임에 대 한 PIN은 오디오 **회의** 라이선스를 할당 하 고 오디오 회의를 사용할 수 있는 경우 오디오 사용자에 게 전송 됩니다. 음성 회의 [설정이 변경 될 때 자동으로 사용자에 게 전송 되는](emails-sent-to-users-when-their-settings-change-in-teams.md) [전자 메일을 사용자에 게 오디오 회의 정보](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) 및 메일로 보내기를 참조 하세요.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>익명 호출자가 모임에 참가 하지 못하도록 설정 또는 해제

![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘

1. 왼쪽 탐색 창에서 **사용자**를 클릭 합니다. 

2. 목록에서 사용자를 선택한 다음, 페이지 맨 위에 있는 **편집** 을 클릭 합니다. 

3. **오디오 회의**옆에 있는 **편집**을 클릭 합니다.

4. **오디오 회의** 창에서 인증 되지 않은 발신자를 사용 하거나 사용 하지 않도록 설정 하는 **것이 모임에서 첫 번째 사용자가 될 수 있습니다**.
    
4. **저장**을 클릭 합니다. 

**Windows Powershell 사용**
  
자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.

## <a name="what-else-should-you-know"></a>알아야 할 기타 사항

- PIN을 다시 설정 하려면 [오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin-in-teams.md)참조 하세요.
    
- 익명 액세스 또는 모임을 시작 하기 위해 PIN이 필요 하지 않은 경우 사용 하지 않도록 설정 됩니다.
    
  - 모임이 시작 되지 않은 경우 (모임에 아무도 없음) 다음을 수행 하는 경우 호출자에 게 해당 사람이 이끌이 인지 묻는 메시지가 표시 됩니다. 예, pin을 입력 하 라는 메시지가 표시 되 면, 모임이 시작 되 고 사용자가 모임에 참가 합니다.
    
  - 모임이 이미 시작 된 경우 (다른 사람이 이미 모임에 참가 한 경우): 주최자가 이끌이이 고 PIN을 입력 하 라는 메시지가 표시 되지 않으면 발신자에 게 메시지가 표시 되지 않습니다. 모임이 이미 시작 되었으며 호출자가 참가 하 게 됩니다.
    
- 익명 액세스 또는 모임을 시작 하기 위해 PIN이 필요 하지 않은 경우 다음을 사용 합니다.
    
  - 모임이 시작 되지 않은 경우 (모임에 아무도 없음) 다음을 수행 하 라는 메시지가 표시 되지 않습니다. 주최자는 이끌이이 고 PIN을 입력 하 라는 메시지가 표시 되지 않습니다. 이끌이의 설정이 off로 설정 되어 있으므로 모임이 시작 되 고 익명 발신자가 모임에 참가 합니다.
    
  - 모임이 이미 시작 된 경우 (다른 사람이 이미 모임에 속해 있는 경우), 발신자에 게 메시지가 표시 되지 않으며, PIN을 입력 하 라는 메시지가 표시 되지 않으며, 모임이 이미 시작 되어 발신자가 참여 하 게 됩니다.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.
  
## <a name="related-topics"></a>관련 주제

[Office 365에서 오디오 회의 체험 또는 구매](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
