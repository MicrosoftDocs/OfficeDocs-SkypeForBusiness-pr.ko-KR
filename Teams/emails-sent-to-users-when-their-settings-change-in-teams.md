---
title: 설정이 변경되면 사용자에게 전송되는 전자 메일
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Microsoft 팀에서 전화 접속 회의 설정이 변경 되는 경우 전자 메일을 통해 사용자에 게 자동으로 전송 되는 정보에 대해 알아봅니다. '
ms.openlocfilehash: ada608da12791a586d3adcbfd6477c1f26f7e30d
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141261"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Microsoft 팀에서 설정이 변경 될 때 사용자에 게 전송 되는 전자 메일

전자 메일은 오디오 회의 공급자로 Microsoft를 사용 하 여 [오디오 회의를 사용 하도록 설정](set-up-audio-conferencing-in-teams.md) 된 사용자에 게 자동으로 전송 됩니다.

기본적으로 오디오 회의를 사용 하도록 설정 된 사용자에 게 전송 되는 전자 메일에는 네 가지 유형이 있습니다. 그러나 사용자에 게 전송 되는 전자 메일의 수를 제한 하려는 경우이 기능을 해제할 수 있습니다. Office 365의 오디오 회의는 다음과 같은 경우 사용자의 전자 메일에 전자 메일을 보냅니다.

- **오디오 회의 라이선스가 자신에 게 할당 되거나 오디오 회의 공급자를 Microsoft로 변경 하는 경우**

     이 전자 메일에는 전화 회의 ID, 모임에 대 한 기본 컨퍼런스 전화 번호, 사용자 용 오디오 회의 PIN, 지침 및 링크를 사용 하 여 사용자의 기존 모임을 업데이트 하는 데 사용 되는 비즈니스용 Skype Online 모임 업데이트 도구를 사용할 수 있습니다. [Microsoft 팀 라이선스 할당](assign-teams-licenses.md) 또는 [microsoft를 오디오 회의 공급자로 지정을](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)참조 하세요.

    > [!NOTE]
    > 조직에서 동적 전화 회의 Id를 사용할 수 있는 경우, 자신이 예약한 모든 사용자의 모임에 고유한 전화 회의 Id가 포함 됩니다. [조직에서 오디오 회의 동적 id](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user)를 설정할 수 있습니다. 

    다음은이 전자 메일의 예입니다.

     ![비즈니스용 Skype 라이선스 확인](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    라이선스에 대해 자세히 알아보려면 [Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.

- **사용자의 전화 회의 ID 또는 기본 컨퍼런스 전화 번호가 변경 되었습니다.**

    이 전자 메일에는 전화 회의 ID, 기본 컨퍼런스 전화 번호, 사용자의 기존 모임을 업데이트 하는 데 사용 되는 비즈니스용 Skype Online 모임 업데이트 도구를 사용 하는 지침 및 링크가 포함 되어 있습니다. 그러나이 전자 메일에는 사용자의 오디오 회의 PIN이 포함 되어 있지 않습니다. [사용자의 전화 회의 ID 다시 설정을](reset-a-conference-id-for-a-user-in-teams.md)참조 하세요.

    다음은이 전자 메일의 예입니다.

     ![전화 접속 회의 정보가 변경 되었습니다.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **사용자의 오디오 회의 PIN이 다시 설정 됩니다.**

    이 전자 메일에는 이끌이의 오디오 회의 PIN, 기존 회의 ID 및 사용자의 기본 컨퍼런스 전화 번호가 포함 됩니다. [오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin-in-teams.md)참조 하세요.
    
     다음은이 전자 메일의 예입니다.
    
     ![전화 접속 회의 PIN이 변경 되었습니다.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **사용자의 라이선스가 제거 되거나 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 없음으로 변경 됩니다.**

    오디오 **회의** 라이선스가 사용자에서 제거 되거나 오디오 회의 공급자를 **없음**으로 설정할 때이 문제가 발생 합니다.

    [비즈니스용 Office 365에 대 한 라이선스 할당 또는 제거를](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)참조 하세요.

    다음은이 전자 메일의 예입니다.

     ![전화 접속 회의 기능이 꺼져 있습니다.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>자신에 게 전송 되는 전자 메일 메시지 변경 하기

사용자에 게 자동으로 전송 되는 전자 메일을 변경할 수 있습니다. 기본적으로 전자 메일을 보낸 사람은 Office 365에 있지만, Windows PowerShell을 사용 하 여 표시 이름을 변경할 수 있습니다. 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>전자 메일을 보낼 수 없도록 하려면 어떻게 하나요?

사용자에 게 전자 메일 보내기를 사용 하지 않도록 설정 하면 사용자에 게 라이선스가 할당 되지 않은 경우에도 전자 메일이 전송 되지 않습니다. 이 경우 전화 회의 ID, 기본 회의 전화 번호, 그리고 더 중요 한 것은 사용자에 게 오디오 회의 PIN이 전송 되지 않습니다. 이런 경우에는 별도의 전자 메일을 보내거나 전화를 걸어 사용자에 게 알려야 합니다.

기본적으로 전자 메일은 사용자에 게 전송 되지만 오디오 회의에 대 한 전자 메일을 받지 않도록 하려면 Microsoft 팀 또는 Windows PowerShell을 사용할 수 있습니다. 

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지로**이동 합니다. 

2. **회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다. 

3. **브리지 설정** 창에서 **전화 접속 설정이 변경 되는 경우 자동으로 사용자에 게 전자 메일 보내기**사용 또는 사용 안 함을 설정 하거나 해제 합니다.

4. **저장**을 클릭합니다.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Windows PowerShell 사용**

자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.


## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

기본적으로 전자 메일을 보낸 사람은 Office 365에 있지만, Windows PowerShell을 사용 하 여 전자 메일 주소와 표시 이름을 변경할 수 있습니다. 

Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.

  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)

Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.


## <a name="related-topics"></a>관련 항목

[오디오 회의 설정이 변경되면 전자 메일 보내기 사용 또는 사용 안 함](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
