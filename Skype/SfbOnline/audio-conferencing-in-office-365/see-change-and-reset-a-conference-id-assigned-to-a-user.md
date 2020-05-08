---
title: 비즈니스용 Skype Online에서 사용자에 게 할당 된 전화 회의 ID 보기, 변경, 다시 설정
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
description: '비즈니스용 Skype Online에서 사용자에 게 전화 번호를 할당 하는 방법과 회의 id 매개 변수를 확인 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: caa94984b06ff73d8f14acf4727870a988298974
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163917"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 사용자에 게 할당 된 회의 ID 보기 및 재설정

> [!Note]
> Microsoft 팀의 사용자 회의 Id에 대 한 자세한 내용은 [Microsoft 팀에서 사용자에 게 할당 된 회의 Id 보기 및 재설정](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)을 참조 하세요.

Microsoft 365 또는 Office 365에서 오디오 회의를 위해 설정 되 고 Microsoft를 오디오 회의 공급자로 사용 하는 경우 비즈니스용 Skype 사용자에 게 자동으로 회의 ID가 할당 됩니다. 모임이 예정 되 면 모임 초대에 할당 된 전화 회의 ID가 전송 됩니다. 사용자가 예약 하는 각 모임에는 고유한 전화 번호를 할당 받게 됩니다.

전화 회의 ID는 사용자에 게 자동으로 만들어지고 할당 되지만, 사용자가이를 사용 하지 않고 특정 번호로 설정 하려는 경우 또는 사용자가 자신의 전화 회의 ID를 분실 하거나 손실 하지 않았을 때가 있을 수 있습니다. **비즈니스용 Skype 관리 센터** 및 Windows PowerShell을 사용 하 여 전화 회의 ID를 보고 변경 하 고 다시 설정할 수 있습니다.

전화 회의 ID와 기본 오디오 회의 전화 번호로 사용자에 게 전자 메일이 전송 되거나, 전화 회의 id를 다시 설정 하는 경우에는 전화 회의 ID만 포함 하 고 PIN이 아닌 다른 전자 메일을 보낼 수 있습니다. 회의 이끌이의 PIN을 다시 설정 하는 방법에 대 한 자세한 내용은 [여기](reset-a-conference-id-for-a-user.md)를 참조 하세요.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>회의 Id 보기 및 재설정

### <a name="to-view-the-conference-id"></a>전화 회의 ID를 보려면

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

자신의 전화 회의 ID를 보고 사용자에 게 보낼 수 있습니다.

1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype**> 관리 센터로 이동 합니다.

3. **비즈니스용 Skype 관리 센터**> 의**오디오 회의** > **사용자**의 경우, 전화 회의 ID를 필요로 하는 사용자를 선택 합니다.

4. 작업 페이지에서 **전화 회의 ID**를 확인 합니다.

    > [!TIP]
    > **사용자 페이지에서** 사용자를 선택한 후 **전자 메일을 통해 전화 회의 정보 보내기** 링크를 클릭 하 여 전화 회의 ID 및 오디오 전화 번호가 포함 된 전자 메일에서 모든 회의 정보를 사용자에 게 보낼 수 있습니다.

**Windows PowerShell 사용**

Windows PowerShell을 사용 하 여 사용자의 전화 회의 ID를 볼 수 있습니다. 이렇게 하려면 다음을 실행 합니다.

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Cmdlet에 대해 자세히 알아보려면 [get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617693 ) 를 참조 하세요.


### <a name="to-reset-the-conference-id"></a>전화 회의 ID를 다시 설정 하려면

예를 들어 사용자가 잊어버린 경우 전화 회의 ID를 다시 설정할 수 있습니다.

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype**> 관리 센터로 이동 합니다.

3. **비즈니스용 Skype 관리 센터**> **오디오 회의** > **사용자**의 작업 창에 있는 **전화 회의 ID**아래에서 **원래 대로**를 클릭 합니다.

4. **전화 회의 ID 다시 설정** 창에서 **예**를 클릭 합니다. 전화 회의 ID가 자동으로 만들어지고 새 전화 회의 ID를 사용 하 여 사용자에 게 전자 메일이 전송 됩니다.

**Windows PowerShell 사용**

Windows PowerShell을 사용 하 여 사용자의 전화 회의 ID를 다시 설정할 수 있습니다. 이 작업을 수행 하려면 다음을 실행 합니다.

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>알아야 할 기타 사항

   > [!IMPORTANT]
   >  새 전화 회의 ID가 만들어지거나 하나는 다시 설정 된 후에는 발신자가 이전 전화 회의 ID를 사용할 수 없습니다. 사용자에 게 기존 모임 초대를 다시 예약 하 여 새 회의 ID가 초대에 추가 되었는지 알려 주어 야 합니다. 사용자는 비즈니스용 Skype 모임 마이그레이션 도구를 사용 하 여 기존 모임을 업데이트할 수 있습니다. 도구를 다운로드 하 고 설치 하 고 실행 하는 방법에 대 한 자세한 내용은 비즈니스용 [skype 및 Lync 용 모임 업데이트 도구](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), 비즈니스용 [Skype Online, 모임 마이그레이션 도구 (64 비트)](https://go.microsoft.com/fwlink/?LinkID=626047), 비즈니스용 [Skype online, 모임 마이그레이션 도구 (32 비트)](https://www.microsoft.com/download/details.aspx?id=54079)를 참조 하세요.

- Cmdlet에 대해 자세히 알아보려면 [Set-get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 을 참조 하세요.

- 전화 회의 ID는 오디오 회의 브리지에 설정 된 길이의 자릿수를 충족 해야 합니다. 전화 회의 Id에는 영문자 또는 특수 문자를 사용할 수 없습니다. 숫자만 사용할 수 있습니다.

- 모든 오디오 회의 사용자의 전화 회의 ID는 기본적으로 7 자리로 표시 되며 자릿수는 변경할 수 없습니다.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

- Windows PowerShell이 제공 되는 경우 사용자 및 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.

  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Microsoft 365 또는 Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.

  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>관련 항목

[Microsoft 365 또는 Office 365에서 오디오 회의 체험 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

