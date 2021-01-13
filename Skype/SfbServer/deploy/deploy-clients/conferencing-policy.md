---
title: Skype 룸 시스템 계정에 대한 회의 정책
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: 이 항목을 읽고 Skype 채팅방 시스템 계정에 대한 회의 정책을 할당하는 방법을 배워야 합니다.
ms.openlocfilehash: 3fb462168bd4121f5feef365f881ed9f02620e25
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812728"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Skype 룸 시스템 계정에 대한 회의 정책
 
이 항목을 읽고 Skype 채팅방 시스템 계정에 대한 회의 정책을 할당하는 방법을 배워야 합니다.
  
## <a name="conferencing-policy-features"></a>회의 정책 기능

Skype 룸 시스템 계정에 할당된 회의 정책에는 특정 특성이 있어야 합니다. 대부분의 경우 Skype 룸 시스템 클라이언트는 예약된 모임에 참가하므로 모임 이끌이의 회의 정책이 전화 회의에 영향을 미치게 됩니다. 그러나 비즈니스용 Skype 서버에서는 특정 기능이 참가자의 구성에 따라 다릅니다. 예를 들어 참가자의 정책에서 최대 비디오 해상도를 1080p로 허용하는 경우 이끌이의 정책에서 허용하지 않는 경우에도 참가자는 회의에서 이 고해상도 비디오 기능을 경험하게 됩니다. 다음 표에서는 조직에서 Skype 룸 시스템 계정에 대한 회의 정책을 설정할 때 인식해야 하는 몇 가지 이러한 설정에 대해 설명합니다. 
  
|기능  <br/> |값  <br/> |댓글  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Skype 룸 시스템 오디오의 경우 true가 되어야 합니다.  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Skype 채팅방 시스템 오디오가 Skype 룸 시스템의 회의 시작(애드월) 화이트보드 세션에서 작동하려면 true가 되어야 합니다.  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Skype 룸 시스템에서 다중 보기, 여러 비디오 스트림을 렌더링할 수 있습니다.  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Skype 채팅방 시스템의 지금(애드월) 화이트보드 세션에 영향을 미치기  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Skype 채팅방 시스템의 지금(애드월) 화이트보드 세션에 영향을 미치기  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Skype 채팅방 시스템의 지금(애드월) 화이트보드 세션에 영향을 미치기  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Skype 채팅방 시스템의 지금(애드월) 화이트보드 세션에 영향을 미치기  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |계정이 EV(EV)Enterprise Voice(비즈니스용 Skype에 대한 Skype 채팅방 시스템 계정 사용 섹션 참조)에 따라 결정됩니다.  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |계정이 EV(Enterprise Voice)를 사용할 수 있는지 여부에 따라 결정됩니다.  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Skype 채팅방 시스템의 지금(애드월) 화이트보드 세션에 영향을 미치기  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Skype 채팅방 시스템의 지금(애드월) 화이트보드 세션에 영향을 미치기  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Skype 채팅방 시스템의 지금(애드월) 화이트보드 세션에 영향을 미치기  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Skype 채팅방 시스템의 지금(애드월) 화이트보드 세션에 영향을 미치기  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |모임 시작(애드문) 모임의 N/A이지만 Skype 룸 시스템은 회의실 앞의 화면에서 설문에 응답할 수 있습니다.  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |모임 시작(애드문) 모임의 N/A이지만 Skype 룸 시스템은 회의실 앞의 화면에서 설문에 응답할 수 있습니다.  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Skype 채팅방 시스템의 지금(애드월) 화이트보드 세션에 영향을 미치기  <br/> |
|EnableAppDesktopSharing  <br/> |데스크톱  <br/> |Skype 채팅방 시스템의 지금(애드월) 화이트보드 세션에 영향을 미치기  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |Skype 룸 시스템용 N/A입니다. TRUE인 경우 원격 사용자가 기록할 수 있습니다.  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |Skype 룸 시스템용 N/A입니다. TRUE인 경우 원격 사용자가 기록할 수 있습니다.  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |해당 없음  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |해당 없음  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Skype 룸 시스템 클라이언트가 피어 투 피어 비디오 세션에 참가할 수 있도록 설정  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |해당 없음  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Skype 채팅방 시스템의 지금(애드월) 화이트보드 세션에 영향을 미치기  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |비즈니스용 Skype 서버에서 무시, Skype 채팅방 시스템은 HD1080을 사용  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Skype 채팅방 시스템의 지금(애드월) 화이트보드 세션에 영향을 미치기  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |표의 끝에 있는 참고 사항 참조\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |허용되는 최대 아웃바운드 비디오 비트 속도입니다. Skype 룸 시스템은 이 비트 전송률로 하나의 1080 스트림과 함께 pano(RoundTable를 사용하는 경우)를 보낼 수 있습니다. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |표의 끝에 있는 참고 사항 참조\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |해당 없음  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |이 설정은 가능한 한 높음으로 설정하는 것이 좋습니다. 유효 대역폭은 회의 시의 네트워크 조건에 따라 달라 집니다.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |다중 보기 비디오 스트림을 확인하려면 Skype 룸 시스템에 대해 TRUE로 설정해야 합니다.  <br/> |
   
* 대역폭 계획에 대한 자세한 내용은 미디어 [트래픽에 대한 네트워크 대역폭 요구 사항을 참조하세요.](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)
  
> [!NOTE]
> Skype 룸 시스템 클라이언트가 Lync Server 2010 풀에 있는 사용자가 구성한 예약된 모임에 참가할 경우 모임 이끌이의 회의 정책으로 인해 Skype 룸 시스템 클라이언트가 공동 작업을 수행하지 못하게 할 수 있습니다. 
  
## <a name="meeting-authentication"></a>모임 인증

Skype 룸 시스템은 사용자가 모임 참가 링크를 사용하여 제한된 모임에 참가할 때 인증을 묻는 메시지를 사용자에게 제공합니다. 예를 들어 Outlook에서 모임 대기실 옵션이 구성된 모임이 있습니다. 이 설정은 사용자 지정된 모임에 대해 항상 설정하며 사용자에게 항상 메시지가 표시될 수 있습니다. 그러나 무제한 모임의 경우 사용자는 인증 없이 모임에 참가할 수 있습니다. 
  
다음 명령을 사용하면 관리자가 무제한 모임을 포함하여 모든 모임에 대해 인증을 요구할 수 있습니다. 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

기본적으로 RequireRoomSystemsAuthorization은 FALSE입니다. 
  

