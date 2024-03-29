---
title: 오디오 회의 설정 관리
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
- seo-marvel-mar2020
description: 사용자 및 기타 여러 전화 접속 회의 설정에 전화 접속 회의 라이선스 및 회의 ID를 할당하려면 Microsoft Teams 단계를 참조하세요.
ms.openlocfilehash: 4bfb813b6e7b472ad7a9ab58e6403b92f60fd039
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271223"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Microsoft Teams에서 조직의 오디오 회의 설정 관리

Microsoft Teams에 대한 모든 오디오 회의 설정을 한 곳에서 보는 것이 더 쉬울 수 있습니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="assign-an-audio-conferencing-license"></a>오디오 회의 라이선스 할당

> [!NOTE]
> Teams를 사용하여 라이선스를 할당할 수 없습니다. Microsoft 365 관리 센터 사용해야 합니다. [Microsoft Teams 추가 기능 라이선스 할당을 참조하세요](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

### <a name="to-assign-a-license-for-a-user"></a>사용자에 대한 라이선스를 할당하려면

1. 회사 또는 학교 계정으로 Microsoft 365에 로그인합니다.

2. **Microsoft 365 관리 센터** 왼쪽 탐색에서 **사용자** > **활성 사용자** 로 이동한 다음 사용 가능한 사용자 목록에서 사용자 또는 사용자를 선택합니다.

    > [!NOTE]
    > 동시에 최대 20명의 사용자에게 라이선스를 할당하는 경우 **보기 선택** 드롭다운을 사용한 다음 옵션 중 하나를 선택하거나 고유한 보기를 만들 수 있습니다. 그런 다음 **편집**, **다음** 을 두 번 클릭한 다음 라이선스를 선택하고 **제출** 을 클릭합니다.  
  
3. **제품 라이선스** 아래의 작업 창에서 **편집** 을 클릭합니다.

4. **제품 라이선스** 페이지에서 **오디오 회의를** 켜고 **저장** 을 클릭합니다. 라이선스에 대한 자세한 내용은 [Microsoft Teams 추가 기능 라이선스를](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 참조하세요.

   > [!NOTE]
   > 라이선스를 할당한 후에는 Microsoft가 처음에 오디오 회의 공급자로 목록에 표시되지 않을 수 있습니다. 이 경우 관리 센터에서 로그아웃하거나 Ctrl+F5를 눌러 브라우저 창을 새로 고칩니다.
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>오디오 회의 사용자에게 전송된 전자 메일 사용 또는 사용 안 함

### <a name="enable-or-disable-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터를 사용하여 사용하거나 사용하지 않도록 설정

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지** 로 이동합니다.

2. **컨퍼런스 브리지** 페이지 위쪽에서 **브리지 설정을** 클릭합니다.

3. **브리지 설정** 창에서 **전화 접속 설정이 변경되면 자동으로 사용자에게 전자 메일을 보내도록** 설정하거나 사용하지 않도록 설정합니다.

4. **저장** 을 클릭합니다.

### <a name="enable-or-disable-using-windows-powershell"></a>Windows PowerShell 사용하여 사용 또는 사용 안 함

자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps) 를 참조하세요.
  
## <a name="reset-the-meeting-conference-id"></a>모임 회의 ID 다시 설정

### <a name="reset-the-meeting-conference-id-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터를 사용하여 모임 회의 ID 다시 설정

1. 왼쪽 탐색 영역에서 **사용자를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. **오디오 회의** 아래에서 **전화 회의 ID 재설정** 을 클릭합니다.  

3. **전화 회의 ID 다시 설정?** 창에서 **다시 설정을** 클릭합니다. 사용자에게 전자 메일을 보낼 수 있는 경우 전화 회의 ID가 자동으로 생성되고 사용자에게 새 회의 ID가 있는 전자 메일이 전송됩니다. 기본적으로 사용하도록 설정됩니다.

[사용자의 전화 회의 ID 재설정을 참조하세요](reset-a-conference-id-for-a-user-in-teams.md).

## <a name="reset-a-conference-organizers-pin"></a>회의 이끌이의 PIN 다시 설정

사용자가 예약하는 각 모임에는 고유한 회의 ID가 할당됩니다. 회의 ID가 자동으로 만들어지고 사용자에게 할당되지만 사용자가 이 ID를 사용하지 않고 특정 번호로 설정하려고 하거나 사용자가 전화 회의 ID를 기억하지 못하거나 분실한 경우가 있을 수 있습니다.

### <a name="reset-a-conference-organizers-pin-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터를 사용하여 회의 이끌이의 PIN 다시 설정

1. 왼쪽 탐색 영역에서 **사용자를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. **오디오 회의** 아래에서 **PIN 다시 설정을** 클릭한 다음 **다시 설정을** 클릭합니다.
  
사용자는 오디오 회의를 사용하도록 설정하거나 PIN을 다시 설정할 때 PIN이 포함된 전자 메일을 받게 됩니다. 그러나 전자 메일을 자동으로 전송하지 않도록 설정한 경우 PIN 재설정 전자 메일이 전송되지 않으며 사용자에게 PIN을 수동으로 보내야 합니다. PIN은 재설정된 후에 한 번만 표시됩니다. 다시 설정한 직후에 표시되면 PIN이 사용자 속성에 더 이상 표시되지 않습니다. 대신 *****가 표시됩니다.
  
[오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin-in-teams.md) 참조하세요.
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>사용자에게 오디오 회의 정보가 포함된 전자 메일 보내기

### <a name="send-an-email-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터를 사용하여 전자 메일 보내기

1. 왼쪽 탐색 영역에서 **사용자를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. **오디오 회의** 아래에서 **전자 메일로 회의 정보 보내기를** 클릭합니다.

    > [!NOTE]
    > 이렇게 하면 오디오 회의 PIN이 사용자에게 전송되지 않습니다.

[오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) 참조하세요.
  
## <a name="set-the-phone-numbers-included-on-invites"></a>초대에 포함할 전화 번호 설정

### <a name="set-invite-phone-numbers-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터를 사용하여 초대 전화 번호 설정

[Microsoft Teams의 초대에 포함된 전화 번호 설정을 참조하세요](set-the-phone-numbers-included-on-invites-in-teams.md).

> [!NOTE]
> *TeamsAudioconferencingpolicy* 에 전화 번호를 추가하고 사용자에게 정책을 할당하여 전화 번호를 설정할 수도 있습니다. 정책에 추가된 수신자 및 무료 전화 번호는 오디오 회의 설정 창을 통해 사용자에게 개별적으로 설정된 전화 번호보다 우선합니다. *Teamsaudioconferencingpolicy* 에 전화 번호가 추가되지 않으면 오디오 회의 설정 창을 통해 사용자에 대해 개별적으로 설정된 전화 번호가 Microsoft Teams 모임 요청에 표시됩니다. [유료 및 무료 번호에 대한 오디오 회의 정책 설정에는](audio-conferencing-toll-free-numbers-policy.md) 자세한 정보가 있습니다.

## <a name="choose-audio-conferencing-bridge-settings"></a>오디오 회의 브리지 설정 선택

### <a name="set-the-meeting-experience-when-callers-join-a-meeting-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터를 사용하여 발신자가 모임에 참가할 때 모임 환경 설정

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지** 로 이동합니다.

2. **컨퍼런스 브리지** 페이지 위쪽에서 **브리지 설정을** 클릭합니다.

3. **브리지 설정** 창에서 **모임 항목 및 종료 알림을** 사용하거나 사용하지 않도록 설정합니다.

    기본적으로 사용하도록 설정됩니다. 이 옵션을 사용하지 않도록 설정하면 기본적으로 모임에 이미 참가한 사용자는 모임에 참가하거나 모임을 떠날 때 알림을 받지 않습니다.

4. **항목/종료 공지 유형** 에서 **톤** 또는 **이름 또는 전화 번호를** 선택합니다.

    **이름 또는 전화 번호를** 선택하는 경우 **모임에 참가하기 전에 발신자에게 자신의 이름을 기록하도록 요청** 하도록 설정하거나 사용하지 않도록 선택할 수도 있습니다.
    > [!NOTE]
    > 기본적으로 외부 참가자는 전화 접속 참가자의 전화 번호를 볼 수 없습니다. 이러한 전화 번호의 프라이버시를 유지하려면 **입장/종료** **알림** 유형에 대해 톤을 선택하십시오(이로 인해 Teams가 번호를 읽을 수 없음).
5. **저장** 을 클릭합니다.

[오디오 회의 브리지에 대한 설정 변경을](change-the-settings-for-an-audio-conferencing-bridge.md) 참조하세요.
  
### <a name="set-the-pin-length-for-meetings"></a>모임의 PIN 길이 설정

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지** 로 이동합니다.

2. **컨퍼런스 브리지** 페이지 위쪽에서 **브리지 설정을** 클릭합니다.

3. **브리지 설정** 창의 **PIN 길이** 목록에서 PIN에 대해 원하는 자릿수를 입력한 다음 **저장** 을 클릭합니다.

    PIN은 4~12자리여야 합니다. 기본값은 5입니다.

[오디오 회의 브리지에 대한 설정 변경을](change-the-settings-for-an-audio-conferencing-bridge.md) 참조하세요.

### <a name="enable-or-disable-email-from-being-sent-to-audio-users"></a>전자 메일이 오디오 사용자에게 전송되지 않도록 설정하거나 사용하지 않도록 설정

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지** 로 이동합니다.

2. **컨퍼런스 브리지** 페이지 위쪽에서 **브리지 설정을** 클릭합니다.

3. **브리지 설정** 창에서 **오디오 회의 설정이 변경되면 자동으로 사용자에게 전자 메일을 보내도록** 설정하거나 사용하지 않도록 설정합니다.

4. **저장** 을 클릭합니다.

    사용자의 오디오 회의 속성으로 이동하고 전자 메일에서 **회의 정보 보내기** 를 클릭하여 오디오 회의 설정을 사용하여 사용자에게 전자 메일을 보낼 수도 있습니다.

    이렇게 하면 전화 회의 ID 및 전화 회의 전화 번호만 포함하는 전자 메일이 전송되지만 PIN은 포함되지 않습니다.

[오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) 참조하세요.

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>오디오 회의 브리지에서 기본(기본) 및 보조(대체) 언어를 보고 설정합니다.

### <a name="see-primary-and-secondary-languages-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터를 사용하여 기본 및 보조 언어 보기

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지** 로 이동합니다.

2. 목록에서 전화 번호를 선택하고 **편집** 을 클릭합니다.

3. **기본 언어** 및 **대체 언어(선택 사항)에서 원하는 언어를** 선택합니다.

4. **저장** 을 클릭합니다.

[오디오 회의에 대한 자동 전화 교환 언어 설정을 참조하세요](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers-using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터를 사용하여 오디오 회의 전화 접속 번호 보기

1. 왼쪽 탐색 창에서 **모임** > **회의 브리지** 로 이동합니다.

2. 목록에서 전화 번호를 선택하고 **편집** 을 클릭합니다. 여기에서 다음을 수행할 수 있습니다.

   - 오디오 회의에 사용할 전화 번호를 봅니다.

   - 오디오 회의 자동 전화 교환에서 사용할 위치 및 기본 언어를 봅니다.

[오디오 회의 번호 목록을 참조하세요](see-a-list-of-audio-conferencing-numbers-in-teams.md).

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell 대해 자세히 알고 싶으신가요?

Windows PowerShell 사용자를 관리하는 것과 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. Windows PowerShell 사용하면 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365 관리할 수 있습니다. Windows PowerShell 시작하려면 다음 항목을 참조하세요.

- [Microsoft 365 또는 Office 365 PowerShell을 사용해야 하는 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Windows PowerShell 사용하여 Microsoft 365 또는 Office 365 관리하는 가장 좋은 방법](/previous-versions//dn568025(v=technet.10))

Windows PowerShell 대한 자세한 내용은 [Microsoft Teams PowerShell 참조](/powershell/module/teams/?view=teams-ps)를 참조하세요.

## <a name="related-topics"></a>관련 항목

[사용자의 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)
