---
title: 비즈니스용 Skype Online에서 사용자에게 할당된 전화 회의 ID 보기, 변경 및 재설정
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '비즈니스용 Skype Online에서 사용자에게 전화 회의 ID를 할당하는 방법과 회의 ID 매개 변수에 대해 자세히 배워야 합니다. '
ms.openlocfilehash: a8f0e64ef30e1e503a1e3b78c9823f5d115df837
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46643608"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 사용자에게 할당된 전화 회의 ID 보기 및 다시 설정

> [!Note]
> Microsoft Teams의 사용자 회의 ID에 대한 자세한 내용은 Microsoft Teams에서 사용자에게 할당된 회의 ID 보기 및 재설정을 [참조하세요.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

Microsoft 365 또는 Office 365에서 오디오 회의를 설정하고 Microsoft를 오디오 회의 공급자로 사용할 때 비즈니스용 Skype 사용자에게 회의 ID가 자동으로 할당됩니다. 할당된 회의 ID는 모임이 예약될 때 모임 초대에 전송됩니다. 사용자가 예약하는 각 모임에는 고유한 회의 ID가 할당됩니다.

전화 회의 ID가 자동으로 만들어지며 사용자에게 할당되어도 사용자가 이 ID를 사용하지 못하고 특정 번호로 설정하거나 사용자가 전화 회의 ID를 기억하지 못하거나 분실한 경우도 있을 수 있습니다. 비즈니스용 **Skype** 관리 센터 및 Windows PowerShell ID를 보고, 변경하고, 재설정할 수 있습니다.

전화 회의 ID와 기본 오디오 회의 전화 번호가 포함된 전자 메일이 사용자에게 전송되거나 전화 회의 ID를 다시 설정하면 전화 회의 ID는 포함하지만 PIN은 포함하지 않는 다른 전자 메일이 전송됩니다. 회의 이끌이의 PIN을 다시 설정하는 자세한 내용은 [여기를 클릭하세요.](reset-a-conference-id-for-a-user.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>회의 ID 보기 및 재설정

### <a name="to-view-the-conference-id"></a>회의 ID를 보기 위해

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

자신의 회의 ID를 보고 사용자에게 보낼 수 있습니다.

1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 Skype의 > **관리 센터로 이동하세요.**

3. 비즈니스용 **Skype 관리 센터** 오디오 회의 사용자에서 전화 회의 >    >  ID가 필요한 사용자를 선택합니다.

4. 작업 페이지에서 회의 **ID를 살펴 봐야 합니다.**

    > [!TIP]
    > 사용자 페이지에서 사용자를 선택한 후 전자 메일 링크를 통해 전화 회의 정보 보내기 링크를 클릭하여  전화 회의 ID 및 오디오 전화 번호가 포함된 전자 메일로 사용자에게 모든 회의 정보를 보낼 수 있습니다. 

**다음 Windows PowerShell**

사용자에 대한 Windows PowerShell ID를 볼 수 있습니다. 이렇게 하여 다음을 실행합니다.

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

cmdlet에 대한 자세한 내용은 [Get-CsOnlineDialInConferencingUser를](https://go.microsoft.com/fwlink/?LinkId=617693 ) 참조합니다.


### <a name="to-reset-the-conference-id"></a>회의 ID를 다시 설정

예를 들어 사용자가 잊어버렸다면 사용자의 회의 ID를 다시 설정할 수 있습니다.

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 Skype의 > **관리 센터로 이동하세요.**

3. 비즈니스용 Skype 관리 **센터** 오디오 회의 사용자의 작업 창에서 전화 회의 ID 아래에 >    >   **있는**[다시 설정]을 **클릭합니다.**

4. 회의 **ID 재설정 창에서** **예를 클릭합니다.** 회의 ID가 자동으로 만들어지며 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다.

**다음 Windows PowerShell**

사용자에 대한 회의 ID는 다음을 사용하여 다시 설정할 Windows PowerShell. 이를 위해 다음을 실행합니다.

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>알아야 할 다른 것은 무엇입니까?

   > [!IMPORTANT]
   >  새 전화 회의 ID가 만들어지거나 다시 설정되면 발신자에 의해 이전 전화 회의 ID를 사용할 수 없습니다. 새 회의 ID가 초대에 추가될 수 있도록 사용자에게 기존 모임 초대를 다시 계획할지 알려야 합니다. 사용자는 비즈니스용 Skype 모임 마이그레이션 도구를 사용하여 기존 모임을 업데이트할 수 있습니다. 도구를 다운로드, 설치 및 실행하려면 비즈니스용 Skype 및 [Lync용](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)모임 업데이트 도구, 비즈니스용 Skype Online, 모임 마이그레이션 도구(64비트) 및 비즈니스용 Skype Online 모임 마이그레이션 [](https://go.microsoft.com/fwlink/?LinkID=626047) [도구(32비트)를](https://www.microsoft.com/download/details.aspx?id=54079)참조하세요.

- cmdlet에 대한 자세한 내용은 [Set-CsOnlineDialInConferencingUser를](https://go.microsoft.com/fwlink/?LinkId=617688 ) 참조합니다.

- 회의 ID는 오디오 회의 브리지에 설정된 자릿수 길이를 충족해야 합니다. 회의 신분증에는 사전 또는 특수 문자를 사용할 수 없습니다. 숫자만 사용할 수 있습니다.

- 모든 오디오 회의 사용자의 전화 회의 ID는 기본적으로 9자리로 설정되어 있으며, 자릿수는 변경할 수 없습니다.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?

- 이 경우 Windows PowerShell 관리에 대한 모든 것 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.

  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell Microsoft 365 관리 센터를 사용하는 경우와 같이 여러 사용자에 대해 한 번씩 설정을 변경하는 경우와 같이 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.

  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 시도 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

