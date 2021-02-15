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
description: 조직의 사용자가 Skype 모임 브로드캐스트를 사용하려면 먼저 사용하도록 설정해야 합니다. 이렇게하려면 이 작업을 사용하는 방법을 알아야 Windows PowerShell. 이 단계를 Windows PowerShell Microsoft 파트너를 고용하는 것이 가장 좋은 일입니다.
ms.openlocfilehash: 1ba8f11913c932d695806ae4fd30db5e8609530f
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865142"
---
# <a name="enable-skype-meeting-broadcast"></a>Skype 모임 브로드캐스트 사용

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021년 7월 31일 사용이 중지됩니다. 그러면 서비스에 대한 액세스가 종료됩니다. Microsoft 365에서 커뮤니케이션 및 팀워크를 위한 핵심 클라이언트인 Microsoft Teams로 업그레이드하는 것이 권장됩니다.

조직의 사용자가 Skype 모임 브로드캐스트를 사용하려면 먼저 사용하도록 설정해야 합니다. 이렇게하려면 이 작업을 사용하는 방법을 알아야 Windows PowerShell. 이 단계를 Windows PowerShell [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 파트너를 고용하는 것이 가장 좋은 일입니다.



> [!NOTE]
> Microsoft Teams 관리 센터가 비즈니스용 Skype 관리 센터(레거시 포털)를 대체했습니다. 이제 비즈니스용 Skype를 관리하기 위한 모든 설정이 Teams 관리 센터에 있습니다. Teams 관리 센터에서 비즈니스용 Skype 기능을 관리하려면 전역 관리자 또는 비즈니스용 Skype 관리자의 [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) 관리자 역할이 할당되어야 합니다. 자세한 내용은 [Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)를 참조하세요.

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>비즈니스용 Skype 관리 센터를 사용하여 Skype 모임 브로드캐스트 사용

![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**

1. 전역 관리자 계정 또는 비즈니스용 Skype 관리자 계정으로 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 로그인합니다.
    
2. 관리 센터에서 관리 센터  >  **Teams로 이동하세요.**
    
3. Teams 관리 **센터에서** 레거시 포털 온라인 모임 브로드캐스트 모임으로 이동한 다음 Skype 모임 브로드캐스트  >    >   **사용을 선택합니다.**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>PowerShell을 사용하여 Skype 모임 브로드캐스트 사용

1. 버전 3.0 이상을 실행하고 있는지 Windows PowerShell.
    
2. 버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.
    
3. 웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 확인
    
4. 버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치해야 Windows PowerShell. 버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다. 메시지가 표시될 때 컴퓨터를 다시 시작합니다.
    
5. 또한 비즈니스용 Skype Online에 Windows PowerShell 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online용 Windows PowerShell 모듈을 설치해야 합니다. 64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 Skype Online용 Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 다운로드할 [수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688) 메시지가 표시될 경우 컴퓨터를 다시 시작합니다.
    
6. 시작 **메뉴에서** 다음 **Windows PowerShell.**
    
7. 다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. 실행하여 현재 Skype 모임 브로드캐스트 구성을 확인:
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    _EnableBroadcastMeeting_ 매개 변수가 으로 설정되어 있는지 `False` 확인
    
     ![Skype 모임 브로드캐스트를 사용하면 조직 cmdlet을 사용할 수 있습니다.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. 실행하여 조직에 대해 Skype 모임 브로드캐스트를 사용하도록 설정:
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    다시 실행하여 설정이 활성화되어 있는지 확인할 수  `Get-CsBroadcastMeetingConfiguration` 있습니다.
    
     ![Skype 모임 브로드캐스트를 사용하면 조직 Cmdlet을 사용할 수 있습니다.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 변경한 후 Skype 모임 브로드캐스트 포털에서 적용하는 데 최대 1시간이 걸릴 수 있습니다. 
  
10. 이제 사용자는 비즈니스의 다른 사용자와 브로드캐스트 모임을 개최할 수 있습니다. 시작을 위해 Skype 모임 [](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) 브로드캐스트란?
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>외부 참석자와 모임을 브로드캐스트하도록 네트워크 구성

방화벽이 있는 경우 비즈니스 외부의 사용자(페더맹 비즈니스가 아닌 사용자)와 브로드캐스트를 보류하려는 경우 다음 지침을 사용하여 네트워크를 구성해야 합니다. [Skype](set-up-your-network-for-skype-meeting-broadcast.md)모임 브로드캐스트에 대한 네트워크 설정. 
  
방화벽 구성에 경험이 없는 경우 이 단계를 위해 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 파트너를 고용하는 것이 좋습니다.
  
이 단계를 건너뛰고 페더러에 다른 비즈니스를 추가하는 대신 사용자가 외부 비즈니스용 Skype 사용자에게 연락할 수 있도록 [허용을 참조하세요.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) 
  
## <a name="related-topics"></a>관련 항목

[Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[비즈니스용 Skype 온라인 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
