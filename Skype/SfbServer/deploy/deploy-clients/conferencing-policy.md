---
title: Skype 대화방 시스템 계정에 대 한 회의 정책
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Skype 대화방 시스템 계정에 대 한 회의 정책을 할당 하는 방법을 알아보려면이 항목을 읽으십시오.
ms.openlocfilehash: 1ffa0065f6df27edb4b5e0bfd39564728ee0a582
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769102"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Skype 대화방 시스템 계정에 대 한 회의 정책
 
Skype 대화방 시스템 계정에 대 한 회의 정책을 할당 하는 방법을 알아보려면이 항목을 읽으십시오.
  
## <a name="conferencing-policy-features"></a>회의 정책 기능

Skype 채팅방 시스템 계정에 할당 된 회의 정책은 특정 특성을 가져야 합니다. 대부분의 경우 Skype 대화방 시스템 클라이언트는 예약 된 모임에 참가 하므로 모임 이끌이의 회의 정책은 회의에 영향을 줍니다. 그러나 비즈니스용 Skype 서버에서 특정 접근 권한 값은 참가자의 구성에 따라 달라 집니다. 예를 들어 참가자의 정책에서 1080p의 최대 비디오 해상도를 허용 하는 경우 참가자는 이끌이의 정책에서 허용 하지 않는 경우에도 더 높은 해상도의 비디오 기능을 경험할 수 있습니다. 다음 표에서는 조직의 Skype 대화방 시스템 계정에 대 한 회의 정책을 설정할 때 알아야 하는 몇 가지 해당 설정에 대해 설명 합니다. 
  
