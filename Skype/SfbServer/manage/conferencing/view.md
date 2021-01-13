---
title: 비즈니스용 Skype 서버에서 회의 정책 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: '요약: 비즈니스용 Skype 서버에서 회의 정책을 보는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 39b37a1335f8b257f9dec1fff28bea90ac7a6db9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817508"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 회의 정책 보기
 
**요약:** 비즈니스용 Skype 서버에서 회의 정책을 보는 방법에 대해 자세히 알아보습니다.
  
비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책을 볼 수 있습니다.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype 서버 제어판을 사용하여 회의 정책 보기

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 회의를 클릭한 다음 회의 **정책을 클릭합니다.**
    
4. 회의 정책 **페이지에서** 보게 될 회의 정책을 두 번 클릭합니다.
    
5. 파일 **필터 편집에서** 세부 정보 **표시 확인란을** 선택합니다.
    
    **회의 정책 편집 - \<policy\>** 선택한 정책에 대한 설정이 표시됩니다.
    
    설정을 구성하는 데 대한 자세한 내용은 비즈니스용 Skype 서버에서 회의 정책 [만들기를 참조하세요.](create-policies.md)
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype 서버 관리 셸을 사용하여 회의 정책 보기

회의 정책을 보기 위해 **Get-CsConferencingPolicy** cmdlet을 사용 합니다.
  
```PowerShell
Get-CsConferencingPolicy
```

이 cmdlet은 다음과 같은 정보를 반환합니다.
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

전체 구문 설명 및 매개 변수 목록을 비롯한 자세한 내용은 [Get-CsConferencingPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)
  

