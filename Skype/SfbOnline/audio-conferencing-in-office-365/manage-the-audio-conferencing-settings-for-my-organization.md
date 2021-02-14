---
title: 비즈니스용 Skype Online에서 조직에 대한 오디오 회의 설정 관리
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
description: '사용자 및 기타 여러 전화 접속 회의 설정에 전화 접속 회의 라이선스 및 전화 회의 ID를 할당하려면 비즈니스용 Skype Online 단계를 참조하세요. '
ms.openlocfilehash: aa8e9cbaf063ebf1780e3f8ce45b7bd54ced474f
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164147"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>비즈니스용 Skype Online에서 조직에 대한 오디오 회의 설정 관리

> [!NOTE]
> Teams에서 이러한 설정을 관리하려면 Microsoft Teams에서 조직에 대한 오디오 회의 설정 관리를 [참조하세요.](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams)

비즈니스용 Skype의 모든 오디오 회의 설정을 한 곳으로 쉽게 볼 수 있습니다.


## <a name="assign-an-audio-conferencing-license"></a>오디오 회의 라이선스 할당

> [!NOTE]
> 비즈니스용 Skype 관리 센터를 사용하여 라이선스를 **할당할 수 없습니다.** Microsoft 365 관리 센터를 사용해야 합니다. 비즈니스용 [Skype 라이선스 할당을 참조하세요.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)

 **사용자에 대한 라이선스를 할당합니다.**

1. 직장 또는 학교 계정으로 로그인합니다.

2. 관리 센터의 왼쪽 탐색 모음에서 **사용자** 활성 사용자로 이동한 다음 사용 가능한 사용자 목록에서 사용자 또는  >  사용자를 선택합니다.

    > [!NOTE]
    > 동시에 최대 20명까지 라이선스를 할당하는 경우 보기 선택 드롭다운을 사용하여 옵션 중 하나를 선택하거나 고유한 보기를 만들 수 있습니다.  그런 다음 **편집을 클릭하고** **다음을** 두 번 클릭한 다음 라이선스를 선택하고 제출을 **클릭합니다.** Windows Powershell을 사용하여 여러 사용자에게 라이선스를 할당할 수도 있습니다. 지침 및 샘플 PowerShell 스크립트는 비즈니스용 Skype 라이선스 [할당을 참조하세요.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)

3. 제품 라이선스 아래의 작업 창에서 편집을 **클릭합니다.**

