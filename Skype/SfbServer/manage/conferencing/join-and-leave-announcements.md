---
title: 회의 참가 및 나가기 공지 사항을 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: '요약: 회의 참가 및 퇴장 공지 사항을 관리하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: f2219fc8d55485a4c34a8730fbec6b556d57b728
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625210"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>회의 참가 및 나가기 공지 사항을 비즈니스용 Skype 서버
 
**요약:** 회의 참가 및 퇴장 공지 사항을 관리하는 방법을 비즈니스용 Skype 서버.
  
전화 접속 사용자가 회의에 참가하거나 회의에서 나서면 회의 알림 애플리케이션 재생하거나 이름을 말하여 입장 또는 퇴장할 수 있습니다. 다음 매개 변수와 함께 비즈니스용 Skype 서버 **Set-CsDialinConferencing** cmdlet을 사용하여 공지 사항의 작동 방법을 변경할 수 있습니다.
  
- EnableNameRecording - 회의에 입장하기 전에 익명 참가자에게 이름을 기록하도록 요구할지 여부를 지정합니다. 기본값은 "$true"입니다. 즉, 회의에 참가할 때 익명 참가자에게 이름을 입력하라는 메시지가 표시됩니다. 인증된 참가자는 표시 이름이 대신 사용되지 때문에 이름을 기록하지 않습니다.
    
- EntryExitAnnouncementsEnabledByDefault - 기본적으로 공지 사항을 켜거나 끄는지 여부를 나타냅니다. 기본값은 "$false"입니다. 즉, 참가자가 회의에 참가하거나 회의에서 나간 경우 기본적으로 공지가 없습니다. 모임 이끌이는 모임을 계획할 때 이 설정을 오버라이드할 수 있습니다.
    
- EntryExitAnnouncementsType - 참가자가 발표가 사용하도록 설정된 회의에 참가하거나 회의에서 나설 때마다 수행되는 작업을 나타냅니다. 기본값은 "UseNames"입니다. 즉, 공지가 켜져 있는 경우 "Ken Myer가 회의에 참가했습니다."라는 공지가 있습니다.
    
이러한 설정은 전역 범위나 사이트 범위에서 구성할 수 있습니다. 사이트 범위에서 구성된 설정이 전역 범위에서 구성된 설정보다 우선합니다.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>회의 입장 및 퇴장 알림 동작을 수정하려면

1. RTCUniversalServerAdmins 그룹의 구성원이나 Cs-ServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 명령 프롬프트에서 다음을 실행합니다.
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

이 cmdlet은 참가자가 전화 회의에 참가할 때 이름을 기록해야 하는지 여부와 참가자가 전화 접속 회의에 참가하거나 퇴장할 비즈니스용 Skype 서버 응답하는 방법에 대한 정보를 검색합니다.
    
4. 명령 프롬프트에서 다음을 실행합니다.
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

다음 예제에서는 Redmond의 사이트 범위에서 설정을 구성합니다. 알림이 설정되었지만 참가자가 회의에 참가할 때 이름을 얘기하라는 메시지가 표시되지 않습니다. 참가자가 회의에 입장 또는 퇴장할 때 신호음이 재생됩니다.
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

구문과 전체 매개 변수 목록을 비롯한 자세한 내용은 [Set-CsDialInConferencingConfiguration을 참조하십시오.](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)
