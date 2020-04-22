---
title: 비즈니스용 Skype Online에서 조직의 오디오 회의 설정 관리
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: '전화 접속 회의 라이선스 및 전화 회의 ID를 사용자와 여러 다른 전화 접속 회의 설정에 할당 하려면 비즈니스용 Skype Online 단계를 참조 하세요. '
ms.openlocfilehash: 9567c8234c0ef7a5b65c5894666747eab3cff7a5
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777983"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 조직의 오디오 회의 설정 관리

> [!NOTE]
> 팀에서 이러한 설정을 관리 하려면 [Microsoft 팀에서 내 조직의 오디오 회의 설정 관리](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams)를 참조 하세요.

한 곳에서 비즈니스용 Skype에 대 한 오디오 회의 설정을 모두 확인 하는 것이 더 쉬울 수 있습니다.


## <a name="assign-an-audio-conferencing-license"></a>오디오 회의 라이선스 할당

> [!NOTE]
> **비즈니스용 Skype 관리 센터**를 사용 하 여 라이선스를 할당할 수 없습니다. Microsoft 365 관리 센터를 사용 해야 합니다. [비즈니스용 Skype 라이선스 할당](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)을 참조 하세요.

 **사용자에 게 라이선스를 할당 하려면**

1. 회사 또는 학교 계정으로 로그인 합니다.

2. 관리 센터의 왼쪽 탐색 창에서 **사용자** > **활성 사용자**로 이동한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

    > [!NOTE]
    > 동시에 최대 20 명의 사용자에 게 라이선스를 할당 하는 경우 **보기 선택** 드롭다운을 사용 하 여 해당 옵션 중 하나를 선택 하거나 고유한 보기를 만들 수 있습니다. 그런 다음 **편집**을 클릭 하 고 두 **번 다음 라이선스** 를 선택 하 고 **제출을**클릭 합니다. Windows Powershell을 사용 하 여 여러 사용자에 게 라이선스를 할당할 수도 있습니다. 지침 및 샘플 PowerShell 스크립트는 [비즈니스용 Skype 라이선스 할당](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)을 참조 하세요.

3. 작업 창의 **제품 라이선스**에서 **편집**을 클릭 합니다.

4. **제품 라이선스** 페이지에서 **오디오 회의** 를 켠 다음 **저장**을 클릭 합니다. 라이선스에 대 한 자세한 내용은 [비즈니스용 Skype 추가 기능 라이선스](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)를 참조 하세요.

> [!NOTE]
> 라이선스를 할당 한 후에는 Microsoft에서 처음에 오디오 회의 공급자로 목록에 표시 되지 않을 수 있습니다. 이 문제가 발생 하면 관리 센터에서 로그 아웃 하거나 CTRL + F5를 눌러 브라우저 창을 새로 고칩니다.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>오디오 회의 사용자에 게 전송 되는 전자 메일 사용 또는 사용 안 함

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype** > 관리 센터로 이동 하 여 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.

3. **Microsoft 브리지 설정** 페이지에서 **오디오 회의 설정이 변경 된 경우 사용자에 게 자동으로 전자 메일 보내기**를 선택 하거나 선택을 취소 합니다.

4. **저장**을 클릭합니다.

    사용자의 오디오 회의 속성으로 이동한 다음 **전자 메일로 회의 정보 보내기를**클릭 하 여 오디오 회의 설정으로 사용자에 게 전자 메일을 보낼 수도 있습니다. 전화 회의 ID 및 기본 오디오 회의 전화 번호가 모임 초대에 포함 되지만 PIN이 아닙니다.

    [오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information.md)참조 하세요.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Windows PowerShell 사용**

- Windows PowerShell을 사용 하 여 다음을 실행할 수도 있습니다.

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    [Set-사용](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) 를 사용 하 여 전자 메일을 포함 한 조직의 기타 설정을 관리할 수 있습니다.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>사용자에 게 전송 되는 전자 메일 메시지의 보낸 사람 연락처 정보 변경

