---
title: Skype 모임 브로드캐스트 사용
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: 조직의 사용자가 Skype 모임 브로드캐스트를 사용하기 전에 이를 사용하도록 설정해야 합니다. 이렇게하려면 이 작업을 사용하는 방법을 Windows PowerShell. Microsoft 파트너를 Windows PowerShell 모르는 경우 이 단계를 위해 Microsoft 파트너를 고용하는 것이 고려됩니다.
ms.openlocfilehash: ab59348d32ef130df6b0de6e1eb65c92d0222e04
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097114"
---
# <a name="enable-skype-meeting-broadcast"></a>Skype 모임 브로드캐스트 사용

> [!IMPORTANT]
> 비즈니스용 Skype Online이 2021년 7월 31일 사용 중지 중입니다. 그러면 서비스에 대한 액세스가 종료됩니다. 고객이 Microsoft 365에서 통신 및 팀워크의 핵심 클라이언트인 Microsoft Teams로 업그레이드를 시작하는 것이 권장됩니다.

조직의 사용자가 Skype 모임 브로드캐스트를 사용하기 전에 이를 사용하도록 설정해야 합니다. 이렇게하려면 이 작업을 사용하는 방법을 Windows PowerShell. Microsoft 파트너를 Windows PowerShell 모르는 경우 이 단계를 위해 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 파트너를 고용하는 것이 고려됩니다.



> [!NOTE]
> Microsoft Teams 관리 센터가 비즈니스용 Skype 관리 센터(레거시 포털)를 대체했습니다. 이제 비즈니스용 Skype를 관리하기 위한 모든 설정이 Teams 관리 센터에 있습니다. Teams 관리 센터에서 [비즈니스용 Skype](/azure/active-directory/roles/permissions-reference) 기능을 관리하려면 글로벌 관리자 또는 비즈니스용 Skype 관리자의 Azure AD 관리자 역할이 할당되어야 합니다. 자세한 내용은 [Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)를 참조하세요.

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>비즈니스용 Skype 관리 센터를 사용하여 Skype 모임 브로드캐스트 사용

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

1. 글로벌 관리자 계정 또는 비즈니스용 Skype 관리자 계정으로 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 로그인합니다.
    
2. 관리 센터에서 관리 센터 **Teams로**  >  **이동하세요.**
    
3. Teams 관리 **센터에서** 레거시 포털 온라인 모임 브로드캐스트 모임으로 이동한 다음 Skype 모임 브로드캐스트 사용  >    >   **을 선택합니다.**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>PowerShell을 사용하여 Skype 모임 브로드캐스트 사용

1. Teams [PowerShell 모듈을 설치합니다.](/microsoftteams/teams-powershell-install)
    
2. 명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다. 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. 실행하여 현재 Skype 모임 브로드캐스트 구성 확인:
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    _EnableBroadcastMeeting_ 매개 변수가 로 설정되어 있는지 `False` 확인
    
     ![Skype 모임 브로드캐스트 조직 cmdlet을 사용하도록 설정합니다.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. 실행하여 조직에 Skype 모임 브로드캐스트 사용:
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    다시 실행하여 설정을 사용하도록 설정할 수  `Get-CsBroadcastMeetingConfiguration` 있습니다.
    
     ![Skype 모임 브로드캐스트는 조직 Cmdlet을 사용하도록 설정합니다.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 변경한 후 Skype 모임 브로드캐스트 포털에서 적용하는 데 최대 1시간이 걸릴 수 있습니다. 
  
10. 이제 사용자는 비즈니스의 다른 사용자와 브로드캐스트 모임을 개최할 수 있습니다. 시작을 위해 Skype 모임 [](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) 브로드캐스트란?
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>외부 참석자들과 모임을 브로드캐스트하도록 네트워크 구성

방화벽이 있는 경우 비즈니스 외부 사용자(페더리드 비즈니스가 아닌 사용자)와 브로드캐스트를 보류하려는 경우 다음 지침을 사용하여 네트워크를 구성해야 [합니다. Skype 모임](set-up-your-network-for-skype-meeting-broadcast.md)브로드캐스트에 대한 네트워크 설정 입니다. 
  
방화벽을 구성하는 데 경험이 없는 경우 이 단계를 위해 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 파트너를 고용하는 것이 좋습니다.
  
이 단계를 건너뛰고 페더연맹에 다른 비즈니스를 추가하는 대신 사용자가 비즈니스용 외부 Skype 사용자에 문의하도록 허용을 [참조하세요.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) 
  
## <a name="related-topics"></a>관련 항목

[Windows PowerShell 및 비즈니스용 Skype Online 소개](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[비즈니스용 Skype 온라인 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
