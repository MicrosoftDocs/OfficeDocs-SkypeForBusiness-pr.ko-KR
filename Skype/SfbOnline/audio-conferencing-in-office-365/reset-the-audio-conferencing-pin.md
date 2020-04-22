---
title: 비즈니스용 Skype Online에서 오디오 회의 PIN 다시 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'Pin에 대해 알아야 할 내용과 비즈니스용 Skype Online에서 다시 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: a2f91e1ccae53f08507a63ea56b499a3ad968c73
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777703"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 오디오 회의 PIN 다시 설정

> [!Note]
> Microsoft 팀에서 오디오 회의 pin을 다시 설정 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에서 오디오 회의 Pin 다시 설정을](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)참조 하세요.

PIN은 오디오 회의를 사용 하도록 설정 된 각 비즈니스용 Skype 사용자에 대해 생성 되는 숫자로 구성 된 코드입니다. 모임 이끌이가 오디오 회의 Pin을 사용 하 여 모임 이끌이가이를 식별 하 고 휴대폰을 통해 모임을 시작 하도록 허용 합니다. Skype for Business 앱을 사용 하 여 모임을 시작 하는 경우 PIN이 필요 하지 않습니다. 사용자가 PIN을 잊거나 오디오 회의를 사용 하도록 설정 했을 때 전송 된 전자 메일에서 찾을 수 없는 경우 관리자가 PIN을 다시 설정 하거나 자신의 PIN을 다시 설정할 수 있습니다.
  
인증 된 사용자가 비즈니스용 Skype 앱을 사용 하 여 참가할 때 또는 주최자가 전화기를 통해 자신의 PIN으로 참가할 때 모임을 시작할 수 있습니다. 모임에서 PIN을 시작 해야 하는 경우 휴대폰을 통해 참가 하는 사용자는 대기실에 저장 되며 모임이 시작 될 때까지 보류 중인 음악을 청취 하 게 됩니다. 모임 이끌이가 휴대폰을 통해 모임을 시작 하기 위해 PIN이 필요 하지 않은 경우에는 호출자가 모임에 참가할 때 PIN을 제공 하 라는 메시지가 표시 되지 않습니다.
  
## <a name="reset-a-users-pin"></a>사용자의 PIN 다시 설정

1. 회사 또는 학교 계정으로 로그인 합니다.
    
2. **비즈니스용 Skype**> 관리 센터로 이동 하 고 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.
    
3. **사용자**를 클릭 하 고 PIN을 다시 설정 하려는 사용자를 선택 합니다.
    
4. 작업 창의 **핀**에서 **원래 대로**를 클릭 합니다.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>사용자가 자신의 PIN을 재설정 하도록 설정

사용자는 **전화 접속 회의** 페이지의 **pin 다시 설정** 옵션을 사용 하 여 pin을 다시 설정할 수 있습니다. 이 페이지는 다음 세 가지 방법 중 하나로 액세스할 수 있습니다.

* 브라우저에서으로 이동 [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling)합니다.
* 비즈니스용 Skype에서 **옵션**옆에 있는 **메뉴 표시** 화살표를 클릭 한 다음 **도구** > **전화 접속 회의 설정을**클릭 합니다.
* 비즈니스용 Skype에서 **옵션**을 클릭 하 고 왼쪽 메뉴의 착신 **전환을** 클릭 한 다음 **기타 통화 설정** 섹션에서 **온라인 설정 편집**을 클릭 합니다. 

## <a name="what-else-should-you-know-about-pins"></a>핀에 대해 알아야 할 기타 사항

- Pin을 다시 설정 하면 PIN이 한 번만 관리자 에게만 표시 됩니다. 관리자가 PIN을 다시 설정한 후에는 **비즈니스용 Skype 관리 센터** 에 * * * * * * * * * * *로 표시 되는 Pin이 Windows PowerShell에서 CsCsOnlineDialInConfencingUser를 사용할 때 그 결과를 볼 수 있습니다.
    
- 사용자에 게 전자 메일을 자동으로 보내는 기능은 기본적으로 사용 되며, 사용자는 오디오 회의를 사용 하도록 설정 하거나 PIN을 다시 설정한 경우 PIN이 포함 된 전자 메일을 받게 됩니다. 그러나 자동으로 전자 메일 보내기를 사용 하지 않도록 설정한 경우 PIN 다시 설정 이메일이 사용자에 게 전송 되지 않으므로 PIN 정보를 사용자에 게 수동으로 보내야 합니다.
    
- 모임이 시작 되 면 대기실에 있는 모든 사용자가 자동으로 참가 합니다. 예를 들어 두 명의 참가자가 모임에 참가 하 려 할 때 모임이 시작 되기 전에 해당 사용자가 보류 중인 음악을 청취 하 고 모임 이끌이가 휴대폰을 통해 PIN을 사용 하 여 참가할 때 모임이 시작 되 고 대기실의 참가자가 모임에 참가 합니다.
    
- 기본 설정은 익명 호출자가 모임을 시작 하도록 허용 하지 않는 것입니다.
    
- 오디오 회의에 대 한 사용자를 활성화 하면 기본적으로 회의 정보와 PIN이 포함 된 전자 메일이 전송 됩니다. PIN을 다시 설정 하면 사용자에 게 설정 된 기본 SMTP 주소 (별칭)로 새 PIN이 사용자에 게 전송 되므로 사용자에 게 Office 365 사서함이 있어야 합니다.
    
- 오디오 회의를 설정할 때 조직의 핀에 필요한 자릿수를 설정 합니다. Pin은 4 ~ 12 자리로 지정할 수 있으며 기본값은 5입니다. PIN 길이 설정을 변경 하면 새로 생성 된 핀에만 설정이 적용 되 고 오디오 회의에 사용 하도록 설정 된 기존 사용자의 PIN 설정에는 적용 되지 않습니다. [오디오 회의 모임에 대 한 PIN 길이 설정을](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)참조 하세요.
    
- 기본적으로 전자 메일은 사용자의 Office 365 기본 SMTP 주소로 설정 됩니다. 전자 메일을 Hotmail 또는 MSN 전자 메일 주소와 같은 비 Office 365 주소로 보낼 수 있습니다. Windows PowerShell을 사용 하 여 기본 전자 메일 주소를 재정의할 수 있습니다. 이 기능은 사용자에 게 Office 365의 Exchange 사서함이 없는 경우에 유용 합니다.
    
- 전자 메일이 전송 되는 기본 사용자 주소를 재정의 하려면 테 넌 트 관리자가 다음 cmdlet을 사용할 수 있습니다. Get-csonlinedialinconferencinguser-amos. e-ResetLeaderPIN-SendEmail-SendEmailToAddress "u@hotmail.com". SendEmail 매개 변수는 사용자의 전자 메일 주소를 재정의 하는 데 필요 합니다.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

- 시간을 절약 하거나이 작업을 자동화 하려면 [Set-get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet을 사용 하면 됩니다.
    
- 다음을 실행 하 여 Amos 대리석에 대 한 PIN을 설정할 수 있습니다.
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[사용자의 회의 ID 다시 설정](reset-a-conference-id-for-a-user.md)
