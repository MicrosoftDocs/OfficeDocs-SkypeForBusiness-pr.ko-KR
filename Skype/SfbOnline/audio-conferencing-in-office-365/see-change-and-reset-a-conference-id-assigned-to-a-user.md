---
title: 온라인에서 사용자에게 할당된 회의 ID를 비즈니스용 Skype 변경 및 다시 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '온라인에서 사용자에게 회의 ID를 할당하는 비즈니스용 Skype 및 회의 ID 매개 변수를 지정하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: a400536050ea22d4f841e3b401e30c3c14729093
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728007"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>온라인에서 사용자에게 할당된 비즈니스용 Skype 다시 설정

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 의 사용자 회의 ID에 대한 자세한 Microsoft Teams 에서 사용자에게 할당된 회의 ID [보기 및 Microsoft Teams.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

회의 ID는 비즈니스용 Skype 또는 오디오 회의에서 오디오 회의를 설정하고 Microsoft를 오디오 회의 공급자로 Microsoft 365 Office 365 사용자에 자동으로 할당됩니다. 할당된 회의 ID는 모임이 예약될 때 모임 초대에 전송됩니다. 사용자가 예약하는 각 모임에 고유한 회의 ID가 할당됩니다.

회의 ID가 사용자에게 자동으로 만들어지지만 사용자가 이 ID를 사용하지 않을 때나 사용자가 회의 ID를 기억하지 못하거나 분실한 경우도 있을 수 있습니다. 관리자 센터  및 비즈니스용 Skype 사용하여 Windows PowerShell, 변경 및 재설정할 수 있습니다.

전화 회의 ID 및 기본 오디오 회의 전화 번호가 있는 사용자에게 전자 메일이 전송되거나, 전화 회의 ID를 다시 설정하면 전화 회의 ID가 포함되지만 PIN이 아닌 다른 전자 메일이 전송됩니다. 회의 이끌이의 PIN을 다시 설정하는 자세한 내용은 [여기를 클릭하세요.](reset-a-conference-id-for-a-user.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>회의 아이디 보기 및 재설정

### <a name="to-view-the-conference-id"></a>회의 ID를 보기 위해

![로고가 비즈니스용 Skype 아이콘입니다.](../images/sfb-logo-30x30.png) **관리 비즈니스용 Skype 사용**

해당 회의 ID를 보고 사용자에게 보낼 수 있습니다.

1. 직장 또는 학교 계정으로 로그인합니다.

2. 관리 센터 > **비즈니스용 Skype.**

3. 관리 **비즈니스용 Skype** 오디오 회의 >    >  **사용자에서** 회의 ID가 필요한 사용자를 선택합니다.

4. 작업 페이지에서 회의 **ID 를 참조하세요.**

    > [!TIP]
    > 사용자 페이지에서 사용자를 선택한 후 전자 메일 링크를 통해 회의 정보 보내기 링크를 클릭하여 회의  ID 및 오디오 전화 번호가 포함된 모든 회의 정보를 사용자에게 보낼 **수** 있습니다.

**Windows PowerShell**

사용자에 대한 Windows PowerShell ID를 볼 수 있습니다. 이렇게 하여 다음을 실행합니다.

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

cmdlet에 대한 자세한 내용은 [Get-CsOnlineDialInConferencingUser를](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) 참조합니다.


### <a name="to-reset-the-conference-id"></a>회의 ID를 다시 설정하는 경우

예를 들어 사용자가 잊어버렸다면 사용자에 대한 회의 ID를 다시 설정할 수 있습니다.

![로고가 비즈니스용 Skype 아이콘입니다.](../images/sfb-logo-30x30.png) **관리 비즈니스용 Skype 사용**

1. 직장 또는 학교 계정으로 로그인합니다.

2. 관리 센터 > **비즈니스용 Skype.**

3. 비즈니스용 Skype 관리 **센터** 오디오 회의 사용자 에서 회의 ID 아래의 작업 창에서 >    >  다시 **설정 을 클릭합니다.** 

4. 회의 **ID 재설정 창에서** 예 **를 클릭합니다.** 회의 ID가 자동으로 생성되고 새 회의 ID가 있는 사용자에게 전자 메일이 전송됩니다.

**Windows PowerShell**

사용자에 대한 회의 ID를 다시 설정할 수 Windows PowerShell. 이렇게 하여 다음을 실행합니다.

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>또 어떤 것을 알아야 하나요?

   > [!IMPORTANT]
   >  새 회의 ID를 만들거나 다시 설정한 후 이전 회의 ID를 호출자에서 사용할 수 없습니다. 새 회의 ID가 초대에 추가될 수 있도록 기존 모임 초대를 다시 계획할 수 있도록 사용자에게 알려야 합니다. 사용자는 모임 마이그레이션 도구를 사용하여 비즈니스용 Skype 업데이트할 수 있습니다. 도구를 다운로드, 설치 및 실행하는 방법을 참조하려면 다음을 참조하세요. 비즈니스용 Skype 및 [Lync에](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)대한 모임 업데이트 도구, 비즈니스용 Skype 온라인 모임 마이그레이션 [도구(64비트)](https://go.microsoft.com/fwlink/?LinkID=626047)및 모임 마이그레이션 도구(32비트)를 비즈니스용 Skype 온라인 모임 마이그레이션 [도구(32비트)를](https://www.microsoft.com/download/details.aspx?id=54079)참조하세요.

- cmdlet에 대한 자세한 내용은 [Set-CsOnlineDialInConferencingUser를](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) 참조합니다.

- 회의 ID는 오디오 회의 브리지에 설정된 숫자의 길이를 충족해야 합니다. 회의 신분증에는 사전 문자 또는 특수 문자를 사용할 수 없습니다. 숫자만 사용할 수 있습니다.

- 모든 오디오 회의 사용자의 회의 ID는 기본적으로 9자리가 며 숫자 수는 변경할 수 없습니다.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자와 함께 관리하는 방법을 알고 Windows PowerShell?

- 사용자 관리에 Windows PowerShell 사용자가 허용되거나 허용되지 않는 작업을 모두 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 있는 단일 관리 Microsoft 365 Office 365 비즈니스용 Skype 온라인에서 관리하거나 온라인을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.

  - [Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [PowerShell 또는 Microsoft 365 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell 많은 사용자에 대해 설정을 한 Microsoft 365 관리 센터 설정하는 경우와 같이 데이터만 사용하여 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 알아보습니다.

  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [온라인 Windows PowerShell 관리하기 위해 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [일반적인 Windows PowerShell 관리 작업을 수행하는 데 비즈니스용 Skype 사용](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>관련 항목

[오디오 회의를 시도하거나 Microsoft 365 또는 Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