실제 전자 메일 주소와 보낸 사람 연락처 정보의 표시 이름을 포함 하 여 사용자에 게 자동으로 전송 되는 전자 메일을 변경할 수 있습니다. 기본적으로 전자 메일을 보낸 사람은 Office 365 이지만, Windows PowerShell 및 [사용](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet을 사용 하 여 전자 메일 주소와 표시 이름을 변경할 수 있습니다. 사용자에 게 전자 메일을 보내는 전자 메일 주소를 변경 하려면 다음을 수행 해야 합니다.

- _SendEmailFromAddress_ 매개 변수에 전자 메일 주소를 입력 합니다.

- 이 매개 변수에 전자 메일 표시 이름을 _입력 합니다._

- "= _" 매개 변수를_ _True_로 설정 합니다.

전자 메일을 보낸 전자 메일 주소 또는 다음을 실행 하 여 전자 메일의 표시 이름 등 사용자에 게 전송 되는 전자 메일을 변경할 수 있습니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

전자 메일 주소 정보를 변경 하려는 경우 조직의 인바운드 전자 메일 정책에서 사용자 지정 전자 메일 주소에 있는 전자 메일을 허용 하는지 확인 해야 합니다.

[Set-사용](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet을 사용 하 여 전자 메일을 비롯 한 조직의 다른 설정을 관리할 수 있습니다.

[오디오 회의 설정이 변경 되 면 사용자에 게 자동으로 전송 되는 전자 메일](emails-sent-to-users-when-their-settings-change.md)을 볼 수 있습니다.

## <a name="reset-the-meeting-conference-id"></a>모임 전화 회의 ID 다시 설정

1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype**> 관리 센터로 이동 합니다.

3. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의**로 이동한 다음, 작업 창의 **전화 회의 ID**에서 **원래 대로**를 클릭 합니다.

4. **전화 회의 ID 다시 설정** 창에서 **예**를 클릭 합니다. 사용자에 게 전자 메일을 보내는 경우 전화 회의 ID가 자동으로 만들어지고 새 전화 회의 ID를 사용 하 여 사용자에 게 전자 메일이 전송 됩니다. 기본적으로 사용 하도록 설정 되어 있습니다.

    > [!IMPORTANT]
    >  새 전화 회의 ID를 만든 후에는 발신자가 이전 회의 ID를 사용할 수 없습니다. 사용자에 게 기존 모임 초대를 다시 예약 하 여 새 회의 ID가 초대에 추가 되었는지 알려 주어 야 합니다. 사용자는 비즈니스용 Skype 모임 마이그레이션 도구를 사용 하 여 기존 모임을 업데이트할 수 있습니다. 비즈니스용 skype 모임 업데이트 도구를 다운로드 하 고 설치 하 고 실행 하는 방법에 대 한 자세한 내용은 비즈니스용 [skype 및 Lync 용 모임 업데이트 도구](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), 비즈니스용 [Skype Online, 모임 마이그레이션 도구 (64 비트)](https://go.microsoft.com/fwlink/?LinkID=626047), 비즈니스용 [Skype online, 모임 마이그레이션 도구 (32 비트)](https://www.microsoft.com/download/details.aspx?id=54079)를 참조 하세요.

[사용자의 전화 회의 ID 다시 설정을](reset-a-conference-id-for-a-user.md)참조 하세요.

## <a name="reset-a-conference-organizers-pin"></a>회의 이끌이의 PIN 다시 설정

사용자가 예약 하는 각 모임에는 고유한 전화 번호를 할당 받게 됩니다. 전화 회의 ID는 자동으로 만들어지고 사용자에 게 할당 되지만, 사용자가이를 사용 하지 않고 특정 번호로 설정 하려는 경우 또는 사용자가 자신의 전화 회의 ID를 분실 하거나 잃어 버릴 수도 있습니다. 비즈니스용 Skype 관리 센터 및 Windows PowerShell을 사용 하 여 전화 회의 ID를 보고 변경 하 고 다시 설정할 수 있습니다.


1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype** > 관리 센터로 이동 하 여 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.

3. **사용자**를 클릭 한 다음 PIN을 다시 설정 하려는 사용자를 선택 합니다.

4. 작업 창의 **핀**에서 **원래 대로**를 클릭 합니다.

사용자가 오디오 회의를 사용 하도록 설정 하거나 PIN을 다시 설정한 경우 PIN이 포함 된 전자 메일을 받게 됩니다. 그러나 자동으로 전자 메일 보내기를 사용 하지 않도록 설정한 경우 PIN 다시 설정 전자 메일을 보내지 않으며 사용자에 게 수동으로 PIN을 보내야 합니다. PIN은 다시 설정 된 후에만 표시 됩니다. 다시 설정 된 후에 표시 된 후에는 사용자 속성에 더 이상 PIN이 표시 되지 않습니다. 대신 * * * * *가 표시 됩니다.

[오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin.md)참조 하세요.

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기

1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype** > 관리 센터로 이동 하 여 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.

3. **사용자**를 클릭 한 다음 PIN을 다시 설정 하려는 사용자를 선택 합니다.

4. 작업 창에서 **전자 메일을 통해 회의 정보 보내기를**클릭 합니다.

    > [!NOTE]
    > 이렇게 하면 오디오 회의 PIN이 사용자에 게 전송 되지 않습니다.

[오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information.md)참조 하세요.

## <a name="setting-the-phone-numbers-included-on-invites"></a>초대에 포함 된 전화 번호 설정

1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype**> 관리 센터로 이동 합니다.

3. 왼쪽 탐색 창에서 **오디오 회의** > **사용자**로 이동 합니다. 오디오 회의에 사용할 사용자를 선택 합니다.

4. 작업 창에서 **유료** 번호를 설정 하 고, 허용 되는 경우 무료 **번호**를 설정할 수 있습니다.

5. **저장**을 클릭합니다.

[초대에 포함 된 전화 번호 설정을](set-the-phone-numbers-included-on-invites.md)참조 하세요.


## <a name="choosing-audio-conferencing-bridge-settings"></a>오디오 회의 브리지 설정 선택

**발신자가 모임에 참가 하는 경우의 모임 환경 설정**


1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype**> 관리 센터로 이동 합니다.

3. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.

4. **모임 참가 환경**에서 다음 작업을 선택 합니다.

   - **모임 입력 및 종료 알림이 설정 되도록 설정** 이 옵션이 기본적으로 선택 되어 있습니다. 이 확인란의 선택을 취소 하면 이미 모임에 참가 한 사용자는 다른 사용자가 모임을 시작 하거나 떠날 때 알림을 받을 수 없습니다.

     이는 사용자가 비즈니스용 Skype 앱을 사용 하 여 모임에 참가 하는 경우 모임 별로 설정할 수 있으며, 모임의 Skype 모임 **옵션** 메뉴에 사용자 **가 입력 하거나 탈퇴할 때의 알림** 설정을 수정 합니다.

   - **모임에 참가 하기 전에 호출자에 게 자신의 이름을 기록 하도록 요청** 이 옵션이 기본적으로 선택 되어 있습니다. 이 확인란의 선택을 취소 하면 호출자가 모임에 참가 하기 전에 자신의 이름을 기록해 야 합니다.

5. 변경 작업을 수행한 후 **저장**을 클릭 합니다.
    
[오디오 회의 브리지에 대 한 설정 변경을](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)참조 하세요.
  
 **모임의 PIN 길이 설정**

1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype**> 관리 센터로 이동 합니다.

3. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.

4. **보안**에서 **pin 길이** 목록에 원하는 pin의 자릿수를 입력 한 다음 **저장**을 클릭 합니다.

    PIN은 4 ~ 12 자리 여야 합니다. 기본값은 5입니다.
    
[오디오 회의 브리지에 대 한 설정 변경을](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)참조 하세요.
  
 **오디오 사용자에 게 전자 메일을 보낼 수 있도록 설정 또는 해제**

1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype** > 관리 센터로 이동 하 여 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.

3. **Microsoft 브리지 설정** 페이지에서 **오디오 회의 설정이 변경 된 경우 사용자에 게 자동으로 전자 메일 보내기**를 선택 하거나 선택을 취소 합니다.

4. **저장**을 클릭합니다.

    사용자의 오디오 회의 속성으로 이동한 다음 **전자 메일로 회의 정보 보내기를**클릭 하 여 오디오 회의 설정을 사용 하 여 사용자에 게 전자 메일을 보낼 수도 있습니다.

    이렇게 하면 전화 회의 ID 및 전화 회의 전화 번호만 포함 된 전자 메일이 전송 되지만 PIN은 포함 되지 않습니다.

    [오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information.md)참조 하세요.

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>오디오 회의 브리지의 기본 (기본) 및 보조 (대체) 언어를 표시 하 고 설정 합니다.


1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype**> 관리 센터로 이동 합니다.

3. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의**로 이동한 다음 **Microsoft bridge**를 클릭 합니다.

4. 목록에서 전화 번호를 선택 하 고, 작업 창에서 **언어 설정을** 클릭 한 다음 **언어 설정** 페이지에서 **기본 언어** 목록 사용을 클릭 하 여 지원 되는 언어의 전체 목록을 봅니다.

    Microsoft를 오디오 회의 공급자로 선택 하는 경우 지원 되는 기본 및 보조 언어를 설정할 수도 있습니다. 목록에서 선택 하는 순서는 호출자에 게 표시 되는 언어의 순서와 동일 합니다.

[오디오 회의에 대 한 자동 전화 교환 언어 설정을](set-auto-attendant-languages-for-audio-conferencing.md)참조 하세요.

## <a name="see-audio-conferencing-dial-in-numbers"></a>오디오 회의 전화 접속 번호 보기

1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype**> 관리 센터로 이동 합니다.

3. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge**로 이동 합니다. 다음과 같은 작업을 수행할 수 있습니다.

   - 오디오 회의에 사용 하도록 Office 365에서 설정한 전화 번호를 확인 합니다.

   - 오디오 회의 자동 전화 교환에 사용 되는 위치와 기본 및 보조 언어를 확인 합니다.

   - 오디오 회의를 사용 하도록 설정 된 사용자에 게 제공 되는 기본 전화 번호를 선택 합니다. 그러나 오디오 회의 브리지의 기본 전화 번호가 변경 되는 경우 기존 사용자의 기본 전화 번호가 변경 되지 않습니다.

**오디오 회의** > **사용자** 로 이동 하 여 사용자의 속성을 선택 하 여 조직에서 사용할 수 있는 숫자 목록에서 새 번호를 선택 하 여 사용자의 기본 번호를 변경할 수 있습니다.

[오디오 회의 번호 목록 보기를](see-a-list-of-audio-conferencing-numbers.md)참조 하세요.

## <a name="see-a-list-of-users-that-are-enabled"></a>사용 하도록 설정 된 사용자 목록 보기

1. 회사 또는 학교 계정으로 로그인 합니다.

2. **비즈니스용 Skype**> 관리 센터로 이동 합니다.

3. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의**>으로 이동한 다음 **사용자**를 클릭 합니다.

[오디오 회의를 사용 하도록 설정 된 사용자 목록 보기를](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)참조 하세요.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

Windows PowerShell을 사용 하 여 조직 수준에서 관리할 수 있는 몇 가지 설정이 있습니다. 이렇게 하면 모든 사용자에 게 설정을 쉽게 적용할 수 있습니다.

각 cmdlet에 대 한 자세한 도움말을 보려면 [비즈니스용 Skype Online cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324)을 참조 하세요.

조직 수준 설정은 다음과 같습니다.

- **입력/종료 알림 설정** 기본값은 _$true_입니다.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **이름 기록 설정** 기본값은 _$true_입니다.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **PIN 길이 설정** 기본값은 5입니다.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **휴대폰에서 전화 접속 모임만 설정** 기본 _$false_입니다.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **사용자에 게 전자 메일을 보낼지 여부 설정** 기본값은 _$true_입니다.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **다른 계정에서 전자 메일을 보낼지 여부 설정** 기본값은 _$false_입니다.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **사용자에 게 전송 되는 전자 메일의 보낸 사람 주소 설정** 기본값은 _$null_입니다.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **사용자에 게 전송 되는 전자 메일의 표시 이름 설정** 기본값은 _$null_입니다.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대해 자세히 알고 싶은 경우
- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.

  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell에는 한 번에 여러 사용자에 게 설정을 변경 하는 경우와 같이 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등의 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.

  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)

    비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[사용자의 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-a-user.md)


