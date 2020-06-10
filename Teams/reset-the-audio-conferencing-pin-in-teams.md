---
title: Microsoft 팀에서 오디오 회의 PIN 다시 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Microsoft 팀에서 사용자의 오디오 회의 PIN을 재설정 하는 방법과 Pin에 대 한 중요 한 정보를 확인 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 8926218c72c888edb00480ff8382672a3730cf15
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666190"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Microsoft 팀에서 오디오 회의 PIN 다시 설정

PIN은 오디오 회의를 사용 하도록 설정 된 각 Microsoft 팀 사용자에 대해 생성 되는 숫자로 구성 된 코드입니다. 모임 이끌이가 오디오 회의 Pin을 사용 하 여 모임 이끌이가이를 식별 하 고 휴대폰을 통해 모임을 시작 하도록 허용 합니다. Microsoft 팀 앱을 사용 하 여 모임을 시작 하는 경우에는 PIN이 필요 하지 않습니다. 사용자가 PIN을 잊거나 오디오 회의를 사용 하도록 설정 했을 때 전송 된 전자 메일에서 찾을 수 없는 경우 관리자가 PIN을 다시 설정 하거나 자신의 PIN을 다시 설정할 수 있습니다.
  
인증 된 사용자가 Microsoft 팀 앱을 사용 하 여 참가할 때 또는 주최자가 휴대폰을 통해 자신의 PIN으로 참가할 때 모임을 시작할 수 있습니다. 모임에서 PIN을 시작 해야 하는 경우 휴대폰을 통해 참가 하는 사용자는 대기실에 저장 되며 모임이 시작 될 때까지 보류 중인 음악을 청취 하 게 됩니다. 모임 이끌이가 휴대폰을 통해 모임을 시작 하기 위해 PIN이 필요 하지 않은 경우에는 호출자가 모임에 참가할 때 PIN을 제공 하 라는 메시지가 표시 되지 않습니다.

## <a name="reset-a-users-pin"></a>사용자의 PIN 다시 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

2. **편집**을 클릭 합니다.

3. **오디오 회의**에서 **PIN 다시 설정을**클릭 합니다.

4. **원래 대로**를 클릭 합니다.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>사용자가 자신의 PIN을 재설정 하도록 설정

1. 사용자를 이동 [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) 합니다.
2. **PIN 다시 설정을**클릭 합니다. 


## <a name="what-else-should-you-know-about-pins"></a>핀에 대해 알아야 할 기타 사항

- Pin을 다시 설정 하면 PIN이 한 번만 관리자 에게만 표시 됩니다. 관리자가 PIN을 다시 설정한 후에는 * * * * * * * * * * *와 같은 PIN이 표시 됩니다.
    
- 사용자에 게 전자 메일을 자동으로 보내는 기능은 기본적으로 사용 되며, 사용자는 오디오 회의를 사용 하도록 설정 하거나 PIN을 다시 설정한 경우 PIN이 포함 된 전자 메일을 받게 됩니다. 그러나 자동으로 전자 메일 보내기를 사용 하지 않도록 설정한 경우 PIN 다시 설정 이메일이 사용자에 게 전송 되지 않으므로 PIN 정보를 사용자에 게 수동으로 보내야 합니다.
    
- 모임이 시작 되 면 대기실에 있는 모든 사용자가 자동으로 참가 합니다. 예를 들어 두 명의 참가자가 모임에 참가 하 려 할 때 모임이 시작 되기 전에 해당 사용자가 보류 중인 음악을 청취 하 고 모임 이끌이가 휴대폰을 통해 PIN을 사용 하 여 참가할 때 모임이 시작 되 고 대기실의 참가자가 모임에 참가 합니다.
    
- 기본 설정은 익명 호출자가 모임을 시작 하도록 허용 하지 않는 것입니다.
    
- 오디오 회의에 대 한 사용자를 활성화 하면 기본적으로 회의 정보와 PIN이 포함 된 전자 메일이 전송 됩니다. PIN이 다시 설정 되 면 사용자에 게 설정 된 기본 SMTP 주소 (별칭)에 대 한 새 PIN이 사용자에 게 전자 메일에 전송 되는 경우 Microsoft 365 또는 Office 365 사서함이 있어야 합니다.
    
- 오디오 회의를 설정할 때 조직의 핀에 필요한 자릿수를 설정 합니다. Pin은 4 ~ 12 자리로 지정할 수 있으며 기본값은 5입니다. PIN 길이 설정을 변경 하면 새로 생성 된 핀에만 설정이 적용 되 고 오디오 회의에 사용 하도록 설정 된 기존 사용자의 PIN 설정에는 적용 되지 않습니다. [오디오 회의 모임에 대 한 PIN 길이 설정을](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)참조 하세요.
    
- 기본적으로 전자 메일은 사용자의 Microsoft 365 또는 Office 365 기본 SMTP 주소로 설정 됩니다. Microsoft 이외의 365 또는 Hotmail 또는 MSN 전자 메일 주소와 같은 비 Office 365 주소로 전자 메일을 보낼 수 있습니다. Windows PowerShell을 사용 하 여 기본 전자 메일 주소를 재정의할 수 있습니다. 이 기능은 사용자에 게 Microsoft 365 또는 Office 365의 Exchange 사서함이 없는 경우에 유용 합니다.

    

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.
  
## <a name="related-topics"></a>관련 항목

[사용자의 회의 ID 다시 설정](reset-a-conference-id-for-a-user-in-teams.md)
