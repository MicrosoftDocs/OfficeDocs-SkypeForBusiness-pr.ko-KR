---
title: 비즈니스용 Skype의 통화 공원 배포 프로세스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 비즈니스용 Skype Server Enterprise Voice의 통화 파킹에 대 한 배포 프로세스 및 단계.
ms.openlocfilehash: e0e0559a99160bad06379751cbc0bb89fb882c20
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767481"
---
# <a name="deployment-process-for-call-park-in-skype-for-business"></a>비즈니스용 Skype의 통화 공원 배포 프로세스
 
비즈니스용 Skype Server Enterprise Voice의 통화 파킹에 대 한 배포 프로세스 및 단계.
  
통화 대기-엔터프라이즈 음성 사용자는 전화를 걸 수 있으며, 나중에 모든 전화기에서 내부 번호 (통화 공원 회전 이라고 함)로 전화를 걸어 전화를 겁니다.
  
통화 대기를 사용 하는 구성 요소는 엔터프라이즈 음성을 구축할 때 프런트 엔드 서버 또는 Standard Edition 서버에서 자동으로 설치 되 고 사용 하도록 설정 됩니다. 그러나 사용자에 게 전화를 걸 수 있으려면 다음 단계를 사용 하 여 통화 대기를 구성 해야 합니다. 
  
**통화 파킹 배포 프로세스**

|**단계의**|**방법은**|**필수 그룹 및 역할**|**배포 설명서**|
|:-----|:-----|:-----|:-----|
|궤도 테이블에서 통화 공원 궤도 범위 구성  <br/> |비즈니스용 Skype Server 제어판 또는 **CSCallParkOrbit** cmdlet을 사용 하 여 통화 공원 궤도 표에 궤도 범위를 만들고이를 통화 공원 응용 프로그램을 호스팅하는 응용 프로그램 서비스와 연결 합니다. <br/> **참고:** 기존 다이얼 플랜을 완벽 하 게 통합 하기 위해 일반적으로 궤도 범위는 가상 확장 블록으로 구성 됩니다. 직접 연결 된 전화 접속 (연결) 번호를 통화 공원 궤도 테이블의 궤도 번호로 지정 하는 것은 지원 되지 않습니다. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype에서 통화 공원 궤도 범위 만들기 또는 수정](create-or-modify-a-call-park-orbit-range.md) <br/> |
|통화 파킹 설정 구성  <br/> | **CsCpsConfiguration** cmdlet을 사용 하 여 통화 공원 설정을 구성 합니다. 적어도 파킹 된 통화 시간 초과 시 사용할 대체 대상을 구성 하려면 **Ontimeouturi** 옵션을 구성 하는 것이 좋습니다. 다음 설정을 구성할 수도 있습니다. <br/>  ) **Enablemusiconhold** 대기 음악을 사용 하거나 사용 하지 않도록 설정 합니다. <br/>  ) **MaxCallPickupAttempts** 호출을 URI (Fallback Uniform resource Identifier)로 전달 하기 전에 파킹 된 통화가 응답 전화로 다시 연결 하는 횟수를 확인 합니다. <br/>  ) 통화에 응답 한 전화기로 전화를 **CallPickupTimeoutThreshold** 전에 대기 하는 시간을 결정 합니다. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype에서 통화 공원 설정 구성](configure-call-park-settings.md) <br/> |
|선택적으로 음악을 보류할 때 사용자 지정  <br/> |기본 음악을 누르고 싶지 않은 경우 **CsCallParkServiceMusicOnHoldFile** cmdlet을 사용 하 여 오디오 파일을 사용자 지정 하 고 업로드 합니다. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[통화 대기 음악 사용자 지정 (비즈니스용 Skype for Business)](customize-call-park-music-on-hold.md) <br/> |
|사용자에 게 전화를 걸 수 있도록 음성 정책 구성  <br/> |비즈니스용 Skype Server 제어판 또는 **EnableCallPark** 옵션과 함께 **CSVoicePolicy** cmdlet을 사용 하 여 음성 정책 사용자에 대 한 통화 대기를 사용 하도록 설정 합니다. <br/> 기본적으로 모든 사용자에 대해 통화 대기를 사용할 수 없습니다.  <br/> 여러 음성 정책을 사용 하는 경우 기본 정책만이 아니라 각 음성 정책에 대해 EnableCallPark 속성이 설정 되어 있는지 확인 합니다.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsUserAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype에서 사용자에 게 통화 공원 사용](enable-call-park-for-users.md) <br/> |
|통화 대기에 대한 정규화 규칙 확인  <br/> |통화 공원 orbits는 정규화 해서는 안 됩니다. 정규화 규칙에 궤도 범위 중 어느 것도 포함 되어 있지 않은지 확인 합니다. 필요한 경우 orbits의 정규화를 방지 하는 추가 정규화 규칙을 만듭니다.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[비즈니스용 Skype에서 통화 공원에 대 한 정규화 규칙 확인](verify-normalization-rules-for-call-park.md) <br/> |
|통화 공원 배포 확인  <br/> |주차장 및 통화 검색을 테스트 하 여 구성이 예상 대로 작동 하는지 확인 합니다.  <br/> |-  <br/> |[) 비즈니스용 Skype에서 통화 공원 배포 확인](optional-verify-call-park-deployment.md) <br/> |
   

