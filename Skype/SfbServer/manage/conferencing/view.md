---
title: 2013에서 회의 정책 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: '요약: 2013에서 회의 정책을 보는 비즈니스용 Skype 서버.'
---

# <a name="view-conferencing-policies-in-skype-for-business-server"></a>2013에서 회의 정책 비즈니스용 Skype 서버
 
**요약:** 2013에서 회의 정책을 보는 방법을 비즈니스용 Skype 서버.
  
회의 정책은 제어판을 사용하여 보거나 비즈니스용 Skype 서버 관리 셸을 사용하여 비즈니스용 Skype 서버 있습니다.
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 회의 비즈니스용 Skype 서버 보기

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2.  제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 회의를 **클릭한** 다음 회의 정책을 **클릭합니다**.
    
4. 회의 **정책** 페이지에서 보게 될 회의 정책을 두 번 클릭합니다.
    
5. 파일 **필터 편집에서** 자세한 정보 **표시 확인** 란을 선택합니다.
    
    **회의 정책 편집 - \<policy\>** 를 열면 선택한 정책에 대한 설정이 표시됩니다.
    
    설정 구성에 대한 자세한 내용은 [Create conferencing policies in 비즈니스용 Skype 서버](create-policies.md).
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 회의 비즈니스용 Skype 서버 보기

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

전체 구문 설명 및 매개 변수 목록을 포함하여 자세한 내용은 [Get-CsConferencingPolicy를 참조하십시오](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).
