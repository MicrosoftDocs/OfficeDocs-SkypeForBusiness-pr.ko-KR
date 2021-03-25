---
title: Microsoft Teams에서 오디오 회의 PIN 재설정
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
description: Microsoft Teams에서 사용자의 오디오 회의 PIN을 다시 설정하고 PIN에 대한 중요한 사실을 알아보는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 7ea380fbeb722337eaec598823b12dbe18f49918
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117636"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Microsoft Teams에서 오디오 회의 PIN 재설정

PIN은 오디오 회의를 사용하도록 설정된 각 Microsoft Teams 사용자에 대해 생성된 숫자로 만들어진 코드입니다. 오디오 회의 PI는 모임 이끌이가 모임 이끌이로 식별하고 전화를 통해 모임을 시작할 수 있도록 하는 데 사용됩니다. Microsoft Teams 앱을 사용하여 모임을 시작하는 경우 PIN이 필요하지 않습니다. 사용자가 PIN을 잊어버려 오디오 회의를 사용하도록 설정한 경우 보낸 전자 메일에서 해당 PIN을 찾을 수 없는 경우 관리자가 PIN을 다시 설정할 수 있습니다.
  
Microsoft Teams 앱을 사용하여 인증된 사용자가 조인하거나 이끌이가 휴대폰을 통해 PIN에 조인할 때 모임을 시작할 수 있습니다. 모임을 시작하려면 PIN이 필요한 경우 전화를 통해 참가하는 사용자는 로비에 배치됩니다. 모임이 시작될 때까지 음악이 대기 중입니다. 모임 이끌이가 전화를 통해 모임을 시작하는 데 PIN이 필요하지 않은 경우 발신자는 모임에 참가할 때 PIN을 제공해야 합니다.

## <a name="reset-a-users-pin"></a>사용자의 PIN 재설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

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
    
- 모임이 시작되면 로비의 모든 사용자가 자동으로 참가합니다. 예를 들어 두 참가자가 모임을 시작하기 전에 모임에 참가하려고 하면 로비에 배치되고 대기 중이던 음악을 듣게 되고 모임 이끌이가 전화를 통해 PIN을 사용하여 참가하면 모임이 시작되고 로비의 참가자가 모임에 참가합니다.
    
- 기본 설정은 익명 호출자에 의해 모임을 시작하도록 허용하지 않는 것입니다.
    
- 오디오 회의에 사용자를 사용하도록 설정하면 기본적으로 회의 정보와 해당 PIN이 포함된 전자 메일이 전송됩니다. 사용자가 Microsoft 365 또는 Office 365 사서함이 있어야 합니다. 이 경우 PIN이 다시 설정되면 사용자에게 설정된 기본 SMTP 주소(별칭)로 새 PIN이 전자 메일로 사용자에게 전송됩니다.
    
- 오디오 회의를 설정할 때 조직의 PI에 필요한 숫자를 설정합니다. PINS는 4~12자리일 수 있습니다. 기본값은 5입니다. PIN 길이 설정을 변경하는 경우 설정은 새로 생성된 PI에만 적용되고 오디오 회의에 사용하도록 설정된 기존 사용자의 PIN 설정에는 적용되지 않습니다. 오디오 회의 모임에 대한 PIN 길이 설정 을 [참조합니다.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)
    
- 기본적으로 전자 메일은 사용자의 Microsoft 365 또는 Office 365 기본 SMTP 주소로 설정됩니다. Microsoft 365가 아닌 주소 또는 Office 365가 아닌 주소(예: Hotmail 또는 MSN 전자 메일 주소)로 전자 메일을 보낼 수 있습니다. 기본 전자 메일 주소를 사용하여 다시 Windows PowerShell. 사용자에게 Microsoft 365 또는 Office 365에 Exchange 사서함이 없는 경우 유용합니다.

    

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
자세한 내용은 Windows PowerShell [Microsoft Teams PowerShell 참조를](/powershell/module/teams/?view=teams-ps) 참조하세요.
  
## <a name="related-topics"></a>관련 항목

[사용자의 회의 ID 다시 설정](reset-a-conference-id-for-a-user-in-teams.md)