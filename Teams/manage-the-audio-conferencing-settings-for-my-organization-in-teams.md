---
title: 오디오 회의 설정 관리
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '사용자와 다른 여러 전화 접속 회의 설정에 전화 접속 회의 라이선스 및 전화 회의 ID를 할당 하려면 Microsoft 팀의 단계를 참조 하세요. '
ms.openlocfilehash: 704bcd5777fd0327ed944cc903959ef019f794a5
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638467"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Microsoft 팀에서 조직의 오디오 회의 설정 관리

Microsoft 팀에 대 한 오디오 회의 설정을 한 곳에 모두 표시 하는 것이 더 쉬울 수 있습니다. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>오디오 회의 라이선스 할당

> [!NOTE]
> 팀을 사용 하 여 라이선스를 할당할 수 없습니다. Microsoft 365 관리 센터를 사용 해야 합니다. [Microsoft 팀 추가 기능 라이선스 할당](teams-add-on-licensing/assign-teams-add-on-licenses.md)을 참조 하세요. 
  
 **사용자에 게 라이선스를 할당 하려면**
  
1. 회사 또는 학교 계정으로 Microsoft 365에 로그인 합니다.
    
2. **Microsoft 365 관리 센터**의 왼쪽 탐색 창에서 **사용자**  >  **활성 사용자**로 이동한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.
    
    > [!NOTE]
    > 동시에 최대 20 명의 사용자에 게 라이선스를 할당 하는 경우 **보기 선택** 드롭다운을 사용 하 여 해당 옵션 중 하나를 선택 하거나 고유한 보기를 만들 수 있습니다. 그런 다음 **편집**을 클릭 하 고 두 **번 다음 라이선스** 를 선택 하 고 **제출을**클릭 합니다.  
  
3. 작업 창의 **제품 라이선스**에서 **편집**을 클릭 합니다. 
    
