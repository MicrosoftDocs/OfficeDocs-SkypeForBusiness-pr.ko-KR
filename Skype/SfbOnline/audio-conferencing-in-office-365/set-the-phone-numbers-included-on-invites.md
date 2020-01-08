---
title: 비즈니스용 Skype Online의 초대에 포함 된 전화 번호 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: '발신자가 비즈니스용 Skype Online 모임에 참가 하는 데 사용할 기본 전화 번호를 만드는 단계를 확인 하세요. '
ms.openlocfilehash: 33c2f69cbd05efedf5af1bb35c7ea5d560930da4
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962516"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>비즈니스용 Skype Online의 초대에 포함 된 전화 번호 설정

> [!Note]
> Microsoft 팀의 모임 초대 전화 번호에 대 한 자세한 내용은 [Microsoft 팀의 초대에 포함 된 전화 번호 설정을](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)참고 하세요.

Office 365의 오디오 회의를 통해 조직의 사용자가 비즈니스용 Skype 모임을 만든 다음 사용자가 휴대폰을 사용 하 여 해당 모임에 전화를 걸 수 있습니다. Office 365에서 Microsoft 오디오 회의 브리지 또는 ACP (승인 된 오디오 회의 공급자)에 의해 호스팅되는 타사 오디오 회의 브리지를 사용 하는 옵션이 있습니다.
  
> [!NOTE]
> 오디오 회의에 대 한 모든 전화 접속 번호 목록이 포함 된 리소스가 없습니다. 해당 지역 또는 국가/지역에서 전화 접속 전화 번호를 사용할 수 있는지 확인 하려는 경우 **비즈니스용 Skype 관리 센터** > **음성** > **전화 번호**를 사용 하 여 **추가** , **새 서비스 번호**를 차례로 클릭 합니다. **국가/지역**, **시/지역** , 구/군/ **시** 목록을 사용 하 여 검색을 필터링 합니다. 또한, > 무료 서비스 번호를 찾고 있는 경우에는 **상태/지역** 목록에서 무료 **통화** 를 선택 합니다.
  
회의 브리지는 조직의 전화 접속 전화 번호 집합을 제공 합니다. 이 모든 항목은 모임 이끌이가 만든 모임에 참가 하는 데 사용할 수 있지만 모임 초대에 포함 될 모임을 선택할 수 있습니다.
  
> [!NOTE]
> 모임 주최자에 대 한 모임 초대에는 최대 1 명의 유료 전화 번호와 한 명 이상의 무료 전화번호가 있을 수 있지만, 모임 참가에 사용할 수 있는 모든 전화 접속 전화 번호의 전체 목록을 여는 링크가 각 모임 초대의 맨 아래에 있는 링크 이기도 합니다. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>모임 이끌이의 기본 전화 접속 전화 번호 설정

1. 회사 또는 학교 계정으로 Office 365에 로그인 합니다.
    
2. **관리 센터** > **비즈니스용 Skype를**선택 합니다.
    
3. **사용자**를 선택 합니다.
    
    ![비즈니스용 Skype 관리 센터에서 사용자 선택을 표시 합니다.](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. 편집 하려는 사용자를 선택 합니다.
    
   - 단일 사용자를 선택 하려면 해당 사용자의 이름을 선택 합니다.
    
   - 페이지의 모든 사용자를 선택 하려면 목록 맨 위의 **표시 이름** 옆에 있는 상자를 선택 합니다.
    
   - 여러 사용자를 선택 하려면 각 사용자의 이름 옆에 있는 상자를 선택 합니다.
    
5. 오른쪽 창에서 **편집**을 선택 합니다.
    
    ![편집 아이콘을 선택 합니다.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. **오디오 회의**를 선택 합니다.
    
7. **속성** 페이지의 **공급자 이름** 목록에서 사용자의 공급자를 선택 합니다. 공급자에 따라 다음 상자를 완료 합니다.
    
   - **Microsoft는 공급자입니다**: **기본 유료 번호** 및 기본 무료 **번호** 목록을 사용 하 여 사용자의 기본 번호를 선택 합니다.
    
     > [!NOTE]
     > 무료 사용자의 기본 무료 전화 번호로 설정 하려면 먼저 하나 이상의 무료 번호를 회의 브리지에 할당 해야 합니다. 무료 전화 번호를 받으려면 [비즈니스용 Skype에 대 한 서비스 전화 번호 가져오기를](/microsoftteams/getting-service-phone-numbers)참조 하세요. 
  
   - **제 3 자는 공급자입니다**. **유료** 번호 및 무료 **번호** 필드를 사용 하 여 사용자의 번호를 입력 합니다.


## <a name="reset-audio-conferencing-phone-numbers"></a>오디오 회의 전화 번호 다시 설정

1. **비즈니스용 Skype 관리 센터**에서 **오디오 회의**를 선택 합니다.
    
2. 페이지 맨 위에 있는 **사용자**를 선택 합니다.
    
3. 다시 설정 하려는 사용자를 선택한 다음 작업 창에서 **지우기를**클릭 합니다.
    
기본적으로 사용자의 회의 설정을 변경 하면 사용자에 게 전자 메일이 전송 됩니다. 이를 변경 하려면 [오디오 회의 설정이 변경 되는 경우 전자 메일 보내기 사용 또는 사용 안 함을](enable-or-disable-sending-emails-when-their-settings-change.md)참조 하세요.
  
> [!IMPORTANT]
> 사용자의 오디오 회의 설정을 변경 하는 경우에는 되풀이 및 향후 비즈니스용 Skype 모임을 업데이트 하 고 참석자에 게 보내야 합니다. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?

- 시간을 절약 하거나이 작업을 자동화 하려면 [Set-get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet을 사용 하면 됩니다.
    
- [Get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet을 사용 하 여 특정 사용자의 기본 유료 또는 무료 전화 번호를 변경 합니다.
    
    사용자의 기본 무료 전화 번호를 변경 하려면 다음을 실행 합니다.
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- **CsOnlineDialInConferencingUserDefaultNumber** cmdlet을 사용 하 여 기본 유료 또는 수신자의 사용자 수를 원래의 기본 숫자나 해당 위치에 따라 변경 합니다.
    
    > [!NOTE]
    > BridgeID를 찾으려면 **CsOnlineDialInConferencingBridge** cmdlet을 사용 합니다.
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 1 ~ + 18005551234 없는 모든 사용자의 기본 무료 전화 번호를 설정 하려면 다음을 실행 합니다.
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - + 18005551234를 기본 무료 번호로 사용 하는 모든 사용자의 기본 무료 무료 전화 번호를 + 18005551239으로 변경 하려면 다음을 실행 합니다.
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 미국에 거주 하는 모든 사용자의 기본 무료 무료 전화 번호를 + 18005551234으로 설정 하려면 다음을 실행 합니다.
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 내용을 확인 하 고 싶으신가요?
- Windows PowerShell이 제공 되는 경우 사용자 및 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>관련 항목

[Office 365에서 오디오 회의 체험 또는 구매](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
