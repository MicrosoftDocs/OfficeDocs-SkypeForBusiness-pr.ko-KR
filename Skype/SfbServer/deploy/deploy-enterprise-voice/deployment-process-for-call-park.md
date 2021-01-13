---
title: 비즈니스용 Skype의 통화 파크 배포 프로세스
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
description: 비즈니스용 Skype 서버 2013의 통화 파크 배포 프로세스 및 Enterprise Voice.
ms.openlocfilehash: 0ddc46c391d362fde922e682db0813ad1c0d72bd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812358"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>비즈니스용 Skype의 통화 파크 배포 프로세스
 
비즈니스용 Skype 서버 2013의 통화 파크 배포 프로세스 및 Enterprise Voice.
  
통화 파킹을 Enterprise Voice 사용자가 한 전화에서 통화를 보류한 다음 나중에 모든 전화에서 내부 번호(통화 파킹된 통화 번호)로 전화를 걸면 통화를 다시 검색할 수 있습니다.
  
통화 파크에서 사용하는 구성 요소는 통화를 배포할 때 프런트 엔드 서버 또는 Standard Edition 서버에 자동으로 설치되고 Enterprise Voice. 그러나 사용자가 통화를 사용할 수 있도록 설정하려면 먼저 다음 단계를 사용하여 통화 파크를 구성해야 합니다. 
  
**통화 대기 배포 프로세스**

|**작업 단계**|**단계**|**필수 그룹 및 역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|파킹된 통화 번호 표에서 통화 대기 파킹된 통화 번호 범위 구성  <br/> |비즈니스용 Skype 서버 제어판 또는 **New-CSCallParkOrbit** cmdlet을 사용하여 통화 파킹된 통화 걸기 표에서 파킹된 통화 걸기 범위를 만든 다음 통화 파킹된 응용 프로그램을 호스팅하는 응용 프로그램 서비스에 연결합니다. <br/> **참고:** 기존 다이얼 플랜과 원활하게 통합하기 위해, 통화 번호 범위는 일반적으로 가상 내선 번호 블록으로 구성됩니다. DID(Direct Inward Dialing) 번호를 통화 대기 파킹된 통화 번호 표에서 파킹된 통화 번호로 할당할 수는 없습니다. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype에서 통화 파크 궤도 범위 만들기 또는 수정](create-or-modify-a-call-park-orbit-range.md) <br/> |
|통화 파킹 설정 구성  <br/> | **Set-CsCpsConfiguration** cmdlet을 사용하여 통화 파킹 설정을 구성합니다. 최소한 **OnTimeoutURI** 옵션을 구성하여 통화가 시간 제한이 짧을 때 사용할 콜백 대상을 구성하는 것이 좋습니다. 다음 설정을 구성할 수 있습니다. <br/>  (선택 사항) **EnableMusicOnHold** - 대기 음악을 사용하거나 사용하지 않도록 설정합니다. <br/>  (선택 사항) **MaxCallPickupAttempts** - 대기된 통화를 대체 URI(Uniform Resource Identifier)로 착신 전환할 때까지 해당 통화가 전화기에서 다시 울리는 횟수를 결정합니다. <br/>  (선택 사항) **CallPickupTimeoutThreshold** - 통화가 대기된 후부터 전화를 받은 전화기가 다시 울릴 때까지의 경과 시간을 결정합니다. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype에서 통화 파크 설정 구성](configure-call-park-settings.md) <br/> |
|원하는 경우 대기 음악을 사용자 지정합니다.  <br/> |**Set-CsCallParkServiceMusicOnHoldFile** cmdlet을 사용하여 오디오 파일을 사용자 지정하고 업로드합니다(기본 대기 음악을 사용하지 않으려는 경우) <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 통화 파킹된 통화 음악 사용자 지정](customize-call-park-music-on-hold.md) <br/> |
|사용자에 대해 통화 파크를 사용하도록 음성 정책 구성  <br/> |비즈니스용 Skype 서버 제어판 또는 **EnableCallPark** 옵션과 함께 **Set-CSVoicePolicy** cmdlet을 사용하여 음성 정책에서 사용자에 대해 통화 파킹을 사용하도록 설정할 수 있습니다. <br/> 기본적으로 모든 사용자에 대해 통화 파크는 사용하지 않도록 설정됩니다.  <br/> 음성 정책이 여러 개인 경우에는 기본 정책뿐 아니라 각 음성 정책에 대해 EnableCallPark 속성이 설정되어 있는지 확인합니다.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype에서 사용자에 대해 통화 파크 사용](enable-call-park-for-users.md) <br/> |
|통화 파킹에 대한 정규화 규칙 확인  <br/> |통화 대기 파킹된 통화 번호는 정규화해서는 안 됩니다. 정규화 규칙에 파킹된 통화 번호 범위가 포함되어 있지 않은지 확인하고, 필요한 경우에는 파킹된 통화 번호가 정규화되지 않도록 추가 정규화 규칙을 만드십시오.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype에서 통화 파크에 대한 정규화 규칙 확인](verify-normalization-rules-for-call-park.md) <br/> |
|통화 파크 배포 확인  <br/> |통화를 파킹하고 검색하여 구성이 예상대로 작동하는지 테스트합니다.  <br/> |-  <br/> |[(선택 사항) 비즈니스용 Skype에서 통화 파크 배포 확인](optional-verify-call-park-deployment.md) <br/> |
   