4. **제품 라이선스** 페이지에서 **오디오 회의** 를 켠 다음 **저장**을 클릭 합니다. 라이선스에 대 한 자세한 내용은 [Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.
    
> [!NOTE]
> 라이선스를 할당 한 후에는 Microsoft에서 처음에 오디오 회의 공급자로 목록에 표시 되지 않을 수 있습니다. 이 문제가 발생 하면 관리 센터에서 로그 아웃 하거나 CTRL + F5를 눌러 브라우저 창을 새로 고칩니다. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>오디오 회의 사용자에 게 전송 되는 전자 메일 사용 또는 사용 안 함

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **모임**  >  **회의 브리지로**이동 합니다. 

2. **회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다. 

3. **브리지 설정** 창에서 **전화 접속 설정이 변경 되는 경우 자동으로 사용자에 게 전자 메일 보내기**사용 또는 사용 안 함을 설정 하거나 해제 합니다.

4. **저장**을 클릭합니다.

    
**Windows PowerShell 사용**
  
자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 를 참조 하세요.
  
## <a name="reset-the-meeting-conference-id"></a>모임 전화 회의 ID 다시 설정

![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** 팀 로고를 표시 하는 아이콘

1. 왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

2. **오디오 회의**에서 **전화 회의 ID 재설정**을 클릭 합니다.  

3. **전화 회의 ID 다시 설정** 창에서 **원래 대로**를 클릭 합니다. 사용자에 게 전자 메일을 보내는 경우 전화 회의 ID가 자동으로 만들어지고 새 전화 회의 ID를 사용 하 여 사용자에 게 전자 메일이 전송 됩니다. 기본적으로 사용 하도록 설정 되어 있습니다.

[사용자의 전화 회의 ID 다시 설정을](reset-a-conference-id-for-a-user-in-teams.md)참조 하세요.
  
## <a name="reset-a-conference-organizers-pin"></a>회의 이끌이의 PIN 다시 설정

사용자가 예약 하는 각 모임에는 고유한 전화 번호를 할당 받게 됩니다. 전화 회의 ID는 자동으로 만들어지고 사용자에 게 할당 되지만, 사용자가이를 사용 하지 않고 특정 번호로 설정 하려는 경우 또는 사용자가 자신의 전화 회의 ID를 분실 하거나 잃어 버릴 수도 있습니다. 

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

2. **오디오 회의**에서 **PIN 다시 설정을**클릭 한 다음 **원래 대로**를 클릭 합니다. 
  
사용자가 오디오 회의를 사용 하도록 설정 하거나 PIN을 다시 설정한 경우 PIN이 포함 된 전자 메일을 받게 됩니다. 그러나 자동으로 전자 메일 보내기를 사용 하지 않도록 설정한 경우 PIN 다시 설정 전자 메일을 보내지 않으며 사용자에 게 수동으로 PIN을 보내야 합니다. PIN은 다시 설정 된 후에만 표시 됩니다. 다시 설정 된 후에 표시 된 후에는 사용자 속성에 더 이상 PIN이 표시 되지 않습니다. 대신 * * * * *가 표시 됩니다. 
  
[오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin-in-teams.md)참조 하세요.
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

2. **오디오 회의**에서 **전자 메일로 회의 정보 보내기를**클릭 합니다. 

    > [!NOTE]
    > 이렇게 하면 오디오 회의 PIN이 사용자에 게 전송 되지 않습니다. 

[오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)참조 하세요.
  
## <a name="set-the-phone-numbers-included-on-invites"></a>초대에 포함할 전화 번호 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **사용자**를 클릭 한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.

2. **오디오 회의**옆에 있는 **편집**을 클릭 합니다.
 
3. **오디오 회의** 창에서 **유료** 번호를 설정 하 고, 허용 되는 경우 무료 **번호**를 설정할 수 있습니다.

4. **저장**을 클릭합니다.
    
[초대에 포함 된 전화 번호 설정을](set-the-phone-numbers-included-on-invites-in-teams.md)참조 하세요.
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>오디오 회의 브리지 설정 선택

**발신자가 모임에 참가 하는 경우의 모임 환경 설정**

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **모임**  >  **회의 브리지로**이동 합니다. 

2. **회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다. 

3. **브리지 설정** 창에서 모임 항목을 사용 하거나 사용 하지 않도록 설정 **하 고 알림을 종료**합니다.

    이 기능은 기본적으로 활성화 되어 있습니다. 이 옵션을 사용 하지 않도록 설정 하면 모임에 이미 참가 한 사용자는 다른 사용자가 모임을 시작 하거나 떠날 때 알림을 받을 수 없습니다.

4. **알림 유형 입력/종료**에서 **톤** 또는 **이름 또는 전화 번호**를 선택 합니다. 

    **이름 또는 전화 번호**를 선택 하 **는 경우 모임에 참가 하기 전에 해당 사용자의 이름을 기록 하도록 요청 발신자**를 선택 하거나 사용 하지 않도록 설정할 수도 있습니다. 
    > [!NOTE]
> 기본적으로 외부 참가자는 전화를 건 참가자의 전화 번호를 볼 수 없습니다. 이러한 전화 번호에 대 한 개인 정보를 유지 관리 하려면 **입력/종료 알림 유형에** **색조** 를 선택 하세요 (이로 인해 팀에서 번호를 읽지 못하게 됩니다).

    > [!NOTE]
    > 기본적으로 외부 참가자는 전화를 건 참가자의 전화 번호를 볼 수 없습니다. 이러한 전화 번호에 대 한 개인 정보를 유지 관리 하려면 **입력/종료 알림 유형에** **색조** 를 선택 하세요 (이로 인해 팀에서 번호를 읽지 못하게 됩니다).

5. **저장**을 클릭합니다.

    
[오디오 회의 브리지에 대 한 설정 변경을](change-the-settings-for-an-audio-conferencing-bridge.md)참조 하세요.
  
 **모임의 PIN 길이 설정**

1. 왼쪽 탐색 창에서 **모임**  >  **회의 브리지로**이동 합니다. 

2. **회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다. 

3. **브리지 설정** 창에서 **pin 길이** 목록에 원하는 pin의 자릿수를 입력 한 다음 **저장**을 클릭 합니다.

    PIN은 4 ~ 12 자리 여야 합니다. 기본값은 5입니다.

    
[오디오 회의 브리지에 대 한 설정 변경을](change-the-settings-for-an-audio-conferencing-bridge.md)참조 하세요.
  
 **오디오 사용자에 게 전자 메일을 보낼 수 있도록 설정 또는 해제**

1. 왼쪽 탐색 창에서 **모임**  >  **회의 브리지로**이동 합니다. 

2. **회의 브리지** 페이지 맨 위에서 **브리지 설정을**클릭 합니다. 

3. **브리지 설정** 창에서 **오디오 회의 설정이 변경 된 경우 자동으로 사용자에 게 전자 메일 보내기를**사용 하거나 사용 하지 않도록 설정 합니다.

4. **저장**을 클릭합니다. 
 
    사용자의 오디오 회의 속성으로 이동한 다음 **전자 메일로 회의 정보 보내기를**클릭 하 여 오디오 회의 설정을 사용 하 여 사용자에 게 전자 메일을 보낼 수도 있습니다.
    
    이렇게 하면 전화 회의 ID 및 전화 회의 전화 번호만 포함 된 전자 메일이 전송 되지만 PIN은 포함 되지 않습니다.

[오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)참조 하세요.
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>오디오 회의 브리지의 기본 (기본) 및 보조 (대체) 언어를 표시 하 고 설정 합니다.

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **모임**  >  **회의 브리지로**이동 합니다. 

2. 목록에서 전화 번호를 선택 하 고 **편집**을 클릭 합니다.

3. **기본 언어** 및 대체 언어에서 원하는 언어를 선택 합니다 **(선택 사항)**.

4. **저장**을 클릭합니다.


[오디오 회의에 대 한 자동 전화 교환 언어 설정을](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)참조 하세요.
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>오디오 회의 전화 접속 번호 보기

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 창에서 **모임**  >  **회의 브리지로**이동 합니다. 

2. 목록에서 전화 번호를 선택 하 고 **편집**을 클릭 합니다. 다음과 같은 작업을 수행할 수 있습니다.
    
   - 오디오 회의에 사용 되는 전화 번호를 확인 합니다. 
    
   - 오디오 회의 자동 전화 교환에 사용 되는 위치와 기본 언어를 확인 합니다.

  
[오디오 회의 번호 목록 보기를](see-a-list-of-audio-conferencing-numbers-in-teams.md)참조 하세요.
  

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell을 사용 하 여 Microsoft 365 또는 Office 365을 관리 하는 최상의 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell에 대 한 자세한 내용은 [Microsoft 팀 PowerShell 참조](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 에서 자세한 내용을 참조 하세요.
  
    
## <a name="related-topics"></a>관련 항목

[사용자의 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


