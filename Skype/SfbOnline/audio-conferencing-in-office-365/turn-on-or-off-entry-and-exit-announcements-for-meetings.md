---
title: 비즈니스용 Skype Online에서 모임에 대 한 시작 및 종료 알림 설정 또는 해제
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
description: '비즈니스용 Skype 관리 센터를 사용 하 여 비즈니스용 Skype Online 모임에서 입력 및 종료 알림을 설정 또는 해제 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 4ce040a329bbdc4095bbda1f964ede970021f80f
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163867"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 모임에 대 한 시작 및 종료 알림 설정 또는 해제

> [!Note]
> Microsoft 팀의 입력 및 종료 알림에 대 한 자세한 내용은 [Microsoft 팀에서 모임에 대 한 시작 및 종료 알림 설정 또는 해제](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)를 참조 하세요.

Microsoft 365 또는 Office 365에서 오디오 회의를 설정 하는 경우 오디오 회의 브리지가 제공 됩니다. 회의 브리지에는 다른 사용자가 비즈니스용 Skype 모임에 전화를 걸 때 사용할 수 있는 하나 이상의 전화 번호가 포함 됩니다. 
  
회의 브리지가 휴대폰을 사용 하 여 모임에 전화를 거는 사용자에 대 한 통화에 응답 합니다. 회의 브리지는 회의 자동 전화 교환에서 음성 메시지를 사용 하 여 발신자에 응답 한 다음 설정에 따라 알림을 재생 하 고, 발신자에 게 이름을 기록 하도록 요청 하 고, PIN 보안을 설정할 수 있습니다. Skype for business 모임 이끌이에게 PIN을 제공 하 고 비즈니스용 Skype 앱을 사용 하 여 모임을 시작할 수 없는 경우 모임을 시작할 수 있습니다. 그러나 모임 시작에 PIN이 필요 하지 않도록 설정할 수 있습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>모임 참가 옵션 설정
    
1. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.
    
2. **모임 참가 환경**에서 **모임 입장 사용 및 종료 알림**기능을 선택 하거나 선택을 취소 합니다. 이 옵션이 기본적으로 선택 되어 있습니다. 이 확인란을 선택 취소 하면 모임에 참가 한 사용자에 게 다른 사용자가 모임에 입장 하거나 떠날 때 알림이 표시 되지 않습니다.
    
3. **입력/종료 알림 유형에**서 **이름 또는 전화 번호** 또는 **톤**을 선택 합니다.
    
4. **모임에 참가 하기 전에 전화 건 사람에 게 이름을 기록 하도록 요청 합니다를**선택 하거나 선택 취소 합니다.
    
5. 변경 작업을 수행한 후 **저장**을 클릭 합니다.
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

- 시간을 절약 하거나이 작업을 자동화 하려면 [Set-사용](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet을 사용 하면 됩니다.
    
- Windows PowerShell을 사용할 때 비즈니스용 Skype Online은 사용자 관리와 사용자가 허용 하거나 허용 하지 않는 작업에 대 한 정보를 제공 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell에는 한 번에 여러 사용자에 게 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요. 
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[오디오 회의 일반적인 질문](/MicrosoftTeams/audio-conferencing-common-questions)