|기능  <br/> |값  <br/> |댓글을  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |FALSE  <br/> |Skype 채팅방 시스템 오디오에 대해 참 이어야 합니다.  <br/> |
|AllowIPVideo  <br/> |FALSE  <br/> |Skype 채팅방 시스템의 지금 모임 시작 (ad hoc) 화이트 보드 세션에서 작업 하려면 Skype 대화방 시스템 오디오가 참 이어야 합니다.  <br/> |
|AllowMultiView  <br/> |FALSE  <br/> |Skype 채팅방 시스템에서 다중 보기, 여러 비디오 스트림을 렌더링할 수 있습니다.  <br/> |
|AllowParticipantControl  <br/> |FALSE  <br/> |Skype 대화방 시스템에서 모임 시작 (임시) 화이트 보드 세션에 영향을 줍니다.  <br/> |
|AllowAnnotations  <br/> |FALSE  <br/> |Skype 대화방 시스템에서 모임 시작 (임시) 화이트 보드 세션에 영향을 줍니다.  <br/> |
|DisablePowerPointAnnotations  <br/> |해제  <br/> |Skype 대화방 시스템에서 모임 시작 (임시) 화이트 보드 세션에 영향을 줍니다.  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |FALSE  <br/> |Skype 대화방 시스템에서 모임 시작 (임시) 화이트 보드 세션에 영향을 줍니다.  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |해제  <br/> |계정이 Enterprise Voice (EV)를 사용 하도록 설정 되어 있는지 여부에 따라 달라 집니다 (비즈니스용 Skype에 대 한 Skype 대화방 시스템 계정 사용 섹션 참조).  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |해제  <br/> |계정이 EV (Enterprise Voice)을 사용할 수 있는지 여부에 따라 달라 집니다.  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |FALSE  <br/> |Skype 대화방 시스템에서 모임 시작 (임시) 화이트 보드 세션에 영향을 줍니다.  <br/> |
|AllowExternalUsersToSaveContent  <br/> |FALSE  <br/> |Skype 대화방 시스템에서 모임 시작 (임시) 화이트 보드 세션에 영향을 줍니다.  <br/> |
|AllowExternalUserControl  <br/> |해제  <br/> |Skype 대화방 시스템에서 모임 시작 (임시) 화이트 보드 세션에 영향을 줍니다.  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |해제  <br/> |Skype 대화방 시스템에서 모임 시작 (임시) 화이트 보드 세션에 영향을 줍니다.  <br/> |
|AllowPolls  <br/> |FALSE  <br/> |모임 시작 (광고 hoc) 모임의 경우 해당 없음 Skype 채팅방 시스템은 채팅방 앞 화면에서 설문에 응답할 수 있습니다.  <br/> |
|AllowSharedNotes  <br/> |FALSE  <br/> |모임 시작 (광고 hoc) 모임의 경우 해당 없음 Skype 채팅방 시스템은 채팅방 앞 화면에서 설문에 응답할 수 있습니다.  <br/> |
|EnableDialInConferencing  <br/> |FALSE  <br/> |Skype 대화방 시스템에서 모임 시작 (임시) 화이트 보드 세션에 영향을 줍니다.  <br/> |
|EnableAppDesktopSharing  <br/> |데스크톱이  <br/> |Skype 대화방 시스템에서 모임 시작 (임시) 화이트 보드 세션에 영향을 줍니다.  <br/> |
|AllowConferenceRecording  <br/> |해제  <br/> |Skype 실 시스템의 경우 해당 없음 TRUE 이면 원격 상대방이 녹화할 수 있습니다.  <br/> |
|EnableP2PRecording  <br/> |해제  <br/> |Skype 실 시스템의 경우 해당 없음 TRUE 이면 원격 상대방이 녹화할 수 있습니다.  <br/> |
|EnableFileTransfer  <br/> |FALSE  <br/> |해당 없음  <br/> |
|EnableP2PFileTransfer  <br/> |FALSE  <br/> |해당 없음  <br/> |
|EnableP2PVideo  <br/> |FALSE  <br/> |Skype 대화방 시스템 클라이언트가 피어 투 피어 비디오 세션에 참가할 수 있습니다.  <br/> |
|AllowLargeMeetings  <br/> |해제  <br/> |해당 없음  <br/> |
|EnableDataCollaboration  <br/> |FALSE  <br/> |Skype 대화방 시스템에서 모임 시작 (임시) 화이트 보드 세션에 영향을 줍니다.  <br/> |
|MaxVideoConferenceResolution  <br/> |비디오  <br/> |비즈니스용 Skype 서버에서 무시 됨, Skype 채팅방 시스템은 HD1080를 사용 합니다.  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Skype 대화방 시스템에서 모임 시작 (임시) 화이트 보드 세션에 영향을 줍니다.  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |표 끝에 있는 참고 참조\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |허용 되는 최대 아웃 바운드 비디오 비트 전송률입니다. Skype 채팅방 시스템은이 비트 전송률으로 RoundTable o (사용 되는 경우)와 함께 1 1080 스트림을 전송할 수 있습니다. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |표 끝에 있는 참고 참조\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |해당 없음  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |2만  <br/> |가능한 한 높게 설정 하는 것이 좋습니다. 유효 대역폭은 회의가 끝날 때 네트워크 조건에 따라 달라 집니다.\*  <br/> |
|EnableMultiViewJoin  <br/> |FALSE  <br/> |다중 보기 비디오 스트림을 위해 Skype 대화방 시스템에 적용 해야 합니다.  <br/> |
   
* 대역폭 계획에 대 한 자세한 내용은 [미디어 트래픽에 대 한 네트워크 대역폭 요구 사항을](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)참조 하세요.
  
> [!NOTE]
> Skype 대화방 시스템 클라이언트가 Lync Server 2010 풀에 속한 사용자가 구성한 예약 된 모임에 참가 하려고 시도 하는 경우 모임 이끌이의 회의 정책에 따라 Skype 대화방 시스템 클라이언트가 공동 작업을 수행 하지 못할 수 있습니다. 
  
## <a name="meeting-authentication"></a>모임 인증

Skype 대화방 시스템은 모임 참가 링크를 사용 하 여 제한 된 모임에 참가할 때 사용자에 게 인증을 요청 합니다. 예를 들어 Outlook에서 모임 로비 옵션이 구성 된 모임입니다. 이 설정은 사용자 지정 된 모임에 대해 항상 켜져 있으며, 사용자에 게 항상 메시지가 표시 됩니다. 그러나 무제한 모임에서는 사용자가 인증 없이 모임에 참가할 수 있습니다. 
  
다음 명령을 사용 하 여 관리자는 무제한 모임 등 모든 모임에 대해 인증을 요구할 수 있습니다. 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

기본적으로 RequireRoomSystemsAuthorization은 FALSE입니다. 
  

