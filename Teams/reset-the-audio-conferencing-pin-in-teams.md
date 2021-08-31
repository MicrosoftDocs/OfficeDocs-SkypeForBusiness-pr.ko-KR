---
title: 오디오 회의 PIN을 Microsoft Teams
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: 사용자의 오디오 회의 PIN을 다시 설정하는 방법을 Microsoft Teams PIN에 대한 중요한 사실을 알아보습니다.
ms.openlocfilehash: 206d625fdf656af5c4b30fdcc9f87dae760807cd
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58730097"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>오디오 회의 PIN을 Microsoft Teams

PIN은 오디오 회의를 사용하도록 설정된 각 사용자에 대해 Microsoft Teams 수로 만든 코드입니다. 오디오 회의 PI는 모임 이끌이가 모임 이끌이로 식별하고 전화를 통해 모임을 시작할 수 있도록 하는 데 사용됩니다. 사용자가 모임을 Microsoft Teams 앱을 사용하는 경우 PIN이 필요하지 않습니다. 사용자가 PIN을 잊어버려 오디오 회의를 사용하도록 설정한 경우 보낸 전자 메일에서 해당 PIN을 찾을 수 없는 경우 관리자가 PIN을 다시 설정할 수 있습니다.
  
모임은 인증된 사용자가 앱을 사용하여 Microsoft Teams 또는 이끌이가 휴대폰을 통해 자신의 PIN에 조인할 때 시작할 수 있습니다. 모임을 시작하려면 PIN이 필요한 경우 전화를 통해 참가하는 사용자는 로비에 배치됩니다. 이끌이가 이를 인정할 때까지 대기 중 음악을 들을 수 있습니다. 모임 이끌이가 전화를 통해 모임을 시작하는 데 PIN이 필요하지 않은 경우 발신자는 모임에 참가할 때 PIN을 제공해야 합니다.

## <a name="reset-a-users-pin"></a>사용자의 PIN 재설정

![로고가 Microsoft Teams 아이콘입니다.](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 편집을 **클릭합니다.**

3. 오디오 **회의에서** **PIN 재설정을 클릭합니다.**

4. 다시 **설정 을 클릭합니다.**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>사용자가 자신의 PIN을 다시 설정하도록 설정

1. 사용자가 으로 이동하도록 [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) 합니다.
2. PIN **재설정 을 클릭합니다.** 

> [!NOTE]
> GCCH의 경우 으로 https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing 이동합니다.

## <a name="what-else-should-you-know-about-pins"></a>PINS에 대해 알아야 할 다른 것은 무엇입니까?

- 보안을 위해 PIN은 PIN을 다시 설정하는 경우 관리자에게 한 번만 표시됩니다. 관리자가 PIN을 다시 설정하면 PIN이 *********로 나열됩니다.
    
- 사용자에게 자동으로 전자 메일을 보내는 것은 기본적으로 사용되며, 사용자가 오디오 회의를 사용하도록 설정하거나 PIN이 재설정될 때 해당 PIN이 있는 전자 메일을 받게 됩니다. 하지만 자동으로 전자 메일을 보내지 않도록 설정한 경우 PIN 재설정 전자 메일이 사용자에게 전송되지 않고 PIN 정보를 사용자에게 수동으로 보내야 합니다.
    
- 모임이 시작되면 이끌이는 로비의 모든 PSTN 사용자를 모임에 참가할 수 있도록 인정해야 합니다. 예를 들어 두 PSTN 참가자가 모임을 시작하기 전에 모임에 참가하려고 하면 대기 중이던 음악이 들리며, 모임 이끌이가 전화를 통해 PIN을 사용하여 조인하면 모임이 시작하고 이끌이가 모임 내 명령(*21 누르기)을 사용하여 로비에서 모든 PSTN 사용자를 인정할 수 있습니다.
    
- 기본 설정은 익명 호출자에 의해 모임을 시작하도록 허용하지 않는 것입니다.
    
- 오디오 회의에 사용자를 사용하도록 설정하면 기본적으로 회의 정보와 해당 PIN이 포함된 전자 메일이 전송됩니다. PIN을 다시 설정하면 새 PIN이 사용자에 대해 설정된 기본 SMTP 주소(별칭)에 전자 메일로 보내지기 때문에 사용자에게 Microsoft 365 Office 365 사서함이 있어야 합니다.
    
- 오디오 회의를 설정할 때 조직의 PI에 필요한 숫자를 설정합니다. PINS는 4~12자리일 수 있습니다. 기본값은 5입니다. PIN 길이 설정을 변경하는 경우 설정은 새로 생성된 PI에만 적용되고 오디오 회의에 사용하도록 설정된 기존 사용자의 PIN 설정에는 적용되지 않습니다. 오디오 회의 모임에 대한 PIN 길이 설정 을 [참조합니다.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)
    
- 기본적으로 전자 메일은 사용자의 기본 SMTP Microsoft 365 Office 365 설정됩니다. Hotmail 또는 MSN 전자 메일 주소와 같은 Microsoft 365 또는 Office 365 전자 메일을 보낼 수 있습니다. 기본 전자 메일 주소를 사용하여 기본 전자 메일 주소를 Windows PowerShell. 이 기능은 사용자에게 Exchange 사서함이 없는 Microsoft 365 Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell을 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.
  
## <a name="related-topics"></a>관련 항목

[사용자의 회의 ID 다시 설정](reset-a-conference-id-for-a-user-in-teams.md)
