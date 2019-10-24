---
title: 비즈니스용 Skype Online에서 모임에 참가할 때 사용자가 자신의 이름을 녹화할 수 있도록 설정
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 비즈니스용 Skype Online에서 모임에 참가할 때 사용자가 자신의 이름을 기록할 수 있는지 여부에 대해 알아봅니다.
ms.openlocfilehash: 19fad95c0775663db799a59da159ed145aedda6b
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642614"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 모임에 참가할 때 사용자가 자신의 이름을 녹화할 수 있도록 설정

> [!Note]
> 사용자가 팀에 자신의 이름을 기록할 수 있도록 하려면 [Microsoft 팀에서 모임에 참가할 때 사용자 이름을 기록할 수 있도록](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams)합니다 .를 참조 하세요.

Office 365에서 오디오 회의를 설정 하는 경우 전화 번호를 받고 오디오 회의 브리지 라고 합니다. 회의 브리지에는 전용 또는 공유 전화 번호로 사용할 수 있는 하나 이상의 전화 번호가 포함 될 수 있습니다.
  
회의 브리지가 휴대폰을 사용 하 여 모임에 전화를 거는 사용자에 대 한 통화에 응답 합니다. 회의 브리지는 자동 전화 교환의 음성 프롬프트를 사용 하 여 발신자에 응답 한 다음 설정에 따라 알림을 재생 하 고, 발신자에 게 자신의 이름을 기록 하도록 요청 하 고, 모임 이끌이에게 대 한 PIN 보안을 설정할 수 있습니다. 모임을 시작 하는 데 사용할 수 있도록 모임 이끌이가 Pin을 제공 합니다. 그러나 모임을 시작 하는 데 PIN이 필요 하지 않도록 설정할 수 있습니다.

## <a name="set-whether-callers-should-record-their-name"></a>호출자가 자신의 이름을 기록해 야 하는지 여부 설정
    
1. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.
    
2. **모임 참가 환경**에서 **모임 입장 설정 및 종료 알림**설정 확인란을 참조 하세요.
    
   - **선택 됨** 전화 건 사람이 모임에 진입 하기 전에 이름을 기록해 야 한다는 메시지가 표시 됩니다. 이 옵션이 기본적으로 선택 되어 있습니다.
    
   - **선택 취소** 전화 건 사람이 모임에 진입 하기 전에 자신의 이름을 기록해 야 한다는 메시지가 표시 되지 않습니다.
    
3. 변경 작업을 수행한 후 **저장**을 클릭 합니다.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

- 시간을 절약 하거나이 작업을 자동화 하려면 [Set-사용](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet을 사용 하면 됩니다.
    
- Windows PowerShell은 사용자 관리와 사용자가 수행할 수 있는 작업에 대 한 정보입니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요. 
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[Office 365에서 오디오 회의 체험 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