4. 제품 **라이선스** 페이지에서 오디오 회의를 켜고 저장을 **클릭합니다.**  라이선스에 대한 자세한 내용은 비즈니스용 Skype 추가 [기능 라이선스를 참조하세요.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

> [!NOTE]
> 라이선스를 할당한 후 Microsoft는 처음에 목록에 오디오 회의 공급자로 나타나지 않을 수 있습니다. 이 경우 관리 센터에서 로그아웃하거나 Ctrl+F5를 눌러 브라우저 창을 새로 고치십시오.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>오디오 회의 사용자에게 전송된 전자 메일 사용 또는 사용 안 하도록 설정

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 **Skype의** 관리 > 왼쪽 탐색 모음에서 오디오 **회의를 클릭합니다.**

3. Microsoft **브리지 설정** 페이지에서 오디오 회의 설정이 변경되는 경우 사용자에게 자동으로 전자 메일 보내기를 선택하거나 선택 **취소합니다.**

4. **저장** 을 클릭합니다.

    사용자의 오디오 회의 속성으로 이동하고 전자 메일을 통해 전화 회의 정보 보내기를 클릭하여 오디오 회의 설정을 사용하여 사용자에게 전자 메일을 보낼 **수도 있습니다.** 전화 회의 ID 및 기본 오디오 회의 전화 번호는 모임 초대에 포함되지만 PIN은 포함되지 않습니다.

    오디오 회의 정보가 있는 사용자에게 전자 메일 [보내기를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**다음 Windows PowerShell**

- 또한 다음을 사용하여 Windows PowerShell 수 있습니다.

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    [Set-CsOnlineDialInConferencingTenantSettings를](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>사용자에게 전송된 전자 메일 메시지에서 보낸 사람 연락처 정보 변경

보낸 사람 연락처 정보의 실제 전자 메일 주소 및 표시 이름을 포함하여 사용자에게 자동으로 전송되는 전자 메일을 변경할 수 있습니다. 기본적으로 전자 메일의 보낸 사람이 Microsoft 365 또는 Office 365이지만 Windows PowerShell [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet을 사용하여 전자 메일 주소와 표시 이름을 변경할 수 있습니다. 사용자에게 전자 메일을 보내는 전자 메일 주소를 변경하려면 다음을 해야 합니다.

- _SendEmailFromAddress_ 매개 변수에 전자 메일 주소를 입력합니다.

- _SendEmailFromDisplayName_ 매개 변수에 전자 메일 표시 이름을 입력합니다.

- _SendEmailOverride_ 매개 변수를 _True로 설정_

다음을 실행하여 사용자에게 전송된 전자 메일(예: 전자 메일이 전송된 전자 메일 주소 또는 전자 메일의 표시 이름)을 변경할 수 있습니다.

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

전자 메일 주소 정보를 변경하려면 조직의 인바운드 전자 메일 정책에서 사용자 지정 전자 메일 주소에서 오는 전자 메일을 허용하는지 확인해야 합니다.

[Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet을 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.

오디오 회의 설정이 변경될 때 사용자에게 자동으로 전송되는 전자 메일을 [참조하세요.](emails-sent-to-users-when-their-settings-change.md)

## <a name="reset-the-meeting-conference-id"></a>모임 회의 ID 다시 설정

1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 Skype의 > **관리 센터로 이동하세요.**

3. 비즈니스용 **Skype** 관리 센터의 왼쪽 탐색 창에서 오디오 회의로 이동하고 회의 ID 아래의 작업 **창에서** 다시 설정을  **클릭합니다.**

4. 회의 **ID 재설정 창에서** **예를 클릭합니다.** 사용자에게 전자 메일을 보낼 수 있는 경우 회의 ID가 자동으로 생성되고 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다. 기본적으로 사용하도록 설정되어 있습니다.

    > [!IMPORTANT]
    >  새 전화 회의 ID가 생성되면 발신자에 의해 이전 전화 회의 ID를 사용할 수 없습니다. 새 회의 ID가 초대에 추가될 수 있도록 사용자에게 기존 모임 초대를 다시 계획할지 알려야 합니다. 사용자는 비즈니스용 Skype 모임 마이그레이션 도구를 사용하여 기존 모임을 업데이트할 수 있습니다. 비즈니스용 Skype 모임 업데이트 도구를 다운로드, 설치 및 실행하려면 비즈니스용 Skype 및 [Lync용](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)모임 업데이트 도구, 비즈니스용 Skype Online, 모임 마이그레이션 [도구(64비트)](https://go.microsoft.com/fwlink/?LinkID=626047)및 비즈니스용 Skype Online 모임 마이그레이션  [도구(32비트)를](https://www.microsoft.com/download/details.aspx?id=54079)참조하세요.

사용자의 [회의 ID 재설정을 참조합니다.](reset-a-conference-id-for-a-user.md)

## <a name="reset-a-conference-organizers-pin"></a>회의 이끌이의 PIN 다시 설정

사용자가 예약하는 각 모임에는 고유한 회의 ID가 할당됩니다. 전화 회의 ID가 자동으로 만들어지며 사용자에게 할당되어도 사용자가 이 ID를 사용하지 못하고 특정 번호로 설정하려는 경우 또는 사용자가 전화 회의 ID를 기억하지 못하거나 분실한 경우도 있습니다. 비즈니스용 Skype 관리 센터 및 Windows PowerShell ID를 보고, 변경하고, 재설정할 수 있습니다.


1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 **Skype의** 관리 > 왼쪽 탐색 모음에서 오디오 **회의를 클릭합니다.**

3. 사용자를 **클릭한** 다음 PIN을 다시 설정할 사용자를 선택합니다.

4. 작업 창의 PIN **아래에서** 재설정을 **클릭합니다.**

오디오 회의를 사용하도록 설정하거나 PIN이 다시 설정되면 사용자가 PIN이 있는 전자 메일을 받게 됩니다. 하지만 전자 메일 자동 전송을 사용하지 않도록 설정한 경우 PIN 재설정 전자 메일이 전송되지 않고 사용자에게 PIN을 수동으로 보내야 합니다. PIN은 다시 설정한 후에 한 번만 표시됩니다. 다시 설정 직후에 PIN이 표시되면 사용자 속성에 더 이상 표시되지 않습니다. 대신 *****가 표시됩니다.

오디오 [회의 PIN 재설정을 참조합니다.](reset-the-audio-conferencing-pin.md)

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>사용자에게 오디오 회의 정보가 있는 전자 메일 보내기

1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 **Skype의** 관리 > 왼쪽 탐색 모음에서 오디오 **회의를 클릭합니다.**

3. 사용자를 **클릭한** 다음 PIN을 다시 설정할 사용자를 선택합니다.

4. 작업 창에서 전자 메일을 통해 **전화 회의 정보 보내기 를 클릭합니다.**

    > [!NOTE]
    > 이렇게 하는 경우 오디오 회의 PIN이 사용자에게 전송되지 않습니다.

오디오 회의 정보가 있는 사용자에게 전자 메일 [보내기를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information.md)

## <a name="setting-the-phone-numbers-included-on-invites"></a>초대에 포함된 전화 번호 설정

1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 Skype의 > **관리 센터로 이동하세요.**

3. 왼쪽 탐색에서 오디오 회의 **사용자로**  >  **이동** 오디오 회의를 사용하도록 설정할 사용자를 선택합니다.

4. 작업 창에서 무료 번호를 설정하고 허용되는 경우 무료 번호를 설정할 **수 있습니다.** 

5. **저장** 을 클릭합니다.

초대에 [포함된 전화 번호](set-the-phone-numbers-included-on-invites.md)설정 참조


## <a name="choosing-audio-conferencing-bridge-settings"></a>오디오 회의 브리지 설정 선택

**발신자 모임에 참가할 때 모임 환경 설정**


1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 Skype의 > **관리 센터로 이동하세요.**

3. 비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의 Microsoft 브리지  >  **설정으로 이동합니다.**

4. 모임 **참가 환경 아래에서** 다음 작업을 선택합니다.

   - **모임 입장 및 퇴장 알림을** 사용하도록 설정 기본적으로 선택되어 있습니다. 이 확인란의 선택을 취소하면 기본적으로 모임에 이미 참가한 사용자는 모임에 입장하거나 퇴장할 때 알림을 들을 수 없습니다.

     이 설정은 사용자가 비즈니스용 Skype 앱을 사용하여 모임에 참가하고 모임의 Skype 모임  옵션 메뉴에서 사용자가 입장하거나 떠날 때 발표를 수정할 때 모임을 기준으로 설정할 수 있습니다. 

   - **발신자들에게** 모임에 참가하기 전에 이름을 기록해달라고 요청 기본적으로 선택되어 있습니다. 이 확인란의 선택을 취소하면 발신자는 모임에 참가하기 전에 이름을 기록할지 묻는 요청이 없습니다.

5. 변경한 후 저장을 **클릭합니다.**
    
오디오 회의 브리지의 설정 [변경을 참조하세요.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **모임의 PIN 길이 설정**

1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 Skype의 > **관리 센터로 이동하세요.**

3. 비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의 Microsoft 브리지  >  **설정으로 이동합니다.**

4. 보안 **아래에서** PIN 길이 목록에서 **PIN에** 사용할 자릿 수를 입력한 다음 저장을 **클릭합니다.**

    PIN은 4~12자리 사이입니다. 기본값은 5입니다.
    
오디오 회의 브리지의 설정 [변경을 참조하세요.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **오디오 사용자에게 전자 메일 보내기 사용 또는 사용 안 하도록 설정**

1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 **Skype의** 관리 > 왼쪽 탐색 모음에서 오디오 **회의를 클릭합니다.**

3. Microsoft **브리지 설정** 페이지에서 오디오 회의 설정이 변경되는 경우 사용자에게 자동으로 전자 메일 보내기를 선택하거나 선택 **취소합니다.**

4. **저장** 을 클릭합니다.

    사용자의 오디오 회의 속성으로 이동하고 전자 메일을 통해 전화 회의 정보 보내기를 클릭하여 오디오 회의 설정을 사용하여 사용자에게 전자 메일을 보낼 **수도 있습니다.**

    이렇게 하면 전화 회의 ID와 전화 회의 전화 번호만 포함된 전자 메일이 전송되지만 PIN은 포함되지 않습니다.

    오디오 회의 정보가 있는 사용자에게 전자 메일 [보내기를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information.md)

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>오디오 회의 브리지에서 기본(기본값) 및 보조(대체) 언어 보기 및 설정


1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 Skype의 > **관리 센터로 이동하세요.**

3. 비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의로 이동한 다음 Microsoft 브리지를 **클릭합니다.**

4. 목록에서 전화 번호를 선택하고 작업 창에서 언어 설정을 클릭한  다음 언어 설정 페이지에서 기본  언어 목록을 클릭하여 지원되는 언어의 전체 목록을 볼 수 있습니다. 

    오디오 회의 공급자로 Microsoft를 선택할 때 지원되는 기본 및 보조 언어를 설정할 수 있습니다. 목록에서 선택한 순서는 발신자에 언어를 표시하는 순서와 동일합니다.

오디오 [회의에 대한](set-auto-attendant-languages-for-audio-conferencing.md)자동 참석 언어 설정 참조

## <a name="see-audio-conferencing-dial-in-numbers"></a>오디오 회의 전화 접속 번호 보기

1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 Skype의 > **관리 센터로 이동하세요.**
 
3. 비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의 Microsoft  >  **브리지로 이동하세요.** 여기에서 다음을 할 수 있습니다.

   - 오디오 회의에 사용할 Microsoft 365 또는 Office 365에서 설정한 전화 번호를 볼 수 있습니다.

   - 오디오 회의 자동 연결에서 사용할 위치 및 기본 및 보조 언어를 볼 수 있습니다.

   - 오디오 회의를 사용하도록 설정하면 사용자에게 제공될 기본 전화 번호를 선택합니다. 그러나 오디오 회의 브리지의 기본 전화 번호가 변경되는 경우 기존 사용자의 기본 전화 번호는 변경되지 않습니다.

오디오 회의 사용자로 이동하여 사용자의 속성을 선택하여 조직에서 사용할 수 있는 번호 목록에서 새 번호를 선택하여 사용자의 기본 번호를 변경할  >   수 있습니다.

오디오 회의 번호 목록을 [참조하세요.](see-a-list-of-audio-conferencing-numbers.md)

## <a name="see-a-list-of-users-that-are-enabled"></a>사용하도록 설정된 사용자 목록 보기

1. 직장 또는 학교 계정으로 로그인합니다.

2. 비즈니스용 Skype의 > **관리 센터로 이동하세요.**

3. 비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 오디오 회의>  **사용자로 이동하세요.**

오디오 회의에 사용할 수 있는 사용자 목록을 [참조하세요.](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?

조직 수준에서 여러 설정을 사용하여 관리할 수 Windows PowerShell. 이렇게 하면 모든 사용자에게 설정을 쉽게 적용할 수 있습니다.

각 cmdlet에 대한 자세한 내용은 [비즈니스용 Skype Online cmdlet을 참조하세요.](https://go.microsoft.com/fwlink/?LinkId=627324)

다음은 조직 수준 설정입니다.

- **진입/종료 알림 설정** 기본값은 _$true._
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **이름 녹음/녹화 설정** 기본값은 _$true._
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **PIN 길이 설정** 기본값은 5입니다.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **휴대폰에서 전화 접속 모임만 설정** 기본 _$false._
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **사용자에게 전자 메일을 보낼지 여부 설정** 기본값은 _$true._
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **다른 계정에서 전자 메일을 보낼지 여부 설정** 기본값은 _$false._
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **사용자에게 전송된 전자** 메일에서 보낸 메일 주소 설정 기본값은 _$null._
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **사용자에게 전송된 전자 메일의 표시 이름 설정** 기본값은 _$null._
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>자세한 내용은 다음을 Windows PowerShell
- Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.

  - [Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell 많은 사용자에 대한 설정을 한 번 변경하는 경우와 같이 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.

  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=525038)

    비즈니스 Windows PowerShell용 Skype Online 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 [Skype Online용](https://go.microsoft.com/fwlink/?LinkId=294688) Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[사용자의 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-a-user.md)


