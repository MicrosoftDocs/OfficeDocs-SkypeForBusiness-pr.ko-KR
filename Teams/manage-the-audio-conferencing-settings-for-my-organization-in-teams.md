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
description: '사용자 Microsoft Teams 전화 접속 회의 설정에 전화 접속 회의 라이선스 및 회의 ID를 할당하려면 다음 단계를 참조하세요. '
ms.openlocfilehash: 96a8995b995340642c6b58be9d5062eacd3cd29c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101094"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Microsoft Teams에서 조직의 오디오 회의 설정 관리

한 장소에서 모든 오디오 회의 설정을 Microsoft Teams 수 있습니다. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>오디오 회의 라이선스 할당

> [!NOTE]
> 라이선스를 사용하여 라이선스를 할당할 수 Teams. 관리자 센터를 Microsoft 365 합니다. 추가 [Microsoft Teams 라이선스 할당을 참조합니다.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 
  
 **사용자에 대한 라이선스를 할당하는 경우**
  
1. 직장 또는 Microsoft 365 로그인합니다.
    
2. 관리 센터의 **왼쪽** 탐색에서 Microsoft 365 활성 사용자로 이동한 다음 사용 가능한 사용자 목록에서 사용자 또는 사용자를   >  선택합니다.
    
    > [!NOTE]
    > 동시에 최대 20명에게 라이선스를 할당하는 경우 보기 드롭다운  선택을 사용하여 옵션 중 하나를 선택하거나 고유한 보기를 만들 수 있습니다. 그런 다음 **편집을** 클릭한 **다음** 다음 두 번 라이선스를 선택하고 제출을 **클릭합니다.**  
  
3. 제품 라이선스 아래의 작업 창에서 **편집을** **클릭합니다.** 
    
4. 제품 라이선스 **페이지에서** **오디오** 회의를 켜고 저장을 **클릭합니다.** 라이선스에 대한 자세한 내용은 추가 [Microsoft Teams 라이선스를 참조합니다.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
   > [!NOTE]
   > 라이선스를 할당한 후 Microsoft는 처음에 오디오 회의 공급자로 목록에 나타나지 않을 수 있습니다. 이 경우 관리 센터에서 로그아웃하거나 CTRL+F5를 눌러 브라우저 창을 새로 고침합니다. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>오디오 회의 사용자에게 전송된 전자 메일 사용 또는 사용 안 하도록 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.** 

2. 컨퍼런스 브리지  페이지의 맨 위에 있는 브리지 설정을 **클릭합니다.** 

3. 브리지 **설정 창에서** 전화 접속 설정이 변경될 경우 사용자에게 자동으로 전자 메일 보내기를 사용하도록 설정하거나 **사용하지 않도록 설정합니다.**

4. **저장** 을 클릭합니다.

    
**Windows PowerShell**
  
자세한 [내용은 Microsoft Teams PowerShell 참조를](/powershell/module/teams/?view=teams-ps) 참조하세요.
  
## <a name="reset-the-meeting-conference-id"></a>모임 모임 ID 재설정

![관리 센터를 사용하여 Teams 로고를 Microsoft Teams ](media/teams-logo-30x30.png) **아이콘**

1. 왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 오디오 **회의에서** 회의 ID **재설정을 클릭합니다.**  

3. 회의 **ID 재설정 창에서** 다시 설정 **을 클릭합니다.** 사용자에게 전자 메일을 보낼 수 있는 경우 회의 ID가 자동으로 생성되고 사용자에게 새 회의 ID가 있는 전자 메일이 전송됩니다. 기본적으로 사용하도록 설정되어 있습니다.

사용자의 [회의 ID 재설정을 참조합니다.](reset-a-conference-id-for-a-user-in-teams.md)
  
## <a name="reset-a-conference-organizers-pin"></a>회의 이끌이의 PIN 재설정

사용자가 예약하는 각 모임에 고유한 회의 ID가 할당됩니다. 회의 ID가 사용자에게 자동으로 만들어지지만 사용자가 이 ID를 사용하지 못하고 특정 번호로 설정하려는 경우나 사용자가 회의 ID를 기억하지 못하거나 분실한 경우도 있을 수 있습니다. 

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 오디오 **회의에서** **PIN** 재설정을 클릭한 다음 다시 **설정 을 클릭합니다.** 
  
오디오 회의를 사용하도록 설정하거나 PIN이 다시 설정되면 사용자가 PIN이 있는 전자 메일을 받게 됩니다. 하지만 자동으로 전자 메일을 보내지 않도록 설정한 경우 PIN 재설정 전자 메일이 전송되지 않고 PIN을 사용자에게 수동으로 보내야 합니다. PIN은 다시 설정한 후에만 표시됩니다. 다시 설정한 직후에 표시되면 사용자 속성에 PIN이 더 이상 표시되지 않습니다. 대신 *****가 표시됩니다. 
  
오디오 회의 PIN 재설정을 [참조합니다.](reset-the-audio-conferencing-pin-in-teams.md)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>사용자에게 오디오 회의 정보가 있는 전자 메일 보내기

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 오디오 **회의에서** 전자 메일로 **회의 정보 보내기 를 클릭합니다.** 

    > [!NOTE]
    > 이렇게 할 때 오디오 회의 PIN이 사용자에게 전송되지 않습니다. 

오디오 회의 정보를 통해 사용자에게 전자 메일 [보내기 를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
  
## <a name="set-the-phone-numbers-included-on-invites"></a>초대에 포함할 전화 번호 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 **사용자** 를 클릭한 다음 사용 가능한 사용자 목록에서 사용자를 선택합니다.

2. 오디오 **회의** 옆에 있는 편집을 **클릭합니다.**
 
3. 오디오 **회의** 창에서 전화 번호 및 허용되는  경우 무료 전화 번호 를 설정할 **수 있습니다.**

4. **저장** 을 클릭합니다.
    
초대에 [포함된 전화 번호 설정 을 참조합니다.](set-the-phone-numbers-included-on-invites-in-teams.md)
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>오디오 회의 브리지 설정 선택

**발신자가 모임에 참가할 때 모임 환경 설정**

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.** 

2. 컨퍼런스 브리지  페이지의 맨 위에 있는 브리지 설정을 **클릭합니다.** 

3. Bridge **설정 창에서** 모임 항목 및 종료 알림을 사용하도록 설정하거나 **사용하지 않도록 설정합니다.**

    기본적으로 사용하도록 설정되어 있습니다. 이 옵션을 사용하지 않도록 설정하면 기본적으로 모임에 이미 참가한 사용자는 다른 사용자가 모임에 참가하거나 나가는 경우 알림을 들을 수 없습니다.

4. **진입/종료 공지 유형에서** 톤  또는 이름 또는 전화 **번호를 선택합니다.** 

    이름 또는 전화 **번호를 선택하는** 경우 모임에 참가하기 전에 발신자 요청 을 사용하도록 설정하거나 사용하지 않도록 설정할 **수도 있습니다.** 
    > [!NOTE]
    > 기본적으로 외부 참가자는 전화 접속 참가자의 전화 번호를 볼 수 없습니다. 이러한 전화 번호의 프라이버시를 유지하려면 **입장/종료** **알림** 유형에 대해 톤을 선택하십시오(이로 인해 Teams가 번호를 읽을 수 없음).


5. **저장** 을 클릭합니다.

    
오디오 [회의 브리지의](change-the-settings-for-an-audio-conferencing-bridge.md)설정 변경을 참조하세요.
  
 **모임에 대한 PIN 길이 설정**

1. 왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.** 

2. 컨퍼런스 브리지  페이지의 맨 위에 있는 브리지 설정을 **클릭합니다.** 

3. 브리지 **설정** 창에서 PIN 길이 목록에서 **PIN에** 사용할 자릿수 수를 입력한 다음 저장을 **클릭합니다.**

    PIN은 4~12자리 사이 되어야 합니다. 기본값은 5입니다.

    
오디오 [회의 브리지의](change-the-settings-for-an-audio-conferencing-bridge.md)설정 변경을 참조하세요.
  
 **오디오 사용자에게 전자 메일이 전송되지 않도록 설정하거나 사용하지 않도록 설정**

1. 왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.** 

2. 컨퍼런스 브리지  페이지의 맨 위에 있는 브리지 설정을 **클릭합니다.** 

3. 브리지 **설정** 창에서 오디오 회의 설정이 변경될 경우 사용자에게 자동으로 전자 메일 보내기 를 사용하도록 설정하거나 사용하지 **않도록 설정합니다.**

4. **저장** 을 클릭합니다. 
 
    사용자의 오디오 회의 속성으로 이동하고 전자 메일로 회의 정보 보내기 를 클릭하여 오디오 회의 설정을 사용하여 사용자에게 전자 메일을 보낼 **수도 있습니다.**
    
    이렇게 하면 전화 회의 ID 및 전화 회의 전화 번호만 포함하는 전자 메일이 전송되지만 PIN은 포함되지 않습니다.

오디오 회의 정보를 통해 사용자에게 전자 메일 [보내기 를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>오디오 회의 브리지에서 기본(기본값) 및 보조(대체) 언어를 보고 설정

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.** 

2. 목록에서 전화 번호를 선택하고 **편집을 클릭합니다.**

3. 기본 언어 및 대체  언어(선택 사항)에서 원하는 언어를 **선택합니다.**

4. **저장** 을 클릭합니다.


오디오 회의에 대한 자동 참석 언어 [설정 을 참조합니다.](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>오디오 회의 전화 접속 번호 참조

![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**

1. 왼쪽 탐색에서 모임 회의  >  **브리지로 이동합니다.** 

2. 목록에서 전화 번호를 선택하고 **편집을 클릭합니다.** 여기에서 다음을 할 수 있습니다.
    
   - 오디오 회의에 사용할 전화 번호를 본다. 
    
   - 오디오 회의 자동 참석자가 사용할 위치 및 기본 언어를 본다.

  
오디오 회의 번호 목록을 [참조하세요.](see-a-list-of-audio-conferencing-numbers-in-teams.md)
  

## <a name="want-to-know-more-about-windows-powershell"></a>자세한 정보를 Windows PowerShell?

Windows PowerShell 모든 것은 사용자 관리와 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다. 이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 단순화할 수 Microsoft 365 Office 365 관리 지점을 사용하여 관리 또는 관리 작업을 관리할 수 있습니다. 다음 항목을 Windows PowerShell 다음 항목을 참조하세요.
    
  - [PowerShell 또는 Microsoft 365 Office 365 이유](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [사용자와 함께 Microsoft 365 또는 Office 365 가장 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
자세한 내용은 Windows PowerShell [PowerShell](/powershell/module/teams/?view=teams-ps) Microsoft Teams 참조를 참조하세요.
  
    
## <a name="related-topics"></a>관련 항목

[사용자의 오디오 회의 설정 관리](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)