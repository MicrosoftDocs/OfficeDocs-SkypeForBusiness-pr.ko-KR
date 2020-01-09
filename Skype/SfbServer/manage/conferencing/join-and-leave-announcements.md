---
title: 비즈니스용 Skype 서버에서 컨퍼런스 참가 및 공지 사항 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: '요약: 비즈니스용 Skype 서버에서 컨퍼런스 참가 및 알림을 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 5c2bc7175f99ee50e94bee26ef0e6d54a6a8db5a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991833"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 컨퍼런스 참가 및 공지 사항 관리
 
**요약:** 비즈니스용 Skype 서버에서 컨퍼런스 참가를 관리 하 고 알림을 남기기 위한 방법을 알아봅니다.
  
전화 접속 사용자가 회의에 참가 하거나 나갈 때, 회의 알림 응용 프로그램은 소리를 재생 하거나 자신의 이름을 말하기 때문에 해당 입구 또는 종료를 알릴 수 있습니다. 비즈니스용 Skype Server Management Shell 및 다음 매개 변수를 사용 하 여 **CsDialinConferencing** cmdlet을 사용 하 여 알림이 작동 하는 방식을 변경할 수 있습니다.
  
- EnableNameRecording-회의를 시작 하기 전에 익명 참가자가 자신의 이름을 기록 하도록 요청 했는지 여부를 결정 합니다. 기본값은 "$true" 이며,이는 익명 참가자가 회의에 참가할 때 이름을 명시 하 라는 메시지를 표시 하는 것을 의미 합니다. (인증 된 참가자는 해당 사용자의 표시 이름이 대신 사용 되므로 이름을 기록 하지 않습니다.)
    
- EntryExitAnnouncementsEnabledByDefault-알림을 기본적으로 설정 또는 해제 하는지 여부를 나타냅니다. 기본값은 "$false" 이며,이는 기본적으로 참가자가 회의에 참가 하거나 나갈 때 공지 사항이 없음을 의미 합니다. 모임 이끌이는 모임을 예약할 때이 설정을 무시할 수 있습니다.
    
- EntryExitAnnouncementsType-참가자가 알림을 사용할 수 있도록 전화 회의에 참가 하거나 떠날 때마다 수행 되는 작업을 나타냅니다. 기본값은 "UseNames" 이며, 공지 사항이 설정 된 경우 ": 진구 Myer 님이 회의에 참가 했습니다" 라는 알림을 의미 합니다.
    
전역 범위 또는 사이트 범위에서 이러한 설정을 구성할 수 있습니다. 사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 합니다.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>회의 참가를 수정 하 고 알림 동작을 종료 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 명령 프롬프트에서 다음을 실행 합니다.
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

이 cmdlet은 참가자가 전화 접속 회의에 참가 하거나 나갈 때 비즈니스용 Skype 서버가 응답 하는 방법 및 회의 참가 시 사용자의 이름을 기록 하는 데 필요한 지 여부에 대 한 정보를 검색 합니다.
    
4. 명령 프롬프트에서 다음을 실행 합니다.
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

다음 예제에서는 사이트 범위에서 Redmond에 대 한 설정을 구성 합니다. 알림은 설정 되어 있지만 참가자가 회의에 참가할 때 이름을 말할 것인지 묻는 메시지가 표시 되지 않습니다. 참가자가 회의를 시작 하거나 종료할 때 신호음이 재생 됩니다.
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

구문 및 전체 매개 변수 목록을 비롯 한 자세한 내용은 [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)를 참조 하세요.
  

