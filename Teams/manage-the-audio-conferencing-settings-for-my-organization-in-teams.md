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
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '사용자 및 기타 여러 전화 접속 회의 설정에 전화 접속 회의 라이선스 및 전화 회의 ID를 할당하는 Microsoft Teams 단계를 참조하세요. '
ms.openlocfilehash: f2d056ffd2c3b40b8e39f6d4727859b45e675ebf
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031804"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Microsoft Teams에서 조직의 오디오 회의 설정 관리

Microsoft Teams의 모든 오디오 회의 설정을 한 장소에서 쉽게 볼 수 있습니다. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>오디오 회의 라이선스 할당

> [!NOTE]
> Teams를 사용하여 라이선스를 할당할 수 없습니다. Microsoft 365 관리 센터를 사용해야 합니다. [Microsoft Teams 추가 기능 라이선스 할당을 참조합니다.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 
  
 **사용자에 대한 라이선스를 할당합니다.**
  
1. 직장 또는 학교 계정으로 Microsoft 365에 로그인합니다.
    
2. **Microsoft 365** 관리 센터의 왼쪽 탐색 모음에서 **사용자** 활성 사용자로 이동한 다음 사용 가능한 사용자 목록에서 사용자 또는  >  사용자를 선택합니다.
    
    > [!NOTE]
    > 동시에 최대 20명까지 라이선스를 할당하는 경우 보기 선택 드롭다운을 사용하여 옵션 중 하나를 선택하거나 고유한 보기를 만들 수 있습니다.  그런 다음 **편집을 클릭하고** **다음을** 두 번 클릭한 다음 라이선스를 선택하고 제출을 **클릭합니다.**  
  
3. 제품 라이선스 아래의 작업 창에서 편집을 **클릭합니다.** 
    
4. 제품 **라이선스** 페이지에서 오디오 회의를 켜고 저장을 **클릭합니다.**  라이선스에 대한 자세한 내용은 Microsoft Teams 추가 [기능 라이선스를 참조합니다.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
    
   > [!NOTE]
   > 라이선스를 할당한 후 Microsoft는 처음에 목록에 오디오 회의 공급자로 나타나지 않을 수 있습니다. 이 경우 관리 센터에서 로그아웃하거나 Ctrl+F5를 눌러 브라우저 창을 새로 고치십시오. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>오디오 회의 사용자에게 전송된 전자 메일 사용 또는 사용 안 하도록 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 모음에서 **모임** 회의  >  **브리지로 이동** 

2. 컨퍼런스 브리지  페이지의 맨 위에 있는 **브리지 설정을 클릭합니다.** 

3. 브리지 **설정 창에서** 전화 접속 설정이 변경되는 경우 사용자에게 자동으로 전자 메일 보내기를 사용하도록 설정하거나 **해제합니다.**

4. **저장** 을 클릭합니다.

    
**다음 Windows PowerShell**
  
자세한 내용은 [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.
  
## <a name="reset-the-meeting-conference-id"></a>모임 회의 ID 다시 설정

![Microsoft Teams 관리 센터를 사용하여 ](media/teams-logo-30x30.png) **Teams 로고를 표시하는 아이콘**

1. 왼쪽 탐색 모음에서 **[사용자]를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 오디오 **회의에서** 회의 ID **재설정을 클릭합니다.**  

3. 다시 설정 **회의 ID 창에서** 재설정을 **클릭합니다.** 사용자에게 전자 메일을 보낼 수 있는 경우 회의 ID가 자동으로 생성되고 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다. 기본적으로 사용하도록 설정되어 있습니다.

사용자의 [회의 ID 재설정을 참조합니다.](reset-a-conference-id-for-a-user-in-teams.md)
  
## <a name="reset-a-conference-organizers-pin"></a>회의 이끌이의 PIN 다시 설정

사용자가 예약하는 각 모임에는 고유한 회의 ID가 할당됩니다. 전화 회의 ID가 자동으로 만들어지며 사용자에게 할당되어도 사용자가 이 ID를 사용하지 못하고 특정 번호로 설정하려는 경우 또는 사용자가 전화 회의 ID를 기억하지 못하거나 분실한 경우도 있습니다. 

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 모음에서 **[사용자]를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 오디오 **회의에서** **PIN** 재설정을 클릭한 다음 다시 설정을 **클릭합니다.** 
  
오디오 회의를 사용하도록 설정하거나 PIN이 다시 설정되면 사용자가 PIN이 있는 전자 메일을 받게 됩니다. 하지만 전자 메일 자동 전송을 사용하지 않도록 설정한 경우 PIN 재설정 전자 메일이 전송되지 않고 사용자에게 PIN을 수동으로 보내야 합니다. PIN은 다시 설정한 후에 한 번만 표시됩니다. 다시 설정 직후에 PIN이 표시되면 사용자 속성에 더 이상 표시되지 않습니다. 대신 *****가 표시됩니다. 
  
오디오 [회의 PIN 재설정을 참조합니다.](reset-the-audio-conferencing-pin-in-teams.md)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>사용자에게 오디오 회의 정보가 있는 전자 메일 보내기

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 모음에서 **[사용자]를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 오디오 **회의 아래에서** 전자 **메일로 회의 정보 보내기 클릭** 

    > [!NOTE]
    > 이렇게 하는 경우 오디오 회의 PIN이 사용자에게 전송되지 않습니다. 

오디오 회의 정보가 있는 사용자에게 전자 메일 [보내기를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
  
## <a name="set-the-phone-numbers-included-on-invites"></a>초대에 포함할 전화 번호 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 모음에서 **[사용자]를** 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 오디오 회의 옆에 **있는** 편집을 **클릭합니다.**
 
3. 오디오 **회의** 창에서 무료 번호를 설정하고 허용되는 경우 무료 번호를 설정할 **수 있습니다.** 

4. **저장** 을 클릭합니다.
    
초대에 [포함된 전화 번호](set-the-phone-numbers-included-on-invites-in-teams.md)설정 참조
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>오디오 회의 브리지 설정 선택

**발신자 모임에 참가할 때 모임 환경 설정**

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 모음에서 **모임** 회의  >  **브리지로 이동** 

2. 컨퍼런스 브리지  페이지의 맨 위에 있는 **브리지 설정을 클릭합니다.** 

3. 브리지 **설정 창에서** 모임 항목 및 종료 알림을 사용 또는 사용하지 **않도록 설정합니다.**

    이 설정은 기본적으로 사용하도록 설정됩니다. 이 옵션을 사용하지 않도록 설정하면 기본적으로 모임에 이미 참가한 사용자는 모임에 입장하거나 퇴장할 때 알림을 들을 수 없습니다.

4. **진입/종료 공지 유형에서** 톤  또는 이름 또는 전화 번호를 **선택 합니다.** 

    이름 또는 전화 **번호를** 선택하는 경우 모임에 참가하기 전에 발신자 묻기 기능을 사용하도록 설정하거나 해제하여 이름을 기록할 **수도 있습니다.** 
    > [!NOTE]
    > 기본적으로 외부 참가자는 전화 접속 참가자의 전화 번호를 볼 수 없습니다. 이러한 전화 번호의 프라이버시를 유지하려면 **입장/종료** **알림** 유형에 대해 톤을 선택하십시오(이로 인해 Teams가 번호를 읽을 수 없음).


5. **저장** 을 클릭합니다.

    
오디오 회의 브리지의 설정 [변경을 참조하세요.](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **모임의 PIN 길이 설정**

1. 왼쪽 탐색 모음에서 **모임** 회의  >  **브리지로 이동** 

2. 컨퍼런스 브리지  페이지의 맨 위에 있는 **브리지 설정을 클릭합니다.** 

3. 브리지 **설정** 창에서 PIN 길이 목록에서 **PIN에** 사용할 자릿수를 입력한 다음 저장을 **클릭합니다.**

    PIN은 4~12자리 사이입니다. 기본값은 5입니다.

    
오디오 회의 브리지의 설정 [변경을 참조하세요.](change-the-settings-for-an-audio-conferencing-bridge.md)
  
 **오디오 사용자에게 전자 메일 보내기 사용 또는 사용 안 하도록 설정**

1. 왼쪽 탐색 모음에서 **모임** 회의  >  **브리지로 이동** 

2. 컨퍼런스 브리지  페이지의 맨 위에 있는 **브리지 설정을 클릭합니다.** 

3. 브리지 **설정 창에서** 오디오 회의 설정이 변경되는 경우 사용자에게 자동으로 전자 메일 보내기 사용 또는 사용 안 **하도록 설정**

4. **저장** 을 클릭합니다. 
 
    사용자의 오디오 회의 속성으로 이동하고 전자 메일로 회의 정보 보내기를 클릭하여 오디오 회의 설정을 사용하여 사용자에게 전자 메일을 보낼 **수도 있습니다.**
    
    이렇게 하면 전화 회의 ID와 전화 회의 전화 번호만 포함된 전자 메일이 전송되지만 PIN은 포함되지 않습니다.

오디오 회의 정보가 있는 사용자에게 전자 메일 [보내기를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>오디오 회의 브리지에서 기본(기본값) 및 보조(대체) 언어 보기 및 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 모음에서 **모임** 회의  >  **브리지로 이동** 

2. 목록에서 전화 번호를 선택하고 편집을 **클릭합니다.**

3. 기본 언어 및 대체  언어(선택 사항)에서 원하는 언어를 **선택 합니다.**

4. **저장** 을 클릭합니다.


오디오 [회의에 대한](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)자동 참석 언어 설정 참조
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>오디오 회의 전화 접속 번호 보기

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색 모음에서 **모임** 회의  >  **브리지로 이동** 

2. 목록에서 전화 번호를 선택하고 편집을 **클릭합니다.** 여기에서 다음을 할 수 있습니다.
    
   - 오디오 회의에 사용할 전화 번호를 본다. 
    
   - 오디오 회의 자동 연결에서 사용할 위치 및 기본 언어를 볼 수 있습니다.

  
오디오 회의 번호 목록을 [참조하세요.](see-a-list-of-audio-conferencing-numbers-in-teams.md)
  

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 내용은 Windows PowerShell?

Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다. 다음 항목을 Windows PowerShell 항목을 참조하세요.
    
  - [Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
자세한 내용은 Windows PowerShell [Microsoft Teams PowerShell 참조를](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) 참조하세요.
  
    
## <a name="related-topics"></a>관련 항목

[사용자의 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


