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
description: 조직의 사용자가 Skype 모임 브로드캐스트를 사용 하기 전에 먼저 사용 하도록 설정 해야 합니다. 이렇게 하려면 Windows PowerShell을 사용 하는 방법을 알고 있어야 합니다. Windows PowerShell을 모르는 경우 Microsoft 파트너를 고용 하 여이 단계를 수행 하는 것이 좋습니다.
ms.openlocfilehash: 6ad681972bb62fa1790290a90d4281fe4ccd8571
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692633"
---
# <a name="enable-skype-meeting-broadcast"></a>Skype 모임 브로드캐스트 사용

조직의 사용자가 Skype 모임 브로드캐스트를 사용 하기 전에 먼저 사용 하도록 설정 해야 합니다. 이렇게 하려면 Windows PowerShell을 사용 하는 방법을 알고 있어야 합니다. Windows PowerShell을 모르는 경우 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089) 를 고용 하 여이 단계를 수행 하는 것이 좋습니다.

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>비즈니스용 Skype 관리 센터를 사용 하 여 Skype 모임 브로드캐스트 사용

![비즈니스용 skype](../images/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘

1. Office 365 전역 관리자 계정 또는에서 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)비즈니스용 Skype 관리자 계정을 사용 하 여 로그인 합니다.
    
2. 관리 센터에서 **관리 센터** > **팀**으로 이동 합니다.
    
3. **팀 관리 센터**에서 **기존 포털** > **온라인 모임** > **브로드캐스트 모임**으로 이동한 다음 **Skype 모임 브로드캐스트 사용**을 선택 합니다.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>PowerShell을 사용 하 여 Skype 모임 브로드캐스트 사용

1. Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인 합니다.
    
2. 버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.
    
3. **Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.
    
4. 버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다. Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
5. 비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
6. **시작 메뉴**에서 **Windows PowerShell**을 선택 합니다.
    
7. **Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. 다음을 실행 하 여 현재 Skype 모임 브로드캐스트 구성을 확인 합니다.
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    매개 변수 _EnableBroadcastMeeting_ 가로 `False`설정 되어 있는지 확인 합니다.
    
     ![Skype 모임 브로드캐스트 조직 cmdlet을 사용 하도록 설정 합니다.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. 다음을 실행 하 여 조직에 대해 Skype 모임 브로드캐스트를 사용 하도록 설정 합니다.
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    다시 실행 `Get-CsBroadcastMeetingConfiguration` 하 여 설정을 사용 하도록 설정 했는지 확인할 수 있습니다.
    
     ![Skype 모임 브로드캐스트 조직 Cmdlet을 사용 하도록 설정 합니다.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 변경 후 Skype 모임 브로드캐스트 포털에 영향을 주는 데 시간이 걸릴 수 있습니다. 
  
10. 이제 사용자가 비즈니스의 다른 사용자와 브로드캐스트 모임을 보관할 수 있습니다. 시작 하려면 [Skype 모임 브로드캐스트를 선택](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) 하세요.
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>외부 참석자와의 모임을 브로드캐스트하도록 네트워크 구성

방화벽이 있고 회사 외부의 사람들과 브로드캐스트를 보관 하려는 경우 (페더레이션 비즈니스 사용자가 아닌 경우) 다음 지침을 사용 하 여 네트워크를 구성 해야 합니다. [Skype 모임 브로드캐스트에 맞게 네트워크를 설정](set-up-your-network-for-skype-meeting-broadcast.md)합니다. 
  
방화벽 구성에 대 한 경험이 없는 경우 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089) 를 고용 하 여이 단계를 수행 하는 것이 좋습니다.
  
이 단계를 건너뛰고 대신 다른 비즈니스를 페더레이션에 추가 하려면 [사용자가 외부 비즈니스용 Skype 사용자에 게 연락할 수 있도록 허용](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)을 참조 하세요. 
  
## <a name="related-topics"></a>관련 주제

[Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[비즈니스용 Skype 온라인 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
